---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 是一個協同的威脅防護解決方案，其設計目的是為了保護裝置、身分識別、資料和應用程式
keywords: MMicrosoft 365 Defender，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 32defdf459ec65ba0fd268a5a7c84851e9014efa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934042"
---
# <a name="microsoft-365-defender"></a><span data-ttu-id="98887-104">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98887-104">Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="98887-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="98887-105">**Applies to:**</span></span>
- <span data-ttu-id="98887-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98887-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="98887-107">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="98887-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="98887-108">您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="98887-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="98887-109">Microsoft 365 Defender 是一個統一缺口前和缺口後的企業防禦套件，該套件可在本地協調端點、身份、電子郵件和應用程式之間的偵測、預防、調查和回應，以針對複雜攻擊提供完善的保護。</span><span class="sxs-lookup"><span data-stu-id="98887-109">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span>

<span data-ttu-id="98887-110">透過整合的 Microsoft 365 Defender 解決方案，安全性專業人員可以結合每一種產品接收及決定威脅的完整範圍和影響，以結合威脅。如何進入環境、受到影響的內容，以及目前對組織的影響。</span><span class="sxs-lookup"><span data-stu-id="98887-110">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that each of these products receive and determine the full scope and impact of the threat; how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="98887-111">Microsoft 365 Defender 採取自動動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="98887-111">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span>  


<center><h2><span data-ttu-id="98887-112">Microsoft 365 Defender 服務</center></span><span class="sxs-lookup"><span data-stu-id="98887-112">Microsoft 365 Defender services</center></span></span></h2>
<table><tr><td><span data-ttu-id="98887-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></span><span class="sxs-lookup"><span data-stu-id="98887-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></span></span></a></td>
<td><span data-ttu-id="98887-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></span><span class="sxs-lookup"><span data-stu-id="98887-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></span></span></a></td>
<td><span data-ttu-id="98887-115"><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender 身分識別</b></a></center></span><span class="sxs-lookup"><span data-stu-id="98887-115"><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></span></span></td>
<td><span data-ttu-id="98887-116"><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></span><span class="sxs-lookup"><span data-stu-id="98887-116"><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></span></span></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a><span data-ttu-id="98887-117">Microsoft 365 Defender 互動指南</span><span class="sxs-lookup"><span data-stu-id="98887-117">Microsoft 365 Defender interactive guide</span></span>

<span data-ttu-id="98887-118">在此互動指南中，您將瞭解如何使用 Microsoft 365 Defender 保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="98887-118">In this interactive guide, you'll learn how to protect your organization with Microsoft 365 Defender.</span></span> <span data-ttu-id="98887-119">您將會看到 Microsoft 365 Defender 如何協助您偵測安全性風險、調查對您組織的攻擊，並自動避免有害的活動。</span><span class="sxs-lookup"><span data-stu-id="98887-119">You'll see how Microsoft 365 Defender can help you detect security risks, investigate attacks to your organization, and prevent harmful activities automatically.</span></span>

