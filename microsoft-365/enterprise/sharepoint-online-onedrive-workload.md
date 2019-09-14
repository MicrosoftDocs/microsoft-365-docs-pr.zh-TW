---
title: 部署適用於 Microsoft 365 企業版的 SharePoint Online 和商務用 OneDrive
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/28/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 推行並發揮 Microsoft 365 企業版 SharePoint Online 在組織中的價值，規劃這整個程序的步驟。
ms.openlocfilehash: 9ceadbb0268d3a2aa82309d01933a8bd05429188
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981764"
---
# <a name="deploy-sharepoint-online-and-onedrive-for-business-for-microsoft-365-enterprise"></a>部署適用於 Microsoft 365 企業版的 SharePoint Online 和商務用 OneDrive

*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*

當您進行檔案儲存與共用、內容管理及共同作業時，SharePoint Online 和 Microsoft Teams 就是您的最佳選擇，也是打造 Microsoft 365 企業版團隊合作價值的重要元素。 

SharePoint Online 也具有進階的安全性功能，包括存取控制和權限，以及在執行中及靜態加密。SharePoint Online 安全性是 Microsoft 365 企業版情報安全性價值的重要元素。

如果您是 SharePoint Online 新手，請參閱 [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 與 [SharePoint 入門](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics)。

以下的階段與步驟會帶領您構想 SharePoint Online 在貴組織中的角色，透過一系列的漸進式推行讓組織導入，並向使用者推廣其使用價值。 開始之前，請確定您已設定正確的[基礎結構](deploy-foundation-infrastructure.md)階段，您的 SharePoint Online 網站才能具備您需要的安全性功能。 

若要部署適用於 Microsoft 365 企業版的商務用 OneDrive，請參閱[適用於企業的 OneDrive 指南](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。

## <a name="phase-1-envision"></a>第 1 階段：構想
在這個階段，您要召集負責 SharePoint Online 部署的人員，並決定組織將如何使用它們來解決業務需求。

### <a name="step-1-gather-your-sharepoint-online-deployment-members"></a>步驟 1：收集您的 SharePoint Online 部署成員

為了將 SharePoint Online 成功部署在 [Microsoft 365 企業版底層基礎結構](deploy-foundation-infrastructure.md)上，您需要找到適當的人員取得相關想法和意見反應。重點人物包括企業決策者、IT 人員 (如架構與實作者)、使用者提倡者。 

這三種人員可確保部署涵蓋各種考量，從而解決業務需求和技術層面的資料夾和文件移轉與安全性，讓結果成為一般使用者會使用的工具。

#### <a name="result"></a>結果

代表組織的業務、技術、使用者三方面的人員清單。

### <a name="step-2-determine-and-prioritize-your-sharepoint-online-business-scenarios"></a>步驟 2：決定 SharePoint Online 商務案例並定立優先順序

Sharepoint 可用於不同的用途。您必須判斷哪些用途是對應到您的業務需求。您應該著重於 SharePoint Online，來解決您小組、部門或整個組織的文件儲存與共用、內容管理及共同作業的需求。 

您可在 [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 中查看案例和功能清單。

下列商務要點可解決貴組織的需求：

|||
|:-----|:-----|
| 共用和共同作業 | 利用小組網站、共同作業網站及同步處理。 |
| 通知並保持互動 | 未來的資訊傳入。 |
| 轉換 | 使用流程來建立儲存區或工作流程。 |
| 充分利用集體知識 | 使用搜尋來授與貴組織所需的結果。 |
| 保護 | 確保貴組織受到保護，且有正確的規範。 |
| 外部/開發 | 讓貴組織使用 SharePoint 架構來開發自訂解決方案和應用程式。 |
|||

請參閱＜[SharePoint Online 管理](https://docs.microsoft.com/sharepoint/sharepoint-online)＞，取得如何依您需求設定 SharePoint Online。

要查看 SharePoint Online 優點的其中一個方法，是檢查個人、小組、部門或整個組織現今互動的方式，並找出適當的案例，提供更輕鬆的方法來儲存及共用檔案共同作業。請注意，[Microsoft Teams](teams-workload.md) 對您部分的案例而言可能是較好的選擇。

#### <a name="sharepoint-online-site-for-highly-regulated-data"></a>適用於高管制資料的 SharePoint Online 網站

高管制資料受限於區域法規，或者是貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。您可以設定 SharePoint Online 網站以進行限制存取、資料分類、資料外洩防護以及此資料類型的加密。如需詳細資訊，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站](teams-sharepoint-online-sites-highly-regulated-data.md)。

#### <a name="result"></a>結果
SharePoint Online 的案例清單，能解決貴組織對於文件儲存與共用、內容管理及共同作業的需求。

## <a name="phase-2-onboard"></a>第 2 階段：導入

在這個階段，規劃 SharePoint Online 部署的技術層面，然後開始向所選的使用者群組推行。

### <a name="prerequisites-identity-and-device-access-configuration"></a>必要條件：身分識別與裝置存取設定

若要保護 SharePoint Online 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint Online 存取原則](sharepoint-file-access-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>步驟 1：完成技術規劃

開始技術規劃之前，先決定您是否要使用 FastTrack。如果貴組織有超過 50 個基座，並參與[合格方案](https://technet.microsoft.com/library/dn783224.aspx) (英文)，您可以使用 FastTrack 優點來逐步引導您規劃、部署及採用服務而不必支付額外費用。或者，您可以使用 Office 365 帳戶登入後，從 [FastTrack](https://fasttrack.microsoft.com/) (英文) 取得「FastTrack 導入精靈」來完成這項工作。

如果您要執行自己的規劃 (或搭配 FastTrack)，必須判斷您的網路和組織是否準備好使用 SharePoint Online。請務必符合基本基礎結構的網路允出準則，特別注意網際網路頻寬、輸送量、流量延遲，達到可用於 SharePoint Online 型文件其他流量的最佳效能。

您可以使用這些資源，準備好使用 SharePoint Online 推行的技術層面： 

- [SharePoint Online 規劃指南](https://support.office.com/article/sharepoint-online-planning-guide-abacd1bb-295d-4235-afdd-15f5e4cc2e6c)
- [移轉至 SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

如需更深入了解 SharePoint Online 的安全性，請檢閱下列資源：

-   [SharePoint Online 和 OneDrive 如何保護您在雲端的資料](https://support.office.com/article/How-SharePoint-Online-and-OneDrive-safeguard-your-data-in-the-cloud-5aa038e8-8ff0-4704-9e6a-fd72af0a2035)
-   [商務用 OneDrive 和 SharePoint Online 中的資料加密](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C) (英文)

#### <a name="result"></a>結果

您了解 SharePoint Online 網站和內部部署資料夾與文件移轉及安全性，並準備好開始將 SharePoint Online 推出至貴組織中的指定群組。

### <a name="step-2-run-an-it-pilot"></a>步驟 2：執行 IT 試驗

在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。在 IT 試驗期間：

- 選擇 SharePoint Online 商務案例，讓您的 IT 試驗參與者可以加以練習。
- 為試驗參與者提供一組練習，來測試 SharePoint Online 文件儲存、共用、共同作業、小組排程，以及其他功能。
- 判斷您的變更管理策略，並產生材料來推動整個組織的使用者採用 SharePoint Online。變更管理的材料可包含電子郵件公告文字、內部訓練計劃、走廊海報和簡報。這些材料向組織宣傳 SharePoint Online 相關事宜及其優點，目的是要引發認知和促進使用。請參閱 [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) 一文中變更管理策略的一些想法。
- 讓 IT 試驗參與者根據他們的經驗檢閱變更管理的材料。他們可以提供最佳做法的祕訣，以及最能描述 Microsoft Teams 優點以及如何用於通訊和排程的建議。

#### <a name="result"></a>結果

完成 SharePoint Online 的 IT 試驗，並已開發、檢閱、精簡首次變更管理的材料。

### <a name="step-3-roll-out-to-a-business-group"></a>步驟 3：推行至商務群組

完成 IT 試驗後，將 SharePoint Online 推行至貴組織中的商務群組或部門。此推行應包含：

- 識別商務群組中的 SharePoint Online 重要商務案例。
- 用公告活動通知使用者在部門及工作或專案小組使用 SharePoint Online 的相關預期變更和時間表。
- 將商務群組成員的內部部署資料夾和文件遷移到 SharePoint Online。
- 提供使用者訓練或 SharePoint Online 及其使用方式的資源介紹連結。請參閱 [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) 影片訓練課程。
- 用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。
 
在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。

#### <a name="result"></a>結果

已使用 SharePoint Online 建立並執行商務群組，且已測試並精簡變更管理的材料。

## <a name="phase-3-drive-value"></a>第 3 階段：發揮價值

在這個階段，您完成推出 SharePoint Online 支援您的使用者，以協助他們了解其優點。

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>步驟 1：將推行至組織的其他單位

推行至貴組織其餘單位應包含：

- 識別不同商務群組中的 SharePoint Online 重要商務案例。
- 在公告活動中使用精簡過的變更管理材料，通知貴組織使用的期望和時間表。
- 將貴組織其餘的資料夾和文件移轉至 SharePoint Online。
- 提供使用者訓練或提供 SharePoint Online 及其使用方式的資源介紹連結。
- 用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。

#### <a name="result"></a>結果
已建立並執行組織，且變更管理策略已經準備就緒，可以通知、訓練並讓使用者開始使用 SharePoint Online。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>步驟 2：評估使用狀況、管理滿意度、推動採用

推行至整個組織後，您必須繼續使用變更管理策略：

- 讓您的領導能力將 SharePoint Online 升階為主要工具，以進行文件儲存和共用，以及小組、部門或整個組織的共同作業。
- 鼓勵個人將它用於商務群組、部門、工作和專案小組的共同作業和行事曆編排。

以下是一些建議的活動：

- 請參閱 [Office 365 採用指南](https://aka.ms/successfactors)以了解雲端服務採用的一般最佳做法。 
- 請參閱 [Office 365 系統管理中心的活動報告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。
- 監控意見反應區 (中央 Teams 小組或 Yammer 中的公用通道) 了解個人 SharePoint Online 的使用體驗問題和意見反應。盡快解決疑問和問題，以避免個人的挫折感，並示範推出的支援。
- 在每個商務群組中找出高手並加強培養，強調他們使用 SharePoint Online 的成就和最佳做法。在組織中反映出他們的成功，以彰顯專案的成功與採用。商務群組技術主管的背書對領導者和同儕有強大的影響。

#### <a name="result"></a>結果

貴組織已採用 SharePoint Online 作為服務，來支援文件儲存與共同作業。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

若要深入查看 Microsoft 並了解公司部署 SharePoint Online 的方式，請參閱 [SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)。

## <a name="next-steps"></a>後續步驟

請參閱下列資源，了解 SharePoint Online 的後續維護： 

- [了解 SharePoint 的權限等級](https://support.office.com/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)
- [自訂 SharePoint 網站的權限](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048) (機器翻譯)
- [開啟或關閉 SharePoint Online 的外部共用](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30) (機器翻譯)
- [設定及管理存取要求](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)

