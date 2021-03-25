---
title: 支援的 Microsoft Defender for Endpoint APIs
ms.reviewer: ''
description: 深入瞭解 Microsoft Defender for Endpoint 實體的特定支援，您可以在其中建立 API 呼叫。
keywords: api，支援的 api，主角，警示，裝置，使用者，網域，ip，檔案，高級查詢，高級搜尋
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
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198316"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="ff200-104">支援的 Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="ff200-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ff200-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ff200-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ff200-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ff200-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ff200-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ff200-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="ff200-108">端點 URI 及版本設定</span><span class="sxs-lookup"><span data-stu-id="ff200-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="ff200-109">端點 URI：</span><span class="sxs-lookup"><span data-stu-id="ff200-109">Endpoint URI:</span></span>

> <span data-ttu-id="ff200-110">服務基底 URI 是： https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ff200-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="ff200-111">以查詢為基礎的 OData 具有 '/api ' 前置詞。</span><span class="sxs-lookup"><span data-stu-id="ff200-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="ff200-112">例如，若要取得提醒，您可以將 GET 要求傳送至 https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="ff200-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="ff200-113">版本：</span><span class="sxs-lookup"><span data-stu-id="ff200-113">Versioning:</span></span>

> <span data-ttu-id="ff200-114">API 支援版本設定。</span><span class="sxs-lookup"><span data-stu-id="ff200-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="ff200-115">目前的版本是第 **1.0** 版。</span><span class="sxs-lookup"><span data-stu-id="ff200-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="ff200-116">若要使用特定版本，請使用此格式： `https://api.securitycenter.microsoft.com/api/{Version}` 。</span><span class="sxs-lookup"><span data-stu-id="ff200-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="ff200-117">例如：`https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="ff200-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="ff200-118">如果您未指定任何版本 (例如 https://api.securitycenter.microsoft.com/api/alerts ) 您將會到達最新的版本。</span><span class="sxs-lookup"><span data-stu-id="ff200-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="ff200-119">深入瞭解您可以執行 API 呼叫的個別支援實體和詳細資料，例如 HTTP 要求值、要求標頭和預期的回應。</span><span class="sxs-lookup"><span data-stu-id="ff200-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ff200-120">本節內容</span><span class="sxs-lookup"><span data-stu-id="ff200-120">In this section</span></span>

<span data-ttu-id="ff200-121">主題</span><span class="sxs-lookup"><span data-stu-id="ff200-121">Topic</span></span> | <span data-ttu-id="ff200-122">描述</span><span class="sxs-lookup"><span data-stu-id="ff200-122">Description</span></span>
:---|:---
<span data-ttu-id="ff200-123">高級搜尋</span><span class="sxs-lookup"><span data-stu-id="ff200-123">Advanced Hunting</span></span> | <span data-ttu-id="ff200-124">從 API 執行查詢。</span><span class="sxs-lookup"><span data-stu-id="ff200-124">Run queries from API.</span></span>
<span data-ttu-id="ff200-125">警示</span><span class="sxs-lookup"><span data-stu-id="ff200-125">Alerts</span></span> | <span data-ttu-id="ff200-126">執行 API 通話（如取得提醒、建立警示、更新警示等等）。</span><span class="sxs-lookup"><span data-stu-id="ff200-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="ff200-127">網域</span><span class="sxs-lookup"><span data-stu-id="ff200-127">Domains</span></span> | <span data-ttu-id="ff200-128">執行 API 通話，例如取得與網域相關的裝置、網域統計資料等等。</span><span class="sxs-lookup"><span data-stu-id="ff200-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="ff200-129">檔案</span><span class="sxs-lookup"><span data-stu-id="ff200-129">Files</span></span> | <span data-ttu-id="ff200-130">執行 API 通話，例如 get file information、file 相關的警示、檔相關的裝置及檔案統計資料。</span><span class="sxs-lookup"><span data-stu-id="ff200-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="ff200-131">Ip</span><span class="sxs-lookup"><span data-stu-id="ff200-131">IPs</span></span> | <span data-ttu-id="ff200-132">執行 API 通話，例如取得 IP 相關的警示，以及取得 IP 統計資料。</span><span class="sxs-lookup"><span data-stu-id="ff200-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="ff200-133">機器</span><span class="sxs-lookup"><span data-stu-id="ff200-133">Machines</span></span> | <span data-ttu-id="ff200-134">執行 API 通話，例如 get 裝置、依識別碼取得裝置、登入使用者的相關資訊、編輯標記等等。</span><span class="sxs-lookup"><span data-stu-id="ff200-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="ff200-135">電腦動作</span><span class="sxs-lookup"><span data-stu-id="ff200-135">Machine Actions</span></span> | <span data-ttu-id="ff200-136">執行 [隔離] 等 API 呼叫，執行反病毒掃描等等。</span><span class="sxs-lookup"><span data-stu-id="ff200-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="ff200-137">指標</span><span class="sxs-lookup"><span data-stu-id="ff200-137">Indicators</span></span> | <span data-ttu-id="ff200-138">執行 API 呼叫，例如建立指示器、取得指示器和刪除指示器。</span><span class="sxs-lookup"><span data-stu-id="ff200-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="ff200-139">使用者</span><span class="sxs-lookup"><span data-stu-id="ff200-139">Users</span></span> | <span data-ttu-id="ff200-140">執行 API 通話，例如取得使用者相關的警示和使用者相關的裝置。</span><span class="sxs-lookup"><span data-stu-id="ff200-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="ff200-141">分數</span><span class="sxs-lookup"><span data-stu-id="ff200-141">Score</span></span> | <span data-ttu-id="ff200-142">執行 API 通話（如取得披露分數或取得裝置安全分數）。</span><span class="sxs-lookup"><span data-stu-id="ff200-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="ff200-143">軟體</span><span class="sxs-lookup"><span data-stu-id="ff200-143">Software</span></span> | <span data-ttu-id="ff200-144">依軟體執行清單漏洞等 API 通話。</span><span class="sxs-lookup"><span data-stu-id="ff200-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="ff200-145">漏洞</span><span class="sxs-lookup"><span data-stu-id="ff200-145">Vulnerability</span></span> | <span data-ttu-id="ff200-146">依弱點執行 API 通話（如清單裝置）。</span><span class="sxs-lookup"><span data-stu-id="ff200-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="ff200-147">建議</span><span class="sxs-lookup"><span data-stu-id="ff200-147">Recommendation</span></span> | <span data-ttu-id="ff200-148">執行 API 通話，例如依識別碼取得建議。</span><span class="sxs-lookup"><span data-stu-id="ff200-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff200-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ff200-149">See also</span></span>
- [<span data-ttu-id="ff200-150">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="ff200-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
