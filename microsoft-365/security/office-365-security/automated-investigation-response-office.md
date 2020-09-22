---
title: 自動調查和回應 (AIR) 概述
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
ms.collection: M365-security-compliance
ms.date: 08/21/2020
description: 深入瞭解 Office 365 高級威脅防護方案2中的自動化調查和回應功能。
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: d6793793a663e562b05df7e8458a6a8933e5ee47
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200342"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a>Microsoft 365 中 (AIR) 的自動化調查和回應概覽

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。 在某些情況下，安全性作業小組可能感覺到所觸發的警示數量所淹沒。 自動調查和回應 (Office 365 的 AIR) 功能 (Office 365 ATP) 可助您。 

AIR 可讓您的安全性運作小組更有效率地運作。 AIR 功能包括自動調查處理程式，以回應目前存在的已知威脅。 適當的修正動作等待核准，讓您的安全性作業小組能夠回應偵測到的威脅。 

本文提供空中的概覽。 當您準備好開始使用 AIR 時，請參閱 [自動調查和回應威脅](office-365-air.md)。

## <a name="at-a-high-level"></a>在高層級

當觸發警示時，安全性行動行動會生效。 根據情況而定，可以開始進行 [自動化調查過程](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 。 在自動調查期間和之後，建議進行 [修正動作](air-remediation-actions.md) 。 Office 365 的 [高級威脅防護] 中不會自動採取任何動作。 您的安全性運作小組會評論，然後 [核准或拒絕每項修復動作](air-review-approve-pending-completed-actions.md)。 在調查中的所有動作經核准或拒絕時，調查都會完成。 所有這些活動都會在安全性 & 規範中心中追蹤和查看 (請參閱 [查看調查) 的詳細資料](air-view-investigation-results.md#view-details-of-an-investigation) 。

下列各節提供有關警示、安全性行動手冊及動作中的空氣範例的詳細資訊。

## <a name="alerts"></a>警示

[警示](../../compliance/alert-policies.md#viewing-alerts) 代表事件回應的安全性作業小組工作流程的觸發器。 決定要調查的適當一組提醒，同時確保沒有威脅 unaddressed 面臨挑戰。 當手動調查何時會以手動方式執行提醒時，安全性作業小組必須搜尋和關聯實體 (例如內容、裝置和使用者) 威脅以外的風險。 這類工作和工作流程可能非常耗時且包含多個工具和系統。 透過利用關鍵安全性和威脅管理提醒自動觸發安全性回應行動手冊，透過 AIR、安全事件的調查和回應可自動進行。 

目前對於 AIR，會自動調查從下列類型的報警原則產生的警示：  

- 偵測到可能的惡意 URL 按一下
- 使用者以網路釣魚方式舉報的電子郵件`*`
- 傳遞後移除包含惡意程式碼的電子郵件`*`
- 傳遞後移除包含網路釣魚 URLs 的電子郵件`*`
- 偵測到電子郵件傳送模式`#`
- 使用者限制傳送電子郵件`#`

> [!NOTE]
> 以星號 () 標示的警示 `*` 會在安全性 & 規範中心內的各項警示原則中指派 *資訊* 嚴重性，並關閉電子郵件通知。 您可以透過 [報警原則](../../compliance/alert-policies.md#alert-policy-settings)設定開啟電子郵件通知。 使用雜湊 () 標示的警示， `#` 通常是與公共預覽行動手冊相關聯的警示。

若要在安全性 & 規範中心中查看提醒，請選擇 [**提醒**] [  >  **查看提醒**]。 選取警示以查看其詳細資料，然後從那裡使用「 **查看調查** 」連結，以移至對應的 [調查](air-view-investigation-results.md#investigation-graph)。  

> [!NOTE]
> 預設會在提醒視圖中隱藏資訊警示。 若要查看，請變更警示篩選，以包含資訊性警示。

如果您的組織透過警示管理系統、服務管理系統、安全性資訊和事件管理 (SIEM) 系統來管理安全性警示，您可以透過電子郵件通知或透過 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)，將提醒傳送給該系統。 透過電子郵件或 API 的調查警示通知包含在安全性 & 規範中心中存取警示的連結，讓指派的安全性系統管理員可以快速流覽調查。

![連結至調查的警示](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>安全性行動手冊

安全性行動行動是以 Office 高級威脅防護和 Microsoft 威脅防護為自動化的後端原則。 AIR 中所提供的安全性行動技巧是以常見的實際安全性案例為依據，並根據安全性運作小組的意見來開發。 當您的組織內觸發特定警示時，會自動啟動安全性行動手冊。 警示觸發後，就會透過自動調查和回應 (AIR) 系統來執行相關聯的行動手冊。 調查步驟：透過該特定警示行動手冊分析提醒，查看所有相關聯的中繼資料 (包括電子郵件訊息、使用者、主題、寄件者等 ) 。 根據調查行動手冊的結果，AIR 建議您的組織安全小組可以採取的一組動作來控制及緩解威脅。 

您可以使用 AIR 的安全性行動方式，來處理目前的組織使用電子郵件所遇到的最常見威脅。 它們是以安全性作業和事件回應小組的輸入為基礎，包括協助保護 Microsoft 和客戶資產的人員。

### <a name="security-playbooks-are-rolling-out-in-phases"></a>安全性行動行動是分階段推出

在飛機的一部分中，安全性行動行動是在階段中推出。 階段1現在已可供使用，且包含數個行動手冊，可提供安全性管理員可審查及核准的動作建議：

- 使用者報告的網路釣魚郵件
- URL-按一下判定變更
- 惡意程式碼偵測到傳遞後 (惡意程式碼 ZAP) 
- 網路釣魚程式偵測到傳遞後的 ZAP (網路釣魚 ZAP) 

階段1也包含對管理員使用 [威脅 Explorer](threat-explorer.md))  (觸發電子郵件調查的支援。

階段2現在的進度是 **公開預覽**中的下列行動手冊、提供動作的建議，以及 aiding 安全性管理員以調查問題：

- 使用者報告 (公開預覽的漏洞) 

更多行動手冊會在完成時發佈。 請造訪 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap) ，以查看已計畫及即將推出的內容。

### <a name="playbooks-include-investigation-and-recommendations"></a>行動行動包括調查和建議

在 AIR 中，每個安全性行動手冊包括： 

- 電子郵件實體的根調查 (例如檔案、URLs、收件者、IP 位址等) ）
- 進一步搜尋組織所收到的類似電子郵件 
- 識別和關聯其他潛在威脅所採取的步驟，以及 
- 建議的威脅修復動作。

每個高階步驟都包含一些執行的子步驟，以提供對威脅的深入、詳盡及詳盡的回應。

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>範例：使用者報告的網路釣魚郵件啟動調查行動手冊

假設組織中的使用者收到他們認為是網路釣魚企圖的電子郵件。 使用者在報告這類訊息時，會使用 [報告訊息增益集](enable-the-report-message-add-in.md) 將其傳送至 Microsoft 進行分析。 提交也會傳送至您的系統，而且會顯示在 **提交** 視圖中 (先前稱為 **使用者報告** 的 view) 。 此外，使用者報告的訊息現在會觸發以系統為基礎的資訊性警示，這會自動啟動調查行動手冊。

在根調查階段中，會評估電子郵件的各個層面。 這些方面包括：

- 決定可能的威脅類型;
- 誰送出;
- 電子郵件傳送來源的 (傳送基礎結構) ;
- 電子郵件的其他實例是否已傳遞或封鎖;
- 我們分析員的評估;
- 電子郵件是否與任何已知的市場活動相關聯;
- 等等。

完成根調查之後，「行動手冊」會提供建議執行的動作清單，以供原始電子郵件和與其相關聯的實體使用。
  
接下來，會執行數個威脅調查和搜尋步驟：

- 類似的電子郵件會透過電子郵件聚簇搜尋加以識別。
- 此信號是與其他平臺（例如 [Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共用。
- 決定是否任何使用者已透過可疑電子郵件訊息中的任何惡意連結進行按一下。
- 在 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 Office 365 的高級威脅防護 ([ATP](office-365-atp.md)) 之間進行檢查，以查看使用者是否會報告其他類似的訊息。
- 會執行檢查以查看使用者是否遭到破壞。 這種檢查會利用跨 Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)的信號，以關聯任何相關的使用者活動異常。

在搜尋階段中，會將風險和威脅指派給各種搜尋步驟。 

修正是行動手冊的最後階段。 在此階段中，會根據調查和搜尋階段採取補救措施。 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>範例：安全性管理員會觸發來自威脅瀏覽器的調查

除了警示所觸發的自動調查之外，您的組織的安全性運作小組也可在 [威脅瀏覽器](threat-explorer.md)的視圖中觸發自動調查。

例如，假設您在威脅瀏覽器中使用 **惡意** 代碼視圖。 您可以使用圖表下方的索引標籤，選取 [ **電子郵件** ] 索引標籤。如果您選取清單中的一或多個專案，則會啟動 **+ 動作** 按鈕。 

![具有選取郵件的 Explorer](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

您可以使用 [ **動作** ] 功能表，選取 [ **觸發調查**]。

![選取郵件的動作功能表](../../media/explorer-malwareview-selectedemails-actions.jpg)

類似于警示所觸發的行動行動方式，從瀏覽器中的視圖觸發的自動調查包括根調查、識別和關聯威脅的步驟，以及緩解這些威脅的建議動作。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>範例：使用 Office 365 管理活動 API，安全性運作小組與其 SIEM 整合 AIR

Office 365 ATP 中的 AIR 功能包括 [報告 & 詳細資料](air-view-investigation-results.md) ，安全性作業小組可用以監視和處理威脅。 不過，您也可以整合 AIR 功能與其他解決方案。 範例包括安全性資訊和事件管理 (SIEM) 系統、案例管理系統或自訂報告解決方案。 您可以使用 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)來完成這些整合類型。 

例如，在最近，組織會設定安全性作業小組的方式，以查看已由 AIR 處理的使用者報告網路釣魚警報。 其解決方案會將相關的警示與組織的 SIEM 伺服器及其案例管理系統整合在一起。 此解決方案大幅減少誤報的數目，讓他們的安全性運作小組能夠專注于實際威脅的時間和工作。 若要深入瞭解此自訂解決方案，請參閱 [技術社區博客：使用 Office 365 ATP 和 O365 管理 API，改善 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

## <a name="next-step"></a>下一步

- [開始使用 AIR](office-365-air.md)

## <a name="see-also"></a>請參閱

- [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Microsoft 威脅防護中的自動化調查和回應功能](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide)
