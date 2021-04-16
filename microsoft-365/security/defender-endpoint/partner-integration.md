---
title: Microsoft Defender for Endpoint partner 機遇和案例
ms.reviewer: ''
description: 瞭解如何將現有的安全性產品擴充到開放架構的上方，以及一組豐富的 APIs，以建立分機並與 Microsoft Defender for Endpoint 整合
keywords: API，partner，extend，開放式架構，api，擴充，整合，偵測，管理，回應，漏洞，智慧
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: be2f33514a568f290a3fc5cf0adc62db72243a6f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861104"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="a5f6e-104">Microsoft Defender for Endpoint partner 機遇和案例</span><span class="sxs-lookup"><span data-stu-id="a5f6e-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a5f6e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a5f6e-105">**Applies to:**</span></span>
- [<span data-ttu-id="a5f6e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a5f6e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a5f6e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5f6e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="a5f6e-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a5f6e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a5f6e-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="a5f6e-110">合作夥伴可以輕鬆地將其現有的安全性產品擴充到開放架構的上方，以及豐富且完整的 APIs 集合，以使用 Defender for Endpoint 來建立分機和整合。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="a5f6e-111">APIs 範圍的功能範圍包括偵測、管理、回應、弱點，以及使用全球的智慧功能案例。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="a5f6e-112">根據使用案例及需求，協力廠商可以從 Defender 進行資料 stream 或查詢資料。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="a5f6e-113">案例1：外部警示關聯性及自動化調查和修正</span><span class="sxs-lookup"><span data-stu-id="a5f6e-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="a5f6e-114">Defender for Endpoint 提供了獨特的自動化調查和修正功能，以在規模中促進事件回應。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="a5f6e-115">將自動化調查和回應功能與其他解決方案（如網路安全性產品或其他端點安全性產品）整合，可協助您解決警示。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="a5f6e-116">整合也會將網路和裝置信號關聯的複雜性降到最低，並有效地簡化裝置上的調查和威脅修正動作。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="a5f6e-117">Defender for Endpoint 會以下列形式新增此案例的支援：</span><span class="sxs-lookup"><span data-stu-id="a5f6e-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="a5f6e-118">外部提醒可以推入 Defender for Endpoint，並以來自于來自 Defender for Endpoint 的其他裝置型提醒並排呈現。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="a5f6e-119">這個視圖提供完整的警示內容，包含實際的處理常式和攻擊的完整案例。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="a5f6e-120">警示一經產生，便會在企業中的 Endpoint protected 端點的所有 Defender 間共用信號。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="a5f6e-121">Defender for Endpoint 會採取立即自動或接線員輔助的回應來處理警示。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="a5f6e-122">案例2：安全性 orchestration 和 automation 回應 (SOAR) 整合</span><span class="sxs-lookup"><span data-stu-id="a5f6e-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="a5f6e-123">Orchestration 方案可協助您建立行動手冊，並整合用於端點 APIs 公開進行協調回應的工作，例如查詢裝置資料、觸發裝置隔離、封鎖/允許、解析警示及其他的動作。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="a5f6e-124">案例3：指標匹配</span><span class="sxs-lookup"><span data-stu-id="a5f6e-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="a5f6e-125"> (IoCs) 相符的指示器是每個 endpoint protection 解決方案中的基本功能。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="a5f6e-126">這項功能可在 Defender for Endpoint 中使用，並可為實體的預防、偵測和排除設定標記清單。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="a5f6e-127">一個可以定義要採取的動作，以及套用動作的時間。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="a5f6e-128">上述案例是平臺擴充性的範例。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="a5f6e-129">您不只局限于這些範例，我們一定會鼓勵您利用開放式架構來探索及探索其他案例。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="a5f6e-130">請遵循 [成為 Microsoft defender For endpoint partner](get-started-partner-integration.md) 中的步驟，以在 Defender for endpoint 中整合您的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a5f6e-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="a5f6e-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="a5f6e-131">Related topic</span></span>
- [<span data-ttu-id="a5f6e-132">管理和 API 概觀</span><span class="sxs-lookup"><span data-stu-id="a5f6e-132">Overview of management and APIs</span></span>](management-apis.md)
