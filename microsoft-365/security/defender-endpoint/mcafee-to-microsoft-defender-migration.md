---
title: 從 McAfee 遷移至 Microsoft Defender for Endpoint
description: 將 McAfee 切換至 Microsoft Defender for Endpoint。 如需概述，請閱讀本文。
keywords: 遷移、windows defender 高級威脅防護、atp、edr
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
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: f46fb354537b61630172d3d735ce6b24f25ab39a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198830"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="7f7c5-105">從 McAfee 遷移至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7f7c5-105">Migrate from McAfee to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="7f7c5-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7f7c5-106">**Applies to:**</span></span>
- [<span data-ttu-id="7f7c5-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7f7c5-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7f7c5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f7c5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="7f7c5-109">如果您打算從 McAfee 端點安全性 (McAfee) 至 [Microsoft defender For endpoint](https://docs.microsoft.com/windows/security/threat-protection))  (microsoft defender for endpoint，您就是在正確的位置。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-109">If you are planning to switch from McAfee Endpoint Security (McAfee) to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="7f7c5-110">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-110">Use this article as a guide.</span></span>


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="從 McAfee 遷移至 Defender for Endpoint 的概覽":::

<span data-ttu-id="7f7c5-112">當您將 McAfee 的參數切換至 Defender 時，您會從使用中的 McAfee 方案開始，以被動模式設定 Defender，以 [在被動模式中設定 Defender]，並在 [在使用中的電腦上安裝 Defender]，然後將 [Defender] 設定為使用模式並移除 McAfee。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-112">When you make the switch from McAfee to Defender for Endpoint, you begin with your McAfee solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove McAfee.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="7f7c5-113">遷移程式</span><span class="sxs-lookup"><span data-stu-id="7f7c5-113">The migration process</span></span>

<span data-ttu-id="7f7c5-114">當您從 McAfee 切換至 Microsoft Defender for Endpoint 時，您遵循可以分為三個階段的程式： Prepare、Setup 及板載。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-114">When you switch from McAfee to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases: Prepare, Setup, and Onboard.</span></span> 

![遷移階段-準備設定板載](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="7f7c5-116">階段</span><span class="sxs-lookup"><span data-stu-id="7f7c5-116">Phase</span></span> |<span data-ttu-id="7f7c5-117">描述</span><span class="sxs-lookup"><span data-stu-id="7f7c5-117">Description</span></span> |
|--|--|
|[<span data-ttu-id="7f7c5-118">準備遷移</span><span class="sxs-lookup"><span data-stu-id="7f7c5-118">Prepare for your migration</span></span>](mcafee-to-microsoft-defender-prepare.md) |<span data-ttu-id="7f7c5-119">在 [ [**準備**](mcafee-to-microsoft-defender-prepare.md) ] 階段中，您會更新組織的裝置、取得 microsoft Defender 的端點、規劃您的角色和許可權，以及授與 Microsoft Defender Security Center 的存取權。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-119">During the [**Prepare**](mcafee-to-microsoft-defender-prepare.md) phase, you update your organization's devices, get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="7f7c5-120">您也可以設定裝置 proxy 和網際網路設定，以啟用組織裝置和 Microsoft Defender for 端點之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-120">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="7f7c5-121">設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7f7c5-121">Set up Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-setup.md) |<span data-ttu-id="7f7c5-122">在 [**安裝**](mcafee-to-microsoft-defender-setup.md) 階段中，您會啟用 Microsoft Defender 防病毒，並確定其為被動模式，並為 Microsoft Defender 防病毒、microsoft Defender for Endpoint 和 McAfee 設定 & 排除的設定。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-122">During the [**Setup**](mcafee-to-microsoft-defender-setup.md) phase, you enable Microsoft Defender Antivirus and make sure it's in passive mode, and you configure settings & exclusions for Microsoft Defender Antivirus, Microsoft Defender for Endpoint, and McAfee.</span></span> <span data-ttu-id="7f7c5-123">您也可以建立裝置群組、集合及組織單位。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-123">You also create device groups, collections, and organizational units.</span></span> <span data-ttu-id="7f7c5-124">最後，您可以設定反惡意程式碼原則和即時保護設定。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-124">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="7f7c5-125">在 Microsoft Defender for Endpoint 上的板載</span><span class="sxs-lookup"><span data-stu-id="7f7c5-125">Onboard to Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-onboard.md) |<span data-ttu-id="7f7c5-126">在第 [**板**](mcafee-to-microsoft-defender-onboard.md) 階段中，您會將裝置上架至 microsoft Defender for endpoint，並驗證這些裝置是否與 microsoft Defender for endpoint 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-126">During the [**Onboard**](mcafee-to-microsoft-defender-onboard.md) phase, you onboard your devices to Microsoft Defender for Endpoint and verify that those devices are communicating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7f7c5-127">最後，您會卸載 McAfee，並確定透過 Microsoft Defender 防毒軟體 & Microsoft Defender for Endpoint 中的保護處於 active 模式。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-127">Last, you uninstall McAfee and make sure that protection through Microsoft Defender Antivirus & Microsoft Defender for Endpoint is in active mode.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7f7c5-128">Microsoft Defender for Endpoint 中包含的內容？</span><span class="sxs-lookup"><span data-stu-id="7f7c5-128">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="7f7c5-129">在此遷移指南中，我們著重于 [下一代保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 和 [端點偵測和回應](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 功能，成為移至 Microsoft Defender for endpoint 的起點。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-129">In this migration guide, we focus on [next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) and [endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7f7c5-130">不過，Microsoft Defender for Endpoint 包含的內容遠遠超過防病毒和 Endpoint protection。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-130">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="7f7c5-131">適用於端點的 Microsoft Defender 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-131">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="7f7c5-132">下表摘要說明 Microsoft Defender for Endpoint 中的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-132">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="7f7c5-133">功能/功能</span><span class="sxs-lookup"><span data-stu-id="7f7c5-133">Feature/Capability</span></span> | <span data-ttu-id="7f7c5-134">描述</span><span class="sxs-lookup"><span data-stu-id="7f7c5-134">Description</span></span> |
|---|---|
| [<span data-ttu-id="7f7c5-135">威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="7f7c5-135">Threat & vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | <span data-ttu-id="7f7c5-136">威脅 & 弱點管理功能可協助識別、評估和修正整個 (端點的弱點，如裝置) 。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-136">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="7f7c5-137">受攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="7f7c5-137">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | <span data-ttu-id="7f7c5-138">攻擊面減少規則可協助保護貴組織的裝置和應用程式免受 cyberthreats 和攻擊。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-138">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="7f7c5-139">下一代保護</span><span class="sxs-lookup"><span data-stu-id="7f7c5-139">Next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | <span data-ttu-id="7f7c5-140">下一代保護包括 Microsoft Defender 防毒程式，可協助封鎖威脅和惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-140">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="7f7c5-141">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="7f7c5-141">Endpoint detection and response</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | <span data-ttu-id="7f7c5-142">端點偵測和回應功能偵測、調查和回應入侵嘗試和主動侵犯。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-142">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="7f7c5-143">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="7f7c5-143">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="7f7c5-144">高級搜尋功能可讓您的安全性作業小組找到已知或潛在威脅的指標和實體。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-144">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="7f7c5-145">行為封鎖和包容</span><span class="sxs-lookup"><span data-stu-id="7f7c5-145">Behavioral blocking and containment</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | <span data-ttu-id="7f7c5-146">行為封鎖和包容功能可協助您找出威脅，並根據其行為和程式樹（即使當威脅已開始執行時）加以阻止。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-146">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="7f7c5-147">自動化調查與補救措施</span><span class="sxs-lookup"><span data-stu-id="7f7c5-147">Automated investigation and remediation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | <span data-ttu-id="7f7c5-148">自動化調查和回應功能會檢查提醒並採取立即修正動作，以解決違規行為。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-148">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="7f7c5-149">[威脅搜尋服務](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft 威脅專家) </span><span class="sxs-lookup"><span data-stu-id="7f7c5-149">[Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="7f7c5-150">「威脅搜尋服務」會為安全性運作小組提供專家級的監控和分析，並協助確保重要威脅不會丟失。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-150">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="7f7c5-151">**想要深入瞭解？請參閱 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection)。**</span><span class="sxs-lookup"><span data-stu-id="7f7c5-151">**Want to learn more? See [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**</span></span>

## <a name="next-step"></a><span data-ttu-id="7f7c5-152">下一步</span><span class="sxs-lookup"><span data-stu-id="7f7c5-152">Next step</span></span>

- <span data-ttu-id="7f7c5-153">繼續進行 [遷移的準備工作](mcafee-to-microsoft-defender-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="7f7c5-153">Proceed to [Prepare for your migration](mcafee-to-microsoft-defender-prepare.md).</span></span>
