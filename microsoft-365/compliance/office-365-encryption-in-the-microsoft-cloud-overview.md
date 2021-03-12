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
description: 在本文中，請閱讀用於將客戶資料安全地保存在 Microsoft 雲端中的各種加密形式的概述。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 20236e67432ad5bc7e837b91590387355022ccb5
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727574"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft Cloud 中的加密

Microsoft enterprise cloud services 中的客戶資料受到數種技術和程式的保護，包含各種形式的加密。 本檔中的 (客戶資料包含 Exchange Online 信箱內容、電子郵件內文、行事曆專案，以及電子郵件附件的內容，如果適用，則為商務用 Skype 內容) ，SharePoint 線上網站內容和儲存在網站中的檔案，以及上傳至商務用 OneDrive 或商務用 Skype 的檔案。 ) Microsoft 會跨其產品和服務使用多個加密方法、通訊協定和密碼，以協助提供一種安全路徑，讓客戶資料透過我們的雲端服務，並協助保護儲存在雲端服務中的客戶資料的機密性。 Microsoft 使用一些最強大且最安全的加密通訊協定，以防範未經授權的存取客戶資料的屏障。 適當的金鑰管理也是加密最佳作法的重要要素，而 Microsoft 可確保所有的 Microsoft 受管理加密金鑰都受到適當的保護。

儲存在 Microsoft enterprise 雲端服務中的客戶資料，是使用一或多個加密形式來保護。 加密原則和其強制執行的 (驗證會獨立于多個協力廠商審計員進行驗證，而這些審核的報告可在 [服務信任入口網站](https://aka.ms/stp)上使用。 ) 

Microsoft 提供的服務端技術會在靜止和傳輸過程中加密客戶資料。 例如，針對 rest 的客戶資料，Microsoft Azure 使用 [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) 和 [DM Crypt](https://en.wikipedia.org/wiki/Dm-crypt)，而 microsoft 365 使用 BitLocker、 [Azure Storage Service 加密](https://docs.microsoft.com/azure/)、 [分散式金鑰管理員](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-secures-email-secrets) (DKM) 及 Microsoft 365 服務加密。 針對 transport 中的客戶資料，Azure，Office 365，Microsoft 商務版支援，Microsoft Dynamics 365，Microsoft Power BI，Visual Studio Team Services 使用業界標準的安全傳輸通訊協定，例如網際網路通訊協定安全性 (IPsec) 和傳輸層安全性 (TLS) ，在 Microsoft 資料中心之間和使用者裝置與 Microsoft 資料中心之間。

除了 Microsoft 所提供之密碼安全性的基準層級之外，我們的雲端服務也包含您可以管理的密碼編譯選項。 例如，您可以對其 Azure 虛擬機器 (Vm) 及其使用者之間的流量啟用加密。 透過 [Azure 虛擬網路](https://azure.microsoft.com/services/virtual-network/)，您可以使用業界標準的 IPsec 通訊協定來加密您公司 VPN 閘道和 Azure 之間的流量。 您也可以加密虛擬網路上的 Vm 之間的流量。 此外， [新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md) 可讓您將加密郵件傳送給任何人。

遵循公開金鑰基礎結構運作安全性標準（即 [Microsoft 安全性原則](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)的元件），microsoft 會使用 Windows 作業系統中包含憑證和驗證機制的加密功能。 這些機制包括使用符合美國政府之 [聯邦資訊處理標準](https://csrc.nist.gov/publications/PubsFIPS.html) 的密碼模組， (FIPS) 140-2 standard。 您可以使用 [ [加密模組驗證計畫] CMVP](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search)，搜尋 Microsoft 的相關 NIST 憑證號碼。

> 記若要以資源的身分存取 Microsoft 安全性原則，您必須使用您的公司或學校帳戶登入。 如果您尚無訂閱， [可以註冊免費試用版](https://servicetrust.microsoft.com/Home/TrialSubscriptions)。

FIPS 140-2 是一種標準，專門用來驗證實施密碼編譯的產品模組，而不是使用這些模組的產品。 在服務內實施的加密模組，可作為符合雜湊強度、金鑰管理等需求的認證。 用來保護 Microsoft 雲端服務之機密性、完整性或可用性的加密模組和密碼，符合 FIPS 140-2 standard。

Microsoft 會透過每個新版本的 Windows 作業系統，證明雲端服務中所用的基礎加密模組：

- Azure 和 Azure 美國政府版
- Dynamics 365 和 Dynamics 365 美國政府
- Office 365、Office 365 美國政府和 Office 365 美國政府國防版

靜態客戶資料的加密是由多種服務端技術所提供，包括 BitLocker、DKM、Azure 儲存服務加密，以及 Exchange Online 中的服務加密、商務用 Skype、商務 OneDrive，以及 SharePoint 線上。 Office 365 服務加密包含一個選項，可使用儲存在 Azure Key Vault 中客戶管理的加密金鑰。 此客戶管理的金鑰選項（稱為「 [客戶金鑰](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)」）適用于 Exchange online、SharePoint 線上、商務用 Skype 和商務 OneDrive。

針對傳輸中的客戶資料，所有的 Office 365 伺服器都會使用 TLS 與用戶端電腦協商安全會話，以保護客戶資料。 例如，Office 365 會將安全的會話與商務用 Skype、Outlook 和 Outlook 網頁版、行動用戶端和網頁瀏覽器協商。

 (所有客戶對向的伺服器預設會與 TLS 1.2 協商。 ) 

## <a name="related-links"></a>相關連結

- [Azure 中的加密](office-365-azure-encryption.md)
- [BitLocker 與 Distributed Key Manager (DKM) 的加密](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 服務加密](office-365-service-encryption.md)
- [商務用 Skype、商務用 OneDrive、SharePoint 線上和 Exchange Online 的 Office 365 加密](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [傳輸中資料的加密](office-365-encryption-for-data-in-transit.md)
- [客戶管理加密功能](office-365-customer-managed-encryption-features.md)
- [加密風險與防護](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 中的加密](office-365-encryption-in-microsoft-dynamics-365.md)
