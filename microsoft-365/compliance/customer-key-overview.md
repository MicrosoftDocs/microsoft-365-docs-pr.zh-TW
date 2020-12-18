---
title: 客戶金鑰服務加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: 在本文中，您將瞭解如何使用 Microsoft 365 中的客戶金鑰來處理服務加密。
ms.openlocfilehash: 0008d145db81d5d6c4eb9ab89ca194b7e426d2e4
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709525"
---
# <a name="service-encryption-with-customer-key"></a>客戶金鑰服務加密

Microsoft 365 提供使用 BitLocker 和分散式金鑰管理員 (DKM) 所啟用的基準、磁片區層級加密。 Microsoft 365 在應用層級為您的內容提供額外的加密層級。 此內容包含 Exchange Online 中的資料、商務用 Skype、SharePoint 線上、商務 OneDrive，以及小組檔案。 這個新增的加密層稱為「服務加密」。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>服務加密、BitLocker 及客戶金鑰共同運作的方式

服務加密可確保在服務層級加密靜止的內容。 在 **Microsoft 365 服務中，您的資料會永遠以靜態方式加密，並 BitLocker 和 DKM**。 如需詳細資訊，請參閱《安全性、隱私權和規範資訊》，以及 [Exchange Online 如何保護您的電子郵件機密](exchange-online-secures-email-secrets.md)。 客戶金鑰提供額外的保護，以防止未經授權的系統或人員查看資料，以及在 Microsoft 資料中心中補充 BitLocker 磁片加密。 服務加密不是為了防止 Microsoft 人員存取客戶資料。 主要用途是協助客戶滿足控制根機碼的管制或合規性義務。 客戶會明確授權 O365 服務使用加密金鑰，以提供增值的雲端服務，例如 eDiscovery、反惡意程式碼、反垃圾郵件、搜尋索引等等。

客戶金鑰是以服務加密為基礎，可讓您提供和控制加密金鑰。 然後，Microsoft 365 會使用這些金鑰來加密您的資料，如 [線上服務條款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products.aspx)所述。 客戶金鑰可協助您符合法規遵從性義務，因為您可以控制 Microsoft 365 用來加密及解密資料的加密金鑰。
  
客戶金鑰可提升您的組織符合規範需求的能力，以指定與雲端服務提供者的重要安排。 使用客戶金鑰，您可以在應用層級為您的 Microsoft 365 資料同時提供及控制根加密金鑰。 因此，您會練習控制組織的按鍵。 如果您決定要退出服務，請撤銷您組織的根機碼的存取權。 針對所有 Microsoft 365 服務，撤銷機碼存取權的第一步是資料刪除的路徑。 透過撤銷對機碼的存取權，無法將資料從服務中讀取。

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>客戶金鑰會在 Office 365 中加密靜態資料

使用您提供的金鑰，客戶金鑰加密：

- SharePoint 線上、商務及小組檔案的 OneDrive。
- 上傳至商務 OneDrive 的檔案。
- Exchange Online 信箱內容，包括電子郵件內文內容、行事曆專案，以及電子郵件附件中的內容。
- 商務用 Skype 中的文字交談。

目前我們並不會為 Skype 會議廣播和 Skype 會議內容上傳的加密金鑰提供客戶控制權。 相反地，此內容會與 Office 365 中的所有其他內容一起加密。

### <a name="customer-key-with-hybrid-deployments"></a>具有混合式部署的客戶金鑰

客戶金鑰只會加密雲端中靜態的資料。 客戶金鑰不會用來保護您的內部部署信箱和檔案。 您可以使用另一種方法（例如 BitLocker）來加密您的內部部署資料。

## <a name="about-the-data-encryption-policy-dep"></a>關於資料加密原則 (DEP) 

資料加密原則定義加密階層，使用您提供的每個金鑰以及 Microsoft 所保護的可用性金鑰來加密資料。 您可以使用 PowerShell Cmdlet 來建立 DEPs，這些 Cmdlet 會不同于每個服務，並指派這些 DEPs 以加密應用程式資料。 例如：

**Exchange Online 和商務用 Skype** 每個租使用者最多可以建立 50 DEPs。 您可以將 DEPs 關聯到 Azure Key Vault 中的客戶機碼，然後將 DEPs 指派給個別信箱。 當您為信箱指派 DEP 時：

- 信箱已標記為要移動信箱。 根據此處所述的 Microsoft 365 中的優先順序，在 [microsoft 365 服務中移動要求](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)。

- 移動信箱時，會進行加密。 允許信箱的72小時使用新的 DEP 進行加密。 如果信箱在您指派 DEP 的時間之後，等待72小時之後未加密，請與 Microsoft 聯繫。

稍後，您可以依照 [管理 Office 365 的客戶金鑰](customer-key-manage.md)中所述的方式，重新整理 DEP 或指派不同的 dep 至信箱。 每個信箱都必須有適當的授權，才可指派 DEP。 如需授權的詳細資訊，請參閱 [設定客戶金鑰之前](customer-key-set-up.md#before-you-set-up-customer-key)。

**SharePoint 線上、商務及小組檔案的 OneDrive** 如果您使用的是多地理位置功能，您的組織可以為每個地理位置建立多個 DEP。 您可以針對每個地理位置使用不同的客戶金鑰。 如果您不是使用多地理位置功能，則每個承租人只能建立一個 DEP。 當您指派 DEP 時，加密會自動開始，但可能需要一些時間才能完成。 請參閱 [設定客戶金鑰](customer-key-set-up.md)中的詳細資料。

## <a name="leaving-the-service"></a>離開服務

客戶金鑰可協助您在離開 Microsoft 365 服務時撤銷您的金鑰，以協助您履行法規遵從性義務。 當您在離開服務時撤銷您的金鑰時，會刪除可用性機碼，以加密刪除您的資料。 加密刪除可降低資料 remanence 的風險，這對於迎接安全性和合規性義務很重要。 如需有關資料清除程式和金鑰吊銷的詳細資訊，請參閱 [撤銷您的金鑰，然後啟動資料清除路徑處理](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)程式。

### <a name="encryption-ciphers-used-by-customer-key"></a>客戶金鑰使用的加密密碼

客戶金鑰使用各種加密密碼來加密金鑰，如下圖所示。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>加密密碼，用來加密 Exchange Online 和商務用 Skype 的金鑰

![Exchange Online 客戶機碼的加密密碼](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>用來加密 SharePoint 線上、商務 OneDrive 與小組檔案的金鑰的加密密碼

![SharePoint Online 客戶機碼的加密密碼](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相關文章

- [設定客戶金鑰](customer-key-set-up.md)

- [管理客戶金鑰](customer-key-manage.md)

- [滾動或旋轉客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)

- [深入瞭解可用性金鑰](customer-key-availability-key-understand.md)

- [客戶加密箱](customer-lockbox-requests.md)

- [服務加密](office-365-service-encryption.md)
