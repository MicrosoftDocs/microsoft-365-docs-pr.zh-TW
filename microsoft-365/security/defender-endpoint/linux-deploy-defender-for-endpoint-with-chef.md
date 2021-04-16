---
title: 如何使用 Chef 在 Linux 上部署適用于端點的 Defender
description: 瞭解如何使用 Chef 在 Linux 上部署適用于端點的 Defender
keywords: 'microsoft、defender、atp、linux、掃描、防病毒、microsoft defender for endpoint (linux) '
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 362222e4737b1a8dd6b8a0a284bf3bfb1903c288
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861441"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>使用 Chef 在 Linux 上部署用於端點的 Defender

開始之前：

- 若尚未安裝解壓縮，請安裝解壓縮。 已安裝 Chef 元件，且已存在 Chef 存放庫 (Chef 產生 <reponame> 存放庫) ，用來儲存將用來在 Chef Managed Linux server 上為端點部署至 Defender 的菜譜。

您可以從 chef 存放庫中的 cookbooks 資料夾內部執行下列命令，以在現有的存放庫中建立新的菜譜：</br>
`chef generate cookbook mdatp`

這個命令會為名為 mdatp 的新菜譜建立新的資料夾結構。  您也可以使用現有的菜譜（如果您已有的話），以將 MDE 部署新增至中。
在建立菜譜之後，請在剛剛建立的菜譜資料夾中建立 files 資料夾：

`mkdir mdatp/files`

將可從 Microsoft Defender Security Center 入口網站下載的 Linux Server 上架 zip 檔案，轉移至此新的 files 資料夾。

在 Chef 工作站上，流覽至 [mdatp/食譜] 資料夾。 當產生菜譜時，就會建立此資料夾。 使用您偏好的文字編輯器 (例如 vi 或 nano) ，將下列指示新增至預設的 rb 檔案的結尾：
-   include_recipe '：： onboard_mdatp '
- include_recipe '：： install_mdatp '

然後儲存並關閉預設的 rb 檔案。
接下來，在食譜資料夾中建立名為 install_mdatp 的新食譜檔案，並將此文字新增至檔案：

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

您必須修改版本號碼、發佈和儲存機制名稱，使其符合您要部署的版本，以及您想要部署的通道。
接下來，您應該在 mdatp/recipies 資料夾中建立 onboard_mdatp rb 檔案。  將下列文字新增至該檔案：

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

請務必將路徑名稱更新為上架檔案的位置。
若要測試在 Chef 工作站上部署它，只要執行 ``sudo chef-client -z -o mdatp`` 。
部署之後，您應該考慮根據  [設定 Microsoft DEFENDER ATP For Linux-Windows 安全性 | 中的設定，建立及部署設定檔至伺服器。Microsoft](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences)檔。  
在您建立及測試您的設定檔之後，您可以將它放在您也放置該上架套件的 [菜譜/mdatp/files] 資料夾中。  然後，您可以在 mdatp/recipies 資料夾中建立 settings_mdatp rb 檔案，並新增此文字：

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

若要在食譜中包含此步驟，只需將 include_recipe '：： settings_mdatp ' 新增至食譜資料夾內的預設 rb 檔。
您也可以使用 crontab 排程自動更新 [排程更新 Microsoft Defender For Endpoint (Linux) ](linux-update-MDE-Linux.md)。

卸載 MDATP 手冊：

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

