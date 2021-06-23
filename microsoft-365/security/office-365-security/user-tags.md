---
title: Microsoft Defender 中 Office 365 的使用者標記
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Microsoft Defender 的使用者標記中識別特定的使用者群組，以 Office 365 方案2。 標記篩選可用於 Office 365 的通知、報告和調查中，以快速識別已標記的使用者。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ac53891e0eb106ab3681251cc4cb8c969b51f8a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083113"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的使用者標記

> [!NOTE]
> 使用者標記功能是在預覽中，並非所有人都可以使用，而且可能會變更。 如需發行排程的相關資訊，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。

使用者標記是 Microsoft Defender 中的特定使用者群組的識別碼，[以供 Office 365](defender-for-office-365.md)。 使用者標記有兩種類型：

- **系統標記**：目前， [優先順序帳戶](../../admin/setup/priority-accounts.md) 是唯一的系統標記類型。
- **自訂標記**：您可以自行建立這些使用者標記。

如果您的組織擁有 Office 365 方案中的 Defender， (包含在您的訂閱中或附加元件) 中，除了使用 [優先順序帳戶] 標籤之外，您還可以建立自訂使用者標記。

> [!NOTE]
> 目前您只能將使用者標記套用至信箱使用者。

在您將系統標記或自訂標記套用至使用者後，您可以使用這些標記做為預警、報告和調查中的篩選器：

