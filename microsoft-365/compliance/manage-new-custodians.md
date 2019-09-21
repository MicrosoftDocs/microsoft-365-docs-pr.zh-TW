---
title: 管理 custodians 進階電子文件探索案例中
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
description: ''
ms.openlocfilehash: 17c77f14267f988a071e201733ae54ad9c438547
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077188"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="e313c-102">管理 custodians 進階電子文件探索案例中</span><span class="sxs-lookup"><span data-stu-id="e313c-102">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="e313c-103">在進階電子文件中的 [Custodians] 索引標籤包含所有 custodians 已新增至案例清單。</span><span class="sxs-lookup"><span data-stu-id="e313c-103">The Custodians tab in Advanced eDiscovery contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="e313c-104">您將 custodians 新增至案例之後，每個 custodian 詳細自動收集自 Azure Active Directory 且進階電子文件探索中檢視。</span><span class="sxs-lookup"><span data-stu-id="e313c-104">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![管理 Custodians](media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="e313c-106">檢視 custodian 詳細資料</span><span class="sxs-lookup"><span data-stu-id="e313c-106">View custodian details</span></span>

<span data-ttu-id="e313c-107">若要檢視有關 custodian 的詳細資訊，請按一下 [ **Custodians** ] 索引標籤上，從清單 custodian。彈出式頁面隨即出現，並包含 custodian 的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="e313c-107">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="e313c-108">連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="e313c-108">Contact information</span></span>

  - <span data-ttu-id="e313c-109">**顯示名稱**-custodian 顯示在通訊錄中的名稱。</span><span class="sxs-lookup"><span data-stu-id="e313c-109">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="e313c-110">這通常是 custodian 名字]、 [中間的初始，和最後一個名稱的組合。</span><span class="sxs-lookup"><span data-stu-id="e313c-110">This is usually the combination of the custodian’s first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="e313c-111">**郵件/SMTP** -custodian，例如 brianj@contoso.onmicrosoft.com 的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="e313c-111">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="e313c-112">請注意 custodian 的使用者主要名稱 (UPN) 也會列。</span><span class="sxs-lookup"><span data-stu-id="e313c-112">Note that the custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="e313c-113">**標題**-custodian 的職稱。</span><span class="sxs-lookup"><span data-stu-id="e313c-113">**Title** - The custodian’s job title.</span></span>

  - <span data-ttu-id="e313c-114">**部門**-custodian 適用於部門的名稱。</span><span class="sxs-lookup"><span data-stu-id="e313c-114">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="e313c-115">**管理員**-custodian 的管理員。</span><span class="sxs-lookup"><span data-stu-id="e313c-115">**Manager** - The custodian’s manager.</span></span> <span data-ttu-id="e313c-116">指定的管理員會收到此 custodian 任何呈報通訊。</span><span class="sxs-lookup"><span data-stu-id="e313c-116">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="e313c-117">位置資訊</span><span class="sxs-lookup"><span data-stu-id="e313c-117">Location information</span></span>

  - <span data-ttu-id="e313c-118">**縣/市**-custodian 所在的市/鎮。</span><span class="sxs-lookup"><span data-stu-id="e313c-118">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="e313c-119">**狀態**-縣 / 市 custodian 的地址。</span><span class="sxs-lookup"><span data-stu-id="e313c-119">**State** - The state or province in the custodian’s address.</span></span>

  - <span data-ttu-id="e313c-120">**國家/地區**-custodian 所在的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="e313c-120">**Country/Region** - The country/region where the custodian’s is located.</span></span>

  - <span data-ttu-id="e313c-121">**Office** -商務版 custodian 就地的辦公室位置。</span><span class="sxs-lookup"><span data-stu-id="e313c-121">**Office** - The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="e313c-122">案例資訊</span><span class="sxs-lookup"><span data-stu-id="e313c-122">Case information</span></span>

  - <span data-ttu-id="e313c-123">**保留狀態**-會指出是否 custodian 具有已處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="e313c-123">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="e313c-124">**通訊狀態**： 指出 custodian 是否已經發出保留通知。</span><span class="sxs-lookup"><span data-stu-id="e313c-124">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="e313c-125">如果 custodian 已發出的通知，此屬性的這個值會是**已發佈**。</span><span class="sxs-lookup"><span data-stu-id="e313c-125">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="e313c-126">如果 custodian 已不發出通知，狀態會**取消發佈**。</span><span class="sxs-lookup"><span data-stu-id="e313c-126">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="e313c-127">**狀態**-在 case custodian 的狀態。</span><span class="sxs-lookup"><span data-stu-id="e313c-127">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="e313c-128">**作用中的**] 狀態表示 custodian 是這種情況的一部分。</span><span class="sxs-lookup"><span data-stu-id="e313c-128">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="e313c-129">如果 custodian 一經釋出從案例，狀態會變更為**發行**。</span><span class="sxs-lookup"><span data-stu-id="e313c-129">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="e313c-130">資料來源及索引資訊</span><span class="sxs-lookup"><span data-stu-id="e313c-130">Data sources and indexing information</span></span>

    - <span data-ttu-id="e313c-131">**資料來源**-顯示計數和類型的資料來源 （信箱、 網站和小組） 與 custodian 相關聯，而且這種情況的一部分。</span><span class="sxs-lookup"><span data-stu-id="e313c-131">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="e313c-132">**索引更新時間**-會指出上次觸發進階索引工作的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="e313c-132">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="e313c-133">此屬性也會指出當進階索引處理序正在進行中。</span><span class="sxs-lookup"><span data-stu-id="e313c-133">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="e313c-134">編輯 custodian</span><span class="sxs-lookup"><span data-stu-id="e313c-134">Edit a custodian</span></span>

