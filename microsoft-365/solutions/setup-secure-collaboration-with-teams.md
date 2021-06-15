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
recommendations: false
description: 瞭解如何在 Teams 中設定安全的內容共同作業，以根據其敏感度來保護您的資料。
ms.openlocfilehash: 7a5b8f58cc5e4a23d2d143419f99ecdd87b949c1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924356"
---
# <a name="set-up-secure-collaboration-with-microsoft-365-and-microsoft-teams"></a>使用 Microsoft 365 和 Microsoft Teams 設定安全協同作業

能夠輕易與適當的人員分享資訊，同時避免 oversharing 是組織成功的關鍵。 這包括可以安全地與只有應有存取權的使用者共用機密資料。 視專案而定，這可能包括與組織外部人員共用機密資料。

這個共同作業方案指南包含兩個元件，可協助您：
- 以適當的保護層級，為每個專案部署 Microsoft Teams
- 針對每個專案設定具有適當安全性設定的外部共用

![使用適當的安全性設定來部署 Teams 以適當的保護和設定外部共用](..\media\solutions-architecture-center\secure-collaboration-overview.png)

如果您無法使用多功能和便於使用的內容共同作業工具，使用者通常會透過電子郵件檔進行共同作業。 這是一種單調乏味且容易出錯的共同作業方法，可增加不適當共用資訊的風險。 如果人員發現共用資訊過於困難，他們可能會回復為使用不受 IT 管理的消費產品。 這可能會帶來更大的風險。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

透過 Microsoft 365，您可以使用各種設定來部署 Teams，以協助：

- 保護您的智慧財產權
- 啟用輕鬆合作
- 建立安全性和可用性之間的平衡，以提升使用者滿意度並降低陰影的風險

如果資訊未適當共用，大部分的組織都有各種資訊，但敏感度程度不同，而且業務影響程度也會不同。 根據特定資訊的敏感度，您可能想要允許與共享：

- 任何人 (未驗證) 
- 組織內的人員
- 組織內的特定人員
- 組織內部和外部的特定人員

「行銷手冊」等資訊是要在組織外廣泛共用。 諸如諸如自助共用之外的資訊（例如，自助）可能不會影響任何業務，如果是外部共用。 這些類型的資訊需要很少或沒有防護。

在開發時，這些相同的行銷手冊只會在組織內共用。 在此情況下，Teams 中的預設共用設定可能已足夠。

在開發中的新產品資訊可能被視為敏感，甚至是在組織內。 在此情況下，可能會有較大程度的保護。 例如，您可以限制對此資訊的存取權給特定小組的成員。 視專案而定，您可能需要與組織外部的人員（例如廠商或夥伴組織）進行共同作業。

對貴組織成功與否重要的資訊，或具有嚴格的安全性或規範需求可能需要更高的保護等級。

