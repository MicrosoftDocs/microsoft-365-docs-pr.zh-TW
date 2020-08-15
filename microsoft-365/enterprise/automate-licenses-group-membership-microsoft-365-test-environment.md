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
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685555"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2ccbf-103">為您的 Microsoft 365 for enterprise 測試環境自動化授權和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="2ccbf-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2ccbf-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="2ccbf-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="2ccbf-105">以群組為基礎的授權會根據群組成員資格，自動指派或移除使用者帳戶的授權。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="2ccbf-106">動態群組成員資格會根據使用者帳戶屬性（例如部門或國家/地區），新增或移除群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="2ccbf-107">本文會逐步引導您在 Microsoft 365 的企業版測試環境中示範。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-107">This article steps you through a demonstration of both in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="2ccbf-108">在 Microsoft 365 企業版測試環境中設定自動授權和動態群組成員資格有兩個階段：</span><span class="sxs-lookup"><span data-stu-id="2ccbf-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="2ccbf-109">建立適用于企業測試環境的 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-109">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="2ccbf-110">設定及測試動態群組成員資格和自動授權。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="2ccbf-112">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2ccbf-113">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="2ccbf-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2ccbf-114">如果您只想以輕量的方式測試自動授權和群組成員資格，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2ccbf-115">如果您想要在模擬的企業中測試自動授權和群組成員資格，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ccbf-116">測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="2ccbf-117">這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="2ccbf-118">階段2：設定及測試動態群組成員資格和自動授權</span><span class="sxs-lookup"><span data-stu-id="2ccbf-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="2ccbf-119">首先，您會建立新的銷售群組，並新增動態群組成員資格規則，使設定為「銷售部門」的使用者帳戶會自動新增至 Sales 群組。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="2ccbf-120">使用網際網路瀏覽器的私人實例，使用您的 Microsoft 365 E5 測試實驗室訂閱的全域系統管理員帳戶登入 [microsoft 365 系統管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-120">Using a private instance of your Internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="2ccbf-121">在您瀏覽器的個別索引標籤上，移至 Azure 入口網站，網址為 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="2ccbf-122">在 Azure 入口網站的搜尋方塊中輸入 [ **群組** ]，然後按一下 [ **群組**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="2ccbf-123">在 [ **所有群組** ] 窗格中，按一下 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="2ccbf-124">在 [ **群組類型**] 中，選取 [ **Microsoft 365**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="2ccbf-125">在 [ **組名**] 中輸入 **Sales**。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="2ccbf-126">在 [ **成員資格類型**] 中，選取 [ **動態使用者**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="2ccbf-127">按一下 [ **動態使用者成員**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="2ccbf-128">在 [ **動態成員資格規則** ] 窗格中：</span><span class="sxs-lookup"><span data-stu-id="2ccbf-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="2ccbf-129">選取 [ **部門** ] 屬性。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-129">Select the **department** property.</span></span>
   - <span data-ttu-id="2ccbf-130">選取 [ **等於** ] 運算子。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="2ccbf-131">在**值**中輸入**Sales** 。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="2ccbf-132">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-132">Click **Save**.</span></span>
11. <span data-ttu-id="2ccbf-133">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-133">Click **Create**.</span></span>

<span data-ttu-id="2ccbf-134">接下來，您要設定 Sales 群組，讓成員自動獲指派 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="2ccbf-135">按一下 [ **Sales** ] 群組，然後按一下 [ **授權**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="2ccbf-136">在 [ **更新授權指派** ] 窗格中，選取 [ **Microsoft 365 E5**]，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="2ccbf-137">關閉瀏覽器的 Azure 入口網站索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="2ccbf-138">接下來，在使用者4帳戶上測試動態群組成員資格和自動授權。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="2ccbf-139">從瀏覽器的 [ **Microsoft Office 首頁** ] 索引標籤中，按一下 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="2ccbf-140">在 [ **Microsoft 365 系統管理中心** ] 索引標籤上，按一下 [作用中 **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="2ccbf-141">在 [作用中 **使用者** ] 頁面上，按一下 [ **使用者 4** ] 帳戶。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="2ccbf-142">在 [**使用者 4** ] 窗格上，按一下 [**產品授權**] 的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="2ccbf-143">在 [ **產品授權** ] 窗格上，停用 **Microsoft 365 E5** 授權，然後按一下 [ **儲存 > 關閉**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="2ccbf-144">在 [使用者 4] 帳戶的內容中，確認未指派任何產品授權，而且沒有群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="2ccbf-145">按一下 [ **編輯** 以取得 **連絡人資訊**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="2ccbf-146">在 [ **編輯連絡人資訊** ] 窗格中，按一下 [ **連絡人資訊**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="2ccbf-147">在 [ **部門** ] 欄位中，輸入 **Sales**，然後按一下 [ **儲存 > 關閉**]。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="2ccbf-148">等候幾分鐘，然後定期按一下 [使用者 4] [帳戶] 窗格右上角的 [重新整理] 圖示。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="2ccbf-149">您應該會看到下列專案：</span><span class="sxs-lookup"><span data-stu-id="2ccbf-149">In time you should see the:</span></span>

- <span data-ttu-id="2ccbf-150">使用**Sales**群組更新的**群組成員資格**屬性。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="2ccbf-151">使用**Microsoft 365 E5**授權更新的**產品授權**屬性。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="2ccbf-152">請參閱下列文章，以在實際執行環境中部署動態群組成員資格和自動授權：</span><span class="sxs-lookup"><span data-stu-id="2ccbf-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- <span data-ttu-id="2ccbf-153">連結 TBD</span><span class="sxs-lookup"><span data-stu-id="2ccbf-153">LINK TBD</span></span>
- <span data-ttu-id="2ccbf-154">連結 TBD</span><span class="sxs-lookup"><span data-stu-id="2ccbf-154">LINK TBD</span></span>

## <a name="next-step"></a><span data-ttu-id="2ccbf-155">下一步</span><span class="sxs-lookup"><span data-stu-id="2ccbf-155">Next step</span></span>

<span data-ttu-id="2ccbf-156">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="2ccbf-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ccbf-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2ccbf-157">See also</span></span>

[<span data-ttu-id="2ccbf-158">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="2ccbf-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="2ccbf-159">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="2ccbf-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2ccbf-160">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="2ccbf-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2ccbf-161">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="2ccbf-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
