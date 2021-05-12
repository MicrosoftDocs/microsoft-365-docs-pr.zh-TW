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
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 0a8e1f11cdb9d7363e6b47d1e671c546e5eac9b4
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327499"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="efb7a-105">將非 Microsoft 端點解決方案切換至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="efb7a-105">Make the switch from a non-Microsoft endpoint solution to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="efb7a-106">如果您打算將非 Microsoft endpoint protection 解決方案切換至 [Microsoft defender for](microsoft-defender-endpoint.md) Endpoint (Defender for endpoint) ，就是正確的位置。</span><span class="sxs-lookup"><span data-stu-id="efb7a-106">If you are planning to switch from a non-Microsoft endpoint protection solution to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="efb7a-107">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="efb7a-107">Use this article as a guide.</span></span>

:::image type="content" source="images/nonms-mde-migration.png" alt-text="遷移至端點的 Defender 的概覽":::

<span data-ttu-id="efb7a-109">當您將參數切換到 Endpoint 時，您會在主動模式中以非 Microsoft 方案開始，在被動模式中設定 Defender for endpoint，並以 endpoint to to Endpoint，然後將 Defender 設定為使用模式，並移除非 Microsoft 解決方案。</span><span class="sxs-lookup"><span data-stu-id="efb7a-109">When you make the switch to Defender for Endpoint, you begin with your non-Microsoft solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove the non-Microsoft solution.</span></span>

