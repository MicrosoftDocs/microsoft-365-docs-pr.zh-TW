---
title: Microsoft 365 企業版底層基礎結構
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 03/05/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解貴組織中部署 Microsoft 365 企業版底層基礎結構的主要階段，也稱為核心部署。
ms.openlocfilehash: e6b8a71f59f20633e323c71e931b930198bc4deb
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400047"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="7f766-103">Microsoft 365 企業版底層基礎結構</span><span class="sxs-lookup"><span data-stu-id="7f766-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="7f766-104">如果您要自行進行 Microsoft 365 企業版的端對端部署，請先建置穩固的基礎，以便應用程式與服務能夠在安全的環境中發揮創意和實現團隊合作能力。</span><span class="sxs-lookup"><span data-stu-id="7f766-104">If you're doing the end-to-end deployment of Microsoft 365 Enterprise yourself, you should first build a firm foundation upon which applications and services can unlock creativity and teamwork in a secure environment.</span></span> <span data-ttu-id="7f766-105">此基礎有時也稱為核心部署。</span><span class="sxs-lookup"><span data-stu-id="7f766-105">This foundation is sometimes referred to as the core deployment.</span></span>

<span data-ttu-id="7f766-106">如需明確的端對端部署路徑，您可以使用下列階段來規劃和部署 Microsoft 365 企業版的底層基礎結構：</span><span class="sxs-lookup"><span data-stu-id="7f766-106">For a defined end-to-end path for deployment, you can use these phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise:</span></span>

| | <span data-ttu-id="7f766-107">階段</span><span class="sxs-lookup"><span data-stu-id="7f766-107">Phase</span></span> | <span data-ttu-id="7f766-108">結果</span><span class="sxs-lookup"><span data-stu-id="7f766-108">Results</span></span> |
|:-------|:-----|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="7f766-109">階段 1：網路</span><span class="sxs-lookup"><span data-stu-id="7f766-109">Phase 1: Networking</span></span>](networking-infrastructure.md)| <span data-ttu-id="7f766-110">網路會針對 Microsoft 365 雲端式服務的存取進行最佳化。</span><span class="sxs-lookup"><span data-stu-id="7f766-110">Your network is optimized for access to Microsoft 365's cloud-based services.</span></span> |
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="7f766-111">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="7f766-111">Phase 2: Identity</span></span>](identity-infrastructure.md)| <span data-ttu-id="7f766-112">系統管理員帳戶會受到保護、使用者和群組會進行同步處理，並提供增強式的使用者驗證機制。</span><span class="sxs-lookup"><span data-stu-id="7f766-112">Your admin accounts are protected, your users and groups are synchronized, and your user authentication is strong.</span></span> |
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="7f766-113">階段 3：Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="7f766-113">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)| <span data-ttu-id="7f766-114">現有的 Windows 架構電腦可升級為 Windows 10 企業版，且新裝置會使用 Windows 10 企業版來進行安裝。</span><span class="sxs-lookup"><span data-stu-id="7f766-114">Your existing Windows-based computers can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="7f766-115">階段 4：Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="7f766-115">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)| <span data-ttu-id="7f766-116">現有的 Microsoft Office 使用者可升級為 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="7f766-116">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="7f766-117">階段 5：行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="7f766-117">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)| <span data-ttu-id="7f766-118">裝置可以進行註冊並受到管理。</span><span class="sxs-lookup"><span data-stu-id="7f766-118">Your devices can be enrolled and managed.</span></span> |
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="7f766-119">階段 6：資訊保護</span><span class="sxs-lookup"><span data-stu-id="7f766-119">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)| <span data-ttu-id="7f766-120">標籤已準備好保護文件，並啟用 Office 365 安全性功能。</span><span class="sxs-lookup"><span data-stu-id="7f766-120">Your labels are ready to protect documents and Office 365 security features are enabled.</span></span> |

