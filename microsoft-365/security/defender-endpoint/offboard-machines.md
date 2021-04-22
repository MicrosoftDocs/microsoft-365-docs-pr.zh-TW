---
title: Microsoft Defender for Endpoint service 中的下架裝置
description: Microsoft Defender for Endpoint service 中的板載 Windows 10 裝置、伺服器、非 Windows 裝置
keywords: 脫離，Microsoft Defender 用於端點脫離，脫離
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
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934150"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Microsoft Defender for Endpoint service 中的下架裝置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平臺**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

請根據您慣用的部署方法，依照對應的指示進行。

>[!NOTE]
> 裝置狀態會在脫離後的7天內切換成 [非](fix-unhealthy-sensors.md#inactive-devices) 使用中狀態。 <br> Offboarded 裝置的資料 (例如時程表、警示、弱點等等 ) 會保留在入口網站中，直到設定的 [保留期間](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) 到期為止。 <br>
> 裝置的設定檔 (（沒有資料）) 會保留在 [裝置清單](machines-view-overview.md) 中，不得超過180天。
> 此外，在過去30天內未使用中的裝置，不會考慮反映組織威脅的資料，以及裝置的安全性漏洞管理 [洩密分數](tvm-exposure-score.md) 和 Microsoft 安全評分。 <br>
> 若只要查看作用中的裝置，您可以依 [健康狀態](machines-view-overview.md#health-state)、 [裝置標記](machine-tags.md) 或 [機器群組](machine-groups.md)進行篩選。 

## <a name="offboard-windows-10-devices"></a>Windows 10 裝置下架
- [使用本機腳本的下架裝置](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [使用群組原則的下架裝置](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [使用行動裝置管理工具下架裝置](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>下架伺服器
- [下架伺服器](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>下架非 Windows 裝置
- [下架非 Windows 裝置](configure-endpoints-non-windows.md#offboard-non-windows-devices)

