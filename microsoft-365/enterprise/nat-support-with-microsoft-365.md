---
title: Office 365 的 NAT 支援
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: 本文提供如何大致接近您組織中使用 NAT 的每個 IP 位址的用戶端數目的詳細資料。
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688250"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="4d1da-103">Office 365 的 NAT 支援</span><span class="sxs-lookup"><span data-stu-id="4d1da-103">NAT support with Office 365</span></span>

<span data-ttu-id="4d1da-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="4d1da-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4d1da-105">先前，指導方針建議您每個 IP 位址應使用的 Exchange 用戶端數目上限，以連接到 Office 365，每個網路埠大約有2000個用戶端。</span><span class="sxs-lookup"><span data-stu-id="4d1da-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="4d1da-106">為何要使用 NAT？</span><span class="sxs-lookup"><span data-stu-id="4d1da-106">Why use NAT?</span></span>

<span data-ttu-id="4d1da-107">透過使用 NAT，公司網路上的數以千計人員可以「共用」一些可公開路由傳送的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4d1da-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="4d1da-108">大部分公司網路都使用 private (RFC1918) IP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="4d1da-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="4d1da-109">私人位址空間是由網際網路指派的號碼核證機關 (IANA) 所指派，且僅適用于不直接與全球網際網路直接路由傳送的網路。</span><span class="sxs-lookup"><span data-stu-id="4d1da-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="4d1da-110">若要在私人 IP 位址空間上提供對裝置的網際網路存取，組織會使用閘道技術（如防火牆和 proxy），以提供網路位址轉譯 (NAT) 或埠位址轉譯 (PAT) 服務。</span><span class="sxs-lookup"><span data-stu-id="4d1da-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="4d1da-111">這些閘道會使來自內部裝置的流量成為網際網路 (包括 Office 365) 似乎來自一或多個可公開路由傳送的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4d1da-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="4d1da-112">來自內部裝置的每個輸出連線會轉換為公用 IP 位址上的不同來源 TCP 埠。</span><span class="sxs-lookup"><span data-stu-id="4d1da-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="4d1da-113">為什麼您需要讓許多連線同時開啟 Office 365？</span><span class="sxs-lookup"><span data-stu-id="4d1da-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="4d1da-114">在有增益集、共用行事曆、信箱等 ) 情況下，Outlook 可能會開啟八個以上的連線 (。</span><span class="sxs-lookup"><span data-stu-id="4d1da-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="4d1da-115">由於 Windows 的 NAT 裝置上最多可使用64000埠，因此在埠耗盡之前，最多可以有8000個使用者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4d1da-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="4d1da-116">請注意，如果客戶使用的是非 Windows OS 型裝置的 NAT，可用埠總數取決於所使用的 NAT 裝置或軟體。</span><span class="sxs-lookup"><span data-stu-id="4d1da-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="4d1da-117">在此案例中，埠數目上限可能小於64000。</span><span class="sxs-lookup"><span data-stu-id="4d1da-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="4d1da-118">埠的可用性也會受到其他因素（例如 Windows 限制4000埠以供自身使用）的影響，從而減少60000的可用埠總數。</span><span class="sxs-lookup"><span data-stu-id="4d1da-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="4d1da-119">可能有其他應用程式（例如 Internet Explorer）可以同時連接，但需要額外的埠。</span><span class="sxs-lookup"><span data-stu-id="4d1da-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="4d1da-120">使用 Office 365 計算單一公用 IP 位址後支援的裝置數目上限</span><span class="sxs-lookup"><span data-stu-id="4d1da-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="4d1da-121">若要判斷單一公用 IP 位址後裝置的數目上限，您應該監視網路流量，以判斷每個用戶端的流量峰值埠使用量。</span><span class="sxs-lookup"><span data-stu-id="4d1da-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="4d1da-122">此外，埠使用量的峰值因素應該用於 (最少 4) 。</span><span class="sxs-lookup"><span data-stu-id="4d1da-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="4d1da-123">**使用下列公式計算每個 IP 位址支援的裝置數目：**</span><span class="sxs-lookup"><span data-stu-id="4d1da-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="4d1da-124">單一公用 IP 位址後支援的裝置數目上限 = (64000-限制的埠) / (峰值埠使用量 + 峰值因數) </span><span class="sxs-lookup"><span data-stu-id="4d1da-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="4d1da-125">**例如，如果下列條件成立：**</span><span class="sxs-lookup"><span data-stu-id="4d1da-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="4d1da-126">**限制的埠：** 作業系統的4000</span><span class="sxs-lookup"><span data-stu-id="4d1da-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="4d1da-127">**流量峰值埠消耗：** 每台裝置6個</span><span class="sxs-lookup"><span data-stu-id="4d1da-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="4d1da-128">**峰值因素：** 4</span><span class="sxs-lookup"><span data-stu-id="4d1da-128">**Peak factor:** 4</span></span>

