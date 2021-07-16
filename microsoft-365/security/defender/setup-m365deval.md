---
title: 設定您的 Microsoft 365 Defender 試用實驗室或試驗環境
description: Access Microsoft 365 的安全性中心，然後設定 Microsoft 365 Defender 試用實驗室環境
keywords: Microsoft 365 Defender 試用設定，請 Microsoft 365 Defender 試點設定，嘗試 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室安裝程式
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454730"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a><span data-ttu-id="c8a11-104">在實驗室環境中設定您的 Microsoft 365 Defender 試用版</span><span class="sxs-lookup"><span data-stu-id="c8a11-104">Set up your Microsoft 365 Defender trial in a lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c8a11-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c8a11-105">**Applies to:**</span></span>
- <span data-ttu-id="c8a11-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8a11-106">Microsoft 365 Defender</span></span> 

<span data-ttu-id="c8a11-107">本主題將引導您設定專用實驗室環境。</span><span class="sxs-lookup"><span data-stu-id="c8a11-107">This topic guides you to set up a dedicated lab environment.</span></span> <span data-ttu-id="c8a11-108">如需在生產中設定試用的詳細資訊，請參閱《新[評估與試驗 Microsoft 365 Defender](eval-overview.md)手冊》。</span><span class="sxs-lookup"><span data-stu-id="c8a11-108">For information on setting up a trial in production, see the new [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) guide.</span></span> 

## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="c8a11-109">建立 Office 365 E5 試用租使用者</span><span class="sxs-lookup"><span data-stu-id="c8a11-109">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="c8a11-110">如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 的試用租使用者建立步驟。</span><span class="sxs-lookup"><span data-stu-id="c8a11-110">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="c8a11-111">移至 [Office 365 E5 的產品入口網站](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)，然後選取 [**免費試用版**]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-111">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![影像 of_Office 365 E5 免費試用版頁面](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="c8a11-113">輸入您的電子郵件地址 (個人或公司) ，以完成試用註冊。</span><span class="sxs-lookup"><span data-stu-id="c8a11-113">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="c8a11-114">按一下 [ **設定帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-114">Click **Set up account**.</span></span>

   ![影像 of_Office 365 E5 試用版註冊設定] 頁面](../../media/mtp-eval-10.png)

3. <span data-ttu-id="c8a11-116">請填入您的名字、姓氏、商務電話號碼、公司名稱、公司規模和國家或地區。</span><span class="sxs-lookup"><span data-stu-id="c8a11-116">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![影像 of_Office 365 E5 試用註冊設定頁面要求名稱、電話及公司詳細資料](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="c8a11-118">您在這裡設定的國家或地區決定 Office 365 將主控的資料中心區域。</span><span class="sxs-lookup"><span data-stu-id="c8a11-118">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="c8a11-119">選擇您的驗證喜好設定：透過短信或來電。</span><span class="sxs-lookup"><span data-stu-id="c8a11-119">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="c8a11-120">按一下 [ **傳送驗證碼**]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-120">Click **Send Verification Code**.</span></span> 

   ![影像 of_Office 365 E5 試用註冊設定頁面要求驗證偏好設定](../../media/mtp-eval-12.png)

5. <span data-ttu-id="c8a11-122">為您的租使用者設定自訂的功能變數名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c8a11-122">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![影像 of_Office 365 E5 試用註冊設定] 頁面，您可以在其中設定自訂功能變數名稱](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="c8a11-124">設定第一個身分識別，這將是租使用者的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="c8a11-124">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="c8a11-125">填入 **名稱** 和 **密碼**。</span><span class="sxs-lookup"><span data-stu-id="c8a11-125">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="c8a11-126">按一下 [註冊]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-126">Click **Sign up**.</span></span>

   ![影像 of_Office 365 E5 試用註冊設定] 頁面，您可以在這裡設定您的商務身分識別](../../media/mtp-eval-14.png)

7. <span data-ttu-id="c8a11-128">按一下 [**移至設定**] 以完成 Office 365 E5 試用租使用者布建。</span><span class="sxs-lookup"><span data-stu-id="c8a11-128">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Office 365 E5 試用註冊安裝程式頁面的影像，提示按一下 [前往設定] 按鈕](../../media/mtp-eval-15.png)

