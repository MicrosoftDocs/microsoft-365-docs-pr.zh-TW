---
title: 查看 Microsoft Defender 的端點架構需求和重要概念
description: 在 Microsoft 365 Defender 中，Microsoft Defender for Endpoint 的技術圖表可協助您在建立試用實驗室或試驗環境之前，先瞭解 Microsoft 365 中的身分識別。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
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
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457817"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a><span data-ttu-id="83baf-103">查看 Microsoft Defender 的端點架構需求和重要概念</span><span class="sxs-lookup"><span data-stu-id="83baf-103">Review Microsoft Defender for Endpoint architecture requirements and key concepts</span></span>

<span data-ttu-id="83baf-104">**適用于：** Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83baf-104">**Applies to:** Microsoft 365 Defender</span></span>

<span data-ttu-id="83baf-105">本文將引導您在設定 Microsoft Defender for Endpoint 環境評估的過程中。</span><span class="sxs-lookup"><span data-stu-id="83baf-105">This article will guide you in the process of setting up the evaluation for Microsoft Defender for Endpoint environment.</span></span>

<span data-ttu-id="83baf-106">如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-endpoint-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="83baf-106">For more information about this process, see the [overview article](eval-defender-endpoint-overview.md).</span></span>

<span data-ttu-id="83baf-107">啟用 Microsoft Defender for Endpoint 之前，請確定您瞭解架構，並且可以符合需求。</span><span class="sxs-lookup"><span data-stu-id="83baf-107">Before enabling Microsoft Defender for Endpoint, be sure you understand the architecture and can meet the requirements.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="83baf-108">了解架構</span><span class="sxs-lookup"><span data-stu-id="83baf-108">Understand the architecture</span></span>

<span data-ttu-id="83baf-109">下圖說明用於端點架構和整合的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="83baf-109">The following diagram illustrates Microsoft Defender for Endpoint architecture and integrations.</span></span> 

![將 Microsoft defender for Office 新增至 Defender 評估環境的步驟](../../media/defender/m365-defender-endpoint-architecture.png)

<span data-ttu-id="83baf-111">下表說明圖例。</span><span class="sxs-lookup"><span data-stu-id="83baf-111">The following table describes the illustration.</span></span>

<span data-ttu-id="83baf-112">撥出</span><span class="sxs-lookup"><span data-stu-id="83baf-112">Call-out</span></span> | <span data-ttu-id="83baf-113">說明</span><span class="sxs-lookup"><span data-stu-id="83baf-113">Description</span></span>
:---|:---|
<span data-ttu-id="83baf-114">1</span><span class="sxs-lookup"><span data-stu-id="83baf-114">1</span></span> | <span data-ttu-id="83baf-115">透過其中一個支援的管理工具來 boarded 裝置。</span><span class="sxs-lookup"><span data-stu-id="83baf-115">Devices are on-boarded through one of the supported management tools.</span></span> 
<span data-ttu-id="83baf-116">2 </span><span class="sxs-lookup"><span data-stu-id="83baf-116">2</span></span> | <span data-ttu-id="83baf-117">Boarded 裝置會提供 Microsoft Defender for Endpoint 信號資料，並加以回應。</span><span class="sxs-lookup"><span data-stu-id="83baf-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span></span>
<span data-ttu-id="83baf-118">3 </span><span class="sxs-lookup"><span data-stu-id="83baf-118">3</span></span> | <span data-ttu-id="83baf-119">受管理的裝置會在 Azure Active Directory 中加入和/或註冊。</span><span class="sxs-lookup"><span data-stu-id="83baf-119">Managed devices are joined and/or enrolled in Azure Active Directory.</span></span>
<span data-ttu-id="83baf-120">4 </span><span class="sxs-lookup"><span data-stu-id="83baf-120">4</span></span> | <span data-ttu-id="83baf-121">加入網域的 Windows 10 裝置會使用 Azure Active Directory 連線同步處理至 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="83baf-121">Domain-joined Windows 10 devices are synchronized to Azure Active Directory using Azure Active Directory Connect.</span></span>
<span data-ttu-id="83baf-122">5 </span><span class="sxs-lookup"><span data-stu-id="83baf-122">5</span></span> | <span data-ttu-id="83baf-123">Microsoft Defender for Endpoint 警示、調查和回應是在 Microsoft 365 Defender 中管理。</span><span class="sxs-lookup"><span data-stu-id="83baf-123">Microsoft Defender for Endpoint alerts, investigations, and responses are managed in Microsoft 365 Defender.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="83baf-124">瞭解重要概念</span><span class="sxs-lookup"><span data-stu-id="83baf-124">Understand key concepts</span></span>

