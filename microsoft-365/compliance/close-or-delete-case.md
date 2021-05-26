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
description: 瞭解 Advanced eDiscovery 案例所支援的調查或法律案例關閉或刪除時會發生什麼情況。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657636"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="aef75-103">關閉或刪除 Advanced eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="aef75-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="aef75-104">當 Advanced eDiscovery 案例支援的法律案例或調查完成時，您可以關閉或刪除案例。</span><span class="sxs-lookup"><span data-stu-id="aef75-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="aef75-105">您也可以重新開啟已關閉的案例。</span><span class="sxs-lookup"><span data-stu-id="aef75-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="aef75-106">關閉案例</span><span class="sxs-lookup"><span data-stu-id="aef75-106">Close a case</span></span>

<span data-ttu-id="aef75-107">以下是關閉 Advanced eDiscovery 案例時會發生的情況：</span><span class="sxs-lookup"><span data-stu-id="aef75-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="aef75-108">如果案例包含處於保留狀態的內容位置，將會關閉這些保留。</span><span class="sxs-lookup"><span data-stu-id="aef75-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="aef75-109">關閉關閉後，30天的寬限期 (稱為 *延遲保留*) 會套用到保留的內容位置。</span><span class="sxs-lookup"><span data-stu-id="aef75-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="aef75-110">這有助於防止內容立即刪除，並可讓系統管理員在延遲保留期間到期時，搜尋或復原將會永久刪除的內容。</span><span class="sxs-lookup"><span data-stu-id="aef75-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="aef75-111">如需詳細資訊，請參閱 [移除 eDiscovery 保留中的內容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="aef75-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="aef75-112">將案例結案只會關閉與該案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="aef75-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="aef75-113">如果內容位置上有其他保留， (例如訴訟暫止、核心 eDiscovery 保留或不同 Advanced eDiscovery 案例的保留，) 仍會保留這些保留。</span><span class="sxs-lookup"><span data-stu-id="aef75-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="aef75-114">此案例仍會列在 Microsoft 365 規範中心的 eDiscovery 頁面上。</span><span class="sxs-lookup"><span data-stu-id="aef75-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="aef75-115">已結案案例的詳細資料、保留、搜尋和成員都會保留。</span><span class="sxs-lookup"><span data-stu-id="aef75-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="aef75-116">您可以在關閉案例後進行編輯。</span><span class="sxs-lookup"><span data-stu-id="aef75-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="aef75-117">例如，您可以在 Advanced eDiscovery 中新增或移除成員、建立搜尋、匯出搜尋結果，以及準備用於分析的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="aef75-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="aef75-118">作用中案例與已關閉案例的主要差異在於，案例關閉時會關閉保留。</span><span class="sxs-lookup"><span data-stu-id="aef75-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="aef75-119">若要關閉案例：</span><span class="sxs-lookup"><span data-stu-id="aef75-119">To close a case:</span></span>

1. <span data-ttu-id="aef75-120">在 [進階電子文件探索]\*\*\*\* 頁面上，選取您想要關閉的案例。</span><span class="sxs-lookup"><span data-stu-id="aef75-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="aef75-121">在 [設定]\*\*\*\* 索引標籤上，按一下 [案例資訊]\*\*\*\* 底下的 \*\*\*\*[選取]。</span><span class="sxs-lookup"><span data-stu-id="aef75-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="aef75-122">在 [ **案例資訊** 浮出] 頁面的底部，按一下 [ (**...**) **更多選項**]，然後按一下 [ **關閉案例**]。</span><span class="sxs-lookup"><span data-stu-id="aef75-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   ![以關閉 Advanced eDiscovery 案例的 [其他選項] 功能表中的選項](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="aef75-124">關閉程序最多可能需要 60 分鐘才會完成。</span><span class="sxs-lookup"><span data-stu-id="aef75-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="aef75-125">重新開啟已關閉的案例</span><span class="sxs-lookup"><span data-stu-id="aef75-125">Reopen a closed case</span></span>

<span data-ttu-id="aef75-126">當您重新開啟 Advanced eDiscovery 案例時，在關閉案例時，任何已就地保留都不會自動復原。</span><span class="sxs-lookup"><span data-stu-id="aef75-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="aef75-127">在重新開啟案例之後，您必須移至 [ **保留** ] 索引標籤，並開啟先前的保留。</span><span class="sxs-lookup"><span data-stu-id="aef75-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="aef75-128">若要開啟保留，請加以選取以顯示飛出視窗頁面，然後將 [狀態]\*\*\*\* 切換開關設定為 \*\*\*\*[開啟]。</span><span class="sxs-lookup"><span data-stu-id="aef75-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="aef75-129">若要重新開啟已關閉的案例：</span><span class="sxs-lookup"><span data-stu-id="aef75-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="aef75-130">在 [進階電子文件探索]\*\*\*\* 頁面上，選取您想要重新開啟的案例。</span><span class="sxs-lookup"><span data-stu-id="aef75-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="aef75-131">在 [設定]\*\*\*\* 索引標籤上，按一下 [案例資訊]\*\*\*\* 底下的 \*\*\*\*[選取]。</span><span class="sxs-lookup"><span data-stu-id="aef75-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="aef75-132">在 [ **案例資訊** 浮出] 頁面的底部，按一下 [ (**...**) **更多選項**]，然後按一下 [ **重新開啟案例**]。</span><span class="sxs-lookup"><span data-stu-id="aef75-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   ![可重新開啟 Advanced eDiscovery 案例的 [其他選項] 功能表中的選項](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="aef75-134">最多可能需要60分鐘的時間，重新開啟程式才會完成。</span><span class="sxs-lookup"><span data-stu-id="aef75-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="aef75-135">刪除案例</span><span class="sxs-lookup"><span data-stu-id="aef75-135">Delete a case</span></span>

<span data-ttu-id="aef75-136">您可以刪除作用中和關閉的 Advanced eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="aef75-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="aef75-137">當您刪除案例時，也會刪除與該案例相關聯的所有元件，例如監管人清單、通訊、搜尋、檢閱集和匯出作業。</span><span class="sxs-lookup"><span data-stu-id="aef75-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="aef75-138">案例會從 Microsoft 365 規範中心的 **Advanced eDiscovery** 頁面上的案例清單中移除。</span><span class="sxs-lookup"><span data-stu-id="aef75-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="aef75-139">您無法復原或重新開啟已刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="aef75-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="aef75-140">在資料外泄案例中，移除考核集內專案的唯一方法是刪除 Advanced eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="aef75-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="aef75-141">其他的「搜尋及清除」方法不會從審閱集中移除專案。</span><span class="sxs-lookup"><span data-stu-id="aef75-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="aef75-142">您必須先刪除與案例相關聯的 *所有* 保留，才可刪除案例 () 中或已關閉。</span><span class="sxs-lookup"><span data-stu-id="aef75-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="aef75-143">這包括刪除狀態為 **Off** 的保留。</span><span class="sxs-lookup"><span data-stu-id="aef75-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="aef75-144">若要刪除與案例相關聯的保留：</span><span class="sxs-lookup"><span data-stu-id="aef75-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="aef75-145">在您要刪除的 Advanced eDiscovery 案例中，移到 [**保留**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="aef75-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="aef75-146">按一下您要刪除的保留。</span><span class="sxs-lookup"><span data-stu-id="aef75-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="aef75-147">在飛入頁面上，按一下 [ **刪除保留**]。</span><span class="sxs-lookup"><span data-stu-id="aef75-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="aef75-148">若要刪除案例：</span><span class="sxs-lookup"><span data-stu-id="aef75-148">To delete a case:</span></span>

1. <span data-ttu-id="aef75-149">在 [進階電子文件探索]\*\*\*\* 頁面上，選取您想要刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="aef75-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="aef75-150">在 [設定]\*\*\*\* 索引標籤上，按一下 [案例資訊]\*\*\*\* 底下的 \*\*\*\*[選取]。</span><span class="sxs-lookup"><span data-stu-id="aef75-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="aef75-151">在 [ **案例資訊** 浮出] 頁面的底部，按一下 [ (**...**) **更多選項**]，然後按一下 [ **刪除案例**]。</span><span class="sxs-lookup"><span data-stu-id="aef75-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   ![可刪除 Advanced eDiscovery 案例的 [其他選項] 功能表中的選項](..\Media\DeleteAdvancedeDiscoveryCase.png)
