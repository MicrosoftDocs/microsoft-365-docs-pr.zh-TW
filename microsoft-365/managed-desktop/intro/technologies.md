---
title: Microsoft 受管理的電腦技術
description: 本文列出 Microsoft 受管理的電腦中所用的技術和應用程式。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7c1f768e69fa65c76529e641f095e13fc7ad67c8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841337"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 受管理的電腦技術

本文列出 Microsoft 受管理的電腦中所用的技術和應用程式。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

所有 Microsoft 受管理的電腦使用者都需要 Microsoft 365 企業版授權。 如需服務授權需求的詳細資訊，請參閱[Microsoft 受管理的電腦的必要條件](../get-ready/prerequisites.md)。

本文摘要說明所需 Enterprise 授權中包含的元件，以及服務如何搭配每個元件使用 Microsoft 受管理的電腦裝置。 每個區域的特定角色和責任在整個 Microsoft 受管理的電腦檔中都是詳細的。 

## <a name="office-365-e3-or-e5"></a>Office 365E3 或 E5
 |
 --- | ---
Microsoft 365 Apps 企業版 (64 位)  | 這些 Office 的應用程式會隨裝置運送： Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype、OneNote。<br><br>不包含64位的 Microsoft Project 和 Microsoft Visio 的完整版本。 不過，因為安裝這些應用程式取決於 Microsoft 365 Apps 企業版安裝，所以 Microsoft 受管理的電腦已建立預設的 Microsoft Intune 部署和安全性群組，您可以使用這些部署和安全性群組將這些應用程式部署至授權的使用者。 如需詳細資訊，請參閱[Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio](../get-started/project-visio.md)。
OneDrive |Azure Active Directory當使用者第一次登入 OneDrive 時，會為使用者啟用單一登入。<br><br>包含「桌面」、「檔」及「圖片」資料夾的已知資料夾重新導向;由 Microsoft 受管理的電腦啟用和設定。
儲存應用程式 |    Microsoft Sway 和 Power BI 未附帶裝置。 這些應用程式可從 Microsoft Store 下載。
Win32 應用程式 |    Teams 不會隨裝置附帶，但會打包並由 Microsoft 提供給 Microsoft 受管理的電腦裝置。 Azure 資訊保護用戶端未附帶裝置，但是您可以將它打包以進行部署。
Web 應用程式 |  Yammer，在瀏覽器中 Office、Delve、Flow、StaffHub、PowerApps 和 Planner 不隨裝置附帶。 使用者可以使用瀏覽器存取這些應用程式的 web 版本。


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 企業版使用 Microsoft Defender for Endpoint 的 E5 或 E3
建議您的 IT 系統管理員設定下列設定值。 在 Microsoft 受管理的電腦中不會包含或管理這些設定。

 |
 --- | ---
