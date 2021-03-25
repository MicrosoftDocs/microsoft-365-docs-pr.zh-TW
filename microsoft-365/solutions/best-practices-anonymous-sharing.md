---
title: 未驗證共用的最佳做法
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: 在本文中，您將了解與未驗證使用者共用檔案和資料夾的最佳做法。
ms.openlocfilehash: acc825a8fc445d224fbc91dd12dace2a5e1b25c8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199522"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a><span data-ttu-id="1a920-103">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="1a920-103">Best practices for sharing files and folders with unauthenticated users</span></span>

<span data-ttu-id="1a920-104">未驗證共用 (*任何人* 連結) 在許多案例下都相當方便。</span><span class="sxs-lookup"><span data-stu-id="1a920-104">Unauthenticated sharing (*Anyone* links) can be convenient and is useful in various scenarios.</span></span> <span data-ttu-id="1a920-105">*任何人* 連結為共用最簡單的方式：人員可以不經驗證就開啟連結，且可隨意將它傳送給其他人。</span><span class="sxs-lookup"><span data-stu-id="1a920-105">*Anyone* links are the easiest way to share: people can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="1a920-106">一般來說，並非組織中的所有內容都適合進行未驗證共用。</span><span class="sxs-lookup"><span data-stu-id="1a920-106">Usually, not all content in an organization is appropriate for unauthenticated sharing.</span></span> <span data-ttu-id="1a920-107">本文涵蓋可協助您建立一個環境的選項，您的使用者能夠在該環境中未驗證共用檔案和資料夾，但在其中有一些既有措施可協助保護組織內容的安全。</span><span class="sxs-lookup"><span data-stu-id="1a920-107">This article covers the options available to help you create an environment where your users can use unauthenticated sharing of files and folders, but where there are safeguards in place to help protect your organization's content.</span></span>

> [!NOTE]
> <span data-ttu-id="1a920-108">若要讓未驗證共用運作，您必須為組織以及您將使用的個別網站或小組啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="1a920-108">For unauthenticated sharing to work, you must enable it for your organization and for the individual site or team that you'll be using.</span></span> <span data-ttu-id="1a920-109">如需您要啟用的案例，請參閱[與組織外部人員共同作業](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="1a920-109">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for the scenario that you want to enable.</span></span>

## <a name="set-an-expiration-date-for-anyone-links"></a><span data-ttu-id="1a920-110">設定任何人連結的到期日</span><span class="sxs-lookup"><span data-stu-id="1a920-110">Set an expiration date for Anyone links</span></span>

<span data-ttu-id="1a920-111">檔案通常會長時間儲存在網站、群組和小組。</span><span class="sxs-lookup"><span data-stu-id="1a920-111">Files are often stored in sites, groups, and teams for long periods of time.</span></span> <span data-ttu-id="1a920-112">有時候，有一些資料保留原則會要求將檔案保留數年。</span><span class="sxs-lookup"><span data-stu-id="1a920-112">Occasionally there are data retention policies that require files to be retained for years.</span></span> <span data-ttu-id="1a920-113">如果將這類檔案與未驗證的人員共用，可能導致未來非預期地存取和變更這些檔案。</span><span class="sxs-lookup"><span data-stu-id="1a920-113">If such files are shared with unauthenticated people, this could lead to unexpected access and changes to files in the future.</span></span> <span data-ttu-id="1a920-114">若要降低此可能性，您可以為 *任何人* 連結設定到期時間。</span><span class="sxs-lookup"><span data-stu-id="1a920-114">To mitigate this possibility, you can configure an expiration time for *Anyone* links.</span></span>

<span data-ttu-id="1a920-115">*任何人* 連結到期後，就無法再用來存取內容。</span><span class="sxs-lookup"><span data-stu-id="1a920-115">Once an *Anyone* link expires, it can no longer be used to access content.</span></span>

<span data-ttu-id="1a920-116">設定組織中任何人的連結到期日。</span><span class="sxs-lookup"><span data-stu-id="1a920-116">To set an expiration date for Anyone links across the organization</span></span>

