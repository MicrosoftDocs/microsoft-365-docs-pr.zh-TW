---
title: 軟體方法和屬性
description: 檢索最新的最近警示。
keywords: api、graph api、支援的 api、get、警示、最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187103"
---
# <a name="software-resource-type"></a><span data-ttu-id="2f981-104">軟體資源類型</span><span class="sxs-lookup"><span data-stu-id="2f981-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f981-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2f981-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f981-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f981-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f981-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f981-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="2f981-108">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2f981-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2f981-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2f981-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2f981-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2f981-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="2f981-111">方法</span><span class="sxs-lookup"><span data-stu-id="2f981-111">Methods</span></span>

<span data-ttu-id="2f981-112">方法	</span><span class="sxs-lookup"><span data-stu-id="2f981-112">Method</span></span> |<span data-ttu-id="2f981-113">傳回類型</span><span class="sxs-lookup"><span data-stu-id="2f981-113">Return Type</span></span> |<span data-ttu-id="2f981-114">描述</span><span class="sxs-lookup"><span data-stu-id="2f981-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="2f981-115">清單軟體</span><span class="sxs-lookup"><span data-stu-id="2f981-115">List software</span></span>](get-software.md) | <span data-ttu-id="2f981-116">軟體集合</span><span class="sxs-lookup"><span data-stu-id="2f981-116">Software collection</span></span> | <span data-ttu-id="2f981-117">列出組織軟體清查。</span><span class="sxs-lookup"><span data-stu-id="2f981-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="2f981-118">依識別碼取得軟體</span><span class="sxs-lookup"><span data-stu-id="2f981-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="2f981-119">軟體</span><span class="sxs-lookup"><span data-stu-id="2f981-119">Software</span></span> | <span data-ttu-id="2f981-120">根據軟體識別碼取得特定軟體。</span><span class="sxs-lookup"><span data-stu-id="2f981-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="2f981-121">軟體發行版本本清單</span><span class="sxs-lookup"><span data-stu-id="2f981-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="2f981-122">通訊組集合</span><span class="sxs-lookup"><span data-stu-id="2f981-122">Distribution collection</span></span> | <span data-ttu-id="2f981-123">依軟體識別碼列出軟體版本發行。</span><span class="sxs-lookup"><span data-stu-id="2f981-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="2f981-124">依軟體列出電腦</span><span class="sxs-lookup"><span data-stu-id="2f981-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="2f981-125">MachineRef 集合</span><span class="sxs-lookup"><span data-stu-id="2f981-125">MachineRef collection</span></span> | <span data-ttu-id="2f981-126">取得與軟體識別碼相關聯的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="2f981-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="2f981-127">依軟體列出弱點</span><span class="sxs-lookup"><span data-stu-id="2f981-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="2f981-128">[弱點](vulnerability.md) 集合</span><span class="sxs-lookup"><span data-stu-id="2f981-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="2f981-129">取得軟體識別碼相關聯的安全性漏洞清單。</span><span class="sxs-lookup"><span data-stu-id="2f981-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="2f981-130">取得遺失的 Kb</span><span class="sxs-lookup"><span data-stu-id="2f981-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="2f981-131">KB 集合</span><span class="sxs-lookup"><span data-stu-id="2f981-131">KB collection</span></span> | <span data-ttu-id="2f981-132">取得與軟體識別碼相關的遺失 Kb 清單。</span><span class="sxs-lookup"><span data-stu-id="2f981-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="2f981-133">屬性</span><span class="sxs-lookup"><span data-stu-id="2f981-133">Properties</span></span>

<span data-ttu-id="2f981-134">屬性	</span><span class="sxs-lookup"><span data-stu-id="2f981-134">Property</span></span> |   <span data-ttu-id="2f981-135">類型</span><span class="sxs-lookup"><span data-stu-id="2f981-135">Type</span></span>   |   <span data-ttu-id="2f981-136">描述</span><span class="sxs-lookup"><span data-stu-id="2f981-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="2f981-137">id</span><span class="sxs-lookup"><span data-stu-id="2f981-137">id</span></span> | <span data-ttu-id="2f981-138">字串</span><span class="sxs-lookup"><span data-stu-id="2f981-138">String</span></span> | <span data-ttu-id="2f981-139">軟體識別碼</span><span class="sxs-lookup"><span data-stu-id="2f981-139">Software ID</span></span>
<span data-ttu-id="2f981-140">名稱</span><span class="sxs-lookup"><span data-stu-id="2f981-140">Name</span></span> | <span data-ttu-id="2f981-141">字串</span><span class="sxs-lookup"><span data-stu-id="2f981-141">String</span></span> | <span data-ttu-id="2f981-142">軟體名稱</span><span class="sxs-lookup"><span data-stu-id="2f981-142">Software name</span></span>
<span data-ttu-id="2f981-143">廠商</span><span class="sxs-lookup"><span data-stu-id="2f981-143">Vendor</span></span> | <span data-ttu-id="2f981-144">字串</span><span class="sxs-lookup"><span data-stu-id="2f981-144">String</span></span> | <span data-ttu-id="2f981-145">軟體廠商名稱</span><span class="sxs-lookup"><span data-stu-id="2f981-145">Software vendor name</span></span>
<span data-ttu-id="2f981-146">弱點</span><span class="sxs-lookup"><span data-stu-id="2f981-146">Weaknesses</span></span> | <span data-ttu-id="2f981-147">Long</span><span class="sxs-lookup"><span data-stu-id="2f981-147">Long</span></span> | <span data-ttu-id="2f981-148">發現的漏洞數目</span><span class="sxs-lookup"><span data-stu-id="2f981-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="2f981-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="2f981-149">publicExploit</span></span> | <span data-ttu-id="2f981-150">布林值</span><span class="sxs-lookup"><span data-stu-id="2f981-150">Boolean</span></span> | <span data-ttu-id="2f981-151">部分弱點存在公開利用漏洞</span><span class="sxs-lookup"><span data-stu-id="2f981-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="2f981-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="2f981-152">activeAlert</span></span> | <span data-ttu-id="2f981-153">布林值</span><span class="sxs-lookup"><span data-stu-id="2f981-153">Boolean</span></span> | <span data-ttu-id="2f981-154">主動警示與此軟體關聯</span><span class="sxs-lookup"><span data-stu-id="2f981-154">Active alert is associated with this software</span></span>
<span data-ttu-id="2f981-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="2f981-155">exposedMachines</span></span> | <span data-ttu-id="2f981-156">Long</span><span class="sxs-lookup"><span data-stu-id="2f981-156">Long</span></span> | <span data-ttu-id="2f981-157">公開裝置的數目</span><span class="sxs-lookup"><span data-stu-id="2f981-157">Number of exposed devices</span></span>
<span data-ttu-id="2f981-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="2f981-158">impactScore</span></span> | <span data-ttu-id="2f981-159">雙精度浮點數</span><span class="sxs-lookup"><span data-stu-id="2f981-159">Double</span></span> | <span data-ttu-id="2f981-160">此軟體的暴露分數影響</span><span class="sxs-lookup"><span data-stu-id="2f981-160">Exposure score impact of this software</span></span>
