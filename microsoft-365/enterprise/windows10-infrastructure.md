---
title: Microsoft 365 企業版的 Windows 10 企業版基礎結構
description: 提供在 Microsoft 365 Enterprise 的一部分上部署 Windows 10 企業版時所需步驟的高階指導方針。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 檔，Windows 10 企業版，部署
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 3b4a0174e96fec1591bcac7ba58bcc7d57db8c87
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552683"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="85c8e-104">階段 3：Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="85c8e-104">Phase 3: Windows 10 Enterprise</span></span>

![階段 3：Windows 10 企業版](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="85c8e-106">Microsoft 365 Enterprise 包含 Windows 10 企業版，可讓您執行更多和保持安全的工具。</span><span class="sxs-lookup"><span data-stu-id="85c8e-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="85c8e-107">Windows 10 企業版：</span><span class="sxs-lookup"><span data-stu-id="85c8e-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="85c8e-108">**已整合，以簡化**雲端的功能，協助降低管理當今現代 IT 裝置環境的複雜性，不論大小為何。</span><span class="sxs-lookup"><span data-stu-id="85c8e-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="85c8e-109">**具有智慧安全性**-它是最安全的 Windows 版本，其設計目的在於搭配搭配使用的智慧安全性功能，以更好地保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="85c8e-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="85c8e-110">**可讓創造性和團隊合作**-解除其創造力和團隊合作，以提供使用者最喜歡的工作效率。</span><span class="sxs-lookup"><span data-stu-id="85c8e-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="85c8e-111">您必須瞭解部署 Windows 10 作業系統的不同方式，並為您的組織選擇適當的方式。</span><span class="sxs-lookup"><span data-stu-id="85c8e-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="85c8e-112">視您的 Microsoft 365 Enterprise 訂閱而定，您需要設定 Windows 10 服務和安全性功能，以充分利用 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="85c8e-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="85c8e-113">若要同時部署 Windows 10 企業版和 Microsoft 365 應用程式，並移至[新式桌面](https://www.microsoft.com/microsoft-365/modern-desktop)，請參閱[新式桌面部署中心](https://aka.ms/howtoshift)。</span><span class="sxs-lookup"><span data-stu-id="85c8e-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="85c8e-114">Windows 10 部署</span><span class="sxs-lookup"><span data-stu-id="85c8e-114">Windows 10 deployment</span></span>

<span data-ttu-id="85c8e-115">您可以利用多種方式，為組織部署 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="85c8e-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="85c8e-116">在這裡，我們將重點講述如何透過這些新式部署案例來設定及部署 Windows 10 企業版映射。</span><span class="sxs-lookup"><span data-stu-id="85c8e-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="85c8e-117">部署案例</span><span class="sxs-lookup"><span data-stu-id="85c8e-117">Deployment scenario</span></span> | <span data-ttu-id="85c8e-118">何時使用</span><span class="sxs-lookup"><span data-stu-id="85c8e-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="85c8e-119">使用 Microsoft 端點 Configuration Manager 做為就地升級</span><span class="sxs-lookup"><span data-stu-id="85c8e-119">Using Microsoft Endpoint Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="85c8e-120">如果您需要將 Windows 7 或 Windows 8.1 電腦升級至目前 Windows 10 企業<a href="https://aka.ms/windows-10-release-information" target="_blank">版</a>，且您的電腦目前是使用<a href="https://docs.microsoft.com/mem/configmgr/core/understand/introduction" target="_blank">Configuration Manager (目前分支) </a>進行管理，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="85c8e-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://docs.microsoft.com/mem/configmgr/core/understand/introduction" target="_blank">Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="85c8e-121">使用 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="85c8e-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="85c8e-122">如果您要設定的新 Windows 電腦具有 Windows 10 企業版、版本1703或更新版本，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="85c8e-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="85c8e-123">使用者可輸入其工作或學校帳戶的認證，以使用您所需的設定來啟動設定。</span><span class="sxs-lookup"><span data-stu-id="85c8e-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="85c8e-124">如果這些部署案例不符合您組織的需求，則可以深入瞭解其他案例，並瞭解每個[Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的功能和限制。</span><span class="sxs-lookup"><span data-stu-id="85c8e-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="85c8e-125">您也可以自行<a href="https://aka.ms/planforwin10deployment" target="_blank">規劃 Windows 10 部署</a>。</span><span class="sxs-lookup"><span data-stu-id="85c8e-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="85c8e-126">您可以使用下列文章深入瞭解 Windows 10：</span><span class="sxs-lookup"><span data-stu-id="85c8e-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="85c8e-127">Microsoft 365 Enterprise 產品頁面</span><span class="sxs-lookup"><span data-stu-id="85c8e-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="85c8e-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="85c8e-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="85c8e-129">部署及更新 Windows 10</span><span class="sxs-lookup"><span data-stu-id="85c8e-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="85c8e-130">其他服務和功能</span><span class="sxs-lookup"><span data-stu-id="85c8e-130">Additional services and features</span></span>
<span data-ttu-id="85c8e-131">在 Windows 10 企業版部署的一部分中，您可以新增這些額外的服務和功能。</span><span class="sxs-lookup"><span data-stu-id="85c8e-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="desktop-analytics"></a><span data-ttu-id="85c8e-132">電腦分析</span><span class="sxs-lookup"><span data-stu-id="85c8e-132">Desktop Analytics</span></span>

<span data-ttu-id="85c8e-133">Windows 會使用診斷資料，提供豐富的可運作資訊，協助您深入瞭解作業效率，以及環境中 Windows 10 裝置的健康情況。</span><span class="sxs-lookup"><span data-stu-id="85c8e-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="85c8e-134">升級準備情況-升級準備可協助您移至 Windows 10，並以新的 Windows 10 功能更新保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="85c8e-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="85c8e-135">更新規範-更新規範是針對想要深入瞭解所有 Windows 10 裝置的 IT 系統管理員，不需要任何其他基礎結構需求。</span><span class="sxs-lookup"><span data-stu-id="85c8e-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="85c8e-136">裝置健康情況-您可以使用裝置健康情況，主動偵測和修正使用者影響的問題。</span><span class="sxs-lookup"><span data-stu-id="85c8e-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="85c8e-137">如需詳細資訊，請參閱[桌面 Analytics 一覽](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)。</span><span class="sxs-lookup"><span data-stu-id="85c8e-137">See [Desktop Analytics Overview](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="85c8e-138">Windows 安全性</span><span class="sxs-lookup"><span data-stu-id="85c8e-138">Windows security</span></span>

<span data-ttu-id="85c8e-139">Windows 10 提供的功能可協助防範威脅、協助您保護裝置，以及協助您進行存取控制。</span><span class="sxs-lookup"><span data-stu-id="85c8e-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="85c8e-140">使用 Windows 10 時，您會獲得重要的安全性功能，可在啟動時立即保護您的裝置。</span><span class="sxs-lookup"><span data-stu-id="85c8e-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="85c8e-141">Microsoft 365 E3 新增諸如 Windows Hello 企業版、Windows Defender 應用程式控制和 Windows 資訊保護等安全性功能。</span><span class="sxs-lookup"><span data-stu-id="85c8e-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="85c8e-142">使用 Microsoft 365 E5，您可以從 Microsoft 365 E3 安全性加上雲端式安全性功能和 Microsoft Defender 高級威脅防護，獲得所有保護。</span><span class="sxs-lookup"><span data-stu-id="85c8e-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="85c8e-143">若要深入瞭解使用 Windows 10 Enterprise 所獲得的安全性功能，並取得如何部署、管理、設定及疑難排解三項重要安全性功能的指導，請參閱「[步驟5：部署 Windows 10 企業版安全性功能](windows10-enable-security-features.md)」。</span><span class="sxs-lookup"><span data-stu-id="85c8e-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key security features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="85c8e-144">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="85c8e-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="85c8e-145">在 Microsoft 內部進行查看，並瞭解公司如何[部署 Windows 10 企業版，以及如何使用強大的驗證、Intune 和 Microsoft DEFENDER ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6)。</span><span class="sxs-lookup"><span data-stu-id="85c8e-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="85c8e-146">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="85c8e-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="85c8e-147">請參閱 Contoso Corporation （虛構但有代表性的跨國企業）如何[部署 Windows 10 企業版](contoso-win10.md)。</span><span class="sxs-lookup"><span data-stu-id="85c8e-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="85c8e-149">下一步</span><span class="sxs-lookup"><span data-stu-id="85c8e-149">Next step</span></span>

|||
|:-------|:-----|
|![步驟 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="85c8e-151">為 Windows 10 企業版準備您的組織</span><span class="sxs-lookup"><span data-stu-id="85c8e-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
