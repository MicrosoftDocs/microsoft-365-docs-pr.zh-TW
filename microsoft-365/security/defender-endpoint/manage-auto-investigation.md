---
title: 檢查自動調查後的修復動作
description: 在自動調查後，複查和核准 (或拒絕) 修正動作。
keywords: autoir，自動化，調查，偵測，修正，動作，擱置，已核准
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: b0c983f4ba939cee6485570af774c8a728c73944
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274925"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>在自動調查後複查修正動作

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>補救動作

當 [自動調查](automated-investigations.md) 執行時，會針對每個證據調查產生一個判定。 Verdicts 可能是 *惡意*、 *可疑* 或 *沒有發現威脅*。 

根據

- 威脅類型 
- 產生的判定和 
- 如何設定組織的 [裝置群組](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) 、 

修正動作可以自動進行，也可以只在組織的安全性運作小組核准時進行。 

以下是一些範例：

- **範例 1**： Fabrikam 的裝置群組會自動設定為 **完整修正威脅** (建議設定) 。 在此情況下，會自動對被視為惡意調查的偽像執行修正動作。 (請參閱 [複查已完成的動作](#review-completed-actions)) 。

- **範例 2**： Contoso 的裝置會包含在裝置群組中，此裝置群組是針對 **任何修正要求核准** 所設定的。 在此案例中，Contoso 的安全操作小組必須在自動調查後複查及核准所有修正動作 (請參閱 [複查擱置的動作](#review-pending-actions)) 。

- **範例 3**： Tailspin 玩具的裝置群組設定為 **無自動回應** (不建議) 。 在此情況下，不會進行自動調查。 未採取任何修正動作或擱置，而且不會在其裝置的 [動作中心](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) 記錄任何動作 (請參閱 [Manage device groups](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)) 。

不論是自動或核准，自動調查都可能會產生一或多項修正動作：
- 隔離檔
- 移除登錄機碼 
- 終止進程 
- 停止服務 
- 停用驅動程式 
- 移除排程任務

## <a name="review-pending-actions"></a>審閱擱置的動作

1. 請移至 Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) 並登入。
2. 在功能窗格中，選擇 [控制中心]。 
3. 檢查 [ **暫** 止] 索引標籤上的專案。 
4. 選取動作開啟其彈出窗格。
5. 在飛入窗格中，複查資訊，然後執行下列其中一個步驟：
   - 選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。
   - 選取 [ **核准** ] 以啟動暫止的動作。
   - 選取 [ **拒絕** ] 以避免採取暫止的動作。
   - 選取 [ **移至搜尋** ] 以進入 [高級搜尋](advanced-hunting-overview.md)。 

## <a name="review-completed-actions"></a>查看已完成的動作

1. 請移至 Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) 並登入。
2. 在功能窗格中，選擇 [控制中心]。 
3. 檢查 [ **記錄** ] 索引標籤上的專案。 
4. 選取專案，以查看有關修正動作的詳細資料。
 
## <a name="undo-completed-actions"></a>復原完成的動作

如果您已判斷某個裝置或檔案不是威脅，您可以復原採取的修正動作，不論這些動作是自動或手動採取的動作。 在 [ **記錄** ] 索引標籤上的 [操作中心] 中，您可以復原下列任何動作：  

| 動作來源 | 支援的動作 |
|:---|:---|
| -自動調查 <br/>-Microsoft Defender 防毒軟體 <br/>-手動回應動作 | 隔離裝置 <br/>-限制執行程式碼 <br/>-隔離檔 <br/>-移除登錄機碼 <br/>-停止服務 <br/>-停用驅動程式 <br/>-移除排程任務 |

### <a name="to-undo-multiple-actions-at-one-time"></a>一次取消執行多個動作

1. 請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。
2. 在 [ **記錄** ] 索引標籤上，選取您要復原的動作。 請務必選取具有相同動作類型的專案。 隨即開啟彈出窗格。
3. 在快顯視窗中，選取 [ **復原**]。

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>在多個裝置間移除隔離檔 

1. 請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。
2. 在 [ **記錄** ] 索引標籤上，選取具有 [ **隔離** 檔] 動作類型的專案。
3. 在飛入窗格中，選取 [套用 **至此檔案的 X 個實例**]，然後選取 [ **復原**]。

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>自動化層級、自動調查結果和結果動作

自動化層級會影響是否會自動或只在核准時採取某些修正動作。 在某些情況下，您的安全性作業小組也會有更多步驟，視自動調查的結果而定。 下表摘要說明自動化層級、自動化調查的結果，以及每個案例中應執行的動作。 

|裝置群組設定 | 自動調查結果 | 處理方式 |
|:---|:---|:---|
|**完整修正威脅會自動** (建議設定)  |對一條證據達成 *惡意的蓄意* 性。 <br/><br/>系統會自動採取適當的修復動作。 |[查看已完成的動作](#review-completed-actions) |
|**自動修正威脅** |有一條證據會達到 *可疑* 的判定。 <br/><br/>修正動作正待核准，繼續進行。 | [核准 (或拒絕) 擱置的動作](#review-pending-actions) |
|**半要求進行任何修正的核准**  |針對某個證據，會達到對 *惡意* 或 *可疑* 的判定。 <br/><br/>修正動作正待核准，繼續進行。  |[核准 (或拒絕) 擱置的動作](#review-pending-actions) |
|**半自動要求核心資料夾修正的核准** |對一條證據達成 *惡意的蓄意* 性。 <br/><br/>如果專案是檔案或可執行檔，且位於作業系統目錄中，例如 Windows 資料夾或 Program files 資料夾，則修正動作會等候等候核准。 <br/><br/>如果專案 *不* 在作業系統目錄中，就會自動採取修復動作。 |1. [核准 (或拒絕) 擱置的動作](#review-pending-actions)<br/><br/>2. [檢查完成的動作](#review-completed-actions) |
|**半自動要求核心資料夾修正的核准** |有一條證據會達到 *可疑* 的判定。 <br/><br/>修正動作正待核准。  |[核准 (或拒絕) 擱置的動作](#review-pending-actions)。|
|**非 temp 資料夾修正的半要求核准** |對一條證據達成 *惡意的蓄意* 性。 <br/><br/>如果專案是不在暫存資料夾中的檔案或可執行檔，例如使用者的 [下載] 資料夾或 temp 資料夾，則修正動作會等候進行核准。 <br/><br/>如果專案是暫存資料夾中的檔案或可執行檔 *，便會* 自動採取修正動作。  |1. [核准 (或拒絕) 擱置的動作](#review-pending-actions)<br/><br/>2. [檢查完成的動作](#review-completed-actions)  |
|**非 temp 資料夾修正的半要求核准** |有一條證據會達到 *可疑* 的判定。 <br/><br/>修正動作正待核准。 |[核准 (或拒絕) 擱置的動作](#review-pending-actions)  | 
|任何 **完整** 或 **半成品** 的自動化層級 |對某項證據的判定，未 *找到任何威脅* 。 <br/><br/>不會採取任何修正動作，也不會有任何動作正待核准。 |[檢視自動調查的詳細資料和結果](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center) |
|不建議使用 **自動回應** () |不會執行自動調查，因此不會達到 verdicts，也不會採取任何修正動作，也不會等候核准。 |[考慮設定或變更您的裝置群組，以使用 **完整** 或 **半** 個自動化](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) |

在 Microsoft Defender for Endpoint 中，所有的 verdicts 都會在「 [行動中心](auto-investigation-action-center.md#new-a-unified-action-center)」追蹤。

## <a name="next-steps"></a>後續步驟

- [深入瞭解即時回應功能](live-response.md)
- [使用高級搜尋主動搜尋威脅](advanced-hunting-overview.md)
- [解決適用於端點的 Microsoft Defender 中的誤判/漏報](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>另請參閱

- [自動化調查的概述](automated-investigations.md)
