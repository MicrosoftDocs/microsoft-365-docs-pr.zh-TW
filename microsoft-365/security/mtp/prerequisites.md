---
title: Microsoft 365 Defender 先決條件
description: 瞭解 Microsoft 365 Defender 的授權、硬體與軟體需求，以及其他設定設定
keywords: 需求、先決條件、硬體、軟體、瀏覽器、MTP、M365、授權、E5、A5、EMS、購買
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930087"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender 先決條件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

瞭解提供和使用 [Microsoft 365 Defender](microsoft-threat-protection.md)的授權與其他需求。

## <a name="licensing-requirements"></a>授權需求
上述任何授權都提供您 Microsoft 365 資訊安全中心 Microsoft 365 Defender 功能的存取權，無需支付額外費用：

- Microsoft 365 E5 或 A5
- Microsoft 365 E5 安全性或 A5 安全性
- Windows 10 企業版 E5 或 A5
- Enterprise Mobility + Security (EMS) E5 或 A5 
- Office 365 E5 或 A5
- 適用於端點的 Microsoft Defender
- 適用於身分識別的 Microsoft Defender 
- Microsoft Cloud App Security
- Office 365 方案 2 (的後) 

> [!NOTE]
> Office 365 試用版授權目前無法提供 Microsoft 365 Defender 的存取權。

詳細資訊請參閱 [Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> 還沒有授權嗎？ [試用或購買 Microsoft 365 訂閱](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>檢查您現有的授權
請前往 Microsoft 365 系統管理中心 [ (admin.microsoft.com) ](https://admin.microsoft.com/) 您現有的授權。 在系統管理中心中，移至 **[帳單]** >  **[授權]**。

>[!NOTE]
> 您必須在 [Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 中指派帳單系統管理員或 **全域** 讀取者角色，才能看到授權資訊。 如果您遭遇存取的問題，請與全域管理員聯繫。

## <a name="required-permissions"></a>必要的權限
您必須是 **Azure** Active Directory 中的全域系統管理員或安全性系統管理員，才能開啟 Microsoft 365 Defender。  若要瞭解使用 Microsoft 365 Defender 所需角色的清單，以及如何規範資料存取，請參閱如何管理[Microsoft 365 Defender 存取權。](mtp-permissions.md)

## <a name="browser-requirements"></a>瀏覽器需求
在 Microsoft 365 資訊安全中心使用 Microsoft Edge、Internet Explorer 11 或任何 HTML 5 相容網頁瀏覽器存取 Microsoft 365 Defender。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>可在美國 GCC、GCC High 及其他美國政府機關使用
目前，Microsoft 365 Defender *無法* 用於：
- 美國政府社群雲端 (GCC) 
- 美國政府社群雲端 High (GCC High) 
- 美國商務部
- 所有擁有商業授權之美國政府機關

## <a name="related-topics"></a>相關主題
- [Microsoft 365 Defender 概觀](microsoft-threat-protection.md)
- [開啟 Microsoft 365 Defender](mtp-enable.md)
- [管理存取與許可權](mtp-permissions.md)
