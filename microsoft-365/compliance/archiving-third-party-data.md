---
title: 封存第三方資料
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何將「社交媒體平臺」、「立即訊息平臺」及「檔共同作業平臺」的協力廠商資料匯入至 Microsoft 365 信箱。
ms.openlocfilehash: fab3147b5226b2d69a8dac6d214da7efdd26def6
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564988"
---
# <a name="archive-third-party-data"></a>封存第三方資料

Microsoft 365 可讓系統管理員使用資料連線器，將協力廠商資料從社交媒體平臺、立即訊息平臺及檔共同作業平臺，匯入到您的 Microsoft 365 組織中的信箱。 在 Microsoft 365 中，使用資料連線器匯入及封存協力廠商資料的主要好處是，您可以在匯入後，對其套用各種 Microsoft 365 相容性解決方案。 這可協助您確保組織的非 Microsoft 資料符合影響組織的規章和標準。

## <a name="third-party-data-connectors"></a>協力廠商資料連接器

下表列出 Microsoft 365 規範中心提供的協力廠商資料連線器。 該表也會摘要您可以在 Microsoft 365 中匯入及封存後，套用至協力廠商資料的相容性解決方案。 請參閱[下一節](#overview-of-compliance-solutions-that-support-third-party-data)，以取得每個規範解決方案的詳細說明，以及它如何受益協力廠商資料。

> [!TIP]
> 按一下**協力廠商資料**欄中的連結，以取得針對該資料類型建立連接器的逐步指示。

|協力廠商資料  |訴訟暫止|電子文件探索  |保留原則  |記錄管理  |通訊合規性  |測試人員風險管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[HR 資料](import-hr-data.md) ||||||![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[立即 Bloomberg](archive-instant-bloomberg-data.md)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[LinkedIn](archive-linkedin-data.md)   |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
||||||||

上表所列的協力廠商資料（HR 資料除外）會匯入至使用者信箱。 支援協力廠商資料的對應相容性解決方案會套用至儲存資料的使用者信箱。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>支援協力廠商資料的相容性解決方案

下列各節說明 Microsoft 365 合規性解決方案可協助您管理上表中所列之協力廠商資料的部分內容。

### <a name="litigation-hold"></a>訴訟暫止

您在使用者信箱上進行[訴訟暫](create-a-litigation-hold.md)止，以保留協力廠商資料。 當您建立保留時，您可以指定保留期間（也稱為以*時間為基礎的保留*），以在指定期間內保留已刪除及已修改的協力廠商資料，然後從信箱中永久刪除。 或者，您可以只保留無限期的內容（稱為*無限期*保留）或移除訴訟暫止。

### <a name="ediscovery"></a>電子文件探索

Microsoft 365 中的三個主要 eDiscovery 工具組括內容搜尋、核心 eDiscovery 和高級 eDiscovery。

- **[內容搜尋](content-search.md)。** 您可以使用內容搜尋工具，針對您匯入的協力廠商資料搜尋信箱。 您可以使用搜尋查詢和條件來縮小搜尋結果，以及匯出搜尋結果。

- **[核心 eDiscovery](get-started-core-ediscovery.md)。** 此工具是在基本搜尋和匯出功能上建立的，可讓您建立用來控制誰可以存取案例資料的案例、保留使用者信箱或符合搜尋準則的信箱內容。 這表示您可以在匯入至使用者信箱的協力廠商資料上放置 eDiscovery 暫止功能。

- **[Advanced eDiscovery](overview-ediscovery-20.md)。** 這項強大的工具可讓您將保管人新增至案例、將保管人的資料置於保留狀態，然後將系統管理員的協力廠商資料載入至評審，以進行進一步分析，例如主題和重複偵測，以擴充核心 eDiscovery 的案例功能。 將協力廠商資料載入到審閱集中之後，您可以查詢並篩選為窄的結果集。

   核心 eDiscovery 和高級 eDiscovery 可讓您管理可能與組織法律或內部調查相關的協力廠商資料。

### <a name="retention-policies"></a>保留原則

您可以將[保留原則](retention-policies.md)套用至使用者信箱，保留期限到期後再刪除協力廠商資料（及其他信箱內容）。 您也可以使用保留原則刪除某段時間內的協力廠商資料，或在保留期間到期時觸發處置檢查。

### <a name="records-management"></a>記錄管理

Microsoft 365 中的[記錄管理](records-management.md)功能可讓您將協力廠商資料宣告為記錄。 這可由套用保留標籤的使用者手動完成，以將信箱中的協力廠商資料標示為記錄。 或者，您可以在協力廠商資料中識別敏感資訊、關鍵字或內容類型，以自動套用保留標籤。

### <a name="communication-compliance"></a>通訊合規性

您可以使用[通訊相容性](communication-compliance.md)來檢查協力廠商資料，以確保其符合您組織的資料標準。 您可以為組織中的不適當郵件偵測、捕獲和採取修正動作，以執行此動作。 例如，您可以監視針對冒犯性語言、機密資訊和規章遵循所匯入的協力廠商資料。

### <a name="insider-risk-management"></a>測試人員風險管理

來自協力廠商資料（如選擇性 HR 資料）的信號可供「[有問必答風險管理](insider-risk-management.md)」解決方案使用，以在組織中偵測、調查與處理危險的活動，以盡可能降低內部風險。 例如，HR 資料連線器匯入的資料會用作風險標記，以協助偵測盜竊員工資料竊取。

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>使用 Microsoft 合作夥伴封存協力廠商資料

匯入及封存協力廠商資料的另一個選擇是讓您的組織與 Microsoft 合作夥伴搭配使用。 如果 Microsoft 規範中心中提供的資料連線器不支援協力廠商資料型別，您可以使用可提供自訂連接器的合作夥伴，以便定期從協力廠商資料來源提取專案，然後以協力廠商 API 連線至 Microsoft 雲端，並將這些專案匯入 Microsoft 365。 夥伴連接器也會將專案的內容從協力廠商資料來源轉換成電子郵件，然後將其匯入 Microsoft 365 中的信箱。

如需您可以使用的合作夥伴清單及此方法的逐步程式，請參閱在[Microsoft 365 中封存協力廠商資料](work-with-partner-to-archive-third-party-data.md)的合作。
