---
title: 在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 服務
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: '摘要: 在單一 Windows PowerShell 視窗中，將 Windows PowerShell 連線至所有 Microsoft 365 服務。'
ms.openlocfilehash: d4e4bf6ec07ee4a0a5b2f8cb1c83ffacd221eaa0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688610"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window"></a>在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 服務

當您使用 PowerShell 管理 Microsoft 365 時，最多可同時開啟五個不同的 Windows PowerShell 會話，這些會話與 Microsoft 365 系統管理中心、SharePoint Online、Exchange Online、商務用 Skype Online、Microsoft Teams 和安全性 &amp; 合規性中心一致。 由於在個別 WindowsPowerShell 會話中，具有五種不同的連線方法，所以您的桌面看起來可能像這樣:
  
![一次執行五個 Windows PowerShell 主控台](../media/a1a852c2-89ea-4e8e-8d8b-dcdf596763d1.png)
  
這對管理 Microsoft 365 而言並非最佳，因為您無法在五個視窗之間交換跨服務管理的資料。 本主題說明如何使用單一 Windows PowerShell 實例，您可以從中管理 Microsoft 365 帳戶、商務用 Skype Online、Exchange Online、SharePoint Online、Microsoft Teams 及安全性 &amp; 合規性中心。

>[!Note]
>本文目前僅包含連線至全球（+ GCC）雲端的指令。 其他備註提供文章連結，內含如何連線到其他 Microsoft 365 雲端的相關資訊。
>

## <a name="before-you-begin"></a>開始之前

在您可以從單一 Windows PowerShell 實例中管理所有 Microsoft 365之前，請考慮下列先決條件:
  
- 您用於這些程序的 Microsoft 365 公司或學校帳戶 必須是 Microsoft 365 系統管理員角色的成員。 如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)。 這是對 Microsoft 365 的 PowerShell 需求，並非所有其他的 Microsoft 365 服務皆須滿足。
    
- 您可以使用下列 Windows 64 位元版本：
    
  - Windows 10
    
  - Windows 8.1 或 Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 或 Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \*您必須安裝 Microsoft .NET Framework 4.5.*x*，然後安裝 Windows Management Framework 3.0 或 Windows Management Framework 4.0。 如需詳細資訊，請參閱[安裝 .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) 和 [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) 或 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344)。
    
    由於商務用 Skype Online 模組和其中一個 Microsoft 365 模組的需求，您需要使用 Windows 64 位元版本。
    
- 您需要安裝 Azure Active Directory （Azure AD）、Exchange Online、SharePoint Online、商務用 Skype Online 及 Teams 所需的模組：
    
   - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [商務用 Skype Online、Windows PowerShell 模組](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [Teams PowerShell 概觀](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  若要執行商務用 Skype Online 及安全性 &amp; 合規性中心的已簽署腳本，則必須設定 Windows PowerShell。 若要執行此動作，請在升級權限的 Windows PowerShell 會話 (透過選取** [以系統管理員身分執行]** 而開啟的 Windows PowerShell 視窗) 中執行下列指令。
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>只使用一組密碼時的連線步驟

當您只使用一組密碼登入時，以下是在單一 PowerShell 視窗中連線至所有服務的步驟。
  
1. 開啟 [Windows PowerShell]。
    
2. 執行此指令並輸入您的 Microsoft 365 公司或學校帳戶憑證。
    
   ```powershell
   $credential = Get-Credential
   ```

3. 執行此指令，以使用 Azure Active Directory PowerShell 的圖表模組連線到 Azure AD。
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   或者，如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，請執行此指令。
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。

4. 執行這些指令，以連線到 SharePoint Online。 指定您網域的組織名稱。 例如，針對 "litwareinc.onmicrosoft.com"，組織名稱值為 "litwareinc"。
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. 執行這些指令，以連線至商務用 Skype Online。 您第一次連線時，預期會有 `WSMan NetworkDelayms` 值增加的警告，而應該忽略。
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. 執行此指令以連線至 Exchange Online。
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > 若要連線至 Microsoft 365 雲端 (而非 [Worldwide]) 的 Exchange Online，請使用 **-ExchangeEnvironmentName** 參數。 如需詳細資訊，請參閱 [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps)。

7. 執行這些命令，以連線到 Teams PowerShell。
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > 若要連線到 Microsoft Teams 雲端 (而非 [ Worldwide])，請參閱 [MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps)。

8. 執行這些指令以連線至安全性 &amp; 合規性中心。
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > 若要連線到 Microsoft 365 雲端 (而非 [Worldwide]) 安全性 &amp; 合規性中心，請參閱 [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

以下是使用 Azure Active Directory PowerShell 的圖表模組時，單一區塊中的所有指令。 指定您網域主機的名稱，然後一次執行它們全部。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

或者，如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，以下則會單一區塊中的所有指令。 指定您網域主機的名稱，然後一次執行它們全部。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

當您準備好關閉 Windows PowerShell 視窗時，請執行此指令將使用中的會話移除至商務用 Skype Online、SharePoint Online、安全性 &amp; 合規性中心及 Teams：
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>使用多重要素驗證時的連線步驟

以下是使用 Azure Active Directory PowerShell 的圖表模組，在單一視窗中使用多重要素驗證連線到 Azure AD、SharePoint Online、商務用 Skype、Exchange Online 和團隊的單一區塊中的所有命令。 指定使用者帳戶的使用者主要名稱（UPN）和您的網域主機名稱，然後一次執行它們全部。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

或者，如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，以下則是所有指令。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

如需安全性 &amp; 合規性中心，請參閱 [ 使用多重要素驗證連線到安全性與合規性中心 PowerShell ](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) 以使用多重要速驗證連線：

## <a name="see-also"></a>請參閱

- [使用 PowerShell 連線至 Microsoft 365](connect-to-microsoft-365-powershell.md)
- [使用 PowerShell 管理 SharePoint Online](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [在 Microsoft 365 中使用 Windows PowerShell 建立報告](use-windows-powershell-to-create-reports-in-microsoft-365.md)
