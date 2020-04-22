---
title: 客戶管理的加密功能
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
ms.collection: Strat_O365_Enterprise
description: 摘要：瞭解 Microsoft 365 中的資料恢復能力。
ms.openlocfilehash: 365cde7137247e20bb4fd2b57039057398deafd5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637339"
---
# <a name="customer-managed-encryption-features"></a>客戶管理的加密功能

除了 microsoft 所管理的 Microsoft 365 中的加密技術之外，Microsoft 365 也可搭配其他可管理及設定的加密技術，例如：

- [Azure 版權管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [安全多用途網際網路郵件擴充](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365 郵件加密](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [與夥伴組織的安全郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

如需這些技術的詳細資訊，請參閱[Microsoft 365 服務說明](https://technet.microsoft.com/library/office-365-service-descriptions.aspx)。

## <a name="azure-rights-management"></a>Azure 版權管理

[Azure 版權管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)（azure RMS）是[azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)所使用的保護技術。 它會使用加密、身分識別和授權原則，協助保護您的檔案和電子郵件跨越多個平臺和裝置（電話、平板電腦和電腦）。 您組織內部和外部的資訊都能受到保護，因為保護仍會保留資料。 Azure RMS 提供所有檔案類型的持續保護、保護檔案的任何地方、支援企業對企業共同作業，以及廣泛的 Windows 和非 Windows 裝置。 Azure RMS 保護也可以擴充[資料遺失防護（DLP）原則](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。 如需哪些應用程式和服務可以從 Azure 資訊保護使用 Azure Rights Management 服務的詳細資訊，請參閱[應用程式如何支援 Azure Rights management 服務](https://docs.microsoft.com/information-protection/understand-explore/applications-support)。

Azure RMS 已與 Microsoft 365 整合，可供所有客戶使用。 若要將 Microsoft 365 設定為使用 Azure RMS，請參閱[CONFIGURE IRM to Use Azure Rights management 和設定資訊版權管理（IRM）的 SharePoint 系統管理中心](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx)。 如果您使用內部部署的 Active Directory （AD） RMS 伺服器，您也可以[將 IRM 設定為使用內部部署 AD RMS 伺服器](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)，但我們強烈建議您將 IRM[遷移至 Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) ，以使用與其他組織的安全共同作業等新功能。

當您使用 Azure RMS 保護客戶資料時，Azure RMS 會使用2048位的 RSA 非對稱金鑰與 SHA-256 雜湊演算法，以進行資料加密的完整性。 Office 檔和電子郵件的對稱金鑰為 AES 128 位（使用 PKCS # 7 顯示的 CBC 模式）。 針對每個由 Azure RMS 保護的檔或電子郵件，Azure RMS 會建立單一 AES 金鑰（"content key"），該機碼會內嵌在檔中，並繼續透過檔的版本。 內容金鑰會以組織的 RSA 金鑰（「Azure 資訊保護租使用者金鑰」）加以保護，作為檔中的原則的一部分，而且該原則也會由檔作者簽署。 此租使用者金鑰組于組織所保護的所有檔和電子郵件而言是通用的，如果組織使用客戶管理的承租人機碼，則只有 Azure 資訊保護系統管理員可以變更此金鑰。 如需 Azure RMS 使用之密碼控制的詳細資訊，請參閱[AZURE rms 的運作方式？在 [蓋子](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)] 底下。

在預設的 Azure RMS 實施中，Microsoft 會產生及管理每個租使用者特有的根機碼。 客戶可以使用稱為「[帶您自己的金鑰」（BYOK）](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)的金鑰管理方法，在 azure RMS 中管理其根機碼的生命週期，讓您在內部部署 hsm （硬體安全性模組）中產生您的金鑰，並在傳輸至 MICROSOFT 的 FIPS 140-2 Level 2 驗證的 hsm 後，繼續控制此機碼。 不會將存取根機碼給任何人員，因為這些機碼無法從 Hsm 中匯出或解壓縮。 此外，您還可以存取接近即時記錄檔，顯示所有存取根機碼的時間。 如需詳細資訊，請參閱[記錄和分析 Azure 版權管理的使用](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)方式。

Azure 版權管理可協助減少威脅，例如，網路攻絲、中間人攻擊、資料竊取，以及組織共用原則的意外違反。 同時，未獲授權的使用者無法使用該資料，而不具有適當許可權的任何 unwarranted 存取任何客戶資料，也會降低該資料在故意或不知不覺中遭受的危險，並提供資料遺失防護功能。 如果使用做為 Azure 資訊保護的一部分，Azure RMS 也會提供資料分類及標籤功能、標記內容、檔存取追蹤和存取撤銷功能。 若要深入瞭解這些功能，請參閱 azure 資訊[保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)、 [azure 資訊保護部署藍圖](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)，以及[azure 資訊保護的快速入門教程](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)。

## <a name="secure-multipurpose-internet-mail-extension"></a>安全多用途網際網路郵件擴充

安全/多用途網際網路郵件擴充（S/MIME）是一種公開金鑰加密和 MIME 資料數位簽署的標準。 S/MIME 定義于 Rfc 3369、3370、3850、3851和其他。 它可讓使用者加密電子郵件，並以數位方式簽署電子郵件。 使用 S/MIME 加密的電子郵件只能透過電子郵件的收件者使用其私密金鑰（只供該收件者使用）進行解密。 如此一來，電子郵件無法由非電子郵件收件者的任何人解密。

[Microsoft 支援 S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)。 公用憑證會發佈到客戶的內部部署 Active Directory，並儲存在可複製到 Microsoft 365 租使用者的屬性中。 對應到公開金鑰的私密金鑰會保留在內部部署中，而且決不會傳送至 Office 365。 使用者可以使用 Outlook、Outlook 網頁版和 Exchange ActiveSync 用戶端，在組織中的兩個使用者之間撰寫、加密、解密、讀取和數位簽署電子郵件。 如需詳細資訊，請參閱[now S/MIME encryption In Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)。

## <a name="office-365-message-encryption"></a>Office 365 郵件加密

以[Azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)（AIP）為基礎的[Office 365 郵件加密](https://products.office.com/exchange/office-365-message-encryption)（OME）可讓您將加密和許可權保護的郵件傳送給任何人。 OME 可減少諸如電線攻絲和中間人攻擊等威脅，以及其他威脅，例如未經授權的使用者沒有適當許可權的 unwarranted 存取權。 我們為您提供的投資，為您提供以 Azure 資訊保護為基礎的更簡單、更具視覺安全性的電子郵件經驗。 您可以保護從 Microsoft 365 傳送給組織內部或外部任何人的郵件。 使用任何身分識別（包括 Azure Active Directory、Microsoft 帳戶和 Google IDs），可以跨一組不同的郵件客戶程式來查看這些郵件。 如需組織如何使用加密郵件的詳細資訊，請參閱[Office 365 Message Encryption](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A)。

## <a name="transport-layer-security"></a>傳輸層安全性   

如果您想要確保與夥伴之間的通訊安全，您可以使用輸入和輸出連接器，以提供安全性和郵件完整性。 您可以使用憑證設定每個連接器上的強制輸入和輸出 TLS。 使用加密的 SMTP 通道可防止透過中間人攻擊竊取資料。 如需詳細資訊，請參閱[Exchange Online 如何使用 TLS 來保護電子郵件](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F)連線。

## <a name="domain-keys-identified-mail"></a>識別郵件的網域金鑰

Exchange Online Protection （EOP）和 Exchange Online 支援網域機碼的輸入驗證，識別出郵件（DKIM）郵件。 DKIM 是一種方法，用來驗證郵件是由其來源的網域所傳送，且沒有其他人冒充。 它會將電子郵件訊息傳送給負責傳送電子郵件的組織，而且也是較大的電子郵件加密模式的一部分。 如需此範例之三個部分的詳細資訊，請參閱：

- [設定 SPF 以協助防止電子欺騙](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [使用 DKIM 來驗證從您的自訂網域傳送的輸出電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [使用 DMARC 驗證電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
