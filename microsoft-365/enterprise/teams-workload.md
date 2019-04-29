---
title: 部署 Microsoft 365 企業版的 Microsoft Teams
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 推行並發揮 Microsoft 365 企業版 Microsoft Teams 在組織中的價值，規劃這整個程序的步驟。
ms.openlocfilehash: bfc9e76211779aa960ff7633dd7d59b2b01e9f98
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400207"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a>部署 Microsoft 365 企業版的 Microsoft Teams

*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*

Microsoft Teams 將交談、會議、共用文件、往來對話整合在一起，讓您在群組間輕鬆建立及共用內容。Teams 是進行 Microsoft 365 企業版團隊合作和共同作業的工具，是專門為了 Microsoft 365 團隊合作而打造的重要元素。如果您沒用過 Teams，請參閱 [Microsoft Teams 概觀](https://docs.microsoft.com/MicrosoftTeams/teams-overview)。
 
如果您目前使用商務用 Skype，我們正在將商務用 Skype 的功能建置在 Teams 之中。這會在一段時間後完成，Teams 最終會變成單一用戶端體驗。您是重要的商務用 Skype 客戶，Microsoft 在此支援您。如需詳細資訊，請參閱[從商務用 Skype 到 Microsoft Teams 的旅程](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams)。

以下的階段與步驟會帶領您構想 Teams 在組織中的角色，透過一系列的漸進式推行讓組織導入 Teams，並向使用者推廣 Teams 的使用和價值。 

開始之前，請確定您已設定正確的[基礎結構](deploy-foundation-infrastructure.md)階段，您的小組才能具備您需要的安全性功能。

## <a name="phase-1-envision"></a>第 1 階段：構想

在這個階段，您要召集負責 Teams 部署的人員，並決定組織將如何使用 Teams 解決業務需求。

### <a name="step-1-gather-your-teams-deployment-members"></a>步驟 1：召集 Teams 部署成員
為了將 Teams 成功部署在 Microsoft 365 [基本基礎結構](deploy-foundation-infrastructure.md)上，您需要找到適當的人員取得相關想法和意見反應。重點人物包括企業決策者、IT 人員 (如架構與實作者)、使用者提倡者。 

這三種人可確保 Teams 的部署涵蓋各種考量，可以解決業務需求和技術層面的授權與安全性，讓 Teams 成為一般使用者會使用的工具。

#### <a name="result"></a>結果

代表組織的業務、技術、使用者三方面的人員清單。

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a>步驟 2：決定 Teams 商務案例並定立優先順序
Teams 可以用於許多不同的用途。您必須決定哪些用途對應到組織中業務需求、業務群組、部門、個別工作與專案小組的不同層級。如需範例請參閱 [Microsoft 365 生產力文件庫](https://www.microsoft.com/microsoft-365/success/?rtc=1)，來協助您定義 Teams 案例。 

您應該將 Teams 的目標放在處理進展快速且高度共同作業的小組，他們密切合作並需要電子郵件和 Exchange Online 以外的更多功能。像是具有歷程記錄的即時群組聊天、用通用易找的位置儲存檔案和備忘稿。 

看見 Teams 優點的其中一個方法是查看小組或虛擬小組今天的互動，然後找出可取代互動並提供更輕鬆共同作業方式的適當 Teams 案例，再提供額外的功能。

Teams 達成了 Microsoft 365 企業版的這些策略商務案例：

- 與小組溝通以取得最新資訊、要求輸入，並建立凝聚力和共識
- 與第一線員工互動，啟用數位轉型
- 了解您的工作習慣以提升影響力

如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。 

#### <a name="microsoft-teams-for-highly-regulated-data"></a>適用於高管制資料的 Microsoft Teams

高管制資料受限於區域法規，或者是貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。您可以設定小組以進行限制存取、資料分類、資料外洩防護以及此資料類型的加密。如需詳細資訊，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站](teams-sharepoint-online-sites-highly-regulated-data.md)。

#### <a name="result"></a>結果

解決組織共同作業和團隊合作需求的 Teams 案例清單。

## <a name="phase-2-onboard"></a>第 2 階段：導入

在這個階段，規劃 Teams 部署的技術層面，並開始向所選的使用者群組推行 Teams。

### <a name="prerequisites-identity-and-device-access-configuration"></a>必要條件：身分識別與裝置存取設定

若要保護 Teams 的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint Online 存取原則](sharepoint-file-access-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>步驟 1：完成技術規劃

開始技術規劃之前，先決定您是否要使用 FastTrack。如果組織有超過 50 個基座，並參與[合格方案](https://technet.microsoft.com/library/dn783224.aspx)，您可以使用[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) (不另外收費) 來逐步引導您規劃、部署及採用服務。或者，您可以使用我們的「FastTrack 導入精靈」自己完成這項工作，您可以使用 Office 365 帳戶登入，即可從 [FastTrack](https://fasttrack.microsoft.com/) 取得此精靈。

如果您要執行自己的規劃 (或搭配 FastTrack)，必須判斷您的網路和組織是否準備好使用 Teams。請務必符合[基本基礎結構](deploy-foundation-infrastructure.md)的網路允出準則，特別注意頻寬、輸送量、流量延遲，達到以 Teams 舉行會議的最佳效能。

使用以下資源來準備組織推行 Teams 的技術層面： 

- [檢查環境的 Teams 整備程度](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [準備用於 Teams 的網路](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [Office 365 URL 與 IP 位址範圍](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

若要更深入了解 Teams 的安全性，請參閱下列資源：

- [Teams 的安全性與合規性概觀](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [Office 365 群組與 Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [Teams 中的來賓存取](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

接下來，使用這些資源以了解 Teams 授權，以及執行組織的 Teams 設定：

- [Office 365 的 Teams 授權](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [管理使用者對 Microsoft Teams 的存取](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [取得 Microsoft Teams 用戶端](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [開啟 Office 365 組織中的 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [管理 Office 365 組織中的 Microsoft Teams 功能](https://docs.microsoft.com/microsoftteams/enable-features-office-365)

#### <a name="result"></a>結果

您已完成網路、安全性、Office 365 授權的規劃，您已可以開始向組織中所選的群組推行 Teams。

### <a name="step-2-run-an-it-pilot"></a>步驟 2：執行 IT 試驗

在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。在 IT 試驗期間：

- 選擇 IT 試驗參與者可以練習的 Teams 商務案例。請參閱 [Microsoft Teams 快速入門套件](http://microsoft.com/download/56505)中的想法。
- 給試驗參與者一些練習，來測試透過 Teams 進行的聊天、檔案儲存、會議及其他功能。
- 判斷您的變更管理策略，並產生材料來推動整個組織的使用者採用。變更管理的材料可包含電子郵件公告文字、內部訓練計劃、走廊海報和簡報。這些材料向組織宣傳 Teams 相關事宜及其優點，目的是要引發認知和促進使用。請參閱[Microsoft Teams 的變更管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)中的一些想法。
- 讓 IT 試驗參與者根據他們的經驗檢閱變更管理策略的材料。他們可以提供最佳做法的祕訣，以及最能描述 Teams 優點以及如何用於共同作業和團隊合作的建議。

#### <a name="result"></a>結果

完成 Teams 的 IT 試驗，且已經開發、檢閱、精簡首次變更管理的材料。

### <a name="step-3-roll-out-to-a-business-group"></a>步驟 3：推行至商務群組

完成 IT 試驗後，將 Teams 推行至組織中的商務群組或部門。此推行應包含：

- 識別商務群組中的 Teams 重要商務案例。
- 用公告活動通知使用者有關在部門、工作或專案小組使用 Teams 的預期變更和時間表。
- 引導使用者參與 Teams 訓練，或使用介紹 Teams 與用法的資源連結。
- 用意見反應機制 (例如包含商務群組中每個人的中央小組) 收集商務群組使用者的意見和問題。

在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。

#### <a name="result"></a>結果

已使用 Teams 建立並執行商務群組，且已經測試並精簡變更管理的材料。

## <a name="phase-3-drive-value"></a>階段 3：發揮價值

在這個階段，您要將 Teams 推行至組織，並支援使用者讓他們知道其優點。

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a>步驟 1：將 Teams 推行至組織的其他單位

推行至目標商務群組之後，將 Teams 推行至組織中的其他單位。此推行應包含：

- 識別個別商務群組中的 Teams 重要商務案例。
- 在公告活動中使用精簡過的變更管理材料，通知組織有關在部門、工作或專案小組使用 Teams 的預期變更和時間表。
- 提供 Teams 訓練給使用者，或提供介紹 Teams 與用法的資源連結。請參閱 [Microsoft Teams 使用者訓練](https://docs.microsoft.com/microsoftteams/enduser-training)的訓練資源。
- 用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和針對問題採取的行動。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。

#### <a name="result"></a>結果

已使用 Teams 建立並執行組織，且變更管理策略已經準備就緒，可以通知、訓練並讓使用者開始使用 Teams。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>步驟 2：評估使用狀況、管理滿意度、推動採用

將 Teams 推行至整個組織後，您必須繼續使用變更管理策略：

- 讓領導者將 Teams 提升為組織的團隊合作和共同作業的工具。
- 鼓勵個人將 Teams 用於商務群組、部門、工作、專案小組的溝通和共同作業。

以下是一些建議的活動：

- 請參閱 [Office 365 採用指南](https://aka.ms/successfactors)以了解雲端服務採用的一般最佳做法。 
- 請參閱 [Office 365 活動報告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)以了解整個組織的 Office 365 服務用法。如果組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人，讓您可以存取活動報告。
- 監控意見反應區 (中央小組或 Yammer 中的公用通道) 了解個人的使用 Teams 的 問題和意見反應。盡快解決疑問和問題，以避免個人使用 Teams 的挫折感甚至放棄 Teams。
- 在每個商務群組中找出高手並加強培養，強調他們使用 Teams 的成就和最佳做法。在組織中反映出他們的成功，以彰顯專案的成功與採。商務群組技術主管的背書對領導者和同儕有強大的影響。

#### <a name="result"></a>結果

組織已經採用 Teams 作為共同作業和團隊合作的工具。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

若要深入了解 Microsoft 並了解該公司如何部署及使用 Microsoft Teams 進行共同作業，請參閱：

- [部署 Microsoft Teams 可簡化共同作業並提升團隊合作](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [Microsoft Teams 可在 Microsoft 的現代化工作場所增進共同作業](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a>後續步驟

- [管理 Office 365 組織中的 Microsoft Teams 功能](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [Microsoft Teams 的管理訓練](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
