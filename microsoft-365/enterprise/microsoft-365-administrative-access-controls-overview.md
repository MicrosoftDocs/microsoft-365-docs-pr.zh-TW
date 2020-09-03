---
title: Microsoft 365 中的管理存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 本文提供 Microsoft 365 中的「管理存取控制」和「資料分類」的概述。
ms.openlocfilehash: 817a5907566435d021fe78d89b5c9476c04318d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332589"
---
# <a name="administrative-access-controls-in-microsoft-365"></a>Microsoft 365 中的管理存取控制 

Microsoft 投入大量的系統和控制，可自動化大多數的 Microsoft 365 作業，並在 Microsoft 中故意限制存取客戶內容。 人工管理服務，軟體會運作服務。 這可讓 Microsoft 以比例管理 Microsoft 365，以管理對客戶內容的內部威脅風險。

根據預設，Microsoft 工程師在使用 Microsoft 365 的系統管理許可權中有零的管理許可權，且可以存取客戶內容。 Microsoft 工程師在有限的時間內，可對客戶的內容進行有限、經過審核和安全的存取。 只有在服務作業必要時才能存取，而且只有在 Microsoft 高層管理成員核准時，才可存取。 針對客戶密碼箱授權的客戶，客戶可對其主控于 Microsoft 365 的內容提供存取核准。

Microsoft 提供使用多種形式的雲端傳遞的線上服務：

- **公用雲彩：** 包含多承租人版本的 Microsoft 365、Azure 及其他主控于北美、南美洲、歐洲、亞洲、澳大利亞等的服務。
- **國家雲彩：** 包括美國以外的所有以及主權和協力廠商運作的雲彩 (，但除了上述) 之外，它是由 Microsoft 運作的中國 (中的 Microsoft 365，而由 Microsoft 使用的德國) 中的 Microsoft 365，但在該模型下，在此模型中，您可以控制並監控 Microsoft 對客戶資料和包含客戶資料 (的系統的存取。
- **政府雲彩：** 包含適用于美國政府客戶的 Microsoft 365 和 Azure 服務。

基於本文的目的，Microsoft 365 服務包括：

- [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)
- [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [商務用 OneDrive](https://docs.microsoft.com/OneDrive/onedrive)
- [商務用 Skype](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a>Microsoft 365 存取控制

針對存取控制目的，Microsoft 會將 Microsoft 365 資料分類為客戶資料或其他類型的資料。

### <a name="customer-data"></a>客戶資料

「客戶資料」是使用 Microsoft 365 服務時，代表客戶提供的所有資料。 這是 Microsoft 365 使用者直接建立或上傳的客戶內容，包括：

- 電子郵件
- SharePoint 線上內容
- 立即訊息
- 行事曆專案
- 文件
- Contacts
- 使用者識別資訊 (EUII () 使用者特有或 linkable 個別使用者的資料，但不包括客戶內容) 

### <a name="other-types-of-data"></a>其他類型的資料

其他類型的資料包括：

- **帳戶資料：** 包含系統管理員在註冊或購買服務) 時所提供的管理資料 (資訊，以及付款資料 (相關的付款資訊，例如信用卡詳細資料) 。
- **組織識別資訊：** 包含用來識別租使用者、使用狀況資料，而不是 linkable 給個別使用者或包含在客戶內容中的資料。
- **系統中繼資料：** 包含服務記錄，包含有關訂閱及承租人的設定設定、系統狀態、Microsoft IP 位址和技術資訊。

Microsoft 已建立存取控制機制，以確保沒有人撤銷對客戶資料或存取控制資料的存取。 存取控制資料可管理環境中其他類型的資料或功能，包括存取客戶內容或 EUII、Microsoft 密碼、安全性憑證及其他驗證相關資料。 存取控制機制也會防止對 Microsoft 365 生產環境進行未核准的實體、邏輯或遠端存取。

Microsoft 使用 Microsoft 365 的存取控制類別有三種：

- 隔離控制項
- 人員控制
- 技術控制項

結合時，這些控制項可協助防止及偵測 Microsoft 365 中的惡意動作。 除了 Microsoft 所用的隔離、人員和技術控制項之外，還有第四個控制項類別：由客戶實施。

Microsoft 365 可讓您在內部部署環境中管理資料的方式相同。 註冊 Microsoft 365 組織的人員，會自動成為全域管理員。 全域管理員可以存取管理入口網站中的所有功能，而且可以：

- 建立或編輯使用者
- 指派系統管理員角色給其他人
- 重設使用者密碼
- 管理使用者授權
- 管理網域
- 核准客戶加密箱要求

建議每個組織至少要設定兩個系統管理員帳戶。 對於大型企業組織，我們建議針對不同功能的特殊系統管理員帳戶。

如需指派系統管理員角色和許可權的相關資訊，請參閱 [指派系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) 及 [關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="related-links"></a>相關連結

- [隔離控制項](microsoft-365-isolation-controls.md)
- [人員控制項](microsoft-365-personnel-controls.md)
- [技術控制項](microsoft-365-technology-controls.md)
- [監視及稽核的存取控制](microsoft-365-monitoring-and-auditing-access-controls.md)
- [Yammer 企業存取控制](microsoft-365-yammer-enterprise-access-controls.md)
