---
title: 使用 Microsoft 365 強化遠端工作者
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 設定安全性和服務基礎結構，讓您的工作人員隨時隨地都能遠端工作。
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560458"
---
# <a name="empower-remote-workers-with-microsoft-365"></a><span data-ttu-id="65516-103">使用 Microsoft 365 強化遠端工作者</span><span class="sxs-lookup"><span data-stu-id="65516-103">Empower remote workers with Microsoft 365</span></span>

<span data-ttu-id="65516-104">貴組織可能必須讓工作人員能夠從家裡安全地存取貴組織的內部部署與雲端式資訊、工具及資源。</span><span class="sxs-lookup"><span data-stu-id="65516-104">Your business may need to enable your workers to have secure access to your organization's on-premises and cloud-based information, tools, and resources from their homes.</span></span> <span data-ttu-id="65516-105">對於許多組織而言，能讓工作人員順暢且安全地不在辦公室工作是非常重要的，可達到以下目的：</span><span class="sxs-lookup"><span data-stu-id="65516-105">Allowing workers to work away from the office seamlessly and securely is important for many organizations to:</span></span>

- <span data-ttu-id="65516-106">節省辦公室空間。</span><span class="sxs-lookup"><span data-stu-id="65516-106">Save on office space.</span></span>
- <span data-ttu-id="65516-107">聘用並留住不願意調派的工作人員。</span><span class="sxs-lookup"><span data-stu-id="65516-107">Hire and retain workers who are unwilling to relocate.</span></span>
- <span data-ttu-id="65516-108">縮短工作人員的通勤時間，讓他們有更多時間來提高生產力，並在下班後放鬆壓力。</span><span class="sxs-lookup"><span data-stu-id="65516-108">Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="65516-109">遠端工作 (又稱為遠距工作) 可以涵蓋以下範圍：</span><span class="sxs-lookup"><span data-stu-id="65516-109">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="65516-110">偶爾會離開辦公室去參加會議或客戶會議的工作人員。</span><span class="sxs-lookup"><span data-stu-id="65516-110">workers that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="65516-111">遠端全職工作的部分工作人員。</span><span class="sxs-lookup"><span data-stu-id="65516-111">Some workers that work remotely full-time.</span></span>
- <span data-ttu-id="65516-112">沒有辦公室且所有工作者皆為遠端工作的完全遠端組織。</span><span class="sxs-lookup"><span data-stu-id="65516-112">A fully remote organization in which there is no office and all workers are remote.</span></span>

<span data-ttu-id="65516-113">無論身在何處，遠端工作者都必須能夠隨時存取：</span><span class="sxs-lookup"><span data-stu-id="65516-113">From anywhere in the world and at any time, remote workers must be able to access:</span></span>

- <span data-ttu-id="65516-114">組織資源，例如內部部署應用程式資料中心所提供的資源。</span><span class="sxs-lookup"><span data-stu-id="65516-114">Organization resources, such those offered by on-premises application datacenters.</span></span>
- <span data-ttu-id="65516-115">Microsoft 365 訂閱中的雲端服務和資料，例如 Teams、Exchange Online、SharePoint 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="65516-115">Cloud-based services and data in your Microsoft 365 subscription, such as Teams, Exchange Online, SharePoint, and OneDrive.</span></span>

<span data-ttu-id="65516-116">若要取得無縫登入體驗，您的 Active Directory 網域服務 (AD DS) 使用者帳戶應與 Azure Active Directory (Azure AD) 同步處理。</span><span class="sxs-lookup"><span data-stu-id="65516-116">For a seamless sign-in experience, your Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="65516-117">為了保護您的 Windows 10 裝置，應在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="65516-117">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="65516-118">以下是基礎結構的高階檢視。</span><span class="sxs-lookup"><span data-stu-id="65516-118">Here is a high-level view of the infrastructure.</span></span>

