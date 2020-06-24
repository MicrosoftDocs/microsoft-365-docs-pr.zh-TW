---
title: Microsoft 威脅防護先決條件
description: 了解 Microsoft 威脅防護的相關授權、硬體和軟體需求，以及其他組態設定
keywords: 需求，必要條件，硬體，軟體，瀏覽器，MTP，M365，授權，E5，A5，EMS，購買
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c64adf870d3669b983e11093196f59c82b1f59e0
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844903"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Microsoft 威脅防護先決條件

**適用範圍：**
- Microsoft 威脅防護

深入瞭解布建和使用[Microsoft 威脅防護](microsoft-threat-protection.md)的其他需求。

## <a name="licensing-requirements"></a>授權需求
這些授權中的任何一種可讓您存取 microsoft 365 安全中心的 Microsoft 威脅防護功能，而不需要額外成本：

- Microsoft 365 E5 或 A5
- Microsoft 365 E5 Security 或 A5 Security
- Windows 10 企業版 E5 或 A5
- Enterprise 可移動性 + Security （EMS） E5 或 A5 
- Office 365 E5 或 A5
- Microsoft Defender 進階威脅防護
- Azure 進階威脅防護 
- Microsoft Cloud App Security
- Office 365 高級威脅防護（方案2）

> [!NOTE]
> Office 365 的試用版授權目前不提供 Microsoft 威脅防護的存取權。

如需詳細資訊，請[查看 Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> 還沒有授權？ [試用或購買 Microsoft 365 訂閱](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>檢查您現有的授權
移至 Microsoft 365 系統管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看您現有的授權。 在系統管理中心中，移至 **[帳單]** >  **[授權]**。

>[!NOTE]
> 您必須被指派至[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)的**帳務系統管理員**或**全域讀取**者角色，才能看到授權資訊。 如果您遭遇存取的問題，請與全域管理員聯繫。

## <a name="required-permissions"></a>必要的權限
您必須是**全域系統管理員**或 Azure Active Directory 中的**安全性系統管理員**，才可開啟 Microsoft 威脅防護。 如需使用 Microsoft 威脅防護所需的角色清單，以及如何管制資料存取的相關資訊，請參閱[管理 Microsoft 威脅防護的存取](mtp-permissions.md)。

## <a name="browser-requirements"></a>瀏覽器需求
使用 Microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 標準的網頁瀏覽器，存取 microsoft 365 security center 中的 Microsoft 威脅防護。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>可供美國 GCC、GCC 高及其他美國政府機構供貨
目前，Microsoft 威脅防護*無法*用於：
- 美國政府社區雲端（GCC）
- 美國政府社區雲端高（GCC 高）
- 美國國防部
- 具有商業授權的所有美國政府機構

## <a name="related-topics"></a>相關主題
- [Microsoft 威脅防護概觀](microsoft-threat-protection.md)
- [開啟 Microsoft 威脅防護](mtp-enable.md)
- [管理存取權和許可權](mtp-permissions.md)
