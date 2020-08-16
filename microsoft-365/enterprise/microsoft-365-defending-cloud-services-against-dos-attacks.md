---
title: 防禦拒絕服務攻擊的 Microsoft 365 雲端服務
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，您將瞭解 Microsoft 如何抵禦拒絕服務 (DoS) 攻擊的雲服務。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 26c3df54811ffee06797c635bc565fcbe78b58fa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688740"
---
# <a name="defending-microsoft-365-cloud-services-against-denial-of-service-attacks"></a><span data-ttu-id="94b0f-103">防禦拒絕服務攻擊的 Microsoft 365 雲端服務</span><span class="sxs-lookup"><span data-stu-id="94b0f-103">Defending Microsoft 365 cloud services against denial-of-service attacks</span></span>

<span data-ttu-id="94b0f-104">透過縱深防禦安全性保護 Microsoft 資料中心，其中包括周邊防護、影片相機、安全性人員，以及使用生物特徵、智慧卡和多重要素驗證的安全入口。</span><span class="sxs-lookup"><span data-stu-id="94b0f-104">Microsoft datacenters are protected by defense-in-depth security that includes perimeter fencing, video cameras, security personnel, and secure entrances that use biometrics, smartcard, and multi-factor authentication.</span></span> <span data-ttu-id="94b0f-105">縱深防禦安全性會持續透過設施的每個區域和每個實體伺服器單元。</span><span class="sxs-lookup"><span data-stu-id="94b0f-105">The defense-in-depth security continues through every area of the facility and to each physical server unit.</span></span> <span data-ttu-id="94b0f-106">[Microsoft 雲端基礎結構和作業群組](https://www.microsoft.com/cloud-platform/global-datacenters)為雲端服務提供核心基礎結構和基礎技術。</span><span class="sxs-lookup"><span data-stu-id="94b0f-106">The [Microsoft Cloud Infrastructure and Operations Group](https://www.microsoft.com/cloud-platform/global-datacenters) delivers the core infrastructure and foundational technologies for our cloud services.</span></span> <span data-ttu-id="94b0f-107">我們的資料中心遵循實體安全性和可靠性的行業標準，並由 Microsoft 作業人員管理、監視和管理。</span><span class="sxs-lookup"><span data-stu-id="94b0f-107">Our datacenters comply with industry standards for physical security and reliability and are managed, monitored, and administered by Microsoft operations personnel.</span></span>

<span data-ttu-id="94b0f-108">為了進一步保護我們的雲端服務，Microsoft 提供了 DDoS 防護系統，屬於 Microsoft Azure 持續監控和滲透測試程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="94b0f-108">To further protect our cloud services, Microsoft provides a DDoS defense system that is part of the Microsoft Azure continuous monitoring and penetration-testing processes.</span></span> <span data-ttu-id="94b0f-109">Azure DDoS 防護系統的設計不僅能經受外界的攻擊，也不受限於來自其他 Azure 承租人。</span><span class="sxs-lookup"><span data-stu-id="94b0f-109">The Azure DDoS defense system is designed not only to withstand attacks from the outside, but also from other Azure tenants.</span></span> <span data-ttu-id="94b0f-110">Azure 使用標準偵測和緩解技術，例如 SYN cookie、速率限制和連線限制，以防範 DDoS 攻擊。</span><span class="sxs-lookup"><span data-stu-id="94b0f-110">Azure uses standard detection and mitigation techniques such as SYN cookies, rate limiting, and connection limits to protect against DDoS attacks.</span></span>

<span data-ttu-id="94b0f-111">Microsoft 的雲端服務受到來自多個來源的攻擊威脅。</span><span class="sxs-lookup"><span data-stu-id="94b0f-111">Microsoft's cloud services are subject to the threat of attack from multiple sources.</span></span> <span data-ttu-id="94b0f-112">為了緩解和保護不同的 DoS 威脅，已開發高擴充性和動態 Azure 威脅偵測和緩解系統，其主要目標是保護底層基礎結構免受 DoS 攻擊，並協助避免雲端服務客戶的服務中斷。</span><span class="sxs-lookup"><span data-stu-id="94b0f-112">To mitigate and protect against the various DoS threats, a highly-scalable and dynamic Azure-based threat detection and mitigation system have been developed and implemented with the primary objective of protecting the underlying infrastructure from DoS attacks and helping to prevent service interruptions for cloud services customers.</span></span> <span data-ttu-id="94b0f-113">Azure DoS 緩解系統會保護輸入、輸出及地區對區域的流量。</span><span class="sxs-lookup"><span data-stu-id="94b0f-113">The Azure DoS mitigation system protects inbound, outbound, and region-to-region traffic.</span></span>

<span data-ttu-id="94b0f-114">在網路上 (L3) 和傳輸 (L4) DoS 的目標 [互連](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model) (OSI) 模型上，會針對目標發起大多數的攻擊。</span><span class="sxs-lookup"><span data-stu-id="94b0f-114">Most DoS attacks launched against targets at the Network (L3) and Transport (L4) layers of the [Open Systems Interconnection](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model) (OSI) model.</span></span> <span data-ttu-id="94b0f-115">位於 L3 和 L4 層的攻擊是專門用來淹沒網路介面或服務，其攻擊流量會淹沒資源，並拒絕回應合法流量的能力。</span><span class="sxs-lookup"><span data-stu-id="94b0f-115">Attacks directed at the L3 and L4 layers are designed to flood a network interface or service with attack traffic to overwhelm resources and deny the ability to respond to legitimate traffic.</span></span> <span data-ttu-id="94b0f-116">具體而言，L3 和 L4 攻擊會嘗試將網路連結、裝置或服務的容量飽和，或在支援應用程式的伺服器或虛擬機器 CPUs 中不堪重負。</span><span class="sxs-lookup"><span data-stu-id="94b0f-116">Specifically, L3 and L4 attacks attempt to either saturate the capacity of network links, devices, or services or overwhelm the CPUs of servers or virtual machines supporting an application.</span></span>

<span data-ttu-id="94b0f-117">為了防範 L3 和 L4 遭受的攻擊，Microsoft 已設計、開發及部署的解決方案，都是以保護這些層級，以保護受到攻擊的基礎結構和客戶目標。</span><span class="sxs-lookup"><span data-stu-id="94b0f-117">To guard against L3 and L4 attacks Microsoft has designed, developed, and deployed a solution aimed specifically at safeguarding the infrastructure and customer targets that come under attack by protecting these layers.</span></span> <span data-ttu-id="94b0f-118">保護基礎結構可確保針對某位客戶的攻擊流量不會造成其他客戶的宣傳資料損毀或降低網路服務品質。</span><span class="sxs-lookup"><span data-stu-id="94b0f-118">Protecting the infrastructure ensures that attack traffic intended for one customer does not result in collateral damage or diminished network quality of service for other customers.</span></span> <span data-ttu-id="94b0f-119">此解決方案會使用來自資料中心路由器的流量採樣資料。</span><span class="sxs-lookup"><span data-stu-id="94b0f-119">The solution uses traffic sampling data from datacenter routers.</span></span> <span data-ttu-id="94b0f-120">網路監控服務會分析此資料，以偵測攻擊。</span><span class="sxs-lookup"><span data-stu-id="94b0f-120">This data is analyzed by a network monitoring service to detect attacks.</span></span> <span data-ttu-id="94b0f-121">偵測到攻擊時，自動防護機制開始。</span><span class="sxs-lookup"><span data-stu-id="94b0f-121">When an attack is detected, automated defense mechanisms kick in.</span></span>

## <a name="application-level-defenses"></a><span data-ttu-id="94b0f-122">應用層級防護</span><span class="sxs-lookup"><span data-stu-id="94b0f-122">Application-Level Defenses</span></span>
<span data-ttu-id="94b0f-123">Microsoft 工程小組遵循 [Microsoft Operational Security 保障](https://www.microsoft.com/SDL/OperationalSecurityAssurance) 所設定的嚴格標準，協助保護客戶資料。</span><span class="sxs-lookup"><span data-stu-id="94b0f-123">Microsoft engineering teams follow the rigorous standards set by [Microsoft Operational Security Assurance](https://www.microsoft.com/SDL/OperationalSecurityAssurance) to help protect customer data.</span></span> <span data-ttu-id="94b0f-124">Microsoft 的雲端服務是專為支援非常高的負載，以及保護及緩解應用程式層級 DoS 攻擊而進行的。</span><span class="sxs-lookup"><span data-stu-id="94b0f-124">Microsoft's cloud services are intentionally built to support a very high load as well as to protect and mitigate against application-level DoS attacks.</span></span> <span data-ttu-id="94b0f-125">我們已經實施了一種向外延展的架構，其中服務分佈于多部全球資料中心，而某些工作負載中有區域隔離及節流功能。</span><span class="sxs-lookup"><span data-stu-id="94b0f-125">We have implemented a scaled-out architecture where services are distributed across multiple global datacenters with regional isolation and throttling features in some of the workloads.</span></span>

<span data-ttu-id="94b0f-126">客戶所在的國家或地區，客戶的系統管理員會在服務的初始設定中識別該客戶資料的主要儲存位置。</span><span class="sxs-lookup"><span data-stu-id="94b0f-126">Each customer's country or region, which the customer's administrator identifies during the initial setup of the services, determines the primary storage location for that customer's data.</span></span> <span data-ttu-id="94b0f-127">根據主要/備份策略，在重複資料中心之間複製客戶資料。</span><span class="sxs-lookup"><span data-stu-id="94b0f-127">Customer data is replicated between redundant datacenters according to a primary/backup strategy.</span></span> <span data-ttu-id="94b0f-128">主要資料中心會裝載應用程式軟體，以及軟體中所執行的所有主要客戶資料。</span><span class="sxs-lookup"><span data-stu-id="94b0f-128">A primary datacenter hosts the application software along with all the primary customer data running on the software.</span></span> <span data-ttu-id="94b0f-129">備份資料中心提供自動容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="94b0f-129">A backup datacenter provides automatic failover.</span></span> <span data-ttu-id="94b0f-130">如果主要資料中心因任何原因而停止運作，則要求會重新導向到備份資料中心內的軟體和客戶資料的複本。</span><span class="sxs-lookup"><span data-stu-id="94b0f-130">If the primary datacenter ceases to function for any reason, requests are redirected to the copy of the software and customer data in the backup datacenter.</span></span> <span data-ttu-id="94b0f-131">在任何指定的時間，都可能會在主要或備份資料中心處理客戶資料。</span><span class="sxs-lookup"><span data-stu-id="94b0f-131">At any given time, customer data may be processed in either the primary or the backup datacenter.</span></span> <span data-ttu-id="94b0f-132">跨多個資料中心散佈資料，可在一部資料中心遭到攻擊時減少受影響的面範圍。</span><span class="sxs-lookup"><span data-stu-id="94b0f-132">Distributing data across multiple datacenters reduces the affected surface area in case one datacenter is attacked.</span></span> <span data-ttu-id="94b0f-133">此外，受影響的資料中心內的服務可快速重新導向至次要資料中心，成為其中一個復原機制，反之亦然 (重新導向至主要資料中心時) 還原。</span><span class="sxs-lookup"><span data-stu-id="94b0f-133">Furthermore, the services in the affected datacenter can be quickly redirected to the secondary datacenter as one of the recovery mechanisms, and vice versa (redirected back to the primary datacenter once service is restored).</span></span>

<span data-ttu-id="94b0f-134">個別工作負載包括管理資源使用狀況的內建功能。</span><span class="sxs-lookup"><span data-stu-id="94b0f-134">Individual workloads include built-in features that manage resource utilization.</span></span> <span data-ttu-id="94b0f-135">例如，Exchange Online 和 SharePoint Online 中的節流機制都是多種階層式方法，以防禦 DoS 攻擊。</span><span class="sxs-lookup"><span data-stu-id="94b0f-135">For example, the throttling mechanisms in Exchange Online and SharePoint Online are part of a multi-layered approach to defending against DoS attacks.</span></span> <span data-ttu-id="94b0f-136">Exchange Online 使用者的節流是以使用者消耗的資源層級為基礎，不論資源位於 Active Directory、Exchange Online 資訊儲存區，還是其他地方。</span><span class="sxs-lookup"><span data-stu-id="94b0f-136">Throttling for Exchange Online users is based on the level of resources consumed by the end user, whether the resources are in Active Directory, the Exchange Online information store, or elsewhere.</span></span> <span data-ttu-id="94b0f-137">預算會指派給每個用戶端，以限制使用者消耗的資源。</span><span class="sxs-lookup"><span data-stu-id="94b0f-137">A budget is allocated to each client to limit the resources consumed by a user.</span></span> <span data-ttu-id="94b0f-138">使用者活動和系統元件的 Exchange Online 節流是以 [工作負載管理](https://technet.microsoft.com/library/jj150503(v=exchg.150).aspx)為基礎。</span><span class="sxs-lookup"><span data-stu-id="94b0f-138">Exchange Online throttling for user activity and system components is based on [workload management](https://technet.microsoft.com/library/jj150503(v=exchg.150).aspx).</span></span> <span data-ttu-id="94b0f-139">Exchange Online 工作負載是為 Exchange Online 系統資源管理的目的明確定義的 Exchange Online 功能、通訊協定或服務。</span><span class="sxs-lookup"><span data-stu-id="94b0f-139">An Exchange Online workload is an Exchange Online feature, protocol, or service that has been explicitly defined for the purposes of Exchange Online system resource management.</span></span> <span data-ttu-id="94b0f-140">每個 Exchange Online 工作負載都需要諸如 CPU、信箱資料庫操作或 Active Directory 要求等系統資源，以執行使用者要求或背景工作。</span><span class="sxs-lookup"><span data-stu-id="94b0f-140">Each Exchange Online workload requires system resources such as CPU, mailbox database operations, or Active Directory requests to perform user requests or background work.</span></span> <span data-ttu-id="94b0f-141">Exchange Online 工作負載的範例包括網頁型 Outlook、Exchange ActiveSync、信箱遷移和信箱助理。</span><span class="sxs-lookup"><span data-stu-id="94b0f-141">Examples of Exchange Online workloads include Outlook on the web, Exchange ActiveSync, mailbox migration, and mailbox assistants.</span></span> <span data-ttu-id="94b0f-142">租使用者系統管理員可以使用 Exchange 管理命令介面來管理使用者的 Exchange 工作負載管理節流設定。</span><span class="sxs-lookup"><span data-stu-id="94b0f-142">Tenant administrators can manage Exchange workload management throttling settings for users with the Exchange Management Shell.</span></span> <span data-ttu-id="94b0f-143">在 Exchange Online 中實施了多種形式的節流，包括 PowerShell、Exchange Web 服務、POP 和 IMAP、Exchange ActiveSync、行動裝置連線、收件者等等。</span><span class="sxs-lookup"><span data-stu-id="94b0f-143">There are various forms of throttling that have been implemented within Exchange Online, including PowerShell, Exchange Web Services, and POP and IMAP, Exchange ActiveSync, mobile device connections, recipients, and more.</span></span> <span data-ttu-id="94b0f-144">雖然內部部署 Exchange 部署的管理員可以設定節流原則，但系統管理員無法為 Exchange Online 設定節流原則。</span><span class="sxs-lookup"><span data-stu-id="94b0f-144">While administrators of on-premises Exchange deployments can configure throttling policies, Administrators cannot configure throttling policies for Exchange Online.</span></span>

<span data-ttu-id="94b0f-145">在 SharePoint Online 中，最常見的節流限制是用戶端物件模型 (CSOM) 程式碼，乙太高的頻率執行太多動作。</span><span class="sxs-lookup"><span data-stu-id="94b0f-145">The most common trigger for throttling in SharePoint Online is client-side object model (CSOM) code that performs too many actions at too high a frequency.</span></span> <span data-ttu-id="94b0f-146">使用 CSOM 時，可以使用單一要求來執行許多動作，其可超過使用限制，而且會導致個別使用者節流。</span><span class="sxs-lookup"><span data-stu-id="94b0f-146">With CSOM, many actions can be performed with a single request, which can exceed usage limits and cause per-user throttling.</span></span>

<span data-ttu-id="94b0f-147">不論可能導致節流的活動為何，當使用者超過使用限制時，SharePoint 線上會限制來自該使用者帳戶的任何要求，通常是一小段時間。</span><span class="sxs-lookup"><span data-stu-id="94b0f-147">Regardless of the activity that might result in throttling, when a user exceeds usage limits, SharePoint Online throttles any further requests from that user account, usually for a short period.</span></span> <span data-ttu-id="94b0f-148">當使用者節流作用時，使用者的所有動作都會受到節流，直到節流到期為止，依照下列準則：</span><span class="sxs-lookup"><span data-stu-id="94b0f-148">While a user throttle is in effect, all actions by that user are throttled until the throttle expires, according to the following criteria:</span></span>
- <span data-ttu-id="94b0f-149">針對使用者直接在瀏覽器中執行的要求，SharePoint 線上重新導向節流資訊頁面，且要求失敗。</span><span class="sxs-lookup"><span data-stu-id="94b0f-149">For requests performed by the user directly in a browser, SharePoint Online redirects to a throttling information page, and the requests fail.</span></span>
- <span data-ttu-id="94b0f-150">針對所有其他要求（包括 CSOM 呼叫），SharePoint 線上傳回 HTTP 狀態碼 429 ( 「太多要求」 ) ，且要求失敗。</span><span class="sxs-lookup"><span data-stu-id="94b0f-150">For all other requests, including CSOM calls, SharePoint Online returns HTTP status code 429 ("too many requests"), and the requests fail.</span></span>

<span data-ttu-id="94b0f-151">如果有問題的程式繼續超出使用限制，SharePoint 線上可能會完全封鎖處理常式，並傳回 HTTP 狀態碼 503 ( 「服務無法使用」 ) 。</span><span class="sxs-lookup"><span data-stu-id="94b0f-151">If the offending process continues to exceed usage limits, SharePoint Online may completely block the process and return HTTP status code 503 ("service unavailable").</span></span>

## <a name="vulnerability-and-penetration-testing"></a><span data-ttu-id="94b0f-152">弱點和滲透測試</span><span class="sxs-lookup"><span data-stu-id="94b0f-152">Vulnerability and Penetration Testing</span></span>
<span data-ttu-id="94b0f-153">Microsoft 使用許多 [安全性技術和做法](https://www.microsoft.com/trustcenter/security/threatmanagement) ，針對新式的複雜威脅來 [保護其雲端基礎結構](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/) 和內部部署網路，包括使用反惡意軟體元件和服務以進行雲端服務、虛擬機器 (vm) 及其他系統。</span><span class="sxs-lookup"><span data-stu-id="94b0f-153">Microsoft uses many [security technologies and practices](https://www.microsoft.com/trustcenter/security/threatmanagement) to [protect its cloud infrastructure](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/) and on-premises networks against modern, sophisticated threats, including using antimalware components and services for cloud services, virtual machines (VMs), and other systems.</span></span> <span data-ttu-id="94b0f-154">高級威脅分析，它會監控網路、系統和使用者的一般使用模式，並採用機器學習功能來標示出不是一般和一般滲透測試的任何行為。</span><span class="sxs-lookup"><span data-stu-id="94b0f-154">Advanced Threat Analytics, which monitors normal usage patterns for networks, systems, and users, and employs machine learning to flag any behavior that is out of the ordinary, and regular penetration testing.</span></span>

<span data-ttu-id="94b0f-155">除了執行我們自己的滲透測試並為我們的客戶提供 [Microsoft Cloud 整合滲透測試計畫](https://technet.microsoft.com/mt784683)之外，我們也會與協力廠商的安全性專業人員接洽，針對我們的雲端服務執行定期漏洞評估和滲透測試。</span><span class="sxs-lookup"><span data-stu-id="94b0f-155">In addition to performing our own penetration tests and offering to our customers a [Microsoft Cloud Unified Penetration Testing program](https://technet.microsoft.com/mt784683), we also engage with third-party security professionals who perform regular vulnerability assessments of and penetration testing against our cloud services.</span></span> <span data-ttu-id="94b0f-156">我們會從 [服務信任](https://aka.ms/STP) 和 [服務保證](https://aka.ms/ServiceAssurance) 入口網站，將這些協力廠商漏洞評估的報告提供給您。</span><span class="sxs-lookup"><span data-stu-id="94b0f-156">We make the reports from these third-party vulnerability assessments available for download from the [Service Trust](https://aka.ms/STP) and the [Service Assurance](https://aka.ms/ServiceAssurance) portals.</span></span>