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
# <a name="connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window"></a><span data-ttu-id="9de1a-103">在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="9de1a-103">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>

<span data-ttu-id="9de1a-104">當您使用 PowerShell 管理 Microsoft 365 時，最多可同時開啟五個不同的 Windows PowerShell 會話，這些會話與 Microsoft 365 系統管理中心、SharePoint Online、Exchange Online、商務用 Skype Online、Microsoft Teams 和安全性 &amp; 合規性中心一致。</span><span class="sxs-lookup"><span data-stu-id="9de1a-104">When you use PowerShell to manage Microsoft 365, it is possible to have up to five different Windows PowerShell sessions open at the same time corresponding to Microsoft 365 admin center, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="9de1a-105">由於在個別 WindowsPowerShell 會話中，具有五種不同的連線方法，所以您的桌面看起來可能像這樣:</span><span class="sxs-lookup"><span data-stu-id="9de1a-105">With five different connection methods in separate Windows PowerShell sessions, your desktop could look like this:</span></span>
  
![一次執行五個 Windows PowerShell 主控台](../media/a1a852c2-89ea-4e8e-8d8b-dcdf596763d1.png)
  
<span data-ttu-id="9de1a-107">這對管理 Microsoft 365 而言並非最佳，因為您無法在五個視窗之間交換跨服務管理的資料。</span><span class="sxs-lookup"><span data-stu-id="9de1a-107">This is not optimal for managing Microsoft 365 because you can't exchange data among those five windows for cross-service management.</span></span> <span data-ttu-id="9de1a-108">本主題說明如何使用單一 Windows PowerShell 實例，您可以從中管理 Microsoft 365 帳戶、商務用 Skype Online、Exchange Online、SharePoint Online、Microsoft Teams 及安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="9de1a-108">This topic describes how to use a single instance of Windows PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="9de1a-109">本文目前僅包含連線至全球（+ GCC）雲端的指令。</span><span class="sxs-lookup"><span data-stu-id="9de1a-109">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="9de1a-110">其他備註提供文章連結，內含如何連線到其他 Microsoft 365 雲端的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9de1a-110">Additional notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="9de1a-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="9de1a-111">Before you begin</span></span>

