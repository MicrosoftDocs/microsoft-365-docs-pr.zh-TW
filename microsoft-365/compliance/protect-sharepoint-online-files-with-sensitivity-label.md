---
title: 使用敏感度標籤來保護 SharePoint Online 檔案
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 摘要：套用 Azure 資訊保護來保護高度機密 SharePoint Online 小組網站中的檔案。
ms.openlocfilehash: 8d802d8c2b5202e51089659264b2e2c14f14ad3d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214627"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a>使用敏感度標籤來保護 SharePoint Online 檔案

使用本文中的步驟來設定敏感度標籤，以提供檔案的加密和權限。 您可以將這些檔案新增至已設定高度機密保護的 SharePoint 文件庫。 或者，您可以直接從網站開啟檔案並套用標籤。 此加密和權限保護會與檔案一起移動，即使是從網站下載檔案也一樣。 

這些步驟是屬於較大的解決方案，用於設定 SharePoint 網站和這些網站中檔案的高度機密保護。如需詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)。 

不建議針對所有的客戶在 SharePoint Online 中的檔案使用敏感度標籤，但可供需要此檔案子集合保護層級的客戶選擇使用。

這套解決方案的一些相關重要注意事項：
- 如果貴組織未[在 SharePoint 和 OneDrive (公開預覽版) 中針對 Office 檔案啟用敏感度標籤](/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files)：當您將加密套用到儲存在 Office 365 中的檔案時，服務無法處理這些檔案的內容。 共同撰寫、eDiscovery、搜尋、Delve 和其他共同作業功能無法運作。 此外，資料外洩防護 (DLP) 原則只可用於中繼資料 (包括標籤)，但無法用於這些檔案的內容 (例如檔案中的信用卡號碼)。

- 本解決方案要求使用者選取適用保護的標籤。 如果您需要自動加密和 SharePoint 的功能來為檔案編製索引及檢查檔案，請考慮在 SharePoint Online 中使用資訊版權管理 (IRM)。 當您為 IRM 設定 SharePoint 文件庫，即會在下載檔案以供編輯時自動加密。  SharePoint IRM 包含可能會影響您決策的限制。 如需詳細資訊，請參閱[在 SharePoint 系統管理中心設定資訊版權管理 (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center)。

## <a name="admin-setup"></a>系統管理員設定

若要為特定 SharePoint Online 小組網站中的檔案達成這個額外的安全性層級，您必須設定自訂的敏感度標籤，而此標籤可以是單獨的標籤，或是高度管制資料之一般標籤的子標籤。 只有 SharePoint Online 小組網站的 Microsoft 365 群組成員，才會在其標籤清單中看到自訂的標籤或子標籤。

- 當您需要同時用於全域使用和個別私人小組的少量標籤時，請使用敏感度標籤。

- 當您有大量標籤，或想要將高度機密小組的標籤整理到高度機密檔案之多用途標籤之下時，請使用敏感度子標籤。

依照[下列指示](encryption-sensitivity-labels.md)，設定具有下列設定的不同標籤或子標籤：

- 標籤或子標籤的名稱中包含小組網站的名稱
- 已啟用加密
- 小組網站的 Microsoft 365 群組具有共同撰寫權限

建立之後，請為您的使用者發佈新的標籤或子標籤，讓他們能夠在檔案上傳至小組前先在本機的檔案套用標籤，或等到檔案儲存至小組時再套用。
 
您一旦使用，便能從 Microsoft Word、Excel 和 PowerPoint 的 [常用]**** 功能區中選取 [敏感度]**** 選項的靈敏度標籤。
  
> [!NOTE]
> 如果您有多個高度敏感度的 SharePoint Online 小組網站，即應建立多個靈敏度標籤。 
  
## <a name="adding-permissions-for-external-users"></a>新增外部使用者的權限
您可以使用兩種方式，將敏感度標籤所保護的檔案存取權授與外部使用者。 在這兩種情況下，外部使用者皆必須擁有 Azure AD 帳戶。 如果外部使用者不屬於使用 Azure AD 的組織成員，可以使用 [https://aka.ms/aip-signup](https://aka.ms/aip-signup) 這個註冊頁面，以個人身分取得 Azure AD 帳戶。

 - 將外部使用者新增至小組網站的 Microsoft 365 群組。 您必須先將帳戶新增為目錄中的 B2B 使用者。 當 [Azure Rights Management 進行群組成員資格的快取](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection)時，可能需要數小時的時間。  
 - 將外部使用者帳戶直接新增至標籤設定。 您可以從組織 (例如 Fabrikam.com)、Microsoft 365 群組 (例如組織內的財務部門) 或使用者，新增所有使用者。 例如，您可以將外部的監理人員小組新增至敏感度標籤的許可項目中。

## <a name="see-also"></a>另請參閱

[適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
