---
title: Contoso 的 COVID-19 回應及支援混合式工作
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 瞭解 Contoso Corporation 如何回應 COVID-19 pandemic，並將其軟體安裝和更新基礎結構用於混合式工作。
ms.openlocfilehash: 2d28b0513221f6c14526baba69bf0f5986154805
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788376"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a><span data-ttu-id="ff542-103">Contoso 的 COVID-19 回應及支援混合式工作</span><span class="sxs-lookup"><span data-stu-id="ff542-103">Contoso's COVID-19 response and support for hybrid work</span></span>

<span data-ttu-id="ff542-104">Contoso 永遠支援其遠端工作者，該員工是透過巴黎總部的中央 VPN 伺服器來存取內部部署資源。</span><span class="sxs-lookup"><span data-stu-id="ff542-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="ff542-105">Contoso 已頒佈所有的遠端工作者為受管理的膝上型電腦。</span><span class="sxs-lookup"><span data-stu-id="ff542-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="ff542-106">內部部署工作者會混合使用桌上型電腦和可擕式電腦。</span><span class="sxs-lookup"><span data-stu-id="ff542-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="ff542-107">Contoso 對 COVID-19 的回應</span><span class="sxs-lookup"><span data-stu-id="ff542-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="ff542-108">使用 COVID-19 pandemic 的 onset，就會突然，但所有重要工作者都是遠端工作者。</span><span class="sxs-lookup"><span data-stu-id="ff542-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="ff542-109">Contoso 會透過將其員工轉變為在家中運作，並使用 Microsoft 365 雲端服務對內部部署資源和線上執行主要活動，以作出回應。</span><span class="sxs-lookup"><span data-stu-id="ff542-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="ff542-110">Contoso 擁有位於巴黎總部辦公室的遠端存取 VPN 伺服器，可支援25% 的遠端員工，但快速移動以擴充其遠端存取能力，以支援其工作力的90%。</span><span class="sxs-lookup"><span data-stu-id="ff542-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="ff542-111">Contoso 在每個衛星辦公室中部署遠端存取 VPN 伺服器，讓遠端工作者使用地區 close 進入點來存取 Contoso 內部網路。</span><span class="sxs-lookup"><span data-stu-id="ff542-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="ff542-112">Contoso 也會更新安裝在膝上型電腦、平板電腦及智慧型電話上分割隧道的 VPN 用戶端設定，讓 Office 365 的優化集合的流量繞過 VPN 連線，並透過網際網路直接傳送。</span><span class="sxs-lookup"><span data-stu-id="ff542-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="ff542-113">如需詳細資訊，請參閱[Optimize Office 365 connectivity for 使用 VPN 分割隧道的遠端使用者](../enterprise/microsoft-365-vpn-split-tunnel.md)。</span><span class="sxs-lookup"><span data-stu-id="ff542-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="ff542-114">以下是安裝于巴黎總部及每個衛星辦公室中的 VPN 裝置所產生的設定。</span><span class="sxs-lookup"><span data-stu-id="ff542-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Contoso 的 VPN 基礎結構](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

<span data-ttu-id="ff542-116">安裝了 VPN 用戶端的遠端工作者會使用 DNS 來尋找地區最接近的 office，並連接到此處安裝的 VPN 裝置。</span><span class="sxs-lookup"><span data-stu-id="ff542-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="ff542-117">透過分割隧道，Microsoft 365 的流量優化端點會直接傳送至最近 Microsoft 365 網路位置的地區。</span><span class="sxs-lookup"><span data-stu-id="ff542-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="ff542-118">其他所有流量都會透過 VPN 連線傳送至 VPN 裝置。</span><span class="sxs-lookup"><span data-stu-id="ff542-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-hybrid-work"></a><span data-ttu-id="ff542-119">Contoso 對混合式工作的支援</span><span class="sxs-lookup"><span data-stu-id="ff542-119">Contoso’s support for hybrid work</span></span>

<span data-ttu-id="ff542-120">在地區鎖定期間，為了支援大多數的遠端工作者所做的初步變更之後，Contoso 進行基礎結構變更，以支援工作人員可以執行的混合式工作：</span><span class="sxs-lookup"><span data-stu-id="ff542-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support hybrid work in which a worker could be:</span></span>

- <span data-ttu-id="ff542-121">Always remote。</span><span class="sxs-lookup"><span data-stu-id="ff542-121">Always remote.</span></span>
- <span data-ttu-id="ff542-122">永遠在現場。</span><span class="sxs-lookup"><span data-stu-id="ff542-122">Always onsite.</span></span>
- <span data-ttu-id="ff542-123">現場和遠端的組合。</span><span class="sxs-lookup"><span data-stu-id="ff542-123">A combination of onsite and remote.</span></span>

