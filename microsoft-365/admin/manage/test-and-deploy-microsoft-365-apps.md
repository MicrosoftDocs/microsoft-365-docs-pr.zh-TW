---
title: 在整合式應用程式入口網站中測試及部署合作夥伴的 Microsoft 365 Apps
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
description: 針對組織中的使用者和群組，從 Microsoft 365 系統管理中心中的整合式應用程式入口網站，尋找、測試及部署 microsoft 和 microsoft 合作夥伴應用程式。
ms.openlocfilehash: dcd4a91d9e43c0a740094615cd3dca0b0e8bc0f6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007054"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a><span data-ttu-id="7ffe5-103">在整合式應用程式入口網站中測試及部署合作夥伴的 Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="7ffe5-103">Test and deploy Microsoft 365 Apps by partners in the Integrated apps portal</span></span>

<span data-ttu-id="7ffe5-104">Microsoft 365 系統管理中心可讓您靈活地從單一位置部署單一 store 應用程式、自訂業務線和 Microsoft 365 夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-104">The Microsoft 365 admin center gives you the flexibility to deploy single store apps, custom business line of apps and  Microsoft 365 partner apps from a single location.</span></span> <span data-ttu-id="7ffe5-105">在整合式應用程式中，可以存取 Microsoft 系統管理中心設定中的位置。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-105">The location can be accessed in the Microsoft Admin center settings, in Integrated apps.</span></span> <span data-ttu-id="7ffe5-106">透過 Microsoft 合作夥伴從整合的應用程式入口網站尋找、測試及完整部署已購買和授權的應用程式，可提供您組織所需的便利性和優點，讓商務服務定期更新並有效地運作。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-106">The ability to find, test, and fully deploy purchased and licensed apps by Microsoft partners from the Integrated apps portal provides the convenience and benefits your organization requires to keep business services updated regularly and running efficiently.</span></span>

