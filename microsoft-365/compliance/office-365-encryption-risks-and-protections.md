---
title: 加密風險與防護
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: 在本文中，您將瞭解 Office 365 的風險及可用於保護的加密技術。
ms.openlocfilehash: a9abf3dcc6cbd1bdb237c6ccecbbbaa4d42fda2b
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769183"
---
# <a name="encryption-risks-and-protections"></a>加密風險與防護

Microsoft 遵循控制和規範架構，側重于 Microsoft 365 服務和客戶資料的風險。 Microsoft 會執行一組大量的技術和程式型方法， (稱為控制項) 來緩解這些風險。 透過控制措施，對風險進行識別、評估與緩解，是一個持續的處理方式。 

在我們的雲端服務層級（如設施、網路、伺服器、應用程式、使用者 (，例如 Microsoft 系統管理員) 和資料表單中的控制項的實施，都是防禦深度策略。 此策略的關鍵是，許多不同的控制項都是在不同的層級實施，以防範相同或類似的風險案例。 這種多層次的方法會提供失效安全保護，以防控制項因某些原因而失敗。

下列是一些風險案例及目前可用的加密技術，下列所列是加以緩解。 在許多情況下，您也可以透過 Office 365 中所執行的其他控制項來緩解這些案例。

| 加密技術 | 服務 | 金鑰管理 | 風險案例 | 值 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、SharePoint 線上和商務用 Skype | 微軟 | 磁片或伺服器失竊或錯誤地回收。 | BitLocker 提供一種防安全的方法，避免因失竊或錯誤回收的硬體 (伺服器/磁片) 而遺失資料。 |
| 服務加密 | SharePoint 線上、商務用 Skype 和商務 OneDrive;Exchange Online (on 藍圖)  | 微軟 | 內部或外部駭客會嘗試以 blob 存取個別的檔案/資料。 | 在沒有存取機碼的情況下，無法解密加密的資料。 協助緩解駭客存取資料的風險。 |
| 客戶金鑰 | SharePoint 線上、商務用 OneDrive、Exchange Online 和商務用 Skype | 客戶 | N/A (此功能是設計為符合性功能;不是任何風險的緩解。 )  | 協助客戶滿足內部的法規和合規性義務，以及留下服務的能力，並撤銷 Microsoft 的資料存取權 |
| Microsoft 365 和用戶端之間的 TLS | Exchange Online、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype、小組和 Yammer | Microsoft，客戶 | 中間人或其他攻擊，以點擊透過網際網路的 Microsoft 365 和用戶端電腦之間的資料流程。 | 這項實施會為 Microsoft 和客戶提供價值，並確保在 Microsoft 365 和用戶端之間流動的資料完整性。 |
| Microsoft 資料中心之間的 TLS | Exchange Online、SharePoint 線上、商務 OneDrive 和商務用 Skype | 微軟 | 中間人或其他攻擊，以點擊位於不同 Microsoft 資料中心的 Microsoft 365 伺服器之間的客戶資料流程程。 | 此實現是另一種方法，可防止 Microsoft 資料中心之間的攻擊。 |
| Microsoft 365 或 Azure 資訊保護中包含的 azure Rights Management ()  | Exchange Online、SharePoint 線上和商務 OneDrive | 客戶 | 資料是指不應該存取資料之人員的手。 | Azure 資訊保護使用 Azure RMS 為客戶提供價值的方式是使用加密、身分識別和授權原則，以協助保護跨多個裝置的檔案和電子郵件。 Azure RMS 為客戶提供了一些價值，其中來自 Microsoft 365 的所有電子郵件都符合特定準則 (也就是說，所有電子郵件到特定位址) 可以在傳送給另一位收件者之前自動加密。 |
| S/MIME | Exchange Online | 客戶 | 電子郵件落入不是預定收件者的人員。 | S/MIME 會保證使用 S/MIME 加密的電子郵件只能由電子郵件的直接收件者解密，為客戶提供價值。 |
| Office 365 郵件加密 | Exchange Online，SharePoint 線上 | 客戶 | 電子郵件（包含受保護的附件）是由 Microsoft 365 （不是電子郵件的預定收件者）內部或外部的任何人員所手。 | OME 為客戶提供一些價值，其中來自 Microsoft 365 的所有電子郵件都符合特定準則 (也就是說，所有電子郵件到特定位址) 都會在傳送給另一個內部或外部收件者之前自動加密。 |
| 具有夥伴組織的 SMTP TLS | Exchange Online | 客戶 | 電子郵件會透過中間人或其他攻擊來截獲，但從 Microsoft 365 租使用者傳輸到另一個夥伴組織。 | 此案例為客戶提供價值，讓他們可以在加密的 SMTP 通道內傳送/接收其 Microsoft 365 租使用者和其夥伴的電子郵件組織之間的所有電子郵件。 |

