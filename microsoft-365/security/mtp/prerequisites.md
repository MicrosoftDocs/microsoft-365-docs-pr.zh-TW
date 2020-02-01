---
title: Microsoft 威脅防護先決條件
description: 了解 Microsoft 威脅防護的相關授權、硬體和軟體需求，以及其他組態設定
keywords: 需求、 必要條件、 硬體、 軟體、 瀏覽器中，具有 mtp 之、 M365，授權
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
ms.openlocfilehash: d45be77abd404f87484d0f8390f09f1b9bc3b8ce
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600002"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Microsoft 威脅防護先決條件

**適用範圍：**
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

了解授權、硬體和軟體需求，以及其他組態設定以執行和使用 Microsoft 365 安全性。

## <a name="licensing-requirements"></a>授權需求
Microsoft 365 安全性需要以下其中一種授權：

- Microsoft 365 E5 
- Office 365 E5、Enterprise Mobility + Security E5 和 Windows E5

您可以從 [Microsoft 365 企業版頁面](https://www.microsoft.com/en-us/microsoft-365/enterprise)取得這些授權。

### <a name="check-your-existing--licenses"></a>檢查您現有的授權
移至 [admin.microsoft.com](https://admin.microsoft.com/) 的 Microsoft 365 系統管理中心，以檢視您現有的授權。 在系統管理中心中，移至 **[帳單]** >  **[授權]**。

您必須將 **[帳單系統管理員]** 或 **[全域讀取器]** 指派為 [[Azure AD 中的角色]](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)，才能查看授權資訊。 如果您遭遇存取的問題，請與全域管理員聯繫。  

## <a name="browser-requirements"></a>瀏覽器需求
Microsoft 365 安全中心的存取必須透過瀏覽器才能完成。 支援 Internet Explorer 和 Microsoft Edge。 也支援任何符合 HTML5 規範的瀏覽器。

## <a name="related-topics"></a>相關主題
- [Microsoft 威脅防護概觀](microsoft-threat-protection.md)
- [開啟 Microsoft 威脅防護](mtp-enable.md)