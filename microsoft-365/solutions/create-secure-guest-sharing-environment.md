---
title: 建立安全的來賓共用環境
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: 瞭解在 Microsoft 365 中建立安全的來賓共用環境的可用選項，提供來賓存取改善的共同作業。
ms.openlocfilehash: 28b2efba9f0c4ba17811a9871b05ab9f5a7a4839
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838670"
---
# <a name="create-a-secure-guest-sharing-environment"></a><span data-ttu-id="d5c08-103">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="d5c08-103">Create a secure guest sharing environment</span></span>

<span data-ttu-id="d5c08-104">在本文中，我們將逐一介紹用於在 Microsoft 365 中建立安全的來賓共用環境的各種選項。</span><span class="sxs-lookup"><span data-stu-id="d5c08-104">In this article, we'll walk through a variety of options for creating a secure guest sharing environment in Microsoft 365.</span></span> <span data-ttu-id="d5c08-105">下列是可讓您了解可用選項的一些範例。</span><span class="sxs-lookup"><span data-stu-id="d5c08-105">These are examples to give you an idea of the options available.</span></span> <span data-ttu-id="d5c08-106">您可以用不同的組合使用這些程序，以符合貴組織的安全性和合規性需求。</span><span class="sxs-lookup"><span data-stu-id="d5c08-106">You can use these procedures in different combinations to meet the security and compliance needs of your organization.</span></span>

<span data-ttu-id="d5c08-107">本文包括：</span><span class="sxs-lookup"><span data-stu-id="d5c08-107">This article includes:</span></span>

- <span data-ttu-id="d5c08-108">為來賓設定多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="d5c08-108">Setting up multi-factor authentication for guests.</span></span>
- <span data-ttu-id="d5c08-109">為來賓設定使用規定。</span><span class="sxs-lookup"><span data-stu-id="d5c08-109">Setting up a terms of use for guests.</span></span>
- <span data-ttu-id="d5c08-110">設定每季來賓存取權檢閱，以定期驗證來賓是否繼續需要小組和網站的使用權限。</span><span class="sxs-lookup"><span data-stu-id="d5c08-110">Setting up quarterly guest access reviews to periodically validate whether guests continue to need permissions to teams and sites.</span></span>
- <span data-ttu-id="d5c08-111">將來賓限制為僅限網頁存取未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="d5c08-111">Restricting guests to web-only access for unmanaged devices.</span></span>
- <span data-ttu-id="d5c08-112">設定工作階段逾時原則，以確保來賓每天進行驗證。</span><span class="sxs-lookup"><span data-stu-id="d5c08-112">Configuring a session timeout policy to ensure guests authenticate daily.</span></span>
- <span data-ttu-id="d5c08-113">為高敏感性專案建立敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="d5c08-113">Creating a sensitive information type for a highly sensitive project.</span></span>
- <span data-ttu-id="d5c08-114">自動將高敏感性標籤指派給包含敏感性資訊類型的文件。</span><span class="sxs-lookup"><span data-stu-id="d5c08-114">Automatically assigning a sensitivity label to documents that contain a sensitive information type.</span></span>
- <span data-ttu-id="d5c08-115">自動從具有敏感度標籤的檔案移除來賓存取。</span><span class="sxs-lookup"><span data-stu-id="d5c08-115">Automatically removing guest access from files with a sensitivity label.</span></span>

