---
title: Microsoft 威脅防護服務問題的疑難排解
description: 尋找已知 Microsoft 威脅防護問題的解決方案與因應措施
keywords: 疑難排解 Microsoft 威脅防護、疑難排解、Azure ATP、問題、附加元件、設定頁面
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
ms.openlocfilehash: bcf5b79fcd2fdf0a5af5648e6f6b7ea65d69594c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201284"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Microsoft 威脅防護服務問題的疑難排解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用範圍：**
- Microsoft 威脅防護

本節說明使用 Microsoft 威脅防護服務時可能會發生的問題。


## <a name="i-dont-see-microsoft-threat-protection-content"></a>我沒有看到 Microsoft 威脅防護內容
如果您在流覽窗格中看不到 [事件]、[重要訊息中心] 或 [搜尋] 等功能，您必須確認您的承租人具有適當的授權。 

如需詳細資訊，請參閱[先決條件](prerequisites.md)。

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Azure ATP 警示沒有在 Microsoft 威脅防護事件中顯示
如果您已在環境中部署 Azure ATP，但並沒有在 Microsoft 威脅防護事件中看到 Azure ATP 警報，您需要確定已啟用 Microsoft 雲端 App 安全性和 Azure ATP 整合。 

如需詳細資訊，請參閱 [Azure ATP 整合](https://docs.microsoft.com/cloud-app-security/aatp-integration)。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>開啟服務的設定頁面位於何處？
若要開啟 Microsoft 威脅防護，請從 Microsoft 365 安全性中心的功能窗格存取 **設定** 。 只有當您具有 [必要許可權和授權](mtp-enable.md#check-license-eligibility-and-required-permissions)時，才會顯示此導覽專案。
 

