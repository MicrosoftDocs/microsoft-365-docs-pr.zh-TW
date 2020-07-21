---
title: 有問必答風險管理原則
description: 深入瞭解 Microsoft 365 中的內幕人士風險管理原則
keywords: Microsoft 365, 測試人員風險管理, 風險管理, 合規性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: a08d07f574c1cd5463772c803be0d4b3850144f4
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199534"
---
# <a name="insider-risk-management-policies"></a>有問必答風險管理原則

有問必答風險管理原則決定哪些使用者屬於範圍，以及已針對警示設定哪些類型的風險指示器。 您可以快速建立套用至組織中所有使用者的原則，或定義個別使用者或群組以進行原則管理。 原則支援內容優先順序，以在多重或特定 Microsoft 團隊上聚焦原則條件，SharePoint 網站、資料敏感度類型及資料標籤。 使用範本，您可以選取特定風險指示器，並自訂原則指標的事件臨界值，有效地自訂風險的分數和等級及警示頻率。 此外，風險分數 boosters 和反常狀況的偵測可協助識別高重要性或更不尋常的使用者活動。 原則 windows 可讓您定義將原則套用至警示活動的時間範圍，以及在啟動時用來判斷原則的持續時間。

## <a name="policy-dashboard"></a>原則儀表板

**原則儀表板**可讓您快速查看組織中的原則，以及與每個原則相關聯之警示的目前狀態。

- **原則名稱**：指派給原則嚮導中之原則的名稱。
- **主動警示**：每個原則的作用中警示數目。
- 已**確認的警示**：過去365天內從原則產生案例的警示總數。
- **對提醒採取的動作**：過去365天內已確認或已解除的警示總數。
- **原則有效性**：已確認的警示總數取決於對警示所進行的動作總數（即過去一年已確認或已消除的警示總數）。
- **Active**：案例的狀態為 *[是]* 或 [*否*]。

