---
title: Microsoft 365 Defender 必要條件
description: 深入瞭解 Microsoft 365 Defender 的授權、硬體和軟體需求，以及其他設定設定
keywords: 需求，必要條件，硬體，軟體，瀏覽器，Microsoft 365 Defender，M365，授權，E5，A5，EMS，purchase
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
ms.openlocfilehash: 930a3de078d6d003241bb6fcd5df71bc9f301962
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935602"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender 必要條件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

深入瞭解布建和使用 [Microsoft 365 Defender](microsoft-365-defender.md)的其他需求。

## <a name="licensing-requirements"></a>授權需求
這些授權中的任何一種可讓您存取 microsoft 365 security center 中的 Microsoft 365 Defender 功能，而不需要額外成本：

- Microsoft 365 E5 或 A5
- Microsoft 365 E5 Security 或 A5 Security
- Windows 10 企業版 E5 或 A5
- Enterprise 可移動性 + Security (EMS) E5 或 A5 
- Office 365 E5 或 A5
- 適用於端點的 Microsoft Defender
- 適用於身分識別的 Microsoft Defender 
- Microsoft Cloud App Security
- 適用于 Office 的 Defender 365 (方案 2) 

如需詳細資訊，請 [查看 Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> 還沒有授權？ [試用或購買 Microsoft 365 訂閱](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>檢查您現有的授權
移至 Microsoft 365 系統管理中心 ([admin.microsoft.com](https://admin.microsoft.com/)) 以查看您現有的授權。 在系統管理中心中，移至 **[帳單]** >  **[授權]**。

>[!NOTE]
> 您必須被指派至 [AZURE AD 中](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)的 **帳務系統管理員** 或 **全域讀取** 者角色，才能看到授權資訊。 如果您遭遇存取的問題，請與全域管理員聯繫。

## <a name="required-permissions"></a>必要權限
您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員** ，才可開啟 Microsoft 365 Defender。 如需使用 Microsoft 365 Defender 所需的角色清單，以及如何管制資料存取的相關資訊，請參閱 [管理 Microsoft 365 Defender 的存取](m365d-permissions.md)。

## <a name="browser-requirements"></a>瀏覽器需求
使用 Microsoft Edge、Internet Explorer 11 或任何與 HTML 5 相容的網頁瀏覽器，存取 microsoft 365 security center 中的 Microsoft 365 Defender。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>可供美國 GCC、GCC 高及其他美國政府機構供貨
目前 *無法* 使用 Microsoft 365 Defender：
- 美國政府社區雲端 (GCC) 
- 美國政府社區雲端高 (GCC 高) 
- 美國國防部
- 具有商業授權的所有美國政府機構

## <a name="related-topics"></a>相關主題
- [Microsoft 365 Defender 概述](microsoft-365-defender.md)
- [開啟 Microsoft 365 Defender](m365d-enable.md)
- [管理存取權和許可權](m365d-permissions.md)
