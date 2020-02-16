---
title: 自動化適用於 Microsoft 365 企業版測試環境的授權和群組成員資格
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
description: Microsoft 365 企業版測試環境中設定群組為基礎的授權和動態群組成員資格。
ms.openlocfilehash: 266ae8cb133eccf74ea75382b400ca8241782ec5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068500"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="87e1d-103">自動化適用於 Microsoft 365 企業版測試環境的授權和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="87e1d-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="87e1d-104">*這個測試實驗室指南只能用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="87e1d-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="87e1d-105">群組為基礎的授權會自動指派或移除根據群組成員資格的使用者帳戶的授權。</span><span class="sxs-lookup"><span data-stu-id="87e1d-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="87e1d-106">動態群組成員資格新增或移除使用者帳戶內容，例如部門或國家/地區為基礎的群組成員。</span><span class="sxs-lookup"><span data-stu-id="87e1d-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="87e1d-107">本文會引導您完成 Microsoft 365 企業版測試環境中這兩者的示範。</span><span class="sxs-lookup"><span data-stu-id="87e1d-107">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="87e1d-108">有兩個主要階段設定 Microsoft 365 企業版測試環境中的自動授權和動態群組成員資格：</span><span class="sxs-lookup"><span data-stu-id="87e1d-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="87e1d-109">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="87e1d-109">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="87e1d-110">設定並測試動態群組成員資格和自動授權。</span><span class="sxs-lookup"><span data-stu-id="87e1d-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="87e1d-112">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="87e1d-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="87e1d-113">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="87e1d-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="87e1d-114">如果您只想以具有最小需求的輕量型方式測試自動授權和群組成員資格，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="87e1d-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="87e1d-115">如果您想要在模擬的企業中測試自動授權和群組成員資格，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="87e1d-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="87e1d-116">測試自動授權和群組成員資格不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。</span><span class="sxs-lookup"><span data-stu-id="87e1d-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="87e1d-117">它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="87e1d-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="87e1d-118">階段 2： 設定並測試動態群組成員資格和自動授權</span><span class="sxs-lookup"><span data-stu-id="87e1d-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="87e1d-119">首先，您建立新的 「 業務 」 群組，並新增動態群組成員資格規則，以便與設定為銷售部門的使用者帳戶會自動新增至 「 業務 」 群組。</span><span class="sxs-lookup"><span data-stu-id="87e1d-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="87e1d-120">使用網際網路瀏覽器的私用執行個體，登入 Office 365 入口網站，網址[https://portal.office.com](https://portal.office.com)與您的 Microsoft 365 E5 的全域系統管理員帳戶測試實驗室訂閱。</span><span class="sxs-lookup"><span data-stu-id="87e1d-120">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="87e1d-121">在瀏覽器的個別索引標籤，移至 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="87e1d-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="87e1d-122">在 Azure 入口網站中，在 [搜尋] 方塊中，輸入**群組**，然後按一下 [**群組**]。</span><span class="sxs-lookup"><span data-stu-id="87e1d-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="87e1d-123">在 [**所有群組**] 窗格中，按一下 [**新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="87e1d-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="87e1d-124">在 [**群組類型**] 中，選取 [ **Office 365**]。</span><span class="sxs-lookup"><span data-stu-id="87e1d-124">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="87e1d-125">在 [**群組名稱**] 中，輸入 「**銷售額**」。</span><span class="sxs-lookup"><span data-stu-id="87e1d-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="87e1d-126">在 [**成員資格類型**] 中，選取 [**動態使用者**]。</span><span class="sxs-lookup"><span data-stu-id="87e1d-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="87e1d-127">按一下 [**動態使用者成員**。</span><span class="sxs-lookup"><span data-stu-id="87e1d-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="87e1d-128">在 [**動態成員資格的規則**] 窗格中：</span><span class="sxs-lookup"><span data-stu-id="87e1d-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="87e1d-129">選取 [**部門**] 內容。</span><span class="sxs-lookup"><span data-stu-id="87e1d-129">Select the **department** property.</span></span>
   - <span data-ttu-id="87e1d-130">選取 [**等於**運算子。</span><span class="sxs-lookup"><span data-stu-id="87e1d-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="87e1d-131">類型中的 [**銷售\*\*\*\*值**。</span><span class="sxs-lookup"><span data-stu-id="87e1d-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="87e1d-132">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="87e1d-132">Click **Save**.</span></span>
11. <span data-ttu-id="87e1d-133">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="87e1d-133">Click **Create**.</span></span>

<span data-ttu-id="87e1d-134">接下來，您設定 「 業務 」 群組，以便成員自動獲指派的 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="87e1d-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="87e1d-135">按一下 [**銷售**] 群組中，然後按一下 [**授權**]。</span><span class="sxs-lookup"><span data-stu-id="87e1d-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="87e1d-136">在 [**更新授權指派**] 窗格中，選取 [ **Microsoft 365 E5**，，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="87e1d-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="87e1d-137">關閉瀏覽器的 Azure 入口網站索引標籤。</span><span class="sxs-lookup"><span data-stu-id="87e1d-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="87e1d-138">接下來，您測試動態群組成員資格及使用者 4 帳戶上的自動授權。</span><span class="sxs-lookup"><span data-stu-id="87e1d-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="87e1d-139">從瀏覽器的 [ **Microsoft Office 的首頁**] 索引標籤按一下 [**系統**]。</span><span class="sxs-lookup"><span data-stu-id="87e1d-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="87e1d-140">從**Microsoft 365 系統管理中心**] 索引標籤上，按一下 [**作用中使用者**]。</span><span class="sxs-lookup"><span data-stu-id="87e1d-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="87e1d-141">在 [**作用中使用者**] 頁面上，按一下 [**使用者 4**帳戶。</span><span class="sxs-lookup"><span data-stu-id="87e1d-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="87e1d-142">在 [**使用者 4** ] 窗格中，按一下 [**編輯\*\*\*\*產品**授權。</span><span class="sxs-lookup"><span data-stu-id="87e1d-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="87e1d-143">在 [**產品授權**] 窗格中，停用**Microsoft 365 E5**授權，，然後按一下 [**儲存 > 關閉**。</span><span class="sxs-lookup"><span data-stu-id="87e1d-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="87e1d-144">在 [使用者 4 帳戶的內容，請確認已指派任何產品授權，且沒有任何群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="87e1d-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="87e1d-145">**連絡人資訊**，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="87e1d-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="87e1d-146">在 [**編輯連絡人資訊**] 窗格中，按一下 [**連絡人資訊**]。</span><span class="sxs-lookup"><span data-stu-id="87e1d-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="87e1d-147">在 [**部門**] 欄位中，輸入**銷售**]，然後按一下 [**儲存 > 關閉**。</span><span class="sxs-lookup"><span data-stu-id="87e1d-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="87e1d-148">請稍候幾分鐘，然後定期按一下右上角的 [使用者 4 的帳戶] 窗格中的重新整理圖示。</span><span class="sxs-lookup"><span data-stu-id="87e1d-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="87e1d-149">在時間應該會看到:</span><span class="sxs-lookup"><span data-stu-id="87e1d-149">In time you should see the:</span></span>

- <span data-ttu-id="87e1d-150">更新 「**業務**」 群組的**群組成員資格**屬性。</span><span class="sxs-lookup"><span data-stu-id="87e1d-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="87e1d-151">使用**Microsoft 365 E5**授權更新的**產品授權**屬性。</span><span class="sxs-lookup"><span data-stu-id="87e1d-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="87e1d-152">在身分識別階段中的資訊，以及部署動態群組成員資格和自動授權在生產環境中的連結，請參閱下列步驟：</span><span class="sxs-lookup"><span data-stu-id="87e1d-152">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="87e1d-153">設定自動授權</span><span class="sxs-lookup"><span data-stu-id="87e1d-153">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="87e1d-154">設定動態群組成員資格</span><span class="sxs-lookup"><span data-stu-id="87e1d-154">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="87e1d-155">下一步</span><span class="sxs-lookup"><span data-stu-id="87e1d-155">Next step</span></span>

<span data-ttu-id="87e1d-156">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="87e1d-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="87e1d-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="87e1d-157">See also</span></span>

[<span data-ttu-id="87e1d-158">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="87e1d-158">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="87e1d-159">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="87e1d-159">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="87e1d-160">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="87e1d-160">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="87e1d-161">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="87e1d-161">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
