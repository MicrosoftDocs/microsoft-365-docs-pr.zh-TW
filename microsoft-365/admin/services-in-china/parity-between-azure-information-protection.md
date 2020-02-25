---
title: 21Vianet 運作的 Office 365
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: 深入了解 Azure 資訊保護 21Vianet 以及如何將它設定為客戶在中國由 21vianet 運作的 Office 365。
monikerRange: o365-21vianet
ms.openlocfilehash: a4eb8c3370a123b939fdccc53eec3905f79ee806
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240279"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>由 21Vianet 和商業供應項目運作的 Office 365 的 Azure 資訊保護之間的同位檢查

雖然我們的目標是由 21Vianet 提供的功能運作的 Office 365 的客戶在中國使用我們的 Azure 資訊保護傳遞所有商業功能和功能，還有一些遺漏的功能，我們想要反白顯示。

由 21Vianet 和截至年 7 月 2019年我們商業供應項目運作的 Office 365 的 Azure 資訊保護之間的現有差距，如下：

- 僅適用於 Office 365 專業增強版 （組建 11731.10000 或更高版本） 支援資訊版權管理 (IRM)。 不支援 office 2010、 Office 2013 和其他 Office 2016 版本。

- 從 Active Directory Rights Management Services (AD RMS) 移轉至 Azure 資訊保護目前無法使用。
  
- 支援的受保護的電子郵件給商業雲端中的使用者共用。
  
- 共用文件和電子郵件附件商業雲端中使用者的目前無法使用。 這包括由 21Vianet 使用者商業雲端，非 Office 365 21vianet 運作的商業雲端中，21Vianet 使用者和使用 RMS 個人授權的使用者中運作的 Office 365。
  
- IRM 與 SharePoint （受 IRM 保護的網站和文件庫） 目前無法使用。
  
- 版權管理連接器目前無法使用。
  
- AD rms 的行動裝置擴充目前無法使用。

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>中國的客戶設定 Azure 資訊保護

### <a name="enable-rights-management-for-the-tenant"></a>針對租用戶啟用權限管理

若要正常運作的加密，RMS 必須啟用租用戶。

- 如果已啟用 RMS，檢查：
  1. 以系統管理員身分啟動 PowerShell。
  2. 如果未安裝 AIPService 模組，執行 `Install-Module AipService`。
  3. 匯入模組使用`Import-Module AipService`。
  4. 連線至服務使用 `Connect-AipService -environmentname azurechinacloud`。
  5. 執行 `(Get-AipServiceConfiguration).FunctionalState` 及檢查的狀態是否為 `Enabled`。

- 如果正常運作狀態是 `Disabled`、 執行 `Enable-AipService`。

### <a name="dns-configuration-for-encryption-windows"></a>DNS 組態加密 (Windows)

加密能夠正常運作，Office 用戶端應用程式必須連線至中國執行個體的服務和啟動安裝程式從該處。 若要重新導向至正確的服務執行個體的用戶端應用程式，租用戶系統管理員必須設定 DNS SRV 記錄，與 Azure RMS URL 的相關資訊。 DNS SRV 記錄，而用戶端應用程式會嘗試連線至公用雲端執行個體，根據預設，並將會失敗。

此外，將假設是使用者將登入基礎關閉租用戶擁有網域使用者名稱 (例如， `joe@contoso.cn`)，而不`onmschina`使用者名稱 (例如， `joe@contoso.onmschina.cn`)。 使用者名稱的網域名稱用於 DNS 重新導向至正確的服務執行個體。

- 取得 RMS 識別碼：
  1. 以系統管理員身分啟動 PowerShell。
  2. 如果未安裝 AIPService 模組，執行 `Install-Module AipService`。
  3. 連線至服務使用 `Connect-AipService -environmentname azurechinacloud`。
  4. 執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 若要取得 RMS 識別碼。

- 登入您的 DNS 提供者，瀏覽至該網域的 DNS 設定，然後新增新的 SRV 記錄。
  - 服務 = `_rmsredir`
  - 通訊協定 = `_http`
  - 名稱 = `_tcp`
  - 目標 = `[GUID].rms.aadrm.cn` （其中的 GUID 是 RMS 識別碼）
  - 優先順序、 粗細秒，TTL = 預設值

- 建立自訂的網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的租用戶的關聯。 這會在 DNS 中，這可能需要數分鐘才能取得驗證之後您將值新增至 [DNS 設定新增項目。

- Microsoft 365 系統管理中心使用對應的全域系統管理員認證登入，並新增網域 (例如， `contoso.cn`) 的使用者建立。 中的驗證程序可能需要額外的 DNS 變更。 一旦完成驗證時，您可以建立使用者。

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>DNS 組態加密 (Mac、 iOS、 Android)

- 登入您的 DNS 提供者，瀏覽至該網域的 DNS 設定，然後新增新的 SRV 記錄。
  - 服務 = `_rmsdisco`
  - 通訊協定 = `_http`
  - 名稱 = `_tcp`
  - 目標 = `api.aadrm.cn`
  - 連接埠 = `80`
  - 優先順序、 粗細秒，TTL = 預設值
