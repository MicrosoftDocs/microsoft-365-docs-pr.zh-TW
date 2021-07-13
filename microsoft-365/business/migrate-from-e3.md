---
title: 從 Office 365 E3 遷移至 Microsoft 365 商務版
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: 如果您有 Office 365 E3 訂閱，但沒有超過300名員工，請考慮切換至 Microsoft 365 商務進階版。
ms.openlocfilehash: c1b4da07b3bf28cce1a48424ab45cde6ea54d367
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394164"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>從 Office 365 E3 遷移至 Microsoft 365 商務進階版

Microsoft 365 商務進階版具有您的小型企業所需的一切，結合了最佳的雲端架構應用程式與簡單的裝置管理和安全性。 如果您目前已有 Office 365 E3 訂閱，但沒有超過300名員工，請考慮切換至 Microsoft 365 商務進階版以新增安全性功能。

遷移非常簡單：先切換授權，您的目前訂閱中的所有資料和使用者資訊仍會維護。 遷移之後，您必須設定 Microsoft 365 商務進階版中新增的功能。

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Office 365 E3 和 Microsoft 365 商務進階版之間的差異

下表顯示 Microsoft 365 商務進階版和 Office 365 E3 之間的差異。

| 功能    | Microsoft 365 商務進階版中的支援    | Office 365 E3 中的支援 |
|:-------|:-----|:-----|
| **內部部署**        | | |
| Office 應用程式<sup>1</sup>    | Microsoft 365 Apps 商務版    | Microsoft 365 Apps 企業版 |
| **雲端生產力應用程式**        | | |
| Exchange Online 和 Outlook    | 每個信箱 50 GB 儲存量限制，而不限 Exchange Online 封存    | 每個信箱 100 GB 儲存量限制，而不限 Exchange Online 封存 |
| Teams    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Office 365 E3](../media/check-mark.png) | 
| 商務用 OneDrive    | 每個使用者 1 TB 的儲存空間限制    | 無限制 | 
| Yammer、SharePoint Online、Planner、Stream    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Office 365 E3](../media/check-mark.png) |
| **威脅防護**        | | |
| 適用於 Office 365 的 Defender 方案 1 | ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | 不包含，但可以新增于 |
| **身分識別管理**        | | |
| 混合式 Azure Active Directory 的自助密碼重設 (Azure ad) 帳戶，azure ad 多重要素驗證 (MFA) ，條件式存取，針對內部部署身分識別的密碼回寫。|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    |  |
| **裝置和應用程式管理**        | | |
| Microsoft Intune，Windows AutoPilot|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    |  |
| 共用電腦啟用|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    | ![包含 Office 365 E3](../media/check-mark.png)| 
| 從 Win 7/8.1 Pro 授權 Windows 10 專業版的升級許可權|     ![包含 Microsoft 365 商務進階版](../media/check-mark.png)    ||
| **資訊保護**        | | |
|Office 365 資料外洩防護|    ![包含 Microsoft 365 商務進階版](../media/check-mark.png)|![包含 Office 365 E3](../media/check-mark.png)|
|Azure 資訊保護方案1，BitLocker 強制執行|![包含 Microsoft 365 商務進階版](../media/check-mark.png)||
|Azure 資訊保護方案1，敏感度標籤|![包含 Microsoft 365 商務進階版](../media/check-mark.png)||
|**用戶端存取許可證 (CAL 許可權)**|||
|EnterpriseCAL 套件 (Exchange、SharePoint、Skype) ||![包含 Office 365 E3](../media/check-mark.png)|

<sup>1</sup> Office 應用程式的 Microsoft 365 商務進階版版本不包括透過群組原則、應用程式遙測、更新控制項、試算表比較和查詢或商務智慧的大量啟用。

## <a name="migration"></a>移轉

若要 Microsoft 365 商務進階版將您的訂閱遷移，請參閱[手動變更計畫](../commerce/subscriptions/change-plans-manually.md)，以取得相關指示。 您也可以[自動升級所有人](../commerce/subscriptions/upgrade-to-different-plan.md)，或與合作夥伴合作，將 E3 訂閱和授權移至 Microsoft 365 商務進階版訂閱。
下列各節說明您需要做的變更（若有的話），以及遷移後可以執行的動作。

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 訂閱設定和資料
您不需要在遷移之前對目前的訂閱或資料做任何變更，包括：

