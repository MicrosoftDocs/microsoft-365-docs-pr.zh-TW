---
title: 使用 PowerShell 連線至 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: 使用適用於 Microsoft 365 的 PowerShell 連線至您的 Microsoft 365 租用戶，以從命令列執行系統管理中心工作。
ms.openlocfilehash: 70d6aa1373daf2322319d21e385fc1498af3351e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782798"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>使用 PowerShell 連線至 Microsoft 365

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

適用於 Microsoft 365 的 PowerShell 允許您從命令列管理您的 Microsoft 365 設定。 要連線至 PowerShell，只需安裝所需的軟體，然後連線至 Microsoft 365 組織。

可以用來連線至 Microsoft 365 及管理使用者帳戶、群組和授權的 PowerShell 模組有兩個版本：

- 適用於圖表的 Azure Active Directory PowerShell，其 cmdlet 名稱中包含 *AzureAD*
- 適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，其 cmdlets 名稱中包含 *MSol*

目前，適用於圖表的 Azure Active Directory PowerShell 模組無法完全取代適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中針對使用者、群組和授權管理的功能。 在某些情況下，您需要同時使用這兩個版本。 您可以在同一部電腦上安全地安裝這兩個版本。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？


**作業系統**

必須使用 64 位元的 Windows 版本。對適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組 32 位元版本的支援已在 2014 年終止。

您可以使用下列 Windows 版本：
    
  - Windows 10、Windows 8.1、Windows 8 或 Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 SP1

>[!Note]
>若為 Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2 SP1，請下載並安裝 [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).

**PowerShell**

- 針對 Azure Active Directory PowerShell 的圖表模組，請務必使用 PowerShell 版本 5.1 或更新版本。

- 針對適用於 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，請務必使用 PowerShell 版本 5.1 或更新版本 (最多可至 PowerShell 版本 6)。無法使用 PowerShell 版本 7。
       
>[!Note]
>這些程序適用於屬於 Microsoft 365 系統管理員角色成員的使用者。 如需詳細資訊，請參閱[關於系統管理員角色](../admin/add-users/about-admin-roles.md)。


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>與 Azure Active Directory PowerShell for Graph 模組連線

在Azure Active Directory PowerShell 圖表模組中的命令，其 Cmdlet 名稱中會包含 *AzureAD*。 您可以安裝 [Azure Active Directory PowerShell 的圖表](/powershell/azure/active-directory/install-adv2)或 [Azure PowerShell](/powershell/azure/install-az-ps)。

針對需要 Azure Active Directory PowerShell for Graph 模組中新 Cmdlet 的程序，請按照下列步驟來安裝模組，並連線至您的 Microsoft 365 訂閱。

> [!Note]
> 如需支援不同版本的 Microsoft Windows 的詳細資訊，請參閱 [Azure Active Directory PowerShell for Graph 模組](/powershell/azure/active-directory/install-adv2)。

### <a name="step-1-install-the-required-software"></a>步驟 1：安裝必要的軟體

這些步驟只需在電腦上執行一次。 但您可能需要定期更新軟體。
  
1. 開啟提升權限的 Windows PowerShell 命令提示字元視窗 (以系統管理員身分執行 Windows PowerShell)。
    
2. 執行此命令︰
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  根據預設，PowerShell 資源庫 (PSGallery) 未針對 **PowerShellGet** 設定為受信賴的存放庫。 第一次使用 PSGallery 時，您會看到下列訊息：

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

回答 [是] 或 [全部皆是] 以繼續安裝。


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>步驟 2：連接到您的 Microsoft 365 訂閱的 Azure AD

若要使用帳戶名稱和密碼或使用多重要素驗證連接到您的 Microsoft 365 訂閱的 Azure Active Directory (Azure AD)，請從 Windows PowerShell 命令提示字元執行下列其中一個命令 (不需提升權限)。

| Office 365 雲端 | 命令 |
|:-------|:-----|
| Office 365 全球 (+GCC) | `Connect-AzureAD` |
| 21 Vianet 運作的 Office 365 | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 美國政府 DoD 和 Office 365 美國政府 GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

在 **[登入您的帳戶]** 對話方塊中，輸入您的 Microsoft 365 公司或學校帳戶使用者名稱和密碼，然後選取 **[確定]**。

