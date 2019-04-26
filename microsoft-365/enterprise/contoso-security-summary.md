---
title: 適用於 Contoso Corporation 之 Microsoft 365 企業版安全性的摘要
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何使用整個 Microsoft 365 企業版的安全性功能。
ms.openlocfilehash: 55ee8ff88490a82a9438b076bcebfab976f8baf6
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289031"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a>適用於 Contoso Corporation 之 Microsoft 365 企業版安全性的摘要

**摘要：** Contoso 如何使用整個 Microsoft 365 企業版的安全性功能。

為了取得 IT 安全性部門對於 Microsoft 365 企業版部署的簽核，必須執行徹底的安全性檢閱。以下是 Contoso 對於雲端的安全性需求：

- 針對存取雲端資源的員工使用最嚴格的驗證方法
- 確定電腦和行動裝置連線與存取應用程式均安全無虞。
- 保護電腦和電子郵件不受惡意程式碼侵襲
- 雲端式數位資產的權限，定義誰可以存取哪些項目，可以執行哪些動作，以及指定最低權限存取權
- 機密和高管制數位資產會經過標示、加密，並且儲存在安全的位置
- 高管制數位資產會以權限進行保護
- IT 安全性人員可以從中央儀表板檢視安全性狀態，並取得安全性事件通知，以便快速回應及防護

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Contoso 進行 Microsoft 365 安全性整備的途徑

Contoso 會使用下列步驟來準備部署 Microsoft 365 企業版的安全性：

1. 受限制的雲端系統管理員帳戶

   Contoso 針對現有的 Active Directory Domain Services (AD DS) 系統管理員帳戶進行全面的審查，並設定了一系列的雲端系統管理員帳戶和群組。

2. 進行資料分類分析並分為三個層級

   Contoso 進行了謹慎的審查，並區分為三個層級，這三個層級可用來判斷 Microsoft 365 企業版功能以保護 Contoso 最重要的資料。

3. 判別各資料層級的存取權、保留期和資訊保護原則

   Contoso 會根據資料層級來決定詳細的要求，這些要求將運用於限定未來移至雲端的 IT 工作負載。

根據安全性最佳做法和 Microsoft 365 企業版部署需求，Contoso 的安全性管理員和 IT 部門已部署許多安全性功能，如下列章節所述。

## <a name="identity--access-management"></a>身分識別和存取管理 

- 專用的全域管理員帳戶 (具有 MFA 和 PIM)

  Contoso 並非將全域管理角色指派給每日使用者帳戶，而是建立三個、專用的全域管理員帳戶，具有非常強式的密碼，並且以多重要素驗證 (MFA) 和 Azure AD Privileged Identity Management (PIM) 加以保護。 

  使用全域管理員帳戶登入只能執行特定系統管理工作，只有指定的人員才知道密碼，且只能在使用 Azure AD PIM 設定的時間內使用。 

  Contoso 的安全性管理員相較於該 IT 人員作業功能和責任的適當帳戶，獲指派較少的管理角色。

  如需詳細資訊，請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

- 適用於所有使用者帳戶的 MFA

  MFA 會藉由要求使用者在正確輸入其密碼之後，確認電話來電、簡訊或智慧型手機上的應用程式通知，為登入程序新增多一層的保護。使用 MFA，Azure AD 使用者帳戶就會受保護，即使帳戶密碼遭到洩漏，也能防止未獲授權的登入。

   - 為了防護 Microsoft 365 訂閱遭入侵，Contoso 在所有全域管理員帳戶上都需要 MFA。
   - 為了防範網路釣魚攻擊，在此類攻擊中攻擊者會入侵組織中受信任人員的認證，並且傳送惡意電子郵件，Contoso 在所有使用者帳戶上啟用了 MFA，包括經理和決策階層人員。 

- 使用條件式存取原則獲得更安全的裝置和應用程式存取

  Contoso 針對身分識別、裝置、Exchange Online 和 SharePoint Online 使用[條件式存取原則](microsoft-365-policies-configurations.md)。身分識別條件式存取原則包含針對高風險使用者要求密碼變更，並且阻止用戶端使用未支援新式驗證的應用程式。裝置條件式存取原則包含已核准應用程式的定義，會要求相容的電腦和行動裝置。Exchange Online 條件式存取原則包含封鎖 ActiveSync 用戶端並設定 Office 365 訊息加密。SharePoint Online 條件式存取原則包含機密和高管制網站的額外保護。

- Windows Hello 企業版

  Contoso 已部署並要求 [Windows Hello 企業版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) (機器翻譯)，最終會在執行Windows 10 企業版的電腦和行動裝置上使用雙因素驗證，消除密碼的需求。

