---
title: 適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/03/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 建立安全的 SharePoint Online 小組網站或 Microsoft Teams 小組，以儲存您最有價值且機密的數位資產。
ms.openlocfilehash: d80be334f692f905ec70ae43f851d2b73801f4a0
ms.sourcegitcommit: dbcc32218489ab256b7eb343290fcccb9bc04e36
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/02/2019
ms.locfileid: "33553322"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a>適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站

*此案例同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

Microsoft 365 企業版包含一套完整的雲端式服務，因此您可以建立、儲存和保護高管制資料。包含的資料為：

- 受限於區域法規。
- 貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。

符合此商務需求的 Microsoft 365 企業版雲端式解決方案需要您：

- 將數位資產 (文件、投影片組、試算表等等) 儲存在 SharePoint Online 小組網站或 Microsoft Teams 小組的 [檔案]**** 索引標籤中。
- 鎖定網站或小組，以防止：
   - 透過群組成員資格僅存取一組特定的使用者帳戶，這包含可以用哪個權限等級存取 SharePoint Online 小組網站的使用者，以及可以進行管理的使用者。
   - 網站成員將存取權授與其他使用者。
   - 非網站成員要求網站的存取權。
- 為您的 SharePoint Online 網站或小組設定 Office 365 保留標籤，作為在網站或小組中的文件上定義保留原則的預設方法。
- 防止使用者將檔案傳送到組織外部。
- 加密網站或小組上最機密的數位資產。
- 新增權限至最機密的數位資產，即使這些資產在網站外部共用，開啟資產時仍然需要具有權限之使用者帳戶的有效認證。

下表將此解決方案的需求對應至 Microsoft 365 企業版的功能。

|||
|:-------|:-----|
| **需求** | **Microsoft 365 企業版功能** |
| 儲存數位資產 | SharePoint Online 小組網站和 Office 365 中的小組 |
| 鎖定網站 | Azure AD 群組和 SharePoint Online 小組網站權限 |
| 標示網站的數位資產 | Office 365 保留標籤 |
| 將檔案傳送到組織外部時封鎖使用者 | Office 365 中的資料外洩防護 (DLP) 原則 |
| 加密網站的所有數位資產 | Enterprise Mobility + Security (EMS) 中的 Azure 資訊保護子標籤 |
| 新增權限至網站的數位資產 | EMS 中的 Azure 資訊保護子標籤 |
|||

此解決方案需要您已部署：

- 基礎結構的[身分識別](identity-infrastructure.md)階段及[資訊保護](infoprotect-infrastructure.md)階段的步驟 1 和 2。 
- 針對 SharePoint Online 小組網站中的高管制資料，部署 [SharePoint Online](sharepoint-online-onedrive-workload.md)。
- 針對 Microsoft Teams 小組中的高管制資料，部署 [Microsoft Teams](teams-workload.md)。

下列階段會逐步帶您針對適用於高管制資料的 SharePoint Online 網站和小組，進行設計、設定及推動採用。

若要查看 Contoso Corporation (虛構但有代表性的跨國企業) 如何為其研究小組設計 SharePoint Online 網站，請參閱[範例設定](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。

>[!Note]
>高管制資料的小組需要您先建立適用於高管制資料的 SharePoint Online 小組網站。然後建立新的小組，該小組使用 SharePoint Online 小組網站的 Office 365 群組。如需詳細資訊，請參閱階段 2，步驟 4。
>

## <a name="identity-and-device-access-prerequisites"></a>身分識別與裝置存取必要條件

若要保護小組或 SharePoint Online 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint Online 存取原則](sharepoint-file-access-policies.md)。

## <a name="phase-1-design"></a>階段 1：設計

若要建立適用於高管制資料的 SharePoint Online 網站或小組，您必須先識別其目的。例如，製造業組織的研究和開發部門需要 SharePoint Online 網站來儲存現有產品的目前設計規格，以及一個為新產品共同作業的地方。只有研究和開發部門的成員和選取的管理階層人員可以存取網站。

該目的會驅使基本組態項目的決定，例如：