> [!TIP]
> - <span data-ttu-id="efb7a-110">如果您目前使用 McAfee 端點安全性 (McAfee) ，請參閱 [從 McAfee 遷移至 Microsoft Defender For Endpoint](mcafee-to-microsoft-defender-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="efb7a-110">If you're currently using McAfee Endpoint Security (McAfee), see [Migrate from McAfee to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).</span></span>
> - <span data-ttu-id="efb7a-111">如果您目前正在使用 Symantec Endpoint Protection (Symantec) ，請參閱 [從 Symantec 遷移至 Microsoft Defender For Endpoint](symantec-to-microsoft-defender-endpoint-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="efb7a-111">If you're currently using Symantec Endpoint Protection (Symantec), see [Migrate from Symantec to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="efb7a-112">遷移程式</span><span class="sxs-lookup"><span data-stu-id="efb7a-112">The migration process</span></span>

<span data-ttu-id="efb7a-113">當您切換至 Microsoft Defender for Endpoint 時，請遵循可以分為三個階段的程式，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="efb7a-113">When you switch to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![遷移階段-準備、安裝、板載](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="efb7a-115">階段</span><span class="sxs-lookup"><span data-stu-id="efb7a-115">Phase</span></span> |<span data-ttu-id="efb7a-116">描述</span><span class="sxs-lookup"><span data-stu-id="efb7a-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="efb7a-117">準備遷移</span><span class="sxs-lookup"><span data-stu-id="efb7a-117">Prepare for your migration</span></span>](switch-to-microsoft-defender-prepare.md) |<span data-ttu-id="efb7a-118">在 [[ **準備** ] 階段](switch-to-microsoft-defender-prepare.md)中，您會更新組織的裝置、取得 microsoft defender 的端點、規劃您的角色和許可權，以及授與 Microsoft Defender Security Center 的存取權。</span><span class="sxs-lookup"><span data-stu-id="efb7a-118">During [the **Prepare** phase](switch-to-microsoft-defender-prepare.md), you update your organization's devices, get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="efb7a-119">您也可以設定裝置 proxy 和網際網路設定，以啟用組織裝置和 Microsoft Defender for 端點之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="efb7a-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="efb7a-120">設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="efb7a-120">Set up Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-setup.md) |<span data-ttu-id="efb7a-121">在 [**安裝** 階段](switch-to-microsoft-defender-setup.md)中，您會啟用 Microsoft Defender 防病毒，並確定它處於被動模式。</span><span class="sxs-lookup"><span data-stu-id="efb7a-121">During [the **Setup** phase](switch-to-microsoft-defender-setup.md), you enable Microsoft Defender Antivirus and make sure it's in passive mode.</span></span> <span data-ttu-id="efb7a-122">您也可以為 Microsoft Defender 防病毒和現有的 endpoint protection 解決方案，設定 & 排除的設定。</span><span class="sxs-lookup"><span data-stu-id="efb7a-122">You also configure settings & exclusions for Microsoft Defender Antivirus and your existing endpoint protection solution.</span></span> <span data-ttu-id="efb7a-123">接著，您會建立裝置群組、集合及組織單位。</span><span class="sxs-lookup"><span data-stu-id="efb7a-123">Then, you create your device groups, collections, and organizational units.</span></span> <span data-ttu-id="efb7a-124">最後，您可以設定反惡意程式碼原則和即時保護設定。</span><span class="sxs-lookup"><span data-stu-id="efb7a-124">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="efb7a-125">在 Microsoft Defender for Endpoint 上的板載</span><span class="sxs-lookup"><span data-stu-id="efb7a-125">Onboard to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-onboard.md) |<span data-ttu-id="efb7a-126">在 [第 **板** 階段](switch-to-microsoft-defender-onboard.md)中，您會將裝置上架至 microsoft defender for endpoint，並驗證這些裝置是否與 microsoft defender for endpoint 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="efb7a-126">During [the **Onboard** phase](switch-to-microsoft-defender-onboard.md), you onboard your devices to Microsoft Defender for Endpoint and verify that those devices are communicating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="efb7a-127">最後，您會卸載現有的 endpoint protection 方案，並確定透過 Microsoft Defender 防毒軟體 & Microsoft Defender for Endpoint 中的保護處於主動模式。</span><span class="sxs-lookup"><span data-stu-id="efb7a-127">Last, you uninstall your existing endpoint protection solution and make sure that protection through Microsoft Defender Antivirus & Microsoft Defender for Endpoint is in active mode.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="efb7a-128">Microsoft Defender for Endpoint 中包含的內容？</span><span class="sxs-lookup"><span data-stu-id="efb7a-128">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="efb7a-129">在此遷移指南中，我們著重于 [下一代保護](microsoft-defender-antivirus-in-windows-10.md) 和 [端點偵測和回應](overview-endpoint-detection-response.md) 功能，成為移至 Microsoft Defender for endpoint 的起點。</span><span class="sxs-lookup"><span data-stu-id="efb7a-129">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="efb7a-130">不過，Microsoft Defender for Endpoint 包含的內容遠遠超過防病毒和 Endpoint protection。</span><span class="sxs-lookup"><span data-stu-id="efb7a-130">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="efb7a-131">適用於端點的 Microsoft Defender 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。</span><span class="sxs-lookup"><span data-stu-id="efb7a-131">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="efb7a-132">下表摘要說明 Microsoft Defender for Endpoint 中的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="efb7a-132">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="efb7a-133">功能/功能</span><span class="sxs-lookup"><span data-stu-id="efb7a-133">Feature/Capability</span></span> | <span data-ttu-id="efb7a-134">描述</span><span class="sxs-lookup"><span data-stu-id="efb7a-134">Description</span></span> |
|---|---|
| [<span data-ttu-id="efb7a-135">威脅與漏洞管理</span><span class="sxs-lookup"><span data-stu-id="efb7a-135">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="efb7a-136">威脅 & 弱點管理功能可協助識別、評估和修正整個 (端點的弱點，如裝置) 。</span><span class="sxs-lookup"><span data-stu-id="efb7a-136">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="efb7a-137">攻擊面縮減</span><span class="sxs-lookup"><span data-stu-id="efb7a-137">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="efb7a-138">攻擊面減少規則可協助保護貴組織的裝置和應用程式免受 cyberthreats 和攻擊。</span><span class="sxs-lookup"><span data-stu-id="efb7a-138">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="efb7a-139">新一代保護</span><span class="sxs-lookup"><span data-stu-id="efb7a-139">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="efb7a-140">下一代保護包括 Microsoft Defender 防毒程式，可協助封鎖威脅和惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="efb7a-140">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="efb7a-141">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="efb7a-141">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="efb7a-142">端點偵測和回應功能偵測、調查和回應入侵嘗試和主動侵犯。</span><span class="sxs-lookup"><span data-stu-id="efb7a-142">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="efb7a-143">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="efb7a-143">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="efb7a-144">高級搜尋功能可讓您的安全性作業小組找到已知或潛在威脅的指標和實體。</span><span class="sxs-lookup"><span data-stu-id="efb7a-144">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="efb7a-145">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="efb7a-145">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="efb7a-146">行為封鎖和包容功能可協助您找出威脅，並根據其行為和程式樹（即使當威脅已開始執行時）加以阻止。</span><span class="sxs-lookup"><span data-stu-id="efb7a-146">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="efb7a-147">自動化調查和修正</span><span class="sxs-lookup"><span data-stu-id="efb7a-147">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="efb7a-148">自動化調查和回應功能會檢查提醒並採取立即修正動作，以解決違規行為。</span><span class="sxs-lookup"><span data-stu-id="efb7a-148">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="efb7a-149">[威脅搜尋服務](microsoft-threat-experts.md) (Microsoft 威脅專家) </span><span class="sxs-lookup"><span data-stu-id="efb7a-149">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="efb7a-150">「威脅搜尋服務」會為安全性運作小組提供專家級的監控和分析，並協助確保重要威脅不會丟失。</span><span class="sxs-lookup"><span data-stu-id="efb7a-150">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="efb7a-151">**想要深入瞭解？請參閱 [Microsoft Defender For Endpoint](microsoft-defender-endpoint.md)。**</span><span class="sxs-lookup"><span data-stu-id="efb7a-151">**Want to learn more? See [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="efb7a-152">下一步</span><span class="sxs-lookup"><span data-stu-id="efb7a-152">Next step</span></span>

- <span data-ttu-id="efb7a-153">繼續進行 [遷移的準備工作](switch-to-microsoft-defender-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="efb7a-153">Proceed to [Prepare for your migration](switch-to-microsoft-defender-prepare.md).</span></span>
