---
title: 郵件流程儀表板中的最上層網域郵件流程狀態洞察力
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
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全性 & 規範中心內郵件流程儀表板中的最上層網域郵件流程狀態，來疑難排解與電子郵件網域中的 MX 記錄相關的郵件流程問題。
ms.openlocfilehash: 6366e3aee0ab50096f1396776397c80fabc8aaf2
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577744"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>安全性 & 規範中心內的最上層網域郵件流程狀態洞察力

安全性 & 合規性中心內的[郵件流程儀表板](mail-flow-insights-v2.md)中的**最上層網域郵件流程狀態**，可讓您在郵件流程方面，為您組織的網域提供目前的狀態。 這種洞察力可協助您識別及疑難排解發生***郵件流程影響***問題的網域 (例如，無法接收外部電子郵件) ，尤其是網域到期或具有不正確 MX 記錄的網域。

![安全性 & 規範中心內郵件流程儀表板中的上方網域流程狀態構件](../../media/mfi-top-domain-mail-flow-status-widget.png)

當您按一下小工具中的 [**查看詳細資料**] 時，會出現一個**網域狀態**快顯視窗，顯示每個網域狀態的詳細資訊：

- **網域**
- **先前的 MX 記錄**
- **目前的 MX 記錄**
- **電子郵件接收狀態**
- **網域狀態**：綠色核取記號表示在您按一下小工具時 (目前的 MX 記錄，) 符合我們記錄的值，而且該網域已于過去的兩個小時內收到電子郵件。

  紅色 X 表示 MX 記錄已變更，且在過去6小時內，該網域未收到任何電子郵件。 這可能表示您的網域已到期，或 MX 記錄的更新錯誤。 請洽詢網域註冊機構或 DNS 主機服務，以查看網域是否已過期，或網域的 MX 記錄是否不正確。

您可以按一下 [ **View more** ]，以查看更多網域的相同資訊。

![最上層網域郵件流程狀態洞察力中的詳細資料快顯視窗](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>相關主題

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱[Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。
