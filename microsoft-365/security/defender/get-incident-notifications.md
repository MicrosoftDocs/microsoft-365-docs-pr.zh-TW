---
title: 在 Microsoft 365 Defender 中透過電子郵件取得事件通知
description: 瞭解如何建立規則，以在 Microsoft 365 Defender 中取得事件的電子郵件通知
keywords: 事件，電子郵件，電子郵件 notfications，設定，使用者，信箱，電子郵件，事件，分析，回應
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8d29291c63bdc437163feecce8164089d958d71d
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299961"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="09f37-104">透過電子郵件取得事件通知</span><span class="sxs-lookup"><span data-stu-id="09f37-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="09f37-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="09f37-105">**Applies to:**</span></span>
- <span data-ttu-id="09f37-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09f37-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="09f37-107">您可以設定 Microsoft 365 Defender 以透過電子郵件通知員工有關新的事件或更新現有的事件。</span><span class="sxs-lookup"><span data-stu-id="09f37-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="09f37-108">您可以選擇根據下列專案取得通知：</span><span class="sxs-lookup"><span data-stu-id="09f37-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="09f37-109">事件嚴重性。</span><span class="sxs-lookup"><span data-stu-id="09f37-109">Incident severity.</span></span>
- <span data-ttu-id="09f37-110">裝置群組。</span><span class="sxs-lookup"><span data-stu-id="09f37-110">Device group.</span></span>
- <span data-ttu-id="09f37-111">僅限每個事件第一個更新。</span><span class="sxs-lookup"><span data-stu-id="09f37-111">Only on the first update per incident.</span></span>

<span data-ttu-id="09f37-112">電子郵件通知包含有關事件的重要詳細資料，例如事件名稱、嚴重性和類別，以及其他。</span><span class="sxs-lookup"><span data-stu-id="09f37-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="09f37-113">您也可以直接前往該事件，並立即開始進行分析。</span><span class="sxs-lookup"><span data-stu-id="09f37-113">You can also go directly to the incident and start your analysis right away.</span></span> <span data-ttu-id="09f37-114">如需詳細資訊，請參閱 [調查事件](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="09f37-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="09f37-115">您可以在電子郵件通知中新增或移除收件者。</span><span class="sxs-lookup"><span data-stu-id="09f37-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="09f37-116">新增的收件者會在新增事件後收到相關通知。</span><span class="sxs-lookup"><span data-stu-id="09f37-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="09f37-117">您必須具有「管理安全性設定」許可權，才可設定電子郵件通知設定。</span><span class="sxs-lookup"><span data-stu-id="09f37-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="09f37-118">如果您已選擇使用基本版權管理，具有安全性管理員或全域系統管理員角色的使用者便可為您設定電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="09f37-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="09f37-119">同樣地，如果您的組織使用角色型存取控制 (RBAC) ，您可以根據允許管理的裝置群組，只建立、編輯、刪除和接收通知。</span><span class="sxs-lookup"><span data-stu-id="09f37-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="09f37-120">建立電子郵件通知的規則</span><span class="sxs-lookup"><span data-stu-id="09f37-120">Create a rule for email notifications</span></span>

<span data-ttu-id="09f37-121">請遵循下列步驟建立新的規則，並自訂電子郵件通知設定。</span><span class="sxs-lookup"><span data-stu-id="09f37-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="09f37-122">在功能窗格中，選取 [**設定 > Microsoft 365 Defender > 事件電子郵件通知**]。</span><span class="sxs-lookup"><span data-stu-id="09f37-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="09f37-123">選取 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="09f37-123">Select **Add item**.</span></span>
3. <span data-ttu-id="09f37-124">在 [ **基礎** ] 頁面上，輸入規則名稱和描述，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="09f37-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="09f37-125">在 [ **通知設定** ] 頁面上，設定：</span><span class="sxs-lookup"><span data-stu-id="09f37-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="09f37-126">**警示嚴重性** -選擇會觸發事件通知的警示嚴重性。</span><span class="sxs-lookup"><span data-stu-id="09f37-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="09f37-127">例如，如果您只想要知道高嚴重性的事件，請選取 [ **高**]。</span><span class="sxs-lookup"><span data-stu-id="09f37-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="09f37-128">**裝置群組範圍** -您可以指定所有的裝置群組，或從您租使用者中的裝置群組清單中進行選取。</span><span class="sxs-lookup"><span data-stu-id="09f37-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="09f37-129">**僅在每個事件第一次出現** 時，如果您只想要在第一個警示中符合其他選項，請選取 [僅限通知]。</span><span class="sxs-lookup"><span data-stu-id="09f37-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="09f37-130">稍後與該事件相關的更新或警示將不會傳送其他通知。</span><span class="sxs-lookup"><span data-stu-id="09f37-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="09f37-131">**在電子郵件中包含組織名稱** -如果您想要讓組織名稱出現在電子郵件通知中，請選取 [選取]。</span><span class="sxs-lookup"><span data-stu-id="09f37-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="09f37-132">**包含租使用者專用入口網站連結**-如果您想要在電子郵件通知中新增具有租使用者識別碼的連結，以便存取特定 Microsoft 365 租使用者，請選取此連結。</span><span class="sxs-lookup"><span data-stu-id="09f37-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="事件電子郵件通知的通知設定":::

5. <span data-ttu-id="09f37-134">選取 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="09f37-134">Select **Next**.</span></span> <span data-ttu-id="09f37-135">**在 [收** 件者] 頁面上，新增要接收事件通知的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="09f37-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="09f37-136">在輸入每個新的電子郵件地址後，選取 **[新增]** 。</span><span class="sxs-lookup"><span data-stu-id="09f37-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="09f37-137">若要測試通知，並確認收件者在收件匣中收到這些通知，請選取 [ **傳送測試電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="09f37-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="09f37-138">選取 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="09f37-138">Select **Next**.</span></span> <span data-ttu-id="09f37-139">在 [ **檢查規則** ] 頁面上，複查規則的設定，然後選取 [ **建立規則**]。</span><span class="sxs-lookup"><span data-stu-id="09f37-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="09f37-140">收件者會開始透過電子郵件以設定為基礎來接收事件通知。</span><span class="sxs-lookup"><span data-stu-id="09f37-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="09f37-141">若要編輯現有規則，請從規則清單中進行選取。</span><span class="sxs-lookup"><span data-stu-id="09f37-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="09f37-142">在具有規則名稱的窗格上，選取 [ **編輯規則** ]，然後在 [ **基本** 設定]、[ **通知設定**] 及 [收件者 **] 頁面上** 進行變更。</span><span class="sxs-lookup"><span data-stu-id="09f37-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="09f37-143">若要編輯現有規則，請從規則清單中進行選取。</span><span class="sxs-lookup"><span data-stu-id="09f37-143">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="09f37-144">在具有規則名稱的窗格上，選取 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="09f37-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="09f37-145">請參閱</span><span class="sxs-lookup"><span data-stu-id="09f37-145">See also</span></span>
- [<span data-ttu-id="09f37-146">事件概觀</span><span class="sxs-lookup"><span data-stu-id="09f37-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="09f37-147">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="09f37-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="09f37-148">調查事件</span><span class="sxs-lookup"><span data-stu-id="09f37-148">Investigate incidents</span></span>](investigate-incidents.md)
