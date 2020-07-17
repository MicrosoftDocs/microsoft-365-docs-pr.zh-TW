---
title: 從其原始位置刪除項目
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明如何使用安全性 & 規範中心中的「新增資料調查（預覽）」工具，從原始位置刪除專案。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0787944791fea65dfc940b1067abe1bad8097dcd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817882"
---
# <a name="delete-items-from-their-original-location-preview"></a><span data-ttu-id="4952b-103">從原始位置刪除專案（預覽）</span><span class="sxs-lookup"><span data-stu-id="4952b-103">Delete items from their original location (Preview)</span></span>

<span data-ttu-id="4952b-104">從原始位置刪除專案的功能是在預覽中。</span><span class="sxs-lookup"><span data-stu-id="4952b-104">The feature to delete items from their original location is in Preview.</span></span>

<span data-ttu-id="4952b-105">您可以使用資料調查，從原始位置刪除專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-105">Using data investigations, you can delete items from their original locations.</span></span> <span data-ttu-id="4952b-106">這表示您可以在組織內刪除 Exchange 信箱、SharePoint 網站和 OneDrive 帳戶中的專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-106">This means you can delete items from  Exchange mailboxes, SharePoint sites, and OneDrive accounts across your organization.</span></span> <span data-ttu-id="4952b-107">因為您收集的專案是證據，所以您有保留在證據集內的專案複本，可進一步調查或保留為參考。</span><span class="sxs-lookup"><span data-stu-id="4952b-107">Because you collected items as evidence, you have copies of the items retained in the evidence set for further investigation or keep as reference.</span></span>

## <a name="before-you-delete-items"></a><span data-ttu-id="4952b-108">刪除專案之前</span><span class="sxs-lookup"><span data-stu-id="4952b-108">Before you delete items</span></span>

- <span data-ttu-id="4952b-109">若要刪除專案，您必須在安全性 & 合規性中心內指派「**搜尋」和「清除**」角色。</span><span class="sxs-lookup"><span data-stu-id="4952b-109">To delete items, you have to be assigned the **Search And Purge** role in the Security & Compliance Center.</span></span> <span data-ttu-id="4952b-110">此角色預設會指派給內建的資料調查者角色群組。</span><span class="sxs-lookup"><span data-stu-id="4952b-110">This role is assigned by default to the built-in Data Investigator role group.</span></span>

- <span data-ttu-id="4952b-111">本主題中的程式假設您已執行與調查相關聯的搜尋，並已將搜尋結果新增至證據集。</span><span class="sxs-lookup"><span data-stu-id="4952b-111">The procedure in this topic assumes that you have run a search associated with an investigation and added the search results to an evidence set.</span></span> <span data-ttu-id="4952b-112">搜尋結果在證據中之後，您可以選取一或多個要刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-112">After the search results are in evidence, you can select one or more items to delete.</span></span> <span data-ttu-id="4952b-113">如需詳細資訊，請參閱[在調查中搜尋資料](search-for-data.md)。</span><span class="sxs-lookup"><span data-stu-id="4952b-113">For more information, see [Search for data in an investigation](search-for-data.md).</span></span>

- <span data-ttu-id="4952b-114">請務必記住，只有原始內容位置（例如 Exchange 信箱、SharePoint 網站和 OneDrive 帳戶）中的專案會被刪除。</span><span class="sxs-lookup"><span data-stu-id="4952b-114">It's important to keep in mind that only the items in the original content locations (such as Exchange mailboxes, SharePoint sites, and OneDrive accounts) are deleted.</span></span> <span data-ttu-id="4952b-115">這些專案不會從證據集中刪除。</span><span class="sxs-lookup"><span data-stu-id="4952b-115">These items aren't deleted from the evidence set.</span></span> <span data-ttu-id="4952b-116">這是因為證據集中的專案是原始的副本。</span><span class="sxs-lookup"><span data-stu-id="4952b-116">That's because the items in an evidence set are copies of the original.</span></span> <span data-ttu-id="4952b-117">當您將搜尋結果新增至證據集時，會複製這些專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-117">These items are copied when you added the results of a search to an evidence set.</span></span>

