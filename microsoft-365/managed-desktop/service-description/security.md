---
title: Microsoft 受管理電腦中的安全性
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 6d3be89b52d71543687a02a1fd3fbae8bc1543f8
ms.sourcegitcommit: 4460975970ae13e917d4d336e92dbd76ae26493b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243934"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中的安全性

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft 受管理的電腦使用數種 Microsoft 技術來協助保護受管理的裝置和資料。 特別是： 

- [資料安全性](#data-security)的 Microsoft 受管理的電腦並安全地儲存所收集的資料類型
- [裝置安全性](#device-security)– 安全性和保護 Microsoft 受管理的電腦裝置上
- [身分識別與存取管理](#identity-and-access-management)– 管理安全使用的裝置透過 Azure Active Directory 身分識別服務
- [網路安全性](#network-security)– VPN 資訊和 Microsoft 受管理電腦的建議解決方案和設定
- [資訊安全性](#information-security)– 選用可用的服務，以進一步保護敏感資訊 

## <a name="data-security"></a>資料安全性

從客戶租用戶所收集的資料 （這可讓 Microsoft 受管理的桌上型電腦 IT 服務與作業） 會儲存在 Azure SQL 資料庫裝載於美國 Microsoft 租用戶中。

如需詳細資訊，請參閱[Microsoft Azure 安全性](https://docs.microsoft.com/azure/security/azure-database-security-overview)。

下面列出的資料從您的租用戶傳輸類型：

- 裝置更新、 使用狀況和可靠性資料
- 應用程式部署及可靠性資料
- [更新與安全性原則部署資料
- 使用者指派到裝置
- 從您的租用戶由 Microsoft 受管理的電腦，以管理服務的帳戶與相關的安全性記錄檔



## <a name="device-security"></a>裝置安全性

Microsoft 受管理的電腦，以確保所有受管理的裝置的安全和保護，且偵測威脅早開始儘可能使用下列服務：

Service | 描述
--- | ---
防毒 | 安裝及設定 Microsoft Defender AV<br>Microsoft Defender AV 的定義是最新狀態
完整的磁碟區加密 |    Windows BitLocker 是 Microsoft 受管理的電腦裝置的磁碟區加密解決方案。<br><br>恢復服務上的架組織之後，就會以防止未經授權的存取本機資料睡眠模式] 或 [關閉裝置時使用 Windows BitLocker 與內建信任平台模組 (TPM) 來加密裝置。 
監視 |    Microsoft Defender 進階威脅防護 (Microsoft Defender ATP) 用於所有 Microsoft 受管理的電腦裝置上的安全性威脅監視。 Microsoft Defender ATP 可讓企業客戶偵測、 調查及回應進階威脅其公司網路中。 如需詳細資訊，請參閱[Microsoft Defender 進階威脅防護。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
作業系統更新 |  Microsoft 受管理的電腦裝置一律受到保護與最新的安全性更新。
安全的裝置設定 |   Microsoft 受管理的電腦會實作 Microsoft 安全性基準。 如需詳細資訊，請參閱[Windows 安全性基準線。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>身分識別和存取管理

身分識別與存取管理保護公司資產和重要商業資料。 Microsoft 受管理的電腦設定裝置，以確保安全使用 Azure Active Directory (Azure AD) 與受管理的身分識別。 是要維護其 Azure AD 租用戶中的正確資訊的客戶的責任。 

Service | 描述
--- | ---
生物識別驗證 |  Windows Hello 可讓使用者使用其圖像] 或 [pin 碼，讓密碼忘記或竊取更難登入。 客戶負責在混合式組態中實作的這項服務的使用其內部部署 Active Directory 所需的必要條件。 如需詳細資訊，請參閱[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
標準使用者權限 |  若要保護您的系統，並讓它更安全，使用者會指派標準使用者權限。 這會指定為 Windows Autopilot 現成可用的體驗的一部分。



## <a name="network-security"></a>網路安全性

客戶負責網路安全性。 

Service | 描述
--- | ---
VPN | 客戶擁有其 VPN 基礎結構，以確保可以內部網路外公開公司資源有限。<br><br>最低需求： Microsoft 受管理的桌上型電腦需要 Windows 10 相容，並且支援的 VPN 解決方案。 如果您的組織需要的 VPN 解決方案，需要支援 Windows 10 和會封裝並可透過 Intune 部署。 如需詳細資訊，請連絡您的軟體發行者。<br><br>建議：<br>-Microsoft 建議新式的 VPN 解決方案可以輕易地部署透過 Intune 推入 VPN 設定檔。 這提供一律會開啟、 無縫、 可靠性和安全的方法來存取公司網路。 如需詳細資訊，請參閱[[在 Intune 中的 VPN 設定]](https://docs.microsoft.com/intune/vpn-settings-configure)。<br>-粗 VPN 用戶端或舊版 VPN 用戶端，不建議由 Microsoft 時使用 Microsoft 受管理的電腦，因為它可能會影響使用者的環境。<br>-Microsoft 建議的外寄的 web 流量直接移至網際網路而不必經由 VPN 為了避免發生效能問題。<br>-理想狀況下，Microsoft 建議使用 Azure Active Directory 應用程式 Proxy 而不是 VPN。


## <a name="information-security"></a>資訊安全性

客戶可以設定下列選用的服務，來協助保護公司高價值資產。 

Service | 描述
--- | ---
資料復原  | 至商務用 OneDrive 被備份儲存在裝置上的主要資料夾中的資訊。 Microsoft 受管理的電腦不負責不與商務用 OneDrive 同步處理的資料。 
Windows 資訊保護 |    對於需要高等級的資訊安全性的公司而言，我們建議[Windows 資訊保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)和[Azure 資訊保護。](https://www.microsoft.com/cloud-platform/azure-information-protection)。 

