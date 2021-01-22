---
title: 在 Microsoft 365 Defender 中取得事件通知
description: 瞭解如何在 Microsoft 365 Defender 中建立規則以取得事件的電子郵件通知
keywords: 事件、電子郵件、電子郵件通知、設定、使用者、信箱、電子郵件、事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9db025818fdd5eb2635a9a676e4a10e20f3036b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930975"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="d5c0c-104">以電子郵件取得事件通知</span><span class="sxs-lookup"><span data-stu-id="d5c0c-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d5c0c-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="d5c0c-105">**Applies to:**</span></span>
- <span data-ttu-id="d5c0c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5c0c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d5c0c-107">您可以設定 Microsoft 365 Defender，每當有新事件或現有事件的更新時，都會以電子郵件通知您。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="d5c0c-108">您可以選擇根據事件嚴重性或裝置群組來取得通知。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="d5c0c-109">您也可以選擇只在每個事件的第一次更新時收到通知。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="d5c0c-110">您可以在電子郵件通知中新增或移除收件者。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="d5c0c-111">新增的收件者在新增事件後會收到事件通知。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="d5c0c-112">電子郵件通知包含事件的重要詳細資料，例如事件名稱、嚴重性和類別等等。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="d5c0c-113">您也可以直接前往事件，以便立即開始調查。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="d5c0c-114">有關調查事件的更多資訊，請參閱 [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)中的調查事件。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="d5c0c-115">您需要有管理安全性設定的許可權，才能設定電子郵件通知設定。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="d5c0c-116">如果您選擇使用基本版權管理，具有安全性系統管理員或全域系統管理員角色的使用者可以設定電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="d5c0c-117">同樣地，如果貴組織是使用角色型存取控制 (RBAC) ，則只能根據您允許管理的裝置群組來建立、編輯、刪除及接收通知。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="d5c0c-118">建立事件通知規則</span><span class="sxs-lookup"><span data-stu-id="d5c0c-118">Create rules for incident notifications</span></span>

<span data-ttu-id="d5c0c-119">若要設定事件的第一封電子郵件通知，請建立新規則並自訂電子郵件通知設定。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="d5c0c-120">在功能窗格中，選取 **設定**  >  **事件電子郵件通知**。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="d5c0c-121">選取 **新增專案**。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-121">Select **Add item**.</span></span>
3. <span data-ttu-id="d5c0c-122">在名稱中為規則 **命名，** 並提供 **描述**。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![事件電子郵件通知的建立規則視窗](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="d5c0c-124">選取 **下一** 步以前往 **通知設定**。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="d5c0c-125">您可以在此處指定：</span><span class="sxs-lookup"><span data-stu-id="d5c0c-125">Here you can specify:</span></span>
    - <span data-ttu-id="d5c0c-126">**警示嚴重性** - 選擇會觸發事件通知的警示嚴重性。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="d5c0c-127">例如，如果您只想通知高嚴重性事件，請選取 [高。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="d5c0c-128">**裝置群組範圍** - 此下拉式清單會顯示使用者可以存取的所有裝置群組。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="d5c0c-129">選取要建立事件通知規則的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="d5c0c-130">**只會在每個事件第** 一次出現時通知 - 選取此選項只會在符合您其他選項的第一個通知上傳送電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="d5c0c-131">之後與事件相關的更新或警示不會觸發通知。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="d5c0c-132">**包含組織名稱** - 指出客戶名稱是否顯示在電子郵件通知上。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="d5c0c-133">**包含租使用者專用入口網站連結** -新增包含租使用者識別碼的連結，以允許存取特定租使用者。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![事件電子郵件的 Notif 設定視窗](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="d5c0c-135">選取 **下一** 步以前往收 **件者** 區段。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="d5c0c-136">您可以在此處指定將接收事件電子郵件通知的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="d5c0c-137">輸入 **每個電子郵件地址之後** ，選取新增收件者。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-137">Select **Add a recipient** after typing every email address.</span></span>

    ![事件電子郵件的新增收件者視窗](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="d5c0c-139">最後，選取 **下一** 步以前往檢查 **規則** ，以便查看所有與新規則相關聯的設定。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="d5c0c-140">收件者會開始根據設定，透過電子郵件接收事件通知。</span><span class="sxs-lookup"><span data-stu-id="d5c0c-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5c0c-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d5c0c-141">See also</span></span>
- [<span data-ttu-id="d5c0c-142">Microsoft 365 Defender 中的事件概觀</span><span class="sxs-lookup"><span data-stu-id="d5c0c-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="d5c0c-143">在 Microsoft 365 Defender 中排列事件的優先順序</span><span class="sxs-lookup"><span data-stu-id="d5c0c-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="d5c0c-144">調查 Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="d5c0c-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

