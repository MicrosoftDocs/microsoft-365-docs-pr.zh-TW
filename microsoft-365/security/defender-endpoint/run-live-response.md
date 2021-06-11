---
title: 在裝置上執行 live 回應命令
description: 瞭解如何在裝置上執行 live response 命令順序。
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879653"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="7266d-104">在裝置上執行 live 回應命令</span><span class="sxs-lookup"><span data-stu-id="7266d-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7266d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7266d-105">**Applies to:**</span></span>
- [<span data-ttu-id="7266d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7266d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="7266d-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="7266d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7266d-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="7266d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="7266d-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="7266d-109">API description</span></span>

<span data-ttu-id="7266d-110">在裝置上執行 live response 命令順序</span><span class="sxs-lookup"><span data-stu-id="7266d-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="7266d-111">限制</span><span class="sxs-lookup"><span data-stu-id="7266d-111">Limitations</span></span>

1.  <span data-ttu-id="7266d-112">此 API 的速率限制是每分鐘10個通話 (其他要求會以 HTTP 429) 回應。</span><span class="sxs-lookup"><span data-stu-id="7266d-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="7266d-113">25個同時執行的會話 (要求超過節流限制，將會收到「429-太多要求」回應) 。</span><span class="sxs-lookup"><span data-stu-id="7266d-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="7266d-114">如果機器無法使用，會話將會排隊等候最多3天。</span><span class="sxs-lookup"><span data-stu-id="7266d-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="7266d-115">10分鐘後 RunScript 命令逾時。</span><span class="sxs-lookup"><span data-stu-id="7266d-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="7266d-116">當 live response 命令失敗時，將不會執行所有遵循的動作。</span><span class="sxs-lookup"><span data-stu-id="7266d-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="7266d-117">權限</span><span class="sxs-lookup"><span data-stu-id="7266d-117">Permissions</span></span>

<span data-ttu-id="7266d-118">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="7266d-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7266d-119">若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="7266d-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="7266d-120">許可權類型</span><span class="sxs-lookup"><span data-stu-id="7266d-120">Permission type</span></span>                    | <span data-ttu-id="7266d-121">權限</span><span class="sxs-lookup"><span data-stu-id="7266d-121">Permission</span></span>           | <span data-ttu-id="7266d-122">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="7266d-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="7266d-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="7266d-123">Application</span></span>                        | <span data-ttu-id="7266d-124">LiveResponse</span><span class="sxs-lookup"><span data-stu-id="7266d-124">Machine.LiveResponse</span></span> | <span data-ttu-id="7266d-125">在特定電腦上執行 live 回應</span><span class="sxs-lookup"><span data-stu-id="7266d-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="7266d-126">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="7266d-126">Delegated (work or school account)</span></span> | <span data-ttu-id="7266d-127">LiveResponse</span><span class="sxs-lookup"><span data-stu-id="7266d-127">Machine.LiveResponse</span></span> | <span data-ttu-id="7266d-128">在特定電腦上執行 live 回應</span><span class="sxs-lookup"><span data-stu-id="7266d-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="7266d-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="7266d-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="7266d-130">要求標頭</span><span class="sxs-lookup"><span data-stu-id="7266d-130">Request headers</span></span>

| <span data-ttu-id="7266d-131">名稱</span><span class="sxs-lookup"><span data-stu-id="7266d-131">Name</span></span>      | <span data-ttu-id="7266d-132">類型</span><span class="sxs-lookup"><span data-stu-id="7266d-132">Type</span></span> | <span data-ttu-id="7266d-133">描述</span><span class="sxs-lookup"><span data-stu-id="7266d-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="7266d-134">授權</span><span class="sxs-lookup"><span data-stu-id="7266d-134">Authorization</span></span> | <span data-ttu-id="7266d-135">字串</span><span class="sxs-lookup"><span data-stu-id="7266d-135">String</span></span>   | <span data-ttu-id="7266d-136">承載\<token>\.</span><span class="sxs-lookup"><span data-stu-id="7266d-136">Bearer\<token>\.</span></span> <span data-ttu-id="7266d-137">此為必要動作。</span><span class="sxs-lookup"><span data-stu-id="7266d-137">Required.</span></span>   |
| <span data-ttu-id="7266d-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="7266d-138">Content-Type</span></span>  | <span data-ttu-id="7266d-139">string</span><span class="sxs-lookup"><span data-stu-id="7266d-139">string</span></span>   | <span data-ttu-id="7266d-140">application/json。</span><span class="sxs-lookup"><span data-stu-id="7266d-140">application/json.</span></span> <span data-ttu-id="7266d-141">此為必要動作。</span><span class="sxs-lookup"><span data-stu-id="7266d-141">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="7266d-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="7266d-142">Request body</span></span>

| <span data-ttu-id="7266d-143">參數</span><span class="sxs-lookup"><span data-stu-id="7266d-143">Parameter</span></span> | <span data-ttu-id="7266d-144">類型</span><span class="sxs-lookup"><span data-stu-id="7266d-144">Type</span></span> | <span data-ttu-id="7266d-145">描述</span><span class="sxs-lookup"><span data-stu-id="7266d-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="7266d-146">留言</span><span class="sxs-lookup"><span data-stu-id="7266d-146">Comment</span></span>       | <span data-ttu-id="7266d-147">字串</span><span class="sxs-lookup"><span data-stu-id="7266d-147">String</span></span>   | <span data-ttu-id="7266d-148">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="7266d-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="7266d-149">命令</span><span class="sxs-lookup"><span data-stu-id="7266d-149">Commands</span></span>      | <span data-ttu-id="7266d-150">陣列</span><span class="sxs-lookup"><span data-stu-id="7266d-150">Array</span></span>    | <span data-ttu-id="7266d-151">要執行的命令。</span><span class="sxs-lookup"><span data-stu-id="7266d-151">Commands to run.</span></span> <span data-ttu-id="7266d-152">允許的值為 PutFile、RunScript、GetFile。</span><span class="sxs-lookup"><span data-stu-id="7266d-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="7266d-153">命令：</span><span class="sxs-lookup"><span data-stu-id="7266d-153">Commands:</span></span>

| <span data-ttu-id="7266d-154">命令類型</span><span class="sxs-lookup"><span data-stu-id="7266d-154">Command Type</span></span> | <span data-ttu-id="7266d-155">參數</span><span class="sxs-lookup"><span data-stu-id="7266d-155">Parameters</span></span>                                                                          | <span data-ttu-id="7266d-156">描述</span><span class="sxs-lookup"><span data-stu-id="7266d-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7266d-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="7266d-157">PutFile</span></span>      | <span data-ttu-id="7266d-158">索引鍵： FileName</span><span class="sxs-lookup"><span data-stu-id="7266d-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="7266d-159">值：\<file name\></span><span class="sxs-lookup"><span data-stu-id="7266d-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="7266d-160">將檔案從文件庫放入裝置。</span><span class="sxs-lookup"><span data-stu-id="7266d-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="7266d-161">檔案儲存在工作資料夾中，而且會在預設重新開機裝置時刪除。</span><span class="sxs-lookup"><span data-stu-id="7266d-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="7266d-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="7266d-162">RunScript</span></span>    | <span data-ttu-id="7266d-163">機碼： ScriptName</span><span class="sxs-lookup"><span data-stu-id="7266d-163">Key: ScriptName</span></span><br><span data-ttu-id="7266d-164">值：\<Script from library\></span><span class="sxs-lookup"><span data-stu-id="7266d-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="7266d-165">Key： Args</span><span class="sxs-lookup"><span data-stu-id="7266d-165">Key: Args</span></span>  <br> <span data-ttu-id="7266d-166">值：\<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="7266d-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="7266d-167">在裝置上的文件庫中執行腳本。</span><span class="sxs-lookup"><span data-stu-id="7266d-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="7266d-168">Args 參數會傳遞給您的腳本。</span><span class="sxs-lookup"><span data-stu-id="7266d-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="7266d-169">10分鐘後超時。</span><span class="sxs-lookup"><span data-stu-id="7266d-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="7266d-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="7266d-170">GetFile</span></span>      | <span data-ttu-id="7266d-171">Key： Path</span><span class="sxs-lookup"><span data-stu-id="7266d-171">Key: Path</span></span> <br> <span data-ttu-id="7266d-172">值：\<File path\></span><span class="sxs-lookup"><span data-stu-id="7266d-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="7266d-173">從裝置收集檔案。</span><span class="sxs-lookup"><span data-stu-id="7266d-173">Collect file from a device.</span></span> <span data-ttu-id="7266d-174">附注：路徑中的反斜線必須進行轉義。</span><span class="sxs-lookup"><span data-stu-id="7266d-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="7266d-175">回應</span><span class="sxs-lookup"><span data-stu-id="7266d-175">Response</span></span>

-   <span data-ttu-id="7266d-176">如果成功，這個方法會傳回200，[確定]。</span><span class="sxs-lookup"><span data-stu-id="7266d-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="7266d-177">Action 實體。</span><span class="sxs-lookup"><span data-stu-id="7266d-177">Action entity.</span></span> <span data-ttu-id="7266d-178">如果找不到具有指定識別碼的電腦-找不到404。</span><span class="sxs-lookup"><span data-stu-id="7266d-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="7266d-179">範例</span><span class="sxs-lookup"><span data-stu-id="7266d-179">Example</span></span>

<span data-ttu-id="7266d-180">**請求**</span><span class="sxs-lookup"><span data-stu-id="7266d-180">**Request**</span></span>

<span data-ttu-id="7266d-181">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="7266d-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="7266d-182">**Json**</span><span class="sxs-lookup"><span data-stu-id="7266d-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="7266d-183">**回應**</span><span class="sxs-lookup"><span data-stu-id="7266d-183">**Response**</span></span>

<span data-ttu-id="7266d-184">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="7266d-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="7266d-185">內容類型： application/json</span><span class="sxs-lookup"><span data-stu-id="7266d-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="7266d-186">相關主題</span><span class="sxs-lookup"><span data-stu-id="7266d-186">Related topics</span></span>
- [<span data-ttu-id="7266d-187">取得機器動作 API</span><span class="sxs-lookup"><span data-stu-id="7266d-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="7266d-188">取得即時回應結果</span><span class="sxs-lookup"><span data-stu-id="7266d-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="7266d-189">取消機器動作</span><span class="sxs-lookup"><span data-stu-id="7266d-189">Cancel machine action</span></span>](cancel-machine-action.md)
