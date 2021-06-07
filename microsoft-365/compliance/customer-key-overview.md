---
title: 客戶金鑰服務加密
ms.author: krowley
author: kccross
manager: laurawi
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
ms.openlocfilehash: d12a5d2f80de11a69fc4a36146a511c5f9a306f8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769446"
---
# <a name="service-encryption-with-customer-key"></a>客戶金鑰服務加密

Microsoft 365 提供使用 BitLocker 和分散式金鑰管理員 (DKM) 啟用的基準、磁片區層級加密。 Microsoft 365 為您的內容提供額外的加密層級。 此內容包括 Exchange Online、商務用 Skype、SharePoint 線上、商務用 OneDrive 及 Microsoft Teams 的資料。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>服務加密、BitLocker 及客戶金鑰共同運作的方式

您的資料在 Microsoft 365 服務中永遠會以 BitLocker 和 DKM 加密。 如需詳細資訊，請參閱 how [Exchange Online 如何保護您的電子郵件機密](exchange-online-secures-email-secrets.md)。 客戶金鑰提供額外的保護，防止未經授權的系統或人員查看資料，並補充 Microsoft 資料中心的 BitLocker 磁片加密。 服務加密不是為了防止 Microsoft 人員存取您的資料。 相反地，客戶金鑰可協助您符合控制根機碼的規章或合規性義務。 您明確授權 Microsoft 365 服務使用您的加密金鑰，以提供增值雲端服務，例如 eDiscovery、反惡意程式碼、反垃圾郵件、搜尋索引等等。

