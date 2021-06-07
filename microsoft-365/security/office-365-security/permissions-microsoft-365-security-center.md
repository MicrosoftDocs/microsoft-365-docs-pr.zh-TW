---
title: Microsoft 365 安全性中心的權限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 系統管理員可以了解如何在 Microsoft 365 安全性中心管理與安全性相關的所有工作的權限。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c2d28510c25290921084e6a238fa8c781c35624
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772464"
---
# <a name="permissions-in-the-microsoft-365-security-center"></a>Microsoft 365 安全性中心的權限

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

您需要管理橫跨所有 Microsoft 365 服務的安全性案例。 而且您需要靈活地為組織中的合適人員提供正確的管理員權限。

<https://security.microsoft.com> 的 Microsoft 365 安全性中心支援直接管理在 Microsoft 365 中執行安全性工作的使用者的權限。 透過使用安全性中心管理權限，您可以集中管理與安全性相關的所有工作權限。

要在安全性中心内管理權限，移至 **[權限和角色]** 或 <https://security.microsoft.com/securitypermissions>。 您需要是 **全域系統管理員** 或安全性中心中 **組織管理** 角色群組的成員。 具體來說，**角色管理** 角色允許使用者在安全性中心檢視、建立和修改角色群組，預設情況下，該角色僅分配給 **組織管理** 角色群組。

## <a name="relationship-of-members-roles-and-role-groups"></a>成員、角色和角色群組的關係

安全性中心的權限是根據角色型存取控制 (RBAC) 權限模型。 RBAC 與大多數 Microsoft 365 服務使用的權限模型相同，因此如果您熟悉這些服務中的權限結構，那麼就會非常熟悉如何在安全性中心授予權限。

**角色** 會授予執行工作集的權限。

**角色群組** 是一組讓人員在安全性中心完成工作的角色。 例如，攻擊模擬器管理員角色群組包含攻擊模擬器管理員角色，以建立和管理攻擊模擬培訓的所有方面。

安全性中心的預設角色群組包含必須指派給人員的最常見工作和功能。 通常，我們建議您只要將個別使用者新增為預設角色群組的 **成員**。

