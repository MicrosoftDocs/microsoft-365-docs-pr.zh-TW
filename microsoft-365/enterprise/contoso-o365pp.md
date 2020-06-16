---
title: 適用於 Contoso 的 Microsoft 365 Apps 企業版部署
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 來部署 Microsoft 365 Apps 企業版。
ms.openlocfilehash: 4a36e33a6f2ef6df880864dd852f0f63056946e6
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679035"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a><span data-ttu-id="161dc-103">適用於 Contoso 的 Microsoft 365 Apps 企業版部署</span><span class="sxs-lookup"><span data-stu-id="161dc-103">Microsoft 365 Apps for enterprise deployment for Contoso</span></span>

<span data-ttu-id="161dc-104">Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience.</span><span class="sxs-lookup"><span data-stu-id="161dc-104">Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience.</span></span> <span data-ttu-id="161dc-105">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span><span class="sxs-lookup"><span data-stu-id="161dc-105">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="161dc-106">所有電腦都應該執行 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="161dc-106">All PCs should run Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="161dc-107">部署應盡可能使用現有管理工具和基礎架構</span><span class="sxs-lookup"><span data-stu-id="161dc-107">Deployment should use existing management tools and infrastructure when possible</span></span>
- <span data-ttu-id="161dc-108">部署必須支援使用者裝置的多種語言及現有基礎架構</span><span class="sxs-lookup"><span data-stu-id="161dc-108">Deployment must support multiple languages and existing architectures on end-user devices</span></span>
- <span data-ttu-id="161dc-109">電腦應在最低 IT 管理成本與對使用者影響最低的情況下，保持最新狀態及安全性</span><span class="sxs-lookup"><span data-stu-id="161dc-109">PCs should stay up-to-date and secure with minimal IT administrative costs and with minimal impact to end-users</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="161dc-110">部署工具</span><span class="sxs-lookup"><span data-stu-id="161dc-110">Deployment tools</span></span>

<span data-ttu-id="161dc-111">Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise with Configuration Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="161dc-111">Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise with Configuration Manager (Current Branch).</span></span> <span data-ttu-id="161dc-112">Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings.</span><span class="sxs-lookup"><span data-stu-id="161dc-112">Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings.</span></span> <span data-ttu-id="161dc-113">It also has built-in features to make it easier and more efficient to deploy and manage Office, including:</span><span class="sxs-lookup"><span data-stu-id="161dc-113">It also has built-in features to make it easier and more efficient to deploy and manage Office, including:</span></span>

- <span data-ttu-id="161dc-114">對等快取，可協助在部署至遠端位置裝置時限制網路流量</span><span class="sxs-lookup"><span data-stu-id="161dc-114">Peer cache, which can help with limited network capacity when deploying to devices in remote locations</span></span>
- <span data-ttu-id="161dc-115">Office 用戶端管理儀表板，讓您更輕鬆地部署 Office 和監控更新，並可讓系統管理員存取最新的部署和管理功能</span><span class="sxs-lookup"><span data-stu-id="161dc-115">The Office Client Management dashboard, which makes it easy to deploy Office and monitor updates and gives administrators access to the latest deployment and management features</span></span>
- <span data-ttu-id="161dc-116">智慧型語言套件部署，包括自動部署與作業系統相同的語言</span><span class="sxs-lookup"><span data-stu-id="161dc-116">Intelligent language pack deployment, including automatically deploying the same language as the operating system</span></span>
- <span data-ttu-id="161dc-117">完整支援並有簡單好用的方法，在部署期間從用戶端移除現有的 Office 版本</span><span class="sxs-lookup"><span data-stu-id="161dc-117">Fully supported and easy-to-use method of removing existing versions of Office from a client during deployment</span></span>

<span data-ttu-id="161dc-118">除了 Configuration Manager，Contoso 也使用「[整備工具組](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)」，此為 Microsoft 提供的免費工具，可用於評估 Office 巨集和增益集的相容性問題。</span><span class="sxs-lookup"><span data-stu-id="161dc-118">In addition to Configuration Manager, Contoso used the [Readiness Toolkit](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), a free tool from Microsoft, to assess compatibility issues with their Office macros and add-ins.</span></span>

## <a name="managing-the-deployment-and-updates"></a><span data-ttu-id="161dc-119">管理部署及更新</span><span class="sxs-lookup"><span data-stu-id="161dc-119">Managing the deployment and updates</span></span>

