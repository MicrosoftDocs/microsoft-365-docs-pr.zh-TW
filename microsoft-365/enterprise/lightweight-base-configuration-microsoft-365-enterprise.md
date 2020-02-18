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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用這個「測試實驗室指南」建立輕量型測試環境，以測試 Microsoft 365 企業版。
ms.openlocfilehash: 4e90cc01cb37664f3084daf7295e9d59052809af
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067078"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="87ec0-103">輕量型基本組態</span><span class="sxs-lookup"><span data-stu-id="87ec0-103">The lightweight base configuration</span></span>

<span data-ttu-id="87ec0-104">*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*</span><span class="sxs-lookup"><span data-stu-id="87ec0-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="87ec0-105">本文提供建立具備 Microsoft 365 E5 訂閱與執行 Windows 10 企業版電腦的簡化環境的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="87ec0-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![輕量型 Microsoft 365 企業版測試環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="87ec0-107">使用產生的環境來測試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的功能。</span><span class="sxs-lookup"><span data-stu-id="87ec0-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="87ec0-109">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中文件的所有視覺對應。</span><span class="sxs-lookup"><span data-stu-id="87ec0-109">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="87ec0-110">階段 1：建立您的 Office 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="87ec0-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="87ec0-111">我們首先使用 Office 365 E5 試用版訂閱，然後再新增 Microsoft 365 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="87ec0-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="87ec0-112">若要開始 Office 365 E5 試用訂閱，您需要虛構的公司名稱和新 Microsoft 帳戶。</span><span class="sxs-lookup"><span data-stu-id="87ec0-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="87ec0-p101">我們建議您使用公司名稱 Contoso 的變種作為公司名稱，也就是 Microsoft 範例內容中使用的虛構公司，但此為非必要的動作。在此處記錄您虛構公司名稱：</span><span class="sxs-lookup"><span data-stu-id="87ec0-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![線](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="87ec0-p102">若要註冊新 Microsoft 帳戶，請移至 [https://outlook.com ](https://outlook.com)，並使用新電子郵件帳戶以及地址建立帳戶。您會使用這個帳戶來登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="87ec0-118">在此處記錄您新帳戶的名字和姓氏：</span><span class="sxs-lookup"><span data-stu-id="87ec0-118">Record the first and last name of your new account here:</span></span> ![線](../media/Common-Images/TableLine.png)
    
  - <span data-ttu-id="87ec0-120">在此處記錄新電子郵件帳戶地址：</span><span class="sxs-lookup"><span data-stu-id="87ec0-120">Record the new email account address here:</span></span> ![線](../media/Common-Images/TableLine.png)<span data-ttu-id="87ec0-122">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="87ec0-122">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="87ec0-123">註冊 Office 365 E5 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="87ec0-123">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="87ec0-124">在您的電腦上開啟網際網路瀏覽器，然後移至 [https://aka.ms/e5trial](https://aka.ms/e5trial)。</span><span class="sxs-lookup"><span data-stu-id="87ec0-124">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="87ec0-125">在 **[感謝您選擇 Office 365 E5]** 頁面上，請於步驟 1 中指定您的新電子郵件帳戶位址。</span><span class="sxs-lookup"><span data-stu-id="87ec0-125">On the **Thank you for choosing Office 365 E5** page, specify, your new email account address in step 1.</span></span>
3. <span data-ttu-id="87ec0-126">在追蹤訂閱程序的步驟 2 中，輸入要求的資訊，然後執行驗證。</span><span class="sxs-lookup"><span data-stu-id="87ec0-126">In step 2 of the trail subscription process, type the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="87ec0-127">在步驟 3 中，輸入組織名稱，然後輸入將成為訂閱的全域系統管理員的帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="87ec0-127">In step 3, type an organization name and then an account name that will be the global admin for the subscription.</span></span> 
5. <span data-ttu-id="87ec0-128">針對步驟 4，在此記錄登入頁面 (選取並複製)：</span><span class="sxs-lookup"><span data-stu-id="87ec0-128">For step 4, record the sign-in page here (select and copy):</span></span> ![線](../media/Common-Images/TableLine.png) 
6. <span data-ttu-id="87ec0-130">在此記錄使用者識別碼：![線](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="87ec0-130">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="87ec0-131">在安全位置中記錄您輸入的密碼。</span><span class="sxs-lookup"><span data-stu-id="87ec0-131">Record the password that you typed in a secure location.</span></span>
   <span data-ttu-id="87ec0-132">此值將被稱為 **「Office 365 全域系統管理員名稱」**。</span><span class="sxs-lookup"><span data-stu-id="87ec0-132">This value will be referred to as the **Office 365 global administrator name**.</span></span>
8. <span data-ttu-id="87ec0-133">按一下 **[移至設定]**。</span><span class="sxs-lookup"><span data-stu-id="87ec0-133">Click **Go to Setup**.</span></span>
9. <span data-ttu-id="87ec0-134">在 [Office 365 E5 設定] 中，按一下 [繼續在電子郵件和登入中使用 **您的組織.*onmicrosoft.com]*，** 然後按一下 **[結束並稍後再繼續]**。</span><span class="sxs-lookup"><span data-stu-id="87ec0-134">In Office 365 E5 Setup, click **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then click **Exit and continue later**.</span></span>

<span data-ttu-id="87ec0-135">您應該會看到 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="87ec0-135">You should see the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="87ec0-136">我們提供您建立 Office 365 試用版訂閱，以便測試環境中能有不同於您目前已有之付費訂閱的單獨 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="87ec0-136">We have you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="87ec0-137">此區隔表示您可以在測試租用戶中新增和移除使用者，而不會影響到生產訂閱。</span><span class="sxs-lookup"><span data-stu-id="87ec0-137">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="87ec0-138">階段 2：設定 Office 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="87ec0-138">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="87ec0-139">在這個階段中，您可以設定其他使用者使用您的 Office 365 訂閱，並指派他們 Office 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="87ec0-139">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="87ec0-140">使用[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) 中的指示，將 Office 365 訂閱從您的電腦連線到 Azure Active Directory PowerShell for Graph 模組。</span><span class="sxs-lookup"><span data-stu-id="87ec0-140">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="87ec0-141">在 **[Windows PowerShell 認證要求]** 對話方塊中，輸入 Office 365 全域管理員帳戶的使用者名稱 (例如：jdoe@contosotoycompany.onmicrosoft.com) 和密碼。</span><span class="sxs-lookup"><span data-stu-id="87ec0-141">In the **Windows PowerShell Credential Request** dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="87ec0-142">填入您的組織名稱 (範例︰contosotoycompany)，代表位置的兩個字元國家/地區代碼、常用帳戶密碼，再從 PowerShell 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="87ec0-142">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="87ec0-143">這裡會使用常見密碼，以便在測試環境中能自動化並輕鬆進行設定。</span><span class="sxs-lookup"><span data-stu-id="87ec0-143">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="87ec0-144">當然，對於生產訂閱，這是非常不鼓勵的。</span><span class="sxs-lookup"><span data-stu-id="87ec0-144">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="87ec0-145">記錄重要資訊供日後參考</span><span class="sxs-lookup"><span data-stu-id="87ec0-145">Record key information for future reference</span></span>

<span data-ttu-id="87ec0-146">您可能會想要列印本文章，以記錄 在Office 365 試用版訂閱的 30 天中此環境所需的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="87ec0-146">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="87ec0-147">您可以輕鬆將試用訂閱延長 30 天。</span><span class="sxs-lookup"><span data-stu-id="87ec0-147">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="87ec0-148">若為永久測試環境，請建立具有個別 Azure AD 租用戶及少量授權的新付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="87ec0-148">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="87ec0-149">記錄這些值：</span><span class="sxs-lookup"><span data-stu-id="87ec0-149">Record these values:</span></span>
  
- <span data-ttu-id="87ec0-150">Office 365 全域系統管理員名稱：</span><span class="sxs-lookup"><span data-stu-id="87ec0-150">Office 365 global administrator name:</span></span> ![線](../media/Common-Images/TableLine.png)<span data-ttu-id="87ec0-152">.onmicrosoft.com (來自階段 1 的步驟 6)</span><span class="sxs-lookup"><span data-stu-id="87ec0-152">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="87ec0-153">也將此帳戶的密碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="87ec0-153">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="87ec0-154">您的試用訂閱組織名稱：</span><span class="sxs-lookup"><span data-stu-id="87ec0-154">Your trial subscription organization name:</span></span> ![線](../media/Common-Images/TableLine.png) <span data-ttu-id="87ec0-156">(來自階段 1 的步驟 4)</span><span class="sxs-lookup"><span data-stu-id="87ec0-156">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="87ec0-157">若要列出使用者 2、使用者 3、使用者 4 和使用者 5 的帳戶，從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="87ec0-157">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="87ec0-158">在此記錄帳戶名稱：</span><span class="sxs-lookup"><span data-stu-id="87ec0-158">Record the account names here:</span></span>
    
  - <span data-ttu-id="87ec0-159">使用者 2 的帳戶名稱：user2@</span><span class="sxs-lookup"><span data-stu-id="87ec0-159">User 2 account name: user2@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="87ec0-161">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="87ec0-161">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="87ec0-162">使用者 3 的帳戶名稱：user3@</span><span class="sxs-lookup"><span data-stu-id="87ec0-162">User 3 account name: user3@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="87ec0-164">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="87ec0-164">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="87ec0-165">使用者 4 的帳戶名稱：user4@</span><span class="sxs-lookup"><span data-stu-id="87ec0-165">User 4 account name: user4@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="87ec0-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="87ec0-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="87ec0-168">使用者 5 的帳戶名稱：user5@</span><span class="sxs-lookup"><span data-stu-id="87ec0-168">User 5 account name: user5@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="87ec0-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="87ec0-170">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="87ec0-171">一併將這些帳戶的常見密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="87ec0-171">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="87ec0-172">使用 Office 365 測試環境</span><span class="sxs-lookup"><span data-stu-id="87ec0-172">Using an Office 365 test environment</span></span>

<span data-ttu-id="87ec0-173">如果您只需要 Office 365 測試環境，您可以在這裡停止。</span><span class="sxs-lookup"><span data-stu-id="87ec0-173">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="87ec0-174">如需適用於 Office 365 和 Microsoft 365 的其他測試實驗室指南，請參閱 [Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="87ec0-174">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="87ec0-175">階段 3：新增 Microsoft 365 E5 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="87ec0-175">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="87ec0-176">在此階段中，您可以註冊 Microsoft 365 E5 試用版訂閱，並將它新增至與 Office 365 E5 試用版訂閱相同的組織。</span><span class="sxs-lookup"><span data-stu-id="87ec0-176">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="87ec0-177">首先，新增 Microsoft 365 E5 試用版訂閱，並將新的 Microsoft 365 授權指派給您的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="87ec0-177">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="87ec0-178">使用網際網路瀏覽器的私用執行個體，以全域系統管理員帳戶憑證登入位於 [https://admin.microsoft.com](https://admin.microsoft.com) 的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="87ec0-178">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="87ec0-179">在 [Microsoft 365 系統管理中心] \*\*\*\* 頁面的左側導覽中，按一下 [帳單 > 購買服務]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-179">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="87ec0-180">在 **[購買服務]** 頁面上，按一下 **[Microsoft 365 E5]**，然後按一下 **[取得免費試用]**。</span><span class="sxs-lookup"><span data-stu-id="87ec0-180">On the **Purchase services** page, click **Microsoft 365 E5**, and then click **Get free trial**.</span></span>

4. <span data-ttu-id="87ec0-181">在 [Microsoft 365 E5 試用版]\*\*\*\* 頁面上，選擇要收到簡訊或電話、輸入您的電話號碼，然後按一下 [傳送簡訊給我]\*\*\*\* 或 [打電話給我]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-181">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span> <span data-ttu-id="87ec0-182">執行驗證。</span><span class="sxs-lookup"><span data-stu-id="87ec0-182">Perform the verification.</span></span>

5. <span data-ttu-id="87ec0-183">在 [確認訂單]\*\*\*\* 頁面上，按一下 [立即試用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-183">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="87ec0-184">在 [訂單收據]\*\*\*\* 頁面上，按一下 [繼續]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-184">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="87ec0-185">在 Microsoft 365 系統管理中心中，按一下 [使用者] > **[作用中使用者]**。</span><span class="sxs-lookup"><span data-stu-id="87ec0-185">In the Microsoft 365 admin center, click **Users > Active users**.</span></span>

8. <span data-ttu-id="87ec0-186">在 **[作用中使用者]** 中，按一下您的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="87ec0-186">In **Active users**, click your administrator account.</span></span>

9. <span data-ttu-id="87ec0-187">按一下 **[授權與 App]**。</span><span class="sxs-lookup"><span data-stu-id="87ec0-187">Click **Licenses and apps**.</span></span>

10. <span data-ttu-id="87ec0-188">停用 Office 365 企業版 E5 授權，然後啟用 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="87ec0-188">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="87ec0-189">按一下 **[儲存變更]**，然後關閉使用者帳戶資訊窗格。</span><span class="sxs-lookup"><span data-stu-id="87ec0-189">Click **Save changes** and then close the user account information pane.</span></span>

<span data-ttu-id="87ec0-190">接下來，請為所有其他帳戶 (使用者 2、使用者 3、使用者 4 和使用者 5) 重複先前程序的步驟 8 至 11。</span><span class="sxs-lookup"><span data-stu-id="87ec0-190">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="87ec0-191">Microsoft 365 E5 試用版訂閱的期限是 30 天。</span><span class="sxs-lookup"><span data-stu-id="87ec0-191">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="87ec0-192">若為永久測試環境，請將此試用訂閱轉換為具少量授權的付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="87ec0-192">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="87ec0-193">測試環境現在擁有：</span><span class="sxs-lookup"><span data-stu-id="87ec0-193">Your test environment now has:</span></span>
  
- <span data-ttu-id="87ec0-194">Microsoft 365 E5 試用版訂閱。</span><span class="sxs-lookup"><span data-stu-id="87ec0-194">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="87ec0-195">所有適當的使用者帳戶 (全域系統管理員或所有五個使用者帳戶) 皆已可使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="87ec0-195">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="87ec0-196">此處顯示您產生的組態，該組態將新增 Microsoft 365 E5，其中包含 Office 365 和 Enterprise Mobility + Security (EMS)。</span><span class="sxs-lookup"><span data-stu-id="87ec0-196">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Microsoft 365 企業版測試環境的階段 3](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="87ec0-198">階段 4：建立 Windows 10 企業版電腦</span><span class="sxs-lookup"><span data-stu-id="87ec0-198">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="87ec0-199">在這個階段中，您會建立執行 Windows 10 企業版的獨立電腦，作為實體電腦、虛擬機器或是 Azure 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="87ec0-199">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="87ec0-200">實體電腦</span><span class="sxs-lookup"><span data-stu-id="87ec0-200">Physical computer</span></span>

<span data-ttu-id="87ec0-p109">取得個人電腦並在其上安裝 Windows 10 企業版。您可以在[這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="87ec0-203">虛擬機器</span><span class="sxs-lookup"><span data-stu-id="87ec0-203">Virtual machine</span></span>

<span data-ttu-id="87ec0-p110">使用您所選的 Hypervisor 建立虛擬機器並在其上安裝 Windows 10 企業版。您可以在[這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="87ec0-206">Azure 中的虛擬機器</span><span class="sxs-lookup"><span data-stu-id="87ec0-206">Virtual machine in Azure</span></span>

<span data-ttu-id="87ec0-p111">若要在 Microsoft Azure 中建立 Windows 10 虛擬機器，***您必須擁有以 Visual Studio 為基礎的訂閱***，其具有 Windows 10 企業版的影像存取權。其他類型的 Azure 訂閱，例如試用版與付費訂閱，沒有此影像的存取權。如需最新資訊，請參閱[在 Azure 中使用 Windows 用戶端進行開發/測試案例](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="87ec0-p112">下列命令集會使用最新版的 Azure PowerShell。請參閱[開始使用 Azure PowerShell Cmdlet](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)。這些命令集會建置名為 WIN10 的 Windows 10 企業版虛擬機器，以及所有必要的基礎結構，包括資源群組、儲存體帳戶及虛擬網路。如果您已熟悉 Azure 基礎結構服務，請調整這些指示以符合您目前所部署的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="87ec0-214">首先，啟動 Microsoft PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="87ec0-214">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="87ec0-215">使用下列命令登入您的 Azure 帳戶。</span><span class="sxs-lookup"><span data-stu-id="87ec0-215">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="87ec0-216">使用下列命令取得訂用帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="87ec0-216">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="87ec0-p113">設定 Azure 訂用帳戶。以正確的名稱取代括號中的所有項目 (包括 \< 和 > 字元)。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="87ec0-p114">接著，建立新的資源群組。若要判斷資源群組名稱是否是唯一的，可使用此命令來列出現有的資源群組。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="87ec0-p115">使用這些命令建立新的資源群組。以正確的名稱取代引號內的所有項目 (包括 \< 和 > 字元)。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="87ec0-p116">接下來，您可以使用這些命令建立新的虛擬網路和 WIN10 虛擬機器。出現提示時，請提供 WIN10 本機系統管理員帳戶的名稱和密碼，並將其存放在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="87ec0-225">階段 5：將 Windows 10 電腦加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="87ec0-225">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="87ec0-226">建立實體或虛擬機器的 Windows 10 企業版之後，使用本機系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="87ec0-226">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87ec0-227">針對 Azure 中的虛擬機器，使用[這些指示](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)來與它連線。</span><span class="sxs-lookup"><span data-stu-id="87ec0-227">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="87ec0-228">接下來，將 WIN10 電腦加入 Microsoft 365 E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="87ec0-228">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="87ec0-229">在 WIN10 電腦桌面，按一下 [開始] > [設定] > [帳戶] > [存取公司或學校] > [連線]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-229">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="87ec0-230">在 [設定公司或學校帳戶]\*\*\*\* 對話方塊中，按一下 [將此裝置加入 Azure Active Directory]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-230">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="87ec0-231">在 [公司或學校帳戶]\*\*\*\* 中，輸入 Microsoft 365 E5 訂閱的全域管理員帳戶名稱，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-231">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="87ec0-232">在 [輸入密碼]\*\*\*\* 中，輸入全域管理員帳戶的密碼，然後按一下 [登入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-232">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="87ec0-233">系統提示您確認這是您的組織時，按一下 [加入]\*\*\*\*，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-233">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="87ec0-234">關閉設定視窗。</span><span class="sxs-lookup"><span data-stu-id="87ec0-234">Close the settings window.</span></span>
    
<span data-ttu-id="87ec0-235">接下來，在 WIN10 電腦上安裝 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="87ec0-235">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="87ec0-236">開啟 Microsoft Edge 瀏覽器，並使用全域管理員帳戶認證登入 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="87ec0-236">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="87ec0-237">如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="87ec0-237">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="87ec0-238">在 [Microsoft Office 首頁]\*\*\*\* 索引標籤上，按一下 [安裝 Office]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-238">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="87ec0-239">系統提示您要執行的動作時，按一下 [執行]\*\*\*\*，然後為 [使用者帳戶控制]\*\*\*\* 按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-239">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="87ec0-p118">等待 Office 完成安裝。當您看到 **「一切就緒！」** 時，按兩次 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87ec0-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="87ec0-242">以下是您產生的環境。</span><span class="sxs-lookup"><span data-stu-id="87ec0-242">Here is your resulting environment.</span></span>

![Microsoft 365 企業版測試環境的階段 5](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="87ec0-244">這包括已完成下列項目的 WIN10 電腦：</span><span class="sxs-lookup"><span data-stu-id="87ec0-244">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="87ec0-245">已加入您的 Microsoft 365 E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="87ec0-245">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="87ec0-246">已在 Microsoft Intune (EMS) 中註冊為 Azure AD 裝置。</span><span class="sxs-lookup"><span data-stu-id="87ec0-246">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="87ec0-247">已安裝 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="87ec0-247">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="87ec0-248">您現在已準備好嘗試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="87ec0-248">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="87ec0-249">後續步驟</span><span class="sxs-lookup"><span data-stu-id="87ec0-249">Next steps</span></span>

<span data-ttu-id="87ec0-250">探索這些額外的測試實驗室指南集合：</span><span class="sxs-lookup"><span data-stu-id="87ec0-250">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="87ec0-251">身分識別</span><span class="sxs-lookup"><span data-stu-id="87ec0-251">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="87ec0-252">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="87ec0-252">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="87ec0-253">資訊保護</span><span class="sxs-lookup"><span data-stu-id="87ec0-253">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="87ec0-254">另請參閱</span><span class="sxs-lookup"><span data-stu-id="87ec0-254">See also</span></span>

[<span data-ttu-id="87ec0-255">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="87ec0-255">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="87ec0-256">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="87ec0-256">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="87ec0-257">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="87ec0-257">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
