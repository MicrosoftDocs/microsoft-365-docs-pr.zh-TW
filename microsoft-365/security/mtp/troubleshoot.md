---
title: Microsoft 威脅防護服務問題的疑難排解
description: 尋找已知 Microsoft 威脅防護問題的解決方案與因應措施
keywords: 疑難排解 Microsoft 威脅防護、 進行疑難排解，Azure ATP、 問題、 附加元件、 設定] 頁面
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
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661979"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Microsoft 威脅防護服務問題的疑難排解

**適用範圍：**
- Microsoft 威脅防護

本節說明使用 Microsoft 威脅防護服務時可能會發生的問題。


## <a name="i-dont-see-microsoft-threat-protection-content"></a>看不到 Microsoft 威脅保護內容
如果您沒有看到例如事件、 重要訊息中心或狩獵的功能窗格上的功能，在您的入口網站中，您需要確認您的租用戶都有適當的授權。 

如需詳細資訊，請參閱[先決條件](prerequisites.md)。

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Azure ATP 警示沒有在 Microsoft 威脅防護事件中顯示
如果您已在環境中部署 Azure ATP，但並沒有在 Microsoft 威脅防護事件中看到 Azure ATP 警報，您需要確定已啟用 Microsoft 雲端 App 安全性和 Azure ATP 整合。 

如需詳細資訊，請參閱 [Azure ATP 整合](https://docs.microsoft.com/cloud-app-security/aatp-integration)。

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 威脅防護是否可用於美國政府社群雲端 (GCC) 或GCC High？
目前無法使用。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>[設定] 頁面開啟服務位於何處？
若要開啟 Microsoft 威脅防護，請從功能窗格中，Microsoft 365 安全性中心存取**設定**。 此導覽項目會顯示只有當您具備[必要權限和授權](mtp-enable.md#check-license-eligibility-and-required-permissions)。

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a>可以使用附加元件而不是必要的 E5 授權嗎？
目前有任何 Microsoft 威脅防護的附加元件。 [請參閱授權需求](prerequisites.md) 

