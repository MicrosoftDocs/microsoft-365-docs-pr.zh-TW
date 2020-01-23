---
title: 測試人員風險管理使用者 （預覽）
description: 了解 Microsoft 365 中的測試人員風險管理使用者
keywords: Microsoft 365，測試人員風險管理、 風險管理、 合規性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5688d1554bc48632c3dca40dd33c65b4ea41ee20
ms.sourcegitcommit: ca06ee52dec472d3827983d67b049847ec2fdfc1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2020
ms.locfileid: "41256659"
---
# <a name="insider-risk-management-users-preview"></a><span data-ttu-id="94d0e-104">測試人員風險管理使用者 （預覽）</span><span class="sxs-lookup"><span data-stu-id="94d0e-104">Insider risk management users (preview)</span></span>

<span data-ttu-id="94d0e-105">測試人員風險管理使用者是員工在組織中所包含的一或多個測試人員風險管理原則。</span><span class="sxs-lookup"><span data-stu-id="94d0e-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="94d0e-106">若要快速檢閱員工的風險資訊，並將員工新增至現有的測試人員風險管理原則，請使用**使用者儀表板**。</span><span class="sxs-lookup"><span data-stu-id="94d0e-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="94d0e-107">測試人員風險管理原則中包含每個使用者有顯示在**使用者儀表板**上的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="94d0e-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="94d0e-108">**使用者**： 使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="94d0e-108">**Users**: The user name for a user.</span></span>
- <span data-ttu-id="94d0e-109">**風險層級**：</span><span class="sxs-lookup"><span data-stu-id="94d0e-109">**Risk level**:</span></span> 
- <span data-ttu-id="94d0e-110">**作用中警示**： 所有原則的作用中警示的數目。</span><span class="sxs-lookup"><span data-stu-id="94d0e-110">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="94d0e-111">**已確認違規**： 案例數目解析為使用者的 [*確認原則違規情形*。</span><span class="sxs-lookup"><span data-stu-id="94d0e-111">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="94d0e-112">**案例**： 使用者目前作用中的案例。</span><span class="sxs-lookup"><span data-stu-id="94d0e-112">**Case**: The current active case for the user.</span></span>

![測試人員風險管理使用者儀表板](media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="94d0e-114">檢視使用者的詳細資料</span><span class="sxs-lookup"><span data-stu-id="94d0e-114">View user details</span></span>

<span data-ttu-id="94d0e-115">若要檢視更多詳細風險活動的使用者，連按兩下**使用者儀表板**中的使用者開啟使用者的 [詳細資料] 窗格。</span><span class="sxs-lookup"><span data-stu-id="94d0e-115">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="94d0e-116">在 [詳細資料] 窗格中，您可以檢視下列資訊：</span><span class="sxs-lookup"><span data-stu-id="94d0e-116">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="94d0e-117">**使用者設定檔**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="94d0e-117">**User profile** tab</span></span>
    - <span data-ttu-id="94d0e-118">**名稱和職稱**： 使用者名稱和位置的標題。</span><span class="sxs-lookup"><span data-stu-id="94d0e-118">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="94d0e-119">**使用者的電子郵件**： 使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="94d0e-119">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="94d0e-120">**別名**： 使用者的網路別名。</span><span class="sxs-lookup"><span data-stu-id="94d0e-120">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="94d0e-121">**組織或部門**： 組織或部門的使用者。</span><span class="sxs-lookup"><span data-stu-id="94d0e-121">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="94d0e-122">**使用者活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="94d0e-122">**User activity** tab</span></span>
    - <span data-ttu-id="94d0e-123">**最近的使用者活動的歷程記錄**： 列出觸發事件與使用者活動的風險指標這兩個原則。</span><span class="sxs-lookup"><span data-stu-id="94d0e-123">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="94d0e-124">觸發的事件可能會接受放棄日期或最後一個排程的員工的工作。</span><span class="sxs-lookup"><span data-stu-id="94d0e-124">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="94d0e-125">風險指標是的活動，決定有風險的項目，而且會對應至使用者納入的原則。</span><span class="sxs-lookup"><span data-stu-id="94d0e-125">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="94d0e-126">與要先列出最新的項目會列出事件和風險活動。</span><span class="sxs-lookup"><span data-stu-id="94d0e-126">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="94d0e-127">將使用者新增至原則</span><span class="sxs-lookup"><span data-stu-id="94d0e-127">Add a user to a policy</span></span>

<span data-ttu-id="94d0e-128">若要將使用者新增至測試人員風險管理原則，您可以將 Microsoft 365 合規性中心**測試人員風險管理**解決方案中使用新的原則精靈] 或 [**使用者**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="94d0e-128">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="94d0e-129">完成下列步驟，以將使用者新增至現有的測試人員風險原則：</span><span class="sxs-lookup"><span data-stu-id="94d0e-129">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="94d0e-130">在[Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至**測試人員風險管理**並選取 [**使用者**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="94d0e-130">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="94d0e-131">在工具列上，選取 [**新增使用者至原則**。</span><span class="sxs-lookup"><span data-stu-id="94d0e-131">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="94d0e-132">在 [**新增使用者**] 對話方塊中，啟動 [**使用者**] 欄位中輸入使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="94d0e-132">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="94d0e-133">選取您想要新增至原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="94d0e-133">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="94d0e-134">選取要顯示設定的測試人員風險管理原則的**原則**欄位的下拉式箭號。</span><span class="sxs-lookup"><span data-stu-id="94d0e-134">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="94d0e-135">選取要新增至使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="94d0e-135">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="94d0e-136">使用**監控視窗**滑動軸控制來定義...][監視] 視窗中的範圍是 5 到 30 天。</span><span class="sxs-lookup"><span data-stu-id="94d0e-136">Use the **Monitoring window** slider control to define the...... The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="94d0e-137">選取 [**新增]** ，然後**確認**將使用者新增至原則。</span><span class="sxs-lookup"><span data-stu-id="94d0e-137">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
