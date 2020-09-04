---
title: 郵件流程儀表板中的未傳遞回報
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用 [安全性 & 合規性中心內的郵件流程儀表板中的 [未傳遞詳細資料] 報告，以監視未傳遞回報中最常遇到的錯誤碼 (也稱為 NDRs 或退回的郵件) 來自組織中的寄件者。
ms.openlocfilehash: f9017a7f041037c5db2dc9b9f4f5155b038bf2c7
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357407"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>安全性 & 規範中心內的未傳遞回報

在[Security & 合規性中心](https://protection.office.com)的[郵件流程儀表板](mail-flow-insights-v2.md)中，**未傳遞**回報會顯示未傳遞回報中最常遇到的錯誤碼 (也稱為 NDRs 或退回的郵件) 針對您組織中的使用者。 此報告顯示 NDRs 的詳細資料，以便您能夠疑難排解電子郵件傳遞問題。

![安全性 & 規範中心內郵件流程儀表板中的未傳遞回報小工具](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>未傳遞回報的報表檢視

按一下 [ **未傳遞** 回報] 小工具時，將會帶您前往 **未傳遞**回報的報告。

依預設，會顯示所有錯誤碼的活動。 如果您按一下 [ **顯示資料**]，您可以從下拉式清單中選取特定的錯誤碼。

如果您將滑鼠停留在特定色彩上 (錯誤碼) 在圖表中的某一天，您就會看到錯誤的郵件總數。

![不接受的網域報告中的報表檢視](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>未傳遞回報的詳細資料表格視圖

如果您按一下報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：

- **Date**
- **未傳遞回報碼**
- **Count**
- **範例郵件**：郵件 IDs 受影響郵件的範例。

如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期**的日期範圍。

若要將特定日期範圍的報告傳送至一或多個收件者，請按一下 [ **要求下載**]。

當您選取表格中的一列時，會出現一個快顯視窗，其中包含下列資訊：

- **Date**
- **未傳遞回報碼**：您可以按一下連結，以尋找特定錯誤碼的原因和解決方案的詳細資訊。
- **Count**
- **範例郵件**：您可以按一下 [ **View sample messages** ]，以查看受影響郵件之範例的 [郵件追蹤](message-trace-scc.md) 結果。

![在未傳遞回報中，選取 [詳細資料表格] 視圖中的列之後的詳細資料浮出控制項](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>相關主題

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。
