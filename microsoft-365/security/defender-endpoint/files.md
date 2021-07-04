---
title: 檔資源類型
description: 檢索與檔案相關的最近 Microsoft Defender 的端點警示。
keywords: api、graph api、支援的 api、get、警示、最近
search.product: eADQiWindows 10XVcnh
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
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 83a011e649a7289f62acd6a8d985f020b27b1e10
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290012"
---
# <a name="file-resource-type"></a>檔資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

代表在 Defender for Endpoint 中的檔實體。

## <a name="methods"></a>方法

方法	|傳回類型 |描述
:---|:---|:---
[取得檔](get-file-information.md) | [檔](files.md) | 取得單一檔 
[清單檔相關警示](get-file-related-alerts.md) | [警示](alerts.md) 集合 | 取得檔相關聯的 [警示](alerts.md) 實體。
[清單檔相關的電腦](get-file-related-machines.md) | [電腦](machine.md) 集合 | 取得與警示相關聯的 [電腦](machine.md) 實體。
[檔案統計資料](get-file-statistics.md) | 統計資料摘要 | 會檢索指定檔案的流行。


## <a name="properties"></a>屬性

|屬性	 | 類型 | 說明 |
|:---|:---|:---|
|sha1 | 字串 | 檔內容的 Sha1 雜湊 |
|sha256 | 字串 | 檔內容的 Sha256 雜湊 |
|globalPrevalence | 可為 null 的長 | 整個組織的檔傳播 |
|globalFirstObserved | DateTimeOffset | 第一次觀測檔時 |
|globalLastObserved | DateTimeOffset | 上次觀測檔的時間 |
|Size | 可為 null 的長 | 檔案大小 |
|類型 | 字串 | 檔案類型 |
|isPeFile | 布林值 | true 是表示如果檔案是可遷移的可執行檔 (例如 "DLL"、"EXE" 等 )  |
|filePublisher | 字串 | 檔發行者 |
|fileProductName | 字串 | 產品名稱 |
|簽名 | 字串 | 檔簽署者 |
|發行 | 字串 | 檔發行者 |
|signerHash | 字串 | 簽署憑證的雜湊 |
|isValidCertificate | 布林值 | 是由 Microsoft Defender for Endpoint agent 成功驗證的簽署憑證 |
|determinationType | 字串 | 檔的決定類型 |
|determinationValue | 字串 | 判斷值 |

## <a name="json-representation"></a>Json 標記法

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
