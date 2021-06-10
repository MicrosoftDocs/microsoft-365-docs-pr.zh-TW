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
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="3148b-104">Microsoft Defender for Endpoint service 中的下架裝置</span><span class="sxs-lookup"><span data-stu-id="3148b-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3148b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3148b-105">**Applies to:**</span></span>
- [<span data-ttu-id="3148b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3148b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3148b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3148b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3148b-108">**平臺**</span><span class="sxs-lookup"><span data-stu-id="3148b-108">**Platforms**</span></span>
- <span data-ttu-id="3148b-109">macOS</span><span class="sxs-lookup"><span data-stu-id="3148b-109">macOS</span></span>
- <span data-ttu-id="3148b-110">Linux</span><span class="sxs-lookup"><span data-stu-id="3148b-110">Linux</span></span>
- <span data-ttu-id="3148b-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3148b-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="3148b-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3148b-112">Windows Server 2016</span></span>

><span data-ttu-id="3148b-113">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3148b-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3148b-114">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3148b-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="3148b-115">請根據您慣用的部署方法，依照對應的指示進行。</span><span class="sxs-lookup"><span data-stu-id="3148b-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="3148b-116">裝置狀態會在脫離後的7天內切換成 [非](fix-unhealthy-sensors.md#inactive-devices) 使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="3148b-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="3148b-117">Offboarded 裝置的資料 (例如時程表、警示、弱點等等 ) 會保留在入口網站中，直到設定的 [保留期間](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) 到期為止。</span><span class="sxs-lookup"><span data-stu-id="3148b-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="3148b-118">裝置的設定檔 (（沒有資料）) 會保留在 [裝置清單](machines-view-overview.md) 中，不得超過180天。</span><span class="sxs-lookup"><span data-stu-id="3148b-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="3148b-119">此外，在過去30天內未使用中的裝置，不會考慮反映組織威脅與弱點管理[公開分數](tvm-exposure-score.md)和裝置的 Microsoft 安全分數的資料。</span><span class="sxs-lookup"><span data-stu-id="3148b-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="3148b-120">若只要查看作用中的裝置，您可以依 [健康狀態](machines-view-overview.md#health-state)、 [裝置標記](machine-tags.md) 或 [機器群組](machine-groups.md)進行篩選。</span><span class="sxs-lookup"><span data-stu-id="3148b-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="3148b-121">下架 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="3148b-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="3148b-122">使用本機腳本的下架裝置</span><span class="sxs-lookup"><span data-stu-id="3148b-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="3148b-123">使用群組原則的下架裝置</span><span class="sxs-lookup"><span data-stu-id="3148b-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="3148b-124">使用行動裝置管理工具下架裝置</span><span class="sxs-lookup"><span data-stu-id="3148b-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="3148b-125">下架伺服器</span><span class="sxs-lookup"><span data-stu-id="3148b-125">Offboard Servers</span></span>
- [<span data-ttu-id="3148b-126">下架伺服器</span><span class="sxs-lookup"><span data-stu-id="3148b-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="3148b-127">下架非 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="3148b-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="3148b-128">下架非 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="3148b-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

