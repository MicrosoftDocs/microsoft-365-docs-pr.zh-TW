---
title: 高級 eDiscovery 報告
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 387709ebdd84968d2b93992f6b92ef1548117569
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528356"
---
# <a name="advanced-ediscovery-reports-preview"></a><span data-ttu-id="f23e9-102">高級 eDiscovery 報告（預覽）</span><span class="sxs-lookup"><span data-stu-id="f23e9-102">Advanced eDiscovery reports (preview)</span></span>

<span data-ttu-id="f23e9-103">高級 eDiscovery 報告可協助您在整個組織中匯總案例資料，以簡化資料分析和組織報告。</span><span class="sxs-lookup"><span data-stu-id="f23e9-103">Advanced eDiscovery reports help you aggregate case data across your organization to streamline data analysis and organizational reporting.</span></span> <span data-ttu-id="f23e9-104">「高級 eDiscovery 報告」功能包含數個內建報告，可協助您回答如下的問題：</span><span class="sxs-lookup"><span data-stu-id="f23e9-104">The Advanced eDiscovery reports feature includes several built-in reports to help you answer questions like:</span></span>

- <span data-ttu-id="f23e9-105">在我的組織中，所有情況都有多少個主動保管人？</span><span class="sxs-lookup"><span data-stu-id="f23e9-105">How many active custodians are there for all cases in my organization?</span></span>

- <span data-ttu-id="f23e9-106">組織中所有案例的資料來源保留數目為何？</span><span class="sxs-lookup"><span data-stu-id="f23e9-106">How many data sources are on hold for all cases in my organization?</span></span>

- <span data-ttu-id="f23e9-107">在我的組織中所有案例的最後一個月內，已發出多少保留通知？</span><span class="sxs-lookup"><span data-stu-id="f23e9-107">How many hold notifications have been issued in the last month for all cases in my organization?</span></span>

- <span data-ttu-id="f23e9-108">組織中有多少作用中和封閉式案例？</span><span class="sxs-lookup"><span data-stu-id="f23e9-108">How many active and closed cases are there in my organization?</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f23e9-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="f23e9-109">Before you begin</span></span>

- <span data-ttu-id="f23e9-110">若要存取高級 eDiscovery 報告，您必須是 eDiscovery 系統管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f23e9-110">To access Advanced eDiscovery reports, you must be a member of the eDiscovery Admin role group.</span></span> <span data-ttu-id="f23e9-111">成為此角色群組的成員，可為您提供在報告中查看、篩選和匯出資料的必要許可權。</span><span class="sxs-lookup"><span data-stu-id="f23e9-111">Being a member of this role group provides you with the necessary permissions to view, filter, and export the data in the reports.</span></span> <span data-ttu-id="f23e9-112">如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f23e9-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="f23e9-113">每天都會刷新高級 eDiscovery 報告。</span><span class="sxs-lookup"><span data-stu-id="f23e9-113">Advanced eDiscovery reports are refreshed daily.</span></span> <span data-ttu-id="f23e9-114">因此，當新案例、保管人、資料來源及通訊建立時，以及在對應的報告中顯示時，可能會發生延遲。</span><span class="sxs-lookup"><span data-stu-id="f23e9-114">As a result, there may be a delay when new cases, custodians, data sources, and communications are created and when they appear in the corresponding report.</span></span>

<span data-ttu-id="f23e9-115">存取高級 eDiscovery 報告：</span><span class="sxs-lookup"><span data-stu-id="f23e9-115">To access the Advanced eDiscovery reports:</span></span>

1. <span data-ttu-id="f23e9-116">請移至 https://protection.office.com</span><span class="sxs-lookup"><span data-stu-id="f23e9-116">Go to https://protection.office.com</span></span>
  
2. <span data-ttu-id="f23e9-117">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f23e9-117">Sign into Office 365 using your work or school account.</span></span>
  
