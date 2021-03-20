---
title: 基本行動與安全性的功能
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本行動性和安全性可協助您保護和管理行動裝置。
ms.openlocfilehash: 468f06edf16eb6ea00fd4d26c716bc145474dd25
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904273"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>基本行動與安全性的功能

基本行動性和安全性可協助您保護和管理行動裝置，例如 Iphone、Ipad、Androids 和 Windows phone，您的組織中已獲授權的 Microsoft 365 使用者所使用的電話。 您可以建立行動裝置管理原則，其設定可協助控制存取您組織的 Microsoft 365 電子郵件，以及支援的行動裝置和應用程式的檔。 如果裝置遺失或遭盜，您可以遠端清除裝置，以移除敏感的組織資訊。

## <a name="supported-devices"></a>支援的裝置

您可以使用基本行動性和安全性來保護和管理下列裝置。

- iOS 11.0 或更新版本

- Android 5.0 或更新版本<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 行動電話<sup>2</sup>

<sup>1</sup>Windows 8.1 RT 裝置的存取控制限制為 Exchange ActiveSync。

<sup>2</sup>Windows 8.1 RT 裝置的存取控制限制為 Exchange ActiveSync。
Windows 10 的存取控制需要包含 Azure AD Premium 的訂閱，而且裝置必須加入 Azure Active Directory。

<sup>3</sup>Windows 8.1 RT 裝置的存取控制限制為 Exchange ActiveSync。
2020年6月之後，低於9的 Android 版本無法管理密碼設定，但在 Samsung Knox 裝置上除外。

>[!NOTE]
>已註冊舊版作業系統的裝置仍可運作，但功能可能會變更，恕不另行通知。

如果您組織中的人員使用基本行動性和安全性不支援的行動裝置，您可能想要封鎖 Exchange ActiveSync app 存取這些裝置的 Microsoft 365 電子郵件，以協助讓組織的資料更安全。 如需封鎖 Exchange ActiveSync 的步驟，請參閱 [管理基本行動性和安全性中的裝置存取設定](manage-device-access-settings.md)。

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Microsoft 365 電子郵件和檔的存取控制

下表中不同類型的行動裝置支援的應用程式，會提示使用者在基本行動裝置管理原則上登錄，並在其中加入新的行動裝置管理原則，該原則會套用至使用者的裝置，而且使用者先前尚未註冊裝置。 如果使用者的裝置不符合原則，視您設定原則的方式而定，使用者可能會遭到封鎖，無法在這些應用程式中存取 Microsoft 365 資源，或可能有存取權，但 Microsoft 365 會報告原則違規。

|**產品**|**iOS 10.0 或更新版本**|**Android 5.0 或更新版本**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync 包含內建的電子郵件和協力廠商的應用程式，例如 TouchDown，使用 Exchange ActiveSync 版本14.1 或更新版本。 |郵件 |電子郵件 |
|**Office**  和  **OneDrive 商務** 版 |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**在手機和平板電腦上**：<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **僅限電話：** <br/> Office Mobile |

>[!NOTE]
- >支援 iOS 10.0 和更新版本包含 iPhone 和 iPad 裝置。
- >基本的安全性和行動性不支援 BlackBerry OS 裝置的管理。 使用 BlackBerry Business 雲端服務 (BBCS) 從 BlackBerry 管理 BlackBerry 作業系統裝置。 支援執行 Android 作業系統的 Blackberry 裝置作為標準 Android 裝置
- >如果使用者使用行動瀏覽器來存取 Microsoft 365 SharePoint 網站、Office Online 中的檔，或 Outlook Web App 中的電子郵件，則不會提示使用者進行註冊，也不會對原則加以舉報。

下圖顯示當具有新裝置的使用者利用基本行動性和安全性，登入支援存取控制的應用程式時會發生什麼情況。 使用者在註冊其裝置之前，系統會封鎖使用者存取應用程式中的 Microsoft 365 資源。

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本行動性和安全性存取控制":::

> [!NOTE]
> 在 Microsoft 365 商務標準的基本行動及安全性中建立的原則和存取規則，會覆寫 exchange 系統管理中心建立的 Exchange ActiveSync 行動裝置信箱原則和裝置存取規則。 在 Microsoft 365 商務標準的基本行動及安全性中註冊裝置後，任何已套用至裝置的 Exchange ActiveSync 行動裝置信箱原則或裝置存取規則都會被忽略。 若要深入瞭解 Exchange ActiveSync，請參閱 exchange [Online 中的 exchange ActiveSync](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)。

## <a name="policy-settings-for-mobile-devices"></a>行動裝置的原則設定

如果您建立一個原則，以在開啟特定設定時封鎖存取，當您使用 [microsoft 365 電子郵件和檔的存取控制](capabilities.md)中所列的支援應用程式時，系統會封鎖使用者存取 Microsoft 365 資源。 

在下列各節中，可以封鎖使用者存取 Microsoft 365 資源的設定如下：

- 安全性

- 加密

- 越獄中斷

- 受管理的電子郵件設定檔  

例如，下圖顯示使用已註冊裝置的使用者不符合套用至其裝置之行動裝置管理原則中的安全性設定時，會發生什麼情況。 使用者可使用基本行動性和安全性登入支援存取控制的應用程式。 在使用者的裝置符合安全性設定之前，系統會封鎖他們存取應用程式中的 Microsoft 365 資源。

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本行動及安全性合規性訊息":::

下列各節列出您可以用來協助保護和管理連接至 Microsoft 365 組織資源之行動裝置的原則設定。

## <a name="security-settings"></a>安全性設定

