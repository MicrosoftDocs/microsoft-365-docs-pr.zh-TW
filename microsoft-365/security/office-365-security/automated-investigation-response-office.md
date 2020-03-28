---
title: Office 365 中的自動化調查和回應（AIR）
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
description: 深入瞭解 Office 365 高級威脅防護方案2中的自動化調查和回應功能。
ms.custom: air
ms.openlocfilehash: e8e10160da4ddb43b47ecf41e2184dc1b8953941
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033443"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Office 365 中的自動化調查和回應（AIR）

在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。 在某些情況下，安全性作業小組可能感覺到所觸發的警示數量所淹沒。 Office 365 中的自動化調查和回應（AIR）功能可能會有所説明。 AIR 可讓您的安全性運作小組更有效率地運作。 AIR 功能包括自動調查處理程式，以回應目前存在的已知威脅。 適當的修正動作等待核准，讓您的安全性作業小組能夠回應偵測到的威脅。 

本文提供空中的概覽。 當您準備好開始使用 AIR 時，請參閱[自動調查和回應 Office 365 中的威脅](office-365-air.md)。

## <a name="at-a-high-level"></a>在高層級

當觸發警示時，安全性行動行動會生效。 根據情況而定，可以開始進行[自動化調查過程](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 在自動調查期間和之後，建議進行[修正動作](air-remediation-actions.md)。 Office 365 的 [高級威脅防護] 中不會自動採取任何動作。 您的安全性運作小組會進行審閱，然後[核准或拒絕每項修復動作](air-review-approve-pending-completed-actions.md)，當執行完畢時，每項調查都會完成。 所有這些活動都會在 Office 365 安全性 & 規範中心中追蹤和查看（請參閱[查看調查的詳細資料](air-view-investigation-results.md#view-details-of-an-investigation)）。

下列各節提供有關警示、安全性行動手冊及動作中的空氣範例的詳細資訊。

## <a name="alerts"></a>警示

[警示](../../compliance/alert-policies.md#viewing-alerts)代表事件回應的安全性作業小組工作流程的觸發器。 決定要調查的適當一組提醒，同時確保沒有威脅 unaddressed 面臨挑戰。 當手動調查何時執行警示時，安全性作業小組必須搜尋實體（例如內容、裝置和使用者），並與威脅相關聯。 這類工作和工作流程可能非常耗時且包含多個工具和系統。 透過利用關鍵安全性和威脅管理提醒自動觸發安全性回應行動手冊，透過 AIR、調查和 Office 365 安全性事件的回應可自動進行。 

目前對於 AIR，會自動調查從下列類型的報警原則產生的警示：  

- 偵測到可能的惡意 URL 按一下
- 以使用者身分舉報為網路釣魚的電子郵件 *
- 傳遞後移除惡意程式碼的電子郵件訊息 *
- 傳遞後移除包含網路釣魚 URLs 的電子郵件 *
- 偵測到電子郵件傳送模式#
- 使用者限制傳送電子郵件#

> [!NOTE]
> 以星號（*）標示的警示會在安全性 & 合規性中心內的各項警示原則中指派*資訊*嚴重性，並關閉電子郵件通知。 您可以透過[報警原則](../../compliance/alert-policies.md#alert-policy-settings)設定開啟電子郵件通知。 使用雜湊（#）標示的警示，通常是與公共預覽行動手冊相關聯的警示。

若要在安全性 & 規範中心中查看提醒，請選擇 [**提醒** > ] [**查看提醒**]。 選取警示以查看其詳細資料，然後從那裡使用「**查看調查**」連結，以移至對應的[調查](air-view-investigation-results.md#investigation-graph)。  

> [!NOTE]
> 預設會在提醒視圖中隱藏資訊警示。 若要查看，請變更警示篩選，以包含資訊性警示。

如果您的組織透過警示管理系統、服務管理系統或安全性資訊和事件管理（SIEM）系統來管理安全性警示，您可以透過電子郵件通知或透過[office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)，將 Office 365 警示傳送給該系統。 透過電子郵件或 API 的調查警示通知包含在安全性 & 規範中心中存取警示的連結，讓指派的安全性系統管理員可以快速流覽調查。

![連結至調查的警示](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>安全性行動手冊

安全性行動行動是以 Office 高級威脅防護和 Microsoft 威脅防護為自動化的後端原則。 AIR 中所提供的安全性行動技巧是以常見的實際安全性案例為依據，並根據安全性運作小組的意見來開發。 當您的組織內觸發特定警示時，會自動啟動安全性行動手冊。 警示觸發後，會自動調查和回應（AIR）系統執行相關聯的行動手冊。 調查步驟：透過該特定警示行動手冊分析提醒，查看所有相關聯的中繼資料（包括電子郵件訊息、使用者、主題、寄件者等）。 根據調查行動手冊的結果，AIR 建議您的組織安全小組可以採取的一組動作來控制及緩解威脅。 

您可以使用 AIR 的安全性行動方式，來處理目前的組織使用電子郵件所遇到的最常見威脅。 它們是以安全性作業和事件回應小組的輸入為基礎，包含的人員可協助保護 Microsoft 和我們客戶的資產。

### <a name="security-playbooks-are-rolling-out-in-phases"></a>安全性行動行動是分階段推出

在飛機的一部分中，安全性行動行動是在階段中推出。 階段1現在已可供使用，且包含數個行動手冊，可提供安全性管理員可審查及核准的動作建議：
- 使用者報告的網路釣魚郵件
- URL 按一下判定變更
- 惡意程式碼偵測到傳遞後（惡意程式碼 ZAP）
- 網路釣魚偵測到傳遞傳遞（網路釣魚 ZAP）

階段1也包含對管理員觸發電子郵件調查的支援（使用[威脅瀏覽器](threat-explorer.md)）。

第2階段現在的進度是**公開預覽**中的下列行動手冊，提供動作和 aiding 安全性管理員調查問題的建議：
- 使用者舉報為已遭破壞（公開預覽）

進一步的行動手冊將在完成後發行。 請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)，以查看已計畫及即將推出的內容。

### <a name="playbooks-include-investigation-and-recommendations"></a>行動行動包括調查和建議

在 AIR 中，每個安全性行動手冊包括： 
- 電子郵件實體的根調查（檔案、URLs、收件者、IP 位址等）
- 進一步搜尋組織所收到的類似電子郵件 
- 識別和關聯其他潛在威脅所採取的步驟，以及 
- 建議的威脅修復動作。

每個高階步驟都包含一些執行的子步驟，以提供對威脅的深入、詳盡及詳盡的回應。

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>範例：使用者報告的網路釣魚郵件啟動調查行動手冊

假設組織中的使用者收到他們認為是網路釣魚企圖的電子郵件。 使用者在報告這類訊息時，會使用[報告訊息增益集](enable-the-report-message-add-in.md)將其傳送至 Microsoft 進行分析。 提交也會傳送給您的系統，而且會顯示在**提交**視圖（先前稱為**使用者報告**的查看）的 [Explorer] 中。 此外，使用者報告的訊息現在會觸發以系統為基礎的資訊性警示，這會自動啟動調查行動手冊。

在根調查階段中，會評估電子郵件的各個層面。 包括：
- 決定可能的威脅類型;
- 誰送出;
- 電子郵件傳送來源的位置（傳送基礎結構）;
- 電子郵件的其他實例是否已傳遞或封鎖;
- 我們分析員的評估;
- 電子郵件是否與任何已知的市場活動相關聯;
- 等等。

完成根調查之後，「行動手冊」會提供建議執行的動作清單，以供原始電子郵件和與其相關聯的實體使用。
  
接下來，會執行數個威脅調查和搜尋步驟：

- 類似的電子郵件會透過電子郵件聚簇搜尋加以識別。
- 此信號是與其他平臺（例如[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共用。
- 決定是否任何使用者已透過可疑電子郵件訊息中的任何惡意連結進行按一下。
- 您可以透過 Office 365 Exchange Online Protection （[EOP](exchange-online-protection-eop.md)）和 Office 365 高級威脅防護（[ATP](office-365-atp.md)）進行檢查，以查看使用者是否會報告其他類似的訊息。
- 會執行檢查以查看使用者是否遭到破壞。 這種檢查會利用跨 Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)的信號，以關聯任何相關的使用者活動異常。 

在搜尋階段中，會將風險和威脅指派給各種搜尋步驟。 

修正是行動手冊的最後階段。 在此階段中，會根據調查和搜尋階段採取補救措施。 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>範例：安全性管理員會觸發來自威脅瀏覽器的調查

除了警示所觸發的自動調查之外，您的組織的安全性運作小組也可在[威脅瀏覽器](threat-explorer.md)的視圖中觸發自動調查。

例如，假設您在威脅瀏覽器中使用**惡意**代碼視圖。 您可以使用圖表下方的索引標籤，選取 [**電子郵件**] 索引標籤。如果您選取清單中的一或多個專案，則會啟動 **+ 動作**按鈕。 

:::image type="content" source="../../media/Explorer-Malware-Email-ActionsInvestigate.png" alt-text="具有選取郵件的 Explorer":::

您可以使用 [**動作**] 功能表，選取 [**觸發調查**]。

:::image type="content" source="../../media/explorer-malwareview-selectedemails-actions.jpg" alt-text="選取郵件的動作功能表":::

類似于警示所觸發的行動行動方式，從瀏覽器中的視圖觸發的自動調查包括根調查、識別和關聯威脅的步驟，以及緩解這些威脅的建議動作。

## <a name="next-steps"></a>後續步驟

- [開始使用 Office 365 中的 AIR](office-365-air.md)

- [造訪 Microsoft 365 藍圖，查看即將推出的功能](https://www.microsoft.com/microsoft-365/roadmap?filters=)

