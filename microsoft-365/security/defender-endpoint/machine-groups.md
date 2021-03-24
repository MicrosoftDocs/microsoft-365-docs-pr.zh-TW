---
title: 在 Microsoft Defender ATP 中建立及管理裝置群組
description: 透過 confiring 在群組上套用的規則，建立裝置群組並設定其上的自動修正層級。
keywords: 裝置群組、群組、修正、層級、規則、aad 群組、角色、指派、排名
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dfc7c04bbde2b7061c92f5a25115b75a2f5b47b5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059412"
---
# <a name="create-and-manage-device-groups"></a>建立及管理裝置群組

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- Azure Active Directory
- Office 365

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


在企業案例中，一般會為安全性運作小組指派一組裝置。 這些裝置會根據一組屬性（如其網域、電腦名稱稱或指定的標記）組合在一起。

在 Microsoft Defender for Endpoint 中，您可以建立裝置群組，並使用這些群組進行下列作業：
- 將相關警示和資料的存取許可權制為具有[指派 RBAC 角色](rbac.md)的特定 Azure AD 使用者群組 
- 設定不同裝置組的不同自動修復設定
- 在自動調查期間指派要套用的特定修正層級
- 在調查中，請使用 **群組** 篩選，將 [**裝置] 清單** 篩選為 [僅限特定裝置群組]。

您可以在以角色為基礎的 access (RBAC) 中建立裝置群組，以控制誰可以採取特定動作或透過將裝置群組指派 (s) 指派給使用者群組，以控制誰可以採取特定動作或查看資訊。 如需詳細資訊，請參閱 [使用以角色為基礎的存取控制管理入口網站存取](rbac.md)。

>[!TIP]
> 如需 RBAC 應用程式的完整外觀，請參閱： [您的 SOC 是以 rbac 執行平整](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)。

在建立裝置群組的過程中，您會：
- 設定該群組的自動修正層級。 如需修正層級的詳細資訊，請參閱 [使用自動調查調查和修正威脅](automated-investigations.md)。
- 指定符合規則，判斷哪個裝置群組屬於根據裝置名稱、網域、標籤和 OS 平臺的群組。 如果裝置也符合其他群組，它只會新增至最高排名的裝置群組。
- 選取應該具有裝置群組存取權的 Azure AD 使用者群組。
- 在建立其他群組之後，對此裝置群組進行排名。

>[!NOTE]
>如果您未指派任何 Azure AD 群組，則所有使用者都可以存取裝置群組。

## <a name="create-a-device-group"></a>建立裝置群組

1. 在功能窗格中，選取 [**設定**  >  **裝置群組**]。

2. 按一下 [ **新增裝置群組**]。

3. 輸入 [組名] 和 [自動化] 設定，並指定用來判斷哪些裝置屬於群組的符合規則。 請參閱 [自動調查的開始方式](automated-investigations.md#how-the-automated-investigation-starts)。

    >[!TIP]
    >如果您想依組織單位群組裝置，您可以為群組從屬設定登錄機碼。 如需裝置標記的詳細資訊，請參閱 [Create and manage device tags](machine-tags.md)。

4. 預覽數個裝置，此規則將會符合此規則。 如果您對規則滿意，請按一下 [ **使用者存取** ] 索引標籤。

5. 指派可以存取您所建立之裝置群組的使用者群組。

    >[!NOTE]
    >您只可將存取權授與指派給 RBAC 角色的 Azure AD 使用者群組。

6. 按一下 [關閉 **]**。 設定變更。

## <a name="manage-device-groups"></a>管理裝置群組

您可以提升或降級裝置群組的排名，使其在比對的期間具有較高或較低的優先順序。 當裝置與一個以上的群組相符時，它只會新增至最高排名的群組。 您也可以編輯和刪除群組。

>[!WARNING]
>刪除裝置群組可能會影響電子郵件通知規則。 如果已在電子郵件通知規則下設定裝置群組，它會從該規則中移除。 如果設備群組是為電子郵件通知設定的唯一群組，則會與裝置群組一起刪除電子郵件通知規則。

依預設，所有具有入口網站存取權的使用者皆可存取裝置群組。 您可以將 Azure AD 使用者群組指派給裝置群組，以變更預設行為。

不符合任何群組的裝置會新增至取消群組裝置 (預設) 群組。 您無法變更此群組的排名或加以刪除。 不過，您可以變更此群組的修正層級，並定義可以存取此群組的 Azure AD 使用者群組。

>[!NOTE]
> 對裝置群組設定套用變更可能需要數分鐘的時間。

## <a name="related-topics"></a>相關主題

- [使用以角色為基礎的存取控制來管理入口網站存取](rbac.md)
- [建立及管理裝置標記](machine-tags.md)
- [使用 Graph API 取得租使用者群組的清單](https://docs.microsoft.com/graph/api/device-list-memberof)
