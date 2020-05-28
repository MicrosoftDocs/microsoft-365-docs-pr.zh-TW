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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: 深入瞭解 Office 365 所運作的 Azure 資訊保護，以及如何在中國為客戶設定它。
monikerRange: o365-21vianet
ms.openlocfilehash: 1f5d73f5c421a545ea0085f018a2c2a703b0b374
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399035"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>由世紀和商業版產品運作之 Office 365 的 Azure 資訊保護之間的奇偶性

雖然我們的目標是將所有商業功能和功能提供給中國客戶的 Azure 資訊保護，以供由世紀所運作的 Office 365 使用，但我們仍需要反白顯示某些功能。

這些是由世紀運作的 Office 365 Azure 資訊保護之間的現有缺口，從7月2019起。

- 僅適用于企業版（組建11731.10000 或更新版本）的 Microsoft 365 應用程式支援資訊版權管理（IRM）。 Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。

- 從 Active Directory Rights Management Services （AD RMS）到 Azure 資訊保護的遷移目前無法使用。
  
- 支援將受保護的電子郵件共用至商業雲端中的使用者。
  
- 目前無法將檔和電子郵件附件共用給商業雲端中的使用者。 這包括由使用者在商業雲端中運作的 Office 365、由商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。
  
- 具有 SharePoint （IRM 保護的網站和程式庫）的 IRM 目前無法使用。
  
- 目前無法使用 Rights Management 連接器。
  
- 目前無法使用 AD RMS 的行動裝置分機。

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>為中國的客戶設定 Azure 資訊保護

### <a name="enable-rights-management-for-the-tenant"></a>啟用租使用者的版權管理

為使加密正確運作，RMS 必須啟用租使用者。

- 檢查 RMS 是否已啟用：
  1. 以系統管理員身分啟動 PowerShell。
  2. 若未安裝 AIPService 模組，請執行  `Install-Module AipService` 。
  3. 使用匯入模組 `Import-Module AipService` 。
  4. 使用連線至服務  `Connect-AipService -environmentname azurechinacloud` 。
  5. 執行  `(Get-AipServiceConfiguration).FunctionalState`   並檢查狀態是否為  `Enabled` 。

- 如果功能狀態為  `Disabled` ，請執行  `Enable-AipService` 。

### <a name="dns-configuration-for-encryption-windows"></a>加密的 DNS 設定（Windows）

若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡開始進行引導。 若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。 若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。

此外，假設使用者將會以使用者身分登入，而不是以租使用者擁有的網域（例如）來登入 `joe@contoso.cn` ，而不是使用者的使用者 `onmschina` 名稱（例如 `joe@contoso.onmschina.cn` ）。 Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。

- 取得 RMS ID:
  1. 以系統管理員身分啟動 PowerShell。
  2. 若未安裝 AIPService 模組，請執行  `Install-Module AipService` 。
  3. 使用連線至服務  `Connect-AipService -environmentname azurechinacloud` 。
  4. 執行  `(Get-AipServiceConfiguration).RightsManagementServiceId`   以取得 RMS 識別碼。

- 登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。
  - Service = `_rmsredir`
  - Protocol = `_http`
  - 名稱 = `_tcp`
  - Target =  `[GUID].rms.aadrm.cn`   （GUID 是 RMS 識別碼）
  - Priority，權數，Seconds，TTL = 預設值

- 將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。 這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。

- 使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域（例如 `contoso.cn` ）以供使用者建立。 在驗證程式中，可能需要進行其他 DNS 變更。 完成驗證之後，即可建立使用者。

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>加密的 DNS 設定（Mac、iOS、Android）

- 登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。
  - Service = `_rmsdisco`
  - Protocol = `_http`
  - 名稱 = `_tcp`
  - Target = `api.aadrm.cn`
  - 埠 = `80`
  - Priority，權數，Seconds，TTL = 預設值