- [提醒](alerts.md)
- [自訂警示原則](../../compliance/alert-policies.md#viewing-alerts)
- [威脅瀏覽器和即時偵測](threat-explorer.md)
- [電子郵件實體頁面](mdo-email-entity-page.md#other-innovations)
- [威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)
- [行銷活動檢視](campaigns.md)
- 針對優先順序帳戶，您可以使用 Exchange 系統管理中心的「優先順序帳戶」報告 (EAC) 中的[電子郵件問題](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。

本文說明如何在 Microsoft 365 Defender 入口網站中設定使用者標記。 Microsoft 365 Defender 入口網站中沒有 Cmdlet 來管理使用者標記。

若要查看使用者標記屬於策略的一部分，以協助保護高影響的使用者帳戶，請參閱[Microsoft 365 中優先順序帳戶的安全性建議](security-recommendations-for-priority-accounts.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您於 <https://security.microsoft.com/> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [ **使用者標記** ] 頁面，請開啟] <https://security.microsoft.com/securitysettings/userTags> 。

- 您必須在 Microsoft 365 Defender 入口網站中指派許可權，才能執行本文中的程式：
  - 若要建立、修改和刪除使用者標記，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要在現有的使用者標記中新增及移除成員，您必須是「 **組織管理**」、「 **安全性管理員**」或「 **安全操作員** 」角色群組的成員。
  - 若要唯讀的使用者標記存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱 [Microsoft 365 Defender 入口網站中的權限](permissions-microsoft-365-security-center.md)。

  > [!NOTE]
  >
  > - 將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - 使用者標記管理是由「 **標記讀取器** 」和「標籤 **管理員** 」角色所控制。

- 您也可以在 Microsoft 365 系統管理中心中管理及監視優先順序帳戶。 如需相關指示，請參閱 [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md)。

- 如需 (系統管理員帳戶) 保護 _特權帳戶_ 的詳細資訊，請參閱 [本主題](/azure/architecture/framework/security/critical-impact-accounts)。

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>使用 Microsoft 365 Defender 入口網站建立使用者標記

1. 在 Microsoft 365 Defender 入口網站中，移至 **設定** \> **電子郵件 &** 共同作業 \> **使用者標記**。

2. 在 [ **使用者標記** ] 頁面上，按一下 [ ![ 建立標記圖示 ](../../media/m365-cc-sc-create-icon.png) **建立標記**]。

3. [ **建立** 標籤] 嚮導會在新飛入的視窗中開啟。 在 [ **定義標記** ] 頁面上，設定下列設定：
   - **名稱**：輸入標記的唯一描述性名稱。 這是您會看到和使用的值。 請注意，您在建立標記之後，您無法將其重新命名。
   - **描述**：輸入標記的選用描述。

   完成後，按 [下一步 **]**。

4. 在 [ **指派成員** ] 頁面上，執行下列其中一個步驟：
   - 按一下 [ ![ 新增成員] 圖示 [ ](../../media/m365-cc-sc-create-icon.png) **新增成員**]。 在 [飛出顯示] 中，執行下列其中一個步驟，以新增個別使用者或群組：
     - 在方塊中按一下，然後在清單中向內移動，以選取使用者或群組。
     - 在方塊中按一下並輸入，以篩選清單並選取使用者或群組。
     - 若要新增其他值，請按一下方塊中的空白區域。
     - 若要移除個別專案，請按一下 ![移除專案圖示](../../media/m365-cc-sc-remove-selection-icon.png) 方塊中的條目旁邊。
     - 若要移除所有專案，請按一下方塊 ![ ](../../media/m365-cc-sc-remove-selection-icon.png) 上 **所選 nn 使用者和 nn 群組** 專案上的 [移除專案圖示]。

     完成後，按一下 **[新增]**。

     回到 [ **指派成員** ] 頁面上，您也可以按一下 ![ 專案旁邊的 [刪除圖示] 來移除專案 ](../../media/m365-cc-sc-delete-icon.png) 。

   - 按一下 [匯 **入** ]，選取包含使用者或群組之電子郵件地址的文字檔。 請確定文字檔包含每行一個專案。

   完成後，按 [下一步 **]**。

5. 在出現的 [ **複查標記** ] 頁面上，複查您的設定。 您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。

   完成後，請按一下 [ **提交**]，然後按一下 [ **完成**]。

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>使用 Microsoft 365 Defender 入口網站來查看使用者標記

1. 在 Microsoft 365 Defender 入口網站中，移至 **設定** \> **電子郵件 &** 共同作業 \> **使用者標記**。

2. 在 [ **使用者標記** ] 頁面上，下列屬性會顯示在使用者標記清單中：

   - **Tag**： user 標記的名稱。 請注意，這包括內建的 **優先順序帳戶** 系統標記。
   - **適用** 于：成員數目
   - **上次修改日期**
   - **建立時間**

3. 當您按一下名稱來選取使用者標記時，詳細資料會顯示在浮出控制項中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>使用 Microsoft 365 Defender 入口網站修改使用者標記

1. 在 Microsoft 365 Defender 入口網站中，移至 **設定** \> **電子郵件 &** 共同作業 \> **使用者標記**。

2. 在 [ **使用者標記** ] 頁面上，選取清單中的 [使用者] 標籤，然後按一下 [ ![ 編輯標記圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯標記**]。

3. 在出現的 [詳細資料] 浮出控制項中，您可以使用本文前面的[使用 Microsoft 365 Defender 入口網站建立使用者標記](#use-the-microsoft-365-defender-portal-to-create-user-tags)一節所述的相同嚮導和設定。

   **附註**：

   - [ **定義** 標籤] 頁面不適用於內建的「 **優先順序帳戶** 」系統磁碟區標，所以您無法重新命名此標記或變更描述。
   - 您無法重新命名自訂標記，但您可以變更描述。

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>使用 Microsoft 365 Defender 入口網站移除使用者標記

> [!NOTE]
> 您無法移除內建的 [ **優先順序帳戶** 系統] 標記。

1. 在 Microsoft 365 Defender 入口網站中，移至 **設定** \> **電子郵件 &** 共同作業 \> **使用者標記**。

2. 在 [ **使用者標記** ] 頁面上，從清單中選取 [使用者] 標籤，然後按一下 [ ![ 刪除標記圖示] [ ](../../media/m365-cc-sc-delete-icon.png) **刪除** 標籤]。

3. 閱讀出現的確認對話方塊中的警告，然後按一下 [ **是]，[移除**]。
