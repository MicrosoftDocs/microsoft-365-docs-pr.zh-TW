---
title: Contoso Corporation 的資訊保護
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企業版中的資訊保護功能，在雲端中保護其數位資產。
ms.openlocfilehash: f0869dfd661ae4dbaed74fdfd660c863deb20175
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276110"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Contoso Corporation 的資訊保護

**摘要：** 了解 Contoso 如何使用 Microsoft 365 企業版中的資訊保護功能，在雲端中保護其數位資產。

Contoso 相當嚴正地看待其資訊安全性和保護。例如，智慧財產權的外洩或損毀，說明產品設計和專屬製造技術會讓他們處於競爭的劣勢當中。

在將機密和最有價值的資產移至雲端之前，他們要確定在 Microsoft 365 企業版的雲端式服務中，支援及實作他們的內部部署資訊分類和保護需求。

## <a name="contosos-data-security-classification"></a>Contoso 的資料安全性分類

Contoso 執行資料分析，並且決定下列層級。

||||
|:-------|:-----|:-----|
| **第 1 級：基準** | **第 2 級：機密** | **第 3 級：高管制** |
| 資料經過加密並且僅提供給已驗證的使用者 <BR> <BR> 專為儲存在內部部署及雲端式儲存空間和工作負載 (例如 Office 365) 的所有資料而提供。資料會予以加密，並儲存於服務中，而且會在服務和用戶端裝置之間傳輸。 <BR><BR> 第 1 級的範例：一般業務通訊 (電子郵件) 和用於行政、銷售和支援員工的檔案之資料。 | 第 1 級再加上增強式驗證及資料遺失保護 <BR> <BR> 增強式驗證包含利用簡訊驗證的多重要素驗證與，而資料遺失保護則確保敏感或重要的資料不會外流傳至內部部署網路以外的地方。 <BR><BR> 第 2 級的範例：財務和法務資訊以及新產品的研發資料。 | 第 2 級再加上最高層級的加密、驗證及稽核。 <BR> <BR>  對靜態資料和雲端資料的最高層級資料加密，遵循地區法規，結合多重要素驗證與智慧卡以及細微稽核與警示。 <BR> <BR> 第 3 級的範例：客戶與合作夥伴的個人身分識別資訊，以及產品的工程規格和專屬的製造技術。  |
||||

## <a name="contosos-information-policies"></a>Contoso 的資訊原則
下表列出 Contoso 的資訊原則。

|||||
|:-------|:-----|:-----|:-----|
|  | **存取** | **資料保留** | **資訊保護** |
| 低商業價值 (第 1 級：基準) | 允許所有人存取  | 6 個月 | 使用加密 |
| 中等商業價值 (第 2 級：敏感性) | 允許 Contoso 員工、次承攬人和合作夥伴存取 <BR> <BR> 使用多重要素驗證 (MFA)、傳輸層安全性 (TLS) 和行動裝置應用程式管理 (MAM) | 2 年  | 使用雜湊值以確保資料完整  |
| 高商業價值 (第 3 級：高管制) | 允許高階主管以及工程部和製造部的主管存取 <BR> <BR> 版權管理系統 (RMS)，只有受控網路裝置  | 7 年  | 使用數位簽章以提供不可否認性  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a>Contoso 使用 Microsoft 365 企業版進行資訊保護的途徑

Contoso 使用下列步驟，針對其資訊保護需求準備 Microsoft 365 企業版：

1. 識別要保護的資訊

   Contoso 大量檢閱內部部署 SharePoint 網站和檔案共用上的現有數位資產，並且對每個項目進行分類。

2. 判別各資料層級的存取權、保留期和資訊保護原則

   Contoso 根據資料層級決定原則需求，這些原則需求是用來在移至雲端時保護現有的數位資產。

3. 針對不同的資訊層級建立敏感度標籤及其設定

   Contoso 針對其資料層級建立了敏感度標籤，其中包括加密、權限和浮水印等敏感性和高管制標籤。

