---
title: Microsoft 受管理電腦技術
description: 本主題列出在 Microsoft 受管理電腦中使用的應用程式與技術。
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 843a8cd066bbaf87a8b2b7cc74d8817207e47153
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283465"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="76bf9-104">Microsoft 受管理電腦技術</span><span class="sxs-lookup"><span data-stu-id="76bf9-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="76bf9-105">本主題列出在 Microsoft 受管理電腦中使用的應用程式與技術。</span><span class="sxs-lookup"><span data-stu-id="76bf9-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="76bf9-106">Microsoft 365 企業版授權，則需要為 Microsoft 受管理電腦的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="76bf9-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="76bf9-107">如需有關服務的授權需求的詳細資訊，請參閱 < <b0>Microsoft 受管理電腦的必要條件</b0>。</span><span class="sxs-lookup"><span data-stu-id="76bf9-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="76bf9-108">以下是必要的企業授權及服務與 Microsoft 受管理的電腦裝置所使用的每個元件中包含的所有元件。</span><span class="sxs-lookup"><span data-stu-id="76bf9-108">The following are all components that are included in the required Enterprise licenses and how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="76bf9-109">每個區域的特定角色和責任的詳細資訊整個 Microsoft 受管理電腦主題。</span><span class="sxs-lookup"><span data-stu-id="76bf9-109">Specific roles and responsibilities for each area are detailed throughout the Microsoft Managed Desktop topic.</span></span> 

## <a name="office-365-e3"></a><span data-ttu-id="76bf9-110">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="76bf9-110">Office 365 E3</span></span>
 |
 --- | ---
<span data-ttu-id="76bf9-111">Office 365 Standard Suite （64 位元） \*</span><span class="sxs-lookup"><span data-stu-id="76bf9-111">Office 365 Standard Suite (64bit)\*</span></span> | <span data-ttu-id="76bf9-112">標準的 Office 應用程式套件將會隨附裝置： Word、 Excel、 PowerPoint、 Outlook、 Publisher、 Access、 Skype for Business，OneNote。</span><span class="sxs-lookup"><span data-stu-id="76bf9-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="76bf9-113">64 位元隨選 (C2R) 的 Microsoft Project 和 Microsoft Visio 的完整版本不包含在 Office 365 Standard Suite。</span><span class="sxs-lookup"><span data-stu-id="76bf9-113">The 64bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in the Office 365 Standard Suite.</span></span>  <span data-ttu-id="76bf9-114">不過，由於這些應用程式的安裝是取決於標準 Office 套件安裝，Microsoft 受管理的電腦已建立預設 Intune 部署和安全性群組，客戶會用來部署這些應用程式授權使用者。</span><span class="sxs-lookup"><span data-stu-id="76bf9-114">However, since the installation of these applications are dependent on the standard Office Suite installation, Microsoft Managed Desktop has created default Intune deployments and Security groups that the customer will use to deploy these applications to licensed end users.</span></span>  
<span data-ttu-id="76bf9-115">市集應用程式</span><span class="sxs-lookup"><span data-stu-id="76bf9-115">Store Apps</span></span> |    <span data-ttu-id="76bf9-116">Microsoft Sway、 Power BI Desktop 未隨附於裝置。</span><span class="sxs-lookup"><span data-stu-id="76bf9-116">Microsoft Sway, Power BI Desktop are not shipped with device.</span></span> <span data-ttu-id="76bf9-117">這些應用程式可供從 Microsoft Store 下載。</span><span class="sxs-lookup"><span data-stu-id="76bf9-117">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="76bf9-118">Win32 應用程式</span><span class="sxs-lookup"><span data-stu-id="76bf9-118">Win32 Applications</span></span> |    <span data-ttu-id="76bf9-119">Power BI 專業人員、 Azure 資訊保護用戶端，Microsoft Planner 未隨附於裝置並可由客戶封裝部署。</span><span class="sxs-lookup"><span data-stu-id="76bf9-119">Power BI Pro, Azure Information Protection Client, and Microsoft Planner are not shipped with device and can be packaged for deployment by the customer.</span></span> 
<span data-ttu-id="76bf9-120">Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="76bf9-120">Web Applications</span></span> |  <span data-ttu-id="76bf9-121">Yammer，Office Online，Delve、 流程、 StaffHub、 PowerApps 未隨附於裝置。</span><span class="sxs-lookup"><span data-stu-id="76bf9-121">Yammer, Office Online, Delve, Flow, StaffHub, PowerApps are not shipped with the device.</span></span> <span data-ttu-id="76bf9-122">使用者可以存取這些應用程式與瀏覽器網頁版。</span><span class="sxs-lookup"><span data-stu-id="76bf9-122">Users can access the web version of these applications with a browser.</span></span>
<span data-ttu-id="76bf9-123">Skype 商務線上雲端 PBX</span><span class="sxs-lookup"><span data-stu-id="76bf9-123">Skype for Business Online Cloud PBX</span></span> | <span data-ttu-id="76bf9-124">這項功能可透過 Office 365。</span><span class="sxs-lookup"><span data-stu-id="76bf9-124">This feature is available via Office 365.</span></span> <span data-ttu-id="76bf9-125">Microsoft 受管理電腦將不會設定這項服務的任何層面</span><span class="sxs-lookup"><span data-stu-id="76bf9-125">Microsoft Managed Desktop will not configure any aspect of this service</span></span>

## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="76bf9-126">Windows 10 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="76bf9-126">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="76bf9-127">Credential Guard</span><span class="sxs-lookup"><span data-stu-id="76bf9-127">Credential Guard</span></span> |  <span data-ttu-id="76bf9-128">Microsoft 會提供指引，以及管理雲端的這項功能的各個層面。</span><span class="sxs-lookup"><span data-stu-id="76bf9-128">Microsoft will provide guidance and manage cloud aspects of this feature.</span></span>
<span data-ttu-id="76bf9-129">裝置 Guard （Windows Defender 應用程式控制）</span><span class="sxs-lookup"><span data-stu-id="76bf9-129">Device Guard (Windows Defender Application Control)</span></span> | <span data-ttu-id="76bf9-130">Microsoft 受管理的電腦會建立原則。</span><span class="sxs-lookup"><span data-stu-id="76bf9-130">Microsoft Managed Desktop will create the policy.</span></span> <br><br><span data-ttu-id="76bf9-131">客戶會管理簽章。</span><span class="sxs-lookup"><span data-stu-id="76bf9-131">Customer will manage signatures.</span></span>
<span data-ttu-id="76bf9-132">AppLocker 管理</span><span class="sxs-lookup"><span data-stu-id="76bf9-132">AppLocker management</span></span> |  <span data-ttu-id="76bf9-133">Microsoft 將會建立原則。</span><span class="sxs-lookup"><span data-stu-id="76bf9-133">Microsoft will create the policy.</span></span> <br><br><span data-ttu-id="76bf9-134">客戶會管理簽章。</span><span class="sxs-lookup"><span data-stu-id="76bf9-134">Customer will manage signatures.</span></span>
<span data-ttu-id="76bf9-135">Application Virtualization (APP-V)</span><span class="sxs-lookup"><span data-stu-id="76bf9-135">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="76bf9-136">Microsoft 受管理的電腦不支援這種類型的部署，因為它不支援 Intune。</span><span class="sxs-lookup"><span data-stu-id="76bf9-136">Microsoft Managed Desktop does not support this type of deployment as it is not supported on Intune.</span></span>
<span data-ttu-id="76bf9-137">使用者經驗虛擬化 (使用者教育 virtualization，AMD-V)</span><span class="sxs-lookup"><span data-stu-id="76bf9-137">User Experience Virtualization (UE-V)</span></span> | <span data-ttu-id="76bf9-138">這不會使用與受管理的 Microsoft 受管理電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="76bf9-138">This is not used with Microsoft Managed Desktop managed devices.</span></span>
<span data-ttu-id="76bf9-139">受管理的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="76bf9-139">Managed User Experience</span></span>  | <span data-ttu-id="76bf9-140">這不會使用與受管理的 Microsoft 受管理電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="76bf9-140">This is not used with Microsoft Managed Desktop managed devices.</span></span> <span data-ttu-id="76bf9-141">MDM 會當做裝置管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="76bf9-141">MDM is used as a solution for device management.</span></span>
<span data-ttu-id="76bf9-142">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="76bf9-142">Windows Defender Advanced Threat Protection</span></span> |   <span data-ttu-id="76bf9-143">這是 Microsoft 受管理電腦用來管理裝置安全性原則。</span><span class="sxs-lookup"><span data-stu-id="76bf9-143">This is used by Microsoft Managed Desktop to manage device security policies.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="76bf9-144">Enterprise Mobility + Security E5</span><span class="sxs-lookup"><span data-stu-id="76bf9-144">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="76bf9-145">企業行動力 + 安全性版 E3</span><span class="sxs-lookup"><span data-stu-id="76bf9-145">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="76bf9-146">Azure Active Directory 進階版 P2</span><span class="sxs-lookup"><span data-stu-id="76bf9-146">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="76bf9-147">企業行動力 + 安全性版 E3 和 AADP 的所有層面可能都用來管理 MDM 裝置。</span><span class="sxs-lookup"><span data-stu-id="76bf9-147">All aspects of the Enterprise Mobility + Security E3 and AADP may be used to manage MDM devices.</span></span>
<span data-ttu-id="76bf9-148">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="76bf9-148">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="76bf9-149">這是選擇性功能，客戶可以使用 Microsoft 受管理的電腦服務。</span><span class="sxs-lookup"><span data-stu-id="76bf9-149">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
<span data-ttu-id="76bf9-150">Azure 資訊保護 P2</span><span class="sxs-lookup"><span data-stu-id="76bf9-150">Azure Information Protection P2</span></span>  |<span data-ttu-id="76bf9-151">這是選擇性功能，客戶可以使用 Microsoft 受管理的電腦服務。</span><span class="sxs-lookup"><span data-stu-id="76bf9-151">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