- SharePoint Online 權限集和 SharePoint 群組的集合
- 存取群組的集合，要新增至 SharePoint 群組的 Azure AD 安全性群組及其成員
- 要指派至網站和標籤的 DLP 原則集合的 Office 365 保留標籤
- Azure 資訊保護子標籤的設定，使用者會將其套用至網站中的高度機密數位資產

一旦決定，您會使用這些設定在階段 2 中設定網站。 

### <a name="step-1-an-isolated-sharepoint-online-site"></a>步驟 1：隔離的 SharePoint Online 網站

鎖定版本的 SharePoint Online 小組網站也稱為隔離的網站。與私人小組網站的預設設定不同，隔離的網站是設定來防止：

- 非指定群組成員的存取。
- 要求存取。
- 指定群組目前成員未經授權授與存取權。
- 存取群組成員對網站進行系統管理。

包含高管制資產之 SharePoint Online 小組網站的安全性不會變更，除非是由網站的 SharePoint 系統管理員執行。

請參閱[設計隔離的 SharePoint Online 小組網站](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) (機器翻譯)，以取得決定權限等級、SharePoint 群組、存取群組與群組成員集合的詳細資料。

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a>步驟 2：Office 365 保留標籤和 DLP 原則

當套用至 SharePoint Online 小組網站時，Office 365 保留標籤提供預設方法，來分類儲存在網站上的所有數位資產。
 
針對適用於高管制資料的 SharePoint Online 網站，您必須決定要使用哪個 Office 365 保留標籤。

如需 Office 365 標籤的設計考量，請參閱 [Office 365 分類和標籤](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)。

若要保護機密資訊並防止意外或故意洩露，您可以使用 DLP 原則。如需詳細資訊，請參閱[概觀](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies) (機器翻譯)。

針對適用於高管制資料的 SharePoint Online 網站，您必須針對指派至網站的 Office 365 保留標籤設定 DLP 原則，以在使用者嘗試與外部使用者共用數位資產時，封鎖使用者。 

### <a name="step-3-your-azure-information-protection-sub-label"></a>步驟 3：您的 Azure 資訊保護子標籤

若要為最機密的數位資產提供加密和權限集，使用者必須使用 Azure 資訊保護用戶端來套用 Azure 資訊保護標籤。若要針對適用於高管制資料的 SharePoint Online 網站使用 Azure 資訊保護標籤，您必須在有範圍的原則中設定 Azure 資訊保護子標籤。 

子標籤存在於現有標籤底下。例如，您可以在「高度機密」標籤底下建立「研究和開發」子標籤。有範圍的原則是僅套用至使用者子集的原則。針對適用於高管制資料的 SharePoint Online 網站，範圍是屬於網站存取群組成員的使用者集合。

已套用子標籤的設定會隨著資產移動。即使它已下載並且在網站外部共用，只有經過驗證的使用者帳戶有權可以開啟它。

### <a name="design-results"></a>設計結果

您已決定下列項目：

- SharePoint 群組和權限等級的集合
- 存取群組和每個權限等級之成員的集合
- 適當的 Office 365 保留標籤和與標籤相關聯的 DLP 原則
- 包含加密和權限的 Azure 資訊保護子標籤設定

## <a name="phase-2-configure"></a>階段 2：設定

在這個階段中，您採用在階段 1 中決定的設定，然後實作以建立適用於高管制資料的 SharePoint Online 網站。

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a>步驟 1：建立及設定隔離的 SharePoint Online 小組網站

使用[部署隔離的 SharePoint Online 小組網站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) (機器翻譯) 中的指示：

- 針對在網站上使用的每個 SharePoint 權限等級，建立及填入存取群組。
- 建立及設定隔離的小組網站。

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a>步驟 2：針對 Office 365 保留標籤 DLP 原則設定網站

使用[使用 Office 365 標籤與 DLP 來保護 SharePoint Online 檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)中的指示來：

- 識別或建立 Office 365 保留標籤，並且將其套用至隔離的 SharePoint Online 網站。
- 建立及設定 DLP 原則，該原則會在使用者嘗試在組織外部共用 SharePoint Online 網站上的數位資產時，封鎖使用者。

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a>步驟 3：針對網站建立 Azure 資訊保護子標籤

