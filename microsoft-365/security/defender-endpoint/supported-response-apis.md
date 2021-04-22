---
title: 支援的 Microsoft Defender for Endpoint response APIs
description: 深入瞭解特定的回應相關 Microsoft Defender for Endpoint API 呼叫。
keywords: 回應 api，圖形 api，支援的 api，演員，警示，裝置，使用者，網域，ip，檔案
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933766"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>支援的 Microsoft Defender for Endpoint 查詢 APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

深入瞭解您可以執行的支援回應相關 API 通話，以及所需的要求標頭，以及來自呼叫的預期回應等詳細資訊。

## <a name="in-this-section"></a>本節內容
主題 | 描述
:---|:---
收集調查套件 | 執行此 API 以從裝置收集調查套件。
隔離裝置 | 執行此 API 以從網路隔離裝置。
Unisolate 裝置 | 從隔離移除裝置。 
限制程式碼執行 | 透過停止惡意程式執行此 API，以包含攻擊。 您也可以鎖定裝置，並防止後續惡意程式的企圖執行。
Unrestrict 程式碼執行 | 在驗證受損裝置後，請執行下列程式，以反轉應用程式原則的限制。
執行防毒掃描 | 遠端啟動防病毒掃描，以協助識別和修正受損裝置上可能會出現的惡意程式碼。
停止並隔離檔案 |  執行此呼叫以停止執行程式、隔離檔案和刪除 persistency，例如登錄機碼。
要求範例 | 執行此呼叫以從特定裝置要求檔案的範例。 將從裝置收集檔案，並將其上傳至安全儲存區。
封鎖檔 | 在 banning 潛在的惡意檔案或可疑惡意程式碼的情況執行此 API，以防止進一步傳播您組織中的攻擊。 
解除封鎖檔 | 允許使用 Microsoft Defender 防毒軟體在組織中執行檔案。
取得套件 SAS URI | 執行此 API 以取得可下載調查套件的 URI。
取得 MachineAction 物件 | 執行此 API 以取得 MachineAction 物件。
取得 MachineActions 集合 | 執行此以取得 MachineAction 集合。
取得 FileActions 集合 | 執行此 API 以取得 FileActions 集合。
取得 FileMachineAction 物件 | 執行此 API 以取得 FileMachineAction 物件。
取得 FileMachineActions 集合 | 執行此 API 以取得 FileMachineAction 集合。
