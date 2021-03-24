---
title: 疑難排解 Microsoft 365 Defender 服務問題
description: 尋找已知的 Microsoft 365 Defender 問題的解決方案及變通辦法
keywords: 疑難排解 Microsoft 威脅防護、疑難排解、Azure ATP、問題、附加元件、設定頁面
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
ms.openlocfilehash: 8d8083cbba3582c41ca91c57978675987822d0d9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059211"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>疑難排解 Microsoft 365 Defender 服務問題

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

本節說明當您使用 Microsoft 365 Defender 服務時可能會發生的問題。

## <a name="i-dont-see-microsoft-365-defender-content"></a>我未看到 Microsoft 365 Defender 內容

如果您在流覽窗格中看不到 [事件]、[重要訊息中心] 或 [搜尋] 等功能，您必須確認您的承租人具有適當的授權。

如需詳細資訊，請參閱[先決條件](prerequisites.md)。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft 365 Defender 事件中不會顯示識別警示的 microsoft Defender

如果您已在環境中部署 Microsoft Defender，但在 Microsoft 365 Defender 事件中卻沒有看到用於身分識別警示的 Defender，您必須確定已啟用 Microsoft Cloud App Security 和 Defender for Identity integration。

如需詳細資訊，請參閱 [Microsoft Defender For Identity integration](/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>開啟服務的設定頁面位於何處？

若要開啟 Microsoft 365 Defender，請從 Microsoft 365 安全性中心的功能窗格存取 **設定** 。 只有當您具有 [必要許可權和授權](m365d-enable.md#check-license-eligibility-and-required-permissions)時，才會顯示此導覽專案。
