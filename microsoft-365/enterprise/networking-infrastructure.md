---
title: 階段 1：Microsoft 365 企業版的網路基礎結構
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 企業版網路基礎結構的部署步驟。
ms.openlocfilehash: 341e5530b159d4ba78b94001d92427e36224ab04
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631474"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="3460a-103">階段 1：Microsoft 365 企業版的網路基礎結構</span><span class="sxs-lookup"><span data-stu-id="3460a-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![階段 1：網路](../media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="3460a-105">Microsoft 365 企業版包括 Office 365、Microsoft Intune 和許多 Microsoft Azure 的身分識別和安全性服務。</span><span class="sxs-lookup"><span data-stu-id="3460a-105">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="3460a-106">這些所有雲端服務都依賴透過網際網路或專用線路從用戶端裝置連線的安全性、效能及可靠性。</span><span class="sxs-lookup"><span data-stu-id="3460a-106">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="3460a-107">為了裝載這些服務並且讓世界各地的客戶使用，Microsoft 設計了強調效能和整合的網路基礎結構。</span><span class="sxs-lookup"><span data-stu-id="3460a-107">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="3460a-p102">在這個階段，您會逐步探討對 Microsoft 365 企業版雲端服務建立更具效能的連線之關鍵考量。如需概觀，請參閱 [Microsoft 365 網路原則](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)。</span><span class="sxs-lookup"><span data-stu-id="3460a-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Microsoft 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="3460a-110">如果您已部署網路基礎結構，請參閱此階段的[允出準則](networking-exit-criteria.md)，確保其符合 Microsoft 365 企業版的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="3460a-110">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="3460a-111">規劃及部署 Microsoft 365 企業版的網路基礎結構</span><span class="sxs-lookup"><span data-stu-id="3460a-111">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="3460a-112">使用下列步驟為 Microsoft 365 企業版的需求和功能建立您的網路基礎結構。</span><span class="sxs-lookup"><span data-stu-id="3460a-112">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![步驟 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="3460a-114">準備用於 Microsoft 365 的網路</span><span class="sxs-lookup"><span data-stu-id="3460a-114">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![步驟 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="3460a-116">設定每個辦公室的當地網際網路連線</span><span class="sxs-lookup"><span data-stu-id="3460a-116">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![步驟 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="3460a-118">避免網路 hairpin</span><span class="sxs-lookup"><span data-stu-id="3460a-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![步驟 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="3460a-120">設定流量旁路</span><span class="sxs-lookup"><span data-stu-id="3460a-120">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![步驟 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="3460a-122">最佳化用戶端和服務效能</span><span class="sxs-lookup"><span data-stu-id="3460a-122">Optimize client and service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="3460a-123">完成這些步驟之後，請移至此階段的[允出準則](networking-exit-criteria.md)，以確定您符合 Microsoft 365 企業版的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="3460a-123">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="3460a-124">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="3460a-124">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3460a-125">一窺 Microsoft IT 內部，並了解公司如何[針對雲端服務最佳化 Microsoft 網路](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4)。</span><span class="sxs-lookup"><span data-stu-id="3460a-125">Peek inside Microsoft and learn how the company [optimized the Microsoft network for cloud services](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="3460a-126">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="3460a-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3460a-127">看看 Contoso Corporation (虛構但具代表性的跨國企業) 如何為 Microsoft 365 雲端服務[最佳化其網路裝置和網際網路連線](contoso-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="3460a-127">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="3460a-129">下一步</span><span class="sxs-lookup"><span data-stu-id="3460a-129">Next step</span></span>

|||
|:-------|:-----|
|![步驟 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="3460a-131">準備用於 Microsoft 365 的網路</span><span class="sxs-lookup"><span data-stu-id="3460a-131">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

