---
title: 輕量型基本組態
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用此測試實驗室指南來建立輕量測試環境，以測試 Microsoft 365 for enterprise。
ms.openlocfilehash: 2de0760cef7339f62229575b1e0a54b3c67a4e9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909703"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="93f57-103">輕量型基本組態</span><span class="sxs-lookup"><span data-stu-id="93f57-103">The lightweight base configuration</span></span>

<span data-ttu-id="93f57-104">*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="93f57-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="93f57-105">本文說明如何使用 Microsoft 365 E5 訂閱與執行 Windows 10 企業版的電腦建立簡化的環境。</span><span class="sxs-lookup"><span data-stu-id="93f57-105">This article describes how to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span>

![輕量型 Microsoft 365 企業版測試環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="93f57-107">建立輕量測試環境包含五個階段：</span><span class="sxs-lookup"><span data-stu-id="93f57-107">Creating a lightweight test environment involves five phases:</span></span>
- [<span data-ttu-id="93f57-108">階段1：建立您的 Microsoft 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="93f57-108">Phase 1: Create your Microsoft 365 E5 subscription</span></span>](#phase-1-create-your-microsoft-365-e5-subscription)
- [<span data-ttu-id="93f57-109">階段 2：設定 Office 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="93f57-109">Phase 2: Configure your Office 365 trial subscription</span></span>](#phase-2-configure-your-office-365-trial-subscription)
- [<span data-ttu-id="93f57-110">階段 3：新增 Microsoft 365 E5 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="93f57-110">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [<span data-ttu-id="93f57-111">階段 4：建立 Windows 10 企業版電腦</span><span class="sxs-lookup"><span data-stu-id="93f57-111">Phase 4: Create a Windows 10 Enterprise computer</span></span>](#phase-4-create-a-windows-10-enterprise-computer)
- [<span data-ttu-id="93f57-112">階段 5：將 Windows 10 電腦加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="93f57-112">Phase 5: Join your Windows 10 computer to Azure AD</span></span>](#phase-5-join-your-windows-10-computer-to-azure-ad)

<span data-ttu-id="93f57-113">使用所產生的環境來測試 [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise)的功能。</span><span class="sxs-lookup"><span data-stu-id="93f57-113">Use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="93f57-115">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請參閱 [適用于企業測試實驗室指南堆疊的 microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="93f57-115">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

>[!NOTE]
><span data-ttu-id="93f57-116">您可能會想要列印本文章，以記錄 在Office 365 試用版訂閱的 30 天中此環境所需的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="93f57-116">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="93f57-117">您可以輕鬆將試用訂閱延長 30 天。</span><span class="sxs-lookup"><span data-stu-id="93f57-117">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="93f57-118">若為永久測試環境，請建立具有個別 Azure AD 租用戶及少量授權的新付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="93f57-118">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="93f57-119">階段1：建立您的 Microsoft 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="93f57-119">Phase 1: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="93f57-120">我們從 Microsoft 365 E5 試用訂閱開始，然後新增 Microsoft 365 E5 訂閱給它。</span><span class="sxs-lookup"><span data-stu-id="93f57-120">We start with an Microsoft 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

>[!NOTE]
><span data-ttu-id="93f57-121">我們建議您建立 Office 365 的試用訂閱，使測試環境具有您目前所擁有的任何付費訂閱中的個別 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="93f57-121">We recommend that you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="93f57-122">這種分隔意味著您可以新增及移除測試承租人中的使用者和群組，而不會影響您的實際執行訂閱。</span><span class="sxs-lookup"><span data-stu-id="93f57-122">This separation means that you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>

<span data-ttu-id="93f57-123">若要開始 Microsoft 365 E5 試用版訂閱，您需要虛構的公司名稱和新 Microsoft 帳戶。</span><span class="sxs-lookup"><span data-stu-id="93f57-123">To start your Microsoft 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="93f57-p103">我們建議您使用公司名稱 Contoso 的變種作為公司名稱，也就是 Microsoft 範例內容中使用的虛構公司，但此為非必要的動作。在此處記錄您虛構公司名稱：</span><span class="sxs-lookup"><span data-stu-id="93f57-p103">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![線](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="93f57-p104">若要註冊新 Microsoft 帳戶，請移至 [https://outlook.com ](https://outlook.com)，並使用新電子郵件帳戶以及地址建立帳戶。您會使用這個帳戶來登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="93f57-p104">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
    - <span data-ttu-id="93f57-129">在此處記錄您新帳戶的名字和姓氏：</span><span class="sxs-lookup"><span data-stu-id="93f57-129">Record the first and last name of your new account here:</span></span> ![線](../media/Common-Images/TableLine.png)
    
    - <span data-ttu-id="93f57-131">在此處記錄新電子郵件帳戶地址：</span><span class="sxs-lookup"><span data-stu-id="93f57-131">Record the new email account address here:</span></span> ![線](../media/Common-Images/TableLine.png)<span data-ttu-id="93f57-133">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="93f57-133">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="93f57-134">註冊 Office 365 E5 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="93f57-134">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="93f57-135">在您的瀏覽器中，移至 [https://aka.ms/e5trial](https://aka.ms/e5trial) 。</span><span class="sxs-lookup"><span data-stu-id="93f57-135">In your browser, go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="93f57-136">在 **感謝您選擇 Office 365 E5** 頁面的步驟1中，輸入新的電子郵件帳戶位址。</span><span class="sxs-lookup"><span data-stu-id="93f57-136">In step 1 of the **Thank you for choosing Office 365 E5** page, enter your new email account address.</span></span>
3. <span data-ttu-id="93f57-137">在追蹤訂閱處理常式的步驟2中，輸入要求的資訊，然後執行驗證。</span><span class="sxs-lookup"><span data-stu-id="93f57-137">In step 2 of the trail subscription process, enter the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="93f57-138">在 [步驟 3] 中，輸入組織名稱，然後輸入將成為訂閱全域管理員的帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="93f57-138">In step 3, enter an organization name and then an account name that will be the global admin for the subscription.</span></span>
5. <span data-ttu-id="93f57-139">針對步驟 4，在此記錄登入頁面 (選取並複製)：</span><span class="sxs-lookup"><span data-stu-id="93f57-139">For step 4, record the sign-in page here (select and copy):</span></span> ![線](../media/Common-Images/TableLine.png)
6. <span data-ttu-id="93f57-141">在此記錄使用者識別碼：![線](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="93f57-141">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="93f57-142">記錄您在安全位置輸入的密碼。</span><span class="sxs-lookup"><span data-stu-id="93f57-142">Record the password that you entered in a secure location.</span></span>
   <span data-ttu-id="93f57-143">此值將被稱為 **「全域系統管理員名稱」**。</span><span class="sxs-lookup"><span data-stu-id="93f57-143">This value will be referred to as the **global administrator name**.</span></span>
7. <span data-ttu-id="93f57-144">選取 [ **移至設定**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-144">Select **Go to Setup**.</span></span>
8. <span data-ttu-id="93f57-145">在 Office 365 E5 設定中，選取 [ **繼續使用 *您的組織* onmicrosoft.com 電子郵件] 和**[登入]，然後選取 [結束]，然後再依序 **繼續**。</span><span class="sxs-lookup"><span data-stu-id="93f57-145">In Office 365 E5 Setup, select **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then select **Exit and continue later**.</span></span>

<span data-ttu-id="93f57-146">您應該會看到 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="93f57-146">You should see the Microsoft 365 admin center.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="93f57-147">階段 2：設定 Office 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="93f57-147">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="93f57-148">在這個階段中，您可以設定其他使用者使用您的訂閱，並指派他們 Office 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="93f57-148">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="93f57-149">若要使用電腦的 [Azure Active Directory PowerShell 的圖形模組連線到您的訂閱，請使用 [[連線至 Microsoft 365 與 PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)的指示]。</span><span class="sxs-lookup"><span data-stu-id="93f57-149">To connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer, use the instructions in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
    
<span data-ttu-id="93f57-150">在 [ **Windows PowerShell 憑證要求** ] 對話方塊中，輸入全域管理員名稱 (例如，[ *Jdoe@contosotoycompany.onmicrosoft.com*) ] 和 [密碼]。</span><span class="sxs-lookup"><span data-stu-id="93f57-150">In the **Windows PowerShell Credential Request** dialog box, enter the global administrator name (for example, *jdoe@contosotoycompany.onmicrosoft.com*) and password.</span></span>
  
<span data-ttu-id="93f57-151">填寫您的組織名稱 (例如， *contosotoycompany*) 、兩個字元的國家/地區代碼、通用帳戶密碼，然後從 PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="93f57-151">Fill in your organization name (for example, *contosotoycompany*), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="93f57-152">這裡會使用常見密碼，以便在測試環境中能自動化並輕鬆進行設定。</span><span class="sxs-lookup"><span data-stu-id="93f57-152">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="93f57-153">當然，對於生產訂閱，這是非常不鼓勵的。</span><span class="sxs-lookup"><span data-stu-id="93f57-153">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="93f57-154">記錄重要資訊供日後參考</span><span class="sxs-lookup"><span data-stu-id="93f57-154">Record key information for future reference</span></span>

<span data-ttu-id="93f57-155">若尚未記錄這些值，請立即進行記錄：</span><span class="sxs-lookup"><span data-stu-id="93f57-155">If you haven't already recorded these values, record them now:</span></span>
  
- <span data-ttu-id="93f57-156">全域系統管理員名稱：</span><span class="sxs-lookup"><span data-stu-id="93f57-156">Global administrator name:</span></span> ![線](../media/Common-Images/TableLine.png)<span data-ttu-id="93f57-158">.onmicrosoft.com (來自階段 1 的步驟 6)</span><span class="sxs-lookup"><span data-stu-id="93f57-158">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="93f57-159">也將此帳戶的密碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="93f57-159">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="93f57-160">您的試用訂閱組織名稱：</span><span class="sxs-lookup"><span data-stu-id="93f57-160">Your trial subscription organization name:</span></span> ![線](../media/Common-Images/TableLine.png) <span data-ttu-id="93f57-162">(來自階段 1 的步驟 4)</span><span class="sxs-lookup"><span data-stu-id="93f57-162">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="93f57-163">若要列出使用者 2、使用者 3、使用者 4 和使用者 5 的帳戶，從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="93f57-163">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="93f57-164">在此記錄帳戶名稱：</span><span class="sxs-lookup"><span data-stu-id="93f57-164">Record the account names here:</span></span>
    
  - <span data-ttu-id="93f57-165">使用者 2 的帳戶名稱：user2@</span><span class="sxs-lookup"><span data-stu-id="93f57-165">User 2 account name: user2@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="93f57-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="93f57-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="93f57-168">使用者 3 的帳戶名稱：user3@</span><span class="sxs-lookup"><span data-stu-id="93f57-168">User 3 account name: user3@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="93f57-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="93f57-170">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="93f57-171">使用者 4 的帳戶名稱：user4@</span><span class="sxs-lookup"><span data-stu-id="93f57-171">User 4 account name: user4@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="93f57-173">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="93f57-173">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="93f57-174">使用者 5 的帳戶名稱：user5@</span><span class="sxs-lookup"><span data-stu-id="93f57-174">User 5 account name: user5@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="93f57-176">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="93f57-176">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="93f57-177">一併將這些帳戶的常見密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="93f57-177">Also record the common password for these accounts in a secure location.</span></span>
   
### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="93f57-178">使用 Office 365 測試環境</span><span class="sxs-lookup"><span data-stu-id="93f57-178">Using an Office 365 test environment</span></span>

<span data-ttu-id="93f57-179">如果您只需要 Office 365 測試環境，您不需要閱讀本文的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="93f57-179">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="93f57-180">如需同時適用于 Office 365 和 Microsoft 365 的其他測試實驗室指南，請參閱 [Microsoft 365 for Enterprise Test Lab 指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="93f57-180">For additional Test Lab Guides that apply to both Office 365 and Microsoft 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="93f57-181">階段 3：新增 Microsoft 365 E5 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="93f57-181">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="93f57-182">在此階段中，您可以註冊 Microsoft 365 E5 試用版訂閱，並將它新增至與 Office 365 E5 試用版訂閱相同的組織。</span><span class="sxs-lookup"><span data-stu-id="93f57-182">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="93f57-183">首先，新增 Microsoft 365 E5 試用版訂閱，並將新的 Microsoft 365 授權指派給您的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="93f57-183">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="93f57-184">在網際網路瀏覽器私人視窗中，使用您的全域系統管理員帳號憑證，登入 Microsoft 365 系統管理中心 [https://admin.microsoft.com](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="93f57-184">In an internet browser private window, use your global administrator account credentials to sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="93f57-185">在 [ **Microsoft 365 系統管理中心** ] 頁面上，于左側導覽中，選取 [ **帳單 > 購買服務**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-185">On the **Microsoft 365 admin center** page, in the left navigation, select **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="93f57-186">在 [ **購買服務** ] 頁面上，選取 [ **Microsoft 365 E5**]，然後選取 [ **取得免費試用版**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-186">On the **Purchase services** page, select **Microsoft 365 E5**, and then select **Get free trial**.</span></span>

4. <span data-ttu-id="93f57-187">在 [ **Microsoft 365 E5 試用** ] 頁面上，決定接收短信或電話、輸入您的電話號碼，然後選取 [ **文字 me** ] 或 [ **呼叫我**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span></span> <span data-ttu-id="93f57-188">執行驗證。</span><span class="sxs-lookup"><span data-stu-id="93f57-188">Perform the verification.</span></span>

5. <span data-ttu-id="93f57-189">在 [ **確認您的訂單** ] 頁面上，選取 [ **立即試用**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-189">On the **Confirm your order** page, select **Try now**.</span></span>

6. <span data-ttu-id="93f57-190">在 [ **訂單接收** ] 頁面上，選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-190">On the **Order receipt** page, select **Continue**.</span></span>

7. <span data-ttu-id="93f57-191">在 Microsoft 365 系統管理中心中，選取 [ **使用者] >**[作用中的使用者]。</span><span class="sxs-lookup"><span data-stu-id="93f57-191">In the Microsoft 365 admin center, select **Users > Active users**.</span></span>

8. <span data-ttu-id="93f57-192">在 [作用中的 **使用者**] 中，選取您的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="93f57-192">In **Active users**, select your administrator account.</span></span>

9. <span data-ttu-id="93f57-193">選取 [ **授權和應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-193">Select **Licenses and apps**.</span></span>

10. <span data-ttu-id="93f57-194">停用 Office 365 企業版 E5 授權，然後啟用 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="93f57-194">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="93f57-195">選取 [ **儲存變更**]，然後關閉 [使用者帳戶資訊] 窗格。</span><span class="sxs-lookup"><span data-stu-id="93f57-195">Select **Save changes**, and then close the user account information pane.</span></span>

<span data-ttu-id="93f57-196">接下來，請為所有其他帳戶 (使用者 2、使用者 3、使用者 4 和使用者 5) 重複先前程序的步驟 8 至 11。</span><span class="sxs-lookup"><span data-stu-id="93f57-196">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="93f57-197">Microsoft 365 E5 試用訂閱的長度為30天。</span><span class="sxs-lookup"><span data-stu-id="93f57-197">The length of the Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="93f57-198">若為永久測試環境，請將此試用訂閱轉換為具少量授權的付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="93f57-198">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="93f57-199">測試環境現在擁有：</span><span class="sxs-lookup"><span data-stu-id="93f57-199">Your test environment now has:</span></span>
  
- <span data-ttu-id="93f57-200">Microsoft 365 E5 試用版訂閱。</span><span class="sxs-lookup"><span data-stu-id="93f57-200">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="93f57-201">所有適當的使用者帳戶 (全域系統管理員或所有五個使用者帳戶) 皆已可使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="93f57-201">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="93f57-202">您產生的設定會新增 Microsoft 365 E5，如下所示：</span><span class="sxs-lookup"><span data-stu-id="93f57-202">Your resulting configuration, which adds Microsoft 365 E5, looks like this:</span></span>
  
![Microsoft 365 企業版測試環境的階段 3](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="93f57-204">階段 4：建立 Windows 10 企業版電腦</span><span class="sxs-lookup"><span data-stu-id="93f57-204">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="93f57-205">在這個階段中，您會建立執行 Windows 10 企業版的獨立電腦，作為實體電腦、虛擬機器或是 Azure 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="93f57-205">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="93f57-206">實體電腦</span><span class="sxs-lookup"><span data-stu-id="93f57-206">Physical computer</span></span>

<span data-ttu-id="93f57-207">在個人電腦上，安裝 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="93f57-207">On a personal computer, install Windows 10 Enterprise.</span></span> <span data-ttu-id="93f57-208">您可以在 [這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。</span><span class="sxs-lookup"><span data-stu-id="93f57-208">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="93f57-209">虛擬機器</span><span class="sxs-lookup"><span data-stu-id="93f57-209">Virtual machine</span></span>

<span data-ttu-id="93f57-210">使用您選擇的虛擬機器監控程式建立虛擬機器，然後在其上安裝 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="93f57-210">Use the hypervisor of your choice to create a virtual machine, and then install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="93f57-211">您可以在 [這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。</span><span class="sxs-lookup"><span data-stu-id="93f57-211">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="93f57-212">Azure 中的虛擬機器</span><span class="sxs-lookup"><span data-stu-id="93f57-212">Virtual machine in Azure</span></span>

<span data-ttu-id="93f57-p111">若要在 Microsoft Azure 中建立 Windows 10 虛擬機器，***您必須擁有以 Visual Studio 為基礎的訂閱***，其具有 Windows 10 企業版的影像存取權。其他類型的 Azure 訂閱，例如試用版與付費訂閱，沒有此影像的存取權。如需最新資訊，請參閱 [在 Azure 中使用 Windows 用戶端進行開發/測試案例](/azure/virtual-machines/windows/client-images)。</span><span class="sxs-lookup"><span data-stu-id="93f57-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="93f57-216">[!附註] 下列命令集會使用最新版的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="93f57-216">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="93f57-217">請參閱[開始使用 Azure PowerShell Cmdlet](/powershell/azureps-cmdlets-docs/)。</span><span class="sxs-lookup"><span data-stu-id="93f57-217">See [Get started with Azure PowerShell cmdlets](/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="93f57-218">這些命令會將建立一個名為 WIN10 的 Windows 10 企業版虛擬機器，以及其所有必要基礎結構，包括資源群組、儲存體帳戶和虛擬網路。</span><span class="sxs-lookup"><span data-stu-id="93f57-218">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="93f57-219">如果您已熟悉 Azure 基礎結構服務，請將這些指示加以修改，以符合您目前部署的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="93f57-219">If you are already familiar with Azure infrastructure services, adapt these instructions to suit your currently deployed infrastructure.</span></span>
  
<span data-ttu-id="93f57-220">首先，啟動 Microsoft PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="93f57-220">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="93f57-221">使用此命令登入您的 Azure 帳戶。</span><span class="sxs-lookup"><span data-stu-id="93f57-221">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="93f57-222">使用此命令取得您的訂閱名稱。</span><span class="sxs-lookup"><span data-stu-id="93f57-222">Get your subscription name using this  command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="93f57-223">設定 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="93f57-223">Set your Azure subscription.</span></span> <span data-ttu-id="93f57-224">以正確的名稱取代引號內的所有專案（包括 \< and > 字元）。</span><span class="sxs-lookup"><span data-stu-id="93f57-224">Replace everything within the quotation marks, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="93f57-225">接著，建立新的資源群組。</span><span class="sxs-lookup"><span data-stu-id="93f57-225">Next, create a new resource group.</span></span> <span data-ttu-id="93f57-226">若要判斷資源群組名稱是否是唯一的，可使用此命令來列出現有的資源群組。</span><span class="sxs-lookup"><span data-stu-id="93f57-226">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="93f57-227">使用這些命令建立新的資源群組。</span><span class="sxs-lookup"><span data-stu-id="93f57-227">Create your new resource group with these commands.</span></span> <span data-ttu-id="93f57-228">以正確的名稱取代引號內的所有專案（包括 \< and > 字元）。</span><span class="sxs-lookup"><span data-stu-id="93f57-228">Replace everything within the quotation marks, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="93f57-229">接下來，使用下列命令建立新的虛擬網路和 WIN10 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="93f57-229">Next, create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="93f57-230">出現提示時，請提供 WIN10 本機系統管理員帳戶的名稱和密碼，並將它們儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="93f57-230">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="93f57-231">階段 5：將 Windows 10 電腦加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="93f57-231">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="93f57-232">建立實體或虛擬機器的 Windows 10 企業版之後，使用本機系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="93f57-232">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93f57-233">針對 Azure 中的虛擬機器，使用  [這些指示](/azure/virtual-machines/windows/connect-logon) 來連線至該虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="93f57-233">For a virtual machine in Azure, use  [these instructions](/azure/virtual-machines/windows/connect-logon) to connect to it.</span></span>
  
<span data-ttu-id="93f57-234">接下來，將 WIN10 電腦加入 Microsoft 365 E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="93f57-234">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="93f57-235">在 WIN10 電腦的桌面上，選取 [ **啟動 > 設定] > 帳戶 > 存取工作或學校 > Connect**。</span><span class="sxs-lookup"><span data-stu-id="93f57-235">On the desktop of the WIN10 computer, select **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="93f57-236">在 [ **設定公司或學校帳戶** ] 對話方塊中，選取 [將 **此裝置加入 Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-236">In the **Set up a work or school account** dialog box, select **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="93f57-237">在 [ **工作或學校帳戶**] 中，輸入您 Microsoft 365 E5 訂閱的全域系統管理員帳戶名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="93f57-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span></span>
    
4. <span data-ttu-id="93f57-238">在 [ **輸入密碼**] 中，輸入全域管理員帳戶的密碼，然後選取 [登 **入**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-238">In **Enter password**, enter the password for your global administrator account, and then select **Sign in**.</span></span>
    
5. <span data-ttu-id="93f57-239">當系統提示您確認這是您的組織時，請選取 [ **加入**]，然後選取 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-239">When prompted to make sure that this is your organization, select **Join**, and then select **Done**.</span></span>
    
6. <span data-ttu-id="93f57-240">關閉設定視窗。</span><span class="sxs-lookup"><span data-stu-id="93f57-240">Close the settings window.</span></span>
    
<span data-ttu-id="93f57-241">接下來，在 WIN10 電腦上安裝適用于 enterprise 的 Microsoft 365 應用程式：</span><span class="sxs-lookup"><span data-stu-id="93f57-241">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer:</span></span>
  
1. <span data-ttu-id="93f57-242">開啟 Microsoft Edge 瀏覽器，並使用您的全域系統管理員帳號憑證登入 [microsoft 365 系統管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="93f57-242">Open the Microsoft Edge browser and sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="93f57-243">在 [ **Microsoft Office 首頁** ] 索引標籤上，選取 [ **安裝 Office**]。</span><span class="sxs-lookup"><span data-stu-id="93f57-243">On the **Microsoft Office Home** tab, select **Install Office**.</span></span>
    
3. <span data-ttu-id="93f57-244">當系統提示您執行的動作時，請選取 [**執行**]，然後為 [**使用者帳戶控制** **] 選取 [是]** 。</span><span class="sxs-lookup"><span data-stu-id="93f57-244">When prompted with what to do, select **Run**, and then select **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="93f57-245">等候 Office 完成其安裝。</span><span class="sxs-lookup"><span data-stu-id="93f57-245">Wait for Office to complete its installation.</span></span> <span data-ttu-id="93f57-246">當您看到 **全部設定！**，請選取 [ **關閉** ] 兩次。</span><span class="sxs-lookup"><span data-stu-id="93f57-246">When you see **You're all set!**, select **Close** twice.</span></span>
    
<span data-ttu-id="93f57-247">您產生的環境如下所示：</span><span class="sxs-lookup"><span data-stu-id="93f57-247">Your resulting environment looks like this:</span></span>

![Microsoft 365 企業版測試環境的階段 5](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="93f57-249">這包括已完成下列項目的 WIN10 電腦：</span><span class="sxs-lookup"><span data-stu-id="93f57-249">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="93f57-250">已加入您的 Microsoft 365 E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="93f57-250">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="93f57-251">已在 Microsoft Intune (EMS) 中註冊為 Azure AD 裝置。</span><span class="sxs-lookup"><span data-stu-id="93f57-251">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="93f57-252">已安裝適用于企業的 Microsoft 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="93f57-252">Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="93f57-253">您現在已準備好嘗試使用 [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="93f57-253">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="93f57-254">後續步驟</span><span class="sxs-lookup"><span data-stu-id="93f57-254">Next steps</span></span>

<span data-ttu-id="93f57-255">探索這些額外的測試實驗室指南集合：</span><span class="sxs-lookup"><span data-stu-id="93f57-255">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="93f57-256">身分識別</span><span class="sxs-lookup"><span data-stu-id="93f57-256">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="93f57-257">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="93f57-257">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="93f57-258">資訊保護</span><span class="sxs-lookup"><span data-stu-id="93f57-258">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="93f57-259">另請參閱</span><span class="sxs-lookup"><span data-stu-id="93f57-259">See also</span></span>

[<span data-ttu-id="93f57-260">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="93f57-260">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="93f57-261">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="93f57-261">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="93f57-262">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="93f57-262">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)