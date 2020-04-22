---
title: 管理 Microsoft 365 中的資料外泄事件
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明如何在安全性 & 規範中心使用「新增資料調查（預覽）」工具來管理資料外泄事件。
ms.openlocfilehash: a544eb1e021faa82d00ac46a7d64a3eb368cc323
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635933"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="8f7b3-103">管理 Microsoft 365 中的資料外泄事件</span><span class="sxs-lookup"><span data-stu-id="8f7b3-103">Manage a data spillage incident in Microsoft 365</span></span>

<span data-ttu-id="8f7b3-104">資料外泄是指在不受信任的環境中發行包含機密、敏感或惡意資訊的檔時。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-104">Data spillage is when a document containing confidential, sensitive, or malicious information is released in an untrusted environment.</span></span> <span data-ttu-id="8f7b3-105">偵測到資料外泄事件時，必須快速包含環境、評估外泄的大小和位置、檢查其周圍的使用者活動，然後從服務中刪除溢出的資料。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-105">When a data spillage incident is detected, it's important to quickly contain the environment, assess the size and locations of the spillage, examine user activities around it, and then delete the spilled data from the service.</span></span> <span data-ttu-id="8f7b3-106">使用「資料調查（預覽）」工具，您可以在 Office 365 中搜尋敏感、惡意或誤放的資料，調查以找出發生的情況，然後採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-106">Using the Data Investigations (Preview) tool, you can search for sensitive, malicious, or misplaced data across Office 365, investigate to find out what happened, and then take appropriate actions.</span></span>  

## <a name="scope-of-this-article"></a><span data-ttu-id="8f7b3-107">本文的範圍</span><span class="sxs-lookup"><span data-stu-id="8f7b3-107">Scope of this article</span></span>

<span data-ttu-id="8f7b3-108">本文提供如何永久刪除 Microsoft 365 信箱中的專案，以供使用者或系統管理員不再存取或復原的指示清單。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-108">This article provides a list of instructions on how to permanently delete items from Microsoft 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="8f7b3-109">當您刪除位於 SharePoint 或 OneDrive for Business site 中的專案時，會從您從原始位置刪除這些專案時保留93天。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-109">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="8f7b3-110">案例</span><span class="sxs-lookup"><span data-stu-id="8f7b3-110">Scenario</span></span>

<span data-ttu-id="8f7b3-111">您會收到資料外泄事件的通知，其中員工在不知情的情況下，透過電子郵件將高度機密檔與多人共用。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-111">You're informed of a data spillage incident where an employee unknowingly shared a highly confidential document with multiple people through email.</span></span> <span data-ttu-id="8f7b3-112">您想要快速評估在組織內部和外部接收此檔的人員。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-112">You want to quickly assess who received this document, both inside and outside of your organization.</span></span> <span data-ttu-id="8f7b3-113">在調查事件後，您計畫與其他調查人員分享您的調查結果，然後永久移除組織中溢出的資料。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-113">After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from your organization.</span></span> <span data-ttu-id="8f7b3-114">調查完成後，您想要移除所有的證據。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-114">After the investigation is complete, you want to remove all evidence.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8f7b3-115">雖然您可以永久移除組織內溢出的資料，但不能使用這些功能移除任何溢出于組織外的資料。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-115">While you'll be able to permanently remove the spilled data within your own organization, any data spilled outside your organization can't be removed with these capabilities.</span></span>

## <a name="workflow"></a><span data-ttu-id="8f7b3-116">工作流程</span><span class="sxs-lookup"><span data-stu-id="8f7b3-116">Workflow</span></span>

<span data-ttu-id="8f7b3-117">以下是使用資料調查（預覽）管理資料外泄事件的工作流程：</span><span class="sxs-lookup"><span data-stu-id="8f7b3-117">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="8f7b3-118">建立資料調查。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-118">Create a data investigation.</span></span>

2.  <span data-ttu-id="8f7b3-119">搜尋敏感、惡意或誤放的資料，並將其收集為證據。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-119">Search for sensitive, malicious, or misplaced data and collect them as evidence.</span></span>

3.  <span data-ttu-id="8f7b3-120">複查並調查證據。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-120">Review and investigate the evidence.</span></span>

4.  <span data-ttu-id="8f7b3-121">永久刪除濺入的資料。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-121">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="8f7b3-122">請關閉或刪除調查。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-122">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="8f7b3-123">開始之前</span><span class="sxs-lookup"><span data-stu-id="8f7b3-123">Before you begin</span></span>

