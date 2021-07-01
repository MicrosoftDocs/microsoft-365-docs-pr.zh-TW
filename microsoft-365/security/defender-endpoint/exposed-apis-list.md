---
title: 受支援的適用於端點的 Microsoft Defender API
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 3f0f7a2b6a10c3469f0689419934fd8d19070999
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228624"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="53fd4-104">受支援的適用於端點的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="53fd4-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="53fd4-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="53fd4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="53fd4-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="53fd4-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="53fd4-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="53fd4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="53fd4-108">端點 URI 及版本設定</span><span class="sxs-lookup"><span data-stu-id="53fd4-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="53fd4-109">端點 URI</span><span class="sxs-lookup"><span data-stu-id="53fd4-109">Endpoint URI</span></span>

> <span data-ttu-id="53fd4-110">服務基底 URI 是： [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="53fd4-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="53fd4-111">以查詢為基礎的 OData 具有 '/api ' 前置詞。</span><span class="sxs-lookup"><span data-stu-id="53fd4-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="53fd4-112">例如，若要取得提醒，您可以將 GET 要求傳送至 [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="53fd4-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="53fd4-113">版本設定</span><span class="sxs-lookup"><span data-stu-id="53fd4-113">Versioning</span></span>

> <span data-ttu-id="53fd4-114">API 支援版本設定。</span><span class="sxs-lookup"><span data-stu-id="53fd4-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="53fd4-115">目前的版本是第 **1.0** 版。</span><span class="sxs-lookup"><span data-stu-id="53fd4-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="53fd4-116">若要使用特定版本，請使用此格式： `https://api.securitycenter.microsoft.com/api/{Version}` 。</span><span class="sxs-lookup"><span data-stu-id="53fd4-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="53fd4-117">例如：`https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="53fd4-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="53fd4-118">如果您未指定任何版本 (例如 `https://api.securitycenter.microsoft.com/api/alerts`) 您將會到達最新的版本。</span><span class="sxs-lookup"><span data-stu-id="53fd4-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts`) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="53fd4-119">深入瞭解您可以執行 API 呼叫的個別支援實體和詳細資料，例如 HTTP 要求值、要求標頭和預期的回應。</span><span class="sxs-lookup"><span data-stu-id="53fd4-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="53fd4-120">本節內容</span><span class="sxs-lookup"><span data-stu-id="53fd4-120">In this section</span></span>

<span data-ttu-id="53fd4-121">主題</span><span class="sxs-lookup"><span data-stu-id="53fd4-121">Topic</span></span> | <span data-ttu-id="53fd4-122">描述</span><span class="sxs-lookup"><span data-stu-id="53fd4-122">Description</span></span>
:---|:---
[<span data-ttu-id="53fd4-123">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="53fd4-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="53fd4-124">從 API 執行查詢。</span><span class="sxs-lookup"><span data-stu-id="53fd4-124">Run queries from API.</span></span>
[<span data-ttu-id="53fd4-125">警示方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="53fd4-126">執行 API 通話（如 \- 取得提醒、建立警示、更新警示等等）。</span><span class="sxs-lookup"><span data-stu-id="53fd4-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="53fd4-127">匯出每台裝置的評估方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-127">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md) | <span data-ttu-id="53fd4-128">執行 API 呼叫，以依據每個裝置來收集漏洞評估，例如： \- 匯出安全設定評估、匯出軟體清查評估、匯出軟體漏洞評估，以及增量匯出軟體漏洞評估。</span><span class="sxs-lookup"><span data-stu-id="53fd4-128">Run API calls to gather vulnerability assessments on a per-device basis, such as: \- export secure configuration assessment, export software inventory assessment,  export software vulnerabilities assessment, and delta export software vulnerabilities assessment.</span></span>
[<span data-ttu-id="53fd4-129">自動化調查方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-129">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="53fd4-130">執行 API 通話（如 \- 取得調查的集合）。</span><span class="sxs-lookup"><span data-stu-id="53fd4-130">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="53fd4-131">取得網域相關警示</span><span class="sxs-lookup"><span data-stu-id="53fd4-131">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="53fd4-132">執行 API 通話，例如 \- 取得與網域相關的裝置、網域統計資料等等。</span><span class="sxs-lookup"><span data-stu-id="53fd4-132">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="53fd4-133">檔案方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-133">File methods and properties</span></span>](files.md) | <span data-ttu-id="53fd4-134">執行 API 通話，例如 \- get file information、file 相關的警示、檔相關的裝置及檔案統計資料。</span><span class="sxs-lookup"><span data-stu-id="53fd4-134">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="53fd4-135">指示器方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-135">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="53fd4-136">執行 API 呼叫，例如 \- Get 指示器、Create 指示器及 Delete 指示器。</span><span class="sxs-lookup"><span data-stu-id="53fd4-136">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="53fd4-137">取得 IP 相關警示</span><span class="sxs-lookup"><span data-stu-id="53fd4-137">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="53fd4-138">執行 API 通話，例如 \- 取得 ip 相關的警示，以及取得 ip 統計資料。</span><span class="sxs-lookup"><span data-stu-id="53fd4-138">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="53fd4-139">電腦方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-139">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="53fd4-140">執行 API 通話，例如 \- get 裝置、依識別碼取得裝置、登入使用者的相關資訊、編輯標記等等。</span><span class="sxs-lookup"><span data-stu-id="53fd4-140">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="53fd4-141">電腦動作方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-141">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="53fd4-142">執行 [隔離] 等 API 呼叫 \- ，執行反病毒掃描等等。</span><span class="sxs-lookup"><span data-stu-id="53fd4-142">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="53fd4-143">建議方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-143">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="53fd4-144">執行 API 通話，例如 \- 依識別碼取得建議。</span><span class="sxs-lookup"><span data-stu-id="53fd4-144">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="53fd4-145">補救活動方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-145">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="53fd4-146">執行 API 呼叫，例如 \- 取得所有修復工作、取得公開的裝置修復工作，並依識別碼取得一個修復工作。</span><span class="sxs-lookup"><span data-stu-id="53fd4-146">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="53fd4-147">分數方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-147">Score methods and properties</span></span>](score.md) | <span data-ttu-id="53fd4-148">執行 API 通話（如 \- 取得披露分數或取得裝置安全分數）。</span><span class="sxs-lookup"><span data-stu-id="53fd4-148">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="53fd4-149">軟體方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-149">Software methods and properties</span></span>](software.md) | <span data-ttu-id="53fd4-150">\-依軟體執行清單漏洞等 API 通話。</span><span class="sxs-lookup"><span data-stu-id="53fd4-150">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="53fd4-151">使用者方法</span><span class="sxs-lookup"><span data-stu-id="53fd4-151">User methods</span></span>](user.md) | <span data-ttu-id="53fd4-152">執行 API 通話，例如 \- 取得使用者相關的警示和使用者相關的裝置。</span><span class="sxs-lookup"><span data-stu-id="53fd4-152">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="53fd4-153">弱點方法和屬性</span><span class="sxs-lookup"><span data-stu-id="53fd4-153">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="53fd4-154">依弱點執行 API 通話（如 \- 清單裝置）。</span><span class="sxs-lookup"><span data-stu-id="53fd4-154">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="53fd4-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="53fd4-155">See also</span></span>

- [<span data-ttu-id="53fd4-156">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="53fd4-156">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="53fd4-157">Microsoft Defender for Endpoint API 發行附注</span><span class="sxs-lookup"><span data-stu-id="53fd4-157">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
