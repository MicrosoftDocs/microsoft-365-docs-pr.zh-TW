---
title: 部署 Microsoft 365 Enterprise 的 Exchange Online
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 逐步完成規劃、將 Exchange Online 的價值放入組織中的 Microsoft 365 企業版的程式。
ms.openlocfilehash: 9214796c37e9cb5ca9fcb07ced5db7efd8e0f7d0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634143"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>部署 Microsoft 365 Enterprise 的 Exchange Online

*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*

Exchange Online 是您主要的電子郵件和行事曆雲端服務，可協助讓使用者以不需要即時聊天或集中化文件儲存區的方式進行共同作業。 Exchange Online 是 Microsoft 365 企業版的專為團隊合作價值的重要元素。 Exchange Online 可讓您在眾所周知的 Outlook 應用程式（不論您在哪個裝置上），以更有效率地完成工作。

Exchange Online 也有可保護信箱的進階安全性功能 (包括反惡意程式碼和反垃圾郵件篩選)，以及可防止使用者將敏感資訊誤傳給未經授權人員的資料外洩防護功能。 Exchange Online 安全性是 Microsoft 365 企業版之智慧安全性值的重要元素。

如果您從未使用過 Exchange Online，請參閱 [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。

下列階段和步驟會引導您完成構思組織中的 Exchange Online 角色的程式，透過一系列漸進式推廣，將組織加入 Exchange Online，並推動 Exchange Online 和其對您的使用者的價值。

>[!Note]
>只有在完成[Microsoft 365 Enterprise foundation 基礎結構的階段 2](identity-infrastructure.md)之後，才應該遵循這些部署指示。
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>階段1：構想您的 Exchange Online 部署

在此階段中，您會收集 Exchange Online 部署的人員，並決定組織將如何使用 Exchange Online 來滿足其業務需求。

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>步驟1：收集您的 Exchange Online 部署成員

若要在 Microsoft 365 Enterprise foundation 基礎結構的[第2階段](identity-infrastructure.md)（身分識別）上成功部署 Exchange Online，您需要收集適當的人員來輸入與意見反應。 主要人員包括業務決策者、IT 人員（如架構師與實施者），以及對您的使用者的支援。 

這三個群組可確保您的 Exchange Online 部署包含滿足業務需求的考慮、信箱遷移和安全性的技術層面，以及結果是一般使用者會使用的內容。

#### <a name="result"></a>結果

代表組織的業務、技術、使用者三方面的人員清單。

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>步驟2：決定 Exchange Online 商務案例並設定其優先順序

Exchange Online 可用於不同的目的。 您需要瞭解哪些目的對應到您的業務需求，取決於您組織的各個層級、業務群組、部門或個別的工作和專案小組。 您應以 Exchange Online 為目標，以解決您的個人和小群組短暫的通訊和排程需求。 

查看 Exchange Online 效益的方法之一，是檢查個人、小組或 app-v 團隊的互動方式，然後尋找適當的案例，以提供更輕鬆的通訊、排程會議及共同作業的方式。 請記住， [Microsoft 小組](teams-workload.md)可能是一些共同作業案例的更佳選擇。

#### <a name="result"></a>結果
Exchange Online 案例的清單，可滿足您組織的通訊、排程和短期共同作業的需求。

## <a name="phase-2-onboard"></a>第 2 階段：導入

在此階段中，您會規劃 Exchange Online 部署的技術層面，然後開始向所選的使用者群組進行尋找。

### <a name="prerequisites-identity-and-device-access-configuration"></a>必要條件：身分識別與裝置存取設定

若要保護對 Exchange Online 信箱的存取，請確定您已設定身分[識別與裝置存取原則](identity-access-policies.md)和[建議的 Exchange Online 存取原則](secure-email-recommended-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>步驟 1：完成技術規劃

開始技術規劃之前，請先決定是否要使用 FastTrack。 如果您的組織有超過50的席位，且已參與[合格的計畫](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)，您可以使用[Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)，而*無需額外成本*，就能引導您規劃、部署和服務採用。 或者，您可以使用 FastTrack 導入精靈來完成這項工作，只要您使用 Microsoft 365 帳戶登入後，就能從 [FastTrack](https://fasttrack.microsoft.com/) 使用該精靈。

如果您要進行自己的規劃，或與 FastTrack 搭配使用，您必須判斷您的網路和組織是否準備好進行 Exchange Online。 針對連接至組織網路的使用者，您必須符合基礎結構中的[網路](networking-infrastructure.md)出口標準，這一點尤為重要。 特別注意網際網路頻寬、輸送量和流量延遲，以最大程度提高 Exchange Online 電子郵件和附件的流量效能。

您可以使用這些資源來準備 Exchange Online 部署的技術層面： 

- [將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [將 Exchange Server 公用資料夾遷移至 Exchange Online](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [將 Exchange Server 公用資料夾遷移至 Microsoft 365 群組](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [Exchange Online 中的協同作業](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Exchange Online 中的收件者](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [Outlook for iOS 和 Android](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

如需更深入瞭解 Exchange Online 中的安全性，請參閱下列資源：

- [Exchange Online 中的權限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [Exchange Online 的安全性和合規性](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [反垃圾郵件和反惡意程式碼防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

接下來，使用這些資源來瞭解 Exchange Online 信箱管理：

- [在 Exchange Online 中建立使用者信箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [管理使用者信箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [建立並管理通訊群組](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>結果

您瞭解信箱遷移、安全性和管理，並準備好開始將 Exchange Online 推出至組織中所選的群組。

### <a name="step-2-run-an-it-pilot"></a>步驟 2：執行 IT 試驗

對於大部分的大中型組織，您應該對您的專案關係人，從第1階段、早期的使用方式和技術愛好者執行 IT 試驗。 在 IT 試驗期間：

- 向您的試驗參與者提供 Microsoft 365 授權，並將其內部部署信箱遷移至 Exchange Online。
- 為您的試驗參與者提供一組練習，以測試 Exchange Online 電子郵件、排程和其他功能。
- 決定您的變更管理策略，並產生材料，以促進整個組織的使用者採用 Outlook 和 Exchange Online。 
 
  變更管理資料可包含電子郵件公告文字、內部訓練計畫、走道海報和簡報。 這些材料會將 Exchange Online 和其優點告知組織，以提出意識和驅車使用的目的。 如需一些創意，請參閱[Microsoft 小組文章的變更管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)。

- 讓您的 IT 試驗參與者根據經驗審查變更管理資料。 他們可以提供最佳作法和建議的秘訣，以最大的方式描述 Outlook 和 Exchange Online 的優點，以及如何使用它來進行通訊和排程。

#### <a name="result"></a>結果

您的 Exchange Online IT 試驗已完成，而且最初的變更管理材料已開發、評審及完善。

### <a name="step-3-roll-out-to-a-business-group"></a>步驟 3：推行至業務小組

完成您的 IT 試驗後，請將 Exchange Online 向組織中的公司群組或部門推出。 如果您的組織使用內部部署電子郵件服務（例如 Exchange Server），此首展會包含信箱遷移。 這個推行應包括：

- 識別商務群組內的 Exchange Online 重要商務案例。
- 宣告活動，告知使用者對部門和工作或專案小組的 Exchange Online 使用方式的預期和時程表。
- 將商務群組成員的內部部署信箱遷移至 Exchange Online。
- 在 Outlook 上提供[使用者訓練](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)，或介紹如何使用 outlook 的資源連結。
- 用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。

在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。

#### <a name="result"></a>結果

使用 Outlook 和 Exchange Online 來啟動和執行商務群組，且已測試並精簡變更管理的材料。

## <a name="phase-3-drive-value"></a>第 3 階段：發揮價值

在此階段中，您會完成 Exchange Online 的展示，並支援您的使用者，以協助他們實現其優點。

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>步驟1：向組織的其餘部分推出 Exchange Online

推行至貴組織其餘單位應包含：

- 在個別商務群組中識別 Exchange Online 的主要商務案例。
- 使用您精緻的變更管理材料進行宣告活動，告知組織 Exchange Online 使用的預期和時程表。
- 將組織中其他組織的信箱遷移至 Exchange Online。
- 在 Outlook 中傳送[使用者訓練](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)或提供資源連結，以引進 outlook 及其使用方式。
- 用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。

#### <a name="result"></a>結果

您的組織已啟動並執行，您的變更管理策略已到位，可通知、訓練及啟用使用者使用 Exchange Online。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>步驟 2：評估使用狀況、管理滿意度、推動採用

將 Exchange Online 向整個組織推出後，您必須繼續使用變更管理策略：

- 讓您的領導能力將 Exchange Online 提升為主要工具，以進行個別及短期限的通訊和排程。
- 鼓勵個人使用它進行商務群組、部門、工作和專案小組通訊、行事曆和共同作業。

以下是一些建議的活動：

- 請參閱[Microsoft 365 的成功要素](https://aka.ms/successfactors)，以瞭解雲端服務採用的一般最佳作法。 
- 請參閱系統[管理中心的 Microsoft 365 報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以瞭解整個組織的服務使用方式。 如果您不是組織的全域系統管理員，請要求全域系統管理員將報告讀取者許可權授與您的使用者帳戶，這樣您就可以存取活動報告。
- 監視您的意見反應（一個中央小組小組或 Yammer 中的公用通道），以取得來自 Exchange Online 經驗之人員的問題和意見反應。 快速解決問題，避免使用者在使用上感到挫折，並展現出對推行的支援。
- 在每個業務群組中識別並 nurture 冠軍，並使用 Outlook 強調其最佳作法。 向組織反映他們的成功，以顯示專案的成功和導入成效。 由公司群組內的技術領導者認可哥對領導者和對等專案產生強大的影響。

#### <a name="result"></a>結果

您的組織已採用 Exchange Online 和 Outlook 作為主要個人和小群組短壽命的通訊和排程工具。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

若要在 Microsoft 中查看並瞭解如何遷移至 Exchange Online，以及如何使用 Exchange Online Protection 來防禦網路攻擊，請參閱：

- [Microsoft 會將 150000 個信箱移轉到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft 會使用威脅情報來保護、偵測及回應威脅](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>後續步驟

請參閱下列資源，以進行 Exchange Online 的日常維護：

- [Exchange Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [Exchange Online 中的監控、報告和郵件追蹤](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [在 Exchange Online 中備份電子郵件](https://docs.microsoft.com/exchange/back-up-email) 
