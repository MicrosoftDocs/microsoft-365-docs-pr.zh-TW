---
title: 管理授權要求
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: 瞭解如何針對您的 Microsoft 365 訂閱，複查和核准或拒絕來自使用者的授權要求。
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597649"
---
# <a name="manage-license-requests"></a><span data-ttu-id="87a5d-103">管理授權要求</span><span class="sxs-lookup"><span data-stu-id="87a5d-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="87a5d-104">本文中的資訊僅適用于自助購買產品。</span><span class="sxs-lookup"><span data-stu-id="87a5d-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="87a5d-105">若要深入瞭解，請參閱[自助購買常見問題](../subscriptions/self-service-purchase-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="87a5d-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="87a5d-106">如果您在組織中停用自助購買，您可以使用授權要求來管理使用者的授權要求。</span><span class="sxs-lookup"><span data-stu-id="87a5d-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="87a5d-107">當使用者嘗試為已封鎖的產品進行自助購買時，他們可以將授權要求送出給您，以供系統管理員使用。當他們提出要求時，他們可以新增也需要產品授權的其他使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="87a5d-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="87a5d-108">如果您封鎖使用者進行自助購買，Microsoft 不會傳送行銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="87a5d-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="87a5d-109">此外，如果他們使用產品的試用版，他們就不會看到要購買的提示。</span><span class="sxs-lookup"><span data-stu-id="87a5d-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="87a5d-110">若要深入瞭解，請參閱[管理自助購買 (系統管理) ](../subscriptions/manage-self-service-purchases-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="87a5d-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="87a5d-111">若要查看及管理授權要求，系統管理員會使用**授權**頁面上的 [**要求**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="87a5d-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="87a5d-112">清單會顯示要求的產品名稱、要求授權的人員名稱、要求的日期，以及要求的狀態。</span><span class="sxs-lookup"><span data-stu-id="87a5d-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="87a5d-113">系統管理員可以篩選清單，以顯示擱置或已完成的要求。</span><span class="sxs-lookup"><span data-stu-id="87a5d-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="87a5d-114">要求會保留30天。</span><span class="sxs-lookup"><span data-stu-id="87a5d-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="87a5d-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="87a5d-115">Before you begin</span></span>

<span data-ttu-id="87a5d-116">您必須是全域系統管理員，才可執行本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="87a5d-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="87a5d-117">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="87a5d-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="87a5d-118">使用您自己的要求程式</span><span class="sxs-lookup"><span data-stu-id="87a5d-118">Use your own request process</span></span>

<span data-ttu-id="87a5d-119">如果您的組織有其自己的要求程式，您可以改為使用它。</span><span class="sxs-lookup"><span data-stu-id="87a5d-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="87a5d-120">當使用者要求授權時，您會建立要向使用者顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="87a5d-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87a5d-121">如果您使用自己的要求程式，[**要求**] 索引標籤上不會顯示任何要求。您新增郵件之前的現有要求仍會出現，直到您核准或拒絕。</span><span class="sxs-lookup"><span data-stu-id="87a5d-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="87a5d-122">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面，然後選取 [**要求**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="87a5d-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="87a5d-123">選取 [**使用現有的要求處理常式**]。</span><span class="sxs-lookup"><span data-stu-id="87a5d-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="87a5d-124">在右窗格的 [**消息**] 方塊中，輸入您希望使用者在要求授權時看到的訊息。</span><span class="sxs-lookup"><span data-stu-id="87a5d-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="87a5d-125">如果您也想要包含組織原則或其他檔的連結，請在 [檔的連結] 中，輸入 URL \*\* (選用) \*\* ] 文字方塊。</span><span class="sxs-lookup"><span data-stu-id="87a5d-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="87a5d-126">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="87a5d-126">Select **Save**.</span></span>

<span data-ttu-id="87a5d-127">當您回到 [**要求**] 清單時，您會看到**您使用的是您自己的授權要求程式**的訊息。</span><span class="sxs-lookup"><span data-stu-id="87a5d-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="87a5d-128">若要對傳送給使用者的郵件進行變更，請選取 [**使用現有的要求處理常式**]。</span><span class="sxs-lookup"><span data-stu-id="87a5d-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="87a5d-129">停止使用您自己的要求過程</span><span class="sxs-lookup"><span data-stu-id="87a5d-129">Stop using your own request process</span></span>

1. <span data-ttu-id="87a5d-130">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面，然後選取 [**要求**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="87a5d-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="87a5d-131">選取 [**使用現有的要求處理常式**]。</span><span class="sxs-lookup"><span data-stu-id="87a5d-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="87a5d-132">在右窗格中，清除 [**使用我的組織的要求處理**程式] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="87a5d-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="87a5d-133">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="87a5d-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="87a5d-134">核准或拒絕授權要求</span><span class="sxs-lookup"><span data-stu-id="87a5d-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="87a5d-135">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面，然後選取 [**要求**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="87a5d-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="87a5d-136">選取包含您要審閱之要求的列。</span><span class="sxs-lookup"><span data-stu-id="87a5d-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="87a5d-137">右窗格會顯示使用者要授權的產品詳細資料。</span><span class="sxs-lookup"><span data-stu-id="87a5d-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="87a5d-138">若要拒絕整個要求，請選取 [**不核准**]，然後在對話方塊中，選取 [**不核准**]。</span><span class="sxs-lookup"><span data-stu-id="87a5d-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="87a5d-139">若要拒絕某些使用者要求，但核准其他使用者，請依您要移除的使用者名稱選取 X。</span><span class="sxs-lookup"><span data-stu-id="87a5d-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="87a5d-140">其名稱會在 [不**指派給這些使用者**] 下移動。</span><span class="sxs-lookup"><span data-stu-id="87a5d-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="87a5d-141">如果您有一個以上的產品，請在 [**選取產品**] 底下，選取您要用來指派授權的一種產品。</span><span class="sxs-lookup"><span data-stu-id="87a5d-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="87a5d-142">若要拒絕使用者存取特定的應用程式和服務，請展開 [**開啟或關閉應用程式和服務**]，然後清除您要排除的應用程式和服務核取方塊。</span><span class="sxs-lookup"><span data-stu-id="87a5d-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="87a5d-143">在窗格的底部，于文字方塊中輸入選用的訊息。</span><span class="sxs-lookup"><span data-stu-id="87a5d-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="87a5d-144">完成後，請選取 [**核准**]。</span><span class="sxs-lookup"><span data-stu-id="87a5d-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="87a5d-145">右窗格會顯示要求的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="87a5d-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="87a5d-146">關閉右窗格。</span><span class="sxs-lookup"><span data-stu-id="87a5d-146">Close the right pane.</span></span>
    <span data-ttu-id="87a5d-147">使用者會收到一封電子郵件，告知其要求已核准或遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="87a5d-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="87a5d-148">相關內容</span><span class="sxs-lookup"><span data-stu-id="87a5d-148">Related content</span></span>

<span data-ttu-id="87a5d-149"> (篇文章) \[中指派授權給使用者](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="87a5d-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="87a5d-150">[將使用者移至其他訂閱](../subscriptions/move-users-different-subscription.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="87a5d-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="87a5d-151"> (文章) [購買或移除訂閱授權](buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="87a5d-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>