4. 針對機密和高管制資料建立受保護的 SharePoint Online 網站，具有鎖定存取的權限

   機密和高管制網站均已設定為[隔離網站](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites)，在其中預設 SharePoint Online 小組網站的權限已自訂為 Azure Active Directory (Azure AD) 群組。 此外，也以使用對應的保留標籤來設定敏感性和高管制 SharePoint Online 網站。 儲存在高管制 SharePoint Online 網站中的檔案受到高管制敏感度標籤保護。 如需詳細資訊，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站](teams-sharepoint-online-sites-highly-regulated-data.md)案例。

5.  從內部部署 SharePoint 網站和檔案共用將資料移至新的 SharePoint Online 網站

    遷移至新 SharePoint Online 網站的檔案，會繼承指派給網站的預設保留標籤。

6.  訓練員工如何針對新文件使用敏感度標籤、如何在建立新 SharePoint Online 網站時與 Contoso IT 互動，以及一律將數位資產儲存在 SharePoint Online 網站上

    這個部分是雲端資訊保護轉換最困難的部分，Contoso IT 和管理階層必須改變組織員工總是在雲端儲存及標示其數位資產、抑制使用內部部署檔案共用，而從不使用第三方雲端儲存服務或 USB 磁碟機這樣的一個資訊儲存壞習慣。

## <a name="conditional-access-policies-for-information-protection"></a>資訊保護的條件式存取原則

搭配其身分識別和行動裝置管理基礎結構，以及作為推出 Exchange Online 和 SharePoint Online 的一部分，Contoso 設定下列條件式存取原則集合，並且將該集合套用至適當的 Azure AD 群組：

- [裝置原則的受控和非受控應用程式存取](identity-access-policies.md)
- [Exchange Online 存取原則](secure-email-recommended-policies.md)
- [SharePoint Online 存取原則](sharepoint-file-access-policies.md)

圖 1 顯示 Contoso 的資訊保護原則結果集合。

![](./media/contoso-info-protect/contoso-info-protect-fig1.png)

**圖 1：裝置、Exchange Online 和 SharePoint Online 條件式存取原則**
 
>[!Note]
>Contoso 也會為身分識別和登入設定額外的條件式存取原則。請參閱 [Contoso Corporation 的身分識別](contoso-identity.md)。
>

這些原則會確保：

- 允許使用應用程式，並由應用程式保護原則定義這些應用程式可以對組織資料執行哪些動作。
- 電腦和行動裝置都必須符合規範。
- Exchange Online 使用適用於 Exchange Online 的 Office 365 訊息加密。
- SharePoint Online 會使用應用程式強制限制。
- SharePoint Online 會針對僅限瀏覽器存取使用存取控制原則，並封鎖未受控裝置的存取。

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a>將 Microsoft 365 企業版功能對應至 Contoso 的資料層級

下表顯示 Contoso 資料層級與 Microsoft 365 企業版資訊保護功能的對應。

|||||
|:-------|:-----|:-----|:-----|
| | **Office 365** | **Windows 10 和 Office 365 專業增強版** | **EMS** |
| 第 1 級：基準  | SharePoint Online 和 Exchange Online 條件式存取原則 <BR> SharePoint Online 網站的權限 | 敏感度標籤 <BR> BitLocker <BR> Windows 資訊保護 | 裝置條件式存取原則和行動裝置應用程式管理原則 |
| 第 2 級：敏感性 | 第 1 級增強版： <BR> <BR> 敏感度標籤 <BR> SharePoint Online 網站的 Office 365 標籤 <BR> SharePoint Online 和 Exchange Online 的 Office 365 資料外洩防護 <BR> 隔離的 SharePoint Online 網站  | 第 1 級增強版： <BR> <BR> 數位資產上的敏感度標籤 <BR> Office 365 進階資料控管 | 第 1 級 |
| 第 3 級：高管制 | 第 2 級增強版： <BR><BR> 針對營業秘密資訊的使用自己的金鑰 (BYOK) 加密和保護 <BR> 適用於與 Office 365 服務互動之企業營運應用程式的 Azure Key Vault | 第 2 級 | 第 1 級 |
|||||


## <a name="next-step"></a>下一步

[請參閱](contoso-security-summary.md) Contoso 如何針對身分識別與存取管理、威脅防護、資訊保護和安全性管理，使用 Microsoft 365 企業版的安全性功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版的資訊保護](infoprotect-infrastructure.md)

[部署指南](deploy-microsoft-365-enterprise.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)


