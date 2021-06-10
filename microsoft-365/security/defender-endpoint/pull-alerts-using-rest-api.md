---
title: 使用 REST API 提取 Microsoft Defender for Endpoint 偵測
description: 瞭解如何使用 SIEM REST API 呼叫 Microsoft Defender for Endpoint API 端點以提取 JSON 格式的偵測。
keywords: 偵測、拉入檢測、rest api、要求、回應
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
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6716b0eb029b49ec08cb52ebefc23e50b19036ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771666"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="02ca2-104">使用 SIEM REST API 拉入 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="02ca2-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="02ca2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="02ca2-105">**Applies to:**</span></span>
- [<span data-ttu-id="02ca2-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="02ca2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="02ca2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02ca2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="02ca2-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="02ca2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="02ca2-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="02ca2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="02ca2-110">[Microsoft Defender For Endpoint Alert](alerts.md) 是由一或多個偵測所組成。</span><span class="sxs-lookup"><span data-stu-id="02ca2-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="02ca2-111">[Microsoft Defender For Endpoint 偵測](api-portal-mapping.md) 是由裝置上發生的可疑事件及其相關警示詳細資料所組成。</span><span class="sxs-lookup"><span data-stu-id="02ca2-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="02ca2-112">-Microsoft Defender for Endpoint Alert API 是最新的警示消耗 API，且包含每個警示的相關證據的詳細清單。</span><span class="sxs-lookup"><span data-stu-id="02ca2-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="02ca2-113">如需詳細資訊，請參閱 [Alert 方法和屬性](alerts.md) 和 [清單警示](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="02ca2-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="02ca2-114">Microsoft Defender for Endpoint 支援 OAuth 2.0 通訊協定，以從 API 提取偵測。</span><span class="sxs-lookup"><span data-stu-id="02ca2-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="02ca2-115">一般說來，OAuth 2.0 通訊協定支援四種類型的流量：</span><span class="sxs-lookup"><span data-stu-id="02ca2-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="02ca2-116">授權授與流程</span><span class="sxs-lookup"><span data-stu-id="02ca2-116">Authorization grant flow</span></span>
- <span data-ttu-id="02ca2-117">隱含流程</span><span class="sxs-lookup"><span data-stu-id="02ca2-117">Implicit flow</span></span>
- <span data-ttu-id="02ca2-118">用戶端認證流程</span><span class="sxs-lookup"><span data-stu-id="02ca2-118">Client credentials flow</span></span>
- <span data-ttu-id="02ca2-119">資源擁有者流程</span><span class="sxs-lookup"><span data-stu-id="02ca2-119">Resource owner flow</span></span>

<span data-ttu-id="02ca2-120">如需 OAuth 規格的詳細資訊，請參閱 [OAuth 網站](http://www.oauth.net)。</span><span class="sxs-lookup"><span data-stu-id="02ca2-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="02ca2-121">Microsoft Defender for Endpoint 支援 _授權授_ 與 _用戶端認證流程_，以取得提取偵測的存取權，Azure Active Directory (AAD) 為授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="02ca2-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="02ca2-122">_授權授與流程_ 會使用使用者認證取得授權碼，然後用來取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="02ca2-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="02ca2-123">_用戶端認證流程_ 會使用用戶端認證，以進行 Microsoft Defender for ENDPOINT 端點 URL 的驗證。</span><span class="sxs-lookup"><span data-stu-id="02ca2-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="02ca2-124">當 OAuth 用戶端建立不需要使用者認證之 API 的要求時，此流程適用案例。</span><span class="sxs-lookup"><span data-stu-id="02ca2-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="02ca2-125">在 Microsoft Defender for Endpoint API 中使用下列方法，以 JSON 格式提取偵測結果。</span><span class="sxs-lookup"><span data-stu-id="02ca2-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="02ca2-126">Microsoft Defender 資訊安全中心會將類似的警示偵測合併成單一警示。</span><span class="sxs-lookup"><span data-stu-id="02ca2-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="02ca2-127">此 API 會根據您設定的查詢參數，在其原始表單中拉入警示偵測，讓您能夠套用您自己的群組和篩選。</span><span class="sxs-lookup"><span data-stu-id="02ca2-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="02ca2-128">開始之前</span><span class="sxs-lookup"><span data-stu-id="02ca2-128">Before you begin</span></span>
- <span data-ttu-id="02ca2-129">呼叫 Microsoft Defender for endpoint 端點以提取偵測之前，您必須在 Azure Active Directory (AAD) 中啟用 SIEM 整合應用程式。</span><span class="sxs-lookup"><span data-stu-id="02ca2-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="02ca2-130">如需詳細資訊，請參閱 [ENABLE SIEM integration In Microsoft Defender For Endpoint](enable-siem-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="02ca2-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="02ca2-131">請記下 Azure 應用程式註冊中的下列值。</span><span class="sxs-lookup"><span data-stu-id="02ca2-131">Take note of the following values in your Azure application registration.</span></span> <span data-ttu-id="02ca2-132">您需要這些值來設定您的服務或守護程式應用程式中的 OAuth 流量：</span><span class="sxs-lookup"><span data-stu-id="02ca2-132">You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="02ca2-133">您的應用程式獨有的應用程式識別碼 () </span><span class="sxs-lookup"><span data-stu-id="02ca2-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="02ca2-134">您的應用程式) 的應用程式金鑰或機密 (</span><span class="sxs-lookup"><span data-stu-id="02ca2-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="02ca2-135">您的應用程式的 OAuth 2.0 token 端點</span><span class="sxs-lookup"><span data-stu-id="02ca2-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="02ca2-136">在應用程式頁面中，按一下 Azure 管理入口網站底部的 [ **查看端點** ]，以尋找此值。</span><span class="sxs-lookup"><span data-stu-id="02ca2-136">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page.</span></span> <span data-ttu-id="02ca2-137">端點會類似 `https://login.microsoftonline.com/{tenantId}/oauth2/token` 。</span><span class="sxs-lookup"><span data-stu-id="02ca2-137">The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="02ca2-138">取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="02ca2-138">Get an access token</span></span>
<span data-ttu-id="02ca2-139">在建立端點的呼叫之前，您必須取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="02ca2-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="02ca2-140">您將使用存取權杖來存取受保護的資源，這是 Microsoft Defender for Endpoint 中的偵測。</span><span class="sxs-lookup"><span data-stu-id="02ca2-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="02ca2-141">若要取得存取權杖，您必須對「簽發」端點執行 POST 要求。</span><span class="sxs-lookup"><span data-stu-id="02ca2-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="02ca2-142">以下是範例要求：</span><span class="sxs-lookup"><span data-stu-id="02ca2-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="02ca2-143">回應會包含存取權杖和到期資訊。</span><span class="sxs-lookup"><span data-stu-id="02ca2-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="02ca2-144">您現在可以在要求中使用 Defender for Endpoint API 的 *access_token* 欄位中的值。</span><span class="sxs-lookup"><span data-stu-id="02ca2-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="02ca2-145">請求</span><span class="sxs-lookup"><span data-stu-id="02ca2-145">Request</span></span>
<span data-ttu-id="02ca2-146">使用存取權杖，您的應用程式可以對 Microsoft Defender for Endpoint API 進行驗證要求。</span><span class="sxs-lookup"><span data-stu-id="02ca2-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="02ca2-147">您的應用程式必須將存取權杖附加至每個要求的授權標頭。</span><span class="sxs-lookup"><span data-stu-id="02ca2-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="02ca2-148">要求語法</span><span class="sxs-lookup"><span data-stu-id="02ca2-148">Request syntax</span></span>
<span data-ttu-id="02ca2-149">方法</span><span class="sxs-lookup"><span data-stu-id="02ca2-149">Method</span></span> | <span data-ttu-id="02ca2-150">要求 URI</span><span class="sxs-lookup"><span data-stu-id="02ca2-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="02ca2-151">GET</span><span class="sxs-lookup"><span data-stu-id="02ca2-151">GET</span></span>| <span data-ttu-id="02ca2-152">使用適用于您所在地區的 URI。</span><span class="sxs-lookup"><span data-stu-id="02ca2-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="02ca2-153">**對於歐盟**： `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="02ca2-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="02ca2-154">**我們**： `https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="02ca2-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="02ca2-155">若 **為 UK**：`https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="02ca2-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="02ca2-156">要求標頭</span><span class="sxs-lookup"><span data-stu-id="02ca2-156">Request header</span></span>
<span data-ttu-id="02ca2-157">頁首</span><span class="sxs-lookup"><span data-stu-id="02ca2-157">Header</span></span> | <span data-ttu-id="02ca2-158">類型</span><span class="sxs-lookup"><span data-stu-id="02ca2-158">Type</span></span> | <span data-ttu-id="02ca2-159">描述</span><span class="sxs-lookup"><span data-stu-id="02ca2-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="02ca2-160">授權</span><span class="sxs-lookup"><span data-stu-id="02ca2-160">Authorization</span></span> | <span data-ttu-id="02ca2-161">string</span><span class="sxs-lookup"><span data-stu-id="02ca2-161">string</span></span> | <span data-ttu-id="02ca2-162">必要。</span><span class="sxs-lookup"><span data-stu-id="02ca2-162">Required.</span></span> <span data-ttu-id="02ca2-163">表單 **持有** 者權杖中的 Azure AD 存取權杖 &lt;  &gt; 。</span><span class="sxs-lookup"><span data-stu-id="02ca2-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="02ca2-164">要求參數</span><span class="sxs-lookup"><span data-stu-id="02ca2-164">Request parameters</span></span>

<span data-ttu-id="02ca2-165">使用選用的查詢參數來指定及控制回應中傳回的資料量。</span><span class="sxs-lookup"><span data-stu-id="02ca2-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="02ca2-166">如果您呼叫此方法但未參數，則此回應會包含您的組織中過去2小時內的所有警示。</span><span class="sxs-lookup"><span data-stu-id="02ca2-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="02ca2-167">名稱</span><span class="sxs-lookup"><span data-stu-id="02ca2-167">Name</span></span> | <span data-ttu-id="02ca2-168">值</span><span class="sxs-lookup"><span data-stu-id="02ca2-168">Value</span></span>| <span data-ttu-id="02ca2-169">描述</span><span class="sxs-lookup"><span data-stu-id="02ca2-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="02ca2-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="02ca2-170">sinceTimeUtc</span></span> | <span data-ttu-id="02ca2-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="02ca2-171">DateTime</span></span> | <span data-ttu-id="02ca2-172">根據欄位，定義從下列位置檢索的綁定警示下限：</span><span class="sxs-lookup"><span data-stu-id="02ca2-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="02ca2-173">時間範圍將會是：從 sinceTimeUtc 時間到目前時間。</span><span class="sxs-lookup"><span data-stu-id="02ca2-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="02ca2-174">**附注**：如果未指定，則會檢索過去兩小時內產生的所有警示。</span><span class="sxs-lookup"><span data-stu-id="02ca2-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="02ca2-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="02ca2-175">untilTimeUtc</span></span> | <span data-ttu-id="02ca2-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="02ca2-176">DateTime</span></span> | <span data-ttu-id="02ca2-177">定義要檢索的上限時間限制。</span><span class="sxs-lookup"><span data-stu-id="02ca2-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="02ca2-178">時間範圍將會是：開始時間 `sinceTimeUtc` `untilTimeUtc` 。</span><span class="sxs-lookup"><span data-stu-id="02ca2-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="02ca2-179">**附注**：如果未指定，預設值將會是目前的時間。</span><span class="sxs-lookup"><span data-stu-id="02ca2-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="02ca2-180">前</span><span class="sxs-lookup"><span data-stu-id="02ca2-180">ago</span></span> | <span data-ttu-id="02ca2-181">string</span><span class="sxs-lookup"><span data-stu-id="02ca2-181">string</span></span> | <span data-ttu-id="02ca2-182">在下列時間範圍內拉入警示：「開始 `(current_time - ago)` `current_time` 時間。</span><span class="sxs-lookup"><span data-stu-id="02ca2-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="02ca2-183">值應該根據 **ISO 8601** 的持續時間格式設定</span><span class="sxs-lookup"><span data-stu-id="02ca2-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="02ca2-184">範例： `ago=PT10M` 會在過去10分鐘內提取接收到的提醒。</span><span class="sxs-lookup"><span data-stu-id="02ca2-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="02ca2-185">限制</span><span class="sxs-lookup"><span data-stu-id="02ca2-185">limit</span></span> | <span data-ttu-id="02ca2-186">int</span><span class="sxs-lookup"><span data-stu-id="02ca2-186">int</span></span> | <span data-ttu-id="02ca2-187">會定義要檢索的提醒數目。</span><span class="sxs-lookup"><span data-stu-id="02ca2-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="02ca2-188">會根據定義的數目來檢索最新的警示。</span><span class="sxs-lookup"><span data-stu-id="02ca2-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="02ca2-189">**附注**：如果未指定，則會檢索時間範圍內的所有可用警示。</span><span class="sxs-lookup"><span data-stu-id="02ca2-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="02ca2-190">machinegroups</span><span class="sxs-lookup"><span data-stu-id="02ca2-190">machinegroups</span></span> | <span data-ttu-id="02ca2-191">string</span><span class="sxs-lookup"><span data-stu-id="02ca2-191">string</span></span> | <span data-ttu-id="02ca2-192">指定要從中接收警示的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="02ca2-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="02ca2-193">**附注**：如果未指定，則會從所有裝置群組中檢索警示。</span><span class="sxs-lookup"><span data-stu-id="02ca2-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="02ca2-194">範例：</span><span class="sxs-lookup"><span data-stu-id="02ca2-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="02ca2-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="02ca2-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="02ca2-196">string</span><span class="sxs-lookup"><span data-stu-id="02ca2-196">string</span></span> | <span data-ttu-id="02ca2-197">登錄中的單一裝置標記。</span><span class="sxs-lookup"><span data-stu-id="02ca2-197">Single device tag from the registry.</span></span>
<span data-ttu-id="02ca2-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="02ca2-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="02ca2-199">string</span><span class="sxs-lookup"><span data-stu-id="02ca2-199">string</span></span> | <span data-ttu-id="02ca2-200">在 Microsoft Defender 資訊安全中心中建立的裝置標記。</span><span class="sxs-lookup"><span data-stu-id="02ca2-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="02ca2-201">要求範例</span><span class="sxs-lookup"><span data-stu-id="02ca2-201">Request example</span></span>
<span data-ttu-id="02ca2-202">下列範例會示範如何在您的組織中取得所有的偵測。</span><span class="sxs-lookup"><span data-stu-id="02ca2-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="02ca2-203">下列範例會示範自 2016-09-12 00:00:00 起取得最後20項檢測的要求。</span><span class="sxs-lookup"><span data-stu-id="02ca2-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="02ca2-204">回應</span><span class="sxs-lookup"><span data-stu-id="02ca2-204">Response</span></span>
<span data-ttu-id="02ca2-205">傳回值是以 JSON 格式的警示物件陣列。</span><span class="sxs-lookup"><span data-stu-id="02ca2-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="02ca2-206">以下是範例傳回值：</span><span class="sxs-lookup"><span data-stu-id="02ca2-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="02ca2-207">程式碼範例</span><span class="sxs-lookup"><span data-stu-id="02ca2-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="02ca2-208">取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="02ca2-208">Get access token</span></span>
<span data-ttu-id="02ca2-209">下列程式碼範例會示範如何取得存取權杖，以呼叫 Microsoft Defender for Endpoint SIEM API。</span><span class="sxs-lookup"><span data-stu-id="02ca2-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="02ca2-210">使用 token 連接至偵測端點</span><span class="sxs-lookup"><span data-stu-id="02ca2-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="02ca2-211">下列程式碼範例會示範如何使用存取權杖來呼叫 Defender for Endpoint SIEM API，以取得警示。</span><span class="sxs-lookup"><span data-stu-id="02ca2-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="02ca2-212">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="02ca2-212">Error codes</span></span>
<span data-ttu-id="02ca2-213">Microsoft Defender for Endpoint REST API 傳回下列由無效要求所造成的錯誤代碼。</span><span class="sxs-lookup"><span data-stu-id="02ca2-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="02ca2-214">HTTP 錯誤碼</span><span class="sxs-lookup"><span data-stu-id="02ca2-214">HTTP error code</span></span> | <span data-ttu-id="02ca2-215">描述</span><span class="sxs-lookup"><span data-stu-id="02ca2-215">Description</span></span>
:---|:---
<span data-ttu-id="02ca2-216">401</span><span class="sxs-lookup"><span data-stu-id="02ca2-216">401</span></span> | <span data-ttu-id="02ca2-217">格式不良的要求或不正確 token。</span><span class="sxs-lookup"><span data-stu-id="02ca2-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="02ca2-218">403</span><span class="sxs-lookup"><span data-stu-id="02ca2-218">403</span></span> | <span data-ttu-id="02ca2-219">未經授權的例外狀況-已刪除任何網域，而不是由租使用者管理員或租使用者狀態所管理。</span><span class="sxs-lookup"><span data-stu-id="02ca2-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="02ca2-220">500</span><span class="sxs-lookup"><span data-stu-id="02ca2-220">500</span></span> | <span data-ttu-id="02ca2-221">服務中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="02ca2-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="02ca2-222">相關主題</span><span class="sxs-lookup"><span data-stu-id="02ca2-222">Related topics</span></span>
- [<span data-ttu-id="02ca2-223">在 Microsoft Defender for Endpoint 中啟用 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="02ca2-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="02ca2-224">設定 ArcSight 以拉入 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="02ca2-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="02ca2-225">向 SIEM 工具提取偵測</span><span class="sxs-lookup"><span data-stu-id="02ca2-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="02ca2-226">Microsoft Defender for Endpoint 偵測欄位</span><span class="sxs-lookup"><span data-stu-id="02ca2-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="02ca2-227">為 SIEM 工具整合問題疑難排解</span><span class="sxs-lookup"><span data-stu-id="02ca2-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
