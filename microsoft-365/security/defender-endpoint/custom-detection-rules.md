---
title: 在 Microsoft Defender ATP 中建立自訂偵測規則
ms.reviewer: ''
description: 瞭解如何根據高級搜尋查詢建立自訂偵測規則
keywords: 自訂偵測、建立、管理、警示、編輯、執行隨選即用、頻率、間隔、偵測規則、高級搜尋、搜尋、查詢、回應動作、mdatp、microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 15dec5396a5ba95fe3ec7af5f9a72bbf15e07140
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500502"
---
# <a name="create-custom-detection-rules"></a>建立自訂偵測規則

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

透過 [高級搜尋](advanced-hunting-overview.md) 查詢所建立的自訂偵測規則，可讓您主動監視各種事件和系統狀態，包括可疑的入侵行為和設定不當的裝置。 您可以將其設定為定期執行，並在每個專案相符時產生提醒並採取回應動作。

請閱讀本文以瞭解如何建立新的自訂偵測規則。 或者， [請參閱查看和管理現有的規則](custom-detections-manage.md)。

> [!NOTE]
> 若要建立或管理自訂的偵測， [您的角色](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) 必須具有「 **管理安全性設定** 」許可權。

## <a name="1-prepare-the-query"></a>1. 準備查詢。

在 Microsoft Defender Security Center 中，移至 [ **高級搜尋** ]，然後選取現有的查詢或建立新的查詢。 使用新的查詢時，請執行查詢以識別錯誤，並瞭解可能的結果。

>[!IMPORTANT]
>若要防止服務傳回太多警示，每個規則都限制為每次執行時只產生100警示。 在建立規則之前，請先調整您的查詢，以避免正常、日常活動的警示。

### <a name="required-columns-in-the-query-results"></a>查詢結果中的必要欄

若要使用自訂偵測規則的查詢，查詢必須傳回下列資料行：

- `Timestamp`
- `DeviceId`
- `ReportId`

簡單的查詢（如未使用 `project` or `summarize` 運算子自訂或匯總結果的查詢）通常會傳回這些通用欄。

有多種方式可確保更複雜的查詢傳回這些欄位。 例如，如果您想要匯總和計數 `DeviceId` ，您仍然可以傳回， `Timestamp` 並 `ReportId` 從與每個裝置相關的最近事件中取得。

下列範例查詢會計算具有防病毒偵測 () 的唯一裝置數目 `DeviceId` ，並使用這種方式，只尋找具有超過五個偵測的裝置。 若要傳回最新 `Timestamp` 和對應的 `ReportId` ，它會搭配 `summarize` 函數使用運算子 `arg_max` 。

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> 為了獲得更佳的查詢效能，請設定符合規則之預定執行頻率的時間篩選。 由於頻率最低的執行是每24小時，篩選過去一天會涵蓋所有新的資料。

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. 建立新的規則，並提供警示詳細資料。

使用查詢編輯器中的查詢，選取 [ **建立偵測規則** ]，並指定下列警示詳細資料：

