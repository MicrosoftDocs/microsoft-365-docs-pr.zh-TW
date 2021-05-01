---
title: Contoso Corporation 之企業安全性的 Microsoft 365 摘要
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何使用 Microsoft 365 for enterprise 的安全性功能。
ms.openlocfilehash: 59eed0b7e08aae8397bb037e6d1b515bf6aa0ba8
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113447"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Contoso Corporation 之企業安全性的 Microsoft 365 摘要

若要取得部署企業版 Microsoft 365 的核准，Contoso IT 安全部已執行徹底的安全性審查。 他們識別雲端的下列安全性需求：

- 使用最強的驗證方法，以供員工存取雲端資源。
- 確定電腦和行動裝置會以安全的方式連線和存取應用程式。
- 保護電腦及電子郵件免受惡意程式碼攻擊。
- 以雲端為基礎的數位資產許可權定義誰可以存取哪些專案、可以進行哪些動作，以及專為最低許可權存取而設計
- 機密和高管制數位資產會標示、加密，並儲存在安全的位置。
- 高管制數位資產會以額外的加密和許可權加以保護。
- IT 安全性人員可以從中央儀表板監控目前的安全性狀況，並取得安全性事件的通知，以進行快速回應及緩解。

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Microsoft 365 安全性準備工作的 Contoso 路徑

Contoso 遵循下列步驟，為企業版的 Microsoft 365 部署準備安全性：

1. 限制雲端的系統管理員帳戶

   Contoso 已大量複查其現有的 Active Directory 網域服務 (AD DS) 系統管理員帳戶，並設定專門的雲端系統管理員帳戶和群組的系列。

2. 將資料分類至三個安全性層級

   Contoso 已認真檢查並決定三個層級，用來識別企業功能的 Microsoft 365，以保護最有價值的資料。

3. 決定資料層級的存取、保留和資訊保護原則

   Contoso 根據資料層級，確定將未來 IT 工作負載移至雲端的詳細要求。

為了遵循安全性最佳作法和 Microsoft 365 的企業部署需求，Contoso security administrators 和其 IT 部門部署了許多安全性功能，如下列各節所述。

## <a name="identity-and-access-management"></a>身分識別和存取管理 

- 專用的全域管理員帳戶 (具有 MFA 和 PIM)

  Contoso 建立了三個具有強式密碼的專屬全域管理員帳戶，而不是將全域系統管理員角色指派給日常使用者帳戶。 帳戶受到 azure ad Multi-Factor 驗證 (MFA) 和 Azure Active Directory (Azure ad) Privileged Identity Management (PIM) 。 *PIM 僅在 Microsoft 365 E5 中提供。*

  以全域系統管理員帳戶登入只會對特定的管理工作執行。 僅限指定的人員知道密碼，而且只能在 Azure AD PIM 所設定的時段內使用。

  Contoso 安全性管理員指派較低的系統管理員角色給適當于該 IT 工作者工作職能的帳戶。

  如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](/office365/admin/add-users/about-admin-roles)。

- 適用於所有使用者帳戶的 MFA

  MFA 會為登入處理常式新增其他的保護層。 在正確輸入密碼後，它需要使用者在其 smart phone 上承認通話、文字訊息或代理程式更新。 透過 MFA，Azure AD 使用者帳戶會受到保護，防止未經授權的登入，即使帳戶密碼遭到破壞也是一樣。

   - 為了防範 Microsoft 365 訂閱的洩漏，Contoso 在所有全域管理員帳戶上都需要 MFA。
   - 為了防範網路釣魚攻擊，在此類攻擊中攻擊者會入侵組織中受信任人員的認證，並且傳送惡意電子郵件，Contoso 在所有使用者帳戶上啟用了 MFA，包括經理和決策階層。

- 使用條件式存取原則獲得更安全的裝置和應用程式存取

  Contoso 針對身分識別、裝置、Exchange Online 和 SharePoint 使用[條件式存取原則](../security/office-365-security/microsoft-365-policies-configurations.md)。身分識別條件式存取原則包含針對高風險使用者要求密碼變更，並且阻止用戶端使用未支援新式驗證的應用程式。裝置存取原則包含已核准應用程式的定義，會要求相容的電腦和行動裝置。Exchange Online 條件式存取原則包含封鎖 ActiveSync 用戶端並設定 Office 365 訊息加密。SharePoint 條件式存取原則包含機密和高管制網站的額外保護。

