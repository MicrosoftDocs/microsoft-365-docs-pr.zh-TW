---
title: 適用於 Microsoft 365 的 Exchange Online 監視
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: 在 Microsoft 365 中使用 Exchange Online 監視以取得電子郵件事件或建議的相關資訊。
ms.openlocfilehash: 53dc7f990f57fd8d4da68bd424947676cbf0e85d
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572852"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="62130-103">適用於 Microsoft 365 的 Exchange Online 監視</span><span class="sxs-lookup"><span data-stu-id="62130-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="62130-104">您可以在 Microsoft 365 系統管理中心使用 Exchange Online 監視，監視組織之 Microsoft 365 訂閱的 Exchange 服務健康情況。</span><span class="sxs-lookup"><span data-stu-id="62130-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="62130-105">Exchange Online 監視可為您提供下列類別的事件和建議相關資訊：</span><span class="sxs-lookup"><span data-stu-id="62130-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="62130-106">**基礎結構**：在 Microsoft 擁有的 Microsoft 365 基礎結構中偵測問題，以提供定期更新並解決問題。</span><span class="sxs-lookup"><span data-stu-id="62130-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="62130-107">例如，因為 Exchange 或其他 Microsoft 365 雲端基礎結構問題，導致使用者無法存取 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="62130-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="62130-108">**協力廠商基礎結構**：在組織依賴的協力廠商基礎結構中偵測問題，且需要組織採取措施才能解決。</span><span class="sxs-lookup"><span data-stu-id="62130-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="62130-109">例如，使用者驗證交易會受到協力廠商安全性權杖服務 (STS) 提供者的限制，防止使用者連線到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="62130-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="62130-110">**客戶基礎結構**：在您的組織基礎結構中偵測問題，且需要組織採取措施才能解決。</span><span class="sxs-lookup"><span data-stu-id="62130-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="62130-111">例如，使用者無法存取 Exchange Online，因為他們無法取得由貴組織託管的 STS 提供者提供的驗證權杖，因為該憑證已過期。</span><span class="sxs-lookup"><span data-stu-id="62130-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="62130-112">以下是 Microsoft 365 系統管理中心的 **[服務健康情況]** 頁面範例，可從 [健康情況] > **[服務健康情況]** 進入此頁面。</span><span class="sxs-lookup"><span data-stu-id="62130-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![Microsoft 365 系統管理中心的 [服務健康情況] 頁面](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="62130-114">**[狀態]** 欄的值會根據 Microsoft 所維護的雲端服務，指出服務是否健康或是否有建議或事件發生。</span><span class="sxs-lookup"><span data-stu-id="62130-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="62130-115">**[您的組織和協力廠商問題]** 欄的值指出您組織的基礎結構，或協力廠商軟體影響到您的使用者使用 Exchange Online 的服務健康狀況。</span><span class="sxs-lookup"><span data-stu-id="62130-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="62130-116">*「您」* 必須採取行動才能解決建議或事件。</span><span class="sxs-lookup"><span data-stu-id="62130-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="62130-117">以下是 Microsoft 365 系統管理中心的 **[Exchange Online]** 監視頁面範例，可從 **[健康情況] > [服務健康情況]> [Exchange Online]** 進入此頁面。</span><span class="sxs-lookup"><span data-stu-id="62130-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![Microsoft 365 系統管理中心的 Exchange Online 監視頁面](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="62130-119">使用 **[Exchange Online]** 監視頁面，您可以查看 Exchange Online 服務是否健康，以及是否有任何相關的事件或建議。</span><span class="sxs-lookup"><span data-stu-id="62130-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="62130-120">透過 Exchange Online 監視，您可以查看特定電子郵件案例的服務健康情況，並檢視近即時訊號來判斷案例帶來的影響。</span><span class="sxs-lookup"><span data-stu-id="62130-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="62130-121">需求</span><span class="sxs-lookup"><span data-stu-id="62130-121">Requirements</span></span>

