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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 了解如何將貴公司從 Microsoft 365 商務版移到 Microsoft 365 E3。
ms.openlocfilehash: 2515c2d56727b9a8be643dea76e150eeaadce5c9
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593692"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-e3"></a>從 Microsoft 365 商務版移轉至 Microsoft 365 E3

Microsoft 365 商務版具有您需要為您的小型企業，與簡單的裝置管理和安全性，可讓您的員工盡善盡美組合在一起的最佳-雲端生產力應用程式的所有項目。 不過，在某些情況下，您可能需要將您的 Microsoft 365 商務版訂閱移轉至 Microsoft 365 E3。 

例如，貴公司已增加至，並需要超過 300 個授權 （由方式恭喜）。

或者，您的業務需求的企業版功能，例如 Office 365 專業增強版、 Windows 10 企業版 E3 或企業用戶端存取使用權 (Cal)。

升級很簡單： 您可以開始升級[從系統管理中心](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan?view=o365-worldwide)。 維護所有資料及您目前訂閱中的設定。 沒有執行任何動作，以準備移轉且不需要執行動作之後，但是利用的新功能。 

>[!Note]
>您也可以使用 Microsoft 365 商務版訂閱的最多 300 基座，並取得超過 300 個基座的 Microsoft 365 E3 訂閱。 不過，Office 365 ATP 不包含 Microsoft 365 E3。 持續進行的威脅防護，您應該新增額外的 Office 365 ATP 授權，讓所有在您的 Office 365 ATP 的範圍內的使用者原則獲得授權。
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a>Microsoft 365 商務版和 Microsoft 365 企業版之間的差異

此表說明 Microsoft 365 商務版和 Microsoft 365 E3 之間的差異。

| 功能   | 支援在 Microsoft 365 商務版 | 支援在 Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **內部部署**       | | | 
| Windows 10    | Windows 10 商務版  |    Windows 10 企業版 E3| 
| Office 應用程式 *  | [Office 365 商務版](#office-365-business)   | Office 365 專業增強版 | 
| **雲端生產力應用程式**       | | | 
| Exchange Online 和 Outlook   | 每個信箱和無限制的 Exchange Online 封存的 50 GB 儲存空間限制   | 每個信箱並無限制的 Exchange Online 封存的 100 GB 儲存空間上限 | 
| Teams | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| 商務用 OneDrive | 每個使用者 1 TB 的儲存量限制   | 無限制 | 
| Yammer，SharePoint Online，規劃中，資料流    | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| StaffHub  | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| Outlook Customer Manager、 MileIQ  | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | | 
| **威脅防護**     | | | 
| 攻擊縮減功能 | [請參閱此清單](#threat-protection) | 企業管理的硬體型孤立 Microsoft Edge | 
| Office 365 進階的威脅防護 (ATP) 計劃 1 | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)  | 不包含在內，但是可以加上 | 
| **身分識別管理**       | | | 
| 自助密碼重設為混合式 Azure Active Directory (Azure AD) 帳戶，Azure 多重要素驗證 (MFA)、 條件式存取，適用於內部部署身分識別的密碼回寫|    ![隨附於 Microsoft 365 商務版](./media/check-mark.png) | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| 雲端應用程式探索、 Azure AD Connect Health  |   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| Azure AD Office 365 應用程式單一登入 (SSO): 10 每位使用者 （例如 Salesforce 圖庫 SaaS 應用程式） 的應用程式 * | ![隨附於 Microsoft 365 商務版](./media/check-mark.png) | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| Azure AD Premium 1 SSO： 無限制 （Azure AD 應用程式 Proxy 透過內部部署應用程式） 和非庫應用程式使用自助應用程式整合範本  |   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| **裝置和應用程式管理**     | | | 
| Microsoft Intune、 Windows Autopilot|  ![隨附於 Microsoft 365 商務版](./media/check-mark.png) | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
|虛擬桌面存取 (VDA)   |  |    ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
|Windows 虛擬桌面 (WVD)  | ![隨附於 Microsoft 365 商務版](./media/check-mark.png) |     ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
|共用的電腦啟用 (SCA)   | ![隨附於 Microsoft 365 商務版](./media/check-mark.png) |     ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| Microsoft 桌面最佳化套件    | |     ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| **資訊保護**        | | | 
| Office 365 資料外洩防護、 Azure 資訊保護計劃 1  | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| 視窗的端點 DLP 的資訊保護    | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| **用戶端存取使用權 （CAL 權限）**    | | |   
| 企業 CAL 套件 （Exchange、 SharePoint、 Skype、 Windows、 Microsoft 端點 Configuration Manager、 Windows Rights Management）| |       ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| **合規性**        | | | 
| 無限制的電子郵件封存 | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| 合規性分數/合規性管理員   | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| 電子文件探索    | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| 就地保留與訴訟暫止 | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
| 通訊記錄管理 (MRM) 保留標記和保留原則  | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Microsoft 365 E3](./media/check-mark.png) | 
||||

