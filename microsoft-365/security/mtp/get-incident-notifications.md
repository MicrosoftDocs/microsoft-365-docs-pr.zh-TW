---
title: 在 Microsoft 365 Defender 中取得事件通知
description: 瞭解如何建立規則，以在 Microsoft 365 Defender 中取得事件的電子郵件通知
keywords: 事件，電子郵件，電子郵件 notfications，設定，使用者，信箱，電子郵件，事件
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848888"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="46a2e-104">透過電子郵件取得事件通知</span><span class="sxs-lookup"><span data-stu-id="46a2e-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="46a2e-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="46a2e-105">**Applies to:**</span></span>
- <span data-ttu-id="46a2e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46a2e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="46a2e-107">您可以設定 Microsoft 365 Defender 以透過電子郵件通知您每次現有的事件發生新的事件或新的更新。</span><span class="sxs-lookup"><span data-stu-id="46a2e-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="46a2e-108">您可以選擇根據事件嚴重性或設備群組來取得通知。</span><span class="sxs-lookup"><span data-stu-id="46a2e-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="46a2e-109">您也可以選擇只在每個事件第一個更新時取得通知。</span><span class="sxs-lookup"><span data-stu-id="46a2e-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="46a2e-110">您可以在電子郵件通知中新增或移除收件者。</span><span class="sxs-lookup"><span data-stu-id="46a2e-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="46a2e-111">新增的收件者會在新增事件後收到相關通知。</span><span class="sxs-lookup"><span data-stu-id="46a2e-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="46a2e-112">電子郵件通知包含有關事件的重要詳細資料，例如事件名稱、嚴重性和類別，以及其他。</span><span class="sxs-lookup"><span data-stu-id="46a2e-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="46a2e-113">您也可以直接移至 [事件]，以便立即開始調查。</span><span class="sxs-lookup"><span data-stu-id="46a2e-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="46a2e-114">如需調查事件的詳細資訊，請參閱 [調查 Microsoft 365 Defender 中的事件](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)。</span><span class="sxs-lookup"><span data-stu-id="46a2e-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="46a2e-115">您必須具有「管理安全性設定」許可權，才可設定電子郵件通知設定。</span><span class="sxs-lookup"><span data-stu-id="46a2e-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="46a2e-116">如果您已選擇使用基本版權管理，具有安全性管理員或全域系統管理員角色的使用者便可為您設定電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="46a2e-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="46a2e-117">同樣地，如果您的組織使用角色型存取控制 (RBAC) ，您可以根據允許管理的裝置群組，只建立、編輯、刪除和接收通知。</span><span class="sxs-lookup"><span data-stu-id="46a2e-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="46a2e-118">建立事件通知的規則</span><span class="sxs-lookup"><span data-stu-id="46a2e-118">Create rules for incident notifications</span></span>

<span data-ttu-id="46a2e-119">若要設定第一筆電子郵件通知的事件，請建立新的規則，並自訂電子郵件通知設定。</span><span class="sxs-lookup"><span data-stu-id="46a2e-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="46a2e-120">在功能窗格中，選取 [**設定**  >  **事件的電子郵件通知**]。</span><span class="sxs-lookup"><span data-stu-id="46a2e-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="46a2e-121">選取 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="46a2e-121">Select **Add item**.</span></span>
3. <span data-ttu-id="46a2e-122">在 [ **名稱** ] 中為規則命名，並提供 **描述**。</span><span class="sxs-lookup"><span data-stu-id="46a2e-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![建立事件電子郵件 notifs 的規則視窗](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="46a2e-124">選取 **[下一步]** 移至 [ **通知設定**]。</span><span class="sxs-lookup"><span data-stu-id="46a2e-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="46a2e-125">您可以在這裡指定：</span><span class="sxs-lookup"><span data-stu-id="46a2e-125">Here you can specify:</span></span>
    - <span data-ttu-id="46a2e-126">**警示嚴重性** -選擇會觸發事件通知的警示嚴重性。</span><span class="sxs-lookup"><span data-stu-id="46a2e-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="46a2e-127">例如，如果您只想知道高嚴重性事件，請選取 [高]。</span><span class="sxs-lookup"><span data-stu-id="46a2e-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="46a2e-128">**裝置群組範圍** -此下拉式清單顯示使用者可以存取的所有裝置群組。</span><span class="sxs-lookup"><span data-stu-id="46a2e-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="46a2e-129">選取您要為其建立事件通知規則的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="46a2e-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="46a2e-130">**僅在每個事件第一次發生時發出通知** -選取此選項只會在第一個符合其他選擇的警示上傳送電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="46a2e-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="46a2e-131">稍後與該事件相關的更新或警示將不會觸發通知。</span><span class="sxs-lookup"><span data-stu-id="46a2e-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="46a2e-132">**包含組織名稱** -指出客戶名稱是否會出現在電子郵件通知中。</span><span class="sxs-lookup"><span data-stu-id="46a2e-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="46a2e-133">**包含租使用者專用的入口網站連結** -新增具有租使用者識別碼的連結，以允許存取特定租使用者。</span><span class="sxs-lookup"><span data-stu-id="46a2e-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![事件電子郵件 notifs 的 Notif 設定視窗](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="46a2e-135">選取 **[下一步]** 移至 [收件者]**區段。**</span><span class="sxs-lookup"><span data-stu-id="46a2e-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="46a2e-136">在這裡，您可以指定會收到事件電子郵件通知的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="46a2e-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="46a2e-137">在輸入每個電子郵件地址後，選取 [ **新增收件** 者]。</span><span class="sxs-lookup"><span data-stu-id="46a2e-137">Select **Add a recipient** after typing every email address.</span></span>

    ![新增事件電子郵件 notifs 的收件者視窗](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="46a2e-139">最後，選取 **[下一步]** 以 **查看規則** ，這樣您就能看到與新規則相關聯的所有設定。</span><span class="sxs-lookup"><span data-stu-id="46a2e-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="46a2e-140">收件者會開始透過電子郵件以設定為基礎來接收事件通知。</span><span class="sxs-lookup"><span data-stu-id="46a2e-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="46a2e-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="46a2e-141">See also</span></span>
- [<span data-ttu-id="46a2e-142">Microsoft 365 Defender 中的事件概述</span><span class="sxs-lookup"><span data-stu-id="46a2e-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="46a2e-143">設定 Microsoft 365 Defender 中的事件優先順序</span><span class="sxs-lookup"><span data-stu-id="46a2e-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="46a2e-144">調查 Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="46a2e-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

