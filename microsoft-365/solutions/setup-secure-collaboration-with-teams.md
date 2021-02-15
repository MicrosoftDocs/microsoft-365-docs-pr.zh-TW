---
title: 使用 Microsoft 365 設定安全的共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: 瞭解如何設定小組中的安全內容共同作業，以根據其敏感度來保護您的資料。
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233853"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>使用 Microsoft 365 設定安全的共同作業

能夠輕易與適當的人員分享資訊，同時避免 oversharing 是組織成功的關鍵。 這包括可以安全地與只有應有存取權的使用者共用機密資料。 視專案而定，這可能包括與組織外部人員共用機密資料。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

這個共同作業方案指南包含兩個元件，可協助您：
- 以適當的保護層級，為每個專案部署 Microsoft 團隊
- 針對每個專案設定具有適當安全性設定的外部共用

![以適當的安全性設定，以適當的保護和設定外部共用來部署團隊](..\media\solutions-architecture-center\secure-collaboration-overview.png)

如果您無法使用多功能和便於使用的內容共同作業工具，使用者通常會透過電子郵件檔進行共同作業。 這是一種單調乏味且容易出錯的共同作業方法，可增加不適當共用資訊的風險。 如果人員發現共用資訊過於困難，他們可能會回復為使用不受 IT 管理的消費產品。 這可能會帶來更大的風險。

使用 Microsoft 365，您可以使用各種設定來部署小組，以協助：

- 保護您的智慧財產權
- 啟用輕鬆合作
- 建立安全性和可用性之間的平衡，以提升使用者滿意度並降低陰影的風險

如果資訊未適當共用，大部分的組織都有各種資訊，但敏感度程度不同，而且業務影響程度也會不同。 根據特定資訊的敏感度，您可能想要允許與共享：

- 任何人 (未驗證) 
- 組織內的人員
- 組織內的特定人員
- 組織內部和外部的特定人員

「行銷手冊」等資訊是要在組織外廣泛共用。 諸如諸如自助共用之外的資訊（例如，自助）可能不會影響任何業務，如果是外部共用。 這些類型的資訊需要很少或沒有防護。

在開發時，這些相同的行銷手冊只會在組織內共用。 在此情況下，小組中的預設共用設定可能已足夠。

在開發中的新產品資訊可能被視為敏感，甚至是在組織內。 在此情況下，可能會有較大程度的保護。 例如，您可以限制對此資訊的存取權給特定小組的成員。 視專案而定，您可能需要與組織外部的人員（例如廠商或夥伴組織）進行共同作業。

對貴組織成功與否重要的資訊，或具有嚴格的安全性或規範需求可能需要更高的保護等級。

