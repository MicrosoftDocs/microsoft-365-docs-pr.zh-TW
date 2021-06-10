---
title: 支援的 Microsoft Defender for Endpoint response APIs
description: 深入瞭解特定的回應相關 Microsoft Defender for Endpoint API 呼叫。
keywords: 回應 api，圖形 api，支援的 api，演員，警示，裝置，使用者，網域，ip，檔案
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933766"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="00afe-104">支援的 Microsoft Defender for Endpoint 查詢 APIs</span><span class="sxs-lookup"><span data-stu-id="00afe-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="00afe-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="00afe-105">**Applies to:**</span></span>
- [<span data-ttu-id="00afe-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="00afe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="00afe-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="00afe-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="00afe-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="00afe-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="00afe-109">深入瞭解您可以執行的支援回應相關 API 通話，以及所需的要求標頭，以及來自呼叫的預期回應等詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="00afe-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="00afe-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="00afe-110">In this section</span></span>
<span data-ttu-id="00afe-111">主題</span><span class="sxs-lookup"><span data-stu-id="00afe-111">Topic</span></span> | <span data-ttu-id="00afe-112">描述</span><span class="sxs-lookup"><span data-stu-id="00afe-112">Description</span></span>
:---|:---
<span data-ttu-id="00afe-113">收集調查套件</span><span class="sxs-lookup"><span data-stu-id="00afe-113">Collect investigation package</span></span> | <span data-ttu-id="00afe-114">執行此 API 以從裝置收集調查套件。</span><span class="sxs-lookup"><span data-stu-id="00afe-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="00afe-115">隔離裝置</span><span class="sxs-lookup"><span data-stu-id="00afe-115">Isolate device</span></span> | <span data-ttu-id="00afe-116">執行此 API 以從網路隔離裝置。</span><span class="sxs-lookup"><span data-stu-id="00afe-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="00afe-117">Unisolate 裝置</span><span class="sxs-lookup"><span data-stu-id="00afe-117">Unisolate device</span></span> | <span data-ttu-id="00afe-118">從隔離移除裝置。</span><span class="sxs-lookup"><span data-stu-id="00afe-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="00afe-119">限制程式碼執行</span><span class="sxs-lookup"><span data-stu-id="00afe-119">Restrict code execution</span></span> | <span data-ttu-id="00afe-120">透過停止惡意程式執行此 API，以包含攻擊。</span><span class="sxs-lookup"><span data-stu-id="00afe-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="00afe-121">您也可以鎖定裝置，並防止後續惡意程式的企圖執行。</span><span class="sxs-lookup"><span data-stu-id="00afe-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="00afe-122">Unrestrict 程式碼執行</span><span class="sxs-lookup"><span data-stu-id="00afe-122">Unrestrict code execution</span></span> | <span data-ttu-id="00afe-123">在驗證受損裝置後，請執行下列程式，以反轉應用程式原則的限制。</span><span class="sxs-lookup"><span data-stu-id="00afe-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="00afe-124">執行防毒掃描</span><span class="sxs-lookup"><span data-stu-id="00afe-124">Run antivirus scan</span></span> | <span data-ttu-id="00afe-125">遠端啟動防病毒掃描，以協助識別和修正受損裝置上可能會出現的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="00afe-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="00afe-126">停止並隔離檔案</span><span class="sxs-lookup"><span data-stu-id="00afe-126">Stop and quarantine file</span></span> |  <span data-ttu-id="00afe-127">執行此呼叫以停止執行程式、隔離檔案和刪除 persistency，例如登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="00afe-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="00afe-128">要求範例</span><span class="sxs-lookup"><span data-stu-id="00afe-128">Request sample</span></span> | <span data-ttu-id="00afe-129">執行此呼叫以從特定裝置要求檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="00afe-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="00afe-130">將從裝置收集檔案，並將其上傳至安全儲存區。</span><span class="sxs-lookup"><span data-stu-id="00afe-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="00afe-131">封鎖檔</span><span class="sxs-lookup"><span data-stu-id="00afe-131">Block file</span></span> | <span data-ttu-id="00afe-132">在 banning 潛在的惡意檔案或可疑惡意程式碼的情況執行此 API，以防止進一步傳播您組織中的攻擊。</span><span class="sxs-lookup"><span data-stu-id="00afe-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="00afe-133">解除封鎖檔</span><span class="sxs-lookup"><span data-stu-id="00afe-133">Unblock file</span></span> | <span data-ttu-id="00afe-134">允許使用 Microsoft Defender 防毒軟體在組織中執行檔。</span><span class="sxs-lookup"><span data-stu-id="00afe-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="00afe-135">取得套件 SAS URI</span><span class="sxs-lookup"><span data-stu-id="00afe-135">Get package SAS URI</span></span> | <span data-ttu-id="00afe-136">執行此 API 以取得可下載調查套件的 URI。</span><span class="sxs-lookup"><span data-stu-id="00afe-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="00afe-137">取得 MachineAction 物件</span><span class="sxs-lookup"><span data-stu-id="00afe-137">Get MachineAction object</span></span> | <span data-ttu-id="00afe-138">執行此 API 以取得 MachineAction 物件。</span><span class="sxs-lookup"><span data-stu-id="00afe-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="00afe-139">取得 MachineActions 集合</span><span class="sxs-lookup"><span data-stu-id="00afe-139">Get MachineActions collection</span></span> | <span data-ttu-id="00afe-140">執行此以取得 MachineAction 集合。</span><span class="sxs-lookup"><span data-stu-id="00afe-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="00afe-141">取得 FileActions 集合</span><span class="sxs-lookup"><span data-stu-id="00afe-141">Get FileActions collection</span></span> | <span data-ttu-id="00afe-142">執行此 API 以取得 FileActions 集合。</span><span class="sxs-lookup"><span data-stu-id="00afe-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="00afe-143">取得 FileMachineAction 物件</span><span class="sxs-lookup"><span data-stu-id="00afe-143">Get FileMachineAction object</span></span> | <span data-ttu-id="00afe-144">執行此 API 以取得 FileMachineAction 物件。</span><span class="sxs-lookup"><span data-stu-id="00afe-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="00afe-145">取得 FileMachineActions 集合</span><span class="sxs-lookup"><span data-stu-id="00afe-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="00afe-146">執行此 API 以取得 FileMachineAction 集合。</span><span class="sxs-lookup"><span data-stu-id="00afe-146">Run this API to get FileMachineAction collection.</span></span>
