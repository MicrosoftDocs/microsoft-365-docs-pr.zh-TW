---
title: 在單一 PowerShell 視窗中連線至所有 Microsoft 365 服務
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
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
description: 摘要：在單一 PowerShell 視窗中連線至所有 Microsoft 365 服務。
ms.openlocfilehash: 04be916f745e2bde70554045340fc8ec03f87413
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754313"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>在單一 PowerShell 視窗中連線至所有 Microsoft 365 服務

使用 PowerShell 管理 Microsoft 365 時，可以同時開啟多個 PowerShell 工作階段。 您可能有不同的 PowerShell 視窗來管理使用者帳戶、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams 和安全性 &amp; 合規性中心。
  
此案例對於管理 Microsoft 365 而言並不理想，因為您無法在用於交叉服務管理的這些視窗之間交換資料。 本文章說明如何使用 PowerShell 的單一執行個體來管理 Microsoft 365 帳戶、商務用 Skype Online、Exchange Online、SharePoint Online、Microsoft Teams 及安全性 &amp; 合規性中心。

>[!Note]
>本文目前僅包含用來連線至全球 (+GCC) 雲端的命令。 附註提供文章的連結，內含如何連線到其他 Microsoft 365 雲端。

## <a name="before-you-begin"></a>在您開始之前

在您可以從 PowerShell 的單一執行個體管理所有 Microsoft 365 之前，請考慮下列先決條件：
  
- 您使用的 Microsoft 365 公司或學校帳戶必須是 Microsoft 365 系統管理員角色的成員。 如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。 這是對 Microsoft 365 的 PowerShell 需求，但並非所有其他的 Microsoft 365 服務皆須滿足。
    
- 您可以使用下列 Windows 64 位元版本：
    
  - Windows 10
    
  - Windows 8.1 或 Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 或 Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \*您需要安裝 Microsoft .NET Framework 4.5. *x* 然後是 Windows Management Framework 3.0 或4.0。 如需詳細資訊，請參閱 [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7)。
    
    由於商務用 Skype Online 模組和其中一個 Microsoft 365 模組的需求，您需要使用 Windows 64 位元版本。
    
- 您需要安裝 Azure Active Directory （Azure AD）、Exchange Online、SharePoint Online、商務用 Skype Online 及 Teams 所需的模組：
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [商務用 Skype Online，PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Teams PowerShell 概觀](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  必須設定 PowerShell，才能執行商務用 Skype Online 及安全性 &amp; 合規性中心的已簽署指令碼。 在提高權限的 PowerShell 工作階段 ( **以管理員身份執行** 的 PowerShell 執行階段) 中執行以下命令。
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a>Exchange Online 和安全性 &amp; 合規性中心與 Exchange Online PowerShell V2 模組

本文章程序中使用 Exchange Online PowerShell V2 模組連線 Exchange Online 和安全性 &amp; 合規性中心。 但現時無法 *在同一個 PowerShell 視窗* 中同時連線到這兩處。 因此在為多個 Microsoft 365 服務設定 PowerShell 視窗時，必須選擇連線至其中一個。

## <a name="connection-steps-when-using-just-a-password"></a>只使用一組密碼時的連線步驟

僅使用密碼登入時，請按照以下步驟連接到單一 PowerShell 視窗中的所有服務。
  
1. 開啟 [Windows PowerShell]。
    
2. 執行此指令並輸入您的 Microsoft 365 公司或學校帳戶憑證。
    
   ```powershell
   $credential = Get-Credential
   ```

3. 執行此指令，以透過使用 Azure Active Directory PowerShell 的圖表模組連線到 Azure AD。
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   或者如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，請執行此指令。
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。 您必須從 PowerShell 執行這些 Cmdlet。

4. 執行這些指令，以連線到 SharePoint Online。 指定您網域的組織名稱。 例如，針對 "litwareinc\.onmicrosoft.com"，組織名稱值為 "litwareinc"。
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. 執行這些指令，以連線至商務用 Skype Online。 首次連線時，將出現有關增加 `WSMan NetworkDelayms` 值的警告。 略過它。
     
   > [!Note]
   > 商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. 執行此指令以連線至 Exchange Online。
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > 若要連線至 Microsoft 365 雲端 (而非 [Worldwide]) 的 Exchange Online，請參閱 [連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

   或者執行這些指令以連線至安全性 &amp; 合規性中心。
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > 若要連線到 Microsoft 365 雲端 (而非 [Worldwide]) 安全性 &amp; 合規性中心，請參閱 [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

   執行這些命令，以連線到 Teams PowerShell。
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > 若要連線到 Microsoft Teams 雲端 (而非 *[Worldwide]* )，請參閱 [MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams)。


### <a name="azure-active-directory-powershell-for-graph-module"></a>針對 Graph 的 Azure Active Directory PowerShell 模組

以下是使用適用於 Graph 的 Azure Active Directory PowerShell 模組時， *除安全性&amp;合規性中心* 外的單一文字區塊中所有服務的命令。 指定域主機的名稱並同時執行它們。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

以下是使用適用於 Graph 的 Azure Active Directory PowerShell 模組時， *除 Exchange Online* 外的單一文字區塊中所有服務的命令。 指定您網域主機的名稱和用於登入的 UPN，並同時執行它們。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組

以下是使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組時， *除安全性&amp;合規性中心* 外的單一區塊中的所有服務的命令。 指定您網域主機的名稱，然後同時執行它們。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

以下是使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組時， *Exchange Online* 外的單一區塊中的所有服務命令。 為登入指定網域主機的名稱和 UPN，並同時運行它們。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a>使用多重要素驗證時的連線步驟

### <a name="azure-active-directory-powershell-for-graph-module"></a>針對 Graph 的 Azure Active Directory PowerShell 模組

以下是使用 [適用於 Graph 的 Azure Active Directory PowerShell] 模組時，在單一區塊中用於透過多重要素驗證連接到多個 Microsoft 365 服務 ( *安全性 &amp; 合規性中心除外* ) 的命令。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
以下是使用 [適用於 Graph 的 Azure Active Directory PowerShell 模組] 時，在單一區塊中用於透過多要素驗證連接到多個 Microsoft 365服務 ( *Exchange Online 除外* ) 的所有命令。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組

以下是使用 [適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組] 模組時，在單一區塊中用於透過多要素驗證連接到多個 Microsoft 365 服務 ( *安全性 &amp; 合規中心除外* ) 的所有命令。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
以下是使用 [適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組] 模組時，在單一區塊中用於透過多元素驗證連接到多個 Microsoft 365 服務 ( *Exchange Online 除外* ) 的所有命令。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>關閉 PowerShell 視窗

若要關閉 PowerShell 視窗，請執行此命令，以移除連線至商務用 Skype Online、SharePoint Online 及 Teams 的使用中工作階段：
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>另請參閱

- [使用 PowerShell 連線至 Microsoft 365](connect-to-microsoft-365-powershell.md)
- [使用 PowerShell 管理 SharePoint Online](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
