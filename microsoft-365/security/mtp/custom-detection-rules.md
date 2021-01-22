---
title: 在 Microsoft 365 Defender 中建立及管理自訂偵測規則
description: 瞭解如何根據進位搜尋查詢建立及管理自訂偵測規則
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、自訂偵測、規則、架構、kusto、microsoft 365、Microsoft Threat Protection、RBAC、許可權、Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8c7e47e66f9e5543cc122c5b5154207cae836d2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932919"
---
# <a name="create-and-manage-custom-detections-rules"></a>建立及管理自訂偵測規則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

自訂偵測規則是您可以使用進一步搜尋查詢設計和 [調整](advanced-hunting-overview.md) 的規則。 這些規則可讓您主動監控各種事件和系統狀態，包括可疑的外泄活動和錯誤配置的端點。 您可以將它們設定為定期執行、產生警示，以及每當有符合專案時採取回應動作。

## <a name="required-permissions-for-managing-custom-detections"></a>管理自訂偵測功能所需的許可權

若要管理自訂偵測，您必須被指派以下其中一個角色：

- **安全性系統管理員**-擁有 [此 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的使用者可以管理 Microsoft 365 安全性中心及其他入口網站和服務的安全性設定。

- **安全性運算子**-擁有 [此 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的使用者可以管理警示，並擁有安全性相關功能 ，包括 Microsoft 365 安全性中心內所有資訊之全域唯讀存取權。 只有在 Microsoft Defender for Endpoint 中關閉以角色為基礎的存取控制 (RBAC) ，這個角色就足以管理自訂偵測。 如果您設定了 RBAC，您還需要管理端點的Defender 安全性設定許可權。

若要管理必要的許可權，全域 **管理員可以** ：

- 在 **Microsoft** [365](https://admin.microsoft.com/)系統管理中心中，在角色安全性系統管理員下指派安全性系統管理員 ****  >  **或安全性運算子角色**。
- 在設定許可權角色下，檢查 Microsoft [Defender](https://securitycenter.windows.com/)資訊安全中心端點的 Microsoft Defender  >  **RBAC**  >  **設定**。 選取對應的角色以指派 **管理安全性設定** 許可權。

> [!NOTE]
> 若要管理自訂偵測，如果已開啟 RBAC，**安全性** 運算子需要在 Microsoft Defender for Endpoint 中管理安全性設定許可權。 

## <a name="create-a-custom-detection-rule"></a>建立自訂偵測規則
### <a name="1-prepare-the-query"></a>1. 準備查詢。

在 Microsoft 365 資訊安全中心，請前往進位搜尋並選取現有的查詢或建立新查詢。 使用新查詢時，執行查詢以找出錯誤並瞭解可能的結果。

>[!IMPORTANT]
>為了防止服務回電太多通知，每一個規則每次執行時只能產生 100 個通知。 在建立規則之前，請調整查詢，以避免收到一般日常活動的警示。


#### <a name="required-columns-in-the-query-results"></a>查詢結果中所需的資料行
若要建立自訂偵測規則，查詢必須返回下列資料行：

- `Timestamp`—用來設定產生警示的時間戳記
- `ReportId`— 啟用原始記錄的查找
- 識別特定裝置、使用者或信箱的下列其中一欄：
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (信封寄件者或Return-Path位址) 
    - `SenderMailFromAddress` (用戶端視窗顯示的寄件者) 
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>當新資料表新增到進一步搜尋架構時，將會新增其他 [實體的支援](advanced-hunting-schema-tables.md)。

簡單的查詢 ，例如不使用 or 運算子來自訂或匯總結果的查詢， `project` `summarize` 通常會返回這些共同資料行。

有多種方式可確保更複雜的查詢會回回這些資料行。 例如，如果您想要根據欄下的實體匯總和計算，您仍可返回並取得與每個唯一專案有關的最近 `DeviceId` `Timestamp` `ReportId` 事件 `DeviceId` 。

以下的範例查詢會計算具有防毒軟體偵測 () 裝置的唯一裝置數量，並使用此計數僅尋找偵測超過五個 `DeviceId` 的裝置。 若要將最新 `Timestamp` 值及對應的值 `ReportId` 退回，它會 `summarize` 將運算子與 `arg_max` 函數一併使用。

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> 為提升查詢的顯示效果，請設定符合規則預定執行頻率的時間篩選。 由於最不常執行的時間是 _每 24 小時_，因此篩選過去一天會涵蓋所有新資料。

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 建立新規則並提供警示詳細資料。

在查詢編輯器中查詢時，選取建立 **偵測規則** 並指定下列警示詳細資料：

- **偵測名稱**-偵測規則的名稱
- **頻率**—執行查詢和採取動作的間隔。 [請參閱下方的其他指引](#rule-frequency)
- **提醒標題**-顯示由規則引發之提醒的標題
- **嚴重性**-規則所識別之元件或活動的潛在風險
- **類別**—規則所識別的威脅元件或活動
- **MITRE ATT&CK** 技術 — 一或多個由 RULE 所識別的受攻擊技術，如 [MITRE ATT&CK 架構所記錄](https://attack.mitre.org/)。 此區段會隱藏于特定的警示類別，包括惡意攻擊、勒索軟體、可疑活動以及不想要的軟體
- **描述**— 規則所識別之元件或活動詳細資訊 
- **建議的動作**—回應者在回應通知時可能會採取的其他動作

#### <a name="rule-frequency"></a>規則頻率
當您儲存或編輯新規則時，它會執行並檢查過去 30 天內的資料是否一樣。 規則接著會以固定間隔再次執行，並依據您選擇的頻率來申請回期限：

- **每 24 小時** 一次 — 每 24 小時執行一次，檢查過去 30 天的資料
- **每 12 小時** 一次 — 每 12 小時執行一次，檢查過去 24 小時的資料
- **每 3 小時** 一次 — 每 3 小時執行一次，檢查過去 6 小時的資料
- **每小時一** 次 — 每小時執行一次，檢查過去 2 小時的資料

>[!TIP]
> 比對查詢中的時間篩選與回省期間。 會忽略回省期間以外的結果。  

選取與您要密切監控偵測的頻率一樣的頻率。 考慮貴組織回應警示的能力。

### <a name="3-choose-the-impacted-entities"></a>3.選擇影響實體。
在查詢結果中找出預期會受影響或受影響的主要實體的資料行。 例如，查詢可能會 (寄件者) `SenderFromAddress` `SenderMailFromAddress` 寄件者 () `RecipientEmailAddress` 位址。 識別代表主要影響實體的這些欄，可協助服務匯總相關警示、關聯事件及目標回應動作。

您僅能針對信箱、使用者或裝置 (每個實體類型選取一) 。 無法選取查詢未返回的資料行。

### <a name="4-specify-actions"></a>4. 指定動作。
您的自訂偵測規則可以針對查詢所發回的裝置、檔案或使用者自動採取動作。

#### <a name="actions-on-devices"></a>裝置上的動作
這些動作會適用于查詢結果 `DeviceId` 欄中的裝置：
- **隔離裝置**— 使用 Microsoft Defender for Endpoint 來執行完整的網路隔離，防止裝置連接到任何應用程式或服務。 [深入瞭解 Microsoft Defender for Endpoint 電腦隔離](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **收集調查套件**— 收集 ZIP 檔案中的裝置資訊。 [深入瞭解 Microsoft Defender 端點調查套件](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **執行防毒掃描**- 在裝置上執行完整的 Windows Defender 防毒軟體掃描
- **啟動調查**- 啟動 [裝置](mtp-autoir.md) 上的自動化調查
- **限制應用程式執行**— 設定裝置限制，只允許以 Microsoft 發行憑證簽署的檔案執行。 [使用 Microsoft Defender for Endpoint 深入瞭解應用程式限制](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>對檔案執行動作
選取時，您可以選擇對查詢結果的、、或欄中的檔案執行 `SHA1` 隔離 `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 檔案動作。 這個動作會從檔案目前的位置刪除檔案，並隔離一份檔案。

#### <a name="actions-on-users"></a>對使用者採取的動作
選取時 **，會針對** 查詢結果的 、或欄中的使用者採取將使用者標記為已 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` 入侵的動作。 此動作在 Azure Active Directory 中將使用者風險層級設定為「高」，並觸發對應的 [身分識別保護原則](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。

> [!NOTE]
> Microsoft 365 Defender 目前不支援自訂偵測規則的允許或封鎖動作。

### <a name="5-set-the-rule-scope"></a>5. 設定規則範圍。
設定範圍以指定規則涵蓋哪些裝置。 檢查裝置且不影響只檢查信箱和使用者帳戶或身分身分之規則的範圍規則。

設定範圍時，您可以選取：

- 所有裝置
- 特定裝置群組

系統只會查詢範圍中裝置的資料。 此外，只會在那些裝置上採取動作。

### <a name="6-review-and-turn-on-the-rule"></a>6. 檢查並開啟規則。
在審查規則之後，選取建立 **以** 儲存規則。 自訂偵測規則會立即執行。 它會根據已配置的頻率再次執行，以檢查符合專案、產生警示，以及採取回應動作。

## <a name="manage-existing-custom-detection-rules"></a>管理現有的自訂偵測規則
您可以檢閱現有自訂偵測規則的清單、檢查先前的執行，以及檢閱規則所觸發的警示。 您也可以依需求執行規則並進行修改。

### <a name="view-existing-rules"></a>查看現有規則

若要查看所有現有的自訂偵測規則，請流覽至 **搜尋**  >  **自訂偵測**。 此頁面會列出所有規則，並包含下列執行資訊：

- **上次執行** 時 -上次執行規則時，檢查查詢是否符合並產生警示
- **上次執行狀態**- 是否順利執行規則
- **下一次** 執行 -下一個已排程執行
- **狀態**-無論規則已開啟或關閉

### <a name="view-rule-details-modify-rule-and-run-rule"></a>查看規則詳細資料、修改規則及執行規則

若要查看自訂偵測規則完整的資訊，請前往搜尋自訂偵測，  >  然後選取規則名稱。 接著，您可以查看規則的一般資訊，包括其執行狀態和範圍資訊。 此頁面也會提供觸發警示和動作的清單。

![自訂偵測規則詳細資料頁面](../../media/custom-detection-details.png)<br>
*自訂偵測規則詳細資料*

您也可以在此頁面上對規則執行下列動作：

- **執行**- 立即執行規則。 這樣也會重設下一次執行間隔。
- **編輯**- 修改規則而不變更查詢
- **修改查詢**- 在進一步搜尋中編輯查詢
- **開啟**  / **關閉**-啟用規則或停止其運作
- **刪除**- 關閉並移除規則

### <a name="view-and-manage-triggered-alerts"></a>查看及管理觸發警示

在規則詳細資料畫面 (搜尋自訂偵測 [規則名稱]) ，請前往 [觸發的警示]，其中列出由規則比對產生的  >    >  警示。  選取警示以查看其詳細資訊，並採取下列動作：

- 您可以設定警示的狀態和分類， (或誤) 
- 將警示連結至事件
- 執行觸發進位搜尋警示的查詢

### <a name="review-actions"></a>檢查動作
在規則詳細資料畫面 (搜尋自訂偵測 [規則名稱]) ，請前往 [觸發的動作]，其中根據規則比對結果列出  >    >  已採取的動作。 

>[!TIP]
>若要快速查看資訊，並針對表格中的專案採取動作，請使用表格左側的選取欄 [&#10003;]。

## <a name="related-topic"></a>相關主題
- [自訂偵測概觀](custom-detections-overview.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解進階搜捕查詢語言](advanced-hunting-query-language.md)
