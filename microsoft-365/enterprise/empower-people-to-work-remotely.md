---
title: 強化遠端工作人員
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 設定基礎結構和安全性，讓您的員工隨時隨地都能遠端工作。
ms.openlocfilehash: cfbabfbe0c239ca837356b585171778d40daaa93
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2020
ms.locfileid: "42952051"
---
# <a name="empower-remote-workers"></a><span data-ttu-id="b4d19-103">強化遠端工作人員</span><span class="sxs-lookup"><span data-stu-id="b4d19-103">Empower remote workers</span></span>

<span data-ttu-id="b4d19-104">*此案例同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b4d19-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b4d19-105">讓員工順利安全地在辦公室之外工作，對於多組織很重要，可以節省辦公室空間、雇用並留住不願意搬家的員工，以及降低員工的通勤時間，讓員工擁有更多時間來提高生產力和從事工作之外的減輕壓力的活動。</span><span class="sxs-lookup"><span data-stu-id="b4d19-105">Allowing employees to work away from the office seamlessly and securely is important for many organizations to save on office space, hire and retain employees who are unwilling to relocate, and reduce employee commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="b4d19-106">遠端工作 (又稱為遠距工作) 可以涵蓋以下範圍：</span><span class="sxs-lookup"><span data-stu-id="b4d19-106">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="b4d19-107">偶爾會離開辦公室去參加會議或客戶會議的員工。</span><span class="sxs-lookup"><span data-stu-id="b4d19-107">Employees that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="b4d19-108">遠端全職工作的部分員工。</span><span class="sxs-lookup"><span data-stu-id="b4d19-108">Some employees that work remotely full-time.</span></span>
- <span data-ttu-id="b4d19-109">沒有辦公室且所有員工皆為遠端的完全遠端組織。</span><span class="sxs-lookup"><span data-stu-id="b4d19-109">A fully remote organization in which there is no office and all employees are remote.</span></span>

<span data-ttu-id="b4d19-110">為了支援遠端工作人員，Microsoft 365 企業版的功能組合能以高度共同作業的方式來啟用您的遠端工作人員，例如：</span><span class="sxs-lookup"><span data-stu-id="b4d19-110">To support remote workers, a combination of features in Microsoft 365 Enterprise enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="b4d19-111">線上會議和聊天工作階段。</span><span class="sxs-lookup"><span data-stu-id="b4d19-111">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="b4d19-112">使用全域協助工具和即時共同作業的雲端式檔案儲存空間以共用工作區。</span><span class="sxs-lookup"><span data-stu-id="b4d19-112">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="b4d19-113">共用工作和工作流程來劃分並完成工作。</span><span class="sxs-lookup"><span data-stu-id="b4d19-113">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="b4d19-114">為了加強安全性，Microsoft 365 企業版包括：</span><span class="sxs-lookup"><span data-stu-id="b4d19-114">For strong security, Microsoft 365 Enterprise includes:</span></span>

- <span data-ttu-id="b4d19-115">強制執行驗證需求、偵測及回應高風險的登入，並封鎖選取的應用程式和不相容的裝置。</span><span class="sxs-lookup"><span data-stu-id="b4d19-115">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="b4d19-116">加密連線與雲端中的數位資產。</span><span class="sxs-lookup"><span data-stu-id="b4d19-116">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="b4d19-117">用權限來定義使用者能夠如何使用檔案。</span><span class="sxs-lookup"><span data-stu-id="b4d19-117">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="b4d19-118">資料外洩防護 (DLP) 用來防止高管制資料外洩。</span><span class="sxs-lookup"><span data-stu-id="b4d19-118">Data loss prevention (DLP) to prevent leakage of highly regulated data.</span></span>

<span data-ttu-id="b4d19-119">遠端工作人員若要符合這些條件，請使用下列 Microsoft 365 企業版功能：</span><span class="sxs-lookup"><span data-stu-id="b4d19-119">To meet these criteria for remote workers, use the following Microsoft 365 Enterprise features:</span></span>

