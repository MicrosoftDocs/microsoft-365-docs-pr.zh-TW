---
title: Microsoft 受管理的電腦技術
description: 本文列出 Microsoft 受管理的桌面所用的技術和應用程式。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094864"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 受管理的電腦技術

本文列出 Microsoft 受管理的桌面所用的技術和應用程式。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

所有 Microsoft 受管理的桌面使用者都需要 microsoft 365 企業版授權。 如需服務授權需求的詳細資訊，請參閱 [Microsoft Managed Desktop 的必要條件](../get-ready/prerequisites.md)。

本文摘要說明所需企業授權中包含的元件，並說明服務如何使用每個元件與 Microsoft 受管理的桌面裝置。 在整個 Microsoft 受管理的桌面檔中會詳細說明每個區域的特定角色和責任。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 或 E5
 |
 --- | ---
適用于企業的 Microsoft 365 應用程式 (64-位)  | 這些 Office 應用程式會隨裝置運送： Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype、OneNote。<br><br>不包含 Microsoft Project 和 Microsoft Visio 的64位完整版本。 不過，由於安裝這些應用程式取決於 Microsoft 365 應用程式的 enterprise 安裝，因此 Microsoft Managed Desktop 已建立預設的 Microsoft Intune 部署和安全性群組，您可以用來將這些應用程式部署至授權的使用者。 如需詳細資訊，請參閱 [在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio](../get-started/project-visio.md)。
OneDrive |當使用者第一次登入 OneDrive 時，會為使用者啟用 Azure Active Directory 單一登入。<br><br>包含「桌面」、「檔」及「圖片」資料夾的已知資料夾重新導向;由 Microsoft Managed Desktop 啟用和設定。
儲存應用程式 |    Microsoft Sway 和 Power BI 未附帶裝置。 這些應用程式可從 Microsoft Store 下載。
Win32 應用程式 |    小組不會附帶裝置，但是會打包並由 Microsoft 提供給 Microsoft 受管理的桌面裝置。 Azure 資訊保護用戶端未附帶裝置，但是您可以將它打包以進行部署。
Web 應用程式 |  在瀏覽器中的 [Yammer]、「Delve」、「流程」、「StaffHub」、「PowerApps」和「規劃」都不隨裝置一起 使用者可以使用瀏覽器存取這些應用程式的 web 版本。



## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 企業版 E5 或 E3 （含 Microsoft Defender for Endpoint）
建議
 |
 --- | ---
[Windows Hello 企業版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) (英文) | 我們建議客戶實施 Windows Hello 企業版，以在 Microsoft 受管理的桌面裝置上使用強雙因素驗證來取代密碼。
[應用程式虛擬化](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | 客戶可以使用 Intune Win32 App management 用戶端 App-V) 套件部署 Application Virtualization (。
[Microsoft 365 資料遺失防護](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | 客戶建議執行 Microsoft 365 資料遺失防護 (DLP) ，以監視對您已判斷為敏感之專案所採取的動作，以及協助避免無意間共用這些專案。   

服務中包含和管理
 |
 --- | ---
[BitLocker 磁片磁碟機加密](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | BitLocker 磁片磁碟機加密是用來加密所有系統磁片磁碟機。 
[Windows Defender 系統防護]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | 在啟動時保護系統的完整性，並驗證系統完整性是否已真正維護。
[Windows Defender Credential Guard]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | Windows Defender 身分憑證防護會使用虛擬化安全性來隔離機密，這樣只有有許可權的系統軟體可以存取這些機密。
[Microsoft Defender for Endpoint | 端點偵測和回應] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     Microsoft Managed Desktop Security Operations 會以端點偵測和回應，回應提醒並採取動作修正威脅。
[Microsoft Defender for Endpoint | 威脅專家] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | Microsoft 受管理的桌面會透過目標攻擊通知，與威脅專家的洞察力和資料整合。 在啟用此服務之前，必須先向客戶提供額外的同意。  
[Microsoft Defender for Endpoint | 威脅和弱點管理] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | 在 Microsoft Managed Desktop service 方案中未來使用所需。
[Microsoft Defender for Endpoint | 攻擊面減少] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | 攻擊面減少目標是經常被攻擊者濫用的危險軟體行為。
[Microsoft Defender for Endpoint | Exploit Protection] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | 保護惡意程式碼，以利用利用漏洞來感染裝置，並透過自動將利用漏洞緩解技術套用至作業系統進程和應用程式來傳播。
[Microsoft Defender for Endpoint | 網路保護] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | 網路保護可擴充 Microsoft Defender SmartScreen 的範圍，以封鎖所有嘗試連線至低信譽來源的輸出 HTTP (s) 流量。
[Microsoft Defender 防篡改保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | Windows 防篡改保護可用於防止安全性設定（例如防防毒保護）遭到變更。
[Microsoft Defender 防病毒行為、啟發式和即時防防毒保護]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | Always on 掃描檔和處理威脅（可能偵測為惡意程式碼）。
[Microsoft Defender 防病毒雲端提供的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | 針對新的和新興的威脅提供動態接近即時的自動防護。
[Microsoft Defender 在初次看到時會封鎖](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | 會在 Windows 偵測到可疑或不明的檔案時，提供偵測並封鎖新的惡意程式碼。
[Microsoft Defender AV 可能不需要的應用程式](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | 可能有害的應用程式 (PUA) 可用來封鎖可能導致機器執行緩慢、顯示未預期廣告的應用程式，或安裝其他可能是意外或不需要的軟體。
[具有高級安全性的 Windows Defender 防火牆](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | 以主機為基礎的雙向網路流量篩選裝置，Windows Defender 防火牆會封鎖進出本機裝置的未授權網路流量。
[使用者帳戶控制](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | 當任務或動作需要管理員帳戶類型存取權時，使用者帳戶控制會切換至安全的桌面。 Microsoft 受管理的桌面使用者在註冊時會被指派標準使用者存取權。 


## <a name="enterprise-mobility--security-e5"></a>企業行動 + 安全性 E5

 |
 --- | ---
企業行動性 + 安全性 E3<br>Azure Active Directory Premium P2 |    您可以使用企業行動裝置 + Security E3 和 Azure Active Directory Premium P2 的所有功能來管理 MDM 裝置。
Microsoft Cloud App Security |  您可以將此選用功能與 Microsoft Managed Desktop 搭配使用。
Azure 資訊保護 P2  | 您可以將此選用功能與 Microsoft Managed Desktop 搭配使用。
