---
title: 受支援的適用於端點的 Microsoft Defender API
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d0efd97359440ffb3d4b39b6389b477203c56084
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984997"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>受支援的適用於端點的 Microsoft Defender API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>端點 URI 及版本設定

### <a name="endpoint-uri"></a>端點 URI

> 服務基底 URI 是： [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> 以查詢為基礎的 OData 具有 '/api ' 前置詞。 例如，若要取得提醒，您可以將 GET 要求傳送至 [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>版本設定

> API 支援版本設定。
>
> 目前的版本是第 **1.0** 版。
>
> 若要使用特定版本，請使用此格式： `https://api.securitycenter.microsoft.com/api/{Version}` 。 例如：`https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> 如果您未指定任何版本 (例如 `https://api.securitycenter.microsoft.com/api/alerts` ) 您將會到達最新的版本。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

深入瞭解您可以執行 API 呼叫的個別支援實體和詳細資料，例如 HTTP 要求值、要求標頭和預期的回應。

## <a name="in-this-section"></a>本節內容

主題 | 描述
:---|:---
[進階搜捕](run-advanced-query-api.md) | 從 API 執行查詢。
[警示方法和屬性](alerts.md) | 執行 API 通話（如 \- 取得提醒、建立警示、更新警示等等）。
[匯出每台裝置的評估方法和屬性](get-assessment-methods-properties.md) | 執行 API 呼叫，以依據每個裝置來收集漏洞評估，例如： \- 匯出安全設定評估、匯出軟體清查評估、匯出軟體漏洞評估，以及增量匯出軟體漏洞評估。
[自動化調查方法和屬性](investigation.md) | 執行 API 通話（如 \- 取得調查的集合）。
[取得網域相關警示](get-domain-related-alerts.md) | 執行 API 通話，例如 \- 取得與網域相關的裝置、網域統計資料等等。
[檔案方法和屬性](files.md) | 執行 API 通話，例如 \- get file information、file 相關的警示、檔相關的裝置及檔案統計資料。
[指示器方法和屬性](ti-indicator.md) | 執行 API 呼叫，例如 \- Get 指示器、Create 指示器及 Delete 指示器。
[取得 IP 相關警示](get-ip-related-alerts.md) | 執行 API 通話，例如 \- 取得 ip 相關的警示，以及取得 ip 統計資料。
[電腦方法和屬性](machine.md) | 執行 API 通話，例如 \- get 裝置、依識別碼取得裝置、登入使用者的相關資訊、編輯標記等等。
[電腦動作方法和屬性](machineaction.md) | 執行 [隔離] 等 API 呼叫 \- ，執行反病毒掃描等等。
[建議方法和屬性](recommendation.md) | 執行 API 通話，例如 \- 依識別碼取得建議。
[補救活動方法和屬性](get-remediation-methods-properties.md) | 執行 API 呼叫，例如 \- 取得所有修復工作、取得公開的裝置修復工作，並依識別碼取得一個修復工作。
[分數方法和屬性](score.md) | 執行 API 通話（如 \- 取得披露分數或取得裝置安全分數）。
[軟體方法和屬性](software.md) | \-依軟體執行清單漏洞等 API 通話。
[使用者方法](user.md) | 執行 API 通話，例如 \- 取得使用者相關的警示和使用者相關的裝置。
[弱點方法和屬性](vulnerability.md) | 依弱點執行 API 通話（如 \- 清單裝置）。

## <a name="see-also"></a>另請參閱

- [Microsoft Defender for Endpoint APIs](apis-intro.md)

- [Microsoft Defender for Endpoint API 發行附注](api-release-notes.md)
