---
title: 調查資源類型
description: Microsoft Defender for Endpoint 調查實體。
keywords: api、graph api、支援的 api、get、警示、調查
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 252b273995d48d523604802c0c4365a613d86dbe
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771726"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="616aa-104">調查資源類型</span><span class="sxs-lookup"><span data-stu-id="616aa-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="616aa-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="616aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="616aa-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="616aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="616aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="616aa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="616aa-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="616aa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="616aa-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="616aa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="616aa-110">代表用於端點之 Defender 中的自動調查實體。</span><span class="sxs-lookup"><span data-stu-id="616aa-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="616aa-111">如需詳細資訊，請參閱 [自動調查一覽](automated-investigations.md) 。</span><span class="sxs-lookup"><span data-stu-id="616aa-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="616aa-112">方法</span><span class="sxs-lookup"><span data-stu-id="616aa-112">Methods</span></span>
<span data-ttu-id="616aa-113">方法	</span><span class="sxs-lookup"><span data-stu-id="616aa-113">Method</span></span>|<span data-ttu-id="616aa-114">傳回類型</span><span class="sxs-lookup"><span data-stu-id="616aa-114">Return Type</span></span> |<span data-ttu-id="616aa-115">描述</span><span class="sxs-lookup"><span data-stu-id="616aa-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="616aa-116">清單調查</span><span class="sxs-lookup"><span data-stu-id="616aa-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="616aa-117">調查集合</span><span class="sxs-lookup"><span data-stu-id="616aa-117">Investigation collection</span></span> | <span data-ttu-id="616aa-118">取得調查集合</span><span class="sxs-lookup"><span data-stu-id="616aa-118">Get collection of Investigation</span></span>
[<span data-ttu-id="616aa-119">取得單一調查</span><span class="sxs-lookup"><span data-stu-id="616aa-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="616aa-120">調查實體</span><span class="sxs-lookup"><span data-stu-id="616aa-120">Investigation entity</span></span> | <span data-ttu-id="616aa-121">取得單一調查實體。</span><span class="sxs-lookup"><span data-stu-id="616aa-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="616aa-122">開始調查</span><span class="sxs-lookup"><span data-stu-id="616aa-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="616aa-123">調查實體</span><span class="sxs-lookup"><span data-stu-id="616aa-123">Investigation entity</span></span> | <span data-ttu-id="616aa-124">在裝置上開始調查。</span><span class="sxs-lookup"><span data-stu-id="616aa-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="616aa-125">屬性</span><span class="sxs-lookup"><span data-stu-id="616aa-125">Properties</span></span>
<span data-ttu-id="616aa-126">屬性	</span><span class="sxs-lookup"><span data-stu-id="616aa-126">Property</span></span> |  <span data-ttu-id="616aa-127">類型</span><span class="sxs-lookup"><span data-stu-id="616aa-127">Type</span></span>    |   <span data-ttu-id="616aa-128">描述</span><span class="sxs-lookup"><span data-stu-id="616aa-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="616aa-129">id</span><span class="sxs-lookup"><span data-stu-id="616aa-129">id</span></span> | <span data-ttu-id="616aa-130">字串</span><span class="sxs-lookup"><span data-stu-id="616aa-130">String</span></span> | <span data-ttu-id="616aa-131">調查實體的身分識別。</span><span class="sxs-lookup"><span data-stu-id="616aa-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="616aa-132">startTime</span><span class="sxs-lookup"><span data-stu-id="616aa-132">startTime</span></span> | <span data-ttu-id="616aa-133">DateTime 可為 Null</span><span class="sxs-lookup"><span data-stu-id="616aa-133">DateTime Nullable</span></span> | <span data-ttu-id="616aa-134">建立調查的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="616aa-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="616aa-135">endTime</span><span class="sxs-lookup"><span data-stu-id="616aa-135">endTime</span></span> | <span data-ttu-id="616aa-136">DateTime 可為 Null</span><span class="sxs-lookup"><span data-stu-id="616aa-136">DateTime Nullable</span></span> | <span data-ttu-id="616aa-137">完成調查的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="616aa-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="616aa-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="616aa-138">cancelledBy</span></span> | <span data-ttu-id="616aa-139">字串</span><span class="sxs-lookup"><span data-stu-id="616aa-139">String</span></span> | <span data-ttu-id="616aa-140">取消調查的使用者/應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="616aa-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="616aa-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="616aa-141">investigationState</span></span> | <span data-ttu-id="616aa-142">Enum</span><span class="sxs-lookup"><span data-stu-id="616aa-142">Enum</span></span> | <span data-ttu-id="616aa-143">調查的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="616aa-143">The current state of the investigation.</span></span> <span data-ttu-id="616aa-144">可能的值為： ' Unknown '、' 終止 '、' SuccessfullyRemediated '、' 良性 '、' Failed '、' PartiallyRemediated '、' PartiallyInvestigated '、' PendingApproval '、' PendingResource '、' TerminatedByUser '、' TerminatedBySystem '、' InnerFailure '、' PreexistingAlert '、' UnsupportedOs '、' UnsupportedAlertType '、' SuppressedAlert '、' '、' '。</span><span class="sxs-lookup"><span data-stu-id="616aa-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="616aa-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="616aa-145">statusDetails</span></span> | <span data-ttu-id="616aa-146">字串</span><span class="sxs-lookup"><span data-stu-id="616aa-146">String</span></span> | <span data-ttu-id="616aa-147">有關調查狀態的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="616aa-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="616aa-148">machineId</span><span class="sxs-lookup"><span data-stu-id="616aa-148">machineId</span></span> | <span data-ttu-id="616aa-149">字串</span><span class="sxs-lookup"><span data-stu-id="616aa-149">String</span></span> | <span data-ttu-id="616aa-150">執行調查所在之裝置的識別碼。</span><span class="sxs-lookup"><span data-stu-id="616aa-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="616aa-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="616aa-151">computerDnsName</span></span> | <span data-ttu-id="616aa-152">字串</span><span class="sxs-lookup"><span data-stu-id="616aa-152">String</span></span> | <span data-ttu-id="616aa-153">執行調查所在之裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="616aa-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="616aa-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="616aa-154">triggeringAlertId</span></span> | <span data-ttu-id="616aa-155">字串</span><span class="sxs-lookup"><span data-stu-id="616aa-155">String</span></span> | <span data-ttu-id="616aa-156">觸發調查的警示識別碼。</span><span class="sxs-lookup"><span data-stu-id="616aa-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="616aa-157">Json 標記法</span><span class="sxs-lookup"><span data-stu-id="616aa-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
