---
title: Microsoft 365Defender 必要條件
description: 深入瞭解 Microsoft 365 Defender 的授權、硬體和軟體需求，以及其他設定設定
keywords: 需求，必要條件，硬體，軟體，瀏覽器，Microsoft 365 Defender，M365，授權，E5，A5，EMS，購買
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f3fd597181d73c1768057ea7740ab111e5af2068
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689154"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365Defender 必要條件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

深入瞭解布建和使用[Microsoft 365 Defender](microsoft-365-defender.md)的其他需求。

## <a name="licensing-requirements"></a>授權需求
這些授權中的任何一種可讓您存取 Microsoft 365 安全中心 Microsoft 365 的 Defender 功能，而不需要額外的成本：

- Microsoft 365 E5 或 A5
- 使用 Microsoft 365 E5 安全性附加元件 Microsoft 365 E3
- Microsoft 365A3 with Microsoft 365 A5 安全性附加元件
- Windows 10 企業版 E5 或 A5
- Enterprise Mobility + Security (EMS) E5 或 A5 
- Office 365 E5 或 A5
- 適用於端點的 Microsoft Defender
- 適用於身分識別的 Microsoft Defender 
- Microsoft Cloud App Security
- 適用於 Office 365 的 Defender (方案 2)

如需詳細資訊，請[查看 Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> 還沒有授權？ [試用或購買 Microsoft 365 訂閱](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>檢查您現有的授權
移至 Microsoft 365 系統管理中心 ([admin.microsoft.com](https://admin.microsoft.com/)) 以查看您現有的授權。 在系統管理中心中，移至 **[帳單]** >  **[授權]**。

>[!NOTE]
> 您必須被指派至 [AZURE AD 中](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)的 **帳務系統管理員** 或 **全域讀取** 者角色，才能看到授權資訊。 如果您遭遇存取的問題，請與全域管理員聯繫。

## <a name="required-permissions"></a>必要權限
您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員**，才可開啟 Microsoft 365 Defender。 如需使用 Microsoft 365 Defender 的角色清單，以及如何管制資料存取的相關資訊，請參閱管理對[Microsoft 365 Defender 的存取](m365d-permissions.md)。

## <a name="browser-requirements"></a>瀏覽器需求
使用 Microsoft Edge、Internet Explorer 11 或任何 HTML 5 相容網頁瀏覽器，存取 Microsoft 365 security center 中 Microsoft 365 Defender。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>可供我們 GCC、GCC 高及其他美國政府機構供貨
目前 *無法* 使用 Microsoft 365 Defender：
- 我們政府社群雲端 (GCC) 
- GCC 高) ，我們政府社群雲端高 (
- 美國國防部
- 具有商業授權的所有美國政府機構


目前，下列 Office 365 datacenter 位置中的客戶無法使用 Microsoft Defender Office 365 整合至統一 Microsoft 365 Defender 功能：

- 巴西 
- 德國 
- 挪威 
- 新加坡 
- 南非
- 瑞士 
- 阿拉伯聯合大公國 


## <a name="related-topics"></a>相關主題
- [Microsoft 365Defender 概述](microsoft-365-defender.md)
- [開啟 Microsoft 365 Defender](m365d-enable.md)
- [管理存取權和許可權](m365d-permissions.md)
