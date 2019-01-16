---
title: Microsoft 受管理的桌上型電腦技術
description: 本主題將列出的技術及 Microsoft 受管理的桌上型電腦中所使用的應用程式。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 4b26ec88e1f4ca95fee6f7c4c927fc06cab32135
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866324"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="2f224-104">Microsoft 受管理的桌上型電腦技術</span><span class="sxs-lookup"><span data-stu-id="2f224-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="2f224-105">本主題將列出的技術及 Microsoft 受管理的桌上型電腦中所使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="2f224-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="2f224-p101">Microsoft 365 E5 授權 （或對等資格），則需要 Microsoft 受管理的桌上型電腦服務。以下是此授權與 Microsoft 受管理的桌上型電腦與 Microsoft 受管理的桌上型電腦裝置所使用的每個元件中所包含的所有元件。 特定的角色與責任每個區域的詳細說明整個 Microsoft 受管理的桌上型電腦的主題。</span><span class="sxs-lookup"><span data-stu-id="2f224-p101">Microsoft 365 E5 License (or equivalent) is required for Microsoft Managed Desktop service. The following are all components that are included in this license and how Microsoft Managed Desktop uses each component with Microsoft Managed Desktop devices.  Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop topics.</span></span> 

<span data-ttu-id="2f224-109">Microsoft 365 E5 由 3 元件組成： Office 365 E5、 Windows 10 Enterprise 和 E5、 企業行動性 + 安全性 E5。</span><span class="sxs-lookup"><span data-stu-id="2f224-109">Microsoft 365 E5 is comprised of 3 components: Office 365 E5, Windows 10 Enterprise and E5, Enterprise Mobility + Security E5.</span></span>  

## <a name="office-365-e5"></a><span data-ttu-id="2f224-110">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="2f224-110">Office 365 E5</span></span>
 |
 --- | ---
<span data-ttu-id="2f224-111">Office 365 Standard Suite （64 位元） \*</span><span class="sxs-lookup"><span data-stu-id="2f224-111">Office 365 Standard Suite (64bit)\*</span></span> | <span data-ttu-id="2f224-112">標準 Office 套件的應用程式將隨附裝置： Word、 Excel、 PowerPoint、 Outlook、 Publisher、 存取、 Skype for Business、 OneNote。</span><span class="sxs-lookup"><span data-stu-id="2f224-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="2f224-p102">按一下此選項即可執行 64 位元 (C2R) 完整版本的 Microsoft Project 與 Microsoft Visio 不會包含在 Office 365 Standard Suite。 不過，這些應用程式的安裝都取決於標準 Office 套件安裝，因為 Microsoft 受管理的桌上型電腦已建立預設 Intune 部署和客戶會部署至這些應用程式使用的安全性群組授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="2f224-p102">The 64bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in the Office 365 Standard Suite.  However, since the installation of these applications are dependent on the standard Office Suite installation, Microsoft Managed Desktop has created default Intune deployments and Security groups that the customer will use to deploy these applications to licensed end users.</span></span>  
<span data-ttu-id="2f224-115">儲存應用程式</span><span class="sxs-lookup"><span data-stu-id="2f224-115">Store Apps</span></span> |    <span data-ttu-id="2f224-p103">Microsoft Sway、 的 Microsoft 小組、 Power BI 桌面 （不專業人員） 未隨附於裝置。這些應用程式都可供下載 （英文） 從 Microsoft 存放區。</span><span class="sxs-lookup"><span data-stu-id="2f224-p103">Microsoft Sway, Microsoft Teams, Power BI Desktop (not Pro) are not shipped with device. These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="2f224-118">Win32 應用程式</span><span class="sxs-lookup"><span data-stu-id="2f224-118">Win32 Applications</span></span> |    <span data-ttu-id="2f224-119">Power BI Pro、 Azure 資訊保護用戶端及 Microsoft 規劃未隨附於裝置並可由客戶封裝部署。</span><span class="sxs-lookup"><span data-stu-id="2f224-119">Power BI Pro, Azure Information Protection Client, and Microsoft Planner are not shipped with device and can be packaged for deployment by the customer.</span></span> 
<span data-ttu-id="2f224-120">Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="2f224-120">Web Applications</span></span> |  <span data-ttu-id="2f224-p104">Yammer，Office Online Delve、 流程 StaffHub、 PowerApps 未隨附於裝置。使用者可存取 web 瀏覽器中使用這些應用程式版本。</span><span class="sxs-lookup"><span data-stu-id="2f224-p104">Yammer, Office Online, Delve, Flow, StaffHub, PowerApps are not shipped with the device. Users can access the web version of these applications with a browser.</span></span>
<span data-ttu-id="2f224-123">Skype 商務線上雲端 PBX</span><span class="sxs-lookup"><span data-stu-id="2f224-123">Skype for Business Online Cloud PBX</span></span> | <span data-ttu-id="2f224-p105">這項功能是透過 Office 365 E5。Microsoft 受管理的桌上型電腦將不會設定這項服務的任何層面</span><span class="sxs-lookup"><span data-stu-id="2f224-p105">This feature is available via Office 365 E5. Microsoft Managed Desktop will not configure any aspect of this service</span></span>

## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="2f224-126">Windows 10 企業 E5</span><span class="sxs-lookup"><span data-stu-id="2f224-126">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="2f224-127">認證 Guard</span><span class="sxs-lookup"><span data-stu-id="2f224-127">Credential Guard</span></span> |  <span data-ttu-id="2f224-128">Microsoft 受管理的桌上型電腦將提供相關指導和管理的這項功能的雲端層面</span><span class="sxs-lookup"><span data-stu-id="2f224-128">Microsoft Managed Desktop will provide guidance and manage cloud aspects of this feature</span></span>
<span data-ttu-id="2f224-129">裝置 Guard （Windows 防禦者應用程式控制項）</span><span class="sxs-lookup"><span data-stu-id="2f224-129">Device Guard (Windows Defender Application Control)</span></span> | <span data-ttu-id="2f224-p106">Microsoft 受管理的桌上型電腦會建立原則。客戶管理簽章</span><span class="sxs-lookup"><span data-stu-id="2f224-p106">Microsoft Managed Desktop will create the policy. Customer will manage signatures</span></span>
<span data-ttu-id="2f224-132">AppLocker 管理</span><span class="sxs-lookup"><span data-stu-id="2f224-132">AppLocker management</span></span> |  <span data-ttu-id="2f224-p107">Microsoft 受管理的桌上型電腦會建立原則。客戶管理簽章</span><span class="sxs-lookup"><span data-stu-id="2f224-p107">Microsoft Managed Desktop will create the policy. Customer will manage signatures</span></span>
<span data-ttu-id="2f224-135">Application Virtualization (APP-V)</span><span class="sxs-lookup"><span data-stu-id="2f224-135">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="2f224-136">當它不支援 Intune Microsoft 受管理的桌上型電腦不支援這種類型的部署。</span><span class="sxs-lookup"><span data-stu-id="2f224-136">Microsoft Managed Desktop does not support this type of deployment as it is not supported on Intune.</span></span>
<span data-ttu-id="2f224-137">使用者經驗虛擬化 (使用者教育 V)</span><span class="sxs-lookup"><span data-stu-id="2f224-137">User Experience Virtualization (UE-V)</span></span> | <span data-ttu-id="2f224-138">這不會使用與受管理的 Microsoft 受管理的桌上型電腦裝置</span><span class="sxs-lookup"><span data-stu-id="2f224-138">This is not used with Microsoft Managed Desktop managed devices</span></span>
<span data-ttu-id="2f224-139">受管理的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="2f224-139">Managed User Experience</span></span>  | <span data-ttu-id="2f224-p108">這不會使用與受管理的 Microsoft 受管理的桌上型電腦裝置。MDM 作為解決方案的裝置管理</span><span class="sxs-lookup"><span data-stu-id="2f224-p108">This is not used with Microsoft Managed Desktop managed devices. MDM is used as a solution for device management</span></span>
<span data-ttu-id="2f224-142">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="2f224-142">Windows Defender Advanced Threat Protection</span></span> |   <span data-ttu-id="2f224-143">這是由 Microsoft 受管理的桌上型電腦用來管理裝置安全性原則。</span><span class="sxs-lookup"><span data-stu-id="2f224-143">This is used by Microsoft Managed Desktop to manage device security policies.</span></span> 

## <a name="enterprise-mobility--security"></a><span data-ttu-id="2f224-144">Enterprise Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="2f224-144">Enterprise Mobility + Security</span></span> 

 |
 --- | ---
<span data-ttu-id="2f224-145">Enterprise 行動性 + 安全性 E3</span><span class="sxs-lookup"><span data-stu-id="2f224-145">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="2f224-146">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="2f224-146">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="2f224-147">Enterprise 行動性 + 安全性 E3 及 AADP 各方面的可能會用來管理 MDM 裝置</span><span class="sxs-lookup"><span data-stu-id="2f224-147">All aspects of the Enterprise Mobility + Security E3 and AADP may be used to manage MDM devices</span></span>
<span data-ttu-id="2f224-148">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2f224-148">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="2f224-149">這是選用的功能，客戶可以使用與 Microsoft 受管理的桌上型電腦服務。</span><span class="sxs-lookup"><span data-stu-id="2f224-149">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
<span data-ttu-id="2f224-150">Azure 的資訊保護 P2</span><span class="sxs-lookup"><span data-stu-id="2f224-150">Azure Information Protection P2</span></span>  |<span data-ttu-id="2f224-151">這是選用的功能，客戶可以使用與 Microsoft 受管理的桌上型電腦服務。</span><span class="sxs-lookup"><span data-stu-id="2f224-151">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
