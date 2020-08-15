---
title: 在 Microsoft Azure 中部署 Microsoft 365 目錄同步處理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
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
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: 瞭解如何在 Azure 中的虛擬機器上部署 Azure AD Connect，以同步處理內部部署目錄與 Azure AD 租使用者之間的帳戶。
ms.openlocfilehash: 8db78d20ee4c2186918a0b3b433f8f0ae056816e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688617"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a><span data-ttu-id="7fd14-103">在 Microsoft Azure 中部署 Microsoft 365 目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="7fd14-103">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>

<span data-ttu-id="7fd14-104">Azure Active Directory (Azure AD)  (Connect （以前稱為目錄同步處理工具、目錄同步處理工具或 DirSync.exe 工具) ）是您在加入網域的伺服器上安裝，以同步處理內部部署 Active Directory 網域服務 (AD DS) 使用者加入您的 Microsoft 365 訂閱的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="7fd14-104">Azure Active Directory (Azure AD) Connect (formerly known as the Directory Synchronization tool, Directory Sync tool, or the DirSync.exe tool) is an application that you install on a domain-joined server to synchronize your on-premises Active Directory Domain Services (AD DS) users to the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="7fd14-105">Microsoft 365 針對其目錄服務使用 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7fd14-105">Microsoft 365 uses Azure AD for its directory service.</span></span> <span data-ttu-id="7fd14-106">您的 Microsoft 365 訂閱包含 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="7fd14-106">Your Microsoft 365 subscription includes an Azure AD tenant.</span></span> <span data-ttu-id="7fd14-107">此租使用者也可以用來管理組織的身分識別與其他雲端工作負載，包括其他的 SaaS 應用程式和 Azure 中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7fd14-107">This tenant can also be used for management of your organization's identities with other cloud workloads, including other SaaS applications and apps in Azure.</span></span>

<span data-ttu-id="7fd14-108">您可以在內部部署伺服器上安裝Azure AD Connect，您也可以因為以下原因將其安裝在 Azure 中的虛擬機器上：</span><span class="sxs-lookup"><span data-stu-id="7fd14-108">You can install Azure AD Connect on a on-premises server, but you can also install it on a virtual machine in Azure for these reasons:</span></span>
  
- <span data-ttu-id="7fd14-109">您可以更快速地佈建和設定雲端架構伺服器，以讓您的使用者可以更早使用服務。</span><span class="sxs-lookup"><span data-stu-id="7fd14-109">You can provision and configure cloud-based servers faster, making the services available to your users sooner.</span></span>
- <span data-ttu-id="7fd14-110">Azure 以更輕鬆的方式提供更佳的網站可用性。</span><span class="sxs-lookup"><span data-stu-id="7fd14-110">Azure offers better site availability with less effort.</span></span>
- <span data-ttu-id="7fd14-111">您可以減少組織中的內部部署伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="7fd14-111">You can reduce the number of on-premises servers in your organization.</span></span>

