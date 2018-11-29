---
title: 準備 Microsoft 應用程式受管理的桌面
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: ebeb54bd5d1f50cbb6f78b1c8ad4a624c449b8c2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866322"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="99541-103">準備 Microsoft 應用程式受管理的桌面</span><span class="sxs-lookup"><span data-stu-id="99541-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="99541-104">查看 Microsoft 及 Microsoft 受管理的桌上型電腦的客戶同樣也請有重大、 尚未不同責任周圍搭配 Microsoft 受管理的桌上型電腦的應用程式。</span><span class="sxs-lookup"><span data-stu-id="99541-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilites"></a><span data-ttu-id="99541-105">Microsoft responsibilites</span><span class="sxs-lookup"><span data-stu-id="99541-105">Microsoft responsibilites</span></span>
<span data-ttu-id="99541-p101">**Office 365 應用程式**Microsoft 會提供完整的部署、 更新及支援的特定 Office 365 應用程式的服務。所有使用者會都收到基底的 Office 365 按一下此選項即可執行 64 位元版本的應用程式，讓使用者可以快速上手裝置的映像中包含一組。專案與 Visio 應用程式中的 Office 365 套裝軟體分別授權。 Microsoft 受管理的桌上型電腦會提供讓 IT 系統管理員管理授權及部署這些應用程式適當的組織部署群組。Microsoft 支援透過 Microsoft 受管理的桌上型電腦支援通道這些應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="99541-p101">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="99541-p102">**企業營運系統應用程式**Microsoft 提供的管理及部署給使用者及其企業營運系統應用程式作為 Intune 產品的一部分的 it 專業人員適用的工具。Microsoft 支援依照[企業營運系統應用程式](#line-of-business-applications)中的應用程式部署問題</span><span class="sxs-lookup"><span data-stu-id="99541-p102">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their Line of Business applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="99541-p103">**部署 intune**Intune Microsoft 受管理的桌上型電腦 onboarding 允許採購應用程式，以透過 Intune 部署期間要連結到**Microsoft Store for Business** 。使 IT 管理員可以為使用者提供自助體驗 Microsoft 也會為一般使用者部署的公司入口網站的 web 型版本。</span><span class="sxs-lookup"><span data-stu-id="99541-p103">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.</span></span>

<span data-ttu-id="99541-p104">**應用程式的管理**Microsoft 可能會識別因其系統影響不適當的現代工作場所限制應用程式。識別應用程式時 Microsoft 將通知客戶與該應用程式需要移除租用戶。</span><span class="sxs-lookup"><span data-stu-id="99541-p104">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

## <a name="customer-responsibilities"></a><span data-ttu-id="99541-117">客戶責任</span><span class="sxs-lookup"><span data-stu-id="99541-117">Customer responsibilities</span></span>
<span data-ttu-id="99541-p105">Office 365 套裝軟體 Microsoft 的產能方案的核心和隨附於 Microsoft 365 授權的 Microsoft 受管理的桌上型電腦的所有使用者。Microsoft 會部署、 更新、 以及支援 Microsoft 受管理的桌上型電腦裝置的 Office 應用程式時仍有某些客戶會負責的區域。</span><span class="sxs-lookup"><span data-stu-id="99541-p105">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="99541-120">**將授權指派**-客戶負責將適當的授權指派給 Office 365 的使用者。</span><span class="sxs-lookup"><span data-stu-id="99541-120">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="99541-p106">**新增使用者至安全性群組**-客戶與使用者需要 [專案] 或 [Visio IT 系統管理員必須那些將使用者新增至適當的部署群組。IT 系統管理員也是週期的負責管理這些使用者結束。</span><span class="sxs-lookup"><span data-stu-id="99541-p106">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="99541-123">**新增元件部署 Office 365** -客戶負責部署到 Office 365 套裝軟體這必要的任何增益集。</span><span class="sxs-lookup"><span data-stu-id="99541-123">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="99541-p107">由於企業營運系統 (LOB) 應用程式是唯一的每個客戶、 客戶是負責管理未部署 microsoft 其組織內的所有應用程式。這包括：</span><span class="sxs-lookup"><span data-stu-id="99541-p107">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:</span></span>
- <span data-ttu-id="99541-126">決定需要哪些應用程式及誰需要它們</span><span class="sxs-lookup"><span data-stu-id="99541-126">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="99541-127">指派給這些使用者的應用程式</span><span class="sxs-lookup"><span data-stu-id="99541-127">Assigning apps to those users</span></span>
- <span data-ttu-id="99541-128">建立及維護 Azure Active Directory (AD) 群組來管理應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="99541-128">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="99541-p108">一旦 LOB 應用程式的核心集已識別客戶將採購、 授權、 封裝、 及 Microsoft 受管理的桌上型電腦環境中測試這些應用程式。客戶必須上傳及部署至 Intune 部署、 更新和解除委任其 LOB 應用程式的應用程式。客戶是負責管理其使用者的 LOB 應用程式支援。</span><span class="sxs-lookup"><span data-stu-id="99541-p108">Once the core set of LOB apps has been identified the customer will procure, license, package, and test those applications in the Microsoft Managed Desktop environment. The customer must upload and deploy applications to Intune to deploy, update, and decommission their LOB applications. Customers are responsible for managing LOB apps support for their users.</span></span>
 

## <a name="office-applications"></a><span data-ttu-id="99541-132">Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="99541-132">Office applications</span></span>
<span data-ttu-id="99541-133">Microsoft 365 E5 授權的一部分，是由 Microsoft 部署 Office 365 Standard Suite （64 位元）。</span><span class="sxs-lookup"><span data-stu-id="99541-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="99541-134">如需詳細資訊，請參閱[Microsoft 受管理的桌上型電腦技術](../intro/technologies.md)<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span><span class="sxs-lookup"><span data-stu-id="99541-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span></span>

## <a name="line-of-business-applications"></a><span data-ttu-id="99541-135">企業營運系統應用程式</span><span class="sxs-lookup"><span data-stu-id="99541-135">Line-of-business applications</span></span>
<span data-ttu-id="99541-136">下表摘要責任跨企業營運系統 (LOB) 應用程式不同的階段。</span><span class="sxs-lookup"><span data-stu-id="99541-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="99541-137">應用程式工作項目</span><span class="sxs-lookup"><span data-stu-id="99541-137">Application work items</span></span> |    <span data-ttu-id="99541-138">客戶</span><span class="sxs-lookup"><span data-stu-id="99541-138">Customer</span></span>    | <span data-ttu-id="99541-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="99541-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="99541-140">**Onboarding 應用程式**</span><span class="sxs-lookup"><span data-stu-id="99541-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="99541-141">識別應用程式所需的目標的使用者群組</span><span class="sxs-lookup"><span data-stu-id="99541-141">Identify applications needed for targeted user groups</span></span>   | ![是](images/checkmark.png)  |
<span data-ttu-id="99541-143">建立及管理的應用程式部署 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="99541-143">Create and manage Azure AD groups for app deployment</span></span> | ![是](images/checkmark.png) |   
<span data-ttu-id="99541-145">**應用程式封裝**</span><span class="sxs-lookup"><span data-stu-id="99541-145">**App Packaging**</span></span> |  |
<span data-ttu-id="99541-146">封裝應用程式，以符合 Intune 部署標準 （英文）</span><span class="sxs-lookup"><span data-stu-id="99541-146">Package apps to meet Intune deployment standards</span></span> |  ![是](images/checkmark.png) |  
<span data-ttu-id="99541-148">將應用程式上傳至 Intune</span><span class="sxs-lookup"><span data-stu-id="99541-148">Upload apps to Intune</span></span> | ![是](images/checkmark.png)     |
<span data-ttu-id="99541-150">Microsoft 受管理的桌上型電腦環境中測試應用程式</span><span class="sxs-lookup"><span data-stu-id="99541-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![是](images/checkmark.png) |  
<span data-ttu-id="99541-152">測試使用者的應用程式</span><span class="sxs-lookup"><span data-stu-id="99541-152">Test apps with end users</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="99541-154">**部署**</span><span class="sxs-lookup"><span data-stu-id="99541-154">**Deployment**</span></span> | |
<span data-ttu-id="99541-155">管理，並將使用者指派至應用程式</span><span class="sxs-lookup"><span data-stu-id="99541-155">Manage and assign users to applications</span></span>  | ![是](images/checkmark.png)  |
<span data-ttu-id="99541-157">Intune 部署工具將傳遞給遠端用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="99541-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![是](images/checkmark.png)
<span data-ttu-id="99541-159">識別及部署到 Intune 的應用程式更新</span><span class="sxs-lookup"><span data-stu-id="99541-159">Identify and deploy application updates through Intune</span></span> | ![是](images/checkmark.png)    |
<span data-ttu-id="99541-161">Unistall 及移除應用程式時已遭淘汰</span><span class="sxs-lookup"><span data-stu-id="99541-161">Unistall and remove applications when they have been retired</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="99541-163">**管理**</span><span class="sxs-lookup"><span data-stu-id="99541-163">**Management**</span></span> | |
<span data-ttu-id="99541-164">購買和指派授權</span><span class="sxs-lookup"><span data-stu-id="99541-164">Procure and assign licenses</span></span> |   ![是](images/checkmark.png)     |
<span data-ttu-id="99541-166">提供企業營運系統應用程式的使用者支援</span><span class="sxs-lookup"><span data-stu-id="99541-166">Provide end-user support for line-of-business apps</span></span>  | ![是](images/checkmark.png) |
<span data-ttu-id="99541-168">管理應用程式設定遠端</span><span class="sxs-lookup"><span data-stu-id="99541-168">Manage app settings remotely</span></span>    | ![是](images/checkmark.png) |

<span data-ttu-id="99541-170">如需 LOB 應用程式需求的資訊，請參閱[Microsoft 受管理的桌面應用程式需求](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="99541-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="resources"></a><span data-ttu-id="99541-171">資源</span><span class="sxs-lookup"><span data-stu-id="99541-171">Resources</span></span>
<span data-ttu-id="99541-172">雖然許多服務會超出範圍的 Microsoft 受管理的桌上型電腦作業有哪些 Microsoft 產品項目可能會協助客戶管理其應用程式的服務。</span><span class="sxs-lookup"><span data-stu-id="99541-172">While many services are out of scope for Microsoft Managed Desktop operations there are services which Microsoft offers which may help the customer manage their applications.</span></span>

### <a name="windows-upgrade-readiness"></a><span data-ttu-id="99541-173">Windows 升級整備</span><span class="sxs-lookup"><span data-stu-id="99541-173">Windows Upgrade Readiness</span></span>
<span data-ttu-id="99541-p109">設定新的 Microsoft 受管理的裝置的重要部分了解哪些應用程式所需的裝置的使用者。Windows 升級整備是有助於了解應用程式橫向其公司的企業版，並可協助他們例如檢閱這些應用程式相關的重要資料的 Microsoft 工具：</span><span class="sxs-lookup"><span data-stu-id="99541-p109">A key part of setting up new Microsoft Managed Devices is understanding which apps are needed for device users. Windows Upgrade Readiness is a Microsoft tool which helps enterprises understand the application landscape inside their company, and helps them to review key data about those applications, such as:</span></span>

- <span data-ttu-id="99541-176">**應用程式使用量**遙測資料用來監視應用程式使用狀況。</span><span class="sxs-lookup"><span data-stu-id="99541-176">**Application usage** - Telemetry data is used to monitor application usage.</span></span>
- <span data-ttu-id="99541-p110">**應用程式相容性**升級整備會查看每個應用程式及如何廣泛已部署在最新版的 Windows 10 會看到及評估如何識別如果它是"準備 Windows"。此資料可協助測試工作已經廣泛不採用的應用程式上的焦點。</span><span class="sxs-lookup"><span data-stu-id="99541-p110">**Application compatibility** - Upgrade Readiness looks at each application and sees how broadly it has been deployed on the latest version of Windows 10 and assesses how to identify if it is “Ready for Windows”. This data helps focus testing efforts on applications which aren’t already broadly adopted.</span></span>

### <a name="intune-application-deployment"></a><span data-ttu-id="99541-179">Intune 應用程式部署</span><span class="sxs-lookup"><span data-stu-id="99541-179">Intune application deployment</span></span>
<span data-ttu-id="99541-p111">透過 Microsoft 受管理的桌上型電腦管理入口網站或 Intune 入口網站可處理應用程式管理。Intune 的 app management 入口網站會顯示為 Windows、 Android、 及 iOS 部署的應用程式。Microsoft 受管理的桌上型電腦管理入口網站會限制 Windows 10 應用程式的檢視。二者都可透過 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="99541-p111">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal.</span></span> 
- [<span data-ttu-id="99541-184">Intune 應用程式管理基礎 （英文)</span><span class="sxs-lookup"><span data-stu-id="99541-184">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
- [<span data-ttu-id="99541-185">新增 Windows 32 應用程式</span><span class="sxs-lookup"><span data-stu-id="99541-185">Add a Windows 32 application</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
- [<span data-ttu-id="99541-186">新增 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="99541-186">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
- [<span data-ttu-id="99541-187">指定並將應用程式部署至群組</span><span class="sxs-lookup"><span data-stu-id="99541-187">Assign and deploy apps to groups</span></span>](https://docs.microsoft.com/intune/apps-deploy)

### <a name="application-packaging-standards"></a><span data-ttu-id="99541-188">應用程式封裝標準 （英文)</span><span class="sxs-lookup"><span data-stu-id="99541-188">Application packaging standards</span></span>
<span data-ttu-id="99541-p112">若要部署的 Intune 他們必須透過 Windows 32 應用程式封裝為其中一個單一。MSI，.appx，或。MSIX。Intune 的最常見套件類型目前的狀態。MSI。</span><span class="sxs-lookup"><span data-stu-id="99541-p112">To deploy Windows 32 applications through Intune they must be packaged as either a single .MSI, an .appx, or .MSIX. The most common package type for Intune is currently .MSI.</span></span>
