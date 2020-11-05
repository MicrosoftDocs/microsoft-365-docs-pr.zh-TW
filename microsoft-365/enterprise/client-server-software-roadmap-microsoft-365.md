---
title: Microsoft 365 的用戶端與伺服器軟體藍圖
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: it-pro
description: 使用此藍圖設定 Microsoft 365 的用戶端和伺服器軟體。
ms.openlocfilehash: 2fb63f73ad49c68cbeb6c92497835c36f9faf737
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920439"
---
# <a name="client-and-server-software-roadmap-for-microsoft-365"></a>Microsoft 365 的用戶端與伺服器軟體藍圖

大多數的企業組織都有異構環境，包括多個版本的作業系統、用戶端軟體和伺服器軟體。 Microsoft 365 企業版包含您 IT 基礎結構最安全的主要元件版本。 此外，它也包含可讓您利用雲端技術的生產力功能。

若要充分發揮 Microsoft 365 企業版產品整合套件的商務價值，請開始規劃並實作策略以移轉以下版本：

- 您的電腦上安裝的 Office 用戶端至 Microsoft 365 應用程式 enterprise。
- 在您的伺服器上安裝到其對等服務的 Office 伺服器至 Microsoft 365。
- 裝置上的 windows 7 和 Windows 8.1 至 Windows 10 企業版。

>[!Note]
>Windows 7 的支援已于 *2020 年1月14日* 結束。 如需詳細資訊，請參閱 [支援終止的詳細資料](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)。
>

當您隨時間完成這些遷移時，您的組織會更接近 [現代辦公環境](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)的願景。 這種安全且整合的環境可協助您解除組織中的團隊合作和創造力。 Microsoft 365 企業版可讓您在所有的方式中，同時提供您。

## <a name="migration-for-office-client-products"></a>Office 用戶端產品的遷移

大型和小型組織通常會使用舊版 Office 用戶端產品的組合，例如 Word、Excel 及 PowerPoint。 這些舊版本：

- 可使用最新的安全性更新和支援修復程式進行 [更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) 。 不過，此程式有時是手動進行，而且可能無法在您的整個組織中擴充。
- 不會優化使用 Microsoft 雲端技術，協助您以數位方式轉換您的業務。
- 不提供最新功能。

