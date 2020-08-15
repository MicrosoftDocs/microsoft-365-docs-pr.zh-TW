---
title: Azure 中的 Microsoft 365 高可用性同盟驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: 摘要：在 Microsoft Azure 中為您的 Microsoft 365 訂閱設定高可用性同盟驗證。
ms.openlocfilehash: abe01445b8963dcdc5693b45a680e273f5084446
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688621"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a><span data-ttu-id="4d7bf-103">Azure 中的 Microsoft 365 高可用性同盟驗證</span><span class="sxs-lookup"><span data-stu-id="4d7bf-103">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>

<span data-ttu-id="4d7bf-104">本文提供以下列虛擬機器在 Azure 基礎結構服務中部署 Microsoft Microsoft 365 高可用性同盟驗證的逐步指示連結。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-104">This article has links to the step-by-step instructions for deploying high availability federated authentication for Microsoft Microsoft 365 in Azure infrastructure services with these virtual machines:</span></span>
  
- <span data-ttu-id="4d7bf-105">兩個 Web 應用程式 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="4d7bf-105">Two web application proxy servers</span></span>
    
- <span data-ttu-id="4d7bf-106">兩個 Active Directory Federation Services (AD FS) 伺服器</span><span class="sxs-lookup"><span data-stu-id="4d7bf-106">Two Active Directory Federation Services (AD FS) servers</span></span>
    
- <span data-ttu-id="4d7bf-107">兩個複本網域控制站</span><span class="sxs-lookup"><span data-stu-id="4d7bf-107">Two replica domain controllers</span></span>
    
- <span data-ttu-id="4d7bf-108">一個執行 Azure AD Connect 的目錄同步處理伺服器</span><span class="sxs-lookup"><span data-stu-id="4d7bf-108">One directory synchronization server running Azure AD Connect</span></span>
    
<span data-ttu-id="4d7bf-109">組態如下，包含每部伺服器的預留位置名稱。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-109">Here is the configuration, with placeholder names for each server.</span></span>
  
<span data-ttu-id="4d7bf-110">**Azure 中 Microsoft 365 基礎結構的高可用性同盟驗證**</span><span class="sxs-lookup"><span data-stu-id="4d7bf-110">**A high availability federated authentication for Microsoft 365 infrastructure in Azure**</span></span>

