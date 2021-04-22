---
title: 在 Microsoft 365 中查看自動調查的結果
keywords: AIR，autoIR，Microsoft Defender for Endpoint，自動化，調查，修正，動作
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在 Microsoft 365 中的自動調查期間和之後，您可以查看結果和重要結果。
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ebdd25e9bddf53682f747fff7477d49dd1c94755
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933490"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Microsoft 365 中自動調查的詳細資料和結果

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在[Office 365 的 Microsoft Defender](defender-for-office-365.md)中進行[自動調查](office-365-air.md)時，在自動化調查程式期間和之後都會提供該調查的詳細資料。 如果您有必要的許可權，您可以在 Microsoft 365 安全中心中查看這些詳細資料。 調查詳細資料可提供您最新的狀態，以及核准任何擱置中動作的功能。

> [!TIP]
> 請參閱 Microsoft 365 security center 中新的整合調查頁面。 若要深入瞭解，請參閱 [ (NEW！ ) 整合調查] 頁面](../defender/m365d-autoir-results.md#new-unified-investigation-page)。

## <a name="investigation-status"></a>調查狀態

調查狀態會指出分析和動作的進度。 調查執行時，會變更狀態，以指出是否發現威脅，以及是否已核准動作。

|狀態|描述|
|:---|:---|
|**啟動中**|調查已觸發並等候開始執行。|
|**正在執行**|調查過程已開始且正在進行中。 當 [待定的動作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) 獲得批准時，也會發生此狀態。|
|**找不到威脅**|調查已完成，但找不到任何威脅 (使用者帳戶、電子郵件訊息、URL 或檔案) 皆已識別。 <p> **提示**：如果您懷疑某項尚未錯過 (例如誤報) ，您可以使用 [威脅 Explorer](threat-explorer.md)採取動作。|
|**發現威脅**|自動調查發現問題，但沒有任何特定的修正動作可解決這些問題。 <p> 發現某些類型的使用者活動時，可能會發生 **威脅已發現** 狀態，但沒有清除動作可供使用。 範例包括下列任何使用者活動： <br/>- (DLP) 事件的[資料遺失防護](../../compliance/data-loss-prevention-policies.md)<br/>-傳送反常的電子郵件<br/>-傳送惡意程式碼<br/>-傳送網路釣魚 <p> 調查發現沒有惡意的 URLs、檔案或電子郵件訊息要修正，而且沒有要修正的信箱活動，例如關閉轉移規則或委派。 <p> **提示**：如果您懷疑某項尚未錯過 (例如誤報) ，您可以使用 [威脅 Explorer](threat-explorer.md)來調查和採取動作。|
|**由系統終止**|調查已停止。 調查可能會因下列幾點原因而停止： <br/>-調查的擱置中動作已過期。 等候一周的核准，待處理的動作超時。<br/>-動作太多。 例如，如果有太多使用者點擊惡意的 URLs，它可能會超出調查的執行所有分析器的能力，所以調查會暫停。<p> **提示**：如果調查在採取動作之前暫停，請嘗試使用 [威脅瀏覽器](threat-explorer.md) 來尋找並處理威脅。|
|**擱置的動作**|調查發現威脅，例如惡意電子郵件、惡意 URL 或風險信箱設定，以及修正威脅 [等候核准](air-review-approve-pending-completed-actions.md)的動作。 <p> 當找到具有對應動作的任何威脅時，就會觸發 **擱置的動作** 狀態。 不過，擱置中的動作清單會隨著調查的執行而增加。 查看調查詳細資料以查看其他專案是否仍待完成。|
|**修復**|調查已完成，且所有修正動作都已獲核准 (會注明為完全修正) 。 <p> **附注**：核准的修復動作可能會有錯誤，導致無法採取動作。 不論是否成功完成修正動作，調查狀態不會變更。 查看調查詳細資料。|
|**部分修正**|調查產生修正動作，有些已經過核准和完成。 其他動作仍 [有待處理](air-review-approve-pending-completed-actions.md)。|
|**已失敗**|至少有一個調查分析器遇到問題，導致無法正確完成。 <p> **附注**：如果在已核准修正動作後，調查失敗，修正動作可能仍然會成功。 查看調查詳細資料。 |
|**依節流佇列**|在佇列中保存調查。 當其他調查完成時，佇列調查便會開始。 節流可協助避免服務效能不良。  <p> **提示**：擱置的動作可能會限制可執行檔新調查數目。 請務必 [核准 (或拒絕) 擱置的動作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)。|
|**由節流終止**|如果佇列中的調查保持過長，它就會停止。 <p> **提示**：您可以 [從威脅瀏覽器開始調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。|
|

## <a name="view-details-of-an-investigation"></a>檢視調查的詳細資料

1. 請移至 Microsoft 365 security center (<https://security.microsoft.com>) 並登入。
2. 在功能窗格中，選取 [ **動作中心**]。
3. 在 [ **擱置** ] 或 [歷程 **記錄** ] 索引標籤上，選取動作。 其快顯視窗隨即開啟。
4. 在彈出窗格中，選取 [ **開啟調查] 頁面**。 
5. 使用各個索引標籤深入了解調查。

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>檢視與調查相關警示的詳細資料

某些類型的警示會觸發 Microsoft 365 中的自動調查。 若要深入瞭解，請參閱 [觸發自動調查的警示原則](office-365-air.md#which-alert-policies-trigger-automated-investigations)。

1. 請移至 Microsoft 365 security center (<https://security.microsoft.com>) 並登入。
2. 在功能窗格中，選取 [ **動作中心**]。
3. 在 [ **擱置** ] 或 [歷程 **記錄** ] 索引標籤上，選取動作。 其快顯視窗隨即開啟。
4. 在彈出窗格中，選取 [ **開啟調查] 頁面**。 
5. 選取 [ **警示** ] 索引標籤，以查看與該調查相關的所有警示清單。
6. 選取清單中的專案，以開啟其彈出窗格。 您可以在這裡查看有關警示的詳細資訊。

## <a name="keep-the-following-points-in-mind"></a>請記住下列幾點

- 電子郵件計數會在調查時進行計算，當您根據基礎查詢) 開啟調查 flyouts (時，會重新計算部分計數。

- 針對 [ **電子郵件** ] 索引標籤上的電子郵件聚簇，以及在 [叢集] 浮出控制項上顯示的電子郵件數量詞，會在調查時進行計算，而且不會變更。

- 電子郵件 **的 [電子郵件] 索引** 標籤底部顯示的電子郵件計數，以及 Explorer 中所顯示之電子郵件的計數，會反映在調查的初始分析之後所收到的電子郵件。

  因此，顯示原始數量10封電子郵件的電子郵件叢集會顯示超過15個電子郵件的電子郵件清單。在調查分析階段和系統管理員檢查調查時，會有五封以上的電子郵件訊息到貨。 同樣地，舊調查可能會開始顯示比 Explorer 查詢更高的計數，因為 Microsoft Defender for Office 365 方案2中的資料會在試用7天后到期，並且在30天后取得收費授權。

  在不同的視圖中顯示計數歷史和目前的計數，都是為了指出調查時的電子郵件影響，以及目前的影響，直到執行補救的時間為止。

- 在電子郵件的內容中，您可能會在調查過程中看到大量的反常威脅曲面。 大量的事件會指出調查事件時間與較舊的時程表之間的類似電子郵件訊息中的波峰。 電子郵件流量中的波峰和某些特性 (例如，主旨和寄件者網域、內文相似性和寄件者 IP) 一般是電子郵件宣傳活動或攻擊的開始。 不過，大量、垃圾郵件和合法的電子郵件活動通常會共用這些特性。

- 大量的情況代表潛在威脅，因此與使用防病毒引擎、引爆或惡意信譽所識別的惡意程式碼或網路釣魚威脅相比，其可能會較低的危險。

- 您不需要核准每個動作。 如果您不同意建議的動作，或您的組織未選擇某些類型的動作，您可以選擇 **拒絕** 動作或完全忽略動作，不採取任何動作。

- 核准和/或拒絕所有動作可讓調查完全關閉 (狀態會變成修正) ，但保留某些動作不完全會導致調查狀態變更為部分修正狀態。

## <a name="next-steps"></a>後續步驟

- [審閱及核准擱置的動作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
