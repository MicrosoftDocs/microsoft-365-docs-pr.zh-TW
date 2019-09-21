---
title: 安裝 Microsoft Outlook 的垃圾郵件回報增益集
ms.author: MSFTTracyP
author: tracyp
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: 在此 articleSupported LanguagesInstall 垃圾電子郵件報告增益集 inUninstall 垃圾郵件回報增益集這些的詳細資訊
ms.openlocfilehash: 7f294ed78affba6e55f2372b81b517bbd25d3f08
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076832"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>安裝 Microsoft Outlook 的垃圾郵件回報增益集
  
本主題說明如何在組織中的用戶端電腦上，安裝 (和解除安裝) 適用於 Outlook 的 Microsoft 垃圾郵件回報增益集。目前版本的增益集 (2016 年 1 月) 包含支援 Outlook 2016、Outlook 2013、Outlook 2010 和 Outlook 2007。 
  
此增益集 (適用於所有支援的語言) 可讓您直接從 Outlook 功能區回報垃圾郵件。英文版的增益集包括直接從功能區回報電子郵件問題給 Microsoft 的其他選項：
  
-  回報您收到的網路釣魚詐騙電子郵件 
    
- 回報誤認為垃圾郵件的電子郵件。
    
## <a name="supported-languages"></a>支援語言
<a name="sectionSection0"> </a>

垃圾郵件回報增益集支援下列語言： 
  
- 簡體中文
    
- 繁體中文
    
- 荷蘭文
    
- 英文
    
- 法文
    
- 德文
    
- 義大利文
    
- 日文
    
- 韓文
    
- 葡萄牙文
    
- 葡萄牙文 (巴西)
    
- 西班牙文
    
## <a name="install-the-junk-email-reporting-add-in"></a>安裝垃圾郵件回報增益集
<a name="sectionSection1"> </a>

您可以安裝垃圾郵件回報增益集：
  
- 依執行其他 .msi 檔案的方式執行 Windows Installer 套件。安裝增益集時，會開啟一個 GUI 介面，並透過安裝畫面引導您。如需詳細資訊，請參閱[使用安裝精靈安裝垃圾郵件回報增益集](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard)。或
    
- 執行無訊息安裝，此方式會隱藏安裝使用者介面。您需要指定執行安裝指令碼的命令列選項。安裝增益集時，可使用 GUI 介面不提供的額外組態選項。如需詳細資訊，請參閱 [使用無訊息模式安裝垃圾郵件回報增益集](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode)。
    
### <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

安裝適用於 Microsoft Outlook 的 Microsoft 垃圾郵件回報增益集必須具備：
  
- 下列其中一種作業系統：Windows 10、Windows 8.1、Windows 8、Windows 7 Service Pack 1、Windows 10 Server、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2
    
- Outlook 2016、Outlook 2013、Outlook 2010 或 Outlook 2007 (Service Pack 2 或更新版本)
    
