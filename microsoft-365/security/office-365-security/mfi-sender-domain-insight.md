---
title: 修正寄件者網域深入解析
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
description: 系統管理員可以深入瞭解安全性 & 規範中心的郵件流程儀表板中的修正寄件者網域洞察力。
ms.openlocfilehash: a416b4d15ff52a611f00a88de8440c749ff08ad3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635169"
---
# <a name="fix-sender-domain-insight"></a>修正寄件者網域深入解析

Microsoft 365 需要從內部內部部署電子郵件環境傳送至 Microsoft 365 的郵件，以符合特定的安全性準則：

- 您已在 Microsoft 365 中建立輸入連接器，以利用來源 IP 位址或憑證來驗證來自內部部署電子郵件伺服器的 SMTP 連線。

- 您已設定內部部署電子郵件伺服器，透過 Microsoft 365 將電子郵件轉送至外部世界。

- 在您的設定中，下列其中一個表述為真：

  - 寄件者的電子郵件網域已在您的組織中註冊。 如需詳細資訊，請參閱在 Office 365 中新增網域。

  - 您的內部部署電子郵件伺服器設定為使用憑證將電子郵件傳送至 Microsoft 365，該憑證包含或完全符合您在 Microsoft 365 中註冊的功能變數名稱，而且您已在 Microsoft 365 中以該網域建立一個以憑證為基礎的連接器。 

不符合準則的郵件將不會歸對組織，而且可能會遭到拒絕。

**Fix sender domain**真知灼見會向您顯示來自內部部署環境的電子郵件，但不符合準則，可協助您識別內部部署電子郵件環境中可能遭到破壞的機器和使用者帳戶，並協助您採取修正動作。

![在安全性 & 規範中心的郵件流程儀表板中，修正寄件者網域的洞察力](../../media/sender-domain-insight-selected.png)

當您按一下 [**查看詳細資料**] 時，會移至另一個包含更多詳細資料的小工具，如下列圖表所示：

![Fix sender domain 真知灼見中的詳細資料小工具](../../media/sender-domain-view-details.png)

您會看到用來將郵件傳遞到 Office 365 的輸入連接器。 您也可以按一下 [ **view sample message IDs** ]，以查看從您的內部部署電子郵件環境傳送的郵件詳細資訊。 因為這些郵件是由 Office 365 拒絕，所以您無法使用郵件追蹤，但是您可以使用示範郵件識別碼來追蹤內部部署電子郵件環境中的郵件。

![View a Fix sender domain 真知灼見中的示範郵件識別碼](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a>另請參閱

如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。
