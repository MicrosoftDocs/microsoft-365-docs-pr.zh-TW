---
title: Microsoft 365 中的資料復原
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
description: 在本文中，我們將深入瞭解 Microsoft 365 中的資料恢復功能和復原的設計和原則。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e6ca643fe9842a71102fbabd3c05324ba52b70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688445"
---
# <a name="data-resiliency-in-microsoft-365"></a><span data-ttu-id="14d4f-103">Microsoft 365 中的資料復原</span><span class="sxs-lookup"><span data-stu-id="14d4f-103">Data Resiliency in Microsoft 365</span></span>

<span data-ttu-id="14d4f-104">考慮到雲端計算的複雜性質，Microsoft 很注意，如果發生問題，則不是這樣。</span><span class="sxs-lookup"><span data-stu-id="14d4f-104">Given the complex nature of cloud computing, Microsoft is mindful that it's not a case of if things will go wrong, but rather when.</span></span> <span data-ttu-id="14d4f-105">我們設計雲端服務，以最大化可靠性，並在發生錯誤時將負面影響降至最低。</span><span class="sxs-lookup"><span data-stu-id="14d4f-105">We design our cloud services to maximize reliability and minimize the negative effects on customers when things do go wrong.</span></span> <span data-ttu-id="14d4f-106">我們已超越信賴複雜實體基礎結構的傳統策略，而且我們已直接在雲端服務中建立冗余。</span><span class="sxs-lookup"><span data-stu-id="14d4f-106">We have moved beyond the traditional strategy of relying on complex physical infrastructure, and we have built redundancy directly into our cloud services.</span></span> <span data-ttu-id="14d4f-107">我們採用複雜的實體基礎結構和更多智慧軟體的組合，將資料恢復到我們的服務中，並為我們的客戶提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="14d4f-107">We use a combination of less complex physical infrastructure and more intelligent software that builds data resiliency into our services and delivers high availability to our customers.</span></span> 

## <a name="resiliency-and-recoverability-are-built-in"></a><span data-ttu-id="14d4f-108">恢復功能和可恢復性是內建</span><span class="sxs-lookup"><span data-stu-id="14d4f-108">Resiliency and Recoverability Are Built-in</span></span> 

<span data-ttu-id="14d4f-109">以恢復性和復原的方式開始，假設基礎基礎結構和程式在某些情況下會失敗：硬體 (基礎結構) 會失敗、人工會犯錯誤，軟體也會有錯誤。</span><span class="sxs-lookup"><span data-stu-id="14d4f-109">Building in resiliency and recovery starts with the assumption that the underlying infrastructure and processes will fail at some point: hardware (infrastructure) will fail, humans will make mistakes, and software will have bugs.</span></span> <span data-ttu-id="14d4f-110">雖然軟體發展人員不會考慮到雲端之前未考慮到這些事項，但在典型的 IT 實施中處理這些問題的方式，在雲端之前是非常不同的：</span><span class="sxs-lookup"><span data-stu-id="14d4f-110">While it would be incorrect to say that software developers were not thinking about these things before the cloud, how these issues were handled in a typical IT implementation was very different before the cloud:</span></span>