<span data-ttu-id="7fd14-p102">本解決方案需要內部部署網路與 Azure 虛擬網路之間的連線。如需詳細資訊，請參閱[使內部部署網路與 Microsoft Azure 虛擬網路連線](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p102">This solution requires connectivity between your on-premises network and your Azure virtual network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7fd14-114">本文說明單一樹系中單一網域的同步處理。</span><span class="sxs-lookup"><span data-stu-id="7fd14-114">This article describes synchronization of a single domain in a single forest.</span></span> <span data-ttu-id="7fd14-115">Azure AD Connect 會同步處理 Active Directory 樹系中的所有 AD DS 網域與 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7fd14-115">Azure AD Connect synchronizes all AD DS domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="7fd14-116">如果您有多個 Active Directory 樹系與 Microsoft 365 同步，請參閱 [多樹系目錄同步處理單一 Sign-On 案例](https://go.microsoft.com/fwlink/p/?LinkId=393091)。</span><span class="sxs-lookup"><span data-stu-id="7fd14-116">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span></span> 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a><span data-ttu-id="7fd14-117">在 Azure 中部署 Microsoft 365 目錄同步處理的概覽</span><span class="sxs-lookup"><span data-stu-id="7fd14-117">Overview of deploying Microsoft 365 directory synchronization in Azure</span></span>

<span data-ttu-id="7fd14-118">下圖顯示在 Azure 中的虛擬機器上執行 Azure AD Connect (會將內部部署 AD DS 樹系同步處理至 Microsoft 365 訂閱的目錄同步處理伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="7fd14-118">The following diagram shows Azure AD Connect running on a virtual machine in Azure (the directory sync server) that synchronizes an on-premises AD DS forest to a Microsoft 365 subscription.</span></span>
  
![Azure 中虛擬機器上的 azure AD Connect 工具將內部部署帳戶同步處理至具有流量流量之 Microsoft 365 訂閱的 Azure AD 租使用者。](../media/CP-DirSyncOverview.png)
  
<span data-ttu-id="7fd14-p104">在此圖表中，有兩個使用站對站 VPN 或 ExpressRoute 連線連接的網路。有一個其中存在 AD DS 網域控制器的內部部署網路，和一個 Azure 虛擬網路，其中包含目錄同步處理伺服器 (執行 [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) 的虛擬機器)。從目錄同步處理伺服器會產生二個主要流量：</span><span class="sxs-lookup"><span data-stu-id="7fd14-p104">In the diagram, there are two networks connected by a site-to-site VPN or ExpressRoute connection. There is an on-premises network where AD DS domain controllers are located, and there is an Azure virtual network with a directory sync server, which is a virtual machine running [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). There are two main traffic flows originating from the directory sync server:</span></span>
  
-  <span data-ttu-id="7fd14-123">Azure AD Connect 將內部部署網路上的網域控制器排入佇列，來處理帳戶和密碼的變更。</span><span class="sxs-lookup"><span data-stu-id="7fd14-123">Azure AD Connect queries a domain controller on the on-premises network for changes to accounts and passwords.</span></span>
-  <span data-ttu-id="7fd14-124">Azure AD Connect 會將帳戶和密碼的變更傳送至 Microsoft 365 訂閱的 Azure AD 實例。</span><span class="sxs-lookup"><span data-stu-id="7fd14-124">Azure AD Connect sends the changes to accounts and passwords to the Azure AD instance of your Microsoft 365 subscription.</span></span> <span data-ttu-id="7fd14-125">因為目錄同步處理伺服器位於內部部署網路的擴充部分，所以這些變更會透過內部部署網路的 proxy 伺服器來傳送。</span><span class="sxs-lookup"><span data-stu-id="7fd14-125">Because the directory sync server is in an extended portion of your on-premises network, these changes are sent through the on-premises network's proxy server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7fd14-126">此解決方案說明單一 active Directory 網域在單一 Active Directory 樹系中的同步處理。</span><span class="sxs-lookup"><span data-stu-id="7fd14-126">This solution describes synchronization of a single Active Directory domain, in a single Active Directory forest.</span></span> <span data-ttu-id="7fd14-127">Azure AD Connect 會同步處理 Active Directory 樹系中的所有 Active Directory 網域與 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7fd14-127">Azure AD Connect synchronizes all Active Directory domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="7fd14-128">如果您有多個 Active Directory 樹系與 Microsoft 365 同步，請參閱 [多樹系目錄同步處理單一 Sign-On 案例](https://go.microsoft.com/fwlink/p/?LinkId=393091)。</span><span class="sxs-lookup"><span data-stu-id="7fd14-128">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span></span> 
  
<span data-ttu-id="7fd14-129">部署此解決方案有兩個主要步驟：</span><span class="sxs-lookup"><span data-stu-id="7fd14-129">There are two major steps when you deploy this solution:</span></span>
  
1. <span data-ttu-id="7fd14-p107">建立 Azure 虛擬網路，以及建立您的內部部署網路的站對站 VPN 連線。如需詳細資訊，請參閱＜[使內部部署網路與 Microsoft Azure 虛擬網路連線](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)＞。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p107">Create an Azure virtual network and establish a site-to-site VPN connection to your on-premises network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
    
2. <span data-ttu-id="7fd14-132">在 Azure 中已加入網域的虛擬機器上安裝 [AZURE AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) ，然後將內部部署 AD DS 同步處理至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7fd14-132">Install [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) on a domain-joined virtual machine in Azure, and then synchronize the on-premises AD DS to Microsoft 365.</span></span> <span data-ttu-id="7fd14-133">這包括：</span><span class="sxs-lookup"><span data-stu-id="7fd14-133">This involves:</span></span>
    
    <span data-ttu-id="7fd14-134">建立 Azure 虛擬機器以執行 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="7fd14-134">Creating an Azure Virtual Machine to run Azure AD Connect.</span></span>
    
    <span data-ttu-id="7fd14-135">安裝及設定 [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594)。</span><span class="sxs-lookup"><span data-stu-id="7fd14-135">Installing and configuring [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span></span>
    
    <span data-ttu-id="7fd14-136">若要設定 Azure AD Connect，必須 (Azure AD 系統管理員帳戶和 AD DS 企業系統管理員帳戶的認證使用者名稱和密碼) 。</span><span class="sxs-lookup"><span data-stu-id="7fd14-136">Configuring Azure AD Connect requires the credentials (user name and password) of an Azure AD administrator account and a AD DS enterprise administrator account.</span></span> <span data-ttu-id="7fd14-137">Azure AD Connect 會立即執行，並持續執行，以同步處理內部部署 AD DS 樹系與 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7fd14-137">Azure AD Connect runs immediately and on an ongoing basis to synchronize the on-premises AD DS forest to Microsoft 365.</span></span>
    
<span data-ttu-id="7fd14-138">在生產環境中部署此方案之前，您可以使用 [模擬的企業基本](simulated-ent-base-configuration-microsoft-365-enterprise.md) 設定中的指示，將此設定設為概念證明、示範或實驗。</span><span class="sxs-lookup"><span data-stu-id="7fd14-138">Before you deploy this solution in production, you can use the instructions in [The simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to set this configuration up as a proof of concept, for demonstrations, or for experimentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7fd14-139">當 Azure AD Connect 組態完成時，它不會儲存 AD DS 企業系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="7fd14-139">When Azure AD Connect configuration completes, it does not save the AD DS enterprise administrator account credentials.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7fd14-140">此解決方案說明如何將單一 AD DS 樹系同步處理至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7fd14-140">This solution describes synchronizing a single AD DS forest to Microsoft 365.</span></span> <span data-ttu-id="7fd14-141">本文中所討論的拓撲只是實施此方案的一種方法。</span><span class="sxs-lookup"><span data-stu-id="7fd14-141">The topology discussed in this article represents only one way to implement this solution.</span></span> <span data-ttu-id="7fd14-142">組織的拓撲可能會因您的獨特網路需求和安全性考慮而有所不同。</span><span class="sxs-lookup"><span data-stu-id="7fd14-142">Your organization's topology might differ based on your unique network requirements and security considerations.</span></span> 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a><span data-ttu-id="7fd14-143">針對 Azure 中的 Microsoft 365 主控目錄同步處理伺服器的計畫</span><span class="sxs-lookup"><span data-stu-id="7fd14-143">Plan for hosting a directory sync server for Microsoft 365 in Azure</span></span>
<span data-ttu-id="7fd14-144"><a name="PlanningVirtual"> </a></span><span class="sxs-lookup"><span data-stu-id="7fd14-144"><a name="PlanningVirtual"> </a></span></span>

### <a name="prerequisites"></a><span data-ttu-id="7fd14-145">必要條件</span><span class="sxs-lookup"><span data-stu-id="7fd14-145">Prerequisites</span></span>

<span data-ttu-id="7fd14-146">開始之前，請先檢閱本解決方案的下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="7fd14-146">Before you begin, review the following prerequisites for this solution:</span></span>
  
- <span data-ttu-id="7fd14-147">檢閱＜[規劃您的 Azure 虛擬網路](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network)＞中的相關規劃內容。</span><span class="sxs-lookup"><span data-stu-id="7fd14-147">Review the related planning content in [Plan your Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span></span>
    
- <span data-ttu-id="7fd14-148">確保您符合設定 Azure 虛擬網路的所有[必要條件](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="7fd14-148">Ensure that you meet all [Prerequisites](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) for configuring the Azure virtual network.</span></span>
    
- <span data-ttu-id="7fd14-149">擁有包含 Active Directory 整合功能的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7fd14-149">Have a Microsoft 365 subscription that includes the Active Directory integration feature.</span></span> <span data-ttu-id="7fd14-150">如需 Microsoft 365 訂閱的相關資訊，請移至 [ [microsoft 365 訂閱] 頁面](https://products.office.com/compare-all-microsoft-office-products?tab=2)。</span><span class="sxs-lookup"><span data-stu-id="7fd14-150">For information about Microsoft 365 subscriptions, go to the [Microsoft 365 subscription page](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span></span>
    
- <span data-ttu-id="7fd14-151">布建一個執行 Azure AD Connect 的 Azure 虛擬機器，以同步處理內部部署 AD DS 樹系與 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7fd14-151">Provision one Azure Virtual Machine that runs Azure AD Connect to synchronize your on-premises AD DS forest with Microsoft 365.</span></span>
    
    <span data-ttu-id="7fd14-152">您必須具有 AD DS 企業系統管理員帳戶和 Azure AD 系統管理員帳戶的認證 (名稱和密碼)。</span><span class="sxs-lookup"><span data-stu-id="7fd14-152">You must have the credentials (names and passwords) for a AD DS enterprise administrator account and an Azure AD Administrator account.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="7fd14-153">解決方案架構設計假設</span><span class="sxs-lookup"><span data-stu-id="7fd14-153">Solution architecture design assumptions</span></span>

<span data-ttu-id="7fd14-154">下列清單描述此解決方案所採用的設計選擇。</span><span class="sxs-lookup"><span data-stu-id="7fd14-154">The following list describes the design choices made for this solution.</span></span>
  
- <span data-ttu-id="7fd14-p112">這個解決方案使用具備站對站 VPN 連線的單一 Azure 虛擬網路。Azure 虛擬網路會裝載單一子網路，其具有一部執行 Azure AD Connect 的目錄同步處理伺服器。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p112">This solution uses a single Azure virtual network with a site-to-site VPN connection. The Azure virtual network hosts a single subnet that has one server, the directory sync server that is running Azure AD Connect.</span></span> 
    
- <span data-ttu-id="7fd14-157">在內部部署網路上會有網域控制站和 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7fd14-157">On the on-premises network, a domain controller and DNS servers exist.</span></span>
    
- <span data-ttu-id="7fd14-p113">Azure AD Connect 會執行密碼雜湊同步處理，而非單一登入。您不需要部署 Active Directory 同盟服務 (AD FS) 基礎結構。若要深入了解密碼雜湊同步處理與單一登入選項，請參閱＜[為您的 Azure Active Directory 混合式識別解決方案選擇正確的驗證方法](https://aka.ms/auth-options)＞。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p113">Azure AD Connect performs password hash synchronization instead of single sign-on. You do not have to deploy an Active Directory Federation Services (AD FS) infrastructure. To learn more about password hash synchronization and single sign-on options, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://aka.ms/auth-options).</span></span>
    
<span data-ttu-id="7fd14-p114">在您的環境中部署此解決方案時，您可能會考慮的其他設計選擇。其中包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="7fd14-p114">There are additional design choices that you might consider when you deploy this solution in your environment. These include the following:</span></span>
  
- <span data-ttu-id="7fd14-163">如果現有的 Azure 虛擬網路中有現有的 DNS 伺服器，請判斷您的目錄同步處理伺服器是否要使用它們 (而非使用內部部署網路的 DNS 伺服器) 來進行名稱解析。</span><span class="sxs-lookup"><span data-stu-id="7fd14-163">If there are existing DNS servers in an existing Azure virtual network, determine whether you want your directory sync server to use them for name resolution instead of DNS servers on the on-premises network.</span></span>
    
- <span data-ttu-id="7fd14-p115">如果現有的 Azure 虛擬網路中有網域控制站，請判斷設定 Active Directory 網站及服務是否是較好的選擇。目錄同步處理伺服器可以將 Azure 虛擬網路的網域控制器排入佇列，來處理帳戶和密碼的變更，而非內部部署網路上的網域控制器。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p115">If there are domain controllers in an existing Azure virtual network, determine whether configuring Active Directory Sites and Services may be a better option for you. The directory sync server can query the domain controllers in the Azure virtual network for changes in accounts and passwords instead of domain controllers on the on-premises network.</span></span>
    
## <a name="deployment-roadmap"></a><span data-ttu-id="7fd14-166">部署藍圖</span><span class="sxs-lookup"><span data-stu-id="7fd14-166">Deployment roadmap</span></span>

<span data-ttu-id="7fd14-167">在 Azure 中的虛擬機器上部署 Azure AD Connect 由三個階段所組成：</span><span class="sxs-lookup"><span data-stu-id="7fd14-167">Deploying Azure AD Connect on a virtual machine in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="7fd14-168">階段 1：建立及設定 Azure 虛擬網路</span><span class="sxs-lookup"><span data-stu-id="7fd14-168">Phase 1: Create and configure the Azure virtual network</span></span>
    
- <span data-ttu-id="7fd14-169">階段 2：建立及設定 Azure 虛擬機器</span><span class="sxs-lookup"><span data-stu-id="7fd14-169">Phase 2: Create and configure the Azure virtual machine</span></span>
    
- <span data-ttu-id="7fd14-170">階段 3：安裝及設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="7fd14-170">Phase 3: Install and configure Azure AD Connect</span></span>
    
<span data-ttu-id="7fd14-171">部署之後，您還必須在 Microsoft 365 中為新使用者帳戶指派位置和授權。</span><span class="sxs-lookup"><span data-stu-id="7fd14-171">After deployment, you must also assign locations and licenses for the new user accounts in Microsoft 365.</span></span>


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a><span data-ttu-id="7fd14-172">階段 1：建立及設定 Azure 虛擬網路</span><span class="sxs-lookup"><span data-stu-id="7fd14-172">Phase 1: Create and configure the Azure virtual network</span></span>

<span data-ttu-id="7fd14-173">若要建立及設定 Azure 虛擬網路，請完成＜[使內部部署網路與 Microsoft Azure 虛擬網路連線](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)＞中的＜[階段 1：準備內部部署網路](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network)＞和＜[階段 2：在 Azure 中建立跨單位的虛擬網路](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure)＞。</span><span class="sxs-lookup"><span data-stu-id="7fd14-173">To create and configure the Azure virtual network, complete [Phase 1: Prepare your on-premises network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) and [Phase 2: Create the cross-premises virtual network in Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) in the deployment roadmap of [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
<span data-ttu-id="7fd14-174">這是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="7fd14-174">This is your resulting configuration.</span></span>
  
![Azure 中所主控之 Microsoft 365 目錄同步處理伺服器的階段1](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
<span data-ttu-id="7fd14-176">本圖顯示使用站對站 VPN 或 ExpressRoute 連線方式，連線到 Azure 虛擬網路的內部部署網路。</span><span class="sxs-lookup"><span data-stu-id="7fd14-176">This figure shows an on-premises network connected to an Azure virtual network through a site-to-site VPN or ExpressRoute connection.</span></span>
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a><span data-ttu-id="7fd14-177">階段 2：建立及設定 Azure 虛擬機器</span><span class="sxs-lookup"><span data-stu-id="7fd14-177">Phase 2: Create and configure the Azure virtual machine</span></span>

<span data-ttu-id="7fd14-p116">使用＜[在 Azure 入口網站中建立第一個 Windows 虛擬機器](https://go.microsoft.com/fwlink/p/?LinkId=393098)＞中的指示，在 Azure 中建立虛擬機器。使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="7fd14-p116">Create the virtual machine in Azure using the instructions [Create your first Windows virtual machine in the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098). Use the following settings:</span></span>
  
- <span data-ttu-id="7fd14-p117">在 [基本概念]\*\*\*\* 窗格中，選取相同的訂閱、位置及資源群組做為您的虛擬網路，並在安全位置記錄使用者名稱和密碼。您稍後連線到虛擬機器時會需要這些資訊。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p117">On the **Basics** pane, select the same subscription, location, and resource group as your virtual network. Record the user name and password in a secure location. You will need these later to connect to the virtual machine.</span></span>
    
- <span data-ttu-id="7fd14-183">在 [選擇大小]\*\*\*\* 窗格中，選擇 [A2 標準]\*\*\*\* 大小。</span><span class="sxs-lookup"><span data-stu-id="7fd14-183">On the **Choose a size** pane, choose the **A2 Standard** size.</span></span>
    
- <span data-ttu-id="7fd14-p118">在 [設定]\*\*\*\* 窗格中，請在 [儲存體]\*\*\*\* 區段中，選取 [標準]\*\*\*\* 儲存體類型。在 [網路]\*\*\*\* 區段中，選取您裝載目錄同步處理伺服器 (不是閘道子網路) 的虛擬網路和子網路名稱。其他所有設定都保留預設值。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p118">On the **Settings** pane, in the **Storage** section, select the **Standard** storage type. In the **Network** section, select the name of your virtual network and the subnet for hosting the directory sync server (not the GatewaySubnet). Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="7fd14-187">驗證目錄同步處理伺服器正確使用 DNS，檢查內部 DNS 以確定已使用其 IP 位址，新增虛擬機器的位址 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="7fd14-187">Verify that your directory sync server is using DNS correctly by checking your internal DNS to make sure that an Address (A) record was added for the virtual machine with its IP address.</span></span> 
  
<span data-ttu-id="7fd14-p119">使用[連線到虛擬機器並且登入](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)中的指示，使用遠端桌面連線以連線到目錄同步處理伺服器。登入之後，將虛擬機器加入到內部部署 AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p119">Use the instructions in [Connect to the virtual machine and sign on](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to the directory sync server with a Remote Desktop Connection. After signing in, join the virtual machine to the on-premises AD DS domain.</span></span>
  
<span data-ttu-id="7fd14-p120">若要讓 Azure AD Connect 取得存取網際網路資源的權限，您必須設定目錄同步處理伺服器來使用內部部署網路的 Proxy 伺服器。您應該連絡您的網路系統管理員，以取得需要執行的其他設定步驟。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p120">For Azure AD Connect to gain access to Internet resources, you must configure the directory sync server to use the on-premises network's proxy server. You should contact your network administrator for any additional configuration steps to perform.</span></span>
  
<span data-ttu-id="7fd14-192">這是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="7fd14-192">This is your resulting configuration.</span></span>
  
![Azure 中主控的 Microsoft 365 目錄同步處理伺服器的階段2](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
<span data-ttu-id="7fd14-194">本圖顯示在跨部署 Azure 虛擬網路中的目錄同步處理伺服器虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="7fd14-194">This figure shows the directory sync server virtual machine in the cross-premises Azure virtual network.</span></span>
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a><span data-ttu-id="7fd14-195">階段 3：安裝及設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="7fd14-195">Phase 3: Install and configure Azure AD Connect</span></span>

<span data-ttu-id="7fd14-196">完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="7fd14-196">Complete the following procedure:</span></span>
  
1. <span data-ttu-id="7fd14-p121">透過具有本機系統管理員權限的 AD DS 網域帳戶使用遠端桌面連線，連線到目錄同步處理伺服器。請參閱[連線到虛擬機器並且登入](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p121">Connect to the directory sync server using a Remote Desktop Connection with an AD DS domain account that has local administrator privileges. See [Connect to the virtual machine and sign on](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
    
2. <span data-ttu-id="7fd14-199">在目錄同步處理伺服器中，開啟 [ [設定 Microsoft 365 文章的目錄同步](set-up-directory-synchronization.md) 處理]，並遵循密碼雜湊同步處理的目錄同步處理指示。</span><span class="sxs-lookup"><span data-stu-id="7fd14-199">From the directory sync server, open the [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) article and follow the directions for directory synchronization with password hash synchronization.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="7fd14-p122">安裝程式會在本機使用者組織單位 (OU) 中建立 **AAD_xxxxxxxxxxxx** 帳戶。請勿移動或移除此帳戶，否則同步處理將會失敗。</span><span class="sxs-lookup"><span data-stu-id="7fd14-p122">Setup creates the **AAD_xxxxxxxxxxxx** account in the Local Users organizational unit (OU). Do not move or remove this account or synchronization will fail.</span></span>
  
<span data-ttu-id="7fd14-202">這是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="7fd14-202">This is your resulting configuration.</span></span>
  
![Azure 中所主控之 Microsoft 365 目錄同步處理伺服器的階段3](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
<span data-ttu-id="7fd14-204">本圖顯示在跨部署 Azure 虛擬網路中的 Azure AD Connect 目錄同步處理伺服器。</span><span class="sxs-lookup"><span data-stu-id="7fd14-204">This figure shows the directory sync server with Azure AD Connect in the cross-premises Azure virtual network.</span></span>
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a><span data-ttu-id="7fd14-205">將位置和授權指派給 Microsoft 365 中的使用者</span><span class="sxs-lookup"><span data-stu-id="7fd14-205">Assign locations and licenses to users in Microsoft 365</span></span>

<span data-ttu-id="7fd14-206">Azure AD Connect 會從內部部署 AD DS 將帳戶新增至 Microsoft 365 訂閱，但是為了讓使用者能夠登入 Microsoft 365 並使用其服務，必須使用位置和授權來設定帳戶。</span><span class="sxs-lookup"><span data-stu-id="7fd14-206">Azure AD Connect adds accounts to your Microsoft 365 subscription from the on-premises AD DS, but in order for users to sign in to Microsoft 365 and use its services, the accounts must be configured with a location and licenses.</span></span> <span data-ttu-id="7fd14-207">使用下列步驟為適當的使用者帳戶新增位置和啟用授權：</span><span class="sxs-lookup"><span data-stu-id="7fd14-207">Use these steps to add the location and activate licenses for the appropriate user accounts:</span></span>
  
1. <span data-ttu-id="7fd14-208">登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)，然後按一下 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="7fd14-208">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com), and then click **Admin**.</span></span>
    
2. <span data-ttu-id="7fd14-209">在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7fd14-209">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="7fd14-210">在使用者帳戶清單中，選取您要啟動使用者旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7fd14-210">In the list of user accounts, select the check box next to the user you want to activate.</span></span>
    
4. <span data-ttu-id="7fd14-211">在使用者的頁面上，按一下 [產品授權]\*\*\*\* 的 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7fd14-211">On the page for the user, click **Edit** for **Product licenses**.</span></span>
    
5. <span data-ttu-id="7fd14-212">在 [產品授權]\*\*\*\* 頁面上，為**位置**的使用者選取一個位置，然後為使用者啟用適當授權。</span><span class="sxs-lookup"><span data-stu-id="7fd14-212">On the **Product licenses** page, select a location for the user for **Location**, and then enable the appropriate licenses for the user.</span></span>
    
6. <span data-ttu-id="7fd14-213">完成時，按一下 [儲存]\*\*\*\*，然後按兩下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7fd14-213">When complete, click **Save**, and then click **Close** twice.</span></span>
    
7. <span data-ttu-id="7fd14-214">針對其他使用者回到步驟 3。</span><span class="sxs-lookup"><span data-stu-id="7fd14-214">Go back to step 3 for additional users.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7fd14-215">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7fd14-215">See also</span></span>

[<span data-ttu-id="7fd14-216">Microsoft 365 解決方案與架構中心</span><span class="sxs-lookup"><span data-stu-id="7fd14-216">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)
  
[<span data-ttu-id="7fd14-217">使內部部署網路與 Microsoft Azure 虛擬網路連線</span><span class="sxs-lookup"><span data-stu-id="7fd14-217">Connect an on-premises network to a Microsoft Azure virtual network</span></span>](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[<span data-ttu-id="7fd14-218">下載 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="7fd14-218">Download Azure AD Connect</span></span>](https://www.microsoft.com/download/details.aspx?id=47594)
  
[<span data-ttu-id="7fd14-219">設定 Microsoft 365 的目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="7fd14-219">Set up directory synchronization for Microsoft 365</span></span>](set-up-directory-synchronization.md)
  