如果使用多重要素驗證，請按照說明提供其他身份驗證資訊，例如驗證碼。

連線之後，您可以對 [Azure Active Directory PowerShell for Graph 模組](/powershell/module/azuread)使用這些 Cmdlet。

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>與適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組連線

>[!Note]
>在適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中的 Cmdlet 名稱會包含 *Msol*。

PowerShell 版本 7 和更新版本不支援適用於 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。 針對 PowerShell 版本 7 和更高版本，請務必使用 Azure Active Directory PowerShell 的圖表模組或 Azure PowerShell。

PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。 從 PowerShell 執行這些 Cmdlet。
    
### <a name="step-1-install-the-required-software"></a>步驟 1：安裝必要的軟體

這些步驟只需在電腦上執行一次。 但您可能需要定期更新軟體。
  
1.  如果您未執行 Windows 10，請安裝 64 位元版本的 Microsoft Online Services 登入小幫手：[適用於 IT 專業人員的 Microsoft Online Services 登入小幫手 RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)。
    
2. 請按照以下步驟，安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：
    
   1. 開啟提升權限的 Windows PowerShell 命令提示字元 (以系統管理員身分執行 Windows PowerShell)。
   1.  執行 **Install-Module MSOnline** 命令。
   1. 如果系統提示您安裝 NuGet 提供者，請輸入 **Y**，然後按 Enter 鍵。
   1. 如果系統提示您從 PSGallery 安裝模組，請輸入 **Y**，然後按 Enter 鍵。
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>步驟 2：連接到您的 Microsoft 365 訂閱的 Azure AD

若要使用帳戶名稱和密碼或使用多重要素驗證連接到您的 Microsoft 365 訂閱的 Azure AD，請從 Windows PowerShell 命令提示字元執行下列其中一個命令 (不需提升權限)。

| Office 365 雲端 | 命令 |
|:-------|:-----|
| Office 365 全球 (+GCC) | `Connect-MsolService` |
| 21 Vianet 運作的 Office 365 | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 美國政府 DoD 和 Office 365 美國政府 GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

在 **[登入您的帳戶]** 對話方塊中，輸入您的 Microsoft 365 公司或學校帳戶使用者名稱和密碼，然後選取 **[確定]**。

如果使用多重要素驗證，請按照說明提供其他身份驗證資訊，例如驗證碼。

### <a name="how-do-you-know-it-worked"></a>如何得知它的運作正常？

如果您沒有收到錯誤訊息，則已成功連線。 若要快速測試，請執行 Microsoft 365 cmdlet，例如 **Get-MsolUser**，然後查看結果。
  
如果收到錯誤訊息，請檢查下列問題：
  
- **密碼錯誤是常見的問題**。 再次執行[步驟 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)，並密切注意您輸入的使用者名稱和密碼。
    
- **適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組要求在您的電腦上啟用 Microsoft .NET Framework 3.5.* x*。您的電腦可能已安裝了較新的版本 (例如 4 或 4.5.* x*). 但可以啟用或停用舊版 .NET Framework 的回溯相容性。 如需詳細資訊，請參閱下列文章：
    
  - 針對 Windows Server 2012 或 Windows Server 2012 R2，請參閱[使用新增角色及功能精靈來啟用 .NET Framework 3.5](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10))。
    
  - 針對 Windows 7 或 Windows Server 2008 R2，請參閱[您無法開啟 Windows PowerShell 的 Azure Active Directory 模組](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell)。

  - 若為 Windows 10、Windows 8.1 和 Windows 8，請參閱[在 Windows 10、Windows 8.1 以及 Windows 8 上安裝 .NET Framework 3.5](/dotnet/framework/install/dotnet-35-windows-10)。

  
- **您的適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組版本可能已過時。** 若要檢查，請在適用於 Microsoft 365 的 PowerShell 或適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中執行下列命令：
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    如果傳回的版本號碼低於 *1.0.8070.2*，請將適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組解除安裝，然後從以上的 [步驟 1](#step-1-install-the-required-software) 中安裝。

- **如果您收到連線錯誤**，請參閲 [「Connect-MsolService：擲回類型例外狀況」錯誤](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception)。
    
- 訊息 **如果您收到「Get-Item：找不到路徑」錯誤訊息**，請執行此命令：


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a>另請參閱

- [使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
- [開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
- [在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 服務](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
