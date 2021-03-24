---
title: Advanced 搜尋架構中的 DeviceInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceInfo 資料表中的作業系統、電腦名稱稱及其他裝置資訊
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、deviceinfo、裝置、OS、平臺、使用者、DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059795"
---
# <a name="deviceinfo"></a><span data-ttu-id="de421-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="de421-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="de421-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="de421-105">**Applies to:**</span></span>
- [<span data-ttu-id="de421-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="de421-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="de421-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="de421-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="de421-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="de421-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="de421-109">[！附注] `DeviceInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含組織中裝置的相關資訊，包括作業系統版本、作用中使用者及電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="de421-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="de421-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="de421-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="de421-111">如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。</span><span class="sxs-lookup"><span data-stu-id="de421-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="de421-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="de421-112">Column name</span></span> | <span data-ttu-id="de421-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="de421-113">Data type</span></span> | <span data-ttu-id="de421-114">描述</span><span class="sxs-lookup"><span data-stu-id="de421-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="de421-115">datetime</span><span class="sxs-lookup"><span data-stu-id="de421-115">datetime</span></span> | <span data-ttu-id="de421-116">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="de421-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="de421-117">string</span><span class="sxs-lookup"><span data-stu-id="de421-117">string</span></span> | <span data-ttu-id="de421-118">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="de421-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="de421-119">string</span><span class="sxs-lookup"><span data-stu-id="de421-119">string</span></span> | <span data-ttu-id="de421-120">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="de421-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="de421-121">string</span><span class="sxs-lookup"><span data-stu-id="de421-121">string</span></span> | <span data-ttu-id="de421-122">裝置上所執行之端點代理程式或感應器的版本</span><span class="sxs-lookup"><span data-stu-id="de421-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="de421-123">string</span><span class="sxs-lookup"><span data-stu-id="de421-123">string</span></span> | <span data-ttu-id="de421-124">架裝置用來連線到端點服務之 Defender 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="de421-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="de421-125">這可能是裝置本身的 IP 位址、NAT 裝置或 proxy</span><span class="sxs-lookup"><span data-stu-id="de421-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="de421-126">string</span><span class="sxs-lookup"><span data-stu-id="de421-126">string</span></span> | <span data-ttu-id="de421-127">裝置上所執行作業系統的架構</span><span class="sxs-lookup"><span data-stu-id="de421-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="de421-128">string</span><span class="sxs-lookup"><span data-stu-id="de421-128">string</span></span> | <span data-ttu-id="de421-129">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="de421-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="de421-130">這表示特定作業系統（包括相同家族內的變化，例如 Windows 10 和 Windows 7）</span><span class="sxs-lookup"><span data-stu-id="de421-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="de421-131">string</span><span class="sxs-lookup"><span data-stu-id="de421-131">string</span></span> | <span data-ttu-id="de421-132">裝置上所執行作業系統的組建版本</span><span class="sxs-lookup"><span data-stu-id="de421-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="de421-133">布林值</span><span class="sxs-lookup"><span data-stu-id="de421-133">boolean</span></span> | <span data-ttu-id="de421-134">表示裝置是否已加入 Azure Active Directory 的布林指標</span><span class="sxs-lookup"><span data-stu-id="de421-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="de421-135">string</span><span class="sxs-lookup"><span data-stu-id="de421-135">string</span></span> | <span data-ttu-id="de421-136">以 JSON 陣列格式出現事件時，在裝置上登入之所有使用者的清單</span><span class="sxs-lookup"><span data-stu-id="de421-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="de421-137">string</span><span class="sxs-lookup"><span data-stu-id="de421-137">string</span></span> | <span data-ttu-id="de421-138">透過登錄新增的裝置標記</span><span class="sxs-lookup"><span data-stu-id="de421-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="de421-139">long</span><span class="sxs-lookup"><span data-stu-id="de421-139">long</span></span> | <span data-ttu-id="de421-140">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="de421-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="de421-141">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="de421-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="de421-142">string</span><span class="sxs-lookup"><span data-stu-id="de421-142">string</span></span> | <span data-ttu-id="de421-143">裝置上所執行的作業系統版本</span><span class="sxs-lookup"><span data-stu-id="de421-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="de421-144">string</span><span class="sxs-lookup"><span data-stu-id="de421-144">string</span></span> | <span data-ttu-id="de421-145">機器的電腦群組。</span><span class="sxs-lookup"><span data-stu-id="de421-145">Machine group of the machine.</span></span> <span data-ttu-id="de421-146">這個群組是由以角色為基礎的存取控制用來判斷對機器的存取權</span><span class="sxs-lookup"><span data-stu-id="de421-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="de421-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="de421-147">Related topics</span></span>
- [<span data-ttu-id="de421-148">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="de421-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="de421-149">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="de421-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="de421-150">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="de421-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
