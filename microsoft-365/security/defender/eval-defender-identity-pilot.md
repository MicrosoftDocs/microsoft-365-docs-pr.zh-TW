---
title: 試驗 Microsoft Defender for Identity，設定設定基準，標準，指導方針，並取得偵測和修正各種身分識別威脅（如偵測、受損認證、橫向移動、網域控制和 exfiltration 警示）、執行使用者、電腦、實體及橫向移動路徑調查的教程。
description: 試驗 Microsoft Defender 身分識別、設定基準、取得偵測上的教學課程、受損的認證、側向移動、網域控制和 exfiltration 提醒等其他。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457765"
---
# <a name="pilot-microsoft-defender-for-identity"></a><span data-ttu-id="4c11d-103">試驗 Microsoft Defender 身分識別</span><span class="sxs-lookup"><span data-stu-id="4c11d-103">Pilot Microsoft Defender for Identity</span></span>


<span data-ttu-id="4c11d-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4c11d-104">**Applies to:**</span></span>
- <span data-ttu-id="4c11d-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c11d-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="4c11d-106">本文是設定 Microsoft Defender 身分識別的評估環境過程中的 [步驟 3](eval-defender-identity-overview.md) 之3。</span><span class="sxs-lookup"><span data-stu-id="4c11d-106">This article is [Step 3 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="4c11d-107">如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4c11d-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="4c11d-108">使用下列步驟來設定和設定 Microsoft Defender 身分識別的試驗。</span><span class="sxs-lookup"><span data-stu-id="4c11d-108">Use the following steps to setup and configure the pilot for Microsoft Defender for identity.</span></span> <span data-ttu-id="4c11d-109">請注意，建議不要包含設定試驗群組。</span><span class="sxs-lookup"><span data-stu-id="4c11d-109">Note that the recommendations don't include setting up a pilot group.</span></span> <span data-ttu-id="4c11d-110">最佳作法是先繼續，然後在所有執行 Active Directory 網域服務的伺服器上安裝感應器 (AD DS) 和 Active Directory 同盟服務 (AD FS) 。</span><span class="sxs-lookup"><span data-stu-id="4c11d-110">The best practice is to go ahead and install the sensor on all of your servers running Active Directory Domain Services (AD DS) and Active Directory Federated Services (AD FS).</span></span>

![將 Microsoft Defender 身分識別新增至 Defender 評估環境的步驟](../../media/defender/m365-defender-identity-pilot-steps.png)

<span data-ttu-id="4c11d-112">下表說明圖例中的步驟。</span><span class="sxs-lookup"><span data-stu-id="4c11d-112">The following table describes the steps in the illustration.</span></span>

