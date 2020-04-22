---
title: 在高級 eDiscovery 案例中管理保管人
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
description: 在高級 eDiscovery 案例中管理保管人。
ms.openlocfilehash: b497aef50c2bafd58e3b9cf8643a1ecc038520a4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635893"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="46081-103">在高級 eDiscovery 案例中管理保管人</span><span class="sxs-lookup"><span data-stu-id="46081-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="46081-104">[！注意] 「高級 eDiscovery」中的「保管人」索引標籤會包含已新增至案例的所有保管人清單。</span><span class="sxs-lookup"><span data-stu-id="46081-104">The Custodians tab in Advanced eDiscovery contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="46081-105">在您將保管人新增至案例後，會自動從 Azure Active Directory 收集每個保管人的詳細資訊，並在高級 eDiscovery 中查看。</span><span class="sxs-lookup"><span data-stu-id="46081-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![管理保管人](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="46081-107">查看保管人詳細資料</span><span class="sxs-lookup"><span data-stu-id="46081-107">View custodian details</span></span>

<span data-ttu-id="46081-108">若要查看有關保管人的詳細資料，請按一下 [**保管人**] 索引標籤上的 [管理員] 清單。隨即會顯示飛出的頁面，並包含下列管理員的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="46081-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="46081-109">連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="46081-109">Contact information</span></span>

  - <span data-ttu-id="46081-110">**顯示名稱**-顯示在保管人的通訊錄中的名稱。</span><span class="sxs-lookup"><span data-stu-id="46081-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="46081-111">這通常是管理員的名字、中間名首字母和姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="46081-111">This is usually the combination of the custodian’s first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="46081-112">**Mail/SMTP** -保管人的主要 SMTP 位址，例如，brianj@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="46081-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="46081-113">也會列出保管人的使用者主要名稱（UPN）。</span><span class="sxs-lookup"><span data-stu-id="46081-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="46081-114">**Title** -保管人的職稱。</span><span class="sxs-lookup"><span data-stu-id="46081-114">**Title** - The custodian’s job title.</span></span>

  - <span data-ttu-id="46081-115">**部門**-保管人運作所在部門的名稱。</span><span class="sxs-lookup"><span data-stu-id="46081-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="46081-116">**Manager** -保管人的管理員。</span><span class="sxs-lookup"><span data-stu-id="46081-116">**Manager** - The custodian’s manager.</span></span> <span data-ttu-id="46081-117">指定的管理員會收到此管理員的任何升級通訊。</span><span class="sxs-lookup"><span data-stu-id="46081-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="46081-118">位置資訊</span><span class="sxs-lookup"><span data-stu-id="46081-118">Location information</span></span>

  - <span data-ttu-id="46081-119">**City** -保管人所在的城市。</span><span class="sxs-lookup"><span data-stu-id="46081-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="46081-120">**State** -保管人位址中的省或市。</span><span class="sxs-lookup"><span data-stu-id="46081-120">**State** - The state or province in the custodian’s address.</span></span>

  - <span data-ttu-id="46081-121">**國家/地區**-保管人所在的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="46081-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="46081-122">**Office** -在保管人公司地點的辦公室地點。</span><span class="sxs-lookup"><span data-stu-id="46081-122">**Office** - The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="46081-123">案例資訊</span><span class="sxs-lookup"><span data-stu-id="46081-123">Case information</span></span>

  - <span data-ttu-id="46081-124">**保留狀態**-表示是否已將保管人置於暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="46081-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="46081-125">**通訊狀態**：指出是否已簽發保管人的持有者通知。</span><span class="sxs-lookup"><span data-stu-id="46081-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="46081-126">如果保管人已發出通知，則會**發佈**此屬性的值。</span><span class="sxs-lookup"><span data-stu-id="46081-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="46081-127">如果保管人尚未發出通知，則狀態會**取消發佈**。</span><span class="sxs-lookup"><span data-stu-id="46081-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="46081-128">**狀態**-案例內管理員的狀態。</span><span class="sxs-lookup"><span data-stu-id="46081-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="46081-129">**Active**的狀態表示保管人是案例的一部分。</span><span class="sxs-lookup"><span data-stu-id="46081-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="46081-130">如果從案例中發佈保管人，則狀態會變更為 [已**發放**]。</span><span class="sxs-lookup"><span data-stu-id="46081-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="46081-131">資料來源和索引資訊</span><span class="sxs-lookup"><span data-stu-id="46081-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="46081-132">**資料來源**-顯示與保管人相關聯且屬於案例一部分之資料來源（信箱、網站及小組）的計數和類型。</span><span class="sxs-lookup"><span data-stu-id="46081-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="46081-133">**索引更新時間**-指出上次觸發高級索引工作的時間與日期。</span><span class="sxs-lookup"><span data-stu-id="46081-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="46081-134">此屬性也會指出高級索引處理常式目前的進行時間。</span><span class="sxs-lookup"><span data-stu-id="46081-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="46081-135">編輯保管人</span><span class="sxs-lookup"><span data-stu-id="46081-135">Edit a custodian</span></span>

