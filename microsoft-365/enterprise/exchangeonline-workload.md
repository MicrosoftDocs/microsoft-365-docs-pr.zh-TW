---
title: 部署 Microsoft 365 企業版適用於 Exchange Online
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 逐步說明的規劃、 推行並發揮值的 Exchange Online 中 Microsoft 365 企業版整個組織的程序。
ms.openlocfilehash: 6efd94da7806b6268881f7eaabe5efacc8920f47
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281203"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>部署 Microsoft 365 企業版適用於 Exchange Online

*此工作負載隨附於 Microsoft 365 企業版 E3 和 E5 版本*

Exchange Online 是您的電子郵件的主要雲端服務和行事曆，可協助您的使用者共同作業不需要即時聊天或集中式文件儲存方式。 Exchange Online 是具體做法個別及小型群組短暫的通訊和排程，Microsoft 365 企業版的團隊合作值內建的重要元素。 Exchange Online 可讓您達成更多，並與已知的 Outlook 應用程式，無論您是哪一種裝置更有效率地運作。

Exchange Online 也具有進階安全性功能，包括反惡意程式碼和反垃圾郵件篩選來保護信箱和資料遺失防護功能，防止使用者誤將機密資訊傳送給未經授權的人員。 Exchange Online 安全性是 Microsoft 365 企業版的智慧型安全性值的重要元素。

