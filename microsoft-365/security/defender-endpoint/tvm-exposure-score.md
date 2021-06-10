---
title: 威脅與弱點管理中的披露分數
description: 威脅與弱點管理公開得分會反映您的組織 cybersecurity 威脅的漏洞。
keywords: 披露分數，microsoft defender for endpoint 洩密分數，microsoft defender for endpoint tvm 洩密分數，組織暴露分數，tvm 組織公開分數，威脅與弱點管理，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcea240fe1dc0ce97a2800391320b04c39c84336
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934102"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="4c28c-104">披露分數-威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="4c28c-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4c28c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4c28c-105">**Applies to:**</span></span>

- [<span data-ttu-id="4c28c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4c28c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4c28c-107">威脅及弱點管理</span><span class="sxs-lookup"><span data-stu-id="4c28c-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4c28c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c28c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4c28c-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="4c28c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4c28c-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="4c28c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="4c28c-111">您的披露分數會顯示在 Microsoft Defender 資訊安全中心中的 [[威脅與弱點管理] 儀表板](tvm-dashboard-insights.md)中。</span><span class="sxs-lookup"><span data-stu-id="4c28c-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="4c28c-112">它會反映您的組織 cybersecurity 威脅的漏洞。</span><span class="sxs-lookup"><span data-stu-id="4c28c-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="4c28c-113">低暴露分數表示您的裝置不易受到攻擊。</span><span class="sxs-lookup"><span data-stu-id="4c28c-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="4c28c-114">快速瞭解及識別您組織中的安全性狀態的高層次優點。</span><span class="sxs-lookup"><span data-stu-id="4c28c-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="4c28c-115">偵測並回應需要調查的區域，或採取動作以改善目前狀態。</span><span class="sxs-lookup"><span data-stu-id="4c28c-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="4c28c-116">與同行和管理有關安全性工作影響的通訊。</span><span class="sxs-lookup"><span data-stu-id="4c28c-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="4c28c-117">這張卡片為您提供一段時間的公開得分趨勢的高層級。</span><span class="sxs-lookup"><span data-stu-id="4c28c-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="4c28c-118">圖表中的任何峰值可讓您直觀地指出您可以進一步調查的高 cybersecurity 威脅危險性。</span><span class="sxs-lookup"><span data-stu-id="4c28c-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![披露分數卡片](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="4c28c-120">運作方式</span><span class="sxs-lookup"><span data-stu-id="4c28c-120">How it works</span></span>

<span data-ttu-id="4c28c-121">曝光分數分為下列層級：</span><span class="sxs-lookup"><span data-stu-id="4c28c-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="4c28c-122">0–29：低曝光分數</span><span class="sxs-lookup"><span data-stu-id="4c28c-122">0–29: low exposure score</span></span>
- <span data-ttu-id="4c28c-123">30–69：中度曝光分數</span><span class="sxs-lookup"><span data-stu-id="4c28c-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="4c28c-124">70–100：高暴露程度分數</span><span class="sxs-lookup"><span data-stu-id="4c28c-124">70–100: high exposure score</span></span>

<span data-ttu-id="4c28c-125">您可以根據已設定優先順序的 [安全性建議](tvm-security-recommendation.md) ，修正問題，以降低暴露分數。</span><span class="sxs-lookup"><span data-stu-id="4c28c-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="4c28c-126">每個軟體都有缺點，會根據組織面臨的風險，加以轉換為建議並設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="4c28c-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="4c28c-127">減少威脅和弱點洩密</span><span class="sxs-lookup"><span data-stu-id="4c28c-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="4c28c-128">修正 [安全性建議](tvm-security-recommendation.md)，以降低威脅和弱點的危險性。</span><span class="sxs-lookup"><span data-stu-id="4c28c-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="4c28c-129">修正可在[威脅與弱點管理儀表板](tvm-dashboard-insights.md)中查看的最高安全性建議，以充分影響曝光分數。</span><span class="sxs-lookup"><span data-stu-id="4c28c-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c28c-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="4c28c-130">Related topics</span></span>

- [<span data-ttu-id="4c28c-131">威脅與弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="4c28c-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4c28c-132">裝置用 Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="4c28c-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="4c28c-133">安全性建議</span><span class="sxs-lookup"><span data-stu-id="4c28c-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="4c28c-134">活動時間表</span><span class="sxs-lookup"><span data-stu-id="4c28c-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
