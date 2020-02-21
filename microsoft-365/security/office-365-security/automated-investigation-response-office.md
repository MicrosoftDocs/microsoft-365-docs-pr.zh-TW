---
title: 自動化的調查和 Office 365 中的回應 （空調）
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
description: 在 Office 365 進階威脅防護計劃 2 中，取得自動化調查及回應能力的概觀。
ms.openlocfilehash: 8f781687047f39d4d038e293e50c9caad83d051a
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179244"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>自動化的調查和 Office 365 中的回應 （空調）

為會觸發安全性警訊，它會高達您查看這些提醒，並採取步驟來保護您的組織的安全性作業小組。 有時候，安全性作業小組可以覺得負荷量，便會觸發警示。 自動化的調查和 Office 365 中的回應 （空調） 功能可協助。 空調可讓您操作更有效率的安全性作業小組。 空調功能在今日的熟知威脅的回應中包含自動化的調查程序。 適當的補救動作等候核准，讓您回應偵測到的威脅的安全性作業小組。 

本文提供空調和其元件的概觀。 當您準備好要開始使用空調時，請參閱[自動調查及回應 Office 365 中的威脅](office-365-air.md)。

> [!TIP]
> 您有 Microsoft 365 E5 或 Microsoft 365 E3 以及身分識別與威脅防護產品？ 考慮嘗試 [Microsoft 威脅防護](../mtp/microsoft-threat-protection.md)。

## <a name="at-a-high-level"></a>在高層級

