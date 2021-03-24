---
title: 威脅與弱點管理
description: 這項新功能使用以遊戲為基礎的風險方式，來探索、優先順序和修正端點漏洞與錯誤配置。
keywords: 威脅 & 漏洞管理、威脅和弱點管理、MDATP TVM、MDATP-TVM、弱點管理、弱點評估、威脅和弱點掃描、安全設定評估、microsoft defender atp、microsoft defender atp、端點漏洞、下一代
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: a56b10ec32611a046bffb5ea3c0bfd226c51f8cb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056911"
---
# <a name="threat-and-vulnerability-management"></a><span data-ttu-id="4b489-104">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="4b489-104">Threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4b489-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4b489-105">**Applies to:**</span></span>
- [<span data-ttu-id="4b489-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4b489-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4b489-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b489-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="4b489-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4b489-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4b489-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="4b489-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="4b489-110">有效地識別、評估和修正端點弱點，是在執行健康的安全性計畫及降低組織風險方面 pivotal。</span><span class="sxs-lookup"><span data-stu-id="4b489-110">Effectively identifying, assessing, and remediating endpoint weaknesses is pivotal in running a healthy security program and reducing organizational risk.</span></span> <span data-ttu-id="4b489-111">威脅和弱點管理是一種能降低組織暴露程度、強化端點表面區域，並提高組織彈性的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="4b489-111">Threat and vulnerability management serves as an infrastructure for reducing organizational exposure, hardening endpoint surface area, and increasing organizational resilience.</span></span>

<span data-ttu-id="4b489-112">以感應器即時探索弱點與錯誤配置，而不需要代理程式或定期掃描。</span><span class="sxs-lookup"><span data-stu-id="4b489-112">Discover vulnerabilities and misconfigurations in real time with sensors, and without the need of agents or periodic scans.</span></span> <span data-ttu-id="4b489-113">它會根據威脅情況、組織中的偵測、有缺陷裝置的敏感資訊和商務內容來劃分安全性漏洞。</span><span class="sxs-lookup"><span data-stu-id="4b489-113">It prioritizes vulnerabilities based on the threat landscape, detections in your organization, sensitive information on vulnerable devices, and business context.</span></span>

<span data-ttu-id="4b489-114">觀賞這段影片，以快速流覽威脅及弱點的管理。</span><span class="sxs-lookup"><span data-stu-id="4b489-114">Watch this video for a quick overview of threat and vulnerability management.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a><span data-ttu-id="4b489-115">橋接工作流程缺口</span><span class="sxs-lookup"><span data-stu-id="4b489-115">Bridging the workflow gaps</span></span>

<span data-ttu-id="4b489-116">威脅和弱點管理是內建、即時和雲端電源。</span><span class="sxs-lookup"><span data-stu-id="4b489-116">Threat and vulnerability management is built in, real time, and cloud powered.</span></span> <span data-ttu-id="4b489-117">它會與 Microsoft 端點安全性堆疊、Microsoft 智慧型 Security Graph 及 application analytics 知識庫完全整合。</span><span class="sxs-lookup"><span data-stu-id="4b489-117">It's fully integrated with Microsoft endpoint security stack, the Microsoft Intelligent Security Graph, and the application analytics knowledge base.</span></span>  

<span data-ttu-id="4b489-118">「弱點管理」是業界中的第一個解決方案，可在修正過程中，彌合安全性管理與 IT 系統管理之間的缺口。</span><span class="sxs-lookup"><span data-stu-id="4b489-118">Vulnerability management is the first solution in the industry to bridge the gap between security administration and IT administration during remediation process.</span></span> <span data-ttu-id="4b489-119">與 Microsoft Intune 和 Microsoft 端點 Configuration Manager 整合，以建立安全性工作或票證。</span><span class="sxs-lookup"><span data-stu-id="4b489-119">Create a security task or ticket by integrating with Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span>

### <a name="real-time-discovery"></a><span data-ttu-id="4b489-120">即時探索</span><span class="sxs-lookup"><span data-stu-id="4b489-120">Real-time discovery</span></span>

<span data-ttu-id="4b489-121">若要探索端點漏洞及錯誤配置，威脅和弱點管理會使用相同的無代理程式內建 Defender，以減少繁重的網路掃描和開銷。</span><span class="sxs-lookup"><span data-stu-id="4b489-121">To discover endpoint vulnerabilities and misconfiguration, threat and vulnerability management uses the same agentless built-in Defender for Endpoint sensors to reduce cumbersome network scans and IT overhead.</span></span>

<span data-ttu-id="4b489-122">它還提供：</span><span class="sxs-lookup"><span data-stu-id="4b489-122">It also provides:</span></span>

- <span data-ttu-id="4b489-123">**即時設備清查** -架 to Defender for Endpoint 的裝置會自動向儀表板報告及推入弱點及安全性設定資料。</span><span class="sxs-lookup"><span data-stu-id="4b489-123">**Real-time device inventory** - Devices onboarded to Defender for Endpoint automatically report and push vulnerability and security configuration data to the dashboard.</span></span>
- <span data-ttu-id="4b489-124">深入瞭解 **軟體和弱點**-光學架構中的軟體和弱點，以及軟體變更（如安裝、卸載及修補程式）。</span><span class="sxs-lookup"><span data-stu-id="4b489-124">**Visibility into software and vulnerabilities** - Optics into the organization's software inventory, and software changes like installations, uninstalls, and patches.</span></span> <span data-ttu-id="4b489-125">針對第一個和協力廠商應用程式，會以行動的緩解建議來報告新發現的漏洞。</span><span class="sxs-lookup"><span data-stu-id="4b489-125">Newly discovered vulnerabilities are reported with actionable mitigation recommendations for 1st and 3rd party applications.</span></span>
- <span data-ttu-id="4b489-126">**應用程式執行時間內容** -應用程式使用模式的可見度，以改善優先順序和決策的制定。</span><span class="sxs-lookup"><span data-stu-id="4b489-126">**Application runtime context** - Visibility on application usage patterns for better prioritization and decision-making.</span></span>
- <span data-ttu-id="4b489-127">設定 **狀況**-查看組織的安全性設定或錯誤配置。</span><span class="sxs-lookup"><span data-stu-id="4b489-127">**Configuration posture** - Visibility into organizational security configuration or misconfigurations.</span></span> <span data-ttu-id="4b489-128">會在儀表板中報告問題，並提供切實可行的安全性建議。</span><span class="sxs-lookup"><span data-stu-id="4b489-128">Issues are reported in the dashboard with actionable security recommendations.</span></span>

### <a name="intelligence-driven-prioritization"></a><span data-ttu-id="4b489-129">智慧導向的優先順序</span><span class="sxs-lookup"><span data-stu-id="4b489-129">Intelligence-driven prioritization</span></span>

<span data-ttu-id="4b489-130">威脅和弱點管理可協助客戶設定優先順序，並將重點放在組織面臨最緊迫和最高風險的弱點上。</span><span class="sxs-lookup"><span data-stu-id="4b489-130">Threat and vulnerability management helps customers prioritize and focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="4b489-131">它會 fuses 具有動態威脅及商業內容的安全性建議：</span><span class="sxs-lookup"><span data-stu-id="4b489-131">It fuses security recommendations with dynamic threat and business context:</span></span>

- <span data-ttu-id="4b489-132">**以動態方式公開新興的攻擊，以** 與安全性建議的優先順序對齊。</span><span class="sxs-lookup"><span data-stu-id="4b489-132">**Exposing emerging attacks in the wild** - Dynamically aligns the prioritization of security recommendations.</span></span> <span data-ttu-id="4b489-133">威脅和弱點管理著重于目前正被利用的漏洞，以及帶來最高風險的新興威脅。</span><span class="sxs-lookup"><span data-stu-id="4b489-133">Threat and vulnerability management focuses on vulnerabilities currently being exploited in the wild and emerging threats that pose the highest risk.</span></span>
- <span data-ttu-id="4b489-134">查明作用中的 **違規行為**-關聯威脅和弱點管理和 EDR 真知灼見，以優先處理組織內使用中的非法漏洞所加以利用的漏洞。</span><span class="sxs-lookup"><span data-stu-id="4b489-134">**Pinpointing active breaches** - Correlates threat and vulnerability management and EDR insights to prioritize vulnerabilities being exploited in an active breach within the organization.</span></span>
- <span data-ttu-id="4b489-135">**保護高價值資產** -利用業務關鍵型應用程式、機密資料或高價值的使用者來識別公開的裝置。</span><span class="sxs-lookup"><span data-stu-id="4b489-135">**Protecting high-value assets** - Identify the exposed devices with business-critical applications, confidential data, or high-value users.</span></span>

### <a name="seamless-remediation"></a><span data-ttu-id="4b489-136">無縫修復</span><span class="sxs-lookup"><span data-stu-id="4b489-136">Seamless remediation</span></span>

<span data-ttu-id="4b489-137">威脅和弱點管理可讓安全性管理員和 IT 系統管理員順利合作，以修正問題。</span><span class="sxs-lookup"><span data-stu-id="4b489-137">Threat and vulnerability management allows security administrators and IT administrators to collaborate seamlessly to remediate issues.</span></span>

- <span data-ttu-id="4b489-138">**已傳送的修正要求** -從特定安全性建議在 Microsoft Intune 中建立修復工作。</span><span class="sxs-lookup"><span data-stu-id="4b489-138">**Remediation requests sent to IT** - Create a remediation task in Microsoft Intune from a specific security recommendation.</span></span> <span data-ttu-id="4b489-139">我們打算將此功能擴充為其他 IT 安全性管理平臺。</span><span class="sxs-lookup"><span data-stu-id="4b489-139">We plan to expand this capability to other IT security management platforms.</span></span>
- <span data-ttu-id="4b489-140">**替代的緩解** -深入瞭解其他緩解措施，例如可降低軟體弱點相關風險的設定變更。</span><span class="sxs-lookup"><span data-stu-id="4b489-140">**Alternate mitigations** - Gain insights on additional mitigations, such as configuration changes that can reduce risk associated with software vulnerabilities.</span></span>
- <span data-ttu-id="4b489-141">**即時修復狀態** -即時監控整個組織中的修復活動狀態和進度。</span><span class="sxs-lookup"><span data-stu-id="4b489-141">**Real-time remediation status** - Real-time monitoring of the status and progress of remediation activities across the organization.</span></span>

## <a name="threat-and-vulnerability-management-walk-through"></a><span data-ttu-id="4b489-142">威脅與弱點管理逐步進行</span><span class="sxs-lookup"><span data-stu-id="4b489-142">Threat and vulnerability management walk-through</span></span>

<span data-ttu-id="4b489-143">請觀看這段影片，以瞭解威脅和弱點管理的全面逐步。</span><span class="sxs-lookup"><span data-stu-id="4b489-143">Watch this video for a comprehensive walk-through of threat and vulnerability management.</span></span>

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a><span data-ttu-id="4b489-144">功能窗格 </span><span class="sxs-lookup"><span data-stu-id="4b489-144">Navigation pane</span></span>

<span data-ttu-id="4b489-145">範圍</span><span class="sxs-lookup"><span data-stu-id="4b489-145">Area</span></span> | <span data-ttu-id="4b489-146">描述</span><span class="sxs-lookup"><span data-stu-id="4b489-146">Description</span></span>
:---|:---
<span data-ttu-id="4b489-147">**儀表板**</span><span class="sxs-lookup"><span data-stu-id="4b489-147">**Dashboard**</span></span>   | <span data-ttu-id="4b489-148">取得組織公開分數、Microsoft 安全分數、裝置洩密發佈、主要安全性建議、熱門的軟體、熱門的修復活動，以及主要公開裝置資料的高層次的視圖。</span><span class="sxs-lookup"><span data-stu-id="4b489-148">Get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span>
[<span data-ttu-id="4b489-149">**安全性建議**</span><span class="sxs-lookup"><span data-stu-id="4b489-149">**Security recommendations**</span></span>](tvm-security-recommendation.md) | <span data-ttu-id="4b489-150">請參閱安全性建議和相關威脅資訊的清單。</span><span class="sxs-lookup"><span data-stu-id="4b489-150">See the list of security recommendations and related threat information.</span></span> <span data-ttu-id="4b489-151">當您從清單中選取專案時，會開啟彈出面板，其中包含弱點詳細資料、開啟軟體頁面的連結，以及修正和例外狀況選項。</span><span class="sxs-lookup"><span data-stu-id="4b489-151">When you select an item from the list, a flyout panel opens with vulnerability details, a link to open the software page, and remediation and exception options.</span></span> <span data-ttu-id="4b489-152">如果您的裝置透過 Azure Active Directory 加入，而且您已在 Defender for Endpoint 中啟用 Intune 連線，您也可以在 Intune 中開啟票證。</span><span class="sxs-lookup"><span data-stu-id="4b489-152">You can also open a ticket in Intune if your devices are joined through Azure Active Directory and you've enabled your Intune connections in Defender for Endpoint.</span></span>
[<span data-ttu-id="4b489-153">**修復**</span><span class="sxs-lookup"><span data-stu-id="4b489-153">**Remediation**</span></span>](tvm-remediation.md) | <span data-ttu-id="4b489-154">請參閱您已建立的修復活動和建議的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="4b489-154">See remediation activities you've created and recommendation exceptions.</span></span>
[<span data-ttu-id="4b489-155">**軟體清查**</span><span class="sxs-lookup"><span data-stu-id="4b489-155">**Software inventory**</span></span>](tvm-software-inventory.md) | <span data-ttu-id="4b489-156">查看您組織中有缺陷的軟體清單，以及弱點和威脅資訊。</span><span class="sxs-lookup"><span data-stu-id="4b489-156">See the list of vulnerable software in your organization, along with weakness and threat information.</span></span>
[<span data-ttu-id="4b489-157">**弱點**</span><span class="sxs-lookup"><span data-stu-id="4b489-157">**Weaknesses**</span></span>](tvm-weaknesses.md) | <span data-ttu-id="4b489-158">請參閱您組織中 (Cve) 的常見漏洞與洩密清單。</span><span class="sxs-lookup"><span data-stu-id="4b489-158">See the list of common vulnerabilities and exposures (CVEs) in your organization.</span></span>
[<span data-ttu-id="4b489-159">**事件時程表**</span><span class="sxs-lookup"><span data-stu-id="4b489-159">**Event timeline**</span></span>](threat-and-vuln-mgt-event-timeline.md) | <span data-ttu-id="4b489-160">查看可能影響組織風險的事件。</span><span class="sxs-lookup"><span data-stu-id="4b489-160">View events that may impact your organization's risk.</span></span>

## <a name="apis"></a><span data-ttu-id="4b489-161">API</span><span class="sxs-lookup"><span data-stu-id="4b489-161">APIs</span></span>

<span data-ttu-id="4b489-162">執行威脅與安全性漏洞管理相關 API 通話，以自動化弱點管理工作流程。</span><span class="sxs-lookup"><span data-stu-id="4b489-162">Run threat and vulnerability management-related API calls to automate vulnerability management workflows.</span></span> <span data-ttu-id="4b489-163">若要深入瞭解，請參閱 [Microsoft 技術社區的博客文章](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。</span><span class="sxs-lookup"><span data-stu-id="4b489-163">Learn more from this [Microsoft Tech Community blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).</span></span>

<span data-ttu-id="4b489-164">相關 APIs 請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4b489-164">See the following articles for related APIs:</span></span>

- [<span data-ttu-id="4b489-165">支援的 Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="4b489-165">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="4b489-166">電腦 APIs</span><span class="sxs-lookup"><span data-stu-id="4b489-166">Machine APIs</span></span>](machine.md)
- [<span data-ttu-id="4b489-167">建議 APIs</span><span class="sxs-lookup"><span data-stu-id="4b489-167">Recommendation APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="4b489-168">分數 APIs</span><span class="sxs-lookup"><span data-stu-id="4b489-168">Score APIs</span></span>](score.md)
- [<span data-ttu-id="4b489-169">軟體 APIs</span><span class="sxs-lookup"><span data-stu-id="4b489-169">Software APIs</span></span>](software.md)
- [<span data-ttu-id="4b489-170">弱點 APIs</span><span class="sxs-lookup"><span data-stu-id="4b489-170">Vulnerability APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="4b489-171">依機器及軟體列出弱點</span><span class="sxs-lookup"><span data-stu-id="4b489-171">List vulnerabilities by machine and software</span></span>](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a><span data-ttu-id="4b489-172">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4b489-172">See also</span></span>

- [<span data-ttu-id="4b489-173">支援的作業系統和平臺</span><span class="sxs-lookup"><span data-stu-id="4b489-173">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="4b489-174">威脅與弱點管理儀表板</span><span class="sxs-lookup"><span data-stu-id="4b489-174">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="4b489-175">博客： Microsoft 的威脅 & 弱點管理現在可協助成千上萬的客戶即時探索、優先考慮和修復弱點。</span><span class="sxs-lookup"><span data-stu-id="4b489-175">BLOG: Microsoft's Threat & Vulnerability Management now helps thousands of customers to discover, prioritize, and remediate vulnerabilities in real time</span></span>](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
