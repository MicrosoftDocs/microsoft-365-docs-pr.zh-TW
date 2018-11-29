---
title: Microsoft 受管理電腦中的安全性
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866744"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中的安全性

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

藉由使用許多 Microsoft 技術，我們可以確保 Microsoft 受管理的桌上型電腦裝置是安全與 Microsoft 受管理的桌上型電腦安全性 ops 小組可防止、 偵測、 及回應進階的威脅。不允許使用協力廠商安全性產品、 應用程式] 及服務。Microsoft 將會套用標準原則比較基準以確保裝置、 身分識別、 網路與公司資料安全，並且保護。

下列各節中記載的安全性保護這些類別：

- [資料安全性](#data-security)-我們要如何確保您的資料會儲存並符合的 Azure 安全性位置需求
- [裝置安全性](#device-security)– 我們要如何確保 Microsoft 受管理的桌上型電腦裝置的安全
- [身分識別安全性](#identity-security)– 我們要如何確保現代工作週年中的使用者不會危害
- [網路安全性](#network-security)– 我們要如何確保安全存取公司資源
- [資訊安全性](#information-security)– 我們要如何確保公司資料是安全
- [使用權限的帳戶存取](#privileged-account-access)-我們如何限制存取

## <a name="data-security"></a>資料安全性

從您的租用戶傳輸的資料會儲存在 Azure SQL 資料庫裝載於 USA Microsoft 租用戶中。將資料儲存，並符合需求 Azure 安全性位置。 

如需詳細資訊，請參閱[Microsoft Azure 安全性](https://www.microsoft.com/TrustCenter/Security/azure-security)。

這份清單摘要說明 Microsoft 和您的租用戶之間傳輸資料的類型。 

- 從 Microsoft 租用戶
    - 群組名稱
    - 安全性原則設定
    - 裝置訂單
    - 使用者帳戶 （msadmin、 mstest Microsoft 受管理的 Desktop_soc_ro、 Microsoft 受管理的 Desktop_wdgsoc）
    - E5 授權指派給上述 4 位使用者
    - Windows 更新更新鈴響的原則
    - 未來，進一步功能將會被開發以供其他類型的組態內容包括應用程式、 原則與設定的張貼。
- 從您的租用戶給 Microsoft
    - 裝置更新、 使用量及可靠性資料
    - 應用程式部署及可靠性資料
    - 更新與安全性原則部署資料
    - 指派給裝置的使用者



## <a name="device-security"></a>裝置安全性

若要防止安全性缺口，務必確定所有的 Microsoft 受管理的桌上型電腦裝置正常且安全。同樣也請務必以確保我們可以偵測狀況不良的裝置和盡早降低風險。

下表列出以確保 Microsoft 受管理的桌上型電腦裝置信任、 正常且為安全提供的服務。

服務 | 描述
--- | ---
防毒 | 我們將確認：<br>安裝及設定 Windows 防禦者 AV<br>Windows 防禦者 AV 定義為最新
完整的磁碟區加密 |    Windows BitLocker 是 Microsoft 受管理的桌上型電腦裝置資料加密解決方案。<br><br>後組織 onboarded 服務，裝置會使用與內建信任平台模組 (TPM) Windows BitLocker 防止本機資料未經授權的存取裝置時睡眠模式] 或 [關閉加密。 
監視 |    Windows 防禦者進階威脅保護 (Windows 防禦者 ATP) 是監視解決方案的 Microsoft 受管理的桌上型電腦的所有裝置的安全性威脅。Windows 防禦者 ATP 可讓企業客戶偵測、 調查及應對其公司網路中的進階威脅。如需詳細資訊，請參閱[Windows 防禦者進階威脅保護。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
軟體更新 |  Microsoft 可確保 Microsoft 受管理的桌上型電腦裝置一律安全的最新的安全性更新、 Windows 及 Office、 使用 Windows Update for Business。
[復原] |  公司資料儲存於 OneDrive for business 與可以輕鬆地還原 Microsoft 受管理的桌上型電腦裝置。如需詳細資訊，請參閱[OneDrive for Business。](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US) 



## <a name="identity-security"></a>身分識別安全性

身分識別與存取管理會保護的公司資產及重要商業資料。Azure Active Directory (Azure AD) 提供在雲端身分識別服務並啟用雲端式驗證可確保僅信任的個人可以從 Microsoft 受管理的桌上型電腦的裝置存取公司資源。

服務 | 描述
--- | ---
企業等級驗證提供者 |  使用 Microsoft azure AD Premium 版本提供高可用性服務主控的全域分散式資料中心。服務處理的驗證十億做從多個 200 萬個作用中使用者每日，讓您達 99.9 %sla。
生物特徵驗證 |  Windows Hello 可讓使用者使用其圖像或 PIN 進行更困難忘記或竊取密碼登入。這可能需要額外的工作來設定。如需詳細資訊，請參閱[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
多重要素驗證 | Azure 的多重要素驗證避免未經授權的存取內部部署及雲端應用程式以提供額外的層級的驗證使用行動電話，也為自助密碼重設。 
標準使用者權限 |  若要保護系統並讓它更安全，使用者會指派標準使用者權限。這會指定為 Windows 自動駕駛儀上的現成體驗的一部分。



## <a name="network-security"></a>網路安全性

客戶負責網路安全性。 

服務 | 描述
--- | ---
VPN | 客戶擁有其 VPN 基礎結構，以確保有限的公司資源可以公開於內部網路之外。<br><br>最低需求： Microsoft 受管理的桌上型電腦需要 Windows 10 相容和支援 VPN 解決方案。如果您的組織需要 VPN 解決方案，它必須支援 Windows 10 會封裝並可透過 Intune 部署。如需詳細資訊，請洽詢您軟體發行者。<br><br>建議：<br>Microsoft 建議無法輕鬆地部署到 Intune 至推入 VPN 設定檔的現代 VPN 解決方案。這提供一律在、 順暢、 可靠且安全的方法來存取公司網路。如需詳細資訊，請參閱 VPN settings in Intune。<br>-粗 VPN 用戶端或舊版 VPN 用戶端，並不建議 microsoft 時使用 Microsoft 受管理的桌上型電腦它可能會影響使用者環境。<br>Microsoft 建議的外寄的網頁流量前往直接網際網路而不必經由 VPN，以免發生任何效能問題。<br>-理想狀況下，Microsoft 建議 Azure Active Directory 應用程式 Proxy，而非 VPN 的使用。


## <a name="information-security"></a>資訊安全性

客戶可能會設定可協助保護高價值的公司資產這些選用的服務。 

服務 | 描述
--- | ---
條件式存取 |    只有當裝置符合時允許存取公司資源和服務。
資料修復  | 在裝置上的主要資料夾中儲存的資訊備份至 OneDrive for Bbusiness。Microsoft 受管理的桌上型電腦不負責含有 OneDrive for Business 不同步的資料。 
Windows 資訊保護 |    對於需要高的資訊安全性層級的公司，我們建議使用[Windows 資訊保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)及[Azure 資訊保護。](https://www.microsoft.com/cloud-platform/azure-information-protection)。 


## <a name="privileged-account-access"></a>權限的帳戶存取權

今天，我們限制存取權的客戶 MSAdmin 認證及應用程式透過這些機制：

- **運算子**-Microsoft 整-次-員工位於美國順利完成定期背景與安全性檢查。
- 根據 Microsoft 所設定的標準受保護**運算子 identity** –。如需詳細資訊，請參閱[Managing 使用者身分識別和 microsoft 安全存取](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)。 
- **記錄**以及客戶的租用戶中的運算子環境中執行。記錄資料和個人資訊都會保留在各自的環境中並不會周遊環境。 

