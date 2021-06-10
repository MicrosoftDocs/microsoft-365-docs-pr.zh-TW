---
title: 在行動中心中查看及管理動作
description: 使用「行動中心」來查看及管理修正動作
keywords: 動作, 中心, autoair, 自動化, 調查, 回應, 補救
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 95c82f815c794662f7eb0ffaabcfb5f81df3e828
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782990"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>在行動中心中查看及管理動作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

Microsoft 365 Defender 中的威脅防護功能可能會導致某些修正動作。 範例如下：

- [自動調查](m365d-autoir.md) 可能會導致自動採取或等待您核准的修復動作。
- 防毒程式、反惡意程式碼和其他威脅防護功能可能會導致修復動作，例如封鎖檔案、URL 或程式，或將專案傳送至隔離區。
- 您的安全性運作小組可以手動採取補救措施，例如在 [高級搜尋](advanced-hunting-overview.md) 期間或調查 [警示](investigate-alerts.md) 或 [事件](investigate-incidents.md)。

> [!NOTE]
> 您必須具備[適當的權限](m365d-action-center.md#required-permissions-for-action-center-tasks)，才能核准或拒絕補救動作。 如需詳細資訊，請參閱 [必要條件](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。

## <a name="review-pending-actions-in-the-action-center"></a>在重要中心檢查擱置的動作

務必盡快核准 (或拒絕) 擱置中的動作，這樣您的自動化調查才能及時進行和完成。 

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 

2. 在功能窗格中，選擇 [控制中心]。 

3. 在 [動作中心] 的 [ **擱置** ] 索引標籤上，選取清單中的專案。 其快顯視窗隨即開啟。 以下為範例。

   ![核准或拒絕動作](../../media/air-actioncenter-itemselected.png)

4. 查看彈出窗格中的資訊，然後執行下列其中一個步驟：
   - 選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。
   - 選取 [ **核准** ] 以啟動暫止的動作。
   - 選取 [ **拒絕** ] 以避免採取暫止的動作。
   - 選取 [ **移至搜尋** ] 以進入 [高級搜尋](advanced-hunting-overview.md)。 

## <a name="undo-completed-actions"></a>復原完成的動作

如果您已判斷某個裝置或檔案不是威脅，您可以復原採取的修正動作，不論這些動作是自動或手動採取的動作。 在 [ **記錄** ] 索引標籤上的 [操作中心] 中，您可以復原下列任何動作：  

| 動作來源 | 支援的動作 |
|:---|:---|
| -自動調查 <br/>-Microsoft Defender 防毒軟體 <br/>-手動回應動作 | 隔離裝置 <br/>-限制執行程式碼 <br/>-隔離檔 <br/>-移除登錄機碼 <br/>-停止服務 <br/>-停用驅動程式 <br/>-移除排程任務 |

### <a name="undo-one-remediation-action"></a>復原一個修正動作

1. 請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。

2. 在 [ **記錄** ] 索引標籤上，選取您要復原的動作。

3. 在螢幕右側的窗格中，選取 [ **復原**]。

### <a name="undo-multiple-remediation-actions"></a>復原多項修復動作

1. 請移至「行動中心」 (https://security.microsoft.com/action-center) 並登入。

2. 在 [ **記錄** ] 索引標籤上，選取您要復原的動作。 請務必選取具有相同動作類型的專案。 隨即開啟彈出窗格。

3. 在快顯視窗中，選取 [ **復原**]。

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>在多個裝置間移除隔離檔 

1. 請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。

2. 在 [ **記錄** ] 索引標籤上，選取具有 **隔離檔** 動作類型的檔案。

3. 在螢幕右側的窗格中，選取 [套用至此檔案 **的 X 個實例**]，然後選取 [ **復原**]。

## <a name="next-steps"></a>後續步驟

- [檢視自動調查的詳細資料和結果](m365d-autoir-results.md)
- [位址誤報或漏報](m365d-autoir-report-false-positives-negatives.md)
