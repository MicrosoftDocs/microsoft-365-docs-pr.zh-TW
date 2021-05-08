---
title: 使用 Microsoft 365 設定遠端工作基礎結構。
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
description: 逐步執行基礎結構層，讓遠端工作者可以安全地存取內部部署和 Microsoft 365 資源。
ms.openlocfilehash: 1a8cf471cf92e1301c231f395ed0238bb35359cb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246317"
---
# <a name="set-up-your-infrastructure-for-remote-work-with-microsoft-365"></a><span data-ttu-id="c602a-104">使用 Microsoft 365 設定遠端工作基礎結構。</span><span class="sxs-lookup"><span data-stu-id="c602a-104">Set up your infrastructure for remote work with Microsoft 365</span></span>

<span data-ttu-id="c602a-105">若要保護及優化遠端工作者的生產力和共同作業，您必須設定 IT 和雲端基礎結構，以啟用遠端工作，並提供貴組織內部部署和雲端式資訊、工具和資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="c602a-105">To secure and optimize your remote worker’s productivity and collaboration, you need to configure your IT and cloud infrastructure to enable remote work and to provide access to your organization's on-premises and cloud-based information, tools, and resources.</span></span> <span data-ttu-id="c602a-106">此解決方案會執行重要基礎結構層部署的步驟，讓您的工作者無論身在何處，都能夠完成最佳工作。</span><span class="sxs-lookup"><span data-stu-id="c602a-106">This solution steps through the deployment of key layers of infrastructure that empower your workers to do their best work, wherever they are.</span></span>

<span data-ttu-id="c602a-107">允許員工遠端辦公對許多組織達到以下目的非常重要:</span><span class="sxs-lookup"><span data-stu-id="c602a-107">Allowing workers to work away from the office is important for many organizations to:</span></span>

- <span data-ttu-id="c602a-108">節省辦公室空間。</span><span class="sxs-lookup"><span data-stu-id="c602a-108">Save on office space.</span></span>
- <span data-ttu-id="c602a-109">聘用並留住不願意調派的工作人員。</span><span class="sxs-lookup"><span data-stu-id="c602a-109">Hire and retain workers who are unwilling to relocate.</span></span>
- <span data-ttu-id="c602a-110">縮短工作人員的通勤時間，讓他們有更多時間來提高生產力，並在下班後放鬆壓力。</span><span class="sxs-lookup"><span data-stu-id="c602a-110">Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="c602a-111">Microsoft 365 具備讓您的工作人員能夠遠端作業的功能。</span><span class="sxs-lookup"><span data-stu-id="c602a-111">Microsoft 365 has the capabilities to empower your workers to work remotely.</span></span>

