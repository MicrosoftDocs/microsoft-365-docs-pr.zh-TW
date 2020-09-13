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
ms.openlocfilehash: 08d2f4c6ce67aa9fea196d56b2eb5f36a36d7943
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430043"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="2879f-103">在單一 PowerShell 視窗中連線至所有 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="2879f-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="2879f-104">當您使用 PowerShell 來管理 Microsoft 365，可同時在不同 PowerShell 視窗中開啟與管理使用者帳戶、SharePoint Online、Exchange Online、商務用 Skype Online、Microsoft Teams 和安全性與合規性中心對應的多個 PowerShell 工作階段。&amp;</span><span class="sxs-lookup"><span data-stu-id="2879f-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="2879f-105">這對於管理 Microsoft 365 而言並不理想，因為您無法在用於交叉服務管理的這些視窗之間交換資料。</span><span class="sxs-lookup"><span data-stu-id="2879f-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="2879f-106">本主題說明如何使用 PowerShell 的單一執行個體，您可以從中管理 Microsoft 365 帳戶、商務用 Skype Online、Exchange Online、SharePoint Online、Microsoft Teams 及安全性與合規性中心。&amp;</span><span class="sxs-lookup"><span data-stu-id="2879f-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="2879f-107">本文目前僅包含用來連線至全球 (+GCC) 雲端的命令。</span><span class="sxs-lookup"><span data-stu-id="2879f-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="2879f-108">附註提供文章的連結，內含如何連線到其他 Microsoft 365 雲端的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2879f-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="2879f-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="2879f-109">Before you begin</span></span>

<span data-ttu-id="2879f-110">在您可以從 PowerShell 的單一執行個體管理所有 Microsoft 365 之前，請考慮下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="2879f-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="2879f-111">您用於這些程序的 Microsoft 365 公司或學校帳戶 必須是 Microsoft 365 系統管理員角色的成員。</span><span class="sxs-lookup"><span data-stu-id="2879f-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="2879f-112">如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="2879f-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="2879f-113">這是對 Microsoft 365 的 PowerShell 需求，並非所有其他的 Microsoft 365 服務皆須滿足。</span><span class="sxs-lookup"><span data-stu-id="2879f-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="2879f-114">您可以使用下列 Windows 64 位元版本：</span><span class="sxs-lookup"><span data-stu-id="2879f-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="2879f-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2879f-115">Windows 10</span></span>
    
  - <span data-ttu-id="2879f-116">Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="2879f-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="2879f-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2879f-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="2879f-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="2879f-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="2879f-119">Windows Server 2012 R2 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2879f-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="2879f-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="2879f-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="2879f-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="2879f-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="2879f-122">\*您必須安裝 Microsoft .NET Framework 4.5.*x*，然後安裝 Windows Management Framework 3.0 或 Windows Management Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="2879f-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="2879f-123">如需詳細資訊，請參閱[安裝 .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) 和 [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) 或 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344)。</span><span class="sxs-lookup"><span data-stu-id="2879f-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="2879f-124">由於商務用 Skype Online 模組和其中一個 Microsoft 365 模組的需求，您需要使用 Windows 64 位元版本。</span><span class="sxs-lookup"><span data-stu-id="2879f-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="2879f-125">您需要安裝 Azure Active Directory （Azure AD）、Exchange Online、SharePoint Online、商務用 Skype Online 及 Teams 所需的模組：</span><span class="sxs-lookup"><span data-stu-id="2879f-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="2879f-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="2879f-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="2879f-127">SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="2879f-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="2879f-128">商務用 Skype Online，PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="2879f-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="2879f-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="2879f-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="2879f-130">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="2879f-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="2879f-131">必須設定 PowerShell，才能執行商務用 Skype Online 及安全性與合規性中心的已簽署指令碼。&amp;</span><span class="sxs-lookup"><span data-stu-id="2879f-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="2879f-132">若要執行此動作，請在提高權限的 PowerShell 工作階段 (透過選取 [以系統管理員身分執行 **]** 而開啟的 PowerShell 視窗) 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="2879f-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="2879f-133">Exchange Online 和安全性 &amp; 合規性中心與 Exchange Online PowerShell V2 模組</span><span class="sxs-lookup"><span data-stu-id="2879f-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="2879f-134">本文章使用 Exchange Online PowerShell V2 模組連線 Exchange Online 和安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="2879f-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="2879f-135">不過，您目前無法**在同一 PowerShell 視窗中連線到 Exchange Online 和安全性 &amp; 合規性中心**。</span><span class="sxs-lookup"><span data-stu-id="2879f-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="2879f-136">因此，為多個 Microsoft 365 服務設定 PowerShell 視窗時，您必須選擇與 Exchange Online *或* 安全性 &amp; 合規性中心連線。</span><span class="sxs-lookup"><span data-stu-id="2879f-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="2879f-137">只使用一組密碼時的連線步驟</span><span class="sxs-lookup"><span data-stu-id="2879f-137">Connection steps when using just a password</span></span>

