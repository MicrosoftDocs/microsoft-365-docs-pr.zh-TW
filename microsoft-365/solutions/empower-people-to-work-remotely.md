---
title: 使用 Microsoft 365 強化遠端工作者
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/23/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
ms.custom: ''
description: 設定安全性和服務基礎結構，讓您的工作人員隨時隨地都能遠端工作。
ms.openlocfilehash: 17cc826f5cf28ff375deaf1e6a4b192700eebf2f
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898125"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>使用 Microsoft 365 強化遠端工作者

貴組織可能必須讓工作人員能夠從家裡安全地存取貴組織的內部部署與雲端式資訊、工具及資源。 允許員工遠端辦公對許多組織達到以下目的非常重要:

- 節省辦公室空間。
- 聘用並留住不願意調派的工作人員。
- 縮短工作人員的通勤時間，讓他們有更多時間來提高生產力，並在下班後放鬆壓力。

Microsoft 365 具備讓您的工作人員能夠遠端作業的功能。

![使用 Microsoft 365 強化您的遠端工作人員](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

| 主要功能 | 說明 |
|:-------|:-----|
| 連接 | 遠端工作人員必須能夠隨時隨地存取： <ul><li>您的 Microsoft 365 訂閱中的雲端服務和資料。 </li><li>組織資源，例如內部部署應用程式資料中心所提供的資源。</li></ul> |
| 安全 | 以 Microsoft 365 和 Windows 10 的多重要素驗證（MFA）和內建安全性功能保護登入，避免惡意程式碼、惡意攻擊和資料遺失。 |
| 受管理 | 您可以透過安全性設定、允許的應用程式和對系統健康的符合要求以雲端來管理您的遠端工作人員的裝置。 |
| 共同作業和生產力 | 透過以下高度協作的方式，您的遠端工作人員可以像在內部部屬工作時一樣高效: <ul><li>以 Teams 進行線上會議和聊天會話。 </li><li>透過 SharePoint 和 OneDrive，使用全域協助工具和即時共同作業的雲端式檔案儲存空間以共用工作區。 </li><li>共用工作和工作流程來劃分並完成工作。 </li></ul> |
|||

若要取得無縫登入體驗，您的內部部署 Active Directory 網域服務 (AD DS) 使用者帳戶應與 Azure Active Directory (Azure AD) 同步處理。 為了保護您的 Windows 10 裝置，應在 Intune 中註冊。 以下是基礎結構的高階檢視。

![適用於使用 Microsoft 365 之遠端工作者的基本基礎結構](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

遠端工作人員若要符合此條件，請使用這些 Microsoft 365 功能。

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| 採用安全性預設值強制執行 MFA   | 要求第二種形式的登入驗證，以防止身分識別和裝置遭到入侵。安全性預設值要求所有使用者帳戶使用 MFA。   | Microsoft 365 E3 或 E5 |
| 使用條件式存取強制執行 MFA| 根據具有條件式存取原則的登入屬性，要求使用 MFA。    | Microsoft 365 E3 或 E5 | 
| 使用風險型條件式存取強制執行 MFA   | 根據使用者使用 Azure 進階威脅防護登入的風險要求使用 MFA。 | Microsoft 365 E5 或 E3 (含 Azure AD Premium P2 授權) | 
| 自助式密碼重設 (SSPR)    | 允許您的使用者重設或解除鎖定他們的密碼或帳戶。  | Microsoft 365 E3 或 E5 |
| Azure AD 應用程式 Proxy    | 針對內部網路伺服器上的網頁型應用程式，提供安全的遠端存取。   | 需要個別付費的 Azure 訂閱 |
| Azure 點對站 VPN   | 透過 Azure 虛擬網路，建立從遠端工作者裝置到您內部網路的安全連線。   | 需要個別付費的 Azure 訂閱 |
| Windows 虛擬桌面   | 支援只能在 Azure 中執行虛擬桌面才能使用其個人和不受管理裝置的遠端工作者。 | 需要個別付費的 Azure 訂閱 |
| 遠端桌面服務 (RDS) | 允許員工連線到您內部網路上的 Windows 型電腦。 | Microsoft 365 E3 或 E5 | 
| 遠端桌面服務閘道   | 加密通訊並防止 RDS 主機直接暴露在網際網路上。 | 需要不同的 Windows Server 授權 |
| Microsoft Intune | 管理裝置和應用程式。   | Microsoft 365 E3 或 E5 | 
| 功能 | 在您的裝置上管理軟體安裝、更新及設定 | 需要個別的 Configuration Manager 授權 |
| 電腦分析 | 判斷 Windows 用戶端的更新準備就緒狀況。   | 需要個別的 Configuration Manager 授權 |
| Windows Autopilot | 設定並預先設定新的 Windows 10 裝置，以提高生產力。   | Microsoft 365 E3 或 E5 |
| Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive、Microsoft 365 Apps、Microsoft Power Platform、Yammer、Power Apps | 建立、溝通與共同作業。 | Microsoft 365 E3 或 E5 |
||||

如需安全性與合規性準則，請參閱[為遠端工作者部署安全性與合規性](empower-people-to-work-remotely-security-compliance.md)。

<a name="poster"></a> 如需這份解決方案的2頁摘要，請參閱 [[強化遠端工作人員] 海報](../downloads/empower-remote-workers.pdf)。

[![強化遠端工作人員海報](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

您也可以用 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) 或 [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pptx) 格式下載此海報，以及用 Letter、Legal 或 Tabloid (11 x 17) 大小的紙張列印此海報。

請使用下列步驟來保護和最佳化組織伺服器、資料和雲端服務的存取，並讓員工發揮最高的生產力。

1. [使用 MFA 提升登入安全性](empower-people-to-work-remotely-secure-sign-in.md)
2. [可遠端存取內部部署應用程式和服務](empower-people-to-work-remotely-remote-access.md)
3. [部署安全性與合規性服務](empower-people-to-work-remotely-security-compliance.md)
4. [為您的裝置、電腦和其他端點部署端點管理](empower-people-to-work-remotely-manage-endpoints.md)
5. [部署遠端工作者生產力應用程式和服務](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [訓練遠端工作者和處理使用上的意見反應](empower-people-to-work-remotely-train-monitor-usage.md)

![使用 Microsoft 365 強化遠端工作人員的步驟](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

如需有關支援遠端工作人員的 Microsoft 最新資訊，請參閱[啟用遠端工作技術社群網站](https://resources.techcommunity.microsoft.com/enabling-remote-work/)。