![Azure 中高可用性 Microsoft 365 同盟驗證基礎結構的最終設定](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="4d7bf-112">所有虛擬機器位於單一跨單位 Azure 虛擬網路中 (VNet)。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-112">All of the virtual machines are in a single cross-premises Azure virtual network (VNet).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4d7bf-p101">個別使用者的聯盟驗證不會仰賴任何內部部署資源。不過，如果跨單位連線無法使用，VNet 中的網域控制站就不會收到使用者帳戶和群組在內部部署 Active Directory Domain Services (AD DS) 中的更新。若要確保不會發生這個情況，您可以設定跨場所連線的高可用性。如需詳細資訊，請參閱[高度可用的跨單位和 VNet-VNet 連線](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-p101">Federated authentication of individual users does not rely on any on-premises resources. However, if the cross-premises connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services (AD DS). To ensure this does not happen, you can configure high availability for your cross-premises connection. For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="4d7bf-117">特定角色的每個虛擬機器配對都是位於它自己的子網路和可用性設定組中。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-117">Each pair of virtual machines for a specific role is in its own subnet and availability set.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d7bf-p102">因為此 VNet 會連線到內部部署網路，所以此組態不包含管理子網路上的 Jumpbox 或監視虛擬機器。如需詳細資訊，請參閱＜[執行 N 層架構的 Windows VM](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm)＞。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-p102">Because this VNet is connected to the on-premises network, this configuration does not include jumpbox or monitoring virtual machines on a management subnet. For more information, see [Running Windows VMs for an N-tier architecture](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm).</span></span> 
  
<span data-ttu-id="4d7bf-120">這項設定的結果是您將具備所有 Microsoft 365 使用者的同盟驗證，讓他們可以使用其 AD DS 認證來登入，而不是其 Microsoft 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-120">The result of this configuration is that you will have federated authentication for all of your Microsoft 365 users, in which they can use their AD DS credentials to sign in rather than their Microsoft 365 account.</span></span> <span data-ttu-id="4d7bf-121">聯盟驗證基礎結構會使用一組多餘的伺服器，能更輕鬆部署在 Azure 基礎結構服務而不是內部部署邊緣網路中。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-121">The federated authentication infrastructure uses a redundant set of servers that are more easily deployed in Azure infrastructure services, rather than in your on-premises edge network.</span></span>
  
## <a name="bill-of-materials"></a><span data-ttu-id="4d7bf-122">物料單</span><span class="sxs-lookup"><span data-stu-id="4d7bf-122">Bill of materials</span></span>

<span data-ttu-id="4d7bf-123">此基準組態需要下列 Azure 服務和元件集合：</span><span class="sxs-lookup"><span data-stu-id="4d7bf-123">This baseline configuration requires the following set of Azure services and components:</span></span>
  
- <span data-ttu-id="4d7bf-124">九部虛擬機器</span><span class="sxs-lookup"><span data-stu-id="4d7bf-124">Seven virtual machines</span></span>
    
- <span data-ttu-id="4d7bf-125">具有四個子網路的一個跨單位虛擬網路</span><span class="sxs-lookup"><span data-stu-id="4d7bf-125">One cross-premises virtual network with four subnets</span></span>
    
- <span data-ttu-id="4d7bf-126">四個資源群組</span><span class="sxs-lookup"><span data-stu-id="4d7bf-126">Four resource groups</span></span>
    
- <span data-ttu-id="4d7bf-127">三個可用性設定組</span><span class="sxs-lookup"><span data-stu-id="4d7bf-127">Three availability sets</span></span>
    
- <span data-ttu-id="4d7bf-128">一個 Azure 訂用帳戶</span><span class="sxs-lookup"><span data-stu-id="4d7bf-128">One Azure subscription</span></span>
    
<span data-ttu-id="4d7bf-129">以下是此組態的虛擬機器與其預設大小。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-129">Here are the virtual machines and their default sizes for this configuration.</span></span>
  
|<span data-ttu-id="4d7bf-130">**項目**</span><span class="sxs-lookup"><span data-stu-id="4d7bf-130">**Item**</span></span>|<span data-ttu-id="4d7bf-131">**虛擬機器描述**</span><span class="sxs-lookup"><span data-stu-id="4d7bf-131">**Virtual machine description**</span></span>|<span data-ttu-id="4d7bf-132">**Azure 圖庫影像**</span><span class="sxs-lookup"><span data-stu-id="4d7bf-132">**Azure gallery image**</span></span>|<span data-ttu-id="4d7bf-133">**預設大小**</span><span class="sxs-lookup"><span data-stu-id="4d7bf-133">**Default size**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d7bf-134">1.</span><span class="sxs-lookup"><span data-stu-id="4d7bf-134">1.</span></span>  <br/> |<span data-ttu-id="4d7bf-135">第一個網域控制站</span><span class="sxs-lookup"><span data-stu-id="4d7bf-135">First domain controller</span></span>  <br/> |<span data-ttu-id="4d7bf-136">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="4d7bf-136">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="4d7bf-137">D2</span><span class="sxs-lookup"><span data-stu-id="4d7bf-137">D2</span></span>  <br/> |
|<span data-ttu-id="4d7bf-138">2.</span><span class="sxs-lookup"><span data-stu-id="4d7bf-138">2.</span></span>  <br/> |<span data-ttu-id="4d7bf-139">第二個網域控制站</span><span class="sxs-lookup"><span data-stu-id="4d7bf-139">Second domain controller</span></span>  <br/> |<span data-ttu-id="4d7bf-140">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="4d7bf-140">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="4d7bf-141">D2</span><span class="sxs-lookup"><span data-stu-id="4d7bf-141">D2</span></span>  <br/> |
|<span data-ttu-id="4d7bf-142">3.</span><span class="sxs-lookup"><span data-stu-id="4d7bf-142">3.</span></span>  <br/> |<span data-ttu-id="4d7bf-143">Azure AD Connect 伺服器</span><span class="sxs-lookup"><span data-stu-id="4d7bf-143">Azure AD Connect server</span></span>  <br/> |<span data-ttu-id="4d7bf-144">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="4d7bf-144">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="4d7bf-145">D2</span><span class="sxs-lookup"><span data-stu-id="4d7bf-145">D2</span></span>  <br/> |
|<span data-ttu-id="4d7bf-146">4.</span><span class="sxs-lookup"><span data-stu-id="4d7bf-146">4.</span></span>  <br/> |<span data-ttu-id="4d7bf-147">第一個 AD FS 伺服器</span><span class="sxs-lookup"><span data-stu-id="4d7bf-147">First AD FS server</span></span>  <br/> |<span data-ttu-id="4d7bf-148">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="4d7bf-148">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="4d7bf-149">D2</span><span class="sxs-lookup"><span data-stu-id="4d7bf-149">D2</span></span>  <br/> |
|<span data-ttu-id="4d7bf-150">5.</span><span class="sxs-lookup"><span data-stu-id="4d7bf-150">5.</span></span>  <br/> |<span data-ttu-id="4d7bf-151">第二個 AD FS 伺服器</span><span class="sxs-lookup"><span data-stu-id="4d7bf-151">Second AD FS server</span></span>  <br/> |<span data-ttu-id="4d7bf-152">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="4d7bf-152">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="4d7bf-153">D2</span><span class="sxs-lookup"><span data-stu-id="4d7bf-153">D2</span></span>  <br/> |
|<span data-ttu-id="4d7bf-154">6.</span><span class="sxs-lookup"><span data-stu-id="4d7bf-154">6.</span></span>  <br/> |<span data-ttu-id="4d7bf-155">第一個 Web 應用程式 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="4d7bf-155">First web application proxy server</span></span>  <br/> |<span data-ttu-id="4d7bf-156">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="4d7bf-156">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="4d7bf-157">D2</span><span class="sxs-lookup"><span data-stu-id="4d7bf-157">D2</span></span>  <br/> |
|<span data-ttu-id="4d7bf-158">7.</span><span class="sxs-lookup"><span data-stu-id="4d7bf-158">7.</span></span>  <br/> |<span data-ttu-id="4d7bf-159">第二個 Web 應用程式 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="4d7bf-159">Second web application proxy server</span></span>  <br/> |<span data-ttu-id="4d7bf-160">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="4d7bf-160">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="4d7bf-161">D2</span><span class="sxs-lookup"><span data-stu-id="4d7bf-161">D2</span></span>  <br/> |
   
<span data-ttu-id="4d7bf-162">若要計算此組態的估計成本，請參閱 [Azure 價格計算機](https://azure.microsoft.com/pricing/calculator/)</span><span class="sxs-lookup"><span data-stu-id="4d7bf-162">To compute the estimated costs for this configuration, see the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/)</span></span>
  
## <a name="phases-of-deployment"></a><span data-ttu-id="4d7bf-163">部署階段</span><span class="sxs-lookup"><span data-stu-id="4d7bf-163">Phases of deployment</span></span>

<span data-ttu-id="4d7bf-164">您可以在下列階段部署此工作負載：</span><span class="sxs-lookup"><span data-stu-id="4d7bf-164">You deploy this workload in the following phases:</span></span>
  
- <span data-ttu-id="4d7bf-p104">[階段 1：設定 Azure](high-availability-federated-authentication-phase-1-configure-azure.md)。建立資源群組、儲存體帳戶、可用性設定組和跨單位虛擬網路。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-p104">[Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md). Create resource groups, storage accounts, availability sets, and a cross-premises virtual network.</span></span>
    
- <span data-ttu-id="4d7bf-167">[階段 2：設定網域控制站](high-availability-federated-authentication-phase-2-configure-domain-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-167">[Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="4d7bf-168">建立並設定複本 AD DS 網域控制站和目錄同步處理伺服器。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-168">Create and configure replica AD DS domain controllers and the directory synchronization server.</span></span>
    
- <span data-ttu-id="4d7bf-p106">[階段 3：設定 AD FS 伺服器](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)。建立並設定兩個 AD FS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-p106">[Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Create and configure the two AD FS servers.</span></span>
    
- <span data-ttu-id="4d7bf-p107">[階段 4：設定 Web 應用程式 Proxy](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)。建立並設定兩個 Web 應用程式 Proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-p107">[Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). Create and configure the two web application proxy servers.</span></span>
    
- <span data-ttu-id="4d7bf-173">[階段5：設定 Microsoft 365 的同盟驗證](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-173">[Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="4d7bf-174">為您的 Microsoft 365 訂閱設定同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-174">Configure federated authentication for your Microsoft 365 subscription.</span></span>
    
<span data-ttu-id="4d7bf-175">這些文章針對預先定義的架構，提供在 Azure 基礎結構服務中為 Microsoft 365 建立功能性、高可用性同盟驗證的規範性階段指南。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-175">These articles provide a prescriptive, phase-by-phase guide for a predefined architecture to create a functional, high availability federated authentication for Microsoft 365 in Azure infrastructure services.</span></span> <span data-ttu-id="4d7bf-176">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="4d7bf-176">Keep the following in mind:</span></span>
  
- <span data-ttu-id="4d7bf-177">如果您是有經驗的 AD FS 實作者，請自行適應階段 3 至 4 中的指示，並建置最符合您需求的伺服器組。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-177">If you are an experienced AD FS implementer, feel free to adapt the instructions in phases 3 and 4 and build the set of servers that best suits your needs.</span></span>
    
- <span data-ttu-id="4d7bf-178">如果您已擁有的現有 Azure 混合式雲端部署具有現有跨單位虛擬網路，請依需要調整或略過階段 1 和 2 中的指示，並將 AD FS 和 Web 應用程式 Proxy 伺服器置於適當的子網路中。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-178">If you already have an existing Azure hybrid cloud deployment with an existing cross-premises virtual network, feel free to adapt or skip the instructions in phases 1 and 2 and place the AD FS and web application proxy servers on the appropriate subnets.</span></span>
    
<span data-ttu-id="4d7bf-179">若要建立開發/測試環境或此設定的概念證明，請參閱 [適用于 Microsoft 365 開發/測試環境](federated-identity-for-your-microsoft-365-dev-test-environment.md)的同盟身分識別。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-179">To build a dev/test environment or a proof-of-concept of this configuration, see [Federated identity for your Microsoft 365 dev/test environment](federated-identity-for-your-microsoft-365-dev-test-environment.md).</span></span>
  
## <a name="next-step"></a><span data-ttu-id="4d7bf-180">下一步</span><span class="sxs-lookup"><span data-stu-id="4d7bf-180">Next step</span></span>

<span data-ttu-id="4d7bf-181">使用[階段 1：設定 Azure](high-availability-federated-authentication-phase-1-configure-azure.md) 開始設定此工作負載。</span><span class="sxs-lookup"><span data-stu-id="4d7bf-181">Start the configuration of this workload with [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> 
  
