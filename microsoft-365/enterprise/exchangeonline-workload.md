---
title: 部署 Microsoft 365 企業版適用於 Exchange Online
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
description: 逐步說明的規劃、 推行並發揮值的 Exchange Online 中 Microsoft 365 企業版整個組織的程序。
ms.openlocfilehash: 30ba71fbf2af684afbbffe0a2e2b1720a8eeec2c
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453859"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>部署 Microsoft 365 企業版適用於 Exchange Online

*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*

Exchange Online 是您主要的電子郵件和行事曆雲端服務，可協助讓使用者以不需要即時聊天或集中化文件儲存區的方式進行共同作業。 Exchange Online 會針對 Microsoft 365 企業版的團隊合作值內建的重要元素。 Exchange Online 可讓您達成更多，並與已知的 Outlook 應用程式，無論您是哪一種裝置更有效率地運作。

Exchange Online 也有可保護信箱的進階安全性功能 (包括反惡意程式碼和反垃圾郵件篩選)，以及可防止使用者將敏感資訊誤傳給未經授權人員的資料外洩防護功能。 Exchange Online 安全性是 Microsoft 365 企業版的智慧型安全性值的重要元素。

如果您從未使用過 Exchange Online，請參閱 [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。

下列階段與步驟逐步引導您想像的 Exchange Online 組織上架中的角色變換一系列的漸進式發行至 Exchange Online 組織並發揮的 Exchange Online 的使用狀況的程序和其您的使用者值。

>[!Note]
>您已完成[階段 2-的身分識別的 Microsoft 365 企業版底層基礎結構](identity-infrastructure.md)之後，才應該遵循下列部署指示。
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>第 1 階段： 構想 Exchange Online 部署

在這個階段，您要召集負責 Exchange Online 部署的人員，並決定組織將如何使用 Exchange Online 來解決其商業需求。

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>步驟 1： 收集您的 Exchange Online 部署成員

適用於成功部署的 Exchange Online 上的 Microsoft 365 企業版底層基礎結構的[階段 2-Identity](identity-infrastructure.md) ，您需要收集的輸入和意見反應正確的人員。 主要人員包括商務決策者、 IT 人員，例如架構師和實作者注意事項，與使用者的代言人。 

這三個群組請確定您 Exchange Online 的部署包含解決業務需求、 技術方面的信箱移轉及安全性]，和結果是某個項目會使用一般使用者的考量。

#### <a name="result"></a>結果

代表組織的業務、技術、使用者三方面的人員清單。

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>步驟 2： 決定您 Exchange Online 商務案例並優先順序

Exchange Online 可以用於不同用途。 您要找出哪些用途對應至您的業務需求，在您的組織、 您的業務團隊、 部門或個別的工作和專案小組的不同層級上。 您應該針對 Exchange Online，以解決您個別及小型群組短暫通訊和排程需求。 

若要查看 Exchange Online 的好處的其中一個方法是檢查如何個人、 小組成員或 v 小組互動今日，然後尋找適當的案例，提供更容易的方法來進行通訊，排程會議，並進行共同作業。 請記住， [Microsoft Teams](teams-workload.md)可能是比較好的選擇，某些共同作業案例。

#### <a name="result"></a>結果
Exchange Online 案例，能解決貴組織的需求為通訊、 排程及短暫的共同作業清單。

## <a name="phase-2-onboard"></a>第 2 階段：導入

在這個階段，規劃的 Exchange Online 部署的技術層面，然後開始向所選的使用者群組推行。

### <a name="prerequisites-identity-and-device-access-configuration"></a>必要條件：身分識別與裝置存取設定

