---
title: 上層網域郵件流程狀態深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以了解上方網域郵件流程狀態深入解析，在郵件流程儀表板中安全性 & 合規性中心。
ms.openlocfilehash: 1fb22ac1543c490dcbd316464803f5393003d503
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598880"
---
# <a name="top-domain-mail-flow-status-insight"></a>上層網域郵件流程狀態深入解析

**上層網域郵件流程狀態**深入了解提供您的目前狀態的郵件流程方面的貴組織的網域。 此深入了解可協助您找出並疑難排解網域的***郵件流程影響***遇到問題 （例如，無法接收外部電子郵件），尤其是網域到期日或網域不正確的 MX 記錄。

![上層網域流程狀態深入了解在郵件流程儀表板中安全性 & 合規性中心](../media/domain-mail-flow-status-selected.png)

當您按一下 [**檢視詳細資料**中深入了解時，彈出式視窗會顯示，以顯示更多詳細資料，每個網域的狀態。

網域的綠色核取記號表示目前的 MX 記錄 （當您瀏覽至郵件流程深入了解儀表板） 符合我們對記錄的值與網域已在過去兩小時期間收到電子郵件。

紅色的 x 網域會指出已經變更的 MX 記錄，並在網域已收到電子郵件不在過去的 6 個小時期間。 這可能表示，您的網域已過期，或 MX 記錄已正確更新。 請與您的網域註冊機構或 DNS 主機服務，才能查看如果網域已經過期，或者網域的 MX 記錄不正確。

![在上方網域流程狀態深入了解詳細資訊彈出式視窗](../media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a>另請參閱

如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。
