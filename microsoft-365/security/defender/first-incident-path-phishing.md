---
title: 網路釣魚電子郵件攻擊的範例
description: 逐步分析網路釣魚攻擊的範例。
keywords: 事件, 警示, 調查, 關聯, 攻擊, 電腦, 裝置, 使用者, 身分識別, 身分識別, 信箱, 電子郵件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114568"
---
# <a name="example-of-a-phishing-email-attack"></a>網路釣魚電子郵件攻擊的範例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

Microsoft 365Defender 可協助偵測透過電子郵件傳遞的惡意附件。 因為[Office 365 安全性與合規性中心](https://protection.office.com/)會與 Microsoft 365 Defender 整合，所以安全性分析分析員可以深入瞭解來自于 Office 365 的威脅，例如透過電子郵件附件。

例如，分析員已被指派多階段事件。
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="多階段事件範例"::: 

在事件的 [**警示**] 索引標籤中，會顯示來自 Office 365 和 Microsoft Cloud App Security 的 Defender 的警示。 分析者可以透過選取電子郵件訊息警示，深入查看 Office 365 警示的 Defender。 警示的詳細資料會顯示在側邊窗格上。

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="電子郵件警示的範例":::
 
進一步展開時，會顯示詳細資訊，顯示受到影響的惡意檔案和使用者。

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="電子郵件警示的使用者與檔影響的範例":::
  
選取 [ **開啟警示] 頁面** 會帶您前往特定警示，透過此連結，您可以更詳細地查看各種資訊。 您可以透過選取 [ **在瀏覽器中查看訊息** 朝] 面板的底部來查看實際的電子郵件訊息。
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="警示詳細資料的範例"::: 

這會讓分析員使用「威脅管理」頁面，其中會顯示電子郵件主旨、收件者、寄件者及其他資訊。 「**特殊動作**」下的 **ZAP** 會告知分析員已執行零小時自動清除功能。 ZAP 會自動偵測組織中信箱的惡意和垃圾郵件，並從中移除。 如需詳細資訊，請參閱[Exchange Online 中的零小時自動清除 (ZAP) ](../office-365-security/zero-hour-auto-purge.md)。

您可以選取 [ **動作**]，針對特定郵件採取其他動作。 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="可以對電子郵件訊息執行其他動作的範例"::: 

## <a name="next-step"></a>下一步

請參閱以身分 [識別的攻擊](first-incident-path-identity.md) 調查路徑。

## <a name="see-also"></a>另請參閱

- [事件概觀](incidents-overview.md)
- [分析事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