![從低 (發行的摺頁冊) 到高 (敏感商務資料) ](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

針對上述所有案例，您可以使用 Microsoft Teams 中的小組來儲存、共用及共同作業資訊。 

若要設定安全共同作業，您可以使用這些 Microsoft 365 功能。

| 產品或元件 | 功能 | 授權 |
|:-------|:-----|:-------|
| 適用於 Office 365 的 Microsoft Defender | SPO、OneDrive 及 Teams 的安全附件;安全檔;Teams 的安全連結    | Microsoft 365E1、E3 及 E5 |
| SharePoint    | 網站與檔案共用原則、網站共用許可權、共用連結、存取要求、網站來賓共用設定 | Microsoft 365E1、E3 及 E5 |
| Microsoft Teams   | 來賓存取、私人團隊、專用通道 | Microsoft 365E1、E3 及 E5 |
| Microsoft 365 合規性  | 敏感度標籤    | Microsoft 365 E3 和 E5 |

### <a name="collaboration-governance"></a>共同作業控管

Microsoft 365 提供許多選項來管理共同作業解決方案。 我們建議您使用此部署內容與共同作業控管 [內容](collaboration-governance-overview.md) ，為您的組織建立最佳的共同作業解決方案。

### <a name="using-teams-for-all-kinds-of-data"></a>針對所有種類的資料使用 Teams

為了管理不同 sensitivities 的資訊存取，我們[為 Teams 開發了三個不同的保護層級](configure-teams-three-tiers-protection.md)。 您可以自訂這些層級，以更好地解決需求或您的業務。 

![Teams 的三種保護層級圖形](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


這些層級- *基準*、 *敏感* 和 *高敏感度* -逐步增加保護，協助避免 oversharing 和潛在的資訊洩漏，如下表所示。

|-|**基準層**|**機密層**|**高度機密層**|
|:--|:-----------|:------------|:-------------------|
|公用或私人團隊|兩者之一|私人|私人|
|未經驗證的共用|已封鎖|已封鎖|已封鎖|
|檔案共用|允許|允許|只有小組擁有者可以共用。|
|小組成員資格|任何人都可以加入 public 團隊。<br>加入私人團隊所需的小組擁有者核准。|加入所需的小組擁有者核准。|加入所需的小組擁有者核准。|
|檔加密|||可用於敏感度標籤|
|來賓共用|允許|可以允許或封鎖|可以允許或封鎖|
|未受管理的裝置|無限制|僅限網頁存取|已封鎖|

設定這些層級包括：

- 在 Teams 中設定來賓存取和專用通道的設定
- 為內部及來賓共用、存取要求和共用連結設定小組相關 SharePoint 網站中的設定
- 針對 *敏感* 和 *高敏感度* 的層級，設定敏感度標籤來分類小組，以及控制來賓共用和非管理裝置的存取
- 針對 *高度敏感* 的層級，設定靈敏度標籤以加密其所套用的檔

從基準層開始，然後根據需要新增使用 *敏感* 和 *高度機密* 階層的團隊，以協助保護組織中的資訊。 請參閱下列資源以開始執行：

- [為小組設定基準保護](configure-teams-baseline-protection.md)
- [為團隊設定高敏感性資料保護](configure-teams-sensitive-protection.md)
- [為小組設定高敏感度資料保護](configure-teams-highly-sensitive-protection.md)

如果您有高度機密的專案需要在組織內共用額外的保護，您可以設定一個小組，該小組使用自己的敏感度標籤來加密檔案，只有小組成員可以讀取這些檔案。 如需詳細資訊，請參閱 [Configure a team with security 隔離](secure-teams-security-isolation.md) 。

### <a name="sharing-with-people-outside-your-organization"></a>與組織外部的人員共用

您可能需要 [與組織外部的人員共用任何敏感度的資訊](collaborate-with-people-outside-your-organization.md)。 這可能包括與單一人員共用單一檔，以從世界各地的大型夥伴組織或兼職處理主要專案。 在 Microsoft 365 中，您可以輕鬆執行這種外部共用的範圍，並以適當的防範措施來協助保護您的敏感資訊。

這些資源會協助您開始設定您的環境，以與組織外部的人員進行合作：

- [在檔上共同](collaborate-on-documents.md) 作業，以共用個別的資料夾檔案。
- [在網站中共同](collaborate-in-site.md)作業，以與在 SharePoint 網站中的客人進行合作。
- [以](collaborate-as-team.md) 團隊方式共同作業，以與小組中的客人合作。

根據所共用資訊的敏感度，您可以新增安全保護，以協助防止 oversharing。 這些資源將協助您設定組織所需的保護：

- [與未驗證使用者共用檔案和資料夾的最佳做法](best-practices-anonymous-sharing.md)
- [在與組織外的人員共用檔案時，限制資訊意外暴露](share-limit-accidental-exposure.md)
- [建立安全的來賓共用環境](create-secure-guest-sharing-environment.md)

如果您有一個主要專案與一個夥伴組織，您可以使用 Azure 權利管理，在您為專案設定的小組中管理該組織的客人。 如需詳細資訊，請參閱 [Create a B2B extranet with managed guests](b2b-extranet.md) 。



## <a name="training-for-administrators"></a>系統管理員訓練

Microsoft 學習的這些訓練模組可協助您瞭解 Teams 和 SharePoint 中的共同作業、控管和身分識別功能。

#### <a name="teams"></a>Teams

|培訓：|使用 Microsoft Teams 管理團隊共同作業|
|:---|:---|
|![Teams 協同作業訓練圖示](../media/manage-team-collaboration-with-microsoft-teams.svg)|使用 Microsoft Teams 管理團隊共同作業會為您介紹 Microsoft Teams 的功能，Microsoft Teams 是 Microsoft 365 中的團隊共同作業中心。 您將了解如何使用 Teams 來促進組織內部和外部的團隊合作和溝通，包括從桌面、平板電腦和手機等各種設備，同時利用 Office 365 應用程式的所有豐富功能。 您將了解 Teams 如何提供全面且靈活的環境，以便在各個應用程式和裝置上共同作業。 這個學習路徑可協助您準備 Microsoft 365 認證：Teams 系統管理員關聯認證。<br><br>2個 hr 17 min-教學路徑-5 模組|

> [!div class="nextstepaction"]
> [開始 >](/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|培訓：|在 Microsoft 365 中使用 SharePoint 共同作業|
|:---|:---|
|![SharePoint 訓練圖示](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|使用 Microsoft SharePoint 管理共用內容，為您提供 SharePoint 的各項功能，以及它如何與 Microsoft 365 搭配使用。 您將了解不同類型的 SharePoint 網站，包括中樞網站，以及資訊保護、報告及監視。 您也將了解如何使用 SharePoint 檔案和資料夾共用，以最佳化共同作業、如何在外部共用檔案，以及如何在 SharePoint 系統管理中心管理 SharePoint 網站。 這個學習路徑可協助您準備 Microsoft 365 認證：團隊工作系統管理員關聯認證。<br><br>1 hr 14 min-教學路徑-4 模組|

> [!div class="nextstepaction"]
> [開始 >](/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

#### <a name="information-protection"></a>資訊保護

|培訓：|使用 Microsoft 365 保護企業資訊|
|:---|:---|
|![Teams info protection 訓練圖示](../media/protect-enterprise-information-microsoft-365.svg)|保護您組織資訊的方式比以往更具挑戰性。 使用 Microsoft 365 保護企業資訊學習路徑將討論如何防止您的敏感資訊意外地過度分享或誤用、如何探索和分類資料、如何使用敏感度標籤保護資料，以及如何監視和分析您的敏感資訊以避免資料遺失。 這種教學途徑可協助您準備 Microsoft 365 認證：安全性系統管理員關聯並 Microsoft 365 認證： Enterprise 管理專家認證。<br><br>1 hr 教學路徑-5 模組|

> [!div class="nextstepaction"]
> [開始 >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>身分識別和存取

|培訓：|使用 Azure Active Directory 保護身分識別和存取|
|:---|:---|
|![身分識別和存取訓練圖示](../media/protect-identity-and-access-with-microsoft-365.svg)|身分識別和存取學習路徑涵蓋最新的身分識別和存取技術、強化驗證所需的工具，以及組織內部身分識別保護的指導方針。 Microsoft 存取和身分識別技術可讓您保護組織的身分識別 (無論是內部部署或雲端)，還能讓您的使用者從任何位置安全地工作。 這個學習路徑可協助您準備 Microsoft 365 認證：安全性系統管理員助理和 Microsoft 365 認證：企業管理員專家認證。<br><br>2小時 52 min-教學路徑-6 模組|

> [!div class="nextstepaction"]
> [開始 >](/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>適用於終端使用者的訓練

這些訓練模組可協助您的使用者在 Microsoft 365 中使用 Teams、群組和 SharePoint 進行共同作業。

|Teams|SharePoint|
|:---|:---|
|![設定和自訂小組訓練圖示](../media/set-up-customize-team-training.png)<br>**[設定和自訂您的小組](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint 共用及同步訓練圖示](../media/sharepoint-share-sync-training.png)<br>**[共用及同步處理](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Teams 上傳及尋找檔案訓練圖示](../media/smc-teams-upload-find-files-training.png)<br>**[Upload 及尋找檔](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![在小組和頻道中共同作業圖示](../media/teams-collaborate-channels-training.png)<br>**[小組和頻道共同作業](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**||

## <a name="illustrations"></a>插圖

這些圖例可協助您瞭解群組和團隊如何與 Microsoft 365 中的其他服務互動，以及可協助您在組織中管理這些服務的控管和合規性功能。

### <a name="groups-in-microsoft-365-for-it-architects"></a>適用於 IT 結構設計師的 Microsoft 365 中的群組
對於 Microsoft 365 中的群組，IT 結構設計師需要知道的事項

|**項目**|**描述**|
|:-----|:-----|
|[![群組資訊圖的縮圖影像](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> 更新日期：2019 年 6 月|這些圖例會詳細說明不同類型的群組、如何建立及管理群組，以及一些控管建議。|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>適用於 IT 結構設計師的 Microsoft 365 中的Microsoft Teams 和相關生產力服務
使用 Microsoft Teams 領導，Microsoft 365 中生產力服務的邏輯架構。

|**項目**|**描述**|
|:-----|:-----|
|[![Teams 邏輯架構海報的縮圖影像](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>更新日期：2019 年 4 月   |Microsoft 提供一套生產力服務，共同合作來提供資料管理、安全性和法規遵循功能的共同作業體驗。 <br/> <br/>這系列的圖例可為企業結構設計師提供生產力服務邏輯架構使用 Microsoft Teams 引導的檢視。|

## <a name="deploy-the-secure-collaboration-solution"></a>部署安全的共同作業解決方案

當您準備好部署此方案時，請繼續執行下列步驟：
1. [為 Teams 設定三種不同的保護層級](configure-teams-three-tiers-protection.md)。
2. 設定 [與組織外部人員共用任何敏感度資訊的](collaborate-with-people-outside-your-organization.md)設定。

## <a name="see-also"></a>另請參閱

[Microsoft 365 安全性文件](../security/index.yml)

[Microsoft 365 合規性文件](../compliance/index.yml)

[歡迎使用 Microsoft Teams](/MicrosoftTeams/Teams-overview)