- <span data-ttu-id="14d4f-111">首先，硬體和基礎結構保護非常重要。</span><span class="sxs-lookup"><span data-stu-id="14d4f-111">First, hardware and infrastructure protections were significant.</span></span> <span data-ttu-id="14d4f-112">這意味著具有99.99% 可靠性的資料中心需要大量的電源和網路冗余，而且伺服器是以硬體型集群、雙電源、雙網路介面，以及類似的方式來執行。</span><span class="sxs-lookup"><span data-stu-id="14d4f-112">This meant having datacenters with 99.99% reliability required significant power and network redundancy, and servers were implemented with hardware-based clustering, dual power supplies, dual network interfaces, and the like.</span></span> 
- <span data-ttu-id="14d4f-113">其次，處理常式是極其重要的。</span><span class="sxs-lookup"><span data-stu-id="14d4f-113">Second, process was paramount.</span></span> <span data-ttu-id="14d4f-114">運作小組維護嚴格的程式、對 windows 的變更所採用的工作，而且經常會產生大量的專案管理工作負載。</span><span class="sxs-lookup"><span data-stu-id="14d4f-114">Operations teams maintained rigorous procedures, change windows were employed, and there was often significant project management overhead.</span></span> 
- <span data-ttu-id="14d4f-115">第三，部署是以 glacial 節奏進行。</span><span class="sxs-lookup"><span data-stu-id="14d4f-115">Third, deployment took place at a glacial pace.</span></span> <span data-ttu-id="14d4f-116">部署不含來源的程式碼表示要等候修補程式版本，主要版本版本則涉及硬體取代和大量的資本 outlay。</span><span class="sxs-lookup"><span data-stu-id="14d4f-116">Deploying code without owning the source meant waiting for patch releases, and major version releases involved hardware replacement and significant capital outlay.</span></span> <span data-ttu-id="14d4f-117">此外，修正問題的唯一方法是回復。</span><span class="sxs-lookup"><span data-stu-id="14d4f-117">Moreover, the only way to correct a problem was to roll back.</span></span> <span data-ttu-id="14d4f-118">因此，大部分的 IT 組織只會部署主要版本，以避免工作保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="14d4f-118">Thus, most IT organizations would deploy only major releases to avoid the work to keep up-to-date.</span></span> 
- <span data-ttu-id="14d4f-119">最後，已部署系統的規模，以及其 interconnectedness 的層級，都比現在更小。</span><span class="sxs-lookup"><span data-stu-id="14d4f-119">Finally, the scale of deployed systems, as well as the level of their interconnectedness was historically much smaller than it is now.</span></span> 

<span data-ttu-id="14d4f-120">目前，客戶預期來自 Microsoft 的連續創新，但不會降低品質，這是 Microsoft 的服務和軟體以恢復性和恢復為基礎而建立的原因之一。</span><span class="sxs-lookup"><span data-stu-id="14d4f-120">Today, customers expect continuous innovation from Microsoft without compromising quality, and this is one of the reasons why Microsoft's services and software are built with resiliency and recoverability in mind.</span></span> 

## <a name="microsoft-365-data-resiliency-principles"></a><span data-ttu-id="14d4f-121">Microsoft 365 資料恢復原則</span><span class="sxs-lookup"><span data-stu-id="14d4f-121">Microsoft 365 Data Resiliency Principles</span></span>

<span data-ttu-id="14d4f-122">恢復性指的是雲端架構服務可經受某些類型的失敗的能力，但在客戶的觀點上仍然能完全運作。</span><span class="sxs-lookup"><span data-stu-id="14d4f-122">Resiliency refers to the ability of a cloud-based service to withstand certain types of failures and yet remain fully-functional from the customers' perspective.</span></span> <span data-ttu-id="14d4f-123">資料恢復意味著不論 Microsoft 365 中發生的失敗為何，重要的客戶資料會保持不變且不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="14d4f-123">Data resiliency means that no matter what failures occur within Microsoft 365, critical customer data remains intact and unaffected.</span></span> <span data-ttu-id="14d4f-124">為做到這一點，Microsoft 365 服務的設計是圍繞五個特定的恢復原則：</span><span class="sxs-lookup"><span data-stu-id="14d4f-124">To that end, Microsoft 365 services have been designed around five specific resiliency principles:</span></span>

