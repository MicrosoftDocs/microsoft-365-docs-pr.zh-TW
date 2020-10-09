---
title: Contoso Corporation 的資訊保護
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 瞭解 Contoso 如何使用 Microsoft 365 for enterprise 中的資訊保護功能，在雲端中保護其數位資產。
ms.openlocfilehash: 1966fdec3de246ca54fd99ab018485b9ee817281
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399238"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Contoso Corporation 的資訊保護

Contoso 相當嚴正地看待其資訊安全性和保護。例如，智慧財產權的外洩或損毀，說明產品設計和專屬製造技術會讓他們處於競爭的劣勢當中。

在將其機密和最寶貴的數位資產移至雲端之前，他們必須確定其內部部署資訊分類及保護需求受到支援，並已在適用于企業的 Microsoft 365 雲端架構服務中實施。

## <a name="contosos-data-security-classification"></a>Contoso 的資料安全性分類

Contoso 執行資料分析，並且決定下列層級。

| 第 1 級：基準 | 第 2 級：敏感性 | 第 3 級：高管制 |
|:-------|:-----|:-----|
| 資料經過加密並且僅提供給已驗證的使用者。 <BR> <BR> 針對所有儲存在內部部署和雲端架構存放區和工作負載中的資料提供。當資料位於服務中，且在服務和用戶端裝置之間傳輸時，會進行加密。 <BR><BR> 第 1 級的範例：一般業務通訊 (電子郵件) 和用於行政、銷售和支援員工的檔案之資料。 | 第 1 級再加上增強式驗證及資料遺失保護。 <BR> <BR> 增強式驗證包括使用 SMS 驗證的 Azure 多重要素驗證 (MFA)。 資料遺失防護可確保機密或關鍵資訊不會洩漏到 Microsoft 雲端以外的地方。 <BR><BR> 第 2 級的範例：財務和法務資訊以及新產品的研發資料。 | 第 2 級再加上最高層級的加密、驗證及稽核。 <BR> <BR>  對靜態資料和雲端資料的最高層級資料加密，遵循地區法規，結合 MFA 與智慧卡以及細微稽核與警示。 <BR> <BR> 第 3 級的範例：客戶與合作夥伴的個人身分識別資訊，以及產品的工程規格和專屬的製造技術。  |
||||

## <a name="contosos-information-policies"></a>Contoso 的資訊原則
下表列出 Contoso 的資訊原則。


| 值 | Access | 資料保留 | 資訊保護 |
|:-------|:-----|:-----|:-----|
| 低商業價值 (第 1 級：基準) | 允許所有人存取  | 6 個月 | 使用加密。 |
| 中等商業價值 (第 2 級：敏感性) | 允許 Contoso 員工、次承攬人和合作夥伴存取 <BR> <BR> 使用 MFA、傳輸層安全性 (TLS) 和行動裝置應用程式管理 (MAM)。 | 2 年  | 使用雜湊值以確保資料完整。  |
| 高商業價值 (第 3 級：高管制) | 允許高階主管以及工程部和製造部的主管存取。 <BR> <BR> 版權管理系統 (RMS)，只有受控網路裝置。  | 7 年  | 使用數位簽章以提供不可否認性。  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Contoso 使用 Microsoft 365 for enterprise 的資訊保護途徑

Contoso 使用下列步驟來準備 Microsoft 365 for enterprise 以滿足其資訊保護需求：

1. 識別要保護的資訊

   Contoso 大量檢閱內部部署 SharePoint 網站和檔案共用上的現有數位資產，並且對每個項目進行分類。

2. 判別各資料層級的存取權、保留期和資訊保護原則

   Contoso 根據資料層級決定原則需求，這些原則需求是用來在移至雲端時保護現有的數位資產。

3. 針對不同的資訊層級建立敏感度標籤及其設定

   Contoso 針對其資料層級建立了敏感度標籤，以及包括加密、權限和浮水印等高管制標籤。

4.  從內部部署 SharePoint 網站和檔案共用將資料移至新的 SharePoint 網站

    遷移至新 SharePoint 網站的檔案，會繼承指派給網站的預設保留標籤。

5.  訓練員工如何針對新文件使用敏感度標籤、如何在建立新 SharePoint 網站時與 Contoso IT 互動，以及一律將數位資產儲存在 SharePoint 網站上

    這個部分是雲端資訊保護轉換最困難的部分，Contoso IT 和管理階層必須改變組織員工總是在雲端標示及儲存其數位資產、抑制使用內部部署檔案共用，而從不使用第三方雲端儲存服務或 USB 磁碟機這樣的一個資訊儲存壞習慣。

## <a name="conditional-access-policies-for-information-protection"></a>資訊保護的條件式存取原則

搭配其身分識別和行動裝置管理基礎結構，以及作為推出 Exchange Online 和 SharePoint 的一部分，Contoso 設定下列條件式存取原則集合，並且將該集合套用至適當的群組：

- [裝置原則的受控和非受控應用程式存取](../security/office-365-security/identity-access-policies.md)
- [Exchange Online 存取原則](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint 存取原則](../security/office-365-security/sharepoint-file-access-policies.md)

以下是 Contoso 的資訊保護原則結果集合。

![裝置、Exchange Online 和 SharePoint 條件式存取原則](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso 也會為身分識別和登入設定額外的條件式存取原則。 請參閱 [Contoso Corporation 的身分識別](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。
>

這些原則會確保：

- 允許使用應用程式，並由應用程式保護原則定義這些應用程式可以對組織資料執行哪些動作。
- 電腦和行動裝置都必須符合規範。
- Exchange Online 使用 Office 365 郵件加密 (OME) 用於 Exchange Online。
- SharePoint 使用應用程式強制限制。
- SharePoint 會針對僅限瀏覽器存取使用存取控制原則，並封鎖未受控裝置的存取。

## <a name="mapping-microsoft-365-for-enterprise-features-to-contosos-data-levels"></a>將 Microsoft 365 企業版功能對應至 Contoso 的資料層級

下表將 Contoso 的資料層級對應至 Microsoft 365 for enterprise 中的資訊保護功能。

| 層級 | Microsoft 365 雲端服務 | Windows 10 和 Microsoft 365 Apps 企業版 | 安全性與合規性 |
|:-------|:-----|:-----|:-----|
| 第 1 級：基準  | SharePoint 和 Exchange Online 條件式存取原則 <BR> SharePoint 網站的權限 | 敏感度標籤 <BR> BitLocker <BR> Windows 資訊保護 | 裝置條件式存取原則和行動裝置應用程式管理原則 |
| 第 2 級：敏感性 | 第 1 級增強版： <BR> <BR> 敏感度標籤 <BR> SharePoint 網站上的 Microsoft 365 保留標籤 <BR> SharePoint 和 Exchange Online 的資料外洩防護 <BR> 隔離的 SharePoint 網站  | 第 1 級增強版： <BR> <BR> 數位資產上的敏感度標籤  | 第 1 級 |
| 第 3 級：高管制 | 第 2 級增強版： <BR><BR> 針對營業秘密資訊的使用自己的金鑰 (BYOK) 加密和保護 <BR> 適用於與 Microsoft 365 服務互動的企業營運應用程式 Azure Key Vault | 第 2 級 | 第 1 級 |
|||||

以下是 Contoso 的資訊保護設定結果。

![Contoso 的資訊保護設定結果](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>下一步

[請參閱](contoso-security-summary.md) Contoso 如何針對身分識別與存取管理、威脅防護、資訊保護和安全性管理，使用跨 Microsoft 365 的安全性功能。

## <a name="see-also"></a>請參閱

[安全性藍圖](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)