![測試人員風險管理原則儀表板](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>原則範本

「內幕風險管理範本」是預先定義的原則條件，可定義原則所使用的風險指示器和風險計分模型類型。 在建立原則之前，每個原則都必須在 [原則建立] 嚮導中指派範本。 有問必答風險管理最多可支援五個原則範本的原則。 當您使用原則嚮導建立新的內幕使用者風險原則時，您可以選擇下列其中一個原則範本：

### <a name="data-theft-by-departing-users"></a>由去聲使用者竊取資料

當使用者離開您的組織時，使用者通常會有與資料竊取相關的特定風險指示器。 這個原則範本使用指示器來表示風險計分，並將重點偵測和警示通知給此風險區域。 用於去聲使用者的資料竊取可能包括從 SharePoint 線上下載檔案、列印檔案，以及將資料複製到員工辭職和結束日期附近的個人雲端訊息和儲存服務。 這個範本會對與這些活動相關的風險指示器以及其與使用者雇傭狀態的關聯性開始計分。

>[!IMPORTANT]
>使用此範本時，您必須設定 Microsoft 365 HR connector，定期為組織中的使用者匯入辭職及終止日期資訊。 如需為組織設定 Microsoft 365 HR connector 的逐步指引，請參閱[Import data WITH HR connector](import-hr-data.md)文章。

### <a name="general-data-leaks"></a>一般資料洩漏

保護資料和防止資料洩漏是大多陣列織面臨的挑戰，尤其是使用者、裝置及服務建立的新資料的快速成長。 使用者可在服務和裝置間建立、儲存及共用資訊，使管理資料洩漏變得越來越複雜和困難。 資料洩漏可能包括意外 oversharing 組織外部的資訊，或惡意目的資料竊取。 在與指派的資料遺失防護（DLP）原則一起使用時，此範本會從即時偵測至可疑的 SharePoint 線上資料下載、檔案和資料夾共用、列印檔案，以及將資料複製到個人雲端郵件和儲存服務。

使用**資料洩漏**範本時，您必須指派 DLP 原則，以針對組織中的高嚴重性警示，在內幕風險原則中觸發指示器。 當 DLP 原則規則所產生的高嚴重性警示新增至 Office 365 審核記錄檔時，使用此範本所建立的會員風險原則，會自動檢查高嚴重性的 DLP 警示。 如果警示包含內部使用者風險原則中所定義的範圍內使用者，則此警示會由內幕使用者風險原則處理為新的警示，並指派給內部使用者風險嚴重性和風險分數。 這個原則可讓您在內容中評估此警示，與案例中包含的其他活動。

#### <a name="data-leaks-policy-guidelines"></a>資料洩漏原則指導方針

在建立或修改 DLP 原則以用於「內幕風險管理原則」時，請考慮下列指導方針：

- 當您設定 DLP 原則中的規則時，在指派**附隨報告**設定為 [*高*] 時，設定資料 exfiltration 事件的優先順序並加以選擇性。 例如，電子郵件敏感檔至已知的競爭對手應該是*高*警示等級 exfiltration 事件。 在其他 DLP 原則規則的 [**附隨報告**] 中，以 [高] 指派*高*層次，可增加「內幕風險管理」提醒工作流程中的噪音，並使資料調查人員和分析員更難於正確評估這些警示。 例如，指派*高*警示等級來存取 DLP 原則中的 [拒絕] 活動，可使評估真正危險的使用者行為和活動變得更困難。
- 請確定您瞭解並正確設定 DLP 和有問必答風險管理原則中的範圍內使用者。 只有在使用**資料洩漏**範本的情況中，定義為內部的內幕風險管理原則的使用者，才能處理高嚴重性原則警示。 此外，在高嚴重性的 DLP 警示中，只有定義為內部範圍的使用者，才能考慮使用「內幕風險管理」原則。 您不會以衝突的方式，在您的 DLP 和內幕郵件原則原則中，無意設定範圍內的使用者，這一點很重要。

     例如，如果您的 DLP 原則規則的適用範圍只是 Sales 小組的使用者，而從**資料洩漏**範本所建立的有問必答風險原則，已將所有使用者定義為範圍內，則「內部使用者風險原則」只會對 Sales 小組的使用者實際處理高嚴重性的 DLP 警示。 內幕郵件原則不會收到任何高優先順序 DLP 警示，供使用者在此範例中未定義的 DLP 規則中進行處理。 相反地，如果您從**資料洩漏**範本所建立的會員風險管理原則僅限銷售小組的使用者，且指派的 DLP 原則的範圍限定為所有使用者，則「有問必答風險原則」只會處理 sales 團隊成員的高嚴重性 DLP 警示。 「內部使用者風險管理」原則會忽視所有不在 Sales 團隊之使用者的高嚴重性 DLP 警示。

- 請確定針對此內部人員風險管理範本使用的 DLP 原則中的 [**附隨報告**] 規則設定設定*高*嚴重性等級警示。 *高*嚴重性層級是不會從 DLP 原則中的規則產生觸發事件和內部的風險管理提醒，其 [**附隨報告**] 欄位設定為 [*低*] 或「*中*」。

    ![DLP 原則警示設定](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >使用內建範本建立新的 DLP 原則時，您需要選取 [**建立或自訂 ADVANCED DLP 規則**] 選項，才能設定*高*嚴重性層級的「**附隨報告**」設定。

從**資料洩漏**範本所建立的每個內幕人士風險管理原則，只能有一個指派的 DLP 原則。 請考慮建立專用的 DLP 原則，將您要偵測的不同活動和作用中的事件，當作使用**資料洩漏**範本的有問必答風險原則的觸發事件。

如需為貴組織設定 DLP 原則的逐步指示，請參閱[建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)主題。

### <a name="data-leaks-by-priority-users-preview"></a>依優先順序的使用者資料洩漏（預覽）

保護資料和防止組織中使用者的資料洩漏可能取決於其位置、機密資訊的存取層級，或風險歷程記錄。 資料洩漏可能包括意外 oversharing 組織外部的高敏感度資訊，或有惡意目的的資料竊取。 在與指派的資料遺失防護（DLP）原則一起使用時，此範本會開始計分可疑活動的即時偵測，並產生具有較高嚴重性層級的有問必答風險警示和警示的增加可能性。 優先順序使用者是在「內幕風險管理設定」區域中設定的優先順序使用者群組中定義。 新增連結

就像**一般資料洩漏範本**一樣，您必須指派 DLP 原則，以在組織中高嚴重性警示的內幕風險原則中觸發指示器。 使用此範本建立原則時，請遵循上述資料洩漏原則指導方針。 此外，您必須將「內部使用者群組」原則**管理**  >  **設定**  >  **優先順序使用者群組**中所建立的優先順序使用者群組指派給原則。

### <a name="data-leaks-by-disgruntled-users-preview"></a>因不滿使用者的資料洩漏（預覽）

當使用者遇到雇用 stressors 時，可能會因不滿而導致「內幕風險」活動的機率增加。 在識別與 disgruntlement 相關聯的指示器時，此範本會開始計分使用者活動。 範例包括效能改進通知、效能檢查不良或工作層級狀態的變更。 不滿的使用者可能會包含從 SharePoint 線上下載檔案，並將資料複製到員工 stressor 事件附近的個人雲端訊息和儲存服務。

使用此範本時，您也必須設定 Microsoft 365 HR 連接器，以定期匯入效能改進通知、不良效能檢查狀態，或組織中使用者的工作層級變更資訊。 如需為組織設定 Microsoft 365 HR connector 的逐步指引，請參閱[Import data WITH HR connector](import-hr-data.md)文章。

### <a name="general-security-policy-violations-preview"></a>一般安全性原則違規（預覽）

在許多組織中，使用者有權在其裝置上安裝軟體或修改裝置設定，以協助其工作。 不管是無意或惡意的目的，使用者可能會安裝惡意程式碼或停用重要的安全性功能，以協助保護其裝置或網路資源上的資訊。 這個原則範本使用 Microsoft Defender 高級威脅防護（ATP）的安全性警示，以開始計分這些活動，並將此風險區域的功能重點放在偵測和警示。 當使用者可能會有可能是「有問必答」風險的安全性原則違規記錄時，請使用此範本為案例中的安全性原則違規提供洞察力。

您需要在您的組織中設定 Microsoft Defender ATP，並在 Defender Security Center 中啟用 Microsoft Defender ATP，以取得內部的內幕風險管理整合，以匯入安全性侵犯警示。 如需設定 Microsoft Defender ATP for 內幕風險管理整合的詳細資訊，請參閱[在 Microsoft DEFENDER atp 中設定高級功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="security-policy-violations-by-departing-users-preview"></a>脫離使用者的安全性原則違規（預覽）

使用者不論是保留正負字詞，都可能會有較高的違反安全性原則的風險。 為了協助防止使用者遭受意外或惡意的安全性違規，此原則範本會使用 Microsoft Defender ATP 警示，以提供與安全性相關的活動的洞察力。 這些活動包含使用者安裝惡意程式碼或其他可能有害的應用程式，以及停用裝置上的安全性功能。 當使用者有讓步或終止日期匯入 Microsoft 365 HR Connector 做為觸發事件後，就會啟動原則指示器。

使用此範本時，您必須設定 Microsoft 365 HR connector，定期為組織中的使用者匯入辭職及終止日期資訊。 如需為組織設定 Microsoft 365 HR connector 的逐步指引，請參閱[Import data WITH HR connector](import-hr-data.md)文章。

您需要在您的組織中設定 Microsoft Defender ATP，並在 Defender Security Center 中啟用 Microsoft Defender ATP，以取得內部的內幕風險管理整合，以匯入安全性侵犯警示。 如需設定 Microsoft Defender ATP for 內幕風險管理整合的詳細資訊，請參閱[在 Microsoft DEFENDER atp 中設定高級功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="security-policy-violations-by-priority-users-preview"></a>依優先順序的使用者所違反的安全性原則（預覽）

保護組織中使用者的安全性違規可能取決於其位置、機密資訊的存取層級，或風險歷程記錄。 由於優先順序使用者的安全性違規可能會對組織的重要區域產生 outsized 影響，因此這個原則範本會從這些指示器開始計分，並使用 Microsoft Defender ATP 警示，為這些使用者提供與安全性相關的活動的洞察力。 這可能包括安裝惡意程式碼或其他可能有害之應用程式的優先順序使用者，以及停用裝置上的安全性功能。 優先順序使用者是在「內幕風險管理設定」區域中設定的優先順序使用者群組中定義。

您需要在您的組織中設定 Microsoft Defender ATP，並在 Defender Security Center 中啟用 Microsoft Defender ATP，以取得內部的內幕風險管理整合，以匯入安全性侵犯警示。 如需設定 Microsoft Defender ATP for 內幕風險管理整合的詳細資訊，請參閱[在 Microsoft DEFENDER atp 中設定高級功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。 此外，您必須將「內部使用者群組」原則**管理**  >  **設定**  >  **優先順序使用者群組**中所建立的優先順序使用者群組指派給原則。

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>因不滿使用者而違反的安全性原則（預覽）

經驗 stressors 的使用者可能會遭受無意或惡意安全性原則違規的較高風險。 這些 stressors 可能包含要置於效能改進計畫、效能檢查狀態不良或從目前位置降級的使用者。 這個原則範本會啟動與這些使用者相關之事件的相關指示器和活動，以風險計分為基礎。

使用此範本時，您也必須設定 Microsoft 365 HR 連接器，以定期匯入效能改進通知、不良效能檢查狀態，或組織中使用者的工作層級變更資訊。 如需為組織設定 Microsoft 365 HR connector 的逐步指引，請參閱[Import data WITH HR connector](import-hr-data.md)文章。

您也需要在您的組織中設定 Microsoft Defender ATP，並在 Defender Security Center 中啟用內部的內幕程式風險管理整合的 Microsoft Defender ATP，以匯入安全性侵犯警示。 如需設定 Microsoft Defender ATP for 內幕風險管理整合的詳細資訊，請參閱[在 Microsoft DEFENDER atp 中設定高級功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="offensive-language-in-email"></a>電子郵件中的冒犯性語言

偵測和採取動作，以防止冒犯性和濫用行為成為預防風險的重要元件。 Microsoft 365 中內建的分類器會從組織中的 Exchange Online 信箱傳送電子郵件訊息，以取得不同類型的相容性問題。 這些分類器使用人工智慧和關鍵字的組合，識別可能違反反騷擾原則的電子郵件中的語言。 使用此範本快速建立原則，使用這些分類器自動偵測可能被視為濫用或冒犯性的電子郵件內容。 有問必答風險管理使用的分類器掃描已傳送的電子郵件訊息，以包含冒犯性語言的英文字詞和 sentiment。

### <a name="policy-template-prerequisites-and-triggering-events"></a>原則範本必要條件及觸發事件

根據您為有問必答風險管理原則選擇的範本，觸發事件和原則必要條件會有所不同。 觸發事件是決定使用者是否為內部使用者風險管理原則的必要條件。 如果使用者已新增至「內幕風險管理」原則，但沒有觸發事件，則除非手動將其新增至使用者儀表板，否則不會評估該原則的使用者活動。 原則必要條件是必要專案，讓原則接收評估風險所需的信號或活動。

下表列出從每個有問必答風險管理原則範本所建立之原則的觸發事件和必要條件：

| **原則範本** | **觸發原則的事件** | **先決條件** |
| :------------------ | :--------------------------------- | :---------------- |
| 由去聲使用者竊取資料 | 來自 HR 連接器的辭職或終止日期指示器 | 設定為終止和讓步日期指標的 Microsoft 365 HR connector |
| 一般資料洩漏 | 產生高嚴重性警示的資料洩漏原則活動 | 為高嚴重性警示設定的 DLP 原則 |
| 依優先使用者的資料洩漏 | 產生高嚴重性警示的資料洩漏原則活動 | 為高嚴重性警示設定的 DLP 原則 <br><br> 在內部使用者風險設定中設定的優先順序使用者群組 |
| 因不滿使用者的資料洩漏 | HR connector 的效能提高、效能不良或工作層級變更指示器 | 為 disgruntlement 指示器設定的 Microsoft 365 HR connector |
| 一般安全性原則違規 | Microsoft Defender ATP 所偵測到的安全性控制或不需要軟體的防禦性規避 | 使用中的 Microsoft Defender ATP 訂閱 <br><br> Microsoft Defender ATP 已設定 Microsoft 365 規範中心整合 |
| 脫離使用者的安全性原則違規 | 來自 HR 連接器的辭職或終止日期指示器 | 設定為終止和讓步日期指標的 Microsoft 365 HR connector <br><br> 使用中的 Microsoft Defender ATP 訂閱 <br><br> Microsoft Defender ATP 已設定 Microsoft 365 規範中心整合 |
| 依優先順序的使用者所破壞的安全性原則 | Microsoft Defender ATP 所偵測到的安全性控制或不需要軟體的防禦性規避 | 使用中的 Microsoft Defender ATP 訂閱 <br><br> Microsoft Defender ATP 已設定 Microsoft 365 規範中心整合 <br><br> 在內部使用者風險設定中設定的優先順序使用者群組 |
| 因不滿使用者所違反的安全性原則 | HR connector 的效能提高、效能不良或工作層級變更指示器 | 為 disgruntlement 指示器設定的 Microsoft 365 HR connector <br><br> 使用中的 Microsoft Defender ATP 訂閱 <br><br> Microsoft Defender ATP 已設定 Microsoft 365 規範中心整合 |
| 電子郵件中的冒犯性語言 | 電子郵件訊息中的猥褻、威脅或 harassing 語言 | Active Exchange Online 訂閱 |

## <a name="prioritize-content-in-policies"></a>設定原則中內容的優先順序

有問必答風險管理原則支援針對內容指定較高的優先順序，具體取決於其儲存位置或其分類方式。 將內容指定為優先順序，可增加任何關聯活動的風險分數，進而會增加產生高嚴重性警示的機率。 不過，除非相關的內容包含內建或自訂的機密資訊類型，或是在原則中指定為優先順序，否則有些活動根本不會產生警示。

例如，您的組織擁有高度機密專案的專屬 SharePoint 網站。 此 SharePoint 網站中資訊的資料洩漏可能會危及專案，並對其成功產生重大影響。 在資料洩漏原則中優先使用此 SharePoint 網站，可自動增加符合資格活動的風險分數。 這會增加這些活動產生「有問必答風險」警示的可能性，並會提升警示的嚴重性等級。

當您在原則嚮導中建立「有問必答風險管理」原則時，可以選擇下列優先順序：

- **SharePoint 網站**：與定義 SharePoint 網站中的所有檔案類型相關聯的任何活動，都是以較高風險排名指派。 
- **敏感資訊類型**：與包含[機密資訊類型](sensitive-information-type-entity-definitions.md)之內容相關聯的任何活動都會獲指派較高的風險分數。
- **敏感度標籤**：與已套用特定[敏感度標籤](sensitivity-labels.md)之內容相關聯的任何活動，都是以較高的風險排名指派。

## <a name="create-a-new-policy"></a>建立新原則

若要建立新的內部使用者風險管理原則，您會使用 Microsoft 365 規範中心內的「**內部使用者風險管理**」方案中的原則嚮導。

完成下列步驟以建立新的原則：

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至 **[測試人員風險管理]**，然後選取 **[原則]** 索引標籤。
2. 選取 **[建立原則]** 以開啟原則精靈
3. 在 **[新增測試人員風險原則]** 頁面上，完成下列欄位：
    - **名稱（必要）**：輸入原則的易記名稱。
    - **說明 (選用)**：輸入原則的說明。
    - **選擇原則範本 (必要)**：選取其中一個[原則範本](insider-risk-management-policies.md#policy-templates)，以定義受原則監視的風險指標類型。

    >[!IMPORTANT]
    >大多數原則範本都具有必須針對原則進行設定以產生相關警示的必要條件。 若尚未設定適用的原則必要條件，請參閱「[開始使用內部使用者風險管理](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)」。

4. 選取 **[下一步]** 繼續。
5. 在 [**使用者**] 頁面上，選取 [**新增使用者或群組**] 或 **[選擇優先級使用者群組**]，以根據您所選取的原則範本，定義納入原則中的使用者或優先順序使用者群組。 如果適用的話，請選取 [**所有使用者及擁有郵件功能的群組**] 核取方塊（如果您尚未選取優先順序使用者的範本）。 選取 **[下一步]** 繼續。
6. 在 [**指定要設定優先順序的內容（選用）** ] 頁面上，您可以指派來源，以優先增加風險分數。 不過，除非相關的內容包含內建或自訂的機密資訊類型，或是在此頁面上指定為優先順序，否則有些活動根本不會產生警示：
    - **SharePoint 網站**：選取 **[新增 SharePoint 網站]**，然後選取要設定優先順序的 SharePoint 組織。 例如，*"group1@contoso.sharepoint.com/sites/group1"*。
    - **敏感性資訊類型**：選取 **[新增敏感性資訊類型]**，然後選取要設定優先順序的敏感性類型。 例如，*[美國銀行帳戶號碼]* 和 *[信用卡號碼]*。
    - **敏感度標籤**：選取 **[新增敏感度標籤]**，然後選取要設定優先順序的標籤。 例如，*[機密]* 和 *[密碼]*。
7. 選取 **[下一步]** 繼續。
8. 在 [**選取原則指示器**] 頁面上，您會看到您已在「**有問必答風險設定**指示器」頁面上定義為可用的[指示器](insider-risk-management-settings.md#indicators)  >  **Indicators** 。 如果您在嚮導的開頭選取*資料洩漏*範本，則必須從 [ **dlp 原則**] 下拉式清單中選取 dlp 原則，才能啟用該原則的觸發指示器。 選取您要套用到原則的指示器。 如果您不想使用這些指標的預設原則閾值設定，請停用 [**使用 Microsoft 建議的預設閾值**]，然後為每個選取的指示器輸入臨界值。 如果您已選取至少一個*辦公室*或*裝置*指標，請視需要選取 [**風險分數 boosters** ]。 風險分數 boosters 只適用于選取的指示器。

    >[!IMPORTANT]
    >如果無法選取此頁面上的指示器，您必須選取要對「**內幕人員風險管理**  >  **設定**  >  **原則指示器**」頁面上的所有原則啟用的指示器。

9. 選取 **[下一步]** 繼續。
10. 在 [**原則時段**] 頁面上，您會在 [**有問必答風險設定**原則時段] 頁面上看到 [原則] 的 [[啟用] 視窗條件](insider-risk-management-settings.md#policy-timeframes)  >  **Policy timeframes** 。
11. 選取 **[下一步]** 繼續。
12. 在**檢閱**頁面上，檢閱您為原則選擇的設定。 選取 **[編輯]** 以變更任何原則值，或選取 **[提交]** 來建立並啟用原則。

## <a name="update-a-policy"></a>更新原則

若要更新現有的「內部使用者風險管理」原則，您將使用 Microsoft 365 規範中心內的「**內幕風險管理**」方案中的原則嚮導。

完成下列步驟以管理現有的原則：

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至 **[測試人員風險管理]**，然後選取 **[原則]** 索引標籤。
2. 在 [原則] 儀表板上，選取您要管理的原則。
3. 在 [原則詳細資料] 頁面上，選取 [**編輯原則**]
4. 在 [原則嚮導] 中，您無法編輯下欄欄位：
    - **名稱**：原則的易記名稱
    - **選擇 [原則範本**]：用來定義原則所監控之風險指示器類型的範本。
5. 在 [**描述**] 欄位中輸入原則的新描述。 
6. 選取 **[下一步]** 繼續。
7. 在 [**使用者**] 頁面上，選取 [**新增使用者或群組**] 或 **[選擇優先級使用者群組**]，以根據您所選取的原則範本，定義納入原則中的使用者或優先順序使用者群組。 如果適用的話，請選取 [**所有使用者及擁有郵件功能的群組**] 核取方塊（如果您尚未選取優先順序使用者的範本）。 選取 **[下一步]** 繼續。
8. 在 [**指定要設定優先順序的內容（選用）** ] 頁面上，您可以指派來源，以優先增加風險分數。 不過，除非相關的內容包含內建或自訂的機密資訊類型，或是在此頁面上指定為優先順序，否則有些活動根本不會產生警示：
    - **SharePoint 網站**：選取 **[新增 SharePoint 網站]**，然後選取要設定優先順序的 SharePoint 組織。 例如，*"group1@contoso.sharepoint.com/sites/group1"*。
    - **敏感性資訊類型**：選取 **[新增敏感性資訊類型]**，然後選取要設定優先順序的敏感性類型。 例如，*[美國銀行帳戶號碼]* 和 *[信用卡號碼]*。
    - **敏感度標籤**：選取 **[新增敏感度標籤]**，然後選取要設定優先順序的標籤。 例如，*[機密]* 和 *[密碼]*。
9. 選取 **[下一步]** 繼續。
10. 在 [**選取原則指示器**] 頁面上，您會看到您已在「**有問必答風險設定**指示器」頁面上定義為可用的[指示器](insider-risk-management-settings.md#indicators)  >  **Indicators** 。 如果您在嚮導的開頭選取*資料洩漏*範本，則必須從 [ **dlp 原則**] 下拉式清單中選取 dlp 原則，才能啟用該原則的觸發指示器。 選取您要套用到原則的指示器。 如果您不想使用這些指標的預設原則閾值設定，請停用 [**使用 Microsoft 建議的預設閾值**]，然後為每個選取的指示器輸入臨界值。 如果您已選取至少一個*辦公室*或*裝置*指標，請視需要選取 [**風險分數 boosters** ]。 風險分數 boosters 只適用于選取的指示器。

    >[!IMPORTANT]
    >如果無法選取此頁面上的指示器，您必須選取要對「**內幕人員風險管理**  >  **設定**  >  **原則指示器**」頁面上的所有原則啟用的指示器。

11. 選取 **[下一步]** 繼續。
12. 在 [**原則時段**] 頁面上，您會在 [**有問必答風險設定**原則時段] 頁面上看到 [原則] 的 [[啟用] 視窗條件](insider-risk-management-settings.md#policy-timeframes)  >  **Policy timeframes** 。
13. 選取 **[下一步]** 繼續。
14. 在 [**複查**] 頁面上，複查您已針對原則更新的設定。 選取 [**編輯**] 以變更任何原則值，或選取 [**提交**] 以更新及啟用原則。

## <a name="delete-a-policy"></a>刪除原則

>[!NOTE]
>刪除原則並不會刪除原則所產生的使用中或已封存警示。

若要刪除現有的有問必答風險管理原則，請完成下列步驟：

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至 **[測試人員風險管理]**，然後選取 **[原則]** 索引標籤。
2. 在 [原則] 儀表板上，選取您要刪除的原則。
3. 選取儀表板工具列上的 [**刪除**]。
4. 在 [**刪除**] 對話方塊中，選取 [是] 刪除原則，或選取 **[** **取消**] 關閉對話方塊。
