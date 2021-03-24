---
title: Microsoft Defender for Endpoint API 發行附注
description: Microsoft Defender APIs 的端點集合所進行的更新的版本資訊。
keywords: microsoft defender for endpoint api 發行附注、mde、api、mdatp api、更新、記事、版本
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
ms.openlocfilehash: e37841fa17a5998c431c6a76b878f20ef1b06d10
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057164"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="e2a82-104">Microsoft Defender for Endpoint API 發行附注</span><span class="sxs-lookup"><span data-stu-id="e2a82-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="e2a82-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e2a82-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e2a82-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e2a82-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e2a82-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e2a82-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="e2a82-108">下列資訊會列出對 Microsoft Defender for Endpoint APIs 所做的更新，以及所進行的日期。</span><span class="sxs-lookup"><span data-stu-id="e2a82-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>


> [!TIP]
> <span data-ttu-id="e2a82-109">RSS 摘要：將下列 URL 複製並貼到您的摘要讀取器時，獲得此頁面的通知：</span><span class="sxs-lookup"><span data-stu-id="e2a82-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span> 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a><span data-ttu-id="e2a82-110">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="e2a82-110">10.02.2021</span></span>
<hr>

- <span data-ttu-id="e2a82-111">新增 API： [批次更新提醒](batch-update-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a82-111">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span> 

<br>

### <a name="25012021"></a><span data-ttu-id="e2a82-112">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="e2a82-112">25.01.2021</span></span>
<hr>

- <span data-ttu-id="e2a82-113">將 [高級搜尋 API](run-advanced-query-api.md) 的更新率限制從15個要求的每分鐘的45個要求。</span><span class="sxs-lookup"><span data-stu-id="e2a82-113">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span> 

<br>

### <a name="21012021"></a><span data-ttu-id="e2a82-114">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="e2a82-114">21.01.2021</span></span>
<hr>

- <span data-ttu-id="e2a82-115">新增 API：依標籤 [尋找裝置](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a82-115">Added new API: [Find devices by tag](machine-tags.md).</span></span> 
- <span data-ttu-id="e2a82-116">新增 API：匯 [入指示器](import-ti-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a82-116">Added new API: [Import Indicators](import-ti-indicators.md).</span></span> 

<br>

### <a name="03012021"></a><span data-ttu-id="e2a82-117">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="e2a82-117">03.01.2021</span></span>
<hr>

- <span data-ttu-id="e2a82-118">更新的警示證據：新增 ***detectionStatus** _、 _*_ParentProcessFilePath_*_ 和 _ *_parentProcessFileName_** 屬性。</span><span class="sxs-lookup"><span data-stu-id="e2a82-118">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="e2a82-119">已更新的 [警示實體](alerts.md)：新增 ***detectorId*** 屬性。</span><span class="sxs-lookup"><span data-stu-id="e2a82-119">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

<br>

### <a name="15122020"></a><span data-ttu-id="e2a82-120">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="e2a82-120">15.12.2020</span></span>
<hr>

- <span data-ttu-id="e2a82-121">已更新 [裝置](machine.md) 實體：新增 ***IpInterfaces*** 清單。</span><span class="sxs-lookup"><span data-stu-id="e2a82-121">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="e2a82-122">請參閱 [清單裝置](get-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a82-122">See [List devices](get-machines.md).</span></span>

<br>

### <a name="04112020"></a><span data-ttu-id="e2a82-123">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="e2a82-123">04.11.2020</span></span>
<hr>

- <span data-ttu-id="e2a82-124">新增 API： [Set device value](set-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a82-124">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="e2a82-125">已更新 [裝置](machine.md) 實體：新增 ***deviceValue*** 屬性。</span><span class="sxs-lookup"><span data-stu-id="e2a82-125">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

<br>

### <a name="01092020"></a><span data-ttu-id="e2a82-126">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="e2a82-126">01.09.2020</span></span>
<hr>

- <span data-ttu-id="e2a82-127">新增選項，以使用其相關的證據來擴充警示實體。</span><span class="sxs-lookup"><span data-stu-id="e2a82-127">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="e2a82-128">請參閱 [清單提醒](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a82-128">See [List Alerts](get-alerts.md).</span></span>

<br>
<br>