---
title: 在單一 PowerShell 視窗中連線至所有 Microsoft 365 服務
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
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
ms.openlocfilehash: 18ff8e1789242b4dde3b4b31aaccf2462e4c5d74
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905125"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="12556-103">在單一 PowerShell 視窗中連線至所有 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="12556-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="12556-104">使用 PowerShell 管理 Microsoft 365 時，可以同時開啟多個 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="12556-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="12556-105">您可能有不同的 PowerShell 視窗來管理使用者帳戶、SharePoint Online、Exchange Online、商務用 Skype Online、Microsoft Teams 和安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="12556-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="12556-106">此案例對於管理 Microsoft 365 而言並不理想，因為您無法在用於交叉服務管理的那些視窗之間交換資料。</span><span class="sxs-lookup"><span data-stu-id="12556-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="12556-107">本文章說明如何使用 PowerShell 的單一執行個體來管理 Microsoft 365 帳戶、商務用 Skype Online、Exchange Online、SharePoint Online、Microsoft Teams 及安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="12556-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="12556-108">本文目前僅包含用來連線至全球 (+GCC) 雲端的命令。</span><span class="sxs-lookup"><span data-stu-id="12556-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="12556-109">附註提供有關如何連線到其他 Microsoft 365 雲端之文章的連結。</span><span class="sxs-lookup"><span data-stu-id="12556-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="12556-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="12556-110">Before you begin</span></span>

