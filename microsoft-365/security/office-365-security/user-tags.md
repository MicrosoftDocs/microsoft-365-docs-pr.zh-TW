---
title: 使用者標記
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Oiffce 365 ATP 方案2中識別具有使用者標記的特定使用者群組。 標記篩選可用於 Office 365 ATP 中的提醒、報告和調查，以快速識別已標記的使用者。
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210021"
---
# <a name="user-tags-in-the-microsoft-security-center"></a>Microsoft Security Center 中的使用者標記

使用者標記是 [Office 365 Advanced 威脅防護 (ATP) ](office-365-atp.md)中的特定使用者群組識別碼。 [優先順序帳戶](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 是一種使用者標記。 如果您的組織有 Office 365 ATP 方案 2 (包含在您的訂閱中，或作為附加元件) ，除了使用 [優先順序帳戶] 標記之外，您還可以建立自訂使用者標記。

在您對特定使用者套用標記之後，您可以使用這些標記做為警示、報告和調查中的篩選器：

- [安全性 & 規範中心的警示](alerts.md)
- [威脅瀏覽器和即時偵測](threat-explorer.md)
- [威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)
- [行銷活動檢視](campaigns.md)

本文說明如何在 [安全性中心] 中設定使用者標記。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您可以在中開啟 [安全性中心] <https://security.microsoft.com/> 。 若要直接移至 [ **使用者標記** ] 頁面，請開啟] <https://security.microsoft.com/securitysettings/userTags> 。

- 若要建立、修改或移除使用者標記，您必須是 Security & 合規性中心內「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。 如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

- 您也可以在 Microsoft 365 admin center 中管理及監視優先順序帳戶。 如需相關指示，請參閱 [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。

## <a name="use-the-security-center-to-create-user-tags"></a>使用安全中心建立使用者標記

1. 在 [安全性中心] 中，移至 [ **設定** \> **電子郵件 & 協同**] \> **使用者標記**。

2. 在開啟的 [ **使用者標記** ] 頁面上，按一下 [ **建立標記**]。

3. [ **建立** 標籤] 嚮導會在新飛出時開啟。在 [ **定義標記** ] 頁面上，設定下列設定：

   - **名稱**：輸入標記的唯一描述性名稱。 這是您會看到和使用的值。

   - **描述**：輸入標記的選用描述。

   完成後，按 [下一步]****。

4. 在 [ **指派信箱** ] 頁面上，執行下列其中一個步驟：

   - 按一下 [ **新增信箱**]。 在 [飛出顯示] 中，執行下列其中一個步驟，以新增個別使用者或群組：

     - 在方塊中按一下，然後在清單中向內移動，以選取使用者或群組。
     - 在方塊中按一下並輸入，以篩選清單並選取使用者或群組。
     - 若要新增其他值，請按一下方塊中的空白區域。
     - 若要從方塊中移除個別專案， **Remove**請 ![ 在方塊中按一下使用者或群組上的 [移除移除圖示] ](../../media/scc-remove-icon.png) 核取方塊。
     - 若要從方塊下方的清單中移除現有的專案，請按一下 [ **移除** ![ 移除圖示] ](../../media/scc-remove-icon.png) 專案。

     完成後，請按一下 [ **新增**]。

   - 按一下 [匯 **入** ]，選取包含使用者或群組之電子郵件地址的文字檔。 請確定文字檔包含每行一個專案。

   完成後，按 [下一步]****。

5. 在 [ **複查標記** ] 頁面上，複查您的設定。 您可以按一下 [特定] 區段中的 [ **編輯** ]，以進行變更。

   當您完成時，按一下 [ **提交**]。

## <a name="use-the-security-center-to-view-user-tags"></a>使用安全中心來查看使用者標記

1. 在 [安全性中心] 中，移至 [ **設定** \> **電子郵件 & 協同**] \> **使用者標記**。

2. 在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標籤 (不要按一下核取方塊) 。

3. 在顯示的唯讀詳細資訊飛出狀態中，複查設定。

   完成時，請按一下 [關閉]****。

## <a name="use-the-security-center-to-modify-user-tags"></a>使用 [安全性中心] 修改使用者標記

1. 在 [安全性中心] 中，移至 [ **設定** \> **電子郵件 & 協同**] \> **使用者標記**。

2. 在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標記，然後按一下 [ **編輯標記**]。

3. [原則] 嚮導會在 [ **編輯] 標記** 飛出的狀態中開啟。按 **[下一步]** 以複查及修改設定。

   當您完成時，按一下 [ **提交**]。

## <a name="use-the-security-center-to-remove-user-tags"></a>使用安全中心來移除使用者標記

**附注**：您無法移除內建的 [ **優先順序] 帳戶** 標記。

1. 在 [安全性中心] 中，移至 [ **設定** \> **電子郵件 & 協同**] \> **使用者標記**。

2. 在開啟的 [ **使用者標記** ] 頁面上，選取您要移除的使用者標籤，按一下 [ **刪除**標籤]，然後選取 [ **是]，** 然後在顯示的警告中移除。