<span data-ttu-id="161dc-120">Microsoft 365 Apps for enterprise has a new release model: Office as a service.</span><span class="sxs-lookup"><span data-stu-id="161dc-120">Microsoft 365 Apps for enterprise has a new release model: Office as a service.</span></span> <span data-ttu-id="161dc-121">The service model makes it easy to stay up to date with new features, but often requires a change in approach for IT departments in how new releases are deployed and tested.</span><span class="sxs-lookup"><span data-stu-id="161dc-121">The service model makes it easy to stay up to date with new features, but often requires a change in approach for IT departments in how new releases are deployed and tested.</span></span> <span data-ttu-id="161dc-122">To minimize any compatibility issues and to ensure their computers stayed up to date, Contoso deployed Windows and Office in two stages:</span><span class="sxs-lookup"><span data-stu-id="161dc-122">To minimize any compatibility issues and to ensure their computers stayed up to date, Contoso deployed Windows and Office in two stages:</span></span> 

- <span data-ttu-id="161dc-123">For the first stage, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization.</span><span class="sxs-lookup"><span data-stu-id="161dc-123">For the first stage, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization.</span></span> <span data-ttu-id="161dc-124">This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="161dc-124">This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="161dc-125">Contoso 在四個月後解決應用程式、增益集與硬體試驗群組中的所有重大問題， 並將 Microsoft 365 Apps 企業版部署至整個組織的裝置 (大型群組)。</span><span class="sxs-lookup"><span data-stu-id="161dc-125">Four months later, after addressing all critical issues with apps, add-ins, and hardware in the pilot group, Contoso deployed Microsoft 365 Apps for enterprise to the rest of the devices in the organization (the broad group).</span></span> 

<span data-ttu-id="161dc-126">Instead of managing updates to Office with Configuration Manager, Contoso enabled automatic updates from the cloud.</span><span class="sxs-lookup"><span data-stu-id="161dc-126">Instead of managing updates to Office with Configuration Manager, Contoso enabled automatic updates from the cloud.</span></span> <span data-ttu-id="161dc-127">Cloud-based updates reduced their administrative overhead while ensuring the devices stayed up to date.</span><span class="sxs-lookup"><span data-stu-id="161dc-127">Cloud-based updates reduced their administrative overhead while ensuring the devices stayed up to date.</span></span> 

<span data-ttu-id="161dc-128">Contoso followed the same two-stage approach for feature updates that they used for deploying Office: devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group).</span><span class="sxs-lookup"><span data-stu-id="161dc-128">Contoso followed the same two-stage approach for feature updates that they used for deploying Office: devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group).</span></span> <span data-ttu-id="161dc-129">To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-update-channels):</span><span class="sxs-lookup"><span data-stu-id="161dc-129">To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-update-channels):</span></span> 

- <span data-ttu-id="161dc-130">對試驗群組更新的半年通道(預覽)</span><span class="sxs-lookup"><span data-stu-id="161dc-130">Semi-Annual Enterprise Channel (Preview) for updates to the pilot group</span></span> 
- <span data-ttu-id="161dc-131">對大型群組更新的半年企業通道。</span><span class="sxs-lookup"><span data-stu-id="161dc-131">Semi-Annual Enterprise Channel for updates to the broad group.</span></span> 

<span data-ttu-id="161dc-132">由於半年企業通道 (預覽) 比半年企業通道早四個月發行 Microsoft 365 Apps 企業版，因此 Contoso 有時間在無需管理更新下，進型驗證更新。</span><span class="sxs-lookup"><span data-stu-id="161dc-132">Because the Semi-Annual Enterprise Channel (Preview) releases a version of Microsoft 365 Apps for enterprise four months earlier than the Semi-Annual Enterprise Channel, Contoso has time to validate the updates without having to manage them.</span></span> 

## <a name="deployment-process"></a><span data-ttu-id="161dc-133">部署程序</span><span class="sxs-lookup"><span data-stu-id="161dc-133">Deployment process</span></span>

