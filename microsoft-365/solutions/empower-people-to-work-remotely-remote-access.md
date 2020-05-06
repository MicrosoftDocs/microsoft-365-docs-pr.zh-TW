---
title: 步驟 2： 可遠端存取內部部署應用程式和服務
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: 請確保您的遠端工作者能夠存取內部部署資源，同時將 Microsoft 365 雲端服務的存取最佳化。
ms.openlocfilehash: daa1a04912dd83c7a53769299b3870b90dbfd33a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049554"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="d2abb-104">步驟 2：</span><span class="sxs-lookup"><span data-stu-id="d2abb-104">Step 2.</span></span> <span data-ttu-id="d2abb-105">可遠端存取內部部署應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="d2abb-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="d2abb-106">如果貴組織使用遠端存取 VPN 解決方案 (通常 VPN 伺服器安裝在網路的邊緣，而 VPN 用戶端則安裝在使用者的裝置上)，您的使用者就可以使用遠端存取 VPN 連線存取內部部署應用程式和伺服器。</span><span class="sxs-lookup"><span data-stu-id="d2abb-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="d2abb-107">但您可能需要將 Microsoft 365 雲端服務的流量最佳化。</span><span class="sxs-lookup"><span data-stu-id="d2abb-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="d2abb-108">如果您的使用者沒有使用 VPN 解決方案，您可以使用 Azure Active Directory (Azure AD) 應用程式 Proxy 和 Azure 點對站台 (P2S) VPN 提供存取權，端視您所有的應用程式是否為 Web 架構而定。</span><span class="sxs-lookup"><span data-stu-id="d2abb-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="d2abb-109">有三種主要設定：</span><span class="sxs-lookup"><span data-stu-id="d2abb-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="d2abb-110">您已經在使用遠端存取 VPN 解決方案。</span><span class="sxs-lookup"><span data-stu-id="d2abb-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="d2abb-111">您沒有使用遠端存取 VPN 解決方案、您有混合式身分識別，而且您只需要遠端存取內部部署的 Web 架構應用程式。</span><span class="sxs-lookup"><span data-stu-id="d2abb-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="d2abb-112">您沒有使用遠端存取 VPN 解決方案、您需要存取內部部署應用程式，而且其中部分應用程式並非 Web 架構。</span><span class="sxs-lookup"><span data-stu-id="d2abb-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="d2abb-113">請參閱此流程圖，了解本文所述的遠端存取設定選項。</span><span class="sxs-lookup"><span data-stu-id="d2abb-113">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![遠端存取設定流程圖](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="d2abb-115">使用遠端存取連線時，您也可以使用[遠端桌面](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop)，將您的使用者連線到內部部署電腦。</span><span class="sxs-lookup"><span data-stu-id="d2abb-115">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="d2abb-116">例如，遠端工作者可以從 Windows、iOS 或 Android 裝置，使用遠端桌面連線到其辦公室中的電腦。</span><span class="sxs-lookup"><span data-stu-id="d2abb-116">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="d2abb-117">從遠端連線之後，他們就可以像坐在電腦前面一樣使用電腦。</span><span class="sxs-lookup"><span data-stu-id="d2abb-117">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="d2abb-118">針對 Microsoft 365 雲端服務，將遠端存取 VPN 用戶端的效能最佳化</span><span class="sxs-lookup"><span data-stu-id="d2abb-118">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="d2abb-119">如果您的遠端工作者使用傳統的 VPN 用戶端取得貴組織網路的遠端存取權，請確認 VPN 用戶端支援分割通道。</span><span class="sxs-lookup"><span data-stu-id="d2abb-119">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="d2abb-120">如果沒有分割通道，您所有的遠端工作流量都會透過 VPN 連線傳送，其中必須先將流量轉送給貴組織的邊緣裝置、進行處理，然後透過網際網路傳送。</span><span class="sxs-lookup"><span data-stu-id="d2abb-120">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![來自 VPN 用戶端的網路流量 (不含通道)](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="d2abb-122">Microsoft 365 流量必須透過貴組織進行間接路由，這可能是從距離 VPN 用戶端實體位置很遠的位置轉送到 Microsoft 網路進入點。</span><span class="sxs-lookup"><span data-stu-id="d2abb-122">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="d2abb-123">這種間接路徑可增加網路流量的延遲，並降低整體效能。</span><span class="sxs-lookup"><span data-stu-id="d2abb-123">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="d2abb-124">您可以利用分割通道設定 VPN 用戶端，以排除透過 VPN 連線傳送到組織網路的特定類型流量。</span><span class="sxs-lookup"><span data-stu-id="d2abb-124">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="d2abb-125">若要將 Microsoft 365 雲端資源的存取最佳化，請設定分割通道 VPN 用戶端，排除透過 VPN 連線到**最佳化**類別 Microsoft 365 端點的流量。</span><span class="sxs-lookup"><span data-stu-id="d2abb-125">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="d2abb-126">如需詳細資訊，請參閱 [Office 365 端點類別](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="d2abb-126">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="d2abb-127">請參閱[這裡](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)的最佳化類別端點清單。</span><span class="sxs-lookup"><span data-stu-id="d2abb-127">See the list of Optimize category endpoints [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

