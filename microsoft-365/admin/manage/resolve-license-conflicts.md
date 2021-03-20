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
ms.openlocfilehash: e2b5daa71164b41825282bd5652549347b8307c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915179"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="47493-103">解決授權衝突</span><span class="sxs-lookup"><span data-stu-id="47493-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="47493-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="47493-104">The admin center is changing.</span></span> <span data-ttu-id="47493-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="47493-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="47493-106">建議您先購買訂閱所需的授權，再建立新的使用者。</span><span class="sxs-lookup"><span data-stu-id="47493-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="47493-107">如此一來，就能在建立使用者帳戶時，將授權指派給新的使用者。</span><span class="sxs-lookup"><span data-stu-id="47493-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="47493-108">如果您已經將所有授權指派給使用者，但其中有部分授權已過期，或是您嘗試移除已經指派給某位使用者的授權，將會發生授權衝突。</span><span class="sxs-lookup"><span data-stu-id="47493-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="47493-109">如需詳細資訊，請參閱 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="47493-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="47493-110">如何查看授權衝突？</span><span class="sxs-lookup"><span data-stu-id="47493-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="47493-111">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="47493-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="47493-112">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="47493-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="47493-113">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="47493-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="47493-114">檢查 [ **狀態** ] 欄，以取得與衝突相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="47493-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="47493-115">如果發生衝突，您會看到一則警告訊息，指出一或多個使用者需要有效的授權。</span><span class="sxs-lookup"><span data-stu-id="47493-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="47493-116">如果沒有衝突，您就不會看到 [ **狀態** ] 欄。</span><span class="sxs-lookup"><span data-stu-id="47493-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="47493-117">如何解決授權衝突？</span><span class="sxs-lookup"><span data-stu-id="47493-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="47493-118">您可以從 [購買更多授權](../../commerce/licenses/buy-licenses.md) 或 [從不再需要授權的使用者中移除](remove-licenses-from-users.md)授權，來解決授權衝突。</span><span class="sxs-lookup"><span data-stu-id="47493-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="47493-119">您可以選擇性地[刪除使用者帳戶以釋出授權](../add-users/delete-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="47493-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="47493-120">相關文章</span><span class="sxs-lookup"><span data-stu-id="47493-120">Related articles</span></span>

[<span data-ttu-id="47493-121">將授權指派給使用者</span><span class="sxs-lookup"><span data-stu-id="47493-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="47493-122">從使用者移除授權</span><span class="sxs-lookup"><span data-stu-id="47493-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)