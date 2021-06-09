---
title: 從共用信箱中移除授權
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: '從共用信箱中移除授權，將其指派給另一位使用者或傳回授權，這樣您就不需要付費。 '
ms.date: 05/11/2021
ms.openlocfilehash: dd2d99d762a4a68a9b0400353d64dabb536a891c
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821425"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="b8ff2-103">從共用信箱移除授權</span><span class="sxs-lookup"><span data-stu-id="b8ff2-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="b8ff2-104">共用信箱通常不需要授權。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="b8ff2-105">請遵循下列指示，從共用信箱中移除授權，以便將其指派給使用者或傳回授權，這樣您就不會支付您不需要的授權。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="b8ff2-106">下列案例中需要授權：</span><span class="sxs-lookup"><span data-stu-id="b8ff2-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="b8ff2-107">共用信箱使用的儲存空間超過 50 GB。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="b8ff2-108">共用信箱使用就地封存。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="b8ff2-109">共用信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="b8ff2-110">共用信箱已指派 Microsoft Defender 授權。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="b8ff2-111">移除授權</span><span class="sxs-lookup"><span data-stu-id="b8ff2-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b8ff2-112">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="b8ff2-113">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b8ff2-114">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

   > [!NOTE]
   > <span data-ttu-id="b8ff2-115">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b8ff2-116">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="b8ff2-117">選取共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="b8ff2-118">一個 [ **授權與應用程式** ] 索引標籤，展開 [ **授權** ]，然後取消選取您要移除之授權的方塊。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="b8ff2-119">選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="b8ff2-120">當您回到 [作用中 **使用者** ] 頁面時，共用信箱的狀態將會是 [未 **授權**]。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b8ff2-121">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-121">You're still paying for the license.</span></span> <span data-ttu-id="b8ff2-122">若要停止付費，請 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="b8ff2-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="b8ff2-123">相關內容</span><span class="sxs-lookup"><span data-stu-id="b8ff2-123">Related content</span></span>

<span data-ttu-id="b8ff2-124">[關於共用信箱](about-shared-mailboxes.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="b8ff2-124">[About shared mailboxes](about-shared-mailboxes.md) (article)\</span></span>
<span data-ttu-id="b8ff2-125">[建立共用信箱](create-a-shared-mailbox.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="b8ff2-125">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="b8ff2-126">[設定共用信箱](configure-a-shared-mailbox.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="b8ff2-126">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)\</span></span>
<span data-ttu-id="b8ff2-127">[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="b8ff2-127">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)\</span></span>
<span data-ttu-id="b8ff2-128">[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="b8ff2-128">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>