<span data-ttu-id="2879f-138">當您只使用一組密碼登入時，以下是在單一 PowerShell 視窗中連線至所有服務的步驟。</span><span class="sxs-lookup"><span data-stu-id="2879f-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="2879f-139">開啟 [Windows PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="2879f-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="2879f-140">執行此指令並輸入您的 Microsoft 365 公司或學校帳戶憑證。</span><span class="sxs-lookup"><span data-stu-id="2879f-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="2879f-141">執行此指令，以使用 Azure Active Directory PowerShell 的圖表模組連線到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="2879f-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="2879f-142">或者，如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，請執行此指令。</span><span class="sxs-lookup"><span data-stu-id="2879f-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="2879f-143">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2879f-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="2879f-144">若要繼續使用這些 Cmdlet，您必須從 PowerShell 執行它們。</span><span class="sxs-lookup"><span data-stu-id="2879f-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="2879f-145">執行這些指令，以連線到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="2879f-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="2879f-146">指定您網域的組織名稱。</span><span class="sxs-lookup"><span data-stu-id="2879f-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="2879f-147">例如，針對 "litwareinc.onmicrosoft.com"，組織名稱值為 "litwareinc"。</span><span class="sxs-lookup"><span data-stu-id="2879f-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="2879f-148">執行這些指令，以連線至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="2879f-148">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="2879f-149">您第一次連線時，預期會有 `WSMan NetworkDelayms` 值增加的警告，而應該忽略。</span><span class="sxs-lookup"><span data-stu-id="2879f-149">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="2879f-150">執行此指令以連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="2879f-150">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="2879f-151">若要連線至 Microsoft 365 雲端 (而非 [Worldwide]) 的 Exchange Online，請參閱 [連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2879f-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="2879f-152">或者執行這些指令以連線至安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="2879f-152">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="2879f-153">若要連線到 Microsoft 365 雲端 (而非 [Worldwide]) 安全性 &amp; 合規性中心，請參閱 [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2879f-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="2879f-154">執行這些命令，以連線到 Teams PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2879f-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="2879f-155">若要連線到 Microsoft Teams 雲端 (而非 [ Worldwide])，請參閱 [MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams)。</span><span class="sxs-lookup"><span data-stu-id="2879f-155">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2879f-156">針對 Graph 的 Azure Active Directory PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="2879f-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2879f-157">以下是使用適用於 Graph 的 Azure Active Directory PowerShell 模組時，*除安全性&amp;合規性中心*外的所有服務的命令。</span><span class="sxs-lookup"><span data-stu-id="2879f-157">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="2879f-158">指定您網域主機的名稱，然後一次執行它們全部。</span><span class="sxs-lookup"><span data-stu-id="2879f-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="2879f-159">以下是使用適用於 Graph 的 Azure Active Directory PowerShell 模組時，*除 Exchange Online* 外的所有服務的命令。</span><span class="sxs-lookup"><span data-stu-id="2879f-159">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="2879f-160">指定您網域主機的名稱和用於登入的 UPN，然後一次執行它們全部。</span><span class="sxs-lookup"><span data-stu-id="2879f-160">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="2879f-161">適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組</span><span class="sxs-lookup"><span data-stu-id="2879f-161">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="2879f-162">以下是使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組時，*除安全性&amp;合規性中心*外的所有服務的命令。</span><span class="sxs-lookup"><span data-stu-id="2879f-162">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="2879f-163">指定您網域主機的名稱，然後一次執行它們全部。</span><span class="sxs-lookup"><span data-stu-id="2879f-163">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="2879f-164">以下是使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組時，*Exchange Online*外的所有服務的命令。</span><span class="sxs-lookup"><span data-stu-id="2879f-164">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="2879f-165">指定您網域主機的名稱和用於登入的 UPN，然後一次執行它們全部。</span><span class="sxs-lookup"><span data-stu-id="2879f-165">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="2879f-166">使用多重要素驗證時的連線步驟</span><span class="sxs-lookup"><span data-stu-id="2879f-166">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2879f-167">針對 Graph 的 Azure Active Directory PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="2879f-167">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2879f-168">以下是一個文字區塊中的所有命令，可讓您連線到多個 Microsoft 365 服務，除使用適用於 Graph 的 Azure Active Directory PowerShell 模組進行多重要素驗證的 *安全性 &amp; 合規性中心*。 </span><span class="sxs-lookup"><span data-stu-id="2879f-168">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="2879f-169">以下是一個文字區塊中的所有命令，可讓您連線到多個 Microsoft 365 服務，除使用適用於 Graph 的 Azure Active Directory PowerShell 模組進行多重要素驗證的 *Exchange Online*。</span><span class="sxs-lookup"><span data-stu-id="2879f-169">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="2879f-170">適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組</span><span class="sxs-lookup"><span data-stu-id="2879f-170">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="2879f-171">以下是一個文字區塊中的所有命令，可讓您連線到多個 Microsoft 365 服務，除使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組進行多重要素驗證的 *安全性 &amp; 合規性中心*。 </span><span class="sxs-lookup"><span data-stu-id="2879f-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="2879f-172">以下是一個文字區塊中的所有命令，可讓您連線到多個 Microsoft 365 服務，除使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組進行多重要素驗證的 *Exchange Online*。 </span><span class="sxs-lookup"><span data-stu-id="2879f-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="2879f-173">關閉 PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="2879f-173">Close the PowerShell window</span></span>

<span data-ttu-id="2879f-174">當您準備好關閉 PowerShell 視窗時，請執行此命令，以移除連線至商務用 Skype Online、SharePoint Online 及 Teams 的使用中工作階段：</span><span class="sxs-lookup"><span data-stu-id="2879f-174">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="2879f-175">也請參閱</span><span class="sxs-lookup"><span data-stu-id="2879f-175">See also</span></span>

- [<span data-ttu-id="2879f-176">使用 PowerShell 連線至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2879f-176">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="2879f-177">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2879f-177">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2879f-178">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="2879f-178">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
