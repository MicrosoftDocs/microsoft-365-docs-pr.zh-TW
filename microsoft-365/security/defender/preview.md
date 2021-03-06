---
title: Microsoft 365 Defender 中的預覽功能
description: 了解 Microsoft 365 安全性中心的新功能。
keywords: 預覽、全新、m365 安全性、安全性、365、功能
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
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430813"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender 預覽功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

Microsoft 365 Defender 服務會持續更新，以包含新功能增強功能及功能。

深入瞭解 Microsoft 365 Defender 預覽版本中的新功能，並透過開啟預覽體驗，以嘗試即將推出的功能。

如需一般可用之新功能的詳細資訊，請參閱[Microsoft 365 Defender 的新](whats-new.md)功能。

 ## <a name="what-you-need-to-know"></a>您需要瞭解的事項

在使用 public preview 中的功能時，這些功能包括：

- 可能具有限制或有限的功能。 例如，此功能可能只適用于一個平臺。
- 一般會透過功能變更， (正式) 使用。
- Microsoft 完全支援。
- 只能在選取的地理區域或雲端環境中使用。 例如，該功能可能不存在於政府雲端中。
- 預覽中的個別功能可能會有更多的使用和支援限制。 如果是的話，此資訊通常會注明在功能檔中。
- 預覽版本會以標準的支援層級提供，並且可用於實際執行環境。 



## <a name="required-permissions"></a>必要權限

已指派下列 Azure Active Directory 的帳戶 (Azure AD) 角色可以開啟 Microsoft 365 Defender 預覽功能：

- 全域管理員
- 安全性系統管理員
- 安全性操作員

## <a name="turn-on-preview-features"></a>開啟預覽功能

您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。

開啟預覽體驗設定，成為第一批嘗試即將推出的功能的人。

1. 在功能窗格中，選取 **[設定]**。
2. 選取 [ **Microsoft 365 Defender**]。
3. 選取 **預覽功能** > **開啟預覽功能**。 
4. 選取 **[儲存]**。

當您看到 **[開啟預覽功能]** 核取方塊已選取時，您就會知道您已開啟預覽功能。 

## <a name="preview-features"></a>預覽功能

目前預覽版提供下列功能和增強功能：

- **[依威脅標記查看報告](threat-analytics.md#view-reports-per-threat-tags)** -威脅標記可協助您將重點放在特定威脅類別上，並複查最相關的報告。
- **[流式 API](../defender-endpoint/raw-data-export.md)** Microsoft 365 Defender 支援透過 Advanced 搜尋向事件中樞和/或 Azure 儲存體帳戶，處理所有可用的事件。
- **[Microsoft 365 Defender APIs](api-overview.md)** -最上層 Microsoft 365 Defender APIs 可讓您根據共用的事件和高級搜尋表來自動化工作流程。 
- **[在高級搜尋中採取行動](advanced-hunting-take-action.md)** -快速包含威脅或處理您在 [高級搜尋](advanced-hunting-overview.md)中所發現的受損資產。
- **[In 入口架構參考](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** -直接在「安全性中心」取得高級搜尋架構表格的相關資訊。 除了資料表和欄描述之外，此參考還包含支援的事件種類 (`ActionType` 值) 和範例查詢。
- **[DeviceFromIP () 函數](advanced-hunting-devicefromip-function.md)** -取得在指定的時間範圍內，哪些裝置已被指派特定的 IP 位址或位址的相關資訊。
