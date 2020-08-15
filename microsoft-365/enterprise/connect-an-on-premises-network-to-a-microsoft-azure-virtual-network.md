---
title: 使內部部署網路與 Microsoft Azure 虛擬網路連線
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 81190961-5454-4a5c-8b0e-6ae75b9fb035
description: 摘要：了解如何設定適用於具有站對站 VPN 連線的 Office 伺服器工作負載的跨單位 Azure 虛擬網路。
ms.openlocfilehash: cddb9cfcff02f91ef76f989b87e9dda049cc1b08
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695576"
---
# <a name="connect-an-on-premises-network-to-a-microsoft-azure-virtual-network"></a><span data-ttu-id="a40a4-103">使內部部署網路與 Microsoft Azure 虛擬網路連線</span><span class="sxs-lookup"><span data-stu-id="a40a4-103">Connect an on-premises network to a Microsoft Azure virtual network</span></span>

<span data-ttu-id="a40a4-p101">跨單位 Azure 虛擬網路會與您的內部部署網路連線，藉此擴充您的網路以包含 Azure 基礎架構服務中裝載的子網路和虛擬機器。此連線能讓內部部署網路上的電腦直接存取 Azure 中的虛擬機器，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p101">A cross-premises Azure virtual network is connected to your on-premises network, extending your network to include subnets and virtual machines hosted in Azure infrastructure services. This connection lets computers on your on-premises network to directly access virtual machines in Azure and vice versa.</span></span> 

<span data-ttu-id="a40a4-p102">例如，Azure 虛擬機器上執行的目錄同步處理伺服器必須查詢內部部署網域控制站，以進行帳戶變更，並同步處理這些變更與 Microsoft 365 訂閱。本文說明如何使用可供主控 Azure 虛擬機器的網站對網站的虛擬私人網路 (VPN) 連線，設定跨部署 Azure 虛擬網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p102">For example, a directory synchronization server running on an Azure virtual machine needs to query your on-premises domain controllers for changes to accounts and synchronize those changes with your Microsoft 365 subscription. This article shows you how to set up a cross-premises Azure virtual network using a site-to-site virtual private network (VPN) connection that is ready to host Azure virtual machines.</span></span>

## <a name="configure-a-cross-premises-azure-virtual-network"></a><span data-ttu-id="a40a4-108">設定跨部署 Azure 虛擬網路</span><span class="sxs-lookup"><span data-stu-id="a40a4-108">Configure a cross-premises Azure virtual network</span></span>

<span data-ttu-id="a40a4-p103">Azure 中的虛擬機器無須與您的內部部署環境隔離。若要讓 Azure 虛擬機器與內部部署網路資源連線，您必須設定跨單位 Azure 虛擬網路。下列圖表顯示當 Azure 中有一部虛擬機器時，部署跨單位 Azure 虛擬網路所需要的元件。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p103">Your virtual machines in Azure don't have to be isolated from your on-premises environment. To connect Azure virtual machines to your on-premises network resources, you must configure a cross-premises Azure virtual network. The following diagram shows the required components to deploy a cross-premises Azure virtual network with a virtual machine in Azure.</span></span>
  
