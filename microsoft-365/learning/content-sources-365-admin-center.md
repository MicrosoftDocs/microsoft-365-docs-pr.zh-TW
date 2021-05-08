---
title: 在 Microsoft 365 系統管理中心中設定 Microsoft Viva 教學 (預覽) 的教學內容來源
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 瞭解如何設定「Microsoft Viva 學習」的教學內容來源 (預覽) Microsoft 365 系統管理中心。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b2e6ab6306db9a5ac9d91226431e5876cc244499
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245417"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6cdfc-103">在 Microsoft 365 系統管理中心中設定 Microsoft Viva 教學 (預覽) 的教學內容來源</span><span class="sxs-lookup"><span data-stu-id="6cdfc-103">Configure learning content sources for Microsoft Viva Learning (Preview) in the Microsoft 365 admin center</span></span>

> [!NOTE]
> <span data-ttu-id="6cdfc-104">本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="6cdfc-105">Microsoft 365 系統管理中心的管理員（自行或指派知識系統管理員角色給組織中所選的個人）可以管理與 Viva 學習 (Preview) 相關的設定，並且可以設定教學內容來源。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-105">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (Preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="6cdfc-106">管理員會選取哪些其他學習內容來源 (例如，SharePoint 或支援的協力廠商內容提供者來源) 可供 Viva 教學 (預覽) 的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-106">The administrator selects which other learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (Preview).</span></span> <span data-ttu-id="6cdfc-107">然後，系統管理員會設定這些來源，以確定內容可用於搜尋及探索，而且可供使用 Viva 教學 (預覽) 的員工流覽。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-107">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (Preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="6cdfc-108">使用者在瀏覽器或內嵌檢視器中登入非 Microsoft 並 LinkedIn 學習 Pro learnings。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-108">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="6cdfc-109">這項設定的學習會受限於組織和協力廠商之間的個別授權、隱私權和服務條款，而不是 Viva 教學 (預覽) 條款。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-109">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (Preview) terms.</span></span> <span data-ttu-id="6cdfc-110">在選取這種教學類型之前，請確認您的組織和使用者已具備適當的合約。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-110">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

## <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="6cdfc-111">指派知識系統管理員角色 (選用) </span><span class="sxs-lookup"><span data-stu-id="6cdfc-111">Assign the knowledge admin role (Optional)</span></span>

<span data-ttu-id="6cdfc-112">您必須是 Microsoft 365 全域系統管理員，才可執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-112">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

> [!TIP]
> <span data-ttu-id="6cdfc-113">知識系統管理員應為適度的技術，且具有現有的 SharePoint 系統管理員認證，最好是 versed 在教育、教學、訓練或員工經驗中的部分組織中。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-113">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>

### <a name="add-a-knowledge-admin"></a><span data-ttu-id="6cdfc-114">新增知識管理</span><span class="sxs-lookup"><span data-stu-id="6cdfc-114">Add a knowledge admin</span></span>

<span data-ttu-id="6cdfc-115">若要新增 Viva 教學的知識管理員 (預覽) ，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6cdfc-115">To add a knowledge admin for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="6cdfc-116">在 Microsoft 365 系統管理中心的左側導覽中，移至 [**角色**]。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-116">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="6cdfc-117">在 [ **角色** ] 頁面上，選取 [ **Azure AD** ] 索引標籤上的 [ **知識管理員**]。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-117">On the **Roles** page, on the **Azure AD** tab, select **Knowledge Administrator**.</span></span>
 
3.  <span data-ttu-id="6cdfc-118">在 [ **知識管理員** ] 面板上，選取 [指派的系統 **管理員**]，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-118">On the **Knowledge Administrator** panel, select **Assigned admins**, and then select **Add**.</span></span>

     ![角色] 頁面的 [Microsoft 365 系統管理中心]，顯示 [知識管理員] 面板，以加入使用者。](../media/learning/learning-add-knowledge-admin-1.png)

