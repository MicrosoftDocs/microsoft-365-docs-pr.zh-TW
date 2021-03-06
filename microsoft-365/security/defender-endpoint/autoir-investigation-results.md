---
title: 檢視自動調查的詳細資料和結果
description: 在自動調查過程中和完成之後，您就可以查看結果和重要結果
keywords: 自動, 調查, 結果, 分析, 詳細資料, 修正, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: a10442bc9d92bb6004149180da30b86b646dd5de
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290156"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>檢視自動調查的詳細資料和結果

適用於：
- 適用於端點的 Microsoft Defender

使用 Microsoft Defender for Endpoint 時，當 [自動調查](automated-investigations.md) 執行時，該調查的詳細資料就會在自動調查程式期間和之後使用。 如果您擁有必要權限，您可以在調查詳細資料檢視中查看這些詳細資料。 調查詳細資料檢視可提供您最新的狀態，以及核准任何待核准動作的能力。 

## <a name="new-unified-investigation-page"></a> (NEW！ ) 整合調查頁面

調查頁面最近已經過更新，可納入整個裝置、電子郵件及共同作業內容的資訊。 新的整合調查頁面會定義一種通用語言，並提供在[Microsoft defender For Endpoint](microsoft-defender-endpoint.md)和[microsoft defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp)中自動調查的整合體驗。 

> [!TIP]
> 若要深入瞭解變更的相關資訊，請參閱 [ (NEW！ ) 整合調查] 頁面](/microsoft-365/security/mtp/mtp-autoir-results)。

## <a name="open-the-investigation-details-view"></a>開啟調查詳細資料檢視

您可以使用下列其中一種方法開啟調查詳細資料檢視：

- [選取 [控制中心] 中的項目](#select-an-item-in-the-action-center)
- [從事件詳細資料頁面中選取調查](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>選取 [控制中心] 中的項目

改進的 [動作中心](auto-investigation-action-center.md) 會透過您的裝置、電子郵件 & 共同作業內容和身分識別，將 [修正動作](manage-auto-investigation.md#remediation-actions) 彙集在一起。 列出的動作包括自動或手動採取的修復動作。 在 [行動中心] 中，您可以查看等候核准的動作，以及已核准或已完成的動作。 您也可以流覽到更多詳細資料，例如調查頁面。

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 
2. 在功能窗格中，選擇 [控制中心]。 
3. 在 [待核准] 或 [歷史記錄] 索引標籤上，選取一個項目。 其快顯視窗隨即開啟。
4. 查看彈出窗格中的資訊，然後執行下列其中一個步驟：
   - 選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。
   - 選取 [ **核准** ] 以啟動暫止的動作。
   - 選取 [ **拒絕** ] 以避免採取暫止的動作。
   - 選取 [ **移至搜尋** ] 以進入 [高級搜尋](advanced-hunting-overview.md)。

### <a name="open-an-investigation-from-an-incident-details-page"></a>從事件詳細資料頁面開啟調查

使用事件詳細資料頁面來查看事件的詳細資訊，包括觸發任何受影響裝置、使用者帳戶或信箱之資訊的警示。

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 
2. 在功能窗格中，選擇 [**事件] & 警示**  >  **事件**。 
3. 選取清單中的專案，然後選擇 [ **開啟事件] 頁面**。
4. 選取 [ **調查** ] 索引標籤，然後在清單中選取調查。 其快顯視窗隨即開啟。
5. 選取 [ **開啟調查] 頁面**。 

## <a name="investigation-details"></a>調查詳細資料

使用調查詳細資料檢視，查看與調查相關的過去、目前和待核准的活動。 調查詳細資料檢視類似以下影像：

在調查詳細資料檢視中，您可以在 [調查圖表]、[警示]、[裝置]、[身分識別]、[重要結果]、[實體]、**[記錄]**，以及 [待核准的動作] 索引標籤上查看資訊，如下表所述。

> [!NOTE]
> 您在 [調查詳細資料] 頁面看到的特定索引標籤取決於您的訂閱所包含的專案。 例如，如果您的訂閱不包含適用于 Office 365 方案2的 Microsoft Defender，您就不會看到 [**信箱**] 索引標籤。

| 索引標籤 | 描述 |
|:--------|:--------|
| **調查圖表** | 提供調查的視覺呈現。 描述實體並列出發現的威脅和警示，以及是否有任何待核准的動作。<br/>您可以在圖形上選取一個專案，以查看詳細資料。 例如，選取 **證據** 圖示會帶您前往 [ **證據** ] 索引標籤，您可以在其中看到偵測到的實體及其 verdicts。 |
| **提醒** | 列出與調查相關聯的警示。 警示可能來自使用者裝置上的威脅防護功能、Office 應用程式、雲端 App 安全性及其他 Microsoft 365 Defender 功能。|
| **裝置** | 列出調查中包含的裝置及其修正層級。  (修正層級會對應至 [裝置群組的自動化層級](automation-levels.md)。 )  |
| **信箱** |列出受偵測到之威脅影響的信箱。  |
| **使用者**  | 列出受偵測到之威脅影響的使用者帳戶。 |
| **證據** | 列出由警示/調查產生的證據片段。 包括 verdicts (*惡意*、 *可疑* 或 *未找到威脅*) 和修正狀態。 |
| **Entities** | 提供每個已分析之實體的詳細資料，包括每個實體類型的判定 (*惡意*、 *可疑* 或沒有) 中 *找到的威脅* 。|
|**Log** | 提供觸發警示之後所採取之所有調查動作的按時間排序的詳細視圖。|
| **待核准的動作** | 列出需要核准才能繼續的項目。 請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 核准擱置的動作。 |

## <a name="see-also"></a>另請參閱

- [在自動調查後複查修正動作](manage-auto-investigation.md)
- [檢視及組織適用於端點的 Microsoft Defender 事件佇列](view-incidents-queue.md)