3. <span data-ttu-id="f23e9-118">在 [安全性 & 規範中心] 中，按一下 [ **eDiscovery > Advanced ediscovery**。</span><span class="sxs-lookup"><span data-stu-id="f23e9-118">In the Security & Compliance Center, click **eDiscovery > Advanced eDiscovery**.</span></span>
  
   <span data-ttu-id="f23e9-119">在 [ **Advanced eDiscovery** ] 首頁上，案例、保管人、資料來源及通訊報告索引標籤都顯示在頁面頂端。</span><span class="sxs-lookup"><span data-stu-id="f23e9-119">On the **Advanced eDiscovery** home page, the Case, Custodian, Data Source, and Communications report tabs are displayed across the top of the page.</span></span> 
  
   ![首頁上的高級 eDiscovery 報告](../media/report-home.png)

5. <span data-ttu-id="f23e9-121">若要查看報告，請按一下 [報告] 索引標籤，必要時您可以執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="f23e9-121">To view a report, click a report tab, and then if necessary you can do one of the following things:</span></span>

   ![您可以篩選或下載報表資料](../media/AeDReportsFilterDownload.png)

   <span data-ttu-id="f23e9-123">a.</span><span class="sxs-lookup"><span data-stu-id="f23e9-123">a.</span></span> <span data-ttu-id="f23e9-124">按一下 [**篩選**] 以縮小報表資料。</span><span class="sxs-lookup"><span data-stu-id="f23e9-124">Click **Filter** to narrow the report data.</span></span> <span data-ttu-id="f23e9-125">您可以針對每個報告篩選不同的屬性。</span><span class="sxs-lookup"><span data-stu-id="f23e9-125">You can filter on different properties for each report.</span></span>
  
   <span data-ttu-id="f23e9-126">b.</span><span class="sxs-lookup"><span data-stu-id="f23e9-126">b.</span></span> <span data-ttu-id="f23e9-127">按一下 [**下載到 csv** ]，將報告資料匯出至 csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="f23e9-127">Click **Download to CSV** to export the report data to a CSV file.</span></span>

## <a name="case-report"></a><span data-ttu-id="f23e9-128">案例報告</span><span class="sxs-lookup"><span data-stu-id="f23e9-128">Case report</span></span>

<span data-ttu-id="f23e9-129">案例報告會匯總組織中主動和封閉式預先探索案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f23e9-129">The Case report aggregates information about active and closed Advance eDiscovery cases in your organization.</span></span>

|<span data-ttu-id="f23e9-130">欄</span><span class="sxs-lookup"><span data-stu-id="f23e9-130">Column</span></span>        |<span data-ttu-id="f23e9-131">描述</span><span class="sxs-lookup"><span data-stu-id="f23e9-131">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="f23e9-132">案例識別碼</span><span class="sxs-lookup"><span data-stu-id="f23e9-132">Case ID</span></span> | <span data-ttu-id="f23e9-133">每個案例的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f23e9-133">The unique identifier for each case.</span></span>| 
|<span data-ttu-id="f23e9-134">案例名稱</span><span class="sxs-lookup"><span data-stu-id="f23e9-134">Case name</span></span> | <span data-ttu-id="f23e9-135">案例的使用者定義名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-135">User-defined name of the case.</span></span>|
|<span data-ttu-id="f23e9-136">狀態</span><span class="sxs-lookup"><span data-stu-id="f23e9-136">Status</span></span> | <span data-ttu-id="f23e9-137">會指出案例是否為使用中或已關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="f23e9-137">Indicates if the case is active or closed.</span></span>|
|<span data-ttu-id="f23e9-138">建立日期</span><span class="sxs-lookup"><span data-stu-id="f23e9-138">Date created</span></span> |<span data-ttu-id="f23e9-139">案例建立的第一天。</span><span class="sxs-lookup"><span data-stu-id="f23e9-139">Th date when the case was created.</span></span> <span data-ttu-id="f23e9-140">日期是 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f23e9-140">Dates are in UTC format.</span></span>|
|<span data-ttu-id="f23e9-141">上次修改日期</span><span class="sxs-lookup"><span data-stu-id="f23e9-141">Last modified</span></span> |<span data-ttu-id="f23e9-142">案例已關閉或上次更新的日期。</span><span class="sxs-lookup"><span data-stu-id="f23e9-142">The date when the case was closed or last updated.</span></span> <span data-ttu-id="f23e9-143">日期是 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f23e9-143">Dates are in UTC format.</span></span>| 
|||

## <a name="custodian-report"></a><span data-ttu-id="f23e9-144">保管人報告</span><span class="sxs-lookup"><span data-stu-id="f23e9-144">Custodian report</span></span>

<span data-ttu-id="f23e9-145">在 eDiscovery 工作流程中，法律案例或調查主旨的個人稱為「*資料保管人*」（或僅限*保管人*），而且會定義為「具有檔或電子檔的系統管理控制權」的人員。</span><span class="sxs-lookup"><span data-stu-id="f23e9-145">In the eDiscovery workflow, individuals who are the subject of a legal case or investigation are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="f23e9-146">保管人報告可協助您識別組織中所有案例的資料來源是保留狀態的所有保管人。</span><span class="sxs-lookup"><span data-stu-id="f23e9-146">The Custodian report helps you identify all the custodians whose data sources are placed on hold for all cases in your organization.</span></span>

|<span data-ttu-id="f23e9-147">欄</span><span class="sxs-lookup"><span data-stu-id="f23e9-147">Column</span></span>         |<span data-ttu-id="f23e9-148">描述</span><span class="sxs-lookup"><span data-stu-id="f23e9-148">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="f23e9-149">保管人名稱</span><span class="sxs-lookup"><span data-stu-id="f23e9-149">Custodian name</span></span>| <span data-ttu-id="f23e9-150">Active Directory 中的保管人名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-150">The name of the custodian in Active Directory.</span></span>|
|<span data-ttu-id="f23e9-151">保管人 UPN</span><span class="sxs-lookup"><span data-stu-id="f23e9-151">Custodian UPN</span></span> | <span data-ttu-id="f23e9-152">管理員的使用者主體名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-152">The user principal name of the custodian.</span></span>|
|<span data-ttu-id="f23e9-153">保管人識別碼</span><span class="sxs-lookup"><span data-stu-id="f23e9-153">Custodian ID</span></span> | <span data-ttu-id="f23e9-154">指定案例內管理員的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f23e9-154">The unique identifier for the custodian within a given case.</span></span> |
|<span data-ttu-id="f23e9-155">案例名稱</span><span class="sxs-lookup"><span data-stu-id="f23e9-155">Case name</span></span> | <span data-ttu-id="f23e9-156">案例的使用者定義名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-156">The user-defined name of the case.</span></span>|
|<span data-ttu-id="f23e9-157">保留狀態</span><span class="sxs-lookup"><span data-stu-id="f23e9-157">Hold status</span></span> | <span data-ttu-id="f23e9-158">會指出系統管理員目前是否正在暫止狀態，或是否已從案例中發放。</span><span class="sxs-lookup"><span data-stu-id="f23e9-158">Indicates if the custodian is currently on hold or if they have been released from the case.</span></span>|
|<span data-ttu-id="f23e9-159">案例識別碼</span><span class="sxs-lookup"><span data-stu-id="f23e9-159">Case Id</span></span> | <span data-ttu-id="f23e9-160">案例的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f23e9-160">The unique identifier for the case.</span></span>|
|<span data-ttu-id="f23e9-161">通訊狀態</span><span class="sxs-lookup"><span data-stu-id="f23e9-161">Communication status</span></span> |<span data-ttu-id="f23e9-162">會指出保管人是否已發出合法保留通知。</span><span class="sxs-lookup"><span data-stu-id="f23e9-162">Indicates if the custodian was issued a legal hold notification or not.</span></span> |
|<span data-ttu-id="f23e9-163">已新增保管人</span><span class="sxs-lookup"><span data-stu-id="f23e9-163">Custodian added</span></span> | <span data-ttu-id="f23e9-164">管理員加入案例的日期。</span><span class="sxs-lookup"><span data-stu-id="f23e9-164">The date the custodian was added to the case.</span></span> <span data-ttu-id="f23e9-165">日期是 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f23e9-165">Dates are in UTC format.</span></span>|
|||

## <a name="data-source-report"></a><span data-ttu-id="f23e9-166">資料來源報告</span><span class="sxs-lookup"><span data-stu-id="f23e9-166">Data source report</span></span>

<span data-ttu-id="f23e9-167">您可以使用 Advanced eDiscovery 案例來建立保留，以保留可能與案例相關的內容。</span><span class="sxs-lookup"><span data-stu-id="f23e9-167">You can use an Advanced eDiscovery case to create holds to preserve content that may be relevant to the case.</span></span> <span data-ttu-id="f23e9-168">使用「高級 eDiscovery 保留」功能，您可以將保留置於保管人及其資料來源。</span><span class="sxs-lookup"><span data-stu-id="f23e9-168">Using the Advanced eDiscovery hold capabilities, you can place holds on custodians and their data sources.</span></span> <span data-ttu-id="f23e9-169">此外，您可以對信箱和 OneDrive 的商務帳戶進行非 custodial 保留。</span><span class="sxs-lookup"><span data-stu-id="f23e9-169">Additionally, you can place a non-custodial hold on mailboxes and OneDrive for Business accounts.</span></span> <span data-ttu-id="f23e9-170">您可以使用 [資料來源] 報告，針對組織中的所有案例，匯總有關保留內容位置的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f23e9-170">You can use the data sources report to aggregate details about content locations on hold for all cases in your organization.</span></span>

|<span data-ttu-id="f23e9-171">欄</span><span class="sxs-lookup"><span data-stu-id="f23e9-171">Column</span></span>        |<span data-ttu-id="f23e9-172">描述</span><span class="sxs-lookup"><span data-stu-id="f23e9-172">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="f23e9-173">案例識別碼</span><span class="sxs-lookup"><span data-stu-id="f23e9-173">Case ID</span></span> |<span data-ttu-id="f23e9-174">每個案例的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f23e9-174">The unique identifier for each case.</span></span> |
|<span data-ttu-id="f23e9-175">工作負載</span><span class="sxs-lookup"><span data-stu-id="f23e9-175">Workload</span></span> |<span data-ttu-id="f23e9-176">會指出置於保留狀態的內容位置類型（例如，Exchange 或 SharePoint）。</span><span class="sxs-lookup"><span data-stu-id="f23e9-176">Indicates the type of content location placed on hold (for example, Exchange or SharePoint).</span></span>
|<span data-ttu-id="f23e9-177">位置名稱</span><span class="sxs-lookup"><span data-stu-id="f23e9-177">Location name</span></span> |<span data-ttu-id="f23e9-178">表示內容位置的 SMTP 位址（適用于 Exchange 信箱）或 URL （SharePoint 網站）。</span><span class="sxs-lookup"><span data-stu-id="f23e9-178">Indicates the SMTP address (for Exchange mailboxes) or the URL (for SharePoint sites) of the content location.</span></span> | 
|<span data-ttu-id="f23e9-179">保管人識別碼</span><span class="sxs-lookup"><span data-stu-id="f23e9-179">Custodian ID</span></span> |<span data-ttu-id="f23e9-180">如果資料來源屬於保管人，此欄位會顯示在指定的情況下，管理員的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f23e9-180">If the data source belongs to a custodian, this column shows the unique identifier for the custodian in a given case.</span></span> <span data-ttu-id="f23e9-181">對於非 custodial 位置，此欄會是 null。</span><span class="sxs-lookup"><span data-stu-id="f23e9-181">This column will be null for non-custodial locations.</span></span>|
|<span data-ttu-id="f23e9-182">保管人名稱</span><span class="sxs-lookup"><span data-stu-id="f23e9-182">Custodian name</span></span> |<span data-ttu-id="f23e9-183">Active Directory 中的保管人名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-183">The name of the custodian in Active Directory.</span></span>| 
|<span data-ttu-id="f23e9-184">案例名稱</span><span class="sxs-lookup"><span data-stu-id="f23e9-184">Case name</span></span> |<span data-ttu-id="f23e9-185">案例的使用者定義名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-185">The user-defined name of the case.</span></span>| 
|<span data-ttu-id="f23e9-186">狀態</span><span class="sxs-lookup"><span data-stu-id="f23e9-186">Status</span></span> |<span data-ttu-id="f23e9-187">會指出內容位置目前是否處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="f23e9-187">Indicates if the content location is currently on hold.</span></span> | 
|<span data-ttu-id="f23e9-188">保留原則識別碼</span><span class="sxs-lookup"><span data-stu-id="f23e9-188">Hold policy ID</span></span> |<span data-ttu-id="f23e9-189">包含內容位置之保留的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f23e9-189">The unique identifier for the hold that contains the content location.</span></span> | 
|<span data-ttu-id="f23e9-190">保留建立日期</span><span class="sxs-lookup"><span data-stu-id="f23e9-190">Hold created date</span></span> |<span data-ttu-id="f23e9-191">會指出保留原則的建立日期。</span><span class="sxs-lookup"><span data-stu-id="f23e9-191">Indicates the date when the hold policy was created.</span></span> <span data-ttu-id="f23e9-192">日期是 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f23e9-192">Dates are in UTC format.</span></span> | 
|<span data-ttu-id="f23e9-193">保留原則名稱</span><span class="sxs-lookup"><span data-stu-id="f23e9-193">Hold policy name</span></span> |<span data-ttu-id="f23e9-194">包含內容位置之保留的名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-194">The name of the hold that contains the content location.</span></span> |
|<span data-ttu-id="f23e9-195">保留修改日期</span><span class="sxs-lookup"><span data-stu-id="f23e9-195">Hold modified date</span></span> |<span data-ttu-id="f23e9-196">上次修改保留的日期。</span><span class="sxs-lookup"><span data-stu-id="f23e9-196">The date when the hold was last modified.</span></span> <span data-ttu-id="f23e9-197">日期是 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f23e9-197">Dates are in UTC format.</span></span>| 
|<span data-ttu-id="f23e9-198">保留上次修改者</span><span class="sxs-lookup"><span data-stu-id="f23e9-198">Hold last modified by</span></span>|<span data-ttu-id="f23e9-199">上次修改保留之使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-199">The name of the user that last modified the hold.</span></span>| 
|||

## <a name="communication-report"></a><span data-ttu-id="f23e9-200">通訊報告</span><span class="sxs-lookup"><span data-stu-id="f23e9-200">Communication report</span></span>

<span data-ttu-id="f23e9-201">您的組織可能會發出法律封存通知，以通知保管人在法律案例或調查過程中，將相關資訊保留在法律上的義務。</span><span class="sxs-lookup"><span data-stu-id="f23e9-201">Your organization may issue legal hold notices to notify custodians of their obligation to preserve relevant information as part of legal case or investigation.</span></span> <span data-ttu-id="f23e9-202">您可以使用通訊報告來查看有關確認、提醒、升級和其他通訊類型的匯總資料。</span><span class="sxs-lookup"><span data-stu-id="f23e9-202">You can use the communications report to view aggregate data on acknowledgments, reminders, escalations, and other types of communications.</span></span>

|<span data-ttu-id="f23e9-203">欄</span><span class="sxs-lookup"><span data-stu-id="f23e9-203">Column</span></span>         |<span data-ttu-id="f23e9-204">描述</span><span class="sxs-lookup"><span data-stu-id="f23e9-204">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="f23e9-205">案例識別碼</span><span class="sxs-lookup"><span data-stu-id="f23e9-205">Case ID</span></span> | <span data-ttu-id="f23e9-206">案例的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f23e9-206">The unique identifier for the case.</span></span>|
|<span data-ttu-id="f23e9-207">案例名稱</span><span class="sxs-lookup"><span data-stu-id="f23e9-207">Case name</span></span> | <span data-ttu-id="f23e9-208">案例的使用者定義名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-208">User-defined name of the case.</span></span>|
|<span data-ttu-id="f23e9-209">保管人識別碼</span><span class="sxs-lookup"><span data-stu-id="f23e9-209">Custodian ID</span></span> |<span data-ttu-id="f23e9-210">在指定的情況下，保管人的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f23e9-210">The unique identifier for the custodian in a given case.</span></span>|
|<span data-ttu-id="f23e9-211">保管人名稱</span><span class="sxs-lookup"><span data-stu-id="f23e9-211">Custodian name</span></span> |<span data-ttu-id="f23e9-212">管理員的名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-212">The name of the custodian.</span></span>|
|<span data-ttu-id="f23e9-213">公告類型</span><span class="sxs-lookup"><span data-stu-id="f23e9-213">Notice type</span></span> |<span data-ttu-id="f23e9-214">會指出發出給保管人的通知類型。</span><span class="sxs-lookup"><span data-stu-id="f23e9-214">Indicates the type of notice that was issued to the custodian.</span></span>|
|<span data-ttu-id="f23e9-215">簽發官</span><span class="sxs-lookup"><span data-stu-id="f23e9-215">Issuing officer</span></span> |<span data-ttu-id="f23e9-216">發出合法保留通知的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="f23e9-216">The name of the user that issued the legal hold notification.</span></span>|
|<span data-ttu-id="f23e9-217">Notification 事件</span><span class="sxs-lookup"><span data-stu-id="f23e9-217">Notification event</span></span>|<span data-ttu-id="f23e9-218">表示傳送給使用者的法律封存通知訊息。</span><span class="sxs-lookup"><span data-stu-id="f23e9-218">Indicates the legal hold notification message sent to the user.</span></span> <span data-ttu-id="f23e9-219">可能的值包括：提醒、升級、確認和保留發佈。</span><span class="sxs-lookup"><span data-stu-id="f23e9-219">Possible values include: Reminder, Escalation, Acknowledgment, and Hold Issuance.</span></span>|
|<span data-ttu-id="f23e9-220">傳送日期</span><span class="sxs-lookup"><span data-stu-id="f23e9-220">Date sent</span></span> |<span data-ttu-id="f23e9-221">通訊的發行日期。</span><span class="sxs-lookup"><span data-stu-id="f23e9-221">The date when the communication was issued.</span></span> <span data-ttu-id="f23e9-222">若為回執，此欄會指出管理員認可的通知時間。</span><span class="sxs-lookup"><span data-stu-id="f23e9-222">For acknowledgments, this column indicates the time that the notice was acknowledged by the custodian.</span></span> <span data-ttu-id="f23e9-223">日期是 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f23e9-223">Dates are in UTC format.</span></span>|
|||
