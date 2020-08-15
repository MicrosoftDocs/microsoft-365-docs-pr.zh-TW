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
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 來部署 Microsoft 365 Apps 企業版。
ms.openlocfilehash: de6a5348a49a490afa3c3ac632e66026966e2ef3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695155"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a><span data-ttu-id="8a530-103">適用於 Contoso 的 Microsoft 365 Apps 企業版部署</span><span class="sxs-lookup"><span data-stu-id="8a530-103">Microsoft 365 Apps for enterprise deployment for Contoso</span></span>

<span data-ttu-id="8a530-p101">Contoso 將其電腦升級至 Windows 10 企業版和 Microsoft 365 Apps 企業版，讓協同合作更有效率、更佳的安全性，以及更現代化的桌面體驗。Contoso 在評估基礎架構和業務需求後，識別這些部署的關鍵需求：</span><span class="sxs-lookup"><span data-stu-id="8a530-p101">Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience. After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="8a530-106">所有電腦都應該執行 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="8a530-106">All PCs should run Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="8a530-107">部署應盡可能使用現有管理工具和基礎架構</span><span class="sxs-lookup"><span data-stu-id="8a530-107">Deployment should use existing management tools and infrastructure when possible</span></span>
- <span data-ttu-id="8a530-108">部署必須支援使用者裝置的多種語言及現有基礎架構</span><span class="sxs-lookup"><span data-stu-id="8a530-108">Deployment must support multiple languages and existing architectures on end-user devices</span></span>
- <span data-ttu-id="8a530-109">電腦應在最低 IT 管理成本與對使用者影響最低的情況下，保持最新狀態及安全性</span><span class="sxs-lookup"><span data-stu-id="8a530-109">PCs should stay up-to-date and secure with minimal IT administrative costs and with minimal impact to end-users</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="8a530-110">部署工具</span><span class="sxs-lookup"><span data-stu-id="8a530-110">Deployment tools</span></span>

<span data-ttu-id="8a530-p102">Contoso 根據自身需求，選擇以 Configuration Manager (最新分支) 部署 Windows 10 企業版和 Microsoft 365 Apps 企業版。Configuration Manager 可針對大型環境進行調整並提供安裝、更新及設定的全面控制，其內建功能更讓您可輕鬆且有效率地部署及管理 Office，包括：</span><span class="sxs-lookup"><span data-stu-id="8a530-p102">Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise with Configuration Manager (Current Branch). Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Office, including:</span></span>

- <span data-ttu-id="8a530-114">對等快取，可協助在部署至遠端位置裝置時限制網路流量</span><span class="sxs-lookup"><span data-stu-id="8a530-114">Peer cache, which can help with limited network capacity when deploying to devices in remote locations</span></span>
- <span data-ttu-id="8a530-115">Office 用戶端管理儀表板，讓您更輕鬆地部署 Office 和監控更新，並可讓系統管理員存取最新的部署和管理功能</span><span class="sxs-lookup"><span data-stu-id="8a530-115">The Office Client Management dashboard, which makes it easy to deploy Office and monitor updates and gives administrators access to the latest deployment and management features</span></span>
- <span data-ttu-id="8a530-116">智慧型語言套件部署，包括自動部署與作業系統相同的語言</span><span class="sxs-lookup"><span data-stu-id="8a530-116">Intelligent language pack deployment, including automatically deploying the same language as the operating system</span></span>
- <span data-ttu-id="8a530-117">完整支援並有簡單好用的方法，在部署期間從用戶端移除現有的 Office 版本</span><span class="sxs-lookup"><span data-stu-id="8a530-117">Fully supported and easy-to-use method of removing existing versions of Office from a client during deployment</span></span>

<span data-ttu-id="8a530-118">除了 Configuration Manager，Contoso 也使用「[整備工具組](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)」，此為 Microsoft 提供的免費工具，可用於評估 Office 巨集和增益集的相容性問題。</span><span class="sxs-lookup"><span data-stu-id="8a530-118">In addition to Configuration Manager, Contoso used the [Readiness Toolkit](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), a free tool from Microsoft, to assess compatibility issues with their Office macros and add-ins.</span></span>

## <a name="managing-the-deployment-and-updates"></a><span data-ttu-id="8a530-119">管理部署及更新</span><span class="sxs-lookup"><span data-stu-id="8a530-119">Managing the deployment and updates</span></span>

