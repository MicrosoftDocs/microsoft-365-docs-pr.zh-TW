---
title: 第4 階段：Office 365 專業增強版
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 企業版 Office 365 專業增強版的部署步驟。
ms.openlocfilehash: cf698e4dbee17a811a4d2bc01d08d4d97d1961c1
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074173"
---
# <a name="phase-4-office-365-proplus"></a>第4 階段：Office 365 專業增強版

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*本文同時適用於 Microsoft 365 企業版和 Microsoft 365 教育版的 E3 和 E5 版本*

Microsoft 365 企業版包含 Office 365 專業增強版，是 Office 的訂閱版本。和 Office 2016 一樣，Office 365 專業增強版包含所有 Office 應用程式，這些應用程式直接安裝在用戶端裝置上。但不同於 Office 2016，Office 365 專業增強版會定期更新新功能，而且採用使用者授權模型，使用者最多可以在 5 個裝置上安裝 Office。如需詳細資訊，請參閱[有關企業中的 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。

您在這個階段將 Office 365 專業增強版部署到用戶端裝置，這是 Microsoft 365 企業版的一部分。除了本指引，我們建議您使用 [Microsoft Fastrack](https://fasttrack.microsoft.com/office) 來進行部署。 

Office 365 專業增強版達成了 Microsoft 365 企業版的這些策略商務案例：

- 即時或自己運用時間在文件上共同作業，簡化共同建立的程序
- 運用集體知識和專業技能，讓組織中的使用者可探索、共用及改善檔案、資訊和想法
- 讓使用者能夠轉換商務程序並提高效率
- 管理專案、工作和截止日期，達成業務目標
- 使用智慧型協助進行設計、撰寫、內容探索等，有助於讓您的工作成績更亮眼
- 探索深入解析、分析資料，並共用您的發現，協助每個人做出明智決策
- 與小組溝通以取得最新資訊、要求輸入，並建立凝聚力和共識
- 與全球的合作夥伴、同事及客戶聯絡，以各種規模的群組進行排定與臨時的通話及線上會議
- 在組織內外部儲存及共用檔案，順暢地跨越組織界限工作
- 隨時隨地在裝置上安全地工作，以達成更多目標，同時維持彈性的工作方式
- 通過產業驗證符合合規性的全球標準，提供控制和可見度讓您安心
- 保護您的資訊，並降低資料遺失風險
- 為桌面軟體與裝置取得並保持在目前最新狀態，同時降低安全性風險並將 IT 部門的效率最大化

如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。 

如果您已部署 Office 365 專業增強版，請參閱此階段的[允出準則](office365proplus-exit-criteria.md)，以確保其符合 Microsoft 365 企業版的必要條件。

>[!Note]
>若要同時部署 Windows 10 企業版和 Office 365 專業增強版，請參閱[桌面部署中心](desktop-deployment-center-home.md)。
>

## <a name="step-1-assess-your-environment"></a>步驟 1：評估環境

部署 Office 365 專業增強版之前，請遵循[針對部署 Office 365 專業增強版評估環境和需求](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)中的指引。此評估包括系統需求、用戶端裝置的詳細資料 (例如架構、所需的語言)、 授權需求、網路功能、應用程式相容性。完成評估可協助您為規劃部署做出重要決策。

## <a name="step-2-plan-your-deployment"></a>步驟 2：規劃部署

評估環境之後，請遵循[規劃 Office 365 專業增強版的部署](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)中的指引建立部署規劃。規劃包含下列決策： 

- 如何部署 Office，包括要使用哪些工具 (例如 System Center 設定管理員或 Office 部署工具 [ODT])，以及從何處安裝 Office
- 如何管理 Office 的更新
- 使用哪些更新通道 (Office 更新通道可控制使用者收到 Office 應用程式功能更新的頻率)
- 您想要使用的 Office 安裝套件和部署群組，包括哪些使用者應安裝哪些 Office 應用程式和語言

[規劃文章](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)中有這些選項的最佳做法，包括管理部署、管理更新、定義安裝套件、建立部署群組。 

## <a name="step-3-deploy"></a>步驟 3：部署

根據您在步驟 2 中的部署，選擇您要部署的方式：

- **[使用 System Center 設定管理員部署 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager)：** 使用設定管理員部署管理，從網路上的發佈點下載並部署 Office

- **[使用 ODT 從雲端部署 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud)：** 使用 ODT 管理部署，直接從 Office CDN 將 Office 安裝在用戶端裝置上
 
- **[使用 ODT 從本機來源部署 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source)：** 使用 ODT 管理部署，直接從網路上的本機來源下載並部署 Office 

- **[從 Office 入口網站自行安裝 Office 365 專業增強版](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658)：** 從 Office 入口網站管理部署，讓使用者直接從入口網站將 Office 安裝在他們的用戶端裝置上

許多組織會組合使用這些選項讓不同使用者使用。例如，組織可能會使用設定管理員為大部分的使用者部署 Office，但為一小群不常連線到內部網路的工作者啟用自行安裝。 

如果您的組織使用設定管理員，建議您升級至最新分支並更新至最新版本。如需詳細資訊，請參閱[我應該使用設定管理員的哪一個分支？](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

了解 Microsoft 的專家如何[部署和管理 Office 365 專業增強版的更新](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR7)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何[部署 Office 365 專業增強版](contoso-o365pp.md)。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>下一步

[Office 365 ProPlus 基礎結構允出準則](office365proplus-exit-criteria.md)