如果您是 Exchange online 新手，請參閱[Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。

下列階段與步驟逐步引導您想像的 Exchange Online 組織上架中的角色變換一系列的漸進式發行至 Exchange Online 組織並發揮的 Exchange Online 的使用狀況的程序和其您的使用者值。

>[!Note]
>只有在您完成 Microsoft 365 企業版基礎結構的[階段 2-Identity](identity-infrastructure.md)之後，應該遵循下列部署指示。
>

## <a name="phase-1-envision"></a>第 1 階段：構想

在這個階段，您要召集負責 Exchange Online 部署的人員，並決定組織將如何使用 Exchange Online 來解決其商業需求。

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>步驟 1： 收集您的 Exchange Online 部署成員

成功部署的 Exchange Online 上的 Microsoft 365 企業版底層基礎結構的[階段 2-Identity](identity-infrastructure.md) ，您必須取得正確的人員的輸入和意見反應。 主要人員包括商務決策者、 IT 人員，例如架構師和實作者注意事項，與使用者的代言人。 

這三個群組請確定您 Exchange Online 的部署包含解決業務需求、 信箱移轉和安全性、 的技術層面及結果將會發生一般使用者會使用的考量。

#### <a name="result"></a>結果

代表組織的業務、技術、使用者三方面的人員清單。

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>步驟 2： 決定您 Exchange Online 商務案例並優先順序

Exchange Online 可以用於不同用途。 您要找出哪些用途對應至您的業務需求，在您的組織、 您的業務團隊、 部門或個別的工作和專案小組的不同層級上。 您應該針對 Exchange Online，以解決您個別及小型群組短暫通訊和排程需求。 

若要查看 Exchange Online 的好處的其中一個方法是檢查如何個人、 小組成員或 v 小組互動今日，然後尋找適當的案例，提供更容易的方法來進行通訊，排程會議，並進行共同作業。 請記住， [Microsoft Teams](teams-workload.md)可能是比較好的選擇，某些共同作業案例。

Exchange Online 達成版 Microsoft 365 企業版的這些策略商務案例：

- 即時或自己運用時間在文件上共同作業，簡化共同建立的程序
- 管理專案、工作和截止日期，達成業務目標
- 了解您的工作習慣以提升影響力
- 與小組溝通以取得最新資訊、要求輸入，並建立凝聚力和共識
- 在組織內外部儲存及共用檔案，順暢地跨越組織界限工作
- 隨時隨地在裝置上安全地工作，以達成更多目標，同時維持彈性的工作方式
- 保護您的資訊，並降低資料遺失風險
- 偵測並防範外部威脅 
- 監控、 報告及分析活動，以回應迅速提供組織的安全性
- 使用增強的隱私權和法規遵循來支援貴組織，以符合一般資料保護規定 (GDPR)

如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。 

#### <a name="result"></a>結果
Exchange Online 案例，能解決貴組織的需求為通訊、 排程及短暫的共同作業清單。

## <a name="phase-2-onboard"></a>第 2 階段：導入

在這個階段，規劃的 Exchange Online 部署的技術層面，然後開始向所選的使用者群組推行。

### <a name="prerequisites-identity-and-device-access-configuration"></a>必要條件：身分識別與裝置存取設定

若要保護 Exchange Online 信箱的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 Exchange Online 存取原則](secure-email-recommended-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>步驟 1：完成技術規劃

在您開始技術規劃之前，請決定您是否要使用 FastTrack。 如果您的組織有超過 50 個基座，並參與[符合資格的方案](https://technet.microsoft.com/library/dn783224.aspx)，您可以使用[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)，可用以引導您進行規劃、 部署及服務採用沒有額外的費用。 或者，您可以使用 FastTrack 上架精靈]，也就是可從[FastTrack](https://fasttrack.microsoft.com/) ，一旦您使用您的 Office 365 帳戶登入自行完成這項工作。

如果您編寫自己的規劃，或與 FastTrack 一起使用，您需要判斷您的網路和組織是否準備好進行 Exchange Online。 請務必特別是在您的基礎，具有特別注意的網際網路頻寬、 輸送量及流量延遲，以達到最佳效能的其他流量的 exchange 中符合網路的允出準則線上架構之電子郵件和附件。

使用這些資源來準備 Exchange Online 推行的技術層面： 

- [將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [共同作業中 Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Exchange Online 中的收件者](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

進一步了解 Exchange Online 中的安全性，請先檢閱下列資源：

- [權限在 Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [安全性與合規性的 Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [反垃圾郵件和反惡意程式碼防護](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

接下來，使用這些資源來了解 Exchange Online 信箱管理：

- [在 Exchange Online 中建立使用者信箱](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [管理使用者信箱](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [建立並管理通訊群組](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>結果

您了解信箱移轉、 安全性和管理，並準備好要開始推出 Exchange Online 至組織中選取的群組。

### <a name="step-2-run-an-it-pilot"></a>步驟 2：執行 IT 試驗

在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。在 IT 試驗期間：

- 選擇 [Exchange Online 的商務案例，您的 IT 試驗參與者可以加以練習。
- Office 365 授權給試驗參與者，並將其內部部署信箱遷移至 Exchange Online。
- 給試驗參與者一些練習，來測試 Exchange Online 電子郵件、 排程及其他功能。
- 判斷您的變更管理策略，並產生的 Exchange Online 的磁碟機全組織的使用者採用的材料。 電子郵件通知文字、 內部訓練計劃、 走廊海報與簡報，可以包含的變更管理材料。 這些資料會通知組織有關 Exchange Online 和以目標引發認知和主導流量及其優點。 請參閱[變更管理策略的 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)一些想法。
- 需要 IT 試驗參與者檢閱變更管理的材料根據其體驗。 他們可以提供的祕訣最佳作法和建議如何以最佳說明 Exchange Online 的優點，以及如何用它來進行通訊，以及排程。

#### <a name="result"></a>結果

Exchange Online 的 IT 試驗完成且次變更管理材料已開發、 檢閱、 並精簡。

### <a name="step-3-roll-out-to-a-business-group"></a>步驟 3：推行至商務群組

完成後您的 IT 試驗，推出 Exchange Online 商務群組或組織中的部門。 如果您的組織使用內部部署電子郵件服務，例如 Exchange Server，此導入包含移轉的信箱。 此導入應包含：

- 識別重要商務案例的 Exchange Online 商務群組中。
- 用公告活動通知使用者的預期變更和時間表部門及工作或專案小組的 Exchange Online 使用。
- 移轉至 Exchange Online 商務群組成員的內部部署信箱。
- 提供在 Exchange Online 或連結的使用者訓練資源介紹 Exchange Online 和如何加以使用。
- 用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。

在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。

#### <a name="result"></a>結果

商務群組，且和執行與 Exchange Online 變更管理的材料已測試並精簡。

## <a name="phase-3-drive-value"></a>階段 3：發揮價值

在這個階段，您完成推出 Exchange Online，並支援您的使用者，以協助他們了解其優點。

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>步驟 1： 推行 Exchange Online 組織的其餘部分

推行至貴組織其餘單位應包含：

- 識別重要商務案例的 Exchange Online 中的個別商務群組。
- 使用精簡的變更管理的材料公告活動通知貴組織的預期變更和時間表的 Exchange Online 使用。
- 移轉至 Exchange Online 組織的其餘部分的信箱。
- 提供使用者訓練在 Exchange Online，或提供的資源介紹 Exchange Online，以及如何使用它的連結。
- 用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。

#### <a name="result"></a>結果

您的組織已啟動並執行和變更管理策略已經準備就緒，可以通知、 訓練並讓使用者使用 Exchange Online。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>步驟 2：評估使用狀況、管理滿意度、推動採用

推行後 Exchange Online 至整個組織，您必須繼續使用變更管理策略：

- 讓領導者將 Exchange Online 升級為主要工具，進行個別和短暫的通訊和排程。
- 鼓勵個人將它用於商務群組、 部門、 工作和專案小組的溝通、 行事曆、 和共同作業。

以下是一些建議的活動：

- 請參閱 [Office 365 採用指南](https://aka.ms/successfactors)以了解雲端服務採用的一般最佳做法。 
- 請參閱 [Office 365 系統管理中心的活動報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。
- 監視您的意見反應場所 （中央 microsoft Teams 小組或 Yammer 中的公用通道） 問題與從他們的經驗與 Exchange Online 相關的個人的意見反應。 您可以防止迷惑的個人與示範首度發行的支援，快速解決問題。
- 識別並加強冠軍每個商務群組中的，並反白顯示其成就和使用 Exchange Online 的最佳作法。 反映出其成功至組織，以顯示專案成功和採用率。 依商務群組內的技術主管適用的背書可以會強大的影響整個負責人及其等項目。

#### <a name="result"></a>結果

貴組織已採用 Exchange Online 做為其主要的個別及小型群組短暫的通訊和排程的工具。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

一窺 Microsoft 並了解公司如何移轉至 Exchange Online 及使用 Exchange Online Protection 來防範網路攻擊，請參閱：

- [Microsoft 會將 150000 個信箱移轉到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft 會使用威脅情報來保護、偵測及回應威脅](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>後續步驟

請參閱 Exchange Online 的持續維護這些資源：

- [Exchange Online 中的 Exchange 系統管理中心](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [監控、 報告和 Exchange Online 中的郵件追蹤](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [備份電子郵件在 Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
