---
title: 進階電子文件探索報表
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
description: ''
ms.openlocfilehash: c3bd87f6a6b06cf6fc75705073df5a95a1025a31
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079946"
---
# <a name="advanced-ediscovery-reports-preview"></a><span data-ttu-id="7be19-102">進階電子文件報告 （預覽）</span><span class="sxs-lookup"><span data-stu-id="7be19-102">Advanced eDiscovery reports (preview)</span></span>

<span data-ttu-id="7be19-103">您進階電子文件探索報告說明整個組織簡化資料分析和組織報告彙總案例資料。</span><span class="sxs-lookup"><span data-stu-id="7be19-103">Advanced eDiscovery reports help you aggregate case data across your organization to streamline data analysis and organizational reporting.</span></span> <span data-ttu-id="7be19-104">進階電子文件報告功能包含幾個內建的報告來協助您回答問題，例如：</span><span class="sxs-lookup"><span data-stu-id="7be19-104">The Advanced eDiscovery reports feature includes several built-in reports to help you answer questions like:</span></span>

- <span data-ttu-id="7be19-105">多少 active custodians 是否有我的組織中的所有案例的？</span><span class="sxs-lookup"><span data-stu-id="7be19-105">How many active custodians are there for all cases in my organization?</span></span>

- <span data-ttu-id="7be19-106">為我的組織中的所有案例，保留多少資料來源位於嗎？</span><span class="sxs-lookup"><span data-stu-id="7be19-106">How many data sources are on hold for all cases in my organization?</span></span>

