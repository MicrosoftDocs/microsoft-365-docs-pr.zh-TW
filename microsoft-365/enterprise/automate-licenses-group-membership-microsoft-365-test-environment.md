---
title: 自動化 Microsoft 365 企業版測試環境的授權與群組成員資格
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: 在 Microsoft 365 企業版測試環境中設定群組型授權和動態群組成員資格。
ms.openlocfilehash: 45a78af202f2d9ab029683aae4d95ed9a3370b08
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866507"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="06d73-103">自動化 Microsoft 365 企業版測試環境的授權與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="06d73-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="06d73-p101">群組型自動授權指派或移除授權根據群組成員資格的使用者帳戶。動態群組成員資格新增或移除使用者帳戶屬性，例如部門或國家 （地區） 為基礎的群組成員。本文會引導您完成兩者 Microsoft 365 企業版測試環境中的示範。</span><span class="sxs-lookup"><span data-stu-id="06d73-p101">Group-based licensing automatically assigns or removes licenses for a user account based on group membership. Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country. This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="06d73-107">有兩個階段來設定 Microsoft 365 企業版測試環境中的自動授權和動態群組成員資格：</span><span class="sxs-lookup"><span data-stu-id="06d73-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="06d73-108">建立 Microsoft 365 企業版的測試環境。</span><span class="sxs-lookup"><span data-stu-id="06d73-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="06d73-109">設定和測試動態群組成員資格與自動授權。</span><span class="sxs-lookup"><span data-stu-id="06d73-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="06d73-111">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="06d73-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="06d73-112">階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境</span><span class="sxs-lookup"><span data-stu-id="06d73-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="06d73-113">如果您只是要測試的基本需求的輕量型方式的自動授權與群組成員資格，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="06d73-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="06d73-114">如果您想要測試模擬企業中的自動授權與群組成員資格，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="06d73-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="06d73-p102">測試自動化授權和群組成員資格不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="06d73-p102">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="06d73-117">階段 2： 設定和測試動態群組成員資格與自動授權</span><span class="sxs-lookup"><span data-stu-id="06d73-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="06d73-118">首先，您建立新的銷售群組並新增動態群組成員資格規則以便與設為銷售部門的使用者帳戶會自動新增至 [銷售] 群組。</span><span class="sxs-lookup"><span data-stu-id="06d73-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="06d73-119">使用網際網路瀏覽器的私人執行個體，請登入 Office 入口網站[https://office.com](https://office.com)與您的 Office 365 E5 試用版訂閱的全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="06d73-119">Using a private instance of your Internet browser, sign in to the Office portal at [https://office.com](https://office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="06d73-120">在瀏覽器中的個別] 索引標籤上移至 Azure 入口網站[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="06d73-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="06d73-121">在 Azure 入口網站中，按一下 [Azure Active Directory] > [使用者和群組] > [所有群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06d73-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="06d73-122">在**所有群組**blade 中，按一下 [**新群組**。</span><span class="sxs-lookup"><span data-stu-id="06d73-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="06d73-123">在**群組類型**] 中選取 [ **Office 365**]。</span><span class="sxs-lookup"><span data-stu-id="06d73-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="06d73-124">在 [**群組名稱**] 中，輸入 「**銷售額**」。</span><span class="sxs-lookup"><span data-stu-id="06d73-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="06d73-125">在 [**成員資格類型**選取**動態的使用者**。</span><span class="sxs-lookup"><span data-stu-id="06d73-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="06d73-126">按一下 [新增動態查詢]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06d73-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="06d73-127">在 [新增使用者位置]\*\*\*\*，請選取 [部門]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06d73-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="06d73-128">在下一個欄位中，選取 [等於]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06d73-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="06d73-129">在 [下一步] 欄位中輸入 「**銷售額**」。</span><span class="sxs-lookup"><span data-stu-id="06d73-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="06d73-130">按一下 [新增查詢]\*\*\*\*，然後按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06d73-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="06d73-131">關閉**群組**及**群組所有群組**刀。</span><span class="sxs-lookup"><span data-stu-id="06d73-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="06d73-132">接下來，設定 [銷售] 群組，讓成員會自動指派 Office 365 E5 和 Enterprise 行動性 + 安全性 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="06d73-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="06d73-133">在 Azure Active Directory**概觀 （英文)** blade，按一下 [**授權 > 所有產品**。</span><span class="sxs-lookup"><span data-stu-id="06d73-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="06d73-134">在清單中，選取 [Enterprise Mobility + Security E5]\*\*\*\* 和 [Office 365 企業版 E5]\*\*\*\*，然後按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06d73-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="06d73-135">在**指派授權給**blade，按一下 [**使用者與群組**]。</span><span class="sxs-lookup"><span data-stu-id="06d73-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="06d73-136">在群組清單中，選取 [**銷售**] 群組。</span><span class="sxs-lookup"><span data-stu-id="06d73-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="06d73-137">按一下 [選取]\*\*\*\*，然後按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06d73-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="06d73-138">關閉瀏覽器的 Azure 入口網站索引標籤。</span><span class="sxs-lookup"><span data-stu-id="06d73-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="06d73-139">接下來，測試動態群組成員資格和使用者 4 帳戶上的自動授權。</span><span class="sxs-lookup"><span data-stu-id="06d73-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="06d73-140">從您的瀏覽器的 [ **Microsoft Office Home** ] 索引標籤按一下 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="06d73-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="06d73-141">從**Office 系統管理中心**] 索引標籤上，按一下 [**作用中使用者**]。</span><span class="sxs-lookup"><span data-stu-id="06d73-141">From the **Office Admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="06d73-142">在 [**作用中使用者**] 頁面上，按一下 [**使用者 4**帳戶。</span><span class="sxs-lookup"><span data-stu-id="06d73-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="06d73-143">在 [**使用者 4** ] 窗格中，按一下 [**編輯\*\*\*\*產品**授權。</span><span class="sxs-lookup"><span data-stu-id="06d73-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="06d73-144">在 [**產品授權**] 窗格中開啟**企業行動性 + 安全性 E5**和**Office 365 企業版 E5**授權 off、] 和 [**儲存 > 關閉**。</span><span class="sxs-lookup"><span data-stu-id="06d73-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="06d73-145">在使用者 4 帳戶的屬性，確認已指派任何產品授權有無群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="06d73-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="06d73-146">按一下 [取得**連絡人資訊**的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="06d73-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="06d73-147">在 [**編輯連絡人資訊**] 窗格中，按一下 [**連絡人資訊**。</span><span class="sxs-lookup"><span data-stu-id="06d73-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="06d73-148">在 [**部門**] 欄位中輸入 [**銷售**] 和 [**儲存 > 關閉**。</span><span class="sxs-lookup"><span data-stu-id="06d73-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="06d73-149">等候數分鐘和定期 [右上方的 [使用者 4 帳戶] 窗格中的 [重新整理] 圖示。</span><span class="sxs-lookup"><span data-stu-id="06d73-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="06d73-150">您應該在時間中會看到：</span><span class="sxs-lookup"><span data-stu-id="06d73-150">In time you should see the:</span></span>

- <span data-ttu-id="06d73-151">更新 [**銷售**] 群組的**群組成員資格**屬性。</span><span class="sxs-lookup"><span data-stu-id="06d73-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="06d73-152">更新**企業行動性 + 安全性 E5**和**Office 365 企業版 E5**授權的**產品授權**屬性。</span><span class="sxs-lookup"><span data-stu-id="06d73-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="06d73-153">請參閱下列步驟中的 「 身分識別 」 階段的資訊及連結部署動態群組成員資格與在生產環境中的自動授權：</span><span class="sxs-lookup"><span data-stu-id="06d73-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="06d73-154">設定自動授權</span><span class="sxs-lookup"><span data-stu-id="06d73-154">Set up automatic licensing</span></span>](identity-group-based-licensing.md)
- [<span data-ttu-id="06d73-155">設定動態群組成員資格</span><span class="sxs-lookup"><span data-stu-id="06d73-155">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md)

## <a name="next-step"></a><span data-ttu-id="06d73-156">下一步</span><span class="sxs-lookup"><span data-stu-id="06d73-156">Next step</span></span>

<span data-ttu-id="06d73-157">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="06d73-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="06d73-158">另請參閱</span><span class="sxs-lookup"><span data-stu-id="06d73-158">See also</span></span>

[<span data-ttu-id="06d73-159">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="06d73-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="06d73-160">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="06d73-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="06d73-161">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="06d73-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="06d73-162">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="06d73-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
