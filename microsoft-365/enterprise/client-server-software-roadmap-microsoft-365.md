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
ms.openlocfilehash: ee101b3ba148f1075939d56904dc9d2ecf14e1b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905197"
---
# <a name="client-and-server-software-roadmap-for-microsoft-365"></a>Microsoft 365 的用戶端與伺服器軟體藍圖

大多數的企業組織都有異構環境，包括多個版本的作業系統、用戶端軟體和伺服器軟體。 Enterprise 的 Microsoft 365 包含您的 IT 基礎結構最安全的主要元件版本。 此外，它也包含可讓您利用雲端技術的生產力功能。

若要最大化 Enterprise 整合產品套件的 Microsoft 365 商業價值，請開始規劃及執行遷移版本的策略：

- 電腦上所安裝的 Office 用戶端，以進行 Microsoft 365 Apps 企業版。
- 伺服器上安裝的 Office 伺服器與 Microsoft 365 中的對等服務。
- 在您的裝置上 Windows 7 和 Windows 8.1 Windows 10 企業版。

>[!Note]
>支援 Windows 7 于 *2020 年1月14日* 結束。 如需詳細資訊，請參閱 [支援終止的詳細資料](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)。
>

當您隨時間完成這些遷移時，您的組織會更接近 [現代辦公環境](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)的願景。 這種安全且整合的環境可協助您解除組織中的團隊合作和創造力。 Enterprise 的 Microsoft 365 可讓您在所有的方式上啟用及提供。

## <a name="migration-for-office-client-products"></a>Office 用戶端產品的遷移

大型和小型組織通常會使用舊版本 Office 用戶端產品的組合，例如 Word、Excel 及 PowerPoint。 這些舊版本：

- 可使用最新的安全性更新和支援修復程式進行 [更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) 。 不過，此程式有時是手動進行，而且可能無法在您的整個組織中擴充。
- 不會優化使用 Microsoft 雲端技術，協助您以數位方式轉換您的業務。
- 不提供最新功能。

Enterprise 的 Microsoft 365 包含 Microsoft 365 Apps 企業版。 Enterprise 授權的 Microsoft 365 提供此 Office 用戶端產品的版本。 它已從 Microsoft 雲端安裝並更新。 Microsoft 365 Apps 企業版授權包括安全性更新和最新功能。 如需詳細資訊，請參閱[關於 Microsoft 365 Apps 企業版](/deployoffice/about-microsoft-365-apps)。

### <a name="office-2007"></a>Office 2007

針對 Office 2007 版本中 Office 的版本，支援終止已過。 如需詳細資訊，請參閱[Office 2007 的支援終止藍圖](/deployoffice/office-2007-end-support-roadmap)。

請考慮採取下列步驟，而不是將執行 Office 2007 的電腦升級為 Office 2010、Office 2013 或 Office 2016。

1. 為您的使用者取得並指派 Microsoft 365 授權。
2. 在其電腦上卸載 Office 2007。
3. 請個別安裝 Microsoft 365 Apps 企業版，或是在 IT 首展期間安裝。 如需詳細資訊，請參閱 [Microsoft 365 Apps 的部署指南](/deployoffice/deployment-guide-microsoft-365-apps)。

Microsoft 365 Apps 企業版會自動安裝更新。 它可利用雲端架構服務，以增強安全性和生產力。

### <a name="office-2010"></a>Office 2010

針對 Office 2010 版本的 Office 版本，支援于 *2020 年10月13日* 結束。 如需詳細資訊，請參閱[Office 2010 的支援終止藍圖](/deployoffice/office-2010-end-support-roadmap)。

您可以考慮將執行 Office 2010 的電腦升級成 Office 2013 或 Office 2016。 不過，這兩個版本都必須手動更新。 所以請改為採取下列步驟：

1. 為您的使用者取得並指派 Microsoft 365 授權。
2. 在其電腦上卸載 Office 2010。
3. 請個別安裝 Microsoft 365 Apps 企業版，或是在 IT 首展期間安裝。 如需詳細資訊，請參閱 [Microsoft 365 Apps 的部署指南](/deployoffice/deployment-guide-microsoft-365-apps)。