<span data-ttu-id="7f766-121">這些階段會從最基本的項目 (網路和身分識別) 開始，然後會建立基礎結構的各個設定和群組層級，以便：</span><span class="sxs-lookup"><span data-stu-id="7f766-121">The phases start with the most foundational (networking and identity), and then create layers of infrastructure settings and groups to:</span></span>

- <span data-ttu-id="7f766-122">在裝置上安裝最新且最安全的 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="7f766-122">Install the most current and secure version of Windows on your devices.</span></span>
- <span data-ttu-id="7f766-123">在裝置上安裝最新的 Office 版本。</span><span class="sxs-lookup"><span data-stu-id="7f766-123">Install the most current version of Office on your devices.</span></span>
- <span data-ttu-id="7f766-124">管理組織的裝置。</span><span class="sxs-lookup"><span data-stu-id="7f766-124">Manage your organization's devices.</span></span>
- <span data-ttu-id="7f766-125">保護這些裝置上和雲端中的資訊。</span><span class="sxs-lookup"><span data-stu-id="7f766-125">Protect the information on those devices and in the cloud.</span></span>

<span data-ttu-id="7f766-126">不過，您可以彈性地設定和推出這些階段或階段內的步驟，以符合 IT 資源和企業的需求。</span><span class="sxs-lookup"><span data-stu-id="7f766-126">However, you have the flexibility of configuring and rolling out the phases or steps within phases to fit your IT resources and business needs.</span></span>

- <span data-ttu-id="7f766-127">**如果您是規模較小或創立不久的組織**，請視需要地遵循這些階段以便有系統地建置基礎結構。</span><span class="sxs-lookup"><span data-stu-id="7f766-127">**If you are a smaller or newer organization**, follow the phases as needed to methodically build out your infrastructure.</span></span>

-  <span data-ttu-id="7f766-128">**如果您是企業組織**，請將這些階段視為 IT 基礎結構層級而非明確的路徑，並判斷最終要如何做才能符合組織內每一層級的需求。</span><span class="sxs-lookup"><span data-stu-id="7f766-128">**If you are an enterprise organization**, view the phases as layers of IT infrastructure, rather than a defined path, and determine how to best work toward eventual adherence to the requirements for each layer across your organization.</span></span>

<span data-ttu-id="7f766-129">在每個階段的結尾，您都應該檢查其允出準則 (內含必須符合的必要條件以及要考慮的選擇性條件)。</span><span class="sxs-lookup"><span data-stu-id="7f766-129">At the end of each phase, you should examine its exit criteria, which include required conditions that you must meet and optional conditions to consider.</span></span> <span data-ttu-id="7f766-130">每個階段的允出準則可確保您的內部部署和雲端基礎結構與產生的端對端設定符合 Microsoft 365 企業版部署需求。</span><span class="sxs-lookup"><span data-stu-id="7f766-130">Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="7f766-131">若要了解內容的建構方式，請觀看這段短片。</span><span class="sxs-lookup"><span data-stu-id="7f766-131">To see how the content is structured, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="7f766-132">以下是整個 Microsoft 365 企業版部署指南中的底層基礎結構：</span><span class="sxs-lookup"><span data-stu-id="7f766-132">Here's the foundation infrastructure in the overall Microsoft 365 Enterprise deployment guide:</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="infrastructure-configuration-vs-user-rollout"></a><span data-ttu-id="7f766-133">基礎結構設定與使用者推出</span><span class="sxs-lookup"><span data-stu-id="7f766-133">Infrastructure configuration vs. user rollout</span></span>

<span data-ttu-id="7f766-134">底層基礎結構是一組設定好的軟體和服務，結合在一起時可讓使用者利用 Microsoft 365 企業版所提供的完整功能和保護機制。</span><span class="sxs-lookup"><span data-stu-id="7f766-134">The foundation infrastructure is a set of configured software and services that, when combined together for a user, allow them to take advantage of the entire spectrum of capabilities and protections that Microsoft 365 Enterprise offers.</span></span> <span data-ttu-id="7f766-135">端對端部署旅程的終點是要讓這個基礎結構套用至所有使用者和其持有的 Windows 架構裝置。</span><span class="sxs-lookup"><span data-stu-id="7f766-135">The ultimate destination of your end-to-end deployment journey is to have this infrastructure apply to all of your users and their Windows-based devices.</span></span> 

