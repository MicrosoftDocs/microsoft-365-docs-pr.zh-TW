---
title: 設定您的 Microsoft 威脅防護試用實驗室環境
description: 存取 Microsoft 365 的安全性中心，然後設定您的 Microsoft 威脅防護試用實驗室環境
keywords: Microsoft 威脅防護試用版設定，請嘗試 Microsoft 威脅防護，Microsoft 威脅防護評估實驗室安裝程式
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049612"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="166ef-104">設定您的 Microsoft 威脅防護試用實驗室環境</span><span class="sxs-lookup"><span data-stu-id="166ef-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="166ef-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="166ef-105">**Applies to:**</span></span>
- <span data-ttu-id="166ef-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="166ef-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="166ef-107">建立 Microsoft 威脅防護試用實驗室環境並加以部署時，會有三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="166ef-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="準備您的 Microsoft 威脅防護評估實驗室" />
      <br/><span data-ttu-id="166ef-109">階段1：準備</a></span><span class="sxs-lookup"><span data-stu-id="166ef-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="設定您的 Microsoft 威脅防護評估實驗室" />
      <br/><span data-ttu-id="166ef-111">階段2：設定</a></span><span class="sxs-lookup"><span data-stu-id="166ef-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
針對您的 Microsoft 威脅防護試用實驗室環境和您的端點設定每個 Microsoft 威脅防護 pillar" />
      <br/><span data-ttu-id="166ef-113">階段3：設定板載 &</a></span><span class="sxs-lookup"><span data-stu-id="166ef-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="166ef-114">您目前在設定階段。</span><span class="sxs-lookup"><span data-stu-id="166ef-114">You are currently in the set up phase.</span></span> <span data-ttu-id="166ef-115">請先開始存取 Microsoft 365 的安全性中心，然後安裝您的試用實驗室環境。</span><span class="sxs-lookup"><span data-stu-id="166ef-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="166ef-116">註冊 Office 365 或 Azure Active Directory 訂閱以產生*onmicrosoft.com*租使用者，您可以用來註冊您的 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="166ef-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="166ef-117">如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用租使用者建立步驟。</span><span class="sxs-lookup"><span data-stu-id="166ef-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="166ef-118">在這個階段中，您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="166ef-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="166ef-119">建立 Office 365 E5 試用租使用者</span><span class="sxs-lookup"><span data-stu-id="166ef-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="166ef-120">啟用 Microsoft 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="166ef-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="166ef-121">建立 Office 365 E5 試用租使用者</span><span class="sxs-lookup"><span data-stu-id="166ef-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="166ef-122">如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用租使用者建立步驟。</span><span class="sxs-lookup"><span data-stu-id="166ef-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="166ef-123">移至[Office 365 E5 產品入口網站](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)，然後選取 [**免費試用版**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="166ef-124">![影像 of_page](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-124">![Image of_page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="166ef-125">輸入您的電子郵件地址（個人或公司）以完成試用註冊。</span><span class="sxs-lookup"><span data-stu-id="166ef-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="166ef-126">按一下 [**設定帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-126">Click **Set up account**.</span></span>
<span data-ttu-id="166ef-127">![影像 of_page](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-127">![Image of_page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="166ef-128">請填入您的名字、姓氏、商務電話號碼、公司名稱、公司規模和國家或地區。</span><span class="sxs-lookup"><span data-stu-id="166ef-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![影像 of_page](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="166ef-130">您在這裡設定的國家或地區決定您的 Office 365 將主控的資料中心區域。</span><span class="sxs-lookup"><span data-stu-id="166ef-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="166ef-131">選擇您的驗證喜好設定：透過短信或來電。</span><span class="sxs-lookup"><span data-stu-id="166ef-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="166ef-132">按一下 [**傳送驗證碼**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="166ef-133">![影像 of_page](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-133">![Image of_page](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="166ef-134">為您的租使用者設定自訂的功能變數名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="166ef-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="166ef-135">![影像 of_page](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-135">![Image of_page](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="166ef-136">設定將成為租使用者之全域管理員的第一個身分識別。</span><span class="sxs-lookup"><span data-stu-id="166ef-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="166ef-137">填入**名稱**和**密碼**。</span><span class="sxs-lookup"><span data-stu-id="166ef-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="166ef-138">按一下 [**註冊**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-138">Click **Sign up**.</span></span>
<span data-ttu-id="166ef-139">![影像 of_page](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-139">![Image of_page](../../media/mtp-eval-14.png)</span></span> <br>
<span data-ttu-id="166ef-140">c</span><span class="sxs-lookup"><span data-stu-id="166ef-140">c</span></span>
7. <span data-ttu-id="166ef-141">按一下 [**移至設定**] 以完成 Office 365 E5 試用租使用者布建。</span><span class="sxs-lookup"><span data-stu-id="166ef-141">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="166ef-142">![影像 of_page](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-142">![Image of_page](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="166ef-143">將公司網域連線到 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="166ef-143">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="166ef-144">選選擇 **[連線您已擁有的網域]** ，然後輸入您的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="166ef-144">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="166ef-145">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="166ef-145">Click **Next**.</span></span>
<br><span data-ttu-id="166ef-146">![影像 of_page](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-146">![Image of_page](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="166ef-147">您將需要新增 TXT 或 MX 記錄以驗證網域擁有權。</span><span class="sxs-lookup"><span data-stu-id="166ef-147">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="166ef-148">將 TXT 或 MX 記錄新增至您的網域後，請選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-148">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="166ef-149">![影像 of_page](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-149">![Image of_page](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="166ef-150">選為您的租使用者建立更多使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="166ef-150">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="166ef-151">您可以按 **[下一步]** 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="166ef-151">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="166ef-152">![影像 of_page](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-152">![Image of_page](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="166ef-153">選下載 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="166ef-153">[Optional] Download Office apps.</span></span> <span data-ttu-id="166ef-154">按 **[下一步]** 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="166ef-154">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="166ef-155">![影像 of_page](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-155">![Image of_page](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="166ef-156">選遷移電子郵件。</span><span class="sxs-lookup"><span data-stu-id="166ef-156">[Optional] Migrate email messages.</span></span> <span data-ttu-id="166ef-157">您也可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="166ef-157">Again, you can skip this step.</span></span>
<br><span data-ttu-id="166ef-158">![影像 of_page](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-158">![Image of_page](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="166ef-159">選擇 [線上服務]。</span><span class="sxs-lookup"><span data-stu-id="166ef-159">Choose online services.</span></span> <span data-ttu-id="166ef-160">選取 [ **Exchange** ] 並按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="166ef-160">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="166ef-161">![影像 of_page](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-161">![Image of_page](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="166ef-162">將 MX、CNAME 和 TXT 記錄新增至您的網域。</span><span class="sxs-lookup"><span data-stu-id="166ef-162">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="166ef-163">完成時，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-163">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="166ef-164">![影像 of_page](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-164">![Image of_page](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="166ef-165">恭喜，您已完成布建您的 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="166ef-165">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="166ef-166">![影像 of_page](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-166">![Image of_page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="166ef-167">啟用 Microsoft 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="166ef-167">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="166ef-168">註冊試用版可提供25個使用者授權供一個月使用。</span><span class="sxs-lookup"><span data-stu-id="166ef-168">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="166ef-169">如需詳細資訊，請參閱[Try Or 購買 M365 訂閱](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1)。</span><span class="sxs-lookup"><span data-stu-id="166ef-169">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="166ef-170">從[Microsoft 365 系統管理中心](https://admin.microsoft.com/)，按一下 [**帳單**]，然後流覽至 [**購買服務**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-170">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="166ef-171">選取 [ **Microsoft 365 E5** ]，然後按一下 [**開始免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-171">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="166ef-172">![影像 of_page](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-172">![Image of_page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="166ef-173">選擇您的驗證喜好設定：透過短信或來電。</span><span class="sxs-lookup"><span data-stu-id="166ef-173">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="166ef-174">決定之後，請輸入電話號碼、選取 [**文字**] 或 [**呼叫我**]，視您的選擇而定。</span><span class="sxs-lookup"><span data-stu-id="166ef-174">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="166ef-175">![影像 of_page](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-175">![Image of_page](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="166ef-176">輸入驗證碼，然後按一下 [**開始免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-176">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="166ef-177">![影像 of_page](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-177">![Image of_page](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="166ef-178">按一下 [**立即試用**] 以確認您的 Microsoft 365 E5 試用版。</span><span class="sxs-lookup"><span data-stu-id="166ef-178">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="166ef-179">![影像 of_page](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-179">![Image of_page](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="166ef-180">移至**Microsoft 365 Admin Center** > **使用者** > 作用中的**使用者**。</span><span class="sxs-lookup"><span data-stu-id="166ef-180">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="166ef-181">選取您的使用者帳戶，選取 [**管理產品授權**]，然後將 Office 365 e5 的授權交換至**Microsoft 365 E5**。</span><span class="sxs-lookup"><span data-stu-id="166ef-181">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="166ef-182">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="166ef-182">Click **Save**.</span></span>
<span data-ttu-id="166ef-183">![影像 of_page](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-183">![Image of_page](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="166ef-184">再次選取全域管理員帳戶，然後按一下 [**管理使用者名稱**]。</span><span class="sxs-lookup"><span data-stu-id="166ef-184">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="166ef-185">![影像 of_page](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-185">![Image of_page](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="166ef-186">選根據您在先前步驟中選取的專案，將網域從*onmicrosoft.com*變更為您自己的網域。</span><span class="sxs-lookup"><span data-stu-id="166ef-186">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="166ef-187">按一下 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="166ef-187">Click **Save changes**.</span></span>
<br><span data-ttu-id="166ef-188">![影像 of_page](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="166ef-188">![Image of_page](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="166ef-189">後續步驟</span><span class="sxs-lookup"><span data-stu-id="166ef-189">Next step</span></span>
<span data-ttu-id="166ef-190">||||：-------|：-----| config-onboard （.png）</span><span class="sxs-lookup"><span data-stu-id="166ef-190">||| |:-------|:-----|config-onboard.png)</span></span> <br><span data-ttu-id="166ef-191">[階段3：設定 & 板載](config-mtpeval.md)|針對您的 Microsoft 威脅防護試用實驗室環境設定每個 Microsoft 威脅防護 pillar，並在您的端點上架。</span><span class="sxs-lookup"><span data-stu-id="166ef-191">[Phase 3: Configure & Onboard](config-mtpeval.md) | Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints.</span></span>
