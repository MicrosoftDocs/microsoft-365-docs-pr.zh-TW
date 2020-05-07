---
title: 適用於 SharePoint Server 的 GDPR
description: 了解如何解決內部部署 SharePoint Server 中的一般資料保護規定 (GDPR) 需求。
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddbe98ec5ca6b08e6d6be58c4258265c13e3de
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036226"
---
# <a name="gdpr-for-sharepoint-server"></a><span data-ttu-id="88743-103">適用於 SharePoint Server 的 GDPR</span><span class="sxs-lookup"><span data-stu-id="88743-103">GDPR for SharePoint Server</span></span>

<span data-ttu-id="88743-104">適用於：</span><span class="sxs-lookup"><span data-stu-id="88743-104">Applies to:</span></span>
- <span data-ttu-id="88743-105">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="88743-105">SharePoint Server 2013</span></span>
- <span data-ttu-id="88743-106">SharePoint Server 2016</span><span class="sxs-lookup"><span data-stu-id="88743-106">SharePoint Server 2016</span></span>
- <span data-ttu-id="88743-107">SharePoint Server 2019</span><span class="sxs-lookup"><span data-stu-id="88743-107">SharePoint Server 2019</span></span>

<span data-ttu-id="88743-108">在保護個人資訊時，我們建議下列事項：</span><span class="sxs-lookup"><span data-stu-id="88743-108">As part of safeguarding personal information, we recommend the following:</span></span>

-   <span data-ttu-id="88743-109">使用 Azure 資訊保護替資料分類</span><span class="sxs-lookup"><span data-stu-id="88743-109">Classify your data, using Azure Information Protection.</span></span>

