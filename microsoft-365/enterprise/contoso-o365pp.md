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
ms.openlocfilehash: 63993a27f23843fd2d75ef9bf08ae064ec46dc77
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637160"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a><span data-ttu-id="23b8b-103">適用於 Contoso 的 Microsoft 365 Apps 企業版部署</span><span class="sxs-lookup"><span data-stu-id="23b8b-103">Microsoft 365 Apps for enterprise deployment for Contoso</span></span>

<span data-ttu-id="23b8b-p101">Contoso 將其電腦升級至 Windows 10 企業版和 Microsoft 365 應用程式的企業版，以啟用更有效率的共同作業、更好的安全性，以及更新式的桌面體驗。在評估其基礎結構和業務需求之後，Contoso 識別出下列部署的主要需求：</span><span class="sxs-lookup"><span data-stu-id="23b8b-p101">Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience. After they assessed their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="23b8b-106">所有的電腦都應該執行適用于 enterprise 的 Microsoft 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="23b8b-106">All PCs should run Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="23b8b-107">部署應盡可能使用現有的管理工具和基礎結構。</span><span class="sxs-lookup"><span data-stu-id="23b8b-107">Deployment should use existing management tools and infrastructure when possible.</span></span>
- <span data-ttu-id="23b8b-108">在使用者的裝置上部署必須支援多種語言和現有的架構。</span><span class="sxs-lookup"><span data-stu-id="23b8b-108">Deployment must support multiple languages and existing architectures on users' devices.</span></span>
- <span data-ttu-id="23b8b-109">電腦應該以最少的 IT 管理成本和對使用者的影響降至最低的方式，保持最新狀態及安全性。</span><span class="sxs-lookup"><span data-stu-id="23b8b-109">PCs should stay up-to-date and secure with minimal IT administrative costs and minimal impact to users.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="23b8b-110">部署工具</span><span class="sxs-lookup"><span data-stu-id="23b8b-110">Deployment tools</span></span>

<span data-ttu-id="23b8b-p102">根據他們的需求，Contoso 選擇透過 Configuration Manager 來部署 Windows 10 企業版和 Microsoft 365 應用程式 (目前的分支) 。Configuration Manager 針對大型環境進行調整，並提供對安裝、更新及設定的廣泛控制。它也具有內建的功能，可讓您更輕鬆快捷地部署及管理 Office，包括：</span><span class="sxs-lookup"><span data-stu-id="23b8b-p102">Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise through Configuration Manager (Current Branch). Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Office, including:</span></span>

- <span data-ttu-id="23b8b-114">對等快取，可在部署至遠端位置的裝置時協助有限的網路容量。</span><span class="sxs-lookup"><span data-stu-id="23b8b-114">Peer cache, which can help with limited network capacity when deploying to devices in remote locations.</span></span>
- <span data-ttu-id="23b8b-115">Office 用戶端管理儀表板，可讓您輕鬆地部署 Office 和監控更新，並可讓系統管理員存取最新的部署和管理功能。</span><span class="sxs-lookup"><span data-stu-id="23b8b-115">The Office Client Management dashboard, which makes it easy to deploy Office and monitor updates and gives administrators access to the latest deployment and management features.</span></span>
- <span data-ttu-id="23b8b-116">智慧語言套件部署，包括自動部署與作業系統相同的語言。</span><span class="sxs-lookup"><span data-stu-id="23b8b-116">Intelligent language pack deployment, including automatically deploying the same language as the operating system.</span></span>
- <span data-ttu-id="23b8b-117">在部署期間，從用戶端移除 Office 的現有版本的完全支援和便於使用的方法。</span><span class="sxs-lookup"><span data-stu-id="23b8b-117">A fully supported and easy-to-use method of removing existing versions of Office from a client during deployment.</span></span>

<span data-ttu-id="23b8b-118">除了 Configuration Manager 之外，Contoso 使用 [office 增益集的準備](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)人工具組和 VBA，也就是 Microsoft 的免費工具，以評估其 Office 宏及增益集的相容性問題。</span><span class="sxs-lookup"><span data-stu-id="23b8b-118">In addition to Configuration Manager, Contoso used the [Readiness Toolkit for Office add-in and VBA](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), a free tool from Microsoft, to assess compatibility issues with their Office macros and add-ins.</span></span>

## <a name="managing-deployment-and-updates"></a><span data-ttu-id="23b8b-119">管理部署和更新</span><span class="sxs-lookup"><span data-stu-id="23b8b-119">Managing deployment and updates</span></span>

<span data-ttu-id="23b8b-p103">Microsoft 365 應用程式 enterprise 具有新的版本模型： Office 即服務。服務模型可讓您輕鬆掌握最新的功能。不過，它通常需要 IT 部門變更其部署與測試新版本的方式。若要將相容性問題降至最低，以確保其電腦維持在最新狀態，Contoso 會分兩個階段部署 Windows 和 Office：</span><span class="sxs-lookup"><span data-stu-id="23b8b-p103">Microsoft 365 Apps for enterprise has a new release model: Office as a service. The service model makes it easy to stay up to date with new features. But it often requires IT departments to change how they deploy and test new releases. To minimize compatibility issues and to ensure their computers stay up to date, Contoso deployed Windows and Office in two stages:</span></span>