<span data-ttu-id="9de1a-112">在您可以從單一 Windows PowerShell 實例中管理所有 Microsoft 365之前，請考慮下列先決條件:</span><span class="sxs-lookup"><span data-stu-id="9de1a-112">Before you can manage all of Microsoft 365 from a single instance of Windows PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="9de1a-113">您用於這些程序的 Microsoft 365 公司或學校帳戶 必須是 Microsoft 365 系統管理員角色的成員。</span><span class="sxs-lookup"><span data-stu-id="9de1a-113">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="9de1a-114">如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="9de1a-114">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="9de1a-115">這是對 Microsoft 365 的 PowerShell 需求，並非所有其他的 Microsoft 365 服務皆須滿足。</span><span class="sxs-lookup"><span data-stu-id="9de1a-115">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="9de1a-116">您可以使用下列 Windows 64 位元版本：</span><span class="sxs-lookup"><span data-stu-id="9de1a-116">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="9de1a-117">Windows 10</span><span class="sxs-lookup"><span data-stu-id="9de1a-117">Windows 10</span></span>
    
  - <span data-ttu-id="9de1a-118">Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="9de1a-118">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="9de1a-119">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="9de1a-119">Windows Server 2019</span></span>
    
  - <span data-ttu-id="9de1a-120">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="9de1a-120">Windows Server 2016</span></span>
    
  - <span data-ttu-id="9de1a-121">Windows Server 2012 R2 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9de1a-121">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="9de1a-122">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="9de1a-122">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="9de1a-123">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="9de1a-123">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="9de1a-124">\*您必須安裝 Microsoft .NET Framework 4.5.*x*，然後安裝 Windows Management Framework 3.0 或 Windows Management Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="9de1a-124">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="9de1a-125">如需詳細資訊，請參閱[安裝 .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) 和 [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) 或 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344)。</span><span class="sxs-lookup"><span data-stu-id="9de1a-125">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="9de1a-126">由於商務用 Skype Online 模組和其中一個 Microsoft 365 模組的需求，您需要使用 Windows 64 位元版本。</span><span class="sxs-lookup"><span data-stu-id="9de1a-126">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="9de1a-127">您需要安裝 Azure Active Directory （Azure AD）、Exchange Online、SharePoint Online、商務用 Skype Online 及 Teams 所需的模組：</span><span class="sxs-lookup"><span data-stu-id="9de1a-127">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="9de1a-128">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="9de1a-128">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="9de1a-129">SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="9de1a-129">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="9de1a-130">商務用 Skype Online、Windows PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="9de1a-130">Skype for Business Online, Windows PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="9de1a-131">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="9de1a-131">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="9de1a-132">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="9de1a-132">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="9de1a-133">若要執行商務用 Skype Online 及安全性 &amp; 合規性中心的已簽署腳本，則必須設定 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9de1a-133">Windows PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="9de1a-134">若要執行此動作，請在升級權限的 Windows PowerShell 會話 (透過選取\*\* [以系統管理員身分執行]\*\* 而開啟的 Windows PowerShell 視窗) 中執行下列指令。</span><span class="sxs-lookup"><span data-stu-id="9de1a-134">To do this, run the following command in an elevated Windows PowerShell session (a Windows PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="9de1a-135">只使用一組密碼時的連線步驟</span><span class="sxs-lookup"><span data-stu-id="9de1a-135">Connection steps when using just a password</span></span>

<span data-ttu-id="9de1a-136">當您只使用一組密碼登入時，以下是在單一 PowerShell 視窗中連線至所有服務的步驟。</span><span class="sxs-lookup"><span data-stu-id="9de1a-136">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="9de1a-137">開啟 [Windows PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="9de1a-137">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="9de1a-138">執行此指令並輸入您的 Microsoft 365 公司或學校帳戶憑證。</span><span class="sxs-lookup"><span data-stu-id="9de1a-138">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="9de1a-139">執行此指令，以使用 Azure Active Directory PowerShell 的圖表模組連線到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="9de1a-139">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="9de1a-140">或者，如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，請執行此指令。</span><span class="sxs-lookup"><span data-stu-id="9de1a-140">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="9de1a-141">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9de1a-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="9de1a-142">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="9de1a-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>

4. <span data-ttu-id="9de1a-143">執行這些指令，以連線到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="9de1a-143">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="9de1a-144">指定您網域的組織名稱。</span><span class="sxs-lookup"><span data-stu-id="9de1a-144">Specify the organization name for your domain.</span></span> <span data-ttu-id="9de1a-145">例如，針對 "litwareinc.onmicrosoft.com"，組織名稱值為 "litwareinc"。</span><span class="sxs-lookup"><span data-stu-id="9de1a-145">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="9de1a-146">執行這些指令，以連線至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="9de1a-146">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="9de1a-147">您第一次連線時，預期會有 `WSMan NetworkDelayms` 值增加的警告，而應該忽略。</span><span class="sxs-lookup"><span data-stu-id="9de1a-147">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="9de1a-148">執行此指令以連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9de1a-148">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="9de1a-149">若要連線至 Microsoft 365 雲端 (而非 [Worldwide]) 的 Exchange Online，請使用 **-ExchangeEnvironmentName** 參數。</span><span class="sxs-lookup"><span data-stu-id="9de1a-149">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="9de1a-150">如需詳細資訊，請參閱 [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="9de1a-150">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="9de1a-151">執行這些命令，以連線到 Teams PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9de1a-151">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="9de1a-152">若要連線到 Microsoft Teams 雲端 (而非 [ Worldwide])，請參閱 [MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="9de1a-152">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="9de1a-153">執行這些指令以連線至安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="9de1a-153">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="9de1a-154">若要連線到 Microsoft 365 雲端 (而非 [Worldwide]) 安全性 &amp; 合規性中心，請參閱 [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9de1a-154">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="9de1a-155">以下是使用 Azure Active Directory PowerShell 的圖表模組時，單一區塊中的所有指令。</span><span class="sxs-lookup"><span data-stu-id="9de1a-155">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="9de1a-156">指定您網域主機的名稱，然後一次執行它們全部。</span><span class="sxs-lookup"><span data-stu-id="9de1a-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
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

<span data-ttu-id="9de1a-157">或者，如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，以下則會單一區塊中的所有指令。</span><span class="sxs-lookup"><span data-stu-id="9de1a-157">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="9de1a-158">指定您網域主機的名稱，然後一次執行它們全部。</span><span class="sxs-lookup"><span data-stu-id="9de1a-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
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

<span data-ttu-id="9de1a-159">當您準備好關閉 Windows PowerShell 視窗時，請執行此指令將使用中的會話移除至商務用 Skype Online、SharePoint Online、安全性 &amp; 合規性中心及 Teams：</span><span class="sxs-lookup"><span data-stu-id="9de1a-159">When you are ready to close down the Windows PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="9de1a-160">使用多重要素驗證時的連線步驟</span><span class="sxs-lookup"><span data-stu-id="9de1a-160">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="9de1a-161">以下是使用 Azure Active Directory PowerShell 的圖表模組，在單一視窗中使用多重要素驗證連線到 Azure AD、SharePoint Online、商務用 Skype、Exchange Online 和團隊的單一區塊中的所有命令。</span><span class="sxs-lookup"><span data-stu-id="9de1a-161">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="9de1a-162">指定使用者帳戶的使用者主要名稱（UPN）和您的網域主機名稱，然後一次執行它們全部。</span><span class="sxs-lookup"><span data-stu-id="9de1a-162">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

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

<span data-ttu-id="9de1a-163">或者，如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，以下則是所有指令。</span><span class="sxs-lookup"><span data-stu-id="9de1a-163">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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

<span data-ttu-id="9de1a-164">如需安全性 &amp; 合規性中心，請參閱 [ 使用多重要素驗證連線到安全性與合規性中心 PowerShell ](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) 以使用多重要速驗證連線：</span><span class="sxs-lookup"><span data-stu-id="9de1a-164">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="9de1a-165">請參閱</span><span class="sxs-lookup"><span data-stu-id="9de1a-165">See also</span></span>

- [<span data-ttu-id="9de1a-166">使用 PowerShell 連線至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de1a-166">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="9de1a-167">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9de1a-167">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="9de1a-168">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="9de1a-168">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="9de1a-169">在 Microsoft 365 中使用 Windows PowerShell 建立報告</span><span class="sxs-lookup"><span data-stu-id="9de1a-169">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