1. <span data-ttu-id="1a920-117">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="1a920-117">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="1a920-118">在左側導覽窗格中，按一下 [共用]。</span><span class="sxs-lookup"><span data-stu-id="1a920-118">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="1a920-119">在 **[為任何人連結選擇過期和授權選項]** 下，選取 **[這些連結必須在此天數內過期]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1a920-119">Under **Choose expiration and permissions options for Anyone links**, select the **These links must expire within this many days** check box.</span></span></br>
   <span data-ttu-id="1a920-120">![SharePoint 組織層級任何人連結到期設定的螢幕擷取畫面](../media/sharepoint-organization-anyone-link-expiration.png)</span><span class="sxs-lookup"><span data-stu-id="1a920-120">![Screenshot of SharePoint organization-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration.png)</span></span>
4. <span data-ttu-id="1a920-121">在方塊中輸入天數，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="1a920-121">Type a number of days in the box, and then click **Save**.</span></span>

<span data-ttu-id="1a920-122">在特定網站上，設定任何人連結的到期日</span><span class="sxs-lookup"><span data-stu-id="1a920-122">To set an expiration date for Anyone links on a specific site</span></span>

1. <span data-ttu-id="1a920-123">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="1a920-123">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="1a920-124">在左側瀏覽窗格中，展開 **[網站]**，然後按一下 **[作用中網站]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-124">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="1a920-125">選取要變更的網站，然後按一下 **[共用]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-125">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="1a920-126">在 **[任何人連結的進階設定]** 的 **[任何人連結到期日]** 底下，清除 **[與組織層級相同設定]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1a920-126">Under **Advanced settings for Anyone links**, under **Expiration of Anyone links**, clear the **Same as organization-level setting** check box.</span></span></br>
   <span data-ttu-id="1a920-127">![SharePoint 網站層級任何人連結到期設定的螢幕擷取畫面](../media/sharepoint-organization-anyone-link-expiration-site.png)</span><span class="sxs-lookup"><span data-stu-id="1a920-127">![Screenshot of SharePoint site-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration-site.png)</span></span>
5. <span data-ttu-id="1a920-128">選取 **[這些連結必須在此天數內過期]** 選項，然後在方塊中輸入天數。</span><span class="sxs-lookup"><span data-stu-id="1a920-128">Select the **These links must expire within this many days** option, and type a number of days in the box.</span></span>
6. <span data-ttu-id="1a920-129">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-129">Click **Save**.</span></span>

<span data-ttu-id="1a920-130">請注意，*任何人* 連結到期之後，就可以使用新的 *任何人* 連結重新共用檔案或資料夾。</span><span class="sxs-lookup"><span data-stu-id="1a920-130">Note that once an *Anyone* link expires, the file or folder can be re-shared with a new *Anyone* link.</span></span>

<span data-ttu-id="1a920-131">您可以使用 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite)，為特定 OneDrive 設定 *任何人* 連結到期日。</span><span class="sxs-lookup"><span data-stu-id="1a920-131">You can set *Anyone* link expiration for a specific OneDrive by using [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite).</span></span>

## <a name="set-link-permissions"></a><span data-ttu-id="1a920-132">設定連結權限</span><span class="sxs-lookup"><span data-stu-id="1a920-132">Set link permissions</span></span>

<span data-ttu-id="1a920-133">根據預設，檔案的 *任何人* 連結會允許人員編輯檔案，而資料夾的 *任何人* 連結則會允許人員編輯和檢視檔案，以及上傳新檔案到資料夾。</span><span class="sxs-lookup"><span data-stu-id="1a920-133">By default, *Anyone* links for a file allow people to edit the file, and *Anyone* links for a folder allow people to edit and view files, and upload new files to the folder.</span></span> <span data-ttu-id="1a920-134">您可以獨立將檔案和資料夾的這些權限變更為僅供檢視。</span><span class="sxs-lookup"><span data-stu-id="1a920-134">You can change these permissions for files and for folders independently to view-only.</span></span>

