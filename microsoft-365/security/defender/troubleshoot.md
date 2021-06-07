---
title: 疑難排解 Microsoft 365 的 Defender 服務問題
description: 尋找已知 Microsoft 365 Defender 問題的解決方案和解決方法
keywords: 疑難排解 Microsoft 365 Defender、疑難排解、Microsoft Defender for Identity、問題、附加元件、設定頁面
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
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782738"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>疑難排解 Microsoft 365 的 Defender 服務問題

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

本節說明當您使用 Microsoft 365 Defender 服務時可能會發生的問題。

## <a name="i-dont-see-microsoft-365-defender-content"></a>我看不到 Microsoft 365 的 Defender 內容

如果您在流覽窗格中看不到 [事件]、[重要訊息中心] 或 [搜尋] 等功能，您必須確認您的承租人具有適當的授權。

如需詳細資訊，請參閱[必要條件](prerequisites.md)。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft defender for Identity 警示未顯示在 Microsoft 365 Defender 事件中

如果您已在環境中部署 Microsoft Defender，但在 Microsoft 365 defender 事件中卻沒有看到身分識別警示，您必須確定已啟用 Microsoft Cloud App Security 和 Defender 的身分識別整合。

如需詳細資訊，請參閱 [Microsoft Defender For Identity integration](/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>開啟服務的設定頁面位於何處？

若要開啟 Microsoft 365 Defender，請從 Microsoft 365 安全性中心的功能窗格存取 **設定**。 只有當您具有 [必要許可權和授權](m365d-enable.md#check-license-eligibility-and-required-permissions)時，才會顯示此導覽專案。

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>如何建立檔案/URL 的例外狀況？

誤報是指偵測為惡意但不是威脅的檔案或 URL。 您可以建立指示器並定義排除專案，以解除封鎖並允許某些檔案/URLs。 請參閱 [在 Defender For Endpoint 中的位址誤報/負片](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。


