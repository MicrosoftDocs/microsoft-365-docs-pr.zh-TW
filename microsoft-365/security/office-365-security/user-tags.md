---
title: Microsoft Defender for Office 365 中的使用者標記
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Microsoft Defender for Office 365 方案2中識別具有使用者標記的特定使用者群組。 標記篩選可用於 Office 365 的 Microsoft Defender 中的提醒、報告和調查，以快速識別已標記的使用者。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f98dcfe3e8c44e852134e7a12def4ff78c1bcdd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203776"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的使用者標記

> [!NOTE]
> 使用者標記功能是在預覽中，並非所有人都可以使用，而且可能會變更。 如需發行排程的相關資訊，請參閱 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。

使用者標記是 [Microsoft Defender For Office 365](defender-for-office-365.md)中特定使用者群組的識別碼。 使用者標記有兩種類型：

- **系統標記**：目前， [優先順序帳戶](../../admin/setup/priority-accounts.md) 是唯一的系統標記類型。
- **自訂標記**：您可以自行建立這些使用者標記。

如果您的組織擁有 Office 365 的 Defender for Office 方案 2 (包含在您的訂閱中或作為附加元件) ，除了使用 [優先順序帳戶] 標記之外，您還可以建立自訂使用者標記。

在您將系統標記或自訂標記套用至使用者後，您可以使用這些標記做為預警、報告和調查中的篩選器：

- [安全性 & 規範中心的警示](alerts.md)
- [威脅瀏覽器和即時偵測](threat-explorer.md)
- [威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)
- [行銷活動檢視](campaigns.md)
- 針對優先順序帳戶，您可以使用 Exchange 系統管理中心的 [優先順序帳戶] 報告 (EAC) 中的 [電子郵件問題](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) 。

本文說明如何在安全性 & 規範中心內設定使用者標記。 安全性 & 合規性中心內沒有 Cmdlet 可管理使用者標記。

若要查看使用者標記屬於策略的一部分，以協助保護高影響的使用者帳戶，請參閱 [Microsoft 365 中優先順序帳戶的安全性建議](security-recommendations-for-priority-accounts.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **使用者標記** ] 頁面，請開啟] <https://protection.office.com/userTags> 。

- 您必須先獲得 [安全性與合規性中心] 指派的權限，才能使用此文章中的程序：
  - 若要建立、修改和刪除使用者標記，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要在現有的使用者標記中新增及移除成員，您必須是「 **組織管理**」、「 **安全性管理員**」或「 **安全操作員** 」角色群組的成員。
  - 若要唯讀的使用者標記存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - 使用者標記管理是由「 **標記讀取器** 」和「標籤 **管理員** 」角色所控制。

- 您也可以在 Microsoft 365 admin center 中管理及監視優先順序帳戶。 如需相關指示，請參閱 [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md)。

## <a name="use-the-security--compliance-center-to-create-user-tags"></a>使用安全性 & 規範中心建立使用者標記

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **使用者標記**。

2. 在開啟的 [ **使用者標記** ] 頁面上，按一下 [ **建立標記**]。

3. [ **建立** 標籤] 嚮導會在新飛出時開啟。在 [ **定義標記** ] 頁面上，設定下列設定：
   - **名稱**：輸入標記的唯一描述性名稱。 這是您會看到和使用的值。
   - **描述**：輸入標記的選用描述。

   完成後，按 [下一步]。

4. 在 [ **指派使用者** ] 頁面上，執行下列其中一個步驟：

   - 按一下 [ **新增使用者**]。 在 [飛出顯示] 中，執行下列其中一個步驟，以新增個別使用者或群組：
     - 在方塊中按一下，然後在清單中向內移動，以選取使用者或群組。
     - 在方塊中按一下並輸入，以篩選清單並選取使用者或群組。
     - 若要新增其他值，請按一下方塊中的空白區域。
     - 若要從方塊中移除個別專案， 請 ![ 在方塊中按一下使用者或群組上的 [移除移除圖示] ](../../media/scc-remove-icon.png) 核取方塊。
     - 若要從方塊下方的清單中移除現有的專案，請按一下 [ **移除** ![ 移除圖示] ](../../media/scc-remove-icon.png) 專案。

     完成後，按一下 **[新增]**。

   - 按一下 [匯 **入** ]，選取包含使用者或群組之電子郵件地址的文字檔。 請確定文字檔包含每行一個專案。

   完成後，按 [下一步]。

5. 在 [ **複查標記** ] 頁面上，複查您的設定。 您可以按一下 [特定] 區段中的 [ **編輯** ]，以進行變更。

   當您完成時，按一下 [ **提交**]。

## <a name="use-the-security--compliance-center-to-view-user-tags"></a>使用安全性 & 規範中心來查看使用者標記

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **使用者標記**。

2. 在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標籤 (不要按一下核取方塊) 。

3. 在顯示的唯讀詳細資訊飛出狀態中，複查設定。

   完成時，請按一下 [關閉]。

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a>使用安全性 & 規範中心來修改使用者標記

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **使用者標記**。

2. 在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標記，然後按一下 [ **編輯標記**]。

3. [原則] 嚮導會在 [ **編輯] 標記** 飛出的狀態中開啟。按 **[下一步]** 以複查及修改設定。

   當您完成時，按一下 [ **提交**]。

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a>使用安全性 & 規範中心移除使用者標記

**附注**：您無法移除內建的 [ **優先順序] 帳戶** 標記。

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **使用者標記**。

2. 在開啟的 [ **使用者標記** ] 頁面上，選取您要移除的使用者標籤，按一下 [ **刪除** 標籤]，然後選取 [ **是]，** 然後在顯示的警告中移除。