- Microsoft Office Primary Interop Assemblies： 
    
  - 若要下載 Primary Interop Assemblies for Microsoft Office 2010 或較新版本，請前往 [Microsoft 下載中心](https://go.microsoft.com/fwlink/?LinkID=166026)。
    
  - 若要下載 Primary Interop Assemblies for Microsoft Office 2007，請前往 [Microsoft 下載中心](https://go.microsoft.com/fwlink/?LinkId=72637)。
    
- Microsoft .NET Framework [2.0 版](https://go.microsoft.com/fwlink/?LinkID=208706)。
    
> [!NOTE]
> 在您要安裝增益集的電腦上，您必須具有系統管理員權限。 
  
### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>使用安裝精靈安裝垃圾郵件回報增益集
<a name="BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard"> </a>

1. 在您的電腦上，關閉 Outlook。
    
2. 前往「適用於 Microsoft Outlook 的 Microsoft 垃圾郵件回報增益集」的 Microsoft 下載中心頁面[https://go.microsoft.com/fwlink/?LinkID=147248](https://go.microsoft.com/fwlink/?LinkID=147248)，下載 .msi 檔案。 
    
3. 連按兩下 .msi 檔案。 
    
4. 在 **[歡迎使用 Microsoft 垃圾郵件回報增益集安裝程式]** 頁面上，按 **[下一步]**。 
    
5. 檢閱授權合約，如果同意安裝條款請按一下 **[我接受授權合約中的條款]** (繼續安裝的必要條件)。按 **[下一步]** 繼續。 
    
6. 當精靈完成時，請按一下 **[完成]**。 
    
7. 請啟動 Outlook。
    
8. 請在 Outlook 功能區上尋找 **[垃圾郵件]** 按鈕。您現在可以選取 [收件匣] 中的垃圾郵件並按一下 **[回報垃圾郵件]** 按鈕，即可向 Microsoft 回報垃圾郵件。 
    
9. 選擇 **[垃圾郵件]** 旁的向下箭號取得更多選項，例如您要向 Microsoft 回報網路釣魚詐騙郵件時使用的 **[回報為網路釣魚]**。在您的垃圾郵件資料夾中，如果電子郵件誤報為垃圾郵件，您也可以選取 **[回報非垃圾郵件]**。 
    
### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>使用無訊息模式安裝垃圾郵件回報增益集
<a name="BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode"> </a>

1. 在您的電腦上，關閉 Outlook。
    
2. 開啟命令提示字元。
    
3. 如果您想直接安裝增益集，不指定任何選用參數，請指定下列命令：
    
  - 執行 x86 Outlook 的電腦： `msiexec /qn /i JunkReportingAdd-in.x86-en.msi`
    
  - 執行 x64 Outlook 的電腦： `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`
    
    您也可以指定選用的 MaxMessageSelection 和 BccEmailAddress 參數：
    
  - MaxMessageSelection 可讓系統管理員定義使用者在單次點按中，可選取用於提交的郵件數目上限。範圍是 1 到 50 封郵件，預設值為 10 封郵件。
    
    範例：如果您想將使用者在單次點按中可選取用於提交的郵件數目上限設為 16，請在安裝命令中使用下列選項： `MaxMessageSelection=16`
    
  - BccEmailAddress 可讓系統管理員設定信箱，透過設定密件副本電子郵件地址來接收所有使用者提交的副本。設定信箱後，所有提交的電子郵件副本都會寄送至 BccEmailAddress。否則，預設設定是沒有密件副本電子郵件地址。
    
    範例：如果您想使用 junkReports@contoso.com 作為所有提交郵件的密件副本電子郵件地址，請使用下列命令： `BccEmailAddress="junkReports@contoso.com"`
    
    > [!NOTE]
    > 您可以輸入多個電子郵件地址並以分號分隔，即可設定多個密件副本電子郵件地址。範例： `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`
  
    若想依照上述範例同時新增這兩個選用參數，您可為執行 x86 Outlook 的電腦指定下列命令： 
    
  ```
  msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
  ```

4. 在完成安裝作業後，請啟動 Outlook。
    
5. 請在 Outlook 功能區上尋找 **[垃圾郵件]** 按鈕。您現在可以選取 [收件匣] 中的垃圾郵件並按一下 **[回報垃圾郵件]** 按鈕，即可向 Microsoft 回報垃圾郵件。 
    
6. 選擇 **[垃圾郵件]** 旁的向下箭號取得更多選項，例如您要向 Microsoft 回報網路釣魚詐騙郵件時使用的 **[回報為網路釣魚]**。在您的垃圾郵件資料夾中，如果電子郵件誤報為垃圾郵件，您也可以選取 **[回報非垃圾郵件]**。 
    
## <a name="uninstall-the-junk-email-reporting-add-in"></a>解除安裝垃圾郵件回報增益集
<a name="sectionSection2"> </a>

使用下列其中一種選項解除安裝垃圾郵件回報增益集：
  
- 使用 [Windows 控制台] 移除增益集。如需詳細資訊，請參閱[從控制台解除安裝垃圾郵件回報增益集](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel)。或
    
- 執行 Windows Installer 套件並選取解除安裝選項。如需詳細資訊，請參閱[執行 Windows Installer 套件以解除安裝垃圾郵件回報增益集](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage)。或
    
- 使用解除安裝選項執行無訊息安裝。如需詳細資訊，請參閱[以無訊息模式解除安裝垃圾郵件回報增益集](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#MK_UninstalltheJunkEmailReportingAdd-ininSilentMode)。
    
> [!NOTE]
> 在您要解除安裝增益集的電腦上，您必須具有系統管理員權限。 
  
### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>從控制台解除安裝垃圾郵件回報增益集
<a name="BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel"> </a>

1. 在您的電腦上，關閉 Outlook。
    
2. 在電腦的 [開始] 功能表上，選取 **[控制台]**。
    
3. 選取 **[程式和功能]**。
    
4. 選取 **[適用於 Microsoft Office Outlook 的 Microsoft 垃圾郵件回報增益集]**。
    
5. 選取 **[解除安裝]**。
    
6. 再次啟動 Outlook，確認增益集不再顯示於 Outlook 功能區上。
    
### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>執行 Windows Installer 套件以解除安裝垃圾郵件回報增益集
<a name="BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage"> </a>

1. 在您的電腦上，關閉 Outlook。
    
    > [!NOTE]
    > 如果解除安裝期間仍在執行 Outlook，您必須將其重新啟動，增益集才能完成解除安裝。 
  
2. 再次執行先前安裝增益集時所執行的 .msi 檔案 
    
    (前往「適用於 Microsoft Outlook 的 Microsoft 垃圾郵件回報增益集」的 Microsoft 下載中心頁面[https://go.microsoft.com/fwlink/?LinkId=147248](https://go.microsoft.com/fwlink/?LinkId=147248)、下載 .msi 檔案，然後按兩下 .msi 檔案)。 
    
3. 遵循提示，解除安裝增益集。
    
4. 再次啟動 Outlook，確認增益集不再顯示於 Outlook 功能區上。
    
### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>以無訊息模式解除安裝垃圾郵件回報增益集
<a name="MK_UninstalltheJunkEmailReportingAdd-ininSilentMode"> </a>

1. 在您的電腦上，關閉 Outlook。
    
    > [!NOTE]
    > 如果解除安裝期間仍在執行 Outlook，您必須將其重新啟動，增益集才能完成解除安裝。 
  
2. 開啟命令提示字元。
    
3. 指定下列命令列參數：
    
    執行 x86 Outlook 的電腦： `msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
    執行 x64 Outlook 的電腦： `msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
4. 再次啟動 Outlook，確認增益集不再顯示於 Outlook 功能區上。
    
## <a name="for-more-information"></a>如需詳細資訊
<a name="sectionSection3"> </a>

[向 Microsoft 回報垃圾郵件](report-junk-email-messages-to-microsoft.md)
  
[疑難排解與支援資訊](troubleshooting-and-support-information.md)
  

