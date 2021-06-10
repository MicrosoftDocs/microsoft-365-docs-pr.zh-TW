---
title: 檔資源類型
description: 檢索與檔案相關的最近 Microsoft Defender 的端點警示。
keywords: api、graph api、支援的 api、get、警示、最近
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
ms.openlocfilehash: c4d392c9c7777a5ab5435d70e36822e11aa39dae
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771186"
---
# <a name="file-resource-type"></a><span data-ttu-id="c3c01-104">檔資源類型</span><span class="sxs-lookup"><span data-stu-id="c3c01-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c3c01-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c3c01-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c3c01-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="c3c01-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c3c01-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c3c01-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="c3c01-108">代表在 Defender for Endpoint 中的檔實體。</span><span class="sxs-lookup"><span data-stu-id="c3c01-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="c3c01-109">方法</span><span class="sxs-lookup"><span data-stu-id="c3c01-109">Methods</span></span>
<span data-ttu-id="c3c01-110">方法	</span><span class="sxs-lookup"><span data-stu-id="c3c01-110">Method</span></span>|<span data-ttu-id="c3c01-111">傳回類型</span><span class="sxs-lookup"><span data-stu-id="c3c01-111">Return Type</span></span> |<span data-ttu-id="c3c01-112">描述</span><span class="sxs-lookup"><span data-stu-id="c3c01-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="c3c01-113">取得檔</span><span class="sxs-lookup"><span data-stu-id="c3c01-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="c3c01-114">檔</span><span class="sxs-lookup"><span data-stu-id="c3c01-114">file</span></span>](files.md) | <span data-ttu-id="c3c01-115">取得單一檔</span><span class="sxs-lookup"><span data-stu-id="c3c01-115">Get a single file</span></span> 
[<span data-ttu-id="c3c01-116">清單檔相關警示</span><span class="sxs-lookup"><span data-stu-id="c3c01-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="c3c01-117">[警示](alerts.md) 集合</span><span class="sxs-lookup"><span data-stu-id="c3c01-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="c3c01-118">取得檔相關聯的 [警示](alerts.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="c3c01-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="c3c01-119">清單檔相關的電腦</span><span class="sxs-lookup"><span data-stu-id="c3c01-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="c3c01-120">[電腦](machine.md) 集合</span><span class="sxs-lookup"><span data-stu-id="c3c01-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="c3c01-121">取得與警示相關聯的 [電腦](machine.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="c3c01-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="c3c01-122">檔案統計資料</span><span class="sxs-lookup"><span data-stu-id="c3c01-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="c3c01-123">統計資料摘要</span><span class="sxs-lookup"><span data-stu-id="c3c01-123">Statistics summary</span></span> | <span data-ttu-id="c3c01-124">會檢索指定檔案的流行。</span><span class="sxs-lookup"><span data-stu-id="c3c01-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="c3c01-125">屬性</span><span class="sxs-lookup"><span data-stu-id="c3c01-125">Properties</span></span>
|<span data-ttu-id="c3c01-126">屬性	</span><span class="sxs-lookup"><span data-stu-id="c3c01-126">Property</span></span> | <span data-ttu-id="c3c01-127">類型</span><span class="sxs-lookup"><span data-stu-id="c3c01-127">Type</span></span>    |   <span data-ttu-id="c3c01-128">描述</span><span class="sxs-lookup"><span data-stu-id="c3c01-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="c3c01-129">sha1</span><span class="sxs-lookup"><span data-stu-id="c3c01-129">sha1</span></span> | <span data-ttu-id="c3c01-130">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-130">String</span></span> | <span data-ttu-id="c3c01-131">檔內容的 Sha1 雜湊</span><span class="sxs-lookup"><span data-stu-id="c3c01-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="c3c01-132">sha256</span><span class="sxs-lookup"><span data-stu-id="c3c01-132">sha256</span></span> | <span data-ttu-id="c3c01-133">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-133">String</span></span> | <span data-ttu-id="c3c01-134">檔內容的 Sha256 雜湊</span><span class="sxs-lookup"><span data-stu-id="c3c01-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="c3c01-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="c3c01-135">globalPrevalence</span></span> | <span data-ttu-id="c3c01-136">可為 null 的長</span><span class="sxs-lookup"><span data-stu-id="c3c01-136">Nullable long</span></span> | <span data-ttu-id="c3c01-137">整個組織的檔傳播</span><span class="sxs-lookup"><span data-stu-id="c3c01-137">File prevalence across organization</span></span> |
|<span data-ttu-id="c3c01-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="c3c01-138">globalFirstObserved</span></span> | <span data-ttu-id="c3c01-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c3c01-139">DateTimeOffset</span></span> | <span data-ttu-id="c3c01-140">第一次觀測檔時</span><span class="sxs-lookup"><span data-stu-id="c3c01-140">First time the file was observed</span></span> |
|<span data-ttu-id="c3c01-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="c3c01-141">globalLastObserved</span></span> | <span data-ttu-id="c3c01-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c3c01-142">DateTimeOffset</span></span> | <span data-ttu-id="c3c01-143">上次觀測檔的時間</span><span class="sxs-lookup"><span data-stu-id="c3c01-143">Last time the file was observed</span></span> |
|<span data-ttu-id="c3c01-144">Size</span><span class="sxs-lookup"><span data-stu-id="c3c01-144">size</span></span> | <span data-ttu-id="c3c01-145">可為 null 的長</span><span class="sxs-lookup"><span data-stu-id="c3c01-145">Nullable long</span></span> | <span data-ttu-id="c3c01-146">檔案大小</span><span class="sxs-lookup"><span data-stu-id="c3c01-146">Size of the file</span></span> |
|<span data-ttu-id="c3c01-147">類型</span><span class="sxs-lookup"><span data-stu-id="c3c01-147">fileType</span></span> | <span data-ttu-id="c3c01-148">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-148">String</span></span> | <span data-ttu-id="c3c01-149">檔案類型</span><span class="sxs-lookup"><span data-stu-id="c3c01-149">Type of the file</span></span> |
|<span data-ttu-id="c3c01-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="c3c01-150">isPeFile</span></span> | <span data-ttu-id="c3c01-151">布林值</span><span class="sxs-lookup"><span data-stu-id="c3c01-151">Boolean</span></span> | <span data-ttu-id="c3c01-152">true 是表示如果檔案是可遷移的可執行檔 (例如 "DLL"、"EXE" 等 ) </span><span class="sxs-lookup"><span data-stu-id="c3c01-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="c3c01-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="c3c01-153">filePublisher</span></span> | <span data-ttu-id="c3c01-154">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-154">String</span></span> | <span data-ttu-id="c3c01-155">檔發行者</span><span class="sxs-lookup"><span data-stu-id="c3c01-155">File publisher</span></span> |
|<span data-ttu-id="c3c01-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="c3c01-156">fileProductName</span></span> | <span data-ttu-id="c3c01-157">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-157">String</span></span> | <span data-ttu-id="c3c01-158">產品名稱</span><span class="sxs-lookup"><span data-stu-id="c3c01-158">Product name</span></span> |
|<span data-ttu-id="c3c01-159">簽名</span><span class="sxs-lookup"><span data-stu-id="c3c01-159">signer</span></span> | <span data-ttu-id="c3c01-160">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-160">String</span></span> | <span data-ttu-id="c3c01-161">檔簽署者</span><span class="sxs-lookup"><span data-stu-id="c3c01-161">File signer</span></span> |
|<span data-ttu-id="c3c01-162">發行</span><span class="sxs-lookup"><span data-stu-id="c3c01-162">issuer</span></span> | <span data-ttu-id="c3c01-163">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-163">String</span></span> | <span data-ttu-id="c3c01-164">檔發行者</span><span class="sxs-lookup"><span data-stu-id="c3c01-164">File issuer</span></span> |
|<span data-ttu-id="c3c01-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="c3c01-165">signerHash</span></span> | <span data-ttu-id="c3c01-166">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-166">String</span></span> | <span data-ttu-id="c3c01-167">簽署憑證的雜湊</span><span class="sxs-lookup"><span data-stu-id="c3c01-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="c3c01-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="c3c01-168">isValidCertificate</span></span> | <span data-ttu-id="c3c01-169">布林值</span><span class="sxs-lookup"><span data-stu-id="c3c01-169">Boolean</span></span> | <span data-ttu-id="c3c01-170">是由 Microsoft Defender for Endpoint agent 成功驗證的簽署憑證</span><span class="sxs-lookup"><span data-stu-id="c3c01-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="c3c01-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="c3c01-171">determinationType</span></span> | <span data-ttu-id="c3c01-172">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-172">String</span></span> | <span data-ttu-id="c3c01-173">檔的決定類型</span><span class="sxs-lookup"><span data-stu-id="c3c01-173">The determination type of the file</span></span> |
|<span data-ttu-id="c3c01-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="c3c01-174">determinationValue</span></span> | <span data-ttu-id="c3c01-175">字串</span><span class="sxs-lookup"><span data-stu-id="c3c01-175">String</span></span> | <span data-ttu-id="c3c01-176">判斷值</span><span class="sxs-lookup"><span data-stu-id="c3c01-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="c3c01-177">Json 標記法</span><span class="sxs-lookup"><span data-stu-id="c3c01-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
