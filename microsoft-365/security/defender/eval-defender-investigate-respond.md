---
title: 在試驗環境中使用 Microsoft 365 Defender 調查和回應，並使用攻擊模擬器、教授使用者偵測、調查攻擊面及強化安全性狀況
description: 在 Microsoft 365 Defender 試用實驗室或試驗環境中設定攻擊模擬，以嘗試用來教授使用者以保護裝置、身分識別、資料及應用程式的安全性解決方案。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 590b9445b08e3a786b32e7086f27b140934d22d0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457941"
---
# <a name="investigate-and-respond-using-microsoft-365-defender-in-a-pilot-environment"></a><span data-ttu-id="c1cd6-103">在試驗環境中使用 Microsoft 365 Defender 調查和回應</span><span class="sxs-lookup"><span data-stu-id="c1cd6-103">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>

<span data-ttu-id="c1cd6-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c1cd6-104">**Applies to:**</span></span>
- <span data-ttu-id="c1cd6-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1cd6-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="c1cd6-106">本文概述使用攻擊模擬及教學課程建立事件的程式，並使用 Microsoft 365 Defender 來調查和回應。</span><span class="sxs-lookup"><span data-stu-id="c1cd6-106">This article outlines the process to create incidents with attack simulations and tutorials and use Microsoft 365 Defender to investigate and respond.</span></span> <span data-ttu-id="c1cd6-107">開始此程式之前，請確定您已複習[評估 Microsoft 365 Defender](eval-overview.md)的整體程式，且已[建立 Microsoft 365 Defender 評估環境](eval-create-eval-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="c1cd6-107">Before starting this process, be sure you've reviewed the overall process for [evaluating Microsoft 365 Defender](eval-overview.md) and you have [created the Microsoft 365 Defender evaluation environment](eval-create-eval-environment.md).</span></span>

<span data-ttu-id="c1cd6-108">請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="c1cd6-108">Use the following steps.</span></span>

![在 Microsoft 365 Defender 評估環境中執行模擬事件回應的步驟](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-steps.png)

<span data-ttu-id="c1cd6-110">下表說明圖例中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c1cd6-110">The following table describes the steps in the illustration.</span></span>

| |<span data-ttu-id="c1cd6-111">步驟</span><span class="sxs-lookup"><span data-stu-id="c1cd6-111">Step</span></span>  |<span data-ttu-id="c1cd6-112">描述</span><span class="sxs-lookup"><span data-stu-id="c1cd6-112">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c1cd6-113">1</span><span class="sxs-lookup"><span data-stu-id="c1cd6-113">1</span></span>|[<span data-ttu-id="c1cd6-114">類比攻擊</span><span class="sxs-lookup"><span data-stu-id="c1cd6-114">Simulate attacks</span></span>](eval-defender-investigate-respond-simulate-attack.md)     |   <span data-ttu-id="c1cd6-115">在評估環境上模擬攻擊，並使用 Microsoft 365 Defender 入口網站來執行事件回應。</span><span class="sxs-lookup"><span data-stu-id="c1cd6-115">Simulate attacks on your evaluation environment and use the Microsoft 365 Defender portal to perform incident response.</span></span>      |
|<span data-ttu-id="c1cd6-116">2 </span><span class="sxs-lookup"><span data-stu-id="c1cd6-116">2</span></span>|[<span data-ttu-id="c1cd6-117">嘗試事件回應功能 </span><span class="sxs-lookup"><span data-stu-id="c1cd6-117">Try incident response capabilities </span></span>](eval-defender-investigate-respond-additional.md)    |    <span data-ttu-id="c1cd6-118">嘗試 Microsoft 365 Defender 中的功能。</span><span class="sxs-lookup"><span data-stu-id="c1cd6-118">Try features and capabilities in Microsoft 365 Defender.</span></span>     |
||||

### <a name="navigation-you-may-need"></a><span data-ttu-id="c1cd6-119">您可能需要的導覽</span><span class="sxs-lookup"><span data-stu-id="c1cd6-119">Navigation you may need</span></span>

[<span data-ttu-id="c1cd6-120">建立 Microsoft 365 Defender 評估環境</span><span class="sxs-lookup"><span data-stu-id="c1cd6-120">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
