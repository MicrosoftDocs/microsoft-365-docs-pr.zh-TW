---
title: Microsoft 受管理的桌面技術
description: 本主題列出 Microsoft 受管理的電腦中所使用的技術和應用程式。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9c0e6481d0dc80e7cf03de2b748935c2f59f132a
ms.sourcegitcommit: e54ec86310a18101f4688890cd5a9fc16bbe6f55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2019
ms.locfileid: "35257816"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="2e35f-104">Microsoft 受管理的桌面技術</span><span class="sxs-lookup"><span data-stu-id="2e35f-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="2e35f-105">本主題列出 Microsoft 受管理的電腦中所使用的技術和應用程式。</span><span class="sxs-lookup"><span data-stu-id="2e35f-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="2e35f-106">所有 Microsoft 受管理的桌面使用者都需要 microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="2e35f-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="2e35f-107">如需服務授權需求的詳細資訊, 請參閱[Microsoft 受管理電腦的必要條件](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="2e35f-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="2e35f-108">以下是所需企業授權中包含的所有元件, 以及服務如何使用 Microsoft 受管理的電腦裝置的每個元件。</span><span class="sxs-lookup"><span data-stu-id="2e35f-108">The following are all components that are included in the required Enterprise licenses and how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2e35f-109">每個區域的特定角色和責任都是在整個 Microsoft 受管理的桌面主題中詳細說明。</span><span class="sxs-lookup"><span data-stu-id="2e35f-109">Specific roles and responsibilities for each area are detailed throughout the Microsoft Managed Desktop topic.</span></span> 

## <a name="office-365-e3"></a><span data-ttu-id="2e35f-110">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="2e35f-110">Office 365 E3</span></span>
 |
 --- | ---
<span data-ttu-id="2e35f-111">Office 365 Standard Suite (64 位) \*</span><span class="sxs-lookup"><span data-stu-id="2e35f-111">Office 365 Standard Suite (64bit)\*</span></span> | <span data-ttu-id="2e35f-112">標準的 Office 套件應用程式會隨附裝置: Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype、OneNote。</span><span class="sxs-lookup"><span data-stu-id="2e35f-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="2e35f-113">64位的按一下以執行 (C2R) 完整版本的 Microsoft Project 和 Microsoft Visio 不包含在 Office 365 Standard Suite 中。</span><span class="sxs-lookup"><span data-stu-id="2e35f-113">The 64bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in the Office 365 Standard Suite.</span></span>  <span data-ttu-id="2e35f-114">不過, 由於這些應用程式的安裝取決於標準 Office 套件安裝, Microsoft 受管理的桌面已建立了預設的 Intune 部署和安全性群組, 客戶將使用這些部署來將這些應用程式部署到授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="2e35f-114">However, since the installation of these applications are dependent on the standard Office Suite installation, Microsoft Managed Desktop has created default Intune deployments and Security groups that the customer will use to deploy these applications to licensed end users.</span></span>  
<span data-ttu-id="2e35f-115">儲存應用程式</span><span class="sxs-lookup"><span data-stu-id="2e35f-115">Store Apps</span></span> |    <span data-ttu-id="2e35f-116">Microsoft Sway、Power BI Desktop 不會隨附裝置。</span><span class="sxs-lookup"><span data-stu-id="2e35f-116">Microsoft Sway, Power BI Desktop are not shipped with device.</span></span> <span data-ttu-id="2e35f-117">這些應用程式可從 Microsoft Store 下載。</span><span class="sxs-lookup"><span data-stu-id="2e35f-117">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="2e35f-118">Win32 應用程式</span><span class="sxs-lookup"><span data-stu-id="2e35f-118">Win32 Applications</span></span> |    <span data-ttu-id="2e35f-119">Power BI Pro、Azure 資訊保護用戶端和 Microsoft Planner 不會隨附裝置, 且可由客戶進行部署。</span><span class="sxs-lookup"><span data-stu-id="2e35f-119">Power BI Pro, Azure Information Protection Client, and Microsoft Planner are not shipped with device and can be packaged for deployment by the customer.</span></span> 
<span data-ttu-id="2e35f-120">Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="2e35f-120">Web Applications</span></span> |  <span data-ttu-id="2e35f-121">Yammer、Office Online、Delve、Flow、StaffHub、PowerApps 不會隨裝置一起隨附。</span><span class="sxs-lookup"><span data-stu-id="2e35f-121">Yammer, Office Online, Delve, Flow, StaffHub, PowerApps are not shipped with the device.</span></span> <span data-ttu-id="2e35f-122">使用者可以使用瀏覽器來存取這些應用程式的 web 版。</span><span class="sxs-lookup"><span data-stu-id="2e35f-122">Users can access the web version of these applications with a browser.</span></span>
<span data-ttu-id="2e35f-123">商務用 Skype Online Cloud PBX</span><span class="sxs-lookup"><span data-stu-id="2e35f-123">Skype for Business Online Cloud PBX</span></span> | <span data-ttu-id="2e35f-124">此功能可透過 Office 365 取得。</span><span class="sxs-lookup"><span data-stu-id="2e35f-124">This feature is available via Office 365.</span></span> <span data-ttu-id="2e35f-125">Microsoft 受管理的桌面不會設定此服務的任何方面</span><span class="sxs-lookup"><span data-stu-id="2e35f-125">Microsoft Managed Desktop will not configure any aspect of this service</span></span>

## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="2e35f-126">Windows 10 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="2e35f-126">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="2e35f-127">Credential Guard</span><span class="sxs-lookup"><span data-stu-id="2e35f-127">Credential Guard</span></span> |  <span data-ttu-id="2e35f-128">Microsoft 會提供此功能的指引和管理雲端層面。</span><span class="sxs-lookup"><span data-stu-id="2e35f-128">Microsoft will provide guidance and manage cloud aspects of this feature.</span></span>
<span data-ttu-id="2e35f-129">Application Virtualization (App-v)</span><span class="sxs-lookup"><span data-stu-id="2e35f-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="2e35f-130">Microsoft 受管理的桌面不支援此類型的部署, 因為 Intune 上不支援此部署。</span><span class="sxs-lookup"><span data-stu-id="2e35f-130">Microsoft Managed Desktop does not support this type of deployment as it is not supported on Intune.</span></span>
<span data-ttu-id="2e35f-131">使用者體驗虛擬化 (UE-V)</span><span class="sxs-lookup"><span data-stu-id="2e35f-131">User Experience Virtualization (UE-V)</span></span> | <span data-ttu-id="2e35f-132">這不是 Microsoft 受管理的桌面受管理裝置使用。</span><span class="sxs-lookup"><span data-stu-id="2e35f-132">This is not used with Microsoft Managed Desktop managed devices.</span></span>
<span data-ttu-id="2e35f-133">受管理的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="2e35f-133">Managed User Experience</span></span>  | <span data-ttu-id="2e35f-134">這不是 Microsoft 受管理的桌面受管理裝置使用。</span><span class="sxs-lookup"><span data-stu-id="2e35f-134">This is not used with Microsoft Managed Desktop managed devices.</span></span> <span data-ttu-id="2e35f-135">MDM 是用來做為裝置管理的解決方案。</span><span class="sxs-lookup"><span data-stu-id="2e35f-135">MDM is used as a solution for device management.</span></span>
<span data-ttu-id="2e35f-136">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="2e35f-136">Windows Defender Advanced Threat Protection</span></span> |   <span data-ttu-id="2e35f-137">Microsoft 受管理的桌面會使用此功能來管理裝置安全性原則。</span><span class="sxs-lookup"><span data-stu-id="2e35f-137">This is used by Microsoft Managed Desktop to manage device security policies.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="2e35f-138">企業行動 + 安全性 E5</span><span class="sxs-lookup"><span data-stu-id="2e35f-138">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="2e35f-139">企業行動性 + 安全性 E3</span><span class="sxs-lookup"><span data-stu-id="2e35f-139">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="2e35f-140">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="2e35f-140">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="2e35f-141">企業行動性 + 安全性 E3 和 AADP 的所有層面都可以用來管理 MDM 裝置。</span><span class="sxs-lookup"><span data-stu-id="2e35f-141">All aspects of the Enterprise Mobility + Security E3 and AADP may be used to manage MDM devices.</span></span>
<span data-ttu-id="2e35f-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2e35f-142">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="2e35f-143">這是客戶可以搭配 Microsoft 受管理的桌面服務使用的選用功能。</span><span class="sxs-lookup"><span data-stu-id="2e35f-143">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
<span data-ttu-id="2e35f-144">Azure 資訊保護 P2</span><span class="sxs-lookup"><span data-stu-id="2e35f-144">Azure Information Protection P2</span></span>  |<span data-ttu-id="2e35f-145">這是客戶可以搭配 Microsoft 受管理的桌面服務使用的選用功能。</span><span class="sxs-lookup"><span data-stu-id="2e35f-145">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
