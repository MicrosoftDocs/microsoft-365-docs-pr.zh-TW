---
title: 關閉、重新開啟和刪除核心 eDiscovery 案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明如何管理核心 eDiscovery 案例。 這包括關閉案例、開啟關閉的案例，以及刪除案例。
ms.openlocfilehash: 8a54d5c8f93d36351538bc235a6dbeaaa602c3e9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532443"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="dfcba-104">關閉、重新開啟和刪除核心 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="dfcba-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="dfcba-105">本文說明如何在 Microsoft 365 中關閉、重新開啟和刪除核心 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="dfcba-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="dfcba-106">關閉案例</span><span class="sxs-lookup"><span data-stu-id="dfcba-106">Close a case</span></span>

<span data-ttu-id="dfcba-107">當核心 eDiscovery 案例支援的法律案例或調查完成後，您就可以關閉案例。</span><span class="sxs-lookup"><span data-stu-id="dfcba-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="dfcba-108">以下是關閉案例時會發生的情況：</span><span class="sxs-lookup"><span data-stu-id="dfcba-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="dfcba-109">若案例中包含任何 eDiscovery 保留，將會關閉這些功能。</span><span class="sxs-lookup"><span data-stu-id="dfcba-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="dfcba-110">關閉關閉後，30天的寬限期 (稱為 *延遲保留*) 會套用到保留的內容位置。</span><span class="sxs-lookup"><span data-stu-id="dfcba-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="dfcba-111">這有助於防止內容立即刪除，並可讓系統管理員在延遲保留期間到期後，永久刪除內容之前，先進行搜尋並還原內容的機會。</span><span class="sxs-lookup"><span data-stu-id="dfcba-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="dfcba-112">如需詳細資訊，請參閱 [移除 eDiscovery 保留中的內容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="dfcba-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="dfcba-113">關閉案例只會關閉與該案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="dfcba-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="dfcba-114">若其他保留放在內容位置 (例如訴訟暫止、保留原則或其他核心 eDiscovery 案例的保留) 仍會保留這些保留。</span><span class="sxs-lookup"><span data-stu-id="dfcba-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="dfcba-115">此案例仍列在 Microsoft 365 規範中心的核心 eDiscovery 頁面上。</span><span class="sxs-lookup"><span data-stu-id="dfcba-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dfcba-116">已關閉案例的詳細資料、保留、搜尋和成員都會保留。</span><span class="sxs-lookup"><span data-stu-id="dfcba-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="dfcba-117">您可以在關閉案例後進行編輯。</span><span class="sxs-lookup"><span data-stu-id="dfcba-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="dfcba-118">例如，您可以新增或移除成員、建立搜尋並匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="dfcba-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="dfcba-119">主動和封閉式案例之間的主要差異是關閉案例時，會關閉 eDiscovery 保留。</span><span class="sxs-lookup"><span data-stu-id="dfcba-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="dfcba-120">若要關閉案例：</span><span class="sxs-lookup"><span data-stu-id="dfcba-120">To close a case:</span></span>
  
