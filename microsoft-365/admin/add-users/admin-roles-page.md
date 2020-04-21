---
title: 關於系統管理員角色
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: svidican
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: 系統管理員角色會與商務功能對應，並提供在系統管理中心執行特定工作的權限。 例如，服務系統管理員向 Microsoft 開啟支援票證。
ms.openlocfilehash: 85952f1f64db0e1ae94d9c5f69e5c95f7f9c2dab
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43618869"
---
# <a name="get-started-with-the-roles-page"></a>「角色」頁面快速入門

在 [角色] 頁面上，您可以授與使用者在系統管理中心執行工作的許可權。 這可協助您的組織將工作散佈給適當的人員，並協助保護您的資料安全。

:::image type="content" source="../../media/roles-main-page.png" alt-text="顯示系統管理員角色的圖形":::

> [!TIP]
> 正在尋找詳細的角色描述嗎？ 請參閱[Azure Active Directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)和相關的系統[管理角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

## <a name="about-the-admin-roles-page"></a>關於系統管理員角色頁面

您可以匯出系統管理員清單，以及依角色進行搜尋及篩選。

:::image type="content" source="../../media/admin-role-page-options.png" alt-text="篩選或匯入系統管理員角色":::

|||
|:-----|:-----|
|  <br/> |使用 [**匯出系統管理員] 清單**可取得組織中所有系統管理員使用者的完整清單。 清單儲存在 Excel .csv 檔案中。   <br/> |
|  <br/> |使用 [**搜尋**] 搜尋系統管理員角色，並查看指派給該角色的使用者。   <br/> |
|  <br/> |使用**Filter**變更所顯示之系統管理員角色的視圖。   <br/> |

## <a name="get-the-most-out-of-the-roles"></a>充分利用角色

閱讀下列內容，瞭解不同的系統管理員角色，以及這些角色可在您的組織中執行的工作。

> [!NOTE]
這不是這些角色所具備之擁有權限的完整清單。 選取 [**深入瞭解**] 連結，以取得每個角色的詳細資訊。

### <a name="exchange-admin"></a>Exchange 系統管理員

將 Exchange 系統管理員角色指派給需要查看及管理使用者的電子郵件信箱、Microsoft 365 群組和 Exchange Online 的使用者。 他們也可以開啟和管理 Microsoft 支援服務要求。 [深入了解](https://docs.microsoft.com/office365/admin/add-users/about-exchange-online-admin-role)

### <a name="global-admin"></a>全域系統管理員

將全域系統管理員角色指派給需要透過 Microsoft online 服務對大部分管理功能和資料進行全域存取的使用者。 授與太多的使用者全域存取權會造成安全性風險，因此建議您擁有 2 到 4 個之間的全域系統管理員。 只有全域系統管理員可以重設所有使用者的密碼，並新增及管理網域。 他們也可以開啟和管理 Microsoft 支援服務要求。 註冊 Microsoft online 服務的人員會自動成為全域系統管理員。[深入瞭解](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

### <a name="global-reader"></a>全域讀取者

將全域讀取者系統管理員角色指派給使用者必須在全域管理員可以查看之所有系統管理中心中查看系統管理功能和設定的使用者。 全域讀取器系統管理員角色無法編輯任何設定。 [深入了解](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

### <a name="helpdesk-admin"></a>服務台系統管理員

將「服務台管理員」角色指派給想要重設密碼的使用者，強制使用者登出任何安全性問題。 他們也可以開啟和管理 Microsoft 支援服務要求。 服務台管理員只會協助非系統管理員的使用者和使用者指派這些角色：目錄讀取者、來賓 inviter、服務台管理員、郵件中心讀取程式和報告讀取器。 [深入了解](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

### <a name="service-admin"></a>服務系統管理員

將服務系統管理員角色指派給需要建立 Azure、Microsoft 365 和 Office 365 服務之服務要求的使用者。 [深入了解](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

### <a name="sharepoint-admin"></a>SharePoint 系統管理員

當您購買 Microsoft 365 訂閱時，會自動建立小組網站，全域管理員會設為主要網站集合管理員。 將 SharePoint 系統管理員角色指派給您想要存取 SharePoint 系統管理中心的使用者。 具有 SharePoint 系統管理員角色的使用者可以建立及管理網站集合、指定網站集合管理員，以及管理使用者設定檔。 具有 SharePoint 系統管理員角色的使用者也可以管理 Microsoft 365 群組，並透過 Microsoft 支援服務要求開啟服務要求。 [深入了解](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

### <a name="teams-service-admin"></a>Teams 服務管理員

將「小組管理員」角色指派給您想要存取和管理小組 & Skype 系統管理中心的使用者。 擁有「小組管理員」角色的使用者也可以管理 Microsoft 365 群組，並透過 Microsoft 支援服務要求開啟服務要求。 [深入了解](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)

### <a name="user-admin"></a>使用者系統管理員

將使用者系統管理員角色指派給您想要存取和管理使用者密碼重設及管理使用者和群組的使用者。 他們也可以開啟和管理 Microsoft 支援服務要求。 [深入了解](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

::: moniker range="o365-worldwide"

## <a name="compare-roles"></a>比較角色

您現在可以一次比較最多3個角色的許可權，這樣您就能找到最小的可指派角色。

在系統管理中心：

- 最多選取3個角色，然後選擇 [**比較角色**]，以查看每個角色擁有的許可權。

:::image type="content" source="../../media/compare-roles-list.png" alt-text="顯示系統管理員角色比較的圖形":::

::: moniker-end
