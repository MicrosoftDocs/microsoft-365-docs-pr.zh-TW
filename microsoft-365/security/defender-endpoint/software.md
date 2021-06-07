---
title: 軟體方法和屬性
description: 檢索最新的最近警示。
keywords: api、graph api、支援的 api、get、警示、最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771392"
---
# <a name="software-resource-type"></a>軟體資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>方法

方法	 |傳回類型 |描述
:---|:---|:---
[列出軟體](get-software.md) | 軟體集合 | 列出組織軟體清查。
[根據識別碼取得軟體](get-software-by-id.md) | 軟體 | 根據軟體識別碼取得特定軟體。
[列出軟體版本發佈](get-software-ver-distribution.md)| 通訊組集合 | 依軟體識別碼列出軟體版本發行。
[以軟體列出電腦](get-machines-by-software.md)| MachineRef 集合 | 取得與軟體識別碼相關聯的裝置清單。
[列出軟體的弱點](get-vuln-by-software.md) | [弱點](vulnerability.md) 集合 | 取得軟體識別碼相關聯的安全性漏洞清單。
[取得遺失的 KB](get-missing-kbs-software.md) | KB 集合 | 取得與軟體識別碼相關的遺失 Kb 清單。

## <a name="properties"></a>屬性

屬性	 |   類型   |   描述
:---|:---|:---
id | 字串 | 軟體識別碼
名稱 | 字串 | 軟體名稱
廠商 | 字串 | 軟體廠商名稱
弱點 | Long | 發現的漏洞數目
publicExploit | 布林值 | 部分弱點存在公開利用漏洞
activeAlert | 布林值 | 主動警示與此軟體關聯
exposedMachines | Long | 公開裝置的數目
impactScore | 雙精度浮點數 | 此軟體的暴露分數影響