為會觸發警訊，安全性 playbooks 會進入效果。 根據情況而異，就可以開始[自動的調查程序](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 期間和之後自動調查，被建議的[修復動作](air-remediation-actions.md)。 Office 365 進階威脅防護中自動不採取任何動作。 您的安全性操作小組評論，然後再[核准或拒絕每個修復動作](air-remediation-actions.md#approve-or-reject-pending-actions)，並完成時，每個調查完成。 所有這些活動追蹤和檢視位於 Office 365 安全性 & 合規性中心 （請參閱[檢視調查的詳細資料](air-view-investigation-results.md#view-details-of-an-investigation)）。

下列各節提供更多詳細資訊提醒、 安全性 playbooks 和空調的巨集指令中的範例。

## <a name="alerts"></a>警示

[提醒](../../compliance/alert-policies.md#viewing-alerts)代表觸發程序適用於安全性事件回應作業小組工作流程。 排列優先順序的調查，同時確保沒有威脅 unaddressed 提醒右組是一項挑戰。 時以手動方式執行提醒到調查，安全性作業小組必須搜尋，並與相互關聯實體 （例如內容、 裝置及使用者） 威脅的風險。 這類任務及工作流程可很耗時及牽涉到多個工具和系統。 空調、 調查與 Office 365 安全性事件回應會自動完成察覺主要的安全性與威脅管理警報自動觸發安全性回應 playbooks。 

目前的空調，從下列幾種類型的警示原則中產生警示，可自動調查：  

- 偵測到有潛在的惡意 URL 點擊
- 報告的釣魚程式 * 作為使用者的電子郵件
- 電子郵件包含惡意程式碼傳遞 * 後移除
- 電子郵件訊息包含傳遞 * 後移除的釣魚程式 Url
- 傳送模式偵測到可疑的電子郵件#
- 使用者限制而無法傳送電子郵件#

> [!NOTE]
> 以星號 （*） 標記的警示關閉的電子郵件通知與指派安全性 & 合規性中心，各自的警示原則*提示資訊*嚴重性。 電子郵件通知可以開啟透過[警示原則設定](../../compliance/alert-policies.md#alert-policy-settings)。 以雜湊 （#） 標記的提醒是通常可公開預覽 playbooks 相關聯的提醒。

若要檢視提醒，安全性 & 合規性中心中，選擇 [**提醒** > **檢視警示**。 選取警示若要檢視其詳細資料，並從該處，使用的**檢視調查**連結移至對應的[調查](air-view-investigation-results.md#investigation-graph)。  

> [!NOTE]
> 預設為 [警示] 檢視中隱藏資訊警示。 若要查看它們，請變更篩選功能，包括資訊警示的警示。

如果您的組織管理您的安全性提醒透過警示管理系統、 服務管理系統或安全性資訊和事件管理 (SIEM) 的系統，您可以透過 [電子郵件通知，或是透過[Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)該系統傳送 Office 365 警示。 透過電子郵件或 API 調查警示通知包含連結來存取安全性 & 合規性中心，啟用快速瀏覽到調查指派的安全性系統管理員中的警示。

![連結至調查的提醒](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>安全性 playbooks

安全性 playbooks 所面臨的自動化 Office 進階威脅防護和 Microsoft 威脅防護中的核心的後端原則。 根據常見的真實世界的安全性案例 playbooks 空調中所提供且開發安全性為基礎的意見反應安全性作業小組。 當組織內會觸發特定的警示時，就會自動啟動安全性 playbook。 之後會觸發警示，相關聯的 playbook 執行自動化調查及回應 （空調） 系統。 調查步驟透過分析根據該特定警示 playbook，查看所有關聯的中繼資料 （包括電子郵件、 使用者、 主旨、 寄件者等等） 的提醒。 根據調查 playbook 的結果，空調建議一組的動作，貴組織的安全性小組可以採取控制項，並降低威脅。 

您會看到與空調安全性 playbooks 被設計來處理最常見的威脅組織遇到今天的電子郵件。 他們根據安全性作業和事件回應小組，包括協助防禦 Microsoft 和我們的客戶資產的輸入。

### <a name="security-playbooks-are-rolling-out-in-phases"></a>安全性 playbooks 已推出階段

航空的一部分，安全性 playbooks 已推出階段。 階段 1 是現在可使用，並包含數個 playbooks 提供建議的安全性系統管理員可以檢閱和核准的動作：
- 使用者報告的釣魚程式訊息
- URL 按一下 verdict 變更
- 偵測到的惡意程式碼後傳遞 （惡意程式碼時能量光束）
- 釣魚程式偵測到後續傳遞 ZAP （Phish 時能量光束）

階段 1 也包含觸發的系統管理員的電子郵件調查 （使用[威脅總管](threat-explorer.md)） 的支援。

階段 2 現在是與**公開預覽**中提供建議的動作，並在調查問題達到安全性管理員下列 playbooks 的進度：
- 使用者回報為遭入侵 （公用預覽）

將發行進一步 playbooks，因為它們已完成。 請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)請參閱什麼是計劃的及接下來推出。

### <a name="playbooks-include-investigation-and-recommendations"></a>Playbooks 包括調查與建議

在空調，每個安全性 playbook 包括： 
- 根調查的電子郵件的實體 （檔案、 Url、 收件者、 IP 位址等等。），
- 進一步四處尋找類似組織所接收的電子郵件 
- 識別並對應其他潛在威脅，所採取的步驟和 
- 建議的威脅修復動作。

每個高階步驟皆包含一些 substeps 執行提供深層、 詳細又詳盡回應威脅。

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>範例： 使用者回報的釣魚程式訊息啟動調查 playbook

當您組織中的使用者送出的電子郵件訊息和報告至 Microsoft，請使用[報告訊息增益集以進行 Outlook 或 Outlook Web App](enable-the-report-message-add-in.md)，報告也會傳送到您的系統，且使用者報告檢視中顯示在檔案總管。 此使用者回報郵件現在會觸發系統架構資訊警示，這會自動啟動 [調查 playbook。

在根調查階段中，會評估的電子郵件的各個層面。 包括：
- 可能需有哪些類型的威脅它決定;
- 寄件者; 它
- 其中電子郵件寄件地 （傳送基礎結構）;
- 電子郵件的其他執行個體是否已傳遞或封鎖;
- 從我們分析師; 評估
- 是否任何已知的行銷活動; 相關聯的電子郵件
- 等等。

根調查完成後，playbook 會提供建議的動作，才會在原始的電子郵件和與它相關聯的實體清單。
  
接下來，數個威脅調查並狩獵步驟執行：

- 透過電子郵件叢集搜尋識別類似的電子郵件訊息。
- 其他平台，例如[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)可共用接收的訊號。
- 決定在任何使用者是否按下可疑的電子郵件訊息中任何前往惡意連結。
- 檢查完成跨 Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) 和 Office 365 進階威脅防護 ([ATP](office-365-atp.md))，以查看是否有任何其他類似的訊息報告的使用者。
- 若要查看是否使用者已遭洩露完成查核。 這項檢查跨 Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)，相互關聯任何相關的使用者活動異常運用訊號。 

狩獵階段風險和威脅指派給各種狩獵步驟。 

修復為 playbook 的最後一個階段。 在這個階段，採取補救步驟為止，根據調查和狩獵階段。 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>範例： 安全性系統管理員會觸發從威脅總管調查

除了警示所觸發的自動調查，貴組織的安全性作業小組可以觸發自動進行調查，從[威脅總管](threat-explorer.md)] 中檢視。

例如，假設您正在檢視的資料在檔案總管中關於使用者報告的郵件。 您可以在結果清單中選取項目，然後按一下 [從 （假設您具備適當的補救權限） 的 [動作] 功能表的 [**調查]** 。

![使用者報告中的郵件檔案總管與調查] 按鈕](../../media/Explorer-UserReported-Investigate.png)

另一個範例，假設您正在檢視包含惡意程式碼，偵測到的電子郵件的相關資料，並有幾個偵測為包含惡意程式碼的電子郵件訊息。 您可以選取 [**電子郵件**] 索引標籤，選取一或多個電子郵件訊息，然後在 [**動作**] 功能表上選取 [**調查]**。 

![在檔案總管中開始進行調查，惡意程式碼](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

類似於 playbooks 觸發警示的通知，會觸發從瀏覽器中檢視的自動調查包含根目錄和調查]，以找出並相互關聯的威脅，步驟及建議的動作來減輕這些威脅。

## <a name="how-to-get-air"></a>如何取得航空

Office 365 AIR 現在包含在以下訂閱中：

- Microsoft 365 E5
- Office 365 E5
- Microsoft 威脅防護
- Office 365 進階威脅防護方案 2

如果您不需要任何這些訂閱，[開始免費試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US)。

若要深入了解可用的功能，請造訪[進階威脅防護 (ATP) 計劃的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="required-permissions-to-use-air-capabilities"></a>若要使用空調功能的必要權限

授與權限是透過特定角色，例如，如下表所述： 

|工作 |所需的角色 |
|--|--|
|若要設定空調功能 |下列其中一個下列角色： <br/>- **全域系統管理員**<br/>- **安全性系統管理員** <br/>可以指派這些角色，在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)中或在[Office 365 安全性 & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。 |
|核准或拒絕建議的動作|下列其中一個指派[Office 365 安全性 & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)或[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)中的下列角色）：<br/>- **全域系統管理員** <br/>- **安全性系統管理員**<br/>- **安全性讀取者** <br/>--- 且 ---<br/>- **搜尋及清除**（此角色指派只能在[Office 365 安全性 & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。 您可能必須建立新角色群組，並將 「 搜尋及清除角色新增至該新的角色群組。）

## <a name="next-steps"></a>後續步驟

- [開始使用 Office 365 中的空調](office-365-air.md)

- [造訪 Microsoft 365 藍圖，查看即將推出的功能](https://www.microsoft.com/microsoft-365/roadmap?filters=)

