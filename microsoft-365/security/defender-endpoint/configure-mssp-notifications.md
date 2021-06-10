---
title: 設定傳送至 MSSPs 的警示通知
description: 設定傳送至 MSSPs 的警示通知
keywords: 受管理的安全性服務提供者、mssp、configure、integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166050"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>設定傳送至 MSSPs 的警示通知 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>此步驟可由 MSSP 客戶或 MSSP 執行。 MSSPs 必須獲得適當的許可權，才可代表 MSSP 客戶進行這項設定。

存取入口網站後，就可以建立警示通知規則，以便在建立與租使用者相關聯的提醒時，將電子郵件傳送至 MSSPs，並符合設定的條件。

 
如需詳細資訊，請參閱 [建立警示通知的規則](configure-email-notifications.md#create-rules-for-alert-notifications)。
 

必須勾選這些核取方塊：
- **包含組織名稱** -客戶名稱將新增至電子郵件通知
- **包含租使用者的入口網站連結** -警示連結 URL 會有租使用者特定參數 (tid = target_tenant_id) 允許直接存取目標租使用者入口網站


## <a name="related-topics"></a>相關主題
- [將入口網站存取權授予 MSSP](grant-mssp-access.md)
- [存取 MSSP 客戶入口網站](access-mssp-portal.md)
- [從客戶租用戶中抓取警示](fetch-alerts-mssp.md)
