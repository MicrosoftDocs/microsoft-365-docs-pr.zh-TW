---
title: 在試驗環境中嘗試 Microsoft 365 Defender 事件回應功能，以優先順序及管理事件、設定自動調查和回應，以及使用高級搜尋
description: 嘗試 Microsoft 365 Defender 的事件回應功能，以優先處理及管理事件、自動化調查，以及在威脅偵測中使用高級搜尋。
keywords: Microsoft 365 Defender 試用版，請嘗試 Microsoft 365 Defender，評估 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室，Microsoft 365 Defender 試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c554f7bcedbdb64118639f5a455fd6f6e55daaa6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457810"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>在試驗環境中嘗試 Microsoft 365 Defender 事件回應功能

**適用於：**
- Microsoft 365 Defender

本文是使用試驗環境在 Microsoft 365 Defender 中執行事件調查和回應的程式中的[步驟 2](eval-defender-investigate-respond.md) 。 如需此程式的詳細資訊，請參閱 [概述](eval-defender-investigate-respond.md) 文章。

在執行[模擬攻擊的事件回應](eval-defender-investigate-respond-simulate-attack.md)後，以下是一些可探索的 Microsoft 365 Defender 功能：

|功能 |描述 |
|:-------|:-----|
| [設定事件優先順序](#prioritize-incidents) | 使用 [事件] 佇列的篩選和排序，判斷要解決的事件。 |
| [管理事件](#manage-incidents) | 修改 incident 屬性，以確保正確的指派、新增標記和批註，以及解決事件。 |
| [自動調查及回應](#examine-automated-investigation-and-response-with-the-action-center) | 自動調查和回應 (空氣) 功能，可協助您的安全性運作小組更有效率地處理威脅。 「行動中心」是「單一窗格的玻璃」的事件和警示工作經驗，例如核准暫止的修復動作。 |
| [進階搜捕](#advanced-hunting) | 查詢型威脅搜尋工具，可讓您主動檢查網路中的事件，並找出威脅指示器和實體。 您也可以在調查和修正事件期間使用高級搜尋。 |
||||

## <a name="prioritize-incidents"></a>設定事件優先順序

您可以從事件中取得事件佇列 **& 警示 >** Microsoft 365 Defender 入口網站 ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上的事件。 以下為範例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件佇列的範例":::

**最新的 [事件及警示**] 區段會顯示過去24小時所收到的警示和事件數目圖表。

若要檢查事件清單並排定其工作分派和調查的重要性，您可以： 

- 設定可自訂的欄 (選取 **[選擇欄**) ]，可讓您深入瞭解事件或受影響的實體的不同特性。 這可協助您作出有關分析的事件優先順序決定。

- 使用篩選以著重于特定案例或威脅。 在事件佇列上套用篩選器，可協助判斷哪些事件需要立即注意。 

從預設的事件佇列中，選取 [ **篩選** ] 以查看 **篩選** 窗格，您可以從中指定一組特定的事件。 範例如下。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件佇列之篩選窗格的範例":::

如需詳細資訊，請參閱 [優先順序事件](incident-queue.md)。

## <a name="manage-incidents"></a>管理事件

您可以從「 **管理事件** 」窗格中管理事件的事件。 以下為範例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="事件的管理事件窗格範例":::

您可以從下列專案上的 **管理事件** 連結，顯示此窗格：

- 事件佇列中事件的屬性窗格。
- 事件的 **摘要** 頁面。

您可以透過下列方式管理您的事件：

- 編輯事件名稱

  根據安全性小組的最佳作法，變更 utomatically 指派的名稱。
  
- 新增事件標籤

  新增您的安全小組用來分類事件的標記，以後可以篩選這些事件。
  
- 指派事件給您自己

  將其指派給您的使用者帳戶名稱，以後可以篩選該名稱。
  
- 解決事件

  在事件修正後關閉事件。
  
- 設定它的分類和決定

  當您解決事件時，分類並選取威脅類型。
  
- 新增註解

  根據安全性小組的最佳作法，使用備註做為進度、記事或其他資訊。 完整的批註記錄可從事件 [詳細資料] 頁面的 [ **批註和記錄** ] 選項中取得。

如需詳細資訊，請參閱 [管理事件](manage-incidents.md)。

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>使用行動中心檢查自動化調查和回應

根據您的組織設定自動化調查和回應功能的方式，修復動作會自動採取或僅在安全操作小組核准時進行。 所有動作（不論是擱置或已完成的動作）都會列在重要訊息 [中心](m365d-action-center.md)，其中會列出裝置的擱置和完成的修正動作、電子郵件 & 共同作業內容，以及在一個位置的身分識別。

以下為範例。

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Microsoft 365 Defender 的整合行動中心":::

您可以從「行動中心」選取 [擱置中的動作]，然後在彈出窗格中核准或拒絕。 以下為範例。

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="核准或拒絕動作":::

請儘快核准 (或拒絕) 擱置的動作，如此您的自動化調查才能繼續進行，並可及時完成。

如需詳細資訊，請參閱 [自動化調查和回應](m365d-autoir.md) 及 [行動中心](m365d-action-center.md)。

## <a name="advanced-hunting"></a>進階搜捕

> [!NOTE]
> 在我們逐步執行高級搜尋類比之前，請觀看下列影片，瞭解高級搜尋概念，查看在入口網站中的位置，並瞭解如何協助您進行安全性運作。

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


如果 [選用的 fileless PowerShell 攻擊模擬](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) 已到達認證存取階段，您可以在調查中的任何一點使用高級搜尋，以主動從所產生的提醒及受影響的實體中，使用您已知道的事件及記錄來搜尋網路中的事件及記錄。 例如，您可以查詢過去30天內任何與外部 IP 位址的連線。

### <a name="hunting-environment-requirements"></a>搜尋環境需求

這種模擬需要單一內部信箱和裝置。 您也需要外部電子郵件帳戶來傳送測試郵件。

1. 確認您的承租人已[啟用 Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on)。
2. 識別要用於接收電子郵件的目標信箱。

   - 此信箱必須由 Microsoft Defender 監控 Office 365

   - 要求3裝置必須存取此信箱

3. 設定測試裝置：

    a. 請確認您使用的是 Windows 10 版本1903或更新版本。

    b. 將測試裝置加入測試網域。

    c. [開啟 Windows Defender 防毒軟體](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 如果您無法啟用 Windows Defender 防毒軟體，請參閱[此疑難排解主題](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。

    d. [在 Microsoft Defender For Endpoint 上的板載](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。

### <a name="run-the-simulation"></a>執行模擬

1. 從外部電子郵件帳戶，將電子郵件傳送至「搜尋環境需求」區段之步驟2中所識別的信箱。 包含可透過任何現有電子郵件篩選原則所允許的附件。 此檔案不需要是惡意或可執行檔。 建議的檔案類型為<i>.pdf</i>、 <i>.exe</i> (如允許) 或 Office 檔案類型（如 Word 檔案）。

2. 從「搜尋環境需求」一節的步驟3中所設定的裝置，開啟已傳送的電子郵件。 開啟附件或將檔儲存到裝置。

#### <a name="go-hunting"></a>開始搜尋

1. 開啟[Microsoft 365 Defender 入口網站](https://security.microsoft.com/)。

2. 從功能窗格中，選取 [ **搜尋] > [高級搜尋**]。

3. 建立以收集電子郵件事件開始的查詢。

   1. 選取 [ **查詢 > 新增**]。

   1. 在 [**高級搜尋**] 底下的 **電子郵件** 群組中，按兩下 [ **EmailEvents**]。 您應該會在 [查詢] 視窗中看到這種情況。

      ```console
      EmailEvents
      ```

   1. 將查詢的時間範圍變更為過去24小時。 假設您在執行上述類比時所傳送的電子郵件是在過去24小時內，否則請視需要變更時間範圍。

   1. 選取 [ **執行查詢**]。 您可能會有不同的結果，視您的試驗環境而定。

      > [!NOTE]
      > 請參閱下一個步驟，篩選選項以限制資料傳回。

      ![高級搜尋查詢結果的範例](../../media/mtp/fig19.png)

        > [!NOTE]
        > 「高級搜尋」會以表格式資料顯示查詢結果。 您也可以選擇以其他格式類型（如圖表）來查看資料。

   1. 查看結果，查看是否可以識別您開啟的電子郵件。 最多可能需要兩個小時的時間，郵件才會顯示在高級搜尋中。 若要縮小結果，您可以將 **where** 條件新增至您的查詢，只會尋找「yahoo.com」為其 SenderMailFromDomain 的電子郵件。 範例如下。

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. 按一下查詢中產生的資料列，以便檢查記錄。

      ![選取高級搜尋結果時所開啟之檢查記錄側面面板的範例](../../media/mtp/fig21.png)

4. 現在，您已確認您可以看到電子郵件，新增附件的篩選器。 在環境中著重于所有包含附件的電子郵件。 針對這種模擬，請將焦點放在輸入電子郵件，而不是從您的環境寄出。 移除您已新增的任何篩選，以找出郵件並新增 "|其中 **AttachmentCount > 0** 和 **EmailDirection**  ==  **"Inbound" "**

   下列查詢會顯示結果，其清單比您的所有電子郵件事件的初始查詢更短：

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. 接下來，包含附件的相關資訊 (例如：檔案名、雜湊) 結果集。 若要這麼做，請加入 **EmailAttachmentInfo** 表格。 在此情況下，要用於加入的一般欄位是 **NetworkMessageId** 和 **RecipientObjectId**。

   下列查詢也包含其他行 "| **project-Rename EmailTimestamp = Timestamp**"，可協助識別與您將在下一個步驟中新增之檔案動作相關的電子郵件與時間戳記有關的時間戳記。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. 接下來，使用 **EmailAttachmentInfo** 表格中的 **SHA256** 值，尋找在該雜湊的端點) 上發生的 **DeviceFileEvents** (檔案動作。 這裡的一般欄位將會是附件的 SHA256 雜湊。

   產生的表格現在包含端點 (Microsoft Defender for Endpoint) （例如裝置名稱）、已完成的動作 (在此情況下，篩選為只包括 FileCreated 事件) ，以及儲存檔案的位置。 也會包含與處理常式相關聯的帳戶名稱。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   您現在已經建立了一個查詢，它會識別所有使用者開啟或儲存附件的輸入電子郵件。 您也可以精煉此查詢，以篩選特定寄件者網域、檔案大小、檔案類型等等。

7. 函數是一種特殊的聯接方式，可讓您將更多的 TI 資料（如其流行、簽署者資訊等等）提取到更多的檔。若要取得檔案的詳細資料，請使用 **FileProfile ()** 函數豐富：

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>建立偵測

當您建立一個查詢，識別您想要針對未來的情況收到 **警示** 的資訊時，您可以從查詢建立自訂偵測。

自訂偵測會根據您設定的頻率執行查詢，而查詢的結果會根據您所選擇的受影響資產，建立安全性警示。 這些警示會與事件相關聯，而且可以被會審為其中一項產品所產生的任何其他安全性警示。

1. 在 [查詢] 頁面上，移除 [前往搜尋指示] 的步驟7中所新增的行7和8，然後按一下 [ **建立偵測規則**]。

   ![在 [高級搜尋] 頁面中，您可以按一下 [建立偵測規則] 的範例](../../media/mtp/fig22.png)

   > [!NOTE]
   > 如果您按一下 [ **建立偵測規則** ]，並在查詢中有語法錯誤，則您的偵測規則不會儲存。 請加倍檢查您的查詢，確定沒有任何錯誤。

2. 請填入必要的欄位，其中包含可讓安全性小組瞭解提醒的資訊、它的產生原因，以及您預期採取的動作。

   ![[建立偵測規則] 頁面的範例，您可以在其中定義警示詳細資料。](../../media/mtp/fig23.png)

   請務必以清晰的方式填寫欄位，以協助下一使用者對此偵測規則警示作出明智的決定。

3. 選取此警示會影響哪些實體。 在此情況下，請選取 [ **裝置** 和 **信箱**]。

   ![[建立偵測規則] 頁面的範例，您可以在其中選擇受影響實體的參數](../../media/mtp/fig24.png)

4. 決定觸發警示時應執行的動作。 在此情況下，請執行防病毒掃描，但可以採取其他動作。

   ![[建立偵測規則] 頁面範例，您可以在觸發警示時執行防病毒掃描，以協助解決威脅](../../media/mtp/fig25.png)

5. 選取警示規則的範圍。 因為此查詢涉及裝置，所以裝置群組會在此自訂偵測中與 Microsoft Defender for Endpoint coNtext 相關。 當您建立未包括裝置作為受影響實體的自訂偵測時，不適用範圍。

   ![[建立偵測規則] 頁面的範例，您可以在其中設定警示規則的範圍，以管理您將看到的結果預期](../../media/mtp/fig26.png)

   在此試驗中，您可能會想要將此規則限制在實際執行環境中的測試裝置子集。

6. 選取 [建立 **]**。 然後，選取導覽窗格中的 **自訂偵測規則** 。

   ![功能表中的自訂偵測規則選項範例](../../media/mtp/fig27a.png)

   ![顯示規則和執行詳細資料的偵測規則頁面範例](../../media/mtp/fig27b.png)

   在此頁面中，您可以選取將會開啟詳細資料頁面的偵測規則。

   ![[電子郵件附件] 頁面的範例，您可以在其中看到規則執行、觸發的警示和動作狀態、編輯偵測等](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a>高級搜尋的專家訓練

**追蹤敵人** 是新安全性分析師和經驗豐富威脅 hunters 的網路廣播系列。 它會引導您完成「高級搜尋」的基本概念，以建立您自己的複雜查詢。 

請參閱 [取得高級搜尋上的專家訓練](advanced-hunting-expert-training.md) ，以開始著手。

### <a name="navigation-you-may-need"></a>您可能需要的導覽

[建立 Microsoft 365 Defender 評估環境](eval-create-eval-environment.md)