- <span data-ttu-id="14d4f-125">有重要且非重要的資料。</span><span class="sxs-lookup"><span data-stu-id="14d4f-125">There is critical and non-critical data.</span></span> <span data-ttu-id="14d4f-126">非重要資料 (例如，郵件是否已讀取) 可以在少見的失敗案例中刪除。</span><span class="sxs-lookup"><span data-stu-id="14d4f-126">Non-critical data (for example, whether a message was read) can be dropped in rare failure scenarios.</span></span> <span data-ttu-id="14d4f-127">重要資料 (例如，客戶資料) （例如電子郵件訊息）應以極高的成本加以保護。</span><span class="sxs-lookup"><span data-stu-id="14d4f-127">Critical data (for example, customer data such as email messages) should be protected at extreme cost.</span></span> <span data-ttu-id="14d4f-128">在設計目標中，傳遞的郵件訊息永遠很重要，也就是郵件已讀取的情況不重要。</span><span class="sxs-lookup"><span data-stu-id="14d4f-128">As a design goal, delivered mail messages are always critical, and things like whether a message has been read is non-critical.</span></span> 
- <span data-ttu-id="14d4f-129">客戶資料的複本必須分割成不同的容錯區域，或盡可能多的容錯網域 (例如，資料中心可透過單一認證進行存取 (程式、伺服器或操作員) # A3，以提供失敗隔離。</span><span class="sxs-lookup"><span data-stu-id="14d4f-129">Copies of customer data must be separated into different fault zones or as many fault domains as possible (e.g., datacenters, accessible by single credentials (process, server, or operator)) to provide failure isolation.</span></span> 
- <span data-ttu-id="14d4f-130">必須監視重要的客戶資料，以失敗任何原子性、一致性、隔離性、耐用性 (ACID) 部分。</span><span class="sxs-lookup"><span data-stu-id="14d4f-130">Critical customer data must be monitored for failing any part of Atomicity, Consistency, Isolation, Durability (ACID).</span></span> 
- <span data-ttu-id="14d4f-131">客戶資料必須受到保護，避免損毀。</span><span class="sxs-lookup"><span data-stu-id="14d4f-131">Customer data must be protected from corruption.</span></span> <span data-ttu-id="14d4f-132">必須主動掃描或監視、修復和恢復。</span><span class="sxs-lookup"><span data-stu-id="14d4f-132">It must be actively scanned or monitored, repairable, and recoverable.</span></span> 
- <span data-ttu-id="14d4f-133">客戶動作中大部分的資料遺失結果，讓客戶可以使用 GUI 自行進行復原，讓他們能夠還原意外刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="14d4f-133">Most data loss results from customer actions, so allow customers to recover on their own using a GUI that enables them to restore accidentally deleted items.</span></span> 
 
<span data-ttu-id="14d4f-134">透過將我們的雲端服務組建至這些原則，並結合可靠的測試和驗證，Microsoft 365 可以符合和超過客戶的需求，同時可確保平臺的持續創新和改進。</span><span class="sxs-lookup"><span data-stu-id="14d4f-134">Through the building of our cloud services to these principles, coupled with robust testing and validation, Microsoft 365 is able to meet and exceed the requirements of customers while ensuring a platform for continuous innovation and improvement.</span></span> 

## <a name="related-links"></a><span data-ttu-id="14d4f-135">相關連結</span><span class="sxs-lookup"><span data-stu-id="14d4f-135">Related Links</span></span>

- [<span data-ttu-id="14d4f-136">處理資料損毀</span><span class="sxs-lookup"><span data-stu-id="14d4f-136">Dealing with Data Corruption</span></span>](microsoft-365-dealing-with-data-corruption.md)
- [<span data-ttu-id="14d4f-137">惡意程式碼與勒索軟體防護</span><span class="sxs-lookup"><span data-stu-id="14d4f-137">Malware and Ransomware Protection</span></span>](microsoft-365-malware-and-ransomware-protection.md)
- [<span data-ttu-id="14d4f-138">監視及自我修復</span><span class="sxs-lookup"><span data-stu-id="14d4f-138">Monitoring and Self-Healing</span></span>](microsoft-365-monitoring-and-self-healing.md)
- [<span data-ttu-id="14d4f-139">Exchange 資料恢復功能</span><span class="sxs-lookup"><span data-stu-id="14d4f-139">Exchange Data Resiliency</span></span>](microsoft-365-exchange-data-resiliency.md)
