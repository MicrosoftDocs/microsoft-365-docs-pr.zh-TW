---
title: 設定您的 Microsoft 威脅防護試用實驗室或試驗環境
description: 存取 Microsoft 365 的安全性中心，然後設定您的 Microsoft 威脅防護試用實驗室環境
keywords: Microsoft 威脅防護試用設定，Microsoft 威脅防護試驗設定，嘗試 Microsoft 威脅防護，Microsoft 威脅防護評估實驗室安裝程式
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 53ff0842e73e275bf4a8fa8b18c1d08ad70a64ec
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418130"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="fb46f-104">設定您的 Microsoft 威脅防護試用實驗室環境</span><span class="sxs-lookup"><span data-stu-id="fb46f-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fb46f-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb46f-105">**Applies to:**</span></span>
- <span data-ttu-id="fb46f-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="fb46f-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="fb46f-107">建立 Microsoft 威脅防護試用實驗室或試驗環境並加以部署時，會有三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="fb46f-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="準備 Microsoft 威脅防護評估實驗室或試驗環境" />
      <br/><span data-ttu-id="fb46f-109">階段1：準備 </a></span><span class="sxs-lookup"><span data-stu-id="fb46f-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="設定您的 Microsoft 威脅防護試用實驗室或試驗環境" />
      <br/><span data-ttu-id="fb46f-111">階段2：設定 </a></span><span class="sxs-lookup"><span data-stu-id="fb46f-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints" title="
