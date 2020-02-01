---
title: 從 Office 365 E3 移轉至 Microsoft 365 商務版
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: 了解如何將業務移至 Microsoft 365 商務版中，從 Office 365 E3。
ms.openlocfilehash: 210f3ebf76da49349dfb6d61d0b8ce88d15d3734
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593702"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a>從 Office 365 E3 移轉至 Microsoft 365 商務版 

Microsoft 365 商務版具有您需要為您的小型企業，簡單的裝置管理與安全性結合最佳-雲端生產力應用程式的所有項目。 如果您目前有 Office 365 E3 訂閱，但沒有超過 300 個員工，請考慮新增的安全性功能切換至 Microsoft 365 商務版。

移轉很簡單： 第一次切換授權和維護您目前訂閱中的所有資料和使用者資訊。 移轉之後，您需要設定 Microsoft 365 商務版中加入的功能。

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a>Office 365 E3 和 Microsoft 365 商務版之間的差異

此表說明 Microsoft 365 商務版和 Office 365 E3 之間的差異。

| 功能   | 支援在 Microsoft 365 商務版 | 支援 office 365 E3 | 
|:-------|:-----|:-----|
| **內部部署**       | | | 
| Office 應用程式<sup>1</sup>   | Office 365 商務版   | Office 365 專業增強版 | 
| **雲端生產力應用程式**       | | | 
| Exchange Online 和 Outlook   | 每個信箱和 unlimited Exchange Online Archiving 50 GB 儲存空間限制   | 每個信箱並無限制 Exchange Online 封存的 100 GB 儲存空間上限 | 
| Teams | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Office 365 E3](./media/check-mark.png) | 
| 商務用 OneDrive | 每個使用者 1 TB 的儲存量限制   | 無限制 | 
| Yammer，SharePoint Online，規劃中，資料流    | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Office 365 E3](./media/check-mark.png) | 
| StaffHub  | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | ![隨附於 Office 365 E3](./media/check-mark.png) | 
| Outlook Customer Manager、 MileIQ  | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)   | | 
| **威脅防護**     | | | 
| Office 365 進階的威脅防護 (ATP) 計劃 1 | ![隨附於 Microsoft 365 商務版](./media/check-mark.png)  | 不包含在內，但是可以加上 | 
| **身分識別管理**       | | | 
| 自助密碼重設為混合式 Azure Active Directory (Azure AD) 帳戶，Azure 多重要素驗證 (MFA)、 條件式存取，適用於內部部署身分識別的密碼回寫|    ![隨附於 Microsoft 365 商務版](./media/check-mark.png) |  | 
| **裝置和應用程式管理**     | | |
| Microsoft Intune、 Windows AutoPilot|  ![隨附於 Microsoft 365 商務版](./media/check-mark.png) |  |
| 共用電腦啟用|   ![隨附於 Microsoft 365 商務版](./media/check-mark.png) | ![隨附於 Office 365 E3](./media/check-mark.png)| 
| 升級到 Windows 10 專業版的權限，從 Win 7/8.1 專業版的授權|     ![隨附於 Microsoft 365 商務版](./media/check-mark.png) || 
| **資訊保護**        | | |
|Office 365 資料外洩防護|   ![隨附於 Microsoft 365 商務版](./media/check-mark.png)|![隨附於 Office 365 E3](./media/check-mark.png)|
|Azure 資訊保護方案 1，Bitlocker 強制執行|![隨附於 Microsoft 365 商務版](./media/check-mark.png)||
|Azure 資訊保護方案 1，敏感度標籤|![隨附於 Microsoft 365 商務版](./media/check-mark.png)||
|**用戶端存取使用權 （CAL 權限）**|||
|企業 CAL 套件 (Exchange、 SharePoint、 Skype)||![隨附於 Office 365 E3](./media/check-mark.png)|

