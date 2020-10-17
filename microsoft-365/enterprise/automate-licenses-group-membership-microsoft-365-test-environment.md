---
title: 為您的 Microsoft 365 for enterprise 測試環境自動化授權和群組成員資格
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 在您的 Microsoft 365 for enterprise test 環境中，設定以群組為基礎的授權和動態群組成員資格。
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487573"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="994ac-103">為您的 Microsoft 365 for enterprise 測試環境自動化授權和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="994ac-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="994ac-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="994ac-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="994ac-105">以群組為基礎的授權會根據群組成員資格，自動指派或移除使用者帳戶的授權。</span><span class="sxs-lookup"><span data-stu-id="994ac-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="994ac-106">動態群組成員資格會根據使用者帳戶屬性（例如 **部門** 或 **國家/地區**），新增或移除群組的成員。</span><span class="sxs-lookup"><span data-stu-id="994ac-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="994ac-107">本文將引導您逐步示範新增及移除 Microsoft 365 for enterprise test 環境中的群組成員。</span><span class="sxs-lookup"><span data-stu-id="994ac-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="994ac-108">在 Microsoft 365 企業版測試環境中設定自動授權和動態群組成員資格包括兩個階段：</span><span class="sxs-lookup"><span data-stu-id="994ac-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="994ac-109">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="994ac-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="994ac-110">階段2：設定及測試動態群組成員資格和自動授權</span><span class="sxs-lookup"><span data-stu-id="994ac-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="994ac-112">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="994ac-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="994ac-113">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="994ac-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="994ac-114">如果您只想以輕量的方式測試自動授權和群組成員資格，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="994ac-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="994ac-115">如果您想要在模擬的企業中測試自動授權和群組成員資格，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="994ac-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="994ac-116">測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="994ac-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="994ac-117">它會以選項形式提供，以便您可以測試自動授權和群組成員資格，並在代表一般組織的環境中進行試驗。</span><span class="sxs-lookup"><span data-stu-id="994ac-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="994ac-118">階段2：設定及測試動態群組成員資格和自動授權</span><span class="sxs-lookup"><span data-stu-id="994ac-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="994ac-119">首先，建立名為 Sales 的新群組，並新增動態群組成員資格規則，讓與設定為「**銷售\*\*\*\*部門**」的使用者帳戶自動加入 sales 群組。</span><span class="sxs-lookup"><span data-stu-id="994ac-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="994ac-120">在網際網路瀏覽器的私人實例中，以 Microsoft 365 E5 測試實驗室訂閱的全域系統管理員帳戶登入 [microsoft 365 系統管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="994ac-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="994ac-121">在您瀏覽器的個別索引標籤上，移至 Azure 入口網站，網址為 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="994ac-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="994ac-122">在 Azure 入口網站中，于搜尋方塊中輸入 **群組** ，然後選取 [ **群組**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="994ac-123">在 [ **所有群組** ] 窗格中，選取 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="994ac-124">在 [ **群組類型**] 中，選取 [ **Microsoft 365**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="994ac-125">在 [ **組名**] 中輸入 **Sales**。</span><span class="sxs-lookup"><span data-stu-id="994ac-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="994ac-126">在 [ **成員資格類型**] 中，選取 [ **動態使用者**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="994ac-127">選取 [ **動態使用者成員**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="994ac-128">在 [ **動態成員資格規則** ] 窗格中：</span><span class="sxs-lookup"><span data-stu-id="994ac-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="994ac-129">選取 [ **部門** ] 屬性。</span><span class="sxs-lookup"><span data-stu-id="994ac-129">Select the **department** property.</span></span>
   - <span data-ttu-id="994ac-130">選取 [ **等於** ] 運算子。</span><span class="sxs-lookup"><span data-stu-id="994ac-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="994ac-131">在 [ **值** ] 方塊中，輸入 **Sales**。</span><span class="sxs-lookup"><span data-stu-id="994ac-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="994ac-132">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="994ac-132">Select **Save**.</span></span>
11. <span data-ttu-id="994ac-133">選取 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="994ac-133">Select **Create**.</span></span>

<span data-ttu-id="994ac-134">接下來，設定 Sales 群組，讓成員自動獲指派 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="994ac-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="994ac-135">選取 [ **銷售** ] 群組，然後選取 [ **授權**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="994ac-136">在 [ **更新授權指派** ] 窗格中，選取 [ **Microsoft 365 E5**]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="994ac-137">在您的瀏覽器中，關閉 [Azure 入口網站] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="994ac-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="994ac-138">接下來，在使用者4帳戶上測試動態群組成員資格和自動授權：</span><span class="sxs-lookup"><span data-stu-id="994ac-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="994ac-139">從瀏覽器的 [ **Microsoft Office 首頁** ] 索引標籤中，選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="994ac-140">從 [ **Microsoft 365 系統管理中心** ] 索引標籤中，選取 [作用中 **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="994ac-141">在 [作用中 **使用者** ] 頁面上，選取 [ **使用者 4** ] 帳戶。</span><span class="sxs-lookup"><span data-stu-id="994ac-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="994ac-142">在 [**使用者 4** ] 窗格中，選取 [**產品授權**] 的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="994ac-143">在 [**產品授權**] 窗格上，停用**Microsoft 365 E5**授權，然後選取 [**儲存**  >  **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="994ac-144">在 [使用者 4] 帳戶的內容中，確認未指派任何產品授權，而且沒有群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="994ac-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="994ac-145">如需 **聯繫資訊**，請選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="994ac-146">在 [ **編輯連絡人資訊** ] 窗格中，選取 [ **連絡人資訊**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="994ac-147">在 [**部門**] 方塊中，輸入**Sales**，然後選取 [**儲存**  >  **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="994ac-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="994ac-148">等候幾分鐘，然後定期選取 [使用者 4] [帳戶] 窗格右上角的 [重新整理 **] 圖示。**</span><span class="sxs-lookup"><span data-stu-id="994ac-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="994ac-149">及時，您應該會看到：</span><span class="sxs-lookup"><span data-stu-id="994ac-149">In time, you should see the:</span></span>

- <span data-ttu-id="994ac-150">使用**Sales**群組更新的**群組成員資格**屬性。</span><span class="sxs-lookup"><span data-stu-id="994ac-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="994ac-151">使用**Microsoft 365 E5**授權更新的**產品授權**屬性。</span><span class="sxs-lookup"><span data-stu-id="994ac-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="994ac-152">請參閱下列文章，以在實際執行環境中部署動態群組成員資格和自動授權：</span><span class="sxs-lookup"><span data-stu-id="994ac-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="994ac-153">在 Azure Active Directory 中以群組為基礎的授權</span><span class="sxs-lookup"><span data-stu-id="994ac-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="994ac-154">Azure Active Directory 中的動態群組</span><span class="sxs-lookup"><span data-stu-id="994ac-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="994ac-155">下一步</span><span class="sxs-lookup"><span data-stu-id="994ac-155">Next step</span></span>

<span data-ttu-id="994ac-156">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="994ac-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="994ac-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="994ac-157">See also</span></span>

[<span data-ttu-id="994ac-158">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="994ac-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="994ac-159">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="994ac-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="994ac-160">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="994ac-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="994ac-161">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="994ac-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
