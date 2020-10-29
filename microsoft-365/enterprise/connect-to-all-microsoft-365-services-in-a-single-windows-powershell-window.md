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
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="ce3b8-103">在單一 PowerShell 視窗中連線至所有 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="ce3b8-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="ce3b8-104">使用 PowerShell 管理 Microsoft 365 時，可以同時開啟多個 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="ce3b8-105">您可能有不同的 PowerShell 視窗來管理使用者帳戶、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams 和安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="ce3b8-106">此案例對於管理 Microsoft 365 而言並不理想，因為您無法在用於交叉服務管理的這些視窗之間交換資料。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="ce3b8-107">本文章說明如何使用 PowerShell 的單一執行個體來管理 Microsoft 365 帳戶、商務用 Skype Online、Exchange Online、SharePoint Online、Microsoft Teams 及安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="ce3b8-108">本文目前僅包含用來連線至全球 (+GCC) 雲端的命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="ce3b8-109">附註提供文章的連結，內含如何連線到其他 Microsoft 365 雲端。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ce3b8-110">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="ce3b8-110">Before you begin</span></span>

<span data-ttu-id="ce3b8-111">在您可以從 PowerShell 的單一執行個體管理所有 Microsoft 365 之前，請考慮下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="ce3b8-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="ce3b8-112">您使用的 Microsoft 365 公司或學校帳戶必須是 Microsoft 365 系統管理員角色的成員。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="ce3b8-113">如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-113">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="ce3b8-114">這是對 Microsoft 365 的 PowerShell 需求，但並非所有其他的 Microsoft 365 服務皆須滿足。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="ce3b8-115">您可以使用下列 Windows 64 位元版本：</span><span class="sxs-lookup"><span data-stu-id="ce3b8-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="ce3b8-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ce3b8-116">Windows 10</span></span>
    
  - <span data-ttu-id="ce3b8-117">Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="ce3b8-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="ce3b8-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="ce3b8-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="ce3b8-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ce3b8-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="ce3b8-120">Windows Server 2012 R2 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ce3b8-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="ce3b8-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="ce3b8-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="ce3b8-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="ce3b8-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="ce3b8-123">\*您需要安裝 Microsoft .NET Framework 4.5. *x* 然後是 Windows Management Framework 3.0 或4.0。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-123">\* You need to install Microsoft .NET Framework 4.5. *x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="ce3b8-124">如需詳細資訊，請參閱 [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-124">For more information, see [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).</span></span>
    
    <span data-ttu-id="ce3b8-125">由於商務用 Skype Online 模組和其中一個 Microsoft 365 模組的需求，您需要使用 Windows 64 位元版本。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="ce3b8-126">您需要安裝 Azure Active Directory （Azure AD）、Exchange Online、SharePoint Online、商務用 Skype Online 及 Teams 所需的模組：</span><span class="sxs-lookup"><span data-stu-id="ce3b8-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="ce3b8-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="ce3b8-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="ce3b8-128">SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="ce3b8-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="ce3b8-129">商務用 Skype Online，PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="ce3b8-129">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="ce3b8-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="ce3b8-130">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="ce3b8-131">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="ce3b8-131">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="ce3b8-132">必須設定 PowerShell，才能執行商務用 Skype Online 及安全性 &amp; 合規性中心的已簽署指令碼。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="ce3b8-133">在提高權限的 PowerShell 工作階段 ( **以管理員身份執行** 的 PowerShell 執行階段) 中執行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator** ).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="ce3b8-134">Exchange Online 和安全性 &amp; 合規性中心與 Exchange Online PowerShell V2 模組</span><span class="sxs-lookup"><span data-stu-id="ce3b8-134">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="ce3b8-135">本文章程序中使用 Exchange Online PowerShell V2 模組連線 Exchange Online 和安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-135">The procedures in this article use the Exchange Online PowerShell V2 module to connect to both Exchange Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="ce3b8-136">但現時無法 *在同一個 PowerShell 視窗* 中同時連線到這兩處。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-136">But currently you can't connect to both *in the same PowerShell window* .</span></span> <span data-ttu-id="ce3b8-137">因此在為多個 Microsoft 365 服務設定 PowerShell 視窗時，必須選擇連線至其中一個。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-137">So you have to choose to connect to one or the other when you configure a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="ce3b8-138">只使用一組密碼時的連線步驟</span><span class="sxs-lookup"><span data-stu-id="ce3b8-138">Connection steps when using just a password</span></span>