- 訂閱設定，例如 DNS 記錄和功能變數名稱。
- 使用者和群群組帳戶及驗證設定，例如多重因素驗證或條件式存取原則。
- 生產力服務設定及其資料，例如 Teams、Exchange Online 信箱、SharePoint 線上網站、商務用 OneDrive 資料夾及 OneNote 筆記本。
- Office 應用程式會自動縮放。 Office 365 新式授權會每72小時檢查一次使用者的授權指派，並將 Office 應用程式轉換成符合使用者訂閱的版本。

### <a name="windows-10"></a>Windows 10

如果您的 Windows 尚未 Windows Pro 建立者更新，請[將其升級為 Windows Pro 創意者更新](upgrade-to-windows-pro-creators-update.md)。

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>設定保護使用者裝置及檔的原則

> [!NOTE]
> 如果您設定 Office 365 MDM 原則和裝置，這些裝置將會列在 Microsoft 365 系統管理中心的 [**裝置**] 頁面上。 您設定的任何原則都會顯示在 [Intune 入口網站](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)的經典原則清單中。

指派授權給 Microsoft 365 商務進階版之後，您可以開始保護使用者的裝置和檔案。

如果您已將組織中的每個人升級為 Microsoft 365 商務進階版，您會在首頁上看到安裝精靈，並且可以遵循[安裝精靈的設定 Microsoft 365 商務進階版中](set-up.md)的步驟，以保護檔案和行動裝置。

您也可以在 [裝置] 頁面上完成這些步驟：
  
1. 在系統管理中心的左側導覽中，移至 [ **裝置** \> **原則**]。

2. 在 [ **裝置原則** ] 頁面上，選擇 [ **新增**]。

3. 在 [ **新增原則** ] 窗格中，將原則命名為 [名稱]，然後從下拉式清單中選擇 **原則類型** 。

     您可以設定應用程式原則來保護 Android 和 iPhone 裝置上的檔案，以及 Windows 10，也可以為擁有 Windows 10 裝置的公司設定裝置配置原則。 如需詳細資訊，請參閱下列連結：

  - [設定 Android 或 iOS 裝置的 App 保護設定](app-protection-settings-for-android-and-ios.md)

  - [設定 Windows 10 裝置的應用程式保護設定](protection-settings-for-windows-10-devices.md)

  - [設定 Windows 10 電腦的裝置保護設定](protection-settings-for-windows-10-pcs.md)
  
4. 一旦您設定原則，您和您的員工便可以設定裝置：

  - 如需 Windows 裝置的步驟，請參閱[設定 Microsoft 365 商務進階版使用者 Windows 裝置](set-up-windows-devices.md)。 

  - 如需 Android 手機和 iphone 的步驟，請參閱[為 Microsoft 365 商務進階版使用者設定行動裝置](set-up-mobile-devices.md)。 
  
### <a name="mailbox-size"></a>信箱大小

Microsoft 365 商務進階版在使用 Exchange Online 方案1時，其使用的儲存量限制為 50 GB。 在遷移至 Microsoft 365 商務進階版時，如果您的任何使用者超過 50 GB 的信箱儲存空間，建議您指派此使用者 Exchange Online 計畫2並移除 Exchange Online 方案1，因為這兩者都不可行。

### <a name="threat-protection"></a>威脅防護

在遷移至 Microsoft 365 商務進階版後，您就能使用 Office 365 的 Defender。 如需概述，請參閱[Microsoft Defender Office 365](../security/office-365-security/defender-for-office-365.md) 。 若要設定，請參閱[設定保管庫連結](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)，[設定保管庫附件](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，並[在 Office 365 中設定 Defender 的反網路釣魚](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)。

### <a name="sensitivity-labels"></a>敏感度標籤

若要開始使用敏感度標籤，請參閱 [敏感度標籤](../compliance/sensitivity-labels.md) 和 [建立及管理敏感度標籤](../business-video/create-sensitivity-labels.md) 影片。

## <a name="related-content"></a>相關內容

[手動變更方案](../commerce/subscriptions/change-plans-manually.md) (文章) \
[升級 Windows 裝置以 Windows 10 專業版](upgrade-to-windows-pro-creators-update.md) (影片) \
[設定 Android 或 iOS 裝置的應用程式保護設定](app-protection-settings-for-android-and-ios.md) (文章) \
[設定或編輯 Windows 10 裝置的應用程式保護設定](protection-settings-for-windows-10-devices.md) (文章) \
[]