Microsoft 365 企業版包含適用于企業的 Microsoft 365 應用程式。 此版本的 Office 用戶端產品可搭配 Microsoft 365 企業版授權使用。 它已從 Microsoft 雲端安裝並更新。 Microsoft 365 Apps 企業版授權包括安全性更新和最新功能。 如需詳細資訊，請參閱 [關於適用于企業的 Microsoft 365 應用程式](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。

### <a name="office-2007"></a>Office 2007

若為 office 2007 版本中的 Office 版本，支援的終止已過去。 如需詳細資訊，請參閱 [Office 2007 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)。

請考慮採取下列步驟，而不是將執行 Office 2007 的電腦升級至 Office 2010、Office 2013 或 Office 2016：

1. 為您的使用者取得並指派 Microsoft 365 授權。
2. 在其電腦上卸載 Office 2007。
3. 安裝 Microsoft 365 應用程式 for enterprise （不論是個別安裝或進行 IT 推廣）。 如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。

適用于企業的 Microsoft 365 應用程式會自動安裝更新。 它可利用雲端架構服務，以增強安全性和生產力。

### <a name="office-2010"></a>Office 2010

若為 Office 2010 版本中的 Office 版本，支援已于 *2020 年10月13日* 結束。 如需詳細資訊，請參閱 [Office 2010 終止支援藍圖](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)。

您可以考慮將執行 Office 2010 的電腦升級至 Office 2013 或 Office 2016。 不過，這兩個版本都必須手動更新。 所以請改為採取下列步驟：

1. 為您的使用者取得並指派 Microsoft 365 授權。
2. 在其電腦上卸載 Office 2010。
3. 安裝 Microsoft 365 應用程式 for enterprise （不論是個別安裝或進行 IT 推廣）。 如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。

適用于企業的 Microsoft 365 應用程式會自動同時安裝安全性更新和新功能更新。 它可以利用 Microsoft 365 中的雲端式服務，以獲得增強的安全性和生產力。

### <a name="office-2013-and-office-2016"></a>Office 2013 和 Office 2016

Office 2013 和 Office 2016 的支援終止藍圖尚未決定。 在這些版本（如 Office 2010）中，您仍然必須 [安裝安全性更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)。 這項工作可能無法正常縮放，視組織的規模而定。

請不要使用 Office 2013 或 Office 2016 的最新安全性更新，或是將電腦從 Office 2013 更新為 Office 2016，而讓電腦保持最新的狀態，請考慮採取下列步驟：

1. 為您的使用者取得並指派 Microsoft 365 授權。
2. 卸載其電腦上的 Office 2013 或 Office 2016。
3. 安裝 Microsoft 365 應用程式 for enterprise （不論是個別安裝或進行 IT 推廣）。 如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。

Microsoft 365 應用程式 enterprise 會自動安裝安全性更新和新功能更新。 它可以利用 Microsoft 365 中的雲端式服務，以獲得增強的安全性和生產力。

## <a name="migration-for-office-server-products"></a>Office server 產品遷移

大型及小型組織通常會使用舊版 Office server 產品的組合，例如 Exchange Server 和 SharePoint Server。 這些舊版本：

- 應該更新，以獲得最新的安全性更新和支援修正程式。 在某些情況下，這些更新會每月發行。
- 不會優化使用 Microsoft 雲端技術，協助您以數位方式轉換您的業務。
- 不要包含新的生產力應用程式，例如 Microsoft 團隊。
- 不要包含最新的安全性功能，例如 Exchange 和 Defender for Office 365。

Microsoft 365 Enterprise 包含雲端架構版本的 Office server 服務，其使用一些與 Office server 軟體內部部署版本（如網頁瀏覽器和 Outlook 用戶端）相同的工具。 這些服務會自動更新以取得安全性。 所以，您的 IT 人員可節省維護和更新內部部署伺服器所需的時間。 這些服務也提供 Office server 軟體中不存在的新功能增強功能。

請使用下列資源，以取得針對特定 Microsoft 365 工作負載的使用者和資料進行遷移的相關資訊：

- [將信箱從內部部署 Exchange Server 移至 Exchange Online](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [將 SharePoint 資料從 SharePoint 伺服器遷移至 SharePoint 線上](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [將商務用 Skype Online 遷移至 Microsoft 團隊](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

### <a name="office-2007-server-products"></a>Office 2007 伺服器產品

針對 Office 2007 版本中的伺服器產品，支援終止已過。 如需詳細資訊，請參閱下列文章：

- [Exchange 2007 終止支援藍圖](exchange-2007-end-of-support.md)
- [SharePoint Server 2007 終止支援藍圖](sharepoint-2007-end-of-support.md)
- [Project Server 2007 終止支援藍圖](project-server-2007-end-of-support.md)
- [Office 通訊伺服器支援終止藍圖](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [PerformancePoint Server 2007 終止支援藍圖](pps-2007-end-of-support.md)

請考慮採取下列步驟，而不是使用 office 2010、Office 2013 或 2016 Office 的版本中的伺服器產品來升級 Office 2007 版本中的伺服器產品：

1. 將您的 Office 2007 伺服器上的資料移轉至 Microsoft 365。 如需詳細資訊或協助，請雇用 Microsoft 合作夥伴。
2. 將新的功能和工作流程推廣給您的使用者。
3. 當您不再需要執行 Office 2007 伺服器產品的內部部署伺服器時，請解除其授權。

### <a name="office-2010-server-products"></a>Office 2010 伺服器產品

[Exchange Server 2010](exchange-2010-end-of-support.md)的支援已于 *2020 年10月13日* 結束。

[SharePoint Server 2010](upgrade-from-sharepoint-2010.md) 的支援終止日期為 *2021 年 4 月 13 日* 。

請考慮採取下列步驟，而不是使用 office 2013 或 Office 2016 的發行版本中的伺服器產品升級這些伺服器2010產品：

1. 將您的 Office 2010 伺服器上的資料移轉至 Microsoft 365。 如需詳細資訊，請參閱 [FastTrack For microsoft 365](https://fasttrack.microsoft.com/microsoft365) 或雇用 microsoft partner。
2. 將新的功能和工作流程推廣給您的使用者。
3. 當您不再需要執行 Office 2010 伺服器產品的內部部署伺服器時，請解除其授權。

### <a name="office-2013-server-products"></a>Office 2013 伺服器產品

針對 Office 2013 版本中的伺服器產品，尚未決定支援的終止。 請考慮採取下列步驟，而不是使用 Office 2016 版本中的伺服器產品升級 Office 2013 版本中的伺服器產品：

1. 將您的 Office 2013 伺服器上的資料移轉至 Microsoft 365。 如需詳細資訊，請參閱 [FastTrack For microsoft 365](https://fasttrack.microsoft.com/microsoft365) 或雇用 microsoft partner。
2. 將新的功能和工作流程推廣給您的使用者。
3. 當您不再需要執行 Office 2013 伺服器產品的內部部署伺服器時，請解除其授權。

### <a name="office-2016-server-products"></a>Office 2016 伺服器產品

針對 Office 2016 版本中的伺服器產品，尚未決定支援的終止。 若要利用雲端架構服務和增強功能以數位方式轉換您的企業，請考慮採取下列步驟：

1. 將您的 Office 2016 伺服器上的資料移轉至 Microsoft 365。 如需詳細資訊，請參閱 [FastTrack For microsoft 365](https://fasttrack.microsoft.com/microsoft365) 或雇用 microsoft partner。
2. 將新的功能和工作流程推廣給您的使用者。
3. 當您不再需要執行 Office 2016 伺服器產品的內部部署伺服器時，請解除其授權。

## <a name="migration-for-windows-7-and-81"></a>Windows 7 和8.1 的遷移

Windows 7 在 *2020 年1月14日* 已結束支援。 若要遷移執行 Windows 7 或 Windows 8.1 的裝置，您可以執行就地升級。

如需其他方法，請參閱 [Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。 您也可以自行[規劃 Windows 10 部署](https://aka.ms/planforwin10deployment)。

## <a name="office-2010-clients-and-servers-and-windows-7"></a>Office 2010 用戶端和伺服器及 Windows 7

以下是 Office 2010 用戶端和伺服器及 Windows 7 的升級、遷移和移至雲端選項的視覺摘要：

[![顯示 Office 2010 用戶端和伺服器及 Windows 7 支援終止選項的影像。](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

這個單頁標牌是一種快速瞭解可用於管理 Office 2010 用戶端和伺服器產品及 Windows 7 支援的路徑。 Microsoft 365 企業版支援偏好的路徑。

您可以 [下載此標牌](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) ，並以 letter 大小、合法大小或 tabloid 列印它，) 大小 (11 x 17。

## <a name="transition-your-entire-organization"></a>轉換整個組織

若要深入瞭解如何將整個組織移至 Microsoft 365 企業版中的產品和服務，請下載此轉換海報：

[![顯示轉換至 Microsoft 365 海報的圖像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

這份雙頁海報是清查現有基礎結構的快速方式。 使用它來取得移至 Microsoft 365 企業版產品或服務的指導方針。 它會顯示 Windows 和 Office 產品及其他基礎結構及安全性元素，例如裝置管理、身分識別和威脅防護，以及資訊和合規性防護。

## <a name="how-microsoft-migrated-to-microsoft-365-enterprise"></a>Microsoft 如何遷移至 Microsoft 365 Enterprise

請參閱 Microsoft IT 專家如何將公司遷移至 Microsoft 365 企業版：

- [部署和更新適用于企業的 Microsoft 365 應用程式](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft 會將 150000 個信箱移轉到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [在 Microsoft 以就地升級方式部署 Windows 10](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Windows 10 部署： MICROSOFT IT (影片) 的秘訣和技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)
