---
title: 從 Microsoft 365 商務版移轉至 Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 瞭解如何將您的企業從 Microsoft 365 商務進階版移至 Microsoft 365 E3。
ms.openlocfilehash: 6502d79dbb283db37b00e4fccf89b15ab4291ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227612"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>從 Microsoft 365 商務進階版移轉至 Microsoft 365 E3

Microsoft 365 商務進階版具有您的小型企業所需的一切，結合了最佳的雲端架構應用程式與簡單的裝置管理和安全性，可讓您的員工採取最佳的工作。 不過，在某些情況下，您可能需要將 Microsoft 365 商務進階版訂閱遷移至 Microsoft 365 E3。

例如，您的公司隨著) 的方式，已成長並需要300以上的授權 (祝賀。

或者，您的業務需要企業版功能，例如 Microsoft 365 Apps 企業版、Windows 10 企業版 E3 或 Enterprise 用戶端存取授權 (cal) 。

升級非常簡單：您可以 [從系統管理中心](../commerce/subscriptions/upgrade-to-different-plan.md)開始升級。 您目前訂閱中的所有資料和設定均會維護。 您不需要做為遷移準備，也不需要執行任何動作，只會利用新功能。

> [!NOTE]
> 您也可以使用 Microsoft 365 商務進階版訂閱，最多300個座位，並針對超過300的席位取得 Microsoft 365 E3 訂閱。 不過，不包含 Microsoft 365 E3 的 Microsoft Defender Office 365。 針對持續威脅防護，您應該為 Office 365 授權新增其他的 Defender，以取得 Office 365 原則的 defender 範圍內的所有使用者授權。

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Microsoft 365 商務進階版和 Microsoft 365 企業版之間的差異

下表顯示 Microsoft 365 商務進階版和 Microsoft 365 E3 之間的差異。

| 功能    | Microsoft 365 商務進階版中的支援    | Microsoft 365 E3 中的支援 |
|:-------|:-----|:-----|
| **內部部署**        | | |
| Windows 10    | Windows 10 商務版  |     Windows 10 企業版E3|
| Office 應用程式 *    | [Microsoft 365 Apps 商務版](#office-365-business)    | Microsoft 365 Apps 企業版 |
| **雲端生產力應用程式**        | | |
| Exchange Online 和 Outlook    | 每個信箱 50 GB 的儲存量限制，以及無限 Exchange Online 封存    | 每個信箱 100 GB 的儲存量限制，以及無限 Exchange Online 封存 |
| Teams    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| 商務用 OneDrive    | 每個使用者 1 TB 的儲存空間限制    | 無限制 |
| Yammer、SharePoint Online、Planner、Stream    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| **威脅防護**        | | |
| 攻擊面降減功能    | [請參閱此清單](#threat-protection) | Enterprise 以硬體為基礎的隔離 Microsoft Edge 管理 |
| 適用於 Office 365 的 Defender 方案 1 | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | 不包含，但可以新增于 |
| **身分識別管理**        | | |
| 混合式 Azure Active Directory 的自助密碼重設 (Azure ad) 帳戶，azure ad 多重要素驗證 (MFA) ，條件式存取，針對內部部署身分識別的密碼回寫。|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| 雲端應用程式探索，Azure AD 連線健康情況    |     | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Office 365 app 單一 Sign-On (SSO) ：每位使用者10個應用程式 (應用程式 SaaS 應用程式，例如 Salesforce) * | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Premium 1 SSO：透過 Azure AD 應用程式 Proxy 和非畫廊應用程式使用 Self-Service 應用程式整合範本，不限 (內部部署應用程式)     |     | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| **裝置和應用程式管理**        | | |
| Microsoft Intune，Windows Autopilot|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
|虛擬桌面存取 (VDA)     |  |     ![包含 Microsoft 365 E3](../media/check-mark.png) |
|Windows虛擬桌面 (WVD)     | ![包含 Microsoft 365 商務進階版](../media/check-mark.png) |     ![包含 Microsoft 365 E3](../media/check-mark.png) |
|共用電腦啟用 (SCA)     | ![包含 Microsoft 365 商務進階版](../media/check-mark.png) |     ![包含 Microsoft 365 E3](../media/check-mark.png) |
| Microsoft 桌面優化套件    | |     ![包含 Microsoft 365 E3](../media/check-mark.png) |
| **資訊保護**        | | |
| Office 365資料遺失防護，Azure 資訊保護方案1    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| Endpoint DLP 的視窗資訊保護    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| **用戶端存取許可證 (CAL 許可權)**    | | |
| EnterpriseCAL 套件 (Exchange，SharePoint，Skype，Windows，Microsoft Endpoint Configuration Manager，Windows Rights Management) | |         ![包含 Microsoft 365 E3](../media/check-mark.png) |
| **合規性**        | | |
| 無限制的電子郵件封存    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| 合規性管理員    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| 電子文件探索    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| 就地保留和訴訟暫止    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
| 通訊記錄管理 (MRM) 保留標記和保留原則    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Microsoft 365 E3](../media/check-mark.png) |
||||

\* 已獲指派 SaaS app 存取權的使用者，可對最多10個應用程式取得 SSO 存取權。 系統管理員可以設定 SSO，並變更使用者對不同 SaaS 應用程式的存取，但是每個使用者一次只能有10個應用程式使用 SSO 存取。 所有 Office 365 的應用程式會計為單一應用程式。

## <a name="migration"></a>移轉

若要進行遷移，請與您的合作夥伴合作，將您的 Microsoft 365 商務進階版訂閱和授權，移至具有其授權的適當 Microsoft 365 E3 訂閱。

下列各節說明您需要做哪些變更（若有的話），以及遷移之後可執行檔動作。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 訂閱設定和資料

您不需要在遷移之前對目前的訂閱或資料進行任何變更，包括：

- 訂閱設定，例如 DNS 功能變數名稱。
- 使用者和群群組帳戶及驗證設定，例如多重因素驗證或條件式存取原則。
- 生產力服務設定及其資料，例如 Teams、Exchange Online 信箱、SharePoint 線上網站、商務用 OneDrive 資料夾及 OneNote 筆記本。

您的使用者現在可以在 Exchange Online 信箱和商務用 OneDrive 資料夾中享受無限的儲存空間。

您可以開始針對超過10個應用程式使用雲端應用程式探索、Azure AD 連線健康情況和 SSO。

<a name="threat-protection"></a>
### <a name="threat-protection"></a>威脅防護

Windows 10 商務版包括下列保護：

- 作業系統啟動處理常式的完整性強制執行
- 機密運作元件的完整性強制執行
- 「高級弱點」和「零日利用」緩解
- Microsoft Edge、Internet Explorer 和 Chrome 的信譽式網路保護
- 主機型防火牆
- 勒索軟體緩解
- 以硬體為基礎的 Microsoft Edge 的隔離
- 由智慧安全 Graph 所支援的應用程式控制
- 裝置控制項 (USB) 
- 網路型威脅的網路保護
- 主機入侵防護規則

Windows 10 企業版E3 也包含以硬體為基礎的企業管理的 Microsoft Edge。

> [!NOTE]
> 遷移至 Microsoft 365 E3 的使用者都需要 Microsoft Defender Office 365 授權，以進行持續威脅防護。 請務必購買其他適用于 Office 365 授權的 defender，以取得 Office 365 原則的 defender 範圍內的所有使用者授權。

### <a name="device-management-with-intune"></a>使用 Intune 的裝置管理

您不需要在遷移之前對目前的 Intune 設定進行任何變更（包括已註冊的裝置和裝置及應用程式設定）。

### <a name="windows-10"></a>Windows 10

Microsoft 365 商務進階版包括 Windows 10 商務版，您可以使用 Windows AutoPilot 加以安裝。 當您將 Microsoft 365 E3 遷移時，每個使用者授權都會包含 Windows 10 企業版 E3，您也可以使用 Windows Autopilot 來安裝。

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps 商務版

您的裝置上安裝的 Microsoft 365 Apps 商務版用戶端將會自動開始使用 Microsoft 365 Apps 企業版的功能。 遷移後，您現在可以使用：

- 群組原則支援
- 試算表比較及查詢
- 商務智慧