- <span data-ttu-id="b4d19-120">使用者身分識別與登入安全性</span><span class="sxs-lookup"><span data-stu-id="b4d19-120">User identity and sign-in security</span></span>
  - <span data-ttu-id="b4d19-121">Azure Active Directory (Azure AD) 使用多重要素驗證 (MFA) 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="b4d19-121">Azure Active Directory (Azure AD) user accounts with multi-factor authentication (MFA)</span></span>
  - <span data-ttu-id="b4d19-122">設定條件式存取原則，要求對有風險的登入進行 MFA</span><span class="sxs-lookup"><span data-stu-id="b4d19-122">Conditional Access policies to require MFA for risky sign-ins</span></span>
- <span data-ttu-id="b4d19-123">共同作業平台</span><span class="sxs-lookup"><span data-stu-id="b4d19-123">Collaboration platforms</span></span>
  - <span data-ttu-id="b4d19-124">遠端工作人員可以使用 Microsoft Teams、SharePoint 和 OneDrive 來排程和參加線上視訊會議，並同時處理相同的文件</span><span class="sxs-lookup"><span data-stu-id="b4d19-124">Microsoft Teams, SharePoint, and OneDrive, with which remote workers can schedule and attend online video-based meetings and work on the same documents at the same time</span></span>
- <span data-ttu-id="b4d19-125">安全的資源存取</span><span class="sxs-lookup"><span data-stu-id="b4d19-125">Secure access to resources</span></span>
  - <span data-ttu-id="b4d19-126">使用 Teams、SharePoint 網站和 OneDrive 的群組和權限，以便只有經過驗證且被允許的使用者才能存取</span><span class="sxs-lookup"><span data-stu-id="b4d19-126">Groups and permissions for Teams, SharePoint sites, and OneDrive so that only authenticated and permitted users have access</span></span>
- <span data-ttu-id="b4d19-127">外洩檔案的保護</span><span class="sxs-lookup"><span data-stu-id="b4d19-127">Protection for leaked files</span></span>
  - <span data-ttu-id="b4d19-128">Office 365 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="b4d19-128">Office 365 DLP policies</span></span>
  - <span data-ttu-id="b4d19-129">跟隨檔案的敏感度標籤，用於加密和權限</span><span class="sxs-lookup"><span data-stu-id="b4d19-129">Sensitivity labels for encryption and permissions that travel with files</span></span>
- <span data-ttu-id="b4d19-130">Microsoft Intune 的裝置管理和安全性</span><span class="sxs-lookup"><span data-stu-id="b4d19-130">Device management and security with Microsoft Intune</span></span>
  - <span data-ttu-id="b4d19-131">註冊受管理裝置</span><span class="sxs-lookup"><span data-stu-id="b4d19-131">Enrollment for managed devices</span></span>
  - <span data-ttu-id="b4d19-132">個人裝置的應用程式設定</span><span class="sxs-lookup"><span data-stu-id="b4d19-132">App settings for personal devices</span></span>
  - <span data-ttu-id="b4d19-133">裝置和應用程式原則</span><span class="sxs-lookup"><span data-stu-id="b4d19-133">Device and app policies</span></span>
- <span data-ttu-id="b4d19-134">裝置的生產力應用程式</span><span class="sxs-lookup"><span data-stu-id="b4d19-134">Productivity apps for devices</span></span>
  - <span data-ttu-id="b4d19-135">Office 365 專業增強版應用程式搭配 Teams、SharePoint 和 OneDrive 進行共同作業的體驗</span><span class="sxs-lookup"><span data-stu-id="b4d19-135">Office 365 ProPlus apps for collaborative experiences with Teams, SharePoint, and OneDrive</span></span> 
