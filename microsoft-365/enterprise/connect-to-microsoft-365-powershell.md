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
ms.openlocfilehash: 9b4cdbe9fcdea48df456e75095f8d269ab84696f
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950553"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="d102c-103">使用 PowerShell 連線至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d102c-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="d102c-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="d102c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d102c-105">適用於 Microsoft 365 的 PowerShell 可讓您從命令列管理您的 Microsoft 365 設定。</span><span class="sxs-lookup"><span data-stu-id="d102c-105">PowerShell for Microsoft 365 lets you manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="d102c-106">連線至 PowerShell 是簡單的程序，您可以在其中安裝必要的軟體，然後連線至您的 Microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="d102c-106">Connecting to PowerShell is a simple process where you install the required software and then connect to your Microsoft 365 organization.</span></span> 

<span data-ttu-id="d102c-107">您用來連線至 Microsoft 365 及管理使用者帳戶、群組和授權的 PowerShell 模組有兩個版本：</span><span class="sxs-lookup"><span data-stu-id="d102c-107">There are two versions of the PowerShell module that you use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="d102c-108">Azure Active Directory PowerShell for Graph (名稱中包含 **AzureAD** 的 Cmdlet)</span><span class="sxs-lookup"><span data-stu-id="d102c-108">Azure Active Directory PowerShell for Graph (cmdlets include **AzureAD** in their name)</span></span>
- <span data-ttu-id="d102c-109">適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組 (名稱中包含 **MSol** 的 Cmdlet)</span><span class="sxs-lookup"><span data-stu-id="d102c-109">Microsoft Azure Active Directory Module for Windows PowerShell (cmdlets include **MSol** in their name)</span></span> 

<span data-ttu-id="d102c-110">自本文發行日期起，Azure Active Directory PowerShell for Graph 模組無法完全取代適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中針對使用者、群組和授權管理的 Cmdlet 功能。</span><span class="sxs-lookup"><span data-stu-id="d102c-110">As of the date of this article, the Azure Active Directory PowerShell for Graph module does not completely replace the functionality in the cmdlets of Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="d102c-111">在某些情況下，您需要同時使用這兩個版本。</span><span class="sxs-lookup"><span data-stu-id="d102c-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="d102c-112">您可以在同一部電腦上安全地安裝這兩個版本。</span><span class="sxs-lookup"><span data-stu-id="d102c-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d102c-113">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d102c-113">What do you need to know before you begin?</span></span>

