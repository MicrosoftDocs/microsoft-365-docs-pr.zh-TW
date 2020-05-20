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
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292409"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="fb374-103">關閉或刪除高級 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="fb374-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="fb374-104">當高級 eDiscovery 案例所支援的法律案例或調查完成時，您可以關閉或刪除案例。</span><span class="sxs-lookup"><span data-stu-id="fb374-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="fb374-105">您也可以重新開啟已關閉的案例。</span><span class="sxs-lookup"><span data-stu-id="fb374-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="fb374-106">關閉案例</span><span class="sxs-lookup"><span data-stu-id="fb374-106">Close a case</span></span>

<span data-ttu-id="fb374-107">以下是當您關閉高級 eDiscovery 案例時會發生的情況：</span><span class="sxs-lookup"><span data-stu-id="fb374-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="fb374-108">如果案例包含保留的任何內容位置，將會關閉那些保留。</span><span class="sxs-lookup"><span data-stu-id="fb374-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="fb374-109">這可能會導致內容被使用者或自動化程式（如刪除原則）永久刪除或清除。</span><span class="sxs-lookup"><span data-stu-id="fb374-109">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="fb374-110">關閉案例只會關閉與該案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="fb374-110">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="fb374-111">如果有其他保留內容位置（例如訴訟暫止、核心 eDiscovery 保留，或來自不同高級 eDiscovery 案例的保留），則仍會保留這些保留。</span><span class="sxs-lookup"><span data-stu-id="fb374-111">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="fb374-112">此案例仍列在 Microsoft 365 規範中心的 eDiscovery 頁面上。</span><span class="sxs-lookup"><span data-stu-id="fb374-112">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fb374-113">已關閉案例的詳細資料、保留、搜尋及成員都會保留。</span><span class="sxs-lookup"><span data-stu-id="fb374-113">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="fb374-114">您可以在關閉案例後進行編輯。</span><span class="sxs-lookup"><span data-stu-id="fb374-114">You can edit a case after it's closed.</span></span> <span data-ttu-id="fb374-115">例如，您可以在高級 eDiscovery 中新增或移除成員、建立搜尋、匯出搜尋結果，以及準備用於分析的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="fb374-115">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="fb374-116">使用中案例和關閉案例之間的主要差異是關閉案例時關閉保留狀態。</span><span class="sxs-lookup"><span data-stu-id="fb374-116">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="fb374-117">若要關閉案例：</span><span class="sxs-lookup"><span data-stu-id="fb374-117">To close a case:</span></span>

1. <span data-ttu-id="fb374-118">在 [**高級電子**檔探索] 頁面上，選取您要關閉的案例。</span><span class="sxs-lookup"><span data-stu-id="fb374-118">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="fb374-119">在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="fb374-119">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="fb374-120">按一下 [**關閉案例**]。</span><span class="sxs-lookup"><span data-stu-id="fb374-120">Click **Close case**.</span></span>

   <span data-ttu-id="fb374-121">完成關閉程式可能需要長達60分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="fb374-121">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="fb374-122">重新開啟已關閉的案例</span><span class="sxs-lookup"><span data-stu-id="fb374-122">Reopen a closed case</span></span>

<span data-ttu-id="fb374-123">當您重新開啟高級 eDiscovery 案例時，在關閉案例時，任何已就地保留的保留都不會自動復原。</span><span class="sxs-lookup"><span data-stu-id="fb374-123">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="fb374-124">在重新開啟案例之後，您必須移至 [**保留**] 索引標籤，並開啟先前的保留。</span><span class="sxs-lookup"><span data-stu-id="fb374-124">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="fb374-125">若要開啟保留，請選取它以顯示飛入頁面，然後將**狀態**切換設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="fb374-125">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="fb374-126">若要重新開啟已關閉的案例：</span><span class="sxs-lookup"><span data-stu-id="fb374-126">To reopen a closed case:</span></span>

1. <span data-ttu-id="fb374-127">在 [**高級電子**檔探索] 頁面上，選取您要刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="fb374-127">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="fb374-128">在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="fb374-128">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="fb374-129">按一下 [**重新開啟案例**]。</span><span class="sxs-lookup"><span data-stu-id="fb374-129">Click **Reopen case**.</span></span>

   <span data-ttu-id="fb374-130">最多可能需要60分鐘的時間，重新開啟程式才會完成。</span><span class="sxs-lookup"><span data-stu-id="fb374-130">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="fb374-131">刪除案例</span><span class="sxs-lookup"><span data-stu-id="fb374-131">Delete a case</span></span>

<span data-ttu-id="fb374-132">您可以刪除現用和關閉的高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="fb374-132">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="fb374-133">當您刪除案例時，所有與案例相關聯的元件（例如保管人清單、通訊、搜尋、複查集和匯出工作）都會遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="fb374-133">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="fb374-134">案例會從 Microsoft 365 規範中心的 [**高級 eDiscovery** ] 頁面上的案例清單中移除。</span><span class="sxs-lookup"><span data-stu-id="fb374-134">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fb374-135">您無法復原或重新開啟已刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="fb374-135">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="fb374-136">在資料外泄案例中，移除考核集內專案的唯一方法是刪除高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="fb374-136">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="fb374-137">其他的「搜尋及清除」方法不會從審閱集中移除專案。</span><span class="sxs-lookup"><span data-stu-id="fb374-137">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="fb374-138">在您可以刪除案例之前（不論是作用中或已關閉），您必須先刪除與案例相關聯的*所有*保留。</span><span class="sxs-lookup"><span data-stu-id="fb374-138">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="fb374-139">這包括刪除狀態為**Off**的保留。</span><span class="sxs-lookup"><span data-stu-id="fb374-139">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="fb374-140">若要刪除與案例相關聯的保留：</span><span class="sxs-lookup"><span data-stu-id="fb374-140">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="fb374-141">在您要刪除的高級 eDiscovery 案例中，移至 [**保留**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="fb374-141">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="fb374-142">按一下您要刪除的保留。</span><span class="sxs-lookup"><span data-stu-id="fb374-142">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="fb374-143">在飛入頁面上，按一下 [**刪除保留**]。</span><span class="sxs-lookup"><span data-stu-id="fb374-143">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="fb374-144">若要刪除案例：</span><span class="sxs-lookup"><span data-stu-id="fb374-144">To delete a case:</span></span>

1. <span data-ttu-id="fb374-145">在 [**高級電子**檔探索] 頁面上，選取您要刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="fb374-145">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="fb374-146">在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="fb374-146">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="fb374-147">按一下 [**刪除案例**]。</span><span class="sxs-lookup"><span data-stu-id="fb374-147">Click **Delete case**.</span></span>