<span data-ttu-id="62130-122">符合以下需求的客戶可以啟用此預覽：</span><span class="sxs-lookup"><span data-stu-id="62130-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="62130-123">組織必須擁有至少 10,000 個授權數，從一或下列產品的組合中：Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="62130-123">Your organization needs to have a license count of at least 10,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="62130-124">例如，您的組織可以擁有 3,000 個 Office 365 E3 授權，以及 8,500 個 Microsoft 365 E5，這樣總計為 11,500 個授權產品即符合資格。</span><span class="sxs-lookup"><span data-stu-id="62130-124">For example, your organization can have 3,000 Office 365 E3 licenses and 8,500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="62130-125">您的組織每月至少需要有 50 位作用中 Exchange Online 使用者</span><span class="sxs-lookup"><span data-stu-id="62130-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="62130-126">使用 Exchange Online 監視，您可以根據電子郵件讀取活動檢視下列電子郵件用戶端的健康情況：</span><span class="sxs-lookup"><span data-stu-id="62130-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="62130-127">Outlook 電腦版</span><span class="sxs-lookup"><span data-stu-id="62130-127">Outlook Desktop</span></span>
- <span data-ttu-id="62130-128">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="62130-128">Outlook on the Web</span></span>
- <span data-ttu-id="62130-129">iOS 和 Android 的原生郵件用戶端</span><span class="sxs-lookup"><span data-stu-id="62130-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="62130-130">iOS 和 Android 版 Outlook 行動裝置應用程式</span><span class="sxs-lookup"><span data-stu-id="62130-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="62130-131">Outlook Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="62130-131">Outlook Mac client</span></span>

<span data-ttu-id="62130-132">對於這些用戶端，您可以根據讀取電子郵件的使用者查看最近 30 分鐘的作用中使用者數量，以及儀表板中的事件和建議數量。</span><span class="sxs-lookup"><span data-stu-id="62130-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="62130-133">這個資料會與前一週相同間隔的資料進行比較，看看是否有問題。</span><span class="sxs-lookup"><span data-stu-id="62130-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="62130-134">作用中使用者計數是由單一活動來計算，例如，使用者讀取電子郵件。</span><span class="sxs-lookup"><span data-stu-id="62130-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="62130-135">僅限活動的最後 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="62130-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="62130-136">您也可以監視下列案例的 Exchange Online 健康情況：</span><span class="sxs-lookup"><span data-stu-id="62130-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="62130-137">**郵件流程**：郵件到達 Microsoft 365 網路後，成功傳遞到信箱而不會有任何延遲的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="62130-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="62130-138">**基本驗證和新式驗證**：在 Exchange Online 服務中成功驗證的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="62130-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![針對郵件傳遞監視 Exchange 健康情況的範例](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="62130-140">對於所有這些案例，關鍵數目是主儀表板中最後 30 分鐘的數目。</span><span class="sxs-lookup"><span data-stu-id="62130-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="62130-141">這些案例中每一個案例的詳細檢視都顯示了與前一週相比，過去 7 天總計 30 分鐘的近即時趨勢。</span><span class="sxs-lookup"><span data-stu-id="62130-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="62130-142">傳送意見反應給我們</span><span class="sxs-lookup"><span data-stu-id="62130-142">Send us feedback</span></span>