- Windows Defender Credential Guard

  為了封鎖在作業系統上使用系統管理權限執行的已設定目標攻擊和惡意程式碼，Contoso 已透過 AD DS 群組原則啟用 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard)。

## <a name="threat-protection"></a>威脅防護

- 使用 Windows Defender 防毒軟體防護惡意程式碼

  Contoso 使用 [Windows Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) (機器翻譯)，針對執行 Windows 10 企業版的電腦和裝置執行惡意程式碼防護和反惡意程式碼管理。

- 使用 Office 365 進階威脅防護來保護電子郵件流程和信箱稽核記錄 

  Contoso 使用 Exchange Online Protection 和 [Office 365 進階威脅防護 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) (機器翻譯)，來防護未知惡意程式碼、病毒及透過電子郵件傳輸的惡意 URL。 

  Contoso 也已啟用信箱稽核記錄，判斷誰已登入使用者信箱、傳送訊息，以及由信箱擁有者、委派使用者或系統管理員執行的其他活動。

- 使用 Office 365 威脅調查及回應來進行攻擊監視和防護

  Contoso 使用 [Office 365 威脅調查及回應](https://docs.microsoft.com/office365/securitycompliance/office-365-ti)，讓識別和解決攻擊以及防範未來的攻擊變得簡單，藉此來保護其 Office 365 使用者。

- 使用 Advanced Threat Analytics 來防護縝密的攻擊

  Contoso 使用 [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata)，來保護自身免於進階設定目標的攻擊。ATA 會自動分析、學習及識別正常和異常實體 (使用者、裝置及資源) 行為。 

## <a name="information-protection"></a>資訊保護

- 使用 Azure 資訊保護來保護機密和高管制數位資產

  Contoso 決定三個層級的資料保護，並且部署 [Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) 標籤，讓使用者套用至數位資產。針對其營業秘密和其他智慧財產權，Contoso 針對高管制資料 (會加密內容並且限制特定安全性群組的存取) 在範圍原則中使用 Azure 資訊保護子標籤。

- 使用 Office 365 資料外洩防護來防止內部網路資料外洩

  Contoso 已針對 Exchange Online、SharePoint Online 和商務用 OneDrive 設定[資料外洩防護](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies) (機器翻譯) 原則，以防止使用者意外或故意共用機密資料。

- 使用 Windows 資訊保護來防止裝置資料外洩

  Contoso 使用 [Windows 資訊保護 (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) (機器翻譯)，來防護下列形式的資料外洩：透過網際網路型應用程式和服務、企業應用程式、企業所擁有裝置上的資料，以及員工帶到職場的個人裝置。

- 使用 Microsoft Cloud App Security 來進行雲端監視

  Contoso 使用 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)，來對應其雲端環境、監視其使用量，以及偵測安全性事件。 

- 使用 Office 365 雲端 App 安全性來進行 Office 365 安全性監視

  Contoso 安全性系統管理員使用 [Office 365 雲端 App 安全性 (CAS)](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview) (機器翻譯) 來設定警示，對不正常或有風險的使用者活動進行通知，例如從 SharePoint Online 或商務用 OneDrive 下載大量資料、多次失敗的登入嘗試，或是從未知或危險的 IP 位址登入。

- 使用 Microsoft Intune 來進行裝置管理

  作為 Enterprise Management + Security (EMS) 套件的一部分，Contoso 使用 [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) 來註冊、管理及設定對於行動裝置及在其上執行之應用程式的存取權。裝置型條件式存取原則也會要求核准的應用程式和相容的電腦和行動裝置。

## <a name="security-management"></a>安全性管理

- 具有 Azure 資訊安全中心的 IT 中央安全性儀表板

  Contoso 使用 [Azure 資訊安全中心](https://docs.microsoft.com/intune/introduction-intune)以取得安全性和威脅保護的整合檢視，來管理工作負載之間的安全性原則，以及回應網路攻擊。

- 適用於具有 Windows Defender 資訊安全中心之使用者的中央安全性儀表板

  Contoso 已將 [Windows Defender 資訊安全中心應用程式](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) (機器翻譯) 部署至其執行 Windows 10 企業版的電腦和裝置，讓使用者可以一眼瀏覽其安全性狀態並採取動作。


## <a name="next-step"></a>下一步

[了解](contoso-sharepoint-online-site-for-highly-confidential-assets.md) Contoso 如何建立用於高管制資料的 Sharepoint 網站，使其研究小組之間能夠共同作業。

