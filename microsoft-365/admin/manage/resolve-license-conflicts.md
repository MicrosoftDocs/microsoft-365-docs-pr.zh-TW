---
title: 解決授權衝突
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: 瞭解如何解決與 Microsoft 365 for business 訂閱的授權衝突。
ms.openlocfilehash: 284a6b169c02314dd2bbd0e13c10c081cb50f58d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114450"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="7598d-103">解決授權衝突</span><span class="sxs-lookup"><span data-stu-id="7598d-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7598d-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="7598d-104">The admin center is changing.</span></span> <span data-ttu-id="7598d-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true) (英文)。</span><span class="sxs-lookup"><span data-stu-id="7598d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="7598d-106">建議您先購買訂閱所需的授權，再建立新的使用者。</span><span class="sxs-lookup"><span data-stu-id="7598d-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="7598d-107">如此一來，就能在建立使用者帳戶時，將授權指派給新的使用者。</span><span class="sxs-lookup"><span data-stu-id="7598d-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="7598d-108">如果您已經將所有授權指派給使用者，但其中有部分授權已過期，或是您嘗試移除已經指派給某位使用者的授權，將會發生授權衝突。</span><span class="sxs-lookup"><span data-stu-id="7598d-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="7598d-109">如需詳細資訊，請參閱 [從您的訂閱中移除授權](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="7598d-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="7598d-110">如何查看授權衝突？</span><span class="sxs-lookup"><span data-stu-id="7598d-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7598d-111">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="7598d-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7598d-112">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="7598d-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7598d-113">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="7598d-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="7598d-114">檢查 [ **狀態** ] 欄，以取得與衝突相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="7598d-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="7598d-115">如果發生衝突，您會看到一則警告訊息，指出一或多個使用者需要有效的授權。</span><span class="sxs-lookup"><span data-stu-id="7598d-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7598d-116">如果沒有衝突，您就不會看到 [ **狀態** ] 欄。</span><span class="sxs-lookup"><span data-stu-id="7598d-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="7598d-117">如何解決授權衝突？</span><span class="sxs-lookup"><span data-stu-id="7598d-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="7598d-118">您可以從 [購買更多授權](../../commerce/licenses/buy-licenses.md) 或 [從不再需要授權的使用者中移除](remove-licenses-from-users.md)授權，來解決授權衝突。</span><span class="sxs-lookup"><span data-stu-id="7598d-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="7598d-119">您可以選擇性地[刪除使用者帳戶以釋出授權](../add-users/delete-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="7598d-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="7598d-120">相關文章</span><span class="sxs-lookup"><span data-stu-id="7598d-120">Related articles</span></span>

[<span data-ttu-id="7598d-121">將授權指派給使用者</span><span class="sxs-lookup"><span data-stu-id="7598d-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="7598d-122">從使用者移除授權</span><span class="sxs-lookup"><span data-stu-id="7598d-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
