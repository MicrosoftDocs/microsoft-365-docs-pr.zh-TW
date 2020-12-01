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
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477610"
---
# <a name="manage-and-monitor-priority-accounts"></a>管理及監視優先順序帳戶

在每個 Microsoft 365 組織中，有重要的人員，也就是主管、領導者、主管或其他具有敏感、專有或高優先順序資訊存取權的使用者。

為了協助您的組織保護這些帳戶，您現在可以將特定使用者指定為優先順序帳戶，並利用可提供額外保護的應用程式特定功能。 在未來，其他應用程式和功能將支援優先順序帳戶，若要開始，我們已宣告兩項功能： **優先順序帳戶保護** 和 **優質郵件流程監控**。

- **優先順序帳戶保護** -Microsoft Defender for office 365 (過去是 office 365 的「高級威脅防護」) 支援優先順序帳戶，作為可在警示、報告和調查篩選中使用的標記。 如需詳細資訊，請參閱 [Microsoft Defender For Office 365 中的使用者標記](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)。
- **優質郵件流程監控** -狀況良好的郵件流程對商務成功來說可能很重要，且傳遞延遲或失敗可能對業務造成負面影響。 您可以針對失敗或延遲的電子郵件選擇臨界值，當超過該臨界值時接收通知，然後查看優先順序帳戶的電子郵件問題報告。 如需詳細資訊，請參閱 [新式 EAC 中「優先順序帳戶」報告的電子郵件問題](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。

## <a name="before-you-begin"></a>開始之前

本主題中所述的「 **優先順序帳戶保護** 」功能僅適用于符合下列需求的組織：

- Microsoft Defender for Office 365 方案2，包括具備 Office 365 E3 的 office 365 E5、Microsoft 365 E5 或 Microsoft 365 E5 Security。

本主題中所述的 **高級郵件流程監控** 功能僅適用于符合下列需求的組織：

- 您的組織必須具有至少10000的授權計數，也就是下列產品的其中一個或下列產品的組合： Office 365 E3，Microsoft 365 E3，Office 365 E5，Microsoft 365 E5。 例如，您的組織可以有 3000 Office 365 E3 授權和 8500 Microsoft 365 E5，以提供來自合格產品的全部11500授權。
- 您的組織必須至少要有50個月的活動 Exchange Online 使用者。

> [!NOTE]
> 您可以監控最多250個優先順序的帳戶。

### <a name="add-priority-accounts-from-the-setup-page"></a>從設定頁面新增優先順序帳戶

在 [ **設定] 頁面** 中新增優先順序帳戶。

1. 移至 Microsoft 365 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。

3. 選擇 [ **開始** ] 或 [ **管理**]。

4. 在 [ **新增優先順序帳戶** ] 頁面上的搜尋欄位中，輸入您要新增至 [優先順序帳戶] 清單之人員的名稱或電子郵件地址。 您也可以針對失敗或延遲的電子郵件設定電子郵件閾值，並取得優先順序帳戶問題的每週報告。

5. 選取使用者，然後選擇 [ **儲存**]。

您也可以從 [作用中的使用者] 頁面新增優先順序帳戶。

### <a name="add-priority-accounts-from-active-users-page"></a>從 [作用中使用者新增優先順序帳戶] 頁面

從 [作用中的使用者] 頁面新增優先順序帳戶。

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

2. 移至 [**使用者** 作用中  >  **使用者**]，然後選擇頁面頂端 **的 [...** ]。 選取 [ **管理優先順序帳戶**]。

3. 選取 [ **新增帳戶**]，然後在 [ **新增優先順序帳戶** ] 頁面的 [搜尋] 欄位中，輸入您要新增至 [優先順序帳戶] 清單的人員名稱。

4. 選取使用者，然後選擇 [ **儲存**]。

## <a name="remove-a-user-from-the-priority-accounts-list"></a>從 [優先順序帳戶] 清單中移除使用者

1. 移至 Microsoft 365 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。

3. 在 [**監視您的大部分帳戶**] 頁面上，選擇 [**管理此功能**] 底下的 [**優先順序帳戶**]。

4. 在 [ **優先順序帳戶** ] 頁面上，選取您要從清單中移除的使用者，然後選擇 [ **移除帳戶**]。

## <a name="related-topics"></a>相關主題

[在 Microsoft 365 中使用優先順序帳戶](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)