[<span data-ttu-id="98887-120">查看互動指南</span><span class="sxs-lookup"><span data-stu-id="98887-120">Check out the interactive guide</span></span>](https://aka.ms/M365Defender-InteractiveGuide)



<span data-ttu-id="98887-121">Microsoft 365 Defender 套件保護：</span><span class="sxs-lookup"><span data-stu-id="98887-121">Microsoft 365 Defender suite protects:</span></span> 
- <span data-ttu-id="98887-122">**使用 Microsoft defender For endpoint 的端點** -microsoft Defender for endpoint 是一個整合的端點平臺，可提供預防性防護、破壞性偵測、自動調查和回應。</span><span class="sxs-lookup"><span data-stu-id="98887-122">**Endpoints with Microsoft Defender for Endpoint** - Microsoft Defender for Endpoint is a unified endpoint platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> 
- <span data-ttu-id="98887-123">**電子郵件與共同作業與 Microsoft defender For office 365** -office 365 的 defender 針對電子郵件訊息、連結 (URLs) 和共同作業工具帶來的惡意威脅進行保護。</span><span class="sxs-lookup"><span data-stu-id="98887-123">**Email and collaboration with Microsoft Defender for Office 365** - Defender for Office 365 safeguards your organization against malicious threats posed by email messages, links (URLs) and collaboration tools.</span></span> 
- <span data-ttu-id="98887-124">**使用 Microsoft defender 身分識別與 AZURE AD 身分識別保護** 的身分識別： microsoft Defender for Identity 使用 Active Directory 信號來識別、偵測和調查您組織中的高級威脅、已遭破壞的身分識別，以及惡意的內幕程式列動。</span><span class="sxs-lookup"><span data-stu-id="98887-124">**Identities with Microsoft Defender for Identity and Azure AD Identity Protection** - Microsoft Defender for Identity uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> 
- <span data-ttu-id="98887-125">**使用 Microsoft Cloud app security 的應用程式** -Microsoft cloud app security 是一種完整的跨 SaaS 解決方案，對您的雲端應用程式帶來深入的可見度、強資料控制及增強威脅防護。</span><span class="sxs-lookup"><span data-stu-id="98887-125">**Applications with Microsoft Cloud App security** - Microsoft Cloud App security is a comprehensive cross-SaaS solution bringing deep visibility, strong data controls, and enhanced threat protection to your cloud apps.</span></span> 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

<span data-ttu-id="98887-126">Microsoft 365 Defender 獨特的跨產品層將個別套件元件擴充為下列專案：</span><span class="sxs-lookup"><span data-stu-id="98887-126">Microsoft 365 Defender's unique cross-product layer augments the individual suite components to:</span></span>
- <span data-ttu-id="98887-127">協助防範攻擊，並透過信號共用和自動動作協調整個套件的防禦回應</span><span class="sxs-lookup"><span data-stu-id="98887-127">Help protect against attacks and coordinate defensive responses across the suite through signal sharing and automated actions</span></span>
- <span data-ttu-id="98887-128">將提醒上的資料、可疑的事件及受影響的資產加入「事件」，針對安全性小組的產品警示、行為和內容敘述完整的攻擊案例</span><span class="sxs-lookup"><span data-stu-id="98887-128">Narrate the full story of the attack across product alerts, behaviors, and context for security teams by joining data on alerts, suspicious events and impacted assets to 'incidents'</span></span>
- <span data-ttu-id="98887-129">透過自動修復觸發對受影響資產的自我修復，以自動化安全回應</span><span class="sxs-lookup"><span data-stu-id="98887-129">Automate response to compromise by triggering self-healing for impacted assets through automated remediation</span></span>
- <span data-ttu-id="98887-130">讓安全性小組能夠跨端點和 Office 資料執行詳細且有效的威脅搜尋</span><span class="sxs-lookup"><span data-stu-id="98887-130">Enable security teams to perform detailed and effective threat hunting across endpoint and Office data</span></span>

<span data-ttu-id="98887-131">![事件的影像概述頁面](../../media/overview-incident.png)</span><span class="sxs-lookup"><span data-stu-id="98887-131">![Image of incident overview page](../../media/overview-incident.png)</span></span> <br>
<span data-ttu-id="98887-132">跨產品的事件 (綜述) </span><span class="sxs-lookup"><span data-stu-id="98887-132">Cross-product incident (Overview)</span></span>

<span data-ttu-id="98887-133">![警示佇列的影像](../../media/incident-list.png)</span><span class="sxs-lookup"><span data-stu-id="98887-133">![Image of alerts queue](../../media/incident-list.png)</span></span><br>
<span data-ttu-id="98887-134">套件產品間所有相關的警示，與單一事件 (提醒] 查看) </span><span class="sxs-lookup"><span data-stu-id="98887-134">All related alerts across the suite products correlated together into a single incident (alerts view)</span></span>