1. <span data-ttu-id="dfcba-121">在 [Microsoft 365 規範中心] 中，按一下 [ **eDiscovery**  >  **Core** ] 以顯示組織中核心 eDiscovery 案例的清單。</span><span class="sxs-lookup"><span data-stu-id="dfcba-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="dfcba-122">按一下您要關閉之案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="dfcba-122">Click the name of the case that you want to close.</span></span>

   ![案例首頁上的關閉案例](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="dfcba-124">在首頁上的 [ **狀態**] 下，按一下 [ **關閉案例**]。</span><span class="sxs-lookup"><span data-stu-id="dfcba-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="dfcba-125">會顯示警告，指出與案例相關聯的保留會關閉。</span><span class="sxs-lookup"><span data-stu-id="dfcba-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="dfcba-126">按一下 **[是]** 以關閉案例。</span><span class="sxs-lookup"><span data-stu-id="dfcba-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="dfcba-127">案例首頁上的狀態會從 [ **可用** ] 變更為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="dfcba-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="dfcba-128">在 [ **核心 eDiscovery** ] 頁面上 **，按一下 [** 重新整理] 以更新封閉式案例的狀態。</span><span class="sxs-lookup"><span data-stu-id="dfcba-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="dfcba-129">關閉程序最多可能需要 60 分鐘才會完成。</span><span class="sxs-lookup"><span data-stu-id="dfcba-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="dfcba-130">當程式完成時，**核心 eDiscovery** 頁面上的案例狀態會變更為 [**已關閉**]。</span><span class="sxs-lookup"><span data-stu-id="dfcba-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="dfcba-131">重新開啟已關閉的案例</span><span class="sxs-lookup"><span data-stu-id="dfcba-131">Reopen a closed case</span></span>

<span data-ttu-id="dfcba-132">當您重新開啟案例時，關閉案例時所使用的任何 eDiscovery 保留都不會自動復原。</span><span class="sxs-lookup"><span data-stu-id="dfcba-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="dfcba-133">在重新開啟案例之後，您必須移至 [ **保留** ] 頁面並開啟先前保留。</span><span class="sxs-lookup"><span data-stu-id="dfcba-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="dfcba-134">若要開啟保留，請加以選取以顯示飛出視窗頁面，然後將 [狀態]\*\*\*\* 切換開關設定為 \*\*\*\*[開啟]。</span><span class="sxs-lookup"><span data-stu-id="dfcba-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="dfcba-135">在 [Microsoft 365 規範中心] 中，按一下 [ **eDiscovery**  >  **Core** ] 以顯示組織中核心 eDiscovery 案例的清單。</span><span class="sxs-lookup"><span data-stu-id="dfcba-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="dfcba-136">按一下您要重新開啟之案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="dfcba-136">Click the name of the case that you want to reopen.</span></span>

   ![重新開啟已關閉的案例](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="dfcba-138">在首頁上的 [ **狀態**] 下，按一下 [ **重新開啟案例**]。</span><span class="sxs-lookup"><span data-stu-id="dfcba-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="dfcba-139">會顯示警告，指出在關閉此案例時，其所關聯的保留不會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="dfcba-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="dfcba-140">按一下 **[是]** 重新開啟案例。</span><span class="sxs-lookup"><span data-stu-id="dfcba-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="dfcba-141">[案例首頁飛出] 頁面上的狀態會從 [ **已關閉** **] 改為**[使用中]。</span><span class="sxs-lookup"><span data-stu-id="dfcba-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="dfcba-142">在 **核心 eDiscovery** 頁面上 **，按一下 [** 重新整理] 以更新重新開啟之案例的狀態。</span><span class="sxs-lookup"><span data-stu-id="dfcba-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="dfcba-143">最多可能需要60分鐘的時間，重新開啟程式才會完成。</span><span class="sxs-lookup"><span data-stu-id="dfcba-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="dfcba-144">當程式完成時，**核心 eDiscovery** 頁面上的案例狀態會變更為 [**作用中]** 。</span><span class="sxs-lookup"><span data-stu-id="dfcba-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

6. <span data-ttu-id="dfcba-145"> (選用) 若要開啟與重新開啟之案例關聯的任何保留，請移至 [ **保留** ] 索引標籤，選取 [保留]，然後選取 [保留快顯視窗] 頁面上 [ **狀態** ] 底下的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dfcba-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="dfcba-146">刪除案例</span><span class="sxs-lookup"><span data-stu-id="dfcba-146">Delete a case</span></span>

<span data-ttu-id="dfcba-147">您也可以刪除主動及封閉式核心 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="dfcba-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="dfcba-148">當您刪除案例時，系統會刪除案例中的所有搜尋和匯出，然後會從 Microsoft 365 規範中心的 **核心 eDiscovery** 頁面上的案例清單中移除此案例。</span><span class="sxs-lookup"><span data-stu-id="dfcba-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dfcba-149">您無法重新開啟已刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="dfcba-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="dfcba-150">您必須先刪除 *所有* 與案例相關聯的 eDiscovery 保留，才可刪除案例 () 使用中或已關閉。</span><span class="sxs-lookup"><span data-stu-id="dfcba-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="dfcba-151">這包括刪除狀態為 **Off** 的保留。</span><span class="sxs-lookup"><span data-stu-id="dfcba-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="dfcba-152">若要刪除 eDiscovery 保留：</span><span class="sxs-lookup"><span data-stu-id="dfcba-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="dfcba-153">移至 [ **保留** ] 索引標籤中您要刪除的情況。</span><span class="sxs-lookup"><span data-stu-id="dfcba-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="dfcba-154">選取您要刪除的保留。</span><span class="sxs-lookup"><span data-stu-id="dfcba-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="dfcba-155">在飛入頁面上，按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="dfcba-155">On the flyout page, click **Delete**.</span></span>

      ![刪除電子檔探索暫止](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="dfcba-157">若要刪除案例：</span><span class="sxs-lookup"><span data-stu-id="dfcba-157">To delete a case:</span></span>

1. <span data-ttu-id="dfcba-158">在 [Microsoft 365 規範中心] 中，按一下 [ **eDiscovery**  >  **Core** ] 以顯示組織中核心 eDiscovery 案例的清單。</span><span class="sxs-lookup"><span data-stu-id="dfcba-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="dfcba-159">按一下您要刪除之案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="dfcba-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="dfcba-160">在 [案例] 首頁的 [ **狀態**] 下，按一下 [ **刪除案例**]。</span><span class="sxs-lookup"><span data-stu-id="dfcba-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![刪除案例](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="dfcba-162">如果您嘗試刪除的案例仍包含 eDiscovery 保留，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="dfcba-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="dfcba-163">您必須刪除所有與案例相關聯的保留，然後再試一次，以刪除案例。</span><span class="sxs-lookup"><span data-stu-id="dfcba-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