<span data-ttu-id="7f766-136">不過請務必注意，對使用者推出軟體與服務的行為與 Microsoft 365 企業版底層基礎結構無關。</span><span class="sxs-lookup"><span data-stu-id="7f766-136">However, it is important to note that the Microsoft 365 Enterprise foundation infrastructure is independent of the rollout of software and services to your users.</span></span> <span data-ttu-id="7f766-137">***您可以設定底層基礎結構的層級，而不需要對所有使用者推出這些層級。***</span><span class="sxs-lookup"><span data-stu-id="7f766-137">***You can configure the layers of the foundation infrastructure without having to roll out those layers to all of your users.***</span></span>

<span data-ttu-id="7f766-138">因此，您可以事先設定、測試和試驗底層基礎結構的元素，然後再對辦公室、地區或組織部門內的眾多使用者推出這些元素。</span><span class="sxs-lookup"><span data-stu-id="7f766-138">Therefore, it is possible to configure, test, and pilot elements of the foundation infrastructure well ahead of the rollout of those elements to the multitude of your users in the offices, regions, or divisions of your organization.</span></span>

<span data-ttu-id="7f766-139">例如，您可以針對下列項目建立設定：</span><span class="sxs-lookup"><span data-stu-id="7f766-139">For example, you create the settings for:</span></span>

| <span data-ttu-id="7f766-140">階段</span><span class="sxs-lookup"><span data-stu-id="7f766-140">Phase</span></span> | <span data-ttu-id="7f766-141">結果</span><span class="sxs-lookup"><span data-stu-id="7f766-141">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="7f766-142">身分識別</span><span class="sxs-lookup"><span data-stu-id="7f766-142">Identity</span></span> | <span data-ttu-id="7f766-143">帳戶同步處理和身分識別型條件式存取原則的群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-143">Account synchronization and groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="7f766-144">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="7f766-144">Windows 10 Enterprise</span></span> | <span data-ttu-id="7f766-145">可自動將執行 Windows 7 或 Windows 8.1 的電腦就地升級為 Windows 10 企業版的群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-145">Groups to automatically upgrade computers running Windows 7 or Windows 8.1 to Windows 10 Enterprise in place.</span></span> |
| <span data-ttu-id="7f766-146">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="7f766-146">Office 365 ProPlus</span></span> | <span data-ttu-id="7f766-147">可自動為使用 Office 2010、Office 2013 或 Office 2016 的使用者部署 Office 365 專業增強版的群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-147">Groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="7f766-148">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="7f766-148">Mobile device management</span></span> | <span data-ttu-id="7f766-149">用於裝置註冊和裝置型條件式存取原則的群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-149">Groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="7f766-150">資訊保護</span><span class="sxs-lookup"><span data-stu-id="7f766-150">Information protection</span></span> | <span data-ttu-id="7f766-151">Office 365 和 Azure 資訊保護標籤與群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-151">Office 365 and Azure Information Protection labels and groups.</span></span> |

<span data-ttu-id="7f766-152">當您準備好對使用者推出這個基礎結構的元素時：</span><span class="sxs-lookup"><span data-stu-id="7f766-152">When you are ready to rollout elements of this infrastructure to users, you:</span></span>

