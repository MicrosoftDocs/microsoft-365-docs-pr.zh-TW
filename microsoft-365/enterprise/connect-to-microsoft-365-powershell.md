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
ms.openlocfilehash: d1e347a13ca5c587fa544ef80a8e289a8dec0a59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688608"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>使用 PowerShell 連線至 Microsoft 365

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

適用於 Microsoft 365 的 PowerShell 可讓您從命令列管理您的 Microsoft 365 設定。 連線至 PowerShell 是簡單的程序，您可以在其中安裝必要的軟體，然後連線至您的 Microsoft 365 組織。 

您用來連線至 Microsoft 365 及管理使用者帳戶、群組和授權的 PowerShell 模組有兩個版本：

- Azure Active Directory PowerShell for Graph (名稱中包含 **AzureAD** 的 Cmdlet)
- 適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組 (名稱中包含 **MSol** 的 Cmdlet) 

自本文發行日期起，Azure Active Directory PowerShell for Graph 模組無法完全取代適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中針對使用者、群組和授權管理的 Cmdlet 功能。 在某些情況下，您需要同時使用這兩個版本。 您可以在同一部電腦上安全地安裝這兩個版本。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

您可以使用下列 Windows 版本：
    
  - Windows 10、Windows 8.1、Windows 8 或 Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 SP1

    > [!NOTE]
    > 針對 Azure Active Directory PowerShell 的圖表模組，請務必使用 PowerShell 版本 5.1 或更新版本。 針對適用於 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，請務必使用 PowerShell 版本 5.1 或更新版本 (最多可至 PowerShell 版本 6)。 無法使用 PowerShell 版本 7。 若為 Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2 SP1，請下載並安裝 [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616). 
    
    > [!NOTE]
    > 請使用 64 位元的 Windows 版本。對 Windows PowerShell 的 Microsoft Azure Active Directory 模組 32 位元版本的支援已在 2014 年 10 月終止。
    
這些程序適用於屬於 Microsoft 365 系統管理員角色成員的使用者。 如需詳細資訊，請參閱[關於系統管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=532367)。


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>與 Azure Active Directory PowerShell for Graph 模組連線

在Azure Active Directory PowerShell 圖表模組中的命令，其 Cmdlet 名稱中會包含 **AzureAD**。 您可以安裝 [Azure Active Directory PowerShell 的圖表](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory)或 [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1)。

針對需要 Azure Active Directory PowerShell for Graph 模組中新 Cmdlet 的程序，請使用下列步驟來安裝模組，並連線至您的 Microsoft 365 訂閱。

>[!Note]
>如需支援不同版本的 Microsoft Windows 的詳細資訊，請參閱 [Azure Active Directory PowerShell for Graph 模組](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory)。
>

### <a name="step-1-install-required-software"></a>步驟 1：安裝必要的軟體

這些步驟只需您在電腦上執行一次，而不必在每次連線時執行。不過，您可能需要定期安裝較新的軟體版本。
  
1. 開啟提升權限的 Windows PowerShell 命令提示字元 (以系統管理員身分執行 Windows PowerShell)。
    
2. 在 [系統管理員：Windows PowerShell] 命令視窗中，執行下列命令：
    
  ```powershell
  Install-Module -Name AzureAD
  ```

如果出現提示，指出需安裝來自不受信任存放庫的模組，請輸入 **Y**，然後按 ENTER 鍵。

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>步驟 2：連接到您的 Microsoft 365 訂閱的 Azure AD

若要使用帳戶名稱和密碼或使用多重要素驗證 (MFA) 連接到您的 Microsoft 365 訂閱的 Azure AD，請從 Windows PowerShell 命令提示字元(不需提升權限) 執行下列其中一個命令。

| Office 365 雲端 | 命令 |
|:-------|:-----|
| Office 365 全球 (+GCC) | `Connect-AzureAD` |
| 21 Vianet 運作的 Office 365 | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 美國政府 DoD 和 Office 365 美國政府 GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

在 [登入您的帳戶]**** 對話方塊中，輸入您的 Microsoft 365 公司或學校帳戶使用者名稱和密碼，然後按一下 [確定]****。

如果您使用 MFA，請遵循其他對話方塊中的指示，提供更多的驗證資訊，例如驗證碼。

