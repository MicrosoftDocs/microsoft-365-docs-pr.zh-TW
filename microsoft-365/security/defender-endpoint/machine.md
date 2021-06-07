---
title: 電腦資源類型
description: 深入瞭解 Microsoft Defender for Endpoint 中的電腦資源類型的方法和屬性。
keywords: api、支援的 api、get、電腦
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
ms.openlocfilehash: 7b95fc487a8ee3e82e0f215b34aa564e063534af
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772074"
---
# <a name="machine-resource-type"></a>電腦資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>方法

方法	|傳回類型 |描述
:---|:---|:---
[列出電腦](get-machines.md) | [電腦](machine.md) 集合 | 組織中 [電腦](machine.md) 實體的清單集。
[取得機器](get-machine-by-id.md) | [機](machine.md) | 以機器的身分識別方式取得 [機器](machine.md) 。
[登入使用者](get-machine-log-on-users.md) | [使用者](user.md) 集合 | 取得一組登入[機器](machine.md)的[使用者](user.md)。
[取得相關警示](get-machine-related-alerts.md) | [警示](alerts.md) 集合 | 取得[電腦](machine.md)上所引發的[警示](alerts.md)實體集。
[取得已安裝的軟體](get-installed-software.md) | [軟體](software.md) 集合 | 會檢索與指定電腦識別碼相關之已安裝軟體的集合。
[取得發現的弱點](get-discovered-vulnerabilities.md) | [弱點](vulnerability.md) 集合 | 會檢索與指定電腦識別碼相關的已探索弱點的集合。
[取得安全性建議](get-security-recommendations.md) | [建議](recommendation.md) 集合 | 會檢索與指定電腦識別碼相關的安全性建議集合。
[新增或移除電腦標記](add-or-remove-machine-tags.md) | [機](machine.md) | 新增或移除特定電腦的標記。
[按 IP 尋找電腦](find-machines-by-ip.md) | [電腦](machine.md) 集合 | 尋找使用 IP 的機器。
[按標籤尋找電腦](find-machines-by-tag.md) | [電腦](machine.md) 集合 | 依 [標記](machine-tags.md)尋找電腦。
[取得遺失的 KB](get-missing-kbs-machine.md) | KB 集合 | 取得與電腦識別碼相關聯的遺失 Kb 清單。
[設定裝置值](set-device-value.md)| [電腦](machine.md) 集合 | 設定 [裝置的值](tvm-assign-device-value.md)。

## <a name="properties"></a>屬性

屬性	 |   類型   |   描述
:---|:---|:---
id | 字串 | [電腦](machine.md) 身分識別。
computerDnsName | 字串 | [電腦](machine.md) 完全限定名稱。
firstSeen | DateTimeOffset | Microsoft Defender for Endpoint 對 [機器](machine.md) 的觀察第一個日期和時間。
lastSeen | DateTimeOffset |上次接收完整裝置報告的時間和日期。 通常，裝置每24小時會傳送一次完整報告。
osPlatform | 字串 | 作業系統平臺。
osProcessor | 字串 | 作業系統處理器。 請改為使用 osArchitecture 屬性。
版本 | 字串 | 作業系統版本。
osBuild | 可為 null 的長 | 作業系統組建編號。
lastIpAddress | 字串 | [電腦](machine.md)上本機 NIC 上的最後一個 IP。
lastExternalIpAddress | 字串 | [機器](machine.md)存取網際網路的最後一個 IP。
healthStatus | Enum | [電腦](machine.md) 健康狀態。 可能的值為： "Active"、"非使用中"、"ImpairedCommunication"、"NoSensorData"、"NoSensorDataImpairedCommunication" 和 "Unknown"。 
rbacGroupName | 字串 | 電腦群組名稱。
riskScore | 可為 null 的列舉 | Microsoft Defender for Endpoint 評估的風險評分。 可能的值為：「無」、「資訊」、「低 '、' 中」及 ' High '。
exposureScore | 可為 null 的列舉 | Microsoft Defender for Endpoint 評估的[披露分數](tvm-exposure-score.md)。 可能的值為：「無」、「低 '、' 中」及 ' 高」。
aadDeviceId | 可為 null 的表示 Guid | 當 [機器](machine.md) 為 aad 加入) 時 (的 AAD 裝置識別碼。
machineTags | String 集合 | [電腦](machine.md)標記的集合。
exposureLevel | 可為 null 的列舉 | 由 Microsoft Defender for Endpoint 評估的公開層級。 可能的值為：「無」、「低 '、' 中」及 ' 高」。
deviceValue | 可為 null 的列舉 | [裝置的值](tvm-assign-device-value.md)。 可能的值為： ' Normal '、' Low ' 和 ' High '。
ipAddresses | IpAddress 集合 | ***IpAddress*** 物件的集合。 請參閱 [Get 電腦 API](get-machines.md)。
osArchitecture | 字串 | 作業系統架構。 可能的值為： "32-bit"，"64-位"。 使用此屬性，而不是 osProcessor。