<span data-ttu-id="46081-136">在您的案例進展中，您可能會發現在您的案例中，可能會有與特定保管人相關的其他資料來源 &。</span><span class="sxs-lookup"><span data-stu-id="46081-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="46081-137">在其他情況下，您可能會想要移除某些已複查並視為不相關的資料來源。</span><span class="sxs-lookup"><span data-stu-id="46081-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="46081-138">若要更新與保管人相關聯的資料來源：</span><span class="sxs-lookup"><span data-stu-id="46081-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="46081-139">請移至**eDiscovery > Advanced ediscovery** ，然後開啟案例。</span><span class="sxs-lookup"><span data-stu-id="46081-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="46081-140">按一下 [**保管人**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="46081-140">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="46081-141">從清單中選取管理員，然後按一下彈出頁面上的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="46081-141">Select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![編輯資料來源](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="46081-143">按一下 **[選擇資料來源**] 索引標籤，以變更保管人的 Exchange 信箱和 OneDrive 帳戶的設定，然後按一下 **[選擇資料來源**]。</span><span class="sxs-lookup"><span data-stu-id="46081-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="46081-144">按一下 [**選取其他資料來源**] 索引標籤，新增或移除與保管人管理員相關聯的小組、SharePoint 或 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="46081-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="46081-145">如需與保管人相關聯之資料來源的詳細資訊，請參閱[Add 保管人 to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian)中的「步驟3：將其他資料來源與保管人關聯。」。</span><span class="sxs-lookup"><span data-stu-id="46081-145">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="46081-146">按一下 [**放置 custodial 保留**]，以啟用或停用保管人的保留。</span><span class="sxs-lookup"><span data-stu-id="46081-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="46081-147">重新索引保管人資料</span><span class="sxs-lookup"><span data-stu-id="46081-147">Re-index custodian data</span></span>

<span data-ttu-id="46081-148">在大部分法律調查的 eDiscovery 工作流程中，在將保管人新增至合法案例後，會搜尋保管人資料的子集。</span><span class="sxs-lookup"><span data-stu-id="46081-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="46081-149">由於非常大的檔案大小或可能的資料損毀，與管理員相關聯之資料來源中的某些專案可能會進行部分編制索引。</span><span class="sxs-lookup"><span data-stu-id="46081-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="46081-150">使用高級 eDiscovery 中的[高級索引](indexing-custodian-data.md)功能時，可以根據需要重新建立這些專案的索引，以自動修正部分的索引項目目。</span><span class="sxs-lookup"><span data-stu-id="46081-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="46081-151">當系統管理員新增至案例時，位於與保管人相關之資料來源中的資料會自動重新編制索引（由高級索引處理常式）。</span><span class="sxs-lookup"><span data-stu-id="46081-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="46081-152">這表示您可以就地保留資料，而不需要下載並修復資料，然後離線搜尋）。</span><span class="sxs-lookup"><span data-stu-id="46081-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="46081-153">不過，在法律案例的生命週期中，可能會與保管人產生關聯的新資料來源。</span><span class="sxs-lookup"><span data-stu-id="46081-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="46081-154">在此情況下，您可以重新執行「高級索引處理常式」以修正任何已部分索引的專案，並更新保管人資料的索引，以重新建立保管人的資料索引。</span><span class="sxs-lookup"><span data-stu-id="46081-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="46081-155">觸發重新編制索引處理常式來處理部分索引的專案：</span><span class="sxs-lookup"><span data-stu-id="46081-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="46081-156">請移至**eDiscovery > Advanced ediscovery** ，然後開啟案例。</span><span class="sxs-lookup"><span data-stu-id="46081-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="46081-157">按一下 [to**保管人]** 索引標籤，然後選取必須重新編制索引其資料的保管人。</span><span class="sxs-lookup"><span data-stu-id="46081-157">Click to **Custodians tab**, and then select a custodian whose data must be reindexed.</span></span> 

3. <span data-ttu-id="46081-158">在飛入頁面上，按一下 [**更新索引**]。</span><span class="sxs-lookup"><span data-stu-id="46081-158">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="46081-159">隨即會顯示一個對話方塊，指出已經建立索引工作。</span><span class="sxs-lookup"><span data-stu-id="46081-159">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="46081-160">重新索引保管人資料是長期執行的程式;所建立的對應工作稱為**重新編制索引的保管人資料**。</span><span class="sxs-lookup"><span data-stu-id="46081-160">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="46081-161">您可以在 [**索引工作狀態**] 欄中監控狀態，以追蹤 [**工作**] 索引標籤或 [**保管人**] 索引標籤上的進度。</span><span class="sxs-lookup"><span data-stu-id="46081-161">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="46081-162">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="46081-162">For more information, see:</span></span>

- [<span data-ttu-id="46081-163">使用處理錯誤</span><span class="sxs-lookup"><span data-stu-id="46081-163">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="46081-164">管理工作</span><span class="sxs-lookup"><span data-stu-id="46081-164">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="46081-165">從案例發行管理員</span><span class="sxs-lookup"><span data-stu-id="46081-165">Release a custodian from a case</span></span>

<span data-ttu-id="46081-166">在關閉案例的情況下，保管人會遭到發佈，但管理員已不再需要保留內容的情況，或當保管人視為不再與案例相關時。</span><span class="sxs-lookup"><span data-stu-id="46081-166">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="46081-167">發佈系統管理員之後，如果您發佈了保留通知，就會將發行通知傳送給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="46081-167">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="46081-168">此外，已移除與保管人相關聯之資料來源的任何保留。</span><span class="sxs-lookup"><span data-stu-id="46081-168">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="46081-169">如果系統管理員是置於無訊息*保留狀態*（未發佈任何合法保留通知），將不會傳送發行通知，但是會移除與該保管人相關聯之資料來源上的任何保留。</span><span class="sxs-lookup"><span data-stu-id="46081-169">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="46081-170">若要發行管理員：</span><span class="sxs-lookup"><span data-stu-id="46081-170">To release a custodian:</span></span> 

1. <span data-ttu-id="46081-171">請移至**eDiscovery > Advanced ediscovery** ，然後開啟案例。</span><span class="sxs-lookup"><span data-stu-id="46081-171">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2.  <span data-ttu-id="46081-172">移至 [**保管人**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="46081-172">Go to the **Custodians** tab.</span></span>

3.  <span data-ttu-id="46081-173">按一下 [to**保管人]** 索引標籤，然後選取從案例中發放的保管人。</span><span class="sxs-lookup"><span data-stu-id="46081-173">Click to **Custodians tab**, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="46081-174">在飛入頁面上，按一下 [**發行管理員**]。</span><span class="sxs-lookup"><span data-stu-id="46081-174">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="46081-175">隨即會顯示 [警告] 頁面，說明如果保留是放在與保管人相關聯的資料來源上，保留將會被移除，而且與不同的高級 eDiscovery 案例關聯的任何其他保留仍會適用。</span><span class="sxs-lookup"><span data-stu-id="46081-175">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="46081-176">包括其他類型的保留和保留功能（例如 Microsoft 365 保留原則）。</span><span class="sxs-lookup"><span data-stu-id="46081-176">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="46081-177">按一下 **[是]** 確認您要釋放保管人。</span><span class="sxs-lookup"><span data-stu-id="46081-177">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="46081-178">在 [**保管人**] 索引標籤上，此使用者的狀態會設定為 [已**發放**]，而且飛入頁面上的 [**保留] 狀態**會變更為**False**。</span><span class="sxs-lookup"><span data-stu-id="46081-178">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="46081-179">在幾個法律案例中，管理員可能會同時參與。</span><span class="sxs-lookup"><span data-stu-id="46081-179">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="46081-180">當保管人從案例發行時，其他重要專案的保留和通知將不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="46081-180">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="46081-181">大量編輯保管人</span><span class="sxs-lookup"><span data-stu-id="46081-181">Bulk-edit custodians</span></span>

<span data-ttu-id="46081-182">您可以使用大量編輯器同時編輯多個保管人。</span><span class="sxs-lookup"><span data-stu-id="46081-182">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="46081-183">若要這麼做，只要在 [**保管人**] 索引標籤上選取兩個或多個保管人，即可顯示大量編輯器，然後按一下其中一個工作。</span><span class="sxs-lookup"><span data-stu-id="46081-183">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![可編輯多個保管人設定的飛出頁面](../media/AeDBulkEditCustodians.png)
