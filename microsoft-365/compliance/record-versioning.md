---
title: 使用記錄版本設定來更新儲存在 SharePoint 或 OneDrive 中的記錄
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解可協助您在 Microsoft 365 中實作記錄管理解決方案的記錄。
ms.openlocfilehash: 4b8209108564f0a75f8d70efecd57d2526d9face
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200522"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="1dcff-103">使用記錄版本設定來更新儲存在 SharePoint 或 OneDrive 中的記錄</span><span class="sxs-lookup"><span data-stu-id="1dcff-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="1dcff-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="1dcff-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

>[!NOTE] 
> <span data-ttu-id="1dcff-105">由於法規記錄會封鎖編輯，法規記錄無法使用記錄版本設定。</span><span class="sxs-lookup"><span data-stu-id="1dcff-105">Because regulatory records block editing, record versioning is not available for regulatory records.</span></span>

<span data-ttu-id="1dcff-106">將文件標示為[記錄](records-management.md#records)的功能，以及限制可對記錄執行的動作，是任何記錄管理解決方案的重要目標。</span><span class="sxs-lookup"><span data-stu-id="1dcff-106">The ability to mark a document as a [record](records-management.md#records) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="1dcff-107">不過，可能也會需要共同作業，讓人員建立後續的版本。</span><span class="sxs-lookup"><span data-stu-id="1dcff-107">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="1dcff-108">例如，您將銷售合約標示為記錄，但是之後需要使用新的條款來更新合約，並將最新的版本標示為新記錄，同時保留前一份記錄版本。</span><span class="sxs-lookup"><span data-stu-id="1dcff-108">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="1dcff-109">針對這些類型的案例，SharePoint 和 OneDrive 支援*記錄版本設定*。</span><span class="sxs-lookup"><span data-stu-id="1dcff-109">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="1dcff-110">OneNote 筆記本資料夾不支援記錄版本設定。</span><span class="sxs-lookup"><span data-stu-id="1dcff-110">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="1dcff-111">若要使用記錄版本設定，請先[為文件加上標籤並將它標示為記錄](declare-records.md)。</span><span class="sxs-lookup"><span data-stu-id="1dcff-111">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="1dcff-112">此時，保留標籤旁會顯示名為 [記錄狀態]\*\* 的文件內容，而初始記錄狀態會是 [鎖定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1dcff-112">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="1dcff-113">您現在可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1dcff-113">You can now do the following things:</span></span>

  - <span data-ttu-id="1dcff-114">**解除鎖定和鎖定記錄狀態內容，持續編輯並將文件的個別版本保留為記錄。**</span><span class="sxs-lookup"><span data-stu-id="1dcff-114">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="1dcff-115">只有當 [記錄狀態]\*\*\*\* 內容設為 [鎖定]\*\*\*\* 時，才會保留記錄的新版本。</span><span class="sxs-lookup"><span data-stu-id="1dcff-115">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="1dcff-116">這個鎖定和解除鎖定的切換，可降低保留不必要文件版本和複本的風險。</span><span class="sxs-lookup"><span data-stu-id="1dcff-116">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="1dcff-117">**將記錄自動儲存在位於網站集合內的就地記錄儲存庫中。**</span><span class="sxs-lookup"><span data-stu-id="1dcff-117">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="1dcff-118">SharePoint 和 OneDrive 中的每個網站集合會在其 [文件保留庫] 中保留內容。</span><span class="sxs-lookup"><span data-stu-id="1dcff-118">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="1dcff-119">記錄版本會儲存在此文件庫的 [記錄] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1dcff-119">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="1dcff-120">**維護包含所有版本的長青文件。**</span><span class="sxs-lookup"><span data-stu-id="1dcff-120">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="1dcff-121">根據預設，每個 SharePoint 和 OneDrive 文件在項目功能表上都會有版本歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="1dcff-121">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="1dcff-122">在這個版本歷程記錄中，您可以輕鬆查看記錄的版本，並檢視這些文件。</span><span class="sxs-lookup"><span data-stu-id="1dcff-122">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="1dcff-123">如果任何文件的保留標籤會將項目標示為記錄，則會自動提供記錄版本設定。</span><span class="sxs-lookup"><span data-stu-id="1dcff-123">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="1dcff-124">當使用者透過 [詳細資料] 窗格檢視文件內容時，系統會將 [記錄狀態]\*\*\*\* 從 [鎖定]\*\*\*\* 切換為 [解除鎖定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1dcff-124">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="1dcff-125">此動作會在 [文件保留庫] 的 [記錄] 資料夾中建立記錄，該記錄將在保留期的剩餘時間內保留在其中。</span><span class="sxs-lookup"><span data-stu-id="1dcff-125">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="1dcff-126">文件解除鎖定後，任何擁有標準編輯權限的使用者都可以編輯該檔案。</span><span class="sxs-lookup"><span data-stu-id="1dcff-126">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="1dcff-127">不過，使用者無法刪除檔案，因為它仍是記錄。</span><span class="sxs-lookup"><span data-stu-id="1dcff-127">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="1dcff-128">編輯完成後，使用者就可以將 [記錄狀態]\*\*\*\* 從 [解除鎖定]\*\*\*\* 切換為 [鎖定]\*\*\*\*，這會在此狀態中防止進一步編輯。</span><span class="sxs-lookup"><span data-stu-id="1dcff-128">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![標記為記錄之文件的 [記錄狀態] 內容](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="1dcff-130">鎖定和解除鎖定記錄</span><span class="sxs-lookup"><span data-stu-id="1dcff-130">Locking and unlocking a record</span></span>

<span data-ttu-id="1dcff-131">將會將內容標示為記錄的保留標籤套用至文件之後，具有 [參與] 權限或更低權限等級的任何使用者都可以解除鎖定記錄或鎖定已解除鎖定的記錄。</span><span class="sxs-lookup"><span data-stu-id="1dcff-131">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![記錄狀態顯示記錄文件已解鎖](../media/recordversioning9.png)

<span data-ttu-id="1dcff-133">當使用者解鎖記錄後，會發生下列動作：</span><span class="sxs-lookup"><span data-stu-id="1dcff-133">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="1dcff-134">如果目前的網站集合沒有文件保留庫，則會建立一個。</span><span class="sxs-lookup"><span data-stu-id="1dcff-134">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="1dcff-135">如果 [文件保留庫] 沒有 [記錄] 資料夾，則會建立一個。</span><span class="sxs-lookup"><span data-stu-id="1dcff-135">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="1dcff-136">[複製到]\*\*\*\* 動作會將最新版本的文件複製到 [記錄] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1dcff-136">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="1dcff-137">[複製到]\*\*\*\* 動作只會包含最新版本，而不包含先前的版本。</span><span class="sxs-lookup"><span data-stu-id="1dcff-137">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="1dcff-138">複製的文件現在被視為文件的記錄版本，其檔案名稱的格式為：\[標題 GUID 版本\#\]</span><span class="sxs-lookup"><span data-stu-id="1dcff-138">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="1dcff-139">在 [記錄] 資料夾中建立的複本會新增到原始文件的版本歷程記錄中，而這個版本則會在 [註解] 欄位中顯示**記錄**一詞。</span><span class="sxs-lookup"><span data-stu-id="1dcff-139">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="1dcff-140">原始文件是可以編輯但無法刪除的新版本。</span><span class="sxs-lookup"><span data-stu-id="1dcff-140">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="1dcff-141">[文件庫] 欄位 [項目是一筆記錄]\*\*\*\* 仍然會顯示 [是]\*\*\*\* 值，因為文件仍是記錄，即使現在可以編輯。</span><span class="sxs-lookup"><span data-stu-id="1dcff-141">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="1dcff-142">當使用者鎖定記錄後，就不能再次編輯原始檔案。</span><span class="sxs-lookup"><span data-stu-id="1dcff-142">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="1dcff-143">但是，解鎖記錄的動作會將版本複製到 [文件保留庫] 中的 [記錄] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1dcff-143">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="1dcff-144">記錄版本</span><span class="sxs-lookup"><span data-stu-id="1dcff-144">Record versions</span></span>

<span data-ttu-id="1dcff-145">每次使用者解鎖記錄時，系統會將最新版本複製到 [文件保留庫] 的 [記錄] 資料夾中，而該版本則會在版本歷程記錄的 [註解]\*\*\*\* 欄位中包含 [記錄]\*\*\*\* 的值。</span><span class="sxs-lookup"><span data-stu-id="1dcff-145">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![在 [文件保留庫] 中顯示的記錄](../media/recordversioning10.png)

<span data-ttu-id="1dcff-147">若要查看版本歷程記錄，請選取文件庫中的文件，然後按一下項目功能表中的 [版本歷程記錄]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1dcff-147">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="1dcff-148">記錄的儲存位置</span><span class="sxs-lookup"><span data-stu-id="1dcff-148">Where records are stored</span></span>

<span data-ttu-id="1dcff-149">記錄會儲存在網站集合中，頂層網站中 [文件保留庫] 的 [記錄] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1dcff-149">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="1dcff-150">在頂層網站的左側導覽中，選擇 [網站內容]\*\*\*\* \> [文件保留庫]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1dcff-150">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![文件保留庫](../media/recordversioning11.png)

<br/><br/>

![[文件保留庫] 中的記錄資料夾](../media/recordversioning12.png)

<span data-ttu-id="1dcff-153">只有網站集合系統管理員才能看到 [文件保留庫]。</span><span class="sxs-lookup"><span data-stu-id="1dcff-153">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="1dcff-154">此外，預設不存在 [文件保留庫]。</span><span class="sxs-lookup"><span data-stu-id="1dcff-154">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="1dcff-155">只有在網站集中第一次刪除具有保留標籤或保留原則的內容時，才會建立。</span><span class="sxs-lookup"><span data-stu-id="1dcff-155">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="1dcff-156">搜尋記錄版本設定事件的稽核記錄</span><span class="sxs-lookup"><span data-stu-id="1dcff-156">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="1dcff-157">鎖定和解鎖記錄的動作會記錄在稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="1dcff-157">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="1dcff-158">您可以搜尋 [已將記錄狀態變更為「鎖定」]\*\*\*\* 和 [已將記錄狀態變更為「未鎖定」]\*\*\*\* 的特定活動，其位於 [安全性與合規性中心]\*\*\*\* 的 [稽核記錄搜尋]\*\*\*\* 頁面上，[檔案與頁面活動] 區段的 [活動]\*\*\*\* 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="1dcff-158">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![搜尋記錄版本設定事件的稽核記錄](../media/recordversioning13.png)

<span data-ttu-id="1dcff-160">如需搜尋這些活動的詳細資訊，請參閱[在安全性與合規性中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)中的「檔案和頁面活動」一節。</span><span class="sxs-lookup"><span data-stu-id="1dcff-160">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1dcff-161">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1dcff-161">Next steps</span></span>

<span data-ttu-id="1dcff-162">若需記錄管理支援的其他案例，請參閱 [[記錄管理的常見案例]](get-started-with-records-management.md#common-scenarios-for-records-management)。</span><span class="sxs-lookup"><span data-stu-id="1dcff-162">For other scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
