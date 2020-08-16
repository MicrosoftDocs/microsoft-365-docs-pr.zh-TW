---
title: 如何檢查 Microsoft 365 服務健康情況
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: 請先查看 Microsoft 365 服務的健康狀態，再致電支援人員，查看是否有使用中的服務中斷狀態。
ms.openlocfilehash: 49f7d3afd3c19cd4e9b6486db580082fe933b997
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688781"
---
# <a name="how-to-check-microsoft-365-service-health"></a><span data-ttu-id="cc010-103">如何檢查 Microsoft 365 服務健康情況</span><span class="sxs-lookup"><span data-stu-id="cc010-103">How to check Microsoft 365 service health</span></span>

<span data-ttu-id="cc010-104">[![[標籤] 可讓您知道系統管理中心正在變更，您可以在 aka.ms/aboutM365preview 取得更多詳細資料。](../media/O365-Admin-AdminCenterChanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="cc010-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview?view=o365-worldwide)</span></span>

<span data-ttu-id="cc010-105">您可以在[microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)的 [**服務健康**情況] 頁面上，查看 microsoft 服務的健康情況，包括網頁上的 Office、YAMMER、Microsoft Dynamics CRM 及行動裝置管理雲端服務。</span><span class="sxs-lookup"><span data-stu-id="cc010-105">You can view the health of your Microsoft services, including Office on the web, Yammer, Microsoft Dynamics CRM, and mobile device management cloud services, on the **Service health** page in the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).</span></span> <span data-ttu-id="cc010-106">如果雲端服務發生問題，在您連絡支援人員或花時間進行疑難排解之前，可以查看服務健康情況，以確定是否為正在開發解決方法的已知問題。</span><span class="sxs-lookup"><span data-stu-id="cc010-106">If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.</span></span>

<span data-ttu-id="cc010-107">如果您無法登入服務入口網站，您可以使用 [ [服務狀態] 頁面](https://status.office365.com) 檢查是否有已知的問題，以防您登入您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="cc010-107">If you are unable to sign in to the service portal, you can use the [service status page](https://status.office365.com) to check for known issues preventing you from logging into your tenant.</span></span>
  
### <a name="how-to-check-service-health"></a><span data-ttu-id="cc010-108">如何查看服務健康情況</span><span class="sxs-lookup"><span data-stu-id="cc010-108">How to check service health</span></span>

1. <span data-ttu-id="cc010-109">移至 Microsoft 365 系統管理中心 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) ，並以系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="cc010-109">Go to the Microsoft 365 admin center at [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339), and sign in with an admin account.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc010-110">被指派全域系統管理員或服務系統管理員角色的人員方可檢視服務健康情況。</span><span class="sxs-lookup"><span data-stu-id="cc010-110">People who are assigned the global admin or service administrator role can view service health.</span></span> <span data-ttu-id="cc010-111">若要允許 Exchange、SharePoint 以及商務用 Skype 管理員檢視服務健康情況，必須同時將服務系統管理員角色指派給他們。</span><span class="sxs-lookup"><span data-stu-id="cc010-111">To allow Exchange, SharePoint, and Skype for Business admins to view service health, they must also be assigned the Service admin role.</span></span> <span data-ttu-id="cc010-112">如需可查看服務健康情況之角色的詳細資訊，請參閱 [關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide#roles-available-in-the-microsoft-365-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="cc010-112">For more information about roles that can view service health, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide#roles-available-in-the-microsoft-365-admin-center).</span></span>
  
2. <span data-ttu-id="cc010-113">如果您不是使用新的系統管理中心，請在 **首頁** 上，選取 [ **嘗試以新系統管理中心** 切換] 右上角。</span><span class="sxs-lookup"><span data-stu-id="cc010-113">If you are not using the new admin center, on the **Home** page, select the **Try the new admin center** toggle in the upper-right corner.</span></span>

3. <span data-ttu-id="cc010-114">若要查看服務健康情況，請在系統管理中心中，移至 [**健康**情況  >  **服務健康**情況]，或選取**首頁儀表板**上的**服務健康**情況卡片。</span><span class="sxs-lookup"><span data-stu-id="cc010-114">To view service health, in the admin center, go to **Health** > **Service health**, or select the **Service health** card on the **Home dashboard**.</span></span> <span data-ttu-id="cc010-115">儀表板卡會指出是否有主動服務問題，以及詳細的 **服務健康** 情況頁面連結。</span><span class="sxs-lookup"><span data-stu-id="cc010-115">The dashboard card indicates whether there is an active service issue and links to the detailed **Service health** page.</span></span>
  
4. <span data-ttu-id="cc010-116">在 [ **服務健康** 情況] 頁面上，每個雲端服務的健康狀態是以表格格式顯示。</span><span class="sxs-lookup"><span data-stu-id="cc010-116">On the **Service health** page, the health state of each cloud service is shown in a table format.</span></span>

   ![View of current issues in service health](../media/service-health-all-services.png)

<span data-ttu-id="cc010-118">[ **所有服務** ] 索引標籤 (預設 view) 會顯示所有服務及其目前的健康狀態。</span><span class="sxs-lookup"><span data-stu-id="cc010-118">The **All services** tab (the default view) shows all services and their current health state.</span></span> <span data-ttu-id="cc010-119">圖示及 [ **狀態** ] 欄會指出每項服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="cc010-119">An icon and the **Status** column indicate the state of each service.</span></span> 

<span data-ttu-id="cc010-120">若要將您的視圖篩選為目前出現事件的服務，請選取頁面頂端的 [ **事件** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cc010-120">To filter your view to services currently experiencing an incident, select the **Incidents** tab at the top of the page.</span></span> <span data-ttu-id="cc010-121">選取 [ **建議** ] 索引標籤只會顯示目前已發表建議的服務。</span><span class="sxs-lookup"><span data-stu-id="cc010-121">Selecting the **Advisories** tab will show only services that currently have an advisory posted.</span></span> 

<span data-ttu-id="cc010-122">[ **記錄** ] 索引標籤會顯示已解決之事件和提議的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="cc010-122">The **History** tab shows the history of incidents and advisories that have been resolved.</span></span>

<span data-ttu-id="cc010-123">如果您在使用 Microsoft 365 服務時發生問題，但您未在 [ **服務健康** 情況] 頁面上看到該問題，請選取 [ **報告問題**]，然後完成簡寫表單來告訴我們。</span><span class="sxs-lookup"><span data-stu-id="cc010-123">If you're experiencing an issue with a Microsoft 365 service and you don’t see it listed on the **Service health** page, tell us about it by selecting **Report an issue**, and completing the short form.</span></span> <span data-ttu-id="cc010-124">我們將從其他組織查看相關資料和報告，以查看問題的程度，以及是否與我們的服務有關。</span><span class="sxs-lookup"><span data-stu-id="cc010-124">We’ll look at related data and reports from other organizations to see how widespread the issue is, and if it originated with our service.</span></span> <span data-ttu-id="cc010-125">如果是的話，我們會將其新增為 [ **服務健康** 情況] 頁面上的新事件或建議，您可以在這裡追蹤其解決方法。</span><span class="sxs-lookup"><span data-stu-id="cc010-125">If it did, we’ll add it as a new incident or advisory on the **Service health** page, where you can track its resolution.</span></span> <span data-ttu-id="cc010-126">如果您在大約30分鐘內沒有看到它出現在清單中，請考慮與支援人員聯繫以解決問題。</span><span class="sxs-lookup"><span data-stu-id="cc010-126">If you don’t see it appear on the list within about 30 minutes, consider contacting support to resolve the issue.</span></span>

<span data-ttu-id="cc010-127">若要註冊影響您租使用者的新事件的電子郵件通知，以及對使用中事件的狀態變更，請選取 [ **喜好**設定]，按一下 [ **以電子郵件傳送我的服務 heath 通知**]，然後指定：</span><span class="sxs-lookup"><span data-stu-id="cc010-127">To sign up for email notifications of new incidents that affect your tenant and status changes for an active incident, select **Preferences**, click **Send me service heath notifications in email**, and then specify:</span></span>

- <span data-ttu-id="cc010-128">最多兩個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cc010-128">Up to two email addresses.</span></span>
- <span data-ttu-id="cc010-129">您是否需要事件或建議的通知</span><span class="sxs-lookup"><span data-stu-id="cc010-129">Whether you want notifications for incidents or advisories</span></span>
- <span data-ttu-id="cc010-130">您要通知的服務</span><span class="sxs-lookup"><span data-stu-id="cc010-130">The services for which you want notification</span></span>

> [!NOTE]
> <span data-ttu-id="cc010-131">每個系統管理員都可以設定其偏好設定，而每個系統管理員帳戶的上述限制為兩個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cc010-131">Each admin can have their Preferences set and the above limit of two email address is per admin account.</span></span>

> [!TIP]
> <span data-ttu-id="cc010-132">您也可以在行動裝置上使用 [Microsoft 365 系統管理應用程式](https://go.microsoft.com/fwlink/p/?linkid=627216) 來查看服務健康情況，這是使用推播通知保持最新狀態的絕佳方式。</span><span class="sxs-lookup"><span data-stu-id="cc010-132">You can also use the [Microsoft 365 Admin app](https://go.microsoft.com/fwlink/p/?linkid=627216) on your mobile device to view Service health, which is a great way to stay current with push notifications.</span></span> 
  
### <a name="view-details-of-posted-service-health"></a><span data-ttu-id="cc010-133">檢視已張貼的服務健康情況詳細資料</span><span class="sxs-lookup"><span data-stu-id="cc010-133">View details of posted service health</span></span>

<span data-ttu-id="cc010-134">在 [ **所有服務** ] 視圖上，選取服務狀態將會開啟 [建議] 或 [事件] 的摘要視圖。</span><span class="sxs-lookup"><span data-stu-id="cc010-134">On the **All services** view, selecting the service status will open a summary view of advisories or incidents.</span></span>
  
![顯示服務建議的螢幕擷取畫面](../media/service-health-advisory.png)

<span data-ttu-id="cc010-136">建議或事件摘要會提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="cc010-136">The advisory or incident summary provides the following information:</span></span>

- <span data-ttu-id="cc010-137">**Title** -問題的摘要。</span><span class="sxs-lookup"><span data-stu-id="cc010-137">**Title** - A summary of the problem.</span></span>
- <span data-ttu-id="cc010-138">**服務** -受影響服務的名稱。</span><span class="sxs-lookup"><span data-stu-id="cc010-138">**Service** - The name of the affected service.</span></span>
- <span data-ttu-id="cc010-139">**ID** -問題的數值識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc010-139">**ID** - A numeric identifier for the problem.</span></span>
- <span data-ttu-id="cc010-140">**狀態** -此問題對服務的影響。</span><span class="sxs-lookup"><span data-stu-id="cc010-140">**Status** - How this problem affects the service.</span></span>
- <span data-ttu-id="cc010-141">**開始時間** -問題的開始時間。</span><span class="sxs-lookup"><span data-stu-id="cc010-141">**Start time** - The time when the issue started.</span></span>
- <span data-ttu-id="cc010-142">**上次更新** 時間-上次更新服務狀況訊息的時間。</span><span class="sxs-lookup"><span data-stu-id="cc010-142">**Last updated** - The last time that the service health message was updated.</span></span> <span data-ttu-id="cc010-143">我們會經常發佈訊息，讓您知道我們在套用方案中所進行的進度。</span><span class="sxs-lookup"><span data-stu-id="cc010-143">We post frequent messages to let you know the progress that we're making in applying a solution.</span></span>

<span data-ttu-id="cc010-144">選取 [問題標題] 以查看 [問題詳細資料] 頁面，它會顯示相關問題的詳細資訊，包括在處理方案時所發佈之所有訊息的 [記錄](#history) 。</span><span class="sxs-lookup"><span data-stu-id="cc010-144">Select the issue title to see the issue detail page, which shows more information about the issue, including the [history](#history) of all messages posted while we work on a solution.</span></span>

![顯示問題詳細資料的螢幕擷取畫面](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a><span data-ttu-id="cc010-146">翻譯服務健康情況詳細資料</span><span class="sxs-lookup"><span data-stu-id="cc010-146">Translate service health details</span></span>

<span data-ttu-id="cc010-p108">服務健康情況說明都是即時張貼的資訊，因此不會自動翻譯成您的語言，且服務事件的詳細資料僅提供英文版。若要翻譯說明，請依照以下步驟進行：</span><span class="sxs-lookup"><span data-stu-id="cc010-p108">Because service health explanations are posted in real-time, they are not automatically translated to your language and the details of a service event are in English only. To translate the explanation, follow these steps:</span></span>
  
1. <span data-ttu-id="cc010-149">移至 [Translator](https://www.bing.com/translator/)。</span><span class="sxs-lookup"><span data-stu-id="cc010-149">Go to [Translator](https://www.bing.com/translator/).</span></span>

2. <span data-ttu-id="cc010-150">在 [ **服務健康** 情況] 頁面上，選取事件或建議。</span><span class="sxs-lookup"><span data-stu-id="cc010-150">On the **Service health** page, select an incident or advisory.</span></span> <span data-ttu-id="cc010-151">在 [ **顯示詳細資料**] 下，複製有關問題的文字。</span><span class="sxs-lookup"><span data-stu-id="cc010-151">Under **Show details**, copy the text about the issue.</span></span>

3. <span data-ttu-id="cc010-152">在 [翻譯器] 中，貼上文字，然後選擇 [ **翻譯**]。</span><span class="sxs-lookup"><span data-stu-id="cc010-152">In Translator, paste the text and choose **Translate**.</span></span>

### <a name="definitions"></a><span data-ttu-id="cc010-153">定義</span><span class="sxs-lookup"><span data-stu-id="cc010-153">Definitions</span></span>

<span data-ttu-id="cc010-154">在大部分的情況下，服務會顯示為良好狀態，而不會進一步資訊。</span><span class="sxs-lookup"><span data-stu-id="cc010-154">Most of the time, services will appear as healthy with no further information.</span></span> <span data-ttu-id="cc010-155">如果服務發生問題，系統就會以建議或事件的方式表示發生問題，並顯示目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="cc010-155">When a service is having a problem, the issue is identified as either an advisory or an incident and shows a current status.</span></span>
  
> [!TIP]
> <span data-ttu-id="cc010-156">預定維修事件不會顯示在服務健康情況中。</span><span class="sxs-lookup"><span data-stu-id="cc010-156">Planned maintenance events aren't shown in service health.</span></span> <span data-ttu-id="cc010-157">您可以在 **郵件中心**保持最新狀態，追蹤計畫的維護事件。</span><span class="sxs-lookup"><span data-stu-id="cc010-157">You can track planned maintenance events by staying up to date with the **Message center**.</span></span> <span data-ttu-id="cc010-158">篩選至歸類為「規劃變更」 的訊息，即可了解何時要進行變更、變更的作用以及如何準備因應。</span><span class="sxs-lookup"><span data-stu-id="cc010-158">Filter to messages categorized as Plan for change to find out when the change is going to happen, its effect, and how to prepare for it.</span></span> <span data-ttu-id="cc010-159">如需詳細資訊，請參閱 [消息中心于 Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) 。</span><span class="sxs-lookup"><span data-stu-id="cc010-159">See [Message center in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) for more details.</span></span>
  
### <a name="incidents-and-advisories"></a><span data-ttu-id="cc010-160">事件和建議</span><span class="sxs-lookup"><span data-stu-id="cc010-160">Incidents and advisories</span></span>

| <span data-ttu-id="cc010-161">圖示</span><span class="sxs-lookup"><span data-stu-id="cc010-161">Icon</span></span> | <span data-ttu-id="cc010-162">描述</span><span class="sxs-lookup"><span data-stu-id="cc010-162">Description</span></span> |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|<span data-ttu-id="cc010-p112">如果系統針對某個服務顯示「建議」，表示我們發現了會對部分使用者造成影響的問題，但該服務仍可使用。建議中通常會提供問題的因應措施，且該問題可能是間歇發生，或其波及範圍和對使用者造成的影響並不大。</span><span class="sxs-lookup"><span data-stu-id="cc010-p112">If a service has an advisory shown, we are aware of a problem that is affecting some users, but the service is still available. In an advisory, there is often a workaround to the problem and the problem may be intermittent or is limited in scope and user impact.</span></span>  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|<span data-ttu-id="cc010-p113">如果系統針對某個服務顯示有作用中的「事件」，代表這是一個重大問題，且該服務或其主要功能無法使用。例如，使用者可能無法傳送和接收電子郵件，或者無法登入。事件會對使用者造成明顯影響。當有進行中的事件時，我們會在服務健康情況儀表板中提供更新資訊，讓您掌握調查和移轉作業的進度，以及確認解決方案。</span><span class="sxs-lookup"><span data-stu-id="cc010-p113">If a service has an active incident shown, it's a critical issue and the service or a major function of the service is unavailable. For example, users may be unable to send and receive email or unable to sign-in. Incidents will have noticeable impact to users. When there is an incident in progress, we will provide updates regarding the investigation, mitigation efforts, and confirmation of resolution in the Service health dashboard.</span></span>  <br/> |

### <a name="status-definitions"></a><span data-ttu-id="cc010-171">狀態定義</span><span class="sxs-lookup"><span data-stu-id="cc010-171">Status definitions</span></span>

| <span data-ttu-id="cc010-172">狀態</span><span class="sxs-lookup"><span data-stu-id="cc010-172">Status</span></span> | <span data-ttu-id="cc010-173">定義</span><span class="sxs-lookup"><span data-stu-id="cc010-173">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="cc010-174">**調查**</span><span class="sxs-lookup"><span data-stu-id="cc010-174">**Investigating**</span></span> | <span data-ttu-id="cc010-175">我們已發現潛在問題，正在收集關於其原因和影響範圍的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cc010-175">We're aware of a potential issue and are gathering more information about what's going on and the scope of impact.</span></span> |
|<span data-ttu-id="cc010-176">**服務效能下降**</span><span class="sxs-lookup"><span data-stu-id="cc010-176">**Service degradation**</span></span> | <span data-ttu-id="cc010-p114">我們已確認某個問題可能會對服務或功能的使用造成影響。舉例來說，如果某個服務的執行速度比平常慢、出現間歇性中斷，或者某個功能無法正常運作，您就會看見此狀態。</span><span class="sxs-lookup"><span data-stu-id="cc010-p114">We've confirmed that there is an issue that may affect use of a service or feature. You might see this status if a service is performing more slowly than usual, there are intermittent interruptions, or if a feature isn't working, for example.</span></span> |
|<span data-ttu-id="cc010-179">**服務中斷**</span><span class="sxs-lookup"><span data-stu-id="cc010-179">**Service interruption**</span></span> | <span data-ttu-id="cc010-p115">如果我們判斷某個問題會影響使用者存取服務的能力，您就會看見此狀態。這種情況表示問題相當嚴重，且在相同條件下會固定發生。</span><span class="sxs-lookup"><span data-stu-id="cc010-p115">You'll see this status if we determine that an issue affects the ability for users to access the service. In this case, the issue is significant and can be reproduced consistently.</span></span> |
|<span data-ttu-id="cc010-182">**正在恢復服務**</span><span class="sxs-lookup"><span data-stu-id="cc010-182">**Restoring service**</span></span> | <span data-ttu-id="cc010-183">我們已經找出問題的成因，知道要採取什麼修正動作，且正在讓服務恢復到健康情況良好的狀態。</span><span class="sxs-lookup"><span data-stu-id="cc010-183">The cause of the issue has been identified, we know what corrective action to take, and are in the process of bringing the service back to a healthy state.</span></span> |
|<span data-ttu-id="cc010-184">**擴充的復原**</span><span class="sxs-lookup"><span data-stu-id="cc010-184">**Extended recovery**</span></span> | <span data-ttu-id="cc010-p116">此狀態表示我們正在進行矯正措施，以便為大多數使用者恢復服務，但需要一些時間才能讓所有受影響的系統恢復正常運作。如果我們在尚未進行永久修復期間先採用暫時修正方法以降低影響，您也可能會看到此狀態。</span><span class="sxs-lookup"><span data-stu-id="cc010-p116">This status indicates that corrective action is in progress to restore service to most users but will take some time to reach all the affected systems. You might also see this status if we've made a temporary fix to reduce impact while we wait to apply a permanent fix.</span></span> |
|<span data-ttu-id="cc010-187">**調查暫停**</span><span class="sxs-lookup"><span data-stu-id="cc010-187">**Investigation suspended**</span></span> | <span data-ttu-id="cc010-p117">在我們詳細調查潛在問題後，如果需要客戶提供額外資訊以進行更深入的調查，您就會看到此狀態。如果我們需要您採取行動，我們會告知您我們所需的資料或記錄。</span><span class="sxs-lookup"><span data-stu-id="cc010-p117">If our detailed investigation of a potential issue results in a request for additional information from customers to allow us to investigate further, you'll see this status. If we need you to act, we'll let you know what data or logs we need.</span></span> |
|<span data-ttu-id="cc010-190">**服務已恢復**</span><span class="sxs-lookup"><span data-stu-id="cc010-190">**Service restored**</span></span> | <span data-ttu-id="cc010-p118">我們確認矯正措施已解決根本問題，且服務也已恢復為健康情況良好的狀態。如需了解何處發生錯誤，請檢視問題詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cc010-p118">We've confirmed that corrective action has resolved the underlying problem and the service has been restored to a healthy state. To find out what went wrong, view the issue details.</span></span> |
|<span data-ttu-id="cc010-193">**False 正值**</span><span class="sxs-lookup"><span data-stu-id="cc010-193">**False positive**</span></span> | <span data-ttu-id="cc010-194">在詳細調查之後，我們已確認服務狀況良好，且如設計方式運作。</span><span class="sxs-lookup"><span data-stu-id="cc010-194">After a detailed investigation, we’ve confirmed the service is healthy and operating as designed.</span></span> <span data-ttu-id="cc010-195">不會對服務的影響，或從服務之外產生事件的原因。</span><span class="sxs-lookup"><span data-stu-id="cc010-195">No impact to the service was observed or the cause of the incident originated outside of the service.</span></span> |
|<span data-ttu-id="cc010-196">**發佈的事件後報告**</span><span class="sxs-lookup"><span data-stu-id="cc010-196">**Post-incident report published**</span></span> | <span data-ttu-id="cc010-197">我們已發佈一個包含根本原因資訊的特定問題的文章附隨報告及後續步驟，以確保不再發生類似的問題。</span><span class="sxs-lookup"><span data-stu-id="cc010-197">We’ve published a Post Incident Report for a specific issue that includes root cause information and next steps to ensure a similar issue doesn’t reoccur.</span></span> |

### <a name="history"></a><span data-ttu-id="cc010-198">歷程記錄</span><span class="sxs-lookup"><span data-stu-id="cc010-198">History</span></span>

<span data-ttu-id="cc010-199">服務健康情況可讓您查看目前的健全狀態，並查看過去30天內，對租使用者造成影響的任何服務建議和事件的記錄。</span><span class="sxs-lookup"><span data-stu-id="cc010-199">Service health lets you look at current health status and view the history of any service advisories and incidents that have affected your tenant in the past 30 days.</span></span> <span data-ttu-id="cc010-200">若要查看所有服務的過去狀況，請選取 [問題詳細資料] 頁面上的 [ **查看歷史記錄** ]。</span><span class="sxs-lookup"><span data-stu-id="cc010-200">To view the past health of all services, select **View history** on the issue detail page.</span></span>
  
![Show link to health history](../media/service-health-view-history.png)
  
<span data-ttu-id="cc010-202">系統就會以清單顯示在所選時間範圍內張貼的所有服務健康情況訊息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc010-202">A list of all service health messages posted in the selected timeframe is displayed, as shown below:</span></span>
  
![View service health history](../media/service-health-history.png)
  
<span data-ttu-id="cc010-204">展開任何列，以查看有關問題的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cc010-204">Expand any row to view more details about the issue.</span></span>
  
<span data-ttu-id="cc010-205">如需關於我們工作時間承諾的詳細資訊，請參閱 [來自 Microsoft 365 的透明作業](https://go.microsoft.com/fwlink/?linkid=848695)。</span><span class="sxs-lookup"><span data-stu-id="cc010-205">For more information about our commitment to uptime, see [Transparent operations from Microsoft 365](https://go.microsoft.com/fwlink/?linkid=848695).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc010-206">相關主題</span><span class="sxs-lookup"><span data-stu-id="cc010-206">Related topics</span></span>

<span data-ttu-id="cc010-207">[Microsoft 365 系統管理中心](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 的活動報告[訊息中心喜好](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide#preferences11)設定</span><span class="sxs-lookup"><span data-stu-id="cc010-207">[Activity Reports in the Microsoft 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
[Message center Preferences](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide#preferences11)</span></span>