客戶金鑰是以服務加密為基礎，可讓您提供和控制加密金鑰。 然後 Microsoft 365 會使用這些機碼，如[線上服務條款 (.ost) ](https://www.microsoft.com/licensing/product-licensing/products.aspx)所述，對您的資料進行加密。 客戶金鑰可協助您達到法規遵從性義務，因為您會控制 Microsoft 365 用來加密及解密資料的加密金鑰。
  
客戶金鑰可提升您的組織符合規範需求的能力，以指定與雲端服務提供者的重要安排。 使用客戶金鑰，您可以在應用層級為您的 Microsoft 365 資料提供及控制根加密金鑰。 因此，您會練習控制組織的按鍵。

## <a name="customer-key-with-hybrid-deployments"></a>具有混合式部署的客戶金鑰

客戶金鑰只會加密雲端中靜態的資料。 客戶金鑰不會用來保護您的內部部署信箱和檔案。 您可以使用另一種方法（例如 BitLocker）來加密您的內部部署資料。

## <a name="about-data-encryption-policies"></a>關於資料加密原則

資料加密原則 (DEP) 會定義加密階層。 此階層由服務使用，以使用每個您管理的金鑰和 Microsoft 所保護的可用性金鑰來加密資料。 您可以使用 PowerShell Cmdlet 來建立 DEPs，然後指派這些 DEPs 以加密應用程式資料。 Microsoft 365 客戶機碼支援三種類型的 DEPs，每個原則類型都使用不同的指令程式，並提供不同類型資料的範圍。 您可以定義的 DEPs 包括：

**多個 Microsoft 365 工作負載的 DEP** 這些 DEPs 會針對租使用者內的所有使用者，在多個 M365 工作負載中加密資料。 這些工作負載包括：

- Teams 聊天訊息 (1:1 聊天、群組交談、會議聊天及通道交談) 
- Teams 媒體訊息 (影像、程式碼片段、影片郵件、音訊訊息、wiki 影像) 
- Teams 儲存區中儲存的 Teams 通話和會議錄製
- Teams 聊天通知
- 使用 Cortana Teams 聊天建議
- Teams 狀態郵件
- Exchange Online 的使用者和信號資訊
- Exchange Online 信箱 DEPs 未加密的信箱
- Microsoft 資訊保護：

  - 完全資料符合 (EDM) 資料，包括資料檔案架構、規則套件，以及用來散列敏感性資料的 salts。 針對 EDM 和 Microsoft Teams，多工作負載 DEP 會從您指派 DEP 給租使用者時，加密新的資料。 針對 Exchange Online，客戶金鑰會加密所有現有和新的資料。

  - 敏感度標籤的標籤設定

多工作負載 DEPs 不會加密下列類型的資料。 相反地，Microsoft 365 會使用其他類型的加密來保護此資料。

- SharePoint 和商務用 OneDrive 資料。
- 商務用 OneDrive 和 SharePoint online 中儲存的 Microsoft Teams 檔案和部分 Teams 呼叫和會議錄製，都是使用 SharePoint 線上 DEP 進行加密。
- 其他 Microsoft 365 工作負載，例如，客戶機碼目前不支援的 Yammer 和 Planner。
- TeamsLive 事件和 Q&即時事件。 針對 Teams，此案例是唯一一種未使用多重工作負載 DEP 以客戶金鑰加密的案例。

每個租使用者可以建立多個 DEPs，但一次只能指派一個 DEP。 當您指派 DEP 時，加密會自動開始，但需要一些時間才能完成，具體取決於您的承租人的大小。

**Exchange Online 信箱的 DEPs** 信箱 DEPs 可在 Exchange Online 內提供更精確的控制個別信箱。 使用信箱 DEPs，加密儲存在不同類型的 EXO 信箱中的資料，例如 UserMailbox、MailUser、群組、PublicFolder 和共用信箱。 每個租使用者最多可以有50個活躍 DEPs，並將這些 DEPs 指派給個別信箱。 您可以將一個 DEP 指派給多個信箱。

根據預設，您的信箱是使用 Microsoft 管理的金鑰加密。 當您將客戶金鑰 DEP 指派給信箱時：

- 如果信箱是使用多工作負載 DEP 進行加密，只要使用者或系統作業可以存取信箱資料，該服務便會以新的信箱 DEP rewraps 信箱。

- 如果信箱已使用 Microsoft 管理金鑰加密，只要使用者或系統作業存取信箱資料，該服務就會使用新的信箱 DEP rewraps 信箱。

- 如果信箱尚未使用預設加密加密，則服務會標示移動信箱。 移動完成後，就會進行加密。 信箱移動取決於所有 Microsoft 365 設定的優先順序。 如需詳細資訊，請參閱[Microsoft 365 服務中的移動要求](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)。 如果在指定的時間內沒有加密信箱，請與 Microsoft 聯繫。

稍後，您可以依照[管理 Office 365 的客戶金鑰](customer-key-manage.md)中所述的方式，重新整理 DEP 或指派不同的 dep 至信箱。 每個信箱都必須有適當的授權，才能被指派 DEP。 如需授權的詳細資訊，請參閱 [設定客戶金鑰之前](customer-key-set-up.md#before-you-set-up-customer-key)。

DEPs 可指派給共用信箱、公用資料夾信箱，以及符合使用者信箱授權需求的承租人的 Microsoft 365 群組信箱。 非使用者特有的信箱不需要個別的授權，就能指派客戶金鑰 DEP。

針對您指派給個別信箱的客戶機碼 DEPs，您可以在離開服務時要求 Microsoft 清除特定 DEPs。 如需有關資料清除程式和金鑰吊銷的詳細資訊，請參閱 [撤銷您的金鑰，然後啟動資料清除路徑處理](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)程式。

當您在離開服務時撤銷您的金鑰存取權時，可用性機碼會刪除，從而導致您的資料被加密刪除。 加密刪除可降低資料 remanence 的風險，這對於迎接安全性和合規性義務很重要。

**SharePoint 線上及商務用 OneDrive 的 DEP** 此 DEP 是用來加密儲存在 SPO 和商務用 OneDrive 中的內容，包括儲存在 SPO 中的 Microsoft Teams 檔案。 如果您使用的是多地理位置功能，您可以為組織建立一個每個地理位置的 DEP。 如果您不是使用多地理位置功能，則每個承租人只能建立一個 DEP。 請參閱 [設定客戶金鑰](customer-key-set-up.md)中的詳細資料。

### <a name="encryption-ciphers-used-by-customer-key"></a>客戶金鑰使用的加密密碼

客戶金鑰使用各種加密密碼來加密金鑰，如下圖所示。

用於 DEPs 多個 Microsoft 365 工作負載之資料的金鑰階層，與 DEPs 用於個別 Exchange Online 信箱的階層類似。 唯一的區別是信箱金鑰會取代對應的 Microsoft 365 工作量機碼。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>用來加密 Exchange Online 和商務用 Skype 金鑰的加密密碼

![Exchange Online 客戶機碼的加密密碼](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>用來加密 SharePoint 線上、商務用 OneDrive 及 Teams 檔案的金鑰的加密密碼

![SharePoint Online 客戶機碼的加密密碼](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相關文章

- [設定客戶金鑰](customer-key-set-up.md)

- [管理客戶金鑰](customer-key-manage.md)

- [滾動或旋轉客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)

- [深入瞭解可用性金鑰](customer-key-availability-key-understand.md)

- [客戶加密箱](customer-lockbox-requests.md)

- [服務加密](office-365-service-encryption.md)