![圖表顯示角色群組和角色及成員的關係](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-security-center"></a>安全性中心的角色和角色群組

安全性中心的 **權限和角色** 中提供以下類型的角色和角色群組:

- **Azure AD 角色**: 可以檢視角色和指派使用者，但不能直接在安全性中心進行管理。 Azure AD 角色是為 **所有** Microsoft 365 服務指派權限的中心角色。

- **電子郵件和共同作業角色**: 這些角色群組與安全性和合規性中心中可用的角色群組相同，但您可以直接在安全性中心管理它們。 你在此處指派的權限僅用於 Microsoft 365 安全性中心、Microsoft 365 合規性中心和安全性與合規性中心，並不涵蓋其他 Microsoft 365 工作負載所需的所有權限。

![Microsoft 365 安全性中心的權限和角色頁面](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-security-center"></a>安全性中心的 Azure AD 角色

當您移至 **電子郵件和共同作業角色** \> **權限和角色** \> **Azure AD 角色** \> **角色**（或直接轉到 <https://security.microsoft.com/aadpermissions>）時，您將看到本章節中描述的 Azure AD 角色。

選取角色時，會出現一個包含角色描述和使用者作業的詳細資料飛出視窗。 但是要管理這些作業，您需要在詳細資料飛出視窗中點擊 **[管理 Azure AD 中的成員]**。

![在 Azure Active Directory 中管理權限的連結](../../media/permissions-manage-in-azure-ad-link.png)

如需詳細資訊，請參閱 [在 Azure Active Directory 中檢視和指派系統管理員角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

<br>

****

|角色|描述|
|---|---|
|**全域管理員**|可以存取所有 Microsoft 365 服務中的所有系統管理功能。 只有全域管理員才能指派其他系統管理員角色。 如需詳細資訊，請參閱[全域系統管理員／公司系統管理員](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)。|
|**合規性資料管理員**|可以追蹤 Microsoft 365 中的組織資料，確保其受到保護，並深入了解任何問題以協助降低風險。 如需詳細資訊，請參閱[合規性資料系統管理員](/azure/active-directory/roles/permissions-reference#compliance-data-administrator)。|
|**合規性系統管理員**|可幫助您的組織遵守任何法規要求、管理電子文件探索案例，並維護 Microsoft 365 各個位置、身分和應用程式的資料監管原則。 如需詳細資訊，請參閱 [合規性系統管理員](/azure/active-directory/roles/permissions-reference#compliance-administrator)。|
|**安全性操作員**|可檢視、調查和回應 Microsoft 365 使用者、裝置和內容所受的主動威脅。 如需詳細資訊，請參閱 [安全性運算子](/azure/active-directory/roles/permissions-reference#security-operator)。|
|**安全性讀取者**|可檢視和調查 Microsoft 365 使用者、裝置和內容所受的主動威脅，但是 (與安全性運算子不同) 他們沒有透過採取行動而回應的權限。 如需詳細資訊，請參閱 [安全性讀取者](/azure/active-directory/roles/permissions-reference#security-reader)。|
|**安全性系統管理員**|可透過管理安全性原則、檢視 Microsoft 365 各項產品的安全性分析和報告，以及在威脅環境中保持最新速度，來控制組織的整體安全性。 如需詳細資訊，請參閱 [安全性系統管理員](/azure/active-directory/roles/permissions-reference#security-administrator)。|
|**全域讀取者**|**全域系統管理員** 角色的唯讀版本。 在 Microsoft 365 中檢視所有設定和管理資訊。 如需詳細資訊，請參閱 [全域讀取者](/azure/active-directory/roles/permissions-reference#global-reader)。|
|**攻擊模擬系統管理員**|建立和管理 [攻擊模擬系統](attack-simulation-training.md) 創建、模擬的啟動/排程，以及模擬結果審查的所有方面。 詳細資訊，請參閲 [攻擊模擬系統管理員](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)。|
|**攻擊承載作者**|建立攻擊承載，但不實際啟動或排程它們。 如需詳細資訊，請參閱 [攻擊承載作者](/azure/active-directory/roles/permissions-reference#attack-payload-author)。|
|

### <a name="email--collaboration-roles-in-the-security-center"></a>安全性中心中的電子郵件和共同作業角色

當您移至 **電子郵件和共同作業角色** \> **權限和角色** \> **電子郵件和共同作業角色** \> **角色**（或直接轉到 <https://security.microsoft.com/emailandcollabpermissions>）時，您將看到安全性與合規性中心中可用的相同角色群組。

如需有關這些角色群組的詳細資訊，請參閱 [安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)。

#### <a name="modify-email--collaboration-role-membership-in-the-security-center"></a>修改安全性中心中的電子郵件和共同作業角色成員資格

1. 在安全性中心，移至 **電子郵件和共同作業角色** \> **權限和角色** \> **電子郵件和共同作業角色** \> **角色**。

2. 在 **權限** 頁面中，從清單中開啟和選取要修改的角色群組。 您可以點擊 **[名稱]** 資料行標題，以按名稱進行排序，也可以點擊 **[搜尋]** ![[搜尋圖示]](../../media/m365-cc-sc-search-icon.png) 來查找角色群組。

3. 在顯示角色群組詳細資料的飛出視窗中，按一下 **[成員]** 章節中的 **[編輯]**。

4. 在出現的 **[正在編輯選擇成員]** 頁面執行下列其中一項操作:
   - 如果沒有角色群組成員，請點擊 **[選擇成員]**。
   - 如果有現有的角色群組成員，請點擊 **[編輯]**。

5. 在出現的 **[選擇成員]** 飛出視窗執行下列其中一項操作:

   - 點擊 **[新增]**。 在出現的使用者清單中，選取一個或多個使用者。 或者，您可以點擊 **[搜尋]** ![[搜尋圖示]](../../media/m365-cc-sc-search-icon.png) 以找出和選取使用者。

     選好要新增的使用者後，點擊 **[新增]**。

   - 點擊 **[移除]**。 選取下列一個或多個現有的成員。 或者，您可以點擊 **[搜尋]** ![[搜尋圖示]](../../media/m365-cc-sc-search-icon.png) 以找出和選取成員。

     選好要移除的使用者後，點擊 **[移除]**。

6. 返回 **[選擇成員]** 飛出視窗，點擊 **[完成]**。

7. 返回 **[正在編輯選擇成員]** 頁面，點擊 **[儲存]**。

8. 返回角色群組詳細資料飛出視窗，點擊 **[完成]**。
