---
title: Microsoft 受管理電腦中的安全性
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 791a69433653de3960af6f8d8e1e9b23067dd6c0
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322002"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中的安全性

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft 受管理的桌面使用數種 Microsoft 技術來協助保護受管理的裝置和資料。 特別是： 


- [裝置安全性](#device-security)– Microsoft 受管理桌面裝置上的安全性和保護
- 身分[識別和存取管理](#identity-and-access-management)-透過 Azure Active Directory 身分識別服務管理裝置的安全使用
- [網路安全性](#network-security)-VPN 資訊和 Microsoft 受管理的桌面建議方案和設定
- [資訊安全性](#information-security)–選用的可用服務以進一步保護機密資訊 

如需 Microsoft 管理的桌面所使用之資料儲存、使用方式及安全性作法的資訊，請下載我們的白皮書 [https://aka.ms/mmd-data](https://aka.ms/mmd-data) 。

如需 Microsoft 受管理電腦上的安全性作業小組及其如何運作以提供裝置安全性的詳細資訊，請參閱[Microsoft Managed Desktop Security Operations](https://www.microsoft.com/videoplayer/embed/RE4q6nP)影片。 

## <a name="device-security"></a>裝置安全性

Microsoft 受管理的桌面可確保所有受管理的裝置受到保護，並受保護，並儘早使用下列服務偵測威脅：

Service | 描述
--- | ---
防毒 | 已安裝並設定 Microsoft Defender AV<br>Microsoft Defender AV 定義是最新的
整磁片區加密 |    Windows BitLocker 是 Microsoft 受管理桌面裝置的磁片區加密解決方案。<br><br>在將組織架至服務後，裝置將會使用 Windows BitLocker 與內建信任平臺模組（TPM）加密，以防止在裝置處於睡眠模式或關閉時未授權存取本機資料。 
監視 |    Microsoft Defender 高級威脅防護（Microsoft Defender ATP）是用於跨所有 Microsoft 受管理的桌面裝置進行安全性威脅監控。 Microsoft Defender ATP 可讓企業客戶偵測、調查和回應公司網路中的高級威脅。 如需詳細資訊，請參閱[Microsoft Defender 高級威脅防護。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
作業系統更新 |  Microsoft 受管理的桌面裝置一定會以最新的安全性更新加以保護。
安全裝置設定 |   Microsoft 受管理的桌面會實現 Microsoft 安全性基準。 如需詳細資訊，請參閱[Windows 安全性基準。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>身分識別和存取管理

身分識別和存取管理可保護公司資產和業務關鍵型資料。 Microsoft Managed Desktop 會設定裝置，以確保與 Azure Active Directory （Azure AD） Managed identity 安全搭配使用。 客戶在其 Azure AD 租使用者中維護正確資訊的責任。 

Service | 描述
--- | ---
生物識別驗證 |  Windows Hello 允許使用者利用其面孔或 PIN 碼登入，使密碼難於忘記或盜取。 客戶負責針對其內部部署 Active Directory 實施必要先決條件，以在混合式設定中使用此服務。 如需詳細資訊，請參閱[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
標準使用者許可權 |  若要保護系統並使其更安全，將會指派標準使用者許可權給使用者。 這會指派為 Windows Autopilot 全新體驗的一部分。



## <a name="network-security"></a>網路安全性

客戶負責網路安全性。 

Service | 描述
--- | ---
VPN | 客戶擁有其 VPN 基礎結構，以確保有限的公司資源可以公開于內部網路以外。<br><br>最低需求： Microsoft 受管理的桌面需要 Windows 10 相容且支援的 VPN 解決方案。 如果您的組織需要 VPN 解決方案，它必須支援 Windows 10，並且可透過 Intune 打包及部署。 如需詳細資訊，請與您的軟體發行者聯繫。<br><br>建議：<br>-Microsoft 建議使用可輕鬆透過 Intune 部署的新式 VPN 解決方案，以推送 VPN 設定檔。 這為存取公司網路提供了永不間斷、流暢、可靠且安全的方式。 如需詳細資訊，請參閱[[Intune 中的 VPN 設定]](https://docs.microsoft.com/intune/vpn-settings-configure)。<br>-使用 Microsoft 受管理的桌面時，Microsoft 不建議使用-厚 VPN 用戶端或舊版 VPN 用戶端，因為這會影響使用者環境。<br>-Microsoft 建議您不經 VPN 直接前往網際網路傳送傳出的 web 流量，以避免任何效能問題。<br>-理想情況下，Microsoft 建議使用 Azure Active Directory 應用程式 Proxy，而不是 VPN。


## <a name="information-security"></a>資訊安全性

您可以設定這些選用服務，協助保護公司的高價值資產。 

Service | 描述
--- | ---
資料恢復  | 儲存在裝置上重要資料夾中的資訊，會備份至 Business OneDrive。 Microsoft 受管理的桌面不會負責未與 Business OneDrive 同步處理的資料。 
Windows 資訊保護 |    針對需要高資訊安全性層級的公司，我們建議[Windows 資訊保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)和[Azure 資訊保護。](https://www.microsoft.com/cloud-platform/azure-information-protection) 

