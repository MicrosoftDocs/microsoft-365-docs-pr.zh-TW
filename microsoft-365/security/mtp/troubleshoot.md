---
title: 疑難排解 Microsoft 365 Defender 服務問題
description: 尋找解決方案並解決已知的 Microsoft 365 Defender 問題
keywords: 疑難排解 Microsoft 威脅防護， 疑難排解， Azure ATP， 問題， 附加元件， 設定頁面
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
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925715"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>疑難排解 Microsoft 365 Defender 服務問題

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用範圍：**
- Microsoft 365 Defender

本節說明使用 Microsoft 365 Defender 服務時可能會出現的問題。

## <a name="i-dont-see-microsoft-365-defender-content"></a>我看不到 Microsoft 365 Defender 內容

如果您在入口網站中沒在流覽窗格中看到事件、控制中心或搜尋等功能，您必須確認您的租使用者擁有適當的授權。

如需詳細資訊，請參閱[先決條件](prerequisites.md)。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft 365 Defender 事件不會顯示身分識別警示的 Microsoft Defender

如果您在環境中部署了身分識別的 Microsoft Defender，但您沒有看到屬於 Microsoft 365 Defender 事件的 Defender，您必須確認已啟用 Microsoft Cloud App 安全性與身分識別整合的 Defender。

詳細資訊請參閱 Microsoft [Defender 的身分識別整合](https://docs.microsoft.com/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>可開啟服務的設定頁面在哪裡？

若要開啟 Microsoft 365 Defender，請從 Microsoft 365 資訊安全中心的流覽窗格存取設定。  只有您具有先決條件許可權和授權時，才能 [看到此流覽專案](mtp-enable.md#check-license-eligibility-and-required-permissions)。