<span data-ttu-id="ff542-124">Microsoft 365 身分識別、安全性和符合性功能是針對零信任而設計，不論使用者及其裝置的位置為何，都能運作。</span><span class="sxs-lookup"><span data-stu-id="ff542-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="ff542-125">如需詳細資訊，請參閱 [零信任](https://www.microsoft.com/security/business/zero-trust)。</span><span class="sxs-lookup"><span data-stu-id="ff542-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="ff542-126">不過，管理軟體的新安裝和更新取決於裝置的位置，因為安裝的軟體可能來自內部部署或網際網路來源。</span><span class="sxs-lookup"><span data-stu-id="ff542-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="ff542-127">Contoso IT 架構設計其新安裝和更新基礎結構，而不是以設備的位置，而是根據工作者的位置。</span><span class="sxs-lookup"><span data-stu-id="ff542-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="ff542-128">其指定了兩種裝置類型：專用的內部部署和漫遊。</span><span class="sxs-lookup"><span data-stu-id="ff542-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="ff542-129">專用的內部部署</span><span class="sxs-lookup"><span data-stu-id="ff542-129">Dedicated on-premises</span></span>

<span data-ttu-id="ff542-130">專用的內部部署裝置是一部桌面或伺服器電腦，永遠不會離開 Contoso 內部網路，也不會安裝 VPN 用戶端。</span><span class="sxs-lookup"><span data-stu-id="ff542-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="ff542-131">這些內部部署裝置會繼續使用 Microsoft Endpoint Configuration Manager 和其發佈點來安裝及更新 Windows 10、Microsoft 365 Apps 企業版和 Edge browser。</span><span class="sxs-lookup"><span data-stu-id="ff542-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="ff542-132">漫遊</span><span class="sxs-lookup"><span data-stu-id="ff542-132">Roaming</span></span>

<span data-ttu-id="ff542-133">漫遊裝置可以留下 Contoso 內部網路，並包含發給許多 office 工作者的膝上型電腦，以及所有遠端工作者及其他組織所擁有的裝置，例如已安裝 Contoso VPN 用戶端的智慧型電話和平板電腦。</span><span class="sxs-lookup"><span data-stu-id="ff542-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="ff542-134">因為這些裝置可在任何時間連接至網際網路，所以他們會使用 Intune 或其他雲端架構服務來安裝及更新 Windows 10、Microsoft 365 Apps 企業版和 Edge。</span><span class="sxs-lookup"><span data-stu-id="ff542-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="ff542-135">它們不使用現有的內部部署 Configuration Manager 發佈點。</span><span class="sxs-lookup"><span data-stu-id="ff542-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="ff542-136">這表示漫遊裝置的部分安裝和更新會在 internet 內部部署並聯機至內部網路時進行。</span><span class="sxs-lookup"><span data-stu-id="ff542-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="ff542-137">但是，Contoso IT 架構師決定簡易性設定比對網際網路內部網路頻寬的優化更為重要，尤其是當大多數的遠端工作者很少連接至內部網路時。</span><span class="sxs-lookup"><span data-stu-id="ff542-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="ff542-138">以下是所產生的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="ff542-138">Here is the resulting infrastructure.</span></span>

![Contoso 的安裝和更新基礎結構](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

<span data-ttu-id="ff542-140">安裝和更新行為是透過讓裝置的電腦帳戶成為其中一個群組的成員來決定：</span><span class="sxs-lookup"><span data-stu-id="ff542-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="ff542-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="ff542-141">OnPremDevices</span></span>

  <span data-ttu-id="ff542-142">裝置上的 Configuration Manager 用戶端使用發佈點來進行安裝和更新。</span><span class="sxs-lookup"><span data-stu-id="ff542-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="ff542-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="ff542-143">RoamingDevices</span></span>

  <span data-ttu-id="ff542-144">Intune 和裝置上的其他設定會指定使用 Microsoft 365 網路進行安裝和更新。</span><span class="sxs-lookup"><span data-stu-id="ff542-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="ff542-145">新的上架過程</span><span class="sxs-lookup"><span data-stu-id="ff542-145">New onboarding process</span></span>

<span data-ttu-id="ff542-146">針對新的工作人員或資料中心內新伺服器發佈的新專屬內部部署裝置，當工作者登入時，會根據 OnPremDevices 群組中裝置的成員資格，從內部部署 Configuration manager 發佈點下載並安裝 Windows 10、Microsoft 365 Apps 企業版和 Edge 的最新更新。</span><span class="sxs-lookup"><span data-stu-id="ff542-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="ff542-147">完成時，專用的內部部署裝置可供使用，並使用這些發佈點進行持續更新。</span><span class="sxs-lookup"><span data-stu-id="ff542-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="ff542-148">針對發佈給新工作者的新遠端裝置，當工作者登入時，裝置會根據其在 RoamingDevices 群組中的成員資格，聯繫 Intune 雲端服務和其他服務，並為 Windows 10、Microsoft 365 Apps 企業版和 Edge 安裝最新的更新。</span><span class="sxs-lookup"><span data-stu-id="ff542-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="ff542-149">完成時，遠端裝置可供使用，並使用已安裝的 VPN 用戶端來存取內部部署資源和 Microsoft 365 網路，以進行持續更新。</span><span class="sxs-lookup"><span data-stu-id="ff542-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="ff542-150">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ff542-150">Next step</span></span>

<span data-ttu-id="ff542-151">[設定您組織中的混合式工作基礎結構](empower-people-to-work-remotely.md) 。</span><span class="sxs-lookup"><span data-stu-id="ff542-151">[Set up your infrastructure for hybrid work](empower-people-to-work-remotely.md) in your organization.</span></span>
