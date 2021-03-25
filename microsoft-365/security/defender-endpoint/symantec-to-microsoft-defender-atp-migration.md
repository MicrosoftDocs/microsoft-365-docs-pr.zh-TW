---
title: 從 Symantec 遷移至 Microsoft Defender for Endpoint
description: 深入瞭解如何將從 Symantec 切換至 Microsoft Defender 以供端點使用
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
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: conceptual
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 35f1ce4bccbf2229106ef4b8417a44fe7c37cde5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183702"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="4341e-104">從 Symantec 遷移至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4341e-104">Migrate from Symantec to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="4341e-105">如果您打算從 Symantec Endpoint Protection (Symantec) 切換至 [Microsoft defender For endpoint](https://docs.microsoft.com/windows/security/threat-protection))  (microsoft defender for endpoint，您就是在正確的位置。</span><span class="sxs-lookup"><span data-stu-id="4341e-105">If you are planning to switch from Symantec Endpoint Protection (Symantec) to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="4341e-106">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="4341e-106">Use this article as a guide.</span></span>

<span data-ttu-id="4341e-107">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4341e-107">**Applies to:**</span></span>
- [<span data-ttu-id="4341e-108">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4341e-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4341e-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4341e-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="從 Symantec 遷移至 Defender for Endpoint 的概覽":::

<span data-ttu-id="4341e-111">當您將 Symantec 從 Symantec 移至 Defender for Endpoint 時，您會以主動模式為您的 Symantec 方案，在被動模式中設定 Defender for Endpoint，並將其設定為使用的端點的 defender，然後再將其設定為使用中模式，並移除 Symantec。</span><span class="sxs-lookup"><span data-stu-id="4341e-111">When you make the switch from Symantec to Defender for Endpoint, you begin with your Symantec solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove Symantec.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="4341e-112">遷移程式</span><span class="sxs-lookup"><span data-stu-id="4341e-112">The migration process</span></span>

<span data-ttu-id="4341e-113">當您從 Symantec 切換至 Microsoft Defender for Endpoint 時，您遵循可以分為三個階段的程式，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="4341e-113">When you switch from Symantec to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![遷移階段-準備、安裝、板載](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="4341e-115">階段</span><span class="sxs-lookup"><span data-stu-id="4341e-115">Phase</span></span> |<span data-ttu-id="4341e-116">描述</span><span class="sxs-lookup"><span data-stu-id="4341e-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="4341e-117">準備遷移</span><span class="sxs-lookup"><span data-stu-id="4341e-117">Prepare for your migration</span></span>](symantec-to-microsoft-defender-atp-prepare.md) |<span data-ttu-id="4341e-118">在 [ **準備** ] 階段中，您可以取得 microsoft Defender for Endpoint、規劃您的角色和許可權，以及授與 Microsoft Defender Security Center 的存取權。</span><span class="sxs-lookup"><span data-stu-id="4341e-118">During the **Prepare** phase, you get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="4341e-119">您也可以設定裝置 proxy 和網際網路設定，以啟用組織裝置和 Microsoft Defender for 端點之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="4341e-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="4341e-120">設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4341e-120">Set up Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-setup.md) |<span data-ttu-id="4341e-121">在 **安裝** 階段中，您可以設定 Microsoft Defender 防病毒、microsoft Defender for Endpoint 和 Symantec endpoint Protection 的設定和排除專案。</span><span class="sxs-lookup"><span data-stu-id="4341e-121">During the **Setup** phase, you configure settings and exclusions for Microsoft Defender Antivirus, Microsoft Defender for Endpoint, and Symantec Endpoint Protection.</span></span> <span data-ttu-id="4341e-122">您也可以建立裝置群組、集合及組織單位。</span><span class="sxs-lookup"><span data-stu-id="4341e-122">You also create device groups, collections, and organizational units.</span></span> <span data-ttu-id="4341e-123">最後，您可以設定反惡意程式碼原則和即時保護設定。</span><span class="sxs-lookup"><span data-stu-id="4341e-123">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="4341e-124">在 Microsoft Defender for Endpoint 上的板載</span><span class="sxs-lookup"><span data-stu-id="4341e-124">Onboard to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-onboard.md) |<span data-ttu-id="4341e-125">在第 **板** 階段中，您會將裝置上架至 microsoft Defender for endpoint，並驗證這些裝置是否與 microsoft Defender for endpoint 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="4341e-125">During the **Onboard** phase, you onboard your devices to Microsoft Defender for Endpoint and verify that those devices are communicating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4341e-126">最後，您會卸載 Symantec，並確定透過 Microsoft Defender for Endpoint 來保護成為 active 模式。</span><span class="sxs-lookup"><span data-stu-id="4341e-126">Last, you uninstall Symantec and make sure protection through Microsoft Defender for Endpoint is in active mode.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4341e-127">Microsoft Defender for Endpoint 中包含的內容？</span><span class="sxs-lookup"><span data-stu-id="4341e-127">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="4341e-128">在此遷移指南中，我們著重于 [下一代保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 和 [端點偵測和回應](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 功能，成為移至 Microsoft Defender for endpoint 的起點。</span><span class="sxs-lookup"><span data-stu-id="4341e-128">In this migration guide, we focus on [next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) and [endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4341e-129">不過，Microsoft Defender for Endpoint 包含的內容遠遠超過防病毒和 Endpoint protection。</span><span class="sxs-lookup"><span data-stu-id="4341e-129">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="4341e-130">適用於端點的 Microsoft Defender 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。</span><span class="sxs-lookup"><span data-stu-id="4341e-130">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="4341e-131">下表摘要說明 Microsoft Defender for Endpoint 中的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="4341e-131">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="4341e-132">功能/功能</span><span class="sxs-lookup"><span data-stu-id="4341e-132">Feature/Capability</span></span> | <span data-ttu-id="4341e-133">描述</span><span class="sxs-lookup"><span data-stu-id="4341e-133">Description</span></span> |
|---|---|
| [<span data-ttu-id="4341e-134">威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="4341e-134">Threat & vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | <span data-ttu-id="4341e-135">威脅 & 弱點管理功能可協助識別、評估和修正整個 (端點的弱點，如裝置) 。</span><span class="sxs-lookup"><span data-stu-id="4341e-135">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="4341e-136">受攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="4341e-136">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | <span data-ttu-id="4341e-137">攻擊面減少規則可協助保護貴組織的裝置和應用程式免受 cyberthreats 和攻擊。</span><span class="sxs-lookup"><span data-stu-id="4341e-137">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="4341e-138">下一代保護</span><span class="sxs-lookup"><span data-stu-id="4341e-138">Next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | <span data-ttu-id="4341e-139">下一代保護包括 Microsoft Defender 防毒程式，可協助封鎖威脅和惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="4341e-139">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="4341e-140">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="4341e-140">Endpoint detection and response</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | <span data-ttu-id="4341e-141">端點偵測和回應功能偵測、調查和回應入侵嘗試和主動侵犯。</span><span class="sxs-lookup"><span data-stu-id="4341e-141">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="4341e-142">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="4341e-142">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="4341e-143">高級搜尋功能可讓您的安全性作業小組找到已知或潛在威脅的指標和實體。</span><span class="sxs-lookup"><span data-stu-id="4341e-143">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="4341e-144">行為封鎖和包容</span><span class="sxs-lookup"><span data-stu-id="4341e-144">Behavioral blocking and containment</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | <span data-ttu-id="4341e-145">行為封鎖和包容功能可協助您找出威脅，並根據其行為和程式樹（即使當威脅已開始執行時）加以阻止。</span><span class="sxs-lookup"><span data-stu-id="4341e-145">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="4341e-146">自動化調查與補救措施</span><span class="sxs-lookup"><span data-stu-id="4341e-146">Automated investigation and remediation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | <span data-ttu-id="4341e-147">自動化調查和回應功能會檢查提醒並採取立即修正動作，以解決違規行為。</span><span class="sxs-lookup"><span data-stu-id="4341e-147">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="4341e-148">[威脅搜尋服務](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft 威脅專家) </span><span class="sxs-lookup"><span data-stu-id="4341e-148">[Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="4341e-149">「威脅搜尋服務」會為安全性運作小組提供專家級的監控和分析，並協助確保重要威脅不會丟失。</span><span class="sxs-lookup"><span data-stu-id="4341e-149">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="4341e-150">**想要深入瞭解？請參閱 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection)。**</span><span class="sxs-lookup"><span data-stu-id="4341e-150">**Want to learn more? See [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**</span></span>

## <a name="next-step"></a><span data-ttu-id="4341e-151">下一步</span><span class="sxs-lookup"><span data-stu-id="4341e-151">Next step</span></span>

- <span data-ttu-id="4341e-152">繼續進行 [遷移的準備工作](symantec-to-microsoft-defender-atp-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="4341e-152">Proceed to [Prepare for your migration](symantec-to-microsoft-defender-atp-prepare.md).</span></span>
