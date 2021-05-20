---
title: 將非 Microsoft 端點解決方案切換至 Microsoft Defender for Endpoint
description: 將參數設為 Microsoft Defender for Endpoint。 如需概述，請閱讀本文。
keywords: 遷移，windows defender advanced endpoint protection，針對端點，edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 013205a1b5b9db204f626a6fe6ab76ad07378558
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538000"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="8fd49-105">將非 Microsoft 端點解決方案切換至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8fd49-105">Make the switch from a non-Microsoft endpoint solution to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="8fd49-106">如果您打算將非 Microsoft endpoint protection 解決方案切換至 [Microsoft defender for](microsoft-defender-endpoint.md) Endpoint (Defender for endpoint) ，就是正確的位置。</span><span class="sxs-lookup"><span data-stu-id="8fd49-106">If you are planning to switch from a non-Microsoft endpoint protection solution to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="8fd49-107">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="8fd49-107">Use this article as a guide.</span></span>

:::image type="content" source="images/nonms-mde-migration.png" alt-text="遷移至端點的 Defender 的概覽":::

<span data-ttu-id="8fd49-109">當您將參數切換到 Endpoint 時，您會在主動模式中以非 Microsoft 方案開始，在被動模式中設定 Defender for endpoint，並以 endpoint to to Endpoint，然後將 Defender 設定為使用模式，並移除非 Microsoft 解決方案。</span><span class="sxs-lookup"><span data-stu-id="8fd49-109">When you make the switch to Defender for Endpoint, you begin with your non-Microsoft solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove the non-Microsoft solution.</span></span>

