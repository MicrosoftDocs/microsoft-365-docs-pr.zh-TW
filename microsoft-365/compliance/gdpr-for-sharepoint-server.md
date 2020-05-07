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
# <a name="gdpr-for-sharepoint-server"></a>適用於 SharePoint Server 的 GDPR

適用於：
- SharePoint Server 2013
- SharePoint Server 2016
- SharePoint Server 2019

在保護個人資訊時，我們建議下列事項：

-   使用 Azure 資訊保護替資料分類

-   以最低權限的設定執行 SharePoint Server。如需詳細資訊，請參閱[規劃 SharePoint Server 中的最低權限管理](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration)與 [SharePoint Server 安全性](https://docs.microsoft.com/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server)。

-   在伺服器上啟用 [BitLocker 加密](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server)。

## <a name="user-generated-content"></a>使用者產生的內容

針對 SharePoint Server 網站和文件庫中使用者產生的內容，基本建議做法是：

-   使用 Azure 資訊保護來標記機密資料。

-   使用 [SharePoint Server 搜尋](https://docs.microsoft.com/SharePoint/search/search)與[電子文件探索](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server)來擷取機密資料。

針對檔案共用、SharePoint 網站及文件庫，建議做法包括下列步驟：

1.  **[安裝及設定 Azure 資訊保護掃描器。](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**

    -   決定要使用哪個機密資料類型。

    -   指定要使用的 SharePoint 網站。

2.  **完成探索循環。**

    -   在探索模式中執行掃描器，並且驗證結果。

    -   視需要最佳化條件和機密資訊類型。

    -   評估自動套用標籤的預期影響。

3.  **執行 Azure 資訊保護掃描器以將標籤套用至符合資格的文件**。

4.  **針對保護：**

    a. 設定 Exchange 資料外洩防護規則，保護具有所需標籤的文件。

    b. 請務必使用權限來限制可以存取檔案的人員。

    c. 針對 SharePoint，使用 IRM 保護文件庫。

5.  **針對監視，整合 Windows Server 記錄與 SIEM 工具。**

    a. 若要尋找資料主體要求的個人資料，使用 [搜尋中心] 或電子文件探索。

將標籤套用到機密資料時，請務必使用未設定保護的標籤。保護包括加密，用於防止服務偵測檔案中的機密資料。

如需使用 Azure 資訊保護掃描器來找出個人資料並加上標籤，詳細資訊請參閱 [Microsoft GDPR 資料探索工具組](https://aka.ms/gdprpartners) (https://aka.ms/gdprpartners)。

如需有關針對條件設定掃描器，以及使用 Office 365 資料外洩防護 (DLP) 機密資訊類型的詳細資訊，請參閱[如何針對 Azure 資訊保護的自動和建議分類設定條件](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification)。請注意，新的 Office 365 機密資訊類型無法立即與掃描器搭配使用，且自訂機密資訊類型無法與掃描器搭配使用。

## <a name="removing-personal-information-from-office-files"></a>移除 Office 檔案中的個人資訊

若要移除儲存在 SharePoint 文件庫中的 Office 檔案裡的個人資訊 (像是中繼資料、Word 文件中的註解)，必須手動移除。請遵循以下步驟：

1.  從 SharePoint Server 下載一份文件到本機磁碟。

2.  刪除 SharePoint 文件庫中的文件。

3.  執行[透過檢查文件來移除隱藏的資料和個人資訊](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F)中的步驟。

4.  將文件重新上傳至 SharePoint 文件庫。

## <a name="telemetry-and-log-files"></a>遙測和記錄檔

### <a name="uls-logs"></a>ULS 記錄

SharePoint Server 中的統一登入服務 (ULS) 和使用情況記錄會追蹤各種系統功能，並可以包含使用者資訊。ULS 記錄和使用情況記錄是文字檔，可使用各種搜尋工具搜尋它們。[Merge-SPLogFile PowerShell Cmdlet](https://docs.microsoft.com/powershell/module/sharepoint-server/merge-splogfile) 可用來將伺服器陣列中多個伺服器上的 ULS 記錄 (log) 中的記錄 (record) 傳回。

請考慮設定記錄保留原則，以適合企業所需的最小值。如需了解如何設定 SharePoint Server 中的記錄，請參閱[設定 SharePoint Server 中的診斷記錄](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging)。

請注意，有些系統事件也會記錄到 Windows 事件記錄。

### <a name="usage-database"></a>使用情況資料庫

SharePoint Server 使用情況資料庫 (預設名稱為 WSS_Logging) 包含在 ULS 記錄中找到的部分資訊。資料庫中資料的保留上限為 30 天。我們建議您將它設為業務需求允許的最短期間。如需詳細資訊，請參閱[設定 SharePoint Server 中的診斷記錄](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging)。

## <a name="personal-information-and-search"></a>個人資訊

搜尋查詢歷程記錄和使用情況記錄包含使用者名稱的參照。

### <a name="query-history-and-favorite-queries"></a>查詢歷程記錄和最愛的查詢

在 SharePoint Server 中，查詢歷程記錄和「最愛」的查詢會自動在 365 天後到期。如果有使用者離開組織，您可以使用下列步驟，從查詢歷程記錄中移除該使用者名稱的參照。

下列 SQL 查詢適用於 SharePoint Server，並讓您能夠：

-   匯出使用者的查詢歷程記錄或最愛的查詢

-   移除查詢歷程記錄中使用者名稱的參照

#### <a name="export-a-users-queries-since-a-specific-date"></a>匯出特定日期後的使用者查詢 

使用下列程序可以將 LinkStore 查詢記錄資料表中自 @StartTime 起由 @UserName 執行的查詢匯出。

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

#### <a name="export-a-users-queries-from-the-past-100-days"></a>匯出使用者在過去 100 天的查詢

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a>匯出使用者最愛的查詢

使用下列程序可以將 Search Admin DB 個人結果資料表中自 <DateTime> 起由 @UserName 執行的使用者最愛的查詢匯出。

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

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a>匯出使用者在過去 100 天的最愛查詢 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a>移除超過 X 天的使用者名稱參照

使用下列程序從連結存放區查詢記錄資料表中，移除超過 @Days 天之對「所有」** 使用者名稱的參照。此程序只會逆時移除參照，直到 @LastCleanupTime 為止。

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

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a>移除超過 X 天的特定使用者名稱參照

使用下列程序從連結存放區查詢記錄資料表中，移除超過 @Days 天之對「特定」** 使用者名稱的參照。此程序只會逆時移除參照，直到 @LastCleanupTime 為止。

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

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a>移除查詢歷程記錄中自某一天起最多 30 天的所有使用者名稱的參照

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a>刪除使用情況記錄

SharePoint Server 會在 3 年後自動刪除使用情況記錄。您可以使用下列程序手動刪除這類記錄：

刪除與已刪除文件相關聯的所有使用情況記錄： 

1.  確定您已安裝最新的 SharePoint 更新。 

2.  啟動 SharePoint 管理命令介面。

3.  停止並清除 UsageAnalytics 分析： 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  等待分析重新啟動 (最多可能需要 24 小時)。 

5.  下一次執行分析時，它會傾印分析報告資料庫中的所有記錄。若是包含許多項目的大型資料庫，這個完整傾印可能需要很長一段時間。

6.  請等待 10 天。分析會每天執行，而與已刪除文件相關聯的記錄將會在 第 10 次執行後移除。如果有許多記錄要刪除，這項執行可能會花費比正常更久的時間。 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a>SharePoint Server 2010 中的個人資訊和搜尋

#### <a name="fast-search-server-2010-for-sharepoint"></a>FAST Search Server 2010 for SharePoint 

除了將檔案儲存在索引中，FAST Search Server 2010 附加元件也將檔案儲存為中繼格式，稱為 FixML。系統預設會在上午 3 點到 5 點之間定期壓縮 FiXML 檔案。壓縮會自動移除 FiXML 檔案中已刪除的檔案。為了確保能及時移除屬於已刪除使用者或文件的資訊，請確定該壓縮永遠啟用。

### <a name="hybrid-search"></a>混合式搜尋 

針對混合式搜尋解決方案的建議動作也和 SharePoint Server 或 SharePoint Online 中的搜尋一樣。混合式搜尋解決方案有兩個：

**雲端混合式搜尋解決方案 - ** 使用 SharePoint 的雲端混合式搜尋解決方案， 您要在 Office 365 的搜尋索引中替所有編目的內容編製索引，包括內部部署內容。當使用者查詢 Office 365 中的搜尋索引，他們就能從內部部署和 Office 365 內容取得搜尋結果。在 SharePoint Server 環境中刪除文件時，也會從 Office 365 的搜尋索引中刪除它們。請參閱[深入了解雲端混合式搜尋解決方案](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint)與[雲端混合式搜尋中搜尋元件和資料庫的互動方式](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint)，了解 GDPR 如何影響混合式環境。

**混合式同盟搜尋解決方案 -** 透過混合式同盟搜尋解決方案，您會使用 SharePoint Server 中的索引和 Office 365 中的索引。SharePoint Server 和 SharePoint Online Search 服務都可以查詢其他環境中的搜尋索引，並傳回同盟的結果。當使用者搜尋搜尋中心時，搜尋結果會來自您在 SharePoint Server 中的搜尋索引和 Office 365 中的搜尋索引。請參閱[深入了解混合式同盟搜尋解決方案](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint)，了解 GDPR 如何影響混合式環境。

## <a name="on-prem-to-cloud-migrations"></a>內部部署到雲端的移轉

將資料從 SharePoint Server 移轉到 SharePoint Online 時，複製資料可能同時存在兩個位置中一段時間。如果您需要在移轉期間刪除資料，建議先完成移轉，然後同時刪除兩個位置的資料。您可以查詢資料，並從其中一個位置匯出資料。

## <a name="user-profile-data"></a>使用者設定檔資料

使用者設定檔服務可用來匯入各種外部來源的設定檔資料。這類使用者設定檔資料的查詢和更新應該在管控資料的系統中處理。如果您對外部系統進行更新，請務必再次同步處理 SharePoint Server 中的使用者設定檔。

遵循下列基本步驟，從 SharePoint Server 使用者設定檔中移除使用者的個人資訊：

1.  移除所有餵送到 SharePoint Server 使用者設定檔的外部系統中的使用者資訊。如果您使用目錄同步處理，則必須在內部部署 Active Directory 環境中移除使用者。

2.  在 SharePoint Server 上執行[設定檔同步處理](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually)。

3.  刪除 SharePoint Server 中的設定檔。完成此操作時，SharePoint Server 將會在 30 天內完全移除使用者設定檔資料庫中的設定檔。也會刪除使用者的設定檔頁面和個人網站。

刪除使用者設定檔之後，在使用者曾造訪的網站集合中，可能仍會記錄部分有限資訊 (例如使用者 ID)。如果您要將特定網站集合中的此資料刪除，可以使用 CSOM。範例指令碼如下：

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