![適用於使用 Microsoft 365 之遠端工作者的基本基礎結構](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


<span data-ttu-id="65516-120">為了支援遠端工作者 (例如因應 COVID-19 疫情)，Microsoft 365 的功能組合能以高度共同作業的方式來啟用您的遠端工作者，例如：</span><span class="sxs-lookup"><span data-stu-id="65516-120">To support remote workers, for example in response to the COVID-19 crisis, a combination of features in Microsoft 365 enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="65516-121">線上會議和聊天工作階段。</span><span class="sxs-lookup"><span data-stu-id="65516-121">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="65516-122">使用全域協助工具和即時共同作業的雲端式檔案儲存空間以共用工作區。</span><span class="sxs-lookup"><span data-stu-id="65516-122">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="65516-123">共用工作和工作流程來劃分並完成工作。</span><span class="sxs-lookup"><span data-stu-id="65516-123">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="65516-124">為了加強安全性，Microsoft 365 包括：</span><span class="sxs-lookup"><span data-stu-id="65516-124">For strong security, Microsoft 365 includes:</span></span>

- <span data-ttu-id="65516-125">強制執行驗證需求、偵測及回應高風險的登入，並封鎖選取的應用程式和不相容的裝置。</span><span class="sxs-lookup"><span data-stu-id="65516-125">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="65516-126">加密連線與雲端中的數位資產。</span><span class="sxs-lookup"><span data-stu-id="65516-126">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="65516-127">用權限來定義使用者能夠如何使用檔案。</span><span class="sxs-lookup"><span data-stu-id="65516-127">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="65516-128">可保護 Windows 10 裝置的全面安全性功能。</span><span class="sxs-lookup"><span data-stu-id="65516-128">Comprehensive security features to protect Windows 10 devices.</span></span>

<span data-ttu-id="65516-129">遠端工作人員若要符合這些條件，請使用下列 Microsoft 365 功能：</span><span class="sxs-lookup"><span data-stu-id="65516-129">To meet these criteria for remote workers, use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="65516-130">功能</span><span class="sxs-lookup"><span data-stu-id="65516-130">Capability or feature</span></span> | <span data-ttu-id="65516-131">描述</span><span class="sxs-lookup"><span data-stu-id="65516-131">Description</span></span> | <span data-ttu-id="65516-132">授權</span><span class="sxs-lookup"><span data-stu-id="65516-132">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="65516-133">採用安全性預設值強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="65516-133">MFA enforced with security defaults</span></span>   | <span data-ttu-id="65516-134">要求第二種形式的登入驗證，以防止身分識別和裝置遭到入侵。安全性預設值要求所有使用者帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="65516-134">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="65516-135">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="65516-135">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="65516-136">使用條件式存取強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="65516-136">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="65516-137">根據具有條件式存取原則的登入屬性，要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="65516-137">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="65516-138">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="65516-138">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="65516-139">使用風險型條件式存取強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="65516-139">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="65516-140">根據使用者使用 Azure 進階威脅防護登入的風險要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="65516-140">Require MFA based on the risk of the user sign-in with Azure Advanced Threat Protection.</span></span> | <span data-ttu-id="65516-141">Microsoft 365 E5 或 E3 (含 Azure AD Premium P2 授權)</span><span class="sxs-lookup"><span data-stu-id="65516-141">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="65516-142">自助式密碼重設 (SSPR)</span><span class="sxs-lookup"><span data-stu-id="65516-142">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="65516-143">允許您的使用者重設或解除鎖定他們的密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="65516-143">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="65516-144">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="65516-144">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="65516-145">Azure AD 應用程式 Proxy</span><span class="sxs-lookup"><span data-stu-id="65516-145">Azure AD Application Proxy</span></span>    | <span data-ttu-id="65516-146">針對內部網路伺服器上的網頁型應用程式，提供安全的遠端存取。</span><span class="sxs-lookup"><span data-stu-id="65516-146">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="65516-147">需要個別付費的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="65516-147">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="65516-148">Azure 點對站 VPN</span><span class="sxs-lookup"><span data-stu-id="65516-148">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="65516-149">透過 Azure 虛擬網路，建立從遠端工作者裝置到您內部網路的安全連線。</span><span class="sxs-lookup"><span data-stu-id="65516-149">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="65516-150">需要個別付費的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="65516-150">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="65516-151">Windows 虛擬桌面</span><span class="sxs-lookup"><span data-stu-id="65516-151">Windows Virtual Desktop</span></span>   | <span data-ttu-id="65516-152">支援只能在 Azure 中執行虛擬桌面才能使用其個人和不受管理裝置的遠端工作者。</span><span class="sxs-lookup"><span data-stu-id="65516-152">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="65516-153">需要個別付費的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="65516-153">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="65516-154">遠端桌面服務 (RDS)</span><span class="sxs-lookup"><span data-stu-id="65516-154">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="65516-155">允許員工連線到您內部網路上的 Windows 型電腦。</span><span class="sxs-lookup"><span data-stu-id="65516-155">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="65516-156">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="65516-156">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="65516-157">遠端桌面服務閘道</span><span class="sxs-lookup"><span data-stu-id="65516-157">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="65516-158">加密通訊並防止 RDS 主機直接暴露在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="65516-158">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="65516-159">需要不同的 Windows Server 授權</span><span class="sxs-lookup"><span data-stu-id="65516-159">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="65516-160">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="65516-160">Microsoft Intune</span></span> | <span data-ttu-id="65516-161">管理裝置和應用程式。</span><span class="sxs-lookup"><span data-stu-id="65516-161">Manage devices and applications.</span></span>   | <span data-ttu-id="65516-162">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="65516-162">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="65516-163">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="65516-163">Configuration Manager</span></span> | <span data-ttu-id="65516-164">在您的裝置上管理軟體安裝、更新及設定</span><span class="sxs-lookup"><span data-stu-id="65516-164">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="65516-165">需要個別的 Configuration Manager 授權</span><span class="sxs-lookup"><span data-stu-id="65516-165">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="65516-166">電腦分析</span><span class="sxs-lookup"><span data-stu-id="65516-166">Desktop Analytics</span></span> | <span data-ttu-id="65516-167">判斷 Windows 用戶端的更新準備就緒狀況。</span><span class="sxs-lookup"><span data-stu-id="65516-167">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="65516-168">需要個別的 Configuration Manager 授權</span><span class="sxs-lookup"><span data-stu-id="65516-168">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="65516-169">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="65516-169">Windows Autopilot</span></span> | <span data-ttu-id="65516-170">設定並預先設定新的 Windows 10 裝置，以提高生產力。</span><span class="sxs-lookup"><span data-stu-id="65516-170">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="65516-171">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="65516-171">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="65516-172">Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive、Microsoft 365 Apps、Microsoft Power Platform、Yammer、Power Apps</span><span class="sxs-lookup"><span data-stu-id="65516-172">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps</span></span> | <span data-ttu-id="65516-173">建立、溝通與共同作業。</span><span class="sxs-lookup"><span data-stu-id="65516-173">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="65516-174">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="65516-174">Microsoft 365 E3 and E5</span></span> |
||||

<span data-ttu-id="65516-175">請使用下列步驟來保護和最佳化組織伺服器、資料和雲端服務的存取，並讓員工發揮最高的生產力。</span><span class="sxs-lookup"><span data-stu-id="65516-175">Use these steps to secure and optimize access to your organization's servers, data, and cloud services and enable maximum worker productivity.</span></span>

1. [<span data-ttu-id="65516-176">使用 MFA 提升登入安全性</span><span class="sxs-lookup"><span data-stu-id="65516-176">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="65516-177">可遠端存取內部部署應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="65516-177">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="65516-178">為您的裝置、電腦和其他端點部署端點管理</span><span class="sxs-lookup"><span data-stu-id="65516-178">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
4. [<span data-ttu-id="65516-179">部署遠端工作者生產力應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="65516-179">Deploy remote worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [<span data-ttu-id="65516-180">建立通訊地點</span><span class="sxs-lookup"><span data-stu-id="65516-180">Create communication venues</span></span>](empower-people-to-work-remotely-communication-venues.md)
6. [<span data-ttu-id="65516-181">訓練遠端工作者和處理使用上的意見反應</span><span class="sxs-lookup"><span data-stu-id="65516-181">Train remote workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

![使用 Microsoft 365 強化遠端工作人員的步驟](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

<span data-ttu-id="65516-183">如需有關支援遠端工作人員的 Microsoft 最新資訊，請參閱[啟用遠端工作技術社群網站](https://resources.techcommunity.microsoft.com/enabling-remote-work/)。</span><span class="sxs-lookup"><span data-stu-id="65516-183">For the latest information from Microsoft about supporting remote workers, see the [Enabling remote work Tech Community site](https://resources.techcommunity.microsoft.com/enabling-remote-work/).</span></span>