> [!TIP]
> - <span data-ttu-id="8fd49-110">如果您目前使用 McAfee 端點安全性 (McAfee) ，請參閱 [從 McAfee 遷移至 Defender For Endpoint](mcafee-to-microsoft-defender-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd49-110">If you're currently using McAfee Endpoint Security (McAfee), see [Migrate from McAfee to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).</span></span>
> - <span data-ttu-id="8fd49-111">如果您目前正在使用 symantec Endpoint Protection (symantec) ，請參閱[從 Symantec 遷移至 Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd49-111">If you're currently using Symantec Endpoint Protection (Symantec), see [Migrate from Symantec to Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="8fd49-112">遷移程式</span><span class="sxs-lookup"><span data-stu-id="8fd49-112">The migration process</span></span>

<span data-ttu-id="8fd49-113">當您切換至 Defender for Endpoint 時，請遵循可以分為三個階段的程式，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="8fd49-113">When you switch to Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![遷移階段-準備、安裝、板載](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="8fd49-115">階段</span><span class="sxs-lookup"><span data-stu-id="8fd49-115">Phase</span></span> |<span data-ttu-id="8fd49-116">描述</span><span class="sxs-lookup"><span data-stu-id="8fd49-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="8fd49-117">準備遷移</span><span class="sxs-lookup"><span data-stu-id="8fd49-117">Prepare for your migration</span></span>](switch-to-microsoft-defender-prepare.md) |<span data-ttu-id="8fd49-118">在 [[**準備**] 階段](switch-to-microsoft-defender-prepare.md)中，您會更新組織的裝置、取得「端點的 Defender」、規劃您的角色和許可權，以及授與 Microsoft Defender 資訊安全中心的存取權。</span><span class="sxs-lookup"><span data-stu-id="8fd49-118">During [the **Prepare** phase](switch-to-microsoft-defender-prepare.md), you update your organization's devices, get Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="8fd49-119">您也可以設定裝置 proxy 和網際網路設定，以啟用組織裝置和 Defender for Endpoint 之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="8fd49-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Defender for Endpoint.</span></span> |
|[<span data-ttu-id="8fd49-120">設定端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="8fd49-120">Set up Defender for Endpoint</span></span>](switch-to-microsoft-defender-setup.md) |<span data-ttu-id="8fd49-121">在 [**安裝** 階段](switch-to-microsoft-defender-setup.md)期間，您可以啟用 Microsoft Defender 防毒軟體，並將其設定為被動模式。</span><span class="sxs-lookup"><span data-stu-id="8fd49-121">During [the **Setup** phase](switch-to-microsoft-defender-setup.md), you enable Microsoft Defender Antivirus and set it to passive mode.</span></span> <span data-ttu-id="8fd49-122">您也可以針對 Microsoft Defender 防毒軟體和現有的 endpoint protection 解決方案，設定 & 排除的設定。</span><span class="sxs-lookup"><span data-stu-id="8fd49-122">You also configure settings & exclusions for Microsoft Defender Antivirus and your existing endpoint protection solution.</span></span> <span data-ttu-id="8fd49-123">接著，您會建立裝置群組、集合及組織單位。</span><span class="sxs-lookup"><span data-stu-id="8fd49-123">Then, you create your device groups, collections, and organizational units.</span></span> <span data-ttu-id="8fd49-124">最後，您可以設定反惡意程式碼原則和即時保護設定。</span><span class="sxs-lookup"><span data-stu-id="8fd49-124">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="8fd49-125">Endpoint to Defender 的板載</span><span class="sxs-lookup"><span data-stu-id="8fd49-125">Onboard to Defender for Endpoint</span></span>](switch-to-microsoft-defender-onboard.md) |<span data-ttu-id="8fd49-126">在 [第 **板** 階段](switch-to-microsoft-defender-onboard.md)中，您將裝置上架到 Defender for endpoint，確認 Microsoft Defender 防毒軟體是以被動模式執行，並確認您的端點正在與適用于 Endpoint 的 defender 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8fd49-126">During [the **Onboard** phase](switch-to-microsoft-defender-onboard.md), you onboard your devices to Defender for Endpoint, confirm that Microsoft Defender Antivirus is running in passive mode, and verify that your endpoints are communicating with Defender for Endpoint.</span></span> <span data-ttu-id="8fd49-127">然後，您會卸載現有的 endpoint protection 方案，並確定該 Endpoint for Endpoint 可以正確運作。</span><span class="sxs-lookup"><span data-stu-id="8fd49-127">Then, you uninstall your existing endpoint protection solution and make sure that Defender for Endpoint working correctly.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8fd49-128">Microsoft Defender for Endpoint 中包含的內容？</span><span class="sxs-lookup"><span data-stu-id="8fd49-128">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="8fd49-129">在此遷移指南中，我們著重于 [下一代保護](microsoft-defender-antivirus-in-windows-10.md) 和 [端點偵測和回應](overview-endpoint-detection-response.md) 功能，成為移至 Defender for endpoint 的起點。</span><span class="sxs-lookup"><span data-stu-id="8fd49-129">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Defender for Endpoint.</span></span> <span data-ttu-id="8fd49-130">不過，Defender for Endpoint 包含的內容遠遠超過防病毒和 Endpoint protection。</span><span class="sxs-lookup"><span data-stu-id="8fd49-130">However, Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="8fd49-131">Defender for Endpoint 是一種整合的平臺，可提供預防性保護、破壞性偵測、自動調查和回應。</span><span class="sxs-lookup"><span data-stu-id="8fd49-131">Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="8fd49-132">下表摘要的 Defender for Endpoint 中的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="8fd49-132">The following table summarizes features and capabilities in Defender for Endpoint.</span></span> 

| <span data-ttu-id="8fd49-133">功能/功能</span><span class="sxs-lookup"><span data-stu-id="8fd49-133">Feature/Capability</span></span> | <span data-ttu-id="8fd49-134">描述</span><span class="sxs-lookup"><span data-stu-id="8fd49-134">Description</span></span> |
|---|---|
| [<span data-ttu-id="8fd49-135">威脅與漏洞管理</span><span class="sxs-lookup"><span data-stu-id="8fd49-135">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="8fd49-136">威脅 & 弱點管理功能可協助識別、評估和修正整個端點的弱點 (例如裝置) 。</span><span class="sxs-lookup"><span data-stu-id="8fd49-136">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="8fd49-137">攻擊面縮減</span><span class="sxs-lookup"><span data-stu-id="8fd49-137">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="8fd49-138">攻擊面減少規則可協助保護貴組織的裝置和應用程式免受 cyberthreats 和攻擊。</span><span class="sxs-lookup"><span data-stu-id="8fd49-138">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="8fd49-139">新一代保護</span><span class="sxs-lookup"><span data-stu-id="8fd49-139">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="8fd49-140">下一代保護包括可協助封鎖威脅和惡意程式碼的 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="8fd49-140">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="8fd49-141">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="8fd49-141">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="8fd49-142">端點偵測和回應功能偵測、調查和回應入侵嘗試和主動侵犯。</span><span class="sxs-lookup"><span data-stu-id="8fd49-142">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="8fd49-143">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="8fd49-143">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="8fd49-144">高級搜尋功能可讓您的安全性作業小組找到已知或潛在威脅的指標和實體。</span><span class="sxs-lookup"><span data-stu-id="8fd49-144">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="8fd49-145">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="8fd49-145">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="8fd49-146">行為封鎖和包容功能可協助您找出威脅，並根據其行為和程式樹（即使當威脅已開始執行時）加以阻止。</span><span class="sxs-lookup"><span data-stu-id="8fd49-146">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="8fd49-147">自動化調查和修正</span><span class="sxs-lookup"><span data-stu-id="8fd49-147">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="8fd49-148">自動化調查和回應功能會檢查提醒並採取立即修正動作，以解決違規行為。</span><span class="sxs-lookup"><span data-stu-id="8fd49-148">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="8fd49-149">[威脅搜尋服務](microsoft-threat-experts.md) (Microsoft 威脅專家) </span><span class="sxs-lookup"><span data-stu-id="8fd49-149">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="8fd49-150">「威脅搜尋服務」會為安全性運作小組提供專家級的監控和分析，並協助確保重要威脅不會丟失。</span><span class="sxs-lookup"><span data-stu-id="8fd49-150">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="8fd49-151">**想要深入瞭解？請參閱 [適用于 Endpoint 的 Defender](microsoft-defender-endpoint.md)。**</span><span class="sxs-lookup"><span data-stu-id="8fd49-151">**Want to learn more? See [Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="8fd49-152">下一步</span><span class="sxs-lookup"><span data-stu-id="8fd49-152">Next step</span></span>

- <span data-ttu-id="8fd49-153">繼續進行 [遷移的準備工作](switch-to-microsoft-defender-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd49-153">Proceed to [Prepare for your migration](switch-to-microsoft-defender-prepare.md).</span></span>
