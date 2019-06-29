---
title: 部署 Microsoft 受管理電腦裝置的應用程式
description: 將應用程式新增及部署至 Microsoft 受管理的電腦裝置的資訊。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、應用程式、企業營運應用程式、LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5eac2e8c3023015bd034c51ad7e16a669a484772
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390420"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="50400-104">將應用程式部署至 Microsoft 受管理的電腦裝置</span><span class="sxs-lookup"><span data-stu-id="50400-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="50400-105">上架的一部分加入 Microsoft 受管理的桌面, 包括在使用者的裝置中新增及部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="50400-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="50400-106">一旦您使用 Microsoft 受管理的桌面入口網站, 您可以新增和部署您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="50400-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="50400-107">整體程式如下所示:</span><span class="sxs-lookup"><span data-stu-id="50400-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="50400-108">[將應用程式新增至 Microsoft 受管理的桌面入口網站](#1)-這可以是現有的企業營運 (LOB) 應用程式, 或您已與 Intune 同步處理的 Microsoft Store 中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="50400-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="50400-109">[建立應用程式指派的 Azure Active Directory (AD) 群組](#2)-您將使用這些群組來管理應用程式指派。</span><span class="sxs-lookup"><span data-stu-id="50400-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="50400-110">將應用程式指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="50400-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="50400-111">步驟 1: 將應用程式新增至 Microsoft 受管理的桌面入口網站</span><span class="sxs-lookup"><span data-stu-id="50400-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="50400-112">您可以將[Win32 或 WINDOWS MSI 型應用](#lob-apps)程式, 或[Microsoft Store for Business App](#msfb-apps)新增至 Microsoft 受管理的電腦, 然後將其部署至 Microsoft 受管理的電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="50400-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="50400-113">Microsoft 受管理的電腦的 Win32 或 Windows MSI 型應用程式</span><span class="sxs-lookup"><span data-stu-id="50400-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="50400-114">您可以將企業營運 (LOB) 應用程式新增至 Microsoft 受管理的桌面入口網站。</span><span class="sxs-lookup"><span data-stu-id="50400-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="50400-115">如需 Microsoft 受管理電腦裝置上所安裝之應用程式需求的相關資訊, 請參閱[Microsoft 受管理的桌面應用程式需求](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)。</span><span class="sxs-lookup"><span data-stu-id="50400-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="50400-116">在此程式中, 您將選取您要新增的應用程式類型, 然後設定及上傳應用程式來源。</span><span class="sxs-lookup"><span data-stu-id="50400-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="50400-117">**將 LOB 應用程式或 Windows 應用程式新增至 Microsoft 受管理的桌面入口網站**</span><span class="sxs-lookup"><span data-stu-id="50400-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="50400-118">您可以登入 Microsoft 受管理的桌面入口網站, 或登入 Intune, 然後搜尋 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="50400-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="50400-119">我們將會顯示 [登入 Microsoft 受管理的桌面入口網站]。</span><span class="sxs-lookup"><span data-stu-id="50400-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="50400-120">登入[Microsoft 受管理的桌面管理入口網站](http://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="50400-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="50400-121">在 [**清查**] 下, 選取 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="50400-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="50400-122">在 [應用程式工作量] 中, 選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="50400-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="50400-123">在 [**新增應用程式**] 中, 選取 [**企業營運應用程式**] 或 **[Windows 應用程式 (Win32)-預覽**]。</span><span class="sxs-lookup"><span data-stu-id="50400-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="50400-124">如果您已選取**企業營運應用程式**, 請參閱[新增 Windows 營運企業應用程式至 Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) , 以取得新增和設定企業營運應用程式的相關指示。</span><span class="sxs-lookup"><span data-stu-id="50400-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="50400-125">如果您選取 **[Windows app (Win32)-預覽**], 請參閱[Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management)以取得新增和設定 Windows 應用程式的指示。</span><span class="sxs-lookup"><span data-stu-id="50400-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="50400-126">商務用 Microsoft Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="50400-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="50400-127">如果您尚未註冊商務用 Microsoft Store, 您可以在購買應用程式時註冊。</span><span class="sxs-lookup"><span data-stu-id="50400-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="50400-128">有您的應用程式之後, 您可以使用 Microsoft 受管理的電腦進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="50400-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="50400-129">**若要從商務用 Microsoft Store 購買應用程式**</span><span class="sxs-lookup"><span data-stu-id="50400-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="50400-130">使用 Microsoft Store for Business Admin account 登入[Microsoft store For business](https://businessstore.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="50400-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="50400-131">選取 [**為我的群組購買**]。</span><span class="sxs-lookup"><span data-stu-id="50400-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="50400-132">使用搜尋來找出您想要的應用程式, 並選取該應用程式。</span><span class="sxs-lookup"><span data-stu-id="50400-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="50400-133">在 [產品詳細資料] 中, 選取 [**取得應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="50400-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="50400-134">Microsoft Store 會將應用程式新增至貴組織的**產品 & 服務**。</span><span class="sxs-lookup"><span data-stu-id="50400-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="50400-135">**強制執行 Intune 與 Microsoft Store for Business 之間的同步處理**</span><span class="sxs-lookup"><span data-stu-id="50400-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="50400-136">以 Intune 系統管理員或您租使用者的全域系統管理員身分登入[Azure 入口網站](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="50400-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="50400-137">選取 [**所有服務 > Intune**]。</span><span class="sxs-lookup"><span data-stu-id="50400-137">Select **All services > Intune**.</span></span> <span data-ttu-id="50400-138">Intune 位於 [監視 + 管理] 區段中。</span><span class="sxs-lookup"><span data-stu-id="50400-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="50400-139">在 [Intune] 窗格中, 選取 [**用戶端應用程式**], 然後選取 [**商務用 Microsoft Store**]。</span><span class="sxs-lookup"><span data-stu-id="50400-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="50400-140">選取 [**啟用**], 以使用 Intune 同步處理商務應用程式的 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="50400-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="50400-141">如果您還沒有使用 Intune 註冊並關聯 Microsoft Store for Business 帳戶</span><span class="sxs-lookup"><span data-stu-id="50400-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="50400-142">選取您的 Intune 主控台中用來進行商務用 Microsoft Store 應用程式的語言</span><span class="sxs-lookup"><span data-stu-id="50400-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="50400-143">選取 [**同步**處理], 以使用 Intune 同步處理商務應用程式的 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="50400-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="50400-144">確認 Microsoft Store for Business 與 Intune 之間的同步處理已啟用 (下一個步驟)。</span><span class="sxs-lookup"><span data-stu-id="50400-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="50400-145">**確認 Intune 與 Microsoft Store for Business 之間的同步處理處於作用中狀態**</span><span class="sxs-lookup"><span data-stu-id="50400-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="50400-146">使用 Microsoft Store for Business Admin account 登入[Microsoft store For business](https://businessstore.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="50400-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="50400-147">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="50400-147">Select **Manage**.</span></span>
3. <span data-ttu-id="50400-148">選取 [**設定**], 然後選取 [**分散**]。</span><span class="sxs-lookup"><span data-stu-id="50400-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="50400-149">在 [**管理工具**] 下, 確認已列出 Intune, 且狀態為 [已**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="50400-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="50400-150">步驟 2: 建立 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="50400-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="50400-151">為每個應用程式建立三個 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="50400-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="50400-152">下表概述您將需要的群組 (可供使用、需要和卸載)。</span><span class="sxs-lookup"><span data-stu-id="50400-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="50400-153">應用程式指派類型</span><span class="sxs-lookup"><span data-stu-id="50400-153">App assignment type</span></span> |   <span data-ttu-id="50400-154">群組使用</span><span class="sxs-lookup"><span data-stu-id="50400-154">Group use</span></span>   | <span data-ttu-id="50400-155">範例 Azure AD 名稱</span><span class="sxs-lookup"><span data-stu-id="50400-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="50400-156">可以使用</span><span class="sxs-lookup"><span data-stu-id="50400-156">Available</span></span> |  <span data-ttu-id="50400-157">此應用程式可從公司入口網站應用程式或網站取得。</span><span class="sxs-lookup"><span data-stu-id="50400-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="50400-158">MMD –*應用程式名稱*-可用</span><span class="sxs-lookup"><span data-stu-id="50400-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="50400-159">必要</span><span class="sxs-lookup"><span data-stu-id="50400-159">Required</span></span> |  <span data-ttu-id="50400-160">應用程式會安裝在選取群組中的裝置上。</span><span class="sxs-lookup"><span data-stu-id="50400-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="50400-161">MMD –*應用程式名稱*-必要</span><span class="sxs-lookup"><span data-stu-id="50400-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="50400-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="50400-162">Uninstall</span></span> |  <span data-ttu-id="50400-163">從選取的群組中的裝置卸載應用程式。</span><span class="sxs-lookup"><span data-stu-id="50400-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="50400-164">MMD –*應用程式名稱*–卸載</span><span class="sxs-lookup"><span data-stu-id="50400-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="50400-165">將您的使用者新增至這些群組, 以讓應用程式 availabe、安裝應用程式, 或從 Microsoft 受管理的電腦裝置中移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="50400-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="50400-166">步驟 3: 將應用程式指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="50400-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="50400-167">**將應用程式指派給您的使用者**</span><span class="sxs-lookup"><span data-stu-id="50400-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="50400-168">登入[Microsoft 受管理的桌面管理入口網站](http://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="50400-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="50400-169">在 [受管理的桌面] 窗格中選取 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="50400-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="50400-170">在 [應用程式工作量] 中, 選取您要指派使用者的應用程式, 然後選取 [**指派使用者群組**]。</span><span class="sxs-lookup"><span data-stu-id="50400-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="50400-171">針對特定應用程式, 選取 [工作分派類型] ([可用]、[必要]、[卸載]), 並指派適當的群組。</span><span class="sxs-lookup"><span data-stu-id="50400-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="50400-172">在 [指派應用程式] 窗格中, 選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="50400-172">In the Assign Apps pane, select **OK**.</span></span>

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->
