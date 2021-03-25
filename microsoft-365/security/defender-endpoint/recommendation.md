---
title: 建議方法和屬性
description: 會檢索最新的警示。
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
ms.technology: mde
ms.openlocfilehash: 6ab4d4e1acab0e4b837195f64c369057d7ceb417
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198230"
---
# <a name="recommendation-resource-type"></a>建議資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>方法
方法	 |傳回類型 |描述
:---|:---|:---
[列出所有建議](get-all-recommendations.md) | 建議集合 | 會檢索影響組織之所有安全性建議的清單
[依識別碼取得建議](get-recommendation-by-id.md) | 建議 | 依識別碼取得安全性建議
[取得建議軟體](get-recommendation-software.md)| [軟體](software.md) | 檢索與特定軟體相關的安全性建議
[取得建議裝置](get-recommendation-machines.md)|MachineRef 集合 | 檢索與安全性建議相關聯的裝置清單
[取得建議的弱點](get-recommendation-vulnerabilities.md) | [弱點](vulnerability.md) 集合 | 會檢索與安全性建議相關的漏洞清單。


## <a name="properties"></a>屬性
屬性	 |   類型   |   描述
:---|:---|:---
id | 字串 | 建議識別碼
Package.productname | 字串 | 相關軟體名稱  
recommendationName | 字串 | 建議名稱
弱點 | Long | 發現的漏洞數目
廠商 | 字串 | 相關的供應商名稱
recommendedVersion | 字串 | 建議的版本
recommendationCategory | 字串 | 建議類別。 可能的值為：「帳戶」、「應用程式」、「網路」、「OS」、「SecurityStack
個子 | 字串 | 建議子類別
severityScore | 雙精度浮點數 | 設定對組織之 Microsoft 安全評分的潛在影響 (1-10) 
publicExploit | 布林值 | 公開利用漏洞可供使用 
activeAlert | 布林值 | 主動警示與此建議相關聯
associatedThreats | String 集合 | 威脅分析報告與此建議相關聯
remediationType | 字串 | 修正類型。 可能的值為： "ConfigurationChange"、"Update"、"Upgrade"、"Uninstall"
狀態 | Enum | 建議例外狀況。 可能的值為：「Active」和「例外狀況」
configScoreImpact | 雙精度浮點數 | 適用于裝置影響的 Microsoft 安全分數
exposureImpacte | 雙精度浮點數 | 曝光分數影響
totalMachineCount | Long | 已安裝裝置的數目
exposedMachinesCount | Long | 對漏洞公開的已安裝裝置數目
nonProductivityImpactedAssets | Long | 不受影響的裝置數目  
relatedComponent | 字串 |  相關的軟體元件