![從低 (發行的摺頁冊) 到高 (敏感商務資料) ](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

針對上述所有案例，您可以使用 Microsoft 團隊中的團隊來儲存、共用及共同作業資訊。 

若要設定安全共同作業，您可以使用這些 Microsoft 365 功能和功能。

| 產品或元件 | 功能 | 授權 |
|:-------|:-----|:-------|
| 適用於 Office 365 的 Microsoft Defender | SPO、OneDrive 及小組的安全附件;安全檔;小組的安全連結    | Microsoft 365 E1，E3 和 E5 |
| SharePoint    | 網站與檔案共用原則、網站共用許可權、共用連結、存取要求、網站來賓共用設定 | Microsoft 365 E1，E3 和 E5 |
| Microsoft Teams   | 來賓存取、私人團隊、專用通道 | Microsoft 365 E1，E3 和 E5 |
| Microsoft 365 合規性  | 敏感度標籤    | Microsoft 365 E3 和 E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>針對所有種類的資料使用團隊

若要使用不同的 sensitivities 管理資訊存取，我們 [為小組開發了三個不同的保護層級](configure-teams-three-tiers-protection.md)。 您可以自訂這些層級，以更好地解決需求或您的業務。 

![Teams 邏輯架構海報的縮圖影像](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


這些層級- *基準*、 *敏感* 和 *高敏感度* -逐步增加保護，協助避免 oversharing 和潛在的資訊洩漏，如下表所示。

|-|**基準層**|**機密層**|**高度機密層**|
|:--|:-----------|:------------|:-------------------|
|公用或私人團隊|兩者之一|Private|Private|
|未經驗證的共用|已封鎖|已封鎖|已封鎖|
|檔案共用|允許|允許|只有小組擁有者可以共用。|
|小組成員資格|任何人都可以加入 public 團隊。<br>加入私人團隊所需的小組擁有者核准。|加入所需的小組擁有者核准。|加入所需的小組擁有者核准。|
|檔加密|||可用於敏感度標籤|
|來賓共用|允許|可以允許或封鎖|可以允許或封鎖|
|非管理裝置|無限制|僅限網頁存取|已封鎖|

設定這些層級包括：

- 為來賓存取和專用通道設定小組中的設定
- 為內部及來賓共用、存取要求和共用連結設定小組相關 SharePoint 網站中的設定
- 針對 *敏感* 和 *高敏感度* 的層級，設定敏感度標籤來分類小組，以及控制來賓共用和非管理裝置的存取
- 針對 *高度敏感* 的層級，設定靈敏度標籤以加密其所套用的檔

從基準層開始，然後根據需要新增使用 *敏感* 和 *高度機密* 階層的團隊，以協助保護組織中的資訊。 請參閱下列資源以開始執行：

- [為小組設定基準保護](configure-teams-baseline-protection.md)
- [為團隊設定高敏感性資料保護](configure-teams-sensitive-protection.md)
- [為小組設定高敏感度資料保護](configure-teams-highly-sensitive-protection.md)

如果您有高度機密的專案需要在組織內共用額外的保護，您可以設定一個小組，該小組使用自己的敏感度標籤來加密檔案，只有小組成員可以讀取這些檔案。 如需詳細資訊，請參閱 [Configure a team with security 隔離](secure-teams-security-isolation.md) 。

### <a name="sharing-with-people-outside-your-organization"></a>與組織外部的人員共用

您可能需要 [與組織外部的人員共用任何敏感度的資訊](collaborate-with-people-outside-your-organization.md)。 這可能包括與單一人員共用單一檔，以從世界各地的大型夥伴組織或兼職處理主要專案。 在 Microsoft 365 中，您可以輕鬆執行這種外部共用，並提供適當的防範措施，協助保護您的敏感資訊。

這些資源會協助您開始設定您的環境，以與組織外部的人員進行合作：

- [在檔上共同](collaborate-on-documents.md) 作業，以共用個別的資料夾檔案。
- [在網站中共同](collaborate-in-site.md) 作業，以與在 SharePoint 網站中的客人進行合作。
- [以](collaborate-as-team.md) 團隊方式共同作業，以與小組中的客人合作。

根據所共用資訊的敏感度，您可以新增安全保護，以協助防止 oversharing。 這些資源將協助您設定組織所需的保護：

- [與未驗證使用者共用檔案和資料夾的最佳做法](best-practices-anonymous-sharing.md)
- [在與組織外的人員共用檔案時，限制資訊意外暴露](share-limit-accidental-exposure.md)
- [建立安全的來賓共用環境](create-secure-guest-sharing-environment.md)

如果您有一個主要專案與一個夥伴組織，您可以使用 Azure 權利管理，在您為專案設定的小組中管理該組織的客人。 如需詳細資訊，請參閱 [Create a B2B extranet with managed guests](b2b-extranet.md) 。

## <a name="deploy-the-secure-collaboration-solution"></a>部署安全的共同作業解決方案

當您準備好部署此方案時，請繼續執行下列步驟：
1. [為小組設定三種不同的保護層級](configure-teams-three-tiers-protection.md)。
2. 設定 [與組織外部人員共用任何敏感度資訊的](collaborate-with-people-outside-your-organization.md)設定。

## <a name="see-also"></a>另請參閱

[Microsoft 365 安全性文件](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365 合規性文件](https://docs.microsoft.com/microsoft-365/compliance)

[歡迎使用 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