- Windows Hello 企業版

  Contoso 已部署[Windows Hello 企業版](/windows/security/identity-protection/hello-for-business/hello-identity-verification)，最終可在執行 Windows 10 企業版的電腦和行動裝置上，透過強雙因素驗證，以消除密碼的需求。

- Windows Defender Credential Guard

  若要以系統管理許可權封鎖在作業系統中執行的目標攻擊和惡意程式碼，Contoso 已透過 AD DS 群組原則啟用[Windows Defender Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard) 。

## <a name="threat-protection"></a>威脅防護

- 使用 Windows Defender 防毒軟體防護惡意程式碼

  Contoso 使用 [Windows Defender 防毒軟體](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)，針對執行 Windows 10 企業版的電腦和裝置執行惡意程式碼防護和反惡意程式碼管理。

- 安全電子郵件流程和信箱審計記錄使用 Microsoft Defender for Office 365 

  Contoso 使用 Exchange Online Protection 和[Defender 進行 Office 365](/office365/securitycompliance/office-365-atp) ，以防範透過電子郵件傳輸的未知惡意程式碼、病毒和惡意 URLs。

  Contoso 也啟用信箱審核記錄，以識別登入使用者信箱的人員、傳送郵件，以及由信箱擁有者、委派的使用者或系統管理員所執行的其他活動。

- 使用 Office 365 威脅調查及回應來進行攻擊監視和防護

  Contoso 使用[Office 365 威脅調查和回應](/office365/securitycompliance/office-365-ti)，讓使用者輕鬆識別及處理攻擊，並避免未來的攻擊，以保護使用者。

- 使用 Advanced Threat Analytics 來防護縝密的攻擊

  Contoso 使用 [Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata)，來保護自身免於進階設定目標的攻擊。ATA 會自動分析、學習及識別正常和異常實體 (使用者、裝置及資源) 行為。

## <a name="information-protection"></a>資訊保護

- 使用 Azure 資訊保護標籤來保護機密和高管制數位資產

  Contoso 決定了三個資料保護層級，並部署了[Microsoft 365 敏感度標籤](../compliance/sensitivity-labels.md)，供使用者套用至數位資產。 對於其商業機密和其他智慧財產權，Contoso 使用敏感度分組進行高管制的資料。 此程式會加密內容，並限制特定使用者帳戶和群組的存取權。

- 使用資料外洩防護來防止內部網路資料外洩

  Contoso 設定 Exchange Online、SharePoint 及商務用 OneDrive 的[資料遺失防護](../compliance/dlp-learn-about-dlp.md)原則，以防止使用者意外或故意共用機密資料。

- 使用 Windows 資訊保護來防止裝置資料外洩

  Contoso 使用[Windows 資訊保護 (WIP) ](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) ，以防止資料洩漏，透過網際網路型應用程式和服務、企業應用程式，以及員工可運作的個人裝置上的資料。

- 使用 Microsoft Cloud App Security 來進行雲端監視

  Contoso 使用 [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)，來對應其雲端環境、監視其使用量，以及偵測安全性事件。 *Microsoft 雲端 App 安全性僅在 Microsoft 365 E5 中提供。*

- 使用 Microsoft Intune 來進行裝置管理

  Contoso 使用 [Microsoft Intune](/intune/introduction-intune) 來註冊、管理及設定對於行動裝置及在其上執行之應用程式的存取權。裝置型條件式存取原則也會要求核准的應用程式和相容的電腦和行動裝置。

## <a name="security-management"></a>安全性管理

- 使用 Azure Defender 時使用的中央安全性儀表板

  Contoso 使用 [Azure Defender](https://azure.microsoft.com/services/security-center/) 來呈現安全和威脅防護的統一視圖、管理其工作負載的安全性原則，以及回應 cyberattacks。

- 適用於具有 Windows Defender 資訊安全中心之使用者的中央安全性儀表板

  Contoso 將[Windows 安全性應用程式](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)部署至其電腦與執行 Windows 10 企業版的裝置，讓使用者可以立即查看其安全性狀態，並採取行動。