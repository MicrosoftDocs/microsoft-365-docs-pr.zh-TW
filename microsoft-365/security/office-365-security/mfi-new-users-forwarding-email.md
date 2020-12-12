---
title: 新使用者轉寄電子郵件深入解析
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以瞭解如何使用「安全性 & 規範中心」中的新使用者轉寄電子郵件，以調查組織中的使用者將郵件轉寄給新網域的時間。
ms.openlocfilehash: cf1852169279e19ac00e5e29dd1c26e155936039
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660014"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>新的使用者在安全性 & 合規性中心轉寄電子郵件洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


當您組織中的新使用者帳戶突然開始將電子郵件轉送至外部網域時，它會是可疑的。

當您組織中新建立的使用者將郵件轉寄給外部網域時，在 [安全性 & 合規性中心](https://protection.office.com)內 **轉寄的新網域** 會通知您。 這種情況可能表示使用已遭到損害的系統管理員帳戶來建立新的使用者。 如果您懷疑帳戶已遭破壞，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。

這種洞察力只會在偵測到問題時出現，而且會出現在 [ [轉接回報報告](view-mail-flow-reports.md#forwarding-report) ] 頁面上。

![新使用者轉寄電子郵件深入解析](../../media/mfi-new-users-forwarding-email.png)

當您按一下該小工具時，會出現一個快顯視窗，您可以在其中找到轉送郵件的詳細資料，包括「轉寄 [修改」報告](#forwarding-modifications-report) 的連結（如本文稍後所述）。

![按一下新的使用者轉寄電子郵件功能之後顯示的詳細資料浮出控制項](../../media/mfi-new-users-forwarding-email-details.png)

您也可以在 [ (**報表** 儀表板] 或 [) ] 的 [**熱門洞察力 & 建議**] 區域中按一下 [**全部查看**] 之後，取得此詳細資料頁面 \>  <https://protection.office.com/insightdashboard> 。

您可以按一下 [ **參閱與真知灼見相關的報告** ] 連結，以移至下一節所述的「轉寄 **修改」報告** 。

## <a name="forwarding-modifications-report"></a>轉送修改報告

[轉寄 **修改] 報告** 顯示從組織中寄件者自動轉寄之郵件的詳細資訊：

- 將郵件轉送至外部網域的新建立帳戶。
- 將郵件轉寄給外部網域的帳戶，而這些網域從未由組織中的其他寄件者轉寄。

這類轉寄郵件可能會帶來安全性或合規性風險，而且可能會指出已遭破壞的帳戶。

報告包含多達90天的資料。 根據預設，報告會顯示過去7天的資料。

在 [郵件流程儀表板](mail-flow-insights-v2.md) 或 [報表儀表板](view-mail-flow-reports.md)中，無法直接使用此報告。 除了按一下 **新使用者轉寄電子郵件** 內容中的 **真知灼見連結相關聯的參閱報告** 之外，您還可以透過下列方式取得報告：

- 按一下 [要轉寄電子郵件網路洞察力之新網域](mfi-new-domains-being-forwarded-email.md)詳細資料中的「轉寄 **通知報告**」連結。
- 開啟 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。

### <a name="report-view-for-the-forwarding-modifications-report"></a>「轉寄修改」報告的報表檢視

報表檢視提供下列圖表：

- **顯示下列專案的資料：新增轉接使用者**：

  ![「轉發修改」報告中的新轉寄使用者視圖](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **顯示下列專案的資料：新增轉送網域**：

  ![「轉發修改」報告中的新轉寄網域視圖](../../media/forwarding-modifications-report-new-forwarded-domains.png)

如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>「轉寄修改」報告的詳細資料表格視圖

如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：

- **顯示下列專案的資料：新增轉接使用者**：

  - **名稱**：寄件者的電子郵件地址。
  - **轉送類型**
  - **收件者位址**
  - **詳細資料**
  - **Count**
  - **第一個轉寄日期**

- **顯示下列專案的資料：新增轉送網域**：

  - **名稱**：寄件者的電子郵件網域。
  - **轉送類型**
  - **收件者位址**
  - **詳細資料**
  - **Count**
  - **第一個轉寄日期**

如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。

如果您從表格選取某一列，則會顯示 **詳細資料** 快顯視窗，並顯示下列資訊：

- **名稱**：這是寄件者的電子郵件地址 (來自 **：新增轉寄使用者** ] view) 或寄件者的電子郵件網域 (**顯示下列的資料：新增轉寄網域** view) 。
- **轉送類型**
- **收件者**
- **詳細資料**
- **Count**
- **開始日期**
- **建議**：從這裡，您可以按一下 [Microsoft 365 系統管理中心] 中的 [管理使用者] 連結。

![「轉發修改」報告中新轉寄使用者 view 的詳細資料表格中的詳細資料。](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

若要回到 [報告] 視圖，請按一下 [ **查看報告**]。

## <a name="related-topics"></a>相關主題

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。
