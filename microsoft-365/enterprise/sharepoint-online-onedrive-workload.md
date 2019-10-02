---
title: 部署適用於 Microsoft 365 企業版的 SharePoint 和 OneDrive
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 推行並發揮 SharePoint 在組織中的價值，規劃這整個程序的步驟。
ms.openlocfilehash: d8a61a6bc6b4dae431d94e7ccfb9fb0ea8019427
ms.sourcegitcommit: a77c4889c5b7d3b8f16e74917079300e8f222941
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2019
ms.locfileid: "37329202"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>部署適用於 Microsoft 365 企業版的 SharePoint 和 OneDrive

*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*

當您進行檔案儲存與共用、內容管理及共同作業時，SharePoint 和 Microsoft Teams 就是您的最佳選擇，也是打造 Microsoft 365 企業版團隊合作價值的重要元素。 

SharePoint 也具有進階的安全性功能，包括存取控制和權限，以及動態和靜態加密。SharePoint 安全性是 Microsoft 365 企業版情報安全性價值的重要元素。

如果您是 SharePoint 新手，請參閱 [SharePoint ](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 與 [SharePoint 快速入門](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics)。

以下的階段與步驟會帶領您構想 SharePoint 在貴組織中的角色，透過一系列的漸進式推行讓組織導入，並向使用者推廣其使用價值。 開始之前，請確定您已設定正確的[基礎結構](deploy-workloads.md#foundation-infrastructure-prerequisites)階段，您的 SharePoint 網站才能具備您需要的安全性功能。 

若要部署適用於 Microsoft 365 企業版的 OneDrive，請參閱[適用於企業的 OneDrive 指南](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。

## <a name="phase-1-envision"></a>第 1 階段：構想
在這個階段，您要召集負責 SharePoint 部署的組織夥伴，並決定組織將如何使用 SharePoint 來解決業務需求。

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>步驟 1：召集 SharePoint 部署成員

為了將 SharePoint 成功部署在 [Microsoft 365 企業版基礎結構](deploy-foundation-infrastructure.md)上，您需要找到適當的人員，以獲得相關想法和意見反應。關鍵人員包括企業決策者、IT 人員 (如架構師與實作者) 以及使用者提倡者。 

這三種人員可確保部署涵蓋各種考量，從而解決業務需求和技術層面的資料夾和文件移轉與安全性，讓結果成為一般使用者會使用的工具。

#### <a name="result"></a>結果

分別代表組織的業務、技術、使用者這三方面的人員清單。

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>步驟 2：決定 SharePoint 商務案例並訂定優先順序

SharePoint 可用於不同的用途。您必須判斷哪些用途對應到您的業務需求。您應該將 SharePoint 的重點放在解決小組、部門或整個組織的文件儲存與共用、內容管理及共同作業的需求。 

您可在 [SharePoint](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 中查看案例和功能清單。

下列商務要點可解決貴組織的需求：

|||
|:-----|:-----|
| 共用和共同作業 | 利用小組網站、共同作業網站及同步處理。 |
| 通知並保持互動 | 未來的資訊傳入。 |
| 轉換 | 使用流程來建立儲存區或工作流程。 |
| 充分利用集體知識 | 使用搜尋來授與貴組織所需的結果。 |
| 保護 | 確保貴組織受到保護，且有正確的規範。 |
| 外部/開發 | 讓組織使用 SharePoint 架構來開發自訂解決方案和應用程式。 |
|||

請參閱 [SharePoint 系統管理](https://docs.microsoft.com/sharepoint/sharepoint-online)，取得如何依需求設定 SharePoint 的資源。

要查看 SharePoint 優點的其中一個方法，是檢查個人、小組、部門或整個組織現今互動的方式，並找出適當的案例，提供更輕鬆的方法來儲存及共用檔案。請注意，[Microsoft Teams](teams-workload.md) 對您部分的案例而言可能是較好的選擇。

#### <a name="sharepoint-site-for-highly-regulated-data"></a>適用於高度管制資料的 SharePoint 網站

高度管制資料受地區法規約束，或者是您組織中最有價值的資料，例如營業機密、財務或人力資源資訊以及組織策略。 您可以針對此類型的資料，設定 SharePoint 網站進行限制存取、資料分類、資料遺失防護和加密。 如需詳細資料，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint 網站](teams-sharepoint-online-sites-highly-regulated-data.md)。

#### <a name="result"></a>結果
SharePoint 的案例清單，能解決組織對於文件儲存與共用、內容管理、共同作業與安全性的需求。

## <a name="phase-2-onboard"></a>第 2 階段：導入

在這個階段，您會規劃 SharePoint 部署的技術層面，然後開始向所選的使用者群組推行。

### <a name="prerequisites-identity-and-device-access-configuration"></a>必要條件：身分識別與裝置存取設定

若要保護 SharePoint 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint 存取原則](sharepoint-file-access-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>步驟 1：完成技術規劃

開始技術規劃之前，請先決定是否要使用 FastTrack。 如果貴組織擁有超過 50 個基座，且參與[合格方案](https://technet.microsoft.com/library/dn783224.aspx)，您可以使用 FastTrack 權益而無需額外費用，它可引導您完成規劃、移轉、部署及服務導入。 或者，您可以使用 FastTrack 導入精靈來完成這項工作，只要您使用 Microsoft 365 帳戶登入後，就能從 [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) 使用該精靈。

如果您要自行規劃，或者搭配 FastTrack 使用，則需要確定您的網路和組織是否已準備好使用 SharePoint。 請務必符合基礎結構的網路允出準則，特別注意網際網路頻寬、輸送量、流量延遲，以達到可用於 SharePoint 型文件其他流量的最佳效能。

您可以使用以下資源來準備推行 SharePoint 的技術層面工作： 

- [SharePoint 規劃指南](https://docs.microsoft.com/sharepoint/planning-guide)
- [移轉至 SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

如需更深入了解 SharePoint 的安全性，請檢閱下列資源：

-   [SharePoint 和 OneDrive 如何保護您在雲端的資料](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [OneDrive 和 SharePoint 中的資料加密](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo) (機器翻譯)

#### <a name="result"></a>結果

您了解 SharePoint 網站和內部部署資料夾與文件移轉及安全性，並準備好開始將 SharePoint 推出至貴組織中的指定群組。

### <a name="step-2-run-an-it-pilot"></a>步驟 2：執行 IT 試驗

在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。 在 IT 試驗期間：

- 選擇 SharePoint 商務案例，讓您的 IT 試驗參與者可以加以練習。
- 為試驗參與者提供一組練習，來測試 SharePoint 文件儲存、共用、共同作業、小組排程，以及其他功能。
- 決定您的變更管理策略，並製作可提升整個組織使用者採用 SharePoint 的資料。 變更管理資料可包含電子郵件公告文字、內部訓練計畫、走道海報和簡報。 這些資料可將 SharePoint 及其優點通報給您的組織，以提高認知度並推動使用。 請參閱 [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) 的變更管理策略文章，以取得一些想法。
- 讓您的 IT 試驗參與者根據經驗審查變更管理資料。 他們可以提供最佳做法的秘訣，以及如何最貼切地描述 SharePoint 的優點和使用方法。

#### <a name="result"></a>結果

您已完成 SharePoint 的 IT 試驗，並已開發、審核、調整首次變更管理的資料。

### <a name="step-3-roll-out-to-a-business-group"></a>步驟 3：推行至業務小組

完成 IT 試驗後，將 SharePoint 推行至貴組織中的業務小組或部門。 這個推行應包括：

- 識別不同業務小組中，SharePoint 的重要業務案例。
- 透過公告活動通知使用者在部門及工作或專案團隊中使用 SharePoint 的相關事先通知和時間表。
- 業務小組成員的內部部署資料夾和文件移轉到 SharePoint。
- 提供使用者訓練或資源連結，以介紹 SharePoint 及其使用方式。 請參閱 [SharePoint 影片訓練](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23)。
- 用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。
 
在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。

#### <a name="result"></a>結果

已使用 SharePoint 建立並執行業務小組，且已測試並調整變更管理的資料。

## <a name="phase-3-drive-value"></a>第 3 階段：發揮價值

在這個階段，您會完成 SharePoint 的推行並協助使用者了解其優點。

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>步驟 1：將推行至組織的其他單位

推行至貴組織其餘單位應包含：

- 識別不同業務小組中，SharePoint Online 的重要業務案例。
- 在公告活動中使用調整過的變更管理資料，通知貴組織使用事先通知和時間表。
- 將組織其餘的資料夾和文件移轉至 SharePoint。
- 提供使用者訓練或提供資源連結，以介紹 SharePoint 及其使用方式。
- 用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。

#### <a name="result"></a>結果
組織已經準備好，且變更管理策略已經準備就緒，可以通知、訓練並讓使用者開始使用 SharePoint。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>步驟 2：評估使用狀況、管理滿意度、推動採用

推行至整個組織後，您必須繼續使用變更管理策略：

- 請管理階層推廣 SharePoint，做為文件儲存與共用的主要工具。
- 鼓勵個人在業務小組、部門和工作及專案小組之間使用它來進行文件儲存與共用。

以下是一些建議的活動：

- 請參閱 [Office 365 的成功要素](https://aka.ms/successfactors) (英文) 以了解雲端服務導入的一般最佳做法。 
- 請參閱 [Office 365 系統管理中心的活動報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。
- 監控您的意見反應管道 (位於中央 Teams 團隊或 Yammer 中的公共頻道)，以發現個人在使用 SharePoint 上的問題和意見反應。 快速解決問題，避免使用者在使用上感到挫折，並展現出對推行的支援。
- 在每個業務小組中找出並培養擁護者，並特別表彰他們在使用 SharePoint 上的成就和最佳作法。 向組織反映他們的成功，以顯示專案的成功和導入成效。 透過業務小組內的技術領導者的認可，可以對領導者和同儕產生強大的影響力。

#### <a name="result"></a>結果

貴組織已導入 Microsoft 365 企業版的 SharePoint 來支援文件儲存與共同作業。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

若要深入查看 Microsoft 並了解公司部署 SharePoint 的方式，請參閱 [SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉](https://www.microsoft.com/zh-TW/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration) (英文)。

## <a name="next-steps"></a>後續步驟

請參閱下列資源，了解 SharePoint 的後續維護： 

- [了解 SharePoint 中的權限等級](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [自訂 SharePoint 網站權限](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [開啟或關閉 SharePoint 的外部共用功能](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [設定及管理存取要求](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
