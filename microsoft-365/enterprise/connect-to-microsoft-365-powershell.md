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
ms.openlocfilehash: 33f9af45418ae8a1f126d2b321e7246201bd1f6e
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002402"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="a9c08-103">使用 PowerShell 連線至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9c08-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="a9c08-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="a9c08-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a9c08-105">適用於 Microsoft 365 的 PowerShell 允許您從命令列管理您的 Microsoft 365 設定。</span><span class="sxs-lookup"><span data-stu-id="a9c08-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="a9c08-106">要連線至 PowerShell，只需安裝所需的軟體，然後連線至 Microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="a9c08-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="a9c08-107">可以用來連線至 Microsoft 365 及管理使用者帳戶、群組和授權的 PowerShell 模組有兩個版本：</span><span class="sxs-lookup"><span data-stu-id="a9c08-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="a9c08-108">適用於圖表的 Azure Active Directory PowerShell，其 cmdlet 名稱中包含 *AzureAD*</span><span class="sxs-lookup"><span data-stu-id="a9c08-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="a9c08-109">適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組，其 cmdlets 名稱中包含 *MSol*</span><span class="sxs-lookup"><span data-stu-id="a9c08-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="a9c08-110">目前，適用於圖表的 Azure Active Directory PowerShell 模組無法完全取代適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中針對使用者、群組和授權管理的功能。</span><span class="sxs-lookup"><span data-stu-id="a9c08-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="a9c08-111">在某些情況下，您需要同時使用這兩個版本。</span><span class="sxs-lookup"><span data-stu-id="a9c08-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="a9c08-112">您可以在同一部電腦上安全地安裝這兩個版本。</span><span class="sxs-lookup"><span data-stu-id="a9c08-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a9c08-113">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="a9c08-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="a9c08-114">**作業系統**</span><span class="sxs-lookup"><span data-stu-id="a9c08-114">**Operating system**</span></span>

<span data-ttu-id="a9c08-115">必須使用 64 位元的 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="a9c08-115">You must use a 64-bit version of Windows.</span></span> <span data-ttu-id="a9c08-116">2014 年終止對 32 位元版本的適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組的支援。</span><span class="sxs-lookup"><span data-stu-id="a9c08-116">Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="a9c08-117">您可以使用下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="a9c08-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="a9c08-118">Windows 10、Windows 8.1、Windows 8 或 Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="a9c08-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="a9c08-119">Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="a9c08-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="a9c08-120">若為 Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2 SP1，請下載並安裝 [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="a9c08-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="a9c08-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a9c08-121">**PowerShell**</span></span>

