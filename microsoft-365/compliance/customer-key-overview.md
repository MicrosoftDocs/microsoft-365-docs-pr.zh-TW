---
title: 使用 Office 365 中的客戶金鑰服務加密
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
description: 使用客戶金鑰，您可以控制您組織的加密金鑰，然後設定 [要用來加密存放在 Microsoft 資料中心中的 Office 365。
ms.openlocfilehash: ee62065542ea50091d73362dd8d05f2e4e7dc337
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804771"
---
# <a name="service-encryption-with-customer-key-in-office-365"></a>使用 Office 365 中的客戶金鑰服務加密

Office 365 提供基準，啟用透過 BitLocker 與分散式金鑰管理員 (DKM) 的磁碟區層級加密。 Office 365 提供多一層的加密您的內容應用程式層級。 此內容包含資料從 Exchange Online、 Skype for Business，SharePoint Online、 商務用 OneDrive 和小組檔案。 此額外的階層的加密稱為服務加密。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>服務加密、 BitLocker，與客戶金鑰共同運作方式

服務加密可確保該內容靜態加密應用程式層級。 **BitLocker 與 DKM 的 Office 365 服務中的靜態永遠加密您的資料**。 如需詳細資訊，請參閱 「 安全性、 隱私權和 Office 365 的合規性資訊 」，以及[如何 Exchange Online 保護您電子郵件機密資料](exchange-online-secures-email-secrets.md)。 客戶金鑰提供額外保護，防範檢視的資料未經授權的系統或人員，並輔助 Microsoft 資料中心中的 BitLocker 磁碟加密。 若要防止 Microsoft 人員可以存取客戶資料，並不是服務加密。 主要目的是協助客戶會議法規或控制根機碼的合規性責任。 客戶明確授權提供新增的值使用他們的加密金鑰的 O365 服務雲端服務，例如電子文件探索、 反惡意程式碼、 反垃圾郵件，搜尋編製索引] 等。

客戶金鑰服務加密做為基礎，並可讓您提供並控制加密金鑰。 Office 365 然後使用這些金鑰來加密存放在[線上服務條款 (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx)中所述。 客戶金鑰可協助您符合規範，因為您可以控制加密金鑰來加密及解密資料所使用的 Office 365。
  
客戶金鑰可增強組織能夠滿足指定索引鍵的排列方式與雲端服務提供者的符合性需求。 使用客戶金鑰，您可以提供並控制您 Office 365 資料待用應用程式層級根加密金鑰。 因此，您會演練控制貴組織的機碼。 如果您決定要結束該服務，您會撤銷存取您的組織根機碼。 所有 Office 365 服務，撤銷存取的金鑰都是向資料刪除路徑上的第一個步驟。 藉由撤銷存取權的機碼，此資料是服務無法讀取。

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>客戶金鑰來加密在 Office 365 中的靜態資料

使用您提供的機碼，來加密的 Office 365 的客戶金鑰：

- SharePoint Online、 商務用 OneDrive 和小組檔案。
- 檔案上傳至商務用 OneDrive。
- Exchange Online 的信箱內容，包括電子郵件內文的內容、 行事曆項目和電子郵件附件內的內容。
- 商務用 Skype 的文字交談。

我們目前不提供客戶控制項的 Skype 會議廣播和 Skype 會議內容上傳的加密金鑰。 相反地，此內容會經過加密，以及在 Office 365 中的所有其他內容。

### <a name="customer-key-with-hybrid-deployments"></a>客戶金鑰與混合式部署

客戶金鑰只會加密定域機組中的靜態資料。 客戶金鑰無法運作以保護您的內部部署信箱和檔案。 您可以將使用另一個方法，例如 BitLocker 您內部部署資料的加密。

## <a name="about-the-data-encryption-policy-dep"></a>關於資料加密原則 (DEP)

資料加密原則定義來加密資料使用每個您提供 read 可用性的機碼的加密階層受到 Microsoft 的機碼。 您建立 DEPs 使用 PowerShell cmdlet，以不同的每個服務，以及指派這些應用程式資料加密。 例如：

**Exchange Online 和商務用 Skype**您可以建立每個租用戶最多 50 個 DEPs。 您建立 DEPs 關聯至您在 Azure 金鑰保存庫中的客戶金鑰，然後將 DEPs 指派給個別信箱。 當您將 DEP 指派給信箱：

- 信箱已標示的信箱移動。 根據在 Office 365 中的優先順序，如下所述[的移動要求的 Office 365 服務中](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)。

- 加密會在移動信箱。 允許 72 小時，讓要成為加密與新部署的信箱 如果信箱未加密之後等待 72 小時指派 DEP 的時間，請連絡 Microsoft。

更新版本中，您可以重新整理 DEP，或將不同的 DEP 指派給信箱[管理 Office 365 的客戶金鑰](customer-key-manage.md)所述。 每個信箱都必須有適當的授權才能指派相依性 如需授權的詳細資訊，請參閱[之前設定客戶金鑰](customer-key-set-up.md#before-you-set-up-customer-key)。

**SharePoint Online、 商務用 OneDrive 和小組檔案**如果您使用多地理位置功能，您可以建立最多一個 DEP 每個地理位置為您的組織。 您可以使用不同的客戶金鑰的每個地理位置。 如果您不使用多地理位置功能，您可以只建立一個 DEP 每個租用戶。 當您指派 DEP 時，加密便會自動開始，但可能需要一些時間才能完成。 在 [[設定 Office 365 的客戶金鑰](customer-key-set-up.md)的詳細資料，請參閱。

## <a name="leaving-the-service"></a>離開服務

客戶金鑰可協助您符合規範，讓您離開 Office 365 服務時撤銷您的金鑰。 當您撤銷一部分離開服務您機碼時，可用性機碼會刪除產生密碼編譯刪除您的資料。 密碼編譯刪除減少資料殘餘這是很重要的會議安全性與合規性責任的風險。 如需資料清除程序與索引鍵被撤銷，請參閱[撤銷您金鑰並啟動資料清除路徑程序](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

### <a name="encryption-ciphers-used-by-customer-key"></a>使用客戶金鑰加密 cipher

客戶金鑰可用於各種加密 cipher 加密金鑰，如下圖所示。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>加密 cipher 用來加密金鑰，Exchange Online 和商務用 Skype

![Exchange Online 客戶金鑰加密 cipher](media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>加密 cipher 用來加密金鑰，如 SharePoint Online、 商務用 OneDrive 和小組檔案

![SharePoint Online 客戶金鑰加密 cipher](media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相關文章

- [設定 Office 365 客戶金鑰](customer-key-set-up.md)

- [管理 office 365 的客戶金鑰](customer-key-manage.md)

- [展開或旋轉客戶金鑰或可用性機碼](customer-key-availability-key-roll.md)

- [了解可用性機碼](customer-key-availability-key-understand.md)

- [Office 365 中的客戶加密箱](customer-lockbox-requests.md)

- [Office 365 服務加密](office-365-service-encryption.md)
