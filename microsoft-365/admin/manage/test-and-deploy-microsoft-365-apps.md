---
title: 測試及部署整合式應用程式入口網站中的合作夥伴的 Microsoft 365 應用程式
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 針對組織中的使用者和群組，從 Microsoft 365 系統管理中心的整合式應用程式入口網站，尋找、測試及部署 Microsoft 和 Microsoft 合作夥伴應用程式。
ms.openlocfilehash: f806d48e0ed582b1b5c1ee262058ce987125bd99
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488286"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a><span data-ttu-id="cdfe6-103">測試及部署整合式應用程式入口網站中的合作夥伴的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="cdfe6-103">Test and deploy Microsoft 365 Apps by partners in the Integrated apps portal</span></span>

<span data-ttu-id="cdfe6-104">Microsoft 365 系統管理中心可讓您靈活地從單一位置部署單一存放區應用程式、自訂業務線和 Microsoft 365 夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-104">The Microsoft 365 admin center gives you the flexibility to deploy single store apps, custom business line of apps and  Microsoft 365 partner apps from a single location.</span></span> <span data-ttu-id="cdfe6-105">您可以在 Microsoft 系統管理中心 > 設定 > 整合型應用程式中存取位置。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-105">The location can be accessed at Microsoft Admin center > Settings > Integrated apps.</span></span> <span data-ttu-id="cdfe6-106">透過 Microsoft 合作夥伴從整合的應用程式入口網站尋找、測試及完整部署已購買和授權的應用程式，可提供您組織所需的便利性和優點，讓商務服務定期更新並有效地運作。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-106">The ability to find, test, and fully deploy purchased and licensed apps by Microsoft partners from the Integrated apps portal provides the convenience and benefits your organization requires to keep business services updated regularly and running efficiently.</span></span>

