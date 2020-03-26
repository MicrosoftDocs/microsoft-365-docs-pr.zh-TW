---
title: 適用於高度管制資料的 SharePoint 網站
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: 建立安全的 SharePoint 小組網站來儲存您最重要且最敏感的檔案。
ms.openlocfilehash: bc1a84fa7437d9b2979e10b352f8a422c457e8a0
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951979"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a>適用於高度管制資料的 SharePoint 網站

*此案例同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

Microsoft 365 企業版包含一套完整的雲端式服務，因此您可以建立、儲存、保護和管理檔案中儲存的高度管制資料。包含的資料為：

- 受限於區域法規。
- 貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。

>[!Note]
> 使用 Microsoft Teams 的類似案例[在此](secure-teams-highly-regulated-data-scenario.md)。
>

符合此商務需求的 Microsoft 365 企業版雲端式案例需要您：

- 在 SharePoint 小組網站中儲存檔案 (文件、投影片檔案、試算表等)。
- 鎖定網站，以防止：
  - 非網站的 Office 365 群組成員的使用者存取。
  - 網站成員將存取權授與其他使用者。
  - 非網站成員要求網站的存取權。
- 為 SharePoint 網站設定 Office 365 保留標籤，作為防止使用者在組織外部傳送檔案的預設方法。
- 使用隨檔案一起移動的加密來加密網站中最敏感的檔案。
- 將權限新增至最敏感的檔案，以致於雖然是在網站外部共用這些檔案，開啟檔案時仍然需要具有權限之使用者帳戶的有效認證。

下表將此案例的需求對應至 Microsoft 365 企業版的功能。

|||
|:-------|:-----|
| **需求** | **Microsoft 365 企業版功能** |
| 儲存檔案 | SharePoint 小組網站 |
| 鎖定網站 | Office 365 群組和 SharePoint 小組網站的權限 |
| 為網站上的檔案新增標籤 | Office 365 保留標籤 |
| 將檔案傳送到組織外部時封鎖使用者 | Office 365 中的資料外洩防護 (DLP) 原則 |
| 加密網站上的所有檔案 | Office 365 敏感度標籤或子標籤 |
| 新增權限至網站的檔案 | Office 365 敏感度標籤或子標籤 |
|||

以下是安全 SharePoint 網站的設定範例。

![適用於高度管制資料的 SharePoint 網站案例](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

此案例需要您已部署：

- 基礎結構的[身分識別](identity-infrastructure.md)階段及[資訊保護](infoprotect-infrastructure.md)階段的步驟 1 和 2。 
- [SharePoint](sharepoint-online-onedrive-workload.md)。

下列階段會逐步帶您針對適用於高度管制資料的 SharePoint 網站，進行設計、設定及推動採用。

<a name="poster"></a> 如需此案例的 1 頁式摘要，請參閱[適用於高度管制資料的 SharePoint 網站海報](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)。

[![適用於高度管制資料的 SharePoint 網站海報](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)

您也可以用 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) 或 [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) 格式下載此海報，以及用 Letter、Legal 或 Tabloid (11 x 17) 大小的紙張列印此海報。


## <a name="identity-and-device-access-prerequisites"></a>身分識別與裝置存取必要條件

若要保護 SharePoint 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint 存取原則](sharepoint-file-access-policies.md)。

## <a name="phase-1-design"></a>階段 1：設計

若為高度管制的資料建立 SharePoint 網站，您必須先確定網站的目的。 例如，製造業組織的研發部門需要 SharePoint 網站來儲存現有產品的目前設計規格，以及在新產品上共同作業。 只有研發部門和選取的主管成員才允許存取網站。

該目的會驅使基本組態項目的決定，例如：

- 要指派至網站的文件部分以及標籤的 DLP 原則集合的 Office 365 保留標籤
- Office 365 敏感度子標籤的設定，可讓使用者套用到儲存在網站中的高度敏感檔案

決定後，您就能使用這些設定在階段 2 中設定網站。 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a>步驟 1：Office 365 保留標籤和 DLP 原則

當套用至 SharePoint 小組網站的文件部分時，Office 365 保留標籤提供預設方法，來分類儲存在網站上的所有檔案。
 
針對適用於高度管制資料的 SharePoint 網站，您必須決定要使用哪個 Office 365 保留標籤。

如需 Office 365 標籤的設計考量，請參閱 [Office 365 分類和標籤](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)。

若要保護機密資訊並防止意外或故意洩露，您可以使用 DLP 原則。如需詳細資訊，請參閱[概觀](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)。

針對 SharePoint 網站，您必須針對指派至網站的 Office 365 保留標籤設定 DLP 原則，以在使用者嘗試與外部使用者共用檔案時，封鎖使用者。 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a>步驟 2：您的 Office 365 敏感度子標籤

若要將加密和權限集提供給最敏感的檔案，使用者必須套用 Office 365 敏感度標籤和子標籤。 子標籤位於現有標籤下方。 

當您的需求是少量標籤、可同時用於全域使用和個別的私人小組時，請使用敏感度標籤。 當您有大量標籤或想要將安全網站的標籤整理在您的高度管制標籤之下時，請使用敏感度子標籤。 

所套用的標籤或子標籤設定會隨著檔案移動。 即使檔案流出網站外部，也只有擁有權限的已驗證使用者帳戶能開啟檔案。

### <a name="design-results"></a>設計結果

您已決定下列項目：

- 適當的 Office 365 保留標籤和與標籤相關聯的 DLP 原則
- 包含加密和權限的 Office 365 敏感度子標籤設定

## <a name="phase-2-configure"></a>階段 2：設定