![使用 Microsoft 365 強化您的遠端工作人員](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

>[!Note]
><span data-ttu-id="c602a-113">如果您是 Microsoft 365 新使用者，請參閱[這些資源](https://www.microsoft.com/microsoft-365)。</span><span class="sxs-lookup"><span data-stu-id="c602a-113">If you are new to Microsoft 365, see [these resources](https://www.microsoft.com/microsoft-365).</span></span>
>

<span data-ttu-id="c602a-114">觀看此影片以取得部署程序的概觀。</span><span class="sxs-lookup"><span data-stu-id="c602a-114">Watch this video for an overview of the deployment process.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

<span data-ttu-id="c602a-115">為了讓管理現場和雲端式基礎結構的 IT 專業人員能夠實現工作者生產力，此解決方案提供下列重要功能：</span><span class="sxs-lookup"><span data-stu-id="c602a-115">For IT professionals managing onsite and cloud-based infrastructure to enable worker productivity, this solution provides these key capabilities:</span></span>

- <span data-ttu-id="c602a-116">連接</span><span class="sxs-lookup"><span data-stu-id="c602a-116">Connected</span></span>

  <span data-ttu-id="c602a-117">遠端工作人員必須能夠隨時隨地存取：</span><span class="sxs-lookup"><span data-stu-id="c602a-117">From anywhere in the world and at any time, remote workers are able to access:</span></span> 

  - <span data-ttu-id="c602a-118">您的 Microsoft 365 訂閱中的雲端服務和資料。</span><span class="sxs-lookup"><span data-stu-id="c602a-118">Cloud-based services and data in your Microsoft 365 subscription.</span></span> 

  - <span data-ttu-id="c602a-119">組織資源，例如內部部署應用程式資料中心所提供的資源。</span><span class="sxs-lookup"><span data-stu-id="c602a-119">Organization resources, such those offered by on-premises application datacenters.</span></span>

- <span data-ttu-id="c602a-120">安全</span><span class="sxs-lookup"><span data-stu-id="c602a-120">Secure</span></span>

  <span data-ttu-id="c602a-121">以 Microsoft 365 和 Windows 10 的多重要素驗證（MFA）和內建安全性功能保護登入，避免惡意程式碼、惡意攻擊和資料遺失。</span><span class="sxs-lookup"><span data-stu-id="c602a-121">Sign-ins are secured with multi-factor authentication (MFA) and built-in security features of Microsoft 365 and Windows 10 protect against malware, malicious attacks, and data loss.</span></span>

- <span data-ttu-id="c602a-122">受管理</span><span class="sxs-lookup"><span data-stu-id="c602a-122">Managed</span></span>

  <span data-ttu-id="c602a-123">您可以透過安全性設定、允許的應用程式和對系統健康的符合要求以雲端來管理您的遠端工作人員的裝置。</span><span class="sxs-lookup"><span data-stu-id="c602a-123">Your remote worker's devices can be managed from the cloud with security settings, allowed apps, and to require compliance with system health.</span></span>

- <span data-ttu-id="c602a-124">共同作業和生產力</span><span class="sxs-lookup"><span data-stu-id="c602a-124">Collaborative and productive</span></span>

  <span data-ttu-id="c602a-125">透過以下高度協作的方式，您的遠端工作人員可以像在內部部屬工作時一樣高效:</span><span class="sxs-lookup"><span data-stu-id="c602a-125">Your remote workers can be as productive as on-premises in a highly collaborative way with:</span></span>

  - <span data-ttu-id="c602a-126">以 Teams 進行線上會議和聊天會話。</span><span class="sxs-lookup"><span data-stu-id="c602a-126">Online meetings and chat sessions with Teams.</span></span> 

  - <span data-ttu-id="c602a-127">透過 SharePoint 和 OneDrive，使用全域協助工具和即時共同作業的雲端式檔案儲存空間以共用工作區。</span><span class="sxs-lookup"><span data-stu-id="c602a-127">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration with SharePoint and OneDrive.</span></span>

  - <span data-ttu-id="c602a-128">共用工作和工作流程來劃分並完成工作。</span><span class="sxs-lookup"><span data-stu-id="c602a-128">Shared tasks and workflows to divide up the work and get things done.</span></span> 

<span data-ttu-id="c602a-129">若要取得無縫登入體驗，您的內部部署 Active Directory 網域服務 (AD DS) 使用者帳戶應與 Azure Active Directory (Azure AD) 同步處理。</span><span class="sxs-lookup"><span data-stu-id="c602a-129">For a seamless sign-in experience, your on-premises Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c602a-130">為了保護您的 Windows 10 裝置，應在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="c602a-130">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="c602a-131">以下是基礎結構的高階檢視。</span><span class="sxs-lookup"><span data-stu-id="c602a-131">Here is a high-level view of the infrastructure.</span></span>

![適用於使用 Microsoft 365 之遠端工作者的基本基礎結構](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

<span data-ttu-id="c602a-133">若要為您的遠端工作者啟用 Microsoft 365 的功能，請使用這些 Microsoft 365 功能。</span><span class="sxs-lookup"><span data-stu-id="c602a-133">To enable the capabilities of Microsoft 365 for your remote workers, use these Microsoft 365 features.</span></span>

| <span data-ttu-id="c602a-134">功能</span><span class="sxs-lookup"><span data-stu-id="c602a-134">Capability or feature</span></span> | <span data-ttu-id="c602a-135">描述</span><span class="sxs-lookup"><span data-stu-id="c602a-135">Description</span></span> | <span data-ttu-id="c602a-136">授權</span><span class="sxs-lookup"><span data-stu-id="c602a-136">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c602a-137">採用安全性預設值強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="c602a-137">MFA enforced with security defaults</span></span>   | <span data-ttu-id="c602a-138">要求第二種形式的登入驗證，以防止身分識別和裝置遭到入侵。安全性預設值要求所有使用者帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="c602a-138">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="c602a-139">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="c602a-139">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c602a-140">使用條件式存取強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="c602a-140">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="c602a-141">根據具有條件式存取原則的登入屬性，要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="c602a-141">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="c602a-142">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="c602a-142">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c602a-143">使用風險型條件式存取強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="c602a-143">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="c602a-144">根據使用適用於身分識別的 Microsoft Defender 的使用者登入的風險，要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="c602a-144">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="c602a-145">Microsoft 365 E5 或 E3 (含 Azure AD Premium P2 授權)</span><span class="sxs-lookup"><span data-stu-id="c602a-145">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="c602a-146">自助式密碼重設 (SSPR)</span><span class="sxs-lookup"><span data-stu-id="c602a-146">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="c602a-147">允許您的使用者重設或解除鎖定他們的密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="c602a-147">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="c602a-148">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="c602a-148">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c602a-149">Azure AD 應用程式 Proxy</span><span class="sxs-lookup"><span data-stu-id="c602a-149">Azure AD Application Proxy</span></span>    | <span data-ttu-id="c602a-150">針對內部網路伺服器上的網頁型應用程式，提供安全的遠端存取。</span><span class="sxs-lookup"><span data-stu-id="c602a-150">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="c602a-151">需要個別付費的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="c602a-151">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="c602a-152">Azure 點對站 VPN</span><span class="sxs-lookup"><span data-stu-id="c602a-152">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="c602a-153">透過 Azure 虛擬網路，建立從遠端工作者裝置到您內部網路的安全連線。</span><span class="sxs-lookup"><span data-stu-id="c602a-153">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="c602a-154">需要個別付費的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="c602a-154">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="c602a-155">Windows 虛擬桌面</span><span class="sxs-lookup"><span data-stu-id="c602a-155">Windows Virtual Desktop</span></span>   | <span data-ttu-id="c602a-156">支援只能在 Azure 中執行虛擬桌面才能使用其個人和不受管理裝置的遠端工作者。</span><span class="sxs-lookup"><span data-stu-id="c602a-156">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="c602a-157">需要個別付費的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="c602a-157">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="c602a-158">遠端桌面服務 (RDS)</span><span class="sxs-lookup"><span data-stu-id="c602a-158">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="c602a-159">允許員工連線到您內部網路上的 Windows 型電腦。</span><span class="sxs-lookup"><span data-stu-id="c602a-159">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="c602a-160">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="c602a-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c602a-161">遠端桌面服務閘道</span><span class="sxs-lookup"><span data-stu-id="c602a-161">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="c602a-162">加密通訊並防止 RDS 主機直接暴露在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="c602a-162">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="c602a-163">需要不同的 Windows Server 授權</span><span class="sxs-lookup"><span data-stu-id="c602a-163">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="c602a-164">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c602a-164">Microsoft Intune</span></span> | <span data-ttu-id="c602a-165">管理裝置和應用程式。</span><span class="sxs-lookup"><span data-stu-id="c602a-165">Manage devices and applications.</span></span>   | <span data-ttu-id="c602a-166">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="c602a-166">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c602a-167">功能</span><span class="sxs-lookup"><span data-stu-id="c602a-167">Configuration Manager</span></span> | <span data-ttu-id="c602a-168">在您的裝置上管理軟體安裝、更新及設定</span><span class="sxs-lookup"><span data-stu-id="c602a-168">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="c602a-169">需要個別的 Configuration Manager 授權</span><span class="sxs-lookup"><span data-stu-id="c602a-169">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="c602a-170">電腦分析</span><span class="sxs-lookup"><span data-stu-id="c602a-170">Desktop Analytics</span></span> | <span data-ttu-id="c602a-171">判斷 Windows 用戶端的更新準備就緒狀況。</span><span class="sxs-lookup"><span data-stu-id="c602a-171">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="c602a-172">需要個別的 Configuration Manager 授權</span><span class="sxs-lookup"><span data-stu-id="c602a-172">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="c602a-173">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="c602a-173">Windows Autopilot</span></span> | <span data-ttu-id="c602a-174">設定並預先設定新的 Windows 10 裝置，以提高生產力。</span><span class="sxs-lookup"><span data-stu-id="c602a-174">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="c602a-175">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="c602a-175">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c602a-176">Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive、Microsoft 365 Apps、Microsoft Power Platform 和 Yammer</span><span class="sxs-lookup"><span data-stu-id="c602a-176">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, and Yammer</span></span> | <span data-ttu-id="c602a-177">建立、溝通與共同作業。</span><span class="sxs-lookup"><span data-stu-id="c602a-177">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="c602a-178">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="c602a-178">Microsoft 365 E3 or E5</span></span> |
||||

<span data-ttu-id="c602a-179">如需安全性與合規性準則，請參閱[為遠端工作者部署安全性與合規性](empower-people-to-work-remotely-security-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="c602a-179">For security and compliance criteria, see [Deploy security and compliance for remote workers](empower-people-to-work-remotely-security-compliance.md).</span></span>

<a name="poster"></a> <span data-ttu-id="c602a-180">如需這份解決方案的2頁摘要，請參閱 [[強化遠端工作人員] 海報](../downloads/empower-remote-workers.pdf)。</span><span class="sxs-lookup"><span data-stu-id="c602a-180">For a 2-page summary of this solution, see the [Empower remote workers poster](../downloads/empower-remote-workers.pdf).</span></span>

<span data-ttu-id="c602a-181">[![強化遠端工作人員海報](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)</span><span class="sxs-lookup"><span data-stu-id="c602a-181">[![Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)</span></span>

<span data-ttu-id="c602a-182">您也可以以 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) 或 [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx) 格式下載此海報，然後使用 Letter、Legal 或 Tabloid (11 x 17) 大小的紙張列印此海報。</span><span class="sxs-lookup"><span data-stu-id="c602a-182">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) or  [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="provide-remote-working-for-all-of-your-workers"></a><span data-ttu-id="c602a-183">為您所有的員工提供遠端工作能力</span><span class="sxs-lookup"><span data-stu-id="c602a-183">Provide remote working for all of your workers</span></span>

<span data-ttu-id="c602a-184">您可以使用這些設備使您的所有員工在任何地方都能保持生產力：</span><span class="sxs-lookup"><span data-stu-id="c602a-184">You can enable all of your workers to stay productive from anywhere with these devices:</span></span>

- <span data-ttu-id="c602a-185">現代化設備（例如 Surface 膝上型電腦和 Windows 10），具有可透過網路直接存取 Microsoft 365 雲端應用程式和服務的功能、安全性和效能。</span><span class="sxs-lookup"><span data-stu-id="c602a-185">A modern device, such as a Surface laptop and Windows 10, which has the features, security, and performance to access Microsoft 365 cloud apps and services directly over the web.</span></span>

- <span data-ttu-id="c602a-186">任何裝置，包含在家中使用的舊版膝上型電腦或桌上型電腦，可透過快速部署 [Windows 10 版的虛擬桌面](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices)，間接存取 Microsoft 365 雲端應用程式和服務。</span><span class="sxs-lookup"><span data-stu-id="c602a-186">Any device including older laptops or desktops used from home, which can access Microsoft 365 cloud apps and services indirectly through a quickly deployed [Windows 10-based virtual desktop](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices).</span></span> <span data-ttu-id="c602a-187">此選項可提供高效能、強大的安全性和簡化版的 IT 管理。</span><span class="sxs-lookup"><span data-stu-id="c602a-187">This option provides high performance, strong security, and simplified IT management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c602a-188">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c602a-188">Next steps</span></span>

<span data-ttu-id="c602a-189">使用下列步驟以保護和最佳化對組織的伺服器和雲端服務的存取，並將遠端工作者的生產力提升至最大。</span><span class="sxs-lookup"><span data-stu-id="c602a-189">Use these steps to secure and optimize access to your organization's servers and cloud services and maximize your remote worker's productivity.</span></span>

1. [<span data-ttu-id="c602a-190">使用 MFA 提升登入安全性</span><span class="sxs-lookup"><span data-stu-id="c602a-190">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="c602a-191">可遠端存取內部部署應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="c602a-191">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="c602a-192">部署安全性與合規性服務</span><span class="sxs-lookup"><span data-stu-id="c602a-192">Deploy security and compliance services</span></span>](empower-people-to-work-remotely-security-compliance.md)
4. [<span data-ttu-id="c602a-193">為您的裝置、電腦和其他端點部署端點管理</span><span class="sxs-lookup"><span data-stu-id="c602a-193">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
5. [<span data-ttu-id="c602a-194">部署遠端工作者生產力應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="c602a-194">Deploy remote worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [<span data-ttu-id="c602a-195">訓練遠端工作者和處理使用上的意見反應</span><span class="sxs-lookup"><span data-stu-id="c602a-195">Train remote workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

<span data-ttu-id="c602a-196">[![使用 Microsoft 365 設定遠端工作基礎結構的步驟](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="c602a-196">[![The steps to set up your infrastructure for remote work with Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span></span>

<span data-ttu-id="c602a-197">若要了解虛構但有代表性的多國組織如何設定其遠端工作基礎結構，請參閱 [針對遠端和辦公室工作的 Contoso COVID-19 回應和基礎架構](contoso-remote-onsite-work.md)。</span><span class="sxs-lookup"><span data-stu-id="c602a-197">To see how a fictional but representative multi-national organization set up its infrastructure for remote work, see [Contoso's COVID-19 response and infrastructure for remote and onsite work](contoso-remote-onsite-work.md).</span></span>
