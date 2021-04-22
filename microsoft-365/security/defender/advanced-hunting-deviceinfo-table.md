---
title: Advanced 搜尋架構中的 DeviceInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceInfo 資料表中的作業系統、電腦名稱稱及其他機器資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，machineinfo，DeviceInfo，device，machine，OS，平臺，使用者
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e3686099606ec1cdab756bd4991cf61289299b43
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934882"
---
# <a name="deviceinfo"></a><span data-ttu-id="8e1c9-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="8e1c9-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8e1c9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8e1c9-105">**Applies to:**</span></span>
- <span data-ttu-id="8e1c9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e1c9-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="8e1c9-107">[！附注] `DeviceInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含組織中裝置的相關資訊，包括作業系統版本、作用中使用者及電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="8e1c9-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8e1c9-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8e1c9-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="8e1c9-110">Column name</span></span> | <span data-ttu-id="8e1c9-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="8e1c9-111">Data type</span></span> | <span data-ttu-id="8e1c9-112">描述</span><span class="sxs-lookup"><span data-stu-id="8e1c9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8e1c9-113">datetime</span><span class="sxs-lookup"><span data-stu-id="8e1c9-113">datetime</span></span> | <span data-ttu-id="8e1c9-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="8e1c9-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8e1c9-115">string</span><span class="sxs-lookup"><span data-stu-id="8e1c9-115">string</span></span> | <span data-ttu-id="8e1c9-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="8e1c9-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8e1c9-117">string</span><span class="sxs-lookup"><span data-stu-id="8e1c9-117">string</span></span> | <span data-ttu-id="8e1c9-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="8e1c9-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="8e1c9-119">string</span><span class="sxs-lookup"><span data-stu-id="8e1c9-119">string</span></span> | <span data-ttu-id="8e1c9-120">電腦上執行的端點代理程式或感應器版本</span><span class="sxs-lookup"><span data-stu-id="8e1c9-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="8e1c9-121">string</span><span class="sxs-lookup"><span data-stu-id="8e1c9-121">string</span></span> | <span data-ttu-id="8e1c9-122">架電腦用來連接至 Microsoft Defender for Endpoint service 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="8e1c9-123">這可以是電腦本身、NAT 裝置或 proxy 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8e1c9-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="8e1c9-124">字串</span><span class="sxs-lookup"><span data-stu-id="8e1c9-124">string</span></span> | <span data-ttu-id="8e1c9-125">電腦上執行的作業系統架構。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="8e1c9-126">字串</span><span class="sxs-lookup"><span data-stu-id="8e1c9-126">string</span></span> | <span data-ttu-id="8e1c9-127">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="8e1c9-128">這表示特定作業系統（包括相同家族內的變化，例如 Windows 10 和 Windows 7）</span><span class="sxs-lookup"><span data-stu-id="8e1c9-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="8e1c9-129">string</span><span class="sxs-lookup"><span data-stu-id="8e1c9-129">string</span></span> | <span data-ttu-id="8e1c9-130">電腦上所執行作業系統的組建版本</span><span class="sxs-lookup"><span data-stu-id="8e1c9-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="8e1c9-131">布林值</span><span class="sxs-lookup"><span data-stu-id="8e1c9-131">boolean</span></span> | <span data-ttu-id="8e1c9-132">對電腦是否加入 Azure Active Directory 的布林指標</span><span class="sxs-lookup"><span data-stu-id="8e1c9-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="8e1c9-133">string</span><span class="sxs-lookup"><span data-stu-id="8e1c9-133">string</span></span> | <span data-ttu-id="8e1c9-134">Azure AD 中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="8e1c9-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="8e1c9-135">string</span><span class="sxs-lookup"><span data-stu-id="8e1c9-135">string</span></span> | <span data-ttu-id="8e1c9-136">以 JSON 陣列格式出現事件時，在機器上記錄的所有使用者清單</span><span class="sxs-lookup"><span data-stu-id="8e1c9-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="8e1c9-137">string</span><span class="sxs-lookup"><span data-stu-id="8e1c9-137">string</span></span> | <span data-ttu-id="8e1c9-138">透過登錄加入的電腦標記</span><span class="sxs-lookup"><span data-stu-id="8e1c9-138">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="8e1c9-139">字串</span><span class="sxs-lookup"><span data-stu-id="8e1c9-139">string</span></span> | <span data-ttu-id="8e1c9-140">電腦上執行的作業系統版本。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-140">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="8e1c9-141">字串</span><span class="sxs-lookup"><span data-stu-id="8e1c9-141">string</span></span> | <span data-ttu-id="8e1c9-142">機器的電腦群組。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-142">Machine group of the machine.</span></span> <span data-ttu-id="8e1c9-143">這個群組是由以角色為基礎的存取控制用來判斷對機器的存取權</span><span class="sxs-lookup"><span data-stu-id="8e1c9-143">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="8e1c9-144">long</span><span class="sxs-lookup"><span data-stu-id="8e1c9-144">long</span></span> | <span data-ttu-id="8e1c9-145">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8e1c9-146">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="8e1c9-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="8e1c9-147">string</span><span class="sxs-lookup"><span data-stu-id="8e1c9-147">string</span></span> | <span data-ttu-id="8e1c9-148">有關 JSON 陣列格式之事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="8e1c9-148">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="8e1c9-149">`DeviceInfo`表格提供以心跳方式（即來自裝置的定期報告或信號）為基礎的裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="8e1c9-150">每十五分鐘，裝置會傳送部分心跳，其中包含經常變更的屬性，如 `LoggedOnUsers` 。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="8e1c9-151">一天一次，會傳送包含裝置之屬性的完整心跳。</span><span class="sxs-lookup"><span data-stu-id="8e1c9-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="8e1c9-152">您可以使用下列範例查詢取得裝置的最新狀態：</span><span class="sxs-lookup"><span data-stu-id="8e1c9-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="8e1c9-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="8e1c9-153">Related topics</span></span>
- [<span data-ttu-id="8e1c9-154">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="8e1c9-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8e1c9-155">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="8e1c9-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8e1c9-156">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="8e1c9-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8e1c9-157">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="8e1c9-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8e1c9-158">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="8e1c9-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8e1c9-159">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="8e1c9-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
