---
title: 將非 Microsoft endpoint protection 切換為 Microsoft Defender for Endpoint
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
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: cff0810a4469d3c2d9ff2fe0fe5100b7a37408ae
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454742"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="18eb2-105">將非 Microsoft endpoint protection 切換為 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="18eb2-105">Make the switch from non-Microsoft endpoint protection to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="18eb2-106">如果您想要將非 Microsoft endpoint protection 解決方案切換至 [Microsoft defender for](microsoft-defender-endpoint.md) Endpoint (Defender for endpoint) ，您就是在正確的位置。</span><span class="sxs-lookup"><span data-stu-id="18eb2-106">If you are thinking about switching from a non-Microsoft endpoint protection solution to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="18eb2-107">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="18eb2-107">Use this article as a guide.</span></span>

:::image type="content" source="images/nonms-mde-migration.png" alt-text="遷移至端點的 Defender 的概覽":::

<span data-ttu-id="18eb2-109">當您將參數設為 Defender for Endpoint 時，您會從使用 active 模式的非 Microsoft 方案開始。</span><span class="sxs-lookup"><span data-stu-id="18eb2-109">When you make the switch to Defender for Endpoint, you begin with your non-Microsoft solution operating in active mode.</span></span> <span data-ttu-id="18eb2-110">然後，以被動模式設定 Defender for Endpoint，並將裝置上架至 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="18eb2-110">Then, you configure Defender for Endpoint in passive mode, and onboard your devices to Defender for Endpoint.</span></span> <span data-ttu-id="18eb2-111">接下來，將 [Defender] 設定為 [使用中模式]。</span><span class="sxs-lookup"><span data-stu-id="18eb2-111">Next, you set Defender for Endpoint to active mode.</span></span> <span data-ttu-id="18eb2-112">最後，您移除非 Microsoft 解決方案。</span><span class="sxs-lookup"><span data-stu-id="18eb2-112">Finally, you remove the non-Microsoft solution.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="18eb2-113">遷移程式</span><span class="sxs-lookup"><span data-stu-id="18eb2-113">The migration process</span></span>

<span data-ttu-id="18eb2-114">將端點遷移至 Defender 的程式可以分為三個階段，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="18eb2-114">The process of migrating to Defender for Endpoint can be divided into three phases, as described in the following table:</span></span>