<span data-ttu-id="cdfe6-107">如需從組織的合作夥伴購買及授權 Microsoft 365 應用程式的詳細資訊，請參閱 [從 microsoft 365 系統管理中心管理及部署 microsoft 365 應用程式](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-107">For additional information about purchasing and licensing Microsoft 365 apps from partners for your organization, see [Manage and deploy Microsoft 365 Apps from the Microsoft 365 admin center](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).</span></span>

<span data-ttu-id="cdfe6-108">如需合作夥伴如何建立這些應用程式的詳細資訊，請參閱 how [to plan a SaaS plan for the 商業性 marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)</span><span class="sxs-lookup"><span data-stu-id="cdfe6-108">For more info on how partners create these apps, see [How to plan a SaaS offer for the commercial marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)</span></span>

<span data-ttu-id="cdfe6-109">整合式應用程式入口網站只有全域系統管理員才能存取，僅供全球客戶使用。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-109">The Integrated apps portal is only accessible to global admins and available to WorldWide customers only.</span></span> <span data-ttu-id="cdfe6-110">以及主權和政府雲彩不提供此功能。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-110">This feature is not available in sovereign and government clouds.</span></span>

<span data-ttu-id="cdfe6-111">整合式應用程式入口網站會顯示應用程式的清單，其中包含部署組織之協力廠商的單一應用程式和 Microsoft 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-111">The Integrated apps portal displays a list of apps, which includes single apps and Microsoft 365 apps from partners which are deployed your organization.</span></span> <span data-ttu-id="cdfe6-112">只會列出 web 應用程式、SPFx 應用程式、Office 增益集和團隊應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-112">Only web apps, SPFx apps, Office add-ins and Teams apps are listed.</span></span> <span data-ttu-id="cdfe6-113">針對 web 應用程式，我們可以看到2種應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-113">For web apps, we you can see 2 kinds of apps.</span></span>

- <span data-ttu-id="cdfe6-114">SaaS appsource.microsoft.com 中提供的應用程式，並可由系統管理員用來代表組織授與部署。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-114">SaaS apps that are available in appsource.microsoft.com, and can be deployed by admins giving consent on behalf of organization.</span></span>
- <span data-ttu-id="cdfe6-115">使用 office 增益集連結的 SAML 畫廊應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-115">SAML gallery apps that are linked with office add-ins.</span></span>

## <a name="manage-apps-in-the-integrated-apps-portal"></a><span data-ttu-id="cdfe6-116">在整合式應用程式入口網站中管理應用程式</span><span class="sxs-lookup"><span data-stu-id="cdfe6-116">Manage apps in the Integrated apps portal</span></span>

<span data-ttu-id="cdfe6-117">您可以從合作夥伴管理已購買及授權的 Microsoft 365 應用程式的測試和部署。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-117">You can manage testing and deployment of purchased and licensed Microsoft 365 Apps from partners.</span></span>

1. <span data-ttu-id="cdfe6-118">在系統管理中心的左側導覽中，選擇 [ **設定**]，然後選擇 [ **整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-118">In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**.</span></span>

2. <span data-ttu-id="cdfe6-119">選擇 [**可供** 使用的應用程式]**狀態** 的應用程式，以開啟 [**管理**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-119">Choose an app with **Status** of **More apps available** to open the **Manage** pane.</span></span> <span data-ttu-id="cdfe6-120">**可供使用的更多應用程式** 狀態，可讓您知道還有其他尚未部署的 isv 的整合。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-120">The status of **more apps available** lets you know that there are more integrations from the ISVs that aren't yet deployed.</span></span>

3. <span data-ttu-id="cdfe6-121">在 [ **一覽** ] 索引標籤上，選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-121">On the **Overview** tab select **Deploy**.</span></span> <span data-ttu-id="cdfe6-122">某些應用程式會要求您先新增使用者，才能選擇 [部署]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-122">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="cdfe6-123">選取 [  **使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織**]、[ **特定使用者/群組** ] 或 [ **僅自己**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-123">Select  **Users**, choose **Is this a test deployment**, and then choose **Entire organization**, **Specific users/groups** or **Just me**.</span></span> <span data-ttu-id="cdfe6-124">如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-124">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span> <span data-ttu-id="cdfe6-125">特定的使用者或群組可以是 Microsoft 365 群組、安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-125">Specific users or groups can be a Microsoft 365 group, a security group, or a distribution group.</span></span>

5. <span data-ttu-id="cdfe6-126">選取 [ **更新** ]，然後 **完成**。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-126">Select **Update** and then **Done**.</span></span> <span data-ttu-id="cdfe6-127">您現在可以在 [概覽] 索引標籤上選取 [部署]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-127">You can now select Deploy on the Overview tab.</span></span>

6. <span data-ttu-id="cdfe6-128">查看應用程式資訊，然後選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-128">Review the app information, and then select **Deploy**.</span></span>

7. <span data-ttu-id="cdfe6-129">在 [部署已完成] 頁面上，選取 [ **完成** ]，並在 [ **概覽** ] 索引標籤上複查測試或完整部署的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-129">Select **Done** on the Deployment completed page and review the details of the test or full deployment on the **Overview** tab.</span></span>

8. <span data-ttu-id="cdfe6-130">若應用程式狀態為 [ **待處理的更新**]，您可以按一下應用程式以開啟 [管理] 窗格，然後更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-130">If the app has a status of **Update pending**, you can click on the app to open the Manage pane and update the app.</span></span>

## <a name="find-published-apps-for-testing-and-full-deployment"></a><span data-ttu-id="cdfe6-131">尋找已發佈的應用程式進行測試和完整部署</span><span class="sxs-lookup"><span data-stu-id="cdfe6-131">Find published apps for testing and full deployment</span></span>

<span data-ttu-id="cdfe6-132">您可以在 [整合式應用程式] 頁面上，找出未出現在清單中的已發佈應用程式，並加以測試及完全部署。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-132">You can find, test, and fully deploy published apps that don't already appear in the list on the Integrated apps page.</span></span> <span data-ttu-id="cdfe6-133">透過從系統管理中心購買及授權應用程式，您可以從單一位置將 Microsoft 和 Microsoft 合作夥伴應用程式新增至您的清單。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-133">By purchasing and licensing the apps from the admin center, you can add Microsoft and Microsoft partner apps to your list from a single location.</span></span>

1. <span data-ttu-id="cdfe6-134">在系統管理中心的左側導覽中，選擇 [ **設定**]，然後選擇 [ **整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-134">In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**.</span></span>

2. <span data-ttu-id="cdfe6-135">選取 [ **取得應用** 程式] 以取得應用程式的視圖。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-135">Select **Get apps** to get a view of the apps.</span></span>

3. <span data-ttu-id="cdfe6-136">在 [ **Microsoft 365 應用程式** 發佈的應用程式] 頁面上，選擇您想要部署的應用程式，請選擇 [ **立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-136">On the **Microsoft 365 Apps** published apps page, select the app you want to deploy by choosing **Get it now**.</span></span> <span data-ttu-id="cdfe6-137">顯示的應用程式主要是以 SharePoint 架構技術) 為基礎的 Word、PowerPoint、Excel、Outlook 增益集、小組應用程式和 SharePoint 應用程式 (。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-137">The apps displayed primarily are Word, PowerPoint, Excel, Outlook add-ins, Teams app and SharePoint apps (built on SharePoint Framework technology).</span></span> <span data-ttu-id="cdfe6-138">接受許可權，然後選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-138">Accept the permissions and select **Continue**.</span></span>

5. <span data-ttu-id="cdfe6-139">在頁面頂端的頁面上，選取 [ **部署** ] 參照為等待部署的郵件。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-139">Select **Deploy** at the top of the page next to the message that refers to waiting to be deployed.</span></span>

    <span data-ttu-id="cdfe6-140">如果選取的應用程式連結到 ISV 所提供的 SaaS，則 [設定] 頁面上會出現屬於此連結提供之部分的所有其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-140">If the app selected is linked to a SaaS offer by an ISV, all the other apps that are part of this linked offer will appear on the Configuration page.</span></span> <span data-ttu-id="cdfe6-141">如果您選擇部署所有應用程式，請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-141">If you choose to deploy of all of the apps, select **Next**.</span></span> <span data-ttu-id="cdfe6-142">否則，請選取 [ **編輯**]，然後選擇您要部署的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-142">Otherwise, select **Edit**, and choose which apps you want deployed.</span></span> <span data-ttu-id="cdfe6-143">某些應用程式會要求您先新增使用者，才能選擇 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-143">Some apps require you to add users before you can select **Deploy**.</span></span>

6. <span data-ttu-id="cdfe6-144">選取 [ **新增使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組** ] 或 [ **僅自己**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-144">Select **Add users**, choose **Is this a test deployment**, and then choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="cdfe6-145">特定使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-145">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="cdfe6-146">如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-146">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span>

7. <span data-ttu-id="cdfe6-147">選取 **[下一步]** 進入 [ **接受許可權要求** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-147">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="cdfe6-148">列出每個應用程式的應用程式功能和許可權。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-148">The app capabilities and permissions of each of the apps are listed.</span></span> <span data-ttu-id="cdfe6-149">若應用程式需要同意，請選取 [ **接受許可權**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-149">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="cdfe6-150">只有全域系統管理員可以授與同意。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-150">Only a global administrator can give consent.</span></span>

8. <span data-ttu-id="cdfe6-151">選取 **[下一步** ] 複查部署，然後選擇 **[完成部署]**。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-151">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="cdfe6-152">您可以選擇 [**查看此部署**]，從 [**一覽**] 索引標籤中查看部署。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-152">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span> <span data-ttu-id="cdfe6-153">在 Microsoft 365 系統管理中心中，您可以看到每個已部署應用程式的狀態，以及您部署應用程式的日期。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-153">In the Microsoft 365 admin center, you can see the status of each deployed app and the date you deployed the app.</span></span>

> [!NOTE]
> <span data-ttu-id="cdfe6-154">若應用程式先前部署自整合的應用程式入口網站，則 **部署類型** 是 **自訂的。**</span><span class="sxs-lookup"><span data-stu-id="cdfe6-154">If an app was previously deployed from somewhere other than the Integrated Apps portal, the **Deployment Type** is **Custom.**</span></span>

## <a name="unsupported-scenarios"></a><span data-ttu-id="cdfe6-155">不支援的案例</span><span class="sxs-lookup"><span data-stu-id="cdfe6-155">Unsupported scenarios</span></span>

<span data-ttu-id="cdfe6-156">在下列情況下，您將無法從整合式應用程式入口網站中的合作夥伴部署單一 store 應用程式或 Microsoft 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-156">You won't be able to deploy a single store app or Microsoft 365 Apps by partner from Integrated apps portal for the following scenarios.</span></span>

- <span data-ttu-id="cdfe6-157">同一個增益集會連結至多個 SaaS 提供。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-157">The same add-in is linked to more than one SaaS offer.</span></span>
- <span data-ttu-id="cdfe6-158">SaaS 提供會連結至增益集，但不會與 Microsoft Graph 整合，也不會提供任何 AAD 應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-158">The SaaS offer is linked to add-ins, but it does not integrate with Microsoft Graph and no AAD App ID is provided.</span></span>
- <span data-ttu-id="cdfe6-159">SaaS 提供會連結至增益集，但是提供給 Microsoft Graph 整合的 AAD 應用程式識別碼是跨多個 SaaS 提供共用的。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-159">The SaaS offer is linked to add-ins, but AAD App ID provided for Microsoft Graph integration is shared across multiple SaaS offers.</span></span>

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a><span data-ttu-id="cdfe6-160">上傳自訂的商務應用程式，以進行測試及完整部署</span><span class="sxs-lookup"><span data-stu-id="cdfe6-160">Upload custom line of business apps for testing and full deployment</span></span>

1. <span data-ttu-id="cdfe6-161">在系統管理中心的左側導覽中，選擇 [ **設定** ]，然後選擇 [ **整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-161">In the admin center, in the left nav, choose **Settings** and then **Integrated apps**.</span></span>

2. <span data-ttu-id="cdfe6-162">選取 **[上傳自訂應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-162">Select **Upload custom apps**.</span></span> <span data-ttu-id="cdfe6-163">只支援自訂行的應用程式（適用于 Word、PowerPoint、Excel 和 Outlook）。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-163">Only a custom line of apps for Word, PowerPoint, Excel and Outlook  is supported.</span></span>

3. <span data-ttu-id="cdfe6-164">上傳裝置中的資訊清單檔案，或加入 URL 連結。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-164">Upload the manifest file from your device or add a URL link.</span></span> <span data-ttu-id="cdfe6-165">某些應用程式會要求您先新增使用者，才能選擇 [部署]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-165">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="cdfe6-166">選取 [ **新增使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組** ] 或 [ **僅自己**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-166">Select **Add users**, choose **Is this a test Deployment**, and choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="cdfe6-167">特定使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-167">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="cdfe6-168">如果您想要等待將應用程式部署到整個組織，您也可以選擇 [ **測試部署** ]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-168">You can also choose **Test deployment** if you want to wait to deploy the app to the entire organization.</span></span>

5. <span data-ttu-id="cdfe6-169">選取 **[下一步]** 進入 [ **接受許可權要求** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-169">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="cdfe6-170">列出應用程式的應用程式功能和許可權。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-170">The app capabilities and permissions of the apps are listed.</span></span> <span data-ttu-id="cdfe6-171">若應用程式需要同意，請選取 [ **接受許可權**]。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-171">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="cdfe6-172">只有全域系統管理員可以授與同意。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-172">Only a global administrator can give consent.</span></span>

6. <span data-ttu-id="cdfe6-173">選取 **[下一步** ] 複查部署，然後選擇 **[完成部署]**。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-173">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="cdfe6-174">您可以選擇 [**查看此部署**]，從 [**一覽**] 索引標籤中查看部署。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-174">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="cdfe6-175">常見問題集</span><span class="sxs-lookup"><span data-stu-id="cdfe6-175">Frequently asked questions</span></span>

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a><span data-ttu-id="cdfe6-176">我需要哪些系統管理員角色才能存取整合式應用程式？</span><span class="sxs-lookup"><span data-stu-id="cdfe6-176">Which administrator role do I need to access Integrated apps?</span></span>

<span data-ttu-id="cdfe6-177">只有全域管理員才能存取整合式應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-177">Only global administrators can access Integrated Apps.</span></span> <span data-ttu-id="cdfe6-178">在其他系統管理員的左側導覽中，整合式應用程式不會顯示。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-178">Integrated apps won't show up in the left nav for other administrators.</span></span>

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a><span data-ttu-id="cdfe6-179">為什麼我會在左導覽的 [設定] 底下看到增益集，但不是集成應用程式？</span><span class="sxs-lookup"><span data-stu-id="cdfe6-179">Why do I see Add-in in the left nav under Setting but not Integrated apps?</span></span>

<span data-ttu-id="cdfe6-180">原因如下：</span><span class="sxs-lookup"><span data-stu-id="cdfe6-180">There could be a few reasons:</span></span>

- <span data-ttu-id="cdfe6-181">登入的系統管理員是 Exchange admininstrator。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-181">The logged in administrator is an Exchange admininstrator.</span></span>
- <span data-ttu-id="cdfe6-182">客戶位於以及主權雲端，但整合型應用程式體驗可供以及主權雲端客戶使用。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-182">The customer is in sovereign cloud and Integrated apps experience is available to sovereign cloud customers yet.</span></span>

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a><span data-ttu-id="cdfe6-183">我可以從整合式應用程式部署哪些應用程式？</span><span class="sxs-lookup"><span data-stu-id="cdfe6-183">What apps can I deploy from Integrated apps?</span></span>

<span data-ttu-id="cdfe6-184">整合式應用程式允許部署 Web 應用程式、小組應用程式、Excel、PowerPoint、Word、Outlook 增益集及 SPFx 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-184">Integrated apps allows deployment of Web Apps, Teams app, Excel, PowerPoint, Word, Outlook add-ins, and SPFx apps.</span></span> <span data-ttu-id="cdfe6-185">針對增益集，整合式應用程式支援部署 Exchange online 信箱，而非內部部署 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-185">For add-ins, Integrated apps supports deployment to Exchange online mailboxes and not on-premises Exchange mailboxes.</span></span>

### <a name="can-administrators-delete-or-remove-apps"></a><span data-ttu-id="cdfe6-186">管理員可以刪除或移除應用程式嗎？</span><span class="sxs-lookup"><span data-stu-id="cdfe6-186">Can administrators delete or remove apps?</span></span>

<span data-ttu-id="cdfe6-187">是。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-187">Yes.</span></span> <span data-ttu-id="cdfe6-188">全域管理員可以刪除或移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-188">Global administrators can delete or remove apps.</span></span>

- <span data-ttu-id="cdfe6-189">從清單視圖中選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-189">Select an app from the list view.</span></span> <span data-ttu-id="cdfe6-190">**在 [設定**] 索引標籤上，選取要移除的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-190">On the **Configuration** tab, select which apps to remove.</span></span>  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a><span data-ttu-id="cdfe6-191">以及主權雲端中是否有整合式應用程式？</span><span class="sxs-lookup"><span data-stu-id="cdfe6-191">Is Integrated apps available in sovereign cloud?</span></span>

<span data-ttu-id="cdfe6-192">否。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-192">No.</span></span> <span data-ttu-id="cdfe6-193">無法以及主權 cloud 客戶的整合式應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-193">Integrated apps aren't available to sovereign cloud customers.</span></span>

### <a name="is-integrated-apps-available-in-government-clouds"></a><span data-ttu-id="cdfe6-194">政府雲端中是否有整合式應用程式？</span><span class="sxs-lookup"><span data-stu-id="cdfe6-194">Is Integrated apps available in government clouds?</span></span>

<span data-ttu-id="cdfe6-195">否。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-195">No.</span></span> <span data-ttu-id="cdfe6-196">政府雲端客戶無法使用整合式應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdfe6-196">Integrated apps aren't available to government cloud customers.</span></span>
