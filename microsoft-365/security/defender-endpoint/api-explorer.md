---
title: Microsoft Defender ATP 中的 API Explorer
ms.reviewer: ''
description: 使用 API Explorer 來構造和執行任何可用 API 的 API 查詢、測試及傳送要求
keywords: api、explorer、send、request、get、post、
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 0cfe5227d5d1cdb1f1f4eaea2c859937d7e75264
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058792"
---
# <a name="api-explorer"></a>API Explorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)


Microsoft Defender for Endpoint API Explorer 是一種工具，可協助您深入探索不同的 Defender for Endpoint APIs。 

API Explorer 可讓您輕鬆地構造和執行任何可用之 Defender API 端點的 API 查詢、測試及傳送要求。 使用 API Explorer 來採取動作或尋找可能尚未透過使用者介面提供的資料。

工具在應用程式開發期間很有用。 它可讓您執行遵循使用者存取設定的 API 查詢，以減少產生存取權杖的需求。

您也可以使用工具來流覽範例查詢、複製結果代碼範例，以及產生調試資訊的畫廊。

透過 API Explorer，您可以：

- 對任何方法執行要求，並且即時查看回應
- 快速流覽 API 範例，並瞭解其所支援的參數
- 輕鬆進行 API 呼叫;在管理入口網站登入之外，不需要驗證

## <a name="access-api-explorer"></a>Access API Explorer

從左導覽功能表中，選取 [**夥伴] & APIs**  >  **API Explorer**。

## <a name="supported-apis"></a>支援的 APIs

API Explorer 支援所有由 Defender for Endpoint 所提供的 APIs。
  
[APIs 檔](apis-intro.md)中提供支援的 APIs 清單。 

## <a name="get-started-with-the-api-explorer"></a>開始使用 API Explorer

1. 在左窗格中，有您可以使用的範例要求清單。 
2. 遵循連結，然後按一下 [ **執行查詢**]。 

某些範例可能需要在 URL 中指定參數，例如 {machine ID}。

## <a name="faq"></a>常見問題集

**我需要有 API 權杖才能使用 API Explorer 嗎？** <br>
不需要存取 API 的認證。 API Explorer 會在要求時使用 Defender 進行端點管理入口網站標記。

登入的使用者驗證認證是用來確認 API Explorer 有權代表您存取資料。

根據您的 RBAC 許可權，特定 API 要求會受到限制。 例如，對「送出指示器」的要求限制為安全性系統管理員角色。 
