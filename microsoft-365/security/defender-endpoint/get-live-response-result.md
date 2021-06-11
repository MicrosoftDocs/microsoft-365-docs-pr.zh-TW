---
title: 取得即時回應結果
description: 瞭解如何根據其索引來取回特定即時回應命令結果。
keywords: api，graph api，支援的 api，上傳至文件庫
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879686"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="c1881-104">取得即時回應結果</span><span class="sxs-lookup"><span data-stu-id="c1881-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c1881-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c1881-105">**Applies to:**</span></span>
- [<span data-ttu-id="c1881-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c1881-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="c1881-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="c1881-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c1881-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c1881-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="c1881-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="c1881-109">API description</span></span>

<span data-ttu-id="c1881-110">依其索引來檢索特定即時回應命令結果。</span><span class="sxs-lookup"><span data-stu-id="c1881-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="c1881-111">限制</span><span class="sxs-lookup"><span data-stu-id="c1881-111">Limitations</span></span>

1.  <span data-ttu-id="c1881-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="c1881-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="c1881-113">權限</span><span class="sxs-lookup"><span data-stu-id="c1881-113">Permissions</span></span>

<span data-ttu-id="c1881-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="c1881-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c1881-115">若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="c1881-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="c1881-116">許可權類型</span><span class="sxs-lookup"><span data-stu-id="c1881-116">Permission type</span></span>                    | <span data-ttu-id="c1881-117">權限</span><span class="sxs-lookup"><span data-stu-id="c1881-117">Permission</span></span>           | <span data-ttu-id="c1881-118">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="c1881-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="c1881-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="c1881-119">Application</span></span>                        | <span data-ttu-id="c1881-120">LiveResponse</span><span class="sxs-lookup"><span data-stu-id="c1881-120">Machine.LiveResponse</span></span> | <span data-ttu-id="c1881-121">在特定電腦上執行 live 回應</span><span class="sxs-lookup"><span data-stu-id="c1881-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="c1881-122">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="c1881-122">Delegated (work or school account)</span></span> | <span data-ttu-id="c1881-123">LiveResponse</span><span class="sxs-lookup"><span data-stu-id="c1881-123">Machine.LiveResponse</span></span> | <span data-ttu-id="c1881-124">在特定電腦上執行 live 回應</span><span class="sxs-lookup"><span data-stu-id="c1881-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="c1881-125">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="c1881-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="c1881-126">要求標頭</span><span class="sxs-lookup"><span data-stu-id="c1881-126">Request headers</span></span>

| <span data-ttu-id="c1881-127">名稱</span><span class="sxs-lookup"><span data-stu-id="c1881-127">Name</span></span>      | <span data-ttu-id="c1881-128">類型</span><span class="sxs-lookup"><span data-stu-id="c1881-128">Type</span></span> | <span data-ttu-id="c1881-129">描述</span><span class="sxs-lookup"><span data-stu-id="c1881-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="c1881-130">授權</span><span class="sxs-lookup"><span data-stu-id="c1881-130">Authorization</span></span> | <span data-ttu-id="c1881-131">字串</span><span class="sxs-lookup"><span data-stu-id="c1881-131">String</span></span>   | <span data-ttu-id="c1881-132">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="c1881-132">Bearer {token}.</span></span> <span data-ttu-id="c1881-133">此為必要動作。</span><span class="sxs-lookup"><span data-stu-id="c1881-133">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="c1881-134">要求正文</span><span class="sxs-lookup"><span data-stu-id="c1881-134">Request body</span></span>

<span data-ttu-id="c1881-135">空白</span><span class="sxs-lookup"><span data-stu-id="c1881-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c1881-136">回應</span><span class="sxs-lookup"><span data-stu-id="c1881-136">Response</span></span>

<span data-ttu-id="c1881-137">如果成功，這個方法會傳回200、Ok 回應碼，其物件會在 *value* 屬性中包含命令結果的連結。</span><span class="sxs-lookup"><span data-stu-id="c1881-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="c1881-138">此連結的有效期為30分鐘，應立即用來將套件下載至本機儲存區。</span><span class="sxs-lookup"><span data-stu-id="c1881-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="c1881-139">已到期的連結可以由另一個呼叫重新建立，而且不需要重新執行 live 回應。</span><span class="sxs-lookup"><span data-stu-id="c1881-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="c1881-140">*Runscript 成績單屬性：*</span><span class="sxs-lookup"><span data-stu-id="c1881-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="c1881-141">屬性	</span><span class="sxs-lookup"><span data-stu-id="c1881-141">Property</span></span>  | <span data-ttu-id="c1881-142">描述</span><span class="sxs-lookup"><span data-stu-id="c1881-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="c1881-143">Name</span><span class="sxs-lookup"><span data-stu-id="c1881-143">name</span></span>          | <span data-ttu-id="c1881-144">已執行的腳本名稱</span><span class="sxs-lookup"><span data-stu-id="c1881-144">Executed script name</span></span>                  |
| <span data-ttu-id="c1881-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="c1881-145">exit_code</span></span>     | <span data-ttu-id="c1881-146">已執行腳本的退出程式碼</span><span class="sxs-lookup"><span data-stu-id="c1881-146">Executed script exit code</span></span>             |
| <span data-ttu-id="c1881-147">script_output</span><span class="sxs-lookup"><span data-stu-id="c1881-147">script_output</span></span> | <span data-ttu-id="c1881-148">已執行腳本標準輸出</span><span class="sxs-lookup"><span data-stu-id="c1881-148">Executed script standard output</span></span>       |
| <span data-ttu-id="c1881-149">script_error</span><span class="sxs-lookup"><span data-stu-id="c1881-149">script_error</span></span>  | <span data-ttu-id="c1881-150">已執行的腳本標準錯誤輸出</span><span class="sxs-lookup"><span data-stu-id="c1881-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="c1881-151">範例</span><span class="sxs-lookup"><span data-stu-id="c1881-151">Example</span></span>

<span data-ttu-id="c1881-152">**請求**</span><span class="sxs-lookup"><span data-stu-id="c1881-152">**Request**</span></span>

<span data-ttu-id="c1881-153">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="c1881-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="c1881-154">**回應**</span><span class="sxs-lookup"><span data-stu-id="c1881-154">**Response**</span></span>

<span data-ttu-id="c1881-155">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="c1881-155">Here is an example of the response.</span></span>

<span data-ttu-id="c1881-156">HTTP/1.1 200 確定</span><span class="sxs-lookup"><span data-stu-id="c1881-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="c1881-157">內容類型： application/json</span><span class="sxs-lookup"><span data-stu-id="c1881-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="c1881-158">*檔內容：*</span><span class="sxs-lookup"><span data-stu-id="c1881-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="c1881-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="c1881-159">Related topics</span></span>

- [<span data-ttu-id="c1881-160">取得機器動作 API</span><span class="sxs-lookup"><span data-stu-id="c1881-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="c1881-161">取消機器動作</span><span class="sxs-lookup"><span data-stu-id="c1881-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="c1881-162">執行 live 回應</span><span class="sxs-lookup"><span data-stu-id="c1881-162">Run live response</span></span>](run-live-response.md) 