針對您的 Microsoft 威脅防護試用實驗室或試驗環境和您的端點設定每個 Microsoft 威脅防護 pillar" />
      <br/><span data-ttu-id="fb46f-113">階段3：設定板載 & </a></span><span class="sxs-lookup"><span data-stu-id="fb46f-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="fb46f-114">您目前是在 [設定] 階段。</span><span class="sxs-lookup"><span data-stu-id="fb46f-114">You're currently in the set up phase.</span></span> <span data-ttu-id="fb46f-115">請先開始存取 Microsoft 365 的安全性中心，然後設定您的試用實驗室或試驗環境。</span><span class="sxs-lookup"><span data-stu-id="fb46f-115">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="fb46f-116">註冊 Office 365 或 Azure Active Directory 訂閱以產生 *onmicrosoft.com* 租使用者，您可以用來註冊您的 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="fb46f-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="fb46f-117">如果您已有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用或試驗承租人建立步驟。</span><span class="sxs-lookup"><span data-stu-id="fb46f-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="fb46f-118">在這個階段中，您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="fb46f-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="fb46f-119">建立 Office 365 E5 試用租使用者</span><span class="sxs-lookup"><span data-stu-id="fb46f-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="fb46f-120">啟用 Microsoft 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="fb46f-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="fb46f-121">建立 Office 365 E5 試用租使用者</span><span class="sxs-lookup"><span data-stu-id="fb46f-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="fb46f-122">如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用租使用者建立步驟。</span><span class="sxs-lookup"><span data-stu-id="fb46f-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="fb46f-123">移至 [Office 365 E5 產品入口網站](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) ，然後選取 [ **免費試用版**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![影像 of_Office 365 E5 免費試用版頁面](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="fb46f-125">輸入您的電子郵件地址 (個人或公司) ，以完成試用註冊。</span><span class="sxs-lookup"><span data-stu-id="fb46f-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="fb46f-126">按一下 [ **設定帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-126">Click **Set up account**.</span></span>

   ![影像 of_Office 365 E5 試用版註冊設定] 頁面](../../media/mtp-eval-10.png)

3. <span data-ttu-id="fb46f-128">請填入您的名字、姓氏、商務電話號碼、公司名稱、公司規模和國家或地區。</span><span class="sxs-lookup"><span data-stu-id="fb46f-128">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![影像 of_Office 365 E5 試用註冊設定頁面要求名稱、電話及公司詳細資料](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="fb46f-130">您在這裡設定的國家或地區決定您的 Office 365 將主控的資料中心區域。</span><span class="sxs-lookup"><span data-stu-id="fb46f-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="fb46f-131">選擇您的驗證喜好設定：透過短信或來電。</span><span class="sxs-lookup"><span data-stu-id="fb46f-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="fb46f-132">按一下 [ **傳送驗證碼**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-132">Click **Send Verification Code**.</span></span> 

   ![影像 of_Office 365 E5 試用註冊設定頁面要求驗證偏好設定](../../media/mtp-eval-12.png)

5. <span data-ttu-id="fb46f-134">為您的租使用者設定自訂的功能變數名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb46f-134">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![影像 of_Office 365 E5 試用註冊設定] 頁面，您可以在其中設定自訂功能變數名稱](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="fb46f-136">設定第一個身分識別，這將是租使用者的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="fb46f-136">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="fb46f-137">填入 **名稱** 和 **密碼**。</span><span class="sxs-lookup"><span data-stu-id="fb46f-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="fb46f-138">按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-138">Click **Sign up**.</span></span>

   ![影像 of_Office 365 E5 試用註冊設定] 頁面，您可以在這裡設定您的商務身分識別](../../media/mtp-eval-14.png)

7. <span data-ttu-id="fb46f-140">按一下 [ **移至設定** ] 以完成 Office 365 E5 試用租使用者布建。</span><span class="sxs-lookup"><span data-stu-id="fb46f-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Office 365 E5 試用註冊設定頁面的影像提示按一下 [前往設定] 按鈕](../../media/mtp-eval-15.png)

8. <span data-ttu-id="fb46f-142">將公司網域連線到 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="fb46f-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="fb46f-143">選選擇 **[連線您已擁有的網域]** ，然後輸入您的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="fb46f-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="fb46f-144">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb46f-144">Click **Next**.</span></span>

   ![影像 of_Office 365 E5 安裝頁面，您應該在其中個人化登入和電子郵件](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="fb46f-146">新增 TXT 或 MX 記錄以驗證網域擁有權。</span><span class="sxs-lookup"><span data-stu-id="fb46f-146">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="fb46f-147">將 TXT 或 MX 記錄新增至您的網域後，請選取 [ **驗證**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![影像 of_Office 365 E5 安裝頁面，您應該在這裡新增 TXT 的 MX 記錄以驗證您的網域](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="fb46f-149">選為您的租使用者建立更多使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="fb46f-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="fb46f-150">您可以按 **[下一步]** 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="fb46f-150">You can skip this step by clicking **Next**.</span></span>

    ![影像 of_Office 365 E5 安裝頁面，您可以在其中新增更多使用者](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="fb46f-152">選下載 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="fb46f-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="fb46f-153">按 **[下一步]** 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="fb46f-153">Click **Next** to skip this step.</span></span> 

    ![影像 of_Office 365 E5 頁面，您可以在此安裝 Office 應用程式](../../media/mtp-eval-19.png)

12. <span data-ttu-id="fb46f-155">選遷移電子郵件。</span><span class="sxs-lookup"><span data-stu-id="fb46f-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="fb46f-156">您也可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="fb46f-156">Again, you can skip this step.</span></span>

    ![影像 of_Office 365 E5，您可以在其中設定是否要遷移電子郵件訊息](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="fb46f-158">選擇 [線上服務]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-158">Choose online services.</span></span> <span data-ttu-id="fb46f-159">選取 [ **Exchange** ] 並按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb46f-159">Select **Exchange** and click **Next**.</span></span> 

    ![影像 of_Office 365 E5，您可以在這裡選擇您的線上服務](../../media/mtp-eval-21.png)

14. <span data-ttu-id="fb46f-161">將 MX、CNAME 及 TXT 記錄新增至您的網域。</span><span class="sxs-lookup"><span data-stu-id="fb46f-161">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="fb46f-162">完成時，選取 [ **驗證**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-162">When completed, select **Verify**.</span></span>

    ![影像 of_Office 365 E5 您可以在這裡加入您的 DNS 記錄](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="fb46f-164">恭喜，您已完成布建您的 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="fb46f-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![影像 of_Office 365 E5 安裝完成確認頁面](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="fb46f-166">啟用 Microsoft 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="fb46f-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="fb46f-167">註冊試用版可提供25個使用者授權供一個月使用。</span><span class="sxs-lookup"><span data-stu-id="fb46f-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="fb46f-168">如需詳細資訊，請參閱 [Try Or 購買 M365 訂閱](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 。</span><span class="sxs-lookup"><span data-stu-id="fb46f-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="fb46f-169">從 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，按一下 [ **帳單** ]，然後流覽至 [ **購買服務**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="fb46f-170">選取 [ **Microsoft 365 E5** ]，然後按一下 [ **開始免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![影像 of_Microsoft 365 E5 開始免費試用頁面](../../media/mtp-eval-24.png)

3. <span data-ttu-id="fb46f-172">選擇您的驗證喜好設定：透過短信或來電。</span><span class="sxs-lookup"><span data-stu-id="fb46f-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="fb46f-173">決定之後，請輸入電話號碼、選取 [ **文字** ] 或 [ **呼叫我** ]，視您的選擇而定。</span><span class="sxs-lookup"><span data-stu-id="fb46f-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 開始免費試用頁面，要求連絡人詳細資料傳送程式碼，以證明您不是機器人](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="fb46f-175">輸入驗證碼，然後按一下 [ **開始免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-175">Enter the verification code and click **Start your free trial**.</span></span>

   ![影像 of_Microsoft 365 E5 開始免費試用頁面，您可以在此頁面上填寫驗證碼，以證明您不是機器人](../../media/mtp-eval-26.png)

5. <span data-ttu-id="fb46f-177">按一下 [ **立即試用** ] 以確認您的 Microsoft 365 E5 試用版。</span><span class="sxs-lookup"><span data-stu-id="fb46f-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![影像 of_Microsoft 365 E5 開始免費試用頁面，您應該在此頁面上時鐘立即試按鈕開始](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="fb46f-179">移至**Microsoft 365 Admin Center**使用者作用中的  >  **Users**  >  **使用者**。</span><span class="sxs-lookup"><span data-stu-id="fb46f-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="fb46f-180">選取您的使用者帳戶，選取 [ **管理產品授權**]，然後將 Office 365 e5 的授權交換至 **Microsoft 365 E5**。</span><span class="sxs-lookup"><span data-stu-id="fb46f-180">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="fb46f-181">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="fb46f-181">Click **Save**.</span></span>

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中選取 [Microsoft 365 E5 授權]](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="fb46f-183">再次選取全域管理員帳戶，然後按一下 [ **管理使用者名稱**]。</span><span class="sxs-lookup"><span data-stu-id="fb46f-183">Select the global administrator account again then click **Manage username**.</span></span>

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中選取 [帳戶]，然後管理使用者名稱](../../media/mtp-eval-29.png)

8. <span data-ttu-id="fb46f-185">選根據您在先前步驟中選取的專案，將網域從 *onmicrosoft.com* 變更為您自己的網域。</span><span class="sxs-lookup"><span data-stu-id="fb46f-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="fb46f-186">按一下 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="fb46f-186">Click **Save changes**.</span></span>

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中變更您的網域偏好設定](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="fb46f-188">下一步</span><span class="sxs-lookup"><span data-stu-id="fb46f-188">Next step</span></span>
|<span data-ttu-id="fb46f-189">![階段3：設定板載 &](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="fb46f-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="fb46f-190">階段3：設定板載 &</span><span class="sxs-lookup"><span data-stu-id="fb46f-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="fb46f-191">針對您的 Microsoft 威脅防護試用實驗室或試驗環境和您的端點，設定每個 Microsoft 威脅防護 pillar。</span><span class="sxs-lookup"><span data-stu-id="fb46f-191">Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
