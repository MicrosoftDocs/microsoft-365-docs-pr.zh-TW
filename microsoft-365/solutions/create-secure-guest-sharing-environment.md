---
title: 建立安全的來賓共用環境
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
ms.custom:
- M365solutions
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: 在本文中，您將了解在 Microsoft 365 中建立安全的來賓共用環境的可用選項。
ms.openlocfilehash: 848bdef888ab6d6fb20db2a461912f180bfa212c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036121"
---
# <a name="create-a-secure-guest-sharing-environment"></a><span data-ttu-id="b630d-103">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="b630d-103">Create a secure guest sharing environment</span></span>

<span data-ttu-id="b630d-104">在本文中，我們將逐一介紹用於在 Microsoft 365 中建立安全的來賓共用環境的各種選項。</span><span class="sxs-lookup"><span data-stu-id="b630d-104">In this article, we'll walk through a variety of options for creating a secure guest sharing environment in Microsoft 365.</span></span> <span data-ttu-id="b630d-105">這是範例案例，讓您了解可用的選項。</span><span class="sxs-lookup"><span data-stu-id="b630d-105">This is an example scenario to give you an idea of the options available.</span></span> <span data-ttu-id="b630d-106">您可以用不同的組合使用這些程序，以符合貴組織的安全性和合規性需求。</span><span class="sxs-lookup"><span data-stu-id="b630d-106">You can use these procedures in different combinations to meet the security and compliance needs of your organization.</span></span> <span data-ttu-id="b630d-107">在本文的結尾，我們將逐步說明測試案例，以了解這些選項的共同運作方式。</span><span class="sxs-lookup"><span data-stu-id="b630d-107">At the end of the article, we'll walk through a test case to see how some of these options work together.</span></span>

<span data-ttu-id="b630d-108">此案例包括：</span><span class="sxs-lookup"><span data-stu-id="b630d-108">This scenario includes:</span></span>

- <span data-ttu-id="b630d-109">為來賓設定多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="b630d-109">Setting up multi-factor authentication for guests.</span></span>
- <span data-ttu-id="b630d-110">為來賓設定使用規定。</span><span class="sxs-lookup"><span data-stu-id="b630d-110">Setting up a terms of use for guests.</span></span>
- <span data-ttu-id="b630d-111">設定每季來賓存取權檢閱，以定期驗證來賓是否繼續需要小組和網站的使用權限。</span><span class="sxs-lookup"><span data-stu-id="b630d-111">Setting up quarterly guest access reviews to periodically validate whether guests continue to need permissions to teams and sites.</span></span>
- <span data-ttu-id="b630d-112">將來賓限制為僅限網頁存取未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="b630d-112">Restricting guests to web-only access for unmanaged devices.</span></span>
- <span data-ttu-id="b630d-113">設定工作階段逾時原則，以確保來賓每天進行驗證。</span><span class="sxs-lookup"><span data-stu-id="b630d-113">Configuring a session timeout policy to ensure guests authenticate daily.</span></span>
- <span data-ttu-id="b630d-114">建立及發佈敏感度標籤以分類內容。</span><span class="sxs-lookup"><span data-stu-id="b630d-114">Creating and publishing sensitivity labels to classify content.</span></span>
- <span data-ttu-id="b630d-115">建立高敏感度專案的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b630d-115">Creating a sensitive information type for a highly sensitive project.</span></span>
- <span data-ttu-id="b630d-116">自動將*高敏感度*標籤指派給包含敏感性資訊類型的文件。</span><span class="sxs-lookup"><span data-stu-id="b630d-116">Automatically assigning a *highly sensitive* label to documents that contain the sensitive information type.</span></span>
- <span data-ttu-id="b630d-117">自動從標示為*高敏感度*的檔案移除來賓存取權。</span><span class="sxs-lookup"><span data-stu-id="b630d-117">Automatically removing guest access from files labeled as *highly sensitive*.</span></span>

