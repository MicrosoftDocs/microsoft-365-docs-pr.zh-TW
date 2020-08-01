---
title: Microsoft 受管理的電腦技術
description: 本主題列出 Microsoft 受管理的桌面中所用的技術和應用程式。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1f82c339e8cbe4426c87eae045107d26201b0025
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530016"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="4ebbc-104">Microsoft 受管理的電腦技術</span><span class="sxs-lookup"><span data-stu-id="4ebbc-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="4ebbc-105">本主題列出 Microsoft 受管理的桌面中所用的技術和應用程式。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="4ebbc-106">所有 Microsoft 受管理的桌面使用者都需要 microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="4ebbc-107">如需服務授權需求的詳細資訊，請參閱[Microsoft Managed Desktop 的必要條件](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="4ebbc-108">本主題摘要說明所需企業授權中包含的元件，並說明服務如何使用每個元件與 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-108">This topic summarizes the components included in the required Enterprise licenses, with a description of how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4ebbc-109">在整個 Microsoft 受管理的桌面檔中會詳細說明每個區域的特定角色和責任。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-109">Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop documentation.</span></span> 

## <a name="office-365-e3-or-e5"></a><span data-ttu-id="4ebbc-110">Office 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="4ebbc-110">Office 365 E3 or E5</span></span>
 |
 --- | ---
<span data-ttu-id="4ebbc-111">適用于企業的 Microsoft 365 應用程式（64-位）</span><span class="sxs-lookup"><span data-stu-id="4ebbc-111">Microsoft 365 Apps for enterprise (64-bit)</span></span> | <span data-ttu-id="4ebbc-112">這些 Office 應用程式會隨裝置運送： Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype、OneNote。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-112">These Office applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="4ebbc-113">不包含 Microsoft Project 和 Microsoft Visio 的64位完整版本。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-113">The 64-bit full versions of Microsoft Project and Microsoft Visio are not included.</span></span> <span data-ttu-id="4ebbc-114">不過，由於安裝這些應用程式取決於 Microsoft 365 應用程式的 enterprise 安裝，因此 Microsoft Managed Desktop 已建立預設的 Microsoft Intune 部署和安全性群組，您可以用來將這些應用程式部署到授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-114">However, since the installation of these applications depends on the Microsoft 365 Apps for enterprise installation, Microsoft Managed Desktop has created default Microsoft Intune deployments and security groups that you can then use to deploy these applications to licensed end users.</span></span> <span data-ttu-id="4ebbc-115">如需詳細資訊，請參閱[在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-115">For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>
<span data-ttu-id="4ebbc-116">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ebbc-116">OneDrive for Business</span></span> |<span data-ttu-id="4ebbc-117">在第一次登入商務用 OneDrive 時，會為使用者啟用 Azure Active Directory 單一登入。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-117">Azure Active Directory Single Sign On is enabled for end users upon first sign in to OneDrive for Business.</span></span><br><br><span data-ttu-id="4ebbc-118">包含「桌面」、「檔」及「圖片」資料夾的已知資料夾重新導向;由 Microsoft Managed Desktop 啟用和設定。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-118">Known Folder Redirection for "Desktop", "Document", and "Pictures" folders is included; enabled and configured by Microsoft Managed Desktop.</span></span> 
<span data-ttu-id="4ebbc-119">儲存應用程式</span><span class="sxs-lookup"><span data-stu-id="4ebbc-119">Store Apps</span></span> |    <span data-ttu-id="4ebbc-120">Microsoft Sway 和 Power BI 未附帶裝置。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-120">Microsoft Sway and Power BI are not shipped with the device.</span></span> <span data-ttu-id="4ebbc-121">這些應用程式可從 Microsoft Store 下載。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-121">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="4ebbc-122">Win32 應用程式</span><span class="sxs-lookup"><span data-stu-id="4ebbc-122">Win32 Applications</span></span> |    <span data-ttu-id="4ebbc-123">小組未附帶裝置，但是會打包並由 Microsoft 提供給 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-123">Teams is not shipped with the device, but is packaged and provided by Microsoft for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4ebbc-124">Azure 資訊保護用戶端未附帶裝置，但是您可以將此裝置打包以進行部署。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-124">Azure Information Protection Client is not shipped with the device, but you can have this packaged for deployment.</span></span> 
<span data-ttu-id="4ebbc-125">Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="4ebbc-125">Web Applications</span></span> |  <span data-ttu-id="4ebbc-126">在瀏覽器中的 [Yammer]、「Delve」、「流程」、「StaffHub」、「PowerApps」及「Planner」都不會隨裝置附帶。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-126">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps, and Planner are not shipped with the device.</span></span> <span data-ttu-id="4ebbc-127">使用者可以使用瀏覽器存取這些應用程式的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-127">Users can access the web version of these applications with a browser.</span></span>


## <a name="windows-10-enterprise-e3-or-e5"></a><span data-ttu-id="4ebbc-128">Windows 10 企業版 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="4ebbc-128">Windows 10 Enterprise E3 or E5</span></span>

 |
 --- | ---
<span data-ttu-id="4ebbc-129">Application Virtualization （App-V）</span><span class="sxs-lookup"><span data-stu-id="4ebbc-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="4ebbc-130">客戶可以使用 Intune Win32 應用程式管理用戶端部署 App-V 套件。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-130">Customers can deploy App-V packages using the Intune Win32 app management client.</span></span>
<span data-ttu-id="4ebbc-131">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="4ebbc-131">Microsoft Defender Advanced Threat Protection</span></span> |  <span data-ttu-id="4ebbc-132">Microsoft 受管理的桌面用來監視裝置安全性。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-132">Microsoft Managed Desktop uses this to monitor device security.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="4ebbc-133">企業行動 + 安全性 E5</span><span class="sxs-lookup"><span data-stu-id="4ebbc-133">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="4ebbc-134">企業行動性 + 安全性 E3</span><span class="sxs-lookup"><span data-stu-id="4ebbc-134">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="4ebbc-135">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="4ebbc-135">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="4ebbc-136">您可以使用企業行動裝置 + Security E3 和 Azure Active Directory Premium P2 的所有功能來管理 MDM 裝置。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-136">You can use all features of Enterprise Mobility + Security E3 and Azure Active Directory Premium P2 to manage MDM devices.</span></span>
<span data-ttu-id="4ebbc-137">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4ebbc-137">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="4ebbc-138">您可以將此選用功能與 Microsoft Managed Desktop 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-138">You can use this optional feature with Microsoft Managed Desktop.</span></span>
<span data-ttu-id="4ebbc-139">Azure 資訊保護 P2</span><span class="sxs-lookup"><span data-stu-id="4ebbc-139">Azure Information Protection P2</span></span>  | <span data-ttu-id="4ebbc-140">您可以將此選用功能與 Microsoft Managed Desktop 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4ebbc-140">You can use this optional feature with Microsoft Managed Desktop.</span></span>
