---
title: Microsoft 365 企業版工作負載和案例
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 讓貴組織的使用者快速上手 Microsoft 365 企業版的生產力工作負載。
ms.openlocfilehash: 30dbf913016687025c6159f1f1fc311462a13d29
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400137"
---
# <a name="microsoft-365-enterprise-workloads-and-scenarios"></a>Microsoft 365 企業版工作負載和案例

若要獲得 Microsoft 365 企業版的創意暨團隊合作優點，請將這些工作負載部署到底層基礎結構上：

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint Online](sharepoint-online-onedrive-workload.md)

請參閱[移轉](migration-microsoft-365-enterprise-workload.md)工作負載，以了解用來將整個組織遷移到 Microsoft 365 企業版的一般藍圖，其內含 Microsoft Office 用戶端產品、內部部署 Office Server 產品和 Microsoft Windows 架構裝置。

這些案例會以整合方式使用來自 Microsoft 365 企業版的功能和服務，以因應商務需求。 其中一個這類需求是保護 Microsoft 365 中所儲存的高管制資料。 高管制資料包含下列數位資產：

- 受限於區域法規。
- 貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。

若要讓此資料免於遭受內部和外部威脅，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站](teams-sharepoint-online-sites-highly-regulated-data.md)中的指示。 此案例會逐步引導您完成 SharePoint Online 網站或 Microsoft Teams 小組的設定，以便安全地儲存您最有價值的資料。

以下是整體 Microsoft 365 企業版部署指南中的工作負載和案例：

![](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a>底層基礎結構先決條件

理論上**，您應該在設定好[底層基礎結構](deploy-foundation-infrastructure.md)的所有階段後部署工作負載和案例。 這可確保所有基礎層級都已就緒，而可為使用者及其裝置提供整合、安全性及最佳體驗。

| 階段 | 結果 |
|:-------|:-----|
| 網路 | 網路會進行更新，以獲得最佳的 Microsoft 365 雲端服務效能。 |
| 身分識別 | 身分識別會進行同步處理，並讓使用者帳戶使用增強式驗證以及讓系統管理員帳戶使用保護機制來確保身分識別的安全。 |
| Windows 10 企業版 | 執行 Windows 7 或 Windows 8.1 的電腦可升級為 Windows 10 企業版，且新裝置會使用 Windows 10 企業版來進行安裝。 |
| Office 365 專業增強版 | 現有的 Microsoft Office 使用者可升級為 Office 365 專業增強版。 |
| 行動裝置管理 | 裝置可以進行註冊並受到管理。 |
| 資訊保護 | 會啟用 Office 365 安全性功能，且敏感度標籤或 Azure 資訊保護標籤已準備好而可保護文件。 |

請記住，這是理想狀況，您可能需要花點時間來規劃、設定、測試和試驗，尤其是有既存基礎結構和多個位置的大型組織更是如此。 您不一定要為了更快速地從 Microsoft 365 企業版獲得商業價值，而在所有位置都備有上述所有層級。 

以下是一些要立即部署的常見工作負載： 

- 在對使用者推出底層基礎結構的**身分識別**層級後，許多組織會部署：
  - [Office 365 專業增強版](office365proplus-infrastructure.md)加上[商務用 OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。 Office 365 專業增強版可提供新式驗證的安全性和最新 Microsoft Office 用戶端的使用者體驗。 將使用者的個人檔案遷移到商務用 OneDrive 會減少基礎結構和對於主資料夾及主目錄磁碟的支援需求。
  - [Exchange Online](exchangeonline-workload.md)，讓使用者可以開始使用雲端式電子郵件。
- 如果您並非立即需要在雲端中儲存高管制的數位資產，請先為使用者部署 [Microsoft Teams](teams-workload.md) 和 [SharePoint Online](sharepoint-online-onedrive-workload.md)，再部署**資訊保護**層級。

您必須決定要如何針對底層基礎結構的先決條件階段，做出最佳的設定順序並進行部署，才會最能符合您的業務需求。

### <a name="best-practice"></a>最佳作法

強烈建議您先部署和推出底層基礎結構的**身分識別**階段，再讓使用者快速上手工作負載或案例。

**身分識別**階段可確保雲端式身分識別 (無論是只有雲端，還是會與內部部署 Active Directory Domain Services (AD DS) 同步處理) 會包含可用來管理驗證及存取的使用者和電腦帳戶與群組。 所有使用者都必須使用增強式驗證且系統管理員帳戶必須使用增強式保護，才能將組織的數位資產放入 Microsoft 365 雲端。

雖然整體效能屬於基礎要求且非常重要，但您還是可以在讓使用者快速上手工作負載時同時在網路上推出**網路**階段，因為您知道 Microsoft 365應用程式和服務的效能會慢慢改善。

對於有多個位置並混合使用邊緣裝置與網際網路連線的企業組織來說，更是如此。