<span data-ttu-id="98887-135">![事件佇列的影像](../../media/advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="98887-135">![Image of incident queue](../../media/advanced-hunting.png)</span></span><br>
<span data-ttu-id="98887-136">電子郵件和端點原始資料上方的查詢式搜尋</span><span class="sxs-lookup"><span data-stu-id="98887-136">Query-based hunting on top of email and endpoint raw data</span></span>


<span data-ttu-id="98887-137">Microsoft 365 Defender 跨產品功能包括：</span><span class="sxs-lookup"><span data-stu-id="98887-137">Microsoft 365 Defender cross-product features include:</span></span> 
- <span data-ttu-id="98887-138">**跨產品單一窗格的玻璃** -中央視圖所有偵測資訊、受影響資產、自動執行的動作，以及 [security.microsoft.com](https://security.microsoft.com)中單一窗格中的相關證據。</span><span class="sxs-lookup"><span data-stu-id="98887-138">**Cross-product single pane of glass** - Central view all information for detections, impacted assets, automated actions taken, and related evidence in a single queue and a single pane in [security.microsoft.com](https://security.microsoft.com).</span></span> 
- <span data-ttu-id="98887-139">**結合的事件佇列** -若要協助安全性專業人員著重于確保完整攻擊範圍的重要因素，請將受影響的資產和自動修正動作組合在一起，並及時出現。</span><span class="sxs-lookup"><span data-stu-id="98887-139">**Combined incidents queue** - To help security professionals focus on what is critical by ensuring the full attack scope, impacted assets and automated remediation actions are grouped together and surfaced in a timely manner.</span></span> 
- <span data-ttu-id="98887-140">**對威脅的自動回應** -重要威脅資訊可在 Microsoft 365 Defender 產品間即時共用，以協助停止攻擊的產生。</span><span class="sxs-lookup"><span data-stu-id="98887-140">**Automatic response to threats** - Critical threat information is shared in real time between the Microsoft 365 Defender products to help stop the progression of an attack.</span></span> <span data-ttu-id="98887-141">例如，如果在 Microsoft Defender for Endpoint 所保護的端點上偵測到惡意檔案，則會指示 Office 365 的 Defender 可掃描並移除所有電子郵件中的檔案。</span><span class="sxs-lookup"><span data-stu-id="98887-141">For example, if a malicious file is detected on an endpoint protected by Microsoft Defender for Endpoint, it will instruct Defender for Office 365 to scan and remove the file from all e-mail messages.</span></span> <span data-ttu-id="98887-142">整個 Microsoft 365 安全套件會封鎖檔案。</span><span class="sxs-lookup"><span data-stu-id="98887-142">The file will be blocked on sight by the entire Microsoft 365 security suite.</span></span>
- <span data-ttu-id="98887-143">**受到損害的裝置、使用者身分識別及信箱的自我修復** -Microsoft 365 DEFENDER 使用 AI 功能的自動動作和行動裝置，將受影響的資產修正回安全狀態。</span><span class="sxs-lookup"><span data-stu-id="98887-143">**Self-healing for compromised devices, user identities, and mailboxes** - Microsoft 365 Defender uses AI-powered automatic actions and playbooks to remediate impacted assets back to a secure state.</span></span> <span data-ttu-id="98887-144">Microsoft 365 Defender 利用套件產品的自動修正功能，確保與事件相關的所有受影響資產都會在可能的情況下自動修正。</span><span class="sxs-lookup"><span data-stu-id="98887-144">Microsoft 365 Defender leverages automatic remediation capabilities of the suite products to ensure all impacted assets related to an incident are automatically remediated where possible.</span></span>
- <span data-ttu-id="98887-145">**跨產品威脅搜尋** -安全小組可以透過透過各種保護產品所收集的原始資料來建立自己的自訂查詢，利用其獨特的組織知識來尋找損害的跡象。</span><span class="sxs-lookup"><span data-stu-id="98887-145">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries over the raw data collected by the various protection products.</span></span> <span data-ttu-id="98887-146">Microsoft 365 Defender 提供以查詢為基礎的存取權，可對30天的歷史原始信號進行存取，並在端點和 Microsoft Defender for Office 365 資料中提供警示資料。</span><span class="sxs-lookup"><span data-stu-id="98887-146">Microsoft 365 Defender provides query-based access to 30 days of historic raw signals and alert data across endpoint and Microsoft Defender for Office 365 data.</span></span> 


## <a name="get-started"></a><span data-ttu-id="98887-147">快速入門</span><span class="sxs-lookup"><span data-stu-id="98887-147">Get started</span></span>
<span data-ttu-id="98887-148">若要在 Microsoft 365 security center 中啟用服務，必須符合 microsoft 365 Defender 授權需求，才能在 [security.microsoft.com](https://security.microsoft.com)上啟用服務。</span><span class="sxs-lookup"><span data-stu-id="98887-148">Microsoft 365 Defender licensing requirements must be met before you can enable the service in the Microsoft 365 security center at [security.microsoft.com](https://security.microsoft.com).</span></span> <span data-ttu-id="98887-149">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="98887-149">For more information, read:</span></span>
- [<span data-ttu-id="98887-150">授權需求</span><span class="sxs-lookup"><span data-stu-id="98887-150">Licensing requirements</span></span>](prerequisites.md#licensing-requirements)
- [<span data-ttu-id="98887-151">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98887-151">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)


## <a name="see-also"></a><span data-ttu-id="98887-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="98887-152">See also</span></span>
- [<span data-ttu-id="98887-153">跨 Microsoft 365 E5 部署威脅防護功能</span><span class="sxs-lookup"><span data-stu-id="98887-153">Deploy threat protection capabilities across Microsoft 365 E5</span></span>](https://docs.microsoft.com/microsoft-365/solutions/deploy-threat-protection)