若要保護 Exchange Online 信箱的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 Exchange Online 存取原則](secure-email-recommended-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>步驟 1：完成技術規劃

開始技術規劃之前，請先決定是否要使用 FastTrack。 如果您的組織有超過 50 個基座，並參與[符合資格的方案](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)，您可以使用[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)，*沒有額外的費用可*引導您完成規劃、 部署及服務採用。 或者，您可以使用 FastTrack 導入精靈來完成這項工作，只要您使用 Microsoft 365 帳戶登入後，就能從 [FastTrack](https://fasttrack.microsoft.com/) 使用該精靈。

如果您編寫自己的規劃，或與 FastTrack 一起使用，您需要判斷您的網路和組織是否準備好進行 Exchange Online。 請務必特別是您在 [連線到您組織網路的使用者在基本基礎結構符合[網路](networking-infrastructure.md)的允出準則。 請特別注意網際網路頻寬、 輸送量及流量延遲，以最佳化效能的其他流量的 Exchange Online 式電子郵件和附件。

使用這些資源來準備 Exchange Online 推行的技術層面： 

- [將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [將 Exchange Server 公用資料夾遷移至 Exchange Online](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [Exchange Server 公用資料夾移轉到 Office 365 群組](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [共同作業中 Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Exchange Online 中的收件者](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [Outlook for iOS 和 Android](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

進一步了解 Exchange Online 中的安全性，請先檢閱下列資源：

- [Exchange Online 中的權限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [安全性與合規性的 Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [反垃圾郵件和反惡意程式碼防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

接下來，使用這些資源來了解 Exchange Online 信箱管理：

- [在 Exchange Online 中建立使用者信箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [管理使用者信箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [建立並管理通訊群組](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>結果

您了解信箱移轉、 安全性和管理，並準備好要開始推出 Exchange Online 至組織中選取的群組。

### <a name="step-2-run-an-it-pilot"></a>步驟 2：執行 IT 試驗

針對最中型和大型的組織，您應該從階段 1、 早期採納者和技術愛好者 IT 試驗執行與專案關係人。 在 IT 試驗期間：

- 給試驗參與者 Microsoft 365 授權，並將其內部部署信箱遷移至 Exchange Online。
- 給試驗參與者一些練習，來測試 Exchange Online 電子郵件、 排程及其他功能。
- 判斷您的變更管理策略，並產生到 Outlook 和 Exchange Online 的全組織的使用者採用的材料。 
 
  變更管理資料可包含電子郵件公告文字、內部訓練計畫、走道海報和簡報。 這些資料會通知組織有關 Exchange Online 和以目標引發認知和主導流量及其優點。 請參閱[變更管理策略的 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)一些想法。

- 讓您的 IT 試驗參與者根據經驗審查變更管理資料。 他們可以提供的祕訣最佳作法和建議如何以最佳說明 Outlook 與 Exchange Online 的優點，以及如何用它來進行通訊，以及排程。

#### <a name="result"></a>結果

Exchange Online 的 IT 試驗完成且次變更管理材料已開發、 檢閱、 並精簡。

### <a name="step-3-roll-out-to-a-business-group"></a>步驟 3：推行至業務小組

完成後您的 IT 試驗，推出 Exchange Online 商務群組或組織中的部門。 如果您的組織使用內部部署電子郵件服務，例如 Exchange Server，此導入包含移轉的信箱。 這個推行應包括：

- 識別重要商務案例的 Exchange Online 商務群組中。
- 用公告活動通知使用者的預期變更和時間表部門及工作或專案小組的 Exchange Online 使用。
- 移轉至 Exchange Online 商務群組成員的內部部署信箱。
- 提供在 Outlook 或連結的[使用者訓練](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)資源介紹 Outlook 和如何加以使用。
- 用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。

在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。

#### <a name="result"></a>結果

商務群組，且和執行與 Outlook 和 Exchange Online 變更管理的材料已測試並精簡。

## <a name="phase-3-drive-value"></a>第 3 階段：發揮價值

在這個階段，您完成推出 Exchange Online，並支援您的使用者，以協助他們了解其優點。

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>步驟 1： 推行 Exchange Online 組織的其餘部分

推行至貴組織其餘單位應包含：

- 識別重要商務案例的 Exchange Online 中的個別商務群組。
- 使用精簡的變更管理的材料公告活動通知貴組織的預期變更和時間表的 Exchange Online 使用。
- 移轉至 Exchange Online 組織的其餘部分的信箱。
- Outlook 提供[使用者訓練](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)或提供的資源介紹 Outlook，以及如何使用它的連結。
- 用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。

#### <a name="result"></a>結果

您的組織已啟動並執行和變更管理策略已經準備就緒，可以通知、 訓練並讓使用者使用 Exchange Online。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>步驟 2：評估使用狀況、管理滿意度、推動採用

推行後 Exchange Online 至整個組織，您必須繼續使用變更管理策略：

- 讓領導者將 Exchange Online 升級為主要工具，進行個別和短暫的通訊和排程。
- 鼓勵個人將它用於商務群組、 部門、 工作和專案小組的溝通、 行事曆、 和共同作業。

以下是一些建議的活動：

- 請參閱 [Office 365 的成功要素](https://aka.ms/successfactors) (英文) 以了解雲端服務導入的一般最佳做法。 
- 請參閱 [Office 365 系統管理中心的活動報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。
- 監視您的意見反應場所 （中央 microsoft Teams 小組或 Yammer 中的公用通道） 問題與從他們的經驗與 Exchange Online 相關的個人的意見反應。 快速解決問題，避免使用者在使用上感到挫折，並展現出對推行的支援。
- 識別並加強冠軍每個商務群組中的，並反白顯示其使用 Outlook 的最佳作法。 向組織反映他們的成功，以顯示專案的成功和導入成效。 依商務群組內的技術主管適用的背書可以會強大的影響整個負責人及其等項目。

#### <a name="result"></a>結果

貴組織已採用 Exchange Online 和 Outlook，為其主要的個別及小型群組短暫的通訊和排程的工具。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

一窺 Microsoft 並了解我們如何移轉至 Exchange Online 及使用 Exchange Online Protection 防範網路攻擊，請參閱：

- [Microsoft 會將 150000 個信箱移轉到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft 會使用威脅情報來保護、偵測及回應威脅](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>後續步驟

請參閱 Exchange Online 的持續維護這些資源：

- [Exchange Online 中的 Exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [監控、 報告和 Exchange Online 中的郵件追蹤](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [備份電子郵件在 Exchange Online](https://docs.microsoft.com/exchange/back-up-email) 
