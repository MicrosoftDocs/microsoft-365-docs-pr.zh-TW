---
title: 在 Microsoft 365 Defender 中建立及管理自訂偵測規則
description: 瞭解如何根據高級搜尋查詢建立及管理自訂偵測規則
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，自訂偵測，rules，schema，kusto，microsoft 365，Microsoft 威脅防護，RBAC，許可權，Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 5de4532a1bba809cde16ba6033ab30773a832176
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846769"
---
# <a name="create-and-manage-custom-detections-rules"></a>建立及管理自訂的偵測規則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

自訂偵測規則是您可以使用 [高級搜尋](advanced-hunting-overview.md) 查詢進行設計和調整的規則。 這些規則可讓您主動監視各種事件和系統狀態，包括可疑的侵犯活動和設定不當的端點。 您可以將其設定為定期執行，並在每個專案相符時產生提醒並採取回應動作。

## <a name="required-permissions-for-managing-custom-detections"></a>管理自訂偵測的必要許可權

若要管理自訂偵測，您必須被指派其中一個角色：

- **安全性管理員** ：具有此 [Azure Active Directory 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 的使用者可以管理 Microsoft 365 安全性中心及其他入口網站和服務中的安全性設定。

- **安全操作員** -具有此 [Azure Active Directory 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 的使用者可以管理提醒，並具有安全相關功能的全域唯讀許可權，包括 Microsoft 365 Security center 中的所有資訊。 只有在 Microsoft Defender for Endpoint 中關閉以角色為基礎的存取控制 (RBAC) 時，此角色才足以管理自訂偵測。 如果您已設定 RBAC，您也需要使用 Defender for Endpoint 的「 **管理安全性設定** 」許可權。

若要管理必要的許可權， **全域管理員** 可以：

- 在 [ **role** security admin] 底下的 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)中指派 **安全性管理員** 或 **安全性操作員** 角色  >  **** 。
- 在 [ **設定** 許可權角色] 底下的 [microsoft defender Security Center](https://securitycenter.windows.com/)中檢查 microsoft defender for Endpoint 的 RBAC 設定  >  **Permissions**  >  **** 。 選取對應的角色以指派「 **管理安全性設定** 」許可權。

> [!NOTE]
> 若要管理自訂偵測，當已開啟 RBAC 時， **安全性操作員** 會需要 Microsoft Defender for Endpoint 中的「 **管理安全性設定** 」許可權。

## <a name="create-a-custom-detection-rule"></a>建立自訂偵測規則
### <a name="1-prepare-the-query"></a>1. 準備查詢。

在 Microsoft 365 的 [安全性中心] 中，移至 [ **高級搜尋** ]，然後選取現有的查詢或建立新的查詢。 使用新的查詢時，請執行查詢以識別錯誤，並瞭解可能的結果。

>[!IMPORTANT]
>若要防止服務傳回太多警示，每個規則都限制為每次執行時只產生100警示。 在建立規則之前，請先調整您的查詢，以避免正常、日常活動的警示。


#### <a name="required-columns-in-the-query-results"></a>查詢結果中的必要欄
若要建立自訂偵測規則，查詢必須傳回下列資料行：

- `Timestamp`-用於設定所產生警示的時間戳記
- `ReportId`-啟用原始記錄的查閱
- 下列其中一欄可識別特定裝置、使用者或信箱：
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (信封寄件者或 Return-Path 位址) 
    - `SenderMailFromAddress` 電子郵件客戶程式顯示的 (寄件者位址) 
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>當新的資料表新增至 [高級搜尋架構](advanced-hunting-schema-tables.md)時，將新增額外實體的支援。

簡單的查詢（如未使用 `project` or `summarize` 運算子自訂或匯總結果的查詢）通常會傳回這些通用欄。

有多種方式可確保更複雜的查詢傳回這些欄位。 例如，如果您想要依實體（如所示）匯總和計數 `DeviceId` ，仍然可以傳回 `Timestamp` ，並 `ReportId` 從每個唯一相關的最近事件中取得 `DeviceId` 。

下列範例查詢計算使用防病毒偵測 () 的唯一裝置數目 `DeviceId` ，並使用此計數來找出超過五個偵測的裝置。 若要傳回最新 `Timestamp` 和對應的 `ReportId` ，它會搭配 `summarize` 函數使用運算子 `arg_max` 。

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> 為了獲得更佳的查詢效能，請設定符合規則之預定執行頻率的時間篩選。 由於頻率最低的執行是 _每24小時_ ，篩選過去一天會涵蓋所有新的資料。

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 建立新的規則，並提供警示詳細資料。

使用查詢編輯器中的查詢，選取 [ **建立偵測規則** ]，並指定下列警示詳細資料：

- **偵測名稱** —偵測規則的名稱
- **Frequency** ：執行查詢和採取動作的間隔。 [請參閱以下其他指導方針](#rule-frequency)
- **警示標題** —顯示規則所觸發警示的標題
- **嚴重性** （由規則所識別之元件或活動的潛在風險）
- **類別** ：由規則識別的威脅元件或活動
- **MITRE ATT&CK 技術** -由規則識別的一或多個攻擊技術（如 MITRE ATT 中所述） [&CK framework](https://attack.mitre.org/)。 此區段針對某些警示類別（包括惡意程式碼、勒索軟體、可疑活動和不需要的軟體）隱藏。
- **描述** -規則所識別之元件或活動的詳細資訊 
- **建議動作** -回應者可能會採取以回應警示的其他動作

#### <a name="rule-frequency"></a>規則頻率
當您儲存或編輯新規則時，它會執行並檢查過去30天的資料是否相符。 然後，此規則會以固定間隔重新執行，並根據您選擇的頻率套用 lookback 持續時間：

- **每24小時** -每24小時執行一次，檢查過去30天的資料
- **每12小時** -每12小時執行一次，檢查過去24小時的資料
- **每3小時** ，每3小時執行一次，檢查過去6個小時的資料
- **每小時-每小時執行一次** ，檢查過去2個小時的資料

>[!TIP]
> 使查詢中的時間篩選與 lookback 持續時間相符。 Lookback 持續時間以外的結果會被忽略。  

選取頻率，以符合您要監視偵測的程度。 請考慮您組織的容量，以回應提醒。

### <a name="3-choose-the-impacted-entities"></a>3. 選擇受影響的實體。
在查詢結果中識別欄，以找出主要受影響或受影響的實體。 例如，查詢可能會傳回寄件者 (`SenderFromAddress` 或 `SenderMailFromAddress`) 和收件者 (`RecipientEmailAddress`) 位址。 識別哪些欄位代表主要受影響的實體，可協助服務匯總相關的警示、關聯事件，以及目標回應動作。

您只能為每個實體類型 (信箱、使用者或裝置) 選取一個資料行。 無法選取查詢未傳回的資料行。

### <a name="4-specify-actions"></a>4. 指定動作。
您的自訂偵測規則可在查詢所傳回的裝置、檔案或使用者上自動採取動作。

#### <a name="actions-on-devices"></a>裝置上的動作
這些動作會套用至 `DeviceId` 查詢結果欄中的裝置：
- **隔離裝置** —使用 Microsoft Defender for Endpoint 來套用完整網路隔離，以防止裝置連接至任何應用程式或服務。 [深入瞭解 Microsoft Defender for Endpoint machine 隔離](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **收集調查套件** —收集 ZIP 檔案中的裝置資訊。 [深入瞭解 Microsoft Defender for Endpoint 調查套件](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **執行防病毒掃描** -在裝置上執行完整的 Windows Defender 防病毒掃描
- **開始調查** --在裝置上開始 [自動調查](mtp-autoir.md)
- **限制應用程式執行** —設定裝置上的限制，只允許以 Microsoft 發行的憑證簽署的檔案執行。 [深入瞭解 Microsoft Defender for Endpoint 的應用程式限制](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>檔上的動作
選取此選項時，您可以選擇對查詢結果的、、或欄中的檔案套用 **隔離檔** 動作 `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 。 此巨集指令會從目前的位置刪除檔案，並將複本放入隔離區。

#### <a name="actions-on-users"></a>使用者的動作
選取此選項時，會對使用者于、或欄中的查詢結果，對使用者採取「將 **使用者標示為受損** 」動作 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` 。 此動作會在 Azure Active Directory 中將使用者風險層級設為「高」，以觸發對應的身分 [識別保護原則](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。

> [!NOTE]
> Microsoft 365 Defender 目前不支援自訂偵測規則的 allow 或 block 動作。

### <a name="5-set-the-rule-scope"></a>5. 設定規則範圍。
設定範圍以指定規則涵蓋哪些裝置。 此範圍會影響檢查裝置的規則，而不會影響僅檢查信箱和使用者帳戶或身分識別的規則。

當您設定範圍時，您可以選取：

- 所有裝置
- 特定裝置群組

只會查詢範圍中裝置的資料。 此外，只會對那些裝置採取動作。

### <a name="6-review-and-turn-on-the-rule"></a>6. 檢查並開啟規則。
檢查規則之後，請選取 [ **建立** ] 以儲存該規則。 自訂偵測規則會立即執行。 它會以檢查相符專案的設定頻率重新執行，並產生警示和採取回應動作。

## <a name="manage-existing-custom-detection-rules"></a>管理現有的自訂偵測規則
您可以查看現有的自訂偵測規則清單，檢查其先前的執行，並查看其觸發的警示。 您也可以根據需要執行規則，並加以修改。

### <a name="view-existing-rules"></a>查看現有規則

若要查看所有現有的自訂偵測規則，請流覽至 **搜尋**  >  **自訂** 偵測。 頁面會列出具有下列執行資訊的所有規則：

- **上次執行** 時間-最後一次執行規則以檢查查詢符合專案並產生警示
- **上次執行狀態** —是否已成功執行規則
- **下一次執行** （下一個排程的執行）
- **狀態** —是否已開啟或關閉規則

### <a name="view-rule-details-modify-rule-and-run-rule"></a>View rule details、modify rule 及 run rule

若要查看有關自訂偵測規則的完整資訊，請移至 **搜尋**  >  **自訂** 偵測，然後選取規則的名稱。 然後您就可以查看規則的一般資訊，包括資訊的執行狀態和範圍。 此頁面也會提供觸發警示和動作的清單。

![自訂偵測規則詳細資料頁面](../../media/custom-detection-details.png)<br>
*自訂偵測規則詳細資料*

您也可以在此頁面上對規則採取下列動作：

- **Run** -立即執行規則。 這也會重設下一個執行的間隔。
- **編輯** —修改規則但不變更查詢
- **修改查詢** -在高級搜尋中編輯查詢
- **開啟**  / **關閉** —啟用規則或停止執行
- **刪除** —關閉規則並加以移除

### <a name="view-and-manage-triggered-alerts"></a>查看及管理觸發的警示

在 [規則詳細資料] 畫面中 ( **搜尋**  >  **自訂** 偵測  >  **[規則名稱]** ) 中，移至 [ **觸發警示** ]，其中會列出與規則相符所產生的警示。 選取警示以查看與其相關的詳細資訊，並採取下列動作：

- 透過設定其狀態和分類 (true 或 false 警示來管理提醒) 
- 將警示連結到事件
- 在高級搜尋中執行觸發警示的查詢

### <a name="review-actions"></a>審閱動作
在 [規則詳細資料] 畫面中 ( **搜尋**  >  **自訂** 偵測  >  **[規則名稱]** ) 中，移至 [ **觸發的動作** ]，其中會根據符合規則的相符，列出所採取的動作。

>[!TIP]
>若要快速查看資訊，並對表格中的專案採取動作，請使用表格左邊的選取範圍欄 [&#10003;]。

## <a name="related-topic"></a>相關主題
- [自訂偵測概觀](custom-detections-overview.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解進階搜捕查詢語言](advanced-hunting-query-language.md)
