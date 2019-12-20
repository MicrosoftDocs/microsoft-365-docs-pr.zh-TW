---
title: DeviceInfo 資料表中的進階的狩獵結構描述
description: 了解 OS、 電腦名稱，以及 DeviceInfo 表格中其他電腦資訊的進階的狩獵結構描述
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 machineinfo，DeviceInfo，裝置，machine，作業系統、 平台、 使用者
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1141447de9b7ac714fb200dab56c4c2e8d75a05d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809267"
---
# <a name="deviceinfo"></a><span data-ttu-id="af2fe-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="af2fe-104">DeviceInfo</span></span>

<span data-ttu-id="af2fe-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="af2fe-105">**Applies to:**</span></span>
- <span data-ttu-id="af2fe-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="af2fe-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="af2fe-107">`DeviceInfo` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含機器在組織中，包括 OS 版本、 作用中使用者和電腦名稱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="af2fe-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="af2fe-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="af2fe-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="af2fe-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="af2fe-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="af2fe-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="af2fe-110">Column name</span></span> | <span data-ttu-id="af2fe-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="af2fe-111">Data type</span></span> | <span data-ttu-id="af2fe-112">描述</span><span class="sxs-lookup"><span data-stu-id="af2fe-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="af2fe-113">datetime</span><span class="sxs-lookup"><span data-stu-id="af2fe-113">datetime</span></span> | <span data-ttu-id="af2fe-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="af2fe-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="af2fe-115">字串</span><span class="sxs-lookup"><span data-stu-id="af2fe-115">string</span></span> | <span data-ttu-id="af2fe-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="af2fe-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="af2fe-117">string</span><span class="sxs-lookup"><span data-stu-id="af2fe-117">string</span></span> | <span data-ttu-id="af2fe-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="af2fe-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="af2fe-119">string</span><span class="sxs-lookup"><span data-stu-id="af2fe-119">string</span></span> | <span data-ttu-id="af2fe-120">端點代理程式或感應器在機器上執行的版本</span><span class="sxs-lookup"><span data-stu-id="af2fe-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="af2fe-121">string</span><span class="sxs-lookup"><span data-stu-id="af2fe-121">string</span></span> | <span data-ttu-id="af2fe-122">用來連線至 Microsoft Defender ATP 服務上架機器的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="af2fe-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="af2fe-123">這可能是電腦本身的 IP 位址、 NAT 裝置或 proxy</span><span class="sxs-lookup"><span data-stu-id="af2fe-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="af2fe-124">字串</span><span class="sxs-lookup"><span data-stu-id="af2fe-124">string</span></span> | <span data-ttu-id="af2fe-125">電腦上執行的作業系統架構。</span><span class="sxs-lookup"><span data-stu-id="af2fe-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="af2fe-126">string</span><span class="sxs-lookup"><span data-stu-id="af2fe-126">string</span></span> | <span data-ttu-id="af2fe-127">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="af2fe-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="af2fe-128">這表示特定的作業系統，包括在相同的系列，例如 Windows 10 和 Windows 7 的變化</span><span class="sxs-lookup"><span data-stu-id="af2fe-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="af2fe-129">string</span><span class="sxs-lookup"><span data-stu-id="af2fe-129">string</span></span> | <span data-ttu-id="af2fe-130">建置在機器上執行的作業系統版本</span><span class="sxs-lookup"><span data-stu-id="af2fe-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="af2fe-131">布林值</span><span class="sxs-lookup"><span data-stu-id="af2fe-131">boolean</span></span> | <span data-ttu-id="af2fe-132">布林值的電腦是否加入 Azure Active Directory 指示器</span><span class="sxs-lookup"><span data-stu-id="af2fe-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="af2fe-133">string</span><span class="sxs-lookup"><span data-stu-id="af2fe-133">string</span></span> | <span data-ttu-id="af2fe-134">JSON 陣列格式中的事件次登入電腦的所有使用者的清單</span><span class="sxs-lookup"><span data-stu-id="af2fe-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="af2fe-135">string</span><span class="sxs-lookup"><span data-stu-id="af2fe-135">string</span></span> | <span data-ttu-id="af2fe-136">機器標記新增到登錄</span><span class="sxs-lookup"><span data-stu-id="af2fe-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="af2fe-137">long</span><span class="sxs-lookup"><span data-stu-id="af2fe-137">long</span></span> | <span data-ttu-id="af2fe-138">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="af2fe-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="af2fe-139">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="af2fe-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="af2fe-140">string</span><span class="sxs-lookup"><span data-stu-id="af2fe-140">string</span></span> | <span data-ttu-id="af2fe-141">電腦上執行的作業系統版本。</span><span class="sxs-lookup"><span data-stu-id="af2fe-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="af2fe-142">string</span><span class="sxs-lookup"><span data-stu-id="af2fe-142">string</span></span> | <span data-ttu-id="af2fe-143">電腦的電腦群組。</span><span class="sxs-lookup"><span data-stu-id="af2fe-143">Machine group of the machine.</span></span> <span data-ttu-id="af2fe-144">此群組決定機器的存取權限時，是由角色型存取控制</span><span class="sxs-lookup"><span data-stu-id="af2fe-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="af2fe-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="af2fe-145">Related topics</span></span>
- [<span data-ttu-id="af2fe-146">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="af2fe-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="af2fe-147">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="af2fe-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="af2fe-148">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="af2fe-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="af2fe-149">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="af2fe-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="af2fe-150">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="af2fe-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="af2fe-151">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="af2fe-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)