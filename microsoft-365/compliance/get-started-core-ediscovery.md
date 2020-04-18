---
title: Microsoft 365 中的核心 eDiscovery 案例快速入門
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明如何開始使用 Microsoft 365 中的核心 eDiscovery。 指派 eDiscovery 許可權並建立案例之後，您可以新增成員、建立 eDiscovery 保留，然後搜尋並匯出與調查相關的資料。
ms.openlocfilehash: 838870f60c55c82225c3809aa8f281beadd0dba1
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551391"
---
# <a name="get-started-with-core-ediscovery"></a>開始使用核心電子檔探索

Microsoft 365 中的核心 eDiscovery 提供一種基本 eDiscovery 工具，可讓組織用來搜尋並匯出 Microsoft 365 和 Office 365 中的內容。 您也可以使用核心 eDiscovery，在內容位置（例如 Exchange 信箱、SharePoint 網站、OneDrive 帳戶和 Microsoft 小組）上進行 eDiscovery 暫止。 不需要部署核心 eDiscovery，但在您的組織開始使用核心 eDiscovery 來搜尋、匯出及保留內容之前，必須先完成一些必要的工作，IT 系統管理員和 eDiscovery 管理員才能開始使用。

本文討論設定核心 eDiscovery 所需的步驟。 這包括確保存取核心 eDiscovery 所需的適當授權，並在內容位置上放置 eDiscovery 保留，以及將許可權指派給您的 IT、法律和調查小組，讓他們能夠存取及管理案例。 本文也提供使用案例來搜尋及匯出內容的高層次概述。

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>步驟1：確認並指派適當的授權

核心 eDiscovery 的授權要求適當的組織訂閱和每一使用者授權。

- **組織訂閱：** 若要存取 Microsoft 365 規範中心或 Office 365 安全性 & 規範中心的核心 eDiscovery，以及使用保留與匯出功能，您的組織必須具有 Microsoft 365 E3 或 Office 365 E3 訂閱或更高版本。