<span data-ttu-id="b630d-118">本文中所述的部分選項要求來賓在 Azure Active Directory 中擁有帳戶。</span><span class="sxs-lookup"><span data-stu-id="b630d-118">Some of the options discussed in this article require guests to have an account in Azure Active Directory.</span></span> <span data-ttu-id="b630d-119">若要確保共用檔案和資料夾時目錄中包含來賓，請使用 [SharePoint 和 OneDrive 與 Azure AD B2B 整合 (預覽版)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)。</span><span class="sxs-lookup"><span data-stu-id="b630d-119">To ensure that guests are included in the directory when you share files and folders with them, use the [SharePoint and OneDrive integration with Azure AD B2B Preview](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="b630d-120">請注意，我們不會在本文中討論啟用來賓共用設定。</span><span class="sxs-lookup"><span data-stu-id="b630d-120">Note that we won't discuss enabling guest sharing settings in this article.</span></span> <span data-ttu-id="b630d-121">如需針對不同案例啟用來賓共用的詳細資訊，請參閱[與組織外部人員共同作業](https://docs.microsoft.com/Office365/Enterprise/collaborate-with-people-outside-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="b630d-121">See [Collaborating with people outside your organization](https://docs.microsoft.com/Office365/Enterprise/collaborate-with-people-outside-your-organization) for details about enabling guest sharing for different scenarios.</span></span>

## <a name="set-up-multi-factor-authentication-for-guests"></a><span data-ttu-id="b630d-122">為來賓設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="b630d-122">Set up multi-factor authentication for guests</span></span>

<span data-ttu-id="b630d-123">多重要素驗證可大幅降低帳戶遭入侵的機會。</span><span class="sxs-lookup"><span data-stu-id="b630d-123">Multi-factor authentication greatly reduces the chances of an account being compromised.</span></span> <span data-ttu-id="b630d-124">由於來賓使用者可能使用不符合任何控管原則或最佳做法的個人電子郵件帳戶，因此要求來賓進行多重要素驗證特別重要。</span><span class="sxs-lookup"><span data-stu-id="b630d-124">Since guest users may be using personal email accounts that don't adhere to any governance policies or best practices, it's especially important to require multi-factor authentication for guests.</span></span> <span data-ttu-id="b630d-125">若來賓使用者的使用者名稱和密碼遭竊，要求第二個驗證要素能大幅降低未知人員存取網站和檔案的機會。</span><span class="sxs-lookup"><span data-stu-id="b630d-125">If a guest user's username and password is stolen, requiring a second factor of authentication greatly reduces the chances of unknown parties gaining access to your sites and files.</span></span>

<span data-ttu-id="b630d-126">在此範例中，我們將使用 Azure Active Directory 中的條件式存取原則為來賓設定多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="b630d-126">In this example, we'll set up multi-factor authentication for guests by using a conditional access policy in Azure Active Directory.</span></span>

<span data-ttu-id="b630d-127">若要為來賓設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="b630d-127">To set up multi-factor authentication for guests</span></span>
1. <span data-ttu-id="b630d-128">在 Microsoft Azure 中，搜尋*條件式存取*。</span><span class="sxs-lookup"><span data-stu-id="b630d-128">In Microsoft Azure, search for *Conditional access*.</span></span>
2. <span data-ttu-id="b630d-129">在 **[條件式存取原則]** 刀鋒視窗中，按一下 **[新增原則]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-129">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="b630d-130">在 **[名稱]** 欄位中，輸入*來賓 MFA*。</span><span class="sxs-lookup"><span data-stu-id="b630d-130">In the **Name** field, type *Guest MFA*.</span></span>
4. <span data-ttu-id="b630d-131">在 **[指派]** 底下，按一下 **[使用者和群組]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-131">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="b630d-132">在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，然後選取 **[所有來賓和外部使用者]** 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-132">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box, and then click **Done**.</span></span>
4. <span data-ttu-id="b630d-133">在 **[存取控制]** 底下，按一下 **[授與]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-133">Under **Access controls**, click **Grant**.</span></span>
5. <span data-ttu-id="b630d-134">在 **[授與]** 刀鋒視窗中，選取 **[需要多重要素驗證]** 核取方塊，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-134">On the **Grant** blade, select the **Require multi-factor authentication** check box, and then click **Select**.</span></span>
6. <span data-ttu-id="b630d-135">在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-135">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="b630d-136">現在，來賓必須先註冊多重要素驗證，才能存取共用的內容、網站或小組。</span><span class="sxs-lookup"><span data-stu-id="b630d-136">Now, guest will be required to enroll in multi-factor authentication before they can access shared content, sites, or teams.</span></span>

### <a name="more-information"></a><span data-ttu-id="b630d-137">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b630d-137">More information</span></span>

[<span data-ttu-id="b630d-138">規劃雲端式 Azure Multi-Factor Authentication 部署</span><span class="sxs-lookup"><span data-stu-id="b630d-138">Planning a cloud-based Azure Multi-Factor Authentication deployment</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a><span data-ttu-id="b630d-139">為來賓設定使用規定</span><span class="sxs-lookup"><span data-stu-id="b630d-139">Set up a terms of use for guests</span></span>

<span data-ttu-id="b630d-140">通常來賓使用者可能沒有與貴組織簽署保密合約或其他法律合約。</span><span class="sxs-lookup"><span data-stu-id="b630d-140">Often times guest users may not have signed non-disclosure agreements or other legal agreements with your organization.</span></span> <span data-ttu-id="b630d-141">在來賓存取與他們共用的檔案之前，您可以要求來賓同意使用規定。</span><span class="sxs-lookup"><span data-stu-id="b630d-141">You can require guests to agree to a terms of use before accessing files that are shared with them.</span></span> <span data-ttu-id="b630d-142">使用規定可在來賓首次嘗試存取共用檔案或網站時顯示。</span><span class="sxs-lookup"><span data-stu-id="b630d-142">The terms of use can be displayed the first time they attempt to access a shared file or site.</span></span>

<span data-ttu-id="b630d-143">若要建立使用規定，您必須先在 Word 或其他撰寫程式建立文件，然後將文件儲存為 .pdf 檔案。</span><span class="sxs-lookup"><span data-stu-id="b630d-143">To create a terms of use, you first need to create the document in Word or another authoring program, and then save it as a .pdf file.</span></span> <span data-ttu-id="b630d-144">然後便能將此檔案上傳到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="b630d-144">This file can then be uploaded to Azure AD.</span></span>

<span data-ttu-id="b630d-145">若要建立 Azure AD 使用規定</span><span class="sxs-lookup"><span data-stu-id="b630d-145">To create an Azure AD terms of use</span></span>
1. <span data-ttu-id="b630d-146">以全域管理員、安全性系統管理員或條件式存取系統管理員的身分登入 Azure。</span><span class="sxs-lookup"><span data-stu-id="b630d-146">Sign in to Azure as a Global Administrator, Security Administrator, or Conditional Access Administrator.</span></span>
2. <span data-ttu-id="b630d-147">瀏覽至 [[使用規定]](https://aka.ms/catou)。</span><span class="sxs-lookup"><span data-stu-id="b630d-147">Navigate to [Terms of use](https://aka.ms/catou).</span></span>
3. <span data-ttu-id="b630d-148">按一下 **[新增規定]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-148">Click **New terms**.</span></span></br>
   <span data-ttu-id="b630d-149">![Azure AD 新使用規定設定的螢幕擷取畫面](../media/azure-ad-guest-terms-of-use.png)</span><span class="sxs-lookup"><span data-stu-id="b630d-149">![Screenshot of Azure AD new terms of use settings](../media/azure-ad-guest-terms-of-use.png)</span></span>
4. <span data-ttu-id="b630d-150">在 **[名稱]** 和 **[顯示名稱]** 方塊中，輸入*來賓使用規定*。</span><span class="sxs-lookup"><span data-stu-id="b630d-150">In the **Name** and **Display name** boxes, type *Guest terms of use*.</span></span>
6. <span data-ttu-id="b630d-151">在**使用規定文件**，瀏覽及選取您建立的 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="b630d-151">For **Terms of use document**, browse to the pdf file that you created and select it.</span></span>
7. <span data-ttu-id="b630d-152">選取使用規定文件的語言。</span><span class="sxs-lookup"><span data-stu-id="b630d-152">Select the language for your terms of use document.</span></span>
8. <span data-ttu-id="b630d-153">將 **[要求使用者展開使用規定]** 設為 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-153">Set **Require users to expand the terms of use** to **On**.</span></span>
9. <span data-ttu-id="b630d-154">在 **[條件式存取]** 底下的 **[強制使用條件式存取原則範本]** 清單中，選擇 **[稍後建立條件式存取原則]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-154">Under **Conditional Access**, in the **Enforce with Conditional Access policy template** list choose **Create conditional access policy later**.</span></span>
10. <span data-ttu-id="b630d-155">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-155">Click **Create**.</span></span>

<span data-ttu-id="b630d-156">建立使用規定後，下一個步驟是建立條件式存取原則，以顯示來賓使用者的使用規定。</span><span class="sxs-lookup"><span data-stu-id="b630d-156">Once you've created the terms of use, the next step is to create a conditional access policy that displays the terms of use to guest users.</span></span>

<span data-ttu-id="b630d-157">若要建立條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="b630d-157">To create a conditional access policy</span></span>
1. <span data-ttu-id="b630d-158">在 Microsoft Azure 中，搜尋*條件式存取*。</span><span class="sxs-lookup"><span data-stu-id="b630d-158">In Microsoft Azure, search for *Conditional access*.</span></span>
2. <span data-ttu-id="b630d-159">在 **[條件式存取原則]** 刀鋒視窗中，按一下 **[新增原則]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-159">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="b630d-160">在 **[名稱]** 方塊中，輸入*來賓使用者的使用規定原則*。</span><span class="sxs-lookup"><span data-stu-id="b630d-160">In the **Name** box, type *Guest user terms of use policy*.</span></span>
4. <span data-ttu-id="b630d-161">在 **[指派]** 底下，按一下 **[使用者和群組]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-161">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="b630d-162">在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，然後選取 **[所有來賓和外部使用者]** 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-162">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box, and then click **Done**.</span></span>
6. <span data-ttu-id="b630d-163">在 **[指派]** 底下，按一下**雲端應用程式或動作**。</span><span class="sxs-lookup"><span data-stu-id="b630d-163">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="b630d-164">在 **[包含]** 索引標籤上，選取 **[選取應用程式]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-164">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="b630d-165">在 **[選取]** 刀鋒視窗中，選取 **Microsoft Teams**、**Office 365 SharePoint Online** 和 **Outlook Groups**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-165">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="b630d-166">在 **[雲端應用程式或動作]** 刀鋒視窗中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-166">On the **Cloud apps or actions** blade, click **Done**.</span></span>
10. <span data-ttu-id="b630d-167">在 **[存取控制]** 底下，按一下 **[授與]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-167">Under **Access controls**, click **Grant**.</span></span>
11. <span data-ttu-id="b630d-168">在 **[授與]** 刀鋒視窗中，選取 **[來賓使用規定]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-168">On the **Grant** blade, select **Guest terms of use**, and then click **Select**.</span></span>
12. <span data-ttu-id="b630d-169">在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-169">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="b630d-170">現在，來賓使用者首次嘗試存取貴組織中的內容、小組或網站時，必須接受使用規定。</span><span class="sxs-lookup"><span data-stu-id="b630d-170">Now, the first time a guest user attempts to access content or a team or site in your organization, they will be required to accept the terms of use.</span></span>

### <a name="more-information"></a><span data-ttu-id="b630d-171">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b630d-171">More information</span></span>
[<span data-ttu-id="b630d-172">Azure Active Directory 使用規定</span><span class="sxs-lookup"><span data-stu-id="b630d-172">Azure Active Directory terms of use</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a><span data-ttu-id="b630d-173">設定來賓存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="b630d-173">Set up guest access reviews</span></span>

<span data-ttu-id="b630d-174">透過 Azure AD 中的存取權檢閱，您可以自動定期檢閱各小組和群組的使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="b630d-174">With access reviews in Azure AD, you can automate a periodic review of user access to various teams and groups.</span></span> <span data-ttu-id="b630d-175">透過特別要求來賓的存取權檢閱，您可以協助確保來賓使用者不會在非必要時持續存取貴組織的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="b630d-175">By requiring an access review for guests specifically, you can help ensure guest users do not retain access to your organization's sensitive information for longer than is necessary.</span></span>

<span data-ttu-id="b630d-176">存取權檢閱可組織為程式。</span><span class="sxs-lookup"><span data-stu-id="b630d-176">Access reviews can be organized into programs.</span></span> <span data-ttu-id="b630d-177">程式是一組類似的存取權檢閱，可用於組織存取權檢閱，以便進行報告和稽核。</span><span class="sxs-lookup"><span data-stu-id="b630d-177">A program is a grouping of similar access reviews that can be used to organize access reviews for reporting and auditing purposes.</span></span>

<span data-ttu-id="b630d-178">在此範例中，我們將建立來賓存取權檢閱程式。</span><span class="sxs-lookup"><span data-stu-id="b630d-178">In this example, we'll create a program for guest access reviews.</span></span>

<span data-ttu-id="b630d-179">若要建立程式</span><span class="sxs-lookup"><span data-stu-id="b630d-179">To create a program</span></span>
1. <span data-ttu-id="b630d-180">登入 Azure 入口網站，並開啟 [Identity Governance 頁面](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade)。</span><span class="sxs-lookup"><span data-stu-id="b630d-180">Sign in to the Azure portal and open the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade).</span></span>
2. <span data-ttu-id="b630d-181">按一下左方功能表中的 **[程式]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-181">In the left menu, click **Programs**</span></span>
3. <span data-ttu-id="b630d-182">按一下 **[新增程式]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-182">Click **New program**.</span></span>
4. <span data-ttu-id="b630d-183">在 **[名稱]** 方塊中，輸入*來賓存取權檢閱程式*。</span><span class="sxs-lookup"><span data-stu-id="b630d-183">In the **Name** box, type *Guest access review program*.</span></span>
5. <span data-ttu-id="b630d-184">在 **[描述]** 方塊中，輸入*用於來賓存取權檢閱的程式*。</span><span class="sxs-lookup"><span data-stu-id="b630d-184">In the **Description** box, type *Program for guest access reviews*.</span></span>
6. <span data-ttu-id="b630d-185">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-185">Click **Create**.</span></span>

<span data-ttu-id="b630d-186">程式建立後，我們就可以建立來賓存取權檢閱，並將其與程式建立關聯。</span><span class="sxs-lookup"><span data-stu-id="b630d-186">Once the program has been created, we can create a guest access review and associate it with the program.</span></span>

<span data-ttu-id="b630d-187">若要設定來賓使用者存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="b630d-187">To set up a guest user access review</span></span>
1. <span data-ttu-id="b630d-188">在 [Identity Governance 頁面](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade)的左側功能表中，按一下 **[存取權檢閱]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-188">On the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade), in the left menu, click **Access reviews**.</span></span>
2. <span data-ttu-id="b630d-189">按一下 **[新增存取權檢閱]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-189">Click **New access review**.</span></span></br>
   <span data-ttu-id="b630d-190">![Azure AD 存取權檢閱設定的螢幕擷取畫面](../media/azure-ad-create-access-review.png)</span><span class="sxs-lookup"><span data-stu-id="b630d-190">![Screenshot of Azure AD access review settings](../media/azure-ad-create-access-review.png)</span></span>
3. <span data-ttu-id="b630d-191">在 **[名稱]** 方塊中，輸入*每季來賓存取權檢閱*。</span><span class="sxs-lookup"><span data-stu-id="b630d-191">In the **Name** box, type *Quarterly guest access review*.</span></span>
4. <span data-ttu-id="b630d-192">在 **[頻率]** 選擇 **[每季]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-192">For **Frequency**, choose **Quarterly**.</span></span>
5. <span data-ttu-id="b630d-193">在 **[結束]** 選擇 **[永不]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-193">For **End**, choose **Never**.</span></span>
6. <span data-ttu-id="b630d-194">在 **[範圍]**，選擇 **[僅限來賓使用者]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-194">For **Scope**, choose **Guest users only**.</span></span>
7. <span data-ttu-id="b630d-195">按一下 **[群組]**，選取要包含在存取權檢閱中的群組，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-195">Click **Group**, select the groups that you want to include in the access review, and then click **Select**.</span></span>
8. <span data-ttu-id="b630d-196">按一下 **[程式]** 底下的 **[連結至程式]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-196">Under **Programs**, click **Link to program**.</span></span>
9. <span data-ttu-id="b630d-197">在 **[選取程式]** 刀鋒視窗中，選擇 **[來賓存取權檢閱程式]**</span><span class="sxs-lookup"><span data-stu-id="b630d-197">On the **Select a program** blade, choose **Guest access review program**</span></span>
10. <span data-ttu-id="b630d-198">按一下 **[開始]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-198">Click **Start**.</span></span>

<span data-ttu-id="b630d-199">系統會針對您指定的每個群組建立個別存取權檢閱。</span><span class="sxs-lookup"><span data-stu-id="b630d-199">A separate access review is created for each group that you specify.</span></span> <span data-ttu-id="b630d-200">每個群組的群組擁有者每季會收到電子郵件，以核准或拒絕來賓對其群組的存取權。</span><span class="sxs-lookup"><span data-stu-id="b630d-200">Group owners of each groups will be emailed quarterly to approve or deny guest access to their groups.</span></span>

<span data-ttu-id="b630d-201">請注意，來賓可取得小組或群組，或個別檔案和資料夾的存取權。</span><span class="sxs-lookup"><span data-stu-id="b630d-201">It's important to note that guests can be given access to teams or groups, or to individual files and folders.</span></span> <span data-ttu-id="b630d-202">取得檔案和資料夾存取權時，系統可能不會將來賓新增至任何特定群組。</span><span class="sxs-lookup"><span data-stu-id="b630d-202">When given access to files and folders, guests may not be added to any particular group.</span></span> <span data-ttu-id="b630d-203">如果您要對不屬於某小組或群組的來賓使用者執行存取權檢閱，您可以在 Azure AD 中建立動態群組以包含所有來賓，然後建立該群組的存取權檢閱。</span><span class="sxs-lookup"><span data-stu-id="b630d-203">If you want to do access reviews on guest users who don't belong to a team or group, you can create a dynamic group in Azure AD to contain all guests and then create an access review for that group.</span></span>

### <a name="more-information"></a><span data-ttu-id="b630d-204">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b630d-204">More information</span></span>
[<span data-ttu-id="b630d-205">使用 Azure AD 存取權檢閱來管理來賓存取權</span><span class="sxs-lookup"><span data-stu-id="b630d-205">Manage guest access with Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[<span data-ttu-id="b630d-206">在 Azure AD 存取權檢閱中建立群組或應用程式的存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="b630d-206">Create an access review of groups or applications in Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guest-users"></a><span data-ttu-id="b630d-207">為來賓使用者設定僅限網頁存取</span><span class="sxs-lookup"><span data-stu-id="b630d-207">Set up web-only access for guest users</span></span>

<span data-ttu-id="b630d-208">您可以要求來賓使用者僅使用網頁瀏覽器存取小組、網站和檔案，以縮小受攻擊面，並輕鬆進行管理。</span><span class="sxs-lookup"><span data-stu-id="b630d-208">You can reduce your attack surface and ease administration by requiring guest users to access your teams, sites, and files by using a web browser only.</span></span> <span data-ttu-id="b630d-209">Azure AD 條件式存取原則已設定完成。</span><span class="sxs-lookup"><span data-stu-id="b630d-209">This is done with an Azure AD conditional access policy.</span></span>

<span data-ttu-id="b630d-210">若要限制來賓僅使用網頁存取</span><span class="sxs-lookup"><span data-stu-id="b630d-210">To restrict guests to web-ony access</span></span>
1. <span data-ttu-id="b630d-211">在 Microsoft Azure 中，搜尋*條件式存取*。</span><span class="sxs-lookup"><span data-stu-id="b630d-211">In Microsoft Azure, search for *Conditional access*.</span></span>
2. <span data-ttu-id="b630d-212">在 **[條件式存取原則]** 刀鋒視窗中，按一下 **[新增原則]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-212">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="b630d-213">在 **[名稱]** 方塊中，輸入*來賓使用者瀏覽器存取*。</span><span class="sxs-lookup"><span data-stu-id="b630d-213">In the **Name** box, type *Guest user browser access*.</span></span>
4. <span data-ttu-id="b630d-214">在 **[指派]** 底下，按一下 **[使用者和群組]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-214">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="b630d-215">在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，然後選取 **[所有來賓和外部使用者]** 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-215">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box, and then click **Done**.</span></span>
6. <span data-ttu-id="b630d-216">在 **[指派]** 底下，按一下**雲端應用程式或動作**。</span><span class="sxs-lookup"><span data-stu-id="b630d-216">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="b630d-217">在 **[包含]** 索引標籤上，選取 **[選取應用程式]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-217">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="b630d-218">在 **[選取]** 刀鋒視窗中，選取 **Microsoft Teams**、**Office 365 SharePoint Online** 和 **Outlook Groups**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-218">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="b630d-219">在 **[雲端應用程式或動作]** 刀鋒視窗中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-219">On the **Cloud apps or actions** blade, click **Done**.</span></span>
10. <span data-ttu-id="b630d-220">按一下 **[指派]** 底下的 **[條件]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-220">Under **Assignments**, click **Conditions**.</span></span>
11. <span data-ttu-id="b630d-221">在 **[條件]** 刀鋒視窗中，按一下 **[用戶端應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-221">On the **Conditions** blade, click **Client apps**.</span></span>
12. <span data-ttu-id="b630d-222">在 **[用戶端應用程式]** 刀鋒視窗中，按一下 **[是]** 進行 **[設定]**，然後選取 **[行動裝置 App 及桌面用戶端]** 和 **[新式驗證用戶端]** 設定。</span><span class="sxs-lookup"><span data-stu-id="b630d-222">On the **Client apps** blade, click **Yes** for **Configure**, and then select the **Mobile apps and desktop clients** and **Modern authentication clients** settings.</span></span></br>
    <span data-ttu-id="b630d-223">![Azure AD 條件式存取用戶端應用程式設定的螢幕擷取畫面](../media/azure-ad-conditional-access-client-mobile.png)</span><span class="sxs-lookup"><span data-stu-id="b630d-223">![Screenshot of Azure AD conditional access client apps settings](../media/azure-ad-conditional-access-client-mobile.png)</span></span>
13. <span data-ttu-id="b630d-224">按一下 **[完成]**，然後在 **[條件]** 刀鋒視窗中，再按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-224">Click **Done**, and then on the **Conditions** blade, click **Done** again.</span></span>
14. <span data-ttu-id="b630d-225">在 **[存取控制]** 底下，按一下 **[授與]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-225">Under **Access controls**, click **Grant**.</span></span>
15. <span data-ttu-id="b630d-226">在 **[授與]** 刀鋒視窗中，選取 **[裝置需要標記為合規]** 和 **[需要已加入混合式 Azure AD 的裝置]**。 </span><span class="sxs-lookup"><span data-stu-id="b630d-226">On the **Grant** blade, select **Require device to be marked as compliant** and **Require Hybrid Azure AD joined device**.</span></span>
16. <span data-ttu-id="b630d-227">在 **[針對多個控制項]** 底下，選取 **[需要其中一個選取的控制項]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-227">Under **For multiple controls**, select **Require one of the selected controls**, and then click **Select**.</span></span>
17. <span data-ttu-id="b630d-228">在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-228">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

## <a name="configure-a-session-timeout-for-guest-users"></a><span data-ttu-id="b630d-229">設定來賓使用者的工作階段逾時</span><span class="sxs-lookup"><span data-stu-id="b630d-229">Configure a session timeout for guest users</span></span>

<span data-ttu-id="b630d-230">若來賓使用者的裝置不安全，要求來賓定期驗證可降低未知的使用者存取貴組織內容的可能性。</span><span class="sxs-lookup"><span data-stu-id="b630d-230">Requiring guests to authenticate on a regular basis can reduce the possibility of unknown users accessing your organization's content if a guest user's device isn't kept secure.</span></span> <span data-ttu-id="b630d-231">您可以在 Azure AD 中設定來賓使用者的工作階段逾時條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="b630d-231">You can configure a session timeout conditional access policy for guest users in Azure AD.</span></span>

<span data-ttu-id="b630d-232">若要設定來賓工作階段逾時原則</span><span class="sxs-lookup"><span data-stu-id="b630d-232">To configure a guest session timeout policy</span></span>
1. <span data-ttu-id="b630d-233">在 Microsoft Azure 中，搜尋*條件式存取*。</span><span class="sxs-lookup"><span data-stu-id="b630d-233">In Microsoft Azure, search for *Conditional access*.</span></span>
2. <span data-ttu-id="b630d-234">在 **[條件式存取原則]** 刀鋒視窗中，按一下 **[新增原則]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-234">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="b630d-235">在 **[名稱]** 方塊中，輸入*來賓工作階段逾時*。</span><span class="sxs-lookup"><span data-stu-id="b630d-235">In the **Name** box, type *Guest session timeout*.</span></span>
4. <span data-ttu-id="b630d-236">在 **[指派]** 底下，按一下 **[使用者和群組]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-236">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="b630d-237">在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，然後選取 **[所有來賓和外部使用者]** 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-237">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box, and then click **Done**.</span></span>
6. <span data-ttu-id="b630d-238">在 **[指派]** 底下，按一下**雲端應用程式或動作**。</span><span class="sxs-lookup"><span data-stu-id="b630d-238">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="b630d-239">在 **[包含]** 索引標籤上，選取 **[選取應用程式]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-239">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="b630d-240">在 **[選取]** 刀鋒視窗中，選取 **Microsoft Teams**、**Office 365 SharePoint Online** 和 **Outlook Groups**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-240">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="b630d-241">在 **[雲端應用程式或動作]** 刀鋒視窗中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-241">On the **Cloud apps or actions** blade, click **Done**.</span></span>
10. <span data-ttu-id="b630d-242">在 **[存取控制]** 底下，按一下 **[工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-242">Under **Access controls**, click **Session**.</span></span>
11. <span data-ttu-id="b630d-243">在 **[工作階段]** 刀鋒視窗中，選取 **[登入頻率]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-243">On the **Session** blade, select **Sign-in frequency**.</span></span>
12. <span data-ttu-id="b630d-244">選取 **1**，並在時間週期選取 **[天]** ，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-244">Select **1** and **Days** for the time period, and then click **Select**.</span></span>
13. <span data-ttu-id="b630d-245">在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-245">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

## <a name="create-sensitivity-labels"></a><span data-ttu-id="b630d-246">建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b630d-246">Create sensitivity labels</span></span>

<span data-ttu-id="b630d-247">您可透過多種方式使用敏感度標籤來分類及保護貴組織的資訊。</span><span class="sxs-lookup"><span data-stu-id="b630d-247">Sensitivity labels can be used in a variety of ways to classify and protect your organization's information.</span></span> <span data-ttu-id="b630d-248">在此範例中，我們將說明如何使用標籤來協助您管理來賓對共用檔案和資料夾的存取權。</span><span class="sxs-lookup"><span data-stu-id="b630d-248">In this example, we'll look at how labels can be used to help you manage guest access to shared files and folders.</span></span>

<span data-ttu-id="b630d-249">首先，我們會在 Microsoft 365 合規性中心建立三個敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="b630d-249">First, we'll create three sensitivity labels in the Microsoft 365 Compliance Center:</span></span>

- <span data-ttu-id="b630d-250">一般</span><span class="sxs-lookup"><span data-stu-id="b630d-250">General</span></span>
- <span data-ttu-id="b630d-251">敏感度</span><span class="sxs-lookup"><span data-stu-id="b630d-251">sensitive</span></span>
- <span data-ttu-id="b630d-252">高敏感度</span><span class="sxs-lookup"><span data-stu-id="b630d-252">Highly sensitive</span></span>

<span data-ttu-id="b630d-253">使用下列程序建立 *[一般]* 和 *[敏感度]* 標籤。</span><span class="sxs-lookup"><span data-stu-id="b630d-253">Use the following procedure to create the *General* and *sensitive* labels.</span></span>

<span data-ttu-id="b630d-254">若要建立分類標籤 ([一般] 和 [敏感度])</span><span class="sxs-lookup"><span data-stu-id="b630d-254">To create a classification label (General and sensitive)</span></span>
1. <span data-ttu-id="b630d-255">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)的左側瀏覽窗格中，展開 **[分類]**，然後按一下 **[敏感度標籤]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-255">In the [Microsoft 365 Compliance Center](https://compliance.microsoft.com), in the left navigation, expand **Classification**, and then click **Sensitivity labels**.</span></span>
2. <span data-ttu-id="b630d-256">按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b630d-256">Click **Create a label**.</span></span>
3. <span data-ttu-id="b630d-257">在 **[標籤名稱]** 中，輸入 *[一般]* 或 *[敏感度]*。</span><span class="sxs-lookup"><span data-stu-id="b630d-257">In **Label name**, type *General* or *sensitive*.</span></span>
4. <span data-ttu-id="b630d-258">在 **[工具提示]** 中，輸入*可與員工、來賓和合作夥伴共用的一般資訊*，或輸入*敏感度資訊，只與員工和授權來賓共用*，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-258">In **Tooltip**, type *General information that can be shared with employees, guests, and partners* or *sensitive information. Share only with employees and authorized guests*, and then click **Next**.</span></span>
5. <span data-ttu-id="b630d-259">將加密**關閉**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-259">Leave encryption **Off** and click **Next**.</span></span>
6. <span data-ttu-id="b630d-260">將內容標記**關閉**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-260">Leave content marking **Off** and click **Next**.</span></span>
7. <span data-ttu-id="b630d-261">將端點資料外洩防護**關閉**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-261">Leave endpoint data loss prevention **Off** and click **Next**.</span></span>
8. <span data-ttu-id="b630d-262">將自動標籤**關閉**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-262">Leave auto labeling **Off** and click **Next**.</span></span>
9. <span data-ttu-id="b630d-263">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b630d-263">Click **Create**.</span></span>

<span data-ttu-id="b630d-264">我們可以使用 *[高敏感度]* 標籤在文件上自動加上浮水印與標籤。</span><span class="sxs-lookup"><span data-stu-id="b630d-264">With the *Highly sensitive* label, we'll add automatic watermarking of documents with the label.</span></span>

<span data-ttu-id="b630d-265">若要建立分類標籤 (高敏感度)</span><span class="sxs-lookup"><span data-stu-id="b630d-265">To create a classification label (Highly sensitive)</span></span>
1. <span data-ttu-id="b630d-266">按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b630d-266">Click **Create a label**.</span></span>
2. <span data-ttu-id="b630d-267">在 **[標籤名稱]** 中，輸入 *[高度敏感度]*。</span><span class="sxs-lookup"><span data-stu-id="b630d-267">In **Label name**, type *Highly sensitive*.</span></span>
3. <span data-ttu-id="b630d-268">在 **[工具提示]** 中，輸入*高敏感度資訊，請勿與來賓共用*，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-268">In **Tooltip**, type *Highly sensitive information. Do not share with guests*, and then click **Next**.</span></span>
4. <span data-ttu-id="b630d-269">將加密**關閉**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-269">Leave encryption **Off** and click **Next**.</span></span>
5. <span data-ttu-id="b630d-270">將內容標記**開啟**，選取 **[新增頁首]** 核取方塊，然後按一下 **[自訂文字]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-270">Turn content marking **On**, select the **Add a header** check box, and then click **Customize text**.</span></span>
6. <span data-ttu-id="b630d-271">在頁首文字輸入*高敏感度*，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-271">Type *Highly sensitive* for the header text and click **Save**.</span></span>
7. <span data-ttu-id="b630d-272">在**內容標記**頁面上，將內容標記**開啟**。</span><span class="sxs-lookup"><span data-stu-id="b630d-272">On the **Content marking** page, turn content marking **On**.</span></span>
8. <span data-ttu-id="b630d-273">選取 **[新增浮水印]** 核取方塊，然後按一下 **[自訂文字]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-273">Select the **Add a watermark** check box, and then click **Customize text**.</span></span>
9. <span data-ttu-id="b630d-274">在**浮水印文字**輸入*高敏感度*。</span><span class="sxs-lookup"><span data-stu-id="b630d-274">For **Watermark text**, type *Highly sensitive*.</span></span>
10. <span data-ttu-id="b630d-275">在**字型大小**輸入 *24*，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-275">Type *24* for **Font size**, and then click **Save**.</span></span>
11. <span data-ttu-id="b630d-276">在**內容標記**頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-276">On the **Content marking** page, click **Next**.</span></span>
12. <span data-ttu-id="b630d-277">將端點資料外洩防護**關閉**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-277">Leave endpoint data loss prevention **Off** and click **Next**.</span></span>
13. <span data-ttu-id="b630d-278">將自動標籤**關閉**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-278">Leave auto labeling **Off** and click **Next**.</span></span>
14. <span data-ttu-id="b630d-279">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-279">Click **Create**.</span></span>

![Microsoft 365 合規性中心敏感度標籤的螢幕擷取畫面](../media/microsoft-365-sharing-sensitivity-labels.png)

<span data-ttu-id="b630d-281">建立標籤後，下一個步驟是發佈標籤。</span><span class="sxs-lookup"><span data-stu-id="b630d-281">Once you've created the labels, the next step is to publish them.</span></span> 

<span data-ttu-id="b630d-282">若要發佈標籤</span><span class="sxs-lookup"><span data-stu-id="b630d-282">To publish labels</span></span>
1. <span data-ttu-id="b630d-283">在**敏感度標籤**頁面上，按一下 **[發佈標籤]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-283">On the **Sensitivity labels** page, click **Publish labels**.</span></span>
2. <span data-ttu-id="b630d-284">按一下 **[選擇要發佈的標籤]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-284">Click **Choose labels to publish**.</span></span>
3. <span data-ttu-id="b630d-285">按一下 **[新增]**，選取您所建立的標籤，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-285">Click **Add**, select the labels that you created, and then click **Add**.</span></span>
4. <span data-ttu-id="b630d-286">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-286">Click **Done**.</span></span>
5. <span data-ttu-id="b630d-287">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-287">Click **Next**.</span></span>
6. <span data-ttu-id="b630d-288">將使用者和群組設為**全部**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-288">Leave the users and groups set to **All** and click **Next**.</span></span>
7. <span data-ttu-id="b630d-289">在 **[預設將此標籤套用到文件和電子郵件]** 清單中，選擇 **[一般]**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-289">In the **Apply this label by default to documents and email** list, choose **General**, and then click **Next**.</span></span>
8. <span data-ttu-id="b630d-290">在**原則設定**頁面上的名稱輸入*文件敏感度*，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-290">On the **Policy settings** page, type *Document sensitivity* for the name, and then click **Next**.</span></span>
9. <span data-ttu-id="b630d-291">按一下 **[發佈]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-291">Click **Publish**.</span></span>

<span data-ttu-id="b630d-292">發佈標籤後，Office 桌面 App 的使用者便能使用標籤。</span><span class="sxs-lookup"><span data-stu-id="b630d-292">With the labels published, they're available to users of Office desktop apps.</span></span> <span data-ttu-id="b630d-293">當使用者套用 **[高敏感度]** 標籤時，浮水印會自動新增到文件。</span><span class="sxs-lookup"><span data-stu-id="b630d-293">When users apply the **Highly sensitive** label, a watermark is automatically added to the document.</span></span>

### <a name="more-information"></a><span data-ttu-id="b630d-294">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b630d-294">More information</span></span>
[<span data-ttu-id="b630d-295">敏感度標籤概觀</span><span class="sxs-lookup"><span data-stu-id="b630d-295">Overview of sensitivity labels</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a><span data-ttu-id="b630d-296">建立高敏感度專案的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="b630d-296">Create a sensitive information type for a highly sensitive project</span></span>

<span data-ttu-id="b630d-297">敏感性資訊類型是預先定義的字串，可用於原則工作流程中，以強制執行法規遵循需求。</span><span class="sxs-lookup"><span data-stu-id="b630d-297">Sensitive information types are predefined strings that can be used in policy workflows to enforce compliance requirements.</span></span> <span data-ttu-id="b630d-298">Microsoft 365 合規性中心隨附超過 100 種敏感性資訊類型，包括駕照編號、信用卡號、銀行帳號等。</span><span class="sxs-lookup"><span data-stu-id="b630d-298">The Microsoft 365 Compliance Center comes with over one hundred sensitive information types, including driver's license numbers, credit card numbers, bank account numbers, etc.</span></span>

<span data-ttu-id="b630d-299">您可以建立自訂敏感性資訊類型以協助管理貴組織的特定內容。</span><span class="sxs-lookup"><span data-stu-id="b630d-299">You can create custom sensitive information types to help manage content specific to your organization.</span></span> <span data-ttu-id="b630d-300">在此範例中，我們將建立高敏感度專案的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b630d-300">In this example, we'll create a custom sensitive information type for a highly sensitive project.</span></span> <span data-ttu-id="b630d-301">然後，我們可以使用此敏感性資訊類型自動套用分類標籤。</span><span class="sxs-lookup"><span data-stu-id="b630d-301">We can then use this sensitive information type to automatically apply a classification label.</span></span>

<span data-ttu-id="b630d-302">若要建立敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="b630d-302">To create a sensitive information type</span></span>
1. <span data-ttu-id="b630d-303">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)的左側瀏覽窗格中，展開 **[分類]**，然後按一下 **[敏感性資訊類型]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-303">In the [Microsoft 365 Compliance Center](https://compliance.microsoft.com), in the left navigation, expand **Classification**, and then click **Sensitive info types**.</span></span>
2. <span data-ttu-id="b630d-304">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-304">Click **Create**.</span></span>
3. <span data-ttu-id="b630d-305">在**名稱**和**描述**輸入 **Saturn 專案**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-305">For **Name** and **Description**, type **Project Saturn**, and then click **Next**.</span></span>
4. <span data-ttu-id="b630d-306">按一下 **[新增元素]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-306">Click **Add an element**.</span></span>
5. <span data-ttu-id="b630d-307">在 **[偵測內容包含]** 清單中，選取 **[關鍵字]**，然後在關鍵字方塊中輸入 *Saturn 專案*。</span><span class="sxs-lookup"><span data-stu-id="b630d-307">On the **Detect content containing** list, select **Keywords**, and then type *Project Saturn* in the keyword box.</span></span>
6. <span data-ttu-id="b630d-308">按一下 **[下一步]**，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-308">Click **Next**, and then click **Finish**.</span></span>
7. <span data-ttu-id="b630d-309">若系統詢問您是否要測試敏感性資訊類型，請按一下 **[否]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-309">If asked if you would like to test the sensitive information type, click **No**.</span></span>

### <a name="more-information"></a><span data-ttu-id="b630d-310">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b630d-310">More information</span></span>
[<span data-ttu-id="b630d-311">自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="b630d-311">Custom sensitive information types</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-a-policy-to-assign-a-label-based-on-a-sensitive-information-type"></a><span data-ttu-id="b630d-312">建立原則以根據敏感性資訊類型指派標籤</span><span class="sxs-lookup"><span data-stu-id="b630d-312">Create a policy to assign a label based on a sensitive information type</span></span>

<span data-ttu-id="b630d-313">建立敏感性資訊類型後，我們可以在 Microsoft Cloud App Security 中建立檔案原則，以將 *[高敏感度]* 標籤自動套用至包含 *Saturn 專案*字串的文件。</span><span class="sxs-lookup"><span data-stu-id="b630d-313">Once the sensitive information type is created, we can create a file policy in Microsoft Cloud App Security to apply the *Highly sensitive* label to documents that contain the *Project Saturn* string automatically.</span></span>

> [!NOTE]
> <span data-ttu-id="b630d-314">有複寫程序可讓敏感度標籤在 Cloud App Security 中使用。</span><span class="sxs-lookup"><span data-stu-id="b630d-314">There is a replication process that makes sensitivity labels available in Cloud App Security.</span></span> <span data-ttu-id="b630d-315">您可能無法立即查看原則可用的標籤。</span><span class="sxs-lookup"><span data-stu-id="b630d-315">You may not see the label available for a policy right away.</span></span>

<span data-ttu-id="b630d-316">若要建立以敏感性資訊類型為基礎的檔案原則</span><span class="sxs-lookup"><span data-stu-id="b630d-316">To create a sensitive information type-based file policy</span></span>
1. <span data-ttu-id="b630d-317">開啟 [Microsoft Cloud App Security](https://portal.cloudappsecurity.com)。</span><span class="sxs-lookup"><span data-stu-id="b630d-317">Open [Microsoft Cloud App Security](https://portal.cloudappsecurity.com).</span></span>
2. <span data-ttu-id="b630d-318">在左側瀏覽窗格中，展開 **[控制]**，然後按一下 **[原則]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-318">In the left navigation, expand **Control**, and then click **Policies**.</span></span>
3. <span data-ttu-id="b630d-319">按一下 **[建立原則]**，然後選擇 **[檔案原則]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-319">Click **Create policy**, and then choose **File policy**.</span></span>
4. <span data-ttu-id="b630d-320">在**原則名稱**中輸入 *Saturn 專案標籤*。</span><span class="sxs-lookup"><span data-stu-id="b630d-320">For **Policy name**, type *Project Saturn labeling*.</span></span>
5. <span data-ttu-id="b630d-321">在 **[為套用這項原則的檔案建立篩選]** 底下，按兩下 X 以刪除預設篩選。</span><span class="sxs-lookup"><span data-stu-id="b630d-321">Under **Create a filter for the files this policy will act on**, click X twice to delete the default filters.</span></span>
7. <span data-ttu-id="b630d-322">在 **[選取篩選器]** 清單中，選擇 **[應用程式]**，然後從 **[選取應用程式...]** 清單選取 **[Microsoft SharePoint Online]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-322">In the **Select a filter** list, choose **App**, and then select **Microsoft SharePoint Online** from the **Select apps...** list.</span></span>
8. <span data-ttu-id="b630d-323">在 **[檢查方法]** 底下，選擇 **[資料分類服務]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-323">Under **Inspection method**, choose **Data classification service**.</span></span>
9. <span data-ttu-id="b630d-324">在 **[選擇檢查類型]** 清單中，選擇 **[敏感性資訊類型]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-324">On the **Choose inspection type** list, choose **Sensitive information type**.</span></span>
10. <span data-ttu-id="b630d-325">搜尋並選取 *Saturn 專案*敏感度標籤，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-325">Search for and select the *Project Saturn* sensitivity label, and then click **Done**.</span></span></br>
   <span data-ttu-id="b630d-326">![Cloud App Security 檢查方法設定的螢幕擷取畫面](../media/mcas-sensitive-info-type-project-saturn.png)</span><span class="sxs-lookup"><span data-stu-id="b630d-326">![Screenshot of Cloud App Security inspection method settings](../media/mcas-sensitive-info-type-project-saturn.png)</span></span>
11. <span data-ttu-id="b630d-327">在 **[控管]** 底下，展開 **[Microsoft SharePoint Online]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-327">Under **Governance**, expand **Microsoft SharePoint Online**.</span></span>
12. <span data-ttu-id="b630d-328">選取 **[套用分類標籤]** 核取方塊，然後選取 **[高敏感度]** 標籤。</span><span class="sxs-lookup"><span data-stu-id="b630d-328">Select the **Apply classification label** check box and select the **Highly sensitive** label.</span></span>
13. <span data-ttu-id="b630d-329">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b630d-329">Click **Create**.</span></span>

<span data-ttu-id="b630d-330">建立原則後，當使用者在文件中輸入「Saturn 專案」時，Cloud App Security 會在掃描檔案時自動套用 *[高敏感度]* 標籤。</span><span class="sxs-lookup"><span data-stu-id="b630d-330">With the policy in place, when a user types "Project Saturn" into a document, Cloud App Security will automatically apply the *Highly sensitive* label when it scans the file.</span></span>

### <a name="more-information"></a><span data-ttu-id="b630d-331">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b630d-331">More information</span></span>
[<span data-ttu-id="b630d-332">檔案原則</span><span class="sxs-lookup"><span data-stu-id="b630d-332">File policies</span></span>](https://docs.microsoft.com/cloud-app-security/data-protection-policies)

## <a name="create-a-policy-to-remove-guest-access-to-highly-sensitive-files"></a><span data-ttu-id="b630d-333">建立原則以移除高敏感度檔案的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="b630d-333">Create a policy to remove guest access to highly sensitive files</span></span>

<span data-ttu-id="b630d-334">在本文的範例中，具有 *[高敏感度]* 標籤的檔案不應與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="b630d-334">In the example in this article, files with the *Highly sensitive* label shouldn't be shared with guests.</span></span> <span data-ttu-id="b630d-335">我們可以在 Cloud App Security 中建立檔案原則，以自動移除具有該標籤的檔案。</span><span class="sxs-lookup"><span data-stu-id="b630d-335">We can create a file policy in Cloud App Security that automatically removes guest access from files with that label.</span></span>

<span data-ttu-id="b630d-336">請注意，這並不會妨礙使用者共用或重新共用這些檔案。</span><span class="sxs-lookup"><span data-stu-id="b630d-336">Note that this doesn't prevent users from sharing or re-sharing these files.</span></span> <span data-ttu-id="b630d-337">您仍得信任使用者遵循儲存在允許來賓共用之網站中的檔案控管原則。</span><span class="sxs-lookup"><span data-stu-id="b630d-337">You're still reliant on your users to follow your governance policies for files that are stored in sites that allow guest sharing.</span></span> <span data-ttu-id="b630d-338">不過，這是一個實用的工具，可讓您與來賓共用含敏感性資訊的檔案後，將來賓的檔案存取權移除。</span><span class="sxs-lookup"><span data-stu-id="b630d-338">However, this can be a useful tool for removing guest access from files that had sensitive information added to them after they were shared with guests.</span></span>

<span data-ttu-id="b630d-339">若要建立以標籤為基礎的檔案原則</span><span class="sxs-lookup"><span data-stu-id="b630d-339">To create a label-based file policy</span></span>
1. <span data-ttu-id="b630d-340">開啟 [Microsoft Cloud App Security](https://portal.cloudappsecurity.com)。</span><span class="sxs-lookup"><span data-stu-id="b630d-340">Open [Microsoft Cloud App Security](https://portal.cloudappsecurity.com).</span></span>
2. <span data-ttu-id="b630d-341">在左側瀏覽窗格中，展開 **[控制]**，然後按一下 **[原則]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-341">In the left navigation, expand **Control**, and then click **Policies**.</span></span>
3. <span data-ttu-id="b630d-342">按一下 **[建立原則]**，然後選擇 **[檔案原則]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-342">Click **Create policy**, and then choose **File policy**.</span></span>
4. <span data-ttu-id="b630d-343">在**原則名稱**中輸入 *Saturn 專案 - 移除來賓存取權*。</span><span class="sxs-lookup"><span data-stu-id="b630d-343">For **Policy name**, type *Project Saturn - remove guest access*.</span></span>
5. <span data-ttu-id="b630d-344">在 **[為套用這項原則的檔案建立篩選]** 底下，按兩下 X 以刪除預設篩選。</span><span class="sxs-lookup"><span data-stu-id="b630d-344">Under **Create a filter for the files this policy will act on**, click X twice to delete the default filters.</span></span>
6. <span data-ttu-id="b630d-345">在 **[選取篩選器]** 清單中，選擇 **[應用程式]**，然後從 **[選取應用程式...]** 清單選取 **[Microsoft SharePoint Online]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-345">In the **Select a filter** list, choose **App**, and then select **Microsoft SharePoint Online** from the **Select apps...** list.</span></span>
7. <span data-ttu-id="b630d-346">按一下 **[加入篩選]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-346">Click **Add a filter**.</span></span>
8. <span data-ttu-id="b630d-347">在 **[選取篩選器]** 清單中，選擇 **[分類標籤]**，然後從 **[選取篩選器...]** 清單選取 **[Azure 資訊保護]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-347">In the **Select a filter** list, choose **Classification label**, and then select **Azure Information Protection** from the **Select filter...** list.</span></span>
9. <span data-ttu-id="b630d-348">在 **[選取分類標籤]** 清單中，選取 **[高敏感度]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-348">In the **Select classification label** list, select **Highly sensitive**.</span></span></br>
   <span data-ttu-id="b630d-349">![Cloud App Security 原則篩選器設定的螢幕擷取畫面](../media/mcas-sharepoint-confidential-label-filter.png)</span><span class="sxs-lookup"><span data-stu-id="b630d-349">![Screenshot of Cloud App Security policy filter settings](../media/mcas-sharepoint-confidential-label-filter.png)</span></span>
10. <span data-ttu-id="b630d-350">在 **[控管]** 底下，展開 **[Microsoft SharePoint Online]**。</span><span class="sxs-lookup"><span data-stu-id="b630d-350">Under **Governance**, expand **Microsoft SharePoint Online**.</span></span>
11. <span data-ttu-id="b630d-351">選取 **[將原則對應摘要傳送給檔案擁有者]** 和 **[移除外部使用者]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b630d-351">Select the **Send policy-match digest to file owner** and **Remove external users** check boxes.</span></span>
12. <span data-ttu-id="b630d-352">在自訂通知訊息輸入*此檔案具有高敏感度，公司原則禁止與來賓共用此檔案*。</span><span class="sxs-lookup"><span data-stu-id="b630d-352">For the custom notification message, type *This file is highly sensitive. Company policy prohibits sharing it with guests*.</span></span>
13. <span data-ttu-id="b630d-353">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b630d-353">Click **Create**.</span></span>

<span data-ttu-id="b630d-354">請注意，此原則會移除使用*特定人員*連結共用的檔案存取權。</span><span class="sxs-lookup"><span data-stu-id="b630d-354">It's important to note, that this policy removes access for files shared using a *Specific people* link.</span></span> <span data-ttu-id="b630d-355">而不會移除未驗證 (*任何人*) 連結的存取權。</span><span class="sxs-lookup"><span data-stu-id="b630d-355">It doesn't remove access from unauthenticated (*Anyone*) links.</span></span> <span data-ttu-id="b630d-356">如果來賓是整個網站或小組的成員，也不會移除存取權。</span><span class="sxs-lookup"><span data-stu-id="b630d-356">It also doesn't remove access if the guest is a member of the site or team as a whole.</span></span> <span data-ttu-id="b630d-357">如果您計劃讓具有來賓成員的網站或團隊擁有高敏感度文件，請考慮[在 Teams 中使用私人頻道](https://support.office.com/article/60ef929a-4d68-418b-bf4f-5784db184ec9)，且只允許組織中的成員使用私人頻道。</span><span class="sxs-lookup"><span data-stu-id="b630d-357">If you plan to have highly sensitive documents in a site or team with guest members, consider using [private channels in Teams](https://support.office.com/article/60ef929a-4d68-418b-bf4f-5784db184ec9) and only allowing members of your organization in the private channels.</span></span>

## <a name="test-the-solution"></a><span data-ttu-id="b630d-358">測試解決方案</span><span class="sxs-lookup"><span data-stu-id="b630d-358">Test the solution</span></span>

<span data-ttu-id="b630d-359">若要測試本文所述的解決方案，請建立 Word 文件，並將該文件儲存到文件庫。</span><span class="sxs-lookup"><span data-stu-id="b630d-359">To test the solution described in this article, create a Word document and save it to a document library.</span></span> <span data-ttu-id="b630d-360">與來賓使用者共用檔案。</span><span class="sxs-lookup"><span data-stu-id="b630d-360">Share the file with a guest user.</span></span> <span data-ttu-id="b630d-361">來賓嘗試存取文件時，必須註冊多重要素驗證，然後接受使用規定。</span><span class="sxs-lookup"><span data-stu-id="b630d-361">When the guest attempts to access the document, they should be required to enroll in multi-factor authentication, and then accept the terms of use.</span></span>

<span data-ttu-id="b630d-362">一旦來賓取得文件的存取權，請在文件中輸入 *Saturn 專案*並儲存文件。</span><span class="sxs-lookup"><span data-stu-id="b630d-362">Once the guest has access to the document, type *Project Saturn* in the document and save it.</span></span> <span data-ttu-id="b630d-363">Cloud App Security 掃描文件時，系統應套用 *[高敏感度]* 標籤，來賓使用者便無法再存取該文件。</span><span class="sxs-lookup"><span data-stu-id="b630d-363">Once Cloud App Security scans the document, the *Highly sensitive* label should be applied and the guest user should no longer have access to it.</span></span>

<span data-ttu-id="b630d-364">您可以以各種組合來使用本文所述的工具，為貴組織建立具生產力且安全的來賓共用環境。</span><span class="sxs-lookup"><span data-stu-id="b630d-364">You can use the tools described in this article in various combinations to help create a productive but safe guest sharing environment for your organization.</span></span>

## <a name="additional-options"></a><span data-ttu-id="b630d-365">其他選項</span><span class="sxs-lookup"><span data-stu-id="b630d-365">Additional options</span></span>

<span data-ttu-id="b630d-366">Microsoft 365 和 Azure Active Directory 中有一些其他選項可以協助保護您的來賓共用環境。</span><span class="sxs-lookup"><span data-stu-id="b630d-366">There are some additional options in Microsoft 365 and Azure Active Directory that can help secure your guest sharing environment.</span></span>

- <span data-ttu-id="b630d-367">您可以建立允許或拒絕共用網域的清單，以限制要共用的使用者。</span><span class="sxs-lookup"><span data-stu-id="b630d-367">You can create a list of allowed or denied sharing domains to limit who users can share with.</span></span> <span data-ttu-id="b630d-368">如需詳細資訊，請參閱[依網域限制 SharePoint 和 OneDrive 內容的共用](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)和[允許或封鎖對特定組織的 B2B 使用者的邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="b630d-368">See [Restrict sharing of SharePoint and OneDrive content by domain](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) and [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) for more information.</span></span>
- <span data-ttu-id="b630d-369">您可以限制使用者可以連線到哪些其他 Azure Active Directory 租用戶。</span><span class="sxs-lookup"><span data-stu-id="b630d-369">You can limit which other Azure Active Directory tenants your users can connect to.</span></span> <span data-ttu-id="b630d-370">如需詳細資訊，請參閱[使用租用戶限制管理 SaaS 雲端應用程式的存取](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="b630d-370">See [Use tenant restrictions to manage access to SaaS cloud applications](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions) for information.</span></span>
- <span data-ttu-id="b630d-371">您可以建立受管理環境，讓合作夥伴能夠協助管理來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="b630d-371">You can create a managed environment where partners can help manage guest accounts.</span></span> <span data-ttu-id="b630d-372">如需詳細資訊，請參閱[建立 B2B 外部網路](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet)。</span><span class="sxs-lookup"><span data-stu-id="b630d-372">See [Create a B2B extranet with managed guests](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet) for information.</span></span>

## <a name="see-also"></a><span data-ttu-id="b630d-373">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b630d-373">See Also</span></span>

[<span data-ttu-id="b630d-374">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="b630d-374">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="b630d-375">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="b630d-375">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="b630d-376">使用受管理來賓建立 B2B 外部網路</span><span class="sxs-lookup"><span data-stu-id="b630d-376">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