<span data-ttu-id="83baf-125">下清單格識別重要概念，在評估、設定及部署 Microsoft Defender for Endpoint 時，重要概念非常重要：</span><span class="sxs-lookup"><span data-stu-id="83baf-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Endpoint:</span></span> 

<span data-ttu-id="83baf-126">概念</span><span class="sxs-lookup"><span data-stu-id="83baf-126">Concept</span></span> | <span data-ttu-id="83baf-127">描述</span><span class="sxs-lookup"><span data-stu-id="83baf-127">Description</span></span> | <span data-ttu-id="83baf-128">其他資訊</span><span class="sxs-lookup"><span data-stu-id="83baf-128">More information</span></span>
:---|:---|:---|
<span data-ttu-id="83baf-129">管理入口網站</span><span class="sxs-lookup"><span data-stu-id="83baf-129">Administration Portal</span></span> | <span data-ttu-id="83baf-130">Microsoft 365 Defender 入口網站，以監視及協助回應潛在的持續威脅活動或資料違例的警示。</span><span class="sxs-lookup"><span data-stu-id="83baf-130">Microsoft 365 Defender portal to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> | [<span data-ttu-id="83baf-131">Microsoft Defender for Endpoint 入口網站概述</span><span class="sxs-lookup"><span data-stu-id="83baf-131">Microsoft Defender for Endpoint portal overview</span></span>](/defender-endpoint/portal-overview)
<span data-ttu-id="83baf-132">攻擊面減少</span><span class="sxs-lookup"><span data-stu-id="83baf-132">Attack Surface Reduction</span></span> | <span data-ttu-id="83baf-133">將您的組織容易遭受 cyberthreats 和攻擊的位置降到最低，協助減少攻擊面。</span><span class="sxs-lookup"><span data-stu-id="83baf-133">Help reduce your attack surfaces by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> | [<span data-ttu-id="83baf-134">攻擊面縮小概觀</span><span class="sxs-lookup"><span data-stu-id="83baf-134">Overview of attack surface reduction</span></span>](/defender-endpoint/overview-attack-surface-reduction)
<span data-ttu-id="83baf-135">端點偵測和回應</span><span class="sxs-lookup"><span data-stu-id="83baf-135">Endpoint Detection and Response</span></span> | <span data-ttu-id="83baf-136">端點偵測和回應功能提供接近即時及可行動的高級攻擊偵測。</span><span class="sxs-lookup"><span data-stu-id="83baf-136">Endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> | [<span data-ttu-id="83baf-137">端點偵測和回應功能的概覽</span><span class="sxs-lookup"><span data-stu-id="83baf-137">Overview of endpoint detection and response capabilities</span></span>](/defender-endpoint/overview-endpoint-detection-response)
<span data-ttu-id="83baf-138">行為封鎖和包容</span><span class="sxs-lookup"><span data-stu-id="83baf-138">Behavioral Blocking and Containment</span></span> | <span data-ttu-id="83baf-139">行為封鎖和包容功能可在威脅已開始執行時，根據其行為和程式樹，協助識別及停止威脅。</span><span class="sxs-lookup"><span data-stu-id="83baf-139">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> | [<span data-ttu-id="83baf-140">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="83baf-140">Behavioral blocking and containment</span></span>](/defender-endpoint/behavioral-blocking-containment)
<span data-ttu-id="83baf-141">自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="83baf-141">Automated Investigation and Response</span></span> | <span data-ttu-id="83baf-142">自動調查使用各種檢查演算法，取決於安全分析員所使用的處理常式，並設計用來檢查提醒並立即採取動作來解決違規行為。</span><span class="sxs-lookup"><span data-stu-id="83baf-142">Automated investigation uses various inspection algorithms based on processes that are used by security analysts and designed to examine alerts and take immediate action to resolve breaches.</span></span> | [<span data-ttu-id="83baf-143">使用自動調查以調查和修正威脅</span><span class="sxs-lookup"><span data-stu-id="83baf-143">Use automated investigations to investigate and remediate threats</span></span>](/defender-endpoint/automated-investigations)
<span data-ttu-id="83baf-144">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="83baf-144">Advanced Hunting</span></span> | <span data-ttu-id="83baf-145">「高級搜尋」是查詢型威脅搜尋工具，可讓您探索最多30天的原始資料，使您能夠主動檢查網路中的事件，以找出威脅指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="83baf-145">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data so that you can proactively inspect events in your network to locate threat indicators and entities.</span></span> | [<span data-ttu-id="83baf-146">高級搜尋一覽</span><span class="sxs-lookup"><span data-stu-id="83baf-146">Overview of advanced hunting</span></span>](/defender-endpoint/advanced-hunting-overview)
<span data-ttu-id="83baf-147">威脅分析</span><span class="sxs-lookup"><span data-stu-id="83baf-147">Threat Analytics</span></span> | <span data-ttu-id="83baf-148">威脅分析是一組來自專家 Microsoft 安全性研究人員的報表，涵蓋最相關的威脅。</span><span class="sxs-lookup"><span data-stu-id="83baf-148">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats.</span></span> | [<span data-ttu-id="83baf-149">追蹤並回應新興威脅</span><span class="sxs-lookup"><span data-stu-id="83baf-149">Track and respond to emerging threats</span></span>](/defender-endpoint/threat-analytics)


