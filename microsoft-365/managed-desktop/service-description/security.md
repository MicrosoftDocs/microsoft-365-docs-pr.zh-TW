---
title: Microsoft 受管理電腦中的安全性
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866744"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中的安全性

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft 受管理的桌上型電腦套用之原則的標準設定並使用為了安全 Microsoft 受管理的桌上型電腦裝置、 預存的公司資料及其他許多 Microsoft 技術。下面所列的區域會進一步詳細說明：  

- [資料安全性](#data-security)Microsoft 受管理的桌上型電腦及安全地儲存所收集的資料類型
- [裝置安全性](#device-security)– 安全性和保護 Microsoft 受管理的桌上型電腦裝置上
- [身分識別與存取管理](#identity-and-access-management)– 管理安全使用的裝置透過 Azure Active Directory 身分識別服務
- [網路安全性](#network-security)– VPN 資訊和 Microsoft 受管理的桌上型電腦建議的解決方案和設定
- [資訊安全性](#information-security)– 進一步保護敏感資訊的選用可用服務 

## <a name="data-security"></a>資料安全性

從客戶承租人收集的資料 （可讓 Microsoft 受管理的桌上型電腦 IT 服務和作業） 會儲存在架設在美國為 Microsoft 租用戶中的 Azure SQL 資料庫。

如需詳細資訊，請參閱[Microsoft Azure 安全性](https://docs.microsoft.com/azure/security/azure-database-security-overview)。

下面所列是從您的租用戶傳輸的資料類型：

- 裝置更新、 使用量及可靠性資料
- 應用程式部署及可靠性資料
- 更新與安全性原則部署資料
- 指派給裝置的使用者



## <a name="device-security"></a>裝置安全性

Microsoft 受管理的桌上型電腦會確保受管理的所有裝置保護及受到保護，且偵測威脅早儘可能使用下列服務：

服務 | 描述
--- | ---
防毒 | 安裝及設定 Windows 防禦者 AV<br>Windows 防禦者 AV 定義為最新
完整的磁碟區加密 |    Windows BitLocker 是 Microsoft 受管理的桌上型電腦裝置的磁碟區加密解決方案。<br><br>後組織 onboarded 服務，裝置會使用與內建信任平台模組 (TPM) Windows BitLocker 防止本機資料未經授權的存取裝置時睡眠模式] 或 [關閉加密。 
監視 |    跨 Microsoft 受管理的桌上型電腦的所有裝置的安全性威脅監視適用於 Windows 防禦者進階威脅保護 (Windows 防禦者 ATP)。Windows 防禦者 ATP 可讓企業客戶偵測、 調查及回應其公司網路中的進階威脅。如需詳細資訊，請參閱[Windows 防禦者進階威脅保護。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
軟體更新 |  Microsoft 受管理的桌上型電腦裝置一律保護使用最新的安全性更新。
安全的裝置設定 |   Microsoft 受管理的桌上型電腦實作 Microsoft 安全性基準。如需詳細資訊，請參閱[Windows 安全性基準。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>身分識別和存取管理

身分識別與存取管理會保護的公司資產及重要商業資料。Microsoft 受管理的桌上型電腦設定以確保安全使用 Azure Active Directory (Azure AD) 受管理的身分識別的裝置。它會維護其 Azure AD 租用戶中的正確資訊的客戶的責任。 

服務 | 描述
--- | ---
生物特徵驗證 |  Windows Hello 可讓使用者使用其圖像或 PIN 進行更困難忘記或竊取密碼登入。如需詳細資訊，請參閱[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
多重要素驗證 | Azure 的多重要素驗證更緊密控制存取權之 Microsoft 受管理的桌上型電腦服務機密函數提供使用行動電話，以及為自助密碼重設為驗證其他層級。 
標準使用者權限 |  若要保護系統並讓它更安全，使用者會指派標準使用者權限。這會指定為 Windows 自動駕駛儀上的現成體驗的一部分。



## <a name="network-security"></a>網路安全性

客戶負責網路安全性。 

服務 | 描述
--- | ---
VPN | 客戶擁有其 VPN 基礎結構，以確保有限的公司資源可以公開於內部網路之外。<br><br>最低需求： Microsoft 受管理的桌上型電腦需要 Windows 10 相容和支援 VPN 解決方案。如果您的組織需要 VPN 解決方案，它必須支援 Windows 10 會封裝並可透過 Intune 部署。如需詳細資訊，請洽詢您軟體發行者。<br><br>建議：<br>Microsoft 建議無法輕鬆地部署到 Intune 至推入 VPN 設定檔的現代 VPN 解決方案。這提供一律在、 順暢、 可靠且安全的方法來存取公司網路。如需詳細資訊，請參閱[[Intune VPN 設定]](https://docs.microsoft.com/intune/vpn-settings-configure)。<br>-粗 VPN 用戶端或舊版 VPN 用戶端，並不建議 microsoft 時使用 Microsoft 受管理的桌上型電腦它可能會影響使用者環境。<br>Microsoft 建議的外寄的網頁流量前往直接網際網路而不必經由 VPN，以免發生任何效能問題。<br>-理想狀況下，Microsoft 建議 Azure Active Directory 應用程式 Proxy，而非 VPN 的使用。


## <a name="information-security"></a>資訊安全性

客戶可能會設定可協助保護高價值的公司資產這些選用的服務。 

服務 | 描述
--- | ---
資料修復  | 在裝置上的主要資料夾中儲存的資訊備份至 OneDrive for Business。Microsoft 受管理的桌上型電腦不負責含有 OneDrive for Business 不同步的資料。 
Windows 資訊保護 |    對於需要高的資訊安全性層級的公司，我們建議使用[Windows 資訊保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)及[Azure 資訊保護。](https://www.microsoft.com/cloud-platform/azure-information-protection)。 

