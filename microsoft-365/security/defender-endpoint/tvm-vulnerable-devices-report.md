---
title: 易受攻擊的裝置報告-威脅與弱點管理
description: 顯示受影響裝置趨勢和目前統計資料的報告。 目標是讓您瞭解裝置洩密的 breath 和範圍。
keywords: Microsoft Defender for Endpoint tvm 易受攻擊的裝置、Microsoft Defender for Endpoint、tvm、降低威脅 & 弱點洩密、減少威脅和弱點，監視安全性設定
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245477"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>易受攻擊的裝置報告-威脅與弱點管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威脅及弱點管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

報告會顯示圖表和橫條圖，包含易受影響的裝置趨勢和目前的統計資料。 目標是讓您瞭解裝置洩密的 breath 和範圍。

前往 **報告 > 易受攻擊的裝置**，以存取 Microsoft Defender 資訊安全中心中的報告

有兩個欄：

- 隨時間)  (趨勢。 可顯示過去30天、3個月、6個月或自訂的日期範圍。
- 今天 (目前的資訊) 

**篩選**：您可以依弱點嚴重性層級、利用可用性、弱點年齡、作業系統平臺、Windows 10 版本或裝置群組篩選資料。

**深入** 查看：如果您想要進一步探索，請選取相關的橫條圖，以在 [設備庫存] 頁面中查看已篩選的裝置清單。 您可以從這裡匯出清單。

## <a name="severity-level-graphs"></a>嚴重性層級圖形

每個裝置會根據該裝置上最嚴重的弱點，只計算一次。

![目前裝置弱點嚴重性層級的一個圖形，以及一個顯示一段時間的層級的圖形。](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a>利用可用性圖表

每個裝置只會根據最上層的已知利用方式，計算一次。

![目前裝置侵入可用性的一個圖形，以及一個顯示一段時間可用性的圖形。](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a>弱點時期圖表

每個裝置只會在最舊的弱點發布日期下計算一次。 較舊的漏洞可能會受到攻擊的可能性較高。

![目前裝置弱點壽命的一個圖形，以及一個顯示一段時間的時期的圖形。](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>受作業系統平臺圖影響的裝置

每個作業系統上因軟體弱點而公開的裝置數目。

![由作業系統平臺所組成的目前易受攻擊裝置的一個圖形，以及一段時間後作業系統平臺顯示有漏洞裝置的圖形。](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>Windows 10 版本圖形的裝置受到攻擊

每個 Windows 10 版本上由於易受攻擊的應用程式或作業系統而公開的裝置數目。

![Windows 10 版本的目前有漏洞裝置的一個圖形，以及一段時間內 Windows 10 版本顯示有缺陷裝置的圖形。](images/tvm-report-version.png)

## <a name="related-topics"></a>相關主題

- [威脅與弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [安全性建議](tvm-security-recommendation.md)
