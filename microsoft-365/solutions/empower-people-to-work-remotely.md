---
title: 使用 Microsoft 365 設定混合式工作基礎結構。
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: 在家工作、混合式、遠端工作者、混合式工作、遠端員工、混合式連線、遠端存取、遠距工作、行動工作、遠端工作、隨處工作、彈性工作場所
description: 逐步執行基礎結構層，讓混合式工作者可以安全地存取內部部署和 Microsoft 365 資源。
ms.openlocfilehash: fed23a4607cfb47049a6540dfb592d9a8baf9d21
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229368"
---
# <a name="set-up-your-infrastructure-for-hybrid-work-with-microsoft-365"></a><span data-ttu-id="de020-104">使用 Microsoft 365 設定混合式工作基礎結構。</span><span class="sxs-lookup"><span data-stu-id="de020-104">Set up your infrastructure for hybrid work with Microsoft 365</span></span>

<span data-ttu-id="de020-105">若要保護及最佳化工作者的生產力和共同作業，您必須允許現場和遠端工作者能輕鬆而安全地存取貴組織的內部部署和雲端式資訊、工具和資源。</span><span class="sxs-lookup"><span data-stu-id="de020-105">To secure and optimize your worker’s productivity and collaboration, you need to allow on-site and remote workers to easily and securely access your organization's on-premises and cloud-based information, tools, and resources.</span></span> <span data-ttu-id="de020-106">此解決方案會執行重要基礎結構層部署的步驟，讓您的工作者無論身在何處，都能夠完成最佳工作。</span><span class="sxs-lookup"><span data-stu-id="de020-106">This solution steps through the deployment of key layers of infrastructure that empower your workers to do their best work, wherever they are.</span></span>

<span data-ttu-id="de020-107">混合式工作者可以在現場或不同地點的遠端工作。</span><span class="sxs-lookup"><span data-stu-id="de020-107">Hybrid workers can work on-site or remotely in a combination of locations.</span></span> <span data-ttu-id="de020-108">允許員工在辦公室以外的地點工作對許多組織的以下目的非常重要:</span><span class="sxs-lookup"><span data-stu-id="de020-108">Allowing workers to work away from a traditional office is important for many organizations to:</span></span>

- <span data-ttu-id="de020-109">雇用並保留不想搬家或需要彈性工作環境的員工。</span><span class="sxs-lookup"><span data-stu-id="de020-109">Hire and retain workers who are unwilling to relocate or require a flexible work environment.</span></span>
- <span data-ttu-id="de020-110">縮短工作人員的通勤時間，讓他們有更多時間來提高生產力，並在下班後從事能放鬆壓力的活動。</span><span class="sxs-lookup"><span data-stu-id="de020-110">Reduce worker commuting, leaving workers with more time to be productive and for stress-reducing activities outside of work.</span></span>
- <span data-ttu-id="de020-111">節省辦公室空間。</span><span class="sxs-lookup"><span data-stu-id="de020-111">Save on office space.</span></span>

<span data-ttu-id="de020-112">Microsoft 365 具備讓您的混合式工作者能夠在現場或遠端工作的功能。</span><span class="sxs-lookup"><span data-stu-id="de020-112">Microsoft 365 has the capabilities to empower your hybrid workers to work either on-site or remotely.</span></span>

