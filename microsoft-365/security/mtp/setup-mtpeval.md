---
title: 設定您的 Microsoft 365 Defender 試用版實驗室或試驗環境
description: Access Microsoft 365 資訊安全中心，然後設定您的 Microsoft 365 Defender 試用版實驗室環境
keywords: Microsoft 威脅防護試驗設定、Microsoft 威脅防護試驗設定、試用 Microsoft 威脅防護、Microsoft 威脅防護評估實驗室設定
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932979"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="fd571-104">設定您的 Microsoft 365 Defender 試用版實驗室環境</span><span class="sxs-lookup"><span data-stu-id="fd571-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fd571-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="fd571-105">**Applies to:**</span></span>
- <span data-ttu-id="fd571-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd571-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="fd571-107">建立 Microsoft 365 Defender 試用版實驗室或試驗環境並部署此為三階段程式：</span><span class="sxs-lookup"><span data-stu-id="fd571-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="fd571-108">[![階段 1：準備](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="fd571-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="fd571-109">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="fd571-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![階段 2：設定](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="fd571-111">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="fd571-111">Phase 2: Set up</span></span> |<span data-ttu-id="fd571-112">[![階段 3：上機](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="fd571-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="fd571-113">階段 3：上機</span><span class="sxs-lookup"><span data-stu-id="fd571-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="fd571-114">[![返回試驗](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="fd571-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="fd571-115">回到試驗手冊</span><span class="sxs-lookup"><span data-stu-id="fd571-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="fd571-116">*您目前在這裡！*</span><span class="sxs-lookup"><span data-stu-id="fd571-116">*You are here!*</span></span>  | | |


<span data-ttu-id="fd571-117">您目前處於設定階段。</span><span class="sxs-lookup"><span data-stu-id="fd571-117">You're currently in the set up phase.</span></span> <span data-ttu-id="fd571-118">採取存取 Microsoft 365 資訊安全中心的初始步驟，然後設定您的試驗實驗室或試驗環境。</span><span class="sxs-lookup"><span data-stu-id="fd571-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="fd571-119">註冊 Office 365 或 Azure Active Directory 訂閱以產生 *.onmicrosoft.com* 租使用者，您可以使用該租使用者註冊您的 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="fd571-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="fd571-120">如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用版或試驗租使用者建立步驟。</span><span class="sxs-lookup"><span data-stu-id="fd571-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="fd571-121">在這個階段，您將受指引到：</span><span class="sxs-lookup"><span data-stu-id="fd571-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="fd571-122">建立 Office 365 E5 試用版租使用者</span><span class="sxs-lookup"><span data-stu-id="fd571-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="fd571-123">啟用 Microsoft 365 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="fd571-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="fd571-124">建立 Office 365 E5 試用版租使用者</span><span class="sxs-lookup"><span data-stu-id="fd571-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="fd571-125">如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用版租使用者建立步驟。</span><span class="sxs-lookup"><span data-stu-id="fd571-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="fd571-126">請前往 [Office 365 E5 產品](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 入口網站，然後選取 **免費試用**。</span><span class="sxs-lookup"><span data-stu-id="fd571-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![365 of_Office 365 免費試用版頁面的影像](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="fd571-128">在個人或公司 (電子郵件地址以完成) 。</span><span class="sxs-lookup"><span data-stu-id="fd571-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="fd571-129">按一下 **[設定帳戶**。</span><span class="sxs-lookup"><span data-stu-id="fd571-129">Click **Set up account**.</span></span>

   ![365 E5 of_Office註冊設定頁面的圖像](../../media/mtp-eval-10.png)

3. <span data-ttu-id="fd571-131">填入您的名字、姓氏、公司電話號碼、公司名稱、公司大小，以及國家/地區。</span><span class="sxs-lookup"><span data-stu-id="fd571-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![影像of_Office 365 E5 試用版註冊設定頁面，詢問名稱、電話和公司詳細資料](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="fd571-133">您在這裡設定的國家/地區或區域會決定您的 Office 365 將託管的資料中心區域。</span><span class="sxs-lookup"><span data-stu-id="fd571-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="fd571-134">選擇您的驗證喜好設定：透過文字訊息或通話。</span><span class="sxs-lookup"><span data-stu-id="fd571-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="fd571-135">按一下 **[傳送驗證碼**。</span><span class="sxs-lookup"><span data-stu-id="fd571-135">Click **Send Verification Code**.</span></span> 

   ![要求of_Office 365 E5 試用版註冊設定頁面的圖像](../../media/mtp-eval-12.png)

5. <span data-ttu-id="fd571-137">設定租使用者自訂功能變數名稱，然後按一下 [下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="fd571-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![可在 of_Office 365 E5 試用版註冊設定頁面設定自訂功能變數名稱的影像](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="fd571-139">設定第一個身分識別，該身分識別即為租使用者全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="fd571-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="fd571-140">填入 **名稱和\*\*\*\*密碼**。</span><span class="sxs-lookup"><span data-stu-id="fd571-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="fd571-141">按一下 **[註冊**。</span><span class="sxs-lookup"><span data-stu-id="fd571-141">Click **Sign up**.</span></span>

   ![可在 of_Office 365 E5 試用版註冊設定頁面設定商務身分識別的影像](../../media/mtp-eval-14.png)

7. <span data-ttu-id="fd571-143">按一下 **[前往設定** 以完成 Office 365 E5 試用版租使用者設定。</span><span class="sxs-lookup"><span data-stu-id="fd571-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Office 365 E5 試用版註冊設定頁面的影像，提示您按一下 [執行設定按鈕](../../media/mtp-eval-15.png)

8. <span data-ttu-id="fd571-145">將您的公司網域連接到 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="fd571-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="fd571-146">[選擇性]選擇 **連接您已有的網域** ，然後輸入您的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="fd571-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="fd571-147">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fd571-147">Click **Next**.</span></span>

   ![365 of_Office 365 設定頁面的影像，您應該在這裡個人化您的登錄和電子郵件](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="fd571-149">新增 TXT 或 MX 記錄以驗證網域擁有權。</span><span class="sxs-lookup"><span data-stu-id="fd571-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="fd571-150">一旦將 TXT 或 MX 記錄新增到您的網域後， **請選取驗證**。</span><span class="sxs-lookup"><span data-stu-id="fd571-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![<of_Office 365 E5 設定頁面的圖像，您應該在這裡新增 MX 記錄的 TXT 以驗證您的網域](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="fd571-152">[選擇性]為租使用者建立更多使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="fd571-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="fd571-153">您可以按一下下一步來跳過 **此步驟**。</span><span class="sxs-lookup"><span data-stu-id="fd571-153">You can skip this step by clicking **Next**.</span></span>

    ![可在 of_Office 365 E5 設定頁面新增更多使用者的影像](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="fd571-155">[選擇性]下載 Office App。</span><span class="sxs-lookup"><span data-stu-id="fd571-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="fd571-156">按一下 **[下一** 步， 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="fd571-156">Click **Next** to skip this step.</span></span> 

    ![可在 of_Office 365 E5 頁面安裝 Office 應用程式的影像](../../media/mtp-eval-19.png)

12. <span data-ttu-id="fd571-158">[選擇性]遷移電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="fd571-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="fd571-159">同樣，您可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="fd571-159">Again, you can skip this step.</span></span>

    ![圖像of_Office 365 E5 中，您可以在這裡設定是否要要遷移電子郵件訊息](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="fd571-161">選擇線上服務。</span><span class="sxs-lookup"><span data-stu-id="fd571-161">Choose online services.</span></span> <span data-ttu-id="fd571-162">選取 **Exchange，** 然後按一下 [下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="fd571-162">Select **Exchange** and click **Next**.</span></span> 

    ![可在 of_Office 365 E5 選擇線上服務的影像](../../media/mtp-eval-21.png)

14. <span data-ttu-id="fd571-164">新增 MX、CNAME 和 TXT 記錄至您的網域。</span><span class="sxs-lookup"><span data-stu-id="fd571-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="fd571-165">完成後， **請選取驗證**。</span><span class="sxs-lookup"><span data-stu-id="fd571-165">When completed, select **Verify**.</span></span>

    ![您可以在of_Office 365 E5 中新增 DNS 記錄的影像](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="fd571-167">恭喜您，您已完成您的 Office 365 租使用者提供。</span><span class="sxs-lookup"><span data-stu-id="fd571-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![365 E5 of_Office確認頁面的圖像](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="fd571-169">啟用 Microsoft 365 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="fd571-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="fd571-170">註冊試用版可給您 25 個使用者授權，一個月可以使用。</span><span class="sxs-lookup"><span data-stu-id="fd571-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="fd571-171">請參閱 [試用或購買 M365 訂閱以](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 瞭解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="fd571-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="fd571-172">從 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，按一下 [ **帳單** ，然後流覽至 **購買服務**。</span><span class="sxs-lookup"><span data-stu-id="fd571-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="fd571-173">選取 **Microsoft 365 E5，** 然後按一下 [ **開始免費試用**。</span><span class="sxs-lookup"><span data-stu-id="fd571-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![365 of_Microsoft 365 開始免費試用頁面的圖像](../../media/mtp-eval-24.png)

3. <span data-ttu-id="fd571-175">選擇您的驗證喜好設定：透過文字訊息或通話。</span><span class="sxs-lookup"><span data-stu-id="fd571-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="fd571-176">一旦決定好後，請輸入電話號碼，**然後根據您的選擇** 選取範圍選取給我或撥打給我。</span><span class="sxs-lookup"><span data-stu-id="fd571-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![影像of_Microsoft 365 E5 開始免費試用頁面，要求聯絡人詳細資料以傳送驗證碼以證明您不是機器人](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="fd571-178">輸入驗證碼，然後按一下 **[開始免費試用**。</span><span class="sxs-lookup"><span data-stu-id="fd571-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![圖像of_Microsoft 365 E5 開始免費試用頁面，您可以在此填寫系統為了證明您不是機器人而送出驗證碼](../../media/mtp-eval-26.png)

5. <span data-ttu-id="fd571-180">按一下 **[立即試用** 以確認您的 Microsoft 365 E5 試用版。</span><span class="sxs-lookup"><span data-stu-id="fd571-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![影像of_Microsoft 365 E5 開始免費試用頁面，您應該在此頁面打卡以開始試用](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="fd571-182">請前往 **Microsoft 365 系統管理中心**  >  **使用者**  >  **主動使用者**。</span><span class="sxs-lookup"><span data-stu-id="fd571-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="fd571-183">選取您的使用者帳戶，選取 **管理產品** 授權，然後將授權從 Office 365 E5 切換至 **Microsoft 365 E5。**</span><span class="sxs-lookup"><span data-stu-id="fd571-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="fd571-184">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="fd571-184">Click **Save**.</span></span>

   ![可在 of_Microsoft 365 系統管理中心頁面選取 Microsoft 365 E5 授權的圖像](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="fd571-186">再次選取全域系統管理員帳戶，然後按一下 [ **管理使用者名稱**。</span><span class="sxs-lookup"><span data-stu-id="fd571-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![可在 of_Microsoft 365 系統管理中心頁面選取帳戶，然後管理使用者名稱的影像](../../media/mtp-eval-29.png)

8. <span data-ttu-id="fd571-188">[選擇性]根據您在onmicrosoft.com選擇哪些專案，將網域從新網域變更為您自己的網域。</span><span class="sxs-lookup"><span data-stu-id="fd571-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="fd571-189">按一下 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="fd571-189">Click **Save changes**.</span></span>

   ![可在 of_Microsoft 365 系統管理中心頁面變更網域喜好設定的圖像](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="fd571-191">下一步</span><span class="sxs-lookup"><span data-stu-id="fd571-191">Next step</span></span>
|[<span data-ttu-id="fd571-192">階段 3：設定&上</span><span class="sxs-lookup"><span data-stu-id="fd571-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="fd571-193">針對您的 Microsoft 365 Defender 試用版實驗室或試驗環境設定每個 Microsoft 365 Defender 基礎，並設置端點。</span><span class="sxs-lookup"><span data-stu-id="fd571-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
