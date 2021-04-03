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
ms.technology: mde
ms.openlocfilehash: 1c287a72318cfb2e6e4e3860ac90a90e561040fe
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500949"
---
# <a name="score-resource-type"></a>評分資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

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