![遷移階段-準備、安裝、板載](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="18eb2-116">階段</span><span class="sxs-lookup"><span data-stu-id="18eb2-116">Phase</span></span> |<span data-ttu-id="18eb2-117">描述</span><span class="sxs-lookup"><span data-stu-id="18eb2-117">Description</span></span> |
|--|--|
|[<span data-ttu-id="18eb2-118">準備遷移</span><span class="sxs-lookup"><span data-stu-id="18eb2-118">Prepare for your migration</span></span>](switch-to-microsoft-defender-prepare.md) |<span data-ttu-id="18eb2-119">[在 **準備** 階段](switch-to-microsoft-defender-prepare.md)內：</span><span class="sxs-lookup"><span data-stu-id="18eb2-119">During [the **Prepare** phase](switch-to-microsoft-defender-prepare.md):</span></span> <p><span data-ttu-id="18eb2-120">1. 更新您組織的裝置。</span><span class="sxs-lookup"><span data-stu-id="18eb2-120">1. Update your organization's devices.</span></span> <p><span data-ttu-id="18eb2-121">2. 取得適用于端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="18eb2-121">2. Get Defender for Endpoint.</span></span> <p><span data-ttu-id="18eb2-122">3. 規劃您的角色和許可權，並授與 Microsoft 365 Defender 入口網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="18eb2-122">3. Plan your roles and permissions, and grant access to the Microsoft 365 Defender portal.</span></span> <p><span data-ttu-id="18eb2-123">4. 設定您的裝置 proxy 和網際網路設定，以啟用組織裝置和 Defender for Endpoint 之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="18eb2-123">4. Configure your device proxy and internet settings to enable communication between your organization's devices and Defender for Endpoint.</span></span> |
|[<span data-ttu-id="18eb2-124">設定端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="18eb2-124">Set up Defender for Endpoint</span></span>](switch-to-microsoft-defender-setup.md) |<span data-ttu-id="18eb2-125">在 [**安裝** 階段](switch-to-microsoft-defender-setup.md)內：</span><span class="sxs-lookup"><span data-stu-id="18eb2-125">During [the **Setup** phase](switch-to-microsoft-defender-setup.md):</span></span> <p><span data-ttu-id="18eb2-126">1. 啟用/重新安裝 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="18eb2-126">1. Enable/reinstall Microsoft Defender Antivirus.</span></span> <p><span data-ttu-id="18eb2-127">2. 設定用於端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="18eb2-127">2. Configure Defender for Endpoint.</span></span> <p><span data-ttu-id="18eb2-128">3. 將用於端點的 Defender 新增至現有解決方案的排除清單。</span><span class="sxs-lookup"><span data-stu-id="18eb2-128">3. Add Defender for Endpoint to the exclusion list for your existing solution.</span></span> <p><span data-ttu-id="18eb2-129">4. 將現有的解決方案新增至 Microsoft Defender 防毒軟體的排除清單。</span><span class="sxs-lookup"><span data-stu-id="18eb2-129">4. Add your existing solution to the exclusion list for Microsoft Defender Antivirus.</span></span> <p><span data-ttu-id="18eb2-130">5. 設定您的裝置群組、集合及組織單位。</span><span class="sxs-lookup"><span data-stu-id="18eb2-130">5. Set up your device groups, collections, and organizational units.</span></span> <p><span data-ttu-id="18eb2-131">6. 設定反惡意程式碼原則和即時保護設定。</span><span class="sxs-lookup"><span data-stu-id="18eb2-131">6. Configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="18eb2-132">Endpoint to Defender 的板載</span><span class="sxs-lookup"><span data-stu-id="18eb2-132">Onboard to Defender for Endpoint</span></span>](switch-to-microsoft-defender-onboard.md) |<span data-ttu-id="18eb2-133">在 [第 **板** 階段](switch-to-microsoft-defender-onboard.md)期間：</span><span class="sxs-lookup"><span data-stu-id="18eb2-133">During [the **Onboard** phase](switch-to-microsoft-defender-onboard.md):</span></span> <p><span data-ttu-id="18eb2-134">1. 將裝置板載 to Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="18eb2-134">1. Onboard your devices to Defender for Endpoint.</span></span> <p><span data-ttu-id="18eb2-135">2. 執行偵測測試。</span><span class="sxs-lookup"><span data-stu-id="18eb2-135">2. Run a detection test.</span></span> <p><span data-ttu-id="18eb2-136">3. 確認 Microsoft Defender 防毒軟體以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="18eb2-136">3. Confirm that Microsoft Defender Antivirus is running in passive mode.</span></span> <p><span data-ttu-id="18eb2-137">4. 取得 Microsoft Defender 防毒軟體的更新。</span><span class="sxs-lookup"><span data-stu-id="18eb2-137">4. Get updates for Microsoft Defender Antivirus.</span></span> <p><span data-ttu-id="18eb2-138">5. 卸載現有的 endpoint protection 解決方案。</span><span class="sxs-lookup"><span data-stu-id="18eb2-138">5. Uninstall your existing endpoint protection solution.</span></span> <p><span data-ttu-id="18eb2-139">6. 確定 Endpoint for Endpoint 可以正確運作。</span><span class="sxs-lookup"><span data-stu-id="18eb2-139">6. Make sure that Defender for Endpoint working correctly.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="18eb2-140">Microsoft Defender for Endpoint 中包含的內容？</span><span class="sxs-lookup"><span data-stu-id="18eb2-140">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="18eb2-141">在此遷移指南中，我們著重于 [下一代保護](microsoft-defender-antivirus-in-windows-10.md) 和 [端點偵測和回應](overview-endpoint-detection-response.md) 功能，成為移至 Defender for endpoint 的起點。</span><span class="sxs-lookup"><span data-stu-id="18eb2-141">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Defender for Endpoint.</span></span> <span data-ttu-id="18eb2-142">不過，Defender for Endpoint 包含的內容遠遠超過防病毒和 Endpoint protection。</span><span class="sxs-lookup"><span data-stu-id="18eb2-142">However, Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="18eb2-143">Defender for Endpoint 是一種整合的平臺，可提供預防性保護、破壞性偵測、自動調查和回應。</span><span class="sxs-lookup"><span data-stu-id="18eb2-143">Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="18eb2-144">下表摘要的 Defender for Endpoint 中的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="18eb2-144">The following table summarizes features and capabilities in Defender for Endpoint.</span></span> 

