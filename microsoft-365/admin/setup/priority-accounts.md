---
title: 管理和監視優先帳戶
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
ms.openlocfilehash: 2a58f4090244fc6d68be69cf6b3c8ab6e00874fa
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535803"
---
# <a name="manage-and-monitor-priority-accounts"></a>管理和監視優先帳戶

在每個 Microsoft 365 組織中，都有重要的人員，例如主管、負責人、主管或其他具有敏感、專有或高優先順序資訊存取權的使用者。

為了協助您的組織保護這些帳戶，您現在可以將特定使用者指定為優先順序帳戶，並利用可提供額外保護的應用程式特定功能。 在未來，其他應用程式和功能將支援優先順序帳戶，若要開始，我們已宣告兩項功能： **優先順序帳戶保護** 和 **優質郵件流程監控**。

- **Priority account protection** -Microsoft Defender for Office 365 (過去 Office 365 的「高級威脅防護」) 支援優先順序帳戶，作為可在警示、報告和調查篩選中使用的標記。 如需詳細資訊，請參閱[Microsoft Defender 中的使用者標記以取得 Office 365](../../security/office-365-security/user-tags.md)。

  「自然問題」是「所有使用者都不是優先順序？ 為何不將所有使用者指定為優先順序帳戶？ 是的，所有使用者都是優先順序，但優先順序帳戶保護提供下列額外優點：

  - **其他試探法**：我們在 Microsoft 資料中心內分析郵件流程，表示公司主管的郵件流程模式與平均員工不同。 「優先順序帳戶保護」提供額外的試探法，特別針對公司主管所定制，對一般員工沒有益處。
  - **報表的其他可見度**：實際上，所有使用者的資訊 (或所有受影響的使用者) ，都已存在於警示、報告和調查中。 [優先順序帳戶] 標記為篩選，可讓您特別瞄準調查。

- **進階版郵件 Flow 監控**-狀況良好的郵件流程對商務成功來說可能很重要，且傳遞延遲或失敗可能會對業務造成負面影響。 您可以針對失敗或延遲的電子郵件選擇臨界值，當超過該臨界值時接收通知，然後查看優先順序帳戶的電子郵件問題報告。 如需詳細資訊，請參閱 [新式 EAC 中優先順序帳戶報告的電子郵件問題](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

如需優先順序帳戶的安全性最佳作法，請參閱 [優先順序帳戶的安全性建議](../../security/office-365-security/security-recommendations-for-priority-accounts.md)。

## <a name="before-you-begin"></a>開始之前

本主題中所述的「 **優先順序帳戶保護** 」功能僅適用于符合下列需求的組織：

- 適用于 Office 365 方案2（包括具有 Office 365 E3、Office 365 E5、Microsoft 365 E5 或 Microsoft 365 E5 安全性的 Microsoft Defender）。

本主題中所述 **進階版郵件 Flow 監控** 功能僅適用于符合下列需求的組織：

- 您的組織必須具有至少10000的授權計數、下列產品之一或其組合中的產品： Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。 例如，您的組織可能會有 3000 Office 365 E3 授權和 8500 Microsoft 365 E5，共提供合格產品的11500授權。
- 您的組織每月至少需要有 50 位作用中 Exchange Online 使用者。

> [!NOTE]
> 您可以監控最多250個優先順序的帳戶。

當您對信箱套用優先順序帳戶保護時，您也應該對擁有信箱存取權的使用者套用優先順序帳戶保護 (例如，CEO 及 CEO 的執行助理負責管理 CEO 的行事曆) 。

### <a name="add-priority-accounts-from-the-setup-page"></a>從設定頁面新增優先順序帳戶

在 [ **設定] 頁面** 中新增優先順序帳戶。

1. 前往 Microsoft 365 系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。

3. 選取 [**入門**] 或 [**管理**]。

4. 在 [ **新增優先順序帳戶** ] 頁面上的搜尋欄位中，輸入您要新增至 [優先順序帳戶] 清單之人員的名稱或電子郵件地址。 您也可以針對失敗或延遲的電子郵件設定電子郵件閾值，並取得優先順序帳戶問題的每週報告。

5. 選取使用者，然後選擇 [ **儲存**]。

您也可以從 [作用中的使用者] 頁面新增優先順序帳戶。

### <a name="add-priority-accounts-from-active-users-page"></a>從 [作用中使用者新增優先順序帳戶] 頁面

從 [作用中的使用者] 頁面新增優先順序帳戶。

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

2. 移至 [**使用者**] [作用中的  >  **使用者**]，然後在頁面頂端 ([其他動作]) 的三個點。 選取 [ **管理優先順序帳戶**]。

3. 選取 [ **新增帳戶**]，然後在 [ **新增優先順序帳戶** ] 頁面的 [搜尋] 欄位中，輸入您要新增至 [優先順序帳戶] 清單的人員名稱。

4. 選取使用者，然後選擇 [ **儲存**]。

## <a name="remove-a-user-from-the-priority-accounts-list"></a>從 [優先順序帳戶] 清單中移除使用者

1. 前往 Microsoft 365 系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。

3. 在 [**監視您的大部分帳戶**] 頁面上，選擇 [**管理此功能**] 底下的 [**優先順序帳戶**]。

4. 在 [ **優先順序帳戶** ] 頁面上，選取您要從清單中移除的使用者，然後選擇 [ **移除帳戶**]。

## <a name="related-topics"></a>相關主題

[在 Microsoft 365 中使用優先順序帳戶](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