8. <span data-ttu-id="c8a11-130">連線公司網域加入 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="c8a11-130">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="c8a11-131">選選擇 [**連線您已擁有的網域**，然後輸入您的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="c8a11-131">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="c8a11-132">按一下 \*\*\*\*[下一步]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-132">Click **Next**.</span></span>

   ![影像 of_Office 365 E5 安裝頁面，您應該在其中個人化登入和電子郵件](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="c8a11-134">新增 TXT 或 MX 記錄以驗證網域擁有權。</span><span class="sxs-lookup"><span data-stu-id="c8a11-134">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="c8a11-135">將 TXT 或 MX 記錄新增至您的網域後，請選取 [ **驗證**]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-135">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![影像 of_Office 365 E5 安裝頁面，您應該在這裡新增 TXT 的 MX 記錄以驗證您的網域](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="c8a11-137">選為您的租使用者建立更多使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c8a11-137">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="c8a11-138">您可以按 **[下一步]** 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="c8a11-138">You can skip this step by clicking **Next**.</span></span>

    ![影像 of_Office 365 E5 安裝頁面，您可以在其中新增更多使用者](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="c8a11-140">選下載 Office 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c8a11-140">[Optional] Download Office apps.</span></span> <span data-ttu-id="c8a11-141">按 **[下一步]** 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="c8a11-141">Click **Next** to skip this step.</span></span> 

    ![影像 of_Office 365 E5 頁面，您可以在此頁面上安裝 Office 應用程式](../../media/mtp-eval-19.png)

12. <span data-ttu-id="c8a11-143">選遷移電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c8a11-143">[Optional] Migrate email messages.</span></span> <span data-ttu-id="c8a11-144">您也可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="c8a11-144">Again, you can skip this step.</span></span>

    ![影像 of_Office 365 E5，您可以在其中設定是否要遷移電子郵件訊息](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="c8a11-146">選擇 [線上服務]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-146">Choose online services.</span></span> <span data-ttu-id="c8a11-147">選取 **Exchange** ，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c8a11-147">Select **Exchange** and click **Next**.</span></span> 

    ![影像 of_Office 365 E5，您可以在這裡選擇您的線上服務](../../media/mtp-eval-21.png)

14. <span data-ttu-id="c8a11-149">將 MX、CNAME 及 TXT 記錄新增至您的網域。</span><span class="sxs-lookup"><span data-stu-id="c8a11-149">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="c8a11-150">完成時，選取 [ **驗證**]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-150">When completed, select **Verify**.</span></span>

    ![影像 of_Office 365 E5 您可以在這裡加入您的 DNS 記錄](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="c8a11-152">恭喜，您已完成對 Office 365 租使用者的布建。</span><span class="sxs-lookup"><span data-stu-id="c8a11-152">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![影像 of_Office 365 E5 安裝完成確認頁面](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="c8a11-154">啟用 Microsoft 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="c8a11-154">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="c8a11-155">註冊試用版可提供25個使用者授權供一個月使用。</span><span class="sxs-lookup"><span data-stu-id="c8a11-155">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="c8a11-156">如需詳細資訊，請參閱 [Try Or 購買 M365 訂閱](../../commerce/try-or-buy-microsoft-365.md) 。</span><span class="sxs-lookup"><span data-stu-id="c8a11-156">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="c8a11-157">從 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，按一下 [**帳單**]，然後流覽至 [**購買服務**]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-157">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="c8a11-158">選取 **Microsoft 365 E5** ，然後按一下 [**開始免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-158">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![影像 of_Microsoft 365 E5 開始免費試用頁面](../../media/mtp-eval-24.png)

3. <span data-ttu-id="c8a11-160">選擇您的驗證喜好設定：透過短信或來電。</span><span class="sxs-lookup"><span data-stu-id="c8a11-160">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="c8a11-161">決定之後，請輸入電話號碼、選取 [ **文字** ] 或 [ **呼叫我** ]，視您的選擇而定。</span><span class="sxs-lookup"><span data-stu-id="c8a11-161">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 開始免費試用頁面，要求連絡人詳細資料傳送程式碼，以證明您不是機器人](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="c8a11-163">輸入驗證碼，然後按一下 [ **開始免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-163">Enter the verification code and click **Start your free trial**.</span></span>

   ![影像 of_Microsoft 365 E5 開始免費試用頁面，您可以在此頁面上填寫驗證碼，以證明您不是機器人](../../media/mtp-eval-26.png)

5. <span data-ttu-id="c8a11-165">按一下 [**立即試用**] 以確認您的 Microsoft 365 E5 試用版。</span><span class="sxs-lookup"><span data-stu-id="c8a11-165">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![影像 of_Microsoft 365 E5 開始免費試用頁面，您應該在此頁面上時鐘立即試按鈕開始](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="c8a11-167">前往 **Microsoft 365 系統管理 Center**  >  **使用者** 作用中的使用者  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8a11-167">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="c8a11-168">選取您的使用者帳戶，選取 [**管理產品授權**]，然後將授權從 Office 365 E5 換成 **Microsoft 365 E5**。</span><span class="sxs-lookup"><span data-stu-id="c8a11-168">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="c8a11-169">按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="c8a11-169">Click **Save**.</span></span>

   ![Image of_Microsoft 365 Admin Center 頁面，您可以在其中選取 Microsoft 365 E5 授權](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="c8a11-171">再次選取全域管理員帳戶，然後按一下 [ **管理使用者名稱**]。</span><span class="sxs-lookup"><span data-stu-id="c8a11-171">Select the global administrator account again then click **Manage username**.</span></span>

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中選取 [帳戶]，然後管理使用者名稱](../../media/mtp-eval-29.png)

8. <span data-ttu-id="c8a11-173">選根據您在先前步驟中選取的專案，將網域從 *onmicrosoft.com* 變更為您自己的網域。</span><span class="sxs-lookup"><span data-stu-id="c8a11-173">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="c8a11-174">按一下 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="c8a11-174">Click **Save changes**.</span></span>

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中變更您的網域偏好設定](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="c8a11-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c8a11-176">Next step</span></span>
|[<span data-ttu-id="c8a11-177">階段3：設定板載 &</span><span class="sxs-lookup"><span data-stu-id="c8a11-177">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="c8a11-178">針對 Microsoft 365 Defender 試用實驗室或試驗環境設定每個 Microsoft 365 Defender pillar，並在您的端點上架。</span><span class="sxs-lookup"><span data-stu-id="c8a11-178">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