![來自 VPN 用戶端的網路流量 (含通道)](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="d2abb-129">如此可讓 VPN 用戶端直接透過網際網路傳送和接收重要的 Microsoft 365 雲端服務流量，並透過最接近的進入點到 Microsoft 網路。</span><span class="sxs-lookup"><span data-stu-id="d2abb-129">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="d2abb-130">如需詳細資訊和指導方針，請參閱[使用 VPN 分割通道將遠端使用者的 Office 365 連線能力最佳化](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)。</span><span class="sxs-lookup"><span data-stu-id="d2abb-130">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="d2abb-131">當您的所有應用程式都為 Web 應用程式且您擁有混合式身分識別時，部署遠端存取</span><span class="sxs-lookup"><span data-stu-id="d2abb-131">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="d2abb-132">如果您的遠端工作者並未使用傳統的 VPN 用戶端，且您的內部部署使用者帳戶和群組已與 Azure AD 同步處理，則您可以使用 Azure AD 應用程式 Proxy，為內部網路伺服器上託管的 Web 架構應用程式，提供安全的遠端存取。</span><span class="sxs-lookup"><span data-stu-id="d2abb-132">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="d2abb-133">Web 架構應用程式包括 SharePoint 網站、Outlook Web Access 伺服器或其他任何 Web 架構企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="d2abb-133">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="d2abb-134">以下是 Azure AD 應用程式 Proxy 的元件。</span><span class="sxs-lookup"><span data-stu-id="d2abb-134">Here are the components of Azure AD Application Proxy.</span></span>

![Azure AD 應用程式 Proxy 的元件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="d2abb-136">如需詳細資訊，請參閱這個 [Azure AD 應用程式 Proxy 概觀](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="d2abb-136">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="d2abb-137">並非所有應用程式都是 Web 應用程式時，部署遠端存取</span><span class="sxs-lookup"><span data-stu-id="d2abb-137">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="d2abb-138">如果您的遠端工作者並未使用傳統的 VPN 用戶端，且您的任何應用程式都不是 Web 架構，則您可以使用 Azure 點對站台 (P2S) VPN。</span><span class="sxs-lookup"><span data-stu-id="d2abb-138">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="d2abb-139">P2S VPN 連線會透過 Azure 虛擬網路，建立遠端工作者裝置到貴組織網路的安全連線。</span><span class="sxs-lookup"><span data-stu-id="d2abb-139">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Azure P2S VPN 的元件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="d2abb-141">如需詳細資訊，請參閱這個 [P2S VPN 概觀](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="d2abb-141">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="d2abb-142">部署 Windows 虛擬桌面，以便為使用個人裝置的遠端工作者提供遠端存取</span><span class="sxs-lookup"><span data-stu-id="d2abb-142">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="d2abb-143">為支援只能使用其個人和非受管理裝置的遠端工作者，請使用 Azure 中的 Windows 虛擬桌面建立並配置虛擬桌面，讓您的使用者可以在家使用。</span><span class="sxs-lookup"><span data-stu-id="d2abb-143">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span>

<span data-ttu-id="d2abb-144">虛擬化的電腦可以充當連線至貴組織網路的電腦使用。</span><span class="sxs-lookup"><span data-stu-id="d2abb-144">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

<span data-ttu-id="d2abb-145">如需詳細資訊，請參閱這個 [Windows 虛擬桌面的概觀](https://docs.microsoft.com/azure/virtual-desktop/overview)。</span><span class="sxs-lookup"><span data-stu-id="d2abb-145">For more information, see [this overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="d2abb-146">適用於遠端存取的系統管理技術資源</span><span class="sxs-lookup"><span data-stu-id="d2abb-146">Admin technical resources for remote access</span></span>

- <span data-ttu-id="d2abb-147">[如何快速優化遠端員工的 Office 365 流量，並降低基礎結構負載](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571) (英文)</span><span class="sxs-lookup"><span data-stu-id="d2abb-147">[How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)</span></span>
- [<span data-ttu-id="d2abb-148">使用 VPN 分割通道將遠端使用者的 Office 365 連線能力最佳化</span><span class="sxs-lookup"><span data-stu-id="d2abb-148">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="d2abb-149">步驟 2 的結果</span><span class="sxs-lookup"><span data-stu-id="d2abb-149">Results of Step 2</span></span>

<span data-ttu-id="d2abb-150">為您的遠端工作者部署遠端存取解決方案之後：</span><span class="sxs-lookup"><span data-stu-id="d2abb-150">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="d2abb-151">遠端存取設定</span><span class="sxs-lookup"><span data-stu-id="d2abb-151">Remote access configuration</span></span> | <span data-ttu-id="d2abb-152">結果</span><span class="sxs-lookup"><span data-stu-id="d2abb-152">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="d2abb-153">遠端存取 VPN 解決方案已就緒</span><span class="sxs-lookup"><span data-stu-id="d2abb-153">A remote access VPN solution is in place</span></span> | <span data-ttu-id="d2abb-154">您已經針對分割通道以及 Microsoft 365 端點的最佳化類別，設定您的遠端存取 VPN 用戶端。</span><span class="sxs-lookup"><span data-stu-id="d2abb-154">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="d2abb-155">沒有遠端存取 VPN 解決方案，而且您只需要遠端存取內部部署的 Web 架構應用程式</span><span class="sxs-lookup"><span data-stu-id="d2abb-155">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="d2abb-156">您已經設定 Azure 應用程式 Proxy。</span><span class="sxs-lookup"><span data-stu-id="d2abb-156">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="d2abb-157">沒有遠端存取 VPN 解決方案、您需要存取內部部署應用程式，而且其中部分應用程式並非 Web 架構</span><span class="sxs-lookup"><span data-stu-id="d2abb-157">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="d2abb-158">您已經設定 Azure P2S VPN。</span><span class="sxs-lookup"><span data-stu-id="d2abb-158">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="d2abb-159">遠端工作者正在家中使用其個人裝置</span><span class="sxs-lookup"><span data-stu-id="d2abb-159">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="d2abb-160">您已經設定 Windows 虛擬桌面。</span><span class="sxs-lookup"><span data-stu-id="d2abb-160">You have configured Windows Virtual Desktop.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="d2abb-161">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d2abb-161">Next step</span></span>

<span data-ttu-id="d2abb-162">繼續執行[步驟 3](empower-people-to-work-remotely-manage-endpoints.md) 以管理裝置、電腦及其他端點。</span><span class="sxs-lookup"><span data-stu-id="d2abb-162">Continue with [Step 3](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
