---
title: 部署 Exchange Online Microsoft 365 enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: 逐步解說規劃、 啟用、 及 Microsoft 365 enterprise 驅動的 Exchange Online 值整個組織的程序的步驟。
ms.openlocfilehash: aafa1b28546eb77938bb3e4a5ebe9ccd60b9a60b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866741"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>部署 Exchange Online Microsoft 365 enterprise

Exchange Online 是您的電子郵件的主要雲端服務和行事曆的可幫助您的使用者共同作業不需要即時聊天或集中式文件儲存區的方式。Exchange Online 是您執行個別及小型群組短期通訊及排程並且 Microsoft 365 企業版的團隊合作值的內建的關鍵元素。Exchange Online 可讓您完成多及更有效率地使用已知的 Outlook 應用程式，不論您是在何種裝置。

Exchange Online 也具有進階安全性功能，包括反惡意程式碼和反垃圾郵件篩選保護信箱並防止使用者遭傳送機密資訊給未經授權人士的資料遺失防護功能。Exchange Online 安全性是 Microsoft 365 企業版的智慧型安全性值的關鍵元素。

如果您是全新 Exchange online，請參閱[Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。

下列階段與步驟引導您進行想像變換一系列的漸進式部署至 Exchange Online 組織的 Exchange Online 組織 onboarding 中的角色及驅動的 Exchange Online 的使用狀況的程序和其為一般使用者的值。

>[!Note]
>只有在您完成 Microsoft 365 企業版 foundation 基礎結構的[階段 2-Identity](identity-infrastructure.md)之後應該遵循這些部署指示。
>

## <a name="phase-1-envision"></a>第 1 階段：構想

在此階段中，您收集 Exchange Online 部署的人員，並決定如何組織會使用 Exchange Online 工具來處理其業務需求。

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>步驟 1： 收集您的 Exchange Online 部署成員

成功部署的 Exchange Online 上的[階段 2-Identity](identity-infrastructure.md) Microsoft 365 企業版 foundation 基礎結構的功能，您需要輸入及意見反應取得適當的人員。主要人員包括商業性決策負責人、 IT 人員如架構師和實施者注意事項，以及適用於使用者的代言人。 

這三個群組請確定您的 Exchange Online 部署包含解決的業務需求、 技術方面的信箱移轉與安全性，及結果會是某個項目將會使用一般使用者的考量。

#### <a name="result"></a>結果

代表組織的業務、技術、使用者三方面的人員清單。

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>步驟 2： 決定與 Exchange Online 的商務案例的優先順序

Exchange Online 可用於不同的用途。您必須了解哪些用途對應至您的業務需求的組織、 業務團隊、 部門或個別的工作及專案小組的不同層級上。您應該目標 Exchange Online，以解決您個別及小型群組短期通訊及排程需求。 

請參閱 Exchange Online 的優點的其中一個方法是檢查如何個人、 小組、 或 v 小組 today、 互動，然後尋找適當的案例提供更輕鬆地排程會議和共同作業的方式。請記住[的 Microsoft 小組](teams-workload.md)可能的共同作業案例的一些較佳的選擇。

Exchange Online 達成了 Microsoft 365 企業版的這些策略商務案例：

- 即時或自己運用時間在文件上共同作業，簡化共同建立的程序
- 管理專案、工作和截止日期，達成業務目標
- 了解您的工作習慣以提升影響力
- 與小組溝通以取得最新資訊、要求輸入，並建立凝聚力和共識
- 在組織內外部儲存及共用檔案，順暢地跨越組織界限工作
- 隨時隨地在裝置上安全地工作，以達成更多目標，同時維持彈性的工作方式
- 保護您的資訊，並降低資料遺失風險
- 偵測及防範外部威脅 
- 監控、 報告及分析活動回應立即提供組織的安全性
- 使用增強的隱私權和法規遵循來支援貴組織，以符合一般資料保護規定 (GDPR)

如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。 

#### <a name="result"></a>結果
Exchange Online 解決貴組織的需求為通訊、 排程和短期的共同作業的案例清單。

## <a name="phase-2-onboard"></a>第 2 階段：導入

在此階段中，您的 Exchange Online 部署的技術方面的規劃，並啟動推出至選取的使用者群組。

### <a name="prerequisites-identity-and-device-access-configuration"></a>必要條件：身分識別與裝置存取設定

若要保護 Exchange Online 信箱的存取權，請確定您已設定[身分識別與裝置存取的原則](identity-access-policies.md)和[建議的 Exchange Online 存取原則](secure-email-recommended-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>步驟 1：完成技術規劃

開始技術規劃之前，請決定您是否要使用 FastTrack。如果您的組織有超過 50 基座及參與[合格的計劃](https://technet.microsoft.com/library/dn783224.aspx)中，您可以使用[Microsoft 365 FastTrack](https://fasttrack.microsoft.com/microsoft365)，可在引導您進行規劃、 部署及服務採用任何其他成本。或者，您可以使用 FastTrack Onboarding 精靈一旦您使用 Office 365 帳戶登入，均可在[FastTrack](https://fasttrack.microsoft.com/)自行完成這項工作。

如果您執行的動作您自己的規劃、 或 FastTrack 搭配，您必須決定您的網路和組織是否已準備好用於 Exchange Online。尤為重要 foundation 基礎結構，以特別注意的網際網路頻寬、 輸送量和流量延遲自學針對其他流量的 Exchange 中符合網路允出準則線上式電子郵件和附件。

使用下列資源準備 Exchange Online 的導入的技術方面： 

- [將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Office 365 郵件移轉顧問](https://portal.office.com/onboarding/mailsetupadvisor#/)（必須先登入您的 Office 365 訂閱）
- [Exchange Online 中的協同作業](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Exchange Online 中的收件者](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

搭配成效更深入了解 Exchange Online 中的安全性的檢閱下列資源：

- [Exchange Online 中的權限](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [安全性及規範的 Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [反垃圾郵件和反惡意程式碼防護](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

接下來，了解 Exchange Online 信箱管理使用下列資源：

- [在 Exchange Online 中建立使用者信箱](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [管理使用者信箱](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [建立並管理通訊群組](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>結果

您了解信箱移轉、 安全性和管理並準備開始啟用 Exchange Online 組織中所選群組。

### <a name="step-2-run-an-it-pilot"></a>步驟 2：執行 IT 試驗

在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。在 IT 試驗期間：

- 選擇您的 IT 試驗參與者可以在其中練習 Exchange Online 商務案例。
- Office 365 授權給您的試驗參與者並將其內部部署信箱遷移至 Exchange Online。
- 將授與您的試驗參與者練習測試 Exchange Online 電子郵件、 排程和其他功能。
- 判斷您變更管理策略及產生的 Exchange Online 的磁碟機全組織使用者採用的運送。變更管理教材 （英文） 可以包含電子郵件宣告文字、 內部訓練計劃、 走廊海報與簡報。這些資料會通知您的組織有關 Exchange Online 與及其優點與引發傳達和主導流量的目標。請參閱[變更的 Microsoft 小組管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)的某些概念。
- 請檢閱根據其體驗變更管理教材您 IT 試驗參與者。他們可以提供秘訣最佳作法和建議如何以最佳描述的 Exchange Online 優點及如何使用的通訊及排程。

#### <a name="result"></a>結果

Exchange Online IT 試驗完成且初始變更管理教材 （英文） 已開發方法、 檢閱、 以及精簡。

### <a name="step-3-roll-out-to-a-business-group"></a>步驟 3：推行至商務群組

完成後 IT 試驗，導入 Exchange Online 商務群組或組織中的部門。如果您的組織會使用內部部署電子郵件服務，例如 Exchange Server，此導入包含移轉的信箱。此導入應該包括：

- 識別重要的商務案例的 Exchange Online 的商務群組中。
- 宣告的活動，告知使用者的期望與時間表的 Exchange Online 的部門和公司或專案小組使用。
- 移轉至 Exchange Online 您商務群組成員的內部部署信箱。
- 提供在 Exchange Online 或連結的使用者訓練資源引進 Exchange Online 以及如何使用它。
- 用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。

在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。

#### <a name="result"></a>結果

商務群組已開啟並執行與 Exchange Online 和變更管理教材 （英文） 已測試及精簡。

## <a name="phase-3-drive-value"></a>階段 3：發揮價值

在此階段中，您需要完成的 Exchange Online 導入並支援您的使用者來協助他們瞭解及其優點。

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>步驟 1： 導入 Exchange Online 組織的其餘部分

推行至貴組織其餘單位應包含：

- 識別的主要商務案例的 Exchange Online 內個別業務團隊。
- 使用您精簡的變更管理材料來通知您的組織的期望的宣告活動和時間表的 Exchange Online 使用。
- 移轉至 Exchange Online 組織的其餘使用者的信箱。
- 提供使用者訓練在 Exchange Online 或提供以引進 Exchange Online 以及如何使用它的資源連結。
- 用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。

#### <a name="result"></a>結果

您的組織已開啟並執行與您變更管理策略可隨時通知、 訓練，並讓使用者使用 Exchange Online。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>步驟 2：評估使用狀況、管理滿意度、推動採用

後啟用 Exchange Online 至整個組織，您必須繼續將採用以變更管理策略：

- 已將 Exchange Online 升級個別和短期通訊的主要工具為您領導及排程。
- 鼓勵使用商務群組、 部門、 工作、 個人和專案小組通訊、 行事曆、 及共同作業。

以下是一些建議的活動：

- 請參閱 [Office 365 採用指南](https://aka.ms/successfactors)以了解雲端服務採用的一般最佳做法。 
- 請參閱 [Office 365 系統管理中心的活動報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。
- 監視問題及從其體驗與 Exchange Online 相關的個人的意見反應您的意見反應場所 （中央團隊小組或 Yammer 中的公用通道）。您可以防止挫折的個人及示範以支援導入以快速解決問題與問題。
- 識別及加強冠軍中每個商務群組並反白顯示其完成事項及使用 Exchange Online 的最佳作法。會反映出其成功顯示專案成功和採用組織。依商務群組內的技術主管適用的簽署可以會強大的影響整個負責人和等項目。

#### <a name="result"></a>結果

您的組織已採用 Exchange Online 做為其主要的個別及小型群組短期通訊及排程的工具。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

Microsoft 內鑽入並了解如何在公司移轉至 Exchange Online 及保護網路攻擊使用 Exchange Online Protection，請參閱：

- [Microsoft 會將 150000 個信箱移轉到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft 會使用威脅情報來保護、偵測及回應威脅](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>後續步驟

請參閱 Exchange online 持續的維護這些資源：

- [Exchange Online 中的 Exchange 系統管理中心](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [在 Exchange Online 中監控、報告和執行郵件追蹤](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [在 Exchange Online 中備份電子郵件](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