-   <span data-ttu-id="88743-p101">以最低權限的設定執行 SharePoint Server。如需詳細資訊，請參閱[規劃 SharePoint Server 中的最低權限管理](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration)與 [SharePoint Server 安全性](https://docs.microsoft.com/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server)。</span><span class="sxs-lookup"><span data-stu-id="88743-p101">Run SharePoint Server in a least-privileged configuration. See [Plan for least-privileged administration in SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) and [Security for SharePoint Server](https://docs.microsoft.com/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server) for more information.</span></span>

-   <span data-ttu-id="88743-112">在伺服器上啟用 [BitLocker 加密](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server)。</span><span class="sxs-lookup"><span data-stu-id="88743-112">[Enable BitLocker encryption on your servers](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).</span></span>

## <a name="user-generated-content"></a><span data-ttu-id="88743-113">使用者產生的內容</span><span class="sxs-lookup"><span data-stu-id="88743-113">User Generated content</span></span>

<span data-ttu-id="88743-114">針對 SharePoint Server 網站和文件庫中使用者產生的內容，基本建議做法是：</span><span class="sxs-lookup"><span data-stu-id="88743-114">The basic recommended approach for user generated content contained in SharePoint Server sites and libraries is:</span></span>

-   <span data-ttu-id="88743-115">使用 Azure 資訊保護來標記機密資料。</span><span class="sxs-lookup"><span data-stu-id="88743-115">Use Azure Information Protection to label sensitive data.</span></span>

-   <span data-ttu-id="88743-116">使用 [SharePoint Server 搜尋](https://docs.microsoft.com/SharePoint/search/search)與[電子文件探索](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server)來擷取機密資料。</span><span class="sxs-lookup"><span data-stu-id="88743-116">Use [SharePoint Server search](https://docs.microsoft.com/SharePoint/search/search) and [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) to retrieve sensitive data.</span></span>

<span data-ttu-id="88743-117">針對檔案共用、SharePoint 網站及文件庫，建議做法包括下列步驟：</span><span class="sxs-lookup"><span data-stu-id="88743-117">The recommended approach for files shares and SharePoint sites and libraries includes these steps:</span></span>

1.  <span data-ttu-id="88743-118">**[安裝及設定 Azure 資訊保護掃描器。](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span><span class="sxs-lookup"><span data-stu-id="88743-118">**[Install and configure Azure Information Protection scanner.](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span></span>

    -   <span data-ttu-id="88743-119">決定要使用哪個機密資料類型。</span><span class="sxs-lookup"><span data-stu-id="88743-119">Decide which sensitive data types to use.</span></span>

    -   <span data-ttu-id="88743-120">指定要使用的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="88743-120">Specify which SharePoint sites to use.</span></span>

2.  <span data-ttu-id="88743-121">**完成探索循環。**</span><span class="sxs-lookup"><span data-stu-id="88743-121">**Complete a discovery cycle.**</span></span>

    -   <span data-ttu-id="88743-122">在探索模式中執行掃描器，並且驗證結果。</span><span class="sxs-lookup"><span data-stu-id="88743-122">Run the scanner in discovery mode and validate the findings.</span></span>

    -   <span data-ttu-id="88743-123">視需要最佳化條件和機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="88743-123">If needed, optimize the conditions and sensitive information types.</span></span>

    -   <span data-ttu-id="88743-124">評估自動套用標籤的預期影響。</span><span class="sxs-lookup"><span data-stu-id="88743-124">Assess the expected impact of automatically applying labels.</span></span>

3.  <span data-ttu-id="88743-125">**執行 Azure 資訊保護掃描器以將標籤套用至符合資格的文件**。</span><span class="sxs-lookup"><span data-stu-id="88743-125">**Run the Azure Information Protection scanner to apply labels to qualifying documents**.</span></span>

4.  <span data-ttu-id="88743-126">**針對保護：**</span><span class="sxs-lookup"><span data-stu-id="88743-126">**For protection:**</span></span>

    <span data-ttu-id="88743-p102">a. 設定 Exchange 資料外洩防護規則，保護具有所需標籤的文件。</span><span class="sxs-lookup"><span data-stu-id="88743-p102">a.  Configure Exchange data loss prevention rules to protect documents with the desired label.</span></span>

    <span data-ttu-id="88743-p103">b. 請務必使用權限來限制可以存取檔案的人員。</span><span class="sxs-lookup"><span data-stu-id="88743-p103">b.  Be sure permissions to limit who can access files.</span></span>

    <span data-ttu-id="88743-p104">c. 針對 SharePoint，使用 IRM 保護文件庫。</span><span class="sxs-lookup"><span data-stu-id="88743-p104">c.  For SharePoint, use IRM-protection for libraries.</span></span>

5.  <span data-ttu-id="88743-133">**針對監視，整合 Windows Server 記錄與 SIEM 工具。**</span><span class="sxs-lookup"><span data-stu-id="88743-133">**For monitoring, integrate Windows Server logs with a SIEM tool.**</span></span>

    <span data-ttu-id="88743-p105">a. 若要尋找資料主體要求的個人資料，使用 [搜尋中心] 或電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="88743-p105">a.  To find personal data for data subject requests, use Search Center or eDiscovery.</span></span>

<span data-ttu-id="88743-p106">將標籤套用到機密資料時，請務必使用未設定保護的標籤。保護包括加密，用於防止服務偵測檔案中的機密資料。</span><span class="sxs-lookup"><span data-stu-id="88743-p106">When applying labels to sensitive data, be sure to use a label that is not configured with protection. Protection includes encryption which prevents services from detecting sensitive data in the files.</span></span>

<span data-ttu-id="88743-138">如需使用 Azure 資訊保護掃描器來找出個人資料並加上標籤，詳細資訊請參閱 [Microsoft GDPR 資料探索工具組](https://aka.ms/gdprpartners) (https://aka.ms/gdprpartners)。</span><span class="sxs-lookup"><span data-stu-id="88743-138">For more information on using Azure Information Protection scanner to find and label personal data, see the [Microsoft GDPR Data Discovery Toolkit](https://aka.ms/gdprpartners) (https://aka.ms/gdprpartners).</span></span>

<span data-ttu-id="88743-p107">如需有關針對條件設定掃描器，以及使用 Office 365 資料外洩防護 (DLP) 機密資訊類型的詳細資訊，請參閱[如何針對 Azure 資訊保護的自動和建議分類設定條件](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification)。請注意，新的 Office 365 機密資訊類型無法立即與掃描器搭配使用，且自訂機密資訊類型無法與掃描器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="88743-p107">For information on configuring the scanner for conditions and using the Office 365 data loss prevention (DLP) sensitive information types, see [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Note that new Office 365 sensitive information types will not be immediately available to use with the scanner and custom sensitive information types cannot be used with the scanner.</span></span>

## <a name="removing-personal-information-from-office-files"></a><span data-ttu-id="88743-141">移除 Office 檔案中的個人資訊</span><span class="sxs-lookup"><span data-stu-id="88743-141">Removing personal information from Office files</span></span>

<span data-ttu-id="88743-p108">若要移除儲存在 SharePoint 文件庫中的 Office 檔案裡的個人資訊 (像是中繼資料、Word 文件中的註解)，必須手動移除。請遵循以下步驟：</span><span class="sxs-lookup"><span data-stu-id="88743-p108">Removing personal information (such as metadata or comments in a Word document) from Office files that are stored in a SharePoint document library must be done manually. Follow these steps:</span></span>

1.  <span data-ttu-id="88743-144">從 SharePoint Server 下載一份文件到本機磁碟。</span><span class="sxs-lookup"><span data-stu-id="88743-144">Download a copy of the document from SharePoint Server to your local disk.</span></span>

2.  <span data-ttu-id="88743-145">刪除 SharePoint 文件庫中的文件。</span><span class="sxs-lookup"><span data-stu-id="88743-145">Delete the document from the SharePoint document library.</span></span>

3.  <span data-ttu-id="88743-146">執行[透過檢查文件來移除隱藏的資料和個人資訊](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="88743-146">Follow the steps in [Remove hidden data and personal information by inspecting documents](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).</span></span>

4.  <span data-ttu-id="88743-147">將文件重新上傳至 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="88743-147">Upload the document back to the SharePoint document library.</span></span>

## <a name="telemetry-and-log-files"></a><span data-ttu-id="88743-148">遙測和記錄檔</span><span class="sxs-lookup"><span data-stu-id="88743-148">Telemetry and log files</span></span>

### <a name="uls-logs"></a><span data-ttu-id="88743-149">ULS 記錄</span><span class="sxs-lookup"><span data-stu-id="88743-149">ULS Logs</span></span>

<span data-ttu-id="88743-p109">SharePoint Server 中的統一登入服務 (ULS) 和使用情況記錄會追蹤各種系統功能，並可以包含使用者資訊。ULS 記錄和使用情況記錄是文字檔，可使用各種搜尋工具搜尋它們。[Merge-SPLogFile PowerShell Cmdlet](https://docs.microsoft.com/powershell/module/sharepoint-server/merge-splogfile) 可用來將伺服器陣列中多個伺服器上的 ULS 記錄 (log) 中的記錄 (record) 傳回。</span><span class="sxs-lookup"><span data-stu-id="88743-p109">Unified Logging Service (ULS) and Usage logging in SharePoint Server track a variety of system functions and can contain user information. ULS logs and usage logs are text files and can be searched using a variety of searching tools. The [Merge-SPLogFile PowerShell cmdlet](https://docs.microsoft.com/powershell/module/sharepoint-server/merge-splogfile) provides a way to return records from the ULS logs on multiple servers in a farm.</span></span>

<span data-ttu-id="88743-p110">請考慮設定記錄保留原則，以適合企業所需的最小值。如需了解如何設定 SharePoint Server 中的記錄，請參閱[設定 SharePoint Server 中的診斷記錄](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging)。</span><span class="sxs-lookup"><span data-stu-id="88743-p110">Consider setting log retention policies to the minimum value needed for your business purposes. For information about configuring logging in SharePoint Server, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

<span data-ttu-id="88743-155">請注意，有些系統事件也會記錄到 Windows 事件記錄。</span><span class="sxs-lookup"><span data-stu-id="88743-155">Note that some system events are also logged to the Windows Event Log.</span></span>

### <a name="usage-database"></a><span data-ttu-id="88743-156">使用情況資料庫</span><span class="sxs-lookup"><span data-stu-id="88743-156">Usage Database</span></span>

<span data-ttu-id="88743-p111">SharePoint Server 使用情況資料庫 (預設名稱為 WSS_Logging) 包含在 ULS 記錄中找到的部分資訊。資料庫中資料的保留上限為 30 天。我們建議您將它設為業務需求允許的最短期間。如需詳細資訊，請參閱[設定 SharePoint Server 中的診斷記錄](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging)。</span><span class="sxs-lookup"><span data-stu-id="88743-p111">The SharePoint Server Usage database (default name WSS_Logging) contains a subset of the information found in the ULS logs. The maximum retention of data in this database is 30 days. We recommend that you configure it for the shortest duration allowable by your business needs. For more information, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

## <a name="personal-information-and-search"></a><span data-ttu-id="88743-161">個人資訊</span><span class="sxs-lookup"><span data-stu-id="88743-161">Personal information and search</span></span>

<span data-ttu-id="88743-162">搜尋查詢歷程記錄和使用情況記錄包含使用者名稱的參照。</span><span class="sxs-lookup"><span data-stu-id="88743-162">The search query history and usage records contain references to user names.</span></span>

### <a name="query-history-and-favorite-queries"></a><span data-ttu-id="88743-163">查詢歷程記錄和最愛的查詢</span><span class="sxs-lookup"><span data-stu-id="88743-163">Query history and favorite queries</span></span>

<span data-ttu-id="88743-p112">在 SharePoint Server 中，查詢歷程記錄和「最愛」的查詢會自動在 365 天後到期。如果有使用者離開組織，您可以使用下列步驟，從查詢歷程記錄中移除該使用者名稱的參照。</span><span class="sxs-lookup"><span data-stu-id="88743-p112">In SharePoint Server, query histories and 'favorite' queries automatically expire after 365 days. If a user leaves your organization, it is possible to remove references to a user's name from the query history using the steps below.</span></span>

<span data-ttu-id="88743-166">下列 SQL 查詢適用於 SharePoint Server，並讓您能夠：</span><span class="sxs-lookup"><span data-stu-id="88743-166">The following SQL queries apply to SharePoint Server and make it possible to:</span></span>

-   <span data-ttu-id="88743-167">匯出使用者的查詢歷程記錄或最愛的查詢</span><span class="sxs-lookup"><span data-stu-id="88743-167">Export a user's query history or favorite queries</span></span>

-   <span data-ttu-id="88743-168">移除查詢歷程記錄中使用者名稱的參照</span><span class="sxs-lookup"><span data-stu-id="88743-168">Remove references to user names in the query history</span></span>

#### <a name="export-a-users-queries-since-a-specific-date"></a><span data-ttu-id="88743-169">匯出特定日期後的使用者查詢</span><span class="sxs-lookup"><span data-stu-id="88743-169">Export a user's queries since a specific date</span></span> 

<span data-ttu-id="88743-170">使用下列程序可以將 LinkStore 查詢記錄資料表中自 @StartTime 起由 @UserName 執行的查詢匯出。</span><span class="sxs-lookup"><span data-stu-id="88743-170">Use the following procedure to export queries from the Link Store query log tables, performed by @UserName since @StartTime.</span></span>

```sql
[In dbo].[LinkStore_<ID>]:
CREATE PROCEDURE proc_MSS_GetQueryTermsForUser 
( 
    @UserName nvarchar(256), 
    @StartTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT searchTime, queryString 
    FROM 
        dbo.MSSQLogPageImpressionQuery 
    WITH 
        (NOLOCK) 
    WHERE 
        userName = @UserName AND 
        searchTime > @StartTime 
END 
GO 
```

#### <a name="export-a-users-queries-from-the-past-100-days"></a><span data-ttu-id="88743-171">匯出使用者在過去 100 天的查詢</span><span class="sxs-lookup"><span data-stu-id="88743-171">Export a user's queries from the past 100 days</span></span>

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a><span data-ttu-id="88743-172">匯出使用者最愛的查詢</span><span class="sxs-lookup"><span data-stu-id="88743-172">Export a user's favorite queries</span></span>

<span data-ttu-id="88743-173">使用下列程序可以將 Search Admin DB 個人結果資料表中自 <DateTime> 起由 @UserName 執行的使用者最愛的查詢匯出。</span><span class="sxs-lookup"><span data-stu-id="88743-173">Use the following procedure to export a user's favorite queries from the Search Admin DB personal result tables, performed by @UserName, since <DateTime>.</span></span>

```sql
In [dbo].[Search_<ID>]:
CREATE PROCEDURE proc_MSS_GetPersonalFavoriteQueries 
( 
    @UserName nvarchar(256), 
    @SearchTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT max(queries.SearchTime) as SearchTime, 
           max(queries.querystring) as queryString, 
           max(url.url) as URL 
    FROM MSSQLogOwner owners WITH(NOLOCK) 
    JOIN MSSQLogPersonalResults results WITH(NOLOCK) on owners.OwnerId = results.OwnerId 
    JOIN MSSQLogUrl url WITH(NOLOCK) on results.ClickedUrlId = url.urlId 
    JOIN MSSQLogPersonalQueries queries WITH(NOLOCK) on results.OwnerId = queries.OwnerId 
    WHERE queries.SearchTime > @SearchTime 
        AND queries.UserName = @UserName 
        GROUP BY queries.QueryString,url.url 
END 
GO 
```

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a><span data-ttu-id="88743-174">匯出使用者在過去 100 天的最愛查詢</span><span class="sxs-lookup"><span data-stu-id="88743-174">Export a user's favorite queries from the past 100 days</span></span> 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a><span data-ttu-id="88743-175">移除超過 X 天的使用者名稱參照</span><span class="sxs-lookup"><span data-stu-id="88743-175">Remove references to user names that are more than X days old</span></span>

<span data-ttu-id="88743-p113">使用下列程序從連結存放區查詢記錄資料表中，移除超過 @Days 天之對「所有」\*\* 使用者名稱的參照。此程序只會逆時移除參照，直到 @LastCleanupTime 為止。</span><span class="sxs-lookup"><span data-stu-id="88743-p113">Use the following procedure to remove references to *all* user names that are more than @Days old, from the Links Store query log tables. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

```sql
In [dbo].[LinksStore_<ID>]:  
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a><span data-ttu-id="88743-178">移除超過 X 天的特定使用者名稱參照</span><span class="sxs-lookup"><span data-stu-id="88743-178">Remove references to a specific user name that's more than X days old</span></span>

<span data-ttu-id="88743-p114">使用下列程序從連結存放區查詢記錄資料表中，移除超過 @Days 天之對「特定」\*\* 使用者名稱的參照。此程序只會逆時移除參照，直到 @LastCleanupTime 為止。</span><span class="sxs-lookup"><span data-stu-id="88743-p114">Use the following procedure to remove references to a *specific* user name from the Links Store query log tables, where the references are more than @Days old. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

```sql
In [dbo].[LinksStore_<ID>]:
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @UserName nvarchar(256),
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a><span data-ttu-id="88743-181">移除查詢歷程記錄中自某一天起最多 30 天的所有使用者名稱的參照</span><span class="sxs-lookup"><span data-stu-id="88743-181">Remove references to all user names in the query history from a date and up to the past 30 days</span></span>

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a><span data-ttu-id="88743-182">刪除使用情況記錄</span><span class="sxs-lookup"><span data-stu-id="88743-182">Delete usage records</span></span>

<span data-ttu-id="88743-p115">SharePoint Server 會在 3 年後自動刪除使用情況記錄。您可以使用下列程序手動刪除這類記錄：</span><span class="sxs-lookup"><span data-stu-id="88743-p115">SharePoint Server automatically deletes usage records after 3 years. You can manually delete such records using the procedure below:</span></span>

<span data-ttu-id="88743-185">刪除與已刪除文件相關聯的所有使用情況記錄：</span><span class="sxs-lookup"><span data-stu-id="88743-185">To delete all usage records associated with deleted documents:</span></span> 

1.  <span data-ttu-id="88743-186">確定您已安裝最新的 SharePoint 更新。</span><span class="sxs-lookup"><span data-stu-id="88743-186">Ensure that you have the latest SharePoint update installed.</span></span> 

2.  <span data-ttu-id="88743-187">啟動 SharePoint 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="88743-187">Start a SharePoint Management shell.</span></span>

3.  <span data-ttu-id="88743-188">停止並清除 UsageAnalytics 分析：</span><span class="sxs-lookup"><span data-stu-id="88743-188">Stop and Clear the Usage Analytics analysis:</span></span> 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  <span data-ttu-id="88743-189">等待分析重新啟動 (最多可能需要 24 小時)。</span><span class="sxs-lookup"><span data-stu-id="88743-189">Wait for the analysis to start again (might take up to 24 hours).</span></span> 

5.  <span data-ttu-id="88743-p116">下一次執行分析時，它會傾印分析報告資料庫中的所有記錄。若是包含許多項目的大型資料庫，這個完整傾印可能需要很長一段時間。</span><span class="sxs-lookup"><span data-stu-id="88743-p116">On the next run of the analysis, it will dump all records from the Analytics Reporting database. This full dump may take a while for a large database with many entries.</span></span>

6.  <span data-ttu-id="88743-p117">請等待 10 天。分析會每天執行，而與已刪除文件相關聯的記錄將會在 第 10 次執行後移除。如果有許多記錄要刪除，這項執行可能會花費比正常更久的時間。</span><span class="sxs-lookup"><span data-stu-id="88743-p117">Wait for 10 days. The analysis runs daily, and records associated with deleted documents will be removed after the 10^th^ run. This run may take longer than normal if many records need to be deleted.</span></span> 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a><span data-ttu-id="88743-195">SharePoint Server 2010 中的個人資訊和搜尋</span><span class="sxs-lookup"><span data-stu-id="88743-195">Personal information and search in SharePoint Server 2010</span></span>

#### <a name="fast-search-server-2010-for-sharepoint"></a><span data-ttu-id="88743-196">FAST Search Server 2010 for SharePoint</span><span class="sxs-lookup"><span data-stu-id="88743-196">FAST Search Server 2010 for SharePoint</span></span> 

<span data-ttu-id="88743-p118">除了將檔案儲存在索引中，FAST Search Server 2010 附加元件也將檔案儲存為中繼格式，稱為 FixML。系統預設會在上午 3 點到 5 點之間定期壓縮 FiXML 檔案。壓縮會自動移除 FiXML 檔案中已刪除的檔案。為了確保能及時移除屬於已刪除使用者或文件的資訊，請確定該壓縮永遠啟用。</span><span class="sxs-lookup"><span data-stu-id="88743-p118">In addition to storing files in the index, the FAST Search Server 2010 Add-On also stores files in an intermediate format called FixML. FiXML files are compacted regularly, by default between 3 am and 5 am every night. Compaction removes deleted files from the FiXML files automatically. To ensure timely removal of information belonging to deleted users or documents, ensure that compaction is always enabled.</span></span>

### <a name="hybrid-search"></a><span data-ttu-id="88743-201">混合式搜尋</span><span class="sxs-lookup"><span data-stu-id="88743-201">Hybrid Search</span></span> 

<span data-ttu-id="88743-p119">針對混合式搜尋解決方案的建議動作也和 SharePoint Server 或 SharePoint Online 中的搜尋一樣。混合式搜尋解決方案有兩個：</span><span class="sxs-lookup"><span data-stu-id="88743-p119">The recommended actions for hybrid search solutions are the same as for search in SharePoint Server or SharePoint Online. There are two hybrid search solutions:</span></span>

<span data-ttu-id="88743-p120">\*\*雲端混合式搜尋解決方案 - \*\* 使用 SharePoint 的雲端混合式搜尋解決方案， 您要在 Office 365 的搜尋索引中替所有編目的內容編製索引，包括內部部署內容。當使用者查詢 Office 365 中的搜尋索引，他們就能從內部部署和 Office 365 內容取得搜尋結果。在 SharePoint Server 環境中刪除文件時，也會從 Office 365 的搜尋索引中刪除它們。請參閱[深入了解雲端混合式搜尋解決方案](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint)與[雲端混合式搜尋中搜尋元件和資料庫的互動方式](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint)，了解 GDPR 如何影響混合式環境。</span><span class="sxs-lookup"><span data-stu-id="88743-p120">**The cloud hybrid search solution -** With the cloud hybrid search solution for SharePoint, you index all your crawled content, including on-premises content, in your search index in Office 365. When users query your search index in Office 365, they get search results from both on-premises and Office 365 content. When documents are deleted from the SharePoint Server environment, they are also deleted from the search index in Office 365. [Read more about the cloud hybrid search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) and [how search components and databases interact in cloud hybrid search](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

<span data-ttu-id="88743-p121">**混合式同盟搜尋解決方案 -** 透過混合式同盟搜尋解決方案，您會使用 SharePoint Server 中的索引和 Office 365 中的索引。SharePoint Server 和 SharePoint Online Search 服務都可以查詢其他環境中的搜尋索引，並傳回同盟的結果。當使用者搜尋搜尋中心時，搜尋結果會來自您在 SharePoint Server 中的搜尋索引和 Office 365 中的搜尋索引。請參閱[深入了解混合式同盟搜尋解決方案](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint)，了解 GDPR 如何影響混合式環境。</span><span class="sxs-lookup"><span data-stu-id="88743-p121">**The hybrid federated search solution -** With the hybrid federated search solution, you use both your index in SharePoint Server and your index in Office 365. Both SharePoint Server and SharePoint Online Search services can query the search index in the other environment and return federated results. When users search from a Search Center, the search results come from both your search index in SharePoint Server and your search index in Office 365. [Read more about the hybrid federated search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

## <a name="on-prem-to-cloud-migrations"></a><span data-ttu-id="88743-212">內部部署到雲端的移轉</span><span class="sxs-lookup"><span data-stu-id="88743-212">On Prem to Cloud Migrations</span></span>

<span data-ttu-id="88743-p122">將資料從 SharePoint Server 移轉到 SharePoint Online 時，複製資料可能同時存在兩個位置中一段時間。如果您需要在移轉期間刪除資料，建議先完成移轉，然後同時刪除兩個位置的資料。您可以查詢資料，並從其中一個位置匯出資料。</span><span class="sxs-lookup"><span data-stu-id="88743-p122">While migrating data from SharePoint Server to SharePoint Online, duplicate data may exist in both locations for a time. If you have data that you need to delete that is in mid-migration, we recommend that you complete the migration first, and then delete the data from both locations. You can query data for export from either location.</span></span>

## <a name="user-profile-data"></a><span data-ttu-id="88743-216">使用者設定檔資料</span><span class="sxs-lookup"><span data-stu-id="88743-216">User Profile data</span></span>

<span data-ttu-id="88743-p123">使用者設定檔服務可用來匯入各種外部來源的設定檔資料。這類使用者設定檔資料的查詢和更新應該在管控資料的系統中處理。如果您對外部系統進行更新，請務必再次同步處理 SharePoint Server 中的使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="88743-p123">The User Profile Service allows for import of profile data from a variety of external sources. Queries for and update of such user profile data should be handled in the systems in which the data is mastered. If you make updates to the external system, be sure to synchronize the user profiles in SharePoint Server again.</span></span>

<span data-ttu-id="88743-220">遵循下列基本步驟，從 SharePoint Server 使用者設定檔中移除使用者的個人資訊：</span><span class="sxs-lookup"><span data-stu-id="88743-220">Follow these basic steps to remove a user's personal information from their SharePoint Server user profile:</span></span>

1.  <span data-ttu-id="88743-p124">移除所有餵送到 SharePoint Server 使用者設定檔的外部系統中的使用者資訊。如果您使用目錄同步處理，則必須在內部部署 Active Directory 環境中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="88743-p124">Remove the user information from any external systems that feed into the SharePoint Server user profile. If you are using directory synchronization, the user must be removed from the on-premises Active Directory environment.</span></span>

2.  <span data-ttu-id="88743-223">在 SharePoint Server 上執行[設定檔同步處理](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually)。</span><span class="sxs-lookup"><span data-stu-id="88743-223">Run a [profile synchronization](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) on SharePoint Server.</span></span>

3.  <span data-ttu-id="88743-p125">刪除 SharePoint Server 中的設定檔。完成此操作時，SharePoint Server 將會在 30 天內完全移除使用者設定檔資料庫中的設定檔。也會刪除使用者的設定檔頁面和個人網站。</span><span class="sxs-lookup"><span data-stu-id="88743-p125">Delete the profile from SharePoint Server. Once this is done, SharePoint Server will fully remove the profile from the User Profile Database in 30 days. The user's profile page and personal site will be deleted.</span></span>

<span data-ttu-id="88743-p126">刪除使用者設定檔之後，在使用者曾造訪的網站集合中，可能仍會記錄部分有限資訊 (例如使用者 ID)。如果您要將特定網站集合中的此資料刪除，可以使用 CSOM。範例指令碼如下：</span><span class="sxs-lookup"><span data-stu-id="88743-p126">After deleting a user's profile, some limited information (such as user ID) may still be recorded in site collections that the user has visited. If you choose to delete this data from a given site collection, this can be done using CSOM. A sample script is provided below:</span></span>

```powershell
$username = "<admin@company.sharepoint.com>"
$password = "password"
$url = "<https://site.sharepoint.com>"
$securePassword = ConvertTo-SecureString $Password -AsPlainText -Force

# the path here may need to change if you used e.g. C:Lib.
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.dll"
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.Runtime.dll"

# connect/authenticate to SharePoint Online and get ClientContext object.
$clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($username, $securePassword)
$clientContext.Credentials = $credentials
if (!$clientContext.ServerObjectIsNull.Value)
{
    Write-Host "Connected to SharePoint Online site: '$Url'" -ForegroundColor Green
}

# Get user
$user = $clientContext.Web.SiteUsers.GetByLoginName("i:0#.f|membership|user@company.sharepoint.com")

# Redact user
$user.Email = "Redacted"
$user.Title = "Redacted"
$user.Update()
$clientContext.Load($user)
$clientContext.ExecuteQuery()

# Get users
$users = $clientContext.Web.SiteUsers

# Remove user from site
$users.RemoveById($user.Id)
$clientContext.Load($users)
$clientContext.ExecuteQuery()
```
