---
title: 準備應用程式以使用 Microsoft 受管理的電腦
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289061"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="d77c5-103">準備應用程式以使用 Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="d77c5-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="d77c5-104">Microsoft 和 Microsoft 受管理電腦的客戶同樣也有重大、 尚未不同職責周圍搭配 Microsoft 受管理電腦的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d77c5-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilities"></a><span data-ttu-id="d77c5-105">Microsoft 責任</span><span class="sxs-lookup"><span data-stu-id="d77c5-105">Microsoft responsibilities</span></span>
<span data-ttu-id="d77c5-106">**Office 365 應用程式**Microsoft 會提供完整的部署、 更新和支援的特定的 Office 365 應用程式的服務。</span><span class="sxs-lookup"><span data-stu-id="d77c5-106">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps.</span></span> <span data-ttu-id="d77c5-107">所有使用者會都收到 Office 365 隨執行，以便使用者可以快速上手，裝置的映像中包含的應用程式 64 位元版本的基底集。</span><span class="sxs-lookup"><span data-stu-id="d77c5-107">All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive.</span></span> <span data-ttu-id="d77c5-108">Project 和 Visio 應用程式中的 Office 365 套件將分別獲得授權。</span><span class="sxs-lookup"><span data-stu-id="d77c5-108">The Project and Visio applications in of the Office 365 suite are licensed separately.</span></span>  <span data-ttu-id="d77c5-109">Microsoft 受管理的電腦會提供讓 IT 系統管理員管理授權及部署這些應用程式適當地為其組織的部署群組。</span><span class="sxs-lookup"><span data-stu-id="d77c5-109">Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization.</span></span> <span data-ttu-id="d77c5-110">Microsoft 將會支援透過 Microsoft 受管理的桌上型電腦支援頻道這些應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="d77c5-110">Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="d77c5-111">**營運應用程式**Microsoft 提供工具的 IT 系統管理員管理及部署至使用者其-營運 (LOB) 應用程式作為 Intune 產品的一部分。</span><span class="sxs-lookup"><span data-stu-id="d77c5-111">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product.</span></span> <span data-ttu-id="d77c5-112">Microsoft 將支援如同詳細的[行的商務應用程式](#line-of-business-applications)的應用程式部署問題</span><span class="sxs-lookup"><span data-stu-id="d77c5-112">Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="d77c5-113">**使用 Intune 部署**Intune 會連結至**商務用 Microsoft Store** ，讓採購應用程式以透過 Intune 部署 Microsoft 受管理的電腦上架期間。</span><span class="sxs-lookup"><span data-stu-id="d77c5-113">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune.</span></span> <span data-ttu-id="d77c5-114">Microsoft 也會部署至使用者從 Microsoft 網上商店的公司入口網站應用程式，以便 IT 系統管理員可以為使用者提供自助體驗。</span><span class="sxs-lookup"><span data-stu-id="d77c5-114">Microsoft will also deploy the Company Portal application from the Microsoft Store to end users so that IT Administrators can provide a self-service experience for their end users.</span></span>

<span data-ttu-id="d77c5-115">**應用程式管理**Microsoft 可能會找出受限制的應用程式，這並不適合現代化工作場所增進因其系統的影響。</span><span class="sxs-lookup"><span data-stu-id="d77c5-115">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact.</span></span> <span data-ttu-id="d77c5-116">識別此類應用程式時 Microsoft 將會通知客戶，而該應用程式需要從租用戶中移除。</span><span class="sxs-lookup"><span data-stu-id="d77c5-116">When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

<span data-ttu-id="d77c5-117">如需有關受限制的應用程式行為和應用程式需求的詳細資訊，請參閱 < <b0>Microsoft 受管理的電腦應用程式需求</b0></span><span class="sxs-lookup"><span data-stu-id="d77c5-117">For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="customer-responsibilities"></a><span data-ttu-id="d77c5-118">客戶責任</span><span class="sxs-lookup"><span data-stu-id="d77c5-118">Customer responsibilities</span></span>
<span data-ttu-id="d77c5-119">Office 365 套件是核心 Microsoft 的生產力供應項目，隨附於 Microsoft 受管理電腦的所有使用者的 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="d77c5-119">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="d77c5-120">Microsoft 部署、 更新，以及支援 Microsoft 受管理的電腦裝置的 Office 應用程式時仍有一些客戶有責任的區域。</span><span class="sxs-lookup"><span data-stu-id="d77c5-120">While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="d77c5-121">**指派授權**的客戶負責將適當的授權指派給使用者的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d77c5-121">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="d77c5-122">**新增使用者至安全性群組**-的客戶與使用者需要 Project 或 Visio，IT 系統管理員必須將這些使用者加入適當的部署群組。</span><span class="sxs-lookup"><span data-stu-id="d77c5-122">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="d77c5-123">IT 系統管理員也負責管理這些使用者的生命週期結束。</span><span class="sxs-lookup"><span data-stu-id="d77c5-123">IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="d77c5-124">**新增元件部署 Office 365**的客戶負責部署至 Office 365 套件這必要的任何增益集。</span><span class="sxs-lookup"><span data-stu-id="d77c5-124">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="d77c5-125">由於-營運 (LOB) 應用程式是唯一的每個客戶，客戶負責管理其組織未部署由 Microsoft 中的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="d77c5-125">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft.</span></span> <span data-ttu-id="d77c5-126">其中包括：</span><span class="sxs-lookup"><span data-stu-id="d77c5-126">This includes:</span></span>
- <span data-ttu-id="d77c5-127">決定哪些應用程式所需及他們需要由誰</span><span class="sxs-lookup"><span data-stu-id="d77c5-127">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="d77c5-128">將應用程式指派給這些使用者</span><span class="sxs-lookup"><span data-stu-id="d77c5-128">Assigning apps to those users</span></span>
- <span data-ttu-id="d77c5-129">建立及管理應用程式的工作分派的維護 Azure Active Directory (AD) 群組</span><span class="sxs-lookup"><span data-stu-id="d77c5-129">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="d77c5-130">客戶必須將 LOB 應用程式上傳到 Intune。</span><span class="sxs-lookup"><span data-stu-id="d77c5-130">The customer must upload LOB apps to Intune.</span></span> <span data-ttu-id="d77c5-131">然後，他們必須負責部署、 更新，並透過其各自的週期，解除委任這些應用程式，以及管理這些應用程式的使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="d77c5-131">They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.</span></span>

## <a name="office-applications"></a><span data-ttu-id="d77c5-132">Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-132">Office applications</span></span>
<span data-ttu-id="d77c5-133">Microsoft 365 E5 授權的一部分，Microsoft 被部署 Office 365 Standard Suite （64 位元）。</span><span class="sxs-lookup"><span data-stu-id="d77c5-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="d77c5-134">如需詳細資訊，請參閱 < <b0>Microsoft 受管理電腦技術</b0></span><span class="sxs-lookup"><span data-stu-id="d77c5-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md)</span></span> <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a><span data-ttu-id="d77c5-135">線條的商務應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-135">Line-of-business applications</span></span>
<span data-ttu-id="d77c5-136">下表總結了責任，跨-營運 (LOB) 應用程式的不同階段。</span><span class="sxs-lookup"><span data-stu-id="d77c5-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="d77c5-137">應用程式的工作項目</span><span class="sxs-lookup"><span data-stu-id="d77c5-137">Application work items</span></span> |    <span data-ttu-id="d77c5-138">客戶</span><span class="sxs-lookup"><span data-stu-id="d77c5-138">Customer</span></span>    | <span data-ttu-id="d77c5-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="d77c5-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="d77c5-140">**上架應用程式**</span><span class="sxs-lookup"><span data-stu-id="d77c5-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="d77c5-141">識別應用程式所需的目標的使用者群組</span><span class="sxs-lookup"><span data-stu-id="d77c5-141">Identify applications needed for targeted user groups</span></span>   | ![是](images/checkmark.png)  |
<span data-ttu-id="d77c5-143">建立及管理應用程式部署 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="d77c5-143">Create and manage Azure AD groups for app deployment</span></span> | ![是](images/checkmark.png) |   
<span data-ttu-id="d77c5-145">**應用程式封裝**</span><span class="sxs-lookup"><span data-stu-id="d77c5-145">**App Packaging**</span></span> |  |
<span data-ttu-id="d77c5-146">封裝應用程式，以符合 Intune 部署標準</span><span class="sxs-lookup"><span data-stu-id="d77c5-146">Package apps to meet Intune deployment standards</span></span> |  ![是](images/checkmark.png) |  
<span data-ttu-id="d77c5-148">將應用程式上傳到 Intune</span><span class="sxs-lookup"><span data-stu-id="d77c5-148">Upload apps to Intune</span></span> | ![是](images/checkmark.png)     |
<span data-ttu-id="d77c5-150">Microsoft 受管理的桌上型電腦環境中測試應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![是](images/checkmark.png) |  
<span data-ttu-id="d77c5-152">測試與使用者的應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-152">Test apps with end users</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="d77c5-154">**部署**</span><span class="sxs-lookup"><span data-stu-id="d77c5-154">**Deployment**</span></span> | |
<span data-ttu-id="d77c5-155">管理，並將使用者指派給應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-155">Manage and assign users to applications</span></span>  | ![是](images/checkmark.png)  |
<span data-ttu-id="d77c5-157">Intune 部署工具會傳遞至遠端用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![是](images/checkmark.png)
<span data-ttu-id="d77c5-159">識別並部署到 Intune 應用程式更新</span><span class="sxs-lookup"><span data-stu-id="d77c5-159">Identify and deploy application updates through Intune</span></span> | ![是](images/checkmark.png)    |
<span data-ttu-id="d77c5-161">Unistall] 和 [移除應用程式時已停用</span><span class="sxs-lookup"><span data-stu-id="d77c5-161">Unistall and remove applications when they have been retired</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="d77c5-163">**管理**</span><span class="sxs-lookup"><span data-stu-id="d77c5-163">**Management**</span></span> | |
<span data-ttu-id="d77c5-164">視需要而定，並指派授權</span><span class="sxs-lookup"><span data-stu-id="d77c5-164">Procure and assign licenses</span></span> |   ![是](images/checkmark.png)     |
<span data-ttu-id="d77c5-166">提供-營運應用程式的使用者支援</span><span class="sxs-lookup"><span data-stu-id="d77c5-166">Provide end-user support for line-of-business apps</span></span>  | ![是](images/checkmark.png) |
<span data-ttu-id="d77c5-168">管理應用程式設定遠端</span><span class="sxs-lookup"><span data-stu-id="d77c5-168">Manage app settings remotely</span></span>    | ![是](images/checkmark.png) |

<span data-ttu-id="d77c5-170">如需 LOB 應用程式需求的詳細資訊，請參閱 < <b0>Microsoft 受管理的電腦應用程式需求</b0></span><span class="sxs-lookup"><span data-stu-id="d77c5-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>


## <a name="intune-application-deployment"></a><span data-ttu-id="d77c5-171">Intune 應用程式部署</span><span class="sxs-lookup"><span data-stu-id="d77c5-171">Intune application deployment</span></span>
<span data-ttu-id="d77c5-172">透過 Microsoft 受管理的桌上型電腦系統管理入口網站，或透過 Intune 入口網站，可以處理應用程式管理。</span><span class="sxs-lookup"><span data-stu-id="d77c5-172">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal.</span></span> <span data-ttu-id="d77c5-173">Intune 的應用程式管理入口網站顯示部署 for Windows、 Android 和 iOS 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d77c5-173">Intune’s app management portal shows applications deployed for Windows, Android, and iOS.</span></span> <span data-ttu-id="d77c5-174">Microsoft 受管理的桌上型電腦系統管理入口網站限制檢視以 Windows 10 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d77c5-174">Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications.</span></span> <span data-ttu-id="d77c5-175">兩者都可透過 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="d77c5-175">Both are available through the Azure Portal.</span></span> 
* [<span data-ttu-id="d77c5-176">Intune 應用程式管理基本概念</span><span class="sxs-lookup"><span data-stu-id="d77c5-176">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
* [<span data-ttu-id="d77c5-177">將應用程式新增至 Intune</span><span class="sxs-lookup"><span data-stu-id="d77c5-177">Add apps to Intune</span></span>](https://docs.microsoft.com/intune/app-management)
   * [<span data-ttu-id="d77c5-178">新增-營運應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-178">Add a line-of-business App</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
   * [<span data-ttu-id="d77c5-179">將 Win32 應用程式新增至 Intune</span><span class="sxs-lookup"><span data-stu-id="d77c5-179">Add Win32 apps to Intune</span></span>](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [<span data-ttu-id="d77c5-180">新增 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-180">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
* [<span data-ttu-id="d77c5-181">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-181">Deploy apps</span></span>](https://docs.microsoft.com/intune/apps-deploy)
   * [<span data-ttu-id="d77c5-182">將應用程式部署至 Windows 10</span><span class="sxs-lookup"><span data-stu-id="d77c5-182">Deploy apps to Windows 10</span></span>](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* <span data-ttu-id="d77c5-183">公司入口網站</span><span class="sxs-lookup"><span data-stu-id="d77c5-183">Company Portal</span></span>
   * [<span data-ttu-id="d77c5-184">部署在公司入口網站</span><span class="sxs-lookup"><span data-stu-id="d77c5-184">Deploy the Company Portal</span></span>](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [<span data-ttu-id="d77c5-185">設定公司入口網站應用程式</span><span class="sxs-lookup"><span data-stu-id="d77c5-185">Configure the Company Portal app</span></span>](https://docs.microsoft.com/intune/company-portal-app)
