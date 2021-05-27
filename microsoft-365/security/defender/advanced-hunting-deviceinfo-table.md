---
title: Advanced 搜尋架構中的 DeviceInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceInfo 資料表中的作業系統、電腦名稱稱及其他機器資訊
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、Microsoft 365 Defender、Microsoft 365、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、machineinfo、DeviceInfo、裝置、電腦、OS、平臺、使用者
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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689106"
---
# <a name="deviceinfo"></a><span data-ttu-id="b32af-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="b32af-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b32af-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b32af-105">**Applies to:**</span></span>
- <span data-ttu-id="b32af-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b32af-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b32af-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b32af-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="b32af-108">[！附注] `DeviceInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含組織中裝置的相關資訊，包括作業系統版本、作用中使用者及電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="b32af-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="b32af-109">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="b32af-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b32af-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="b32af-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b32af-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="b32af-111">Column name</span></span> | <span data-ttu-id="b32af-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="b32af-112">Data type</span></span> | <span data-ttu-id="b32af-113">描述</span><span class="sxs-lookup"><span data-stu-id="b32af-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b32af-114">datetime</span><span class="sxs-lookup"><span data-stu-id="b32af-114">datetime</span></span> | <span data-ttu-id="b32af-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="b32af-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b32af-116">string</span><span class="sxs-lookup"><span data-stu-id="b32af-116">string</span></span> | <span data-ttu-id="b32af-117">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="b32af-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b32af-118">string</span><span class="sxs-lookup"><span data-stu-id="b32af-118">string</span></span> | <span data-ttu-id="b32af-119">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b32af-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="b32af-120">string</span><span class="sxs-lookup"><span data-stu-id="b32af-120">string</span></span> | <span data-ttu-id="b32af-121">電腦上執行的端點代理程式或感應器版本</span><span class="sxs-lookup"><span data-stu-id="b32af-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="b32af-122">string</span><span class="sxs-lookup"><span data-stu-id="b32af-122">string</span></span> | <span data-ttu-id="b32af-123">架電腦用來連接至 Microsoft Defender for Endpoint service 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b32af-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="b32af-124">這可以是電腦本身、NAT 裝置或 proxy 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="b32af-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="b32af-125">字串</span><span class="sxs-lookup"><span data-stu-id="b32af-125">string</span></span> | <span data-ttu-id="b32af-126">電腦上執行的作業系統架構。</span><span class="sxs-lookup"><span data-stu-id="b32af-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b32af-127">字串</span><span class="sxs-lookup"><span data-stu-id="b32af-127">string</span></span> | <span data-ttu-id="b32af-128">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="b32af-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b32af-129">這表示特定作業系統（包括相同家族內的變化），例如 Windows 10 和 Windows 7</span><span class="sxs-lookup"><span data-stu-id="b32af-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="b32af-130">string</span><span class="sxs-lookup"><span data-stu-id="b32af-130">string</span></span> | <span data-ttu-id="b32af-131">電腦上所執行作業系統的組建版本</span><span class="sxs-lookup"><span data-stu-id="b32af-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="b32af-132">布林值</span><span class="sxs-lookup"><span data-stu-id="b32af-132">boolean</span></span> | <span data-ttu-id="b32af-133">布林指標，表示機器是否已加入 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b32af-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="b32af-134">string</span><span class="sxs-lookup"><span data-stu-id="b32af-134">string</span></span> | <span data-ttu-id="b32af-135">Azure AD 中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="b32af-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="b32af-136">string</span><span class="sxs-lookup"><span data-stu-id="b32af-136">string</span></span> | <span data-ttu-id="b32af-137">以 JSON 陣列格式出現事件時，在機器上記錄的所有使用者清單</span><span class="sxs-lookup"><span data-stu-id="b32af-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="b32af-138">string</span><span class="sxs-lookup"><span data-stu-id="b32af-138">string</span></span> | <span data-ttu-id="b32af-139">透過登錄加入的電腦標記</span><span class="sxs-lookup"><span data-stu-id="b32af-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="b32af-140">字串</span><span class="sxs-lookup"><span data-stu-id="b32af-140">string</span></span> | <span data-ttu-id="b32af-141">電腦上執行的作業系統版本。</span><span class="sxs-lookup"><span data-stu-id="b32af-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="b32af-142">字串</span><span class="sxs-lookup"><span data-stu-id="b32af-142">string</span></span> | <span data-ttu-id="b32af-143">機器的電腦群組。</span><span class="sxs-lookup"><span data-stu-id="b32af-143">Machine group of the machine.</span></span> <span data-ttu-id="b32af-144">這個群組是由以角色為基礎的存取控制用來判斷對機器的存取權</span><span class="sxs-lookup"><span data-stu-id="b32af-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="b32af-145">long</span><span class="sxs-lookup"><span data-stu-id="b32af-145">long</span></span> | <span data-ttu-id="b32af-146">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="b32af-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b32af-147">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="b32af-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="b32af-148">string</span><span class="sxs-lookup"><span data-stu-id="b32af-148">string</span></span> | <span data-ttu-id="b32af-149">表示裝置目前是架，或不是 Microsoft Defender For Endpoint，或是不支援裝置</span><span class="sxs-lookup"><span data-stu-id="b32af-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="b32af-150">string</span><span class="sxs-lookup"><span data-stu-id="b32af-150">string</span></span> | <span data-ttu-id="b32af-151">有關 JSON 陣列格式之事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="b32af-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="b32af-152">string</span><span class="sxs-lookup"><span data-stu-id="b32af-152">string</span></span> | <span data-ttu-id="b32af-153">在下列類別中群組特定裝置類型的更大分類：端點、網路裝置、IoT、不明</span><span class="sxs-lookup"><span data-stu-id="b32af-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="b32af-154">string</span><span class="sxs-lookup"><span data-stu-id="b32af-154">string</span></span> | <span data-ttu-id="b32af-155">根據用途及功能的裝置類型，例如網路裝置、工作站、伺服器、行動裝置、遊戲主控台或印表機</span><span class="sxs-lookup"><span data-stu-id="b32af-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="b32af-156">string</span><span class="sxs-lookup"><span data-stu-id="b32af-156">string</span></span> | <span data-ttu-id="b32af-157">某些類型裝置的其他修飾符，例如行動裝置可以是平板電腦或 smartphone</span><span class="sxs-lookup"><span data-stu-id="b32af-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="b32af-158">string</span><span class="sxs-lookup"><span data-stu-id="b32af-158">string</span></span> | <span data-ttu-id="b32af-159">廠商或製造商產品的模型名稱或編號</span><span class="sxs-lookup"><span data-stu-id="b32af-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="b32af-160">string</span><span class="sxs-lookup"><span data-stu-id="b32af-160">string</span></span> | <span data-ttu-id="b32af-161">產品廠商或製造商的名稱</span><span class="sxs-lookup"><span data-stu-id="b32af-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="b32af-162">string</span><span class="sxs-lookup"><span data-stu-id="b32af-162">string</span></span> | <span data-ttu-id="b32af-163">分散式作業系統平臺，例如 Ubuntu 或 RedHat for Linux 平臺</span><span class="sxs-lookup"><span data-stu-id="b32af-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="b32af-164">string</span><span class="sxs-lookup"><span data-stu-id="b32af-164">string</span></span> | <span data-ttu-id="b32af-165">作業系統版本的其他相關資訊，例如常用名稱、程式碼名稱或版本號碼</span><span class="sxs-lookup"><span data-stu-id="b32af-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="b32af-166">string</span><span class="sxs-lookup"><span data-stu-id="b32af-166">string</span></span> | <span data-ttu-id="b32af-167">已指派給相同裝置的先前裝置 IDs</span><span class="sxs-lookup"><span data-stu-id="b32af-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="b32af-168">string</span><span class="sxs-lookup"><span data-stu-id="b32af-168">string</span></span> | <span data-ttu-id="b32af-169">指派給裝置的最近裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="b32af-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="b32af-170">`DeviceInfo`表格提供以心跳方式（即來自裝置的定期報告或信號）為基礎的裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="b32af-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="b32af-171">每十五分鐘，裝置會傳送部分心跳，其中包含經常變更的屬性，如 `LoggedOnUsers` 。</span><span class="sxs-lookup"><span data-stu-id="b32af-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="b32af-172">一天一次，會傳送包含裝置之屬性的完整心跳。</span><span class="sxs-lookup"><span data-stu-id="b32af-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="b32af-173">您可以使用下列範例查詢取得裝置的最新狀態：</span><span class="sxs-lookup"><span data-stu-id="b32af-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="b32af-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="b32af-174">Related topics</span></span>
- [<span data-ttu-id="b32af-175">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="b32af-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b32af-176">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="b32af-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b32af-177">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="b32af-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b32af-178">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="b32af-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b32af-179">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="b32af-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b32af-180">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="b32af-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
