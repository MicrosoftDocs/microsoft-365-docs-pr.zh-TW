---
title: Advanced 搜尋架構中的 DeviceInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceInfo 資料表中的作業系統、電腦名稱稱及其他機器資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，machineinfo，DeviceInfo，device，machine，OS，平臺，使用者
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 526e210a472862593f2652e9b2b21957702c48f0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899276"
---
# <a name="deviceinfo"></a><span data-ttu-id="0fa31-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="0fa31-104">DeviceInfo</span></span>

<span data-ttu-id="0fa31-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0fa31-105">**Applies to:**</span></span>
- <span data-ttu-id="0fa31-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="0fa31-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="0fa31-107">[！附注] `DeviceInfo` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含組織中電腦的相關資訊，包括作業系統版本、作用中使用者及電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="0fa31-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="0fa31-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="0fa31-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0fa31-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="0fa31-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0fa31-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="0fa31-110">Column name</span></span> | <span data-ttu-id="0fa31-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="0fa31-111">Data type</span></span> | <span data-ttu-id="0fa31-112">描述</span><span class="sxs-lookup"><span data-stu-id="0fa31-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0fa31-113">datetime</span><span class="sxs-lookup"><span data-stu-id="0fa31-113">datetime</span></span> | <span data-ttu-id="0fa31-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="0fa31-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0fa31-115">字串</span><span class="sxs-lookup"><span data-stu-id="0fa31-115">string</span></span> | <span data-ttu-id="0fa31-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0fa31-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0fa31-117">string</span><span class="sxs-lookup"><span data-stu-id="0fa31-117">string</span></span> | <span data-ttu-id="0fa31-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="0fa31-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="0fa31-119">string</span><span class="sxs-lookup"><span data-stu-id="0fa31-119">string</span></span> | <span data-ttu-id="0fa31-120">電腦上執行的端點代理程式或感應器版本</span><span class="sxs-lookup"><span data-stu-id="0fa31-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="0fa31-121">string</span><span class="sxs-lookup"><span data-stu-id="0fa31-121">string</span></span> | <span data-ttu-id="0fa31-122">架電腦用來連接至 Microsoft Defender ATP 服務的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0fa31-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="0fa31-123">這可以是電腦本身、NAT 裝置或 proxy 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0fa31-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="0fa31-124">字串</span><span class="sxs-lookup"><span data-stu-id="0fa31-124">string</span></span> | <span data-ttu-id="0fa31-125">電腦上執行的作業系統架構。</span><span class="sxs-lookup"><span data-stu-id="0fa31-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="0fa31-126">string</span><span class="sxs-lookup"><span data-stu-id="0fa31-126">string</span></span> | <span data-ttu-id="0fa31-127">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="0fa31-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="0fa31-128">這表示特定作業系統（包括相同家族內的變化，例如 Windows 10 和 Windows 7）</span><span class="sxs-lookup"><span data-stu-id="0fa31-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="0fa31-129">string</span><span class="sxs-lookup"><span data-stu-id="0fa31-129">string</span></span> | <span data-ttu-id="0fa31-130">電腦上所執行作業系統的組建版本</span><span class="sxs-lookup"><span data-stu-id="0fa31-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="0fa31-131">布林值</span><span class="sxs-lookup"><span data-stu-id="0fa31-131">boolean</span></span> | <span data-ttu-id="0fa31-132">對電腦是否加入 Azure Active Directory 的布林指標</span><span class="sxs-lookup"><span data-stu-id="0fa31-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="0fa31-133">string</span><span class="sxs-lookup"><span data-stu-id="0fa31-133">string</span></span> | <span data-ttu-id="0fa31-134">以 JSON 陣列格式出現事件時，在機器上記錄的所有使用者清單</span><span class="sxs-lookup"><span data-stu-id="0fa31-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="0fa31-135">string</span><span class="sxs-lookup"><span data-stu-id="0fa31-135">string</span></span> | <span data-ttu-id="0fa31-136">透過登錄加入的電腦標記</span><span class="sxs-lookup"><span data-stu-id="0fa31-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="0fa31-137">long</span><span class="sxs-lookup"><span data-stu-id="0fa31-137">long</span></span> | <span data-ttu-id="0fa31-138">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="0fa31-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0fa31-139">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="0fa31-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="0fa31-140">string</span><span class="sxs-lookup"><span data-stu-id="0fa31-140">string</span></span> | <span data-ttu-id="0fa31-141">電腦上執行的作業系統版本。</span><span class="sxs-lookup"><span data-stu-id="0fa31-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="0fa31-142">string</span><span class="sxs-lookup"><span data-stu-id="0fa31-142">string</span></span> | <span data-ttu-id="0fa31-143">機器的電腦群組。</span><span class="sxs-lookup"><span data-stu-id="0fa31-143">Machine group of the machine.</span></span> <span data-ttu-id="0fa31-144">這個群組是由以角色為基礎的存取控制用來判斷對機器的存取權</span><span class="sxs-lookup"><span data-stu-id="0fa31-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0fa31-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="0fa31-145">Related topics</span></span>
- [<span data-ttu-id="0fa31-146">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="0fa31-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0fa31-147">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="0fa31-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0fa31-148">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="0fa31-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0fa31-149">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="0fa31-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0fa31-150">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="0fa31-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0fa31-151">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="0fa31-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
