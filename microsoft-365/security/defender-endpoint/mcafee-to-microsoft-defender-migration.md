---
title: 從 McAfee 遷移至 Microsoft Defender for Endpoint
description: 將 McAfee 切換至 Microsoft Defender for Endpoint。 如需概述，請閱讀本文。
keywords: 遷移，Microsoft Defender for Endpoint，edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 5bbcf885ec160204916507aee60398aee35e470b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538048"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="c43ba-105">從 McAfee 遷移至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c43ba-105">Migrate from McAfee to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="c43ba-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c43ba-106">**Applies to:**</span></span>
- [<span data-ttu-id="c43ba-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c43ba-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c43ba-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c43ba-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c43ba-109">如果您打算從 McAfee 端點安全性 (McAfee) 至 [Microsoft defender For endpoint](microsoft-defender-endpoint.md))  (microsoft defender for endpoint，您就是在正確的位置。</span><span class="sxs-lookup"><span data-stu-id="c43ba-109">If you are planning to switch from McAfee Endpoint Security (McAfee) to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Microsoft Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="c43ba-110">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="c43ba-110">Use this article as a guide.</span></span>


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="從 McAfee 遷移至 Defender for Endpoint 的概覽":::

<span data-ttu-id="c43ba-112">當您將 McAfee 的參數切換至 Defender 時，您會從使用中的 McAfee 方案開始，以被動模式設定 Defender，以 [在被動模式中設定 Defender]，並在 [在使用中的電腦上安裝 Defender]，然後將 [Defender] 設定為使用模式並移除 McAfee。</span><span class="sxs-lookup"><span data-stu-id="c43ba-112">When you make the switch from McAfee to Defender for Endpoint, you begin with your McAfee solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove McAfee.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="c43ba-113">遷移程式</span><span class="sxs-lookup"><span data-stu-id="c43ba-113">The migration process</span></span>

<span data-ttu-id="c43ba-114">當您從 McAfee 切換至 Microsoft Defender for Endpoint 時，您遵循可以分為三個階段的程式： Prepare、Setup 及板載。</span><span class="sxs-lookup"><span data-stu-id="c43ba-114">When you switch from McAfee to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases: Prepare, Setup, and Onboard.</span></span> 

![遷移階段-準備設定板載](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="c43ba-116">階段</span><span class="sxs-lookup"><span data-stu-id="c43ba-116">Phase</span></span> |<span data-ttu-id="c43ba-117">描述</span><span class="sxs-lookup"><span data-stu-id="c43ba-117">Description</span></span> |
|--|--|
|[<span data-ttu-id="c43ba-118">準備遷移</span><span class="sxs-lookup"><span data-stu-id="c43ba-118">Prepare for your migration</span></span>](mcafee-to-microsoft-defender-prepare.md) |<span data-ttu-id="c43ba-119">在 [[**準備**](mcafee-to-microsoft-defender-prepare.md)] 階段中，您會更新組織的裝置、取得 Microsoft Defender 的端點、規劃您的角色和許可權，以及授與 Microsoft Defender 資訊安全中心的存取權。</span><span class="sxs-lookup"><span data-stu-id="c43ba-119">During the [**Prepare**](mcafee-to-microsoft-defender-prepare.md) phase, you update your organization's devices, get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="c43ba-120">您也可以設定裝置 proxy 和網際網路設定，以啟用組織裝置和 Microsoft Defender for 端點之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="c43ba-120">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="c43ba-121">設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c43ba-121">Set up Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-setup.md) |<span data-ttu-id="c43ba-122">在 [**安裝**](mcafee-to-microsoft-defender-setup.md)階段期間，您可以啟用 Microsoft Defender 防毒軟體，並將其設定為被動模式。</span><span class="sxs-lookup"><span data-stu-id="c43ba-122">During the [**Setup**](mcafee-to-microsoft-defender-setup.md) phase, you enable Microsoft Defender Antivirus and set it to passive mode.</span></span> <span data-ttu-id="c43ba-123">您也可以針對 Microsoft Defender 防毒軟體和現有的 endpoint protection 解決方案，設定 & 排除的設定。</span><span class="sxs-lookup"><span data-stu-id="c43ba-123">You also configure settings & exclusions for Microsoft Defender Antivirus and your existing endpoint protection solution.</span></span> <span data-ttu-id="c43ba-124">接著，您會建立裝置群組、集合及組織單位。</span><span class="sxs-lookup"><span data-stu-id="c43ba-124">Then, you create your device groups, collections, and organizational units.</span></span> <span data-ttu-id="c43ba-125">最後，您可以設定反惡意程式碼原則和即時保護設定。</span><span class="sxs-lookup"><span data-stu-id="c43ba-125">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="c43ba-126">在 Microsoft Defender for Endpoint 上的板載</span><span class="sxs-lookup"><span data-stu-id="c43ba-126">Onboard to Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-onboard.md) |<span data-ttu-id="c43ba-127">在第 [**板**](mcafee-to-microsoft-defender-onboard.md)階段中，您會將裝置上架至 Microsoft Defender for Endpoint，確認 Microsoft Defender 防毒軟體在被動模式中執行，並確認您的端點正在與使用 Defender for endpoint 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c43ba-127">During the [**Onboard**](mcafee-to-microsoft-defender-onboard.md) phase, you onboard your devices to Microsoft Defender for Endpoint, confirm that Microsoft Defender Antivirus is running in passive mode, and verify that your endpoints are communicating with Defender for Endpoint.</span></span> <span data-ttu-id="c43ba-128">然後，您會卸載 McAfee，並確定 Endpoint for Endpoint 可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="c43ba-128">Then, you uninstall McAfee and make sure that Defender for Endpoint is working correctly.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c43ba-129">Microsoft Defender for Endpoint 中包含的內容？</span><span class="sxs-lookup"><span data-stu-id="c43ba-129">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="c43ba-130">在此遷移指南中，我們著重于 [下一代保護](microsoft-defender-antivirus-in-windows-10.md) 和 [端點偵測和回應](overview-endpoint-detection-response.md) 功能，成為移至 Microsoft Defender for endpoint 的起點。</span><span class="sxs-lookup"><span data-stu-id="c43ba-130">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c43ba-131">不過，Microsoft Defender for Endpoint 包含的內容遠遠超過防病毒和 Endpoint protection。</span><span class="sxs-lookup"><span data-stu-id="c43ba-131">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="c43ba-132">適用於端點的 Microsoft Defender 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。</span><span class="sxs-lookup"><span data-stu-id="c43ba-132">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="c43ba-133">下表摘要說明 Microsoft Defender for Endpoint 中的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="c43ba-133">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="c43ba-134">功能/功能</span><span class="sxs-lookup"><span data-stu-id="c43ba-134">Feature/Capability</span></span> | <span data-ttu-id="c43ba-135">描述</span><span class="sxs-lookup"><span data-stu-id="c43ba-135">Description</span></span> |
|---|---|
| [<span data-ttu-id="c43ba-136">威脅與漏洞管理</span><span class="sxs-lookup"><span data-stu-id="c43ba-136">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="c43ba-137">威脅 & 弱點管理功能可協助識別、評估和修正整個端點的弱點 (例如裝置) 。</span><span class="sxs-lookup"><span data-stu-id="c43ba-137">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="c43ba-138">攻擊面縮減</span><span class="sxs-lookup"><span data-stu-id="c43ba-138">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="c43ba-139">攻擊面減少規則可協助保護貴組織的裝置和應用程式免受 cyberthreats 和攻擊。</span><span class="sxs-lookup"><span data-stu-id="c43ba-139">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="c43ba-140">新一代保護</span><span class="sxs-lookup"><span data-stu-id="c43ba-140">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="c43ba-141">下一代保護包括可協助封鎖威脅和惡意程式碼的 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="c43ba-141">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="c43ba-142">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="c43ba-142">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="c43ba-143">端點偵測和回應功能偵測、調查和回應入侵嘗試和主動侵犯。</span><span class="sxs-lookup"><span data-stu-id="c43ba-143">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="c43ba-144">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="c43ba-144">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="c43ba-145">高級搜尋功能可讓您的安全性作業小組找到已知或潛在威脅的指標和實體。</span><span class="sxs-lookup"><span data-stu-id="c43ba-145">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="c43ba-146">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="c43ba-146">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="c43ba-147">行為封鎖和包容功能可協助您找出威脅，並根據其行為和程式樹（即使當威脅已開始執行時）加以阻止。</span><span class="sxs-lookup"><span data-stu-id="c43ba-147">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="c43ba-148">自動化調查和修正</span><span class="sxs-lookup"><span data-stu-id="c43ba-148">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="c43ba-149">自動化調查和回應功能會檢查提醒並採取立即修正動作，以解決違規行為。</span><span class="sxs-lookup"><span data-stu-id="c43ba-149">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="c43ba-150">[威脅搜尋服務](microsoft-threat-experts.md) (Microsoft 威脅專家) </span><span class="sxs-lookup"><span data-stu-id="c43ba-150">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="c43ba-151">「威脅搜尋服務」會為安全性運作小組提供專家級的監控和分析，並協助確保重要威脅不會丟失。</span><span class="sxs-lookup"><span data-stu-id="c43ba-151">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="c43ba-152">**想要深入瞭解？請參閱 [Microsoft Defender For Endpoint](microsoft-defender-endpoint.md)。**</span><span class="sxs-lookup"><span data-stu-id="c43ba-152">**Want to learn more? See [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="c43ba-153">下一步</span><span class="sxs-lookup"><span data-stu-id="c43ba-153">Next step</span></span>

- <span data-ttu-id="c43ba-154">繼續進行 [遷移的準備工作](mcafee-to-microsoft-defender-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="c43ba-154">Proceed to [Prepare for your migration](mcafee-to-microsoft-defender-prepare.md).</span></span>
