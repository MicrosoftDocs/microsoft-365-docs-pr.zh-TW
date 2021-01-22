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
ms.custom:
- seo-marvel-mar2020
description: 本文將說明您可以在 Microsoft 365 中管理和設定之加密技術。
ms.openlocfilehash: bb6f9fedf915fd261266a9ed5d0c561d1352ea09
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921553"
---
# <a name="customer-managed-encryption-features"></a>客戶管理的加密功能

除了 Microsoft 管理的 Microsoft 365 中的加密技術，Microsoft 365 也能夠使用您可以管理及設定的其他加密技術，例如：

- [Azure 版權管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [安全多重用途網際網路郵件延伸模組](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365 郵件加密](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [與合作夥伴組織保護郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

有關這些技術的其他資訊，請參閱 Microsoft [365 服務描述](https://technet.microsoft.com/library/office-365-service-descriptions.aspx)。

## <a name="azure-rights-management"></a>Azure 版權管理

[Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (Azure RMS) 是 Azure 資訊保護所使用的 [保護技術](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)。 它使用加密、身分識別及授權策略，協助保護您的檔案和電子郵件在多個平臺和裝置上，包括手機、平板電腦和電腦。 組織內外的資訊都可以受到保護，因為資料中會保留保護。 Azure RMS 提供所有檔案類型的持續性保護、隨時隨地保護檔案、支援企業與企業共同合作，以及各種 Windows 和非 Windows 裝置。 Azure RMS 保護也可以增強 DLP ([資料外) 防護](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。 有關哪些應用程式和服務可以使用 Azure 資訊保護的 Azure Rights Management Service 之詳細資訊，請參閱應用程式如何[支援 Azure Rights Management Service。](https://docs.microsoft.com/information-protection/understand-explore/applications-support)

Azure RMS 已與 Microsoft 365 整合，且可供所有客戶使用。 若要將 Microsoft 365 設定為使用 Azure RMS，請參閱設定 IRM 以使用 [Azure Rights Management，以及設定 SharePoint](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx)系統管理中心的資訊版權管理 (IRM) 。 如果您操作內部部署 Active Directory (AD) RMS 伺服器，那麼您也可以將 IRM 設定為使用內部部署 [AD RMS](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)伺服器，但我們強烈建議您遷移至 [Azure RMS，](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) 以使用新功能，例如與其他組織的安全共同合作。

當您使用 Azure RMS 保護客戶資料時，Azure RMS 會使用 2048 位 RSA 非對稱金鑰與 SHA-256 雜湊演算法，以完整性加密資料。 Office 檔和電子郵件的對稱金鑰是 AES 128 位。 Azure RMS 會針對受 Azure RMS 保護的每一份檔或電子郵件，建立單一 AES 金鑰 (「內容金鑰」) ，而該金鑰會內嵌在檔中，並持續透過檔的版本。 內容金鑰受組織的 RSA 金鑰 ("Azure 資訊保護租使用者金鑰") 保護，做為檔中策略的一部分，且該政策也由檔作者簽署。 此租使用者金鑰是受組織 Azure RMS 保護的所有檔和電子郵件的常見功能，且只有在組織使用客戶管理的租使用者金鑰時，Azure 資訊保護系統管理員才能變更此金鑰。 有關 Azure RMS 使用的密碼加密控制項之詳細資訊，請參閱 [Azure RMS 如何工作？在進場下](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)。

在預設的 Azure RMS 執行中，Microsoft 會產生和管理每個租使用者唯一的根金鑰。 客戶可以使用稱為攜帶您自己的金鑰 [ (BYOK) ](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) 的金鑰管理方法，在 Azure RMS 與 Azure 金鑰庫服務中管理其根金鑰的生命週期，此方法可讓您在內部部署 HSMS (硬體安全性模組) 中產生金鑰，並可在轉換至 Microsoft 的 FIPS 140-2 層級 2 驗證 HSMS 之後，掌握此金鑰的控制權。 系統不會提供根鍵存取權給任何人員，因為無法從保護根金鑰的 HSMS 匯出或解壓縮金鑰。 此外，您也可以隨時存取顯示所有根鍵存取的近即時記錄。 詳細資訊請參閱記錄和分析[Azure Rights Management Usage。](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)

Azure Rights Management 可協助減輕威脅，例如點線、男士在中間攻擊、資料竊取，以及不小心違反組織共用原則。 同時，未獲授權的未經授權使用者對客戶資料進行傳輸或休息的無預警存取，會透過遵循該資料之後的政策防止，進而降低資料在明知或未知時落在錯誤人員手中的風險，並提供資料外遺失防護功能。 如果做為 Azure 資訊保護的一部分，Azure RMS 也會提供資料分類和標籤功能、內容標記、檔存取追蹤和存取撤銷功能。 若要深入瞭解這些功能，請參閱什麼是 Azure[資訊保護、Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)[資訊保護部署](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)藍圖，以及 Azure 資訊保護[的快速入門教學課程](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)。

## <a name="secure-multipurpose-internet-mail-extension"></a>安全多重用途網際網路郵件延伸模組

安全/多重用途的網際網路郵件延伸模組 (S/MIME) 是公開金鑰加密和 MIME 資料數位簽章的標準。 S/MIME 定義于 RFC 3369、3370、3850、3851 等。 此功能可讓使用者加密電子郵件，並數位簽署電子郵件。 使用 S/MIME 加密的電子郵件，只能由電子郵件收件者使用其私密金鑰解密，而該金鑰只能供該收件者使用。 因此，電子郵件無法由電子郵件收件者外的任何一人解密。

[Microsoft 支援 S/MIME。](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx) 公用憑證會發佈至客戶內部部署 Active Directory，並儲存在可複製到 Microsoft 365 租使用者的屬性中。 對應到公開金鑰的私密金鑰會保留在內部部署，而且不會傳送至 Office 365。 使用者可以使用 Outlook、Outlook 網頁和 Exchange ActiveSync 用戶端，在組織中兩個使用者之間撰寫、加密、解密、讀取及數位簽署電子郵件。 詳細資訊請參閱 Office [365 中的 S/MIME](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)加密。

## <a name="office-365-message-encryption"></a>Office 365 郵件加密

[Office 365](https://products.office.com/exchange/office-365-message-encryption) 郵件加密 (Azure 資訊保護) 上所建的 [Office](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) 365 郵件加密 (AIP) 可讓您傳送加密且受許可權保護的郵件給任何人。 OME 可減輕威脅，例如點線和進行中間攻擊，及其他威脅，例如未經授權的使用者沒有適當許可權而無威脅地存取資料。 我們做出投資，在 Azure 資訊保護功能下，為您提供簡單、更直覺且安全的電子郵件體驗。 您可以保護從 Microsoft 365 中將郵件寄給組織內外的任何人。 您可以使用任何身分識別在各種不同的郵件用戶端集上查看這些郵件，包括 Azure Active Directory、Microsoft 帳戶和 Google 身分識別。 有關貴組織如何使用加密郵件詳細資訊，請參閱 [Office 365 郵件加密](https://docs.microsoft.com/microsoft-365/compliance/ome)。

## <a name="transport-layer-security"></a>傳輸層安全性   

如果您想要確保與合作夥伴的安全通訊，您可以使用輸入和輸出連接器來提供安全性和訊息完整性。 您可以在每個連接器上，使用憑證設定強制輸入和輸出 TLS。 使用加密的 SMTP 通道可防止資料透過男士在中間受到攻擊而遭竊。 詳細資訊請參閱 Exchange [Online 如何使用 TLS 保護電子郵件連線](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)。

## <a name="domain-keys-identified-mail"></a>網域金鑰識別郵件

Exchange Online Protection (EOP) 和 Exchange Online 支援網域金鑰識別郵件的輸入驗證 (DKIM) 郵件。 DKIM 是一種驗證郵件是否來自郵件來源網域，且不是由他人詐騙的方法。 它會將電子郵件訊息與負責傳送的電子郵件組織建立關係，且屬於電子郵件加密的一部分。 有關此方式的三個部分之詳細資訊，請參閱：

- [設定 SPF 以協助防止詐騙 ](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [使用 DKIM 驗證從您自訂網域傳送的輸出電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [使用 DMARC 驗證電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