<span data-ttu-id="62130-143">有兩種方式可提供意見反應：</span><span class="sxs-lookup"><span data-stu-id="62130-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="62130-144">使用 Microsoft 365 系統管理中心中，每個頁面均提供的 **[提供意見反應]** 選項。</span><span class="sxs-lookup"><span data-stu-id="62130-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="62130-145">針對特定事件或建議，使用 **[此文章是否有幫助?]** 連結提交意見反應。</span><span class="sxs-lookup"><span data-stu-id="62130-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![特定事件或建議的 ](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="62130-148">常見問題集</span><span class="sxs-lookup"><span data-stu-id="62130-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="62130-149">1. 為什麼我在 Microsoft 365 系統管理中心沒看到「Exchange Online 監視」?</span><span class="sxs-lookup"><span data-stu-id="62130-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="62130-150">首先，請確定您已在 Microsoft 365 系統管理中心的 **[首頁]** 頁面上啟用新的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="62130-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="62130-151">然後，確定您符合下列兩個需求：</span><span class="sxs-lookup"><span data-stu-id="62130-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="62130-152">組織必須擁有至少 10,000 個授權數，從一或下列產品的組合中：Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="62130-152">Your organization needs to have a license count of at least 10,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="62130-153">您的組織每月至少需要有 50 位作用中 Exchange Online 使用者</span><span class="sxs-lookup"><span data-stu-id="62130-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="62130-154">如果組織的授權數量少於 10,000 位使用者，且每月作用中使用者少於 50 位，則必須先符合這些需求，才會啟用 Exchange Online 監視。</span><span class="sxs-lookup"><span data-stu-id="62130-154">If the license count for your organization goes below 10,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="62130-155">2. 儀表板中每個用戶端的作用中使用者數太低。</span><span class="sxs-lookup"><span data-stu-id="62130-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="62130-156">我們已將大量的作用中授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="62130-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="62130-157">這代表什麼意思？</span><span class="sxs-lookup"><span data-stu-id="62130-157">What does this mean?</span></span> 

<span data-ttu-id="62130-158">監視中顯示的作用中使用者數是以 30 分鐘為基礎，使用者在該時間內執行功能呼叫的活動。</span><span class="sxs-lookup"><span data-stu-id="62130-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="62130-159">不應將此與使用次數混淆。</span><span class="sxs-lookup"><span data-stu-id="62130-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="62130-160">若要檢視使用次數，請使用 Microsoft 365 系統管理中心的活動報告 (**[報告] > [使用狀況]**)。</span><span class="sxs-lookup"><span data-stu-id="62130-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="62130-161">3. Teams 和 SharePoint 等其他服務是否還有其他監視案例？</span><span class="sxs-lookup"><span data-stu-id="62130-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="62130-162">Microsoft 已在 Microsoft 365 系統管理中心的 [服務健康情況] 儀表板中直接整合了此體驗。</span><span class="sxs-lookup"><span data-stu-id="62130-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="62130-163">這將為 Microsoft 提供擴充其他服務監視案例的機會，而當有最新消息時，我們將予以公佈。</span><span class="sxs-lookup"><span data-stu-id="62130-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="62130-164">4. 針對這項體驗有何正式發行計劃？</span><span class="sxs-lookup"><span data-stu-id="62130-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="62130-165">Microsoft 已在 Microsoft 365 系統管理中心的 **[服務健康情況]** 儀表板中直接整合 Exchange Online 監視功能。</span><span class="sxs-lookup"><span data-stu-id="62130-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="62130-166">透過這項全新的整合體驗，Microsoft 計劃先收集您的意見反應，然後再定義正式發行的計劃。</span><span class="sxs-lookup"><span data-stu-id="62130-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="62130-167">5. 這是免費 (隨附) 或付費 (額外) 功能？</span><span class="sxs-lookup"><span data-stu-id="62130-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="62130-168">這項功能處於公開預覽階段，且僅適用於符合問題 1 中需求的客戶。</span><span class="sxs-lookup"><span data-stu-id="62130-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="62130-169">6. 如何提供意見反應？</span><span class="sxs-lookup"><span data-stu-id="62130-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="62130-170">一般意見反應，請使用 **[Exchange Online]** 監視頁面右下角的 **[提供意見反應]** 圖示。</span><span class="sxs-lookup"><span data-stu-id="62130-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="62130-171">有關事件或建議的意見反應，請使用 **[此文章是否有幫助?]** 連結。</span><span class="sxs-lookup"><span data-stu-id="62130-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="62130-172">7. 顯示活動趨勢的案例資料在哪裡檢測？</span><span class="sxs-lookup"><span data-stu-id="62130-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="62130-173">會在 Exchange Online 服務中檢測資料。</span><span class="sxs-lookup"><span data-stu-id="62130-173">The data is instrumented in the Exchange Online service.</span></span> <span data-ttu-id="62130-174">如果在要求到達 Exchange Online 前發生錯誤，或 Exchange Online 中發生錯誤，則活動訊號將會下降。</span><span class="sxs-lookup"><span data-stu-id="62130-174">If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>