- <span data-ttu-id="23b8b-124">首先，他們將 Microsoft 365 應用程式部署到整個組織中的一小小組代表裝置。</span><span class="sxs-lookup"><span data-stu-id="23b8b-124">First, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization.</span></span> <span data-ttu-id="23b8b-125">此試驗群組是用來測試應用程式、增益集及硬體與 Microsoft 365 應用程式企業版的應用程式。</span><span class="sxs-lookup"><span data-stu-id="23b8b-125">This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="23b8b-126">Contoso 在四個月後解決應用程式、增益集與硬體試驗群組中的所有重大問題， 並將 Microsoft 365 Apps 企業版部署至整個組織的裝置 (大型群組)。</span><span class="sxs-lookup"><span data-stu-id="23b8b-126">Four months later, after addressing all critical issues with apps, add-ins, and hardware in the pilot group, Contoso deployed Microsoft 365 Apps for enterprise to the rest of the devices in the organization (the broad group).</span></span>

<span data-ttu-id="23b8b-127">Contoso 從雲端啟用自動更新，而不是使用 Configuration Manager 管理 Office 更新。</span><span class="sxs-lookup"><span data-stu-id="23b8b-127">Instead of managing updates to Office by using Configuration Manager, Contoso enabled automatic updates from the cloud.</span></span> <span data-ttu-id="23b8b-128">雲端式更新可減少管理負荷，同時確保裝置保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="23b8b-128">Cloud-based updates reduce administrative overhead while ensuring that devices stay up to date.</span></span>

