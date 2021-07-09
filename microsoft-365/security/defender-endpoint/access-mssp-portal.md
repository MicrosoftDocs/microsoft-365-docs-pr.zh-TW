---
title: 存取 Microsoft 365 Defender MSSP 客戶入口網站
description: 存取 Microsoft 365 Defender MSSP 客戶入口網站
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
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339583"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>存取 Microsoft 365 Defender MSSP 客戶入口網站

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>這些步驟組會向 MSSP 導向。 

根據預設，MSSP 客戶會透過下列 URL: 存取其 Microsoft Defender 資訊安全中心承租人 `https://securitycenter.windows.com` 。
 

MSSPs 不過，將需要使用下列格式的承租人特定 URL：  `https://securitycenter.windows.com?tid=customer_tenant_id` 存取 MSSP 客戶入口網站。 

一般說來，MSSPs 將需要新增至他們想要管理的每一個 MSSP 客戶的 Azure AD。


使用下列步驟取得 MSSP 客戶租使用者識別碼，然後使用識別碼來存取租使用者特定的 URL:

1. MSSP，使用您的認證登入 Azure AD。 

2. 切換目錄至 MSSP 客戶的承租人。

3.  選取 [ **Azure Active Directory > 屬性**]。 您會在 [目錄識別碼] 欄位中找到租使用者識別碼。 

4. 取代下列 URL: 中的值，以存取 MSSP 客戶入口網站 `customer_tenant_id` `https://securitycenter.windows.com?tid=customer_tenant_id` 。


## <a name="related-topics"></a>相關主題
- [將入口網站存取權授予 MSSP](grant-mssp-access.md)
- [設定警示通知](configure-mssp-notifications.md)
- [從客戶租用戶中抓取警示](fetch-alerts-mssp.md)
