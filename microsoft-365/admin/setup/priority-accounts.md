---
title: 管理及監視優先順序帳戶
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: 監視寄件者或寄件者對具有高業務影響之帳戶的失敗及延遲的電子郵件。
ms.openlocfilehash: 053246da7f57c46045bfc777bc4de981ce51c6e5
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794186"
---
# <a name="manage-and-monitor-priority-accounts"></a>管理及監視優先順序帳戶

在 Microsoft 365 組織的系統管理員中，您現在可以監控傳送給使用者的失敗或延遲的電子郵件訊息，其具有高業務影響，例如 CEO。 您可以將使用者新增至您的優先順序帳戶清單以啟用此功能。 優先順序帳戶是執行組織時必不可少的帳戶。 新增具有敏感或高優先順序資訊存取權、主管、主管或其他使用者。

## <a name="access-priority-accounts"></a>存取優先順序帳戶

本主題中所述的優先順序帳戶功能僅適用于符合下列兩項需求的組織：

- Office 365 E3 或 Microsoft 365 E3，或 Office 365 E5 或 Microsoft 365 E5。
- 至少10000個授權，以及至少50個每月使用中 Exchange Online 使用者。

## <a name="add-priority-accounts-from-the-setup-page"></a>從設定頁面新增優先順序帳戶

在 [ **設定] 頁面**中新增優先順序帳戶。

1. 移至 Microsoft 365 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。

3. 選擇 [ **開始** ] 或 [ **管理**]。

4. 在 [ **新增優先順序帳戶** ] 頁面上的搜尋欄位中，輸入您要新增至 [優先順序帳戶] 清單之人員的名稱或電子郵件地址。 您也可以針對失敗或延遲的電子郵件設定電子郵件閾值，並取得優先順序帳戶問題的每週報告。

5. 選取使用者，然後選擇 [ **儲存**]。

您也可以從 [作用中的使用者] 頁面新增優先順序帳戶。

### <a name="add-priority-accounts-from-active-users-page"></a>從 [作用中使用者新增優先順序帳戶] 頁面

從 [作用中的使用者] 頁面新增優先順序帳戶。

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

2. 移至 [**使用者**作用  >  中**使用者**]，然後選擇頁面頂端的 **[...** ]。 選取 [ **管理優先順序帳戶**]。

3. 選取 [ **新增帳戶**]，然後在 [ **新增優先順序帳戶** ] 頁面的 [搜尋] 欄位中，輸入您要新增至 [優先順序帳戶] 清單的人員名稱。

4. 選取使用者，然後選擇 [ **儲存**]。

## <a name="monitor-your-priority-accounts"></a>監視您的優先順序帳戶

您可以在 [ **設定** ] 頁面的 [Microsoft 365 系統管理中心] 中，監控優先順序帳戶的電子郵件狀態。 您可以主動監控最多250個帳戶。

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

2. 選取 [**安裝**]，然後選擇 [**高級監控**] 旁邊的 [**查看**]，以查看優先順序帳戶的狀態。

## <a name="email-issues-for-priority-accounts"></a>優先順序帳戶的電子郵件問題

您可以在 Exchange 系統管理中心中，移至優先順序帳戶報告的 **電子郵件問題** ，以追蹤優先順序帳戶的電子郵件問題。 如需詳細資訊，請參閱 [優先順序帳戶的電子郵件問題](https://review.docs.microsoft.com/en-us/Exchange/mail-flow-best-practices/mail-flow-insights/mfi-email-issues-for-priority-accounts?branch=Priority-chrisda)。

## <a name="remove-a-user-from-the-priority-accounts-list"></a>從 [優先順序帳戶] 清單中移除使用者

1. 移至 Microsoft 365 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。

3. 在 [**監視您的大部分帳戶**] 頁面上，選擇 [**管理此功能**] 底下的 [**優先順序帳戶**]。

4. 在 [ **優先順序帳戶** ] 頁面上，選取您要從清單中移除的使用者，然後選擇 [ **移除帳戶**]。