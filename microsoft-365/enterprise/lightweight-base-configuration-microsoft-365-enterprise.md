---
title: 輕量型基本組態
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
ms.openlocfilehash: c654dc80620b98d09cf508e309d4410d9cf4a4dc
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639913"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="70a1b-103">輕量型基本組態</span><span class="sxs-lookup"><span data-stu-id="70a1b-103">The lightweight base configuration</span></span>

<span data-ttu-id="70a1b-104">本文提供建立具備 Microsoft 365 E5 訂閱與執行 Windows 10 企業版電腦的簡化環境的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="70a1b-104">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![輕量型 Microsoft 365 企業版測試環境](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="70a1b-106">使用產生的環境來測試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的功能。</span><span class="sxs-lookup"><span data-stu-id="70a1b-106">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="70a1b-108">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中文件的所有視覺對應。</span><span class="sxs-lookup"><span data-stu-id="70a1b-108">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="70a1b-109">階段 1：建立您的 Office 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="70a1b-109">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="70a1b-110">我們首先使用 Office 365 E5 試用版訂閱，然後再新增 Microsoft 365 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="70a1b-110">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="70a1b-111">若要開始 Office 365 E5 試用訂閱，您需要虛構的公司名稱和新 Microsoft 帳戶。</span><span class="sxs-lookup"><span data-stu-id="70a1b-111">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="70a1b-p101">我們建議您使用公司名稱 Contoso 的變種作為公司名稱，也就是 Microsoft 範例內容中使用的虛構公司，但此為非必要的動作。在此處記錄您虛構公司名稱：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="70a1b-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="70a1b-p102">若要註冊新 Microsoft 帳戶，請移至 [https://outlook.com ](https://outlook.com)，並使用新電子郵件帳戶以及地址建立帳戶。您會使用這個帳戶來登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="70a1b-116">在此處記錄您新帳戶的名字和姓氏：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="70a1b-116">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="70a1b-117">在此處記錄新電子郵件帳戶地址：![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="70a1b-117">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="70a1b-118">註冊 Office 365 E5 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="70a1b-118">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="70a1b-119">在您的電腦上開啟網際網路瀏覽器，然後移至 [https://aka.ms/e5trial](https://aka.ms/e5trial)。</span><span class="sxs-lookup"><span data-stu-id="70a1b-119">For the lightweight Office 365 dev/test environment, open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="70a1b-120">在 [歡迎，讓我們認識您]\*\*\*\* 頁面上，指定：</span><span class="sxs-lookup"><span data-stu-id="70a1b-120">On the **Welcome, let's get to know you** page, specify:</span></span>
    
  - <span data-ttu-id="70a1b-121">您的實際位置</span><span class="sxs-lookup"><span data-stu-id="70a1b-121">Your physical location</span></span>
    
  - <span data-ttu-id="70a1b-122">新 Microsoft 帳戶的名字和姓氏</span><span class="sxs-lookup"><span data-stu-id="70a1b-122">The first and last name of your new Microsoft account</span></span>
    
  - <span data-ttu-id="70a1b-123">新電子郵件帳戶地址</span><span class="sxs-lookup"><span data-stu-id="70a1b-123">Your new email account address</span></span>
    
  - <span data-ttu-id="70a1b-124">公司電話號碼</span><span class="sxs-lookup"><span data-stu-id="70a1b-124">A business phone number</span></span>
    
  - <span data-ttu-id="70a1b-125">虛構公司名稱</span><span class="sxs-lookup"><span data-stu-id="70a1b-125">Your fictional company name</span></span>
    
  - <span data-ttu-id="70a1b-126">250-999 名人員的組織規模</span><span class="sxs-lookup"><span data-stu-id="70a1b-126">An organization size of 250-999 people</span></span>
    
3. <span data-ttu-id="70a1b-127">按一下 [再多一個步驟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-127">Click **Just one more step**.</span></span>
    
4. <span data-ttu-id="70a1b-128">在 [建立使用者識別碼]\*\*\*\* 頁面上，根據新電子郵件地址輸入使用者名稱、在 @ 符號之後接上虛構公司 (移除名稱中的所有空格)，接著是此新 Office 365 帳戶的密碼 (兩次)。</span><span class="sxs-lookup"><span data-stu-id="70a1b-128">On the **Create your user ID** page, type a user name based on your new email address, your fictional company after the @ sign (remove all spaces in the name), then a password (twice) for this new Office 365 account.</span></span>
    
    <span data-ttu-id="70a1b-129">在安全位置中記錄您輸入的密碼。</span><span class="sxs-lookup"><span data-stu-id="70a1b-129">Record the password that you typed in a secure location.</span></span>
    
    <span data-ttu-id="70a1b-130">在這裡輸入虛構公司的名稱：![](./media/Common-Images/TableLine.png) (此將稱為**組織名稱**)</span><span class="sxs-lookup"><span data-stu-id="70a1b-130">Record your fictional company name, to be referred to as the **organization name**, here: ![](./media/Common-Images/TableLine.png)</span></span>
    
5. <span data-ttu-id="70a1b-131">按一下 [建立我的帳戶] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-131">Click **Create my account**.</span></span>
    
6. <span data-ttu-id="70a1b-p103">在 [證明您不是機器人。]\*\*\*\* 頁面中，輸入能夠傳送簡訊的手機號碼，然後按一下 [傳送簡訊給我]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p103">On the **Prove. You're. Not. A. Robot.** page, type the phone number of your text-capable phone, and then click **Text me**.</span></span>
    
7. <span data-ttu-id="70a1b-134">輸入已接收簡訊訊息中的驗證代碼，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-134">Type the verification code from the received text message, and then click **Next**.</span></span>
    
8. <span data-ttu-id="70a1b-135">在此記錄登入頁面 URL (選取並複製)：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="70a1b-135">Record the sign-in page URL here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span>
    
9. <span data-ttu-id="70a1b-136">在此記錄使用者識別碼 (選取與複製)：![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="70a1b-136">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="70a1b-137">此值將被稱為 **Office 365 全域系統管理員名稱**。</span><span class="sxs-lookup"><span data-stu-id="70a1b-137">This value will be referred to as the **Office 365 global administrator name**.</span></span>
    
10. <span data-ttu-id="70a1b-138">當您看到 [您已準備就緒]\*\*\*\*，對其按一下。</span><span class="sxs-lookup"><span data-stu-id="70a1b-138">When you see **You're ready to go**, click it.</span></span>
    
11. <span data-ttu-id="70a1b-139">在下一頁中，請稍候直到 Office 365 完成設定且所有的圖標皆可供使用。</span><span class="sxs-lookup"><span data-stu-id="70a1b-139">On the next page, wait until Office 365 completes setting up and all the tiles are available.</span></span>
    
<span data-ttu-id="70a1b-140">您應會看到主要 Office 365 入口網站頁面，您可以從其中存取 Office 服務和 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="70a1b-140">You should see main Office 365 portal page from which you can access Office services and the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="70a1b-141">我們提供您建立 Office 365 試用版訂閱，以便開發/測試環境中能有不同於您目前已有之付費訂閱的單獨 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="70a1b-141">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="70a1b-142">此區隔表示您可以在測試租用戶中新增和移除使用者，而不會影響到生產訂閱。</span><span class="sxs-lookup"><span data-stu-id="70a1b-142">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="70a1b-143">階段 2：設定 Office 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="70a1b-143">Phase 3: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="70a1b-144">在這個階段中，您可以設定其他使用者使用您的 Office 365 訂閱，並指派他們 Office 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="70a1b-144">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="70a1b-145">使用[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) 中的指示，將 Office 365 訂閱從您的電腦連線到 Azure Active Directory PowerShell for Graph 模組。</span><span class="sxs-lookup"><span data-stu-id="70a1b-145">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from:</span></span>
    
<span data-ttu-id="70a1b-146">在 [Windows PowerShell 認證要求] 對話方塊中，輸入 Office 365 全域管理員帳戶的使用者名稱 (例如：jdoe@contosotoycompany.onmicrosoft.com) 和密碼。</span><span class="sxs-lookup"><span data-stu-id="70a1b-146">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="70a1b-147">填入您的組織名稱 (範例︰contosotoycompany)，代表位置的兩個字元國家/地區代碼、常用帳戶密碼，再從 PowerShell 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="70a1b-147">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="70a1b-148">這裡會使用常見密碼，以便在開發/測試環境中能自動化並輕鬆進行設定。</span><span class="sxs-lookup"><span data-stu-id="70a1b-148">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="70a1b-149">當然，對於生產訂閱，這是非常不鼓勵的。</span><span class="sxs-lookup"><span data-stu-id="70a1b-149">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="70a1b-150">記錄重要資訊供日後參考</span><span class="sxs-lookup"><span data-stu-id="70a1b-150">Record key information for future reference</span></span>

<span data-ttu-id="70a1b-151">您可能會想要列印本文章，以記錄 在Office 365 試用版訂閱的 30 天中此環境所需的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="70a1b-151">You might want to print this article to record the specific values that you will need for this environment over the 30 days of the Office 365 trial subscription. You can easily extend the trail subscription for another 30 days. For a permanent dev/test environment, create a new paid subscription with a small number of licenses.</span></span> <span data-ttu-id="70a1b-152">您可以輕鬆將試用訂閱延長 30 天。</span><span class="sxs-lookup"><span data-stu-id="70a1b-152">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="70a1b-153">針對永久開發/測試環境，建立具有單獨 Azure AD 租用戶及少數授權的新付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="70a1b-153">For a permanent dev/test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="70a1b-154">記錄這些值︰</span><span class="sxs-lookup"><span data-stu-id="70a1b-154">Record these values:</span></span>
  
- <span data-ttu-id="70a1b-155">Office 365 全域系統管理員名稱：![](./media/Common-Images/TableLine.png).onmicrosoft.com (在階段 2 的步驟 9)</span><span class="sxs-lookup"><span data-stu-id="70a1b-155">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="70a1b-156">將此帳戶的密碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="70a1b-156">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="70a1b-157">您的試用訂閱組織名稱：![](./media/Common-Images/TableLine.png) (從階段 2 的步驟 4)</span><span class="sxs-lookup"><span data-stu-id="70a1b-157">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="70a1b-158">若要列出使用者 2、使用者 3、使用者 4 和使用者 5 的帳戶，從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="70a1b-158">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="70a1b-159">在此記錄帳戶名稱：</span><span class="sxs-lookup"><span data-stu-id="70a1b-159">Record the account names here:</span></span>
    
  - <span data-ttu-id="70a1b-160">使用者 2 的帳戶名稱：user2 @![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="70a1b-160">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="70a1b-161">使用者 3 的帳戶名稱：user3 @![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="70a1b-161">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="70a1b-162">使用者 4 的帳戶名稱：user4 @![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="70a1b-162">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="70a1b-163">使用者 5 的帳戶名稱：user5 @![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="70a1b-163">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="70a1b-164">一併將這些帳戶的常見密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="70a1b-164">Also record the passwords for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-devtest-environment"></a><span data-ttu-id="70a1b-165">使用 Office 365 開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="70a1b-165">Phase 1: Create an Office 365 dev/test environment</span></span>

<span data-ttu-id="70a1b-166">如果您只需要 Office 365 開發/測試環境，您可以在這裡停止。</span><span class="sxs-lookup"><span data-stu-id="70a1b-166">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="70a1b-167">如需適用於 Office 365 和 Microsoft 365 的其他測試實驗室指南，請參閱 [Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="70a1b-167">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="70a1b-168">階段 3：新增 Microsoft 365 E5 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="70a1b-168">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="70a1b-169">在此階段中，您可以註冊 Microsoft 365 E5 試用版訂閱，並將它新增至與 Office 365 E5 試用版訂閱相同的組織。</span><span class="sxs-lookup"><span data-stu-id="70a1b-169">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="70a1b-170">首先，新增 Microsoft 365 E5 試用版訂閱，並將 Microsoft 365 授權指派給您的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="70a1b-170">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="70a1b-171">使用網際網路瀏覽器的私用執行個體，以全域系統管理員帳戶憑證登入位於 [https://admin.microsoft.com](https://admin.microsoft.com) 的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="70a1b-171">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="70a1b-172">在 [Microsoft 365 系統管理中心] \*\*\*\* 頁面的左側導覽中，按一下 [帳單 > 購買服務]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-172">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="70a1b-173">在 [購買服務]\*\*\*\* 頁面上，找到 [Microsoft 365 E5]\*\*\*\* 項目。</span><span class="sxs-lookup"><span data-stu-id="70a1b-173">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="70a1b-174">將滑鼠指標停留在上面，並且按一下 [開始免費試用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-174">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="70a1b-175">在 [Microsoft 365 E5 試用版]\*\*\*\* 頁面上，選擇要收到簡訊或電話、輸入您的電話號碼，然後按一下 [傳送簡訊給我]\*\*\*\* 或 [打電話給我]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-175">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="70a1b-176">在 [確認訂單]\*\*\*\* 頁面上，按一下 [立即試用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-176">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="70a1b-177">在 [訂單收據]\*\*\*\* 頁面上，按一下 [繼續]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-177">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="70a1b-178">在 Microsoft 365 系統管理中心，按一下 [作用中使用者]\*\*\*\*，然後您的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="70a1b-178">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="70a1b-179">按一下 [產品授權]\*\*\*\* 的 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-179">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="70a1b-180">關閉 Office 365 企業版 E5 授權，然後開啟 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="70a1b-180">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="70a1b-181">按一下 [儲存 > 關閉 > 關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-181">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="70a1b-182">接下來，請為所有其他帳戶 (使用者 2、使用者 3、使用者 4 和使用者 5) 重複先前程序的步驟 8 至 11。</span><span class="sxs-lookup"><span data-stu-id="70a1b-182">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="70a1b-183">Microsoft 365 E5 試用版訂閱的期限是 30 天。</span><span class="sxs-lookup"><span data-stu-id="70a1b-183">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="70a1b-184">在永久測試環境中，將此試用訂閱轉換為具少數授權數的付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="70a1b-184">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="70a1b-185">測試環境現在擁有：</span><span class="sxs-lookup"><span data-stu-id="70a1b-185">Your test environment now has:</span></span>
  
- <span data-ttu-id="70a1b-186">Microsoft 365 E5 試用版訂閱。</span><span class="sxs-lookup"><span data-stu-id="70a1b-186">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="70a1b-187">所有適當的使用者帳戶 (全域系統管理員或所有五個使用者帳戶) 皆已可使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="70a1b-187">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="70a1b-188">此處顯示您產生的組態，該組態將新增 Microsoft 365 E5，其中包含 Office 365 和 Enterprise Mobility + Security (EMS)。</span><span class="sxs-lookup"><span data-stu-id="70a1b-188">Figure 1 shows your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Microsoft 365 企業版測試環境的階段 2](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="70a1b-190">階段 4：建立 Windows 10 企業版電腦</span><span class="sxs-lookup"><span data-stu-id="70a1b-190">Phase 3: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="70a1b-191">在這個階段中，您會建立執行 Windows 10 企業版的獨立電腦，作為實體電腦、虛擬機器或是 Azure 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="70a1b-191">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="70a1b-192">實體電腦</span><span class="sxs-lookup"><span data-stu-id="70a1b-192">Physical computer</span></span>

<span data-ttu-id="70a1b-p109">取得個人電腦並在其上安裝 Windows 10 企業版。您可以在[這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="70a1b-195">虛擬機器</span><span class="sxs-lookup"><span data-stu-id="70a1b-195">Virtual machine</span></span>

<span data-ttu-id="70a1b-p110">使用您所選的 Hypervisor 建立虛擬機器並在其上安裝 Windows 10 企業版。您可以在[這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="70a1b-198">Azure 中的虛擬機器</span><span class="sxs-lookup"><span data-stu-id="70a1b-198">Virtual machine in Azure</span></span>

<span data-ttu-id="70a1b-p111">若要在 Microsoft Azure 中建立 Windows 10 虛擬機器，***您必須擁有以 Visual Studio 為基礎的訂閱***，其具有 Windows 10 企業版的影像存取權。其他類型的 Azure 訂閱，例如試用版與付費訂閱，沒有此影像的存取權。如需最新資訊，請參閱[在 Azure 中使用 Windows 用戶端進行開發/測試案例](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="70a1b-p112">下列命令集會使用最新版的 Azure PowerShell。請參閱[開始使用 Azure PowerShell Cmdlet](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)。這些命令集會建置名為 WIN10 的 Windows 10 企業版虛擬機器，以及所有必要的基礎結構，包括資源群組、儲存體帳戶及虛擬網路。如果您已熟悉 Azure 基礎結構服務，請調整這些指示以符合您目前所部署的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="70a1b-206">首先，啟動 Microsoft PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="70a1b-206">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="70a1b-207">使用下列命令登入您的 Azure 帳戶。</span><span class="sxs-lookup"><span data-stu-id="70a1b-207">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="70a1b-208">使用下列命令取得訂用帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="70a1b-208">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="70a1b-p113">設定 Azure 訂用帳戶。以正確的名稱取代括號中的所有項目 (包括 \< 和 > 字元)。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="70a1b-p114">接著，建立新的資源群組。若要判斷資源群組名稱是否是唯一的，可使用此命令來列出現有的資源群組。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="70a1b-p115">使用這些命令建立新的資源群組。以正確的名稱取代引號內的所有項目 (包括 \< 和 > 字元)。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="70a1b-p116">接下來，您可以使用這些命令建立新的虛擬網路和 WIN10 虛擬機器。出現提示時，請提供 WIN10 本機系統管理員帳戶的名稱和密碼，並將其存放在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="70a1b-217">階段 5：將 Windows 10 電腦加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="70a1b-217">Phase 4: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="70a1b-218">建立實體或虛擬機器的 Windows 10 企業版之後，使用本機系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="70a1b-218">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="70a1b-219">針對 Azure 中的虛擬機器，使用[這些指示](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)來與它連線。</span><span class="sxs-lookup"><span data-stu-id="70a1b-219">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="70a1b-220">接下來，將 WIN10 電腦加入 Microsoft 365 E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="70a1b-220">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="70a1b-221">在 WIN10 電腦桌面，按一下 [開始] > [設定] > [帳戶] > [存取公司或學校] > [連線]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-221">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="70a1b-222">在 [設定公司或學校帳戶]\*\*\*\* 對話方塊中，按一下 [將此裝置加入 Azure Active Directory]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-222">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="70a1b-223">在 [公司或學校帳戶]\*\*\*\* 中，輸入 Microsoft 365 E5 訂閱的全域管理員帳戶名稱，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-223">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="70a1b-224">在 [輸入密碼]\*\*\*\* 中，輸入全域管理員帳戶的密碼，然後按一下 [登入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-224">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="70a1b-225">系統提示您確認這是您的組織時，按一下 [加入]\*\*\*\*，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-225">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="70a1b-226">關閉設定視窗。</span><span class="sxs-lookup"><span data-stu-id="70a1b-226">Close the settings window.</span></span>
    
<span data-ttu-id="70a1b-227">接下來，在 WIN10 電腦上安裝 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="70a1b-227">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="70a1b-228">開啟 Microsoft Edge 瀏覽器，並使用全域管理員帳戶認證登入 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="70a1b-228">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="70a1b-229">如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="70a1b-229">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="70a1b-230">在 [Microsoft Office 首頁]\*\*\*\* 索引標籤上，按一下 [安裝 Office]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-230">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="70a1b-231">系統提示您要執行的動作時，按一下 [執行]\*\*\*\*，然後為 [使用者帳戶控制]\*\*\*\* 按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-231">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="70a1b-p118">等待 Office 完成安裝。當您看到 **「一切就緒！」** 時，按兩次 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70a1b-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="70a1b-234">以下是您產生的環境。</span><span class="sxs-lookup"><span data-stu-id="70a1b-234">Here is your resulting configuration.</span></span>

![Microsoft 365 企業版測試環境的階段 5](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="70a1b-236">這包括已完成下列項目的 WIN10 電腦：</span><span class="sxs-lookup"><span data-stu-id="70a1b-236">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="70a1b-237">已加入您的 Microsoft 365 E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="70a1b-237">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="70a1b-238">已在 Microsoft Intune (EMS) 中註冊為 Azure AD 裝置。</span><span class="sxs-lookup"><span data-stu-id="70a1b-238">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="70a1b-239">已安裝 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="70a1b-239">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="70a1b-240">您現在已準備好嘗試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="70a1b-240">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="70a1b-241">後續步驟</span><span class="sxs-lookup"><span data-stu-id="70a1b-241">Next steps</span></span>

<span data-ttu-id="70a1b-242">探索這些額外的測試實驗室指南集合：</span><span class="sxs-lookup"><span data-stu-id="70a1b-242">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="70a1b-243">身分識別</span><span class="sxs-lookup"><span data-stu-id="70a1b-243">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="70a1b-244">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="70a1b-244">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="70a1b-245">資訊保護</span><span class="sxs-lookup"><span data-stu-id="70a1b-245">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="70a1b-246">另請參閱</span><span class="sxs-lookup"><span data-stu-id="70a1b-246">See also</span></span>

[<span data-ttu-id="70a1b-247">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="70a1b-247">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="70a1b-248">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="70a1b-248">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="70a1b-249">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="70a1b-249">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