Windows Hello 企業版 | 您應該使用 Microsoft 受管理的電腦裝置的強雙因素驗證來執行 Windows Hello 企業版以取代密碼。 如需詳細資訊，請參閱[Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。
應用程式虛擬化 | 您可以使用 Intune Win32 App management 用戶端 App-V) 套件部署 Application Virtualization (。 如需詳細資訊，請參閱 [Application Virtualization](/windows/application-management/app-v/appv-technical-reference)。
資料遺失防護 Microsoft 365 | 您應執行 Microsoft 365 資料遺失防護，以監視針對已確定為敏感之專案所採取的動作，以協助避免無意間共用這些專案。 如需詳細資訊，請參閱[Microsoft 365 資料遺失防護](../../compliance/endpoint-dlp-learn-about.md)。


在 Microsoft 受管理的電腦中包含並管理的功能：

 |
 --- | ---
BitLocker磁片磁碟機加密 | BitLocker磁片磁碟機加密是用來加密所有系統磁片磁碟機。 如需詳細資訊，請參閱[BitLocker 磁片磁碟機加密](/windows/security/information-protection/bitlocker/bitlocker-overview)。
Windows Defender系統防護 | 在啟動時保護系統的完整性，並驗證系統完整性是否已真正維護。 如需詳細資訊，請參閱[Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。
Windows Defender Credential Guard | Windows Defender Credential Guard 使用虛擬化的安全性來隔離機密，這樣只有有許可權的系統軟體可以存取這些機密。 如需詳細資訊，請參閱[Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。
Microsoft Defender for Endpoint Endpoint 偵測和回應 | Microsoft 受管理的電腦安全性作業會以端點偵測和回應，回應提醒並採取動作修正威脅。 如需詳細資訊，請參閱 [Microsoft Defender For Endpoint Endpoint 偵測和回應](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)。
Microsoft Defender for Endpoint 威脅專家 | Microsoft 受管理的電腦會透過目標的攻擊通知，與威脅專家的洞察力和資料整合。 您必須先提供額外的同意，才可啟用此服務。 如需詳細資訊，請參閱 [Microsoft Defender For Endpoint 威脅專家](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。
Microsoft Defender for Endpoint-威脅和弱點管理 | 在 Microsoft 受管理的電腦服務方案中供未來使用所需。 如需詳細資訊，請參閱 [Microsoft Defender For Endpoint-威脅和弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。
Microsoft Defender for Endpoint-攻擊面減少 | 攻擊面減少目標是經常被攻擊者濫用的危險軟體行為。 如需詳細資訊，請參閱 [Microsoft Defender For Endpoint 攻擊面降低](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。
Microsoft Defender for Endpoint Exploit Protection | 保護惡意程式碼，以利用利用漏洞來感染裝置，並透過自動將利用漏洞緩解技術套用至作業系統進程和應用程式來傳播。 如需詳細資訊，請參閱 [Microsoft Defender For Endpoint Exploit Protection](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)。
Microsoft Defender 用於端點網路保護 | 網路保護會擴充 Microsoft Defender SmartScreen 的範圍，以封鎖所有嘗試連線至低信譽來源的輸出 HTTP 和 HTTPS 流量。 如需詳細資訊，請參閱 [Microsoft Defender For Endpoint Network Protection](/windows/security/threat-protection/microsoft-defender-atp/network-protection)。
Microsoft Defender 防篡改保護 | Windows使用防篡改保護，可防止安全性設定（例如防防毒保護）遭到變更。 如需詳細資訊，請參閱 [Microsoft Defender 防篡改防護](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)。
Microsoft Defender 防毒軟體行為型、啟發式和即時防防毒保護 | Always on 掃描檔和處理威脅（可能偵測為惡意程式碼）。 如需詳細資訊，請參閱[Microsoft Defender 防毒軟體行為型、啟發式和即時防防毒保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)。
Microsoft Defender 防毒軟體雲端提供的保護 | 針對新的和新興的威脅提供動態接近即時的自動防護。 如需詳細資訊，請參閱[Microsoft Defender 防毒軟體雲端提供的保護](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)。
Microsoft Defender "初次看到即區塊" | 在 Windows 偵測到可疑或不明的檔案時，提供偵測和封鎖新的惡意程式碼。 如需詳細資訊，請參閱 [初次看到的 Microsoft Defender 封鎖](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。
Microsoft Defender AV 可能不需要的應用程式 | 可能有害的應用程式可用來封鎖可能導致機器執行緩慢、顯示未預期廣告的應用程式，或安裝其他可能是意外或不需要的軟體。 如需詳細資訊，請參閱 [Microsoft DEFENDER AV 可能有害的應用程式](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。
具有高級安全性的 Windows Defender 防火牆 | 裝置的主機型雙向網路流量篩選，Windows Defender 防火牆會封鎖進出本機裝置的未授權網路流量。 如需詳細資訊，請參閱[Windows Defender 防火牆具有高級安全性](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
使用者帳戶控制 | 當任務或動作需要管理員帳戶類型存取權時，使用者帳戶控制會切換至安全的桌面。 在註冊時，會為 Microsoft 受管理的電腦使用者指派標準使用者存取權。 如需詳細資訊，請參閱 [User Account Control](/windows/security/identity-protection/user-account-control/how-user-account-control-works)。


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + SecurityE5

 |
 --- | ---
企業行動力 + 安全性 E3<br>Azure Active Directory 進階版 P2 |    您可以使用企業行動力 + 安全性 E3 的所有功能來管理 MDM 裝置。 您可以使用 Azure Active Directory 進階版 P2 做為 Microsoft 受管理的電腦的選用功能。
Microsoft Cloud App Security |  您可以搭配 Microsoft 受管理的電腦使用此選用功能。
Azure 資訊保護 P2  | 您可以搭配 Microsoft 受管理的電腦使用此選用功能。