## <a name="delete-items"></a><span data-ttu-id="4952b-118">刪除項目</span><span class="sxs-lookup"><span data-stu-id="4952b-118">Delete items</span></span>

<span data-ttu-id="4952b-119">請執行下列步驟，從原始位置刪除專案：</span><span class="sxs-lookup"><span data-stu-id="4952b-119">Perform the following steps to delete items from their original location:</span></span>

1. <span data-ttu-id="4952b-120">在 [**資料調查**工具] 中，開啟包含您要刪除之專案的資料調查，然後按一下 [**證據**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4952b-120">In the **Data Investigations** tool, open the data investigation that contains the items you want to delete, and then click the **Evidence** tab.</span></span>

2. <span data-ttu-id="4952b-121">選取您要刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-121">Select the items that you want to delete.</span></span> <span data-ttu-id="4952b-122">您可以選取證據集中的所有專案，或只選取專案的子集。</span><span class="sxs-lookup"><span data-stu-id="4952b-122">You can select all items in the evidence set or select just a subset of items.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4952b-123">如果您選取的電子郵件附件或檔附加至 SharePoint 和 OneDrive 中的檔，當該專案從原始位置刪除時，也會選取並刪除該父專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-123">If you select the attachments of an email or a file attached to a document in SharePoint and OneDrive, the parent item will be also be selected and deleted when the item is deleted from its original location.</span></span> <span data-ttu-id="4952b-124">同樣地，如果您選取具有附件的專案，則會刪除父項專案和所有附件。</span><span class="sxs-lookup"><span data-stu-id="4952b-124">Similarly, if you select an item that has attachments, the parent item item and all attachments are deleted.</span></span>
 
2. <span data-ttu-id="4952b-125">按一下 [**動作**]，然後按一下 [**刪除原始位置的專案**]。</span><span class="sxs-lookup"><span data-stu-id="4952b-125">Click **Action** and then click **Delete items from original locations**.</span></span>

   ![按一下 [動作]，然後按一下 [刪除原始位置的專案]](../media/DataInvestigationsDeleteItems1.png)

3. <span data-ttu-id="4952b-127">在飛入頁面上，確認將會刪除專案和相關的子檔數目，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4952b-127">On the flyout page, verify the number of items and related child documents that will be deleted, and then click **Delete**.</span></span>

   ![飛出頁面會顯示選取要刪除之專案的數目及所有已選用的檔](../media/DataInvestigationsDeleteItems2.png)

   > [!NOTE]
   > <span data-ttu-id="4952b-129">在先前的螢幕擷取畫面中，專案數目會指出選取要刪除的專案數。</span><span class="sxs-lookup"><span data-stu-id="4952b-129">In the previous screenshot, the number of items indicates the number of items that are selected for deletion.</span></span> <span data-ttu-id="4952b-130">檔數目會指出包含附加至上層專案之任何檔案的總專案數。</span><span class="sxs-lookup"><span data-stu-id="4952b-130">The number of documents indicates to total number of items including any files that are attached to a parent item.</span></span> <span data-ttu-id="4952b-131">例如，如果您選取一個電子郵件訊息，且該郵件具有附加的 Word 檔，則 [**選取的檔**] 下顯示的專案和檔數目只會是**1 個專案（2個檔）**。</span><span class="sxs-lookup"><span data-stu-id="4952b-131">For example, if you select one email message and that message has an attached Word document, the number of items and documents displayed under **Selected documents only** would be **1 items (2 documents)**.</span></span>

<span data-ttu-id="4952b-132">您可以在 [**工作**] 索引標籤上，**從原始位置工作追蹤刪除專案**的進度。按一下工作以顯示飛入頁面。</span><span class="sxs-lookup"><span data-stu-id="4952b-132">You can track the progress of the **Delete items from original locations** job on the **Jobs** tab. Click the job to display the flyout page.</span></span>

![從原始位置工作中刪除專案的飛出頁面](../media/DataInvestigationsDeleteItems3.png)

<span data-ttu-id="4952b-134">刪除工作中的專案時，工作狀態會設定為 [**成功**]。</span><span class="sxs-lookup"><span data-stu-id="4952b-134">When the items in the job are deleted, the job status is set to **Successful**.</span></span> <span data-ttu-id="4952b-135">也會顯示已完成工作的時間和日期。</span><span class="sxs-lookup"><span data-stu-id="4952b-135">The time and date of the completed job is also displayed.</span></span>

![已完成刪除專案工作](../media/DataInvestigationsDeleteItems4.png)

> [!NOTE]
> <span data-ttu-id="4952b-137">您可能會收到**從原始位置工作刪除專案**的**部分成功**狀態。</span><span class="sxs-lookup"><span data-stu-id="4952b-137">You may receive a status of **Partially Successful** for the **Delete items from original locations** job.</span></span> <span data-ttu-id="4952b-138">有許多情況會導致這項工作狀態。</span><span class="sxs-lookup"><span data-stu-id="4952b-138">There are a number of situations that result in this job status.</span></span> <span data-ttu-id="4952b-139">如需詳細資訊，請參閱本文的[部分成功刪除](#partially-successful-deletions)區段。</span><span class="sxs-lookup"><span data-stu-id="4952b-139">For more information, see the [Partially successful deletions](#partially-successful-deletions) section in this article.</span></span>

## <a name="what-happens-when-you-delete-items"></a><span data-ttu-id="4952b-140">當您刪除專案時會發生什麼事</span><span class="sxs-lookup"><span data-stu-id="4952b-140">What happens when you delete items</span></span>

<span data-ttu-id="4952b-141">此時，當您從原始內容位置刪除專案時，這些專案會虛*刪除*。</span><span class="sxs-lookup"><span data-stu-id="4952b-141">At this time, when you delete items from their original content location, the items are *soft-deleted*.</span></span> <span data-ttu-id="4952b-142">這表示專案會移至特殊位置並保留，直到已刪除專案的保留期間到期，並且將專案標記為從 Microsoft 365 永久刪除。</span><span class="sxs-lookup"><span data-stu-id="4952b-142">This means that items are moved to special location and retained until the deleted item retention period expires and an item is marked for permanent deletion from Microsoft 365.</span></span> <span data-ttu-id="4952b-143">虛刪除專案表示使用者仍可復原這些專案，直到保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="4952b-143">Soft-deleting items means that users can still recover these items until the retention period expires.</span></span> <span data-ttu-id="4952b-144">以下說明如何從 Exchange 信箱中虛刪除專案，以及 SharePoint 和 OneDrive 商務網站，以及從原始位置刪除專案後，使用者可以執行的動作。</span><span class="sxs-lookup"><span data-stu-id="4952b-144">Here are descriptions about what happens when items are soft-deleted from Exchange mailboxes and SharePoint and OneDrive for Business sites, and what users can do after items are deleted from their original locations.</span></span>

- <span data-ttu-id="4952b-145">**信箱：** 當信箱專案已虛刪除時，它會移至信箱中的 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="4952b-145">**Mailboxes:** When a mailbox item is soft-deleted, it's moved to the Recoverable Items folder in the mailbox.</span></span> <span data-ttu-id="4952b-146">這種行為類似于使用者從 [刪除的郵件] 資料夾中刪除專案或永久刪除專案時，請按 Shift+Delete。</span><span class="sxs-lookup"><span data-stu-id="4952b-146">This behavior is similar to when a user deletes an item from the Deleted Items folder or permanently deletes an item by pressing Shift + Delete.</span></span> <span data-ttu-id="4952b-147">此時，使用者可以復原專案，直到刪除的專案保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="4952b-147">At this point, the user can recover the item up until the deleted item retention period expires.</span></span> <span data-ttu-id="4952b-148">在 Microsoft 365 中，依預設，已刪除的專案保留期間為14天，但系統管理員可以將保留期間增加30天。</span><span class="sxs-lookup"><span data-stu-id="4952b-148">In Microsoft 365, the deleted item retention period is 14 days by default, but an admin can increase the retention period to 30 days.</span></span> <span data-ttu-id="4952b-149">保留期間到期後，該專案就會移至隱藏的資料夾（稱為 [*清除*] 資料夾）。</span><span class="sxs-lookup"><span data-stu-id="4952b-149">After the retention period expires, the item is moved to a hidden folder (called the *Purges* folder).</span></span> <span data-ttu-id="4952b-150">當您下次處理該信箱時，會永久移除 Microsoft 365 中的專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-150">The item is permanently removed from Microsoft 365 the next time the mailbox is processed.</span></span> <span data-ttu-id="4952b-151">每7天處理一次信箱）。</span><span class="sxs-lookup"><span data-stu-id="4952b-151">Mailboxes are processed once every seven days).</span></span>

- <span data-ttu-id="4952b-152">**SharePoint 和 OneDrive 網站：** 當網站上的檔案或檔已虛刪除時，它會移至網站的回收站（也稱為*第一階段*回收站）。</span><span class="sxs-lookup"><span data-stu-id="4952b-152">**SharePoint and OneDrive sites:** When a file or document on a site is soft-deleted, it's moved to the site's Recycle Bin (also called the *first-stage* Recycle Bin).</span></span> <span data-ttu-id="4952b-153">專案會保留在回收站中93天（Microsoft 365 中的網站的刪除專案保留期間）。</span><span class="sxs-lookup"><span data-stu-id="4952b-153">The item remains in the Recycle Bin for 93 days (the deleted item retention period for sites in Microsoft 365).</span></span> <span data-ttu-id="4952b-154">在93天期間內，網站集合管理員仍可在 SharePoint 或 OneDrive 中的使用者或系統管理員復原已刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-154">During the 93-day period, deleted items can still be recovered by a site collection administrator in SharePoint or by the user or admin in OneDrive.</span></span> <span data-ttu-id="4952b-155">也可以從第一階段回收站中刪除專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-155">Items can also be deleted from the first-stage recycle bin.</span></span> <span data-ttu-id="4952b-156">當發生這種情況時，專案會移至網站集合的回收站，這稱為*第二階段*回收站。</span><span class="sxs-lookup"><span data-stu-id="4952b-156">When that happens, the items are moved to the Recycle Bin for the site collection, which is called the *second-stage* Recycle Bin.</span></span> <span data-ttu-id="4952b-157">在第一階段和第二階段回收站中，保留期間為93天。這表示第二階段回收站保留會從最初刪除專案時開始。</span><span class="sxs-lookup"><span data-stu-id="4952b-157">The retention period is 93 days for both the first-stage and second-stage recycle bins. That means the second-stage Recycle Bin retention starts when the item is initially deleted.</span></span> <span data-ttu-id="4952b-158">這表示兩個回收站的總保留時間上限為93天。如果從第二階段回收站中刪除專案（由系統管理員手動或在保留期間到期時自動進行），系統管理員將無法再存取該專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-158">That means the total maximum retention time is 93 days for both recycle bins. If an item is deleted from the second-stage Recycle Bin (either manually by an admin or automatically when the retention period expires), it's no longer accessible by an admin.</span></span>

## <a name="what-happens-if-a-content-location-is-on-hold"></a><span data-ttu-id="4952b-159">內容位置保留時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="4952b-159">What happens if a content location is on hold</span></span>

<span data-ttu-id="4952b-160">在 Microsoft 365 中，信箱和網站可以保留或指派給保留原則。</span><span class="sxs-lookup"><span data-stu-id="4952b-160">In Microsoft 365, mailboxes and sites can be placed on hold or assigned to a retention policy.</span></span> <span data-ttu-id="4952b-161">這表示將不會永久移除任何專案，直到專案的保留期間到期或移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="4952b-161">This means that nothing is permanently removed until the retention period for an item expires or until the hold is removed.</span></span> <span data-ttu-id="4952b-162">即使您從原始位置刪除專案，也不會永久移除 Office 365 中的專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-162">Even if you delete an item from its original location, the item may not be permanently removed from Office 365.</span></span> <span data-ttu-id="4952b-163">例如，如果信箱處於保留狀態，則虛刪除的專案最終會移至 [可復原的專案] 資料夾中的清除或 DiscoveryHold 子資料夾，並保留，直到保留期間或保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="4952b-163">For example, if a mailbox is on hold, soft-deleted items are eventually moved to Purges or DiscoveryHold subfolders in the Recoverable Items folder and retained until the hold duration or retention period expires.</span></span> <span data-ttu-id="4952b-164">在網站上，移至回收站的專案複本會複製到保留或保留原則放在網站時所建立的保留文件庫。</span><span class="sxs-lookup"><span data-stu-id="4952b-164">For sites, a copy of the item that's moved to the Recycle Bin is copied to the Preservation Hold library that's created when a hold or retention policy is placed on a site.</span></span>

## <a name="partially-successful-deletions"></a><span data-ttu-id="4952b-165">部分成功刪除</span><span class="sxs-lookup"><span data-stu-id="4952b-165">Partially successful deletions</span></span>

<span data-ttu-id="4952b-166">**從原始位置工作中刪除專案**完成執行之後，您可能會收到「**部分成功」** 的工作狀態。</span><span class="sxs-lookup"><span data-stu-id="4952b-166">After the **Delete items from original locations** job has completed running, you may received a job status of **Partially Successful**.</span></span> <span data-ttu-id="4952b-167">一般情況下，此狀態表示工作順利執行，但不是所有專案都已虛刪除。</span><span class="sxs-lookup"><span data-stu-id="4952b-167">In general, this status indicates that the job ran successfully, but not all items were soft-deleted.</span></span> <span data-ttu-id="4952b-168">以下是導致部分成功刪除的原因清單：</span><span class="sxs-lookup"><span data-stu-id="4952b-168">Here's a list of reasons that result in partially successful deletions:</span></span>

- <span data-ttu-id="4952b-169">信箱專案已經位於來源信箱的 [可復原的專案] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="4952b-169">A mailbox item was already located in the Recoverable Items folder in the source mailbox.</span></span>

- <span data-ttu-id="4952b-170">已從來源信箱的 [可復原的專案] 資料夾中清除信箱專案。</span><span class="sxs-lookup"><span data-stu-id="4952b-170">A mailbox item was purged from the Recoverable Items folder in the source mailbox.</span></span>

- <span data-ttu-id="4952b-171">檔已經位於 SharePoint 或 OneDrive 網站的第一階段回收站中。</span><span class="sxs-lookup"><span data-stu-id="4952b-171">A document was already located in the first-stage Recycle Bin in a SharePoint or OneDrive site.</span></span>

- <span data-ttu-id="4952b-172">將檔新增至證據集後，它會移至不同的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="4952b-172">A document was moved to a different SharePoint site after it was added to the evidence set.</span></span> <span data-ttu-id="4952b-173">在此情況下，檔不會移至其移動所在之網站的 [回收站]。</span><span class="sxs-lookup"><span data-stu-id="4952b-173">In this case, the document isn't moved to the Recycle Bin in the site it was moved to.</span></span>

- <span data-ttu-id="4952b-174">在將檔新增至證據集之後，會在 SharePoint 或 OneDrive （移至第二階段回收站）中永久刪除該檔。</span><span class="sxs-lookup"><span data-stu-id="4952b-174">A document was permanently deleted in SharePoint or OneDrive (moved to the second-stage Recycle Bin) after it was added to the evidence set.</span></span>
