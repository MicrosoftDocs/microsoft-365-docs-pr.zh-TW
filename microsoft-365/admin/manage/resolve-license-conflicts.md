---
title: 解決商務用 Office 365 中的授權衝突
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: 瞭解如何解決與商務用 Office 365 訂閱的授權衝突。
ms.openlocfilehash: 9dbd483b01566039cb227cd3d2f086c3f6e34be5
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212290"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a><span data-ttu-id="a3e09-103">解決商務用 Office 365 中的授權衝突</span><span class="sxs-lookup"><span data-stu-id="a3e09-103">Resolve license conflicts in Office 365 for business</span></span>

<span data-ttu-id="a3e09-104">建議您先購買訂閱所需的授權，再建立新的使用者。</span><span class="sxs-lookup"><span data-stu-id="a3e09-104">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="a3e09-105">如此一來，就能在建立使用者帳戶時，將授權指派給新的使用者。</span><span class="sxs-lookup"><span data-stu-id="a3e09-105">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="a3e09-106">如果您已經將所有授權指派給使用者，但其中有部分授權已過期，或是您嘗試移除已經指派給某位使用者的授權，將會發生授權衝突。</span><span class="sxs-lookup"><span data-stu-id="a3e09-106">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="a3e09-107">如需詳細資訊，請參閱[從您的訂閱中移除授權](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a3e09-107">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="a3e09-108">如何查看授權衝突？</span><span class="sxs-lookup"><span data-stu-id="a3e09-108">How do I view license conflicts?</span></span>

1. <span data-ttu-id="a3e09-109">在系統管理中心中，移至 [**帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a3e09-109">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="a3e09-110">如果您使用的是 Office 365 德國，請移至 [<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a3e09-110">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="a3e09-111">如果您使用的是由世紀運作的 Office 365，請移至 [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a3e09-111">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="a3e09-112">檢查 [**狀態**] 欄，以取得與衝突相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="a3e09-112">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="a3e09-113">如果發生衝突，您會看到一則警告訊息，指出一或多個使用者需要有效的授權。</span><span class="sxs-lookup"><span data-stu-id="a3e09-113">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3e09-114">如果沒有衝突，您就不會看到 [**狀態**] 欄。</span><span class="sxs-lookup"><span data-stu-id="a3e09-114">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="a3e09-115">如何解決授權衝突？</span><span class="sxs-lookup"><span data-stu-id="a3e09-115">How do I resolve license conflicts?</span></span>

<span data-ttu-id="a3e09-116">您可以從[購買更多授權](../../commerce/licenses/buy-licenses.md)或[從不再需要授權的使用者中移除](remove-licenses-from-users.md)授權，來解決授權衝突。</span><span class="sxs-lookup"><span data-stu-id="a3e09-116">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="a3e09-117">您可以選擇性地[刪除使用者帳戶以釋出授權](../add-users/delete-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="a3e09-117">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="a3e09-118">相關文章</span><span class="sxs-lookup"><span data-stu-id="a3e09-118">Related articles</span></span> 

[<span data-ttu-id="a3e09-119">將授權指派給使用者</span><span class="sxs-lookup"><span data-stu-id="a3e09-119">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="a3e09-120">從使用者移除授權</span><span class="sxs-lookup"><span data-stu-id="a3e09-120">Remove licenses from users</span></span>](remove-licenses-from-users.md)
