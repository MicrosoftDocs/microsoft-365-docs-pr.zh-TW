---
title: Office 365 IP 位址和 URL Web 服務
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: 了解如何使用 Office 365 IP 位址和 URL Web 服務來協助您更能識別並區分 Office 365 網路流量。
ms.openlocfilehash: 0469070ed6d46b7695526697c255e23c0dc009ec
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286414"
---
# <a name="office-365-ip-address-and-url-web-service"></a><span data-ttu-id="c1304-103">Office 365 IP 位址和 URL Web 服務</span><span class="sxs-lookup"><span data-stu-id="c1304-103">Office 365 IP Address and URL web service</span></span>

<span data-ttu-id="c1304-p101">Office 365 IP 位址和 URL Web 服務可協助您更能識別並區分 Office 365 網路流量，讓您更容易評估、設定及掌握變更。此 REST 型 Web 服務會取代之前已於 2018 年 10 月 2 日淘汰的 XML 可下載檔案。</span><span class="sxs-lookup"><span data-stu-id="c1304-p101">The Office 365 IP Address and URL web service helps you better identify and differentiate Office 365 network traffic, making it easier for you to evaluate, configure, and stay up to date with changes. This REST-based web service replaces the previous XML downloadable files, which were phased out on October 2, 2018.</span></span>

<span data-ttu-id="c1304-p102">身為客戶或網路周邊裝置廠商，您可以根據 Web 服務，針對 Office 365 IP 位址和 FQDN 項目進行建置。您可以直接在網頁瀏覽器中使用這些 URL 來存取資料：</span><span class="sxs-lookup"><span data-stu-id="c1304-p102">As a customer or a network perimeter device vendor, you can build against the web service for Office 365 IP address and FQDN entries. You can access the data directly in a web browser using these URLs:</span></span>