| <span data-ttu-id="18eb2-145">功能/功能</span><span class="sxs-lookup"><span data-stu-id="18eb2-145">Feature/Capability</span></span> | <span data-ttu-id="18eb2-146">描述</span><span class="sxs-lookup"><span data-stu-id="18eb2-146">Description</span></span> |
|---|---|
| [<span data-ttu-id="18eb2-147">威脅與漏洞管理</span><span class="sxs-lookup"><span data-stu-id="18eb2-147">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="18eb2-148">威脅 & 弱點管理功能可協助識別、評估和修正整個端點的弱點 (例如裝置) 。</span><span class="sxs-lookup"><span data-stu-id="18eb2-148">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="18eb2-149">攻擊面縮減</span><span class="sxs-lookup"><span data-stu-id="18eb2-149">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="18eb2-150">攻擊面減少規則可協助保護貴組織的裝置和應用程式免受 cyberthreats 和攻擊。</span><span class="sxs-lookup"><span data-stu-id="18eb2-150">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="18eb2-151">新一代保護</span><span class="sxs-lookup"><span data-stu-id="18eb2-151">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="18eb2-152">下一代保護包括可協助封鎖威脅和惡意程式碼的 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="18eb2-152">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="18eb2-153">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="18eb2-153">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="18eb2-154">端點偵測和回應功能偵測、調查和回應入侵嘗試和主動侵犯。</span><span class="sxs-lookup"><span data-stu-id="18eb2-154">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="18eb2-155">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="18eb2-155">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="18eb2-156">高級搜尋功能可讓您的安全性作業小組找到已知或潛在威脅的指標和實體。</span><span class="sxs-lookup"><span data-stu-id="18eb2-156">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="18eb2-157">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="18eb2-157">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="18eb2-158">行為封鎖和包容功能可協助您找出威脅，並根據其行為和程式樹（即使當威脅已開始執行時）加以阻止。</span><span class="sxs-lookup"><span data-stu-id="18eb2-158">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="18eb2-159">自動化調查和修正</span><span class="sxs-lookup"><span data-stu-id="18eb2-159">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="18eb2-160">自動化調查和回應功能會檢查提醒並採取立即修正動作，以解決違規行為。</span><span class="sxs-lookup"><span data-stu-id="18eb2-160">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="18eb2-161">[威脅搜尋服務](microsoft-threat-experts.md) (Microsoft 威脅專家) </span><span class="sxs-lookup"><span data-stu-id="18eb2-161">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="18eb2-162">「威脅搜尋服務」會為安全性運作小組提供專家級的監控和分析，並協助確保重要威脅不會丟失。</span><span class="sxs-lookup"><span data-stu-id="18eb2-162">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="18eb2-163">**想要深入瞭解？請參閱 [適用于 Endpoint 的 Defender](microsoft-defender-endpoint.md)。**</span><span class="sxs-lookup"><span data-stu-id="18eb2-163">**Want to learn more? See [Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="18eb2-164">後續步驟</span><span class="sxs-lookup"><span data-stu-id="18eb2-164">Next step</span></span>

- <span data-ttu-id="18eb2-165">繼續進行 [遷移的準備工作](switch-to-microsoft-defender-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="18eb2-165">Proceed to [Prepare for your migration](switch-to-microsoft-defender-prepare.md).</span></span>
