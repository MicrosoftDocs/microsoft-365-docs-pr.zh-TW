---
title: 在 Microsoft Defender for Endpoint 中設定警示通知
description: 您可以使用 Microsoft Defender for Endpoint，根據嚴重性和其他準則，設定安全性警示的電子郵件通知設定。
keywords: 電子郵件通知，設定警示通知，microsoft defender for endpoint，microsoft defender for endpoint 通知，microsoft defender for endpoint alert，windows 10 企業版，windows 10 教育版
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b629d6a90931026ce28ce241e74d490ce67c6962
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893623"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="af8ff-104">在 Microsoft Defender for Endpoint 中設定警示通知</span><span class="sxs-lookup"><span data-stu-id="af8ff-104">Configure alert notifications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af8ff-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="af8ff-105">**Applies to:**</span></span>
- [<span data-ttu-id="af8ff-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="af8ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="af8ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af8ff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="af8ff-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="af8ff-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="af8ff-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="af8ff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="af8ff-110">您可以將 Defender for Endpoint 設定為將電子郵件通知傳送給指定的收件者，以取得新的提醒。</span><span class="sxs-lookup"><span data-stu-id="af8ff-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="af8ff-111">這項功能可讓您找出會立即獲得通知的個人群組，並根據其嚴重性採取行動。</span><span class="sxs-lookup"><span data-stu-id="af8ff-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="af8ff-112">只有具有「管理安全性設定」許可權的使用者才能設定電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="af8ff-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="af8ff-113">如果您已選擇使用基本版權管理，具有安全性管理員或全域系統管理員角色的使用者便可以設定電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="af8ff-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="af8ff-114">您可以設定觸發通知的警示嚴重性層級。</span><span class="sxs-lookup"><span data-stu-id="af8ff-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="af8ff-115">您也可以新增或移除電子郵件通知的收件者。</span><span class="sxs-lookup"><span data-stu-id="af8ff-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="af8ff-116">新增的收件者會在新增通知之後通知您。</span><span class="sxs-lookup"><span data-stu-id="af8ff-116">New recipients get notified about alerts triggered after they're added.</span></span> <span data-ttu-id="af8ff-117">如需提醒的詳細資訊，請參閱 [查看和組織警示佇列](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="af8ff-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="af8ff-118">如果您是使用角色型存取控制 (RBAC) ，收件者只會根據通知規則中設定的裝置群組來接收通知。</span><span class="sxs-lookup"><span data-stu-id="af8ff-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="af8ff-119">具有適當許可權的使用者只能建立、編輯或刪除局限于其裝置群組管理範圍的通知。</span><span class="sxs-lookup"><span data-stu-id="af8ff-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="af8ff-120">只有指派給全域系統管理員角色的使用者才可以管理為所有裝置群組設定的通知規則。</span><span class="sxs-lookup"><span data-stu-id="af8ff-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="af8ff-121">電子郵件通知包含有關警示的基本資訊，以及可以進行進一步調查之入口網站的連結。</span><span class="sxs-lookup"><span data-stu-id="af8ff-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>


## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="af8ff-122">建立警示通知的規則</span><span class="sxs-lookup"><span data-stu-id="af8ff-122">Create rules for alert notifications</span></span>
<span data-ttu-id="af8ff-123">您可以建立規則來決定裝置及警示嚴重性，以傳送電子郵件通知及通知收件者。</span><span class="sxs-lookup"><span data-stu-id="af8ff-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="af8ff-124">在功能窗格中，選取 [**設定**  >  **電子郵件通知**]。</span><span class="sxs-lookup"><span data-stu-id="af8ff-124">In the navigation pane, select **Settings** > **Email notifications**.</span></span>

2. <span data-ttu-id="af8ff-125">按一下 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="af8ff-125">Click **Add item**.</span></span>

3. <span data-ttu-id="af8ff-126">指定一般資訊：</span><span class="sxs-lookup"><span data-stu-id="af8ff-126">Specify the General information:</span></span>
    - <span data-ttu-id="af8ff-127">**規則名稱** -指定通知規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="af8ff-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="af8ff-128">**包含組織名稱** -指定電子郵件通知上顯示的客戶名稱。</span><span class="sxs-lookup"><span data-stu-id="af8ff-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="af8ff-129">**包含租使用者專用的入口網站連結** -新增具有租使用者識別碼的連結，以允許存取特定租使用者。</span><span class="sxs-lookup"><span data-stu-id="af8ff-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="af8ff-130">**包含裝置資訊** -包括電子郵件警示內文中的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="af8ff-130">**Include device information** - Includes the device name in the email alert body.</span></span>
    
        >[!NOTE]
        > <span data-ttu-id="af8ff-131">此資訊可能會由收件者郵件伺服器處理，而不是在您為您的 Defender for Endpoint data 選取的地理位置中進行 ar。</span><span class="sxs-lookup"><span data-stu-id="af8ff-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="af8ff-132">**裝置** -選擇是否要將收件者的警示通知給收件者 (全域系統管理員角色只) 或選取的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="af8ff-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="af8ff-133">如需詳細資訊，請參閱 [Create and manage device groups](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="af8ff-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="af8ff-134">**警示嚴重性** -選擇警示嚴重性層級。</span><span class="sxs-lookup"><span data-stu-id="af8ff-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="af8ff-135">按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="af8ff-135">Click **Next**.</span></span>
    
5. <span data-ttu-id="af8ff-136">輸入收件者的電子郵件地址，然後按一下 [ **新增收件** 者]。</span><span class="sxs-lookup"><span data-stu-id="af8ff-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="af8ff-137">您可以新增多個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="af8ff-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="af8ff-138">選取 [ **傳送測試電子郵件**]，檢查電子郵件收件者是否可接收電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="af8ff-138">Check that email recipients can receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="af8ff-139">按一下 [ **儲存通知規則**]。</span><span class="sxs-lookup"><span data-stu-id="af8ff-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="af8ff-140">編輯通知規則</span><span class="sxs-lookup"><span data-stu-id="af8ff-140">Edit a notification rule</span></span>
1. <span data-ttu-id="af8ff-141">選取您想要編輯的通知規則。</span><span class="sxs-lookup"><span data-stu-id="af8ff-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="af8ff-142">更新 [一般] 和 [收件者] 索引標籤資訊。</span><span class="sxs-lookup"><span data-stu-id="af8ff-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="af8ff-143">按一下 [ **儲存通知規則**]。</span><span class="sxs-lookup"><span data-stu-id="af8ff-143">Click **Save notification rule**.</span></span>


## <a name="delete-notification-rule"></a><span data-ttu-id="af8ff-144">刪除通知規則</span><span class="sxs-lookup"><span data-stu-id="af8ff-144">Delete notification rule</span></span>

1. <span data-ttu-id="af8ff-145">選取您想要刪除的通知規則。</span><span class="sxs-lookup"><span data-stu-id="af8ff-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="af8ff-146">按一下 [刪除]。</span><span class="sxs-lookup"><span data-stu-id="af8ff-146">Click **Delete**.</span></span>


## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="af8ff-147">疑難排解提醒電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="af8ff-147">Troubleshoot email notifications for alerts</span></span>
<span data-ttu-id="af8ff-148">本節列出使用提醒電子郵件通知時可能會遇到的各種問題。</span><span class="sxs-lookup"><span data-stu-id="af8ff-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="af8ff-149">**問題：** 「預定收件者」報告他們不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="af8ff-149">**Problem:** Intended recipients report they're not getting the notifications.</span></span>

<span data-ttu-id="af8ff-150">**解決方案：** 請確定電子郵件篩選器沒有封鎖通知：</span><span class="sxs-lookup"><span data-stu-id="af8ff-150">**Solution:** Make sure that the notifications aren't blocked by email filters:</span></span>

1. <span data-ttu-id="af8ff-151">檢查 [Defender for Endpoint email] 通知是否未傳送至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="af8ff-151">Check that the Defender for Endpoint email notifications aren't sent to the Junk Email folder.</span></span> <span data-ttu-id="af8ff-152">將它們標示為非垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="af8ff-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="af8ff-153">請檢查您的電子郵件安全性產品未阻止來自 Defender for Endpoint 的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="af8ff-153">Check that your email security product isn't blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="af8ff-154">請檢查您的電子郵件應用程式規則，可能會為您的 Defender 寄出或移動您的 Defender 電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="af8ff-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af8ff-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="af8ff-155">Related topics</span></span>
- [<span data-ttu-id="af8ff-156">更新資料保留設定</span><span class="sxs-lookup"><span data-stu-id="af8ff-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="af8ff-157">設定進階功能</span><span class="sxs-lookup"><span data-stu-id="af8ff-157">Configure advanced features</span></span>](advanced-features.md)