<span data-ttu-id="e313c-135">隨著您案例的進度，您可能會發現可能有其他資料來源相關的特定 custodian & 您的案例。</span><span class="sxs-lookup"><span data-stu-id="e313c-135">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="e313c-136">在其他情況下，您可能想要移除特定資料來源的檢閱和視為不相關。</span><span class="sxs-lookup"><span data-stu-id="e313c-136">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="e313c-137">若要更新 custodian 相關聯的資料來源：</span><span class="sxs-lookup"><span data-stu-id="e313c-137">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="e313c-138">移至**eDiscovery > 進階電子文件**，並開啟案例。</span><span class="sxs-lookup"><span data-stu-id="e313c-138">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="e313c-139">按一下 [ **Custodians** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e313c-139">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="e313c-140">從清單中選取 custodian，然後按一下 [彈出式頁面的 [**編輯**。</span><span class="sxs-lookup"><span data-stu-id="e313c-140">Select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![編輯資料來源](media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="e313c-142">按一下 [**選擇資料來源**] 索引標籤，若要變更 custodian 的 Exchange 信箱和 OneDrive 帳戶的設定，請按一下 [**選擇資料來源**。</span><span class="sxs-lookup"><span data-stu-id="e313c-142">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="e313c-143">按一下 [**選取其他資料來源**] 索引標籤來新增或移除小組、 SharePoint，或 Exchange custodian 相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="e313c-143">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="e313c-144">如需 custodian 相關聯的資料來源的詳細資訊，請參閱 「 步驟 3： 建立關聯的其他資料來源]，以 custodian 「[新增 custodians 案例](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian)中。</span><span class="sxs-lookup"><span data-stu-id="e313c-144">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="e313c-145">按一下 [啟用或停用保留 custodian **custodial 就地保留**]。</span><span class="sxs-lookup"><span data-stu-id="e313c-145">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="resolve-custodian-processing-errors"></a><span data-ttu-id="e313c-146">解決 custodian 處理錯誤</span><span class="sxs-lookup"><span data-stu-id="e313c-146">Resolve custodian processing errors</span></span>

<span data-ttu-id="e313c-147">在大部分法律調查的 eDiscovery 工作流程，custodian 新增的法律案件之後搜尋 custodian 資料的子集。</span><span class="sxs-lookup"><span data-stu-id="e313c-147">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="e313c-148">非常大的檔案大小或可能造成資料損毀，因為 custodian 相關聯的資料來源中的某些項目可能是已局部編製索引。</span><span class="sxs-lookup"><span data-stu-id="e313c-148">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="e313c-149">在進階電子文件中使用的[進階編製索引](indexing-custodian-data.md)的功能，最局部編製索引的項目可進行自動修復藉由重新編製索引視需要這些項目。</span><span class="sxs-lookup"><span data-stu-id="e313c-149">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="e313c-150">當 custodian 新增至案例時，位於 custodian 相關聯的資料來源的資料會自動重新編製索引 （藉由進階索引程序）。</span><span class="sxs-lookup"><span data-stu-id="e313c-150">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="e313c-151">這表示您可以將保留資料就地而不必下載並修復它再搜尋離線）。</span><span class="sxs-lookup"><span data-stu-id="e313c-151">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="e313c-152">不過，週期中法律案例新資料來源可能與 custodian 相關聯。</span><span class="sxs-lookup"><span data-stu-id="e313c-152">However, during the lifecycle of a legal case new data sources might be associated to a custodian.</span></span> <span data-ttu-id="e313c-153">在此情況下，您重新編製索引 custodian 的資料重新執行 [進階索引程序，以修正任何已局部編製索引的項目，並更新 custodian 資料的索引。</span><span class="sxs-lookup"><span data-stu-id="e313c-153">In this case, you re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="e313c-154">若要觸發地址重新編製索引程序已局部編製索引的項目：</span><span class="sxs-lookup"><span data-stu-id="e313c-154">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="e313c-155">移至**eDiscovery > 進階電子文件**，並開啟案例。</span><span class="sxs-lookup"><span data-stu-id="e313c-155">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="e313c-156">按一下以**Custodians] 索引標籤**，，然後選取 [的 custodian，其資料必須編製索引。</span><span class="sxs-lookup"><span data-stu-id="e313c-156">Click to **Custodians tab**, and then select a custodian whose data must be reindexed.</span></span> 

3. <span data-ttu-id="e313c-157">在彈出式頁面上，按一下 [**更新索引**]。</span><span class="sxs-lookup"><span data-stu-id="e313c-157">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="e313c-158">會顯示對話方塊，指出已建立索引工作。</span><span class="sxs-lookup"><span data-stu-id="e313c-158">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="e313c-159">重新編製索引 custodian 資料是長時間執行的程序;相對應的工作會建立名為**重新編製索引 custodian 資料**。</span><span class="sxs-lookup"><span data-stu-id="e313c-159">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="e313c-160">您可以藉由監視**編製索引工作狀態**] 欄中的狀態，[**工作**] 索引標籤或 [ **Custodians** ] 索引標籤上追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="e313c-160">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="e313c-161">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e313c-161">For more information, see:</span></span>

- [<span data-ttu-id="e313c-162">使用處理錯誤</span><span class="sxs-lookup"><span data-stu-id="e313c-162">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="e313c-163">管理工作</span><span class="sxs-lookup"><span data-stu-id="e313c-163">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="e313c-164">釋出 custodian 從案例</span><span class="sxs-lookup"><span data-stu-id="e313c-164">Release a custodian from a case</span></span>

<span data-ttu-id="e313c-165">發行日期 custodian 在會在關閉案例的情況下，custodian 不再下義務以保留內容的情況下，或當 custodian 會被視為不會再是與案件相關。</span><span class="sxs-lookup"><span data-stu-id="e313c-165">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="e313c-166">如果已發佈保留通知之後，您就會釋放 custodian，發行通知會傳送至 custodian。</span><span class="sxs-lookup"><span data-stu-id="e313c-166">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="e313c-167">此外，會移除任何已 custodian 相關聯的資料來源上的保留。</span><span class="sxs-lookup"><span data-stu-id="e313c-167">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="e313c-168">如果 custodian 放在*無訊息保留*、 他們未發出任何法律保留通知、 發行通知將不會傳送，但已與該 custodian 相關聯的資料來源上任何保留移除。</span><span class="sxs-lookup"><span data-stu-id="e313c-168">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="e313c-169">若要發行 custodian:</span><span class="sxs-lookup"><span data-stu-id="e313c-169">To release a custodian:</span></span> 

1. <span data-ttu-id="e313c-170">移至**eDiscovery > 進階電子文件**，並開啟案例。</span><span class="sxs-lookup"><span data-stu-id="e313c-170">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2.  <span data-ttu-id="e313c-171">移至 [ **Custodians** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e313c-171">Go to the **Custodians** tab.</span></span>

3.  <span data-ttu-id="e313c-172">**Custodians] 索引標籤上**，按一下，然後選取 [從案例的 [custodian 正在發行日期。</span><span class="sxs-lookup"><span data-stu-id="e313c-172">Click to **Custodians tab**, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="e313c-173">在彈出式頁面上，按一下 [**發行 custodian**]。</span><span class="sxs-lookup"><span data-stu-id="e313c-173">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="e313c-174">警告] 頁面上會顯示說明，是否保留暫留 custodian 相關聯的資料來源時，保留會被移除，以及其他任何保留與不同的進階電子文件探索案例相關聯仍然會套用。</span><span class="sxs-lookup"><span data-stu-id="e313c-174">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="e313c-175">包括 Office 365 中的其他類型的保留和保留功能 （例如 Office 365 保留原則）。</span><span class="sxs-lookup"><span data-stu-id="e313c-175">That includes other types of preservation and retention features in Office 365 (such as an Office 365 retention policy).</span></span>

5. <span data-ttu-id="e313c-176">按一下 **[是]** ，確認您想要釋出 custodian。</span><span class="sxs-lookup"><span data-stu-id="e313c-176">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="e313c-177">請注意，此使用者**Custodians** ] 索引標籤上的狀態設為**已發行**和**保留狀態**的彈出式頁面會變更為**False**。</span><span class="sxs-lookup"><span data-stu-id="e313c-177">Note that status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="e313c-178">Custodian 可能同時參與數個法律案件。</span><span class="sxs-lookup"><span data-stu-id="e313c-178">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="e313c-179">當 custodian 發行從案例時，不會影響保留和跨其他事件通知。</span><span class="sxs-lookup"><span data-stu-id="e313c-179">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="e313c-180">大量編輯 custodians</span><span class="sxs-lookup"><span data-stu-id="e313c-180">Bulk-edit custodians</span></span>

<span data-ttu-id="e313c-181">您可以使用大量編輯器來編輯多個 custodians 為同一時間。</span><span class="sxs-lookup"><span data-stu-id="e313c-181">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="e313c-182">若要這麼做，請只選取兩個或多個 custodians **Custodians** ] 索引標籤上的顯示大量編輯程式，然後按一下下列其中一個工作。</span><span class="sxs-lookup"><span data-stu-id="e313c-182">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![若要編輯的多個 custodians 設定彈出式頁面](media/AeDBulkEditCustodians.png)