3.  <span data-ttu-id="6cdfc-120">在 [ **新增管理員** ] 面板上，選取您為該角色選擇的人員，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-120">On the **Add admins** panel, select the person you choose for the role, and then select **Add**.</span></span>

     ![角色] 頁面的 Microsoft 365 系統管理中心顯示 [新增管理員] 面板，以新增使用者。](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a><span data-ttu-id="6cdfc-122">移除知識管理</span><span class="sxs-lookup"><span data-stu-id="6cdfc-122">Remove a knowledge admin</span></span>

<span data-ttu-id="6cdfc-123">若要移除 Viva 教學的知識系統管理員 (預覽) ，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6cdfc-123">To remove a knowledge admin for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="6cdfc-124">在 Microsoft 365 系統管理中心的左側導覽中，移至 [**角色**]。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-124">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="6cdfc-125">在 [ **角色** ] 頁面上的 [ **Azure AD** ] 索引標籤上，然後選取 [ **知識管理員**]。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-125">On the **Roles** page, on the **Azure AD** tab, and then select **Knowledge Administrator**.</span></span>
 
3.  <span data-ttu-id="6cdfc-126">在 [ **知識管理員** ] 面板的 [ **指派** 的系統管理員] 索引標籤上，選取 [ **移除**]，然後選取您要從角色中移除的人員。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-126">On the **Knowledge Administrator** panel, on the **Assigned Admins** tab, select **Remove**, and then select the person you want to remove from the role.</span></span> <span data-ttu-id="6cdfc-127">若要確認，請選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-127">To confirm, select **Remove**.</span></span>

     ![角色] 頁面上的 Microsoft 365 系統管理中心顯示指派的系統管理員面板，以移除使用者。](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a><span data-ttu-id="6cdfc-129">設定學習內容來源的設定</span><span class="sxs-lookup"><span data-stu-id="6cdfc-129">Configure settings for the learning content sources</span></span>

<span data-ttu-id="6cdfc-130">您必須是 Microsoft 365 全域管理員或知識系統管理員，才可執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-130">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="6cdfc-131">若要在 Viva 教學中設定學習內容來源的設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6cdfc-131">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="6cdfc-132">在 Microsoft 365 系統管理中心的左側導覽中，移至 **設定**  >  **組織設定**」。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-132">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="6cdfc-133">在 [ **組織設定** ] 頁面上的 [ **服務** ] 索引標籤上，選取 [ **Viva 教學 (預覽])**。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-133">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![Microsoft 365 系統管理中心中的設定頁面，顯示所列的學習應用程式。](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="6cdfc-135">在 [ **Viva 教學 (預覽)** ] 面板上，選取您要為組織設定的學習內容來源，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-135">On the **Viva Learning (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![Microsoft 365 系統管理中心中的學習面板顯示內容來源選項。](../media/learning/learning-sharepoint-configure2.png)

<span data-ttu-id="6cdfc-137">所有已存在的學習來源中，有些會預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-137">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="6cdfc-138">這些學習來源包括：</span><span class="sxs-lookup"><span data-stu-id="6cdfc-138">These learning sources include:</span></span>

- <span data-ttu-id="6cdfc-139">LinkedIn 學習 (可用內容) </span><span class="sxs-lookup"><span data-stu-id="6cdfc-139">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="6cdfc-140">Microsoft 學習</span><span class="sxs-lookup"><span data-stu-id="6cdfc-140">Microsoft Learn</span></span>
- <span data-ttu-id="6cdfc-141">Microsoft 365培訓</span><span class="sxs-lookup"><span data-stu-id="6cdfc-141">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="6cdfc-142">LinkedIn LinkedIn 隱私權原則和使用者合約中提供給使用者的免費內容。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-142">LinkedIn free content is provided to users under the LinkedIn privacy policies and user agreement.</span></span> <span data-ttu-id="6cdfc-143">LinkedIn 會接收使用者的 IP 位址，任何先前由 LinkedIn 設定的 cookie，並會設定新的 cookie，以追蹤可用內容的使用。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-143">LinkedIn will receive the user’s IP address, any cookies previously set by LinkedIn, and will set a new cookie to track use of free content.</span></span> <span data-ttu-id="6cdfc-144">使用者不需要使用 LinkedIn 來登入以取得免費內容。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-144">Users are not required to sign in with LinkedIn to receive free content.</span></span><br><br>
<span data-ttu-id="6cdfc-145">針對 LinkedIn 的精品內容，您的組織必須訂閱小組才能存取該內容。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-145">For LinkedIn premium content, your organization needs a subscription for your team to access that content.</span></span> <span data-ttu-id="6cdfc-146">使用者必須登入 LinkedIn 以存取該教學，這會在組織的條款和使用者條款中以 LinkedIn 提供。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-146">Users will need to sign into LinkedIn to access that learning, which is provided under the terms of your organization’s and user terms with LinkedIn.</span></span><br><br> <span data-ttu-id="6cdfc-147">若為非 Microsoft 內容 (，除了免費 LinkedIn 內容) 以外，請確定您的組織有訂閱，可讓您的使用者在將該內容連接至 Viva 學習 (預覽) 之前，先使用工作帳戶存取該內容。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-147">For non-Microsoft content (except free LinkedIn content), ensure your organization has a subscription for your users to access that content using a work account before connecting it to Viva Learning (Preview).</span></span> <span data-ttu-id="6cdfc-148">使用者的非 Microsoft 學習提供者個人訂閱將不會與 Viva 教學 (預覽) 整合。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-148">Users’ personal subscriptions to non-Microsoft learning providers will not be integrated with Viva Learning (Preview).</span></span> <span data-ttu-id="6cdfc-149">使用者在瀏覽器或內嵌檢視器中登入非 Microsoft 並 LinkedIn 學習 Pro learnings。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-149">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="6cdfc-150">如果使用者流覽到其不具備組織訂閱的內容，他們可能會看到可用於註冊個別訂閱的提供者頁面。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-150">If users navigate to content where they do not have an organizational subscription, they may see a provider page where they could sign up for an individual subscription.</span></span> <span data-ttu-id="6cdfc-151">所有非 Microsoft 的學習都是以非 Microsoft 提供者的條款提供，而不是 Viva 教學的一部分。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-151">All non-Microsoft learning is provided under the non-Microsoft provider’s terms and not as part of Viva Learning.</span></span> 

<span data-ttu-id="6cdfc-152">若要啟用或停用教學內容來源，請選取來源旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-152">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="6cdfc-153">如果已啟用來源，就會顯示核取記號。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-153">If a source is enabled, a check mark will be visible.</span></span>

## <a name="third-party-content-providers"></a><span data-ttu-id="6cdfc-154">協力廠商內容提供者</span><span class="sxs-lookup"><span data-stu-id="6cdfc-154">Third-party content providers</span></span> 

<span data-ttu-id="6cdfc-155">一組可用的已連線的教學提供者可能會隨時變更。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-155">The set of available connected learning providers might change at any time.</span></span> <span data-ttu-id="6cdfc-156">當程式成長時，其他提供者會加入。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-156">More providers will join as the program grows.</span></span> <span data-ttu-id="6cdfc-157">可用的提供者也可以選擇停止其與 Viva 教學 (預覽) 的連線。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-157">Available providers might also choose to discontinue their connection with Viva Learning (Preview).</span></span>

### <a name="skillsoft-as-a-content-source"></a><span data-ttu-id="6cdfc-158">Skillsoft 做為內容來源</span><span class="sxs-lookup"><span data-stu-id="6cdfc-158">Skillsoft as a content source</span></span>  

<span data-ttu-id="6cdfc-159">針對 Viva 教學 (預覽) ，已啟用 Skillsoft 的使用者，並選擇查看 Skillsoft 內容會在 Percipio 頁面上，讓他們輸入您組織的 Percipio 網站名稱。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-159">For Viva Learning (Preview), users who have Skillsoft enabled and choose to view Skillsoft content will land on a Percipio page that asks them to input your organization's Percipio site name.</span></span> <span data-ttu-id="6cdfc-160">使用者輸入您組織的網站名稱後，系統會將其導向至頁面登入您組織的 Percipio 網站。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-160">After users input your organization's site name, they will be directed to page to sign in to your organization's Percipio site.</span></span> <span data-ttu-id="6cdfc-161">使用者將使用其現有的認證登入，並查看其最初選取的內容。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-161">Users will sign in by using their existing credentials and see the content they originally selected.</span></span> <span data-ttu-id="6cdfc-162">使用者只會要求使用者輸入 Percipio 網站名稱一次，直到清除其瀏覽器快取。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-162">Users will be asked to input the Percipio site name only once, until their browser cache is cleared.</span></span> <span data-ttu-id="6cdfc-163">若要為您的使用者簡化這項體驗，建議您在傳送的內部通訊中包含您的 Percipio 網站名稱，以供您在 Viva 學習 (預覽) 中傳送。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-163">To streamline this experience for your users, we recommend including your Percipio site name in internal communications you send about Viva Learning (Preview).</span></span>

<span data-ttu-id="6cdfc-164">這是一種暫時的預覽體驗，而且我們正在與 Skillsoft 搭配使用，以針對一般可用性啟用租使用者特有的整合，這會略過需要使用者提供組織之 Percipio 網站名稱的步驟。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-164">This is intended to be a temporary experience for preview, and we are working with Skillsoft to enable tenant-specific integration for general availability, which will bypass the step that requires users to provide your organization's Percipio site name.</span></span> 

### <a name="details-on-microsoft-substrate"></a><span data-ttu-id="6cdfc-165">Microsoft 基底的詳細資料</span><span class="sxs-lookup"><span data-stu-id="6cdfc-165">Details on Microsoft substrate</span></span>  

<span data-ttu-id="6cdfc-166">若要將資料複製到 Viva 教學 (預覽) 從非 Microsoft service (教學提供者或學習管理系統) ，您無法直接解壓縮、更正或刪除 Viva 教學 (預覽) 中的資料。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-166">For data that you copy to Viva Learning (Preview) from a non-Microsoft service (learning provider or learning management system), you are not able to directly extract, correct, or delete that data in Viva Learning (Preview).</span></span> <span data-ttu-id="6cdfc-167">我們會立即重新整理從非 Microsoft 提供者匯入的資料，以反映非 Microsoft 來源資料中的變更和刪除。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-167">We refresh the data you import from non-Microsoft providers promptly to reflect changes and deletions in the non-Microsoft source data.</span></span>

<span data-ttu-id="6cdfc-168">您需要與非 Microsoft 服務的供應商合作，以存取、更正、刪除或解壓縮非 Microsoft 服務之授權、服務或隱私權方面的資料。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-168">You need to work with the supplier of the non-Microsoft service to access, correct, delete or extract data under the license, service, or privacy terms of the non-Microsoft service.</span></span> <span data-ttu-id="6cdfc-169">在 Viva 學習 () 預覽中所做的變更會反映在非 Microsoft service 和 Viva 教學 (預覽) 的資料更新週期完成時，已處理的資料。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-169">The changes made there will be reflected in the data processed for your use in Viva Learning (Preview) upon completion of the data update cycles of the non-Microsoft service and Viva Learning (Preview).</span></span> <span data-ttu-id="6cdfc-170">如果您關閉 Viva 教學 (預覽) 和非 Microsoft 服務之間的連線，則先前從該服務匯入的所有資料都會被刪除。</span><span class="sxs-lookup"><span data-stu-id="6cdfc-170">If you turn off the connection between Viva Learning (Preview) and a non-Microsoft service, all data you had previously imported from that service will be deleted.</span></span> 

## <a name="next-step"></a><span data-ttu-id="6cdfc-171">下一步</span><span class="sxs-lookup"><span data-stu-id="6cdfc-171">Next step</span></span>

[<span data-ttu-id="6cdfc-172">將 SharePoint 設定為 Microsoft Viva 教學 (Preview 的教學內容來源) </span><span class="sxs-lookup"><span data-stu-id="6cdfc-172">Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>](configure-sharepoint-content-source.md)