<span data-ttu-id="12556-111">在您可以從 PowerShell 的單一執行個體管理所有 Microsoft 365 之前，請考慮下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="12556-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="12556-112">您使用的 Microsoft 365 公司或學校帳戶必須是 Microsoft 365 系統管理員角色的成員。</span><span class="sxs-lookup"><span data-stu-id="12556-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="12556-113">如需詳細資訊，請參閱[關於系統管理員角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="12556-113">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span> <span data-ttu-id="12556-114">這是對 Microsoft 365 的 PowerShell 需求，但並非所有其他 Microsoft 365 服務的需求。</span><span class="sxs-lookup"><span data-stu-id="12556-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="12556-115">您可以使用下列 Windows 64 位元版本：</span><span class="sxs-lookup"><span data-stu-id="12556-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="12556-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="12556-116">Windows 10</span></span>
    
  - <span data-ttu-id="12556-117">Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="12556-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="12556-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="12556-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="12556-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="12556-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="12556-120">Windows Server 2012 R2 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="12556-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="12556-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="12556-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="12556-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="12556-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="12556-123">\*您需要安裝 Microsoft .NET Framework 4.5.*x*，然後安裝 Windows Management Framework 3.0 或4.0。</span><span class="sxs-lookup"><span data-stu-id="12556-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="12556-124">如需詳細資訊，請參閱 [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview)。</span><span class="sxs-lookup"><span data-stu-id="12556-124">For more information, see [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).</span></span>
    
    <span data-ttu-id="12556-125">由於商務用 Skype Online 模組和其中一個 Microsoft 365 模組的需求，您需要使用 Windows 64 位元版本。</span><span class="sxs-lookup"><span data-stu-id="12556-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="12556-126">您需要安裝 Azure Active Directory （Azure AD）、Exchange Online、SharePoint Online、商務用 Skype Online 及 Teams 所需的模組：</span><span class="sxs-lookup"><span data-stu-id="12556-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="12556-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="12556-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="12556-128">SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="12556-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="12556-129">商務用 Skype Online，PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="12556-129">Skype for Business Online, PowerShell Module</span></span>](/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="12556-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="12556-130">Exchange Online PowerShell V2</span></span>](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="12556-131">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="12556-131">Teams PowerShell Overview</span></span>](/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="12556-132">必須設定 PowerShell，才能執行商務用 Skype Online 及安全性與合規性中心的已簽署指令碼。</span><span class="sxs-lookup"><span data-stu-id="12556-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="12556-133">在提高權限的 PowerShell 工作階段 (**以系統管理員身份執行** 的 PowerShell 執行階段) 中執行以下命令。</span><span class="sxs-lookup"><span data-stu-id="12556-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="12556-134">只使用一組密碼時的連線步驟</span><span class="sxs-lookup"><span data-stu-id="12556-134">Connection steps when using just a password</span></span>

<span data-ttu-id="12556-135">僅使用密碼登入時，請按照以下步驟在單一 PowerShell 視窗中連線到所有服務。</span><span class="sxs-lookup"><span data-stu-id="12556-135">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="12556-136">開啟 [Windows PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="12556-136">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="12556-137">執行此指令並輸入您的 Microsoft 365 公司或學校帳戶憑證。</span><span class="sxs-lookup"><span data-stu-id="12556-137">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="12556-138">執行此指令，以透過使用 Azure Active Directory PowerShell for Graph 模組連線到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="12556-138">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="12556-139">或者如果您使用的是適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="12556-139">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="12556-140">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12556-140">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="12556-141">您必須從 PowerShell 執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12556-141">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="12556-142">執行這些指令，以連線到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="12556-142">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="12556-143">指定您網域的組織名稱。</span><span class="sxs-lookup"><span data-stu-id="12556-143">Specify the organization name for your domain.</span></span> <span data-ttu-id="12556-144">例如，針對 "litwareinc\.onmicrosoft.com"，組織名稱值為 "litwareinc"。</span><span class="sxs-lookup"><span data-stu-id="12556-144">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="12556-145">執行這些指令，以連線至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="12556-145">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="12556-146">首次連線時，將出現有關增加 `WSMan NetworkDelayms` 值的警告。</span><span class="sxs-lookup"><span data-stu-id="12556-146">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="12556-147">略過它。</span><span class="sxs-lookup"><span data-stu-id="12556-147">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="12556-148">商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="12556-148">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="12556-149">如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="12556-149">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

6. <span data-ttu-id="12556-150">執行這些命令，以連線到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="12556-150">Run these commands to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="12556-151">若要連線至「全球」以外適用於 Microsoft 365 的 Exchange Online 雲端，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="12556-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="12556-152">執行這些指令以連線至安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="12556-152">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="12556-153">若要連線到 Microsoft 365 雲端 (而非 [Worldwide]) 安全性 &amp; 合規性中心，請參閱 [連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="12556-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="12556-154">執行這些命令，以連線到 Teams PowerShell。</span><span class="sxs-lookup"><span data-stu-id="12556-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="12556-155">若要連線到 Microsoft Teams 雲端 (而非 *[全球]*)，請參閱 [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams)。</span><span class="sxs-lookup"><span data-stu-id="12556-155">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).</span></span>
  



### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="12556-156">Azure Active Directory PowerShell for Graph 模組</span><span class="sxs-lookup"><span data-stu-id="12556-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="12556-157">以下是使用適用於 Graph 的 Azure Active Directory PowerShell 模組時，單一區塊中所有服務的命令。</span><span class="sxs-lookup"><span data-stu-id="12556-157">Here are the commands for all the services in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="12556-158">指定您網域主機的名稱和用於登入的 UPN，並同時執行它們。</span><span class="sxs-lookup"><span data-stu-id="12556-158">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="12556-159">適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組</span><span class="sxs-lookup"><span data-stu-id="12556-159">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="12556-160">以下是使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組時，單一區塊中所有服務的命令。</span><span class="sxs-lookup"><span data-stu-id="12556-160">Here are the commands for all the services in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="12556-161">指定您網域主機的名稱和用於登入的 UPN，並同時執行它們。</span><span class="sxs-lookup"><span data-stu-id="12556-161">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="12556-162">使用多重要素驗證時的連線步驟</span><span class="sxs-lookup"><span data-stu-id="12556-162">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="12556-163">針對 Graph 的 Azure Active Directory PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="12556-163">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="12556-164">以下是使用多重要素驗證搭配適用於 Graph 的 Azure Active Directory PowerShell 模組時，用來在單一區塊中連接至多個 Microsoft 365 服務的所有命令。</span><span class="sxs-lookup"><span data-stu-id="12556-164">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="12556-165">適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組</span><span class="sxs-lookup"><span data-stu-id="12556-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="12556-166">以下是使用多重要素驗證搭配適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組時，用來在單一區塊中連接至多個 Microsoft 365 服務的所有命令。</span><span class="sxs-lookup"><span data-stu-id="12556-166">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="12556-167">關閉 PowerShell 視窗</span><span class="sxs-lookup"><span data-stu-id="12556-167">Close the PowerShell window</span></span>

<span data-ttu-id="12556-168">若要關閉 PowerShell 視窗，請執行此命令，以移除連線至商務用 Skype Online、SharePoint Online 及 Teams 的使用中工作階段：</span><span class="sxs-lookup"><span data-stu-id="12556-168">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="12556-169">請參閱</span><span class="sxs-lookup"><span data-stu-id="12556-169">See also</span></span>

- [<span data-ttu-id="12556-170">使用 PowerShell 連線至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="12556-170">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="12556-171">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="12556-171">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="12556-172">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="12556-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)