- <span data-ttu-id="b4d19-136">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="b4d19-136">Windows 10 Enterprise</span></span>
  - <span data-ttu-id="b4d19-137">全面的安全性功能，可防範網路攻擊並防止資料外洩</span><span class="sxs-lookup"><span data-stu-id="b4d19-137">Comprehensive security features to protect against cyberattacks and prevent data leakage</span></span>
- <span data-ttu-id="b4d19-138">存取內部部署應用程式</span><span class="sxs-lookup"><span data-stu-id="b4d19-138">Access to on-premises apps</span></span>
  - <span data-ttu-id="b4d19-139">具有混合式身分識別的組織可以使用 Azure AD 應用程式 Proxy，而不是使用虛擬私人網路 (VPN) 連線</span><span class="sxs-lookup"><span data-stu-id="b4d19-139">Organizations that have hybrid identity can use Azure AD Application Proxy instead of virtual private network (VPN) connections</span></span>

<span data-ttu-id="b4d19-140">下列階段逐步引導您部署適用于遠端存取的 Microsoft 365 企業版功能，並推動採用遠端工作人員。</span><span class="sxs-lookup"><span data-stu-id="b4d19-140">The following phases step you through deploying the feature of Microsoft 365 Enterprise for remote access and driving adoption for remote workers.</span></span> <span data-ttu-id="b4d19-141">如果您已經部署這些階段的元素，請先確認它們符合所述的需求，再移至下一個元素。</span><span class="sxs-lookup"><span data-stu-id="b4d19-141">If you have already deployed elements of these phases, ensure that they meet the stated requirements before moving on to the next element.</span></span>