\*已指派存取給 SaaS 應用程式的使用者可以存取 SSO 最多 10 個應用程式。 系統管理員可以設定 SSO 和其他 SaaS 應用程式] 中，變更使用者存取，但 10 只允許 SSO 存取每個使用者一次的應用程式。 所有 Office 365 應用程式都會列入都計算成為單一應用程式。

## <a name="migration"></a>移轉

若要移轉，與合作夥伴合作，您將您的 Microsoft 365 商務版訂閱和授權移至適當的 Microsoft 365 E3 訂用帳戶包含其授權。

下列各節說明您需要進行，如果有的話，查看變更，您可以在移轉後執行的動作。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 訂閱設定與資料

您不需要進行任何變更到您目前訂閱或資料移轉之前，其中包括：

- 訂閱設定，例如 DNS 網域名稱。
- 使用者和群組帳戶和驗證設定，例如多因素驗證] 或 [條件式存取原則。
- 生產力服務設定和其資料，例如 Exchange Online 信箱、 SharePoint Online 網站的小組 OneDrive for Business 資料夾及 OneNote 筆記本。

您的使用者現在可以喜歡無限制的儲存體中的 Exchange Online 信箱和 OneDrive 商務資料夾。

您可以開始使用雲端應用程式探索、 Azure AD Connect Health，與 SSO 超過 10 的應用程式。

>[!Note]
>使用者移轉至 Microsoft 365 E3 可以沒有不再使用 Outlook Customer Manager 和 MileIQ。
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>威脅防護

Windows 10 商務版包含這些保護：

- 完整性強制執行的作業系統開機程序
- 機密的作業系統元件的完整性強制執行
- 進階的弱點和零時差惡意探索防護功能
- Microsoft Edge、 Internet Explorer 中和 Chrome 的信譽型網路保護
- 主應用程式為基礎的防火牆
- 勒索軟體防護功能
- Microsoft Edge 的硬體型隔離
- 智慧型安全性 Graph 提供的應用程式控制項
- 裝置控制項 (USB)
- Web 式威脅的網路保護
- 主機入侵防護規則

Windows 10 企業版 E3 也包含企業管理的 Microsoft Edge 的硬體型隔離。

>[!Note]
>使用者移轉至 Microsoft 365 E3 每個需要 Office 365 ATP 授權持續進行的威脅防護。 請務必購買其他 Office 365 ATP 授權，讓所有在您的 Office 365 ATP 的範圍內的使用者原則獲得授權。 
>

### <a name="device-management-with-intune"></a>使用 Intune 裝置管理

您不需要對您目前 Intune 設定在移轉之前，包括註冊的裝置和裝置和應用程式設定進行任何變更。

### <a name="windows-10"></a>Windows 10

Microsoft 365 商務版包含 Windows 10 商務版，您可以透過 Windows AutoPilot 安裝。 當您移轉至 Microsoft 365 E3 時，每個使用者授權包含 Windows 10 企業版 E3，您也可以透過 Windows Autopilot 安裝它。

<a name="office-365-business"></a>
### <a name="office-365-business"></a>Office 365 商務版

您安裝在您的裝置上的 Office 365 企業版用戶端會自動開始使用 Office 365 專業增強版的功能。 在移轉之後，您現在可以使用：

 - 透過群組原則的大量啟用
 - 應用程式遙測
 - 更新控制項
 - 試算表比較和查詢功能
 - 商務智慧