Microsoft 365 Apps 企業版會自動安裝安全性更新和新功能更新。 它可以利用 Microsoft 365 中的雲端式服務，以獲得增強的安全性和生產力。

### <a name="office-2013-and-office-2016"></a>Office 2013 和 Office 2016

請參閱[Office 2013 的支援終止藍圖](/lifecycle/products/microsoft-office-2013)。 Office 2016 的支援結束，尚未決定。 在這些版本（如 Office 2010）中，您仍然必須[安裝安全性更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)。 這項工作可能無法正常縮放，視組織的規模而定。

不必使用 Office 2013 或 Office 2016 的最新安全性更新，或是將您的電腦從 Office 2013 更新為 Office 2016，而讓電腦保持最新的狀態，請考慮採取下列步驟：

1. 為您的使用者取得並指派 Microsoft 365 授權。
2. 在其電腦上卸載 Office 2013 或 Office 2016。
3. 請個別安裝 Microsoft 365 Apps 企業版，或是在 IT 首展期間安裝。 如需詳細資訊，請參閱 [Microsoft 365 Apps 的部署指南](/deployoffice/deployment-guide-microsoft-365-apps)。

Microsoft 365 Apps 企業版會自動安裝安全性更新和新功能更新。 它可以利用 Microsoft 365 中的雲端式服務，以獲得增強的安全性和生產力。

## <a name="migration-for-office-server-products"></a>Office 伺服器產品的遷移

大型及小型組織通常會使用舊版 Office 伺服器產品的組合，例如 Exchange Server 和 SharePoint 伺服器。 這些舊版本：

- 應使用最新的安全性更新和支援修正進行更新。在某些情況下，這些更新會每月發行。
- 不會優化使用 Microsoft 雲端技術，協助您以數位方式轉換您的業務。
- 不要包含新的生產力應用程式，例如 Microsoft Teams。
- 請勿包含最新的安全性功能，例如 Office 365 Exchange 和 Defender。

Enterprise Microsoft 365 包括雲端架構版本的 Office server 服務，其使用一些與內部部署版本 Office server 軟體相同的工具，例如 web 瀏覽器和 Outlook 用戶端。 這些服務會自動更新以取得安全性。 所以，您的 IT 人員可節省維護和更新內部部署伺服器所需的時間。 這些服務也提供 Office server 軟體中不存在的新功能增強功能。

請使用下列資源，以取得針對特定 Microsoft 365 工作負載遷移使用者和資料的相關資訊：

