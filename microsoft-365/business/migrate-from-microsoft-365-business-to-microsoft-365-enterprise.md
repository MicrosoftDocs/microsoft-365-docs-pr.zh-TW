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
description: 瞭解如何將您的企業從 Microsoft 365 商務版移至 Microsoft 365 E3。
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126194"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>從 Microsoft 365 商務進階版移轉至 Microsoft 365 E3

Microsoft 365 商務版 Premium 具有您的小型企業所需的一切，結合了最佳的雲端架構應用程式與簡單的裝置管理和安全性，可讓您的員工採取最佳的運作方式。 不過，在某些情況下，您可能需要將 Microsoft 365 商務版訂閱遷移至 Microsoft 365 E3。 

例如，您的公司隨著) 的方式，已成長並需要300以上的授權 (祝賀。

或者，您的企業需要企業版功能（例如 Microsoft 365 應用程式企業版、Windows 10 企業版 E3 或企業用戶端存取許可證 (Cal) ）。

升級非常簡單：您可以 [從系統管理中心](../commerce/subscriptions/upgrade-to-different-plan.md)開始升級。 您目前訂閱中的所有資料和設定均會維護。 您不需要做為遷移準備，也不需要執行任何動作，只會利用新功能。

>[!Note]
>您也可以使用 Microsoft 365 商務版特優訂閱來獲得最高300的席位，並取得 Microsoft 365 E3 訂閱，以供超過300的席位使用。 不過，microsoft Defender for Office 365 並未包含在 Microsoft 365 E3 中。 針對持續威脅防護，您應該針對 Office 365 授權新增額外的 Defender，以便授權您的 Office 365 原則範圍中的所有使用者。
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Microsoft 365 商務版和 Microsoft 365 企業版之間的差異

下表顯示 Microsoft 365 商務版 Premium 和 Microsoft 365 E3 之間的差異。

| 功能    | Microsoft 365 商務版 Premium 中的支援    | Microsoft 365 E3 中的支援 | 
|:-------|:-----|:-----|
| **內部部署**        | | | 
| Windows 10    | Windows 10 商務版  |     Windows 10 企業版 E3| 
| Office app *    | [Microsoft 365 Apps 商務版](#office-365-business)    | Microsoft 365 Apps 企業版 | 
| **雲端生產力應用程式**        | | | 
| Exchange Online 和 Outlook    | 每個信箱 50 GB 儲存空間限制和 Exchange Online 封存數目不受限制    | 每個信箱 100 GB 儲存空間限制和 Exchange Online 封存數目不受限制 | 
| Teams    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| 商務用 OneDrive    | 每個使用者 1 TB 的儲存空間限制    | 無限制 | 
| Yammer、SharePoint 線上、Planner、Stream    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| MileIQ    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | | 
| **威脅防護**        | | | 
| 攻擊面降減功能    | [請參閱此清單](#threat-protection) | Microsoft Edge 的硬體隔離的企業管理 | 
| 適用于 Office 的 Defender 365 方案1 | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | 不包含，但可以新增于 | 
| **身分識別管理**        | | | 
| 混合式 Azure Active Directory 的自助密碼重設 (Azure AD) 帳戶，Azure AD 多重要素驗證 (MFA) ，條件式存取，針對內部部署身分識別的密碼回寫。|     ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| 雲端應用程式探索，Azure AD Connect Health    |     | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365 應用程式單一 Sign-On (SSO) ：每位使用者10個應用程式 (庫 SaaS 諸如 Salesforce) 等應用程式 | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO：透過 Azure AD 應用程式 Proxy 和非畫廊應用程式使用 Self-Service 應用程式整合範本 (的內部部署應用程式沒有限制)     |     | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| **裝置和應用程式管理**        | | | 
| Microsoft Intune、Windows Autopilot|     ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
|虛擬桌面存取 (VDA)     |  |     ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
|Windows Virtual Desktop (WVD)     | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png) |     ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
|共用電腦啟用 (SCA)     | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png) |     ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| Microsoft 桌面優化套件    | |     ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| **資訊保護**        | | | 
| Office 365 資料遺失防護，Azure 資訊保護方案1    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| Endpoint DLP 的視窗資訊保護    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| **用戶端存取許可證 (CAL 許可權)**    | | |     
| Enterprise CAL 套件 (Exchange、SharePoint、Skype、Windows、Microsoft Endpoint Configuration 管理員、Windows Rights Management) | |         ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| **合規性**        | | | 
| 無限制的電子郵件封存    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| 合規性管理員    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| 電子文件探索    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| 就地保留和訴訟暫止    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
| 通訊記錄管理 (MRM) 保留標記和保留原則    | ![隨附于 Microsoft 365 商務版 Premium](../media/check-mark.png)    | ![隨附于 Microsoft 365 E3](../media/check-mark.png) | 
||||

\* 已獲指派 SaaS app 存取權的使用者，可對最多10個應用程式取得 SSO 存取權。 系統管理員可以設定 SSO，並變更使用者對不同 SaaS 應用程式的存取，但是每個使用者一次只能有10個應用程式使用 SSO 存取。 所有 Office 365 應用程式會計為單一應用程式。

## <a name="migration"></a>移轉

若要進行遷移，請與您的合作夥伴合作，將您的 Microsoft 365 商務高級訂閱和授權，移至具有其授權的適當 Microsoft 365 E3 訂閱。

下列各節說明您需要做哪些變更（若有的話），以及遷移之後可執行檔動作。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 訂閱設定和資料

您不需要在遷移之前對目前的訂閱或資料進行任何變更，包括：

- 訂閱設定，例如 DNS 功能變數名稱。
- 使用者和群群組帳戶及驗證設定，例如多重因素驗證或條件式存取原則。
- 生產力服務設定及其資料，例如小組、Exchange Online 信箱、SharePoint 線上網站、商務 OneDrive 商務資料夾，以及 OneNote 筆記本。

您的使用者現在可以在 Exchange Online 信箱和商務資料夾的 OneDrive 中享受無限儲存體。

您可以開始針對超過10個應用程式使用雲端應用程式探索、Azure AD Connect Health 和 SSO。

>[!Note]
>遷移至 Microsoft 365 E3 的使用者無法再使用 MileIQ。
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>威脅防護

Windows 10 商務版包含下列保護：

- 作業系統啟動處理常式的完整性強制執行
- 機密運作元件的完整性強制執行
- 「高級弱點」和「零日利用」緩解
- Microsoft Edge、Internet Explorer 和 Chrome 的信譽式網路保護
- 主機型防火牆
- 勒索軟體緩解
- Microsoft Edge 的硬體隔離
- 由智慧安全性圖形供電的應用程式控制
- 裝置控制項 (USB) 
- 網路型威脅的網路保護
- 主機入侵防護規則

Windows 10 企業版 E3 也包含以硬體為基礎的 Microsoft Edge 隔離的企業管理。

>[!Note]
>遷移至 Microsoft 365 E3 的使用者，每個使用者都需要 Microsoft Defender for Office 365 授權，以進行持續威脅防護。 請務必購買其他適用于 Office 365 授權的 Defender，以便授權您的 Office 365 範圍中的所有使用者。 
>

### <a name="device-management-with-intune"></a>使用 Intune 的裝置管理

您不需要在遷移之前對目前的 Intune 設定進行任何變更（包括已註冊的裝置和裝置及應用程式設定）。

### <a name="windows-10"></a>Windows 10

Microsoft 365 商務版特優包含 Windows 10 商務版，您可以使用 Windows AutoPilot 進行安裝。 當您遷移至 Microsoft 365 E3 時，每個使用者授權都會包含 Windows 10 企業版 E3，您也可以使用 Windows Autopilot 進行安裝。

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps 商務版

您裝置上安裝的 Microsoft 365 應用程式商務用用戶端將會自動開始使用 Microsoft 365 應用程式的企業版功能。 遷移後，您現在可以使用：

 - 群組原則支援
 - 試算表比較及查詢
 - 商務智慧