- **偵測名稱**—偵測規則的名稱
- **Frequency**：執行查詢和採取動作的間隔。 [請參閱以下其他指導方針](#rule-frequency)
- **警示標題**—顯示規則所觸發警示的標題
- **嚴重性**（取決於規則所識別的元件或活動的潛在風險。 [警示嚴重性的閱讀](alerts-queue.md#severity)
- **類別**-威脅元件或活動的類型（如果有的話）。 [有關警示類別的閱讀資訊](alerts-queue.md#understanding-alert-categories)
- **MITRE ATT&CK 技術**-由規則識別的一或多個攻擊技術（如 MITRE ATT 中所述）&CK framework。 本節不適用於某些警示類別，例如惡意軟體、勒索軟體、可疑活動和不需要的軟體
- **描述**-規則所識別之元件或活動的詳細資訊 
- **建議動作**-回應者可能會採取以回應警示的其他動作

如需如何顯示警示詳細資訊的詳細資訊，請 [參閱警示佇列](alerts-queue.md)。

### <a name="rule-frequency"></a>規則頻率

儲存之後，新的自訂偵測規則會立即執行並檢查過去30天的資料是否相符。 然後，該規則會以固定間隔重新執行，並根據您所選擇的頻率 lookback 持續時間：

- **每24小時**-每24小時執行一次，檢查過去30天的資料
- **每12小時**-每12小時執行一次，檢查過去24小時的資料
- **每3小時**，每3小時執行一次，檢查過去6個小時的資料
- **每小時-每小時執行一次**，檢查過去2個小時的資料

當您編輯規則時，會根據您設定的頻率，在下一個執行時間執行所套用的變更。


> [!TIP]
> 使查詢中的時間篩選與 lookback 持續時間相符。 Lookback 持續時間以外的結果會被忽略。

選取您要監視偵測的頻率，並考慮組織的容量以回應提醒。

## <a name="3-choose-the-impacted-entities"></a>3. 選擇受影響的實體。

在查詢結果中識別欄，以找出主要受影響或受影響的實體。 例如，查詢可能會傳回裝置和使用者 IDs。 識別哪些欄位代表主要受影響的實體，可協助服務匯總相關的警示、關聯事件，以及目標回應動作。

您只能為每個實體類型選取一個欄。 無法選取查詢未傳回的資料行。

## <a name="4-specify-actions"></a>4. 指定動作。

您的自訂偵測規則可對查詢所傳回的檔案或裝置自動採取動作。

### <a name="actions-on-devices"></a>裝置上的動作

這些動作會套用至 `DeviceId` 查詢結果欄中的裝置：

- **隔離裝置**--應用完整網路隔離，以防止裝置連接至任何應用程式或服務，但不包括 Defender for Endpoint service。 [深入瞭解裝置隔離](respond-machine-alerts.md#isolate-devices-from-the-network)
- **收集調查套件**—收集 ZIP 檔案中的裝置資訊。 [深入瞭解調查套件](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **執行防病毒掃描**-在裝置上執行完整的 Microsoft Defender 防病毒掃描
- **開始調查**-在裝置上開始 [自動調查](automated-investigations.md)
- **限制應用程式執行**—設定裝置上的限制，只允許以 Microsoft 發行的憑證簽署的檔案執行。 [深入瞭解限制應用程式執行](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>檔上的動作

這些動作會套用至查詢結果的 [或] 欄中的檔案 `SHA1` `InitiatingProcessSHA1` ：

- **Allow/封鎖**-自動將檔案新增至您的 [自訂指示器清單](manage-indicators.md) ，使其永遠可以執行或封鎖執行。 您可以設定此動作的範圍，使其只會在選取的裝置群組上加以採用。 此範圍獨立于規則的範圍。
- **隔離** 檔-從其目前的位置刪除檔案，並將複本放入隔離區

### <a name="actions-on-users"></a>使用者的動作

- 將 **使用者標示為已遭破壞**-在 Azure Active Directory 中將使用者的風險層級設定為 "high"，以觸發對應的身分 [識別保護原則](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)。

## <a name="5-set-the-rule-scope"></a>5. 設定規則範圍。

設定範圍以指定規則涵蓋的裝置：

- 所有裝置
- 特定裝置群組

只會查詢範圍中裝置的資料。 此外，只會對那些裝置採取動作。

## <a name="6-review-and-turn-on-the-rule"></a>6. 檢查並開啟規則。

檢查規則之後，請選取 [ **建立** ] 以儲存該規則。 自訂偵測規則會立即執行。 它會以檢查相符專案的設定頻率重新執行，並產生警示和採取回應動作。

您可以 [查看和管理自訂的偵測規則](custom-detections-manage.md)、檢查其先前的執行，並查看其觸發的警示。 您也可以根據需要執行規則，並加以修改。

## <a name="related-topics"></a>相關主題

- [查看及管理自訂偵測規則](custom-detections-manage.md)
- [自訂偵測概觀](overview-custom-detections.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解進階搜捕查詢語言](advanced-hunting-query-language.md)
- [查看和組織提醒](alerts-queue.md)