<span data-ttu-id="8a530-p103">Microsoft 365 Apps 企業版有新的發行模式：Office 即服務。此服務模式能讓您輕鬆掌握最新功能，但通常需要 IT 部門變更新版本的部署和測試方式。為了將相容性問題降至最低並確保電腦為最新狀態，Contoso 以兩個階段部署 Windows 和 Office：</span><span class="sxs-lookup"><span data-stu-id="8a530-p103">Microsoft 365 Apps for enterprise has a new release model: Office as a service. The service model makes it easy to stay up to date with new features, but often requires a change in approach for IT departments in how new releases are deployed and tested. To minimize any compatibility issues and to ensure their computers stayed up to date, Contoso deployed Windows and Office in two stages:</span></span> 

- <span data-ttu-id="8a530-p104">第一階段，他們將 Microsoft 365 Apps 企業版部署到組織中具代表性的一小群裝置。此試驗群組用於測試應用程式、增益集和 Microsoft 365 Apps 企業版的硬體</span><span class="sxs-lookup"><span data-stu-id="8a530-p104">For the first stage, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization. This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="8a530-125">Contoso 在四個月後解決應用程式、增益集與硬體試驗群組中的所有重大問題， 並將 Microsoft 365 Apps 企業版部署至整個組織的裝置 (大型群組)。</span><span class="sxs-lookup"><span data-stu-id="8a530-125">Four months later, after addressing all critical issues with apps, add-ins, and hardware in the pilot group, Contoso deployed Microsoft 365 Apps for enterprise to the rest of the devices in the organization (the broad group).</span></span> 

<span data-ttu-id="8a530-p105">Contoso 不使用 Configuration Manager 來管理 Office 的更新，而是啟用雲端自動更新。雲端式更新可在降低管理成本的同時，確保裝置維持最新版本。</span><span class="sxs-lookup"><span data-stu-id="8a530-p105">Instead of managing updates to Office with Configuration Manager, Contoso enabled automatic updates from the cloud. Cloud-based updates reduced their administrative overhead while ensuring the devices stayed up to date.</span></span> 

