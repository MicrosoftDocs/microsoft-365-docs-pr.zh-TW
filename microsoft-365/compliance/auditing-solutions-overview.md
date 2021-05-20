---
title: Microsoft 365 稽核解決方案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: 了解如何稽核 Microsoft 365 組織中使用者和管理員的活動。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d8686a2cd7b1fc6e9082e85b18ba352c1fd7f830
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538498"
---
# <a name="auditing-solutions-in-microsoft-365"></a><span data-ttu-id="b9fba-103">Microsoft 365 中的稽核解決方案</span><span class="sxs-lookup"><span data-stu-id="b9fba-103">Auditing solutions in Microsoft 365</span></span>

<span data-ttu-id="b9fba-104">Microsoft 365 稽核解決方案提供了整合式解決方案，可協助組織有效地回應安全性事件、鑑識調查、內部調查和合規性義務。</span><span class="sxs-lookup"><span data-stu-id="b9fba-104">Microsoft 365 auditing solutions provide an integrated solution to help organizations effectively respond to security events, forensic investigations, internal investigations, and compliance obligations.</span></span> <span data-ttu-id="b9fba-105">在數十個 Microsoft 365 服務和解決方案中執行的數千個使用者和管理作業被擷取、記錄並保留在組織的整合稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="b9fba-105">Thousands of user and admin operations performed in dozens of Microsoft 365 services and solutions are captured, recorded, and retained in your organization's unified audit log.</span></span> <span data-ttu-id="b9fba-106">這些事件的稽核記錄可由組織中的安全性操作員、IT 管理員、內部風險小組以及合規性和法律調查人員進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="b9fba-106">Audit records for these events are searchable by security ops, IT admins, insider risk teams, and compliance and legal investigators in your organization.</span></span> <span data-ttu-id="b9fba-107">此功能提供了對跨 Microsoft 365 組織執行的活動的可見度。</span><span class="sxs-lookup"><span data-stu-id="b9fba-107">This capability provides visibility into the activities performed across your Microsoft 365 organization.</span></span>

## <a name="microsoft-365-auditing-solutions"></a><span data-ttu-id="b9fba-108">Microsoft 365 稽核解決方案</span><span class="sxs-lookup"><span data-stu-id="b9fba-108">Microsoft 365 auditing solutions</span></span>

<span data-ttu-id="b9fba-109">Microsoft 365 提供兩種稽核解決方案：基本稽核和進階稽核。</span><span class="sxs-lookup"><span data-stu-id="b9fba-109">Microsoft 365 provides two auditing solutions: Basic Audit and Advanced Audit.</span></span>

![基本稽核和進階稽核的重要功能](..\media\AuditingSolutionsComparison.png)

### <a name="basic-audit"></a><span data-ttu-id="b9fba-111">基本稽核</span><span class="sxs-lookup"><span data-stu-id="b9fba-111">Basic Audit</span></span>

<span data-ttu-id="b9fba-112">基本稽核提供了記錄和搜尋已稽核活動的功能，並協助您的鑑識、IT、合規性和法律調查。</span><span class="sxs-lookup"><span data-stu-id="b9fba-112">Basic Audit provides with you with the ability to log and search for audited activities and power your forensic, IT, compliance, and legal investigations.</span></span>

