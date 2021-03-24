---
title: 設定您的 Microsoft 365 Defender 試用實驗室或試驗環境
description: 存取 Microsoft 365 的安全性中心，然後設定您的 Microsoft 365 Defender 試用實驗室環境
keywords: Microsoft 威脅防護試用設定，Microsoft 威脅防護試驗設定，嘗試 Microsoft 威脅防護，Microsoft 威脅防護評估實驗室安裝程式
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 976f6a1ec010348e8a281c251064acdd7a26748b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059631"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="86cb8-104">設定您的 Microsoft 365 Defender 試用實驗室環境</span><span class="sxs-lookup"><span data-stu-id="86cb8-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="86cb8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="86cb8-105">**Applies to:**</span></span>
- <span data-ttu-id="86cb8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86cb8-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="86cb8-107">建立 Microsoft 365 Defender 試驗實驗室或試驗環境並加以部署時，會有三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="86cb8-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="86cb8-108">[![階段1：準備](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="86cb8-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="86cb8-109">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="86cb8-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![階段2：設定](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="86cb8-111">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="86cb8-111">Phase 2: Set up</span></span> |<span data-ttu-id="86cb8-112">[![階段3：板載](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="86cb8-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="86cb8-113">階段3：板載</span><span class="sxs-lookup"><span data-stu-id="86cb8-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="86cb8-114">[![回到試驗](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="86cb8-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="86cb8-115">回到試驗行動手冊</span><span class="sxs-lookup"><span data-stu-id="86cb8-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="86cb8-116">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="86cb8-116">*You are here!*</span></span>  | | |


<span data-ttu-id="86cb8-117">您目前是在 [設定] 階段。</span><span class="sxs-lookup"><span data-stu-id="86cb8-117">You're currently in the set up phase.</span></span> <span data-ttu-id="86cb8-118">請先開始存取 Microsoft 365 的安全性中心，然後設定您的試用實驗室或試驗環境。</span><span class="sxs-lookup"><span data-stu-id="86cb8-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="86cb8-119">註冊 Office 365 或 Azure Active Directory 訂閱以產生 *onmicrosoft.com* 租使用者，您可以用來註冊您的 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="86cb8-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="86cb8-120">如果您已有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用或試驗承租人建立步驟。</span><span class="sxs-lookup"><span data-stu-id="86cb8-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="86cb8-121">在這個階段中，您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="86cb8-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="86cb8-122">建立 Office 365 E5 試用租使用者</span><span class="sxs-lookup"><span data-stu-id="86cb8-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="86cb8-123">啟用 Microsoft 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="86cb8-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="86cb8-124">建立 Office 365 E5 試用租使用者</span><span class="sxs-lookup"><span data-stu-id="86cb8-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="86cb8-125">如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用租使用者建立步驟。</span><span class="sxs-lookup"><span data-stu-id="86cb8-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="86cb8-126">移至 [Office 365 E5 產品入口網站](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) ，然後選取 [ **免費試用版**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![影像 of_Office 365 E5 免費試用版頁面](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="86cb8-128">輸入您的電子郵件地址 (個人或公司) ，以完成試用註冊。</span><span class="sxs-lookup"><span data-stu-id="86cb8-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="86cb8-129">按一下 [ **設定帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-129">Click **Set up account**.</span></span>

   ![影像 of_Office 365 E5 試用版註冊設定] 頁面](../../media/mtp-eval-10.png)

3. <span data-ttu-id="86cb8-131">請填入您的名字、姓氏、商務電話號碼、公司名稱、公司規模和國家或地區。</span><span class="sxs-lookup"><span data-stu-id="86cb8-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![影像 of_Office 365 E5 試用註冊設定頁面要求名稱、電話及公司詳細資料](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="86cb8-133">您在這裡設定的國家或地區決定您的 Office 365 將主控的資料中心區域。</span><span class="sxs-lookup"><span data-stu-id="86cb8-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="86cb8-134">選擇您的驗證喜好設定：透過短信或來電。</span><span class="sxs-lookup"><span data-stu-id="86cb8-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="86cb8-135">按一下 [ **傳送驗證碼**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-135">Click **Send Verification Code**.</span></span> 

   ![影像 of_Office 365 E5 試用註冊設定頁面要求驗證偏好設定](../../media/mtp-eval-12.png)

5. <span data-ttu-id="86cb8-137">為您的租使用者設定自訂的功能變數名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="86cb8-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![影像 of_Office 365 E5 試用註冊設定] 頁面，您可以在其中設定自訂功能變數名稱](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="86cb8-139">設定第一個身分識別，這將是租使用者的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="86cb8-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="86cb8-140">填入 **名稱** 和 **密碼**。</span><span class="sxs-lookup"><span data-stu-id="86cb8-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="86cb8-141">按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-141">Click **Sign up**.</span></span>

   ![影像 of_Office 365 E5 試用註冊設定] 頁面，您可以在這裡設定您的商務身分識別](../../media/mtp-eval-14.png)

7. <span data-ttu-id="86cb8-143">按一下 [ **移至設定** ] 以完成 Office 365 E5 試用租使用者布建。</span><span class="sxs-lookup"><span data-stu-id="86cb8-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Office 365 E5 試用註冊設定頁面的影像提示按一下 [前往設定] 按鈕](../../media/mtp-eval-15.png)

8. <span data-ttu-id="86cb8-145">將公司網域連線到 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="86cb8-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="86cb8-146">選選擇 **[連線您已擁有的網域]** ，然後輸入您的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="86cb8-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="86cb8-147">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="86cb8-147">Click **Next**.</span></span>

   ![影像 of_Office 365 E5 安裝頁面，您應該在其中個人化登入和電子郵件](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="86cb8-149">新增 TXT 或 MX 記錄以驗證網域擁有權。</span><span class="sxs-lookup"><span data-stu-id="86cb8-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="86cb8-150">將 TXT 或 MX 記錄新增至您的網域後，請選取 [ **驗證**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![影像 of_Office 365 E5 安裝頁面，您應該在這裡新增 TXT 的 MX 記錄以驗證您的網域](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="86cb8-152">選為您的租使用者建立更多使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="86cb8-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="86cb8-153">您可以按 **[下一步]** 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="86cb8-153">You can skip this step by clicking **Next**.</span></span>

    ![影像 of_Office 365 E5 安裝頁面，您可以在其中新增更多使用者](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="86cb8-155">選下載 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="86cb8-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="86cb8-156">按 **[下一步]** 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="86cb8-156">Click **Next** to skip this step.</span></span> 

    ![影像 of_Office 365 E5 頁面，您可以在此安裝 Office 應用程式](../../media/mtp-eval-19.png)

12. <span data-ttu-id="86cb8-158">選遷移電子郵件。</span><span class="sxs-lookup"><span data-stu-id="86cb8-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="86cb8-159">您也可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="86cb8-159">Again, you can skip this step.</span></span>

    ![影像 of_Office 365 E5，您可以在其中設定是否要遷移電子郵件訊息](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="86cb8-161">選擇 [線上服務]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-161">Choose online services.</span></span> <span data-ttu-id="86cb8-162">選取 [ **Exchange** ] 並按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="86cb8-162">Select **Exchange** and click **Next**.</span></span> 

    ![影像 of_Office 365 E5，您可以在這裡選擇您的線上服務](../../media/mtp-eval-21.png)

14. <span data-ttu-id="86cb8-164">將 MX、CNAME 及 TXT 記錄新增至您的網域。</span><span class="sxs-lookup"><span data-stu-id="86cb8-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="86cb8-165">完成時，選取 [ **驗證**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-165">When completed, select **Verify**.</span></span>

    ![影像 of_Office 365 E5 您可以在這裡加入您的 DNS 記錄](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="86cb8-167">恭喜，您已完成布建您的 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="86cb8-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![影像 of_Office 365 E5 安裝完成確認頁面](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="86cb8-169">啟用 Microsoft 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="86cb8-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="86cb8-170">註冊試用版可提供25個使用者授權供一個月使用。</span><span class="sxs-lookup"><span data-stu-id="86cb8-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="86cb8-171">如需詳細資訊，請參閱 [Try Or 購買 M365 訂閱](../../commerce/try-or-buy-microsoft-365.md) 。</span><span class="sxs-lookup"><span data-stu-id="86cb8-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="86cb8-172">從 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，按一下 [ **帳單** ]，然後流覽至 [ **購買服務**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="86cb8-173">選取 [ **Microsoft 365 E5** ]，然後按一下 [ **開始免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![影像 of_Microsoft 365 E5 開始免費試用頁面](../../media/mtp-eval-24.png)

3. <span data-ttu-id="86cb8-175">選擇您的驗證喜好設定：透過短信或來電。</span><span class="sxs-lookup"><span data-stu-id="86cb8-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="86cb8-176">決定之後，請輸入電話號碼、選取 [ **文字** ] 或 [ **呼叫我** ]，視您的選擇而定。</span><span class="sxs-lookup"><span data-stu-id="86cb8-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 開始免費試用頁面，要求連絡人詳細資料傳送程式碼，以證明您不是機器人](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="86cb8-178">輸入驗證碼，然後按一下 [ **開始免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![影像 of_Microsoft 365 E5 開始免費試用頁面，您可以在此頁面上填寫驗證碼，以證明您不是機器人](../../media/mtp-eval-26.png)

5. <span data-ttu-id="86cb8-180">按一下 [ **立即試用** ] 以確認您的 Microsoft 365 E5 試用版。</span><span class="sxs-lookup"><span data-stu-id="86cb8-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![影像 of_Microsoft 365 E5 開始免費試用頁面，您應該在此頁面上時鐘立即試按鈕開始](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="86cb8-182">移至 **Microsoft 365 Admin Center** 使用者作用中的  >    >  **使用者**。</span><span class="sxs-lookup"><span data-stu-id="86cb8-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="86cb8-183">選取您的使用者帳戶，選取 [ **管理產品授權**]，然後將 Office 365 e5 的授權交換至 **Microsoft 365 E5**。</span><span class="sxs-lookup"><span data-stu-id="86cb8-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="86cb8-184">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="86cb8-184">Click **Save**.</span></span>

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中選取 [Microsoft 365 E5 授權]](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="86cb8-186">再次選取全域管理員帳戶，然後按一下 [ **管理使用者名稱**]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中選取 [帳戶]，然後管理使用者名稱](../../media/mtp-eval-29.png)

8. <span data-ttu-id="86cb8-188">選根據您在先前步驟中選取的專案，將網域從 *onmicrosoft.com* 變更為您自己的網域。</span><span class="sxs-lookup"><span data-stu-id="86cb8-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="86cb8-189">按一下 [儲存變更]。</span><span class="sxs-lookup"><span data-stu-id="86cb8-189">Click **Save changes**.</span></span>

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中變更您的網域偏好設定](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="86cb8-191">下一步</span><span class="sxs-lookup"><span data-stu-id="86cb8-191">Next step</span></span>
|[<span data-ttu-id="86cb8-192">階段3：設定板載 &</span><span class="sxs-lookup"><span data-stu-id="86cb8-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="86cb8-193">針對您的 Microsoft 365 Defender 試用實驗室或試驗環境和您的端點上架每個 Microsoft 365 Defender pillar。</span><span class="sxs-lookup"><span data-stu-id="86cb8-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