連線之後，您可以對 [Azure Active Directory PowerShell for Graph 模組](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory)使用這些 Cmdlet。
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>與適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組連線

在適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中，命令的 Cmdlet 名稱會包含 **Msol**。

PowerShell 版本 7 和更新版本不支援適用於 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 針對 PowerShell 版本 7 和更高版本，請務必使用 Azure Active Directory PowerShell 的圖表模組或 Azure PowerShell。

PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。 
    
### <a name="step-1-install-required-software"></a>步驟 1：安裝必要的軟體

這些步驟只需您在電腦上執行一次，而不必在每次連線時執行。不過，您可能需要定期安裝較新的軟體版本。
  
1.  如果您未執行 Windows 10，請安裝 64 位元版本的 Microsoft Online Services 登入小幫手：[適用於 IT 專業人員的 Microsoft Online Services 登入小幫手 RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152)。
    
2. 以下列步驟安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：
    
  - 開啟提升權限的 Windows PowerShell 命令提示字元 (以系統管理員身分執行 Windows PowerShell)。
  - 執行 **Install-Module MSOnline** 命令。
  - 如果系統提示您安裝 NuGet 提供者，請輸入 **Y**，然後按 ENTER 鍵。
  - 如果系統提示您從 PSGallery 安裝模組，請輸入 **Y**，然後按 ENTER 鍵。
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>步驟 2：連接到您的 Microsoft 365 訂閱的 Azure AD

若要使用帳戶名稱和密碼或使用多重要素驗證 (MFA) 連接到您的 Microsoft 365 訂閱的 Azure AD，請從 Windows PowerShell 命令提示字元(不需提升權限) 執行下列其中一個命令。

| Office 365 雲端 | 命令 |
|:-------|:-----|
| Office 365 全球 (+GCC) | `Connect-MsolService` |
| 21 Vianet 運作的 Office 365 | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 美國政府 DoD 和 Office 365 美國政府 GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

在 [登入您的帳戶]**** 對話方塊中，輸入您的 Microsoft 365 公司或學校帳戶使用者名稱和密碼，然後按一下 [確定]****。

如果您使用 MFA，請遵循其他對話方塊中的指示，提供更多的驗證資訊，例如驗證碼。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

如果您未收到任何錯誤，便已順利連線。 若要做快速測試，您可以執行一個 Microsoft 365 Cmdlet (例如 **Get-MsolUser**)，然後檢視結果。
  
如果出現錯誤，請檢查下列需求：
  
- **密碼錯誤是常見的問題**。 再次執行步驟 2。 並密切注意您輸入的使用者名稱和密碼。
    
- **Microsoft Azure Active Directory Module for Windows PowerShell 要求在您的電腦上啟用 Microsoft .NET Framework 3.5.* x* 功能**。您的電腦可能已安裝了較新的版本 (例如 4 或 4.5.* x*)，但可以啟用或停用舊版 .NET Framework 的回溯相容性。 如需詳細資訊，請參閱下列主題：
    
  - 針對 Windows Server 2012 或 Windows Server 2012 R2，請參閱[使用新增角色及功能精靈來啟用 .NET Framework 3.5](https://go.microsoft.com/fwlink/p/?LinkId=532368)
    
  - 針對 Windows 7 或 Windows Server 2008 R2，請參閱[您無法開啟 Windows PowerShell 的 Azure Active Directory 模組](https://go.microsoft.com/fwlink/p/?LinkId=532370)

  - 若為 Windows 10、Windows 8.1 和 Windows 8，請參閱[在 Windows 10、Windows 8.1 以及 Windows 8 上安裝 .NET Framework 3.5](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)

  
- **您的適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組版本可能已過時。** 若要檢查，請在適用於 Microsoft 365 的 PowerShell 或適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中執行下列命令：
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    如果傳回的版本號碼低於 1.0.8070.2 值，請將適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組解除安裝，然後從以上的步驟 1 中安裝。

- **如果您收到連線錯誤，請參閱本主題：** [「Connect-MsolService：擲回類型例外狀況」錯誤](https://go.microsoft.com/fwlink/p/?LinkId=532377)。
    
- **如果您收到「Get-Item：找不到路徑」錯誤，請使用以下命令：** 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a>另請參閱

- [使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
- [開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
- [在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 服務](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