- **每位使用者授權：** 若要在使用者信箱上進行 eDiscovery 暫止，必須根據您的組織訂閱，為該使用者指派下列其中一個授權：

  - Microsoft 365 E3 或 Office 365 E3 授權或更高版本

  - Microsoft 365 E1 或 Office 365 E1 授權與 Exchange Online 方案2或 Exchange Online 封存附加元件授權

  如需如何指派授權的詳細資訊，請參閱[將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

如需 Microsoft 365 和 Office 365 授權的相關資訊，請下載並參閱[microsoft 365 合規性授權比較](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.pdf)中的「探索 & 回應」方案。

## <a name="step-2-assign-ediscovery-permissions"></a>步驟2：指派 eDiscovery 許可權

若要存取核心 ediscovery 或新增為核心 eDiscovery 案例的成員，必須對使用者指派適當的許可權。 具體而言，使用者必須新增為 Office 365 安全性 & 合規性中心內的 eDiscovery 管理員角色群組成員。 這個角色群組的成員可以建立及管理核心 eDiscovery 案例。 他們可以新增及移除成員、為使用者放置 eDiscovery 暫止功能、建立及編輯搜尋，以及從核心 eDiscovery 案例中匯出內容。

完成下列步驟，將使用者新增至 eDiscovery 管理員角色群組：

1. 移至[https://protection.office.com/permissions](https://protection.office.com/permissions)並使用您的 Microsoft 365 或 Office 365 組織中的系統管理員帳戶的認證登入。

2. 在 [**許可權**] 頁面上，選取 [ **eDiscovery 管理員**] 角色群組。

3. 在 [eDiscovery 管理員飛出] 頁面上，按一下 [ **Ediscovery 管理員**] 區段旁邊的 [**編輯**]。

4. 在 [編輯角色群組] 嚮導的 [**選擇 EDiscovery 管理員**] 頁面上，按一下 **[選擇探索管理員**]。

5. 按一下 [**新增**]，然後選取您要新增至角色群組之所有使用者的核取方塊。

6. 按一下 [**新增**] 以新增選取的使用者，然後按一下 [**完成**]。

7. 按一下 [**儲存**]，將使用者新增至角色群組，然後按一下 [**關閉**] 完成步驟。

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>EDiscovery 管理員角色群組的詳細資訊

EDiscovery 管理員角色群組中有兩個子群組。 這些子群組之間的差異是以範圍為基礎。

- **EDiscovery 管理員：** 可以查看和管理其所建立或屬於的核心 eDiscovery 案例。 如果另一個 eDiscovery 管理員建立了案例，但沒有將第二個 eDiscovery 管理員新增為該案例的成員，則第二個 eDiscovery 管理員將無法在規範中心的核心 eDiscovery 頁面上查看或開啟此案例。 一般說來，您組織中的大部分人員都可以新增至 eDiscovery Manager 子組。

- **EDiscovery 管理員：** 可以執行 eDiscovery 管理員可以執行的所有案例管理工作。 此外，電子檔探索管理員也可以：

  - 查看核心 eDiscovery 頁面上列出的所有案例。
  
  - 管理組織中的任何案例後，將自己新增為案例成員。

  - 針對組織中的任何案例，存取及匯出案例資料。

  因為存取範圍廣泛，所以組織應該只有少數管理員是 eDiscovery Administrators 子群組的成員。

如需有關 eDiscovery 許可權的詳細資訊，以及指派給 eDiscovery 管理員角色群組之每個角色的說明，請參閱[指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。

## <a name="step-3-create-a-core-ediscovery-case"></a>步驟3：建立核心 eDiscovery 案例

下一步是建立案例，並開始使用核心 eDiscovery。 完成下列步驟以建立案例並新增成員。 建立案例的使用者會自動新增為成員。

1. 移至[https://compliance.microsoft.com](https://compliance.microsoft.com)並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。 組織管理角色群組的成員也可以建立核心 eDiscovery 案例。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [ **eDiscovery > Core**]。

3. 在 [**核心電子**檔探索] 頁面上，按一下 [**建立案例**]。

4. 在 [**新案例**飛入] 頁面上，為案例提供名稱（必要），然後輸入選用的案例編號及描述。 案例名稱在您的組織中必須是唯一的。

5. 按一下 [**儲存**] 以建立案例。

   在核心 eDiscovery 頁面上建立及顯示新案例。 您可能**需要按一下 [** 重新整理] 以顯示新的案例。 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>步驟4（選用）：將成員新增至核心 eDiscovery 案例

如果您在步驟3中建立案例，而且您是唯一會使用此案例的人員，則您不需要執行此步驟。 您可以開始使用案例來建立 eDiscovery 保留、搜尋內容或匯出搜尋結果。 如果您想要授與其他使用者（或角色群組）存取案例，請執行此步驟。

1. 在 Microsoft 365 規範中心的**核心 eDiscovery**頁面上，按一下您要新增成員的案例名稱。

2. 在 [**管理此案例**飛入] 頁面上的 [**管理成員**] 底下，按一下 [**新增**] 以將成員新增至案例。 

    您也可以選擇新增角色群組做為案例的成員。 在 [**管理角色群組**] 底下，按一下 [**新增**]。 您只能將您所屬的角色群組指派給案例。 這是因為角色群組控制誰可以指派成員至 eDiscovery 案例。

3. 在可以新增為案例成員的人員或角色群組清單中，按一下您要新增之人員（或角色群組）名稱旁邊的核取方塊。 如果您有很多可以新增為成員的人員清單，請使用**搜尋**方塊來搜尋清單中的特定人員。
  
4. 選取要新增為案例成員的人員或角色群組之後，按一下 [**新增**]。

5. 按一下 [**儲存**] 儲存新的案例成員清單。

## <a name="explore-the-core-ediscovery-workflow"></a>探索核心 eDiscovery 工作流程

為了讓您開始使用核心 eDiscovery，以下是簡單的工作流程，可為感興趣的人員建立 eDiscovery 保留，搜尋與調查相關的內容，然後匯出該資料以進一步複查。 在上述每個步驟中，我們也會強調您可以探索的一些擴充核心 eDiscovery 功能。

![核心 eDiscovery 工作流程](../media/CoreEdiscoveryWorkflow.png)

1. **[建立 eDiscovery 保留](create-ediscovery-holds.md)**。 在建立案例之後的第一個步驟是在調查中所關注之人員的內容位置保留（也稱為*eDiscovery 保留*）。 內容位置包含 Exchange 信箱、SharePoint 網站、OneDrive 帳戶，以及與 Microsoft 團隊和 Office 365 群組相關聯的信箱和網站。 這是選用的步驟，建立 eDiscovery 保留可在調查期間保留與案例相關的內容。 當您建立 eDiscovery 暫止功能時，您可以保留特定內容位置中的所有內容，也可以建立查詢型保留，只保留符合保留查詢的內容。 除了保留內容之外，另一個建立 eDiscovery 保留的最佳原因是，在下一個步驟中建立和執行搜尋時，請快速搜尋內容位置（而不是必須選取要搜尋的各個位置）。 完成調查之後，您可以放開您建立的任何保留。

2. **[搜尋內容](search-for-content-in-core-ediscovery.md)**。 在您建立 eDiscovery 保留後，請使用內建的搜尋工具來搜尋保留中的內容位置。 您也可以在其他內容位置搜尋可能與案例相關的資料。 您可以建立及執行與案例相關聯的不同搜尋。 您可以使用關鍵字、屬性和條件來[建立搜尋查詢](keyword-queries-and-search-conditions.md)，以利用最可能與案例相關的資料傳回搜尋結果。 您也可以：

   - 查看可協助您縮小搜尋查詢以縮小結果的搜尋統計資料。

   - 預覽搜尋結果，以快速確認是否找到相關資料。

   - 修改查詢，然後重新執行搜尋。

3. **[匯出及下載搜尋結果](export-content-in-core-ediscovery.md)**。 搜尋並找出與調查相關的資料之後，您可以將其匯出至 Office 365，以供調查小組以外的人員複查。 匯出資料的過程分為兩個步驟。 第一步是在不在 Office 365 的情況下，匯出搜尋結果。 若要完成此工作，您可以將搜尋結果複製到 Microsoft 提供的 Azure 儲存位置。 下一步是使用 eDiscovery 匯出工具，將內容下載到本機電腦。 除了匯出的資料檔案之外，匯出套件也包含匯出報告、摘要報告及錯誤報表。
