---
title: 在 Microsoft 365 中查看自動調查的結果
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在 Microsoft 365 中的自動調查期間和之後，您可以查看結果和重要結果。
ms.date: 11/05/2020
ms.openlocfilehash: 2018f008e043f36cd41047185f305209fcb725d7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615141"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Microsoft 365 中自動調查的詳細資料和結果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在[Office 365 的 Microsoft Defender](office-365-atp.md)中進行[自動調查](office-365-air.md)時，在自動化調查程式期間和之後都會提供該調查的詳細資料。 如果您有必要的許可權，您可以在 Microsoft 365 安全中心中查看這些詳細資料。 調查詳細資料可提供您最新的狀態，以及核准任何擱置中動作的功能。

## <a name="investigation-status"></a>調查狀態

調查狀態會指出分析和動作的進度。 調查執行時，會變更狀態，以指出是否發現威脅，以及是否已核准動作。

|狀態|描述|
|---|---|
|**啟動中**|調查已觸發並等候開始執行。|
|**正在執行**|調查過程已開始且正在進行中。 當 [待定的動作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) 獲得批准時，也會發生此狀態。|
|**找不到威脅**|調查已完成，但找不到任何威脅 (使用者帳戶、電子郵件訊息、URL 或檔案) 皆已識別。 <p> **提示**：如果您懷疑某項尚未錯過 (例如誤報) ，您可以使用 [威脅 Explorer](threat-explorer.md)採取動作。|
|**發現威脅**|自動調查發現問題，但沒有任何特定的修正動作可解決這些問題。 <p> 發現某些類型的使用者活動時，可能會發生 **威脅已發現** 狀態，但沒有清除動作可供使用。 範例包括下列任何使用者活動： <ul><li>DLP) 事件的 [資料遺失防護](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (</li><li>傳送異常的電子郵件</li><li>傳送惡意程式碼</li><li>傳送網路釣魚</li></ul> <p> 調查發現沒有惡意的 URLs、檔案或電子郵件訊息要修正，而且沒有要修正的信箱活動，例如關閉轉移規則或委派。 <p> **提示**：如果您懷疑某項尚未錯過 (例如誤報) ，您可以使用 [威脅 Explorer](threat-explorer.md)來調查和採取動作。|
|**由系統終止**|調查已停止。 調查可能會因下列幾點原因而停止： <ul><li>調查的擱置中動作已過期。 等候一周的核准，待處理的動作超時。</li><li>動作太多。 例如，如果有太多使用者點擊惡意的 URLs，它可能會超出調查的執行所有分析器的能力，所以調查會暫停。</li></ul> <p> **提示**：如果調查在採取動作之前暫停，請嘗試使用 [威脅瀏覽器](threat-explorer.md) 來尋找並處理威脅。|
|**擱置的動作**|調查發現威脅，例如惡意電子郵件、惡意 URL 或風險信箱設定，以及修正威脅 [等候核准](air-review-approve-pending-completed-actions.md)的動作。 <p> 當找到具有對應動作的任何威脅時，就會觸發 **擱置的動作** 狀態。 不過，擱置中的動作清單會隨著調查的執行而增加。 檢查 [調查記錄](#playbook-log) 檔，查看是否有其他專案仍待完成。|
|**修復**|調查已完成且所有修正動作都已獲批准 (此) 會以完全補救的加以說明。 <p> **附注**：核准的修復動作可能會有錯誤，導致無法採取動作。 不論是否成功完成修正動作，調查狀態不會變更。 檢查 [調查記錄](#playbook-log) 檔中的詳細結果。|
|**部分修正**|調查產生修正動作，有些已經過核准和完成。 其他動作仍 [有待處理](air-review-approve-pending-completed-actions.md)。|
|**已失敗**|至少有一個調查分析器遇到問題，導致無法正確完成。 <p> **附注**：如果在已核准修正動作後，調查失敗，修正動作可能仍然會成功。 檢查 [調查記錄](#playbook-log) 檔中的詳細結果。|
|**依節流佇列**|在佇列中保存調查。 當其他調查完成時，佇列調查便會開始。 節流可協助避免服務效能不良。  <p> **提示**：擱置的動作可能會限制可執行檔新調查數目。 請務必 [核准 (或拒絕) 擱置的動作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)。|
|**由節流終止**|如果佇列中的調查保持過長，它就會停止。 <p> **提示**：您可以 [從威脅瀏覽器開始調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。|
|

## <a name="view-details-of-an-investigation"></a>檢視調查的詳細資料

1. 請移至安全性 & 規範中心 (<https://protection.office.com>) 並登入。

2. 請執行下列其中一個動作：

    - 移至 [ **威脅管理**] \> **儀表板**。 這樣會帶您前往[安全性儀表板](security-dashboard.md)。 您的 AIR 小工具會顯示在[安全性儀表板](security-dashboard.md)上方。 選取小工具，例如 **調查摘要**。

    - 移至 **威脅管理** \> **調查**。

    這兩種方法都會帶您前往調查清單。

    ![AIR 的主要調查頁面](../../media/air-maininvestigationpage.png)

3. 在調查清單中，選取 [識別碼] 欄中的項目。 這樣會開啟調查詳細資料頁面，從檢視中的調查圖形開始。

    ![AIR 調查圖形頁面](../../media/air-investigationgraphpage.png)

   使用各個索引標籤深入了解調查。

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>檢視與調查相關警示的詳細資料

某些類型的警示會觸發 Microsoft 365 中的自動調查。 若要深入瞭解，請參閱 [觸發自動調查的警示原則](office-365-air.md#which-alert-policies-trigger-automated-investigations)。

使用下列程序來檢視與自動化調查相關聯警示的詳細資料。

1. 請移至安全性 & 規範中心 (<https://protection.office.com>) 並登入。

2. 移至 **威脅管理** \> **調查**。

3. 在調查清單中，選取 [識別碼] 欄中的項目。

4. 開啟調查詳細資料時，選取 [警示] 索引標籤。觸發調查的任何警示都會列在此處。

5. 選取清單中的項目。 隨即開啟一個飛出視窗，其中包含警示的詳細資料以及其他資訊和動作的連結。

6. 檢閱飛出視窗中的資訊，並視特定警示採取動作，例如 **解決**、**隱藏**，或 **通知使用者**。

    - **解決** 等同於關閉警示

    - **隱藏** 會導致原則在指定時段不觸發警示

    - **通知使用者** 會啟動電子郵件，並且已輸入使用者的電子郵件地址，讓您的安全性操作小組輸入要給這些使用者的訊息。 (這類似於使用[威脅總管](threat-explorer.md)將訊息傳送給收件者。)

## <a name="how-to-use-the-various-tabs"></a>如何使用各種選項卡

下列各節會逐步引導您完成「自動化調查」頁面上的各項索引標籤，以及如何使用此資訊。

### <a name="automated-investigations-page"></a>自動調查頁面

「自動調查」頁面會顯示您組織的調查及其目前狀態。

![AIR 的主要調查頁面](../../media/air-maininvestigationpage.png)

您可以：

- 直接流覽至調查 (選取 **調查識別碼**) 。

- 套用篩選器。 您可以選擇 **調查類型**、 **時間範圍**、 **狀態** 或兩者的組合。

- 將資料匯出至 .csv 檔案。

### <a name="investigation-graph"></a>調查圖表

當您開啟特定調查時，您會看到 [調查圖形] 頁面。 此頁面會顯示所有不同的實體：電子郵件、使用者 (和其活動) ，以及在觸發的警示中自動調查的裝置。

![AIR 調查圖形頁面](../../media/air-investigationgraphpage.png)

您可以：

- 取得目前調查的視覺效果。
- 查看調查週期的摘要。
- 選取視覺化效果中的節點，以查看該節點的詳細資料。
- 選取頂端的索引標籤，以查看該索引標籤的詳細資料。

### <a name="alert-investigation"></a>警示調查

在調查的 [ **提醒** ] 索引標籤上，您可以看到與調查相關的警示。 詳細資料包括觸發調查的警示，以及與調查相關的其他相關警示（如危險登入、 [DLP 原則](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) 違規等等）。 在此頁面中，安全性分析員也可以查看個別警示的其他詳細資料。

![空氣提醒頁面](../../media/air-investigationalertspage.png)

您可以：

- 取得目前觸發警示及任何相關警示的視覺效果。
- 在清單中選取警示，以開啟顯示完整警示詳細資料的飛出頁面。

### <a name="email-investigation"></a>電子郵件調查

在調查的 [ **電子郵件** ] 索引標籤上，您可以看到原始的電子郵件，以及視為調查之一部分之類似電子郵件的聚簇。 [ **電子郵件** ] 索引標籤也會顯示與調查相關的電子郵件專案，例如使用者報告的電子郵件詳細資料、報告的原始電子郵件、電子郵件訊息 (s) zapped 由於惡意程式碼/網路釣魚等等。

![航空電子郵件調查頁面](../../media/air-investigationemailpage.png)

透過電子郵件調查，您可以：

- 取得目前的聚簇結果及發現威脅的視覺概況。
- 按一下 [叢集] 實體或威脅清單，開啟顯示完整警示詳細資料的飛出頁面。
- 按一下 [**電子郵件群集詳細資料**] 索引標籤頂端的 [**在資源管理器中開啟**] 連結，進一步調查電子郵件叢集。

![使用飛出詳細資料的航空調查電子郵件](../../media/air-investigationemailpageflyoutdetails.png)

針對組織中的使用者傳送及接收的大量電子郵件，以及電子郵件通訊和攻擊的多使用者性質，下列程式可能需要一段時間：

1. 根據來自郵件頭、內文、URL 及附件的類似屬性來聚簇電子郵件訊息。
2. 將惡意電子郵件與良好的電子郵件分開。
3. 對惡意電子郵件採取動作。

AIR 自動化此程式，儲存組織的安全性小組時間和精力。

#### <a name="types-of-email-clusters"></a>電子郵件聚簇類型

電子郵件分析步驟期間可識別三種不同類型的電子郵件簇：相似性群集 (所有調查) 、指示器叢集 (所有調查) ，以及信箱/使用者群組。 下表說明這些類型的電子郵件聚簇。

|電子郵件叢集|描述|
|---|---|
|相似性聚簇|搜尋使用類似寄件者和內容屬性的電子郵件所識別的電子郵件訊息。 根據原始的偵測結果，這些聚簇會針對惡意內容進行評估。 包含足夠惡意電子郵件偵測的電子郵件群集被視為惡意電子郵件。|
|指示器聚簇|搜尋來自原始電子郵件的相同指示器實體 (檔案雜湊或 URL) 所識別的電子郵件訊息。 當原始檔案/URL 實體識別為惡意時，AIR 會將指示器結論套用到包含該實體的完整電子郵件。 識別為惡意程式碼的檔案，表示包含該檔案的電子郵件叢集會被視為惡意程式碼電子郵件訊息。|
|信箱/使用者群組|與使用者受損調查相關之使用者的電子郵件訊息。 這些電子郵件群集可供安全性作業小組進一步分析，而且不會產生電子郵件修復動作。 <p> 「已遭破壞的使用者安全性行動手冊」會檢查所進行分析之使用者所傳送的電子郵件，以便了解從信箱傳送之電子郵件的潛在影響。|

> [!NOTE]
> 聚簇的目標是尋找及尋找其他相關的電子郵件訊息，這些郵件是由同一個寄件者在攻擊或活動中所傳送。  在某些情況下，合法的電子郵件可能會觸發調查 (例如，使用者報告行銷電子郵件) 。  在這些案例中，電子郵件叢集應識別電子郵件群集是否不是惡意的-當有適當的情況時，它不會指出威脅，也 **不** 會建議移除電子郵件。

#### <a name="email-classifications"></a>電子郵件分類

在分析電子郵件訊息時，會將它們分類為 *惡意*、 *可疑* 或 *clean* (，但 *不是識別為威脅*) ：

- 從信箱/使用者送出的 *惡意電子郵件* 指出可能會危及信箱/帳戶。 會顯示其他可能會受到惡意電子郵件影響之部分遭到破壞的使用者/信箱。

- 信箱/使用者所傳送的 *可疑電子郵件* 指出可能發生遭破壞的帳戶或不需要的電子郵件活動。 這些郵件包括從信箱傳送的任何垃圾郵件/大宗郵件。

- *清理電子郵件* (視為不是由信箱/使用者傳送的威脅) 電子郵件，可讓您的安全性運作小組透過已傳送的合法使用者電子郵件進行查看。 不過，如果電子郵件帳戶遭到損害，這些電子郵件也會包含資料 exfiltration。

#### <a name="more-about-email-counts"></a>有關電子郵件計數的詳細資訊

在 [電子郵件] 索引標籤上所識別的電子郵件計數目前代表 [ **電子郵件** ] 索引標籤上顯示的所有電子郵件的總計。由於電子郵件訊息存在於多個聚簇中，因此所識別之電子郵件的實際總計數 (，並受修正動作影響) 是出現在所有聚簇和原始收件者的電子郵件中的唯一電子郵件計數。

根據每個收件者， [Explorer](threat-explorer.md) 和 AIR 電子郵件都是以每個收件者為基礎，因為安全性 verdicts、動作和傳遞位置會因每個收件者而異。 因此，傳送給三位使用者的原始電子郵件會算作三個電子郵件的總數，而不是一封電子郵件。

在某些情況下，電子郵件會被計算兩次以上的時間，例如當電子郵件有多個動作時，或當所有動作都發生時，有多個電子郵件副本。

例如，在傳遞時偵測到的惡意程式碼電子郵件可能會造成封鎖的 (隔離) 電子郵件，以及取代的電子郵件 (威脅檔案，以警告檔取代，然後傳遞至使用者的信箱) 。 因為系統中的電子郵件有逐字的兩個複本，所以兩者都可能會計入簇計數。

> [!IMPORTANT]
> 以下是一些需要謹記的要點：
>
> - 電子郵件計數會在調查時進行計算，當您根據基礎查詢) 開啟調查 flyouts (時，會重新計算部分計數。
>
> - 針對 [ **電子郵件** ] 索引標籤上的電子郵件聚簇，以及在 [叢集] 浮出控制項上顯示的電子郵件數量詞，會在調查時進行計算，而且不會變更。
>
> - 電子郵件 **的 [電子郵件] 索引** 標籤底部顯示的電子郵件計數，以及 Explorer 中所顯示之電子郵件的計數，會反映在調查的初始分析之後所收到的電子郵件。

因此，顯示原始數量10封電子郵件的電子郵件叢集會顯示超過15個電子郵件的電子郵件清單。在調查分析階段和系統管理員檢查調查時，會有五封以上的電子郵件訊息到貨。 同樣地，舊調查可能會開始顯示比 Explorer 查詢更高的計數，因為 Microsoft Defender for Office 365 方案2中的資料會在試用7天后到期，並且在30天后取得收費授權。

在不同的視圖中顯示計數歷史和目前的計數，都是為了指出調查時的電子郵件影響，以及目前的影響，直到執行補救的時間為止。

> [!NOTE]
> 在電子郵件的內容中，您可能會在調查過程中看到大量的反常威脅曲面。 大量的事件會指出調查事件時間與較舊的時程表之間的類似電子郵件訊息中的波峰。 這種具有類似特性的電子郵件流量的此峰值 (例如，主旨和寄件者網域、內文相似性和寄件者 IP) 通常是電子郵件宣傳活動或攻擊的開始。
> 不過，大量、垃圾郵件和合法的電子郵件活動通常會共用這些特性。
>
> 大量的情況代表潛在威脅，而且與使用防病毒引擎、引爆或惡意信譽所識別的惡意程式碼或網路釣魚威脅相比，其可能會較低的危險。

### <a name="user-investigation"></a>使用者調查

在 [ **使用者** ] 索引標籤上，您可以看到所有識別為調查之一部分的使用者。 當發生事件時，使用者帳戶會出現在調查中，或指出這些使用者帳戶可能受到影響或遭到破壞。

例如，在下圖中，AIR 會根據所建立的新收件匣規則，識別出損等損等現象。  (調查的證據) 的其他詳細資料，可透過此索引標籤內的詳細視圖取得。損壞和異常的指示也可能包括來自 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)的反常偵測。

![AIR 調查使用者頁面](../../media/air-investigationuserspage.png)

您可以：

- 深入瞭解已識別的使用者結果和找到的風險。

- 選取使用者開啟彈出頁面，顯示完整的提醒詳細資料。

### <a name="machine-investigation"></a>機器調查

在 [ **機器** ] 索引標籤上，您可以看到識別為調查一部分的所有機器。

![AIR 調查電腦頁面](../../media/air-investigationmachinepage.png)

在某些行動行動中，AIR 會將電子郵件威脅與裝置相關聯 (例如，Zapped 惡意程式碼) 。 例如，調查會將惡意檔雜湊傳遞至 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) 以進行調查。 這可讓您針對使用者自動調查相關的機器，以協助確保雲端和您的端點都有解決威脅。

您可以：

- 取得目前的電腦及發現威脅的視覺概況。

- 選取機器以開啟 Microsoft Defender Security Center 中相關 [Microsoft defender For Endpoint 調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 的視圖。

### <a name="entity-investigation"></a>實體調查

在 [ **實體** ] 索引標籤上，您可以看到在調查中識別及分析的實體。

在這裡，您可以查看已調查的實體和實體類型的詳細資料，例如電子郵件訊息、叢集、IP 位址、使用者等等。 您也可以查看已分析的實體數量，以及與每個實體相關聯的威脅。

![AIR 調查實體頁面](../../media/air-investigationentitiespage.png)

您可以：

- 取得所找到之調查實體和威脅的視覺效果。

- 選取實體以開啟顯示相關實體詳細資料的飛出頁面。

![空中調查實體詳細資料](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>行動手冊記錄

在 [ **記錄** ] 索引標籤上，您可以看到在調查過程中所發生的所有操作手冊步驟。 記錄檔會捕獲 Office 365 自動調查功能所完成之所有 analyzer 和動作的完整清查，做為空氣的一部分。 它提供所有採取步驟的清晰視圖，包括動作本身、描述，以及實際從開始到完成的持續時間。

![航空調查記錄頁面](../../media/air-investigationlogpage.png)

您可以：

- 請參閱行動手冊步驟的視覺概況。
- 將結果匯出至 CSV 檔案。
- 篩選視圖。

### <a name="recommended-actions"></a>建議的動作

在 [ **動作** ] 索引標籤上，您可以看到在調查完成之後，修正建議的所有行動手冊動作。 動作會捕獲 Microsoft 建議您在調查結束時採取的步驟。 您可以選取一或多個動作來採取補救措施。

選取 [ **核准** ] 允許開始修復。 需要 (適當的許可權-從 Explorer 和 AIR) 中執行動作時，必須要有 **搜尋和清除** 角色。

例如，安全性讀者可以查看動作，但不能核准。

> [!IMPORTANT]
> 您不需要核准每個動作。 如果您不同意建議的動作，或您的組織未選擇某些類型的動作，您可以選擇 **拒絕** 動作或完全忽略動作，不採取任何動作。
> 核准和/或拒絕所有動作可讓調查完全關閉 (狀態會變成修正) ，但保留某些動作不完全會導致調查狀態變更為部分修正狀態。

![AIR 調查動作頁面](../../media/air-investigationactionspage.png)

您可以：

- 取得行動手冊-建議動作的視覺效果。
- 選取一個或多個動作。
- 使用批註核准或拒絕建議的動作。
- 將結果匯出至 CSV 檔案。
- 篩選視圖。

## <a name="next-steps"></a>後續步驟

- [審閱及核准擱置的動作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