<span data-ttu-id="7ffe5-107">如需購買及授權 Microsoft 365 來自組織之合作夥伴的應用程式的詳細資訊，請參閱[從 Microsoft 365 系統管理中心管理及部署 Microsoft 365 Apps](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-107">For additional information about purchasing and licensing Microsoft 365 apps from partners for your organization, see [Manage and deploy Microsoft 365 Apps from the Microsoft 365 admin center](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).</span></span>

<span data-ttu-id="7ffe5-108">如需合作夥伴如何建立這些應用程式的詳細資訊，請參閱 how [to plan a SaaS plan for the 商業性 marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)</span><span class="sxs-lookup"><span data-stu-id="7ffe5-108">For more info on how partners create these apps, see [How to plan a SaaS offer for the commercial marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)</span></span>

<span data-ttu-id="7ffe5-109">整合式應用程式入口網站只有全域系統管理員才能存取，而且只能供全球客戶使用。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-109">The Integrated apps portal is only accessible to global admins and available to world-wide customers only.</span></span> <span data-ttu-id="7ffe5-110">以及主權和政府雲彩不提供此功能。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-110">This feature is not available in sovereign and government clouds.</span></span>

<span data-ttu-id="7ffe5-111">整合式應用程式入口網站會顯示應用程式的清單，其中包含部署組織之協力廠商的單一應用程式和 Microsoft 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-111">The Integrated apps portal displays a list of apps, which includes single apps and Microsoft 365 apps from partners which are deployed your organization.</span></span> <span data-ttu-id="7ffe5-112">只會列出 web 應用程式、SPFx 應用程式 Office 增益集及 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-112">Only web apps, SPFx apps, Office add-ins and Teams apps are listed.</span></span> <span data-ttu-id="7ffe5-113">若為 web 應用程式，您可以看到兩種類型的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-113">For web apps, you can see two kinds of apps.</span></span>

- <span data-ttu-id="7ffe5-114">SaaS appsource.microsoft.com 中提供的應用程式，並可由系統管理員用來代表組織授與部署。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-114">SaaS apps that are available in appsource.microsoft.com, and can be deployed by admins giving consent on behalf of the organization.</span></span>
- <span data-ttu-id="7ffe5-115">使用 office 增益集連結的 SAML 畫廊應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-115">SAML gallery apps that are linked with office add-ins.</span></span>

## <a name="manage-apps-in-the-integrated-apps-portal"></a><span data-ttu-id="7ffe5-116">在整合式應用程式入口網站中管理應用程式</span><span class="sxs-lookup"><span data-stu-id="7ffe5-116">Manage apps in the Integrated apps portal</span></span>

<span data-ttu-id="7ffe5-117">您可以管理從夥伴購買及授權的 Microsoft 365 Apps 的測試和部署。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-117">You can manage testing and deployment of purchased and licensed Microsoft 365 Apps from partners.</span></span>

1. <span data-ttu-id="7ffe5-118">在系統管理中心中，選取 [**設定**]，然後選取 [**整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-118">In the admin center, select **Settings**, and then select **Integrated apps**.</span></span>

2. <span data-ttu-id="7ffe5-119">選擇 [**可供** 使用的應用程式]**狀態** 的應用程式，以開啟 [**管理**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-119">Choose an app with **Status** of **More apps available** to open the **Manage** pane.</span></span> <span data-ttu-id="7ffe5-120">**可供使用的更多應用程式** 狀態，可讓您知道還有其他尚未部署的 isv 的整合。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-120">The status of **more apps available** lets you know that there are more integrations from the ISVs that aren't yet deployed.</span></span>

3. <span data-ttu-id="7ffe5-121">在 [ **概覽** ] 索引標籤上，選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-121">On the **Overview** tab, select **Deploy**.</span></span> <span data-ttu-id="7ffe5-122">某些應用程式會要求您先新增使用者，才能選擇 [部署]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-122">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="7ffe5-123">選取 [  **使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織**]、[ **特定使用者/群組** ] 或 [ **僅自己**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-123">Select  **Users**, choose **Is this a test deployment**, and then choose **Entire organization**, **Specific users/groups** or **Just me**.</span></span> <span data-ttu-id="7ffe5-124">如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-124">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span> <span data-ttu-id="7ffe5-125">特定的使用者或群組可以是 Microsoft 365 群組、安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-125">Specific users or groups can be a Microsoft 365 group, a security group, or a distribution group.</span></span>

5. <span data-ttu-id="7ffe5-126">選取 [ **更新** ]，然後 **完成**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-126">Select **Update** and then **Done**.</span></span> <span data-ttu-id="7ffe5-127">您現在可以在 [概覽] 索引標籤上選取 [部署]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-127">You can now select Deploy on the Overview tab.</span></span>

6. <span data-ttu-id="7ffe5-128">查看應用程式資訊，然後選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-128">Review the app information, and then select **Deploy**.</span></span>

7. <span data-ttu-id="7ffe5-129">在 [部署已完成] 頁面上，選取 [ **完成** ]，並在 [ **概覽** ] 索引標籤上複查測試或完整部署的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-129">Select **Done** on the Deployment completed page and review the details of the test or full deployment on the **Overview** tab.</span></span>

8. <span data-ttu-id="7ffe5-130">若應用程式狀態為 [ **待處理的更新**]，您可以按一下應用程式以開啟 [管理] 窗格，然後更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-130">If the app has a status of **Update pending**, you can click on the app to open the Manage pane and update the app.</span></span>

## <a name="find-published-apps-for-testing-and-full-deployment"></a><span data-ttu-id="7ffe5-131">尋找已發佈的應用程式進行測試和完整部署</span><span class="sxs-lookup"><span data-stu-id="7ffe5-131">Find published apps for testing and full deployment</span></span>

<span data-ttu-id="7ffe5-132">您可以在 [整合式應用程式] 頁面上，找出未出現在清單中的已發佈應用程式，並加以測試及完全部署。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-132">You can find, test, and fully deploy published apps that don't already appear in the list on the Integrated apps page.</span></span> <span data-ttu-id="7ffe5-133">透過從系統管理中心購買及授權應用程式，您可以從單一位置將 Microsoft 和 Microsoft 合作夥伴應用程式新增至您的清單。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-133">By purchasing and licensing the apps from the admin center, you can add Microsoft and Microsoft partner apps to your list from a single location.</span></span>

1. <span data-ttu-id="7ffe5-134">在系統管理中心的左側導覽中，選擇 [**設定**]，然後選擇 [**整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-134">In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**.</span></span>

2. <span data-ttu-id="7ffe5-135">選取 [ **取得應用** 程式] 以取得應用程式的視圖。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-135">Select **Get apps** to get a view of the apps.</span></span>

3. <span data-ttu-id="7ffe5-136">在 [ **Microsoft 365 Apps** 發佈的應用程式] 頁面上，選擇您要部署的應用程式，方法是選擇 [**立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-136">On the **Microsoft 365 Apps** published apps page, select the app you want to deploy by choosing **Get it now**.</span></span> <span data-ttu-id="7ffe5-137">顯示的應用程式主要是 Word、PowerPoint、Excel、Outlook 增益集、Teams 應用程式，以及以 SharePoint 技術 (建立 SharePoint 架構應用程式) 。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-137">The apps displayed primarily are Word, PowerPoint, Excel, Outlook add-ins, Teams app and SharePoint apps (built on SharePoint Framework technology).</span></span> <span data-ttu-id="7ffe5-138">接受許可權，然後選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-138">Accept the permissions and select **Continue**.</span></span>

5. <span data-ttu-id="7ffe5-139">在頁面頂端的頁面上，選取 [ **部署** ] 參照為等待部署的郵件。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-139">Select **Deploy** at the top of the page next to the message that refers to waiting to be deployed.</span></span>

    <span data-ttu-id="7ffe5-140">如果選取的應用程式連結到 ISV 所提供的 SaaS，則 [設定] 頁面上會出現屬於此連結提供之部分的所有其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-140">If the app selected is linked to a SaaS offer by an ISV, all the other apps that are part of this linked offer will appear on the Configuration page.</span></span> <span data-ttu-id="7ffe5-141">如果您選擇部署所有應用程式，請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-141">If you choose to deploy of all of the apps, select **Next**.</span></span> <span data-ttu-id="7ffe5-142">否則，請選取 [ **編輯**]，然後選擇您要部署的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-142">Otherwise, select **Edit**, and choose which apps you want deployed.</span></span> <span data-ttu-id="7ffe5-143">某些應用程式會要求您先新增使用者，才能選擇 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-143">Some apps require you to add users before you can select **Deploy**.</span></span>

6. <span data-ttu-id="7ffe5-144">選取 [ **新增使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組** ] 或 [ **僅自己**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-144">Select **Add users**, choose **Is this a test deployment**, and then choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="7ffe5-145">特定的使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-145">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="7ffe5-146">如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-146">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span>

7. <span data-ttu-id="7ffe5-147">選取 **[下一步]** 進入 [ **接受許可權要求** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-147">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="7ffe5-148">列出每個應用程式的應用程式功能和許可權。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-148">The app capabilities and permissions of each of the apps are listed.</span></span> <span data-ttu-id="7ffe5-149">若應用程式需要同意，請選取 [ **接受許可權**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-149">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="7ffe5-150">只有全域系統管理員可以授與同意。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-150">Only a global administrator can give consent.</span></span>

8. <span data-ttu-id="7ffe5-151">選取 **[下一步** ] 複查部署，然後選擇 **[完成部署]**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-151">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="7ffe5-152">您可以選擇 [**查看此部署**]，從 [**一覽**] 索引標籤中查看部署。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-152">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span> <span data-ttu-id="7ffe5-153">在 Microsoft 365 系統管理中心中，您可以看到每個已部署應用程式的狀態，以及您部署應用程式的日期。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-153">In the Microsoft 365 admin center, you can see the status of each deployed app and the date you deployed the app.</span></span>

> [!NOTE]
> <span data-ttu-id="7ffe5-154">若應用程式先前部署自整合的應用程式入口網站，則 **部署類型** 是 **自訂的。**</span><span class="sxs-lookup"><span data-stu-id="7ffe5-154">If an app was previously deployed from somewhere other than the Integrated Apps portal, the **Deployment Type** is **Custom.**</span></span>

## <a name="unsupported-scenarios"></a><span data-ttu-id="7ffe5-155">不支持的案例</span><span class="sxs-lookup"><span data-stu-id="7ffe5-155">Unsupported scenarios</span></span>

<span data-ttu-id="7ffe5-156">在下列情況下，您將無法從整合型應用程式入口網站部署單一 store 應用程式或 Microsoft 365 Apps。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-156">You won't be able to deploy a single store app or Microsoft 365 Apps by partner from Integrated apps portal for the following scenarios.</span></span>

- <span data-ttu-id="7ffe5-157">同一個增益集會連結至多個 SaaS 提供。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-157">The same add-in is linked to more than one SaaS offer.</span></span>
- <span data-ttu-id="7ffe5-158">SaaS 提供會連結至增益集，但不會與 Microsoft Graph 整合，也不會提供任何 AAD 應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-158">The SaaS offer is linked to add-ins, but it does not integrate with Microsoft Graph and no AAD App ID is provided.</span></span>
- <span data-ttu-id="7ffe5-159">SaaS 提供會連結至增益集，但是為 Microsoft Graph 整合所提供的 AAD 應用程式識別碼，可跨多個 SaaS 提供共用。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-159">The SaaS offer is linked to add-ins, but AAD App ID provided for Microsoft Graph integration is shared across multiple SaaS offers.</span></span>

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a><span data-ttu-id="7ffe5-160">Upload 自訂的企業營運應用程式，以進行測試及完整部署</span><span class="sxs-lookup"><span data-stu-id="7ffe5-160">Upload custom line-of-business apps for testing and full deployment</span></span>

1. <span data-ttu-id="7ffe5-161">在系統管理中心的左側導覽中，選擇 [**設定**]，然後選擇 [**整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-161">In the admin center, in the left nav, choose **Settings** and then **Integrated apps**.</span></span>

2. <span data-ttu-id="7ffe5-162">選取 [ **Upload 自訂應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-162">Select **Upload custom apps**.</span></span> <span data-ttu-id="7ffe5-163">只支援自訂行的應用程式（適用于 Word、PowerPoint Excel 和 Outlook）。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-163">Only a custom line of apps for Word, PowerPoint, Excel and Outlook  is supported.</span></span>

3. <span data-ttu-id="7ffe5-164">從您的裝置 Upload 資訊清單檔案，或加入 URL 連結。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-164">Upload the manifest file from your device or add a URL link.</span></span> <span data-ttu-id="7ffe5-165">某些應用程式會要求您先新增使用者，才能選擇 [部署]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-165">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="7ffe5-166">選取 [ **新增使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組** ] 或 [ **僅自己**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-166">Select **Add users**, choose **Is this a test Deployment**, and choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="7ffe5-167">特定的使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-167">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="7ffe5-168">如果您想要等待將應用程式部署到整個組織，您也可以選擇 [ **測試部署** ]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-168">You can also choose **Test deployment** if you want to wait to deploy the app to the entire organization.</span></span>

5. <span data-ttu-id="7ffe5-169">選取 **[下一步]** 進入 [ **接受許可權要求** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-169">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="7ffe5-170">列出應用程式的應用程式功能和許可權。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-170">The app capabilities and permissions of the apps are listed.</span></span> <span data-ttu-id="7ffe5-171">若應用程式需要同意，請選取 [ **接受許可權**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-171">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="7ffe5-172">只有全域系統管理員可以授與同意。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-172">Only a global administrator can give consent.</span></span>

6. <span data-ttu-id="7ffe5-173">選取 **[下一步** ] 複查部署，然後選擇 **[完成部署]**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-173">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="7ffe5-174">您可以選擇 [**查看此部署**]，從 [**一覽**] 索引標籤中查看部署。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-174">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span>

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a><span data-ttu-id="7ffe5-175">準備在整合式應用程式中部署增益集</span><span class="sxs-lookup"><span data-stu-id="7ffe5-175">Prepare to deploy add-ins in Integrated apps</span></span>

<span data-ttu-id="7ffe5-176">Office 增益集可協助您個人化檔，並簡化存取網頁上資訊的方式 (請參閱開始使用 Office 增益集) 。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-176">Office add-ins help you personalize your documents and streamline the way you access information on the web (see Start using your Office Add-in).</span></span> 

<span data-ttu-id="7ffe5-177">增益集提供下列優點：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-177">Add-ins provides the following benefits:</span></span> 

- <span data-ttu-id="7ffe5-178">當相關的 Office 應用程式啟動時，增益集就會自動下載。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-178">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="7ffe5-179">如果增益集支援增益集命令，增益集會自動出現在 Office 應用程式中的功能區。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-179">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span> 

- <span data-ttu-id="7ffe5-180">如果系統管理員關閉或刪除增益集，或從 Azure Active Directory 或將增益集指派給的群組中移除使用者，則使用者不再出現增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-180">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span> 

<span data-ttu-id="7ffe5-181">在三個桌面平臺 Windows，Mac 和線上 Office 應用程式都支援增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-181">Add-ins are supported in three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="7ffe5-182">iOS 和 Android (Outlook 僅限行動增益集) ，也支援此功能。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-182">It is also supported in iOS and Android (Outlook Mobile Add-ins Only).</span></span> 

<span data-ttu-id="7ffe5-183">增益集最多可能需要24小時才能顯示所有使用者的用戶端。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-183">It can take up to 24 hours for an add-in to show up for client for all users.</span></span> 

<span data-ttu-id="7ffe5-184">目前 Exchange 系統管理員和全域系統管理員都可以從整合式應用程式部署增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-184">Today both Exchange Admins and Global Admins can deploy add-ins from Integrated apps.</span></span>   

### <a name="before-you-begin"></a><span data-ttu-id="7ffe5-185">開始之前</span><span class="sxs-lookup"><span data-stu-id="7ffe5-185">Before you begin</span></span>

<span data-ttu-id="7ffe5-186">部署增益集需要使用者使用 Microsoft 365 企業版授權 (E3/E5/F3) 或 Microsoft 365 商務授權 (business Basic、business Standard、business 進階版) 。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-186">Deployment of add-ins requires that the users are using Microsoft 365 Enterprise licenses (E3/E5/F3) or Microsoft 365 Business licenses (Business Basic, Business Standard, Business Premium).</span></span> <span data-ttu-id="7ffe5-187">使用者也需要使用其組織識別碼登入 Office) 並擁有 Exchange Online 和使用中 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-187">The users also need to be signed into Office using their organizational ID) and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="7ffe5-188">您的訂閱目錄必須是 in 或同盟 to Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-188">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span> 

<span data-ttu-id="7ffe5-189">部署不支援下列各項：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-189">Deployment doesn't support the following:</span></span> 

- <span data-ttu-id="7ffe5-190">目標鎖定為 Office 2013 中的 Word、Excel 或 PowerPoint 的增益集</span><span class="sxs-lookup"><span data-stu-id="7ffe5-190">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="7ffe5-191">內部部署目錄服務</span><span class="sxs-lookup"><span data-stu-id="7ffe5-191">An on-premises directory service</span></span> 
- <span data-ttu-id="7ffe5-192">增益集部署至 Exchange 部署信箱</span><span class="sxs-lookup"><span data-stu-id="7ffe5-192">Add-in Deployment to an Exchange On-prem Mailbox</span></span> 
- <span data-ttu-id="7ffe5-193"> (COM) 或 Visual Studio Tools for Office (VSTO) 增益集的元件物件模型部署。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-193">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span> 
- <span data-ttu-id="7ffe5-194">不包含 Exchange Online 的 Microsoft 365 部署，例如 Microsoft 365 Apps 的商務及 Microsoft 365 Apps Enterprise。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-194">Deployments of Microsoft 365 that do not include Exchange Online such as Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>  

### <a name="office-requirements"></a><span data-ttu-id="7ffe5-195">Office要求</span><span class="sxs-lookup"><span data-stu-id="7ffe5-195">Office Requirements</span></span> 

<span data-ttu-id="7ffe5-196">若為 Word、Excel 及 PowerPoint 增益集，您的使用者必須使用下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-196">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span> 
- <span data-ttu-id="7ffe5-197">在 Windows 裝置上，Microsoft 365 企業版授權的版本1704或更新版本 (E3/E5/F3) 或 Microsoft 365 商務授權 (business Basic、business Standard、business 進階版) 。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-197">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise licenses (E3/E5/F3) or Microsoft 365 Business licenses (Business Basic, Business Standard, Business Premium).</span></span> 
- <span data-ttu-id="7ffe5-198">在 Mac 上，版本15.34 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-198">On a Mac, Version 15.34 or later.</span></span> 

<span data-ttu-id="7ffe5-199">若為 Outlook，您的使用者必須使用下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-199">For Outlook, your users must be using one of the following:</span></span> 
- <span data-ttu-id="7ffe5-200">版本1701或更新版本的 Microsoft 365 企業版授權 (E3/E5/F3) 或 Microsoft 365 商務授權 (business Basic、business Standard、business 進階版) 。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-200">Version 1701 or later of Microsoft 365 Enterprise licenses (E3/E5/F3) or Microsoft 365 Business licenses (Business Basic, Business Standard, Business Premium).</span></span> 
- <span data-ttu-id="7ffe5-201">Office Professional Plus 2019 或 Office Standard 2019 的版本1808或更新版本。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-201">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span> 
- <span data-ttu-id="7ffe5-202">16.0.4494.1000 或更新版本的 Office Professional Plus 2016 (MSI) 或 Office Standard 2016 (MSI) 。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-202">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI).</span></span>
    > [!NOTE]
    > <span data-ttu-id="7ffe5-203">MSI 版本的 Outlook 會在適當的 Outlook 功能區中顯示系統管理員安裝的增益集，而不是「我的增益集」一節。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-203">MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>  
- <span data-ttu-id="7ffe5-204">15.0.4937.1000 或更新版本的 Office Professional Plus 2013 (MSI) 或 Office Standard 2013 (MSI) 。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-204">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI).</span></span>
- <span data-ttu-id="7ffe5-205">適用于 Mac 的 Office 2016 版本16.0.9318.1000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-205">Version 16.0.9318.1000 or later of Office 2016 for Mac.</span></span> 
- <span data-ttu-id="7ffe5-206">2.75.0 或更新版本的 Outlook mobile for iOS。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-206">Version 2.75.0 or later of Outlook mobile for iOS.</span></span> 
- <span data-ttu-id="7ffe5-207">2.2.145 或更新版本的 Outlook mobile for Android。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-207">Version 2.2.145 or later of Outlook mobile for Android.</span></span> 



### <a name="exchange-online-requirements"></a><span data-ttu-id="7ffe5-208">Exchange Online 需求</span><span class="sxs-lookup"><span data-stu-id="7ffe5-208">Exchange Online requirements</span></span> 
<span data-ttu-id="7ffe5-209">Microsoft Exchange 會將增益集資訊清單儲存在貴組織的租用戶中。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-209">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="7ffe5-210">部署增益集的系統管理員和接收這些增益集的使用者，必須位於支援 OAuth 驗證的 Exchange Online 版本上。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-210">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span> 

<span data-ttu-id="7ffe5-211">請洽詢貴組織的 Exchange 系統管理員，確認現正使用的設定。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-211">Check with your organization's Exchange admin to find out which configuration is in use.</span></span> <span data-ttu-id="7ffe5-212">您可以使用 [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity)PowerShell Cmdlet 來驗證每個使用者的 OAuth 連線能力   。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-212">OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span> 

### <a name="user-and-group-assignments"></a><span data-ttu-id="7ffe5-213">使用者和群組指派</span><span class="sxs-lookup"><span data-stu-id="7ffe5-213">User and group assignments</span></span>
<span data-ttu-id="7ffe5-214">目前支援將增益集部署至大多數 Azure Active Directory 支援的群組，包括 Microsoft 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-214">The deployment of add-in is currently supported to the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span> <span data-ttu-id="7ffe5-215">部署支援最上層群組或沒有父項群組的群組中的使用者，但不支援具有父項群組的嵌套群組或群組中的使用者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-215">Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="7ffe5-216">目前不支援未啟用郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-216">Non-mail enabled security groups are not currently supported.</span></span> 

<span data-ttu-id="7ffe5-217">在下列範例中，會將 Sandra、Sheila 及銷售部門群組指派給增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-217">In the following example, Sandra, Sheila, and the Sales Department group are assigned to an add-in.</span></span> <span data-ttu-id="7ffe5-218">由於西岸銷售部門是巢狀群組，誠雄和又倫未被指派增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-218">Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span> 

![銷售部門圖表](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="7ffe5-220">確認群組是否包含巢狀群組</span><span class="sxs-lookup"><span data-stu-id="7ffe5-220">Find out if a group contains nested groups</span></span>

<span data-ttu-id="7ffe5-221">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span><span class="sxs-lookup"><span data-stu-id="7ffe5-221">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="7ffe5-222">如果您在電子郵件的 [ **至**] 欄位中輸入組名，   然後在解析時選取組名，它會顯示其是否包含使用者或嵌套的群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-222">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="7ffe5-223">在下列範例中，測試群組的 Outlook 連絡人卡片的 [ **成員**] 索引標籤   不會顯示任何使用者，而且只會顯示兩個子群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-223">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 

![Outlook 連絡人卡片的 [成員] 索引標籤](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

<span data-ttu-id="7ffe5-225">You can do the opposite query by resolving the group to see if it's a member of any group.</span><span class="sxs-lookup"><span data-stu-id="7ffe5-225">You can do the opposite query by resolving the group to see if it's a member of any group.</span></span> <span data-ttu-id="7ffe5-226">在下列範例中，您可以在 Outlook 連絡人卡片的 [ <b>成員資格</b>] 索引標籤上看到，   子群組1是 Test group 的成員。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-226">In the example below, you can see under the <b>Membership</b> tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 

![Outlook 連絡人卡片的 [成員資格] 索引標籤](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

<span data-ttu-id="7ffe5-228">請注意，您可以使用 Azure Active Directory Graph API 來執行查詢，以找出群組中群組的清單。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-228">Note that you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group.</span></span> <span data-ttu-id="7ffe5-229">如需詳細資訊，請參閱 [群組上的 Operations |圖形 API 參照](/previous-versions/azure/ad/graph/api/groups-operations)。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-229">For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span> 

## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="7ffe5-230">部署 Office 增益集的建議方法</span><span class="sxs-lookup"><span data-stu-id="7ffe5-230">Recommended approach for deploying Office add-ins</span></span> 
<span data-ttu-id="7ffe5-231">若要使用逐步式方法來推出增益集，建議您執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-231">To roll out add-ins by using a phased approach, we recommend the following:</span></span> 
1. <span data-ttu-id="7ffe5-232">針對小組的商務專案關係人以及 IT 部門的成員推出增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-232">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="7ffe5-233">您可以開啟旗標 **為測試部署**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-233">You can turn on the flag **Is this a test deployment**.</span></span> <span data-ttu-id="7ffe5-234">如果部署成功，請移至步驟2。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-234">If the deployment is successful, move to step 2.</span></span> 

2. <span data-ttu-id="7ffe5-235">向商務中的更多人員推出增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-235">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="7ffe5-236">請再次評估結果，如果成功，則繼續進行完整部署。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-236">Again, evaluate the results and, if successful, continue with full deployment.</span></span> 

3. <span data-ttu-id="7ffe5-237">對所有使用者執行完整的展示。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-237">Perform a full rollout to all users.</span></span> <span data-ttu-id="7ffe5-238">從 [ **這是測試部署**] 中關閉旗標。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-238">Turn off the flag from **Is this a Test deployment**.</span></span> 

<span data-ttu-id="7ffe5-239">視目標物件的大小而定，您可以新增或移除向外展開步驟。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-239">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="7ffe5-240">使用系統管理中心部署 Office 增益集</span><span class="sxs-lookup"><span data-stu-id="7ffe5-240">Deploy an Office add-in using the admin center</span></span> 

1. <span data-ttu-id="7ffe5-241">在系統管理中心中，選取 [ **設定**]，然後選取 [ **整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-241">In the admin center, select **Settings**, then select **Integrated apps**.</span></span> 

2. <span data-ttu-id="7ffe5-242">選取頁面頂端的 [ **取得應用程式** ]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-242">Select **Get apps** at the top of the page.</span></span> <span data-ttu-id="7ffe5-243">AppSource 會以內嵌的格式載入。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-243">AppSource will load in an embedded format.</span></span> <span data-ttu-id="7ffe5-244">請搜尋增益集或透過按一下左側導覽上的 [產品] 來尋找。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-244">Either search for an add-in or find it through clicking on Product on the left nav.</span></span>  <span data-ttu-id="7ffe5-245">若增益集已由 ISV 連結至 SaaS 應用程式或其他應用程式及增益集，且 SaaS 應用程式是付費應用程式，則會顯示一個對話方塊，以購買授權或部署。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-245">If the add-in has been linked by the ISV to a SaaS app or other apps and add-ins and if the SaaS app is a paid app then you will be shown a dialog box to either buy the license or Deploy.</span></span> <span data-ttu-id="7ffe5-246">不論您已購買授權，還是不可以繼續進行部署。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-246">Irrespective of whether you have bought the license or not you can go ahead with the deployment.</span></span> <span data-ttu-id="7ffe5-247">選取 [部署 **]**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-247">Select **Deploy**.</span></span>  

3. <span data-ttu-id="7ffe5-248">您將會看到 [設定 **] 頁面中** 列出所有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-248">You will see the **Configuration** page where all the apps are listed.</span></span> <span data-ttu-id="7ffe5-249">如果您沒有部署應用程式的許可權或正確存取權，將會反白顯示各自的資訊。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-249">If you don’t have permissions or the right access to deploy the app, the respective information will be highlighted.</span></span> <span data-ttu-id="7ffe5-250">您可以選取您要部署的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-250">You can select the apps you want to deploy.</span></span> <span data-ttu-id="7ffe5-251">選取 **[下一步]**，即可查看 [ **使用者** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-251">By selecting **Next**, you will view the **Users** page.</span></span> <span data-ttu-id="7ffe5-252">若增益集尚未透過 ISV 連結，您會路由傳送至 [使用者] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-252">If the add-in hasn’t been linked by the ISV, you will be routed to the Users page.</span></span> 

4. <span data-ttu-id="7ffe5-253">選取 [ **所有人**]、[ **特定使用者/群組**] 或 [ **僅限我**]，   以指定要部署增益集的人員。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-253">Select **Everyone**, **Specific users/groups**, or **Just me** to specify whom the add-in is deployed to.</span></span> <span data-ttu-id="7ffe5-254">使用 [搜尋] 方塊尋找特定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-254">Use the Search box to find specific users or groups.</span></span> <span data-ttu-id="7ffe5-255">如果您要測試增益集，請選取 [ **這是測試部署**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-255">If you are testing the add-in, select **Is this a test deployment**.</span></span> 

5. <span data-ttu-id="7ffe5-256">選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-256">Select **Next**.</span></span> <span data-ttu-id="7ffe5-257">所有應用程式功能和許可權會顯示在單一窗格中，如果應用程式有 Microsoft 365 認證，則會顯示認證資訊。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-257">All the app capabilities and permissions are displayed in a single pane along with certification info if the app has Microsoft 365 certification.</span></span> <span data-ttu-id="7ffe5-258">選取憑證標誌可讓使用者查看有關憑證的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-258">Selecting the certification logo lets the user see more details about the certification.</span></span>  

6. <span data-ttu-id="7ffe5-259">請複習，然後選取 **[完成部署]**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-259">Review, and then select **Finish deployment**.</span></span>  

7. <span data-ttu-id="7ffe5-260">部署增益集時，會出現綠色的「滴答」圖示。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-260">A green "tick" icon appears when the add-in is deployed.</span></span> <span data-ttu-id="7ffe5-261">依照頁面上的指示測試增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-261">Follow the on-page instructions to test the add-in.</span></span> 

> [!NOTE]
> <span data-ttu-id="7ffe5-262">使用者可能需要重新開機 Office 來查看應用程式功能區上的增益集圖示。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-262">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="7ffe5-263">Outlook 增益集最多可能需要24小時才能出現在應用程式功能區上。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-263">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span> 

<span data-ttu-id="7ffe5-264">建議使用已部署增益集的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-264">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="7ffe5-265">請考慮傳送描述何時及如何使用增益集的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-265">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="7ffe5-266">包含或連結，以協助內容或 FAQs 如果增益集發生問題，可能會協助使用者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-266">Include or link to help content or FAQs that might help users if they have problems with the add-in.</span></span> 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="7ffe5-267">將增益集指派給使用者和群組時的考慮事項</span><span class="sxs-lookup"><span data-stu-id="7ffe5-267">Considerations when assigning an add-in to users and groups</span></span> 

<span data-ttu-id="7ffe5-268">全域管理員和 Exchange 系統管理員可以將增益集指派給每個人或特定使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-268">Global admins and Exchange admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="7ffe5-269">每個選項都有其意涵：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-269">Each option has implications:</span></span> 

- <span data-ttu-id="7ffe5-270">**所有人**  此選項會將增益集指派給組織中的每一位使用者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-270">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="7ffe5-271">請謹慎使用此選項，並且只有在貴組織需要普遍使用此增益集時才使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-271">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 

- <span data-ttu-id="7ffe5-272">**使用者**  如果您將增益集指派給個別使用者，然後將增益集部署至新的使用者，您必須先新增新的使用者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-272">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span> 

- <span data-ttu-id="7ffe5-273">**群組**  如果您將增益集指派給群組，則新增至群組的使用者會自動指派增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-273">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="7ffe5-274">當使用者從群組中移除時，使用者將無法存取增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-274">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="7ffe5-275">在這兩種情況下，系統管理員不需要其他的動作。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-275">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="7ffe5-276">**僅自己**  如果您將增益集指派給您自己，增益集就會指派給您的帳戶，這是測試增益集的理想選擇。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-276">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span> 

<span data-ttu-id="7ffe5-277">組織的右選項視您的設定而定。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-277">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="7ffe5-278">不過，我們建議您使用群組來進行工作分派。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-278">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="7ffe5-279">身為系統管理員，您可能會發現使用群組來管理增益集及控制這些群組的成員資格，而不是每次指派個別使用者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-279">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="7ffe5-280">在某些情況下，您可能會想要限制一小部分使用者的存取，只要手動指派使用者給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-280">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span> 

### <a name="more-about-office-add-ins-security"></a><span data-ttu-id="7ffe5-281">更多關於 Office 增益集的安全性</span><span class="sxs-lookup"><span data-stu-id="7ffe5-281">More about Office add-ins security</span></span> 
<span data-ttu-id="7ffe5-p143">Office 增益集會與內含部分增益集中繼資料的 XML 資訊清單檔案合併，但最重要的是，Office 增益集會與指向包含所有程式碼和邏輯的 Web 應用程式合併。增益集可以有各種不同的功能。例如，增益集可以：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-p143">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
- <span data-ttu-id="7ffe5-285">顯示資料。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-285">Display data.</span></span> 
- <span data-ttu-id="7ffe5-286">閱讀使用者的文件以提供內容相關服務。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-286">Read a user's document to provide contextual services.</span></span> 
- <span data-ttu-id="7ffe5-287">從使用者的文件讀取及寫入資料，以提供值給該使用者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-287">Read and write data to and from a user's document to provide value to that user.</span></span>  

<span data-ttu-id="7ffe5-288">如需 Office 增益集類型和功能的相關資訊，請參閱 [Office 增益集平臺概述](/office/dev/add-ins/overview/office-add-ins)，尤其是「剖析 office 增益集」一節。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-288">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span> 

<span data-ttu-id="7ffe5-289">若要與使用者的檔互動，增益集必須宣告資訊清單中所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-289">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest.</span></span> <span data-ttu-id="7ffe5-290">五層級 JavaScript API 存取許可權模型為工作窗格增益集的使用者提供隱私權及安全性的基礎。Office 書店中的大部分增益集是層級 ReadWriteDocument，幾乎所有增益集至少都支援 ReadDocument 層級。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-290">A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level.</span></span> <span data-ttu-id="7ffe5-291">如需許可權等級的詳細資訊，請參閱 [要求用於內容和工作窗格增益集的 API 許可權](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-291">For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span> 

<span data-ttu-id="7ffe5-p145">更新資訊清單時，通常是變更增益集的圖示和文字。有時則會變更增益集的命令。不過，增益集的權限不會遭到變更。執行增益集的所有程式碼和邏輯的 Web 應用程式可能隨時變更，這是 Web 應用程式的本質所致。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-p145">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span> 

<span data-ttu-id="7ffe5-296">增益集的更新會以下列方式進行：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-296">Updates for add-ins happen as follows:</span></span> 
- <span data-ttu-id="7ffe5-297">**企業營運增益集**：在此情況下，系統管理員明確上傳資訊清單的位置，增益集需要系統管理員上載新的資訊清單檔案，以支援中繼資料變更。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-297">**Line-of-business add-in**: In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span></span> <span data-ttu-id="7ffe5-298">在下次啟動相關的 Office 應用程式時，增益集就會更新。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-298">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="7ffe5-299">Web 應用程式可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-299">The web application can change at any time.</span></span> 

- <span data-ttu-id="7ffe5-300">**Office store 增益集**：當系統管理員從 office store 中選取增益集時，如果 office store 中的增益集更新，下次相關的 Office 應用程式啟動時，增益集就會更新。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-300">**Office Store add-in**: When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="7ffe5-301">Web 應用程式可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-301">The web application can change at any time.</span></span> 

> [!NOTE]
> <span data-ttu-id="7ffe5-302">Word、Excel 及 PowerPoint 會使用 [SharePoint 應用程式目錄](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)   ，將增益集部署至內部部署環境中的使用者，但不連接至 Microsoft 365 和/或支援所需 SharePoint 增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-302">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="7ffe5-303">Outlook 使用 Exchange 控制台在內部部署環境中部署，但不連接至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-303">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>  

## <a name="add-in-states"></a><span data-ttu-id="7ffe5-304">增益集狀態</span><span class="sxs-lookup"><span data-stu-id="7ffe5-304">Add-in states</span></span>
<span data-ttu-id="7ffe5-305">增益集可以處於 [開啟] 或 [ \*\*\*\*   關閉] \*\*\*\*   狀態。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-305">An add-in can be in either the **On** or **Off** state.</span></span> 

| <span data-ttu-id="7ffe5-306">狀態</span><span class="sxs-lookup"><span data-stu-id="7ffe5-306">State</span></span> | <span data-ttu-id="7ffe5-307">狀態如何發生</span><span class="sxs-lookup"><span data-stu-id="7ffe5-307">How the state occurs</span></span> | <span data-ttu-id="7ffe5-308">影響</span><span class="sxs-lookup"><span data-stu-id="7ffe5-308">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="7ffe5-309">**Active**</span><span class="sxs-lookup"><span data-stu-id="7ffe5-309">**Active**</span></span>  <br/> |<span data-ttu-id="7ffe5-310">系統管理員上載增益集，並將其指派給使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-310">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="7ffe5-311">被指派增益集的使用者和群組會在相關用戶端中看見增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-311">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="7ffe5-312">**已關閉**</span><span class="sxs-lookup"><span data-stu-id="7ffe5-312">**Turned off**</span></span>  <br/> |<span data-ttu-id="7ffe5-313">系統管理員已關閉增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-313">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="7ffe5-314">被指派增益集的使用者和群組無法再存取增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-314">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="7ffe5-315">如果增益集狀態已變更為 [使用中]，使用者和群組將可再次存取增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-315">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="7ffe5-316">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="7ffe5-316">**Deleted**</span></span>  <br/> |<span data-ttu-id="7ffe5-317">系統管理員已刪除增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-317">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="7ffe5-318">被指派增益集的使用者和群組無法再存取增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-318">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
 
<span data-ttu-id="7ffe5-319">如果沒有人再使用增益集，請考慮刪除增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-319">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="7ffe5-320">例如，如果增益集只會在一年的特定時間內使用，則關閉增益集可能會有意義。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-320">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span> 

## <a name="manage-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="7ffe5-321">使用系統管理中心管理 Office 增益集</span><span class="sxs-lookup"><span data-stu-id="7ffe5-321">Manage an Office add-in using the admin center</span></span>

<span data-ttu-id="7ffe5-322">部署後，系統管理員也可以管理使用者對增益集的存取。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-322">Post deployment, admins can also manage user access to add-ins.</span></span> 

1. <span data-ttu-id="7ffe5-323">在系統管理中心中，選取 [**設定**]，然後選取 [**整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-323">In the admin center, select **Settings**, then select **Integrated apps**.</span></span> 
2. <span data-ttu-id="7ffe5-324">在 [整合式應用程式] 頁面上，它會顯示應用程式的清單，這些應用程式會是單一增益集，也就是與其他應用程式連結的增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-324">On the Integrated apps page, it will display a list of apps will be either single add-ins or add-ins that have been linked with other apps.</span></span> 
3. <span data-ttu-id="7ffe5-325">選取 \*\*\*\*   [ **可供** 使用的應用程式狀態] 的應用程式   ，以開啟 [ **管理**   ] 窗格。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-325">Select an app with **Status** of **More apps available** to open the **Manage** pane.</span></span> <span data-ttu-id="7ffe5-326"> *\*可供使用的更多應用程式** 狀態，可   讓您知道還有其他尚未部署的 isv 的整合。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-326">The status of **more apps available** lets you know that there are more integrations from the ISVs that aren't yet deployed.</span></span> 
4. <span data-ttu-id="7ffe5-327">在 [ **概覽**] 索引標籤上   ，選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-327">On the **Overview** tab, select **Deploy**.</span></span> <span data-ttu-id="7ffe5-328">某些應用程式會要求您先新增使用者，才能選擇 [部署]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-328">Some apps require you to add users before you can select Deploy.</span></span> 
5. <span data-ttu-id="7ffe5-329">選取 [ **使用者**]，選取 [ **這是測試部署**]，然後選取 [ **整個組織**]、[ **特定使用者/群組**]   或 [ **僅自己**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-329">Select **Users**, select **Is this a test deployment**, and then select either **Entire organization**, **Specific users/groups** or **Just me**.</span></span> <span data-ttu-id="7ffe5-330"> \*\*\*\*   如果您想要等待將應用程式部署至整個組織，也可以選取 [測試部署]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-330">You can also select **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span> <span data-ttu-id="7ffe5-331">特定的使用者或群組可以是 Microsoft 365 群組、安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-331">Specific users or groups can be a Microsoft 365 group, a security group, or a distribution group.</span></span> 
6. <span data-ttu-id="7ffe5-332">選取 [ **更新**]   ，然後選取 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-332">Select  **Update** and then select **Done**.</span></span> <span data-ttu-id="7ffe5-333">您現在可以在 [**概覽**] 索引標籤上選取 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-333">You can now select **Deploy** on the **Overview** tab.</span></span> 
7. <span data-ttu-id="7ffe5-334">查看應用程式資訊，然後選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-334">Review the app information, and then select **Deploy**.</span></span>
8. <span data-ttu-id="7ffe5-335">在  \*\*\*\*   [**部署已完成**] 頁面上，選取 [完成]，然後在 [ **概覽**] 索引標籤上複查測試或完整部署的詳細資料   。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-335">Select  **Done** on the **Deployment completed** page, and review the details of the test or full deployment on the **Overview** tab.</span></span> 
9. <span data-ttu-id="7ffe5-336">若應用程式狀態為 [ **待處理的更新**]，您可以按一下應用程式以開啟 [ **管理** ] 窗格，然後更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-336">If the app has a status of  **Update pending**, you can click on the app to open the **Manage** pane and update the app.</span></span> 
10. <span data-ttu-id="7ffe5-337">若只要更新使用者，請選取 [ **使用者** ] 索引標籤並進行適當的變更。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-337">To just update users, select the **Users** tab and make the appropriate change.</span></span> <span data-ttu-id="7ffe5-338">在進行變更後選取 [ **更新** ]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-338">Select **Update** after making your changes.</span></span>  

## <a name="delete-an-add-in"></a><span data-ttu-id="7ffe5-339">刪除增益集</span><span class="sxs-lookup"><span data-stu-id="7ffe5-339">Delete an add-in</span></span>

<span data-ttu-id="7ffe5-340">您也可以刪除已部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-340">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="7ffe5-341">在系統管理中心中，選取 [**設定**]，然後選取 [**整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-341">In the admin center, select **Settings**, then select **Integrated apps** .</span></span>
2. <span data-ttu-id="7ffe5-342">選取任何列以顯示管理窗格。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-342">Select any row to display the management pane.</span></span> 
3. <span data-ttu-id="7ffe5-343">選取 [ **設定** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-343">Select the **Configuration** tab.</span></span> 
4. <span data-ttu-id="7ffe5-344">選取您要刪除的增益集，然後選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-344">Select the add-in that you want to delete and then select **Remove**.</span></span>  

> [!NOTE]
>  <span data-ttu-id="7ffe5-345">如果增益集是由另一個系統管理員部署，則 [移除] 按鈕將會停用。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-345">If the add-in has been deployed by another admin, then the Remove button will be disabled.</span></span> <span data-ttu-id="7ffe5-346">只有已部署應用程式或全域管理員的系統管理員可以刪除增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-346">Only the admin who has deployed the app or a global admin can delete the add-in.</span></span>

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a><span data-ttu-id="7ffe5-347">Exchange 系統管理員無法部署增益集的情況</span><span class="sxs-lookup"><span data-stu-id="7ffe5-347">Scenarios where Exchange admin cannot deploy an add-in</span></span> 

<span data-ttu-id="7ffe5-348">有兩種情況可供 Exchange 管理員無法部署增益集：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-348">There are two cases in which an Exchange Admin won't be able to deploy an add-in:</span></span>
- <span data-ttu-id="7ffe5-349">若增益集需要 MS Graph APIs 的許可權，且需要全域系統管理員的同意。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-349">If an add-in needs permission to MS Graph APIs and needs consent from a global admin.</span></span>
- <span data-ttu-id="7ffe5-350">如果增益集連結至兩個或多個增益集和 webapps，且有至少一個增益集是由另一個系統管理員部署 (exchange/全域) ，且使用者指派不一致。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-350">If an add-in is linked to two or more add-ins and webapps, and at least one of these add-ins is deployed by another admin (exchange/global) and the user assignment is not uniform.</span></span> <span data-ttu-id="7ffe5-351">僅當所有已部署的應用程式的使用者指派相同時，我們才允許部署增益集。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-351">We only allow deployment of add-ins when the user assignment is the same for all the already deployed apps.</span></span>  


## <a name="frequently-asked-questions"></a><span data-ttu-id="7ffe5-352">常見問題集</span><span class="sxs-lookup"><span data-stu-id="7ffe5-352">Frequently asked questions</span></span>

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a><span data-ttu-id="7ffe5-353">我需要哪些系統管理員角色才能存取整合式應用程式？</span><span class="sxs-lookup"><span data-stu-id="7ffe5-353">Which administrator role do I need to access Integrated apps?</span></span>

<span data-ttu-id="7ffe5-354">只有全域管理員才能存取整合式應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-354">Only global administrators can access Integrated Apps.</span></span> <span data-ttu-id="7ffe5-355">在其他系統管理員的左側導覽中，整合式應用程式不會顯示。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-355">Integrated apps won't show up in the left nav for other administrators.</span></span>

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a><span data-ttu-id="7ffe5-356">為什麼我會在左導覽的 [設定] 底下看到增益集，但不是集成應用程式？</span><span class="sxs-lookup"><span data-stu-id="7ffe5-356">Why do I see Add-in in the left nav under Setting but not Integrated apps?</span></span>

<span data-ttu-id="7ffe5-357">原因如下：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-357">There could be a few reasons:</span></span>

- <span data-ttu-id="7ffe5-358">登入的系統管理員是 Exchange 管理員。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-358">The logged in administrator is an Exchange administrator.</span></span>
- <span data-ttu-id="7ffe5-359">客戶位於以及主權雲端，但整合型應用程式體驗可供以及主權雲端客戶使用。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-359">The customer is in sovereign cloud and Integrated apps experience is available to sovereign cloud customers yet.</span></span>

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a><span data-ttu-id="7ffe5-360">我可以從整合式應用程式部署哪些應用程式？</span><span class="sxs-lookup"><span data-stu-id="7ffe5-360">What apps can I deploy from Integrated apps?</span></span>

<span data-ttu-id="7ffe5-361">整合式應用程式允許部署 Web 應用程式、Teams 應用程式、Excel、PowerPoint、Word、Outlook 增益集及 SPFx 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-361">Integrated apps allow deployment of Web Apps, Teams app, Excel, PowerPoint, Word, Outlook add-ins, and SPFx apps.</span></span> <span data-ttu-id="7ffe5-362">針對增益集，整合式應用程式支援部署 Exchange 線上信箱，而非內部部署 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-362">For add-ins, Integrated apps support deployment to Exchange online mailboxes and not on-premises Exchange mailboxes.</span></span>

### <a name="can-administrators-delete-or-remove-apps"></a><span data-ttu-id="7ffe5-363">管理員可以刪除或移除應用程式嗎？</span><span class="sxs-lookup"><span data-stu-id="7ffe5-363">Can administrators delete or remove apps?</span></span>

<span data-ttu-id="7ffe5-364">是。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-364">Yes.</span></span> <span data-ttu-id="7ffe5-365">全域管理員可以刪除或移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-365">Global administrators can delete or remove apps.</span></span>

- <span data-ttu-id="7ffe5-366">從清單視圖中選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-366">Select an app from the list view.</span></span> <span data-ttu-id="7ffe5-367">**在 [設定**] 索引標籤上，選取要移除的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-367">On the **Configuration** tab, select which apps to remove.</span></span>  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a><span data-ttu-id="7ffe5-368">以及主權雲端中是否有整合式應用程式？</span><span class="sxs-lookup"><span data-stu-id="7ffe5-368">Is Integrated apps available in sovereign cloud?</span></span>

<span data-ttu-id="7ffe5-369">否。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-369">No.</span></span> <span data-ttu-id="7ffe5-370">無法以及主權 cloud 客戶的整合式應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-370">Integrated apps aren't available to sovereign cloud customers.</span></span>

### <a name="is-integrated-apps-available-in-government-clouds"></a><span data-ttu-id="7ffe5-371">政府雲端中是否有整合式應用程式？</span><span class="sxs-lookup"><span data-stu-id="7ffe5-371">Is Integrated apps available in government clouds?</span></span>

<span data-ttu-id="7ffe5-372">否。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-372">No.</span></span> <span data-ttu-id="7ffe5-373">政府雲端客戶無法使用整合式應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-373">Integrated apps aren't available to government cloud customers.</span></span>