<span data-ttu-id="1a920-135">如果您想要允許未驗證共用，但擔心未驗證的人員修改組織的內容，請考慮將檔案和資料夾權限設定為 [檢視]。</span><span class="sxs-lookup"><span data-stu-id="1a920-135">If you want to allow unauthenticated sharing, but are concerned about unauthenticated people modifying your organization's content, consider setting the file and folder permissions to **View**.</span></span>

<span data-ttu-id="1a920-136">設定組織中任何人連結的權限。</span><span class="sxs-lookup"><span data-stu-id="1a920-136">To set permissions for Anyone links across the organization</span></span>

1. <span data-ttu-id="1a920-137">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="1a920-137">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="1a920-138">在左側導覽窗格中，按一下 [共用]。</span><span class="sxs-lookup"><span data-stu-id="1a920-138">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="1a920-139">在 [「任何人」連結的進階設定] 底下，選取您要使用的檔案和資料夾權限。</span><span class="sxs-lookup"><span data-stu-id="1a920-139">Under **Advanced settings for "Anyone" links**, select the file and folder permissions that you want to use.</span></span></br>
   <span data-ttu-id="1a920-140">![SharePoint 組織層級任何人連結權限設定的螢幕擷取畫面](../media/sharepoint-organization-anyone-link-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="1a920-140">![Screenshot of SharePoint organization-level Anyone link permissions settings](../media/sharepoint-organization-anyone-link-permissions.png)</span></span>

<span data-ttu-id="1a920-141">將 *任何人* 連結設為 [檢視] 時，使用者仍然可以與來賓共用檔案和資料夾，並使用 *特定人員* 連結提供編輯權限。</span><span class="sxs-lookup"><span data-stu-id="1a920-141">With *Anyone* links set to **View**, users can still share files and folders with guests and give them edit permissions by using *Specific people* links.</span></span> <span data-ttu-id="1a920-142">這些連結要求組織外的人員驗證為來賓身分，而您可以追蹤和稽核使用這些連結共用的檔案和資料夾上的來賓活動。</span><span class="sxs-lookup"><span data-stu-id="1a920-142">These links require people outside your organization to authenticate as guests, and you can track and audit guest activity on files and folders shared with these links.</span></span>

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a><span data-ttu-id="1a920-143">將預設連結類型設定為僅適用組織中的人員</span><span class="sxs-lookup"><span data-stu-id="1a920-143">Set default link type to only work for people in your organization</span></span>

<span data-ttu-id="1a920-144">為組織啟用 *任何人* 共用時，預設的共用連結一般會設定為 **任何人**。</span><span class="sxs-lookup"><span data-stu-id="1a920-144">When *Anyone* sharing is enabled for your organization, the default sharing link is normally set to **Anyone**.</span></span> <span data-ttu-id="1a920-145">雖然這對使用者而言很方便，但可能會增加無意間未驗證共用的風險。</span><span class="sxs-lookup"><span data-stu-id="1a920-145">While this can be convenient for users, it can increase the risk of unintentional unauthenticated sharing.</span></span> <span data-ttu-id="1a920-146">如果使用者在共用機密文件時忘記變更連結類型，他們可能會意外建立不需要驗證的共用連結。</span><span class="sxs-lookup"><span data-stu-id="1a920-146">If a user forgets to change the link type while sharing a sensitive document, they might accidentally create a sharing link that doesn't require authentication.</span></span>

<span data-ttu-id="1a920-147">您可以透過將預設連結設定變更為僅適用組織內部人員的連結，來降低此風險。</span><span class="sxs-lookup"><span data-stu-id="1a920-147">You can mitigate this risk by changing the default link setting to a link that only works for people inside your organization.</span></span> <span data-ttu-id="1a920-148">這麼一來，想要進行未驗證共用的使用者，必須特別選取該選項。</span><span class="sxs-lookup"><span data-stu-id="1a920-148">Users who want to share with unauthenticated people would then have to specifically select that option.</span></span>

<span data-ttu-id="1a920-149">為組織設定預設的檔案和資料夾共用連結</span><span class="sxs-lookup"><span data-stu-id="1a920-149">To set the default file and folder sharing link for the organization</span></span>
1. <span data-ttu-id="1a920-150">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="1a920-150">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="1a920-151">在左側導覽窗格中，按一下 **[共用]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-151">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="1a920-152">在 **[檔案與資料夾連結]** 下，選取 **[只有貴組織中的人員]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-152">Under **File and folder links**, select **Only people in your organization**.</span></span>

   ![SharePoint 預設連結類型設定的螢幕擷取畫面](../media/sharepoint-default-sharing-link-company-link.png)

4. <span data-ttu-id="1a920-154">按一下 **[儲存]**</span><span class="sxs-lookup"><span data-stu-id="1a920-154">Click **Save**</span></span>

<span data-ttu-id="1a920-155">為特定網站設定預設的檔案和資料夾共用連結</span><span class="sxs-lookup"><span data-stu-id="1a920-155">To set the default file and folder sharing link for a specific site</span></span>
1. <span data-ttu-id="1a920-156">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="1a920-156">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="1a920-157">在左側瀏覽窗格中，展開 **[網站]**，然後按一下 **[作用中網站]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-157">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="1a920-158">選取要變更的網站，然後按一下 **[共用]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-158">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="1a920-159">在 **[預設的共用連結類型]** 底下，清除 **[與組織層級設定相同]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1a920-159">Under **Default sharing link type**,  clear the **Same as organization-level setting** check box.</span></span>

   ![SharePoint 網站層級預設連結類型設定的螢幕擷取畫面](../media/sharepoint-organization-anyone-link-permissions-site.png)

5. <span data-ttu-id="1a920-161">選取 **[只有貴組織的人員]** 選項，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-161">Select the **Only people in your organization** option and click **Save**.</span></span>

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a><span data-ttu-id="1a920-162">防止未經驗證的敏感性內容共用</span><span class="sxs-lookup"><span data-stu-id="1a920-162">Prevent unauthenticated sharing of sensitive content</span></span>

<span data-ttu-id="1a920-163">您可以使用 [資料外洩防護 (DLP)](../compliance/data-loss-prevention-policies.md) 以防止未經驗證的敏感性內容共用。</span><span class="sxs-lookup"><span data-stu-id="1a920-163">You can use [data loss prevention (DLP)](../compliance/data-loss-prevention-policies.md) to prevent unauthenticated sharing of sensitive content.</span></span> <span data-ttu-id="1a920-164">資料外洩防護可根據檔案的敏感度標籤、保留標籤或檔案本身的敏感性資訊採取行動。</span><span class="sxs-lookup"><span data-stu-id="1a920-164">Data loss prevention can take action based on a file's sensitivity label, retention label, or sensitive information in the file itself.</span></span>

<span data-ttu-id="1a920-165">建立 DLP 規則</span><span class="sxs-lookup"><span data-stu-id="1a920-165">To create a DLP rule</span></span>
1. <span data-ttu-id="1a920-166">在 Microsoft 365 合規性系統管理中心中，移至 [資料外外洩防護頁面](https://compliance.microsoft.com/datalossprevention)。</span><span class="sxs-lookup"><span data-stu-id="1a920-166">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="1a920-167">按一下 **[建立原則]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-167">Click **Create policy**.</span></span>
3. <span data-ttu-id="1a920-168">選擇 **[自訂]** ，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-168">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="1a920-169">輸入原則的名稱，並按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-169">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="1a920-170">在 **[套用原則的位置]** 頁面上，關閉 **SharePoint 網站** 和 **OneDrive 帳戶** 以外的所有設定，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-170">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts**, and then click **Next**.</span></span>
6. <span data-ttu-id="1a920-171">在 **[定義原則設定]** 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-171">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="1a920-172">在 **[自訂進階資料外洩防護規則]** 頁面上，按一下 **[建立規則]**，然後輸入規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="1a920-172">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="1a920-173">在 [條件 **]** 底下，按一下 [新增條件 **]**，並選擇 [內容包含 **]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-173">Under **Conditions**, click **Add condition**, and choose **Content contains**.</span></span>
9. <span data-ttu-id="1a920-174">按一下 **[新增]**，然後選擇您想要防止未經授權共用的資訊類型。</span><span class="sxs-lookup"><span data-stu-id="1a920-174">Click **Add** and choose the type of information for which you want to prevent unauthenticated sharing.</span></span>

   ![條件選項、敏感性資訊類型、敏感性標籤及保留標籤的螢幕擷取畫面。](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="1a920-176">在 [動作 **]** 底下，按一下 [新增動作 **]**，然後選擇 [限制存取或加密 Microsoft 365 位置中的內容 **]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-176">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="1a920-177">選取 **[限制存取權或加密 Microsoft 365 位置中的內容]** 核取方塊，然後選擇 **[僅限透過「具有連結的任何人」 選項獲得存取內容的人員]** 選項。</span><span class="sxs-lookup"><span data-stu-id="1a920-177">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people who were given access to the content through the "Anyone withe the link" options** option.</span></span>

      ![DLP 規則動作選項的螢幕擷取畫面](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. <span data-ttu-id="1a920-179">按一下 **[儲存]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-179">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="1a920-180">選擇您的測試選項，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-180">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="1a920-181">按一下 [提交 **]**，然後按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-181">Click **Submit**, and then click **Done**.</span></span>

## <a name="protect-against-malicious-files"></a><span data-ttu-id="1a920-182">防範惡意檔案</span><span class="sxs-lookup"><span data-stu-id="1a920-182">Protect against malicious files</span></span>

<span data-ttu-id="1a920-183">允許匿名使用者上傳檔案時，可能會增加某人上傳惡意檔案的風險。</span><span class="sxs-lookup"><span data-stu-id="1a920-183">When you allow anonymous users to upload files, you're at an increased risk of someone uploading a malicious file.</span></span> <span data-ttu-id="1a920-184">在 Microsoft 365 中，您可以使用適用於 Office 365 的 Defender 中的 *安全附件* 功能，自動掃描已上傳的檔案並隔離發現不安全的檔案。</span><span class="sxs-lookup"><span data-stu-id="1a920-184">In Microsoft 365, you can use the *Safe Attachments* feature in Defender for Office 365 to automatically scan uploaded files and quarantine files that are found to be unsafe.</span></span>

<span data-ttu-id="1a920-185">開啟安全附件</span><span class="sxs-lookup"><span data-stu-id="1a920-185">To turn on safe attachments</span></span>
1. <span data-ttu-id="1a920-186">開啟 [安全性與合規性系統管理中心] 的 [[ATP 安全附件] 頁面](https://protection.office.com/safeattachmentv2)。</span><span class="sxs-lookup"><span data-stu-id="1a920-186">Open the [ATP Safe Attachments page](https://protection.office.com/safeattachmentv2) in the Security and Compliance admin center.</span></span>
2. <span data-ttu-id="1a920-187">按一下 **[通用設定]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-187">Click **Global settings**.</span></span>
3. <span data-ttu-id="1a920-188">開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP。</span><span class="sxs-lookup"><span data-stu-id="1a920-188">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   ![安全性與合規性中心安全附件設定的螢幕擷取畫面](../media/safe-attachments-setting.png)

4. <span data-ttu-id="1a920-190">或者，也可以開啟 [安全文件]，然後按一下 **[儲存]**</span><span class="sxs-lookup"><span data-stu-id="1a920-190">Optionally turn on Safe Documents as well, and then click **Save**</span></span>

<span data-ttu-id="1a920-191">請參閱 [適用於 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](../security/office-365-security/mdo-for-spo-odb-and-teams.md) ，並 [開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md) 以取得更多指導方針。</span><span class="sxs-lookup"><span data-stu-id="1a920-191">See [ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md) for additional guidance.</span></span>

## <a name="add-copyright-information-to-your-files"></a><span data-ttu-id="1a920-192">新增著作權資訊至您的檔案</span><span class="sxs-lookup"><span data-stu-id="1a920-192">Add copyright information to your files</span></span>

<span data-ttu-id="1a920-193">如果您在 Microsoft 365 合規性系統管理中心使用敏感度標籤，即可以設定您的標籤，以自動新增浮水印或頁首或頁尾至組織的 Office 文件中。</span><span class="sxs-lookup"><span data-stu-id="1a920-193">If you use sensitivity labels in the Microsoft 365 Compliance admin center, you can configure your labels to add a watermark or a header or footer automatically to your organization's Office documents.</span></span> <span data-ttu-id="1a920-194">這麼一來，您就可以確定共用的檔案包含著作權或其他擁有權資訊。</span><span class="sxs-lookup"><span data-stu-id="1a920-194">In this way, you can make sure that shared files contain copyright or other ownership information.</span></span>

<span data-ttu-id="1a920-195">新增頁尾至標籤的檔案</span><span class="sxs-lookup"><span data-stu-id="1a920-195">To add a footer to a labeled file</span></span>

1. <span data-ttu-id="1a920-196">開啟 [Microsoft 365 合規性系統管理中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="1a920-196">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="1a920-197">在左側導覽窗格中的 **[解決方案]** 底下，按一下 **[資訊保護]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-197">In the left navigation, under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="1a920-198">按一下您要新增頁尾的標籤，然後按一下 **[編輯標籤]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-198">Click the label that you want to have add a footer, and then click **Edit label**.</span></span>
4. <span data-ttu-id="1a920-199">按一下 **[下一步]** 以移至 **[內容標示]** 索引標籤，然後 **[開啟]** 內容標示。</span><span class="sxs-lookup"><span data-stu-id="1a920-199">Click **Next** to reach the **Content marking** tab, and then turn **On** content marking.</span></span>
5. <span data-ttu-id="1a920-200">選取要新增的文字類型的核取方塊，然後按一下 [自訂文字]。</span><span class="sxs-lookup"><span data-stu-id="1a920-200">Select the check box for the type of text you want to add, and then click **Customize text**.</span></span>
6. <span data-ttu-id="1a920-201">輸入要新增至文件的文字，選取需要的文字選項，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="1a920-201">Type the text that you want added to your documents, select the text options that you want, and then click **Save**.</span></span></br>
   <span data-ttu-id="1a920-202">![敏感度標籤內容標示設定的螢幕擷取畫面](../media/content-marking-for-anonymous-sharing.png)</span><span class="sxs-lookup"><span data-stu-id="1a920-202">![Screenshot of the content marking settings for a sensitivity label](../media/content-marking-for-anonymous-sharing.png)</span></span>
7. <span data-ttu-id="1a920-203">按一下 **[下一步]** 以移至精靈結尾，然後按一下 **[儲存標籤]**。</span><span class="sxs-lookup"><span data-stu-id="1a920-203">Click **Next** to reach the end of the wizard, and then click **Save label**.</span></span>

<span data-ttu-id="1a920-204">為標籤啟用內容標示後，當使用者套用該標籤，您指定的文字就會新增至 Office 文件中。</span><span class="sxs-lookup"><span data-stu-id="1a920-204">With content marking enabled for the label, the text you specified will be added to Office documents when a user applies that label.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a920-205">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1a920-205">See Also</span></span>

[<span data-ttu-id="1a920-206">敏感度標籤概觀</span><span class="sxs-lookup"><span data-stu-id="1a920-206">Overview of sensitivity labels</span></span>](/Office365/SecurityCompliance/sensitivity-labels)

[<span data-ttu-id="1a920-207">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="1a920-207">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="1a920-208">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="1a920-208">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)