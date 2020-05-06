---
title: 將應用程式部署至裝置
description: 有關新增及部署 Microsoft 受管理桌面裝置之應用程式的資訊。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、應用程式、企業營運服務應用程式、LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd6efc56441cfbe8a05404319246c5e0bbe10ab
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046325"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="7c13e-104">將應用程式部署至裝置</span><span class="sxs-lookup"><span data-stu-id="7c13e-104">Deploy apps to devices</span></span>
<span data-ttu-id="7c13e-105">上架至 Microsoft Managed Desktop 的一部分包括新增及部署使用者裝置的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c13e-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="7c13e-106">使用 Microsoft 受管理的桌面入口網站後，您可以新增及部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c13e-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="7c13e-107">整體程式看起來如下所示：</span><span class="sxs-lookup"><span data-stu-id="7c13e-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="7c13e-108">[新增應用程式至 Microsoft 受管理的桌面入口網站](#1)-這可以是現有的企業營運（LOB）應用程式，或您已與 Intune 同步處理的 Microsoft Store for business 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c13e-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="7c13e-109">[建立應用程式指派的 Azure Active Directory （AD）群組](#2)-您將使用這些群組來管理應用程式指派。</span><span class="sxs-lookup"><span data-stu-id="7c13e-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="7c13e-110">指派應用程式給您的使用者</span><span class="sxs-lookup"><span data-stu-id="7c13e-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="7c13e-111">步驟1：將應用程式新增至 Microsoft 受管理的桌面入口網站</span><span class="sxs-lookup"><span data-stu-id="7c13e-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="7c13e-112">您可以將[Win32 （或 WINDOWS MSI 型應用](#lob-apps)程式）或[Microsoft Store for Business App](#msfb-apps)新增至 microsoft managed desktop，然後將其部署至 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="7c13e-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="7c13e-113">以 Win32 或 Windows MSI 為基礎的應用程式至 Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="7c13e-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="7c13e-114">您可以將企業營運（LOB）應用程式新增至 Microsoft 受管理的桌面入口網站。</span><span class="sxs-lookup"><span data-stu-id="7c13e-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="7c13e-115">如需 Microsoft 受管理的電腦裝置上安裝之應用程式需求的詳細資訊，請參閱[Microsoft Managed desktop app 需求](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)。</span><span class="sxs-lookup"><span data-stu-id="7c13e-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="7c13e-116">在此程式中，您將選取要新增的應用程式類型，然後設定並上傳應用程式來源。</span><span class="sxs-lookup"><span data-stu-id="7c13e-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="7c13e-117">**將您的 LOB 應用程式或 Windows 應用程式新增至 Microsoft 受管理的桌面入口網站**</span><span class="sxs-lookup"><span data-stu-id="7c13e-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="7c13e-118">您可以登入 Microsoft 受管理的桌面入口網站，或登入 Intune，然後搜尋 Microsoft Managed Desktop。</span><span class="sxs-lookup"><span data-stu-id="7c13e-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="7c13e-119">我們會顯示登入 Microsoft 受管理的桌面入口網站。</span><span class="sxs-lookup"><span data-stu-id="7c13e-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="7c13e-120">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="7c13e-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="7c13e-121">在 [**庫存**] 下，選取 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="7c13e-122">在 [應用程式工作負載] 中，選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="7c13e-123">在 [**新增應用程式**] 中，選取 [**企業營運應用程式**] 或 **[Windows 應用程式（Win32）**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="7c13e-124">如果您已選取 [企業營運]**應用程式**，請參閱[新增 Windows 營運 Windows 應用程式至 Microsoft Intune 以](https://docs.microsoft.com/intune/lob-apps-windows)取得有關新增及設定企業營運應用程式的指示。</span><span class="sxs-lookup"><span data-stu-id="7c13e-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="7c13e-125">如果您選取了 **[Windows 應用程式（Win32）**]，請參閱[Win32 應用程式管理](https://docs.microsoft.com/intune/apps-win32-app-management)以取得新增及設定 Windows 應用程式的指示。</span><span class="sxs-lookup"><span data-stu-id="7c13e-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="7c13e-126">Microsoft Store for Business 應用程式</span><span class="sxs-lookup"><span data-stu-id="7c13e-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="7c13e-127">若尚未註冊 Microsoft Store for Business，您可以在購買應用程式時進行註冊。</span><span class="sxs-lookup"><span data-stu-id="7c13e-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="7c13e-128">您有應用程式之後，您可以使用 Microsoft 受管理的桌面進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="7c13e-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="7c13e-129">**從商務用 Microsoft Store 購買應用程式**</span><span class="sxs-lookup"><span data-stu-id="7c13e-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="7c13e-130">使用您的 Microsoft Store for Business Admin account，登入[Microsoft store For business](https://businessstore.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="7c13e-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="7c13e-131">選取 [**為我的群組購買**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="7c13e-132">使用 [搜尋] 來找出您想要的應用程式，然後選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c13e-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="7c13e-133">在 [產品詳細資料] 中，選取 **[取得應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="7c13e-134">Microsoft Store 會將應用程式新增至貴組織的**產品**。</span><span class="sxs-lookup"><span data-stu-id="7c13e-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="7c13e-135">**強制 Intune 與 Microsoft Store for Business 之間的同步處理**</span><span class="sxs-lookup"><span data-stu-id="7c13e-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="7c13e-136">以 Intune 管理員身分登入[Azure 入口網站](https://portal.azure.com/)，或為您的租使用者登入全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="7c13e-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="7c13e-137">選取 [**所有服務] > Intune**。</span><span class="sxs-lookup"><span data-stu-id="7c13e-137">Select **All services > Intune**.</span></span> <span data-ttu-id="7c13e-138">Intune 位於監控 + 管理區段中。</span><span class="sxs-lookup"><span data-stu-id="7c13e-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="7c13e-139">在 Intune 窗格中，選取 [**用戶端應用程式**]，然後選取 [ **Microsoft Store for Business**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="7c13e-140">選取 [**啟用**]，以透過 Intune 同步處理您的 Microsoft Store for Business 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c13e-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="7c13e-141">若尚未註冊，請使用 Intune 註冊和關聯 Microsoft Store for Business 帳戶</span><span class="sxs-lookup"><span data-stu-id="7c13e-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="7c13e-142">從您的 Intune 主控台中，選取商務用 Microsoft 書店中的應用程式將顯示的語言</span><span class="sxs-lookup"><span data-stu-id="7c13e-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="7c13e-143">選取 [**同步**處理]，以使用 Intune 同步處理 Microsoft Store for Business 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c13e-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="7c13e-144">確認 Microsoft Store for Business 與 Intune 之間的同步處理為作用中（下一步）。</span><span class="sxs-lookup"><span data-stu-id="7c13e-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="7c13e-145">**確認 Intune 與 Microsoft Store for Business 之間的同步處理已啟用**</span><span class="sxs-lookup"><span data-stu-id="7c13e-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="7c13e-146">使用您的 Microsoft Store for Business Admin account，登入[Microsoft store For business](https://businessstore.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="7c13e-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="7c13e-147">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-147">Select **Manage**.</span></span>
3. <span data-ttu-id="7c13e-148">選取 [**設定**]，然後選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="7c13e-149">在 [**管理工具**] 下，確認已列出 Intune，且狀態**為 [作用中]**。</span><span class="sxs-lookup"><span data-stu-id="7c13e-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="7c13e-150">步驟2：建立 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="7c13e-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="7c13e-151">為每個應用程式建立三個 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7c13e-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="7c13e-152">下表概述您將需要的群組（可用、必要和卸載）。</span><span class="sxs-lookup"><span data-stu-id="7c13e-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="7c13e-153">應用程式指派類型</span><span class="sxs-lookup"><span data-stu-id="7c13e-153">App assignment type</span></span> |    <span data-ttu-id="7c13e-154">群組使用</span><span class="sxs-lookup"><span data-stu-id="7c13e-154">Group use</span></span>    | <span data-ttu-id="7c13e-155">Azure AD 名稱範例</span><span class="sxs-lookup"><span data-stu-id="7c13e-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="7c13e-156">可以使用</span><span class="sxs-lookup"><span data-stu-id="7c13e-156">Available</span></span> |  <span data-ttu-id="7c13e-157">該應用程式將可從公司入口網站應用程式或網站取得。</span><span class="sxs-lookup"><span data-stu-id="7c13e-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="7c13e-158">MMD –*應用程式名稱*–可用</span><span class="sxs-lookup"><span data-stu-id="7c13e-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="7c13e-159">必要</span><span class="sxs-lookup"><span data-stu-id="7c13e-159">Required</span></span> |  <span data-ttu-id="7c13e-160">App 已安裝在所選群組中的裝置上。</span><span class="sxs-lookup"><span data-stu-id="7c13e-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="7c13e-161">MMD –*應用程式名稱*–必要</span><span class="sxs-lookup"><span data-stu-id="7c13e-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="7c13e-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="7c13e-162">Uninstall</span></span> |  <span data-ttu-id="7c13e-163">已從選取群組中的裝置卸載應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c13e-163">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="7c13e-164">MMD –*應用程式名稱*–卸載</span><span class="sxs-lookup"><span data-stu-id="7c13e-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="7c13e-165">將您的使用者新增至這些群組，讓應用程式 availabe、安裝應用程式，或從 Microsoft 受管理的桌面裝置移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c13e-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="7c13e-166">步驟3：將應用程式指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="7c13e-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="7c13e-167">**若要將應用程式指派給您的使用者**</span><span class="sxs-lookup"><span data-stu-id="7c13e-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="7c13e-168">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="7c13e-168">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="7c13e-169">在 [受管理的桌面] 窗格中，選取 [ **app**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="7c13e-170">在 [應用程式工作負載] 中，選取您要指派使用者的應用程式，然後選取 [**指派使用者群組**]。</span><span class="sxs-lookup"><span data-stu-id="7c13e-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="7c13e-171">針對特定的應用程式，選取工作分派類型（[可用]、[必要]、[卸載]）並指派適當的群組。</span><span class="sxs-lookup"><span data-stu-id="7c13e-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="7c13e-172">在 [指派應用程式] 窗格中，選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7c13e-172">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="7c13e-173">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="7c13e-173">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="7c13e-174">在系統管理入口網站中新增和驗證系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="7c13e-174">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="7c13e-175">調整條件式存取</span><span class="sxs-lookup"><span data-stu-id="7c13e-175">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="7c13e-176">指派授權</span><span class="sxs-lookup"><span data-stu-id="7c13e-176">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="7c13e-177">部署 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="7c13e-177">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="7c13e-178">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="7c13e-178">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="7c13e-179">設定裝置</span><span class="sxs-lookup"><span data-stu-id="7c13e-179">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="7c13e-180">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="7c13e-180">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="7c13e-181">部署應用程式（本主題）</span><span class="sxs-lookup"><span data-stu-id="7c13e-181">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