<span data-ttu-id="8a530-p106">Contoso 遵循相同的兩階段方式進行功能更新和部署 Office：在試驗群組中的裝置會比其他組織中的裝置 (大型群組) 早四個月收到功能更新。為了在 Office 中啟用此功能，Contoso 使用兩個建議的[更新通道](https://docs.microsoft.com/DeployOffice/overview-update-channels)：</span><span class="sxs-lookup"><span data-stu-id="8a530-p106">Contoso followed the same two-stage approach for feature updates that they used for deploying Office: devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group). To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-update-channels):</span></span> 

- <span data-ttu-id="8a530-130">對試驗群組更新的半年通道(預覽)</span><span class="sxs-lookup"><span data-stu-id="8a530-130">Semi-Annual Enterprise Channel (Preview) for updates to the pilot group</span></span> 
- <span data-ttu-id="8a530-131">對大型群組更新的半年企業通道。</span><span class="sxs-lookup"><span data-stu-id="8a530-131">Semi-Annual Enterprise Channel for updates to the broad group.</span></span> 

<span data-ttu-id="8a530-132">由於半年企業通道 (預覽) 比半年企業通道早四個月發行 Microsoft 365 Apps 企業版，因此 Contoso 有時間在無需管理更新下，進型驗證更新。</span><span class="sxs-lookup"><span data-stu-id="8a530-132">Because the Semi-Annual Enterprise Channel (Preview) releases a version of Microsoft 365 Apps for enterprise four months earlier than the Semi-Annual Enterprise Channel, Contoso has time to validate the updates without having to manage them.</span></span> 

## <a name="deployment-process"></a><span data-ttu-id="8a530-133">部署程序</span><span class="sxs-lookup"><span data-stu-id="8a530-133">Deployment process</span></span>

<span data-ttu-id="8a530-134">為了完成 Office 部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：</span><span class="sxs-lookup"><span data-stu-id="8a530-134">To complete the deployment of Office, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="8a530-135">在部署之前，他們會使用「整備工具組」測試的應用程式和 Office 增益集，評估其與 Microsoft 365 Apps 企業版的相容性。</span><span class="sxs-lookup"><span data-stu-id="8a530-135">Before deploying, they used the Readiness Toolkit to test their apps and Office add-ins to assess their compatibility with Microsoft 365 Apps for enterprise.</span></span>
2. <span data-ttu-id="8a530-136">Contoso 啟用 Configuration Manager 的用戶端對等快取，協助在部署至遠端位置的用戶端裝置時限制網路流量。</span><span class="sxs-lookup"><span data-stu-id="8a530-136">In Configuration Manager, Contoso enabled peer cache on their client devices, which helped with limited network capacity when deploying to client devices in remote locations.</span></span> 
3. <span data-ttu-id="8a530-p107">他們在 Configuration Manager 中將兩個部署群組定義為裝置集合：試驗群組和大型群組。試驗群組包含整個組織中具代表性的一小群裝置，用來對 Windows 10 企業版和 Microsoft 365 Apps 企業版的應用程式、增益集及硬體執行額外測試。</span><span class="sxs-lookup"><span data-stu-id="8a530-p107">They defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group. The pilot group, which included a small set of representative devices across the organization, was used to do additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span></span> 
4. <span data-ttu-id="8a530-p108">他們使用皆為 Configuration Manager 控制台一部分的 Office 用戶端管理儀表板和 Office 365 安裝精靈建立 Ofiiice 部署套件。建立的 Microsoft 365 Apps 企業版套件有兩個，一個用於試驗群組半年企業通道 (預覽)，另一個用於大型群組的半年企業通道。</span><span class="sxs-lookup"><span data-stu-id="8a530-p108">They created deployment packages for Office using the Office Client Management dashboard and the Office 365 Installer wizard, both of which are part of the Configuration Manager console. They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel.</span></span> 
5. <span data-ttu-id="8a530-p109">每個 Office 套件皆包含英文、法文及德文語言套件。如果裝置需要的語言不在 Office 套件中，則會從 Office 內容傳遞網路 (CDN) 自動下載。</span><span class="sxs-lookup"><span data-stu-id="8a530-p109">As part of each Office package, they included English, French, and German Language packs. If a device required a language not included in the Office package, it was automatically downloaded from the Office Content Delivery Network (CDN).</span></span>
6. <span data-ttu-id="8a530-143">他們先使用 Office 套件中的內建功能自動移除所有現有的 MSI 版本 Office，再安裝 Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="8a530-143">They used the built-in feature in the Office package to automatically remove all existing MSI versions of Office before installing Microsoft 365 Apps for enterprise.</span></span>
7. <span data-ttu-id="8a530-144">他們在 Configuration Manager 中將 Windows 和 Office 套件部署到內部網路中發佈點，然後執行 Configuration Manager 部署工作順序將試驗 Microsoft 365 Apps 企業版套件部署到試驗群組。</span><span class="sxs-lookup"><span data-stu-id="8a530-144">In Configuration Manager, they deployed the Windows and Office packages to distribution points across their network, and then ran the Configuration Manager deployment task sequences to deploy the pilot Microsoft 365 Apps for enterprise package to the pilot group.</span></span>
8. <span data-ttu-id="8a530-145">Contoso 在試驗群組解決任何相容性問題後，即會執行工作順序將各種 Microsoft 365 Apps 企業版套件部署到大型群組。</span><span class="sxs-lookup"><span data-stu-id="8a530-145">After addressing any compatibility issues with the pilot group, Contoso ran the task sequences to deploy the broad Microsoft 365 Apps for enterprise package to the broad group.</span></span>

<span data-ttu-id="8a530-146">因為 Contoso 選擇從雲端自動更新裝置，因此不需要管理 Configuration Manager 中的程序。</span><span class="sxs-lookup"><span data-stu-id="8a530-146">Because Contoso chose to automatically update devices from the cloud, there was no need to manage the process in Configuration Manager.</span></span> <span data-ttu-id="8a530-147">其裝置會根據初始部署時所定義的更新通道，直接從雲端自動進行更新。</span><span class="sxs-lookup"><span data-stu-id="8a530-147">Their devices are automatically updated directly from the cloud-based on the update channel that was defined as part of the initial deployment.</span></span> 

<span data-ttu-id="8a530-148">這是 Contoso Microsoft 365 Apps 企業版安裝和持續更新部署的基礎架構。</span><span class="sxs-lookup"><span data-stu-id="8a530-148">Here is Contoso’s Microsoft 365 Apps for enterprise installation and ongoing updates deployment architecture.</span></span>

![Contoso 的 Microsoft 365 Apps 企業版部署基礎結構](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a><span data-ttu-id="8a530-150">下一步</span><span class="sxs-lookup"><span data-stu-id="8a530-150">Next step</span></span>

<span data-ttu-id="8a530-151">[瞭解](contoso-mdm.md) Contoso 如何在 microsoft 365 for enterprise 中使用 microsoft Intune，以管理其裝置，以及其組織內執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8a530-151">[Learn](contoso-mdm.md) how Contoso is using Microsoft Intune in Microsoft 365 for enterprise to manage its devices and the apps that run on them across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a530-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="8a530-152">See also</span></span>

[<span data-ttu-id="8a530-153">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="8a530-153">Microsoft 365 Apps for enterprise</span></span>](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[<span data-ttu-id="8a530-154">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="8a530-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8a530-155">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="8a530-155">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
