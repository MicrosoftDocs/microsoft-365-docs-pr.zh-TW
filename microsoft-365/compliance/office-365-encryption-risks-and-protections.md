---
title: Office 365 加密風險與防護
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
description: 摘要： 了解 Microsoft Office 365 中的資料復原。
ms.openlocfilehash: 113fd60f8b585e4f59245f00b0f238cb2020b57d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38690219"
---
# <a name="encryption-risks-and-protections"></a>加密風險與防護

Microsoft 會依照控制項和合規性架構著重在 Office 365 服務和客戶資料的風險。 Microsoft 會實作技術與程序為基礎的方法 （稱為控制項） 一大組，以降低這些風險。 識別、 評估和減輕風險透過控制項是連續的處理程序。 

在我們的雲端服務，例如設施、 網路、 伺服器、 應用程式、 使用者 （例如 Microsoft 系統管理員） 和資料的各種層內的控制項的實作表單的深度防禦策略。 這項策略的重點是，以防止在相同或類似的風險案例的不同層級實作許多不同的控制項。 此多層次的方式提供保全的保護，以防控制項因為某些原因而失敗。

下面列出一些風險案例及減輕其目前可使用的加密技術。 這些案例是在許多情況下也減輕透過 Office 365 中實作其他控制項。

| 加密技術 | 服務 | 金鑰管理 | 風險案例 | 值 |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、 SharePoint Online 和商務用 Skype | Microsoft | 磁碟或 Office 365 中的伺服器是遭竊，或不正確地回收。 | BitLocker 提供保全的方法，以防止因為被竊或不正確地回收硬體 （伺服器/磁碟） 的資料遺失。 |
| 服務加密 | SharePoint Online、 商務用 Skype 和 OneDrive for Business;Exchange Online （在藍圖） | Microsoft | 內部或外部的駭客嘗試存取個別的檔案/資料為 blob。 | 加密的資料無法解密而不需要存取索引鍵。 可協助降低風險的駭客存取資料。 |
| 客戶金鑰 | SharePoint Online、 商務用 OneDrive、 Exchange Online 和商務用 Skype | 客戶 | N/A （這項功能設計為符合性功能; 不為任何風險的緩和措施）。 | 可協助客戶符合內部的規定和合規性責任，且可讓您離開 Office 365 服務，並撤銷 Microsoft 的資料的存取權 |
| Office 365 與用戶端之間的 TLS | Exchange Online、 SharePoint Online、 商務用 OneDrive、 Skype for Business、 小組及 Yammer | Microsoft 客戶 | 在中間人或其他攻擊到網際網路上點選 [Office 365 和用戶端電腦之間的資料流程。 | 這個實作 Microsoft 和客戶提供值，並可確保資料完整性，因為其 Office 365 和用戶端之間流動。 |
| Microsoft 資料中心之間的 TLS | Exchange Online、 SharePoint Online、 商務用 OneDrive 與 Skype for Business | Microsoft | 攔截或點選 [客戶資料流，位於不同 Microsoft 資料中心的 Office 365 伺服器之間的其他攻擊。 | 這個實作是另一個方法來保護資料免於 Microsoft 資料中心之間的攻擊。 |
| Azure 版權管理 （包含在 Office 365 或 Azure 資訊保護） | Exchange Online、 SharePoint Online 和商務用 OneDrive | 客戶 | 資料可分成手中不應有資料的存取權的人員。 | Azure 資訊保護使用 Azure RMS 其提供給客戶的值，以協助保護檔案和跨多個裝置的電子郵件使用加密、 identity 及授權原則。 Azure RMS 提供值給其中所有電子郵件來自 Office 365 符合特定準則 （亦即，到特定的地址的所有電子郵件） 可以自動加密之前有取得傳送給其他收件者的客戶。 |
| S/MIME | Exchange Online | 客戶 | 電子郵件可分為手中不是預定的收件者的人員。 | S/MIME 提供值給客戶，藉由以確保只可以直接收件者的電子郵件由解密使用 S/MIME 加密的電子郵件。 |
| Office 365 郵件加密 | Exchange Online、 SharePoint Online | 客戶 | 電子郵件，包括受保護的附件，落在手中的人員內或外 Office 365 不是預定收件者的電子郵件。 | OME 提供值給客戶其中所有電子郵件來自 Office 365 符合特定準則 （亦即，到特定的地址的所有電子郵件） 會自動加密之前他們取得傳送至另一個內部或外部收件者。 |
| 與夥伴組織的 SMTP TLS | Exchange Online | 客戶 | 電子郵件是透過從 Office 365 租用戶到另一個合作夥伴組織的傳輸中攔截或其他攻擊攔截。 | 此案例，提供值給客戶，他們可以傳送/接收其 Office 365 租用戶和加密的 SMTP 通道內的其合作夥伴的電子郵件組織之間的所有電子郵件。 |

## <a name="encryption-technologies-available-in-office-365-multi-tenant-environments"></a>在 Office 365 多承租人環境中使用的加密技術

| 加密技術 | 藉由實作 | 金鑰交換演算法和強度 | 金鑰管理 * | FIPS 140-2 驗證 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | 使用 AES 128 位元 + | 使用 AES 外部索引鍵儲存在機密安全和 Exchange 伺服器的登錄。 密碼安全是需要高階提高權限與核准機制來存取安全存放庫。 可以要求與核准只能透過使用稱為 Lockbox 內部工具存取。 AES 外部索引鍵也會儲存在信任的平台模組中的伺服器中。 48 位數數字密碼是儲存在 Active Directory，並受加密箱。 | 是的對於伺服器，使用 AES 256 位元 * * |
|  | SharePoint Online | 使用 AES 256 位元 | 使用 AES 外部索引鍵會儲存在安全密碼。 密碼安全是需要高階提高權限與核准機制來存取安全存放庫。 可以要求與核准只能透過使用稱為 Lockbox 內部工具存取。 AES 外部索引鍵也會儲存在信任的平台模組中的伺服器中。 48 位數數字密碼是儲存在 Active Directory，並受加密箱。 | 是 |
|  | 商務用 Skype | 使用 AES 256 位元 | 使用 AES 外部索引鍵會儲存在安全密碼。 密碼安全是需要高階提高權限與核准機制來存取安全存放庫。 可以要求與核准只能透過使用稱為 Lockbox 內部工具存取。 AES 外部索引鍵也會儲存在信任的平台模組中的伺服器中。 48 位數數字密碼是儲存在 Active Directory，並受加密箱。 | 是 |
| 服務加密 | SharePoint Online | 使用 AES 256 位元 | 用來加密 blob 的機碼會儲存在 SharePoint Online 內容資料庫。 SharePoint Online 內容資料庫受到資料庫的存取控制及靜態加密。 加密是 Azure SQL 資料庫中使用 TDE 來執行。 這些密碼會在服務層級的 SharePoint Online 中，不在租用戶層級。 （有時稱為主索引鍵） 這些密碼會儲存在不同的安全存放庫，以稱為索引鍵存放區。 TDE 提供安全性，請參閱作用中的資料庫和資料庫的備份和交易記錄檔的其餘部分。 當客戶提供的選用的索引鍵時，客戶金鑰會儲存在 Azure Key Vault 和服務使用金鑰來加密租用戶金鑰，是用來加密網站金鑰，然後用來加密檔案層級索引鍵。 基本上，客戶提供按鍵時，被引進新的金鑰階層。 | 是 |
|  | 商務用 Skype | 使用 AES 256 位元 | 每一筆資料是使用不同的隨機產生的 256 位元金鑰來加密。 加密金鑰會儲存在相對應的中繼資料 XML 檔這也以每個會議的主要金鑰加密。 每次會議，主索引鍵是也隨機產生一次。 | 是 |
|  | Exchange Online | 使用 AES 256 位元 | 使用資料加密原則使用加密金鑰控制由 Microsoft （位於藍圖） 或由客戶 （使用客戶金鑰） 時進行加密每個信箱。 | 是 |
| Office 365 和用戶端/協力廠商之間的 TLS | Exchange Online | [支援多種加密套件的隨機 TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 | 是，當使用搭配 256 位元加密強度的 TLS 1.2 |
|  | SharePoint Online | 使用 AES 256 的 TLS 1.2 <br> <br> [商務用 OneDrive 和 SharePoint Online 中的資料加密](https://technet.microsoft.com/library/dn905447.aspx) (英文) | SharePoint Online 的 TLS 憑證 (*。 sharepoint.com) 是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> SharePoint Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 | 是 |
|  | 商務用 Skype | [TLS 的 SIP 通訊和 PSOM 資料共用工作階段](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | 商務用 Skype 的 TLS 憑證 (*。 lync.com) 是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> 商務用 Skype 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
|  | Microsoft Teams | 使用 AES 256 的 TLS 1.2 <br> <br> [常見問題集有關 Microsoft Teams – 系統管理說明](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft Teams （teams.microsoft.com、 edge.skype.com） 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> Microsoft Teams 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
| Microsoft 資料中心之間的 TLS | 所有 Office 365 服務 | 使用 AES 256 的 TLS 1.2 <br> <br> 安全即時傳輸通訊協定 (SRTP) | Microsoft 會使用內部 managed 和部署的憑證授權單位 Microsoft 資料中心之間的伺服器對伺服器通訊。 | 是 |
| Azure 版權管理 （包含在 Office 365 或 Azure 資訊保護） | Exchange Online | 支援[密碼編譯模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、 更新及增強 RMS 密碼編譯實作。 它支援 RSA 2048 的簽章和加密，以及 sha-256 雜湊簽章中。 | [由 Microsoft 管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支援[密碼編譯模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、 更新及增強 RMS 密碼編譯實作。 它支援 RSA 2048 簽章和加密，以及 sha-256 針對簽章。 | [由 Microsoft 管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，這是預設設定;或 <br> <br> 這是 Microsoft 受管理的機碼的替代客戶管理。 具有受 IT 管理 Azure 訂用帳戶的組織可以使用 BYOK，並記錄其用法，無須額外收費。 如需詳細資訊，請參閱[實作攜帶您自己的金鑰](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 在此組態中，Thales Hsm 用來保護您的金鑰。 如需詳細資訊，請參閱[Thales Hsm 和 Azure RMS](https://www.thales-esecurity.com/msrms/cloud)。 | 是 |
| S/MIME | Exchange Online | 密碼編譯訊息語法標準 1.5 (PKCS #7) | 客戶管理公開金鑰基礎結構部署而定。 金鑰管理由客戶、 執行和 Microsoft 永遠不會有權存取私密金鑰用於簽署及解密。 | 是，當設定為 3DES 或 AES256 的外寄郵件加密 |
| Office 365 郵件加密 | Exchange Online | Azure RMS ([密碼編譯模式 2](https://technet.microsoft.com/library/dn569290.aspx) -RSA 2048 簽章和加密和簽章的 sha-256) 相同 | 使用 Azure 資訊保護為其加密基礎結構。 使用的加密方法取決於您在哪裡取得用來加密及解密郵件的 RMS 金鑰。 | 是 |
| 與夥伴組織的 SMTP TLS | Exchange Online | 使用 AES 256 的 TLS 1.2 | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 | 是，當使用搭配 256 位元加密強度的 TLS 1.2 |

**美國資料中心; 是參照此表格中的 TLS 憑證非美國資料中心也使用 2048年位元 SHA256RSA 憑證。*

***大部分的伺服器，在 Exchange Online 的多租用戶環境中已部署使用 BitLocker 的 AES 256 位元加密。使用 AES 128 位元伺服器已被淘汰。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>在政府雲端社群環境中使用的加密技術

| 加密技術 | 藉由實作 | 金鑰交換演算法和強度 | 金鑰管理 * | FIPS 140-2 驗證 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | 使用 AES 256 位元 | 使用 AES 外部索引鍵儲存在機密安全和 Exchange 伺服器的登錄。 密碼安全是需要高階提高權限與核准機制來存取安全存放庫。 可以要求與核准只能透過使用稱為 Lockbox 內部工具存取。 AES 外部索引鍵也會儲存在信任的平台模組中的伺服器中。 48 位數數字密碼是儲存在 Active Directory，並受加密箱。 | 是 |
|  | SharePoint Online | 使用 AES 256 位元 | 使用 AES 外部索引鍵會儲存在安全密碼。 密碼安全是需要高階提高權限與核准機制來存取安全存放庫。 可以要求與核准只能透過使用稱為 Lockbox 內部工具存取。 AES 外部索引鍵也會儲存在信任的平台模組中的伺服器中。 48 位數數字密碼是儲存在 Active Directory，並受加密箱。 | 是 |
|  | 商務用 Skype | 使用 AES 256 位元 | 使用 AES 外部索引鍵會儲存在安全密碼。 密碼安全是需要高階提高權限與核准機制來存取安全存放庫。 可以要求與核准只能透過使用稱為 Lockbox 內部工具存取。 AES 外部索引鍵也會儲存在信任的平台模組中的伺服器中。 48 位數數字密碼是儲存在 Active Directory，並受加密箱。 | 是 |
| 服務加密 | SharePoint Online | 使用 AES 256 位元 | 用來加密 blob 的機碼會儲存在 SharePoint Online 內容資料庫。 SharePoint Online 內容資料庫受到資料庫的存取控制及靜態加密。 加密是 Azure SQL 資料庫中使用 TDE 來執行。 這些密碼會在服務層級的 SharePoint Online 中，不在租用戶層級。 （有時稱為主索引鍵） 這些密碼會儲存在不同的安全存放庫，以稱為索引鍵存放區。 TDE 提供安全性，請參閱作用中的資料庫和資料庫的備份和交易記錄檔的其餘部分。 當客戶提供的選用的索引鍵時，客戶金鑰會儲存在 Azure Key Vault 和服務使用金鑰來加密租用戶金鑰，是用來加密網站金鑰，然後用來加密檔案層級索引鍵。 基本上，客戶提供按鍵時，被引進新的金鑰階層。 | 是 |
|  | 商務用 Skype | 使用 AES 256 位元 | 每一筆資料是使用不同的隨機產生的 256 位元金鑰來加密。 加密金鑰會儲存在相對應的中繼資料 XML 檔這也以每個會議的主要金鑰加密。 每次會議，主索引鍵是也隨機產生一次。 | 是 |
|  | Exchange Online | 使用 AES 256 位元 | 使用資料加密原則使用加密金鑰控制由 Microsoft 或客戶 （使用客戶金鑰） 時進行加密每個信箱。 | 是 |
| Office 365 和用戶端/協力廠商之間的 TLS | Exchange Online | [支援多種加密套件的隨機 TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 | 是，當使用搭配 256 位元加密強度的 TLS 1.2 |
|  | SharePoint Online | 使用 AES 256 的 TLS 1.2 | SharePoint Online 的 TLS 憑證 (*。 sharepoint.com) 是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> SharePoint Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 | 是 |
|  | 商務用 Skype | TLS 的 SIP 通訊和 PSOM 資料共用工作階段 | 商務用 Skype 的 TLS 憑證 (*。 lync.com) 是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> 商務用 Skype 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
|  | Microsoft Teams | [常見問題集有關 Microsoft Teams – 系統管理說明](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft Teams （teams.microsoft.com; edge.skype.com） 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> Microsoft Teams 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
| Microsoft 資料中心之間的 TLS | Exchange Online、 SharePoint Online、 商務用 Skype | 使用 AES 256 的 TLS 1.2 | Microsoft 會使用內部 managed 和部署的憑證授權單位 Microsoft 資料中心之間的伺服器對伺服器通訊。 | 是 |
|  |  | 安全即時傳輸通訊協定 (SRTP) |  |  |
| Azure 版權管理服務 | Exchange Online | 支援[密碼編譯模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、 更新及增強 RMS 密碼編譯實作。 它支援 RSA 2048 的簽章和加密，以及 sha-256 雜湊簽章中。 | [由 Microsoft 管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支援[密碼編譯模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、 更新及增強 RMS 密碼編譯實作。 它支援 RSA 2048 的簽章和加密，以及 sha-256 雜湊簽章中。 | [由 Microsoft 管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，這是預設設定;或 <br> <br> 客戶管理 (也稱為 BYOK)，也就是 Microsoft 受管理的機碼的替代方案。 具有受 IT 管理 Azure 訂用帳戶的組織可以使用 BYOK，並記錄其用法，無須額外收費。 如需詳細資訊，請參閱[實作攜帶您自己的金鑰](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 <br> <br> 在 BYOK 案例中，Thales Hsm 用來保護您的金鑰。 如需詳細資訊，請參閱[Thales Hsm 和 Azure RMS](https://www.thales-esecurity.com/msrms/cloud)。 | 是 |
| S/MIME | Exchange Online | 密碼編譯訊息語法標準 1.5 (PKCS #7) | 公開金鑰基礎結構部署而定。 | 是，當設定為 3DES 或 AES 256 的外寄郵件加密。 |
| Office 365 郵件加密 | Exchange Online | Azure RMS ([密碼編譯模式 2](https://technet.microsoft.com/library/dn569290.aspx) -簽章和加密的 RSA 2048 和 sha-256 針對在簽章的雜湊) 相同 | 使用 Azure RMS 作為其加密基礎結構。 使用的加密方法取決於您在哪裡取得用來加密及解密郵件的 RMS 金鑰。 <br> <br> 如果您使用 Microsoft Azure RMS 來取得金鑰時，會使用密碼編譯模式 2。 如果您使用 Active Directory (AD) RMS 來取得金鑰，則會使用密碼編譯模式 1 或密碼編譯模式 2。 使用的方法取決於內部部署 AD RMS 部署。 密碼編譯模式 1 是原始的 AD RMS 密碼編譯實作。 它支援 RSA 1024 個簽章和加密和簽章可支援 sha-1。 此模式會繼續所有目前 RMS，但不包括使用 Hsm BYOK 組態版本受到支援。 | 是 |
| 與夥伴組織的 SMTP TLS | Exchange Online | 使用 AES 256 的 TLS 1.2 | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 <br> <br> Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 sha1RSA 憑證。 <br> <br> 請注意，基於安全性考量，我們的憑證會隨時變更。 | 是 |

**美國資料中心; 是參照此表格中的 TLS 憑證非美國資料中心也使用 2048年位元 SHA256RSA 憑證。*