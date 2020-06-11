---
title: 使用 Microsoft 365 強化遠端工作者
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 設定安全性和服務基礎結構，讓您的工作人員隨時隨地都能遠端工作。
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560458"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>使用 Microsoft 365 強化遠端工作者

貴組織可能必須讓工作人員能夠從家裡安全地存取貴組織的內部部署與雲端式資訊、工具及資源。 對於許多組織而言，能讓工作人員順暢且安全地不在辦公室工作是非常重要的，可達到以下目的：

- 節省辦公室空間。
- 聘用並留住不願意調派的工作人員。
- 縮短工作人員的通勤時間，讓他們有更多時間來提高生產力，並在下班後放鬆壓力。

遠端工作 (又稱為遠距工作) 可以涵蓋以下範圍：

- 偶爾會離開辦公室去參加會議或客戶會議的工作人員。
- 遠端全職工作的部分工作人員。
- 沒有辦公室且所有工作者皆為遠端工作的完全遠端組織。

無論身在何處，遠端工作者都必須能夠隨時存取：

- 組織資源，例如內部部署應用程式資料中心所提供的資源。
- Microsoft 365 訂閱中的雲端服務和資料，例如 Teams、Exchange Online、SharePoint 和 OneDrive。

若要取得無縫登入體驗，您的 Active Directory 網域服務 (AD DS) 使用者帳戶應與 Azure Active Directory (Azure AD) 同步處理。 為了保護您的 Windows 10 裝置，應在 Intune 中註冊。 以下是基礎結構的高階檢視。

![適用於使用 Microsoft 365 之遠端工作者的基本基礎結構](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


為了支援遠端工作者 (例如因應 COVID-19 疫情)，Microsoft 365 的功能組合能以高度共同作業的方式來啟用您的遠端工作者，例如：

- 線上會議和聊天工作階段。
- 使用全域協助工具和即時共同作業的雲端式檔案儲存空間以共用工作區。
- 共用工作和工作流程來劃分並完成工作。

為了加強安全性，Microsoft 365 包括：

- 強制執行驗證需求、偵測及回應高風險的登入，並封鎖選取的應用程式和不相容的裝置。
- 加密連線與雲端中的數位資產。
- 用權限來定義使用者能夠如何使用檔案。
- 可保護 Windows 10 裝置的全面安全性功能。

遠端工作人員若要符合這些條件，請使用下列 Microsoft 365 功能：

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| 採用安全性預設值強制執行 MFA   | 要求第二種形式的登入驗證，以防止身分識別和裝置遭到入侵。安全性預設值要求所有使用者帳戶使用 MFA。   | Microsoft 365 E3 和 E5 |
| 使用條件式存取強制執行 MFA| 根據具有條件式存取原則的登入屬性，要求使用 MFA。    | Microsoft 365 E3 和 E5 | 
| 使用風險型條件式存取強制執行 MFA   | 根據使用者使用 Azure 進階威脅防護登入的風險要求使用 MFA。 | Microsoft 365 E5 或 E3 (含 Azure AD Premium P2 授權) | 
| 自助式密碼重設 (SSPR)    | 允許您的使用者重設或解除鎖定他們的密碼或帳戶。  | Microsoft 365 E3 和 E5 |
| Azure AD 應用程式 Proxy    | 針對內部網路伺服器上的網頁型應用程式，提供安全的遠端存取。   | 需要個別付費的 Azure 訂閱 |
| Azure 點對站 VPN   | 透過 Azure 虛擬網路，建立從遠端工作者裝置到您內部網路的安全連線。   | 需要個別付費的 Azure 訂閱 |
| Windows 虛擬桌面   | 支援只能在 Azure 中執行虛擬桌面才能使用其個人和不受管理裝置的遠端工作者。 | 需要個別付費的 Azure 訂閱 |
| 遠端桌面服務 (RDS) | 允許員工連線到您內部網路上的 Windows 型電腦。 | Microsoft 365 E3 和 E5 | 
| 遠端桌面服務閘道   | 加密通訊並防止 RDS 主機直接暴露在網際網路上。 | 需要不同的 Windows Server 授權 |
| Microsoft Intune | 管理裝置和應用程式。   | Microsoft 365 E3 和 E5 | 
| Configuration Manager | 在您的裝置上管理軟體安裝、更新及設定 | 需要個別的 Configuration Manager 授權 |
| 電腦分析 | 判斷 Windows 用戶端的更新準備就緒狀況。   | 需要個別的 Configuration Manager 授權 |
| Windows Autopilot | 設定並預先設定新的 Windows 10 裝置，以提高生產力。   | Microsoft 365 E3 和 E5 |
| Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive、Microsoft 365 Apps、Microsoft Power Platform、Yammer、Power Apps | 建立、溝通與共同作業。 | Microsoft 365 E3 和 E5 |
||||

請使用下列步驟來保護和最佳化組織伺服器、資料和雲端服務的存取，並讓員工發揮最高的生產力。

1. [使用 MFA 提升登入安全性](empower-people-to-work-remotely-secure-sign-in.md)
2. [可遠端存取內部部署應用程式和服務](empower-people-to-work-remotely-remote-access.md)
3. [為您的裝置、電腦和其他端點部署端點管理](empower-people-to-work-remotely-manage-endpoints.md)
4. [部署遠端工作者生產力應用程式和服務](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [建立通訊地點](empower-people-to-work-remotely-communication-venues.md)
6. [訓練遠端工作者和處理使用上的意見反應](empower-people-to-work-remotely-train-monitor-usage.md)

![使用 Microsoft 365 強化遠端工作人員的步驟](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

如需有關支援遠端工作人員的 Microsoft 最新資訊，請參閱[啟用遠端工作技術社群網站](https://resources.techcommunity.microsoft.com/enabling-remote-work/)。