|**設定名稱**|**iOS 7.1 和更新版本**|**Android 5 及更新版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|需要密碼|是|是|是|
|防止簡單密碼|是|否|否|
|需要一個數位元密碼|是|否|否|
|密碼最小長度 |是|是|是|
|擦除裝置之前的登入失敗次數 |是|是|是|
|鎖定裝置之前的閒置分鐘 |是|是|是|
|密碼到期 (天)  |是|是|是|
|記住密碼歷程記錄，並防止重複使用 |是|是|是|

## <a name="encryption-settings"></a>加密設定

|**設定名稱**|**iOS 7.1 和更新版本**|**Android 5 及更新版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|裝置<sup>1</sup>上需要資料加密 |否|是|是|

<sup>1</sup>使用 Samsung Knox，您也可以要求在儲存卡上加密。 

## <a name="jail-broken-setting"></a>越獄中斷設定 

|**設定名稱**|**iOS 7.1 和更新版本**|**Android 5 及更新版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|無法越獄中斷或根裝置 |是|是|是|

## <a name="managed-email-profile-option"></a>受管理的電子郵件設定檔選項 

下列選項可以封鎖使用者在使用手動建立的電子郵件設定檔時存取其 Microsoft 365 電子郵件。 IOS 裝置上的使用者必須先刪除其手動建立的電子郵件設定檔，才能存取其電子郵件。 在刪除設定檔之後，系統會自動在裝置上建立新的設定檔。 如需使用者如何相容的相關指示，請參閱 [找到現有的電子郵件帳戶](/intune-user-help/existing-company-email-account-found)。

|**設定名稱**|**iOS 7.1 和更新版本**|**Android 5 及更新版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|電子郵件設定檔已管理 |是|否|否|

## <a name="cloud-settings"></a>雲端設定

|**設定名稱**|**iOS 7.1 和更新版本**|**Android 5 及更新版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|需要加密備份 |是|否|否|
|封鎖雲端備份 |是|否|否|
|封鎖檔同步處理 |是|否|否|
|封鎖照片同步處理  |是|否|否|
|允許 Google 備份  |N/A|否|是|
|允許 Google 帳戶自動同步處理  |N/A|否|是|

## <a name="system-settings"></a>系統設定

|**設定名稱**|**iOS 7.1 和更新版本**|**Android 5 及更新版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|封鎖螢幕捕捉 |是|否|是|
|封鎖從裝置傳送診斷資料 |是|否|是|

## <a name="application-settings"></a>應用程式設定

|**設定名稱**|**iOS 7.1 和更新版本**|**Android 5 及更新版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|在裝置上封鎖影片會議 |是|否|否|
|封鎖對應用程式存放區的存取 |是|否|是|
|存取應用程式存放區時需要密碼 |否|是|是|

## <a name="device-capabilities-settings"></a>裝置功能設定

|**設定名稱**|**iOS 7.1 和更新版本**|**Android 5 及更新版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|使用 [可移動儲存區] 封鎖連線 |是|是|否|
|封鎖藍牙連線 |是|是|否|

## <a name="additional-settings"></a>其他設定

您可以使用安全性 & 合規性中心 PowerShell Cmdlet 來設定下列其他原則設定。 如需詳細資訊，請參閱 [安全性 & 規範中心 PowerShell](/powershell/exchange/scc-powershell)。

|**設定名稱**|**iOS 7.1 和更新版本**|**Android 5 及更新版本**|
|:-----|:-----|:-----|
|CameraEnabled|是|是|
|RegionRatings|是|否|
|MoviesRatings|是|否|
|TVShowsRating |是|否|
|AppsRatings |是|否|
|AllowVoiceDialing |是|否|
|AllowVoiceAssistant |是|否|
|AllowAssistantWhileLocked  |是|否|
|AllowPassbookWhileLocked |是|否|
|MaxPasswordGracePeriod |是|否|
|PasswordQuality |否|是|
|SystemSecurityTLS  |是|否|
|WLANEnabled  |否|否|

## <a name="settings-supported-by-windows"></a>Windows 支援的設定

您可以將 Windows 10 裝置登記為行動裝置，以進行管理。 在部署適用的原則之後，當使用者第一次使用內建的電子郵件應用程式存取其 Microsoft 365 電子郵件時，將需要使用 Windows 10 裝置的使用者才會註冊基本行動性和安全性。 (需要 Azure AD premium 訂閱) 。

已註冊為行動裝置的 Windows 10 裝置可支援下列設定。 這些設定不會封鎖使用者存取 Microsoft 365 資源。

### <a name="security-settings"></a>安全性設定

- 需要一個數位元密碼

- 密碼最小長度

- 擦除裝置之前的登入失敗次數

- 鎖定裝置之前的閒置分鐘

- 密碼到期 (天) 

- 記住密碼歷程記錄，並防止重複使用

>[!NOTE]
>下列設定控制密碼只會控制本機 Windows 帳戶。 透過加入網域或 Azure Active Directory 所提供的 Windows 帳戶，不會受到這些設定的影響。

### <a name="system-settings"></a>系統設定

封鎖從裝置發送診斷資料。

### <a name="additional-settings"></a>其他設定

您可以使用 PowerShell Cmdlet 來設定這些額外的原則設定：

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>遠端清除行動裝置

如果裝置遺失或遭盜，您可以移除敏感的組織資料，並透過從安全性 & 合規性中心（>**資料遺失防護**  >  **裝置管理**）進行擦除，以防止存取 Microsoft 365 組織資源。 您可以進行選擇性擦除，只移除組織資料或完全清除，以刪除裝置中的所有資訊，並將其還原為出廠設定。

如需詳細資訊，請參閱 [在基本行動及安全性中清除行動裝置](wipe-mobile-device.md)。

## <a name="related-topics"></a>相關主題

[Microsoft 365 的基本行動及安全性概述](overview.md)

[在基本行動性和安全性中建立裝置安全性原則](create-device-security-policies.md)