<span data-ttu-id="4d1da-129">然後，單一公用 IP 位址後支援的裝置數目上限 = (64000-4000) / (6 + 4) = 6000</span><span class="sxs-lookup"><span data-stu-id="4d1da-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="4d1da-130">使用 Office 365 主控套件發行時，包含在 Microsoft Office Outlook 2007 的9月2011更新，或是 Microsoft Outlook 2010 的11月2011或更新版本，來自 Outlook 的連線數目 (Office Outlook 2007 搭配 Service Pack 2 和 Outlook 2010) 至 Exchange，都可以只是2。</span><span class="sxs-lookup"><span data-stu-id="4d1da-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="4d1da-131">您必須在不同的作業系統、使用者行為等方面加以考慮，以判斷您的網路在高峰時所需的最小和最大端口數目。</span><span class="sxs-lookup"><span data-stu-id="4d1da-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="4d1da-132">如果您想要支援單一公用 IP 位址後的更多裝置，請遵循所述的步驟來評估可支援的裝置數目上限：</span><span class="sxs-lookup"><span data-stu-id="4d1da-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="4d1da-133">監視網路流量，以決定每個用戶端的流量峰值埠使用量。</span><span class="sxs-lookup"><span data-stu-id="4d1da-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="4d1da-134">您應該收集下列資料：</span><span class="sxs-lookup"><span data-stu-id="4d1da-134">You should collect this data:</span></span>
  
- <span data-ttu-id="4d1da-135">從多個位置</span><span class="sxs-lookup"><span data-stu-id="4d1da-135">From multiple locations</span></span>
    
- <span data-ttu-id="4d1da-136">從多個裝置</span><span class="sxs-lookup"><span data-stu-id="4d1da-136">From multiple devices</span></span>
    
- <span data-ttu-id="4d1da-137">在多次</span><span class="sxs-lookup"><span data-stu-id="4d1da-137">At multiple times</span></span>
    
<span data-ttu-id="4d1da-138">使用上述公式，計算其環境中可支援的每個 IP 位址的最大使用者數。</span><span class="sxs-lookup"><span data-stu-id="4d1da-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="4d1da-139">將用戶端負載散佈到其他公用 IP 位址的方法有多種。</span><span class="sxs-lookup"><span data-stu-id="4d1da-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="4d1da-140">可用的策略取決於公司閘道解決方案的功能。</span><span class="sxs-lookup"><span data-stu-id="4d1da-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="4d1da-141">最簡單的解決方法是劃分使用者位址空間，並以靜態方式將多個 IP 位址指派給每個閘道。</span><span class="sxs-lookup"><span data-stu-id="4d1da-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="4d1da-142">許多閘道裝置所提供的另一種方式是使用 IP 位址集區的能力。</span><span class="sxs-lookup"><span data-stu-id="4d1da-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="4d1da-143">位址集區的優點是，在您的使用者群成長時，會有更大的動態，也不需要調整。</span><span class="sxs-lookup"><span data-stu-id="4d1da-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d1da-144">請參閱</span><span class="sxs-lookup"><span data-stu-id="4d1da-144">See also</span></span>

[<span data-ttu-id="4d1da-145">管理 Office 365 端點</span><span class="sxs-lookup"><span data-stu-id="4d1da-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
<span data-ttu-id="4d1da-146">[Office 365 端點常見問題集](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="4d1da-146">[Office 365 endpoints FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)</span></span>