<span data-ttu-id="ce3b8-139">僅使用密碼登入時，請按照以下步驟連接到單一 PowerShell 視窗中的所有服務。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-139">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="ce3b8-140">開啟 [Windows PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-140">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="ce3b8-141">執行此指令並輸入您的 Microsoft 365 公司或學校帳戶憑證。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-141">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="ce3b8-142">執行此指令，以透過使用 Azure Active Directory PowerShell 的圖表模組連線到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-142">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="ce3b8-143">或者如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，請執行此指令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-143">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="ce3b8-144">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-144">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="ce3b8-145">您必須從 PowerShell 執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-145">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="ce3b8-146">執行這些指令，以連線到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-146">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="ce3b8-147">指定您網域的組織名稱。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-147">Specify the organization name for your domain.</span></span> <span data-ttu-id="ce3b8-148">例如，針對 "litwareinc\.onmicrosoft.com"，組織名稱值為 "litwareinc"。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-148">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="ce3b8-149">執行這些指令，以連線至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-149">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="ce3b8-150">首次連線時，將出現有關增加 `WSMan NetworkDelayms` 值的警告。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-150">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="ce3b8-151">略過它。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-151">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="ce3b8-152">商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-152">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="ce3b8-153">如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-153">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="ce3b8-154">執行此指令以連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-154">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="ce3b8-155">若要連線至 Microsoft 365 雲端 (而非 [Worldwide]) 的 Exchange Online，請參閱 [連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-155">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   <span data-ttu-id="ce3b8-156">或者執行這些指令以連線至安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-156">Alternatively, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="ce3b8-157">若要連線到 Microsoft 365 雲端 (而非 [Worldwide]) 安全性 &amp; 合規性中心，請參閱 [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-157">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="ce3b8-158">執行這些命令，以連線到 Teams PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-158">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="ce3b8-159">若要連線到 Microsoft Teams 雲端 (而非 *[Worldwide]* )，請參閱 [MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams)。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-159">To connect to Microsoft Teams clouds other than *Worldwide* , see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ce3b8-160">針對 Graph 的 Azure Active Directory PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="ce3b8-160">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ce3b8-161">以下是使用適用於 Graph 的 Azure Active Directory PowerShell 模組時， *除安全性&amp;合規性中心* 外的單一文字區塊中所有服務的命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-161">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="ce3b8-162">指定域主機的名稱並同時執行它們。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-162">Specify the name of your domain host and run them all at the same time.</span></span>
  
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

<span data-ttu-id="ce3b8-163">以下是使用適用於 Graph 的 Azure Active Directory PowerShell 模組時， *除 Exchange Online* 外的單一文字區塊中所有服務的命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-163">Here are the commands for all the services *except Exchange Online* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="ce3b8-164">指定您網域主機的名稱和用於登入的 UPN，並同時執行它們。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-164">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
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

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="ce3b8-165">適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組</span><span class="sxs-lookup"><span data-stu-id="ce3b8-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="ce3b8-166">以下是使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組時， *除安全性&amp;合規性中心* 外的單一區塊中的所有服務的命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-166">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="ce3b8-167">指定您網域主機的名稱，然後同時執行它們。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-167">Specify the name of your domain host and run them all at one time.</span></span>
  
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

<span data-ttu-id="ce3b8-168">以下是使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組時， *Exchange Online* 外的單一區塊中的所有服務命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-168">Here are the commands for all the services *except Exchange Online* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="ce3b8-169">為登入指定網域主機的名稱和 UPN，並同時運行它們。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-169">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
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
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="ce3b8-170">使用多重要素驗證時的連線步驟</span><span class="sxs-lookup"><span data-stu-id="ce3b8-170">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ce3b8-171">針對 Graph 的 Azure Active Directory PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="ce3b8-171">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ce3b8-172">以下是使用 [適用於 Graph 的 Azure Active Directory PowerShell] 模組時，在單一區塊中用於透過多重要素驗證連接到多個 Microsoft 365 服務 ( *安全性 &amp; 合規性中心除外* ) 的命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

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
<span data-ttu-id="ce3b8-173">以下是使用 [適用於 Graph 的 Azure Active Directory PowerShell 模組] 時，在單一區塊中用於透過多要素驗證連接到多個 Microsoft 365服務 ( *Exchange Online 除外* ) 的所有命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-173">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication when you use the Azure Active Directory PowerShell for Graph module.</span></span>

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
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="ce3b8-174">適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組</span><span class="sxs-lookup"><span data-stu-id="ce3b8-174">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="ce3b8-175">以下是使用 [適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組] 模組時，在單一區塊中用於透過多要素驗證連接到多個 Microsoft 365 服務 ( *安全性 &amp; 合規中心除外* ) 的所有命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-175">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
<span data-ttu-id="ce3b8-176">以下是使用 [適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組] 模組時，在單一區塊中用於透過多元素驗證連接到多個 Microsoft 365 服務 ( *Exchange Online 除外* ) 的所有命令。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-176">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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

## <a name="close-the-powershell-window"></a><span data-ttu-id="ce3b8-177">關閉 PowerShell 視窗</span><span class="sxs-lookup"><span data-stu-id="ce3b8-177">Close the PowerShell window</span></span>

<span data-ttu-id="ce3b8-178">若要關閉 PowerShell 視窗，請執行此命令，以移除連線至商務用 Skype Online、SharePoint Online 及 Teams 的使用中工作階段：</span><span class="sxs-lookup"><span data-stu-id="ce3b8-178">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="ce3b8-179">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce3b8-179">See also</span></span>

- [<span data-ttu-id="ce3b8-180">使用 PowerShell 連線至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ce3b8-180">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="ce3b8-181">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ce3b8-181">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="ce3b8-182">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="ce3b8-182">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
