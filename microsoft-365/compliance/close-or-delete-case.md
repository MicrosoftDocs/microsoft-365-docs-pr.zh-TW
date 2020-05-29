---
title: 關閉或刪除案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解當已關閉或刪除高級 eDiscovery 案例所支援的調查或法律案例時，會發生什麼事。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: be8d133a8215fc40c6d33025f9f4d1dee0f3b609
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412782"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="fefda-103">關閉或刪除高級 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="fefda-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="fefda-104">當高級 eDiscovery 案例所支援的法律案例或調查完成時，您可以關閉或刪除案例。</span><span class="sxs-lookup"><span data-stu-id="fefda-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="fefda-105">您也可以重新開啟已關閉的案例。</span><span class="sxs-lookup"><span data-stu-id="fefda-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="fefda-106">關閉案例</span><span class="sxs-lookup"><span data-stu-id="fefda-106">Close a case</span></span>

<span data-ttu-id="fefda-107">以下是當您關閉高級 eDiscovery 案例時會發生的情況：</span><span class="sxs-lookup"><span data-stu-id="fefda-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="fefda-108">如果案例包含保留的任何內容位置，將會關閉那些保留。</span><span class="sxs-lookup"><span data-stu-id="fefda-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="fefda-109">關閉關閉後，30天的寬限期（稱為*延遲保留*）會套用到保留中的內容位置。</span><span class="sxs-lookup"><span data-stu-id="fefda-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="fefda-110">這有助於防止內容立即刪除，並可讓系統管理員在延遲保留期間到期時，搜尋或復原將會永久刪除的內容。</span><span class="sxs-lookup"><span data-stu-id="fefda-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="fefda-111">如需詳細資訊，請參閱[移除 eDiscovery 保留中的內容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="fefda-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="fefda-112">關閉案例只會關閉與該案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="fefda-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="fefda-113">如果有其他保留內容位置（例如訴訟暫止、核心 eDiscovery 保留，或來自不同高級 eDiscovery 案例的保留），則仍會保留這些保留。</span><span class="sxs-lookup"><span data-stu-id="fefda-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="fefda-114">此案例仍列在 Microsoft 365 規範中心的 eDiscovery 頁面上。</span><span class="sxs-lookup"><span data-stu-id="fefda-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fefda-115">已關閉案例的詳細資料、保留、搜尋及成員都會保留。</span><span class="sxs-lookup"><span data-stu-id="fefda-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="fefda-116">您可以在關閉案例後進行編輯。</span><span class="sxs-lookup"><span data-stu-id="fefda-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="fefda-117">例如，您可以在高級 eDiscovery 中新增或移除成員、建立搜尋、匯出搜尋結果，以及準備用於分析的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="fefda-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="fefda-118">使用中案例和關閉案例之間的主要差異是關閉案例時關閉保留狀態。</span><span class="sxs-lookup"><span data-stu-id="fefda-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="fefda-119">若要關閉案例：</span><span class="sxs-lookup"><span data-stu-id="fefda-119">To close a case:</span></span>

1. <span data-ttu-id="fefda-120">在 [**高級電子**檔探索] 頁面上，選取您要關閉的案例。</span><span class="sxs-lookup"><span data-stu-id="fefda-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="fefda-121">在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="fefda-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="fefda-122">按一下 [**關閉案例**]。</span><span class="sxs-lookup"><span data-stu-id="fefda-122">Click **Close case**.</span></span>

   <span data-ttu-id="fefda-123">完成關閉程式可能需要長達60分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="fefda-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="fefda-124">重新開啟已關閉的案例</span><span class="sxs-lookup"><span data-stu-id="fefda-124">Reopen a closed case</span></span>

<span data-ttu-id="fefda-125">當您重新開啟高級 eDiscovery 案例時，在關閉案例時，任何已就地保留的保留都不會自動復原。</span><span class="sxs-lookup"><span data-stu-id="fefda-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="fefda-126">在重新開啟案例之後，您必須移至 [**保留**] 索引標籤，並開啟先前的保留。</span><span class="sxs-lookup"><span data-stu-id="fefda-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="fefda-127">若要開啟保留，請選取它以顯示飛入頁面，然後將**狀態**切換設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="fefda-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="fefda-128">若要重新開啟已關閉的案例：</span><span class="sxs-lookup"><span data-stu-id="fefda-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="fefda-129">在 [**高級電子**檔探索] 頁面上，選取您要刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="fefda-129">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="fefda-130">在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="fefda-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="fefda-131">按一下 [**重新開啟案例**]。</span><span class="sxs-lookup"><span data-stu-id="fefda-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="fefda-132">最多可能需要60分鐘的時間，重新開啟程式才會完成。</span><span class="sxs-lookup"><span data-stu-id="fefda-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="fefda-133">刪除案例</span><span class="sxs-lookup"><span data-stu-id="fefda-133">Delete a case</span></span>

<span data-ttu-id="fefda-134">您可以刪除現用和關閉的高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="fefda-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="fefda-135">當您刪除案例時，所有與案例相關聯的元件（例如保管人清單、通訊、搜尋、複查集和匯出工作）都會遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="fefda-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="fefda-136">案例會從 Microsoft 365 規範中心的 [**高級 eDiscovery** ] 頁面上的案例清單中移除。</span><span class="sxs-lookup"><span data-stu-id="fefda-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fefda-137">您無法復原或重新開啟已刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="fefda-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="fefda-138">在資料外泄案例中，移除考核集內專案的唯一方法是刪除高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="fefda-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="fefda-139">其他的「搜尋及清除」方法不會從審閱集中移除專案。</span><span class="sxs-lookup"><span data-stu-id="fefda-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="fefda-140">在您可以刪除案例之前（不論是作用中或已關閉），您必須先刪除與案例相關聯的*所有*保留。</span><span class="sxs-lookup"><span data-stu-id="fefda-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="fefda-141">這包括刪除狀態為**Off**的保留。</span><span class="sxs-lookup"><span data-stu-id="fefda-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="fefda-142">若要刪除與案例相關聯的保留：</span><span class="sxs-lookup"><span data-stu-id="fefda-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="fefda-143">在您要刪除的高級 eDiscovery 案例中，移至 [**保留**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="fefda-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="fefda-144">按一下您要刪除的保留。</span><span class="sxs-lookup"><span data-stu-id="fefda-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="fefda-145">在飛入頁面上，按一下 [**刪除保留**]。</span><span class="sxs-lookup"><span data-stu-id="fefda-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="fefda-146">若要刪除案例：</span><span class="sxs-lookup"><span data-stu-id="fefda-146">To delete a case:</span></span>

1. <span data-ttu-id="fefda-147">在 [**高級電子**檔探索] 頁面上，選取您要刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="fefda-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="fefda-148">在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="fefda-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="fefda-149">按一下 [**刪除案例**]。</span><span class="sxs-lookup"><span data-stu-id="fefda-149">Click **Delete case**.</span></span>