<span data-ttu-id="d102c-114">您可以使用下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="d102c-114">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="d102c-115">Windows 10、Windows 8.1、Windows 8 或 Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="d102c-115">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="d102c-116">Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="d102c-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

    > [!NOTE]
    > <span data-ttu-id="d102c-117">針對 Azure Active Directory PowerShell 的圖表模組，請務必使用 PowerShell 版本 5.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="d102c-117">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span> <span data-ttu-id="d102c-118">針對適用於 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，請務必使用 PowerShell 版本 5.1 或更新版本 (最多可至 PowerShell 版本 6)。</span><span class="sxs-lookup"><span data-stu-id="d102c-118">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later up to PowerShell version 6.</span></span> <span data-ttu-id="d102c-119">無法使用 PowerShell 版本 7。</span><span class="sxs-lookup"><span data-stu-id="d102c-119">You cannot use PowerShell version 7.</span></span> <span data-ttu-id="d102c-120">若為 Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2 SP1，請下載並安裝 [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="d102c-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d102c-p104">請使用 64 位元的 Windows 版本。對 Windows PowerShell 的 Microsoft Azure Active Directory 模組 32 位元版本的支援已在 2014 年 10 月終止。</span><span class="sxs-lookup"><span data-stu-id="d102c-p104">Use a 64-bit version of Windows. Support for the 32-bit version the Microsoft Azure Active Directory Module for Windows PowerShell was discontinued in October of 2014.</span></span>
    
<span data-ttu-id="d102c-123">這些程序適用於屬於 Microsoft 365 系統管理員角色成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="d102c-123">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="d102c-124">如需詳細資訊，請參閱[關於系統管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=532367)。</span><span class="sxs-lookup"><span data-stu-id="d102c-124">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d102c-125">與 Azure Active Directory PowerShell for Graph 模組連線</span><span class="sxs-lookup"><span data-stu-id="d102c-125">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="d102c-126">在Azure Active Directory PowerShell 圖表模組中的命令，其 Cmdlet 名稱中會包含 **AzureAD**。</span><span class="sxs-lookup"><span data-stu-id="d102c-126">Commands in the Azure Active Directory PowerShell for Graph module have **AzureAD** in their cmdlet name.</span></span> <span data-ttu-id="d102c-127">您可以安裝 [Azure Active Directory PowerShell 的圖表](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)或 [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)。</span><span class="sxs-lookup"><span data-stu-id="d102c-127">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="d102c-128">針對需要 Azure Active Directory PowerShell for Graph 模組中新 Cmdlet 的程序，請使用下列步驟來安裝模組，並連線至您的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="d102c-128">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, use these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="d102c-129">如需支援不同版本的 Microsoft Windows 的詳細資訊，請參閱 [Azure Active Directory PowerShell for Graph 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。</span><span class="sxs-lookup"><span data-stu-id="d102c-129">See [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) for information about the support for different versions of Microsoft Windows.</span></span>

### <a name="step-1-install-required-software"></a><span data-ttu-id="d102c-130">步驟 1：安裝必要的軟體</span><span class="sxs-lookup"><span data-stu-id="d102c-130">Step 1: Install required software</span></span>

<span data-ttu-id="d102c-p107">這些步驟只需您在電腦上執行一次，而不必在每次連線時執行。不過，您可能需要定期安裝較新的軟體版本。</span><span class="sxs-lookup"><span data-stu-id="d102c-p107">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1. <span data-ttu-id="d102c-133">開啟提升權限的 Windows PowerShell 命令提示字元 (以系統管理員身分執行 Windows PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="d102c-133">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="d102c-134">在 [系統管理員：Windows PowerShell] 命令視窗中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d102c-134">In the **Administrator: Windows PowerShell** command window, run this command:</span></span>
    
  ```powershell
  Install-Module -Name AzureAD
  ```

<span data-ttu-id="d102c-135">如果出現提示，指出需安裝來自不受信任存放庫的模組，請輸入 **Y**，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="d102c-135">If prompted about installing a module from an untrusted repository, type **Y** and press ENTER.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="d102c-136">步驟 2：連接到您的 Microsoft 365 訂閱的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="d102c-136">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="d102c-137">若要使用帳戶名稱和密碼或使用多重要素驗證 (MFA) 連接到您的 Microsoft 365 訂閱的 Azure AD，請從 Windows PowerShell 命令提示字元(不需提升權限) 執行下列其中一個命令。</span><span class="sxs-lookup"><span data-stu-id="d102c-137">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="d102c-138">Office 365 雲端</span><span class="sxs-lookup"><span data-stu-id="d102c-138">Office 365 cloud</span></span> | <span data-ttu-id="d102c-139">命令</span><span class="sxs-lookup"><span data-stu-id="d102c-139">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="d102c-140">Office 365 全球 (+GCC)</span><span class="sxs-lookup"><span data-stu-id="d102c-140">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="d102c-141">21 Vianet 運作的 Office 365</span><span class="sxs-lookup"><span data-stu-id="d102c-141">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="d102c-142">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="d102c-142">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="d102c-143">Office 365 美國政府 DoD 和 Office 365 美國政府 GCC High</span><span class="sxs-lookup"><span data-stu-id="d102c-143">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="d102c-144">在 [登入您的帳戶]\*\*\*\* 對話方塊中，輸入您的 Microsoft 365 公司或學校帳戶使用者名稱和密碼，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d102c-144">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="d102c-145">如果您使用 MFA，請遵循其他對話方塊中的指示，提供更多的驗證資訊，例如驗證碼。</span><span class="sxs-lookup"><span data-stu-id="d102c-145">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

<span data-ttu-id="d102c-146">連線之後，您可以對 [Azure Active Directory PowerShell for Graph 模組](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory)使用這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d102c-146">After connecting, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span></span>
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d102c-147">與適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組連線</span><span class="sxs-lookup"><span data-stu-id="d102c-147">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d102c-148">在適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中，命令的 Cmdlet 名稱會包含 **Msol**。</span><span class="sxs-lookup"><span data-stu-id="d102c-148">Commands in the Microsoft Azure Active Directory Module for Windows PowerShell have **Msol** in their cmdlet name.</span></span>

<span data-ttu-id="d102c-149">PowerShell 版本 7 和更新版本不支援適用於 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d102c-149">PowerShell version 7 and later do not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="d102c-150">針對 PowerShell 版本 7 和更高版本，請務必使用 Azure Active Directory PowerShell 的圖表模組或 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d102c-150">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="d102c-151">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d102c-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="d102c-152">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="d102c-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span> 
    
### <a name="step-1-install-required-software"></a><span data-ttu-id="d102c-153">步驟 1：安裝必要的軟體</span><span class="sxs-lookup"><span data-stu-id="d102c-153">Step 1: Install required software</span></span>

<span data-ttu-id="d102c-p110">這些步驟只需您在電腦上執行一次，而不必在每次連線時執行。不過，您可能需要定期安裝較新的軟體版本。</span><span class="sxs-lookup"><span data-stu-id="d102c-p110">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1.  <span data-ttu-id="d102c-156">如果您未執行 Windows 10，請安裝 64 位元版本的 Microsoft Online Services 登入小幫手：[適用於 IT 專業人員的 Microsoft Online Services 登入小幫手 RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152)。</span><span class="sxs-lookup"><span data-stu-id="d102c-156">If you are not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="d102c-157">以下列步驟安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：</span><span class="sxs-lookup"><span data-stu-id="d102c-157">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
  - <span data-ttu-id="d102c-158">開啟提升權限的 Windows PowerShell 命令提示字元 (以系統管理員身分執行 Windows PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="d102c-158">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
  - <span data-ttu-id="d102c-159">執行 **Install-Module MSOnline** 命令。</span><span class="sxs-lookup"><span data-stu-id="d102c-159">Run the **Install-Module MSOnline** command.</span></span>
  - <span data-ttu-id="d102c-160">如果系統提示您安裝 NuGet 提供者，請輸入 **Y**，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="d102c-160">If prompted to install the NuGet provider, type **Y** and press ENTER.</span></span>
  - <span data-ttu-id="d102c-161">如果系統提示您從 PSGallery 安裝模組，請輸入 **Y**，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="d102c-161">If prompted to install the module from PSGallery, type **Y** and press ENTER.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="d102c-162">步驟 2：連接到您的 Microsoft 365 訂閱的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="d102c-162">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="d102c-163">若要使用帳戶名稱和密碼或使用多重要素驗證 (MFA) 連接到您的 Microsoft 365 訂閱的 Azure AD，請從 Windows PowerShell 命令提示字元(不需提升權限) 執行下列其中一個命令。</span><span class="sxs-lookup"><span data-stu-id="d102c-163">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="d102c-164">Office 365 雲端</span><span class="sxs-lookup"><span data-stu-id="d102c-164">Office 365 cloud</span></span> | <span data-ttu-id="d102c-165">命令</span><span class="sxs-lookup"><span data-stu-id="d102c-165">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="d102c-166">Office 365 全球 (+GCC)</span><span class="sxs-lookup"><span data-stu-id="d102c-166">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="d102c-167">21 Vianet 運作的 Office 365</span><span class="sxs-lookup"><span data-stu-id="d102c-167">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="d102c-168">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="d102c-168">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="d102c-169">Office 365 美國政府 DoD 和 Office 365 美國政府 GCC High</span><span class="sxs-lookup"><span data-stu-id="d102c-169">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="d102c-170">在 [登入您的帳戶]\*\*\*\* 對話方塊中，輸入您的 Microsoft 365 公司或學校帳戶使用者名稱和密碼，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d102c-170">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="d102c-171">如果您使用 MFA，請遵循其他對話方塊中的指示，提供更多的驗證資訊，例如驗證碼。</span><span class="sxs-lookup"><span data-stu-id="d102c-171">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d102c-172">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="d102c-172">How do you know this worked?</span></span>

<span data-ttu-id="d102c-173">如果您未收到任何錯誤，便已順利連線。</span><span class="sxs-lookup"><span data-stu-id="d102c-173">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="d102c-174">若要做快速測試，您可以執行一個 Microsoft 365 Cmdlet (例如 **Get-MsolUser**)，然後檢視結果。</span><span class="sxs-lookup"><span data-stu-id="d102c-174">A quick test is to run a Microsoft 365 cmdlet—for example, **Get-MsolUser** —and see the results.</span></span>
  
<span data-ttu-id="d102c-175">如果出現錯誤，請檢查下列需求：</span><span class="sxs-lookup"><span data-stu-id="d102c-175">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="d102c-176">**密碼錯誤是常見的問題**。</span><span class="sxs-lookup"><span data-stu-id="d102c-176">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="d102c-177">再次執行步驟 2。</span><span class="sxs-lookup"><span data-stu-id="d102c-177">Run Step 2 again.</span></span> <span data-ttu-id="d102c-178">並密切注意您輸入的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="d102c-178">and pay close attention to the user name and password you enter.</span></span>
    
- <span data-ttu-id="d102c-179">**Microsoft Azure Active Directory Module for Windows PowerShell 要求在您的電腦上啟用 Microsoft .NET Framework 3.5.* x* 功能**。您的電腦可能已安裝了較新的版本 (例如 4 或 4.5.* x*)，但可以啟用或停用舊版 .NET Framework 的回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="d102c-179">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that the Microsoft .NET Framework 3.5.* x* feature is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*), but backwards compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="d102c-180">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="d102c-180">For more information, see the following topics:</span></span>
    
  - <span data-ttu-id="d102c-181">針對 Windows Server 2012 或 Windows Server 2012 R2，請參閱[使用新增角色及功能精靈來啟用 .NET Framework 3.5](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span><span class="sxs-lookup"><span data-stu-id="d102c-181">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span></span>
    
  - <span data-ttu-id="d102c-182">針對 Windows 7 或 Windows Server 2008 R2，請參閱[您無法開啟 Windows PowerShell 的 Azure Active Directory 模組](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span><span class="sxs-lookup"><span data-stu-id="d102c-182">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span></span>

  - <span data-ttu-id="d102c-183">若為 Windows 10、Windows 8.1 和 Windows 8，請參閱[在 Windows 10、Windows 8.1 以及 Windows 8 上安裝 .NET Framework 3.5](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="d102c-183">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span></span>

  
- <span data-ttu-id="d102c-184">**您的適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組版本可能已過時。**</span><span class="sxs-lookup"><span data-stu-id="d102c-184">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="d102c-185">若要檢查，請在適用於 Microsoft 365 的 PowerShell 或適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d102c-185">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="d102c-186">如果傳回的版本號碼低於 1.0.8070.2 值，請將適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組解除安裝，然後從以上的步驟 1 中安裝。</span><span class="sxs-lookup"><span data-stu-id="d102c-186">If the version number returned is lower than the value 1.0.8070.2, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from Step 1 above.</span></span>

- <span data-ttu-id="d102c-187">**如果您收到連線錯誤，請參閱本主題：** [「Connect-MsolService：擲回類型例外狀況」錯誤](https://go.microsoft.com/fwlink/p/?LinkId=532377)。</span><span class="sxs-lookup"><span data-stu-id="d102c-187">**If you receive a connection error, see this topic:** ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="d102c-188">**如果您收到「Get-Item：找不到路徑」錯誤，請使用以下命令：**</span><span class="sxs-lookup"><span data-stu-id="d102c-188">**If you receive a "Get-Item : Cannot find path" error, use this command:**</span></span> 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a><span data-ttu-id="d102c-189">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d102c-189">See also</span></span>

- [<span data-ttu-id="d102c-190">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d102c-190">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="d102c-191">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d102c-191">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="d102c-192">在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="d102c-192">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
