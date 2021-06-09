---
title: '威脅防護 (Windows 10) '
description: 適用於端點的 Microsoft Defender 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。
keywords: 威脅防護，Microsoft Defender for Endpoint，攻擊面降低，新一代保護，端點偵測和回應，自動化調查和回應，microsoft 威脅專家，Microsoft 安全評分的裝置，高級搜尋，網路威脅搜尋，網頁威脅防護
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 3db1517d87a47aae254d36cfb28f6c057830ef3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840991"
---
# <a name="threat-protection"></a><span data-ttu-id="7319c-104">威脅防護</span><span class="sxs-lookup"><span data-stu-id="7319c-104">Threat Protection</span></span>
<span data-ttu-id="7319c-105">[適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。</span><span class="sxs-lookup"><span data-stu-id="7319c-105">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="7319c-106">Defender for Endpoint 可保護端點免受網路威脅、偵測高級攻擊和資料違例、自動化安全性事件，以及改善安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="7319c-106">Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>

> [!TIP]
> <span data-ttu-id="7319c-107">讓您的使用者能夠輕鬆存取雲端服務和內部部署應用程式，並為所有裝置啟用新式管理功能。</span><span class="sxs-lookup"><span data-stu-id="7319c-107">Enable your users to access cloud services and on-premises applications with ease and enable modern management capabilities for all devices.</span></span> <span data-ttu-id="7319c-108">如需詳細資訊，請參閱 [保護您的遠端員工](/enterprise-mobility-security/remote-work/)。</span><span class="sxs-lookup"><span data-stu-id="7319c-108">For more information, see [Secure your remote workforce](/enterprise-mobility-security/remote-work/).</span></span> 

<center><h2><span data-ttu-id="7319c-109">Microsoft Defender for Endpoint</center></span><span class="sxs-lookup"><span data-stu-id="7319c-109">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><span data-ttu-id="7319c-110"><b>威脅 & 弱點管理</b></center></a></span><span class="sxs-lookup"><span data-stu-id="7319c-110"><b>Threat & vulnerability management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><span data-ttu-id="7319c-111"><b>攻擊面減少</b></center></a></span><span class="sxs-lookup"><span data-stu-id="7319c-111"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <span data-ttu-id="7319c-112"><b>下一代保護</b></a></center></span><span class="sxs-lookup"><span data-stu-id="7319c-112"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <span data-ttu-id="7319c-113"><b>端點偵測和回應</b></a></center></span><span class="sxs-lookup"><span data-stu-id="7319c-113"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <span data-ttu-id="7319c-114"><b>自動化調查和修正</b></a></center></span><span class="sxs-lookup"><span data-stu-id="7319c-114"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <span data-ttu-id="7319c-115"><b>Microsoft 威脅專家</b></a></center></span><span class="sxs-lookup"><span data-stu-id="7319c-115"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="7319c-116">
<a href="#apis"><center><b>集中式設定和管理、APIs</a></span><span class="sxs-lookup"><span data-stu-id="7319c-116">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="7319c-117"><a href="#mtp"><center><b>Microsoft 365後衛</a></span><span class="sxs-lookup"><span data-stu-id="7319c-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

<span data-ttu-id="7319c-118">**[威脅與漏洞管理](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="7319c-118">**[Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="7319c-119">這項內建的功能使用遊戲變更風險的方法來探索、優先順序和修正端點漏洞及錯誤配置。</span><span class="sxs-lookup"><span data-stu-id="7319c-119">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- [<span data-ttu-id="7319c-120">威脅 & 弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="7319c-120">Threat & vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="7319c-121">開始使用</span><span class="sxs-lookup"><span data-stu-id="7319c-121">Get started</span></span>](tvm-prerequisites.md)
- [<span data-ttu-id="7319c-122">存取您的安全性狀況</span><span class="sxs-lookup"><span data-stu-id="7319c-122">Access your security posture</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="7319c-123">改善您的安全性狀況並降低風險</span><span class="sxs-lookup"><span data-stu-id="7319c-123">Improve your security posture and reduce risk</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="7319c-124">了解您裝置上的弱點</span><span class="sxs-lookup"><span data-stu-id="7319c-124">Understand vulnerabilities on your devices</span></span>](tvm-software-inventory.md)

<a name="asr"></a>

<span data-ttu-id="7319c-125">**[攻擊面縮減](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="7319c-125">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="7319c-126">攻擊面降減功能集可提供堆疊中的第一項防護。</span><span class="sxs-lookup"><span data-stu-id="7319c-126">The attack surface reduction set of capabilities provide the first line of defense in the stack.</span></span> <span data-ttu-id="7319c-127">透過確定設定設定正確，並套用利用緩解技術，這些功能可讓攻擊和利用。</span><span class="sxs-lookup"><span data-stu-id="7319c-127">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

- [<span data-ttu-id="7319c-128">以硬體為基礎的隔離</span><span class="sxs-lookup"><span data-stu-id="7319c-128">Hardware based isolation</span></span>](overview-hardware-based-isolation.md)
- [<span data-ttu-id="7319c-129">應用程式控制</span><span class="sxs-lookup"><span data-stu-id="7319c-129">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [<span data-ttu-id="7319c-130">裝置控制</span><span class="sxs-lookup"><span data-stu-id="7319c-130">Device control</span></span>](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [<span data-ttu-id="7319c-131">入侵防護</span><span class="sxs-lookup"><span data-stu-id="7319c-131">Exploit protection</span></span>](exploit-protection.md)
- <span data-ttu-id="7319c-132">[網路保護](network-protection.md)， [web 保護](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7319c-132">[Network protection](network-protection.md), [web protection](web-protection-overview.md)</span></span>
- [<span data-ttu-id="7319c-133">受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="7319c-133">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="7319c-134">網路防火牆</span><span class="sxs-lookup"><span data-stu-id="7319c-134">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [<span data-ttu-id="7319c-135">受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="7319c-135">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

<a name="ngp"></a>

<span data-ttu-id="7319c-136">**[新一代保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="7319c-136">**[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="7319c-137">若要進一步鞏固網路的安全性周邊，Microsoft Defender for Endpoint 會使用下一代保護，以捕捉所有類型的新威脅。</span><span class="sxs-lookup"><span data-stu-id="7319c-137">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

- [<span data-ttu-id="7319c-138">行為監控</span><span class="sxs-lookup"><span data-stu-id="7319c-138">Behavior monitoring</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="7319c-139">雲端型保護</span><span class="sxs-lookup"><span data-stu-id="7319c-139">Cloud-based protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [<span data-ttu-id="7319c-140">機器學習</span><span class="sxs-lookup"><span data-stu-id="7319c-140">Machine learning</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="7319c-141">URL 保護</span><span class="sxs-lookup"><span data-stu-id="7319c-141">URL Protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [<span data-ttu-id="7319c-142">自動化沙箱服務</span><span class="sxs-lookup"><span data-stu-id="7319c-142">Automated sandbox service</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

<span data-ttu-id="7319c-143">**[端點偵測及回應](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="7319c-143">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="7319c-144">端點偵測和回應功能可就地偵測、調查和回應入侵嘗試和主動違例。</span><span class="sxs-lookup"><span data-stu-id="7319c-144">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span> <span data-ttu-id="7319c-145">使用高級搜尋時，您可以使用查詢型威脅搜尋工具，讓您主動發現違規並建立自訂偵測。</span><span class="sxs-lookup"><span data-stu-id="7319c-145">With Advanced hunting, you have a query-based threat-hunting tool that lets your proactively find breaches and create custom detections.</span></span>

- [<span data-ttu-id="7319c-146">提醒</span><span class="sxs-lookup"><span data-stu-id="7319c-146">Alerts</span></span>](alerts-queue.md)
- [<span data-ttu-id="7319c-147">歷史端點資料</span><span class="sxs-lookup"><span data-stu-id="7319c-147">Historical endpoint data</span></span>](investigate-machines.md#timeline)
- [<span data-ttu-id="7319c-148">回應 orchestration</span><span class="sxs-lookup"><span data-stu-id="7319c-148">Response orchestration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [<span data-ttu-id="7319c-149">鑒證集合</span><span class="sxs-lookup"><span data-stu-id="7319c-149">Forensic collection</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [<span data-ttu-id="7319c-150">威脅情報</span><span class="sxs-lookup"><span data-stu-id="7319c-150">Threat intelligence</span></span>](threat-indicator-concepts.md)
- [<span data-ttu-id="7319c-151">Advanced 引爆及 analysis service</span><span class="sxs-lookup"><span data-stu-id="7319c-151">Advanced detonation and analysis service</span></span>](respond-file-alerts.md#deep-analysis)
- [<span data-ttu-id="7319c-152">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="7319c-152">Advanced hunting</span></span>](advanced-hunting-overview.md)
    - [<span data-ttu-id="7319c-153">自訂偵測</span><span class="sxs-lookup"><span data-stu-id="7319c-153">Custom detections</span></span>](overview-custom-detections.md)

<a name="ai"></a>

<span data-ttu-id="7319c-154">**[自動化調查和修正](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="7319c-154">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="7319c-155">除了快速回應高級攻擊之外，Microsoft Defender for Endpoint 還提供自動調查和修正功能，可協助減少提醒數量，以分鐘為單位的規模。</span><span class="sxs-lookup"><span data-stu-id="7319c-155">In addition to quickly responding to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span>

- [<span data-ttu-id="7319c-156">自動化調查和修正</span><span class="sxs-lookup"><span data-stu-id="7319c-156">Automated investigation and remediation</span></span>](automated-investigations.md)
- [<span data-ttu-id="7319c-157">檢視自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="7319c-157">View details and results of automated investigations</span></span>](auto-investigation-action-center.md)
- [<span data-ttu-id="7319c-158">查看和核准補救動作</span><span class="sxs-lookup"><span data-stu-id="7319c-158">View and approve remediation actions</span></span>](manage-auto-investigation.md)

<a name="mte"></a>

<span data-ttu-id="7319c-159">**[Microsoft 威脅專家](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="7319c-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="7319c-160">Microsoft Defender for Endpoint 的新受管理威脅搜尋服務提供主動的搜尋、優先順序及其他內容和洞察力。</span><span class="sxs-lookup"><span data-stu-id="7319c-160">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights.</span></span> <span data-ttu-id="7319c-161">Microsoft 威脅專家進一步讓安全性運作中心 (SOCs) ，快速且正確地識別及回應威脅。</span><span class="sxs-lookup"><span data-stu-id="7319c-161">Microsoft Threat Experts further empowers Security Operation Centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

- [<span data-ttu-id="7319c-162">目標攻擊通知</span><span class="sxs-lookup"><span data-stu-id="7319c-162">Targeted attack notification</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="7319c-163">專家隨選</span><span class="sxs-lookup"><span data-stu-id="7319c-163">Experts-on-demand</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="7319c-164">設定 Microsoft 365 的 Defender 受管理搜尋服務</span><span class="sxs-lookup"><span data-stu-id="7319c-164">Configure your Microsoft 365 Defender managed hunting service</span></span>](configure-microsoft-threat-experts.md)

<a name="apis"></a>

<span data-ttu-id="7319c-165">**[集中式設定和管理、APIs](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="7319c-165">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="7319c-166">將 Microsoft Defender for 端點整合到現有的工作流程中。</span><span class="sxs-lookup"><span data-stu-id="7319c-166">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>
- [<span data-ttu-id="7319c-167">上線</span><span class="sxs-lookup"><span data-stu-id="7319c-167">Onboarding</span></span>](onboard-configure.md)
- [<span data-ttu-id="7319c-168">API 和 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="7319c-168">API and SIEM integration</span></span>](configure-siem.md)
- [<span data-ttu-id="7319c-169">公開 APIs</span><span class="sxs-lookup"><span data-stu-id="7319c-169">Exposed APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="7319c-170">角色型存取控制 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="7319c-170">Role-based access control (RBAC)</span></span>](rbac.md)
- [<span data-ttu-id="7319c-171">報告和趨勢</span><span class="sxs-lookup"><span data-stu-id="7319c-171">Reporting and trends</span></span>](threat-protection-reports.md)

<a name="integration"></a>
<span data-ttu-id="7319c-172">**[與 Microsoft 解決方案整合](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="7319c-172">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
 <span data-ttu-id="7319c-173">Microsoft Defender for Endpoint 會直接與各種 Microsoft 解決方案整合，包括：</span><span class="sxs-lookup"><span data-stu-id="7319c-173">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="7319c-174">Intune</span><span class="sxs-lookup"><span data-stu-id="7319c-174">Intune</span></span>
- <span data-ttu-id="7319c-175">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7319c-175">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="7319c-176">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7319c-176">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="7319c-177">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="7319c-177">Azure Defender</span></span>
- <span data-ttu-id="7319c-178">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="7319c-178">Skype for Business</span></span>
- <span data-ttu-id="7319c-179">Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="7319c-179">Microsoft Cloud App Security</span></span>

<a name="mtp"></a>
<span data-ttu-id="7319c-180">**[Microsoft 365後衛](/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="7319c-180">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
 <span data-ttu-id="7319c-181">使用 Microsoft 365 defender 時，microsoft defender for Endpoint 和各種 Microsoft security 解決方案會形成共同作業的整合內發佈和入侵後的 enterprise 防護套件，該套件原本會透過端點、身分識別、電子郵件和應用程式整合，以偵測、預防、調查和自動回應複雜的攻擊。</span><span class="sxs-lookup"><span data-stu-id="7319c-181">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>
