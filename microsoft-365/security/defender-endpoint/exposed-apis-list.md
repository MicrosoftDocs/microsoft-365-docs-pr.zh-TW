---
title: 支援的 Microsoft Defender for Endpoint APIs
ms.reviewer: ''
description: 深入瞭解 Microsoft Defender for Endpoint 實體的特定支援，您可以在其中建立 API 呼叫。
keywords: api，支援的 api，主角，警示，裝置，使用者，網域，ip，檔案，高級查詢，高級搜尋
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
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198316"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>支援的 Microsoft Defender for Endpoint APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>端點 URI 及版本設定

### <a name="endpoint-uri"></a>端點 URI：

> 服務基底 URI 是： https://api.securitycenter.microsoft.com
> 
> 以查詢為基礎的 OData 具有 '/api ' 前置詞。 例如，若要取得提醒，您可以將 GET 要求傳送至 https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>版本：

> API 支援版本設定。
> 
> 目前的版本是第 **1.0** 版。
> 
> 若要使用特定版本，請使用此格式： `https://api.securitycenter.microsoft.com/api/{Version}` 。 例如：`https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> 如果您未指定任何版本 (例如 https://api.securitycenter.microsoft.com/api/alerts ) 您將會到達最新的版本。


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


深入瞭解您可以執行 API 呼叫的個別支援實體和詳細資料，例如 HTTP 要求值、要求標頭和預期的回應。

## <a name="in-this-section"></a>本節內容

主題 | 描述
:---|:---
高級搜尋 | 從 API 執行查詢。
警示 | 執行 API 通話（如取得提醒、建立警示、更新警示等等）。
網域 | 執行 API 通話，例如取得與網域相關的裝置、網域統計資料等等。
檔案 | 執行 API 通話，例如 get file information、file 相關的警示、檔相關的裝置及檔案統計資料。
Ip | 執行 API 通話，例如取得 IP 相關的警示，以及取得 IP 統計資料。
機器 | 執行 API 通話，例如 get 裝置、依識別碼取得裝置、登入使用者的相關資訊、編輯標記等等。
電腦動作 | 執行 [隔離] 等 API 呼叫，執行反病毒掃描等等。
指標 | 執行 API 呼叫，例如建立指示器、取得指示器和刪除指示器。
使用者 | 執行 API 通話，例如取得使用者相關的警示和使用者相關的裝置。
分數 | 執行 API 通話（如取得披露分數或取得裝置安全分數）。
軟體 | 依軟體執行清單漏洞等 API 通話。
漏洞 | 依弱點執行 API 通話（如清單裝置）。
建議 | 執行 API 通話，例如依識別碼取得建議。

## <a name="see-also"></a>另請參閱
- [Microsoft Defender for Endpoint APIs](apis-intro.md)