使用[使用 Azure 資訊保護來保護 SharePoint Online 檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)中的指示來： 

- 在有範圍的原則中建立及設定 Azure 資訊保護子標籤。
- 將 Azure 資訊保護用戶端部署至使用者電腦。

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a>步驟 4 (選用)：建立適用於高管制資料的小組

如果您想要一個適用於高管制資料的小組，首先建立適用於高管制資料的 SharePoint Online 網站。當您建立初始私人 SharePoint Online 小組網站時，您會指定 Office 365 群組名稱。

完整設定適用於高管制資料的 SharePoint Online 網站之後，使用以下步驟來將其轉換為適用於高管制資料的小組：

1. 登入 Office 365。
2. 從 [Microsoft Office 的首頁]**** 索引標籤中，按一下 [Teams]****。
3. 從 [Microsoft Teams]**** 索引標籤的 [加入或建立小組]**** 窗格中，按一下 [建立小組]****。
4. 在 [建立您的小組]**** 窗格中，按一下 [從現有的 Office 365 群組建立小組]****。
5. 在 Office 365 群組的清單中，選取對應至適用於高管制資料的 SharePoint Online 網站的 Office 365 群組名稱，然後按一下 [選擇小組]****。

新小組的 [檔案]**** 索引標籤會列出對應 SharePoint Online 網站之 [文件]**** 區域中 [一般]**** 資料夾中的內容。若要查看適用於小組之 SharePoint Online 網站的其餘資源，請按一下省略符號，然後按一下 [在 SharePoint 中開啟]****。

### <a name="configuration-results"></a>設定結果

您已設定下列項目：

- SharePoint Online 隔離網站
- 指派給 SharePoint Online 隔離網站的 Office 365 保留標籤
- Office 365 保留標籤的 DLP 原則
- 使用者可以套用至最機密數位資產之有範圍原則的 Azure 資訊保護子標籤，是儲存在會加密資產並且強制執行權限的網站中。
- 如有需要，適用於高管制資料的小組是以 SharePoint Online 網站為基礎

## <a name="phase-3-drive-user-adoption"></a>階段 3：推動使用者採用

適用於高管制資料的 SharePoint Online 網站或小組，只能在持續用於儲存和存取機密數位資產時保護資料。這是最難的階段，因為這個階段仰賴使用者改變他們的方式。 

例如，以往都是將機密檔案儲存在 USB 磁碟或個人雲端式儲存解決方案的管理階層人員，現在必須將檔案完全都儲存在適用於高管制資料的 SharePoint Online 網站或小組中。

### <a name="step-1-train-your-users"></a>步驟 1：訓練您的使用者

完成您的設定之後，請訓練一組使用者，這些使用者是網站存取群組的成員：

- 著重在使用新網站或小組來保護有價值資產的重要性，以及高管制資料外洩的後果，例如法律後果、法規罰款、勒索軟體或喪失競爭優勢。
- 如何存取網站及其資產。
- 如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。
- DLP 原則如何封鎖他們免於在外部共用檔案。
- 如何使用 Azure 資訊保護用戶端，以設定的子標籤來標示最機密的數位資產。
- Azure 資訊保護子標籤如何在資產即使是洩漏到網站或小組外部時加以保護。

此訓練應該包含實際操作練習，讓使用者可以體驗這些作業及其結果。

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>步驟 2：進行使用量和檔案的定期檢閱

在幾週的訓練之後，SharePoint Online 網站或小組的 SharePoint 系統管理員可以：

- 分析網站或小組的使用量，並且與預期使用量進行比較。
- 確認高度機密檔案已使用 Azure 資訊保護子標籤適當地標示。

視需要重新訓練您的使用者。

### <a name="user-adoption-results"></a>使用者採用結果

機密數位資產僅儲存在適用於高管制資料的 SharePoint Online 網站或小組上，最機密的資產已設定為套用 Azure 資訊保護子標籤。

## <a name="see-also"></a>另請參閱

[部署指南](deploy-microsoft-365-enterprise.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)

[在開發/測試環境中保護 SharePoint Online 網站](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
