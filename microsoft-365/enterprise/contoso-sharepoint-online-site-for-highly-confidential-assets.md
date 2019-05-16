---
title: Contoso Corporation 的高度機密數位資產的 SharePoint Online 網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： 如何 Contoso 實施適用於 SharePoint Online 網站高管制的資料，其研究之間更輕鬆地共同作業的團隊。
ms.openlocfilehash: 99599829658e5dc46c8adebfe59f5c6d09b165de
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072776"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Contoso Corporation 的高度機密數位資產的 SharePoint Online 網站

 **摘要：** Contoso 實作其研究小組之間更輕鬆地共同作業的高管制資料的 SharePoint Online 網站的方式。
  
Contoso 的最有價值的資產是其形式的營業秘密、 專屬的製造技術，例如智慧財產及設計規格正在開發的產品。 這些資產相關數位表單中，原來儲存為 SharePoint Server 2016 網站上的檔案。 Contoso 部署 Microsoft 365 企業版，他們想要在巴黎、 莫斯科、 紐約、 北京和班加羅爾研究小組間轉換至雲端的更容易存取，且更開啟共同作業其內部部署數位資產。 
  
不過，由於其機密性質，存取這些檔案必須是一項：

- 受限制的允許檢視或變更，具有持續的權限僅由 SharePoint 系統管理員管理網站的人員設定。 
- 保護與資料外洩防護 (DLP) 可防止使用者間分散外部網站。
- 加密和保護與存取控制清單，以防止未經授權的使用者存取其內容，即使他們分配站台外。

安全性和 SharePoint 系統管理員在 Contoso 的 IT 部門決定使用[適用於 SharePoint Online 網站高管制資料](teams-sharepoint-online-sites-highly-regulated-data.md)。
  
Contoso 使用下列步驟來建立並保護其研究小組 SharePoint Online 小組網站。

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>步驟 1： 檢閱並確認研究小組群組的成員

Contoso 的 IT 系統管理員為其研究小組執行 < review of 一組安全性群組。 任何人未 researcher 或不需要存取 research 資產移除它們。 

他們也建立這些新的安全性群組：

- **Research 系統管理員** 一組的 SharePoint 系統管理員具有完全控制權的網站，包括修改權限的能力。
- **Research 成員** 一組安全性群組的世界各地的研究小組。
- **參考資料檢視** 一組管理使用者，例如 research 組織，只能在網站檢視資產中的主管。

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>步驟 2： 建立隔離的 SharePoint Online 小組網站 

第一次建立新的小組網站的 Contoso SharePoint 系統管理員名為**Research**。 他們，然後設定：

- 使用參考資料擁有者 SharePoint 群組中，具有**研究-Admins**安全性群組的成員身分的完全控制 」 權限等級
- 使用 [參考成員] SharePoint 群組中，具有**Research 成員**安全性群組的成員身分的編輯權限等級
- 使用 Research 訪客 SharePoint 群組，其為成員的 [**參考資料檢視**安全性] 群組的讀取權限等級

以下是所產生的 SharePoint 權限等級、 SharePoint 群組和其成員。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

接下來，其設定之網站的其他限制。

如設定的詳細資訊，請參閱[部署隔離的 SharePoint Online 小組網站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)。

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a>步驟 3： 設定嚴格的 DLP 原則的網站

首先，Contoso 系統管理員套用**Research**網站的**高度機密**的 Office 365 保留標籤。

接下來，建立新的 Office 365 DLP 原則名為**Research**的：

- 使用**高度機密**的 Office 365 保留標籤。 
- 會套用至**Research**網站。
- 當他們嘗試共用 Contoso 以外的**研究**網站上的數位資產時，就會封鎖使用者。

如設定的詳細資訊，請參閱 <<c0>使用保留標籤與 DLP 保護 SharePoint Online 檔案。

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>步驟 4： 建立網站的 Azure 資訊保護子標籤

Contoso 系統管理員建立新的 Azure 資訊保護子標籤名為**Research**的預設**高度機密**] 標籤中的限域原則的：

- 需要加密。
- 允許完整存取**Research 成員**的 [安全性] 群組的成員。
- 允許讀取權限由**參考資料檢視**的 [安全性] 群組的成員。

接下來，這些部署的 Azure 資訊保護用戶端裝置的研究小組成員。

如設定的詳細資訊，請參閱[使用 Azure 資訊保護保護 SharePoint Online 檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。 

以下是高度機密資產的**研究**網站所產生的組態。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

**研究**站台的資料夾中的檔案受到：

- **研究**Azure 資訊保護子標籤，適用於加密和使用權檔案會對每個檔案已移動或複製從**Research**網站。
- **研究**DLP 原則，會使用**高度機密**的保留標籤和避免與外部使用者共用檔案的設定。
- 網站權限，只允許存取成員**Research 成員**和**參考資料檢視者**安全性群組和管理由**Research Admins**安全性群組的成員集合。

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>步驟 5： 移轉的內部部署 SharePoint research 資料

Contoso 系統管理員移動所有內部研發網站中的內部部署 SharePoint Server 2016 中新**的參考資料**的 SharePoint Online 站台資料夾的檔案。

## <a name="step-6-trained-their-users"></a>步驟 6： 訓練使用者 

Contoso 的安全性人員訓練逐步執行它們透過強制課程中的研究小組：

- How to： 存取新的**研究**SharePoint Online 網站和其現有的檔案。
- 如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。
- 示範 DLP 原則會封鎖從外部共用的檔案。
- 如何使用 Azure 資訊保護用戶端標籤具有**Research**子標籤的參考資料檔案。
- **Research**子標籤如何保護檔案，即使它從網站遺漏的示範。

最後的結果是安全的環境研究人員可以共同在安全的環境中的組織。 

如果從**Research**網站遺漏研究文件與**研究**子標籤，它會經過加密並且只有具有有效認證**Research 成員**和**參考資料檢視**安全性群組的成員可以存取。

## <a name="next-step"></a>下一步

[部署](deploy-microsoft-365-enterprise.md)Microsoft 365 企業版，您組織中。

