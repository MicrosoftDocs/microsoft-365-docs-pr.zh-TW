---
title: 階段 4：Microsoft 365 Apps 企業版
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 適用於 Microsoft 365 企業版的 Microsoft 365 Apps 企業版基礎結構部署步驟。
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011944"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="2a46e-103">階段 4：Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="2a46e-103">Phase 4: Microsoft 365 Apps for enterprise</span></span>

![階段 4：Microsoft 365 Apps 企業版](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="2a46e-105">*本文同時適用於 Microsoft 365 企業版和 Microsoft 365 教育版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="2a46e-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="2a46e-106">Microsoft 365 企業版包括 Office 的訂閱版本 Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="2a46e-106">Microsoft 365 Enterprise includes Microsoft 365 Apps for enterprise, the subscription version of Office.</span></span> <span data-ttu-id="2a46e-107">如同 Office 2019，Microsoft 365 Apps 企業版包括所有 Office 應用程式，而這些應用程式會直接安裝在您的用戶端裝置上。</span><span class="sxs-lookup"><span data-stu-id="2a46e-107">Like Office 2019, Microsoft 365 Apps for enterprise includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="2a46e-108">與 Office 2019 不同，Microsoft 365 Apps 企業版會定期更新新的功能，並擁有可讓使用者在多個裝置上安裝 Office 的使用者型授權模型。</span><span class="sxs-lookup"><span data-stu-id="2a46e-108">Unlike Office 2019, Microsoft 365 Apps for enterprise is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="2a46e-109">如需詳細資訊，請參閱[關於 Microsoft 365 應用程式企業版](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="2a46e-109">For more details, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="2a46e-p102">您在這個階段將 Microsoft 365 應用程式企業版部署到用戶端裝置，這是 Microsoft 365 企業版的一部分。除了本指引，我們建議您使用 [Microsoft FastTrack](https://fasttrack.microsoft.com/office) 來進行部署。</span><span class="sxs-lookup"><span data-stu-id="2a46e-p102">In this phase, you deploy Microsoft 365 Apps for enterprise to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft FastTrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="2a46e-112">如果您已部署 Microsoft 365 Apps 企業版，請參閱此階段的[允出準則](office365proplus-exit-criteria.md)，以確保其符合 Microsoft 365 企業版的必要條件。</span><span class="sxs-lookup"><span data-stu-id="2a46e-112">If you already have Microsoft 365 Apps for enterprise deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="2a46e-113">若要同時部署 Windows 10 企業版和 Microsoft 365 Apps 企業版，請參閱[桌面部署中心](desktop-deployment-center-home.md)。</span><span class="sxs-lookup"><span data-stu-id="2a46e-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="2a46e-114">步驟 1：評估環境</span><span class="sxs-lookup"><span data-stu-id="2a46e-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="2a46e-p103">部署 Microsoft 365 應用程式企業版之前，請遵循[針對部署 Microsoft 365 應用程式評估環境和需求](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps)中的指引。此評估包括系統需求、用戶端裝置的詳細資料 (例如架構、所需的語言)、授權需求、網路功能、應用程式相容性。完成評估可協助您為規劃部署做出重要決策。</span><span class="sxs-lookup"><span data-stu-id="2a46e-p103">Before deploying Microsoft 365 Apps for enterprise, follow the guidance in [Assess your environment and requirements for deploying Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="2a46e-118">步驟 2：規劃部署</span><span class="sxs-lookup"><span data-stu-id="2a46e-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="2a46e-p104">評估環境之後，請遵循[規劃 Microsoft 365 應用程式的部署](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps)中的指引建立部署規劃。規劃包含下列決策：</span><span class="sxs-lookup"><span data-stu-id="2a46e-p104">After assessing your environment, follow the guidance in [Plan your deployment of Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="2a46e-121">如何部署 Office，包括要使用哪些工具 (例如 Microsoft Endpoint Configuration Manager 或 Office 部署工具)，以及從何處安裝 Office</span><span class="sxs-lookup"><span data-stu-id="2a46e-121">How to deploy Office, including what tool to use (such as Microsoft Endpoint Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="2a46e-122">如何管理 Office 的更新</span><span class="sxs-lookup"><span data-stu-id="2a46e-122">How to manage updates to Office</span></span>
- <span data-ttu-id="2a46e-123">使用哪些更新通道 (Office 更新通道可控制使用者收到 Office 應用程式功能更新的頻率)</span><span class="sxs-lookup"><span data-stu-id="2a46e-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="2a46e-124">您想要使用的 Office 安裝套件和部署群組，包括哪些使用者應安裝哪些 Office 應用程式和語言</span><span class="sxs-lookup"><span data-stu-id="2a46e-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="2a46e-125">[規劃文章](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps)中有這些選項的最佳做法，包括管理部署、管理更新、定義安裝套件、建立部署群組。</span><span class="sxs-lookup"><span data-stu-id="2a46e-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="2a46e-126">步驟 3：部署</span><span class="sxs-lookup"><span data-stu-id="2a46e-126">Step 3: Deploy</span></span>

<span data-ttu-id="2a46e-127">根據部署規劃，選擇您要部署的方式：</span><span class="sxs-lookup"><span data-stu-id="2a46e-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="2a46e-128">**[使用 Configuration Manager 部署 Microsoft 365 應用程式](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager)** 使用 Configuration Manager 管理部署，並從網路上的發佈點下載及部署 Office。</span><span class="sxs-lookup"><span data-stu-id="2a46e-128">**[Deploy Microsoft 365 Apps with Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="2a46e-129">**[從雲端部署 Microsoft 365 應用程式](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud)：** 使用 ODT 管理部署，並直接從 Office CDN 將 Office 安裝在用戶端裝置上</span><span class="sxs-lookup"><span data-stu-id="2a46e-129">**[Deploy Microsoft 365 Apps from the cloud](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="2a46e-130">**[從 Office 入口網站自行安裝 Microsoft 365 Apps 企業版](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365)：** 從 Office 入口網站管理部署，讓使用者直接從入口網站將 Office 安裝在他們的用戶端裝置上</span><span class="sxs-lookup"><span data-stu-id="2a46e-130">**[Self-install Microsoft 365 Apps for enterprise from the Office portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="2a46e-p105">許多組織會組合使用這些選項讓不同使用者使用。例如，組織可能會使用設定管理員為大部分的使用者部署 Office，但為一小群不常連線到內部網路的工作者啟用自行安裝。</span><span class="sxs-lookup"><span data-stu-id="2a46e-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="2a46e-p106">如果您的組織使用設定管理員，建議您升級至最新分支並更新至最新版本。如需詳細資訊，請參閱[我應該使用設定管理員的哪一個分支？](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="2a46e-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="2a46e-135">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="2a46e-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2a46e-136">了解 Microsoft 的專家如何[部署和管理 Microsoft 365 Apps 企業版的更新](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7)。</span><span class="sxs-lookup"><span data-stu-id="2a46e-136">Learn how the experts at Microsoft are [deploying and managing updates for Microsoft 365 Apps for enterprise](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="2a46e-137">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="2a46e-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2a46e-138">請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何[部署 Microsoft 365 Apps 企業版](contoso-o365pp.md)。</span><span class="sxs-lookup"><span data-stu-id="2a46e-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Microsoft 365 Apps for enterprise](contoso-o365pp.md).</span></span>

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="2a46e-140">下一步</span><span class="sxs-lookup"><span data-stu-id="2a46e-140">Next step</span></span>

[<span data-ttu-id="2a46e-141">Microsoft 365 Apps 企業版基礎結構的允出準則</span><span class="sxs-lookup"><span data-stu-id="2a46e-141">Microsoft 365 Apps for enterprise infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