- [將信箱從內部部署 Exchange Server 移至 Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [將 SharePoint 資料從 SharePoint 伺服器遷移至 SharePoint 線上](/sharepointmigration/migrate-to-sharepoint-online)
- [將商務用 Skype 線上遷移至 Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

### <a name="office-2007-server-products"></a>Office 2007 伺服器產品

在 Office 2007 版本的伺服器產品中，支援的終止已過。 如需詳細資訊，請參閱下列文章：

- [Exchange 2007 支援終止藍圖](exchange-2007-end-of-support.md)
- [SharePoint伺服器2007的支援終止藍圖](sharepoint-2007-end-of-support.md)
- [Project伺服器2007的支援終止藍圖](project-server-2007-end-of-support.md)
- [Office通訊伺服器支援終止藍圖](/skypeforbusiness/plan-your-deployment/upgrade)
- [PerformancePoint Server 2007 支援終止藍圖](pps-2007-end-of-support.md)

請考慮採取下列步驟，而不是將 Office 2007 版本中的伺服器產品升級成 Office 2010、Office 2013 或 Office 2016 的版本：

1. 將 Office 2007 伺服器上的資料移轉至 Microsoft 365。 如需詳細資訊或協助，請雇用 Microsoft 合作夥伴。
2. 將新的功能和工作流程推廣給您的使用者。
3. 當您不再需要執行 Office 2007 伺服器產品的內部部署伺服器時，請解除其授權。

### <a name="office-2010-server-products"></a>Office 2010 伺服器產品

對 [Exchange Server 2010](exchange-2010-end-of-support.md)的支援已于 *2020 年10月13日* 結束。

[SharePoint Server 2010](upgrade-from-sharepoint-2010.md) 的支援終止日期為 *2021 年 4 月 13 日*。

請考慮採取下列步驟，而不是將 Office 2010 版本的伺服器產品升級為 Office 2013 或 Office 2016 的版本：

1. 將 Office 2010 伺服器上的資料移轉至 Microsoft 365。 如需詳細資訊，請參閱[FastTrack Microsoft 365](https://fasttrack.microsoft.com/microsoft365)或雇用 Microsoft 合作夥伴。
2. 將新的功能和工作流程推廣給您的使用者。
3. 當您不再需要執行 Office 2010 伺服器產品的內部部署伺服器時，請解除其授權。

### <a name="office-2013-server-products"></a>Office 2013 伺服器產品

在 Office 2013 版本中的伺服器產品，尚未決定支援的結束。 請考慮採取下列步驟，而不是使用 Office 2016 版本中的伺服器產品升級 Office 2013 版本中的伺服器產品：

1. 將 Office 2013 伺服器上的資料移轉至 Microsoft 365。 如需詳細資訊，請參閱[FastTrack Microsoft 365](https://fasttrack.microsoft.com/microsoft365)或雇用 Microsoft 合作夥伴。
2. 將新的功能和工作流程推廣給您的使用者。
3. 當您不再需要執行 Office 2013 伺服器產品的內部部署伺服器時，請解除其授權。

### <a name="office-2016-server-products"></a>Office 2016 伺服器產品

在 Office 2016 版本中的伺服器產品，尚未決定支援的結束。 若要利用雲端架構服務和增強功能以數位方式轉換您的企業，請考慮採取下列步驟：

1. 將 Office 2016 伺服器上的資料移轉至 Microsoft 365。 如需詳細資訊，請參閱[FastTrack Microsoft 365](https://fasttrack.microsoft.com/microsoft365)或雇用 Microsoft 合作夥伴。
2. 將新的功能和工作流程推廣給您的使用者。
3. 當您不再需要執行 Office 2016 伺服器產品的內部部署伺服器時，請解除其授權。

## <a name="migration-for-windows-7-and-81"></a>Windows 7 和8.1 的遷移

支援于 *2020 年1月14日* 在 Windows 7 上結束。 若要遷移執行 Windows 7 或 Windows 8.1 的裝置，您可以執行就地升級。

如需其他方法，請參閱 [Windows 10 部署案例](/windows/deployment/windows-10-deployment-scenarios)。您也可以自行[規劃 Windows 10 部署](/windows/deployment/planning/)。

## <a name="office-2010-clients-and-servers-and-windows-7"></a>Office 2010 用戶端和伺服器及 Windows 7

以下是 Office 2010 用戶端和伺服器及 Windows 7 的升級、遷移和移至雲端選項的視覺摘要：

[![顯示 Office 2010 用戶端和伺服器及 Windows 7 的支援結束選項的影像。](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

這個單頁標牌是一種快速瞭解可用於管理 Office 2010 用戶端和伺服器產品及 Windows 7 支援的支援途徑。 Enterprise 的 Microsoft 365 支援慣用的路徑。

您可以 [下載此標牌](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) ，並以 letter 大小、合法大小或 tabloid 列印它，) 大小 (11 x 17。

## <a name="transition-your-entire-organization"></a>轉換整個組織

若要深入瞭解如何將整個組織移至 Enterprise Microsoft 365 中的產品和服務，請下載此轉換海報：

[![顯示轉換為 Microsoft 365 海報的圖像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

這份雙頁海報是清查現有基礎結構的快速方式。 使用它來取得在 Enterprise Microsoft 365 中移至產品或服務的指導方針。 它會顯示 Windows 和 Office 產品及其他基礎結構及安全性元素，例如裝置管理、身分識別和威脅防護，以及資訊和合規性防護。

## <a name="how-microsoft-migrated-to-microsoft-365-for-enterprise"></a>Microsoft 如何遷移至 Microsoft 365 以進行 Enterprise

請參閱 Microsoft 的 IT 專家如何將公司遷移至 Microsoft 365 進行 Enterprise：

- [部署和更新 Microsoft 365 Apps 企業版](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft 會將 150000 個信箱移轉到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [在 Microsoft 以就地升級方式部署 Windows 10](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Windows 10 部署：從 Microsoft IT (影片提示和訣竅](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)) 