<a name="poster"></a> <span data-ttu-id="b4d19-142">如需此案例的 1 頁式摘要，請參閱[強化遠端工作人員海報](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b4d19-142">For a 1-page summary of this scenario, see the [Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf).</span></span>

<span data-ttu-id="b4d19-143">[![強化遠端工作人員海報](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)</span><span class="sxs-lookup"><span data-stu-id="b4d19-143">[![Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)</span></span>

<span data-ttu-id="b4d19-144">您也可以用 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) 或 [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) 格式下載此海報，以及用 Letter、Legal 或 Tabloid (11 x 17) 大小的紙張列印此海報。</span><span class="sxs-lookup"><span data-stu-id="b4d19-144">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="phase-1-deploy-microsoft-365-features-and-capabilities-for-remote-workers"></a><span data-ttu-id="b4d19-145">階段1：部署適用于遠端工作人員的 Microsoft 365 功能</span><span class="sxs-lookup"><span data-stu-id="b4d19-145">Phase 1: Deploy Microsoft 365 features and capabilities for remote workers</span></span>

<span data-ttu-id="b4d19-146">由於此案例需要使用廣泛且大量的功能，我們將逐步引導您瞭解 [Microsoft 365 企業版部署指南](deploy-microsoft-365-enterprise.md)的底層基礎結構和工作量區段所需的元素。</span><span class="sxs-lookup"><span data-stu-id="b4d19-146">Because of the breadth and number of features and capabilities required for this scenario, we’ll step you through the required elements of the foundation infrastructure and workloads sections of the [Microsoft 365 Enterprise Deployment Guide](deploy-microsoft-365-enterprise.md).</span></span>

### <a name="step-1-foundation-infrastructure-requirements-for-remote-workers"></a><span data-ttu-id="b4d19-147">步驟1：遠端工作人員的底層基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="b4d19-147">Step 1: Foundation infrastructure requirements for remote workers</span></span>

<span data-ttu-id="b4d19-148">在此步驟中，我們將造訪[底層基礎結構](deploy-foundation-infrastructure.md)，並列出啟用遠端工作人員所需的元素。</span><span class="sxs-lookup"><span data-stu-id="b4d19-148">In this step, we’ll visit the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) and list the required elements to enable remote workers.</span></span>

<span data-ttu-id="b4d19-149">[階段 2：身分識別](identity-infrastructure.md)針對使用者身分識別和登入安全性部署下列項目：</span><span class="sxs-lookup"><span data-stu-id="b4d19-149">For [Phase 2: Identity](identity-infrastructure.md), deploy the following for user identity and sign-in security:</span></span>

- <span data-ttu-id="b4d19-150">針對混合式身分識別，由內部部署 Active Directory 網域服務 (AD DS) 同步處理使用者帳戶和群組。</span><span class="sxs-lookup"><span data-stu-id="b4d19-150">For hybrid identity, user accounts and groups synchronized from on-premises Active Directory Domain Services (AD DS).</span></span>
- <span data-ttu-id="b4d19-151">針對指派權限，同步處理或使用 Azure AD 群組處理適當的成員。</span><span class="sxs-lookup"><span data-stu-id="b4d19-151">For assigning permissions, synchronized or Azure AD groups with the appropriate members.</span></span>
- <span data-ttu-id="b4d19-152">驗證設定，例如要求 MFA。</span><span class="sxs-lookup"><span data-stu-id="b4d19-152">Authentication settings, such as requiring MFA.</span></span>
- <span data-ttu-id="b4d19-153">設定條件式存取原則，要求對有風險的登入進行 MFA，並封鎖不支援新式驗證的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b4d19-153">Conditional Access policies to require MFA for risky sign-ins and block clients that don’t support modern authentication.</span></span>

<span data-ttu-id="b4d19-154">以下是所產生的組態，強調身分識別元素。</span><span class="sxs-lookup"><span data-stu-id="b4d19-154">Here's the resulting configuration with the identity elements highlighted.</span></span>

![遠端工作人員的身分識別元素](../media/empower-people-to-work-remotely/remote-workers-id-phase.png)
 
<span data-ttu-id="b4d19-156">[階段 3：Windows 10 企業版](windows10-infrastructure.md)部署：</span><span class="sxs-lookup"><span data-stu-id="b4d19-156">For [Phase 3: Windows 10 Enterprise](windows10-infrastructure.md), deploy:</span></span>

- <span data-ttu-id="b4d19-157">使用 Windows 10 企業版部署新裝置以及將您的 Windows 7 或 Windows 8.1 裝置升級到 Windows 10 企業版的基礎結構</span><span class="sxs-lookup"><span data-stu-id="b4d19-157">The infrastructure to deploy new devices with Windows 10 Enterprise and to upgrade of your Windows 7 or Windows 8.1 devices to Windows 10 Enterprise</span></span>
- <span data-ttu-id="b4d19-158">為身分識別、威脅和資訊保護啟用全面的安全性功能</span><span class="sxs-lookup"><span data-stu-id="b4d19-158">Enabling comprehensive security features for identity, threat, and information protection</span></span>

<span data-ttu-id="b4d19-159">以下是使用 Windows 10 企業版裝置所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="b4d19-159">Here's the resulting configuration with Windows 10 Enterprise devices.</span></span>

![適用于遠端工作人員的 Windows 10 企業元素](../media/empower-people-to-work-remotely/remote-workers-win10-phase.png)
 
<span data-ttu-id="b4d19-161">[階段 4：Office 365 專業增強版](office365proplus-infrastructure.md)，部署基礎結構以安裝 Office 365 專業增強版或在組織的裝置上將目前安裝的 Office 套件 (例如 Office 2010 或 Office 2013) 升級至 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="b4d19-161">For [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md), deploy the infrastructure to install Office 365 ProPlus or upgrade your currently installed Office suite, such as Office 2010 or Office 2013, to Office 365 ProPlus on your organization devices.</span></span> <span data-ttu-id="b4d19-162">這會為您的使用者提供最佳的安全性和共同作業體驗。</span><span class="sxs-lookup"><span data-stu-id="b4d19-162">This will give your users the best security and collaborative experiences.</span></span>

<span data-ttu-id="b4d19-163">以下是安裝 Office 365 專業增強版的裝置所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="b4d19-163">Here's the resulting configuration with Office 365 ProPlus installed on devices.</span></span>

![適用于遠端工作人員的 Office 365 專業增強版元素](../media/empower-people-to-work-remotely/remote-workers-proplus-phase.png)
 
<span data-ttu-id="b4d19-165">[階段 5：行動裝置管理](mobility-infrastructure.md)部署 Intune 裝置和應用程式管理：</span><span class="sxs-lookup"><span data-stu-id="b4d19-165">For [Phase 5: Mobile device management](mobility-infrastructure.md), deploy Intune device and app management for:</span></span>

- <span data-ttu-id="b4d19-166">註冊您的 Windows 10 企業版、iOS、macOS、Android 和 Android 企業版裝置，以便收到貴組織定義的功能和安全性設定。</span><span class="sxs-lookup"><span data-stu-id="b4d19-166">Enrollment of your Windows 10 Enterprise, iOS, macOS, Android, and Android Enterprise devices so they receive features and security settings defined by your organization.</span></span>
- <span data-ttu-id="b4d19-167">適用于額外安全性的應用程式設定，以及允許或封鎖應用程式 (即使是在員工擁有的個人裝置)。</span><span class="sxs-lookup"><span data-stu-id="b4d19-167">App settings for extra security and to allow or block apps, even on employee-owned personal devices.</span></span>
- <span data-ttu-id="b4d19-168">具備條件式存取的合規性原則，以防止不符合規範的裝置連線。</span><span class="sxs-lookup"><span data-stu-id="b4d19-168">Compliance policies with Conditional Access to prevent non-compliant devices from connecting.</span></span>

<span data-ttu-id="b4d19-169">以下是所產生的組態，強調 Intune 註冊裝置和原則。</span><span class="sxs-lookup"><span data-stu-id="b4d19-169">Here's the resulting configuration with Intune enrolled devices and policies highlighted.</span></span>

![遠端工作人員的行動裝置管理元素](../media/empower-people-to-work-remotely/remote-workers-mdm-phase.png)
 
<span data-ttu-id="b4d19-171">[階段 6：資訊保護](infoprotect-infrastructure.md)是為您的數位資產設計和設定保護：</span><span class="sxs-lookup"><span data-stu-id="b4d19-171">For [Phase 6: Information protection](infoprotect-infrastructure.md), design and configure protection for your digital assets with:</span></span>

- <span data-ttu-id="b4d19-172">Office 365 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="b4d19-172">Office 365 DLP policies.</span></span>
- <span data-ttu-id="b4d19-173">跟隨檔案的 Office 365 敏感度標籤，用於加密和權限。</span><span class="sxs-lookup"><span data-stu-id="b4d19-173">Office 365 sensitivity labels for encryption and permissions that travel with files.</span></span>

<span data-ttu-id="b4d19-174">以下是所產生的組態，強調 [DLP 原則] 和 [敏感度標籤]。</span><span class="sxs-lookup"><span data-stu-id="b4d19-174">Here's the resulting configuration with DLP policies and sensitivity labels highlighted.</span></span>

![適用于遠端工作人員的資訊保護元素](../media/empower-people-to-work-remotely/remote-workers-ip-phase.png)
 
<span data-ttu-id="b4d19-176">若要存取內部部署的應用程式，您可以使用 [Azure AD 應用程式 Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)，這需要混合式身分識別環境。</span><span class="sxs-lookup"><span data-stu-id="b4d19-176">For access to on-premises apps, you can use [Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy), which requires a hybrid identity environment.</span></span>

<span data-ttu-id="b4d19-177">以下是所產生的組態，強調 [應用程式 Proxy] 元件。</span><span class="sxs-lookup"><span data-stu-id="b4d19-177">Here's the resulting configuration with the application proxy components highlighted.</span></span>

![遠端工作人員的應用程式 Proxy 元素](../media/empower-people-to-work-remotely/remote-workers-app-proxy.png)
 
### <a name="step-2-workloads-for-remote-workers"></a><span data-ttu-id="b4d19-179">步驟2：適用于遠端工作人員的工作負載</span><span class="sxs-lookup"><span data-stu-id="b4d19-179">Step 2: Workloads for remote workers</span></span>

<span data-ttu-id="b4d19-180">若是 [Exchange Online](exchangeonline-workload.md)，部署 Exchange Online 信箱至每個使用者。</span><span class="sxs-lookup"><span data-stu-id="b4d19-180">For [Exchange Online](exchangeonline-workload.md), deploy Exchange Online mailboxes to each of your users.</span></span>

<span data-ttu-id="b4d19-181">若是 [Teams](teams-workload.md)，部署 Teams 到您的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="b4d19-181">For [Teams](teams-workload.md), deploy Teams to your users and groups.</span></span>

<span data-ttu-id="b4d19-182">若是 [SharePoint 和 OneDrive](sharepoint-online-onedrive-workload.md)，部署 SharePoint 小組或通訊網站和 OneDrive 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b4d19-182">For [SharePoint and OneDrive](sharepoint-online-onedrive-workload.md), deploy SharePoint team or communication sites and OneDrive folders.</span></span>

<span data-ttu-id="b4d19-183">以下是所產生的組態，強調工作負載。</span><span class="sxs-lookup"><span data-stu-id="b4d19-183">Here's the resulting configuration with the workloads highlighted.</span></span>

![適用于遠端工作人員的 Microsoft 365 工作負載](../media/empower-people-to-work-remotely/remote-workers-workloads.png)
 
### <a name="deployment-results"></a><span data-ttu-id="b4d19-185">部署結果</span><span class="sxs-lookup"><span data-stu-id="b4d19-185">Deployment results</span></span>

<span data-ttu-id="b4d19-186">部署底層基礎結構和工作負載並推出 Windows 10 企業版和 Office 365 專業增強版之後，遠端工作人員：</span><span class="sxs-lookup"><span data-stu-id="b4d19-186">After deploying the foundation infrastructure and workloads and rolling out Windows 10 Enterprise and Office 365 ProPlus, remote workers:</span></span>

- <span data-ttu-id="b4d19-187">受制于增強式驗證和身分識別保護。</span><span class="sxs-lookup"><span data-stu-id="b4d19-187">Are subject to strong authentication and identity protection.</span></span>
- <span data-ttu-id="b4d19-188">在其 Windows 裝置上使用最新且最安全的 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="b4d19-188">Have the latest and most secure version of Windows on their Windows devices.</span></span>
- <span data-ttu-id="b4d19-189">在其裝置上使用最新且最有生產力的 Office 套件版本。</span><span class="sxs-lookup"><span data-stu-id="b4d19-189">Have the latest and most productive version of the Office suite on their devices.</span></span>
- <span data-ttu-id="b4d19-190">受制于應用程式管理和裝置合規性原則。</span><span class="sxs-lookup"><span data-stu-id="b4d19-190">Are subject to app management and device compliance policies.</span></span>
- <span data-ttu-id="b4d19-191">受制于 DLP 原則和限制。</span><span class="sxs-lookup"><span data-stu-id="b4d19-191">Are subject to DLP policies and restrictions.</span></span>
- <span data-ttu-id="b4d19-192">可以指派跟隨檔案和電子郵件的敏感度標籤，用於加密和權限。</span><span class="sxs-lookup"><span data-stu-id="b4d19-192">Can assign sensitivity labels for encryption and permissions that travel with files and email.</span></span>
- <span data-ttu-id="b4d19-193">可以存取內部部署應用程式，且不需要 VPN 連線。</span><span class="sxs-lookup"><span data-stu-id="b4d19-193">Can access on-premises apps without a VPN connection.</span></span>
- <span data-ttu-id="b4d19-194">可以自行工作，並使用 Teams、SharePoint 和 OneDrive 中的聊天、會議和檔案，參與跟同事的即時共同作業。</span><span class="sxs-lookup"><span data-stu-id="b4d19-194">Can perform their own work and participate in real-time collaboration with co-workers with chats, meetings, and files in Teams and files in SharePoint and OneDrive.</span></span>

<span data-ttu-id="b4d19-195">離線時 (未連線至網際網路) ，您的遠端工作人員可以變更檔案的本機複本。</span><span class="sxs-lookup"><span data-stu-id="b4d19-195">When offline (not connected to the Internet), your remote workers can change local copies of files.</span></span> <span data-ttu-id="b4d19-196">當他們重新連線到網際網路時，OneDrive 就會同步處理本機複本至儲存在 Microsoft 365 訂閱中的檔案。</span><span class="sxs-lookup"><span data-stu-id="b4d19-196">When they reconnect to the Internet, OneDrive synchronizes local copies with the files stored in your Microsoft 365 subscription.</span></span> 

<span data-ttu-id="b4d19-197">如果您使用混合式身分識別，以下是貴組織的遠端工作人員所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="b4d19-197">Here's the resulting configuration for remote workers of your organization if you use hybrid identity.</span></span>

![使用混合式身分識別的組織的最終設定](../media/empower-people-to-work-remotely/remote-workers-hybrid.png) 
 
<span data-ttu-id="b4d19-199">以下是您組織的遠端工作人員 (如果您使用的是雲端身分識別) 所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="b4d19-199">Here's the resulting configuration for remote workers your organization if you use cloud-only identity.</span></span>

![只有雲端身分識別的組織的最終組態](../media/empower-people-to-work-remotely/remote-workers-cloud-only.png)

## <a name="phase-2-drive-user-adoption-for-remote-workers"></a><span data-ttu-id="b4d19-201">階段2：推動使用者採用遠端工作人員</span><span class="sxs-lookup"><span data-stu-id="b4d19-201">Phase 2: Drive user adoption for remote workers</span></span>

<span data-ttu-id="b4d19-202">現在底層基礎結構和工作負載都已就緒，是時候推動您的遠端工作人員持續使用這些功能，讓他們能隨時隨地保持生產力。</span><span class="sxs-lookup"><span data-stu-id="b4d19-202">Now that the foundation infrastructure and workloads are in place, it’s time to drive the ongoing usage of these capabilities to your remote workers so they can be productive anywhere and at any time.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="b4d19-203">步驟 1：訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="b4d19-203">Step 1: Train your users</span></span>

<span data-ttu-id="b4d19-204">訓練您的遠端工作人員：</span><span class="sxs-lookup"><span data-stu-id="b4d19-204">Train your remote workers on:</span></span>

- <span data-ttu-id="b4d19-205">正確的登入程序，包括 MFA 註冊以及如何在偵測到風險時挑戰登入。</span><span class="sxs-lookup"><span data-stu-id="b4d19-205">Proper sign-in procedures, including MFA registration, and how sign ins can be challenged when risk is detected.</span></span>
- <span data-ttu-id="b4d19-206">使用裝置，以及如何使用原則封鎖不合規裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="b4d19-206">The use of devices and how policies can be used to block access for non-compliant devices.</span></span>
- <span data-ttu-id="b4d19-207">使用允許的應用程式，以及如何使用 Intune 應用程式原則封鎖應用程式。</span><span class="sxs-lookup"><span data-stu-id="b4d19-207">The use of allowed apps and how Intune app polices can be used to block apps.</span></span>
- <span data-ttu-id="b4d19-208">Windows 10 企業版安全性功能。</span><span class="sxs-lookup"><span data-stu-id="b4d19-208">Windows 10 Enterprise security features.</span></span>
- <span data-ttu-id="b4d19-209">如何使用 Outlook 的電子郵件和行事曆。</span><span class="sxs-lookup"><span data-stu-id="b4d19-209">How to use Outlook for email and calendaring.</span></span>
- <span data-ttu-id="b4d19-210">如何使用 [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) 來聊天、視訊會議、共用文件和往來交談。</span><span class="sxs-lookup"><span data-stu-id="b4d19-210">How to use [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) for chat, video-based conferencing, document sharing, and threaded conversations.</span></span>
- <span data-ttu-id="b4d19-211">如何使用 SharePoint 小組或通訊網站和 OneDrive 資料夾來瀏覽使用者文件庫中的檔案，以及那些屬於群組的檔案。</span><span class="sxs-lookup"><span data-stu-id="b4d19-211">How to use SharePoint team or communication sites and OneDrive folders to browse files in a user's library and those belonging to a group.</span></span>
- <span data-ttu-id="b4d19-212">在本機和線上版本的檔案中，如何針對內含敏感性或高管制資料的檔案使用及套用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="b4d19-212">How to use and apply sensitivity labels for files containing sensitive or highly regulated data, for both local and online versions of files.</span></span>

<span data-ttu-id="b4d19-213">此訓練應該包含實際操作練習，讓您的學生可以體驗這些功能及其結果。</span><span class="sxs-lookup"><span data-stu-id="b4d19-213">This training should include hands-on exercises so that your students can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-worker-feedback"></a><span data-ttu-id="b4d19-214">步驟2：舉辦定期的使用狀況檢閱和處理工作者意見反應</span><span class="sxs-lookup"><span data-stu-id="b4d19-214">Step 2: Conduct periodic reviews of usage and address worker feedback</span></span>

<span data-ttu-id="b4d19-215">在訓練後的幾周內：</span><span class="sxs-lookup"><span data-stu-id="b4d19-215">In the weeks after training:</span></span>

- <span data-ttu-id="b4d19-216">快速處理遠端工作者的意見反應，並微調原則和設定。</span><span class="sxs-lookup"><span data-stu-id="b4d19-216">Quickly address remote worker feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="b4d19-217">分析 Teams、SharePoint 網站和 OneDrive 資料夾的使用狀況，並比較其使用預期。</span><span class="sxs-lookup"><span data-stu-id="b4d19-217">Analyze usage for teams, SharePoint sites, and OneDrive folders and compare it with usage expectations.</span></span>
- <span data-ttu-id="b4d19-218">確認敏感性或高管制的檔案已正確地標示適當的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="b4d19-218">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="b4d19-219">視需要重新訓練您的使用者。</span><span class="sxs-lookup"><span data-stu-id="b4d19-219">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="b4d19-220">使用者採用結果</span><span class="sxs-lookup"><span data-stu-id="b4d19-220">User adoption results</span></span>

<span data-ttu-id="b4d19-221">您的遠端工作人員可以使用其 Windows 10 企業版或其他裝置與 Office 365 專業增強版，在安全的環境中存取和使用共用的 Microsoft 365 企業版雲端服務和資源，並即時開會、建立和共同作業。</span><span class="sxs-lookup"><span data-stu-id="b4d19-221">Your remote workers can use their Windows 10 Enterprise or other devices and Office 365 ProPlus to access and work on shared Microsoft 365 Enterprise cloud services and resources in a secure environment, and they’re meeting, creating, and collaborating in real time.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4d19-222">請參閱</span><span class="sxs-lookup"><span data-stu-id="b4d19-222">See also</span></span>

[<span data-ttu-id="b4d19-223">工作負載和案例</span><span class="sxs-lookup"><span data-stu-id="b4d19-223">Workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="b4d19-224">[Microsoft 365 生產力資源庫](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="b4d19-224">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="b4d19-225">部署指南</span><span class="sxs-lookup"><span data-stu-id="b4d19-225">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