- <span data-ttu-id="8f7b3-124">若要建立資料調查、搜尋內容及刪除濺入的資料，您必須是安全性 & 規範中心的「資料調查人員」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-124">To create a data investigation, search for content, and delete spilled data, you have to be a member of the Data Investigator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="8f7b3-125">若要控制調查人員可搜尋的使用者信箱和 OneDrive 帳戶，您的組織可以設定規范界限。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-125">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries.</span></span> <span data-ttu-id="8f7b3-126">如需詳細資訊，請[設定 eDiscovery 調查的規範界限](tagging-and-assessment-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-126">For more information, [Set up compliance boundaries for eDiscovery investigations](tagging-and-assessment-in-advanced-ediscovery.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="8f7b3-127">步驟1：建立資料調查</span><span class="sxs-lookup"><span data-stu-id="8f7b3-127">Step 1: Create a data investigation</span></span>

<span data-ttu-id="8f7b3-128">若要在資料調查（預覽）工具中建立調查：</span><span class="sxs-lookup"><span data-stu-id="8f7b3-128">To create an investigation in the Data Investigations (Preview) tool:</span></span>

1. <span data-ttu-id="8f7b3-129">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-129">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="8f7b3-130">使用「資料調查員」角色群組成員的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-130">Sign in using an account that is a member of the Data Investigator role group.</span></span>
    
3. <span data-ttu-id="8f7b3-131">在 [安全性與合規性中心] 中，按一下 [**資料調查**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-131">In the security and compliance center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="8f7b3-132">在 [**資料調查（預覽）** ] 頁面上，按一下 [**建立新調查**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-132">On the **Data Investigations (Preview)** page, click **Create new investigation**.</span></span>
    
5. <span data-ttu-id="8f7b3-133">在 [**新增資料調查**] 飛入頁面上，將調查命名為 [必要]，然後輸入選用的調查編號及描述。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-133">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description.</span></span> <span data-ttu-id="8f7b3-134">該名稱在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-134">The name must be unique in your organization.</span></span>

6. <span data-ttu-id="8f7b3-135">在 [**您要在建立此調查之後設定其他設定嗎？**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="8f7b3-135">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="8f7b3-136">按一下 **[是]** 建立調查，並顯示新案例中的 [**設定**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-136">Click **Yes** to create the investigation, and display the **Settings** page in the new case.</span></span> <span data-ttu-id="8f7b3-137">這可讓您將成員新增至調查。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-137">This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="8f7b3-138">按一下 [**否**] 建立調查並顯示在 [**資料調查（預覽）** ] 頁面上的案例清單中。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-138">Click **No** to create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page.</span></span> <span data-ttu-id="8f7b3-139">如果您選擇此選項，則會將您新增為調查的唯一成員，而且會使用預設的搜尋及分析設定。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-139">If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used.</span></span> <span data-ttu-id="8f7b3-140">建立調查之後，您可以隨時新增成員或變更設定。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-140">You can add members or change settings anytime after the investigation is created.</span></span>

7. <span data-ttu-id="8f7b3-141">按一下 [**儲存**] 以建立調查。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-141">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="8f7b3-142">新的調查會顯示在 [**資料調查（預覽）** ] 頁面上的清單中。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-142">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="8f7b3-143">若要開啟調查，請按一下調查的名稱。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-143">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="8f7b3-144">會顯示調查的 [**首頁**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-144">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="8f7b3-145">請考慮建立調查的命名慣例，並在 [名稱] 和 [描述] 中提供盡可能多的資訊，以便您可以在將來找到及參考。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-145">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to them in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="8f7b3-146">步驟2：搜尋溢出的資料</span><span class="sxs-lookup"><span data-stu-id="8f7b3-146">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="8f7b3-147">如果您知道要搜尋溢出資料的使用者，您可以將其新增到調查中，並快速搜尋其信箱和 OneDrive 帳戶，以將其新增到調查中。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-147">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account.</span></span> <span data-ttu-id="8f7b3-148">若要新增調查的興趣人員，請按一下 [**感興趣的人員**]，然後按一下 [**新增感興趣的人員**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-148">To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> <span data-ttu-id="8f7b3-149">如需詳細資訊，請參閱[管理感興趣的人員](manage-people-of-interest.md)。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-149">For more information, see [Manage people of interest](manage-people-of-interest.md).</span></span>

<span data-ttu-id="8f7b3-150">在 [**搜尋**] 索引標籤上，您可以建立搜尋，以找出溢出的資料。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-150">On the **Searches** tab, you can create searches to find the spilled data.</span></span> <span data-ttu-id="8f7b3-151">如需建立搜尋的詳細資訊，請參閱[在調查中搜尋資料](search-for-data.md)。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-151">For more information about creating searches, see [Search for data in an investigation](search-for-data.md).</span></span>

<span data-ttu-id="8f7b3-152">執行搜尋之後，您可以預覽搜尋結果的範例，並查看搜尋統計資料，以評估搜尋查詢的有效性。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-152">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query.</span></span> <span data-ttu-id="8f7b3-153">在您識別要從 Office 365 刪除的專案之後，您可以將搜尋結果新增至證據集。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-153">After you identify the items that you want to delete from Office 365, you can add the search results to an evidence set.</span></span> <span data-ttu-id="8f7b3-154">若要這麼做，請按一下您要調查的搜尋。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-154">To do this, click the search that you want to investigate.</span></span> <span data-ttu-id="8f7b3-155">在飛入頁面上，按一下 [**將結果新增至證據**並依照指示執行。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-155">On the flyout page, click **Add results to evidence** and follow the instructions.</span></span> <span data-ttu-id="8f7b3-156">然後在證據集中，您可以查看個別檔、調查誰有權存取檔，以及匯出檔。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-156">Then in the evidence set, you can review individual documents, investigate who had access to documents, and export the documents.</span></span> <span data-ttu-id="8f7b3-157">若要刪除檔（或檔的子集），而不是加以檢查，請移至[步驟 4](#step-4-delete-the-spilled-data)。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-157">To delete the documents (or a subset of documents) instead of reviewing them, go to [Step 4](#step-4-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8f7b3-158">您在搜尋查詢中使用的關鍵字可能會包含您要搜尋的實際濺入資料。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-158">The keywords that you use in the search query may contain the actual spilled data that you're searching for.</span></span> <span data-ttu-id="8f7b3-159">例如，如果您搜尋包含社會保險號碼的檔，並將它當做搜尋查詢中的關鍵字使用，則必須在以後刪除查詢，以避免進一步外泄。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-159">For example, if you search for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage.</span></span> <span data-ttu-id="8f7b3-160">您可以在[步驟 5](#step-5-close-or-delete-the-investigation)中刪除搜尋或刪除整個調查。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-160">You can delete the search or delete the entire investigation in [Step 5](#step-5-close-or-delete-the-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="8f7b3-161">步驟3：複查和調查</span><span class="sxs-lookup"><span data-stu-id="8f7b3-161">Step 3: Review and investigate</span></span> 

<span data-ttu-id="8f7b3-162">在調查中，移至 [**證據**] 索引標籤，然後按一下您在上一個步驟中建立的證據集。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-162">In the investigation, go to the **Evidence** tab and click the evidence set that you created in the previous step.</span></span> <span data-ttu-id="8f7b3-163">完成處理工作並將搜尋結果新增至證據後，您就可以以原生格式、文字格式或近乎原生格式來查看個別檔。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-163">After the processing job is completed and the search results are added to the evidence, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="8f7b3-164">您可以建立額外的查詢來縮小檔案清單，並標記檔，以指出調查中的結果。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-164">You can create additional queries to narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span> <span data-ttu-id="8f7b3-165">如需詳細資訊，請參閱在[證據中檢查資料](review-data-in-evidence.md)</span><span class="sxs-lookup"><span data-stu-id="8f7b3-165">For more information, see [Review data in evidence](review-data-in-evidence.md)</span></span>

<span data-ttu-id="8f7b3-166">若要將檔群組並取得更多協助以進行審閱，請按一下 [**管理證據**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-166">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="8f7b3-167">在 [**分析**] 磚中，按一下 [**分析**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-167">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="8f7b3-168">這會執行「高級分析」，例如重複偵測、電子郵件執行緒及主題分析。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-168">This runs advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="8f7b3-169">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="8f7b3-169">For more information, see:</span></span>

- [<span data-ttu-id="8f7b3-170">執行分析以更快速地調查</span><span class="sxs-lookup"><span data-stu-id="8f7b3-170">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)
- [<span data-ttu-id="8f7b3-171">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="8f7b3-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="8f7b3-172">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="8f7b3-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="8f7b3-173">佈景主題</span><span class="sxs-lookup"><span data-stu-id="8f7b3-173">Themes</span></span>](themes.md)

<span data-ttu-id="8f7b3-174">若要判斷資料外泄中所涉及的使用者，您可以在證據集中建立查詢，然後使用寄件者/作者和收件者條件。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-174">To determine which users are involved in the data spillage, you can create a query in the evidence set and then use the Sender/Author and Recipients conditions.</span></span> <span data-ttu-id="8f7b3-175">這會建立在已收集的資料中已新增至證據的所有寄件者、收件者和作者的清單。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-175">This creates a list of all senders, recipients, and authors found in collected data that was added to the evidence.</span></span> <span data-ttu-id="8f7b3-176">請務必檢查清單，以判斷是否有任何外部使用者。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-176">Be sure to examine the list to determine if there are any external users.</span></span> <span data-ttu-id="8f7b3-177">如需使用條件來縮小搜尋結果的詳細資訊，請參閱[搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-177">For more information about using conditions to narrow search results, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-delete-the-spilled-data"></a><span data-ttu-id="8f7b3-178">步驟4：刪除溢出的資料</span><span class="sxs-lookup"><span data-stu-id="8f7b3-178">Step 4: Delete the spilled data</span></span>

<span data-ttu-id="8f7b3-179">您可以使用「資料調查」工具，從原始位置刪除專案。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-179">Using the data investigations tool, you can delete items from their original locations.</span></span> <span data-ttu-id="8f7b3-180">例如，您可以在組織中刪除信箱、SharePoint 網站和 OneDrive 帳戶中的專案。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-180">For example, you can delete items from mailboxes, SharePoint sites, and OneDrive accounts across your organization.</span></span> <span data-ttu-id="8f7b3-181">請記住，由於您將專案收集為證據（透過將搜尋結果新增至步驟2中的證據集），您可以在證據集中包含專案的副本，以進一步調查或保留這些專案。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-181">Keep in mind that because you collected items as evidence (by adding the search results to the evidence set in Step 2), you have copies of the items in the evidence set to further investigate or preserve them.</span></span>

<span data-ttu-id="8f7b3-182">若要從原始位置刪除專案：</span><span class="sxs-lookup"><span data-stu-id="8f7b3-182">To delete items from their original locations:</span></span>

1. <span data-ttu-id="8f7b3-183">在 [證據集] 中，選取您要刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-183">In the evidence set, select the items that you want to delete.</span></span> <span data-ttu-id="8f7b3-184">如果您選取附加至電子郵件的專案，則會同時選取及刪除父系電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-184">If you select items that are attached to an email message, the parent email message will also be selected and deleted.</span></span> 
 
2. <span data-ttu-id="8f7b3-185">按一下 [**動作**]，然後按一下 [**刪除原始位置的專案**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-185">Click **Action** and then click **Delete items from original locations**.</span></span>

   ![按一下 [動作]，然後按一下 [刪除原始位置的專案]](../media/DataInvestigationsDeleteItems1.png)

3. <span data-ttu-id="8f7b3-187">在飛入頁面上，確認將會刪除專案和相關的子檔數目，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-187">On the flyout page, verify the number of items and related child documents that will be deleted, and then click **Delete**.</span></span>

<span data-ttu-id="8f7b3-188">此時，當您從原始位置刪除專案時，這些專案會虛刪除。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-188">At this time, when you delete items from their original location, the items are soft-deleted.</span></span> <span data-ttu-id="8f7b3-189">這表示將保留已刪除的專案，直到專案的已刪除專案恢復週期到期為止。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-189">This means that the deleted items will be retained until the deleted item recovery period for the item expires.</span></span> <span data-ttu-id="8f7b3-190">這也表示使用者可以復原這些專案。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-190">This also means it's possible for users to recover these items.</span></span> <span data-ttu-id="8f7b3-191">如需從信箱和網站刪除專案時發生的詳細資訊，請參閱[從原始位置刪除專案](delete-items-from-original-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-191">For more information about what happens when items are deleted from mailboxes and sites, see [Delete items from their original location](delete-items-from-original-locations.md).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="8f7b3-192">步驟5：關閉或刪除調查</span><span class="sxs-lookup"><span data-stu-id="8f7b3-192">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="8f7b3-193">在 live service 中刪除來源內容位置（信箱或網站）中的檔之後，您仍然會有這些檔的副本，您已在調查中做為證據做為證據的一部分。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-193">After you delete documents in the source content locations (mailboxes or sites) in the live service, you will still have copies of these documents that you added to evidence as part of your investigation.</span></span> <span data-ttu-id="8f7b3-194">若要避免進一步的資料外泄，您應該考慮刪除調查本身。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-194">To avoid further data spillage, you should consider deleting the investigation itself.</span></span>

<span data-ttu-id="8f7b3-195">若要刪除調查：</span><span class="sxs-lookup"><span data-stu-id="8f7b3-195">To delete an investigation:</span></span>

1. <span data-ttu-id="8f7b3-196">在 [**設定**] 索引標籤上，按一下 [**調查資訊**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-196">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="8f7b3-197">按一下 [**刪除調查**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-197">Click  **Delete investigation**.</span></span> 

<span data-ttu-id="8f7b3-198">如果您不需要刪除調查，或是若要儲存在調查期間收集到的資訊，您可以按一下 [**關閉案例**]。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-198">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**.</span></span> <span data-ttu-id="8f7b3-199">之後，您可以重新開啟已關閉的調查。</span><span class="sxs-lookup"><span data-stu-id="8f7b3-199">Then later, you can reopen closed investigations.</span></span>
