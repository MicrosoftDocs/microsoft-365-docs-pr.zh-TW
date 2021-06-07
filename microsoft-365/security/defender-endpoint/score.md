---
title: 分數方法和屬性
description: 依設備群組，檢索組織的公開分數、裝置安全分數和披露分數
keywords: api，graph api，支援的 api，分數，暴露分數，裝置安全分數，依設備群組的暴露分數
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771426"
---
# <a name="score-resource-type"></a>評分資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>方法

方法	 |傳回類型 |描述
:---|:---|:---
[取得暴險分數](get-exposure-score.md) | [分數](score.md) | 取得組織公開分數。
[取得裝置安全分數](get-device-secure-score.md) | [分數](score.md) | 取得組織裝置安全分數。
[依設備群組列出曝光排名](get-machine-group-exposure-score.md)| [分數](score.md) | 依設備群組列出分數。

## <a name="properties"></a>屬性

屬性	 |  類型    |   描述
:---|:---|:---
分數 | 雙精度浮點數 | 目前的分數。
時間 | DateTime | 此 API 通話的日期和時間。
RbacGroupName | 字串 | 裝置群組名稱。