在這個階段中，您會採用在階段 1 中決定的設定，然後實作這些設定來建立適用於高度管制資料的 SharePoint 網站。

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a>步驟 1：使用對應 Office 365 群組的擁有者和成員來建立私人 SharePoint 小組網站

按照[以下指示]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8)來建立私人 SharePoint 小組網站。

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a>步驟 2：為 SharePoint 小組網站設定額外的權限設定

從 SharePoint 網站設定這些權限設定。

1. 在工具列中，按一下設定圖示，然後按一下 [網站權限]****。
2. 在 [網站權限]**** 窗格的 [共用設定]**** 之下，按一下 [變更共用設定]****。
3. 在 [共用權限]**** 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]****。
4. 關閉 [允許存取要求]****，然後按一下 [儲存]****。

清除這些設定後，網站群組成員與其他成員或非成員要求網站存取權以共用網站的功能將會停用。

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a>步驟 3：針對 Office 365 保留標籤設定網站

使用[使用 Office 365 標籤與 DLP 來保護 SharePoint 檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)中的指示來：

1. 建立並發布適用於高度管制資料的保留標籤 (如有需要)。
2. 針對步驟 1 中建立的保留標籤設定網站。
3. 為使用在步驟 2 中建立的保留標籤的高度管制資料建立 DLP 原則，並封鎖使用者在組織外傳送檔案

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a>步驟 4：為網站建立 Office 365 敏感度子標籤

適用於高度管制資料的敏感度標籤可讓任何人套用至任何檔案，但是安全網站不同，它需要自己的子標籤，以致於指派子標籤的檔案都能：

- 受到加密，且加密會隨檔案移動。
- 包含自訂權限，因此只有網站群組的成員能夠開啟檔案。

若要針對儲存在網站中的檔案完成這項額外的安全性，您必須針對高度管制檔案設定一個新的敏感度標籤或一般標籤的子標籤。 只有網站的群組成員能在高度管制標籤的子標籤清單中看到該網站。

使用[這裡](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)的指示來為高度管制檔案所使用的標籤設定標籤或子標籤，其設定如下：

- 標籤或子標籤的名稱包含網站名稱，以便在將標籤或子標籤指派到檔案時輕鬆建立關聯。
- 啟用加密。
- 網站群組具有共同撰寫權限。

### <a name="configuration-results"></a>設定結果

您已設定下列項目：

- SharePoint 網站上的其他限制權限設定
- 指派給 SharePoint 網站文件部分的 Office 365 保留標籤
- Office 365 保留標籤的 DLP 原則
- 使用者可將 Office 365 敏感度標籤或子標籤套用到儲存在網站中的最敏感檔案，其會加密檔案並只允許小組網站群組的成員擁有共同撰寫存取權 

以下是使用高度管制標籤的子標籤所產生的設定。

![適用於高度管制資料的 SharePoint 網站案例](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

以下是使用者將子標籤套用至儲存在網站中的檔案的範例。

![適用於高度管制資料的 SharePoint 網站案例](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a>階段 3：推動使用者採用

如果一直將適用於高度管制資料的 SharePoint 網站用於儲存和存取敏感檔案，則 SharePoint 網站只能保護資料。 這是最難的階段，因為這有賴於使用者變更習慣和偏好。 

例如，員工以前都習慣將敏感檔案儲存在 USB 磁碟或個人雲端式儲存解決方案，而現在必須將檔案單獨儲存在適用於高度管制資料的 SharePoint 網站。

### <a name="step-1-train-your-users"></a>步驟 1：訓練您的使用者

完成您的設定之後，請訓練一組使用者，這些使用者是網站成員：

- 了解使用新網站來保護有價值檔案的重要性以及高度管制資料外洩的後果，例如法律後果、法規罰款、勒索軟體或喪失競爭優勢。
- 如何存取網站及其檔案。
- 如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。
- DLP 原則如何封鎖他們免於在外部共用檔案。
- 如何使用網站的標籤或子標籤來標記最敏感的檔案。
- 標籤或子標籤如何保護檔案，即使該檔案從網站外洩。

此訓練應該包含實際操作練習，讓使用者可以體驗這些作業及其結果。

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>步驟 2：進行使用量和檔案的定期檢閱

在幾週的訓練之後，SharePoint 網站的 SharePoint 系統管理員可以：

- 分析網站的使用方式，並且與預期使用方式進行比較。
- 確認已使用敏感度標籤或子標籤正確地標示高度敏感檔案。

  您可以在 SharePoint 檢視資料夾，然後透過 [新增欄]**** 的 [顯示/隱藏欄]**** 選項新增 [敏感度]**** 欄，查看哪些檔案有被指派標籤。


視需要重新訓練您的使用者。

### <a name="user-adoption-results"></a>使用者採用結果

高度管制的檔案會單獨儲存在適用於高度管制資料的 SharePoint 網站上，且最敏感的檔案已套用網站的敏感度標籤或子標籤。

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a>Contoso Corporation 如何對高度管制的資料使用 SharePoint 網站

Contoso Corporation 是虛構但具代表性的全球製造業集團。 查看 Contoso 如何設計、設定，然後為其在巴黎、莫斯科、紐約、北京和班加羅爾的研究小組推動採用[安全的 SharePoint 網站](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。 

## <a name="see-also"></a>另請參閱

[適用於高度管制資料的 Microsoft Teams](secure-teams-highly-regulated-data-scenario.md)

[Microsoft 365 企業版工作負載和案例](deploy-workloads.md)

[Microsoft 365 生產力資源庫](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)

[部署指南](deploy-microsoft-365-enterprise.md)