<span data-ttu-id="83baf-150">如需 Microsoft Defender for Endpoint 隨附之功能的詳細資訊，請參閱 [什麼是 Microsoft defender For endpoint](/defender-endpoint/microsoft-defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="83baf-150">For more detailed information about the capabilities included with Microsoft Defender for Endpoint, see [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="83baf-151">SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="83baf-151">SIEM integration</span></span>

<span data-ttu-id="83baf-152">您可以整合 Microsoft Defender for Endpoint with Azure Sentinel，以更全面地分析整個組織的安全性事件，並建立行動行動以取得有效且立即的回應。</span><span class="sxs-lookup"><span data-stu-id="83baf-152">You can integrate Microsoft Defender for Endpoint with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> 

<span data-ttu-id="83baf-153">Microsoft Defender for Endpoint 也可以整合到其他安全性資訊和事件管理 (SIEM) 解決方案。</span><span class="sxs-lookup"><span data-stu-id="83baf-153">Microsoft Defender for Endpoint can also be integrated into other Security Information and Event Management (SIEM) solutions.</span></span> <span data-ttu-id="83baf-154">如需詳細資訊，請參閱 [ENABLE SIEM integration In Microsoft Defender For Endpoint](/defender-endpoint/enable-siem-integration)。</span><span class="sxs-lookup"><span data-stu-id="83baf-154">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span></span>


## <a name="next-steps"></a><span data-ttu-id="83baf-155">後續步驟</span><span class="sxs-lookup"><span data-stu-id="83baf-155">Next steps</span></span>
[<span data-ttu-id="83baf-156">啟用評估</span><span class="sxs-lookup"><span data-stu-id="83baf-156">Enable the evaluation</span></span>](eval-defender-endpoint-enable-eval.md)

<span data-ttu-id="83baf-157">回到概述以 [評估 Microsoft Defender For Endpoint](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="83baf-157">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="83baf-158">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="83baf-158">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>