- <span data-ttu-id="c1304-108">如需最新版本的 Office 365 URL 與 IP 位址範圍，請使用 [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)。</span><span class="sxs-lookup"><span data-stu-id="c1304-108">For the latest version of the Office 365 URLs and IP address ranges, use [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="c1304-109">如需在 Office 365 URL 與防火牆和 Proxy 伺服器的 IP 位址範圍頁面上的資料，請使用 [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)。</span><span class="sxs-lookup"><span data-stu-id="c1304-109">For the data on the Office 365 URLs and IP address ranges page for firewalls and proxy servers, use [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="c1304-110">若要在 Web 服務第一次可用時，取得從 2018 年 7 月以來的所有最新變更，請使用 [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)。</span><span class="sxs-lookup"><span data-stu-id="c1304-110">To get all the latest changes since July 2018 when the web service was first available, use [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>

<span data-ttu-id="c1304-111">身為客戶，您可以使用這個 Web 服務：</span><span class="sxs-lookup"><span data-stu-id="c1304-111">As a customer, you can use this web service to:</span></span>

- <span data-ttu-id="c1304-112">更新 PowerShell 指令碼，以取得 Office 365 端點資料以及為您的網路裝置修改任何格式。</span><span class="sxs-lookup"><span data-stu-id="c1304-112">Update your PowerShell scripts to obtain Office 365 endpoint data and modify any formatting for your networking devices.</span></span>
- <span data-ttu-id="c1304-113">使用這項資訊來更新部署到用戶端電腦的 PAC 檔案。</span><span class="sxs-lookup"><span data-stu-id="c1304-113">Use this information to update PAC files deployed to client computers.</span></span>

<span data-ttu-id="c1304-114">身為網路周邊裝置廠商，您可以使用這個 Web 服務：</span><span class="sxs-lookup"><span data-stu-id="c1304-114">As a network perimeter device vendor, you can use this web service to:</span></span>

- <span data-ttu-id="c1304-115">建立及測試裝置軟體，以下載自動設定的清單。</span><span class="sxs-lookup"><span data-stu-id="c1304-115">Create and test device software to download the list for automated configuration.</span></span>
- <span data-ttu-id="c1304-116">檢查目前的版本。</span><span class="sxs-lookup"><span data-stu-id="c1304-116">Check for the current version.</span></span>
- <span data-ttu-id="c1304-117">取得目前的變更。</span><span class="sxs-lookup"><span data-stu-id="c1304-117">Get the current changes.</span></span>

> [!NOTE]
> <span data-ttu-id="c1304-118">如果您使用 Azure ExpressRoute 連線到 Office 365，請檢閱 [Azure ExpressRoute for Office 365](azure-expressroute.md) 來熟悉透過 Azure ExpressRoute 支援的 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="c1304-118">If you are using Azure ExpressRoute to connect to Office 365, please review [Azure ExpressRoute for Office 365](azure-expressroute.md) to familiarize yourself with the Office 365 services supported over Azure ExpressRoute.</span></span> <span data-ttu-id="c1304-119">此外，請檢閱文章 [Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)，以了解哪些 Office 365 應用程式的網路要求需要網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="c1304-119">Also review the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md) to understand which network requests for Office 365 applications require Internet connectivity.</span></span> <span data-ttu-id="c1304-120">這將有助於更有效地設定周邊安全性裝置。</span><span class="sxs-lookup"><span data-stu-id="c1304-120">This will help to better configure your perimeter security devices.</span></span>

<span data-ttu-id="c1304-121">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c1304-121">For more information, see:</span></span>

- [<span data-ttu-id="c1304-122">Office 365 技術社群論壇中的宣告部落格文章</span><span class="sxs-lookup"><span data-stu-id="c1304-122">Announcement blog post in the Office 365 Tech Community Forum</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [<span data-ttu-id="c1304-123">Office 365 技術社群論壇中關於使用 Web 服務的問題</span><span class="sxs-lookup"><span data-stu-id="c1304-123">Office 365 Tech Community Forum for questions about use of the web services</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a><span data-ttu-id="c1304-124">通用參數</span><span class="sxs-lookup"><span data-stu-id="c1304-124">Common parameters</span></span>

<span data-ttu-id="c1304-125">這些參數為所有 Web 服務方法通用：</span><span class="sxs-lookup"><span data-stu-id="c1304-125">These parameters are common across all the web service methods:</span></span>

- <span data-ttu-id="c1304-126">**format=<JSON | CSV>** - 依預設，傳回的資料格式為 JSON。</span><span class="sxs-lookup"><span data-stu-id="c1304-126">**format=<JSON | CSV>** — By default, the returned data format is JSON.</span></span> <span data-ttu-id="c1304-127">使用此選擇性參數可以逗點分隔值 (CSV) 格式傳回資料。</span><span class="sxs-lookup"><span data-stu-id="c1304-127">Use this optional parameter to return the data in comma-separated values (CSV) format.</span></span>
- <span data-ttu-id="c1304-128">**ClientRequestId=\<guid>** - 您為用戶端關聯所產生的必要 GUID。</span><span class="sxs-lookup"><span data-stu-id="c1304-128">**ClientRequestId=\<guid>** — A required GUID that you generate for client association.</span></span> <span data-ttu-id="c1304-129">針對每個呼叫 Web 服務的電腦產生唯一 GUID (此頁面上包含的指令碼會為您產生 GUID)。</span><span class="sxs-lookup"><span data-stu-id="c1304-129">Generate a unique GUID for each machine that calls the web service (the scripts included on this page generate a GUID for you).</span></span> <span data-ttu-id="c1304-130">請勿使用下列範例所示的 GUID，因為未來 Web 服務可能會加以封鎖。</span><span class="sxs-lookup"><span data-stu-id="c1304-130">Do not use the GUIDs shown in the following examples because they might be blocked by the web service in the future.</span></span> <span data-ttu-id="c1304-131">GUID 格式為 _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_，其中 x 代表十六進位數字。</span><span class="sxs-lookup"><span data-stu-id="c1304-131">GUID format is _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, where x represents a hexadecimal number.</span></span>

  <span data-ttu-id="c1304-132">若要產生 GUID，您可以使用 PowerShell 命令 [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid)，或使用線上服務，例如[線上 GUID 產生器](https://www.guidgenerator.com/)。</span><span class="sxs-lookup"><span data-stu-id="c1304-132">To generate a GUID, you can use the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) PowerShell command, or use an online service such as [Online GUID Generator](https://www.guidgenerator.com/).</span></span>

## <a name="version-web-method"></a><span data-ttu-id="c1304-133">版本 Web 方法</span><span class="sxs-lookup"><span data-stu-id="c1304-133">Version web method</span></span>

<span data-ttu-id="c1304-134">Microsoft 在每個月底更新 Office 365 IP 位址和 FQDN 項目。</span><span class="sxs-lookup"><span data-stu-id="c1304-134">Microsoft updates the Office 365 IP address and FQDN entries at the end of each month.</span></span> <span data-ttu-id="c1304-135">有時也會因為支援事件、安全性更新或其他作業需求而發佈額外的更新。</span><span class="sxs-lookup"><span data-stu-id="c1304-135">Out-of-band updates are sometimes published due to support incidents, security updates or other operational requirements.</span></span>

<span data-ttu-id="c1304-p107">每個已發佈執行個體的資料都會被指派一個版本號碼，版本 Web 方法可讓您檢查每個 Office 365 服務執行個體的最新版本。我們建議您檢查版本的頻率是一個小時不超過一次。</span><span class="sxs-lookup"><span data-stu-id="c1304-p107">The data for each published instance is assigned a version number, and the version web method enables you to check for the latest version of each Office 365 service instance. We recommend that you check the version not more than once an hour.</span></span>

<span data-ttu-id="c1304-138">版本 Web 方法的參數為：</span><span class="sxs-lookup"><span data-stu-id="c1304-138">Parameters for the version web method are:</span></span>

- <span data-ttu-id="c1304-139">**AllVersions=<true | false>** - 依預設，傳回的版本是最新的。</span><span class="sxs-lookup"><span data-stu-id="c1304-139">**AllVersions=<true | false>** — By default, the version returned is the latest.</span></span> <span data-ttu-id="c1304-140">由於 Web 服務已先發行，因此包含此選擇性參數可要求所有已發佈的版本。</span><span class="sxs-lookup"><span data-stu-id="c1304-140">Include this optional parameter to request all published versions since the web service was first released.</span></span>
- <span data-ttu-id="c1304-141">**Format=<JSON | CSV | RSS>** - 除了 JSON 和 CSV 格式，版本 Web 方法也支援 RSS。</span><span class="sxs-lookup"><span data-stu-id="c1304-141">**Format=<JSON | CSV | RSS>** — In addition to the JSON and CSV formats, the version web method also supports RSS.</span></span> <span data-ttu-id="c1304-142">您可以使用此選擇性參數搭配 _AllVersions=true_ 參數，要求可以與 Outlook 或其他 RSS 讀取程式搭配使用的 RSS 摘要。</span><span class="sxs-lookup"><span data-stu-id="c1304-142">You can use this optional parameter along with the _AllVersions=true_ parameter to request an RSS feed that can be used with Outlook or other RSS readers.</span></span>
- <span data-ttu-id="c1304-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** - 此選擇性參數可指定要傳回版本的執行個體。</span><span class="sxs-lookup"><span data-stu-id="c1304-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This optional parameter specifies the instance to return the version for.</span></span> <span data-ttu-id="c1304-144">如果省略，則會傳回所有執行個體。</span><span class="sxs-lookup"><span data-stu-id="c1304-144">If omitted, all instances are returned.</span></span> <span data-ttu-id="c1304-145">有效的執行個體為：Worldwide、China、Germany、USGovDoD、USGovGCCHigh。</span><span class="sxs-lookup"><span data-stu-id="c1304-145">Valid instances are: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.</span></span>

<span data-ttu-id="c1304-p111">版本 Web 方法沒有速率限制，也不會傳回 429 HTTP 回應碼。版本 Web 方法的回應會包含建議快取資料達 1 小時的快取控制 (cache-control) 標頭。版本 Web 方法的結果可能是單一記錄或記錄的陣列。每個記錄的元素是：</span><span class="sxs-lookup"><span data-stu-id="c1304-p111">The version web method is not rate limited and does not ever return 429 HTTP Response Codes. The response to the version web method does include a cache-control header recommending caching of the data for 1 hour. The result from the version web method can be a single record or an array of records. The elements of each record are:</span></span>

- <span data-ttu-id="c1304-150">instance - Office 365 服務執行個體的簡短名稱。</span><span class="sxs-lookup"><span data-stu-id="c1304-150">instance — The short name of the Office 365 service instance.</span></span>
- <span data-ttu-id="c1304-151">latest - 指定執行個體端點的最新版本。</span><span class="sxs-lookup"><span data-stu-id="c1304-151">latest — The latest version for endpoints of the specified instance.</span></span>
- <span data-ttu-id="c1304-p112">versions - 指定執行個體所有舊版的清單。這個元素只有在 _AllVersions_ 參數為 true 時才會納入。</span><span class="sxs-lookup"><span data-stu-id="c1304-p112">versions — A list of all previous versions for the specified instance. This element is only included if the _AllVersions_ parameter is true.</span></span>

### <a name="examples"></a><span data-ttu-id="c1304-154">範例：</span><span class="sxs-lookup"><span data-stu-id="c1304-154">Examples:</span></span>

<span data-ttu-id="c1304-155">範例 1 要求 URI：[https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="c1304-155">Example 1 request URI: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="c1304-p113">這個 URI 會傳回每個 Office 365 服務執行個體的最新版本。範例結果：</span><span class="sxs-lookup"><span data-stu-id="c1304-p113">This URI returns the latest version of each Office 365 service instance. Example result:</span></span>

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> <span data-ttu-id="c1304-p114">這些 URI 中 ClientRequestID 參數的 GUID 只是範例。若要試用 Web 服務 URI，請產生您自己的 GUID。這些範例中所顯示的 GUID 未來可能會遭到 Web 服務封鎖。</span><span class="sxs-lookup"><span data-stu-id="c1304-p114">The GUID for the ClientRequestID parameter in these URIs are only an example. To try the web service URIs out, generate your own GUID. The GUIDs shown in these examples may be blocked by the web service in the future.</span></span>

<span data-ttu-id="c1304-161">範例 2 要求 URI：[https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="c1304-161">Example 2 request URI: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="c1304-p115">這個 URI 會傳回指定 Office 365 服務執行個體的最新版本。範例結果：</span><span class="sxs-lookup"><span data-stu-id="c1304-p115">This URI returns the latest version of the specified Office 365 service instance. Example result:</span></span>

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

<span data-ttu-id="c1304-164">範例 3 要求 URI：[https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="c1304-164">Example 3 request URI: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="c1304-p116">此 URI 會以 CSV 格式顯示輸出。範例結果：</span><span class="sxs-lookup"><span data-stu-id="c1304-p116">This URI shows output in CSV format. Example result:</span></span>

```csv
instance,latest
Worldwide,2018063000
```

<span data-ttu-id="c1304-167">範例 4 要求 URI：[https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="c1304-167">Example 4 request URI: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="c1304-p117">此 URI 會顯示已針對 Office 365 全球服務執行個體發佈的所有舊版。範例結果：</span><span class="sxs-lookup"><span data-stu-id="c1304-p117">This URI shows all prior versions that have been published for the Office 365 worldwide service instance. Example result:</span></span>

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

<span data-ttu-id="c1304-170">範例 5 RSS 摘要 URI：[https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span><span class="sxs-lookup"><span data-stu-id="c1304-170">Example 5 RSS Feed URI: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span></span>

<span data-ttu-id="c1304-p118">此 URI 會顯示已發佈版本的 RSS 摘要，其中包含每個版本的變更清單連結。範例結果：</span><span class="sxs-lookup"><span data-stu-id="c1304-p118">This URI shows an RSS feed of the published versions that include links to the list of changes for each version. Example result:</span></span>

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a><span data-ttu-id="c1304-173">端點 Web 方法</span><span class="sxs-lookup"><span data-stu-id="c1304-173">Endpoints web method</span></span>

<span data-ttu-id="c1304-174">端點 Web 方法會傳回組成 Office 365 服務的 IP 位址範圍和 URL 的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="c1304-174">The endpoints web method returns all records for IP address ranges and URLs that make up the Office 365 service.</span></span> <span data-ttu-id="c1304-175">網路裝置組態應一律使用端點 Web 方法的最新資料。</span><span class="sxs-lookup"><span data-stu-id="c1304-175">The latest data from the endpoints web method should always be used for network device configuration.</span></span> <span data-ttu-id="c1304-176">Microsoft 會在發佈新增內容前 30 天提供事先通知，讓您有時間可以更新存取控制清單和 Proxy 伺服器略過清單。</span><span class="sxs-lookup"><span data-stu-id="c1304-176">Microsoft provides advance notice 30 days prior to publishing new additions to give you time to update access control lists and proxy server bypass lists.</span></span> <span data-ttu-id="c1304-177">我們建議您只在版本 Web 方法指出有新版資料可用時，再重新呼叫端點 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="c1304-177">We recommend that you only call the endpoints web method again when the version web method indicates that a new version of the data is available.</span></span>

<span data-ttu-id="c1304-178">端點 Web 方法的參數為：</span><span class="sxs-lookup"><span data-stu-id="c1304-178">Parameters for the endpoints web method are:</span></span>

- <span data-ttu-id="c1304-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** - 以逗點分隔的服務區域清單。</span><span class="sxs-lookup"><span data-stu-id="c1304-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** — A comma-separated list of service areas.</span></span> <span data-ttu-id="c1304-180">有效的項目為 _Common_、_Exchange_、_SharePoint_ 和 _Skype_。</span><span class="sxs-lookup"><span data-stu-id="c1304-180">Valid items are _Common_, _Exchange_, _SharePoint_, and _Skype_.</span></span> <span data-ttu-id="c1304-181">因為 _Common_ 服務區域項目是其他所有服務區域的必要條件，因此 Web 服務一律會包含。</span><span class="sxs-lookup"><span data-stu-id="c1304-181">Because _Common_ service area items are a prerequisite for all other service areas, the web service always includes them.</span></span> <span data-ttu-id="c1304-182">如果您未包含此參數，則會傳回所有服務區域。</span><span class="sxs-lookup"><span data-stu-id="c1304-182">If you do not include this parameter, all service areas are returned.</span></span>
- <span data-ttu-id="c1304-183">**TenantName=<tenant_name>** - 您的 Office 365 租用戶名稱。</span><span class="sxs-lookup"><span data-stu-id="c1304-183">**TenantName=<tenant_name>** — Your Office 365 tenant name.</span></span> <span data-ttu-id="c1304-184">Web 服務會取得您提供的名稱，並將它在 URL 中包含租用戶名稱的部分插入。</span><span class="sxs-lookup"><span data-stu-id="c1304-184">The web service takes your provided name and inserts it in parts of URLs that include the tenant name.</span></span> <span data-ttu-id="c1304-185">如果您沒有提供租用戶名稱，則 URL 的這部分會是萬用字元 (\*)。</span><span class="sxs-lookup"><span data-stu-id="c1304-185">If you don't provide a tenant name, those parts of URLs have the wildcard character (\*).</span></span>
- <span data-ttu-id="c1304-186">**NoIPv6=<true | false>** - 如果您未在網路中使用 IPv6，將此參數設為 _true_ 可從輸出排除 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="c1304-186">**NoIPv6=<true | false>** — Set the value to _true_ to exclude IPv6 addresses from the output if you don't use IPv6 in your network.</span></span>
- <span data-ttu-id="c1304-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** - 此必要參數指定要傳回端點的執行個體。</span><span class="sxs-lookup"><span data-stu-id="c1304-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This required parameter specifies the instance from which to return the endpoints.</span></span> <span data-ttu-id="c1304-188">有效的執行個體為：_Worldwide_、_China_、_Germany_、_USGovDoD_ 及 _USGovGCCHigh_。</span><span class="sxs-lookup"><span data-stu-id="c1304-188">Valid instances are: _Worldwide_, _China_, _Germany_, _USGovDoD_, and _USGovGCCHigh_.</span></span>

<span data-ttu-id="c1304-189">如果您從相同用戶端 IP 位址呼叫端點 Web 方法非常多次，您可能會收到 HTTP 回應碼 _429 (太多要求)_。</span><span class="sxs-lookup"><span data-stu-id="c1304-189">If you call the endpoints web method too many times from the same client IP address, you might receive HTTP response code _429 (Too Many Requests)_.</span></span> <span data-ttu-id="c1304-190">如果您收到此回應碼，請先等候 1 小時，再重複您的要求，或是針對要求產生新的 GUID。</span><span class="sxs-lookup"><span data-stu-id="c1304-190">If you get this response code, wait 1 hour before repeating your request, or generate a new GUID for the request.</span></span> <span data-ttu-id="c1304-191">一般的最佳作法是，只在版本 Web 方法指出有新版本可用時，再呼叫端點 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="c1304-191">As a general best practice, only call the endpoints web method when the version web method indicates that a new version is available.</span></span>

<span data-ttu-id="c1304-p124">端點 Web 方法的結果是記錄的陣列，每個記錄代表特定端點集。每個記錄的元素為：</span><span class="sxs-lookup"><span data-stu-id="c1304-p124">The result from the endpoints web method is an array of records in which each record represents a specific endpoint set. The elements for each record are:</span></span>

- <span data-ttu-id="c1304-194">id - 端點集的固定識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1304-194">id — The immutable id number of the endpoint set.</span></span>
- <span data-ttu-id="c1304-195">serviceArea - 屬於以下項目的服務區域：_Common_、_Exchange_、_SharePoint_ 或 _Skype_。</span><span class="sxs-lookup"><span data-stu-id="c1304-195">serviceArea — The service area that this is part of: _Common_, _Exchange_, _SharePoint_, or _Skype_.</span></span>
- <span data-ttu-id="c1304-p125">urls - 端點集的 URL。DNS 記錄的 JSON 陣列。如果空白則省略。</span><span class="sxs-lookup"><span data-stu-id="c1304-p125">urls — URLs for the endpoint set. A JSON array of DNS records. Omitted if blank.</span></span>
- <span data-ttu-id="c1304-p126">tcpPorts - 端點集的 TCP 連接埠。所有連接埠元素會格式化為以逗點分隔的連接埠清單，或以破折號字元 (-) 分隔的連接埠範圍。該端點中套用至所有 IP 位址和所有 URL 的連接部會針對指定分類進行設定。如果空白則省略。</span><span class="sxs-lookup"><span data-stu-id="c1304-p126">tcpPorts — TCP ports for the endpoint set. All ports elements are formatted as a comma-separated list of ports or port ranges separated by a dash character (-). Ports apply to all IP addresses and all URLs in the endpoint set for a given category. Omitted if blank.</span></span>
- <span data-ttu-id="c1304-p127">udpPorts - 此端點集中 IP 位址範圍的 UDP 連接埠。如果空白則省略。</span><span class="sxs-lookup"><span data-stu-id="c1304-p127">udpPorts — UDP ports for the IP address ranges in this endpoint set. Omitted if blank.</span></span>
- <span data-ttu-id="c1304-p128">ips - 與此端點集相關聯的 IP 位址範圍會設定為與列出的 TCP 或 UDP 連接埠相關聯。IP 位址範圍的 JSON 陣列。如果空白則省略。</span><span class="sxs-lookup"><span data-stu-id="c1304-p128">ips — The IP address ranges associated with this endpoint set as associated with the listed TCP or UDP ports. A JSON array of IP address ranges. Omitted if blank.</span></span>
- <span data-ttu-id="c1304-208">category - 端點集的連線能力類別。</span><span class="sxs-lookup"><span data-stu-id="c1304-208">category — The connectivity category for the endpoint set.</span></span> <span data-ttu-id="c1304-209">有效值為 _Optimize_、_Allow_ 和 _Default_。</span><span class="sxs-lookup"><span data-stu-id="c1304-209">Valid values are _Optimize_, _Allow_, and _Default_.</span></span> <span data-ttu-id="c1304-210">如果您在端點 Web 方法的輸出中搜尋特定 IP 位址或 URL 的類別，您的查詢很有可能會傳回多個類別。</span><span class="sxs-lookup"><span data-stu-id="c1304-210">If you search the endpoints web method output for the category of a specific IP address or URL, it is possible that your query will return multiple categories.</span></span> <span data-ttu-id="c1304-211">在這種情況下，請遵循最高優先順序類別的建議。</span><span class="sxs-lookup"><span data-stu-id="c1304-211">In such a case, follow the recommendation for the highest priority category.</span></span> <span data-ttu-id="c1304-212">例如，如果端點同時出現在 _Optimize_ 和 _Allow_，您應該遵循 _Optimize_ 的要求。</span><span class="sxs-lookup"><span data-stu-id="c1304-212">For example, if the endpoint appears in both _Optimize_ and _Allow_, you should follow the requirements for _Optimize_.</span></span> <span data-ttu-id="c1304-213">此為必要動作。</span><span class="sxs-lookup"><span data-stu-id="c1304-213">Required.</span></span>
- <span data-ttu-id="c1304-214">expressRoute - 如果此端點集是透過 ExpressRoute 路由傳送，則為 _True_；如果不是，則為 _False_。</span><span class="sxs-lookup"><span data-stu-id="c1304-214">expressRoute — _True_ if this endpoint set is routed over ExpressRoute, _False_ if not.</span></span>
- <span data-ttu-id="c1304-p130">required - 如果需要此端點集才能支援 Office 365 連線，則為 _True_。如果此端點集為選擇性的，則為 _False_。</span><span class="sxs-lookup"><span data-stu-id="c1304-p130">required — _True_ if this endpoint set is required to have connectivity for Office 365 to be supported. _False_ if this endpoint set is optional.</span></span>
- <span data-ttu-id="c1304-p131">notes - 針對選擇性的端點，這些文字說明無法在網路層存取此端點集中的 IP 位址或 URL 時，無法使用的 Office 365 功能。如果空白則省略。</span><span class="sxs-lookup"><span data-stu-id="c1304-p131">notes — For optional endpoints, this text describes Office 365 functionality that would be unavailable if IP addresses or URLs in this endpoint set cannot be accessed at the network layer. Omitted if blank.</span></span>

### <a name="examples"></a><span data-ttu-id="c1304-219">範例：</span><span class="sxs-lookup"><span data-stu-id="c1304-219">Examples:</span></span>

<span data-ttu-id="c1304-220">範例 1 要求 URI：[https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="c1304-220">Example 1 request URI: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="c1304-p132">此 URI 會取得所有工作負載之 Office 365 全球執行個體的所有端點。顯示輸出摘要的範例結果：</span><span class="sxs-lookup"><span data-stu-id="c1304-p132">This URI obtains all endpoints for the Office 365 worldwide instance for all workloads. Example result that shows an excerpt of the output:</span></span>

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

<span data-ttu-id="c1304-223">請注意，在此範例中，要求的完整輸出會包含有其他端點集。</span><span class="sxs-lookup"><span data-stu-id="c1304-223">Note that the full output of the request in this example would contain other endpoint sets.</span></span>

<span data-ttu-id="c1304-224">範例 2 要求 URI：[https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="c1304-224">Example 2 request URI: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="c1304-225">這個範例只會取得 Exchange Online 和相依性之 Office 365 全球執行個體的端點。</span><span class="sxs-lookup"><span data-stu-id="c1304-225">This example obtains endpoints for the Office 365 Worldwide instance for Exchange Online and dependencies only.</span></span>

<span data-ttu-id="c1304-226">範例 2 的輸出類似於範例 1，不同之處在於結果不會包含 SharePoint Online 或商務用 Skype Online 的端點。</span><span class="sxs-lookup"><span data-stu-id="c1304-226">The output for example 2 is similar to example 1 except that the results would not include endpoints for SharePoint Online or Skype for Business Online.</span></span>

## <a name="changes-web-method"></a><span data-ttu-id="c1304-227">變更 Web 方法</span><span class="sxs-lookup"><span data-stu-id="c1304-227">Changes web method</span></span>

<span data-ttu-id="c1304-228">變更 Web 方法會傳回已發佈的最新更新，通常是上個月對於 IP 位址範圍和 URL 的變更。</span><span class="sxs-lookup"><span data-stu-id="c1304-228">The changes web method returns the most recent updates that have been published, typically the previous month's changes to IP address ranges and URLs.</span></span>

<span data-ttu-id="c1304-229">端點資料最重要的變更是新的 URL 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c1304-229">The most critical changes to endpoints data are new URLs and IP addresses.</span></span> <span data-ttu-id="c1304-230">無法將 IP 位址新增至防火牆存取控制清單，或是無法將 URL 新增至 Proxy 伺服器略過清單，都會導致該網路裝置後方的 Office 365 使用者服務中斷。</span><span class="sxs-lookup"><span data-stu-id="c1304-230">Failure to add an IP address to a firewall access control list or a URL to a proxy server bypass list can cause an outage for Office 365 users behind that network device.</span></span> <span data-ttu-id="c1304-231">儘管有作業要求，新端點會在端點可供使用日期之前 30 天發佈至 Web 服務，讓您有時間更新存取控制清單和 Proxy 伺服器略過清單。</span><span class="sxs-lookup"><span data-stu-id="c1304-231">Notwithstanding operational requirements, new endpoints are published to the web service 30 days in advance of the date the endpoints are provisioned for use to give you time to update access control lists and proxy server bypass lists.</span></span>

<span data-ttu-id="c1304-232">變更 Web 方法的必要參數為：</span><span class="sxs-lookup"><span data-stu-id="c1304-232">The required parameter for the changes web method is:</span></span>

- <span data-ttu-id="c1304-233">**Version=\<YYYYMMDDNN>** - 必要的 URL 路由參數。</span><span class="sxs-lookup"><span data-stu-id="c1304-233">**Version=\<YYYYMMDDNN>** — Required URL route parameter.</span></span> <span data-ttu-id="c1304-234">此值是您目前實作的版本。</span><span class="sxs-lookup"><span data-stu-id="c1304-234">This value is the version that you have currently implemented.</span></span> <span data-ttu-id="c1304-235">Web 服務會傳回自該版本後所做的變更。</span><span class="sxs-lookup"><span data-stu-id="c1304-235">The web service will return the changes since that version.</span></span> <span data-ttu-id="c1304-236">格式為 _YYYYMMDDNN_，其中 _NN_ 是在一天中必須發佈多個版本時，遞增的自然數，_00_ 代表當天的第一個更新。</span><span class="sxs-lookup"><span data-stu-id="c1304-236">The format is _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day, with _00_ representing the first update for a given day.</span></span> <span data-ttu-id="c1304-237">Web 服務需要 _版本_ 參數，才能包含確切 10 位數。</span><span class="sxs-lookup"><span data-stu-id="c1304-237">The web service requires the _version_ parameter to contain exactly 10 digits.</span></span>

<span data-ttu-id="c1304-238">變更 Web 方法的速率限制方式與端點 Web 方法相同。</span><span class="sxs-lookup"><span data-stu-id="c1304-238">The changes web method is rate limited in the same way as the endpoints web method.</span></span> <span data-ttu-id="c1304-239">如果您收到 429 HTTP 回應碼，請先等候 1 小時，再重複您的要求，或是針對要求產生新的 GUID。</span><span class="sxs-lookup"><span data-stu-id="c1304-239">If you receive a 429 HTTP response code, wait 1 hour before repeating your request or generate a new GUID for the request.</span></span>

<span data-ttu-id="c1304-p136">變更 Web 方法的結果是記錄的陣列，其中的每個記錄都代表特定端點版本中的一個變更。每個記錄的元素為：</span><span class="sxs-lookup"><span data-stu-id="c1304-p136">The result from the changes web method is an array of records in which each record represents a change in a specific version of the endpoints. The elements for each record are:</span></span>

- <span data-ttu-id="c1304-242">id - 變更記錄的固定 ID。</span><span class="sxs-lookup"><span data-stu-id="c1304-242">id — The immutable id of the change record.</span></span>
- <span data-ttu-id="c1304-243">endpointSetId - 已變更的端點集記錄識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1304-243">endpointSetId — The ID of the endpoint set record that is changed.</span></span>
- <span data-ttu-id="c1304-244">disposition - 說明對端點集記錄進行什麼變更。</span><span class="sxs-lookup"><span data-stu-id="c1304-244">disposition — Describes what the change did to the endpoint set record.</span></span> <span data-ttu-id="c1304-245">有 _change_、_add_ 或 _remove_ 等值。</span><span class="sxs-lookup"><span data-stu-id="c1304-245">Values are _change_, _add_, or _remove_.</span></span>
- <span data-ttu-id="c1304-246">impact - 對每個環境來說，每個變更的重要性不一定相同。</span><span class="sxs-lookup"><span data-stu-id="c1304-246">impact — Not all changes will be equally important to every environment.</span></span> <span data-ttu-id="c1304-247">此元素說明此變更與其對企業網路周邊環境造成的影響。</span><span class="sxs-lookup"><span data-stu-id="c1304-247">This element describes the expected impact to an enterprise network perimeter environment as a result of this change.</span></span> <span data-ttu-id="c1304-248">此元素僅包含在 **2018112800** 和更新版本的變更記錄中。</span><span class="sxs-lookup"><span data-stu-id="c1304-248">This element is included only in change records of version **2018112800** and later.</span></span> <span data-ttu-id="c1304-249">影響選項如下：- AddedIp - IP 位址已新增至 Office 365，而且很快就能在服務上生效。</span><span class="sxs-lookup"><span data-stu-id="c1304-249">Options for the impact are: — AddedIp – An IP address was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="c1304-250">這表示您需要在防火牆或其他第 3 層網路周邊裝置上執行變更。</span><span class="sxs-lookup"><span data-stu-id="c1304-250">This represents a change you need to take on a firewall or other layer 3 network perimeter device.</span></span> <span data-ttu-id="c1304-251">如果您沒有在我們開始使用此 IP 位址之前新增此 IP 位址，您可能會遇到服務中斷的情形。</span><span class="sxs-lookup"><span data-stu-id="c1304-251">If you don’t add this before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="c1304-252">- AddedUrl - URL 已新增至 Office 365，而且很快就能在服務上生效。</span><span class="sxs-lookup"><span data-stu-id="c1304-252">— AddedUrl – A URL was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="c1304-253">這表示您需要在 Proxy 伺服器或 URL 剖析網路周邊裝置上執行變更。</span><span class="sxs-lookup"><span data-stu-id="c1304-253">This represents a change you need to take on a proxy server or URL parsing network perimeter device.</span></span> <span data-ttu-id="c1304-254">如果您沒有在我們開始使用此 URL 之前新增此 URL，您可能會遇到服務中斷的情形。</span><span class="sxs-lookup"><span data-stu-id="c1304-254">If you don’t add this URL before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="c1304-255">- AddedIpAndUrl - IP 位址和 URL 兩者皆已新增。</span><span class="sxs-lookup"><span data-stu-id="c1304-255">— AddedIpAndUrl — Both an IP address and a URL were added.</span></span> <span data-ttu-id="c1304-256">這表示您需要在防火牆第 3 層裝置、Proxy 伺服器或 URL 剖析裝置上執行變更。</span><span class="sxs-lookup"><span data-stu-id="c1304-256">This represents a change you need to take on either a firewall layer 3 device or a proxy server or URL parsing device.</span></span> <span data-ttu-id="c1304-257">如果您沒有在我們開始使用此 IP/URL 組合之前新增此 IP/URL 組合，您可能會遇到服務中斷的情形。</span><span class="sxs-lookup"><span data-stu-id="c1304-257">If you don’t add this IP/URL pair before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="c1304-258">- RemovedIpOrUrl - 已從 Office 365 移除至少一個 IP 位址或 URL。</span><span class="sxs-lookup"><span data-stu-id="c1304-258">— RemovedIpOrUrl – At least one IP address or URL was removed from Office 365.</span></span> <span data-ttu-id="c1304-259">請從您的周邊裝置移除網路端點，但沒有限制您要在什麼時候之前完成此動作。</span><span class="sxs-lookup"><span data-stu-id="c1304-259">Remove the network endpoints from your perimeter devices, but there’s no deadline for you to do this.</span></span>
  <span data-ttu-id="c1304-260">- ChangedIsExpressRoute - ExpressRoute 支援屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="c1304-260">— ChangedIsExpressRoute – The ExpressRoute support attribute was changed.</span></span> <span data-ttu-id="c1304-261">如果您使用 ExpressRoute，根據您的組態，您可能需要採取動作。</span><span class="sxs-lookup"><span data-stu-id="c1304-261">If you use ExpressRoute, you might need to take action depending on your configuration.</span></span>
  <span data-ttu-id="c1304-262">- MovedIpOrUrl - 我們已在此端點集和另一個端點集之間移動 IP 位址或 URL。</span><span class="sxs-lookup"><span data-stu-id="c1304-262">— MovedIpOrUrl – We moved an IP address or Url between this endpoint set and another one.</span></span> <span data-ttu-id="c1304-263">通常您不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="c1304-263">Generally no action is required.</span></span>
  <span data-ttu-id="c1304-264">- RemovedDuplicateIpOrUrl - 我們已移除重複的 IP 位址或 URL，但仍會在 Office 365 上發佈。</span><span class="sxs-lookup"><span data-stu-id="c1304-264">— RemovedDuplicateIpOrUrl – We removed a duplicate IP address or Url but it’s still published for Office 365.</span></span> <span data-ttu-id="c1304-265">通常您不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="c1304-265">Generally no action is required.</span></span>
  <span data-ttu-id="c1304-266">- OtherNonPriorityChanges – 我們已變更重要性比其他所有選項低的一些項目，例如附註欄位的內容。</span><span class="sxs-lookup"><span data-stu-id="c1304-266">— OtherNonPriorityChanges – We changed something less critical than all of the other options, such as the contents of a note field.</span></span>
- <span data-ttu-id="c1304-p139">version - 在其中引入變更的已發佈端點集版本。版本號碼的格式為 _YYYYMMDDNN_，其中 _NN_ 是當一天中有多個版本需要發佈時，遞增的自然數。</span><span class="sxs-lookup"><span data-stu-id="c1304-p139">version — The version of the published endpoint set in which the change was introduced. Version numbers are of the format _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day.</span></span>
- <span data-ttu-id="c1304-269">previous - 子結構，詳細說明端點集上已變更元素的舊值。</span><span class="sxs-lookup"><span data-stu-id="c1304-269">previous — A substructure detailing previous values of changed elements on the endpoint set.</span></span> <span data-ttu-id="c1304-270">不會對最近新增的端點集包含此設定。</span><span class="sxs-lookup"><span data-stu-id="c1304-270">This will not be included for newly added endpoint sets.</span></span> <span data-ttu-id="c1304-271">包含 _ExpressRoute_、_serviceArea_、_category_、_required_、_tcpPorts_、_udpPorts_ 和 _notes_。</span><span class="sxs-lookup"><span data-stu-id="c1304-271">Includes  _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="c1304-272">current - 子結構，詳細說明端點集上已變更元素的更新值。</span><span class="sxs-lookup"><span data-stu-id="c1304-272">current — A substructure detailing updated values of changes elements on the endpoint set.</span></span> <span data-ttu-id="c1304-273">包含 _ExpressRoute_、_serviceArea_、_category_、_required_、_tcpPorts_、_udpPorts_ 和 _notes_。</span><span class="sxs-lookup"><span data-stu-id="c1304-273">Includes _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="c1304-274">add - 子結構，詳細說明要新增至端點集集合的項目。</span><span class="sxs-lookup"><span data-stu-id="c1304-274">add — A substructure detailing items to be added to endpoint set collections.</span></span> <span data-ttu-id="c1304-275">如果沒有新增項目則省略。</span><span class="sxs-lookup"><span data-stu-id="c1304-275">Omitted if there are no additions.</span></span>
  <span data-ttu-id="c1304-276">- effectiveDate - 定義新增項目在服務中生效的日期。</span><span class="sxs-lookup"><span data-stu-id="c1304-276">— effectiveDate — Defines the data when the additions will be live in the service.</span></span>
  <span data-ttu-id="c1304-277">- ips - 要新增至 _ips_ 陣列的項目。</span><span class="sxs-lookup"><span data-stu-id="c1304-277">— ips — Items to be added to the _ips_ array.</span></span>
  <span data-ttu-id="c1304-278">- urls - 要新增至 _urls_ 陣列的項目。</span><span class="sxs-lookup"><span data-stu-id="c1304-278">— urls- Items to be added to the _urls_ array.</span></span>
- <span data-ttu-id="c1304-279">- remove - 子結構，詳細說明要從端點集移除的項目。</span><span class="sxs-lookup"><span data-stu-id="c1304-279">remove — A substructure detailing items to be removed from the endpoint set.</span></span> <span data-ttu-id="c1304-280">如果沒有移除項目則省略。</span><span class="sxs-lookup"><span data-stu-id="c1304-280">Omitted if there are no removals.</span></span>
  <span data-ttu-id="c1304-281">- ips - 要從 _ips_ 陣列移除的項目。</span><span class="sxs-lookup"><span data-stu-id="c1304-281">— ips — Items to be removed from the _ips_ array.</span></span>
  <span data-ttu-id="c1304-282">- urls - 要從 _urls_ 陣列移除的項目。</span><span class="sxs-lookup"><span data-stu-id="c1304-282">— urls- Items to be removed from the _urls_ array.</span></span>

### <a name="examples"></a><span data-ttu-id="c1304-283">範例:</span><span class="sxs-lookup"><span data-stu-id="c1304-283">Examples:</span></span>

<span data-ttu-id="c1304-284">範例 1 要求 URI：[https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="c1304-284">Example 1 request URI: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="c1304-p144">這會要求對 Office 365 全球服務執行個體所做的所有先前變更。範例結果：</span><span class="sxs-lookup"><span data-stu-id="c1304-p144">This requests all previous changes to the Office 365 worldwide service instance. Example result:</span></span>

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

<span data-ttu-id="c1304-287">範例 2 要求 URI：[https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="c1304-287">Example 2 request URI: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="c1304-p145">這會要求從 Office 365 全球執行個體指定版本之後的變更。在此案例中，指定版本是最新版本。範例結果：</span><span class="sxs-lookup"><span data-stu-id="c1304-p145">This requests changes since the specified version to the Office 365 Worldwide instance. In this case, the version specified is the latest. Example result:</span></span>

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a><span data-ttu-id="c1304-291">範例 PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="c1304-291">Example PowerShell Script</span></span>

<span data-ttu-id="c1304-292">您可以執行此 PowerShell 指令碼，查看是否有需要針對已更新資料採取的動作。</span><span class="sxs-lookup"><span data-stu-id="c1304-292">You can run this PowerShell script to see if there are actions you need to take for updated data.</span></span> <span data-ttu-id="c1304-293">您可以將此指令碼當成是檢查版本更新的排程工作來執行。</span><span class="sxs-lookup"><span data-stu-id="c1304-293">You can run this script as a scheduled task to check for a version update.</span></span> <span data-ttu-id="c1304-294">為避免對 Web 服務造成過度的負載，請勿嘗試在一小時內執行指令碼一次以上。</span><span class="sxs-lookup"><span data-stu-id="c1304-294">To avoid excessive load on the web service, try not to run the script more than once an hour.</span></span>

<span data-ttu-id="c1304-295">此指令碼會執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c1304-295">The script does the following:</span></span>

- <span data-ttu-id="c1304-296">透過呼叫 Web 服務 REST API，檢查目前 Office 365 全球執行個體端點的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="c1304-296">Checks the version number of the current Office 365 Worldwide instance endpoints by calling the web service REST API.</span></span>
- <span data-ttu-id="c1304-297">檢查位於 _$Env:TEMP\O365_endpoints_latestversion.txt_ 的目前版本檔案。</span><span class="sxs-lookup"><span data-stu-id="c1304-297">Checks for a current version file at _$Env:TEMP\O365_endpoints_latestversion.txt_.</span></span> <span data-ttu-id="c1304-298">全域變數 **$Env:TEMP** 的路徑通常是 _C:\Users\\<username\>\AppData\Local\Temp_。</span><span class="sxs-lookup"><span data-stu-id="c1304-298">The path of the global variable **$Env:TEMP** is usually _C:\Users\\<username\>\AppData\Local\Temp_.</span></span>
- <span data-ttu-id="c1304-299">如果這是第一次執行指令碼，指令碼會傳回目前的版本、目前所有的 IP 位址和 URL，然後將端點版本寫入至檔案 _$Env:TEMP\O365_endpoints_latestversion.txt_，接著將端點資料輸出至檔案 _$Env:TEMP\O365_endpoints_data.txt_。</span><span class="sxs-lookup"><span data-stu-id="c1304-299">If this is the first time the script has been run, the script returns the current version and all current IP addresses and URLs, writes the endpoints version to the file _$Env:TEMP\O365_endpoints_latestversion.txt_ and the endpoints data output to the file _$Env:TEMP\O365_endpoints_data.txt_.</span></span> <span data-ttu-id="c1304-300">您可以修改路徑和/或輸出檔案的名稱，方法是編輯這些指令行：</span><span class="sxs-lookup"><span data-stu-id="c1304-300">You can modify the path and/or name of the output file by editing these lines:</span></span>

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- <span data-ttu-id="c1304-301">後續每次執行指令碼時，如果最新的 Web 服務版本與 _O365_endpoints_latestversion.txt_ 檔案中的版本完全相同時，指令碼會不做任何變更就結束。</span><span class="sxs-lookup"><span data-stu-id="c1304-301">On each subsequent execution of the script, if the latest web service version is identical to the version in the _O365_endpoints_latestversion.txt_ file, the script exits without making any changes.</span></span>
- <span data-ttu-id="c1304-302">當最新的 Web 服務版本比 _O365_endpoints_latestversion.txt_ 檔案中的版本還要新時，指令碼會傳回端點並篩選出 **Allow** 和 **Optimize** 類別的端點，更新 _O365_endpoints_latestversion.txt_ 檔案中的版本，然後將已更新資料寫入至 _O365_endpoints_data.txt_ 檔案。</span><span class="sxs-lookup"><span data-stu-id="c1304-302">When the latest web service version is newer than the version in the _O365_endpoints_latestversion.txt_ file, the script returns the endpoints and filters for the **Allow** and **Optimize** category endpoints, updates the version in the _O365_endpoints_latestversion.txt_ file, and writes the updated data to the _O365_endpoints_data.txt_ file.</span></span>

<span data-ttu-id="c1304-303">指令碼會針對其執行所在的電腦產生唯一 _ClientRequestId_，並在多個呼叫之間重複使用此識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1304-303">The script generates a unique _ClientRequestId_ for the computer it is executed on, and reuses this ID across multiple calls.</span></span> <span data-ttu-id="c1304-304">此識別碼會儲存在 _O365_endpoints_latestversion.txt_ 檔案。</span><span class="sxs-lookup"><span data-stu-id="c1304-304">This ID is stored in the _O365_endpoints_latestversion.txt_ file.</span></span>

### <a name="to-run-the-powershell-script"></a><span data-ttu-id="c1304-305">執行 PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="c1304-305">To run the PowerShell script</span></span>

1. <span data-ttu-id="c1304-306">複製指令碼，並將指令碼儲存至本機硬碟或指令碼位置，儲存名稱為 _Get-O365WebServiceUpdates.ps1_。</span><span class="sxs-lookup"><span data-stu-id="c1304-306">Copy the script and save it to your local hard drive or script location as _Get-O365WebServiceUpdates.ps1_.</span></span>
1. <span data-ttu-id="c1304-307">在您慣用的指令碼編輯器中執行此指令碼，例如 PowerShell ISE 或 VS Code，或在 PowerShell 主控台使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="c1304-307">Execute the script in your preferred script editor such as the PowerShell ISE or VS Code, or from a PowerShell console using the following command:</span></span>

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    <span data-ttu-id="c1304-308">沒有參數傳遞給指令碼。</span><span class="sxs-lookup"><span data-stu-id="c1304-308">There are no parameters to pass to the script.</span></span>

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a><span data-ttu-id="c1304-309">範例 Python 指令碼</span><span class="sxs-lookup"><span data-stu-id="c1304-309">Example Python Script</span></span>

<span data-ttu-id="c1304-p150">以下是 Python 指令碼 (在 Windows 10 上以 Python 3.6.3 進行測試)，您可以執行以查看是否需要針對更新的資料採取動作。此指令碼會檢查 Office 365 全球執行個體端點的版本號碼。有變更時，它會針對 _允許_ 和 _最佳化_ 分類端點，下載端點和篩選條件。它也會在多個呼叫之間使用唯一的 ClientRequestId，並且儲存在暫存檔案中找到的最新版本。您應該一小時呼叫此指令碼一次，以檢查版本更新。</span><span class="sxs-lookup"><span data-stu-id="c1304-p150">Here is a Python script, tested with Python 3.6.3 on Windows 10, that you can run to see if there are actions you need to take for updated data. This script checks the version number for the Office 365 Worldwide instance endpoints. When there is a change, it downloads the endpoints and filters for the _Allow_ and _Optimize_ category endpoints. It also uses a unique ClientRequestId across multiple calls and saves the latest version found in a temporary file. You should call this script once an hour to check for a version update.</span></span>

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a><span data-ttu-id="c1304-315">Web 服務介面版本設定</span><span class="sxs-lookup"><span data-stu-id="c1304-315">Web Service interface versioning</span></span>

<span data-ttu-id="c1304-p151">未來可能需要對於這些 Web 服務方法的參數或結果更新。在這些 Web 服務的正式運作版本發行之後，Microsoft 會致力於提供 Web 服務材料更新的事先通知。當 Microsoft 認為需要對使用 Web 服務的用戶端進行更新時，Microsoft 會讓舊版 (上一個版本) Web 服務在新版本發行之後，仍然保持至少 12 個月可用。在這段期間未升級的客戶可能無法存取 Web 服務及其方法。如果對 Web 服務介面簽章進行下列變更，客戶必須確保 Web 服務的用戶端持續運作且沒有錯誤：</span><span class="sxs-lookup"><span data-stu-id="c1304-p151">Updates to the parameters or results for these web service methods may be required in the future. After the general availability version of these web services is published, Microsoft will make reasonable efforts to provide advance notice of material updates to the web service. When Microsoft believes that an update will require changes to clients using the web service, Microsoft will keep the previous version (one version back) of the web service available for at least 12 months after the release of the new version. Customers who do not upgrade during that time may be unable to access the web service and its methods. Customers must ensure that clients of the web service continue working without error if the following changes are made to the web service interface signature:</span></span>

- <span data-ttu-id="c1304-321">將新的選擇性參數新增至現有 Web 方法，該方法不一定要由舊的用戶端提供，且不會影響舊用戶端接收的結果。</span><span class="sxs-lookup"><span data-stu-id="c1304-321">Adding a new optional parameter to an existing web method that doesn't have to be provided by older clients and doesn't impact the result an older client receives.</span></span>
- <span data-ttu-id="c1304-322">將其中一個回應 REST 項目中的具名屬性或額外資料行新增至回應 CSV。</span><span class="sxs-lookup"><span data-stu-id="c1304-322">Adding a new named attribute in one of the response REST items or additional columns to the response CSV.</span></span>
- <span data-ttu-id="c1304-323">新增具有新名稱 (不是舊用戶端使用的名稱) 的新 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="c1304-323">Adding a new web method with a new name that is not called by the older clients.</span></span>

## <a name="update-notifications"></a><span data-ttu-id="c1304-324">更新通知</span><span class="sxs-lookup"><span data-stu-id="c1304-324">Update notifications</span></span>

<span data-ttu-id="c1304-325">當 IP 位址和 URL 的變更發佈至 Web 服務時，您可以使用數種不同的方法取得電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="c1304-325">You can use a few different methods to get email notifications when changes to the IP addresses and URLs are published to the web service.</span></span>

- <span data-ttu-id="c1304-326">若要使用 Microsoft Flow 解決方案，請參閱[使用 Microsoft Flow 接收有關 Office 365 IP 位址和 URL 變更的電子郵件](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651)。</span><span class="sxs-lookup"><span data-stu-id="c1304-326">To use a Microsoft Flow solution, see [Use Microsoft Flow to receive an email for changes to Office 365 IP Addresses and URLs](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span></span>
- <span data-ttu-id="c1304-327">若要使用 ARM 範本部署 Azure Logic App，請參閱 [Office 365 更新通知 (v1.1)](https://aka.ms/ipurlws-updates-template)。</span><span class="sxs-lookup"><span data-stu-id="c1304-327">To deploy an Azure Logic App using an ARM template, see [Office 365 Update Notification (v1.1)](https://aka.ms/ipurlws-updates-template).</span></span>
- <span data-ttu-id="c1304-328">若要使用 PowerShell 撰寫您自己的通知指令碼，請參閱 [Send-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage)。</span><span class="sxs-lookup"><span data-stu-id="c1304-328">To write your own notification script using PowerShell, see [Send-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage).</span></span>

## <a name="exporting-a-proxy-pac-file"></a><span data-ttu-id="c1304-329">匯出 Proxy PAC 檔案</span><span class="sxs-lookup"><span data-stu-id="c1304-329">Exporting a Proxy PAC file</span></span>

<span data-ttu-id="c1304-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) 是 PowerShell 指令碼，會讀取來自 Office 365 IP 位址和 URL Web 服務的最新網路端點，並建立範例 PAC 檔案。</span><span class="sxs-lookup"><span data-stu-id="c1304-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is a PowerShell script that reads the latest network endpoints from the Office 365 IP Address and URL web service and creates a sample PAC file.</span></span> <span data-ttu-id="c1304-331">如需有關使用 Get-PacFile 的詳細資訊，請參閱[使用 PAC 檔案進行重要 Office 365 流量的直接路由傳送](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic)。</span><span class="sxs-lookup"><span data-stu-id="c1304-331">For information on using Get-PacFile, see [Use a PAC file for direct routing of vital Office 365 traffic](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c1304-332">相關主題</span><span class="sxs-lookup"><span data-stu-id="c1304-332">Related Topics</span></span>
  
[<span data-ttu-id="c1304-333">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="c1304-333">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="c1304-334">管理 Office 365 端點</span><span class="sxs-lookup"><span data-stu-id="c1304-334">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)
  
[<span data-ttu-id="c1304-335">Office 365 端點常見問題集</span><span class="sxs-lookup"><span data-stu-id="c1304-335">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[<span data-ttu-id="c1304-336">Office 365 網路連線原則</span><span class="sxs-lookup"><span data-stu-id="c1304-336">Office 365 Network Connectivity Principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="c1304-337">Office 365 網路與效能調整</span><span class="sxs-lookup"><span data-stu-id="c1304-337">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="c1304-338">評估 Office 365 網路連線能力</span><span class="sxs-lookup"><span data-stu-id="c1304-338">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
[<span data-ttu-id="c1304-339">商務用 Skype Online 中的媒體品質和網路連線效能</span><span class="sxs-lookup"><span data-stu-id="c1304-339">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[<span data-ttu-id="c1304-340">針對商務用 Skype Online 最佳化您的網路</span><span class="sxs-lookup"><span data-stu-id="c1304-340">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[<span data-ttu-id="c1304-341">使用基準與效能歷程記錄進行 Office 365 效能調整</span><span class="sxs-lookup"><span data-stu-id="c1304-341">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)
  
[<span data-ttu-id="c1304-342">Office 365 的效能疑難排解規劃</span><span class="sxs-lookup"><span data-stu-id="c1304-342">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)