<span data-ttu-id="23b8b-129">Contoso 已遵循用於部署 Office 的功能更新的兩階段方式：在試驗群組中的裝置接收到的功能更新，于組織的其餘部分中的裝置的兩個月之前， (廣泛的群組) 。</span><span class="sxs-lookup"><span data-stu-id="23b8b-129">Contoso followed the same two-stage approach for feature updates as they used for deploying Office: Devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group).</span></span> <span data-ttu-id="23b8b-130">若要為 Office 啟用這項功能，Contoso 使用兩個建議的 [更新通道](https://docs.microsoft.com/DeployOffice/overview-update-channels)：</span><span class="sxs-lookup"><span data-stu-id="23b8b-130">To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-update-channels):</span></span>

- <span data-ttu-id="23b8b-131">對試驗群組更新的半年通道(預覽)</span><span class="sxs-lookup"><span data-stu-id="23b8b-131">Semi-Annual Enterprise Channel (Preview) for updates to the pilot group</span></span>
- <span data-ttu-id="23b8b-132">針對廣泛的群組更新 Semi-Annual Enterprise 通道</span><span class="sxs-lookup"><span data-stu-id="23b8b-132">Semi-Annual Enterprise Channel for updates to the broad group</span></span>

<span data-ttu-id="23b8b-133">由於半年企業通道 (預覽) 比半年企業通道早四個月發行 Microsoft 365 Apps 企業版，因此 Contoso 有時間在無需管理更新下，進型驗證更新。</span><span class="sxs-lookup"><span data-stu-id="23b8b-133">Because the Semi-Annual Enterprise Channel (Preview) releases a version of Microsoft 365 Apps for enterprise four months earlier than the Semi-Annual Enterprise Channel, Contoso has time to validate the updates without having to manage them.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="23b8b-134">部署程序</span><span class="sxs-lookup"><span data-stu-id="23b8b-134">Deployment process</span></span>

<span data-ttu-id="23b8b-135">為了完成 Office 部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：</span><span class="sxs-lookup"><span data-stu-id="23b8b-135">To complete the deployment of Office, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="23b8b-136">部署之前，Contoso 使用 Office 增益集和 VBA 的準備工作工具組來測試其應用程式和 Office 增益集，以評估其與 Microsoft 365 應用程式的相容性。</span><span class="sxs-lookup"><span data-stu-id="23b8b-136">Before deployment, Contoso used the Readiness Toolkit for Office add-in and VBA to test their apps and Office Add-ins to assess their compatibility with Microsoft 365 Apps for enterprise.</span></span>
1. <span data-ttu-id="23b8b-137">在 Configuration Manager 中，他們會在其用戶端裝置上啟用對等快取，以在部署至遠端位置的用戶端裝置時，協助有限的網路容量。</span><span class="sxs-lookup"><span data-stu-id="23b8b-137">In Configuration Manager, they enabled peer cache on their client devices, which helps with limited network capacity when deploying to client devices in remote locations.</span></span> 
1. <span data-ttu-id="23b8b-138">Contoso 在 Configuration Manager 中將兩個部署群組定義為裝置集合：一個試驗群組和一個廣泛的群組。</span><span class="sxs-lookup"><span data-stu-id="23b8b-138">Contoso defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group.</span></span> <span data-ttu-id="23b8b-139">試驗群組（包含整個組織中一小部分的代表裝置），用來進一步測試應用程式、增益集，以及 Windows 10 企業版和 Microsoft 365 應用程式的硬體。</span><span class="sxs-lookup"><span data-stu-id="23b8b-139">The pilot group, which included a small set of representative devices across the organization, was used for additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span></span>
1. <span data-ttu-id="23b8b-140">他們會使用 Office 用戶端管理儀表板和 Office 365 Installer 嚮導（同時是 Configuration Manager 主控台的一部分）建立 Office 的部署套件。</span><span class="sxs-lookup"><span data-stu-id="23b8b-140">They created deployment packages for Office by using the Office Client Management dashboard and the Office 365 Installer wizard, which are both part of the Configuration Manager console.</span></span> <span data-ttu-id="23b8b-141">他們會為企業套件建立兩個 Microsoft 365 應用程式，一個用於 Semi-Annual Enterprise 通道 (Preview) 上的試驗群組，另一個適用于 Semi-Annual Enterprise 通道上的廣泛群組。</span><span class="sxs-lookup"><span data-stu-id="23b8b-141">They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel.</span></span>
2. <span data-ttu-id="23b8b-142">每個 Office 套件都包含英文、法文和德文語言套件。</span><span class="sxs-lookup"><span data-stu-id="23b8b-142">Each Office package included English, French, and German Language packs.</span></span> <span data-ttu-id="23b8b-143">如果裝置所需的語言並未包含在 Office 套件中，該語言套件會從 Office 內容傳遞網路（ (CDN) 中自動下載）。</span><span class="sxs-lookup"><span data-stu-id="23b8b-143">If a device required a language that wasn't included in the Office package, that language pack was automatically downloaded from the Office Content Delivery Network (CDN).</span></span>
3. <span data-ttu-id="23b8b-144">他們先使用 Office 套件中的內建功能自動移除所有現有的 MSI 版本 Office，再安裝 Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="23b8b-144">They used the built-in feature in the Office package to automatically remove all existing MSI versions of Office before installing Microsoft 365 Apps for enterprise.</span></span>
4. <span data-ttu-id="23b8b-145">在 Configuration Manager 中，他們會將 Windows 和 Office 套件部署到跨其網路的發佈點。</span><span class="sxs-lookup"><span data-stu-id="23b8b-145">In Configuration Manager, they deployed the Windows and Office packages to distribution points across their network.</span></span> <span data-ttu-id="23b8b-146">然後，他們會執行 Configuration Manager 部署工作順序，將 Microsoft 365 應用程式的試用版應用程式部署到試驗群組。</span><span class="sxs-lookup"><span data-stu-id="23b8b-146">Then they ran the Configuration Manager deployment task sequences to deploy the pilot Microsoft 365 Apps for enterprise package to the pilot group.</span></span>
5. <span data-ttu-id="23b8b-147">當使用者解決試驗群組的相容性問題之後，Contoso 執行工作順序，將 Microsoft 365 應用程式套件部署到廣泛的群組。</span><span class="sxs-lookup"><span data-stu-id="23b8b-147">After they addressed compatibility issues with the pilot group, Contoso ran the task sequences to deploy the Microsoft 365 Apps for enterprise package to the broad group.</span></span>

<span data-ttu-id="23b8b-148">因為 Contoso 選擇從雲端自動更新裝置，因此不需要管理 Configuration Manager 中的程序。</span><span class="sxs-lookup"><span data-stu-id="23b8b-148">Because Contoso chose to automatically update devices from the cloud, there was no need to manage the process in Configuration Manager.</span></span> <span data-ttu-id="23b8b-149">其裝置會根據初始部署中所定義的更新通道，直接從雲端自動更新。</span><span class="sxs-lookup"><span data-stu-id="23b8b-149">Their devices are automatically updated directly from the cloud-based on the update channel that was defined in the initial deployment.</span></span>

<span data-ttu-id="23b8b-150">以下是 Contoso Microsoft 365 Apps for enterprise 安裝和持續更新部署架構。</span><span class="sxs-lookup"><span data-stu-id="23b8b-150">Here is the Contoso Microsoft 365 Apps for enterprise installation and ongoing updates deployment architecture.</span></span>

![適用于企業的 Microsoft 365 應用程式的 Contoso 部署基礎結構](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a><span data-ttu-id="23b8b-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="23b8b-152">Next step</span></span>

<span data-ttu-id="23b8b-153">[深入瞭解](contoso-mdm.md) Contoso 如何在 microsoft 365 for enterprise 中使用 microsoft Intune 來管理其裝置，以及他們在整個組織中執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="23b8b-153">[Learn](contoso-mdm.md) how Contoso is using Microsoft Intune in Microsoft 365 for enterprise to manage its devices and the apps that they run across the organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="23b8b-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="23b8b-154">See also</span></span>

[<span data-ttu-id="23b8b-155">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="23b8b-155">Microsoft 365 Apps for enterprise</span></span>](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[<span data-ttu-id="23b8b-156">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="23b8b-156">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="23b8b-157">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="23b8b-157">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
