---
title: 在 Microsoft 365 中設定高級 eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 本文說明如何設定高級 eDiscovery，讓您可以開始建立及管理案例。 此外，它也會說明必要的 Microsoft 訂閱和授權。 完成一些快速步驟之後，就可以使用「高級 eDiscovery」工具。
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841174"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>設定 Microsoft 365 Advanced eDiscovery

Microsoft 365 中的「高級 eDiscovery」提供 [端對端工作流程](overview-ediscovery-20.md#advanced-ediscovery-workflow) ，可保留、收集、審查、分析和匯出回應組織內部和外部調查的資料。 不需要部署高級 eDiscovery，但是必須先執行一些必要的工作，IT 系統管理員和 eDiscovery 管理員必須完成，您的組織才可以開始建立及使用高級 eDiscovery 案例來管理調查。

本文討論設定高級 eDiscovery 所需的步驟。 這包括確保存取高級 eDiscovery 及將保管人新增至案例，以及將許可權指派給法律和調查小組以供存取及管理案例所需的適當授權。

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>步驟1：確認並指派適當的授權

「高級 eDiscovery」的授權需要適當的組織訂閱和每一使用者授權。

- **組織訂閱：** 若要存取 Microsoft 365 規範中心或安全性 & 規範中心的高級 eDiscovery，您的組織必須具備下列其中一項：

  - Microsoft 365 E5 或 Office 365 E5 訂閱
  
  - 含 E5 合規性附加元件的 Microsoft 365 E3 訂閱

  - 具有 E5 電子檔探索和審核附加元件的 Microsoft 365 E3 訂閱

  如果您沒有現有的 Microsoft 365 E5 計畫，且想要嘗試使用 Advanced eDiscovery，您可以 [將 microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 至現有的訂閱，或註冊 Microsoft 365 E5 的 [試用版](https://www.microsoft.com/microsoft-365/enterprise) 。

- **每位使用者授權：** 若要在預先 eDiscovery 案例中將使用者新增為系統管理員，該使用者必須根據您的組織訂閱，被指派下列其中一個授權：

  - Microsoft 365：使用者必須被指派 Microsoft 365 E5 授權、E5 相容性附加元件授權或 E5 eDiscovery 和審核附加元件授權。

  - Office 365：使用者必須獲指派 Office 365 E5 授權。

   如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

> [!NOTE]
> 使用者只需要 E5 授權 (或適當的附加元件授權) ，以在高級 eDiscovery 案例中新增為保管人。 IT 系統管理員、eDiscovery 管理員、律師、paralegals 或調查人員，使用高級 eDiscovery 來管理案例及審閱案例資料，不需要 E5 或附加元件授權。

## <a name="step-2-assign-ediscovery-permissions"></a>步驟2：指派 eDiscovery 許可權

若要存取高級 eDiscovery 或新增為高級 eDiscovery 案例的成員，必須對使用者指派適當的許可權。 具體說來，使用者必須新增為安全性 & 規範中心的 eDiscovery 管理員角色群組成員。 這個角色群組的成員可以建立及管理高級 eDiscovery 案例。 他們可以新增及移除成員、將保管人和內容位置置於保留狀態、管理合法保留通知、建立及編輯案例中相關聯的搜尋、將搜尋結果新增至審閱集、分析複查集中的資料，以及從高級 eDiscovery 案例匯出及下載。

完成下列步驟，將使用者新增至 eDiscovery 管理員角色群組：

1. 移至 [https://protection.office.com/permissions](https://protection.office.com/permissions) 並使用您的 Microsoft 365 組織中的系統管理員帳戶的認證登入。

2. 在 [ **許可權** ] 頁面上，選取 [ **eDiscovery 管理員** ] 角色群組。

3. 在 [eDiscovery 管理員飛出] 頁面上，按一下 [ **Ediscovery 管理員**] 區段旁邊的 [**編輯**]。

4. 在 [編輯角色群組] 嚮導的 [ **選擇 Ediscovery 管理員** ] 頁面上，按一下 **[選擇 ediscovery 管理員**]。

5. 按一下 [ **新增** ]，然後選取您要新增至角色群組之所有使用者的核取方塊。

6. 按一下 [ **新增** ] 以新增選取的使用者，然後按一下 [ **完成**]。

7. 按一下 [ **儲存** ]，將使用者新增至角色群組，然後按一下 [ **關閉** ] 完成步驟。

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>EDiscovery 管理員角色群組的詳細資訊

EDiscovery 管理員角色群組中有兩個子群組。 這些子群組之間的差異是以範圍為基礎。

- **EDiscovery 管理員：** 可以查看和管理其所建立或其成員的高級 eDiscovery 案例。 如果另一個 eDiscovery 管理員建立了案例，但沒有將第二個 eDiscovery 管理員新增為該案例的成員，則第二個 eDiscovery 管理員將無法在「規範中心」的 [高級 eDiscovery] 頁面上，查看或開啟此案例。 一般說來，您組織中的大部分人員都可以新增至 eDiscovery Manager 子組。

- **EDiscovery 管理員：** 可以執行 eDiscovery 管理員可以執行的所有案例管理工作。 此外，電子檔探索管理員也可以：

  - 查看 [高級 eDiscovery] 頁面上列出的所有案例。
  
  - 管理組織中的任何案例後，將自己新增為案例成員。

  - 針對組織中的任何案例，存取及匯出案例資料。

  因為存取範圍廣泛，所以組織應該只有少數管理員是 eDiscovery Administrators 子群組的成員。

如需有關 eDiscovery 許可權的詳細資訊，以及指派給 eDiscovery 管理員角色群組之每個角色的說明，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>步驟3：設定高級電子檔探索的全域設定

在貴組織中的人員開始建立及使用案例之前完成的最後一個步驟，就是設定適用于組織中所有案例的全域設定。 目前只有一個全域設定是 *律師-用戶端許可權偵測* (未來) 會提供更多全域設定。 當您分析考核集中的資料時，此設定可讓律師-用戶端許可權模型執行。 模型使用電腦學習，判斷檔中包含法律性質的內容的可能性。 此外，它也會比較檔的參與者清單 (在您設定模型) 時所提交的律師清單，以判斷檔是否至少有一個擁有者的參與者。

如需設定和使用律師-用戶端許可權偵測模型的詳細資訊，請參閱 [Advanced eDiscovery 中的設定律師-用戶端許可權偵測](attorney-privilege-detection.md)。

> [!NOTE]
> 這是選擇性的步驟，您可以隨時執行。 未實施律師-用戶端許可權偵測模型不會妨礙您建立及使用高級 eDiscovery 案例。

## <a name="next-steps"></a>後續步驟

在您設定高級 eDiscovery 後，您就可以 [建立案例](create-and-manage-advanced-ediscoveryv2-case.md)。