![內部部署網路已透過站對站 VPN 連線連線到 Microsoft Azure](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
 
<span data-ttu-id="a40a4-p104">在圖表中，有兩個網路透過站對站 VPN 連線來連線：內部部署網路和 Azure 虛擬網路。站對站 VPN 連線是：</span><span class="sxs-lookup"><span data-stu-id="a40a4-p104">In the diagram, there are two networks connected by a site-to-site VPN connection: the on-premises network and the Azure virtual network. The site-to-site VPN connection is:</span></span>

- <span data-ttu-id="a40a4-115">介於可定址且位於公用網際網路上位置的兩個端點之間。</span><span class="sxs-lookup"><span data-stu-id="a40a4-115">Between two endpoints that are addressable and located on the public Internet.</span></span>
- <span data-ttu-id="a40a4-116">由內部部署網路上的 VPN 裝置和 Azure 虛擬網路上的 Azure VPN 閘道加以終止。</span><span class="sxs-lookup"><span data-stu-id="a40a4-116">Terminated by a VPN device on the on-premises network and an Azure VPN gateway on the Azure virtual network.</span></span>

<span data-ttu-id="a40a4-p105">Azure 虛擬網路會裝載虛擬機器。Azure 虛擬網路上虛擬機器所產生的網路流量會轉送至 VPN 閘道，然後會將站對站 VPN 連線的流量轉送至內部部署網路上的 VPN 裝置。然後內部部署網路的路由基礎結構會將流量轉送至其目的地。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p105">The Azure virtual network hosts virtual machines. Network traffic originating from virtual machines on the Azure virtual network gets forwarded to the VPN gateway, which then forwards the traffic across the site-to-site VPN connection to the VPN device on the on-premises network. The routing infrastructure of the on-premises network then forwards the traffic to its destination.</span></span>

>[!Note]
><span data-ttu-id="a40a4-p106">您也可以使用 [ExpressRoute](https://azure.microsoft.com/services/expressroute/)，這是您的組織與 Microsoft 網路之間的直接連線。ExpressRoute 的流量不會在公用網際網路上流動。這篇文章不會說明 ExpressRoute 的使用方式。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p106">You can also use [ExpressRoute](https://azure.microsoft.com/services/expressroute/), which is a direct connection between your organization and Microsoft's network. Traffic over ExpressRoute does not travel over the public Internet. This article does not describe the use of ExpressRoute.</span></span>
>
  
<span data-ttu-id="a40a4-123">若要設定 Azure 虛擬網路和內部部署網路間的 VPN 連線，請執行下列步驟︰</span><span class="sxs-lookup"><span data-stu-id="a40a4-123">To set up the VPN connection between your Azure virtual network and your on-premises network, follow these steps:</span></span> 
  
1. <span data-ttu-id="a40a4-124">**內部部署：** 針對指向您內部部署 VPN 裝置的 Azure 虛擬網路位址空間，定義和建立內部部署網路路由。</span><span class="sxs-lookup"><span data-stu-id="a40a4-124">**On-premises:** Define and create an on-premises network route for the address space of the Azure virtual network that points to your on-premises VPN device.</span></span>
    
2. <span data-ttu-id="a40a4-125">**Microsoft Azure：** 建立具備站對站 VPN 連線的 Azure 虛擬網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-125">**Microsoft Azure:** Create an Azure virtual network with a site-to-site VPN connection.</span></span> 
    
3. <span data-ttu-id="a40a4-126">**內部部署：** 設定內部部署硬體或軟體 VPN 裝置來終止使用網際網路通訊協定安全性 (IPsec) 的 VPN 連線。</span><span class="sxs-lookup"><span data-stu-id="a40a4-126">**On premises:** Configure your on-premises hardware or software VPN device to terminate the VPN connection, which uses Internet Protocol security (IPsec).</span></span>
    
<span data-ttu-id="a40a4-127">建立站台對站台的 VPN 連線之後，將 Azure 虛擬機器新增至虛擬網路的子網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-127">After you establish the site-to-site VPN connection, you add Azure virtual machines to the subnets of the virtual network.</span></span>
  
## <a name="plan-your-azure-virtual-network"></a><span data-ttu-id="a40a4-128">規劃您的 Azure 虛擬網路</span><span class="sxs-lookup"><span data-stu-id="a40a4-128">Plan your Azure virtual network</span></span>
<a name="PlanningVirtual"></a>

### <a name="prerequisites"></a><span data-ttu-id="a40a4-129">必要條件</span><span class="sxs-lookup"><span data-stu-id="a40a4-129">Prerequisites</span></span>
<a name="Prerequisites"></a>

- <span data-ttu-id="a40a4-p107">Azure 訂用帳戶。如需有關 Azure 訂用帳戶的資訊，請移至[如何購買 Azure 頁面](https://azure.microsoft.com/pricing/purchase-options/)。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p107">An Azure subscription. For information about Azure subscriptions, go to the [How To Buy Azure page](https://azure.microsoft.com/pricing/purchase-options/).</span></span>
    
- <span data-ttu-id="a40a4-132">要指派至虛擬網路和其子網路的可用私人 IPv4 位址空間，需具備足夠的擴充空間，以容納現在或未來所需的虛擬機器數量。</span><span class="sxs-lookup"><span data-stu-id="a40a4-132">An available private IPv4 address space to assign to the virtual network and its subnets, with sufficient room for growth to accommodate the number of virtual machines needed now and in the future.</span></span>
    
- <span data-ttu-id="a40a4-p108">內部部署網路中可用的 VPN 裝置，用於終止可支援 IPsec 需求的站台對站台 VPN 連線。如需詳細資訊，請參閱＜[關於適用於站台對站台虛擬網路連線的 VPN 裝置](https://go.microsoft.com/fwlink/p/?LinkId=393093)＞。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p108">An available VPN device in your on-premises network to terminate the site-to-site VPN connection that supports the requirements for IPsec. For more information, see [About VPN devices for site-to-site virtual network connections](https://go.microsoft.com/fwlink/p/?LinkId=393093).</span></span>
    
- <span data-ttu-id="a40a4-135">路由基礎結構的變更，以便讓路由至 Azure 虛擬網路位址空間的流量可轉送至裝載站台對站台 VPN 連線的 VPN 裝置。</span><span class="sxs-lookup"><span data-stu-id="a40a4-135">Changes to your routing infrastructure so that traffic routed to the address space of the Azure virtual network gets forwarded to the VPN device that hosts the site-to-site VPN connection.</span></span>
    
- <span data-ttu-id="a40a4-136">Web Proxy，讓與內部部署網路和 Azure虛擬網路連線的電腦可存取網際網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-136">A web proxy that gives computers that are connected to the on-premises network and the Azure virtual network access to the Internet.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="a40a4-137">解決方案架構設計假設</span><span class="sxs-lookup"><span data-stu-id="a40a4-137">Solution architecture design assumptions</span></span>

<span data-ttu-id="a40a4-138">下列清單會列出針對此解決方案架構所做的設計選擇。</span><span class="sxs-lookup"><span data-stu-id="a40a4-138">The following list represents the design choices that have been made for this solution architecture.</span></span> 
  
- <span data-ttu-id="a40a4-p109">本解決方案使用具備站台對站台 VPN 連線的單一 Azure 虛擬網路。Azure 虛擬網路會裝載內含多部虛擬機器的單一子網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p109">This solution uses a single Azure virtual network with a site-to-site VPN connection. The Azure virtual network hosts a single subnet that can contain multiple virtual machines.</span></span> 
    
- <span data-ttu-id="a40a4-p110">您可以使用 Windows Server 2016 中的路由及遠端存取服務 (RRAS) 或 Windows Server 2012，建立內部部署網路和 Azure 虛擬網路間的 IPsec 站台對站台 VPN 連線。您也可以使用其他選項，例如 Cisco 或 Juniper Networks 的 VPN 裝置。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p110">You can use the Routing and Remote Access Service (RRAS) in Windows Server 2016 or Windows Server 2012 to establish an IPsec site-to-site VPN connection between the on-premises network and the Azure virtual network. You can also use other options, such as Cisco or Juniper Networks VPN devices.</span></span>
    
- <span data-ttu-id="a40a4-p111">內部部署網路可能仍有 Active Directory Domain Services (AD DS)、網域名稱系統 (DNS) 和 Proxy 伺服器等網路服務。視您的需求而定，將一些此類網路資源放在 Azure 虛擬網路中可能會有助益。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p111">The on-premises network might still have network services like Active Directory Domain Services (AD DS), Domain Name System (DNS), and proxy servers. Depending on your requirements, it might be beneficial to place some of these network resources in the Azure virtual network.</span></span>
    
<span data-ttu-id="a40a4-p112">對於具備一個或多個子網路的現有 Azure 虛擬網路，請判斷其是否還有位址空間容納其他子網路，以裝載所需的虛擬機器 (視您的需求而定)。如果您沒有其餘位址空間可容納其他子網路，請建立本身具備站台對站台 VPN 連線的其他虛擬網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p112">For an existing Azure virtual network with one or more subnets, determine whether there is remaining address space for an additional subnet to host your needed virtual machines, based on your requirements. If you don't have remaining address space for an additional subnet, create an additional virtual network that has its own site-to-site VPN connection.</span></span>
  
### <a name="plan-the-routing-infrastructure-changes-for-the-azure-virtual-network"></a><span data-ttu-id="a40a4-147">規劃適用於 Azure 虛擬網路的路由基礎結構變更</span><span class="sxs-lookup"><span data-stu-id="a40a4-147">Plan the routing infrastructure changes for the Azure virtual network</span></span>

<span data-ttu-id="a40a4-148">您必須設定內部部署路由基礎結構，以便將目的地為 Azure 虛擬網路位址空間的流量轉送至裝載站台對站台 VPN 連線的內部部署 VPN 裝置</span><span class="sxs-lookup"><span data-stu-id="a40a4-148">You must configure your on-premises routing infrastructure to forward traffic destined for the address space of the Azure virtual network to the on-premises VPN device that is hosting the site-to-site VPN connection.</span></span>
  
<span data-ttu-id="a40a4-149">更新路由基礎結構的確切方法須根據您管理路由資訊的方法而定，可能是以下方法：</span><span class="sxs-lookup"><span data-stu-id="a40a4-149">The exact method of updating your routing infrastructure depends on how you manage routing information, which can be:</span></span>
  
- <span data-ttu-id="a40a4-150">以手動設定更新路由表。</span><span class="sxs-lookup"><span data-stu-id="a40a4-150">Routing table updates based on manual configuration.</span></span>
    
- <span data-ttu-id="a40a4-151">以「路由資訊通訊協定 (RIP)」或「先開啟最短的路徑 (OSPF)」等路由通訊協定更新路由表。</span><span class="sxs-lookup"><span data-stu-id="a40a4-151">Routing table updates based on routing protocols, such as Routing Information Protocol (RIP) or Open Shortest Path First (OSPF).</span></span>
    
<span data-ttu-id="a40a4-152">請洽詢路由專業人員，以確定目的地是 Azure 虛擬網路的流量會轉送到內部部署的 VPN 裝置。</span><span class="sxs-lookup"><span data-stu-id="a40a4-152">Consult with your routing specialist to make sure that traffic destined for the Azure virtual network is forwarded to the on-premises VPN device.</span></span>
  
### <a name="plan-for-firewall-rules-for-traffic-to-and-from-the-on-premises-vpn-device"></a><span data-ttu-id="a40a4-153">為內部部署 VPN 裝置的流量傳輸規劃防火牆規則</span><span class="sxs-lookup"><span data-stu-id="a40a4-153">Plan for firewall rules for traffic to and from the on-premises VPN device</span></span>

<span data-ttu-id="a40a4-154">如果 VPN 裝置位於周邊網路上，且周邊網路與網際網路間有防火牆，您可能必須為防火牆設定以下規則，以允許站台對站台的 VPN 連線。</span><span class="sxs-lookup"><span data-stu-id="a40a4-154">If your VPN device is on a perimeter network that has a firewall between the perimeter network and the Internet, you might have to configure the firewall for the following rules to allow the site-to-site VPN connection.</span></span>
  
- <span data-ttu-id="a40a4-155">傳輸至 VPN 裝置的流量 (從網際網路傳入)：</span><span class="sxs-lookup"><span data-stu-id="a40a4-155">Traffic to the VPN device (incoming from the Internet):</span></span>
    
  - <span data-ttu-id="a40a4-156">VPN 裝置的目的地 IP 位址和 IP 通訊協定 50</span><span class="sxs-lookup"><span data-stu-id="a40a4-156">Destination IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="a40a4-157">VPN 裝置的目的地 IP 位址和 UDP 目的地通訊協定 500</span><span class="sxs-lookup"><span data-stu-id="a40a4-157">Destination IP address of the VPN device and UDP destination port 500</span></span>
    
  - <span data-ttu-id="a40a4-158">VPN 裝置的目的地 IP 位址和 UDP 目的地通訊協定 4500</span><span class="sxs-lookup"><span data-stu-id="a40a4-158">Destination IP address of the VPN device and UDP destination port 4500</span></span>
    
- <span data-ttu-id="a40a4-159">從 VPN 裝置傳輸出去的流量 (傳出至網際網路)︰</span><span class="sxs-lookup"><span data-stu-id="a40a4-159">Traffic from the VPN device (outgoing to the Internet):</span></span>
    
  - <span data-ttu-id="a40a4-160">VPN 裝置的來源 IP 位址和 IP 通訊協定 50</span><span class="sxs-lookup"><span data-stu-id="a40a4-160">Source IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="a40a4-161">VPN 裝置的來源 IP 位址和 UDP 來源通訊協定 500</span><span class="sxs-lookup"><span data-stu-id="a40a4-161">Source IP address of the VPN device and UDP source port 500</span></span>
    
  - <span data-ttu-id="a40a4-162">VPN 裝置的來源 IP 位址和 UDP 來源通訊協定 4500</span><span class="sxs-lookup"><span data-stu-id="a40a4-162">Source IP address of the VPN device and UDP source port 4500</span></span>
    
### <a name="plan-for-the-private-ip-address-space-of-the-azure-virtual-network"></a><span data-ttu-id="a40a4-163">規劃 Azure 虛擬網路的私人 IP 位址空間</span><span class="sxs-lookup"><span data-stu-id="a40a4-163">Plan for the private IP address space of the Azure virtual network</span></span>

<span data-ttu-id="a40a4-164">Azure 虛擬網路的私人 IP 位址空間必須可容納 Azure 使用的位址，以裝載虛擬網路，以及至少具備一個對 Azure 虛擬機器來說有足夠位址的子網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-164">The private IP address space of the Azure virtual network must be able to accommodate addresses used by Azure to host the virtual network and with at least one subnet that has enough addresses for your Azure virtual machines.</span></span>
  
<span data-ttu-id="a40a4-165">若要判斷子網路所需的位址數量，請計算您現在需要的虛擬機器數量、預估未來的成長量，然後使用下表來決定子網路的大小。</span><span class="sxs-lookup"><span data-stu-id="a40a4-165">To determine the number of addresses needed for the subnet, count the number of virtual machines that you need now, estimate for future growth, and then use the following table to determine the size of the subnet.</span></span>
  
|<span data-ttu-id="a40a4-166">**所需的虛擬機器數量**</span><span class="sxs-lookup"><span data-stu-id="a40a4-166">**Number of virtual machines needed**</span></span>|<span data-ttu-id="a40a4-167">**所需的主機位元數**</span><span class="sxs-lookup"><span data-stu-id="a40a4-167">**Number of host bits needed**</span></span>|<span data-ttu-id="a40a4-168">**子網路大小**</span><span class="sxs-lookup"><span data-stu-id="a40a4-168">**Size of the subnet**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a40a4-169">1-3</span><span class="sxs-lookup"><span data-stu-id="a40a4-169">1-3</span></span>  <br/> |<span data-ttu-id="a40a4-170">3</span><span class="sxs-lookup"><span data-stu-id="a40a4-170">3</span></span>  <br/> |<span data-ttu-id="a40a4-171">/29</span><span class="sxs-lookup"><span data-stu-id="a40a4-171">/29</span></span>  <br/> |
|<span data-ttu-id="a40a4-172">4-11</span><span class="sxs-lookup"><span data-stu-id="a40a4-172">4-11</span></span>  <br/> |<span data-ttu-id="a40a4-173">4</span><span class="sxs-lookup"><span data-stu-id="a40a4-173">4</span></span>  <br/> |<span data-ttu-id="a40a4-174">/28</span><span class="sxs-lookup"><span data-stu-id="a40a4-174">/28</span></span>  <br/> |
|<span data-ttu-id="a40a4-175">12-27</span><span class="sxs-lookup"><span data-stu-id="a40a4-175">12-27</span></span>  <br/> |<span data-ttu-id="a40a4-176">5</span><span class="sxs-lookup"><span data-stu-id="a40a4-176">5</span></span>  <br/> |<span data-ttu-id="a40a4-177">/27</span><span class="sxs-lookup"><span data-stu-id="a40a4-177">/27</span></span>  <br/> |
|<span data-ttu-id="a40a4-178">28-59</span><span class="sxs-lookup"><span data-stu-id="a40a4-178">28-59</span></span>  <br/> |<span data-ttu-id="a40a4-179">6</span><span class="sxs-lookup"><span data-stu-id="a40a4-179">6</span></span>  <br/> |<span data-ttu-id="a40a4-180">/26</span><span class="sxs-lookup"><span data-stu-id="a40a4-180">/26</span></span>  <br/> |
|<span data-ttu-id="a40a4-181">60-123</span><span class="sxs-lookup"><span data-stu-id="a40a4-181">60-123</span></span>  <br/> |<span data-ttu-id="a40a4-182">7</span><span class="sxs-lookup"><span data-stu-id="a40a4-182">7</span></span>  <br/> |<span data-ttu-id="a40a4-183">/25</span><span class="sxs-lookup"><span data-stu-id="a40a4-183">/25</span></span>  <br/> |
   
### <a name="planning-worksheet-for-configuring-your-azure-virtual-network"></a><span data-ttu-id="a40a4-184">設定您 Azure 虛擬網路的規劃工作表</span><span class="sxs-lookup"><span data-stu-id="a40a4-184">Planning worksheet for configuring your Azure virtual network</span></span>
<span data-ttu-id="a40a4-185"><a name="worksheet"> </a></span><span class="sxs-lookup"><span data-stu-id="a40a4-185"><a name="worksheet"> </a></span></span>

<span data-ttu-id="a40a4-186">建立 Azure 虛擬機器以裝載虛擬機器之前，您必須決定下表中的所需設定。</span><span class="sxs-lookup"><span data-stu-id="a40a4-186">Before you create an Azure virtual network to host virtual machines, you must determine the settings needed in the following tables.</span></span>
  
<span data-ttu-id="a40a4-187">針對虛擬網路的設定，填寫表格 V。</span><span class="sxs-lookup"><span data-stu-id="a40a4-187">For the settings of the virtual network, fill in Table V.</span></span>
  
 <span data-ttu-id="a40a4-188">**表格 V：跨單位虛擬網路設定**</span><span class="sxs-lookup"><span data-stu-id="a40a4-188">**Table V: Cross-premises virtual network configuration**</span></span>
  
|<span data-ttu-id="a40a4-189">**項目**</span><span class="sxs-lookup"><span data-stu-id="a40a4-189">**Item**</span></span>|<span data-ttu-id="a40a4-190">**Configuration 元素**</span><span class="sxs-lookup"><span data-stu-id="a40a4-190">**Configuration element**</span></span>|<span data-ttu-id="a40a4-191">**描述**</span><span class="sxs-lookup"><span data-stu-id="a40a4-191">**Description**</span></span>|<span data-ttu-id="a40a4-192">**值**</span><span class="sxs-lookup"><span data-stu-id="a40a4-192">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a40a4-193">1.</span><span class="sxs-lookup"><span data-stu-id="a40a4-193">1.</span></span>  <br/> |<span data-ttu-id="a40a4-194">虛擬網路名稱</span><span class="sxs-lookup"><span data-stu-id="a40a4-194">Virtual network name</span></span>  <br/> |<span data-ttu-id="a40a4-195">指派給 Azure 虛擬網路的名稱 (例如 DirSyncNet)。</span><span class="sxs-lookup"><span data-stu-id="a40a4-195">A name to assign to the Azure virtual network (example DirSyncNet).</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png) |
|<span data-ttu-id="a40a4-197">2.</span><span class="sxs-lookup"><span data-stu-id="a40a4-197">2.</span></span>  <br/> |<span data-ttu-id="a40a4-198">虛擬網路位置</span><span class="sxs-lookup"><span data-stu-id="a40a4-198">Virtual network location</span></span>  <br/> |<span data-ttu-id="a40a4-199">將包含虛擬網路的 Azure 資料中心 (例如美國西部)</span><span class="sxs-lookup"><span data-stu-id="a40a4-199">The Azure datacenter that will contain the virtual network (such as West US).</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a40a4-201">3.</span><span class="sxs-lookup"><span data-stu-id="a40a4-201">3.</span></span>  <br/> |<span data-ttu-id="a40a4-202">VPN 裝置 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a40a4-202">VPN device IP address</span></span>  <br/> |<span data-ttu-id="a40a4-p113">網際網路上 VPN 裝置介面的公用 IPv4 位址請與您的 IT 部門合作以決定此位址。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p113">The public IPv4 address of your VPN device's interface on the Internet. Work with your IT department to determine this address.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a40a4-206">4.</span><span class="sxs-lookup"><span data-stu-id="a40a4-206">4.</span></span>  <br/> |<span data-ttu-id="a40a4-207">虛擬網路位址空間</span><span class="sxs-lookup"><span data-stu-id="a40a4-207">Virtual network address space</span></span>  <br/> |<span data-ttu-id="a40a4-p114">虛擬網路的位址空間 (定義於單一私人位址前置詞中)。請與您的 IT 部門合作以決定此位址空間。位址空間應是無類別網域間路由選擇 (CIDR) 格式 (也稱為網路前置詞格式)。例如 10.24.64.0/20。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p114">The address space (defined in a single private address prefix) for the virtual network. Work with your IT department to determine this address space. The address space should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format. An example is 10.24.64.0/20.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png) <br/> |
|<span data-ttu-id="a40a4-213">5.</span><span class="sxs-lookup"><span data-stu-id="a40a4-213">5.</span></span>  <br/> |<span data-ttu-id="a40a4-214">IPsec 共用金鑰</span><span class="sxs-lookup"><span data-stu-id="a40a4-214">IPsec shared key</span></span>  <br/> |<span data-ttu-id="a40a4-p115">32 個字元的隨機英數字元字串，用以驗證站台對站台 VPN 連線的兩端站台。請與您的 IT 或安全性部門合作，以決定此金鑰值並將其儲存至安全的位置。或者，請參閱[建立隨機字串以作為 IPsec 的預先共用金鑰](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p115">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection. Work with your IT or security department to determine this key value and then store it in a secure location. Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span></span><br/> |![線條](../media/Common-Images/TableLine.png) <br/> |
   
<span data-ttu-id="a40a4-219">針對此解決方案的子網路填寫表格 S。</span><span class="sxs-lookup"><span data-stu-id="a40a4-219">Fill in Table S for the subnets of this solution.</span></span>
  
- <span data-ttu-id="a40a4-p116">針對第一個子網路，請決定 Azure 閘道子網路的 28 位元位址空間 (使用 /28 前置長度)。請參閱[針對 Azure 虛擬網路計算閘道子網路位址空間](https://blogs.technet.microsoft.com/solutions_advisory_board/2016/12/01/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks/)，以取得如何決定此位址空間的資訊。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p116">For the first subnet, determine a 28-bit address space (with a /28 prefix length) for the Azure gateway subnet. See [Calculating the gateway subnet address space for Azure virtual networks](https://blogs.technet.microsoft.com/solutions_advisory_board/2016/12/01/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks/) for information about how to determine this address space.</span></span>
    
- <span data-ttu-id="a40a4-222">針對二個的子網路，請指定好記的名稱、以虛擬網路位址空間為基礎的單一 IP 位址空間，以及具描述性的用途。</span><span class="sxs-lookup"><span data-stu-id="a40a4-222">For the second subnet, specify a friendly name, a single IP address space based on the virtual network address space, and a descriptive purpose.</span></span>
    
<span data-ttu-id="a40a4-p117">請與您的 IT 部門合作，以從虛擬網路位址空間判斷這些位址空間。兩個位址空間皆應為 CIDR 格式。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p117">Work with your IT department to determine these address spaces from the virtual network address space. Both address spaces should be in CIDR format.</span></span>
  
 <span data-ttu-id="a40a4-225">**表格 S：虛擬網路中的子網路**</span><span class="sxs-lookup"><span data-stu-id="a40a4-225">**Table S: Subnets in the virtual network**</span></span>
  
|<span data-ttu-id="a40a4-226">**項目**</span><span class="sxs-lookup"><span data-stu-id="a40a4-226">**Item**</span></span>|<span data-ttu-id="a40a4-227">**子網路名稱**</span><span class="sxs-lookup"><span data-stu-id="a40a4-227">**Subnet name**</span></span>|<span data-ttu-id="a40a4-228">**子網路位址空間**</span><span class="sxs-lookup"><span data-stu-id="a40a4-228">**Subnet address space**</span></span>|<span data-ttu-id="a40a4-229">**用途**</span><span class="sxs-lookup"><span data-stu-id="a40a4-229">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a40a4-230">1.</span><span class="sxs-lookup"><span data-stu-id="a40a4-230">1.</span></span>  <br/> |<span data-ttu-id="a40a4-231">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="a40a4-231">GatewaySubnet</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="a40a4-233">由 Azure 閘道使用的子網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-233">The subnet used by the Azure gateway.</span></span>  <br/> |
|<span data-ttu-id="a40a4-234">2.</span><span class="sxs-lookup"><span data-stu-id="a40a4-234">2.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="a40a4-p118">針對虛擬網路中，虛擬機器要使用的內部部署 DNS 伺服器，請填寫表格 D。此易記名稱無須與主機名稱或 DNS 伺服器的電腦名稱相同。請注意，列出的空白項有兩個，但您可以新增更多。請與您的 IT 部門合作以決定此清單。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p118">For the on-premises DNS servers that you want the virtual machines in the virtual network to use, fill in Table D. Give each DNS server a friendly name and a single IP address. This friendly name does not need to match the host name or computer name of the DNS server. Note that two blank entries are listed, but you can add more. Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="a40a4-242">**表格 D：內部部署 DNS 伺服器**</span><span class="sxs-lookup"><span data-stu-id="a40a4-242">**Table D: On-premises DNS servers**</span></span>
  
|<span data-ttu-id="a40a4-243">**項目**</span><span class="sxs-lookup"><span data-stu-id="a40a4-243">**Item**</span></span>|<span data-ttu-id="a40a4-244">**DNS 伺服器的易記名稱**</span><span class="sxs-lookup"><span data-stu-id="a40a4-244">**DNS server friendly name**</span></span>|<span data-ttu-id="a40a4-245">**DNS 伺服器 IP 位址**</span><span class="sxs-lookup"><span data-stu-id="a40a4-245">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a40a4-246">1.</span><span class="sxs-lookup"><span data-stu-id="a40a4-246">1.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a40a4-249">2.</span><span class="sxs-lookup"><span data-stu-id="a40a4-249">2.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="a40a4-p119">若要透過站台對站台的 VPN 連線將封包從 Azure 虛擬網路路由至組織網路，您必須使用區域網路來設定虛擬網路。此區域網路具有您組織內部部署網路上所有位置的位址空間清單 (CIDR 格式)，且虛擬網路中的虛擬機器必須可觸及這些位址空間。這可以是內部部署網路或子網路上的所有位置。定義區域網路的位址空間清單必須是唯一的，且不可與此虛擬網路使用的位址空間或其他跨單位虛擬網路重疊。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p119">To route packets from the Azure virtual network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network. This local network has a list of the address spaces (in CIDR format) for all of the locations on your organization's on-premises network that the virtual machines in the virtual network must reach. This can be all of the locations on the on-premises network or a subset. The list of address spaces that define your local network must be unique and must not overlap with the address spaces used for this virtual network or your other cross-premises virtual networks.</span></span>
  
<span data-ttu-id="a40a4-p120">針對區域網路位址空間集，請填寫表格 L。請注意，雖已列出三個空白項，但一般來說您會需要更多。請與您的 IT 部門合作以決定此清單。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p120">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more. Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="a40a4-258">**表格 L：區域網路的網址前置詞**</span><span class="sxs-lookup"><span data-stu-id="a40a4-258">**Table L: Address prefixes for the local network**</span></span>
  
|<span data-ttu-id="a40a4-259">**項目**</span><span class="sxs-lookup"><span data-stu-id="a40a4-259">**Item**</span></span>|<span data-ttu-id="a40a4-260">**區域網路位址空間**</span><span class="sxs-lookup"><span data-stu-id="a40a4-260">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a40a4-261">1.</span><span class="sxs-lookup"><span data-stu-id="a40a4-261">1.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a40a4-263">2.</span><span class="sxs-lookup"><span data-stu-id="a40a4-263">2.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a40a4-265">3.</span><span class="sxs-lookup"><span data-stu-id="a40a4-265">3.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
## <a name="deployment-roadmap"></a><span data-ttu-id="a40a4-267">部署藍圖</span><span class="sxs-lookup"><span data-stu-id="a40a4-267">Deployment roadmap</span></span>
<span data-ttu-id="a40a4-268"><a name="DeploymentRoadmap"> </a></span><span class="sxs-lookup"><span data-stu-id="a40a4-268"><a name="DeploymentRoadmap"> </a></span></span>

<span data-ttu-id="a40a4-269">建立跨單位虛擬網路與在 Azure 中新增虛擬機器有三個階段：</span><span class="sxs-lookup"><span data-stu-id="a40a4-269">Creating the cross-premises virtual network and adding virtual machines in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="a40a4-270">階段 1：準備內部部署網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-270">Phase 1: Prepare your on-premises network.</span></span>
    
- <span data-ttu-id="a40a4-271">階段 2：在 Azure 中建立跨單位的虛擬網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-271">Phase 2: Create the cross-premises virtual network in Azure.</span></span>
    
- <span data-ttu-id="a40a4-272">階段 3 (選用)：新增虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="a40a4-272">Phase 3 (Optional): Add virtual machines.</span></span>
    
### <a name="phase-1-prepare-your-on-premises-network"></a><span data-ttu-id="a40a4-273">階段 1：準備內部部署網路</span><span class="sxs-lookup"><span data-stu-id="a40a4-273">Phase 1: Prepare your on-premises network</span></span>
<a name="Phase1"></a>

<span data-ttu-id="a40a4-p121">您必須設定包含路由的內部部署網路，該路由應指向目的地為虛擬網路位址空間的流量，且最終會將流量傳遞至內部部署網路邊緣上的路由器。請洽詢您的網路管理員，以決定如何將路由新增至內部部署網路的路由基礎結構上。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p121">You must configure your on-premises network with a route that points to and ultimately delivers traffic destined for the address space of the virtual network to the router on the edge of the on-premises network. Consult with your network administrator to determine how to add the route to the routing infrastructure of your on-premises network.</span></span>
  
<span data-ttu-id="a40a4-276">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="a40a4-276">Here is your resulting configuration.</span></span>
  
![內部部署網路必須有一個指向 VPN 裝置的虛擬網路位址空間的路由。](../media/90bab36b-cb60-4ea5-81d5-4737b696d41c.png)
  
### <a name="phase-2-create-the-cross-premises-virtual-network-in-azure"></a><span data-ttu-id="a40a4-278">階段 2：在 Azure 中建立跨單位的虛擬網路</span><span class="sxs-lookup"><span data-stu-id="a40a4-278">Phase 2: Create the cross-premises virtual network in Azure</span></span>
<a name="Phase2"></a>

<span data-ttu-id="a40a4-p122">首先，開啟 Azure PowerShell 提示。如果您尚未安裝 Azure PowerShell，請參閱[開始使用 Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps)。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p122">First, open an Azure PowerShell prompt. If you have not installed Azure PowerShell, see [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>

 
<span data-ttu-id="a40a4-281">接著，使用此命令登入您的 Azure 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a40a4-281">Next, login to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="a40a4-282">使用下列命令取得訂用帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="a40a4-282">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort SubscriptionName | Select SubscriptionName
```

<span data-ttu-id="a40a4-p123">使用這些命令設定您的 Azure 訂用帳戶。以正確的訂用帳戶名稱取代括號中的所有項目 (包括 < 和 > 字元)。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p123">Set your Azure subscription with these commands. Replace everything within the quotes, including the < and > characters, with the correct subscription name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="a40a4-p124">接著，為您的虛擬網路建立新的資源群組。若要判斷資源群組名稱是否是唯一的，可使用此命令來列出現有的資源群組。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p124">Next, create a new resource group for your virtual network. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="a40a4-287">使用這些命令建立新的資源群組。</span><span class="sxs-lookup"><span data-stu-id="a40a4-287">Create your new resource group with these commands.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<Table V - Item 2 - Value column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="a40a4-288">接下來，建立 Azure 虛擬網路。</span><span class="sxs-lookup"><span data-stu-id="a40a4-288">Next, you create the Azure virtual network.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V, S, and D
$rgName="<name of your new resource group>"
$locName="<Azure location of your new resource group>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$gwSubnetPrefix="<Table S - Item 1 - Subnet address space column>"
$SubnetName="<Table S - Item 2 - Subnet name column>"
$SubnetPrefix="<Table S - Item 2 - Subnet address space column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the Azure virtual network and a network security group that allows incoming remote desktop connections to the subnet that is hosting virtual machines
$gatewaySubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnetPrefix
$vmSubnet=New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $SubnetPrefix
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gatewaySubnet,$vmSubnet -DNSServer $dnsServers
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName -Location $locShortName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$nsg=Get-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $SubnetName -AddressPrefix $SubnetPrefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="a40a4-289">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="a40a4-289">Here is your resulting configuration.</span></span>
  
![虛擬網路尚未連接至內部部署網路中。](../media/54a37782-a6cc-4d48-b38d-73e128b44a82.png)
  
<span data-ttu-id="a40a4-291">接著，使用以下命令來建立站台對站台 VPN 連線的閘道。</span><span class="sxs-lookup"><span data-stu-id="a40a4-291">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V and L
$vnetName="<Table V - Item 1 - Value column>"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -SubnetId $vnet.Subnets[0].Id
# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig
# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix
# Create the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway
```

<span data-ttu-id="a40a4-292">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="a40a4-292">Here is your resulting configuration.</span></span>
  
![虛擬網路現在有一個閘道。](../media/82dd66b2-a4b7-48f6-a89b-cfdd94630980.png)
  
<span data-ttu-id="a40a4-p125">下一步，設定內部部署 VPN 裝置與 Azure VPN 閘道連線。如需詳細資訊，請參閱＜[關於適用於站台對站台虛擬網路連線的 VPN 裝置](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices)＞。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p125">Next, configure your on-premises VPN device to connect to the Azure VPN gateway. For more information, see [About VPN Devices for site-to-site Azure Virtual Network connections](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="a40a4-296">若要設定您的 VPN 裝置，您需要下列項目︰</span><span class="sxs-lookup"><span data-stu-id="a40a4-296">To configure your VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="a40a4-297">虛擬網路 Azure VPN 閘道的公用 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="a40a4-297">The public IPv4 address of the Azure VPN gateway for your virtual network.</span></span> <span data-ttu-id="a40a4-298">使用 **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** 命令可顯示此位址。</span><span class="sxs-lookup"><span data-stu-id="a40a4-298">Use the **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** command to display this address.</span></span>
    
- <span data-ttu-id="a40a4-299">站台對站台 VPN 連線的 IPsec 預先共用金鑰 (表格 V - 項目 5 - 值欄)。</span><span class="sxs-lookup"><span data-stu-id="a40a4-299">The IPsec pre-shared key for the site-to-site VPN connection (Table V- Item 5 - Value column).</span></span>
    
<span data-ttu-id="a40a4-300">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="a40a4-300">Here is your resulting configuration.</span></span>
  
![虛擬網路現在已連線到內部部署網路。](../media/6379c423-4f22-4453-941b-7ff32484a0a5.png)
  
### <a name="phase-3-optional-add-virtual-machines"></a><span data-ttu-id="a40a4-302">階段 3 (選用)：新增虛擬機器</span><span class="sxs-lookup"><span data-stu-id="a40a4-302">Phase 3 (Optional): Add virtual machines</span></span>

<span data-ttu-id="a40a4-p127">在 Azure 中建立您需要的虛擬機器。如需詳細資訊，請參閱＜[使用 Azure 入口網站建立 Windows 虛擬機器](https://go.microsoft.com/fwlink/p/?LinkId=393098)＞。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p127">Create the virtual machines you need in Azure. For more information, see [Create a Windows virtual machine with the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span></span>
  
<span data-ttu-id="a40a4-305">使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="a40a4-305">Use the following settings:</span></span>
  
- <span data-ttu-id="a40a4-p128">在 [基本概念]\*\*\*\* 索引標籤中，選取相同的訂閱及資源群組做為您的虛擬網路。您稍後登入虛擬機器時需要這些資訊。在 [執行個體詳細資料]\*\*\*\* 區段，選擇適當的虛擬機器大小。將系統管理員帳戶使用者名稱和密碼記錄在安全位置。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p128">On the **Basics** tab, select the same subscription and resource group as your virtual network. You will need these later to sign in to the virtual machine. In the **Instance details** section, choose the appropriate virtual machine size. Record the administrator account user name and password in a secure location.</span></span> 
    
- <span data-ttu-id="a40a4-p129">在 [網路]\*\*\*\* 索引標籤中，選取您裝載虛擬機器 (不是 GatewaySubnet) 的虛擬網路和子網路名稱。將其他設定保留為設定值。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p129">On the **Networking** tab, select the name of your virtual network and the subnet for hosting virtual machines (not the GatewaySubnet). Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="a40a4-p130">請檢查您的內部 DNS 以確認虛擬機器正在正確地使用 DNS，藉此確認適用於新虛擬機器的位址 (A) 記錄已新增。若要存取網際網路，您的 Azure 虛擬機器必須設定為使用內部部署網路的 Proxy 伺服器。請連絡您的網路系統管理員，以取得要在伺服器上執行的其他設定步驟。</span><span class="sxs-lookup"><span data-stu-id="a40a4-p130">Verify that your virtual machine is using DNS correctly by checking your internal DNS to ensure that Address (A) records were added for you new virtual machine. To access the Internet, your Azure virtual machines must be configured to use your on-premises network's proxy server. Contact your network administrator for additional configuration steps to perform on the server.</span></span>
  
<span data-ttu-id="a40a4-315">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="a40a4-315">Here is your resulting configuration.</span></span>
  
![虛擬網路現在主控可從內部部署網路存取的虛擬機器。](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
  
## <a name="next-step"></a><span data-ttu-id="a40a4-317">下一步</span><span class="sxs-lookup"><span data-stu-id="a40a4-317">Next step</span></span>
  
[<span data-ttu-id="a40a4-318">在 Microsoft Azure 中部署 Microsoft 365 目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="a40a4-318">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>](deploy-microsoft-365-directory-synchronization-dirsync-in-microsoft-azure.md)