## <a name="encryption-technologies-available-in-multi-tenant-environments"></a>多租使用者環境中可用的加密技術

| 加密技術 | 實施者 | 金鑰交換演算法和強度 | 金鑰管理 * | 驗證 FIPS 140-2 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位 | 在 Exchange 伺服器的登錄中，會以機密安全且在登錄中儲存 AES 外部金鑰。 機密安全是一種安全的存放庫，需要高層級的仰角和核准才能存取。 只有使用稱為「密碼箱」的內部工具，才可要求和核准存取。 AES 外部金鑰也會儲存在伺服器中的 [受信任的平臺] 模組中。 48位的數值密碼儲存在 Active Directory 中，並由密碼箱保護。 | 是，適用于使用 AES 256-bit * * 的伺服器 |
|  | SharePoint Online | AES 256 位 | AES 外部金鑰儲存在機密安全中。 機密安全是一種安全的存放庫，需要高層級的仰角和核准才能存取。 只有使用稱為「密碼箱」的內部工具，才可要求和核准存取。 AES 外部金鑰也會儲存在伺服器中的 [受信任的平臺] 模組中。 48位的數值密碼儲存在 Active Directory 中，並由密碼箱保護。 | 是 |
|  | 商務用 Skype | AES 256 位 | AES 外部金鑰儲存在機密安全中。 機密安全是一種安全的存放庫，需要高層級的仰角和核准才能存取。 只有使用稱為「密碼箱」的內部工具，才可要求和核准存取。 AES 外部金鑰也會儲存在伺服器中的 [受信任的平臺] 模組中。 48位的數值密碼儲存在 Active Directory 中，並由密碼箱保護。 | 是 |
| 服務加密 | SharePoint Online | AES 256 位 | 用來加密 blob 的金鑰會儲存在 SharePoint 線上內容資料庫中。 SharePoint 線上內容資料庫受到資料庫存取控制及靜態加密的保護。 使用 Azure SQL Database 中的 TDE 執行加密。 這些機密是線上 SharePoint 的服務層級，而不是租使用者層級。 這些機密 (有時候稱為主要金鑰) 儲存在個別的安全存放庫中，稱為機碼存放區。 TDE 為使用中的資料庫與資料庫備份和交易記錄，提供了靜止的安全性。 當客戶提供選用的金鑰時，客戶金鑰會儲存在 Azure Key Vault 中，而且服務會使用金鑰來加密租使用者金鑰（用來加密網站機碼，然後用來加密檔層級金鑰）。 實質上，當客戶提供金鑰時，會引入新的主要階層。 | 是 |
|  | 商務用 Skype | AES 256 位 | 每個資料片段都會使用不同的隨機產生的256位金鑰加密。 加密金鑰儲存在對應的中繼資料 XML 檔中，該檔案也是由每個會議的主要金鑰所加密。 主要金鑰也會隨機產生每個會議一次。 | 是 |
|  | Exchange Online | AES 256 位 | 每個信箱都是以使用 Microsoft (在藍圖) 或客戶 () 時使用的加密金鑰的資料加密原則加密。 | 是 |
| Microsoft 365 與用戶端/合作夥伴之間的 TLS | Exchange Online | [支援多個密碼套件的機會 TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA1RSA 憑證。 | 是，當使用具有256位密碼強度的 TLS 1.2 時 |
|  | SharePoint Online | TLS 1.2 與 AES 256 <br> <br> [商務用 OneDrive 和 SharePoint Online 中的資料加密](https://technet.microsoft.com/library/dn905447.aspx) (英文) | SharePoint Online ( sharepoint.com) 的 TLS 憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> SharePoint Online 的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA1RSA 憑證。 | 是 |
|  | 商務用 Skype | [適用于 SIP 通訊和 PSOM 資料共用會話的 TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | 商務用 Skype ( 的 TLS 憑證) 是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> 商務用 Skype 的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 | 是 |
|  | Microsoft Teams | TLS 1.2 與 AES 256 <br> <br> [有關 Microsoft 團隊的常見問題–系統管理說明](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft 小組的 TLS 憑證 (teams.microsoft.com，edge.skype.com) 是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> Microsoft 小組的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 | 是 |
| Microsoft 資料中心之間的 TLS | 所有 Microsoft 365 服務 | TLS 1.2 與 AES 256 <br> <br> 安全即時傳輸通訊協定 (SRTP)  | Microsoft 使用內部管理及部署的憑證授權單位單位，以用於 Microsoft 資料中心之間的伺服器對伺服器通訊。 | 是 |
| Microsoft 365 或 Azure 資訊保護中包含的 azure Rights Management ()  | Exchange Online | 支援 [加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、更新及增強型 RMS 密碼編譯實施。 它支援簽章和加密的 RSA 2048，以及簽署中雜湊的 SHA-256。 | [由 Microsoft 所管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支援 [加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、更新及增強型 RMS 密碼編譯實施。 它支援簽章和加密的 RSA 2048，以及簽章的 SHA-256。 | [由 Microsoft 管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，這是預設設定;或 <br> <br> 客戶管理，這是 Microsoft 管理金鑰的替代方法。 具有 IT 管理之 Azure 訂閱的組織可使用 BYOK 並記錄其使用狀況，而不需額外收費。 如需詳細資訊，請參閱 [執行攜帶您自己的金鑰](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 在此設定中，nCipher Hsm 是用來保護您的金鑰。 如需詳細資訊，請參閱 [NCipher hsm 和 AZURE RMS](https://www.thales-esecurity.com/msrms/cloud)。 | 是 |
| S/MIME | Exchange Online | 加密郵件語法標準 1.5 (PKCS #7)  | 取決於已部署的客戶管理公開金鑰基礎結構。 主要管理是由客戶執行，且 Microsoft 永不可以存取用來簽署和解密的私密金鑰。 | 是，當設定成使用3DES 或 AES256 加密外寄郵件時 |
| Office 365 郵件加密 | Exchange Online | 與 Azure RMS 相同 ([加密模式 2](https://technet.microsoft.com/library/dn569290.aspx) -RSA 2048 用於簽章和加密，並 SHA-256 簽章)  | 使用 Azure 資訊保護作為其加密基礎結構。 使用的加密方法取決於您在哪裡取得用來加密及解密郵件的 RMS 金鑰。 | 是 |
| 具有夥伴組織的 SMTP TLS | Exchange Online | TLS 1.2 與 AES 256 | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA1RSA 憑證。 | 是，當使用具有256位密碼強度的 TLS 1.2 時 |

**此表格中所參照的 TLS 憑證是針對 US 資料中心;非 US 資料中心也會使用2048位 SHA256RSA 憑證。*

***Exchange Online 多租使用者環境中的大部分伺服器都已部署了 BitLocker 的 AES 256 位加密。使用 AES 128 位的伺服器會逐步淘汰。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>政府雲端群組環境中可用的加密技術

| 加密技術 | 實施者 | 金鑰交換演算法和強度 | 金鑰管理 * | 驗證 FIPS 140-2 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位 | 在 Exchange 伺服器的登錄中，會以機密安全且在登錄中儲存 AES 外部金鑰。 機密安全是一種安全的存放庫，需要高層級的仰角和核准才能存取。 只有使用稱為「密碼箱」的內部工具，才可要求和核准存取。 AES 外部金鑰也會儲存在伺服器中的 [受信任的平臺] 模組中。 48位的數值密碼儲存在 Active Directory 中，並由密碼箱保護。 | 是 |
|  | SharePoint Online | AES 256 位 | AES 外部金鑰儲存在機密安全中。 機密安全是一種安全的存放庫，需要高層級的仰角和核准才能存取。 只有使用稱為「密碼箱」的內部工具，才可要求和核准存取。 AES 外部金鑰也會儲存在伺服器中的 [受信任的平臺] 模組中。 48位的數值密碼儲存在 Active Directory 中，並由密碼箱保護。 | 是 |
|  | 商務用 Skype | AES 256 位 | AES 外部金鑰儲存在機密安全中。 機密安全是一種安全的存放庫，需要高層級的仰角和核准才能存取。 只有使用稱為「密碼箱」的內部工具，才可要求和核准存取。 AES 外部金鑰也會儲存在伺服器中的 [受信任的平臺] 模組中。 48位的數值密碼儲存在 Active Directory 中，並由密碼箱保護。 | 是 |
| 服務加密 | SharePoint Online | AES 256 位 | 用來加密 blob 的金鑰會儲存在 SharePoint 線上內容資料庫中。 SharePoint 線上內容資料庫受到資料庫存取控制及靜態加密的保護。 使用 Azure SQL Database 中的 TDE 執行加密。 這些機密是線上 SharePoint 的服務層級，而不是租使用者層級。 這些機密 (有時候稱為主要金鑰) 儲存在個別的安全存放庫中，稱為機碼存放區。 TDE 為使用中的資料庫與資料庫備份和交易記錄，提供了靜止的安全性。 當客戶提供選用的金鑰時，客戶金鑰會儲存在 Azure Key Vault 中，而且服務會使用金鑰來加密租使用者金鑰（用來加密網站機碼，然後用來加密檔層級金鑰）。 實質上，當客戶提供金鑰時，會引入新的主要階層。 | 是 |
|  | 商務用 Skype | AES 256 位 | 每個資料片段都會使用不同的隨機產生的256位金鑰加密。 加密金鑰儲存在對應的中繼資料 XML 檔中，該檔案也是由每個會議的主要金鑰所加密。 主要金鑰也會隨機產生每個會議一次。 | 是 |
|  | Exchange Online | AES 256 位 | 每個信箱都是以使用 Microsoft 所控制的加密金鑰或客戶 () 使用客戶金鑰的資料加密原則進行加密。 | 是 |
| Microsoft 365 與用戶端/合作夥伴之間的 TLS | Exchange Online | [支援多個密碼套件的機會 TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA1RSA 憑證。 | 是，當使用具有256位密碼強度的 TLS 1.2 時 |
|  | SharePoint Online | TLS 1.2 與 AES 256 | SharePoint Online ( sharepoint.com) 的 TLS 憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> SharePoint Online 的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA1RSA 憑證。 | 是 |
|  | 商務用 Skype | 適用于 SIP 通訊和 PSOM 資料共用會話的 TLS | 商務用 Skype ( 的 TLS 憑證) 是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> 商務用 Skype 的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 | 是 |
|  | Microsoft Teams | [有關 Microsoft 團隊的常見問題–系統管理說明](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft 小組 (的 TLS 憑證，teams.microsoft.comedge.skype.com) 是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> Microsoft 小組的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 | 是 |
| Microsoft 資料中心之間的 TLS | Exchange Online，SharePoint 線上，商務用 Skype | TLS 1.2 與 AES 256 | Microsoft 使用內部管理及部署的憑證授權單位單位，以用於 Microsoft 資料中心之間的伺服器對伺服器通訊。 | 是 |
|  |  | 安全即時傳輸通訊協定 (SRTP)  |  |  |
| Azure Rights Management 服務 | Exchange Online | 支援 [加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、更新及增強型 RMS 密碼編譯實施。 它支援簽章和加密的 RSA 2048，以及簽署中雜湊的 SHA-256。 | [由 Microsoft 所管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支援 [加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、更新及增強型 RMS 密碼編譯實施。 它支援簽章和加密的 RSA 2048，以及簽署中雜湊的 SHA-256。 | [由 Microsoft 管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，這是預設設定;或 <br> <br> 客戶管理的 (也稱為 BYOK) ，也就是 Microsoft 管理的金鑰的替代方法。 具有 IT 管理之 Azure 訂閱的組織可使用 BYOK 並記錄其使用狀況，而不需額外收費。 如需詳細資訊，請參閱 [執行攜帶您自己的金鑰](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 <br> <br> 在 BYOK 案例中，nCipher 的 Hsm 是用來保護您的金鑰。 如需詳細資訊，請參閱 [NCipher hsm 和 AZURE RMS](https://www.thales-esecurity.com/msrms/cloud)。 | 是 |
| S/MIME | Exchange Online | 加密郵件語法標準 1.5 (PKCS #7)  | 取決於已部署的公用金鑰基礎結構。 | 是，當設定成使用3DES 或 AES-256 加密外寄郵件時。 |
| Office 365 郵件加密 | Exchange Online | 與 Azure RMS 相同 ([加密模式 2](https://technet.microsoft.com/library/dn569290.aspx) -RSA 2048 用於簽章和加密，以及簽章中的雜湊 SHA-256)  | 使用 Azure RMS 作為其加密基礎結構。 使用的加密方法取決於您在哪裡取得用來加密及解密郵件的 RMS 金鑰。 <br> <br> 如果您使用 Microsoft Azure RMS 取得機碼，則會使用加密模式2。 如果您使用 Active Directory (AD) RMS 來取得金鑰，則會使用密碼編譯模式 1 或密碼編譯模式 2。 使用的方法取決於內部部署 AD RMS 部署。 密碼編譯模式 1 是原始的 AD RMS 密碼編譯實作。 它支援簽章和加密的 RSA 1024，並支援簽署的 SHA-1。 除了使用 Hsm 的 BYOK 設定之外，所有目前的 RMS 版本仍可繼續支援此模式。 | 是 |
| 具有夥伴組織的 SMTP TLS | Exchange Online | TLS 1.2 與 AES 256 | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 SHA256RSA 憑證。 <br> <br> Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust Root 所發行的2048位 sha1RSA 憑證。 <br> <br> 請注意，基於安全性考量，我們的憑證會隨時變更。 | 是 |

**此表格中所參照的 TLS 憑證是針對 US 資料中心;非 US 資料中心也會使用2048位 SHA256RSA 憑證。*
