---
title: 步驟 4： Microsoft 365 for enterprise 承租人的遷移
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 針對您的 Microsoft 365 承租人遷移您的 Windows 裝置、Office 用戶端應用程式及 Office server。
ms.openlocfilehash: 85f1c0d927b881c4d1526ce538ae54f5954a0664
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406357"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>步驟 4. Microsoft 365 for enterprise 承租人的遷移

大多數的企業組織都有異構環境，包括多個版本的作業系統、用戶端軟體和伺服器軟體。 適用于企業的 Microsoft 365 包括 IT 基礎結構主要元件的最安全版本。 此外，它也包含可讓您利用雲端技術的生產力功能。

若要最大化 Microsoft 365 的企業整合套件的商業價值，請開始規劃及執行策略，以遷移這些版本：

| 寄件者 | 收件者 |
|:-------|:-----|
| Windows 7 和 Windows 8。1 | Windows 10 企業版 |
| 在您的工作人員裝置上安裝的 Office 用戶端產品 | Microsoft 365 Apps 企業版 |
| 在內部部署伺服器上安裝的 Office server 產品 | Microsoft 365 中其對等雲端型服務 |
|  |  |

## <a name="migrating-to-windows-10"></a>遷移至 Windows 10

每個 Microsoft 365 for enterprise license 都包含 Windows 10 企業版的授權。 若要遷移執行 Windows 7 或 Windows 8.1 的裝置，您可以執行就地升級。 Windows 7 在 *2020 年1月14日* 已結束支援。 

如需在就地升級之外安裝 Windows 10 企業版的其他方法，請參閱 [Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。 您也可以自行[規劃 Windows 10 部署](https://aka.ms/planforwin10deployment)。

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>遷移至適用于企業的 Microsoft 365 應用程式

適用于企業的 microsoft 365 包括 Microsoft 365 應用程式的企業版、Office 用戶端產品的版本 (Word、PowerPoint、Excel 和 Outlook) 已從 Microsoft 雲端安裝及更新。 如需詳細資訊，請參閱 [關於適用于企業的 Microsoft 365 應用程式](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。

請執行下列步驟，而不是讓您的電腦成為 Office 2019 或舊版的最新版本：

1. 為您的使用者取得並指派 Microsoft 365 授權。
2. 卸載其電腦上的 Office 2013 或 Office 2016。
3. 安裝 Microsoft 365 應用程式 for enterprise （不論是個別安裝或進行 IT 推廣）。 如需詳細資訊，請參閱 [Microsoft 365 應用程式的部署指南](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。

Microsoft 365 應用程式的企業應用程式會自動安裝安全性更新和新功能，並可利用 Microsoft 365 中的雲端式服務，以獲得增強的安全性和生產力。

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>將內部部署伺服器和資料移轉至 Microsoft 365

Microsoft 365 for enterprise 包含雲端架構版本的 Office server 服務，其使用一些與 Office server 軟體內部部署版本（如網頁瀏覽器和 Outlook 用戶端）相同的工具。 這些雲端式服務會自動更新，以取得安全性和新功能。 遷移後，您的 IT 部門可以節省維護和更新內部部署伺服器所需的時間。

請使用下列資源，以取得針對特定 Microsoft 365 工作負載的使用者和資料進行遷移的相關資訊：

- [將信箱從內部部署 Exchange Server 移至 Exchange Online](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [將 SharePoint 資料從 SharePoint 伺服器遷移至 SharePoint 線上](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [將商務用 Skype Online 遷移至 Microsoft 團隊](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>轉換整個組織

若要深入瞭解如何將整個組織移至 Microsoft 365 for enterprise 中的產品和服務，請下載此轉換海報：

[![顯示轉換至 Microsoft 365 海報的圖像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

這份雙頁海報是清查現有基礎結構的快速方式。 使用此功能，取得在 Microsoft 365 for enterprise 中移至產品或服務的指導方針。 它會顯示 Windows 和 Office 產品及其他基礎結構及安全性元素，例如裝置管理、身分識別和威脅防護，以及資訊保護和符合性。

## <a name="results-of-step-4"></a>步驟 4 的結果

針對您的 Microsoft 365 承租人進行遷移，您已決定：

- 哪些裝置執行 Windows 7 或 Windows 8.1，以及將其更新至 Windows 10 企業版的計畫。
- 哪些裝置執行 Office 用戶端應用程式，以及將其更新至 Microsoft 365 應用程式以進行企業版的計畫。
- 哪些內部部署 Office server 服務應遷移至其 Microsoft 365 對等專案，以及遷移其資料的計畫。

以下是承租人的範例，其中包含已完成的內部部署伺服器遷移。

![已完成內部部署伺服器遷移的承租人範例](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

在此圖中，組織的：

- 已將其內部部署 Exchange 伺服器信箱遷移至 Exchange Online。
- 將其內部部署 SharePoint 伺服器網站和資料移轉至 Microsoft 365 中 SharePoint。

## <a name="ongoing-maintenance-for-migration"></a>進行遷移的持續維護

您可能需要進行下列作業：

- 請根據您的 Exchange 信箱遷移狀態，繼續在您的組織中滾動轉換至 Exchange。
- 請根據您的內部部署 SharePoint 網站遷移狀態，繼續將 Microsoft 365 中 SharePoint 轉換為您的組織。

## <a name="next-step"></a>下一步

[![步驟5。部署裝置和應用程式管理](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

繼續進行 [裝置和應用程式管理](tenant-management-device-management.md) ，以部署裝置和應用程式管理。