- [<span data-ttu-id="4c11d-113">步驟1：設定身分識別環境的基準建議</span><span class="sxs-lookup"><span data-stu-id="4c11d-113">Step 1: Configure benchmark recommendations for your identity environment</span></span>](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [<span data-ttu-id="4c11d-114">步驟2：試用功能-逐步指導教程，以找出並修正不同的攻擊類型 </span><span class="sxs-lookup"><span data-stu-id="4c11d-114">Step 2: Try out capabilities — Walk through tutorials for identifying and remediating different attack types </span></span>](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a><span data-ttu-id="4c11d-115">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="4c11d-115">Step 1.</span></span> <span data-ttu-id="4c11d-116">設定身分識別環境的基準建議</span><span class="sxs-lookup"><span data-stu-id="4c11d-116">Configure benchmark recommendations for your identity environment</span></span>

<span data-ttu-id="4c11d-117">Microsoft 會提供使用 Microsoft 雲端服務之客戶的安全性基準建議。</span><span class="sxs-lookup"><span data-stu-id="4c11d-117">Microsoft provides security benchmark recommendations for customers using Microsoft Cloud services.</span></span> <span data-ttu-id="4c11d-118">[Azure 安全性基準](/security/benchmark/azure/overview) (ASB) 提供規範性的最佳作法和建議，以協助改善 Azure 上工作負載、資料和服務的安全性。</span><span class="sxs-lookup"><span data-stu-id="4c11d-118">The [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) provides prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure.</span></span>

<span data-ttu-id="4c11d-119">這些基準建議包括 [Microsoft Defender 身分識別的 Azure 安全性基準](/security/benchmark/azure/baselines/defender-for-identity-security-baseline)。</span><span class="sxs-lookup"><span data-stu-id="4c11d-119">These benchmark recommendations include [Azure security baseline for Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span></span> <span data-ttu-id="4c11d-120">實施這些建議可能需要一些時間來規劃及實施。</span><span class="sxs-lookup"><span data-stu-id="4c11d-120">Implementing these recommendations can take some time to plan and implement.</span></span> <span data-ttu-id="4c11d-121">雖然這些會極大提高身分識別環境的安全性，但不應阻止您繼續評估和執行 Microsoft Defender 身分識別。</span><span class="sxs-lookup"><span data-stu-id="4c11d-121">While these will greatly increase the security of your identity environment, they shouldn't prevent you from continuing to evaluate and implement Microsoft Defender for Identity.</span></span> <span data-ttu-id="4c11d-122">您可以在這裡為您的認知提供這些內容。</span><span class="sxs-lookup"><span data-stu-id="4c11d-122">These are provided here for your awareness.</span></span>

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a><span data-ttu-id="4c11d-123">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="4c11d-123">Step 2.</span></span> <span data-ttu-id="4c11d-124">嘗試功能-逐步指導教程，以找出並修正不同的攻擊類型</span><span class="sxs-lookup"><span data-stu-id="4c11d-124">Try out capabilities — Walk through tutorials for identifying and remediating different attack types</span></span>

<span data-ttu-id="4c11d-125">Microsoft Defender 身分識別檔包括一系列的教程，可引導您完成識別和修正各種攻擊類型的程式。</span><span class="sxs-lookup"><span data-stu-id="4c11d-125">The Microsoft Defender for Identity documentation includes a series of tutorials that walk through the process of identifying and remediating various attack types.</span></span>

<span data-ttu-id="4c11d-126">嘗試身分識別教程的 Defender：</span><span class="sxs-lookup"><span data-stu-id="4c11d-126">Try out Defender for Identity tutorials:</span></span>
- [<span data-ttu-id="4c11d-127">偵測警示</span><span class="sxs-lookup"><span data-stu-id="4c11d-127">Reconnaissance alerts</span></span>](/defender-for-identity/reconnaissance-alerts)
- [<span data-ttu-id="4c11d-128">已受損的認證警示</span><span class="sxs-lookup"><span data-stu-id="4c11d-128">Compromised credential alerts</span></span>](/defender-for-identity/compromised-credentials-alerts)
- [<span data-ttu-id="4c11d-129">橫向移動警示</span><span class="sxs-lookup"><span data-stu-id="4c11d-129">Lateral movement alerts</span></span>](/defender-for-identity/lateral-movement-alerts)
- [<span data-ttu-id="4c11d-130">網域對警示</span><span class="sxs-lookup"><span data-stu-id="4c11d-130">Domain dominance alerts</span></span>](/defender-for-identity/domain-dominance-alerts)
- [<span data-ttu-id="4c11d-131">Exfiltration 警示</span><span class="sxs-lookup"><span data-stu-id="4c11d-131">Exfiltration alerts</span></span>](/defender-for-identity/exfiltration-alerts)
- [<span data-ttu-id="4c11d-132">調查使用者</span><span class="sxs-lookup"><span data-stu-id="4c11d-132">Investigate a user</span></span>](/defender-for-identity/investigate-a-user)
- [<span data-ttu-id="4c11d-133">調查電腦</span><span class="sxs-lookup"><span data-stu-id="4c11d-133">Investigate a computer</span></span>](/defender-for-identity/investigate-a-computer)
- [<span data-ttu-id="4c11d-134">調查橫向移動路徑</span><span class="sxs-lookup"><span data-stu-id="4c11d-134">Investigate lateral movement paths</span></span>](/defender-for-identity/investigate-lateral-movement-path)
- [<span data-ttu-id="4c11d-135">調查實體</span><span class="sxs-lookup"><span data-stu-id="4c11d-135">Investigate entities</span></span>](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a><span data-ttu-id="4c11d-136">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4c11d-136">Next steps</span></span>

[<span data-ttu-id="4c11d-137">評估 Microsoft Defender 的 Office 365</span><span class="sxs-lookup"><span data-stu-id="4c11d-137">Evaluate Microsoft Defender for Office 365</span></span>](eval-defender-office-365-overview.md)

<span data-ttu-id="4c11d-138">回到概述，以[評估 Microsoft Defender 的 Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4c11d-138">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="4c11d-139">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="4c11d-139">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>