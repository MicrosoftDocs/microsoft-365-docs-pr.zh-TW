---
title: machineAction 資源類型
description: 深入瞭解 Microsoft Defender for Endpoint 中的 MachineAction 資源類型的方法和屬性。
keywords: api、支援的 api、get、machineaction、最近
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
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187381"
---
# <a name="machineaction-resource-type"></a><span data-ttu-id="b56cb-104">MachineAction 資源類型</span><span class="sxs-lookup"><span data-stu-id="b56cb-104">MachineAction resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b56cb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b56cb-105">**Applies to:**</span></span>
- [<span data-ttu-id="b56cb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b56cb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b56cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b56cb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b56cb-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b56cb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b56cb-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b56cb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="b56cb-110">如需詳細資訊，請參閱 [回應動作](respond-machine-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b56cb-110">For more information, see [Response Actions](respond-machine-alerts.md).</span></span> 

| <span data-ttu-id="b56cb-111">方法</span><span class="sxs-lookup"><span data-stu-id="b56cb-111">Method</span></span>                                                            | <span data-ttu-id="b56cb-112">傳回類型</span><span class="sxs-lookup"><span data-stu-id="b56cb-112">Return Type</span></span>                        | <span data-ttu-id="b56cb-113">描述</span><span class="sxs-lookup"><span data-stu-id="b56cb-113">Description</span></span>                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [<span data-ttu-id="b56cb-114">清單 MachineActions</span><span class="sxs-lookup"><span data-stu-id="b56cb-114">List MachineActions</span></span>](get-machineactions-collection.md)           | [<span data-ttu-id="b56cb-115">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-115">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-116">列出 [電腦動作](machineaction.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="b56cb-116">List [Machine Action](machineaction.md) entities.</span></span>           |
| [<span data-ttu-id="b56cb-117">取得 MachineAction</span><span class="sxs-lookup"><span data-stu-id="b56cb-117">Get MachineAction</span></span>](get-machineaction-object.md)                  | [<span data-ttu-id="b56cb-118">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-118">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-119">取得單一 [機器動作](machineaction.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="b56cb-119">Get a single [Machine Action](machineaction.md) entity.</span></span>     |
| [<span data-ttu-id="b56cb-120">收集調查套件</span><span class="sxs-lookup"><span data-stu-id="b56cb-120">Collect investigation package</span></span>](collect-investigation-package.md) | [<span data-ttu-id="b56cb-121">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-121">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-122">從 [機器](machine.md)收集調查套件。</span><span class="sxs-lookup"><span data-stu-id="b56cb-122">Collect investigation package from a [machine](machine.md).</span></span> |
| [<span data-ttu-id="b56cb-123">取得調查套件 SAS URI</span><span class="sxs-lookup"><span data-stu-id="b56cb-123">Get investigation package SAS URI</span></span>](get-package-sas-uri.md)       | [<span data-ttu-id="b56cb-124">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-124">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-125">取得下載調查套件的 URI。</span><span class="sxs-lookup"><span data-stu-id="b56cb-125">Get URI for downloading the investigation package.</span></span>          |
| [<span data-ttu-id="b56cb-126">隔離電腦</span><span class="sxs-lookup"><span data-stu-id="b56cb-126">Isolate machine</span></span>](isolate-machine.md)                             | [<span data-ttu-id="b56cb-127">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-127">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-128">從網路隔離 [電腦](machine.md) 。</span><span class="sxs-lookup"><span data-stu-id="b56cb-128">Isolate [machine](machine.md) from network.</span></span>                 |
| [<span data-ttu-id="b56cb-129">將電腦從隔離中釋出</span><span class="sxs-lookup"><span data-stu-id="b56cb-129">Release machine from isolation</span></span>](unisolate-machine.md)            | [<span data-ttu-id="b56cb-130">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-130">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-131">獨立發行 [電腦](machine.md) 。</span><span class="sxs-lookup"><span data-stu-id="b56cb-131">Release [machine](machine.md) from Isolation.</span></span>               |
| [<span data-ttu-id="b56cb-132">限制應用程式執行</span><span class="sxs-lookup"><span data-stu-id="b56cb-132">Restrict app execution</span></span>](restrict-code-execution.md)              | [<span data-ttu-id="b56cb-133">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-133">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-134">限制應用程式的執行。</span><span class="sxs-lookup"><span data-stu-id="b56cb-134">Restrict application execution.</span></span>                             |
| [<span data-ttu-id="b56cb-135">移除應用程式限制</span><span class="sxs-lookup"><span data-stu-id="b56cb-135">Remove app restriction</span></span>](unrestrict-code-execution.md)            | [<span data-ttu-id="b56cb-136">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-136">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-137">移除應用程式執行限制。</span><span class="sxs-lookup"><span data-stu-id="b56cb-137">Remove application execution restriction.</span></span>                   |
| [<span data-ttu-id="b56cb-138">執行防毒掃描</span><span class="sxs-lookup"><span data-stu-id="b56cb-138">Run antivirus scan</span></span>](run-av-scan.md)                              | [<span data-ttu-id="b56cb-139">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-139">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-140">在適用) 時，使用 Windows Defender (執行 AV 掃描。</span><span class="sxs-lookup"><span data-stu-id="b56cb-140">Run an AV scan using Windows Defender (when applicable).</span></span>    |
| [<span data-ttu-id="b56cb-141">下機</span><span class="sxs-lookup"><span data-stu-id="b56cb-141">Offboard machine</span></span>](offboard-machine-api.md)                       | [<span data-ttu-id="b56cb-142">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-142">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-143">從 Microsoft Defender for Endpoint 下架 [電腦](machine.md) 。</span><span class="sxs-lookup"><span data-stu-id="b56cb-143">Offboard [machine](machine.md) from Microsoft Defender for Endpoint.</span></span> |
| [<span data-ttu-id="b56cb-144">停止並隔離檔案</span><span class="sxs-lookup"><span data-stu-id="b56cb-144">Stop and quarantine file</span></span>](stop-and-quarantine-file.md)           | [<span data-ttu-id="b56cb-145">電腦動作</span><span class="sxs-lookup"><span data-stu-id="b56cb-145">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="b56cb-146">停止執行機器上的檔案，並將它刪除。</span><span class="sxs-lookup"><span data-stu-id="b56cb-146">Stop execution of a file on a machine and delete it.</span></span>        |

<br>

## <a name="properties"></a><span data-ttu-id="b56cb-147">屬性</span><span class="sxs-lookup"><span data-stu-id="b56cb-147">Properties</span></span>

| <span data-ttu-id="b56cb-148">屬性	</span><span class="sxs-lookup"><span data-stu-id="b56cb-148">Property</span></span>            | <span data-ttu-id="b56cb-149">類型</span><span class="sxs-lookup"><span data-stu-id="b56cb-149">Type</span></span>           | <span data-ttu-id="b56cb-150">描述</span><span class="sxs-lookup"><span data-stu-id="b56cb-150">Description</span></span>                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b56cb-151">識別碼</span><span class="sxs-lookup"><span data-stu-id="b56cb-151">ID</span></span>                  | <span data-ttu-id="b56cb-152">Guid</span><span class="sxs-lookup"><span data-stu-id="b56cb-152">Guid</span></span>           | <span data-ttu-id="b56cb-153">[機器動作](machineaction.md)實體的身分識別。</span><span class="sxs-lookup"><span data-stu-id="b56cb-153">Identity of the [Machine Action](machineaction.md) entity.</span></span>                                                                                                                                                     |
| <span data-ttu-id="b56cb-154">類型</span><span class="sxs-lookup"><span data-stu-id="b56cb-154">type</span></span>                | <span data-ttu-id="b56cb-155">Enum</span><span class="sxs-lookup"><span data-stu-id="b56cb-155">Enum</span></span>           | <span data-ttu-id="b56cb-156">動作的類型。</span><span class="sxs-lookup"><span data-stu-id="b56cb-156">Type of the action.</span></span> <span data-ttu-id="b56cb-157">可能的值為： "RunAntiVirusScan"、"下架"、"CollectInvestigationPackage"、"隔離"、"Unisolate"、"StopAndQuarantineFile"、"RestrictCodeExecution" 和 "UnrestrictCodeExecution"</span><span class="sxs-lookup"><span data-stu-id="b56cb-157">Possible values are: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" and "UnrestrictCodeExecution"</span></span> |
| <span data-ttu-id="b56cb-158">範圍</span><span class="sxs-lookup"><span data-stu-id="b56cb-158">scope</span></span>               | <span data-ttu-id="b56cb-159">字串</span><span class="sxs-lookup"><span data-stu-id="b56cb-159">string</span></span>         | <span data-ttu-id="b56cb-160">動作的範圍。</span><span class="sxs-lookup"><span data-stu-id="b56cb-160">Scope of the action.</span></span> <span data-ttu-id="b56cb-161">"Full" 或 "選擇性" 進行隔離，"Quick" 或 "Full" 表示防病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="b56cb-161">"Full" or "Selective" for Isolation, "Quick" or "Full" for Anti-Virus scan.</span></span>                                                                                                   |
| <span data-ttu-id="b56cb-162">請求</span><span class="sxs-lookup"><span data-stu-id="b56cb-162">requestor</span></span>           | <span data-ttu-id="b56cb-163">字串</span><span class="sxs-lookup"><span data-stu-id="b56cb-163">String</span></span>         | <span data-ttu-id="b56cb-164">執行動作之人員的身分識別。</span><span class="sxs-lookup"><span data-stu-id="b56cb-164">Identity of the person that executed the action.</span></span>                                                                                                                                                               |
| <span data-ttu-id="b56cb-165">requestorComment</span><span class="sxs-lookup"><span data-stu-id="b56cb-165">requestorComment</span></span>    | <span data-ttu-id="b56cb-166">字串</span><span class="sxs-lookup"><span data-stu-id="b56cb-166">String</span></span>         | <span data-ttu-id="b56cb-167">發出動作時所撰寫的批註。</span><span class="sxs-lookup"><span data-stu-id="b56cb-167">Comment that was written when issuing the action.</span></span>                                                                                                                                                              |
| <span data-ttu-id="b56cb-168">地位</span><span class="sxs-lookup"><span data-stu-id="b56cb-168">status</span></span>              | <span data-ttu-id="b56cb-169">Enum</span><span class="sxs-lookup"><span data-stu-id="b56cb-169">Enum</span></span>           | <span data-ttu-id="b56cb-170">命令的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="b56cb-170">Current status of the command.</span></span> <span data-ttu-id="b56cb-171">可能的值為：「擱置」、「InProgress」、「成功」、「失敗」、「超時」和「取消」。</span><span class="sxs-lookup"><span data-stu-id="b56cb-171">Possible values are: "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" and "Canceled".</span></span>                                                                                 |
| <span data-ttu-id="b56cb-172">machineId</span><span class="sxs-lookup"><span data-stu-id="b56cb-172">machineId</span></span>           | <span data-ttu-id="b56cb-173">字串</span><span class="sxs-lookup"><span data-stu-id="b56cb-173">String</span></span>         | <span data-ttu-id="b56cb-174">執行動作所在之 [機器](machine.md) 的識別碼。</span><span class="sxs-lookup"><span data-stu-id="b56cb-174">ID of the [machine](machine.md) on which the action was executed.</span></span>                                                                                                                                              |
| <span data-ttu-id="b56cb-175">machineId</span><span class="sxs-lookup"><span data-stu-id="b56cb-175">machineId</span></span>           | <span data-ttu-id="b56cb-176">字串</span><span class="sxs-lookup"><span data-stu-id="b56cb-176">String</span></span>         | <span data-ttu-id="b56cb-177">執行動作所在之 [機器](machine.md) 的名稱。</span><span class="sxs-lookup"><span data-stu-id="b56cb-177">Name of the [machine](machine.md) on which the action was executed.</span></span>                                                                                                                                            |
| <span data-ttu-id="b56cb-178">creationDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="b56cb-178">creationDateTimeUtc</span></span> | <span data-ttu-id="b56cb-179">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b56cb-179">DateTimeOffset</span></span> | <span data-ttu-id="b56cb-180">動作的建立日期和時間。</span><span class="sxs-lookup"><span data-stu-id="b56cb-180">The date and time when the action was created.</span></span>                                                                                                                                                                 |
| <span data-ttu-id="b56cb-181">lastUpdateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="b56cb-181">lastUpdateTimeUtc</span></span>   | <span data-ttu-id="b56cb-182">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b56cb-182">DateTimeOffset</span></span> | <span data-ttu-id="b56cb-183">動作狀態更新的最後日期和時間。</span><span class="sxs-lookup"><span data-stu-id="b56cb-183">The last date and time when the action status was updated.</span></span>                                                                                                                                                     |
| <span data-ttu-id="b56cb-184">relatedFileInfo</span><span class="sxs-lookup"><span data-stu-id="b56cb-184">relatedFileInfo</span></span>     | <span data-ttu-id="b56cb-185">類別</span><span class="sxs-lookup"><span data-stu-id="b56cb-185">Class</span></span>          | <span data-ttu-id="b56cb-186">包含兩個屬性。</span><span class="sxs-lookup"><span data-stu-id="b56cb-186">Contains two Properties.</span></span> <span data-ttu-id="b56cb-187">字串 ```fileIdentifier``` ，列舉的 ```fileIdentifierType``` 可能值為 "Sha1"，"Sha256"，"Md5"。</span><span class="sxs-lookup"><span data-stu-id="b56cb-187">string ```fileIdentifier```, Enum ```fileIdentifierType``` with the possible values: "Sha1", "Sha256" and "Md5".</span></span>                                                                         |


## <a name="json-representation"></a><span data-ttu-id="b56cb-188">Json 標記法</span><span class="sxs-lookup"><span data-stu-id="b56cb-188">Json representation</span></span>

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
