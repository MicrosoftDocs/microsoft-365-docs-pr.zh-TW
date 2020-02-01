---
title: Microsoft Cloud 中的加密
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
description: Microsoft Cloud 中的加密的概觀。
ms.openlocfilehash: 11cce463cf953bd9f8ea0df61e3fe97b356608eb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601820"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft Cloud 中的加密

Microsoft 的 enterprise cloud 服務內的客戶資料會受到各種不同的技術與程序，包括各種不同表單的加密。 (此文件中的 office 365 客戶資料包括 Exchange Online 信箱內容 (電子郵件內文、 行事曆項目和電子郵件附件的內容和如果適用的話，Skype for Business 內容)、 SharePoint Online 網站內容及檔案儲存在內網站和檔案上傳至 OneDrive for Business 或商務用 Skype。）Microsoft 會使用多個的加密方法、 通訊協定及 cipher 跨其產品和服務協助提供通過我們雲端服務時，並協助保護內儲存的客戶資料的機密性的客戶資料的安全路徑我們的雲端服務。 Microsoft 會使用一些可用來提供障礙對抗未經授權存取客戶資料的嚴格，最安全的加密通訊協定。 適當的金鑰管理也是不可或缺的要素加密最佳作法，以及 Microsoft 運作來確保所有的 Microsoft 管理加密金鑰的正確安全。

無論客戶設定儲存在 Microsoft 的 enterprise cloud 服務內的客戶資料受到使用加密的一或多個表單。 （多個協力廠商稽核員，分別檢定我們密碼編譯的原則和其強制執行的驗證和這些稽核的報告可在[服務信任入口網站](https://aka.ms/stp)）。

Microsoft 會提供客戶資料靜止和傳輸中加密的服務端技術。 例如，靜態的客戶資料，Microsoft Azure 使用[BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview)與[DM 窖](https://en.wikipedia.org/wiki/Dm-crypt)，和 Microsoft Office 365 使用 BitLocker、 [Azure 儲存體服務加密](https://azure.microsoft.com/documentation/articles/storage-service-encryption/)、[分散式金鑰管理員](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376)(DKM) 和 Office 365 服務加密。 傳輸中的客戶資料、 Azure、 Office 365、 Microsoft 商業支援、 Microsoft Dynamics 365、 Microsoft Power BI 和 Visual Studio Team Services 使用業界標準安全傳輸通訊協定，例如網際網路通訊協定安全性 (IPsec) 及Microsoft 資料中心之間，以及使用者裝置和 Microsoft 資料中心之間的傳輸層安全性 (TLS)。

除了 Microsoft 所提供的密碼編譯安全的基準層級，我們的雲端服務也會包含您可以管理的其他密碼編譯選項。 例如，您可以啟用其 Azure 的虛擬機器 (Vm) 和其使用者之間的流量加密。 與[Azure 虛擬網路](https://azure.microsoft.com/services/virtual-network/)中，您可以使用的業界標準 IPsec 通訊協定來加密您公司的 VPN 閘道與 Azure 也筆電位於您的虛擬網路的 Vm 之間的流量。 此外，此外，[新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)讓您將加密的郵件傳送給任何人。

根據公用金鑰基礎結構運作安全性標準，也就是元件的[Microsoft 安全性原則](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)，Microsoft 會採用 Windows 作業系統的憑證和驗證機制，其中包含符合美國政府的[聯邦資訊處理標準](https://csrc.nist.gov/publications/PubsFIPS.html)(FIPS) 140-2 標準的密碼編譯模組使用所含的密碼編譯功能。 （如 Microsoft 相關 NIST 憑證數字，請參閱https://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [附註]若要存取 Microsoft 安全性原則，當作資源，您必須使用登入您的公司或學校帳戶。 如果您不需要訂閱尚未，[您可以註冊免費試用版](https://servicetrust.microsoft.com/Home/TrialSubscriptions)。

FIPS 140-2 是專為驗證實作密碼編譯，而不是使用這些產品的產品模組設計的標準。 實作某項服務中的密碼編譯模組可以通過認證，會議雜湊強度、 金鑰管理和類似的需求。 隨時來保護機密性、 完整性或在 Microsoft 雲端服務中的資料的可用性會採用密碼編譯功能的模組和使用的 cipher 符合 FIPS 140-2 標準。

Microsoft 需要認證使用我們的雲端服務與每個新的版本的 Windows 作業系統中的基礎密碼編譯模組：

- Azure 和 Azure US Government
- Dynamics 365 和 Dynamics 365 美國政府
- Office 365、Office 365 美國政府和 Office 365 美國政府國防版

靜態的 Office 365 客戶資料的加密是由提供多個服務端技術，包括 BitLocker、 DKM、 Azure 儲存體服務加密，以及服務加密在 Exchange Online、 商務用 Skype、 OneDrive for Business 和 SharePoint線上。 Office 365 服務加密包括使用儲存在 Azure 金鑰保存庫中的客戶管理加密金鑰] 選項。 客戶管理金鑰，稱為[Office 365 客戶金鑰](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697)，則使用此選項的 Exchange Online、 SharePoint Online、 商務用 Skype 和商務用 OneDrive。

傳輸中的客戶資料，針對 Office 365 的所有伺服器都交涉 TLS 根據預設，使用與用戶端機器，保護客戶資料的安全工作階段。  這適用於用戶端，例如 Skype for Business、 Outlook 和 Outlook 網頁、 行動用戶端和網頁瀏覽器上的使用任何裝置上的通訊協定。

（所有客戶對向伺服器設為 TLS 1.2 都交涉依預設，但我們也支援交涉下的較低的標準，如有必要）。

## <a name="related-links"></a>相關連結

- [Azure 中的加密](office-365-azure-encryption.md)
- [BitLocker 與 Distributed Key Manager (DKM) 的加密](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 服務加密](office-365-service-encryption.md)
- [商務用 Skype、 OneDrive for Business、 SharePoint Online 和 Exchange Online 的 office 365 加密](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [傳輸中資料的加密](office-365-encryption-for-data-in-transit.md)
- [客戶管理加密功能](office-365-customer-managed-encryption-features.md)
- [加密風險與防護](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 中的加密](office-365-encryption-in-microsoft-dynamics-365.md)