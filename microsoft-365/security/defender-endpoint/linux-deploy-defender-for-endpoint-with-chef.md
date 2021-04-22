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
ms.openlocfilehash: aa699aae24b1e6383f5a2afbe7fce31e0f53805c
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903925"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="1547d-104">使用 Chef 在 Linux 上部署適用於端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="1547d-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="1547d-105">開始之前：</span><span class="sxs-lookup"><span data-stu-id="1547d-105">Before you begin:</span></span>

- <span data-ttu-id="1547d-106">若尚未安裝解壓縮，請安裝解壓縮。</span><span class="sxs-lookup"><span data-stu-id="1547d-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="1547d-107">已安裝 Chef 元件，且已存在 Chef 存放庫 (Chef 產生 <reponame> 存放庫) ，用來儲存將用來在 Chef Managed Linux server 上為端點部署至 Defender 的菜譜。</span><span class="sxs-lookup"><span data-stu-id="1547d-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="1547d-108">您可以從 chef 存放庫中的 cookbooks 資料夾內部執行下列命令，以在現有的存放庫中建立新的菜譜：</span><span class="sxs-lookup"><span data-stu-id="1547d-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="1547d-109">這個命令會為名為 mdatp 的新菜譜建立新的資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="1547d-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="1547d-110">您也可以使用現有的菜譜（如果您已有的話），以將 MDE 部署新增至中。</span><span class="sxs-lookup"><span data-stu-id="1547d-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="1547d-111">在建立菜譜之後，請在剛剛建立的菜譜資料夾中建立 files 資料夾：</span><span class="sxs-lookup"><span data-stu-id="1547d-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="1547d-112">將可從 Microsoft Defender Security Center 入口網站下載的 Linux Server 上架 zip 檔案，轉移至此新的 files 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1547d-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="1547d-113">在 Chef 工作站上，流覽至 [mdatp/食譜] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1547d-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="1547d-114">當產生菜譜時，就會建立此資料夾。</span><span class="sxs-lookup"><span data-stu-id="1547d-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="1547d-115">使用您偏好的文字編輯器 (例如 vi 或 nano) ，將下列指示新增至預設的 rb 檔案的結尾：</span><span class="sxs-lookup"><span data-stu-id="1547d-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="1547d-116">include_recipe '：： onboard_mdatp '</span><span class="sxs-lookup"><span data-stu-id="1547d-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="1547d-117">include_recipe '：： install_mdatp '</span><span class="sxs-lookup"><span data-stu-id="1547d-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="1547d-118">然後儲存並關閉預設的 rb 檔案。</span><span class="sxs-lookup"><span data-stu-id="1547d-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="1547d-119">接下來，在食譜資料夾中建立名為 install_mdatp 的新食譜檔案，並將此文字新增至檔案：</span><span class="sxs-lookup"><span data-stu-id="1547d-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

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

<span data-ttu-id="1547d-120">您必須修改版本號碼、發佈和儲存機制名稱，使其符合您要部署的版本，以及您想要部署的通道。</span><span class="sxs-lookup"><span data-stu-id="1547d-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="1547d-121">接下來，您應該在 mdatp/recipies 資料夾中建立 onboard_mdatp rb 檔案。</span><span class="sxs-lookup"><span data-stu-id="1547d-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="1547d-122">將下列文字新增至該檔案：</span><span class="sxs-lookup"><span data-stu-id="1547d-122">Add the following text to that file:</span></span>

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

<span data-ttu-id="1547d-123">請務必將路徑名稱更新為上架檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="1547d-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="1547d-124">若要測試在 Chef 工作站上部署它，只要執行 ``sudo chef-client -z -o mdatp`` 。</span><span class="sxs-lookup"><span data-stu-id="1547d-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="1547d-125">部署之後，您應該考慮根據  [Linux 上 Microsoft Defender For Endpoint 的設定偏好](/linux-preferences.md)，針對伺服器建立及部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="1547d-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender for Endpoint on Linux](/linux-preferences.md).</span></span>  
<span data-ttu-id="1547d-126">在您建立及測試您的設定檔之後，您可以將它放在您也放置該上架套件的 [菜譜/mdatp/files] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1547d-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="1547d-127">然後，您可以在 mdatp/recipies 資料夾中建立 settings_mdatp rb 檔案，並新增此文字：</span><span class="sxs-lookup"><span data-stu-id="1547d-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

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

<span data-ttu-id="1547d-128">若要在食譜中包含此步驟，只需將 include_recipe '：： settings_mdatp ' 新增至食譜資料夾內的預設 rb 檔。</span><span class="sxs-lookup"><span data-stu-id="1547d-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="1547d-129">您也可以使用 crontab 排程自動更新 [排程更新 Microsoft Defender For Endpoint (Linux) ](linux-update-MDE-Linux.md)。</span><span class="sxs-lookup"><span data-stu-id="1547d-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="1547d-130">卸載 MDATP 手冊：</span><span class="sxs-lookup"><span data-stu-id="1547d-130">Uninstall MDATP cookbook:</span></span>

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