<span data-ttu-id="d5c08-116">本文中所述的部分選項要求來賓在 Azure Active Directory 中擁有帳戶。</span><span class="sxs-lookup"><span data-stu-id="d5c08-116">Some of the options discussed in this article require guests to have an account in Azure Active Directory.</span></span> <span data-ttu-id="d5c08-117">若要確保共用檔案和資料夾時目錄中包含來賓，請使用 [SharePoint 和 OneDrive 與 Azure AD B2B 整合 (預覽版)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-117">To ensure that guests are included in the directory when you share files and folders with them, use the [SharePoint and OneDrive integration with Azure AD B2B Preview](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="d5c08-118">請注意，我們不會在本文中討論啟用來賓共用設定。</span><span class="sxs-lookup"><span data-stu-id="d5c08-118">Note that we won't discuss enabling guest sharing settings in this article.</span></span> <span data-ttu-id="d5c08-119">如需針對不同案例啟用來賓共用的詳細資訊，請參閱[與組織外部人員共同作業](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-119">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for details about enabling guest sharing for different scenarios.</span></span>

## <a name="set-up-multi-factor-authentication-for-guests"></a><span data-ttu-id="d5c08-120">為來賓設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="d5c08-120">Set up multi-factor authentication for guests</span></span>

<span data-ttu-id="d5c08-121">多重要素驗證可大幅降低帳戶遭入侵的機會。</span><span class="sxs-lookup"><span data-stu-id="d5c08-121">Multi-factor authentication greatly reduces the chances of an account being compromised.</span></span> <span data-ttu-id="d5c08-122">由於來賓可能使用不符合任何控管原則或最佳做法的個人電子郵件帳戶，因此要求來賓進行多重要數驗證特別重要。</span><span class="sxs-lookup"><span data-stu-id="d5c08-122">Since guests may be using personal email accounts that don't adhere to any governance policies or best practices, it's especially important to require multi-factor authentication for guests.</span></span> <span data-ttu-id="d5c08-123">若來賓的使用者名稱和密碼遭竊，要求第二個驗證要素能大幅降低未知人員存取網站和檔案的機會。</span><span class="sxs-lookup"><span data-stu-id="d5c08-123">If a guest's username and password is stolen, requiring a second factor of authentication greatly reduces the chances of unknown parties gaining access to your sites and files.</span></span>

<span data-ttu-id="d5c08-124">在此範例中，我們將使用 Azure Active Directory 中的條件式存取原則為來賓設定多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="d5c08-124">In this example, we'll set up multi-factor authentication for guests by using a conditional access policy in Azure Active Directory.</span></span>

<span data-ttu-id="d5c08-125">若要為來賓設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="d5c08-125">To set up multi-factor authentication for guests</span></span>

1. <span data-ttu-id="d5c08-126">移至 [[Azure 條件式存取原則]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-126">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d5c08-127">在 [條件式存取 | 原則 **]** 刀鋒視窗中，按一下 [新增原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-127">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="d5c08-128">在 [名稱 **]** 欄位中，輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="d5c08-128">In the **Name** field, type a name.</span></span>
4. <span data-ttu-id="d5c08-129">在 **[指派]** 底下，按一下 **[使用者和群組]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-129">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="d5c08-130">在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，選取 **[所有來賓和外部使用者]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5c08-130">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d5c08-131">在 **[指派]** 底下，按一下 **雲端應用程式或動作**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-131">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="d5c08-132">在 **雲端應用程式或動作** 刀鋒視窗中，選取 **[包含]** 索引標籤上的 **[所有雲端應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-132">On the **Cloud apps or actions** blade, select **All cloud apps** on the **Include** tab.</span></span>
8. <span data-ttu-id="d5c08-133">在 **[存取控制]** 底下，按一下 **[授與]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-133">Under **Access controls**, click **Grant**.</span></span>
9. <span data-ttu-id="d5c08-134">在 **[授與]** 刀鋒視窗中，選取 **[需要多重要素驗證]** 核取方塊，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-134">On the **Grant** blade, select the **Require multi-factor authentication** check box, and then click **Select**.</span></span>
10. <span data-ttu-id="d5c08-135">在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-135">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="d5c08-136">現在，來賓必須先註冊多重要素驗證，才能存取共用的內容、網站或小組。</span><span class="sxs-lookup"><span data-stu-id="d5c08-136">Now, guest will be required to enroll in multi-factor authentication before they can access shared content, sites, or teams.</span></span>

### <a name="more-information"></a><span data-ttu-id="d5c08-137">其他資訊</span><span class="sxs-lookup"><span data-stu-id="d5c08-137">More information</span></span>

[<span data-ttu-id="d5c08-138">規劃 Azure AD Multi-Factor Authentication 部署</span><span class="sxs-lookup"><span data-stu-id="d5c08-138">Planning an Azure AD Multi-Factor Authentication deployment</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a><span data-ttu-id="d5c08-139">為來賓設定使用規定</span><span class="sxs-lookup"><span data-stu-id="d5c08-139">Set up a terms of use for guests</span></span>

<span data-ttu-id="d5c08-140">在某些情況下，來賓可能沒有與貴組織簽署保密合約或其他法律合約。</span><span class="sxs-lookup"><span data-stu-id="d5c08-140">In some situations guests may not have signed non-disclosure agreements or other legal agreements with your organization.</span></span> <span data-ttu-id="d5c08-141">在來賓存取與他們共用的檔案之前，您可以要求來賓同意使用規定。</span><span class="sxs-lookup"><span data-stu-id="d5c08-141">You can require guests to agree to a terms of use before accessing files that are shared with them.</span></span> <span data-ttu-id="d5c08-142">使用規定可在來賓首次嘗試存取共用檔案或網站時顯示。</span><span class="sxs-lookup"><span data-stu-id="d5c08-142">The terms of use can be displayed the first time they attempt to access a shared file or site.</span></span>

<span data-ttu-id="d5c08-143">若要建立使用規定，您必須先在 Word 或其他撰寫程式建立文件，然後將文件儲存為 .pdf 檔案。</span><span class="sxs-lookup"><span data-stu-id="d5c08-143">To create a terms of use, you first need to create the document in Word or another authoring program, and then save it as a .pdf file.</span></span> <span data-ttu-id="d5c08-144">然後便能將此檔案上傳到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="d5c08-144">This file can then be uploaded to Azure AD.</span></span>

<span data-ttu-id="d5c08-145">若要建立 Azure AD 使用規定</span><span class="sxs-lookup"><span data-stu-id="d5c08-145">To create an Azure AD terms of use</span></span>

1. <span data-ttu-id="d5c08-146">以全域管理員、安全性系統管理員或條件式存取系統管理員的身分登入 Azure。</span><span class="sxs-lookup"><span data-stu-id="d5c08-146">Sign in to Azure as a Global Administrator, Security Administrator, or Conditional Access Administrator.</span></span>
2. <span data-ttu-id="d5c08-147">瀏覽至 [[使用規定]](https://aka.ms/catou)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-147">Navigate to [Terms of use](https://aka.ms/catou).</span></span>
3. <span data-ttu-id="d5c08-148">按一下 **[新增規定]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-148">Click **New terms**.</span></span>

   ![Azure AD 新使用規定設定的螢幕擷取畫面](../media/azure-ad-guest-terms-of-use.png)

4. <span data-ttu-id="d5c08-150">輸入 [名稱 **]** 和 [顯示名稱 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-150">Type a **Name** and **Display name**.</span></span>
6. <span data-ttu-id="d5c08-151">在 **使用規定文件**，瀏覽及選取您建立的 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="d5c08-151">For **Terms of use document**, browse to the pdf file that you created and select it.</span></span>
7. <span data-ttu-id="d5c08-152">選取使用規定文件的語言。</span><span class="sxs-lookup"><span data-stu-id="d5c08-152">Select the language for your terms of use document.</span></span>
8. <span data-ttu-id="d5c08-153">將 **[要求使用者展開使用規定]** 設為 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-153">Set **Require users to expand the terms of use** to **On**.</span></span>
9. <span data-ttu-id="d5c08-154">在 **[條件式存取]** 底下的 **[強制使用條件式存取原則範本]** 清單中，選擇 **[稍後建立條件式存取原則]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-154">Under **Conditional Access**, in the **Enforce with Conditional Access policy template** list choose **Create conditional access policy later**.</span></span>
10. <span data-ttu-id="d5c08-155">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-155">Click **Create**.</span></span>

<span data-ttu-id="d5c08-156">建立使用規定後，下一個步驟是建立條件式存取原則，以顯示來賓的使用規定。</span><span class="sxs-lookup"><span data-stu-id="d5c08-156">Once you've created the terms of use, the next step is to create a conditional access policy that displays the terms of use to guests.</span></span>

<span data-ttu-id="d5c08-157">若要建立條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="d5c08-157">To create a conditional access policy</span></span>

1. <span data-ttu-id="d5c08-158">移至 [[Azure 條件式存取原則]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-158">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d5c08-159">在 [條件式存取 | 原則 **]** 刀鋒視窗中，按一下 [新增原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-159">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="d5c08-160">在 [名稱 **]** 方塊中，輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="d5c08-160">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="d5c08-161">在 **[指派]** 底下，按一下 **[使用者和群組]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-161">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="d5c08-162">在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，選取 **[所有來賓和外部使用者]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5c08-162">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d5c08-163">在 **[指派]** 底下，按一下 **雲端應用程式或動作**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-163">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="d5c08-164">在 **[包含]** 索引標籤上，選取 **[選取應用程式]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-164">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="d5c08-165">在 **[選取]** 刀鋒視窗中，選取 **Microsoft Teams**、**Office 365 SharePoint Online** 和 **Outlook Groups**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-165">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="d5c08-166">在 **[存取控制]** 底下，按一下 **[授與]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-166">Under **Access controls**, click **Grant**.</span></span>
10. <span data-ttu-id="d5c08-167">在 **[授與]** 刀鋒視窗中，選取 **[來賓使用規定]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-167">On the **Grant** blade, select **Guest terms of use**, and then click **Select**.</span></span>
11. <span data-ttu-id="d5c08-168">在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-168">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="d5c08-169">現在，在來賓首次嘗試存取貴組織中的內容、小組或網站時，必須接受使用規定。</span><span class="sxs-lookup"><span data-stu-id="d5c08-169">Now, the first time a guest attempts to access content or a team or site in your organization, they will be required to accept the terms of use.</span></span>

> [!NOTE]
> <span data-ttu-id="d5c08-170">使用條件式存取需要 Azure AD Premium P1 授權。</span><span class="sxs-lookup"><span data-stu-id="d5c08-170">Using Conditional Access requires an Azure AD Premium P1 license.</span></span> <span data-ttu-id="d5c08-171">如需詳細資訊，請參閱[何謂條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-171">For more information, see [What is Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="more-information"></a><span data-ttu-id="d5c08-172">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d5c08-172">More information</span></span>

[<span data-ttu-id="d5c08-173">Azure Active Directory 使用規定</span><span class="sxs-lookup"><span data-stu-id="d5c08-173">Azure Active Directory terms of use</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a><span data-ttu-id="d5c08-174">設定來賓存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="d5c08-174">Set up guest access reviews</span></span>

<span data-ttu-id="d5c08-175">透過 Azure AD 中的存取權檢閱，您可以自動定期檢閱各小組和群組的使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="d5c08-175">With access reviews in Azure AD, you can automate a periodic review of user access to various teams and groups.</span></span> <span data-ttu-id="d5c08-176">透過特別要求來賓的存取權檢閱，您可以協助確保來賓不會在非必要時持續存取貴組織的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="d5c08-176">By requiring an access review for guests specifically, you can help ensure guests do not retain access to your organization's sensitive information for longer than is necessary.</span></span>

<span data-ttu-id="d5c08-177">設定來賓存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="d5c08-177">To set up a guest access review</span></span>

1. <span data-ttu-id="d5c08-178">在 [Identity Governance 頁面](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade)的左側功能表中，按一下 **[存取權檢閱]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-178">On the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade), in the left menu, click **Access reviews**.</span></span>
2. <span data-ttu-id="d5c08-179">按一下 **[新增存取權檢閱]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-179">Click **New access review**.</span></span>
3. <span data-ttu-id="d5c08-180">選擇 **Teams + 群組** 選項。</span><span class="sxs-lookup"><span data-stu-id="d5c08-180">Choose the **Teams + Groups** option.</span></span>
4. <span data-ttu-id="d5c08-181">選擇 **來賓使用者的所有 Microsoft 365 群組** 選項。</span><span class="sxs-lookup"><span data-stu-id="d5c08-181">Choose the **All Microsoft 365 groups with guest users** option.</span></span> <span data-ttu-id="d5c08-182">如果您想要排除任何群組，請按一下 **[選取排除群組]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-182">Click **Select group(s) to exclude** if you want to exclude any groups.</span></span>
5. <span data-ttu-id="d5c08-183">選擇 **[僅來賓使用者]** 選項，然後按一下 **[下一步 : 檢閱]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-183">Choose the **Guest users only** option, and then click **Next: Reviews**.</span></span>
6. <span data-ttu-id="d5c08-184">在 **[選取檢閱者]** 下，選擇 **[群組擁有者]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-184">Under **Select reviewers**, choose **Group Owner(s)**.</span></span>
7. <span data-ttu-id="d5c08-185">按一下 **[選取遞補檢閱者]**，選擇誰是遞補檢閱者，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-185">Click **Select fallback reviewers**, choose who should be the fallback reviewers, and then click **Select**.</span></span>
8. <span data-ttu-id="d5c08-186">在 **[指定檢閱週期]** 下，選擇 **[季度]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-186">Under **Specify recurrence of review**, choose **Quarterly**.</span></span>
9. <span data-ttu-id="d5c08-187">選取開始日期和期間。</span><span class="sxs-lookup"><span data-stu-id="d5c08-187">Select a start date and duration.</span></span>
10. <span data-ttu-id="d5c08-188">針對 **[結束]**，選擇 **[永不]**，然後按一下 **[下一步 : 設定]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-188">For **End**, choose **Never**, and then click **Next: Settings**.</span></span>

    ![Azure AD 存取權檢閱索引標籤的螢幕擷取畫面](../media/azure-ad-create-access-review.png)

11. <span data-ttu-id="d5c08-190">在 **[設定]** 索引標籤上，檢閱符合您商務規則的設定。</span><span class="sxs-lookup"><span data-stu-id="d5c08-190">On the **Settings** tab, review the settings for compliance with your business rules.</span></span>

    ![Azure AD 存取權檢閱設定的螢幕擷取畫面](../media/azure-ad-create-access-review-settings.png)

12. <span data-ttu-id="d5c08-192">選取 **[下一步 : 檢閱 + 建立]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-192">Click **Next: Review + Create**.</span></span>
13. <span data-ttu-id="d5c08-193">輸入 **[檢閱名稱]** 並檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="d5c08-193">Type a **Review name** and review the settings.</span></span>
14. <span data-ttu-id="d5c08-194">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-194">Click **Create**.</span></span>

<span data-ttu-id="d5c08-195">請注意，來賓可取得小組或群組，或個別檔案和資料夾的存取權。</span><span class="sxs-lookup"><span data-stu-id="d5c08-195">It's important to note that guests can be given access to teams or groups, or to individual files and folders.</span></span> <span data-ttu-id="d5c08-196">取得檔案和資料夾存取權時，系統可能不會將來賓新增至任何特定群組。</span><span class="sxs-lookup"><span data-stu-id="d5c08-196">When given access to files and folders, guests may not be added to any particular group.</span></span> <span data-ttu-id="d5c08-197">如果您要對不屬於某小組或群組的來賓執行存取權檢閱，您可以在 Azure AD 中建立動態群組以包含所有來賓，然後建立該群組的存取權檢閱。</span><span class="sxs-lookup"><span data-stu-id="d5c08-197">If you want to do access reviews on guests who don't belong to a team or group, you can create a dynamic group in Azure AD to contain all guests and then create an access review for that group.</span></span> <span data-ttu-id="d5c08-198">網站擁有者也可以管理[網站的來賓到期日](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)</span><span class="sxs-lookup"><span data-stu-id="d5c08-198">Site owners can also manage [guest expiration for the site](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)</span></span>

### <a name="more-information"></a><span data-ttu-id="d5c08-199">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d5c08-199">More information</span></span>

[<span data-ttu-id="d5c08-200">使用 Azure AD 存取權檢閱來管理來賓存取權</span><span class="sxs-lookup"><span data-stu-id="d5c08-200">Manage guest access with Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[<span data-ttu-id="d5c08-201">在 Azure AD 存取權檢閱中建立群組或應用程式的存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="d5c08-201">Create an access review of groups or applications in Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guests"></a><span data-ttu-id="d5c08-202">為來賓設定僅限網頁存取</span><span class="sxs-lookup"><span data-stu-id="d5c08-202">Set up web-only access for guests</span></span>

<span data-ttu-id="d5c08-203">您可以要求來賓僅使用網頁瀏覽器存取小組、網站和檔案，以縮小受攻擊面，並輕鬆進行管理。</span><span class="sxs-lookup"><span data-stu-id="d5c08-203">You can reduce your attack surface and ease administration by requiring guests to access your teams, sites, and files by using a web browser only.</span></span>

<span data-ttu-id="d5c08-204">若為 Microsoft 365 群組和 Teams，這會使用 Azure AD 條件式存取原則來完成。</span><span class="sxs-lookup"><span data-stu-id="d5c08-204">For Microsoft 365 Groups and Teams, this is done with an Azure AD conditional access policy.</span></span> <span data-ttu-id="d5c08-205">若為 SharePoint，這會在 SharePoint 系統管理中心設定。</span><span class="sxs-lookup"><span data-stu-id="d5c08-205">For SharePoint, this is configured in the SharePoint admin center.</span></span> <span data-ttu-id="d5c08-206">(您也可以[使用敏感度標籤將來賓限制在僅限 Web 存取](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。)</span><span class="sxs-lookup"><span data-stu-id="d5c08-206">(You can also [use sensitivity labels to restrict guests to web-only access](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="d5c08-207">為群組和小組將來賓限制在僅限 Web 存取：</span><span class="sxs-lookup"><span data-stu-id="d5c08-207">To restrict guests to web-only access for Groups and Teams:</span></span>

1. <span data-ttu-id="d5c08-208">移至 [[Azure 條件式存取原則]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-208">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d5c08-209">在 [條件式存取 - 原則 **]** 刀鋒視窗上，按一下 [新增原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-209">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="d5c08-210">在 [名稱 **]** 方塊中，輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="d5c08-210">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="d5c08-211">在 **[指派]** 底下，按一下 **[使用者和群組]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-211">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="d5c08-212">在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，選取 **[所有來賓和外部使用者]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5c08-212">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d5c08-213">在 **[指派]** 底下，按一下 **雲端應用程式或動作**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-213">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="d5c08-214">在 **[包含]** 索引標籤上，選取 **[選取應用程式]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-214">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="d5c08-215">在 [選取 **]** 刀鋒視窗上，選取 **Microsoft Teams** 和 **Outlook Groups**，然後按一下 [選取 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-215">On the **Select** blade, select **Microsoft Teams** and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="d5c08-216">按一下 **[指派]** 底下的 **[條件]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-216">Under **Assignments**, click **Conditions**.</span></span>
10. <span data-ttu-id="d5c08-217">在 **[條件]** 刀鋒視窗中，按一下 **[用戶端應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-217">On the **Conditions** blade, click **Client apps**.</span></span>
11. <span data-ttu-id="d5c08-218">在 [用戶端應用程式 **]** 刀鋒視窗上，對 [設定 **]** 按一下 [是 **]**，然後選取 [行動裝置應用程式和桌面用戶端 **]**、[Exchange ActiveSync 用戶端 **]** 和 [其他用戶端 **]** 設定。</span><span class="sxs-lookup"><span data-stu-id="d5c08-218">On the **Client apps** blade, click **Yes** for **Configure**, and then select the **Mobile apps and desktop clients**, **Exchange ActiveSync clients**, and **Other clients** settings.</span></span> <span data-ttu-id="d5c08-219">清除 [瀏覽 **]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5c08-219">Clear the **Browser** check box.</span></span>

    ![Azure AD 條件式存取用戶端應用程式設定的螢幕擷取畫面](../media/azure-ad-conditional-access-client-mobile.png)

12. <span data-ttu-id="d5c08-221">按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-221">Click **Done**.</span></span>
13. <span data-ttu-id="d5c08-222">在 **[存取控制]** 底下，按一下 **[授與]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-222">Under **Access controls**, click **Grant**.</span></span>
14. <span data-ttu-id="d5c08-223">在 **[授與]** 刀鋒視窗中，選取 **[裝置需要標記為合規]** 和 **[需要已加入混合式 Azure AD 的裝置]**。 </span><span class="sxs-lookup"><span data-stu-id="d5c08-223">On the **Grant** blade, select **Require device to be marked as compliant** and **Require Hybrid Azure AD joined device**.</span></span>
15. <span data-ttu-id="d5c08-224">在 **[針對多個控制項]** 底下，選取 **[需要其中一個選取的控制項]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-224">Under **For multiple controls**, select **Require one of the selected controls**, and then click **Select**.</span></span>
16. <span data-ttu-id="d5c08-225">在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-225">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="d5c08-226">為 SharePoint 將來賓限制在僅限 Web 存取</span><span class="sxs-lookup"><span data-stu-id="d5c08-226">To restrict guests to web-ony access for SharePoint</span></span>

1. <span data-ttu-id="d5c08-227">在 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)，展開 [原則 **]**，然後按一下 [存取控制 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-227">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), expand **Policies** and click **Access control**.</span></span>
2. <span data-ttu-id="d5c08-228">按一下 [未受管理的裝置 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-228">Click **Unmanaged devices**.</span></span>
3. <span data-ttu-id="d5c08-229">選取 [允許有限的僅限 Web 存取 **]** 選項，然後按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-229">Select the **Allow limited, web-only access** option, and then click **Save**.</span></span>

<span data-ttu-id="d5c08-230">請注意，SharePoint 系統管理中心的此設定會在 Azure AD 中建立支援的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="d5c08-230">Note that this setting in the SharePoint admin center creates a supporting conditional access policy in Azure AD.</span></span>

## <a name="configure-a-session-timeout-for-guests"></a><span data-ttu-id="d5c08-231">為來賓設定工作階段逾時。</span><span class="sxs-lookup"><span data-stu-id="d5c08-231">Configure a session timeout for guests</span></span>

<span data-ttu-id="d5c08-232">若來賓的裝置不安全，要求來賓定期驗證可降低未知的使用者存取貴組織內容的可能性。</span><span class="sxs-lookup"><span data-stu-id="d5c08-232">Requiring guests to authenticate on a regular basis can reduce the possibility of unknown users accessing your organization's content if a guest's device isn't kept secure.</span></span> <span data-ttu-id="d5c08-233">您可以在 Azure AD 中設定來賓的工作階段逾時條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="d5c08-233">You can configure a session timeout conditional access policy for guests in Azure AD.</span></span>

<span data-ttu-id="d5c08-234">若要設定來賓工作階段逾時原則</span><span class="sxs-lookup"><span data-stu-id="d5c08-234">To configure a guest session timeout policy</span></span>

1. <span data-ttu-id="d5c08-235">移至 [[Azure 條件式存取原則]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-235">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d5c08-236">在 **[條件式存取原則]** 刀鋒視窗中，按一下 **[新增原則]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-236">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="d5c08-237">在 **[名稱]** 方塊中，輸入 *來賓工作階段逾時*。</span><span class="sxs-lookup"><span data-stu-id="d5c08-237">In the **Name** box, type *Guest session timeout*.</span></span>
4. <span data-ttu-id="d5c08-238">在 **[指派]** 底下，按一下 **[使用者和群組]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-238">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="d5c08-239">在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，選取 **[所有來賓和外部使用者]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5c08-239">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d5c08-240">在 **[指派]** 底下，按一下 **雲端應用程式或動作**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-240">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="d5c08-241">在 **[包含]** 索引標籤上，選取 **[選取應用程式]**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-241">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="d5c08-242">在 **[選取]** 刀鋒視窗中，選取 **Microsoft Teams**、**Office 365 SharePoint Online** 和 **Outlook Groups**，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-242">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="d5c08-243">在 **[存取控制]** 底下，按一下 **[工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-243">Under **Access controls**, click **Session**.</span></span>
10. <span data-ttu-id="d5c08-244">在 **[工作階段]** 刀鋒視窗中，選取 **[登入頻率]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-244">On the **Session** blade, select **Sign-in frequency**.</span></span>
11. <span data-ttu-id="d5c08-245">選取 **1**，並在時間週期選取 **[天]** ，然後按一下 **[選取]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-245">Select **1** and **Days** for the time period, and then click **Select**.</span></span>
12. <span data-ttu-id="d5c08-246">在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-246">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a><span data-ttu-id="d5c08-247">建立高敏感度專案的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="d5c08-247">Create a sensitive information type for a highly sensitive project</span></span>

<span data-ttu-id="d5c08-248">敏感性資訊類型是預先定義的字串，可用於原則工作流程中，以強制執行法規遵循需求。</span><span class="sxs-lookup"><span data-stu-id="d5c08-248">Sensitive information types are predefined strings that can be used in policy workflows to enforce compliance requirements.</span></span> <span data-ttu-id="d5c08-249">Microsoft 365 合規性中心隨附超過 100 種敏感性資訊類型，包括駕照編號、信用卡號、銀行帳號等。</span><span class="sxs-lookup"><span data-stu-id="d5c08-249">The Microsoft 365 Compliance Center comes with over one hundred sensitive information types, including driver's license numbers, credit card numbers, bank account numbers, etc.</span></span>

<span data-ttu-id="d5c08-250">您可以建立自訂敏感性資訊類型以協助管理貴組織的特定內容。</span><span class="sxs-lookup"><span data-stu-id="d5c08-250">You can create custom sensitive information types to help manage content specific to your organization.</span></span> <span data-ttu-id="d5c08-251">在此範例中，我們將建立高敏感度專案的敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="d5c08-251">In this example, we'll create a custom sensitive information type for a highly sensitive project.</span></span> <span data-ttu-id="d5c08-252">然後，我們可以使用此敏感性資訊類型自動套用敏感性標籤。</span><span class="sxs-lookup"><span data-stu-id="d5c08-252">We can then use this sensitive information type to automatically apply a sensitivity label.</span></span>

<span data-ttu-id="d5c08-253">若要建立敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="d5c08-253">To create a sensitive information type</span></span>

1. <span data-ttu-id="d5c08-254">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)的左側瀏覽窗格中，展開 **[分類]**，然後按一下 **[敏感性資訊類型]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-254">In the [Microsoft 365 Compliance Center](https://compliance.microsoft.com), in the left navigation, expand **Classification**, and then click **Sensitive info types**.</span></span>
2. <span data-ttu-id="d5c08-255">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-255">Click **Create**.</span></span>
3. <span data-ttu-id="d5c08-256">在 **名稱** 和 **描述** 輸入 **Saturn 專案**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-256">For **Name** and **Description**, type **Project Saturn**, and then click **Next**.</span></span>
4. <span data-ttu-id="d5c08-257">按一下 **[新增元素]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-257">Click **Add an element**.</span></span>
5. <span data-ttu-id="d5c08-258">在 **[偵測內容包含]** 清單中，選取 **[關鍵字]**，然後在關鍵字方塊中輸入 *Saturn 專案*。</span><span class="sxs-lookup"><span data-stu-id="d5c08-258">On the **Detect content containing** list, select **Keywords**, and then type *Project Saturn* in the keyword box.</span></span>
6. <span data-ttu-id="d5c08-259">按一下 **[下一步]**，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-259">Click **Next**, and then click **Finish**.</span></span>
7. <span data-ttu-id="d5c08-260">若系統詢問您是否要測試敏感性資訊類型，請按一下 **[否]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-260">If asked if you would like to test the sensitive information type, click **No**.</span></span>

### <a name="more-information"></a><span data-ttu-id="d5c08-261">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d5c08-261">More information</span></span>

[<span data-ttu-id="d5c08-262">自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="d5c08-262">Custom sensitive information types</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a><span data-ttu-id="d5c08-263">建立自動標籤原則，以根據敏感性資訊類型指派敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d5c08-263">Create an auto-labeling policy to assign a sensitivity label based on a sensitive information type</span></span>

<span data-ttu-id="d5c08-264">如果您在組織中使用敏感度標籤，則可以自動將標籤套用至包含所定義敏感性資訊類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="d5c08-264">If you are using sensitivity labels in your organization, you can automatically apply a label to files that contain defined sensitive information types.</span></span> 

<span data-ttu-id="d5c08-265">建立自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="d5c08-265">To create an auto-labeling policy</span></span>

1. <span data-ttu-id="d5c08-266">開啟 [Microsoft 365 合規性系統管理中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-266">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="d5c08-267">在左側導覽中，按一下 [資訊保護 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-267">In the left navigation, click **Information protection**.</span></span>
3. <span data-ttu-id="d5c08-268">在 [自動加上標籤 **]** 索引標籤上，按一下 [建立自動加上標籤原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-268">On the **Auto-labeling** tab, click **Create auto-labeling policy**.</span></span>
4. <span data-ttu-id="d5c08-269">在 [選擇要套用此標籤的資訊 **]** 頁面上，選擇 [自訂 **]**，然後按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-269">On the **Choose info you want this label applied to** page, choose **Custom** and click **Next**.</span></span>
5. <span data-ttu-id="d5c08-270">輸入原則的名稱和描述，然後按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-270">Type a name and description for the policy and click **Next**.</span></span>
6. <span data-ttu-id="d5c08-271">在 [選擇您要套用標籤的位置 **]** 頁面上，開啟 [SharePoint 網站 **]**，然後按一下 [選擇網站 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-271">On the **Choose locations where you want to apply the label** page, turn on **SharePoint sites** and click **Choose sites**.</span></span>
7. <span data-ttu-id="d5c08-272">新增您要開啟自動加上標籤的網站 URL，然後按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-272">Add the URLs for the sites where you want to turn on auto-labeling and click **Done**.</span></span>
8. <span data-ttu-id="d5c08-273">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-273">Click **Next**.</span></span>
9. <span data-ttu-id="d5c08-274">在 [設定一般或進階規則 **]** 頁面上，選擇 [一般規則 **]**，然後按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-274">On the **Set up common or advanced rules** page, choose **Common rules** and click **Next**.</span></span>
10. <span data-ttu-id="d5c08-275">在 [定義所有位置的內容規則 **]** 頁面上，按一下 [新增規則 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-275">On the **Define rules for content in all locations** page, click **New rule**.</span></span>
11. <span data-ttu-id="d5c08-276">在 [新增規則 **]** 頁面上，為規則命名，按一下 [新增條件 **]**，然後按一下 [內容包含敏感性資訊類型 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-276">On the **New rule** page, give the rule a name, click **Add condition**, and then click **Content contains sensitive info types**.</span></span>
12. <span data-ttu-id="d5c08-277">按一下 [新增 **]**，按一下 [敏感性資訊類型 **]**，選擇您要使用的敏感性資訊類型，按一下 [新增 **]**，然後按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-277">Click **Add**, click **Sensitive info types**, choose the sensitive info types that you want to use, click **Add**, and then click **Save**.</span></span>
13. <span data-ttu-id="d5c08-278">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-278">Click **Next**.</span></span>
14. <span data-ttu-id="d5c08-279">按一下 [選擇標籤 **]**，選取您要使用的標籤，然後按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-279">Click **Choose a label**, select the label you want to use, and then click **Add**.</span></span>
15. <span data-ttu-id="d5c08-280">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-280">Click **Next**.</span></span>
16. <span data-ttu-id="d5c08-281">將原則保留為模擬模式，然後按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-281">Leave the policy in simulation mode and click **Next**.</span></span>
17. <span data-ttu-id="d5c08-282">按一下 [建立原則 **]**，然後按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-282">Click **Create policy**, and then click **Done**.</span></span>

<span data-ttu-id="d5c08-283">建立原則後，當使用者在文件中輸入「Saturn 專案」時，自動標籤原則將在掃描檔案時自動套用指定的標籤。</span><span class="sxs-lookup"><span data-stu-id="d5c08-283">With the policy in place, when a user types "Project Saturn" into a document, the auto-labeling policy will automatically apply the specified label when it scans the file.</span></span>

### <a name="more-information"></a><span data-ttu-id="d5c08-284">其他資訊</span><span class="sxs-lookup"><span data-stu-id="d5c08-284">More information</span></span>

[<span data-ttu-id="d5c08-285">自動將敏感性標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="d5c08-285">Apply a sensitivity label to content automatically</span></span>](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a><span data-ttu-id="d5c08-286">建立 DLP 原則以移除高敏感性檔案的來賓存取</span><span class="sxs-lookup"><span data-stu-id="d5c08-286">Create a DLP policy to remove guest access to highly sensitive files</span></span>

<span data-ttu-id="d5c08-287">您可以使用[資料外洩防護 (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 以防止不必要的來賓共用敏感性內容。</span><span class="sxs-lookup"><span data-stu-id="d5c08-287">You can use [data loss prevention (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to prevent unwanted guest sharing of sensitive content.</span></span> <span data-ttu-id="d5c08-288">資料外洩防護可以根據檔案的敏感度標籤採取動作，並移除來賓存取。</span><span class="sxs-lookup"><span data-stu-id="d5c08-288">Data loss prevention can take action based on a file's sensitivity label and remove guest access.</span></span>

<span data-ttu-id="d5c08-289">建立 DLP 規則</span><span class="sxs-lookup"><span data-stu-id="d5c08-289">To create a DLP rule</span></span>

1. <span data-ttu-id="d5c08-290">在 Microsoft 365 合規性系統管理中心中，移至 [資料外外洩防護頁面](https://compliance.microsoft.com/datalossprevention)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-290">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="d5c08-291">按一下 **[建立原則]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-291">Click **Create policy**.</span></span>
3. <span data-ttu-id="d5c08-292">選擇 **[自訂]** ，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-292">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="d5c08-293">輸入原則的名稱，並按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-293">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="d5c08-294">在 **[套用原則的位置]** 頁面上，關閉 **SharePoint 網站** 和 **OneDrive 帳戶** 以外的所有設定，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-294">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts**, and then click **Next**.</span></span>
6. <span data-ttu-id="d5c08-295">在 **[定義原則設定]** 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-295">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="d5c08-296">在 **[自訂進階資料外洩防護規則]** 頁面上，按一下 **[建立規則]**，然後輸入規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="d5c08-296">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="d5c08-297">在 [條件 **]** 底下，按一下 [新增條件 **]**，並選擇 [內容包含 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-297">Under **Conditions**, click **Add condition**, and choose **Content contains**.</span></span>
9. <span data-ttu-id="d5c08-298">按一下 [新增 **]**，選擇 [敏感度標籤 **]**，選擇您要使用的標籤，然後按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-298">Click **Add**, choose **Sensitivity labels**, choose the labels you want to use, and click **Add**.</span></span>

   ![條件選項、敏感性資訊類型、敏感性標籤及保留標籤的螢幕擷取畫面。](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="d5c08-300">在 [動作 **]** 底下，按一下 [新增動作 **]**，然後選擇 [限制存取或加密 Microsoft 365 位置中的內容 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-300">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="d5c08-301">選取 [限制存取或在 Microsoft 365 位置中加密內容 **]** 核取方塊，然後選擇 [只有組織外的人員 **]** 選項。</span><span class="sxs-lookup"><span data-stu-id="d5c08-301">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people outside your organization** option.</span></span>

      ![DLP 規則動作選項的螢幕擷取畫面](../media/dlp-remove-guest-access-sensitive-files.png)

12. <span data-ttu-id="d5c08-303">按一下 **[儲存]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-303">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="d5c08-304">選擇您的測試選項，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-304">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="d5c08-305">按一下 [提交 **]**，然後按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="d5c08-305">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="d5c08-306">請注意，如果來賓是網站或小組整體的成員，則此原則不會移除存取。</span><span class="sxs-lookup"><span data-stu-id="d5c08-306">It's important to note that this policy doesn't remove access if the guest is a member of the site or team as a whole.</span></span> <span data-ttu-id="d5c08-307">如果您計劃讓具有來賓成員的網站或團隊擁有高敏感度文件，請考慮[在 Teams 中使用私人頻道](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e)，且只允許組織中的成員使用私人頻道。</span><span class="sxs-lookup"><span data-stu-id="d5c08-307">If you plan to have highly sensitive documents in a site or team with guest members, consider using [private channels in Teams](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e) and only allowing members of your organization in the private channels.</span></span>

## <a name="additional-options"></a><span data-ttu-id="d5c08-308">其他選項</span><span class="sxs-lookup"><span data-stu-id="d5c08-308">Additional options</span></span>

<span data-ttu-id="d5c08-309">Microsoft 365 和 Azure Active Directory 中有一些其他選項可以協助保護您的來賓共用環境。</span><span class="sxs-lookup"><span data-stu-id="d5c08-309">There are some additional options in Microsoft 365 and Azure Active Directory that can help secure your guest sharing environment.</span></span>

- <span data-ttu-id="d5c08-310">您可以建立允許或拒絕共用網域的清單，以限制要共用的使用者。</span><span class="sxs-lookup"><span data-stu-id="d5c08-310">You can create a list of allowed or denied sharing domains to limit who users can share with.</span></span> <span data-ttu-id="d5c08-311">如需詳細資訊，請參閱[依網域限制 SharePoint 和 OneDrive 內容的共用](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)和[允許或封鎖對特定組織的 B2B 使用者的邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-311">See [Restrict sharing of SharePoint and OneDrive content by domain](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) and [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) for more information.</span></span>
- <span data-ttu-id="d5c08-312">您可以限制使用者可以連線到哪些其他 Azure Active Directory 租用戶。</span><span class="sxs-lookup"><span data-stu-id="d5c08-312">You can limit which other Azure Active Directory tenants your users can connect to.</span></span> <span data-ttu-id="d5c08-313">如需詳細資訊，請參閱[使用租用戶限制管理 SaaS 雲端應用程式的存取](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-313">See [Use tenant restrictions to manage access to SaaS cloud applications](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions) for information.</span></span>
- <span data-ttu-id="d5c08-314">您可以建立受管理環境，讓合作夥伴能夠協助管理來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="d5c08-314">You can create a managed environment where partners can help manage guest accounts.</span></span> <span data-ttu-id="d5c08-315">如需詳細資訊，請參閱[建立 B2B 外部網路](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet)。</span><span class="sxs-lookup"><span data-stu-id="d5c08-315">See [Create a B2B extranet with managed guests](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet) for information.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5c08-316">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d5c08-316">See Also</span></span>

[<span data-ttu-id="d5c08-317">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="d5c08-317">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="d5c08-318">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="d5c08-318">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="d5c08-319">使用受管理來賓建立 B2B 外部網路</span><span class="sxs-lookup"><span data-stu-id="d5c08-319">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