- <span data-ttu-id="b9fba-113">**預設啟用**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-113">**Enabled by default**.</span></span> <span data-ttu-id="b9fba-114">根據預設，所有具有相應訂閱的組織都會啟用基本稽核。</span><span class="sxs-lookup"><span data-stu-id="b9fba-114">Basic Audit is turned on by default for all organizations with the appropriate subscription.</span></span> <span data-ttu-id="b9fba-115">這意味著已稽核活動的記錄將被擷取和可搜尋。</span><span class="sxs-lookup"><span data-stu-id="b9fba-115">That means records for audited activities will be captured and searchable.</span></span> <span data-ttu-id="b9fba-116">唯一需要的設定是指派存取稽核記錄搜尋工具 (和相應的 cmdlet) 所需的授權，並確定為使用者指派了進階稽核功能的正確權限。</span><span class="sxs-lookup"><span data-stu-id="b9fba-116">The only setup that required is to assign the necessary permissions to access the audit log search tool (and the corresponding cmdlet) and make sure that user's are assigned the right license for Advanced Audit features.</span></span>
- <span data-ttu-id="b9fba-117">**數千個可搜尋的稽核事件**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-117">**Thousands of searchable audit events**.</span></span> <span data-ttu-id="b9fba-118">您可以搜尋範圍廣泛、發生在貴組織中的大多數 Microsoft 365 服務中的已稽核活動。</span><span class="sxs-lookup"><span data-stu-id="b9fba-118">You can search for a wide-range of audited activities that occur is most of the Microsoft 365 services in your organization.</span></span> <span data-ttu-id="b9fba-119">有關您可以搜尋的活動之部分清單，請參閱[已稽核活動](search-the-audit-log-in-security-and-compliance.md#audited-activities)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-119">For a partial list of the activities you can search for, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="b9fba-120">有關支援已稽核活動的服務和功能的清單，請參閱[稽核記錄的記錄類型](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-120">For a list of the services and features that support audited activities, see [Audit log record type](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span>
- <span data-ttu-id="b9fba-121">**Microsoft 365 合規性中心中的稽核搜尋工具**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-121">**Audit search tool in the Microsoft 365 compliance center**.</span></span> <span data-ttu-id="b9fba-122">使用 Microsoft 365 合規性中心中的稽核記錄搜尋工具搜尋稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="b9fba-122">Use the Audit log search tool in the Microsoft 365 compliance center to search for audit records.</span></span> <span data-ttu-id="b9fba-123">您可以搜尋特定活動、特定使用者執行的活動以及日期範圍內發生的活動。</span><span class="sxs-lookup"><span data-stu-id="b9fba-123">You can search for specific activities, for activities performed by specific users, and activities that occurred with a date range.</span></span> <span data-ttu-id="b9fba-124">以下是合規中心稽核搜尋工具的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="b9fba-124">Here's a screenshot of the Audit search tool in the compliance center.</span></span>

   ![Microsoft 365 合規性中心中的稽核記錄搜尋工具](../media/AuditLogSearchToolMCC.png)

- <span data-ttu-id="b9fba-126">**Search-UnifiedAuditLog cmdlet**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-126">**Search-UnifiedAuditLog cmdlet**.</span></span> <span data-ttu-id="b9fba-127">您還可以在 Exchange Online PowerShell (搜尋工具的基礎 cmdlet) 中使用 **Search-UnifiedAuditLog** cmdlet 來搜尋稽核事件或在指令碼中使用。</span><span class="sxs-lookup"><span data-stu-id="b9fba-127">You can also use the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell (the underlying cmdlet for the search tool) to search for audit events or to use in a script.</span></span> <span data-ttu-id="b9fba-128">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b9fba-128">For more information, see:</span></span>

  - [<span data-ttu-id="b9fba-129">Search-UnifiedAuditLog cmdlet 參考資料</span><span class="sxs-lookup"><span data-stu-id="b9fba-129">Search-UnifiedAuditLog cmdlet reference</span></span>](/powershell/module/exchange/search-unifiedauditlog)
  - [<span data-ttu-id="b9fba-130">使用 PowerShell 指令碼來搜尋稽核記錄</span><span class="sxs-lookup"><span data-stu-id="b9fba-130">Use a PowerShell script to search the audit log</span></span>](audit-log-search-script.md)

- <span data-ttu-id="b9fba-131">**將稽核記錄匯出至 CSV 檔案**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-131">**Export audit records to a CSV file**.</span></span> <span data-ttu-id="b9fba-132">在合規性中心執行稽核記錄搜尋工具後，可以將搜尋返回的稽核記錄匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="b9fba-132">After running the Audit log search tool in the compliance center, you can export the audit records returned by the search to a CSV file.</span></span> <span data-ttu-id="b9fba-133">這可讓您對不同的稽核記錄屬性使用 Microsoft Excel 排序和篩選。</span><span class="sxs-lookup"><span data-stu-id="b9fba-133">This lets you use Microsoft Excel sort and filter on different audit record properties.</span></span> <span data-ttu-id="b9fba-134">您還可以使用 Excel Power Query 轉換功能將 AuditData JSON 物件中的每個屬性分割至其資料行。</span><span class="sxs-lookup"><span data-stu-id="b9fba-134">You can also use Excel Power Query transform functionality to split each property in the AuditData JSON object into its own column.</span></span> <span data-ttu-id="b9fba-135">這可讓您有效地檢視和比較不同事件的類似資料。</span><span class="sxs-lookup"><span data-stu-id="b9fba-135">This lets you effectively view and compare similar data for different events.</span></span> <span data-ttu-id="b9fba-136">如需詳細資訊，請參閱[匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-136">For more information, see [Export, configure, and view audit log records](export-view-audit-log-records.md).</span></span>

- <span data-ttu-id="b9fba-137">**透過 Office 365 管理活動 API 存取稽核記錄**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-137">**Access to audit logs via Office 365 Management Activity API**.</span></span> <span data-ttu-id="b9fba-138">存取和擷取稽核記錄的第三種方法是使用 Office 365 管理活動 API。</span><span class="sxs-lookup"><span data-stu-id="b9fba-138">A third method for accessing and retrieving audit records is to use the Office 365 Management Activity API.</span></span> <span data-ttu-id="b9fba-139">這使得組織保留稽核資料的時間長於預設的 90 天，並可讓它們將稽核資料匯入至 SIEM 解決方案。</span><span class="sxs-lookup"><span data-stu-id="b9fba-139">This lets organizations retain auditing data for longer periods than the default 90 days and lets them import their auditing data to a SIEM solution.</span></span> <span data-ttu-id="b9fba-140">如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-140">For more information, see [Office 365 Management Activity API reference](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

- <span data-ttu-id="b9fba-141">**90 天稽核記錄保留**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-141">**90-day audit log retention**.</span></span> <span data-ttu-id="b9fba-142">當使用者或系統管理員執行稽核的活動時，稽核記錄會隨即產生，並儲存在您組織的稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="b9fba-142">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="b9fba-143">在基本稽核中記錄將保留 90 天，這意味著您可以搜尋過去三個月內發生的活動。</span><span class="sxs-lookup"><span data-stu-id="b9fba-143">In Basic Audit, records are retained for 90 days, which means you can search for activities that occurred within the past three months.</span></span>

### <a name="advanced-audit"></a><span data-ttu-id="b9fba-144">進階稽核</span><span class="sxs-lookup"><span data-stu-id="b9fba-144">Advanced Audit</span></span>

<span data-ttu-id="b9fba-145">進階稽核提升了基本稽核功能，提供稽核記錄保留原則、更長的稽核記錄保留期、高價值重要事件以及對 Office 365 管理活動 API 的更高頻寬存取。</span><span class="sxs-lookup"><span data-stu-id="b9fba-145">Advanced Audit builds on the capabilities of Basic Audit by providing audit log retention policies, longer retention of audit records, high-value crucial events, and higher bandwidth access to the Office 365 Management Activity API.</span></span>

- <span data-ttu-id="b9fba-146">**稽核記錄保留原則**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-146">**Audit log retention policies**.</span></span> <span data-ttu-id="b9fba-147">您可以建立自訂稽核記錄保留原則，以將稽核記錄保留更長的時間，上限為一年 (對於具有所需附加元件授權的使用者，上限為 10 年)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-147">You can create customized audit log retention policies to retain audit records for longer periods of time up to one year (and up to 10 years for users with required add-on license).</span></span> <span data-ttu-id="b9fba-148">您可以建立原則，保留根據發生稽核活動的服務、特定稽核活動或執行稽核活動的使用者之稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="b9fba-148">You can create a policy to retain audit records based the service where the audited activities occur, specific audited activities, or the user who performs an audited activity.</span></span>

- <span data-ttu-id="b9fba-149">**稽核記錄的較長保留期**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-149">**Longer retention of audit records**.</span></span> <span data-ttu-id="b9fba-150">根據預設，Exchange、SharePoint 和 Azure Active Directory 稽核記錄保留一年。</span><span class="sxs-lookup"><span data-stu-id="b9fba-150">Exchange, SharePoint, and Azure Active Directory audit records are retained for one year by default.</span></span> <span data-ttu-id="b9fba-151">根據預設，所有其他活動的稽核記錄保留 90 天，或者您可以使用稽核記錄保留原則設定更長的保留期。</span><span class="sxs-lookup"><span data-stu-id="b9fba-151">Audit records for all other activities are retained for 90 days by default, or you can use audit log retention policies to configure longer retention periods.</span></span>

- <span data-ttu-id="b9fba-152">**高價值的重要事件**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-152">**High-value, crucial events**.</span></span> <span data-ttu-id="b9fba-153">重要事件的稽核記錄可提供對事件的可見度 (例如存取郵件項目的時間、回覆和轉寄郵件項目的時間，或使用者在 Exchange Online 和 SharePoint Online 中搜尋的時間和內容)，協助貴組織進行鑑識和合規性調查。</span><span class="sxs-lookup"><span data-stu-id="b9fba-153">Audit records for crucial events can help your organization conduct forensic and compliance investigations by providing visibility to events such as when mail items were accessed, or when mail items were replied to and forwarded, or when and what a user searched for in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="b9fba-154">這些重要事件可協助您調查可能的破壞，並判斷危害的範圍。</span><span class="sxs-lookup"><span data-stu-id="b9fba-154">These crucial events can help you investigate possible breaches and determine the scope of compromise.</span></span>

- <span data-ttu-id="b9fba-155">**Office 365 管理活動 API 的更高頻寬**。</span><span class="sxs-lookup"><span data-stu-id="b9fba-155">**Higher bandwidth to the Office 365 Management Activity API**.</span></span> <span data-ttu-id="b9fba-156">進階稽核透過 Office 365 管理活動 API 為組織提供了更多的頻寬以存取稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="b9fba-156">Advanced Audit provides organizations with more bandwidth to access auditing logs through the Office 365 Management Activity API.</span></span> <span data-ttu-id="b9fba-157">儘管所有組織 (具有基本稽核或進階稽核) 最初配置的基準為每分鐘 2000 個要求，但此限制將根據組織的基座數及其授權訂閱動態增加。</span><span class="sxs-lookup"><span data-stu-id="b9fba-157">Although all organizations (that have Basic Audit or Advanced Audit) are initially allocated a baseline of 2,000 requests per minute, this limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="b9fba-158">這導致使用進階稽核的組織取得的頻寬是使用基本稽核組織的兩倍。</span><span class="sxs-lookup"><span data-stu-id="b9fba-158">This results in organizations with Advanced Audit getting about twice the bandwidth as organizations with Basic Audit.</span></span>

<span data-ttu-id="b9fba-159">有關進階稽核功能的詳細資訊，請參閱 [Microsoft 365 中的進階稽核](advanced-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-159">For more detailed information about Advanced Audit features, see [Advanced Audit in Microsoft 365](advanced-audit.md).</span></span>

## <a name="comparison-of-key-capabilities"></a><span data-ttu-id="b9fba-160">主要功能比較</span><span class="sxs-lookup"><span data-stu-id="b9fba-160">Comparison of key capabilities</span></span>

<span data-ttu-id="b9fba-161">以下表格比較了基本稽核和進階稽核中提供的主要功能。</span><span class="sxs-lookup"><span data-stu-id="b9fba-161">The following table compares the key capabilities available in Basic Audit and Advanced Audit.</span></span> <span data-ttu-id="b9fba-162">進階稽核中包含所有基本稽核功能。</span><span class="sxs-lookup"><span data-stu-id="b9fba-162">All Basic Audit functionality is included in Advanced Audit.</span></span>

|<span data-ttu-id="b9fba-163">功能</span><span class="sxs-lookup"><span data-stu-id="b9fba-163">Capability</span></span>|<span data-ttu-id="b9fba-164">基本稽核</span><span class="sxs-lookup"><span data-stu-id="b9fba-164">Basic Audit</span></span>|<span data-ttu-id="b9fba-165">進階稽核</span><span class="sxs-lookup"><span data-stu-id="b9fba-165">Advanced Audit</span></span>|
|:------|:-------------|:-------------|
|<span data-ttu-id="b9fba-166">預設啟用</span><span class="sxs-lookup"><span data-stu-id="b9fba-166">Enabled by default</span></span>|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|<span data-ttu-id="b9fba-169">數千個可搜尋的稽核事件</span><span class="sxs-lookup"><span data-stu-id="b9fba-169">Thousands of searchable audit events</span></span>|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|<span data-ttu-id="b9fba-172">Microsoft 365 合規性中心中的稽核搜尋工具</span><span class="sxs-lookup"><span data-stu-id="b9fba-172">Audit search tool in the Microsoft 365 compliance center</span></span>|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|<span data-ttu-id="b9fba-175">Search-UnifiedAuditLog cmdlet</span><span class="sxs-lookup"><span data-stu-id="b9fba-175">Search-UnifiedAuditLog cmdlet</span></span>|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|<span data-ttu-id="b9fba-178">將稽核記錄匯出至 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="b9fba-178">Export audit records to CSV file</span></span>|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|<span data-ttu-id="b9fba-181">透過 Office 365 管理活動 API 存取稽核記錄 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b9fba-181">Access to audit logs via Office 365 Management Activity API <sup>1</sup></span></span>|![支援](../media/check-mark.png)|<span data-ttu-id="b9fba-183">![支援](../media/check-mark.png)</sup></span><span class="sxs-lookup"><span data-stu-id="b9fba-183">![Supported](../media/check-mark.png)</sup></span></span>|
|<span data-ttu-id="b9fba-184">90 天稽核記錄保留</span><span class="sxs-lookup"><span data-stu-id="b9fba-184">90-day audit log retention</span></span>|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|<span data-ttu-id="b9fba-187">1 年稽核記錄保留</span><span class="sxs-lookup"><span data-stu-id="b9fba-187">1-year audit log retention</span></span>||![支援](../media/check-mark.png)|
|<span data-ttu-id="b9fba-189">10 年稽核記錄保留 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b9fba-189">10-year audit log retention <sup>2</sup></span></span>||![支援](../media/check-mark.png)|
|<span data-ttu-id="b9fba-191">稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="b9fba-191">Audit log retention policies</span></span>||![支援](../media/check-mark.png)|
|<span data-ttu-id="b9fba-193">高值，重要事件</span><span class="sxs-lookup"><span data-stu-id="b9fba-193">High-value, crucial events</span></span>||![支援](../media/check-mark.png)|
||||
> [!NOTE]
> <span data-ttu-id="b9fba-195"><sup>1</sup> 進階稽核包括對 Office 365 管理活動 API 的更高頻寬存取，提供對稽核資料的更快存取。</span><span class="sxs-lookup"><span data-stu-id="b9fba-195"><sup>1</sup> Advanced Audit includes higher bandwidth access to the Office 365 Management Activity API, which provides faster access to audit data.</span></span><br/><span data-ttu-id="b9fba-196"><sup>2</sup> 除了進階稽核所需的權限 (在下一節中介紹) 之外，還必須為使用者指派 10 年稽核記錄保留附加元件授權，以將其稽核記錄保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="b9fba-196"><sup>2</sup> In addition to the required licensing for Advanced Audit (described in the next section), a user must be assigned a 10-Year Audit Log Retention add on license to retain their audit records for 10 years.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="b9fba-197">授權需求</span><span class="sxs-lookup"><span data-stu-id="b9fba-197">Licensing requirements</span></span>

<span data-ttu-id="b9fba-198">以下各節確定了基本稽核和進階稽核的授權需求。</span><span class="sxs-lookup"><span data-stu-id="b9fba-198">The following sections identify the licensing requirements for Basic Audit and Advanced Audit.</span></span> <span data-ttu-id="b9fba-199">進階稽核包含基本稽核功能。</span><span class="sxs-lookup"><span data-stu-id="b9fba-199">Basic Audit functionality is included with Advanced Auditing.</span></span>

### <a name="basic-audit"></a><span data-ttu-id="b9fba-200">基本稽核</span><span class="sxs-lookup"><span data-stu-id="b9fba-200">Basic Audit</span></span>

- <span data-ttu-id="b9fba-201">Microsoft 365 企業版 E3 訂閱</span><span class="sxs-lookup"><span data-stu-id="b9fba-201">Microsoft 365 Enterprise E3 subscription</span></span>
- <span data-ttu-id="b9fba-202">Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="b9fba-202">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="b9fba-203">Microsoft 365 教育版 A3 訂閱</span><span class="sxs-lookup"><span data-stu-id="b9fba-203">Microsoft 365 Education A3 subscription</span></span>
- <span data-ttu-id="b9fba-204">Microsoft 365 政府版 G3 訂閱</span><span class="sxs-lookup"><span data-stu-id="b9fba-204">Microsoft 365 Government G3 subscription</span></span>
- <span data-ttu-id="b9fba-205">Microsoft 365 政府版 G1 訂閱</span><span class="sxs-lookup"><span data-stu-id="b9fba-205">Microsoft 365 Government G1 subscription</span></span>
- <span data-ttu-id="b9fba-206">Office 365 企業版 E3 訂閲</span><span class="sxs-lookup"><span data-stu-id="b9fba-206">Office 365 Enterprise E3 subscription</span></span>
- <span data-ttu-id="b9fba-207">Office 365 企業版 E1 訂閲</span><span class="sxs-lookup"><span data-stu-id="b9fba-207">Office 365 Enterprise E1 subscription</span></span>
- <span data-ttu-id="b9fba-208">Office 365 教育版 A1 訂閱</span><span class="sxs-lookup"><span data-stu-id="b9fba-208">Office 365 Education A1 subscription</span></span>
- <span data-ttu-id="b9fba-209">Office 365 教育版 A3 訂閲</span><span class="sxs-lookup"><span data-stu-id="b9fba-209">Office 365 Education A3 subscription</span></span>

### <a name="advanced-audit"></a><span data-ttu-id="b9fba-210">進階稽核</span><span class="sxs-lookup"><span data-stu-id="b9fba-210">Advanced Audit</span></span>

- <span data-ttu-id="b9fba-211">Microsoft 365 企業版 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="b9fba-211">Microsoft 365 Enterprise E5 subscription</span></span>
- <span data-ttu-id="b9fba-212">Microsoft 365 企業版 E3 訂閱 + Microsoft 365 E5 合規性附加元件</span><span class="sxs-lookup"><span data-stu-id="b9fba-212">Microsoft 365 Enterprise E3 subscription + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="b9fba-213">Microsoft 365 企業版 E3 訂閱 + Microsoft 365 E5 電子文件探索和稽核附加元件</span><span class="sxs-lookup"><span data-stu-id="b9fba-213">Microsoft 365 Enterprise E3 subscription + the Microsoft 365 E5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="b9fba-214">Microsoft 365 教育版 A5 訂閱</span><span class="sxs-lookup"><span data-stu-id="b9fba-214">Microsoft 365 Education A5 subscription</span></span>
- <span data-ttu-id="b9fba-215">Microsoft 365 教育版 A3 訂閱 + Microsoft 365 A5 合規性附加元件</span><span class="sxs-lookup"><span data-stu-id="b9fba-215">Microsoft 365 Education A3 subscription + the Microsoft 365 A5 Compliance add-on</span></span>
- <span data-ttu-id="b9fba-216">Microsoft 365 教育版 E3 訂閱 + Microsoft 365 A5 電子文件探索和稽核附加元件</span><span class="sxs-lookup"><span data-stu-id="b9fba-216">Microsoft 365 Education A3 subscription + the Microsoft 365 A5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="b9fba-217">Microsoft 365 政府版 G5 訂閱</span><span class="sxs-lookup"><span data-stu-id="b9fba-217">Microsoft 365 Government G5 subscription</span></span>
- <span data-ttu-id="b9fba-218">Microsoft 365 政府版 G5 訂閱 + Microsoft 365 G5 合規性附加元件</span><span class="sxs-lookup"><span data-stu-id="b9fba-218">Microsoft 365 Government G5 subscription + the Microsoft 365 G5 Compliance add-on</span></span>
- <span data-ttu-id="b9fba-219">Microsoft 365 政府版 G5 訂閱 + Microsoft 365 G5 電子文件探索和稽核附加元件</span><span class="sxs-lookup"><span data-stu-id="b9fba-219">Microsoft 365 Government G5 subscription + the Microsoft 365 G5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="b9fba-220">Office 365 企業版 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="b9fba-220">Office 365 Enterprise E5 subscription</span></span>
- <span data-ttu-id="b9fba-221">Office 365 教育版 A5 訂閲</span><span class="sxs-lookup"><span data-stu-id="b9fba-221">Office 365 Education A5 subscription</span></span>
- <span data-ttu-id="b9fba-222">Office 365 企業版 E3 訂閱 + Office 365 進階合規性附加元件 (不再適用於新訂閱)</span><span class="sxs-lookup"><span data-stu-id="b9fba-222">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions)</span></span>

## <a name="set-up-microsoft-365-auditing-solutions"></a><span data-ttu-id="b9fba-223">設定 Microsoft 365 稽核解決方案</span><span class="sxs-lookup"><span data-stu-id="b9fba-223">Set up Microsoft 365 auditing solutions</span></span>

<span data-ttu-id="b9fba-224">要開始使用 Microsoft 365 中的稽核解決方案，請參閱以下設定指引。</span><span class="sxs-lookup"><span data-stu-id="b9fba-224">To get started using the auditing solutions in Microsoft 365, see the following setup guidance.</span></span>

### <a name="set-up-basic-audit"></a><span data-ttu-id="b9fba-225">設定基本稽核。</span><span class="sxs-lookup"><span data-stu-id="b9fba-225">Set up Basic Audit</span></span>

<span data-ttu-id="b9fba-226">第一步是設定基本稽核，然後開始執行稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="b9fba-226">The first step is to set up Basic Audit and then start running audit log searches.</span></span>

![設定基本稽核的工作流程](../media/BasicAuditingWorkflow.png)

1. <span data-ttu-id="b9fba-228">請驗證貴組織是否具有支援基本稽核的訂閱，以及是否具有支援進階稽核的訂閱 (若適用)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-228">Verify that your organization has a subscription that supports Basic Audit and if applicable, a subscription that supports Advanced Audit.</span></span>

2. <span data-ttu-id="b9fba-229">將 Exchange Online 中的權限指派給貴組織中將使用 Microsoft 365 合規性中心稽核記錄搜尋工具或 **Search-UnifiedAuditLog** cmdlet 的人員。</span><span class="sxs-lookup"><span data-stu-id="b9fba-229">Assign permissions in Exchange Online to people in your organization who will use the audit log search tool in the Microsoft 365 compliance center or use the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="b9fba-230">特別是必須在 Exchange Online 中為使用者指派 [僅供檢視稽核記錄] 或 [稽核記錄角色]。</span><span class="sxs-lookup"><span data-stu-id="b9fba-230">Specifically, users must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online.</span></span>

3. <span data-ttu-id="b9fba-p116">搜尋稽核記錄。完成步驟 1 和步驟 2 後，貴組織中的使用者可以使用稽核記錄搜尋工具 (或相應的 cmdlet) 搜尋已稽核活動。</span><span class="sxs-lookup"><span data-stu-id="b9fba-p116">Search the audit log. After completing step 1 and step 2, users in your organization can use the audit log search tool (or corresponding cmdlet) to search for audited activities.</span></span>

<span data-ttu-id="b9fba-233">如需詳細指示，請參閱[設定基本稽核](set-up-basic-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-233">For more detailed instructions, see [Set up Basic Audit](set-up-basic-audit.md).</span></span>

### <a name="set-up-advanced-audit"></a><span data-ttu-id="b9fba-234">設定進階稽核</span><span class="sxs-lookup"><span data-stu-id="b9fba-234">Set up Advanced Audit</span></span>

<span data-ttu-id="b9fba-235">如果貴組織具有支援進階稽核的訂閱，請執行以下步驟以設定和使用進階稽核中的其他功能。</span><span class="sxs-lookup"><span data-stu-id="b9fba-235">If your organization has a subscription that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![設定進階稽核的工作流程](../media/AdvancedAuditWorkflow.png)

1. <span data-ttu-id="b9fba-237">為使用者設置進階稽核。</span><span class="sxs-lookup"><span data-stu-id="b9fba-237">Set up Advanced Audit for users.</span></span> <span data-ttu-id="b9fba-238">此步驟包括以下工作：</span><span class="sxs-lookup"><span data-stu-id="b9fba-238">This step consists of the following tasks:</span></span>

   - <span data-ttu-id="b9fba-239">驗證是否為使用者指派了進階稽核的適當權限或附加元件權限。</span><span class="sxs-lookup"><span data-stu-id="b9fba-239">Verifying that users are assigned the appropriate license or add-on license for Advanced Audit.</span></span>
  
   - <span data-ttu-id="b9fba-240">必須為這些使用者啟用進階稽核應用程式/服務方案。</span><span class="sxs-lookup"><span data-stu-id="b9fba-240">Turning on the Advanced Audit app/service plan must be for those users.</span></span>
  
   - <span data-ttu-id="b9fba-241">啟用重要事件的稽核，然後為這些使用者啟用進階稽核應用程式/服務方案。</span><span class="sxs-lookup"><span data-stu-id="b9fba-241">Enabling the auditing of crucial events and then turning on the Advanced Auditing app/service plan for those users.</span></span>

2. <span data-ttu-id="b9fba-242">允許使用者在 Exchange Online 和 SharePoint Online 中執行搜尋時記錄重要事件。</span><span class="sxs-lookup"><span data-stu-id="b9fba-242">Enable crucial events to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span>

3. <span data-ttu-id="b9fba-p118">設定稽核記錄保留原則。除了保留 Exchange、SharePoint 和 Azure AD 稽核記錄一年的預設原則之外，您還可以建立其他稽核記錄保留原則，以符合貴組織的安全性作業、IT 和合規性小組的需求。</span><span class="sxs-lookup"><span data-stu-id="b9fba-p118">Set up audit log retention policies. In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span>

4. <span data-ttu-id="b9fba-p119">進行鑑識調查時搜尋重要事件和其他活動。在完成步驟 1 和步驟 2 後，您可以搜尋重要事件和對遭入侵帳戶的鑑識調查，以及其他類型安全性或合規性調查期間的其他活動稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="b9fba-p119">Search for crucial events and other activities when conducting forensic investigations. After completing step 1 and step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span>

<span data-ttu-id="b9fba-247">如需詳細指示，請參閱[設定進階稽核](set-up-advanced-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-247">For more detailed instructions, see [Set up Advanced Audit](set-up-advanced-audit.md).</span></span>

## <a name="training"></a><span data-ttu-id="b9fba-248">訓練</span><span class="sxs-lookup"><span data-stu-id="b9fba-248">Training</span></span>

<span data-ttu-id="b9fba-249">訓練安全性作業小組、IT 管理員和合規性調查人員小組基礎稽核和進階稽核内容，可協助貴組織更快開始使用稽核來進行調查。</span><span class="sxs-lookup"><span data-stu-id="b9fba-249">Training your security operations team, IT administrators, and compliance investigators team in Basic Audit and Advanced Audit can help your organization get started more quickly using auditing to help with your investigations.</span></span> <span data-ttu-id="b9fba-250">Microsoft 365 提供以下資源以協助組織中的這些使用者開始使用稽核：[描述 Microsoft 365 中的稽核功能](/learn/modules/describe-audit-capabilities-microsoft-365)。</span><span class="sxs-lookup"><span data-stu-id="b9fba-250">Microsoft 365 provides the following resource to help these users in your organization getting started with auditing: [Describe the audit capabilities in Microsoft 365](/learn/modules/describe-audit-capabilities-microsoft-365).</span></span>