| <span data-ttu-id="7f766-153">階段</span><span class="sxs-lookup"><span data-stu-id="7f766-153">Phase</span></span> | <span data-ttu-id="7f766-154">推出動作</span><span class="sxs-lookup"><span data-stu-id="7f766-154">Rollout action</span></span> |
|:-------|:-----|
| <span data-ttu-id="7f766-155">身分識別</span><span class="sxs-lookup"><span data-stu-id="7f766-155">Identity</span></span> | <span data-ttu-id="7f766-156">將使用者帳戶新增至身分識別型條件式存取原則的群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-156">Add user accounts to the groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="7f766-157">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="7f766-157">Windows 10 Enterprise</span></span> | <span data-ttu-id="7f766-158">將帳戶新增至可自動為使用 Windows 7 或 Windows 8.1 的使用者就地部署 Windows 10 企業版的群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-158">Add accounts to the groups to automatically deploy Windows 10 Enterprise in place for users with Windows 7 or Windows 8.1.</span></span> |
| <span data-ttu-id="7f766-159">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="7f766-159">Office 365 ProPlus</span></span> | <span data-ttu-id="7f766-160">將使用者帳戶新增至可自動為使用 Office 2010、Office 2013 或 Office 2016 的使用者部署 Office 365 專業增強版的群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-160">Add user accounts to the groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="7f766-161">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="7f766-161">Mobile device management</span></span> | <span data-ttu-id="7f766-162">將帳戶新增至用於裝置註冊和裝置型條件式存取原則的群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-162">Add accounts to the groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="7f766-163">資訊保護</span><span class="sxs-lookup"><span data-stu-id="7f766-163">Information protection</span></span> | <span data-ttu-id="7f766-164">將使用者帳戶新增至資訊保護標籤的群組。</span><span class="sxs-lookup"><span data-stu-id="7f766-164">Add user accounts to the groups for Information Protection labels.</span></span> |

<span data-ttu-id="7f766-165">在底層基礎結構完成、經過測試及試驗後，您便可以對使用者以最符合業務目標和 IT 資源的方式推出已安裝好的軟體 (例如，Windows 10 企業版和 Office 365 專業增強版) 以及雲端式服務和保護 (例如，裝置註冊和條件式存取原則)。</span><span class="sxs-lookup"><span data-stu-id="7f766-165">Once the foundation infrastructure is completed, tested, and piloted, you can roll out installed software, such as Windows 10 Enterprise and Office 365 ProPlus, and cloud-based services and protections, such as device enrollment and conditional access policies, to your users in the manner that best fits your business goals and IT resources.</span></span>

## <a name="deployment-and-project-management-strategies"></a><span data-ttu-id="7f766-166">部署和專案管理策略</span><span class="sxs-lookup"><span data-stu-id="7f766-166">Deployment and project management strategies</span></span>

<span data-ttu-id="7f766-167">若要了解如何讓試驗使用者和組織內的其他人知道如何對底層基礎結構的不同階段進行專案管理，請參閱[部署策略](deployment-strategies-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="7f766-167">To give you some ideas on how to approach the project management of the different phases of the foundation infrastructure for pilot users and the rest of your organization, see [deployment strategies](deployment-strategies-microsoft-365-enterprise.md).</span></span>


## <a name="next-step"></a><span data-ttu-id="7f766-168">下一步</span><span class="sxs-lookup"><span data-stu-id="7f766-168">Next step</span></span>

- <span data-ttu-id="7f766-169">我有既存的 Office 365、Enterprise Mobility + Security (EMS) 或 Windows 10 企業版基礎結構：</span><span class="sxs-lookup"><span data-stu-id="7f766-169">I have existing infrastructure for Office 365, Enterprise Mobility + Security (EMS), or Windows 10 Enterprise:</span></span>
  - <span data-ttu-id="7f766-170">請參閱[使用現有基礎結構進行部署](deploy-with-existing-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="7f766-170">See [Deploy with existing infrastructure](deploy-with-existing-infrastructure.md).</span></span> <span data-ttu-id="7f766-171">本文將逐步引導您完成每個階段的允出準則。</span><span class="sxs-lookup"><span data-stu-id="7f766-171">This article steps you through the exit criteria for each phase.</span></span>
- <span data-ttu-id="7f766-172">我要從頭開始：</span><span class="sxs-lookup"><span data-stu-id="7f766-172">I'm starting from scratch:</span></span> 
   - <span data-ttu-id="7f766-173">使用[階段 1：網路](networking-infrastructure.md)開始端對端部署旅程。</span><span class="sxs-lookup"><span data-stu-id="7f766-173">Begin your end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>
