---
title: Microsoft Defender for Endpoint API 發行附注
description: Microsoft Defender APIs 的端點集合所進行的更新的版本資訊。
keywords: Microsoft Defender for Endpoint API 發行附注，mde，APIs，Microsoft Defender for Endpoint API，更新，記事，發行
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
ms.openlocfilehash: 5c8e9d8e1c8ec020b4d742f61d276c93f6730bec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245549"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="ef234-104">Microsoft Defender for Endpoint API 發行附注</span><span class="sxs-lookup"><span data-stu-id="ef234-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="ef234-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ef234-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ef234-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="ef234-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ef234-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ef234-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ef234-108">下列資訊會列出對 Microsoft Defender for Endpoint APIs 所做的更新，以及所進行的日期。</span><span class="sxs-lookup"><span data-stu-id="ef234-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="ef234-109">RSS 摘要：將下列 URL 複製並貼到您的摘要讀取器時，獲得此頁面的通知：</span><span class="sxs-lookup"><span data-stu-id="ef234-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="ef234-110">發行附注-最新到最舊 (dd yyyy) </span><span class="sxs-lookup"><span data-stu-id="ef234-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="03052021"></a><span data-ttu-id="ef234-111">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="ef234-111">03.05.2021</span></span>

- <span data-ttu-id="ef234-112">新增 API： [修復活動方法和屬性](get-remediation-methods-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="ef234-112">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="ef234-113">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="ef234-113">10.02.2021</span></span>

- <span data-ttu-id="ef234-114">新增 API： [批次更新提醒](batch-update-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="ef234-114">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="ef234-115">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="ef234-115">25.01.2021</span></span>

- <span data-ttu-id="ef234-116">將 [高級搜尋 API](run-advanced-query-api.md) 的更新率限制從15個要求的每分鐘的45個要求。</span><span class="sxs-lookup"><span data-stu-id="ef234-116">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="ef234-117">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="ef234-117">21.01.2021</span></span>

- <span data-ttu-id="ef234-118">新增 API：依標籤 [尋找裝置](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="ef234-118">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="ef234-119">新增 API：匯 [入指示器](import-ti-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="ef234-119">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="ef234-120">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="ef234-120">03.01.2021</span></span>

- <span data-ttu-id="ef234-121">更新的警示證據：新增 ***detectionStatus** _、 _*_ParentProcessFilePath_*_ 和 _ *_parentProcessFileName_** 屬性。</span><span class="sxs-lookup"><span data-stu-id="ef234-121">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="ef234-122">已更新的 [警示實體](alerts.md)：新增 ***detectorId*** 屬性。</span><span class="sxs-lookup"><span data-stu-id="ef234-122">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="ef234-123">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="ef234-123">15.12.2020</span></span>

- <span data-ttu-id="ef234-124">已更新 [裝置](machine.md) 實體：新增 ***IpInterfaces*** 清單。</span><span class="sxs-lookup"><span data-stu-id="ef234-124">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="ef234-125">請參閱 [清單裝置](get-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="ef234-125">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="ef234-126">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="ef234-126">04.11.2020</span></span>

- <span data-ttu-id="ef234-127">新增 API： [Set device value](set-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="ef234-127">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="ef234-128">已更新 [裝置](machine.md) 實體：新增 ***deviceValue*** 屬性。</span><span class="sxs-lookup"><span data-stu-id="ef234-128">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="ef234-129">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="ef234-129">01.09.2020</span></span>

- <span data-ttu-id="ef234-130">新增選項，以使用其相關的證據來擴充警示實體。</span><span class="sxs-lookup"><span data-stu-id="ef234-130">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="ef234-131">請參閱 [清單提醒](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="ef234-131">See [List Alerts](get-alerts.md).</span></span>