<span data-ttu-id="161dc-134">為了完成 Office 部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：</span><span class="sxs-lookup"><span data-stu-id="161dc-134">To complete the deployment of Office, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="161dc-135">在部署之前，他們會使用「整備工具組」測試的應用程式和 Office 增益集，評估其與 Microsoft 365 Apps 企業版的相容性。</span><span class="sxs-lookup"><span data-stu-id="161dc-135">Before deploying, they used the Readiness Toolkit to test their apps and Office add-ins to assess their compatibility with Microsoft 365 Apps for enterprise.</span></span>
2. <span data-ttu-id="161dc-136">Contoso 啟用 Configuration Manager 的用戶端對等快取，協助在部署至遠端位置的用戶端裝置時限制網路流量。</span><span class="sxs-lookup"><span data-stu-id="161dc-136">In Configuration Manager, Contoso enabled peer cache on their client devices, which helped with limited network capacity when deploying to client devices in remote locations.</span></span> 
3. <span data-ttu-id="161dc-137">They defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group.</span><span class="sxs-lookup"><span data-stu-id="161dc-137">They defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group.</span></span> <span data-ttu-id="161dc-138">The pilot group, which included a small set of representative devices across the organization, was used to do additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span><span class="sxs-lookup"><span data-stu-id="161dc-138">The pilot group, which included a small set of representative devices across the organization, was used to do additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span></span> 
4. <span data-ttu-id="161dc-139">They created deployment packages for Office using the Office Client Management dashboard and the Office 365 Installer wizard, both of which are part of the Configuration Manager console.</span><span class="sxs-lookup"><span data-stu-id="161dc-139">They created deployment packages for Office using the Office Client Management dashboard and the Office 365 Installer wizard, both of which are part of the Configuration Manager console.</span></span> <span data-ttu-id="161dc-140">They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel.</span><span class="sxs-lookup"><span data-stu-id="161dc-140">They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel.</span></span> 
5. <span data-ttu-id="161dc-141">As part of each Office package, they included English, French, and German Language packs.</span><span class="sxs-lookup"><span data-stu-id="161dc-141">As part of each Office package, they included English, French, and German Language packs.</span></span> <span data-ttu-id="161dc-142">If a device required a language not included in the Office package, it was automatically downloaded from the Office Content Delivery Network (CDN).</span><span class="sxs-lookup"><span data-stu-id="161dc-142">If a device required a language not included in the Office package, it was automatically downloaded from the Office Content Delivery Network (CDN).</span></span>
6. <span data-ttu-id="161dc-143">他們先使用 Office 套件中的內建功能自動移除所有現有的 MSI 版本 Office，再安裝 Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="161dc-143">They used the built-in feature in the Office package to automatically remove all existing MSI versions of Office before installing Microsoft 365 Apps for enterprise.</span></span>
7. <span data-ttu-id="161dc-144">他們在 Configuration Manager 中將 Windows 和 Office 套件部署到內部網路中發佈點，然後執行 Configuration Manager 部署工作順序將試驗 Microsoft 365 Apps 企業版套件部署到試驗群組。</span><span class="sxs-lookup"><span data-stu-id="161dc-144">In Configuration Manager, they deployed the Windows and Office packages to distribution points across their network, and then ran the Configuration Manager deployment task sequences to deploy the pilot Microsoft 365 Apps for enterprise package to the pilot group.</span></span>
8. <span data-ttu-id="161dc-145">Contoso 在試驗群組解決任何相容性問題後，即會執行工作順序將各種 Microsoft 365 Apps 企業版套件部署到大型群組。</span><span class="sxs-lookup"><span data-stu-id="161dc-145">After addressing any compatibility issues with the pilot group, Contoso ran the task sequences to deploy the broad Microsoft 365 Apps for enterprise package to the broad group.</span></span>

<span data-ttu-id="161dc-146">因為 Contoso 選擇從雲端自動更新裝置，因此不需要管理 Configuration Manager 中的程序。</span><span class="sxs-lookup"><span data-stu-id="161dc-146">Because Contoso chose to automatically update devices from the cloud, there was no need to manage the process in Configuration Manager.</span></span> <span data-ttu-id="161dc-147">其裝置會根據初始部署時所定義的更新通道，直接從雲端自動進行更新。</span><span class="sxs-lookup"><span data-stu-id="161dc-147">Their devices are automatically updated directly from the cloud-based on the update channel that was defined as part of the initial deployment.</span></span> 

<span data-ttu-id="161dc-148">這是 Contoso Microsoft 365 Apps 企業版安裝和持續更新部署的基礎架構。</span><span class="sxs-lookup"><span data-stu-id="161dc-148">Here is Contoso’s Microsoft 365 Apps for enterprise installation and ongoing updates deployment architecture.</span></span>

![Contoso 的 Microsoft 365 Apps 企業版部署基礎結構](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a><span data-ttu-id="161dc-150">下一步</span><span class="sxs-lookup"><span data-stu-id="161dc-150">Next step</span></span>

<span data-ttu-id="161dc-151">[深入了解](contoso-mdm.md) Contoso 如何在 Microsoft 365 企業版中使用 Microsoft Intune 來管理組織中的裝置與執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="161dc-151">[Learn](contoso-mdm.md) how Contoso is using Microsoft Intune in Microsoft 365 Enterprise to manage its devices and the apps that run on them across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="161dc-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="161dc-152">See also</span></span>

[<span data-ttu-id="161dc-153">適用於 Microsoft 365 企業版的 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="161dc-153">Microsoft 365 Apps for enterprise for Microsoft 365 Enterprise</span></span>](office365proplus-infrastructure.md)

[<span data-ttu-id="161dc-154">部署指南</span><span class="sxs-lookup"><span data-stu-id="161dc-154">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="161dc-155">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="161dc-155">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