<sup>1</sup> Microsoft 365 商務版版本的 Office 應用程式不會包含大量啟用透過群組原則中，應用程式遙測，更新控制項、 試算表比較和查詢，或商務智慧。

## <a name="migration"></a>移轉

若要移轉您的訂閱，請參閱指示[以手動方式切換至不同的計劃](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually)如果您想要將少數使用者移至 Microsoft 365 商務版。 您也可以[自動升級所有人](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan)，或可以使用，將您的 E3 訂閱和授權移至 Microsoft 365 商務版訂閱的合作夥伴。
下列各節說明您需要進行，如果有的話，所做的變更，您可以在移轉後執行的動作。

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 訂閱設定與資料
您不需要執行任何您目前訂閱或變更資料移轉之前，其中包含：

- 訂閱設定，例如 DNS 記錄及網域名稱。
- 使用者和群組帳戶和驗證設定，例如多因素驗證] 或 [條件式存取原則。
- 生產力服務設定和其資料，例如 Exchange Online 信箱、 SharePoint Online 網站的小組 OneDrive for Business 資料夾及 OneNote 筆記本。

### <a name="windows-10"></a>Windows 10

如果您的 Windows 已經不在 Windows Pro Creator 更新，[升級到 Windows 專業人員的 Creators Update](upgrade-to-windows-pro-creators-update.md)。

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>設定原則來保護使用者裝置和檔案

> [!NOTE]
> 如果您設定 Office 365 MDM 原則和裝置，那些裝置將會列在 [**裝置**] 頁面上，在 Microsoft 365 系統管理中心。 [Intune 入口網站](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)中的傳統原則清單中，會顯示您所設定的任何原則。

您已指派授權給 Microsoft 365 商務版之後，您可以開始保護使用者的裝置和檔案。

如果您升級所有人組織 Microsoft 365 商務版中，您會看到安裝精靈] 在 [首頁] 頁面，並可以依照[設定安裝程式精靈] 中的 Microsoft 365 商務版](set-up.md)來保護檔案和行動裝置。

您也可以完成下列步驟，在 [裝置] 頁面上：
  
1. 在系統管理中心中，在左側導覽中，移至 [**裝置** \> **原則**。
    
2. 在 [**裝置原則**] 頁面上，選擇 [**新增**]。
    
3. 在 [**新增原則**] 窗格中輸入原則的名稱，，然後從下拉式清單中選擇 [**原則類型**。 
    
     您可以設定應用程式原則保護 Android 和 iPhone 裝置以及 Windows 10 上的檔案，您可以設定公司擁有 Windows 10 裝置的裝置設定原則。 請參閱下列連結，如需詳細資訊：
    
  - [設定 Android 或 iOS 裝置的 App 保護設定](app-protection-settings-for-android-and-ios.md)
    
  - [設定 Windows 10 裝置的應用程式保護設定](protection-settings-for-windows-10-devices.md)
    
  - [設定適用於 Windows 10 電腦的裝置保護設定](protection-settings-for-windows-10-pcs.md)
  
4. 一旦您設定原則時，您和您的員工可以設定裝置：
    
  - 如需 Windows 裝置步驟，請參閱[為 Microsoft 365 商務版使用者的 Windows 裝置上設定](set-up-windows-devices.md)。 
    
  - 如需 Android 手機和 Iphone 步驟，請參閱[為 Microsoft 365 商務版使用者的行動裝置上設定](set-up-mobile-devices.md)。 

### <a name="threat-protection"></a>威脅防護

移轉至 Microsoft 365 商務版之後，您有 Office 365 ATP。 如需概觀，請參閱[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 。 若要設定，請參閱[設定 ATP 安全連結](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)、[設定 ATP 安全附件](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)和[設定 ATP 防網路釣魚](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)。

### <a name="sensitivity-labels"></a>敏感度標籤

若要開始使用敏感度標籤，請參閱[Overview of 敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)[建立及管理敏感度標籤](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)視訊。