- <span data-ttu-id="7be19-107">多少保留在 [我的組織中的所有案例的最後一個月份已經發出通知？</span><span class="sxs-lookup"><span data-stu-id="7be19-107">How many hold notifications have been issued in the last month for all cases in my organization?</span></span>

- <span data-ttu-id="7be19-108">多少作用中及已關閉的情況下我的組織內是否有一些？</span><span class="sxs-lookup"><span data-stu-id="7be19-108">How many active and closed cases are there in my organization?</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7be19-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="7be19-109">Before you begin</span></span>

- <span data-ttu-id="7be19-110">若要存取進階電子文件報告，您必須是 「 eDiscovery 系統管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7be19-110">To access Advanced eDiscovery reports, you must be a member of the eDiscovery Admin role group.</span></span> <span data-ttu-id="7be19-111">這個角色群組的成員所提供的檢視、 篩選及匯出報告資料的必要權限。</span><span class="sxs-lookup"><span data-stu-id="7be19-111">Being a member of this role group provides you with the necessary permissions to view, filter, and export the data in the reports.</span></span> <span data-ttu-id="7be19-112">如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="7be19-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="7be19-113">進階電子文件報告每日重新整理。</span><span class="sxs-lookup"><span data-stu-id="7be19-113">Advanced eDiscovery reports are refreshed daily.</span></span> <span data-ttu-id="7be19-114">因此，可能會有延遲時建立新的情況下，custodians、 資料來源而言和通訊，它們會出現在對應的報告。</span><span class="sxs-lookup"><span data-stu-id="7be19-114">As a result, there may be a delay when new cases, custodians, data sources, and communications are created and when they appear in the corresponding report.</span></span>

<span data-ttu-id="7be19-115">若要存取進階電子文件報告：</span><span class="sxs-lookup"><span data-stu-id="7be19-115">To access the Advanced eDiscovery reports:</span></span>

1. <span data-ttu-id="7be19-116">請移至 https://protection.office.com</span><span class="sxs-lookup"><span data-stu-id="7be19-116">Go to https://protection.office.com</span></span>
  
2. <span data-ttu-id="7be19-117">登入 Office 365 中，使用您的工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="7be19-117">Sign into Office 365 using your work or school account.</span></span>
  
3. <span data-ttu-id="7be19-118">在安全性 & 合規性中心，按一下 [ **eDiscovery > 進階電子文件**。</span><span class="sxs-lookup"><span data-stu-id="7be19-118">In the Security & Compliance Center, click **eDiscovery > Advanced eDiscovery**.</span></span>
  
   <span data-ttu-id="7be19-119">在**進階電子文件探索**首頁] 頁面上，大小寫、 Custodian、 資料來源，以及通訊報表索引標籤會顯示跨頁的最頂端。</span><span class="sxs-lookup"><span data-stu-id="7be19-119">On the **Advanced eDiscovery** home page, the Case, Custodian, Data Source, and Communications report tabs are displayed across the top of the page.</span></span> 
  
   ![在 [首頁] 頁面上的進階電子文件探索報表](../media/report-home.png)

5. <span data-ttu-id="7be19-121">若要檢視報表，按一下 [報表] 索引標籤中，，然後視您可以執行下列其中一個下列事項：</span><span class="sxs-lookup"><span data-stu-id="7be19-121">To view a report, click a report tab, and then if necessary you can do one of the following things:</span></span>

   ![您可以篩選或下載報告資料](../media/AeDReportsFilterDownload.png)

   <span data-ttu-id="7be19-123">a.</span><span class="sxs-lookup"><span data-stu-id="7be19-123">a.</span></span> <span data-ttu-id="7be19-124">按一下 [**篩選器**來縮小報表資料。</span><span class="sxs-lookup"><span data-stu-id="7be19-124">Click **Filter** to narrow the report data.</span></span> <span data-ttu-id="7be19-125">您可以篩選每個報表的不同內容。</span><span class="sxs-lookup"><span data-stu-id="7be19-125">You can filter on different properties for each report.</span></span>
  
   <span data-ttu-id="7be19-126">b.</span><span class="sxs-lookup"><span data-stu-id="7be19-126">b.</span></span> <span data-ttu-id="7be19-127">按一下 [**下載至 CSV** ] 若要將報表資料匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="7be19-127">Click **Download to CSV** to export the report data to a CSV file.</span></span>

## <a name="case-report"></a><span data-ttu-id="7be19-128">大小寫的報表</span><span class="sxs-lookup"><span data-stu-id="7be19-128">Case report</span></span>

<span data-ttu-id="7be19-129">Case 報表彙總您組織中的作用中及已關閉事先 eDiscovery 案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7be19-129">The Case report aggregates information about active and closed Advance eDiscovery cases in your organization.</span></span>

|<span data-ttu-id="7be19-130">欄</span><span class="sxs-lookup"><span data-stu-id="7be19-130">Column</span></span>        |<span data-ttu-id="7be19-131">描述</span><span class="sxs-lookup"><span data-stu-id="7be19-131">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="7be19-132">大小寫的識別碼</span><span class="sxs-lookup"><span data-stu-id="7be19-132">Case ID</span></span> | <span data-ttu-id="7be19-133">每個案例的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7be19-133">The unique identifier for each case.</span></span>| 
|<span data-ttu-id="7be19-134">案例名稱</span><span class="sxs-lookup"><span data-stu-id="7be19-134">Case name</span></span> | <span data-ttu-id="7be19-135">使用者定義的大小寫名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-135">User-defined name of the case.</span></span>|
|<span data-ttu-id="7be19-136">狀態</span><span class="sxs-lookup"><span data-stu-id="7be19-136">Status</span></span> | <span data-ttu-id="7be19-137">會指出作用中或關閉，是否是這種情況。</span><span class="sxs-lookup"><span data-stu-id="7be19-137">Indicates if the case is active or closed.</span></span>|
|<span data-ttu-id="7be19-138">建立日期</span><span class="sxs-lookup"><span data-stu-id="7be19-138">Date created</span></span> |<span data-ttu-id="7be19-139">建立這種情況對日期。</span><span class="sxs-lookup"><span data-stu-id="7be19-139">Th date when the case was created.</span></span> <span data-ttu-id="7be19-140">日期為 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="7be19-140">Dates are in UTC format.</span></span>|
|<span data-ttu-id="7be19-141">上次修改日期</span><span class="sxs-lookup"><span data-stu-id="7be19-141">Last modified</span></span> |<span data-ttu-id="7be19-142">這種情況時已關閉，或上次更新日期。</span><span class="sxs-lookup"><span data-stu-id="7be19-142">The date when the case was closed or last updated.</span></span> <span data-ttu-id="7be19-143">日期為 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="7be19-143">Dates are in UTC format.</span></span>| 
|||

## <a name="custodian-report"></a><span data-ttu-id="7be19-144">Custodian 報表</span><span class="sxs-lookup"><span data-stu-id="7be19-144">Custodian report</span></span>

<span data-ttu-id="7be19-145">中的 eDiscovery 工作流程之主旨的法律案件或調查的人稱為*資料 custodians* （或只是*custodians*），且會定義為 「 人員擁有管理控制文件或電子檔案 」。</span><span class="sxs-lookup"><span data-stu-id="7be19-145">In the eDiscovery workflow, individuals who are the subject of a legal case or investigation are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="7be19-146">Custodian 報告可協助您識別所有其資料來源處於 custodians 按住您的組織中的所有案例。</span><span class="sxs-lookup"><span data-stu-id="7be19-146">The Custodian report helps you identify all the custodians whose data sources are placed on hold for all cases in your organization.</span></span>

|<span data-ttu-id="7be19-147">欄</span><span class="sxs-lookup"><span data-stu-id="7be19-147">Column</span></span>         |<span data-ttu-id="7be19-148">描述</span><span class="sxs-lookup"><span data-stu-id="7be19-148">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="7be19-149">Custodian 名稱</span><span class="sxs-lookup"><span data-stu-id="7be19-149">Custodian name</span></span>| <span data-ttu-id="7be19-150">在 [Active Directory custodian 名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-150">The name of the custodian in Active Directory.</span></span>|
|<span data-ttu-id="7be19-151">Custodian UPN</span><span class="sxs-lookup"><span data-stu-id="7be19-151">Custodian UPN</span></span> | <span data-ttu-id="7be19-152">Custodian 使用者主體名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-152">The user principal name of the custodian.</span></span>|
|<span data-ttu-id="7be19-153">Custodian 識別碼</span><span class="sxs-lookup"><span data-stu-id="7be19-153">Custodian ID</span></span> | <span data-ttu-id="7be19-154">Custodian 內的特定案例的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7be19-154">The unique identifier for the custodian within a given case.</span></span> |
|<span data-ttu-id="7be19-155">案例名稱</span><span class="sxs-lookup"><span data-stu-id="7be19-155">Case name</span></span> | <span data-ttu-id="7be19-156">案例的使用者定義的名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-156">The user-defined name of the case.</span></span>|
|<span data-ttu-id="7be19-157">保留狀態</span><span class="sxs-lookup"><span data-stu-id="7be19-157">Hold status</span></span> | <span data-ttu-id="7be19-158">會指出是否 custodian 目前保留，或者如果他們已經發行從案例。</span><span class="sxs-lookup"><span data-stu-id="7be19-158">Indicates if the custodian is currently on hold or if they have been released from the case.</span></span>|
|<span data-ttu-id="7be19-159">大小寫的識別碼</span><span class="sxs-lookup"><span data-stu-id="7be19-159">Case Id</span></span> | <span data-ttu-id="7be19-160">這種情況的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7be19-160">The unique identifier for the case.</span></span>|
|<span data-ttu-id="7be19-161">通訊狀態</span><span class="sxs-lookup"><span data-stu-id="7be19-161">Communication status</span></span> |<span data-ttu-id="7be19-162">代表 custodian 是否所發出的合法持有通知。</span><span class="sxs-lookup"><span data-stu-id="7be19-162">Indicates if the custodian was issued a legal hold notification or not.</span></span> |
|<span data-ttu-id="7be19-163">新增 custodian</span><span class="sxs-lookup"><span data-stu-id="7be19-163">Custodian added</span></span> | <span data-ttu-id="7be19-164">Custodian 已新增至案例的日期。</span><span class="sxs-lookup"><span data-stu-id="7be19-164">The date the custodian was added to the case.</span></span> <span data-ttu-id="7be19-165">日期為 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="7be19-165">Dates are in UTC format.</span></span>|
|||

## <a name="data-source-report"></a><span data-ttu-id="7be19-166">資料來源的報表</span><span class="sxs-lookup"><span data-stu-id="7be19-166">Data source report</span></span>

<span data-ttu-id="7be19-167">您可以使用進階電子文件探索案例來建立保留來保留可能與案件相關的內容。</span><span class="sxs-lookup"><span data-stu-id="7be19-167">You can use an Advanced eDiscovery case to create holds to preserve content that may be relevant to the case.</span></span> <span data-ttu-id="7be19-168">使用進階電子文件保留功能，您可以將保留 custodians 和其資料來源上。</span><span class="sxs-lookup"><span data-stu-id="7be19-168">Using the Advanced eDiscovery hold capabilities, you can place holds on custodians and their data sources.</span></span> <span data-ttu-id="7be19-169">此外，您可以保留非 custodial 信箱和 OneDrive for 商務用帳戶。</span><span class="sxs-lookup"><span data-stu-id="7be19-169">Additionally, you can place a non-custodial hold on mailboxes and OneDrive for Business accounts.</span></span> <span data-ttu-id="7be19-170">您可以使用資料來源報表彙總的詳細資訊的相關內容位置上的按住您的組織中的所有案例。</span><span class="sxs-lookup"><span data-stu-id="7be19-170">You can use the data sources report to aggregate details about content locations on hold for all cases in your organization.</span></span>

|<span data-ttu-id="7be19-171">欄</span><span class="sxs-lookup"><span data-stu-id="7be19-171">Column</span></span>        |<span data-ttu-id="7be19-172">描述</span><span class="sxs-lookup"><span data-stu-id="7be19-172">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="7be19-173">大小寫的識別碼</span><span class="sxs-lookup"><span data-stu-id="7be19-173">Case ID</span></span> |<span data-ttu-id="7be19-174">每個案例的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7be19-174">The unique identifier for each case.</span></span> |
|<span data-ttu-id="7be19-175">工作負載</span><span class="sxs-lookup"><span data-stu-id="7be19-175">Workload</span></span> |<span data-ttu-id="7be19-176">會指出處於暫止狀態 （例如 Exchange 或 SharePoint） 的內容位置的類型。</span><span class="sxs-lookup"><span data-stu-id="7be19-176">Indicates the type of content location placed on hold (for example, Exchange or SharePoint).</span></span>
|<span data-ttu-id="7be19-177">位置名稱</span><span class="sxs-lookup"><span data-stu-id="7be19-177">Location name</span></span> |<span data-ttu-id="7be19-178">會指出 （適用於 Exchange 信箱） 的 SMTP 地址或內容的位置 （適用於 SharePoint 網站） 的 URL。</span><span class="sxs-lookup"><span data-stu-id="7be19-178">Indicates the SMTP address (for Exchange mailboxes) or the URL (for SharePoint sites) of the content location.</span></span> | 
|<span data-ttu-id="7be19-179">Custodian 識別碼</span><span class="sxs-lookup"><span data-stu-id="7be19-179">Custodian ID</span></span> |<span data-ttu-id="7be19-180">如果資料來源屬於 custodian，此欄顯示在特定情況下 custodian 的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7be19-180">If the data source belongs to a custodian, this column shows the unique identifier for the custodian in a given case.</span></span> <span data-ttu-id="7be19-181">此欄都是 null 非 custodial 的位置。</span><span class="sxs-lookup"><span data-stu-id="7be19-181">This column will be null for non-custodial locations.</span></span>|
|<span data-ttu-id="7be19-182">Custodian 名稱</span><span class="sxs-lookup"><span data-stu-id="7be19-182">Custodian name</span></span> |<span data-ttu-id="7be19-183">在 [Active Directory custodian 名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-183">The name of the custodian in Active Directory.</span></span>| 
|<span data-ttu-id="7be19-184">案例名稱</span><span class="sxs-lookup"><span data-stu-id="7be19-184">Case name</span></span> |<span data-ttu-id="7be19-185">案例的使用者定義的名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-185">The user-defined name of the case.</span></span>| 
|<span data-ttu-id="7be19-186">狀態</span><span class="sxs-lookup"><span data-stu-id="7be19-186">Status</span></span> |<span data-ttu-id="7be19-187">會指出內容的位置是否目前保留。</span><span class="sxs-lookup"><span data-stu-id="7be19-187">Indicates if the content location is currently on hold.</span></span> | 
|<span data-ttu-id="7be19-188">保留原則識別碼</span><span class="sxs-lookup"><span data-stu-id="7be19-188">Hold policy ID</span></span> |<span data-ttu-id="7be19-189">保留包含的內容位置的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7be19-189">The unique identifier for the hold that contains the content location.</span></span> | 
|<span data-ttu-id="7be19-190">建立保留日期</span><span class="sxs-lookup"><span data-stu-id="7be19-190">Hold created date</span></span> |<span data-ttu-id="7be19-191">會指出建立保留原則時的日期。</span><span class="sxs-lookup"><span data-stu-id="7be19-191">Indicates the date when the hold policy was created.</span></span> <span data-ttu-id="7be19-192">日期為 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="7be19-192">Dates are in UTC format.</span></span> | 
|<span data-ttu-id="7be19-193">保留原則名稱</span><span class="sxs-lookup"><span data-stu-id="7be19-193">Hold policy name</span></span> |<span data-ttu-id="7be19-194">包含的內容位置的保留名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-194">The name of the hold that contains the content location.</span></span> |
|<span data-ttu-id="7be19-195">保留已修改的日期</span><span class="sxs-lookup"><span data-stu-id="7be19-195">Hold modified date</span></span> |<span data-ttu-id="7be19-196">保留上次修改日期。</span><span class="sxs-lookup"><span data-stu-id="7be19-196">The date when the hold was last modified.</span></span> <span data-ttu-id="7be19-197">日期為 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="7be19-197">Dates are in UTC format.</span></span>| 
|<span data-ttu-id="7be19-198">上次修改者的保留</span><span class="sxs-lookup"><span data-stu-id="7be19-198">Hold last modified by</span></span>|<span data-ttu-id="7be19-199">上次修改日期保留使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-199">The name of the user that last modified the hold.</span></span>| 
|||

## <a name="communication-report"></a><span data-ttu-id="7be19-200">通訊報告</span><span class="sxs-lookup"><span data-stu-id="7be19-200">Communication report</span></span>

<span data-ttu-id="7be19-201">您的組織可能會發出通知 custodians 其義務保留一部分法律案件或調查的相關資訊的合法持有通知。</span><span class="sxs-lookup"><span data-stu-id="7be19-201">Your organization may issue legal hold notices to notify custodians of their obligation to preserve relevant information as part of legal case or investigation.</span></span> <span data-ttu-id="7be19-202">您可以使用通訊報告來檢視通知、 提醒、 擴大，與其他類型的通訊的彙總資料。</span><span class="sxs-lookup"><span data-stu-id="7be19-202">You can use the communications report to view aggregate data on acknowledgments, reminders, escalations, and other types of communications.</span></span>

|<span data-ttu-id="7be19-203">欄</span><span class="sxs-lookup"><span data-stu-id="7be19-203">Column</span></span>         |<span data-ttu-id="7be19-204">描述</span><span class="sxs-lookup"><span data-stu-id="7be19-204">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="7be19-205">大小寫的識別碼</span><span class="sxs-lookup"><span data-stu-id="7be19-205">Case ID</span></span> | <span data-ttu-id="7be19-206">這種情況的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7be19-206">The unique identifier for the case.</span></span>|
|<span data-ttu-id="7be19-207">案例名稱</span><span class="sxs-lookup"><span data-stu-id="7be19-207">Case name</span></span> | <span data-ttu-id="7be19-208">使用者定義的大小寫名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-208">User-defined name of the case.</span></span>|
|<span data-ttu-id="7be19-209">Custodian 識別碼</span><span class="sxs-lookup"><span data-stu-id="7be19-209">Custodian ID</span></span> |<span data-ttu-id="7be19-210">在特定情況下 custodian 唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7be19-210">The unique identifier for the custodian in a given case.</span></span>|
|<span data-ttu-id="7be19-211">Custodian 名稱</span><span class="sxs-lookup"><span data-stu-id="7be19-211">Custodian name</span></span> |<span data-ttu-id="7be19-212">Custodian 名稱。</span><span class="sxs-lookup"><span data-stu-id="7be19-212">The name of the custodian.</span></span>|
|<span data-ttu-id="7be19-213">請注意類型</span><span class="sxs-lookup"><span data-stu-id="7be19-213">Notice type</span></span> |<span data-ttu-id="7be19-214">會指出至 custodian 所發出的通知的類型。</span><span class="sxs-lookup"><span data-stu-id="7be19-214">Indicates the type of notice that was issued to the custodian.</span></span>|
|<span data-ttu-id="7be19-215">發出長</span><span class="sxs-lookup"><span data-stu-id="7be19-215">Issuing officer</span></span> |<span data-ttu-id="7be19-216">發出法律使用者的名稱保留通知。</span><span class="sxs-lookup"><span data-stu-id="7be19-216">The name of the user that issued the legal hold notification.</span></span>|
|<span data-ttu-id="7be19-217">通知事件</span><span class="sxs-lookup"><span data-stu-id="7be19-217">Notification event</span></span>|<span data-ttu-id="7be19-218">會指出傳送給使用者的合法持有通知訊息。</span><span class="sxs-lookup"><span data-stu-id="7be19-218">Indicates the legal hold notification message sent to the user.</span></span> <span data-ttu-id="7be19-219">可能的值包括： 提醒、 呈報、 而言，並保留發行。</span><span class="sxs-lookup"><span data-stu-id="7be19-219">Possible values include: Reminder, Escalation, Acknowledgment, and Hold Issuance.</span></span>|
|<span data-ttu-id="7be19-220">傳送的日期</span><span class="sxs-lookup"><span data-stu-id="7be19-220">Date sent</span></span> |<span data-ttu-id="7be19-221">通訊時所發行日期。</span><span class="sxs-lookup"><span data-stu-id="7be19-221">The date when the communication was issued.</span></span> <span data-ttu-id="7be19-222">Acknowledgments，此資料行表示 custodian 已認可通知的時間。</span><span class="sxs-lookup"><span data-stu-id="7be19-222">For acknowledgments, this column indicates the time that the notice was acknowledged by the custodian.</span></span> <span data-ttu-id="7be19-223">日期為 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="7be19-223">Dates are in UTC format.</span></span>|
|||