![使用 Microsoft 365 強化您的混合式工作者的能力](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

> [!NOTE]
> <span data-ttu-id="de020-114">如果您是 Microsoft 365 新使用者，請參閱[這些資源](https://www.microsoft.com/microsoft-365)。</span><span class="sxs-lookup"><span data-stu-id="de020-114">If you are new to Microsoft 365, see [these resources](https://www.microsoft.com/microsoft-365).</span></span>

<span data-ttu-id="de020-115">觀看此影片以取得部署程序的概觀。</span><span class="sxs-lookup"><span data-stu-id="de020-115">Watch this video for an overview of the deployment process.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

<span data-ttu-id="de020-116">為了讓管理現場和雲端式基礎結構的 IT 專業人員能夠實現混合式工作者生產力，此解決方案提供下列重要功能：</span><span class="sxs-lookup"><span data-stu-id="de020-116">For IT professionals managing onsite and cloud-based infrastructure to enable hybrid worker productivity, this solution provides these key capabilities:</span></span>

- <span data-ttu-id="de020-117">連接</span><span class="sxs-lookup"><span data-stu-id="de020-117">Connected</span></span>

  <span data-ttu-id="de020-118">工作者必須能夠隨時隨地都能存取：</span><span class="sxs-lookup"><span data-stu-id="de020-118">From anywhere in the world and at any time, your workers are able to access:</span></span>

  - <span data-ttu-id="de020-119">您的 Microsoft 365 訂閱中的雲端服務和資料。</span><span class="sxs-lookup"><span data-stu-id="de020-119">Cloud-based services and data in your Microsoft 365 subscription.</span></span>

  - <span data-ttu-id="de020-120">組織資源，例如內部部署應用程式資料中心所提供的資源。</span><span class="sxs-lookup"><span data-stu-id="de020-120">Organization resources, such those offered by on-premises application datacenters.</span></span>

- <span data-ttu-id="de020-121">安全</span><span class="sxs-lookup"><span data-stu-id="de020-121">Secure</span></span>

  <span data-ttu-id="de020-122">以 Microsoft 365 和 Windows 10 的多重要素驗證（MFA）和內建安全性功能保護登入，避免惡意程式碼、惡意攻擊和資料遺失。</span><span class="sxs-lookup"><span data-stu-id="de020-122">Sign-ins are secured with multi-factor authentication (MFA) and built-in security features of Microsoft 365 and Windows 10 protect against malware, malicious attacks, and data loss.</span></span>

- <span data-ttu-id="de020-123">受管理</span><span class="sxs-lookup"><span data-stu-id="de020-123">Managed</span></span>

  <span data-ttu-id="de020-124">您可以透過安全性設定、允許的應用程式和要求系統運作狀態符合要求來從雲端管理您的混合式工作者的裝置。</span><span class="sxs-lookup"><span data-stu-id="de020-124">Your hybrid worker's devices can be managed from the cloud with security settings, allowed apps, and to require compliance with system health.</span></span>

- <span data-ttu-id="de020-125">共同作業和生產力</span><span class="sxs-lookup"><span data-stu-id="de020-125">Collaborative and productive</span></span>

  <span data-ttu-id="de020-126">透過以下高度共同作業的方式，您的混合式工作者可以像在內部部署工作時一樣高效:</span><span class="sxs-lookup"><span data-stu-id="de020-126">Your hybrid workers can be as productive as on-premises in a highly collaborative way with:</span></span>

  - <span data-ttu-id="de020-127">以 Teams 進行線上會議和聊天會話。</span><span class="sxs-lookup"><span data-stu-id="de020-127">Online meetings and chat sessions with Teams.</span></span>

  - <span data-ttu-id="de020-128">透過 SharePoint 和 OneDrive，使用全域協助工具和即時共同作業的雲端式檔案儲存空間以共用工作區。</span><span class="sxs-lookup"><span data-stu-id="de020-128">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration with SharePoint and OneDrive.</span></span>

  - <span data-ttu-id="de020-129">共用工作和工作流程來劃分並完成工作。</span><span class="sxs-lookup"><span data-stu-id="de020-129">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="de020-130">若要取得無縫登入體驗，您的內部部署 Active Directory 網域服務 (AD DS) 使用者帳戶應與 Azure Active Directory (Azure AD) 同步處理。</span><span class="sxs-lookup"><span data-stu-id="de020-130">For a seamless sign-in experience, your on-premises Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="de020-131">為了保護您的 Windows 10 裝置，應在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="de020-131">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="de020-132">以下是基礎結構的高階檢視。</span><span class="sxs-lookup"><span data-stu-id="de020-132">Here is a high-level view of the infrastructure.</span></span>

![適用於使用 Microsoft 365 之混合式工作者的基本基礎結構](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

<span data-ttu-id="de020-134">若要為您的混合式工作者啟用 Microsoft 365 的功能，請使用這些 Microsoft 365 功能。</span><span class="sxs-lookup"><span data-stu-id="de020-134">To enable the capabilities of Microsoft 365 for your hybrid workers, use these Microsoft 365 features.</span></span>

| <span data-ttu-id="de020-135">功能</span><span class="sxs-lookup"><span data-stu-id="de020-135">Capability or feature</span></span> | <span data-ttu-id="de020-136">描述</span><span class="sxs-lookup"><span data-stu-id="de020-136">Description</span></span> | <span data-ttu-id="de020-137">授權</span><span class="sxs-lookup"><span data-stu-id="de020-137">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="de020-138">採用安全性預設值強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="de020-138">MFA enforced with security defaults</span></span>   | <span data-ttu-id="de020-139">要求第二種形式的登入驗證，以防止身分識別和裝置遭到入侵。安全性預設值要求所有使用者帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="de020-139">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="de020-140">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="de020-140">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="de020-141">使用條件式存取強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="de020-141">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="de020-142">根據具有條件式存取原則的登入屬性，要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="de020-142">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="de020-143">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="de020-143">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="de020-144">使用風險型條件式存取強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="de020-144">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="de020-145">根據使用適用於身分識別的 Microsoft Defender 的使用者登入的風險，要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="de020-145">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="de020-146">Microsoft 365 E5 或 E3 (含 Azure AD Premium P2 授權)</span><span class="sxs-lookup"><span data-stu-id="de020-146">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> |
| <span data-ttu-id="de020-147">自助式密碼重設 (SSPR)</span><span class="sxs-lookup"><span data-stu-id="de020-147">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="de020-148">允許您的使用者重設或解除鎖定他們的密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="de020-148">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="de020-149">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="de020-149">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="de020-150">Azure AD 應用程式 Proxy</span><span class="sxs-lookup"><span data-stu-id="de020-150">Azure AD Application Proxy</span></span>    | <span data-ttu-id="de020-151">針對內部網路伺服器上的網頁型應用程式，提供安全的遠端存取。</span><span class="sxs-lookup"><span data-stu-id="de020-151">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="de020-152">需要個別付費的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="de020-152">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="de020-153">Azure 點對站 VPN</span><span class="sxs-lookup"><span data-stu-id="de020-153">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="de020-154">透過 Azure 虛擬網路，建立從遠端工作者裝置到您內部網路的安全連線。</span><span class="sxs-lookup"><span data-stu-id="de020-154">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="de020-155">需要個別付費的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="de020-155">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="de020-156">Windows 虛擬桌面</span><span class="sxs-lookup"><span data-stu-id="de020-156">Windows Virtual Desktop</span></span>   | <span data-ttu-id="de020-157">支援只能在 Azure 中執行虛擬桌面才能使用其個人和不受管理裝置的遠端工作者。</span><span class="sxs-lookup"><span data-stu-id="de020-157">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="de020-158">需要個別付費的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="de020-158">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="de020-159">遠端桌面服務 (RDS)</span><span class="sxs-lookup"><span data-stu-id="de020-159">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="de020-160">允許員工連線到您內部網路上的 Windows 型電腦。</span><span class="sxs-lookup"><span data-stu-id="de020-160">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="de020-161">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="de020-161">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="de020-162">遠端桌面服務閘道</span><span class="sxs-lookup"><span data-stu-id="de020-162">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="de020-163">加密通訊並防止 RDS 主機直接暴露在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="de020-163">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="de020-164">需要不同的 Windows Server 授權</span><span class="sxs-lookup"><span data-stu-id="de020-164">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="de020-165">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="de020-165">Microsoft Intune</span></span> | <span data-ttu-id="de020-166">管理裝置和應用程式。</span><span class="sxs-lookup"><span data-stu-id="de020-166">Manage devices and applications.</span></span>   | <span data-ttu-id="de020-167">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="de020-167">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="de020-168">功能</span><span class="sxs-lookup"><span data-stu-id="de020-168">Configuration Manager</span></span> | <span data-ttu-id="de020-169">在您的裝置上管理軟體安裝、更新及設定</span><span class="sxs-lookup"><span data-stu-id="de020-169">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="de020-170">需要個別的 Configuration Manager 授權</span><span class="sxs-lookup"><span data-stu-id="de020-170">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="de020-171">電腦分析</span><span class="sxs-lookup"><span data-stu-id="de020-171">Desktop Analytics</span></span> | <span data-ttu-id="de020-172">判斷 Windows 用戶端的更新準備就緒狀況。</span><span class="sxs-lookup"><span data-stu-id="de020-172">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="de020-173">需要個別的 Configuration Manager 授權</span><span class="sxs-lookup"><span data-stu-id="de020-173">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="de020-174">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="de020-174">Windows Autopilot</span></span> | <span data-ttu-id="de020-175">設定並預先設定新的 Windows 10 裝置，以提高生產力。</span><span class="sxs-lookup"><span data-stu-id="de020-175">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="de020-176">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="de020-176">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="de020-177">Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive、Microsoft 365 Apps、Microsoft Power Platform 和 Yammer</span><span class="sxs-lookup"><span data-stu-id="de020-177">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, and Yammer</span></span> | <span data-ttu-id="de020-178">建立、溝通與共同作業。</span><span class="sxs-lookup"><span data-stu-id="de020-178">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="de020-179">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="de020-179">Microsoft 365 E3 or E5</span></span> |
||||

<span data-ttu-id="de020-180">如需安全性與合規性準則，請參閱[為遠端工作者部署安全性與合規性](empower-people-to-work-remotely-security-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="de020-180">For security and compliance criteria, see [Deploy security and compliance for remote workers](empower-people-to-work-remotely-security-compliance.md).</span></span>

<a name="poster"></a><span data-ttu-id="de020-181">如需這份解決方案的 2 頁摘要，請參閱[強化混合式工作者能力的海報](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)。</span><span class="sxs-lookup"><span data-stu-id="de020-181">For a 2-page summary of this solution, see the [Empower hybrid workers poster](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf).</span></span>

<span data-ttu-id="de020-182">[![強化混合式工作者能力的海報](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)</span><span class="sxs-lookup"><span data-stu-id="de020-182">[![Empower hybrid workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)</span></span>

<span data-ttu-id="de020-183">您也可以用 [PowerPoint](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pptx) 格式下載此海報，以及用 Letter、Legal 或 Tabloid (11 x 17) 大小的紙張列印此海報。</span><span class="sxs-lookup"><span data-stu-id="de020-183">You can also download this poster in [PowerPoint](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pptx) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="provide-hybrid-working-for-all-of-your-workers"></a><span data-ttu-id="de020-184">為您所有的員工提供混合式工作能力</span><span class="sxs-lookup"><span data-stu-id="de020-184">Provide hybrid working for all of your workers</span></span>

<span data-ttu-id="de020-185">您可以使用這些設備使您的所有員工在任何地方都能保持生產力：</span><span class="sxs-lookup"><span data-stu-id="de020-185">You can enable all of your workers to stay productive from anywhere with these devices:</span></span>

- <span data-ttu-id="de020-186">現代化設備（例如 Surface 膝上型電腦和 Windows 10），具有可透過網路直接存取 Microsoft 365 雲端應用程式和服務的功能、安全性和效能。</span><span class="sxs-lookup"><span data-stu-id="de020-186">A modern device, such as a Surface laptop and Windows 10, which has the features, security, and performance to access Microsoft 365 cloud apps and services directly over the web.</span></span>

- <span data-ttu-id="de020-187">任何裝置，包含在家中使用的舊版膝上型電腦或桌上型電腦，可透過快速部署 [Windows 10 版的虛擬桌面](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices)，間接存取 Microsoft 365 雲端應用程式和服務。</span><span class="sxs-lookup"><span data-stu-id="de020-187">Any device including older laptops or desktops used from home, which can access Microsoft 365 cloud apps and services indirectly through a quickly deployed [Windows 10-based virtual desktop](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices).</span></span> <span data-ttu-id="de020-188">此選項可提供高效能、強大的安全性和簡化版的 IT 管理。</span><span class="sxs-lookup"><span data-stu-id="de020-188">This option provides high performance, strong security, and simplified IT management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de020-189">後續步驟</span><span class="sxs-lookup"><span data-stu-id="de020-189">Next steps</span></span>

<span data-ttu-id="de020-190">使用下列步驟以保護和最佳化對組織的伺服器和雲端服務的存取，並將混合式工作者的生產力提升至最大。</span><span class="sxs-lookup"><span data-stu-id="de020-190">Use these steps to secure and optimize access to your organization's servers and cloud services and maximize your hybrid worker's productivity.</span></span>

1. [<span data-ttu-id="de020-191">使用 MFA 提升登入安全性</span><span class="sxs-lookup"><span data-stu-id="de020-191">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="de020-192">可遠端存取內部部署應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="de020-192">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="de020-193">部署安全性與合規性服務</span><span class="sxs-lookup"><span data-stu-id="de020-193">Deploy security and compliance services</span></span>](empower-people-to-work-remotely-security-compliance.md)
4. [<span data-ttu-id="de020-194">為您的裝置、電腦和其他端點部署端點管理</span><span class="sxs-lookup"><span data-stu-id="de020-194">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
5. [<span data-ttu-id="de020-195">部署混合式工作者生產力應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="de020-195">Deploy hybrid worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [<span data-ttu-id="de020-196">訓練工作者和處理使用上的意見反應</span><span class="sxs-lookup"><span data-stu-id="de020-196">Train your workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

<span data-ttu-id="de020-197">[![使用 Microsoft 365 設定混合式工作基礎結構的步驟](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="de020-197">[![The steps to set up your infrastructure for hybrid work with Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span></span>

<span data-ttu-id="de020-198">若要了解虛構但有代表性的多國組織如何設定其混合式工作基礎結構，請參閱[針對混合式工作的 Contoso COVID-19 回應和基礎架構](contoso-remote-onsite-work.md)。</span><span class="sxs-lookup"><span data-stu-id="de020-198">To see how a fictional but representative multi-national organization set up its infrastructure for hybrid work, see [Contoso's COVID-19 response and infrastructure for hybrid work](contoso-remote-onsite-work.md).</span></span>
