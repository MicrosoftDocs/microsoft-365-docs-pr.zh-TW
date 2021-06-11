---
title: 已報告訊息的系統管理員檢閱
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 瞭解如何查看所報告的訊息，並提供對您的使用者意見反應。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9e6969b6dee38135ee2d1d41bbcdb2561943d1fe
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878709"
---
# <a name="admin-review-for-reported-messages"></a>已報告訊息的系統管理員檢閱

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> 本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。 本檔僅供評估和探索之用。

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 具有 Exchange Online 信箱和 Microsoft Defender for Office 365 的組織中，管理員現在可以在查看報告的訊息之後，將範本化郵件傳送回給最終使用者。 您也可以根據系統管理員的判定，針對您的組織自訂此格式。

此功能的設計目的是要提供對使用者的意見反應，但不會變更系統中的郵件 verdicts。 為了協助 Microsoft 更新及改善其篩選，您必須提交郵件以供使用系統 [管理員提交](admin-submission.md)進行分析。

如果郵件被報告為 [誤報或漏報](report-false-positives-and-false-negatives.md)，您將只能標示及通知使用者的審閱結果。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？


- 您可以在中開啟 Microsoft 365 的安全性中心 <https://security.microsoft.com/> 。 若要直接移至 [ **提交** ] 頁面，請使用 <https://security.microsoft.com/reportsubmission> 。

- 若要修改使用者提交的設定，您必須是下列其中一個角色群組的成員：
  - [Microsoft 365 Security center](permissions-microsoft-365-security-center.md)中的組織管理或安全性管理員。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的組織管理。


- 您也需要 Exchange Online PowerShell 的存取權。 如果您嘗試使用的帳戶不具備 Exchange Online PowerShell 的存取權，您會收到錯誤，指出 *在您的網域中指定電子郵件地址*。 如需啟用或停用 Exchange Online PowerShell 存取權的詳細資訊，請參閱下列主題：
  - [啟用或停用 Exchange Online PowerShell 的存取權](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Exchange Online 中的用戶端存取規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>設定用來通知使用者的郵件

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** \> **其他**] 區段 \> **使用者報告的郵件設定**。

2. 在 [**使用者** 送出] 頁面上，如果您想要指定寄件者顯示名稱，請在 [系統管理] 的 [**電子郵件通知**] 區段中，選取 [**指定 Office 365 的電子郵件地址作為寄件者**] 的方塊，然後輸入您想要使用的名稱。 這是 Outlook 會顯示的電子郵件地址，以及回復會移至哪一個位置。

3. 如果您想要自訂任何範本，請按一下 [ **自訂電子郵件通知**]。 在這個浮出控制項中，您將可以自訂下列專案：
    - 網路釣魚
    - 垃圾
    - 找不到威脅
    - 認知訓練
    - 頁尾

4. 完成後，按一下 [儲存]。 若要清除這些值，請在 [使用者報送] 頁面上按一下 [ **放棄** ]。