- <span data-ttu-id="a9c08-122">針對 Azure Active Directory PowerShell 的圖表模組，請務必使用 PowerShell 版本 5.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="a9c08-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="a9c08-123">針對適用於 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，請務必使用 PowerShell 版本 5.1 或更新版本 (最多可至 PowerShell 版本 6)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-123">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6.</span></span> <span data-ttu-id="a9c08-124">無法使用 PowerShell 版本 7。</span><span class="sxs-lookup"><span data-stu-id="a9c08-124">You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="a9c08-125">這些程序適用於屬於 Microsoft 365 系統管理員角色成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9c08-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="a9c08-126">如需詳細資訊，請參閱[關於系統管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=532367)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-126">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a9c08-127">與 Azure Active Directory PowerShell for Graph 模組連線</span><span class="sxs-lookup"><span data-stu-id="a9c08-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="a9c08-128">在Azure Active Directory PowerShell 圖表模組中的命令，其 Cmdlet 名稱中會包含 *AzureAD*。</span><span class="sxs-lookup"><span data-stu-id="a9c08-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="a9c08-129">您可以安裝 [Azure Active Directory PowerShell 的圖表](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)或 [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-129">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="a9c08-130">針對需要 Azure Active Directory PowerShell for Graph 模組中新 Cmdlet 的程序，請按照下列步驟來安裝模組，並連線至您的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="a9c08-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="a9c08-131">如需支援不同版本的 Microsoft Windows 的詳細資訊，請參閱 [Azure Active Directory PowerShell for Graph 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="a9c08-132">步驟 1：安裝必要的軟體</span><span class="sxs-lookup"><span data-stu-id="a9c08-132">Step 1: Install the required software</span></span>

<span data-ttu-id="a9c08-133">這些步驟只需在電腦上執行一次。</span><span class="sxs-lookup"><span data-stu-id="a9c08-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="a9c08-134">但您可能需要定期更新軟體。</span><span class="sxs-lookup"><span data-stu-id="a9c08-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="a9c08-135">開啟提升權限的 Windows PowerShell 命令提示字元視窗 (以系統管理員身分執行 Windows PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="a9c08-136">執行此命令︰</span><span class="sxs-lookup"><span data-stu-id="a9c08-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   <span data-ttu-id="a9c08-137">如果系統提示您從不受信任的存放庫安裝模組，請鍵入 **Y** 並按 Enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="a9c08-137">If you're prompted to install a module from an untrusted repository, type **Y** and press Enter.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="a9c08-138">步驟 2：連接到您的 Microsoft 365 訂閱的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="a9c08-138">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="a9c08-139">若要使用帳戶名稱和密碼或使用多重要素驗證連接到您的 Microsoft 365 訂閱的 Azure Active Directory (Azure AD)，請從 Windows PowerShell 命令提示字元執行下列其中一個命令。</span><span class="sxs-lookup"><span data-stu-id="a9c08-139">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="a9c08-140">(不需提升權限)</span><span class="sxs-lookup"><span data-stu-id="a9c08-140">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="a9c08-141">Office 365 雲端</span><span class="sxs-lookup"><span data-stu-id="a9c08-141">Office 365 cloud</span></span> | <span data-ttu-id="a9c08-142">命令</span><span class="sxs-lookup"><span data-stu-id="a9c08-142">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="a9c08-143">Office 365 全球 (+GCC)</span><span class="sxs-lookup"><span data-stu-id="a9c08-143">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="a9c08-144">21 Vianet 運作的 Office 365</span><span class="sxs-lookup"><span data-stu-id="a9c08-144">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="a9c08-145">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="a9c08-145">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="a9c08-146">Office 365 美國政府 DoD 和 Office 365 美國政府 GCC High</span><span class="sxs-lookup"><span data-stu-id="a9c08-146">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="a9c08-147">在 **[登入您的帳戶]** 對話方塊中，輸入您的 Microsoft 365 公司或學校帳戶使用者名稱和密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a9c08-147">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="a9c08-148">如果使用多重要素驗證，請按照說明提供其他身份驗證資訊，例如驗證碼。</span><span class="sxs-lookup"><span data-stu-id="a9c08-148">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="a9c08-149">連線之後，您可以對 [Azure Active Directory PowerShell for Graph 模組](https://docs.microsoft.com/powershell/module/azuread)使用這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9c08-149">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a9c08-150">與適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組連線</span><span class="sxs-lookup"><span data-stu-id="a9c08-150">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="a9c08-151">在適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中的 Cmdlet 名稱會包含 *Msol*。</span><span class="sxs-lookup"><span data-stu-id="a9c08-151">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="a9c08-152">PowerShell 版本 7 和更新版本不支援適用於 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9c08-152">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="a9c08-153">針對 PowerShell 版本 7 和更高版本，請務必使用 Azure Active Directory PowerShell 的圖表模組或 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a9c08-153">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="a9c08-154">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9c08-154">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="a9c08-155">從 PowerShell 執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9c08-155">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="a9c08-156">步驟 1：安裝必要的軟體</span><span class="sxs-lookup"><span data-stu-id="a9c08-156">Step 1: Install the required software</span></span>

<span data-ttu-id="a9c08-157">這些步驟只需在電腦上執行一次。</span><span class="sxs-lookup"><span data-stu-id="a9c08-157">These steps are required only one time on your computer.</span></span> <span data-ttu-id="a9c08-158">但您可能需要定期更新軟體。</span><span class="sxs-lookup"><span data-stu-id="a9c08-158">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="a9c08-159">如果您未執行 Windows 10，請安裝 64 位元版本的 Microsoft Online Services 登入小幫手：[適用於 IT 專業人員的 Microsoft Online Services 登入小幫手 RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-159">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="a9c08-160">請按照以下步驟，安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：</span><span class="sxs-lookup"><span data-stu-id="a9c08-160">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="a9c08-161">開啟提升權限的 Windows PowerShell 命令提示字元 (以系統管理員身分執行 Windows PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-161">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="a9c08-162">執行 **Install-Module MSOnline** 命令。</span><span class="sxs-lookup"><span data-stu-id="a9c08-162">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="a9c08-163">如果系統提示您安裝 NuGet 提供者，請輸入 **Y**，然後按 Enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="a9c08-163">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="a9c08-164">如果系統提示您從 PSGallery 安裝模組，請輸入 **Y**，然後按 Enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="a9c08-164">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="a9c08-165">步驟 2：連接到您的 Microsoft 365 訂閱的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="a9c08-165">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="a9c08-166">若要使用帳戶名稱和密碼或使用多重要素驗證連接到您的 Microsoft 365 訂閱的 Azure AD，請從 Windows PowerShell 命令提示字元執行下列其中一個命令。</span><span class="sxs-lookup"><span data-stu-id="a9c08-166">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="a9c08-167">(不需提升權限)</span><span class="sxs-lookup"><span data-stu-id="a9c08-167">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="a9c08-168">Office 365 雲端</span><span class="sxs-lookup"><span data-stu-id="a9c08-168">Office 365 cloud</span></span> | <span data-ttu-id="a9c08-169">命令</span><span class="sxs-lookup"><span data-stu-id="a9c08-169">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="a9c08-170">Office 365 全球 (+GCC)</span><span class="sxs-lookup"><span data-stu-id="a9c08-170">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="a9c08-171">21 Vianet 運作的 Office 365</span><span class="sxs-lookup"><span data-stu-id="a9c08-171">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="a9c08-172">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="a9c08-172">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="a9c08-173">Office 365 美國政府 DoD 和 Office 365 美國政府 GCC High</span><span class="sxs-lookup"><span data-stu-id="a9c08-173">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="a9c08-174">在 **[登入您的帳戶]** 對話方塊中，輸入您的 Microsoft 365 公司或學校帳戶使用者名稱和密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a9c08-174">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="a9c08-175">如果使用多重要素驗證，請按照說明提供其他身份驗證資訊，例如驗證碼。</span><span class="sxs-lookup"><span data-stu-id="a9c08-175">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="a9c08-176">如何得知它的運作正常？</span><span class="sxs-lookup"><span data-stu-id="a9c08-176">How do you know it worked?</span></span>

<span data-ttu-id="a9c08-177">如果您沒有收到錯誤訊息，則已成功連線。</span><span class="sxs-lookup"><span data-stu-id="a9c08-177">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="a9c08-178">若要快速測試，請執行 Microsoft 365 cmdlet，例如 **Get-MsolUser**，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="a9c08-178">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="a9c08-179">如果收到錯誤訊息，請檢查下列問題：</span><span class="sxs-lookup"><span data-stu-id="a9c08-179">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="a9c08-180">**密碼錯誤是常見的問題**。</span><span class="sxs-lookup"><span data-stu-id="a9c08-180">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="a9c08-181">再次執行[步驟 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)，並密切注意您輸入的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="a9c08-181">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="a9c08-182">**適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組要求在您的電腦上啟用 Microsoft .NET Framework 3.5.* x*。您的電腦可能已安裝了較新的版本 (例如 4 或 4.5.\* x\*).</span><span class="sxs-lookup"><span data-stu-id="a9c08-182">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="a9c08-183">但可以啟用或停用舊版 .NET Framework 的回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="a9c08-183">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="a9c08-184">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a9c08-184">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="a9c08-185">針對 Windows Server 2012 或 Windows Server 2012 R2，請參閱[使用新增角色及功能精靈來啟用 .NET Framework 3.5](https://go.microsoft.com/fwlink/p/?LinkId=532368)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-185">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span></span>
    
  - <span data-ttu-id="a9c08-186">針對 Windows 7 或 Windows Server 2008 R2，請參閱[您無法開啟 Windows PowerShell 的 Azure Active Directory 模組](https://go.microsoft.com/fwlink/p/?LinkId=532370)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-186">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span></span>

  - <span data-ttu-id="a9c08-187">若為 Windows 10、Windows 8.1 和 Windows 8，請參閱[在 Windows 10、Windows 8.1 以及 Windows 8 上安裝 .NET Framework 3.5](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-187">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="a9c08-188">**您的適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組版本可能已過時。**</span><span class="sxs-lookup"><span data-stu-id="a9c08-188">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="a9c08-189">若要檢查，請在適用於 Microsoft 365 的 PowerShell 或適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a9c08-189">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="a9c08-190">如果傳回的版本號碼低於 *1.0.8070.2*，請將適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組解除安裝，然後從以上的[步驟 1](#step-1-install-the-required-software) 中安裝。</span><span class="sxs-lookup"><span data-stu-id="a9c08-190">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="a9c08-191">**如果您收到連線錯誤**，請參閲 [「Connect-MsolService：擲回類型例外狀況」錯誤](https://go.microsoft.com/fwlink/p/?LinkId=532377)。</span><span class="sxs-lookup"><span data-stu-id="a9c08-191">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="a9c08-192">訊息 **如果您收到「Get-Item：找不到路徑」錯誤訊息**，請執行此命令：</span><span class="sxs-lookup"><span data-stu-id="a9c08-192">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="a9c08-193">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a9c08-193">See also</span></span>

- [<span data-ttu-id="a9c08-194">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9c08-194">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="a9c08-195">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9c08-195">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="a9c08-196">在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="a9c08-196">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
