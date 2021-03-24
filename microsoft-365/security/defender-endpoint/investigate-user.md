---
title: 調查 Microsoft Defender ATP 中的使用者帳戶
description: 調查使用者帳戶在調查期間，是否有可能遭到破壞的認證或在關聯的使用者帳戶上轉動。
keywords: 調查、帳戶、使用者、使用者實體、警示、microsoft defender atp
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e994069220d8f88f1b8910413ad86da399c4a8f3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058408"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="cd208-104">調查 Microsoft Defender for Endpoint 中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="cd208-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cd208-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="cd208-105">**Applies to:**</span></span>
- [<span data-ttu-id="cd208-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cd208-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="cd208-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd208-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="cd208-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="cd208-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cd208-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="cd208-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="cd208-110">調查使用者帳戶實體</span><span class="sxs-lookup"><span data-stu-id="cd208-110">Investigate user account entities</span></span>

<span data-ttu-id="cd208-111">識別具有最活躍之警示的使用者帳戶， (在儀表板上顯示為「面臨危險的使用者」 ) 並調查可能已遭破壞之憑證的案例，或在調查警示或裝置以找出裝置與該使用者帳戶間可能的側面移動時，在相關聯的使用者帳戶上進行資料透視。</span><span class="sxs-lookup"><span data-stu-id="cd208-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="cd208-112">您可以在下列視圖中尋找使用者帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="cd208-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="cd208-113">儀表板</span><span class="sxs-lookup"><span data-stu-id="cd208-113">Dashboard</span></span>
- <span data-ttu-id="cd208-114">警示佇列</span><span class="sxs-lookup"><span data-stu-id="cd208-114">Alert queue</span></span>
- <span data-ttu-id="cd208-115">裝置詳細資料頁面</span><span class="sxs-lookup"><span data-stu-id="cd208-115">Device details page</span></span>

<span data-ttu-id="cd208-116">在這些視圖中可以使用可按一下的使用者帳戶連結，這樣將會帶您前往 [使用者帳戶詳細資料] 頁面，以顯示更多關於使用者帳戶的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cd208-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="cd208-117">當您調查使用者帳戶實體時，您會看到：</span><span class="sxs-lookup"><span data-stu-id="cd208-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="cd208-118">使用者帳戶詳細資料、Azure 高級威脅防護 (Azure ATP) 警示，以及登入的裝置、角色、登入類型和其他詳細資料</span><span class="sxs-lookup"><span data-stu-id="cd208-118">User account details, Azure Advanced Threat Protection (Azure ATP) alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="cd208-119">事件和使用者裝置的概述</span><span class="sxs-lookup"><span data-stu-id="cd208-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="cd208-120">與此使用者相關的警示</span><span class="sxs-lookup"><span data-stu-id="cd208-120">Alerts related to this user</span></span>
- <span data-ttu-id="cd208-121">在組織中觀測的 (裝置登入) </span><span class="sxs-lookup"><span data-stu-id="cd208-121">Observed in organization (devices logged on to)</span></span>

![使用者帳戶實體詳細資料頁面的圖像](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="cd208-123">使用者詳細資料</span><span class="sxs-lookup"><span data-stu-id="cd208-123">User details</span></span>

<span data-ttu-id="cd208-124">左側的 **使用者詳細資料** 窗格提供使用者的相關資訊，例如相關的開啟的事件、作用中的警示、SAM 名稱、SID、Azure ATP 警示、使用者登入的裝置數目、角色和登入類型。</span><span class="sxs-lookup"><span data-stu-id="cd208-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Azure ATP alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="cd208-125">視您已啟用的整合功能而定，您將會看到其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cd208-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="cd208-126">例如，如果您啟用商務用 Skype 整合，您就可以從入口網站聯繫使用者。</span><span class="sxs-lookup"><span data-stu-id="cd208-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="cd208-127">**AZURE atp alerts** 區段包含連結，會帶您前往 azure atp 頁面（如果您已啟用 azure atp 功能，且有與使用者相關的警示）。</span><span class="sxs-lookup"><span data-stu-id="cd208-127">The **Azure ATP alerts** section contains a link that will take you to the Azure ATP page, if you have enabled the Azure ATP feature, and there are alerts related to the user.</span></span> <span data-ttu-id="cd208-128">Azure ATP 頁面將提供有關提醒的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cd208-128">The Azure ATP page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="cd208-129">您需要啟用 Azure ATP 和 Defender for Endpoint 上的整合，才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="cd208-129">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="cd208-130">在 [Defender for Endpoint] 中，您可以在 [高級功能] 中啟用這項功能。</span><span class="sxs-lookup"><span data-stu-id="cd208-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="cd208-131">如需如何啟用高級功能的詳細資訊，請參閱 [開啟高級功能](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="cd208-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="cd208-132">組織中的「綜述」、「警示」和「觀察」是不同的索引標籤，可顯示使用者帳戶的各種屬性。</span><span class="sxs-lookup"><span data-stu-id="cd208-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="cd208-133">概觀</span><span class="sxs-lookup"><span data-stu-id="cd208-133">Overview</span></span>

<span data-ttu-id="cd208-134">[ **一覽表** ] 索引標籤會顯示事件詳細資料，以及使用者已登入的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="cd208-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="cd208-135">您可以展開這些功能，以查看每個裝置的登入事件詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cd208-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="cd208-136">警示</span><span class="sxs-lookup"><span data-stu-id="cd208-136">Alerts</span></span>

<span data-ttu-id="cd208-137">[ **警示** ] 索引標籤提供與使用者帳戶相關聯的警示清單。</span><span class="sxs-lookup"><span data-stu-id="cd208-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="cd208-138">此清單是篩選 [佇列](alerts-queue.md)的篩選視圖，顯示使用者內容是選取的使用者帳戶、偵測到最後一個活動的日期、警報的簡短描述、警報的嚴重性、警報的狀態、警報的狀態，以及指派警示的寄件者的相關警示。</span><span class="sxs-lookup"><span data-stu-id="cd208-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="cd208-139">組織中的觀測</span><span class="sxs-lookup"><span data-stu-id="cd208-139">Observed in organization</span></span>

<span data-ttu-id="cd208-140">[ **組織中的觀測** 專案] 索引標籤可讓您指定日期範圍，以查看已登入此使用者的裝置清單。這兩個裝置中，每個裝置的最常見和最少登入記錄的使用者帳戶，以及每個裝置上觀測的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="cd208-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="cd208-141">在 [在組織中所看到的專案] 表格中選取專案會展開專案，並顯示裝置的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cd208-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="cd208-142">直接選取專案內的連結會將您傳送至對應的頁面。</span><span class="sxs-lookup"><span data-stu-id="cd208-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="cd208-143">搜尋特定的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="cd208-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="cd208-144">從 **搜尋** 列下拉式功能表中選取 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="cd208-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="cd208-145">在 [ **搜尋** ] 欄位中輸入使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="cd208-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="cd208-146">按一下搜尋圖示或按 **enter** 鍵。</span><span class="sxs-lookup"><span data-stu-id="cd208-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="cd208-147">會顯示符合查詢文字的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="cd208-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="cd208-148">您將會看到使用者帳戶的網域和名稱、上次看到使用者帳戶時，以及過去30天內所看到之已登入的裝置總數。</span><span class="sxs-lookup"><span data-stu-id="cd208-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="cd208-149">您可以依下列時間週期篩選結果：</span><span class="sxs-lookup"><span data-stu-id="cd208-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="cd208-150">1 天</span><span class="sxs-lookup"><span data-stu-id="cd208-150">1 day</span></span>
- <span data-ttu-id="cd208-151">3天</span><span class="sxs-lookup"><span data-stu-id="cd208-151">3 days</span></span>
- <span data-ttu-id="cd208-152">7 天</span><span class="sxs-lookup"><span data-stu-id="cd208-152">7 days</span></span>
- <span data-ttu-id="cd208-153">30 天</span><span class="sxs-lookup"><span data-stu-id="cd208-153">30 days</span></span>
- <span data-ttu-id="cd208-154">6 個月</span><span class="sxs-lookup"><span data-stu-id="cd208-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="cd208-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="cd208-155">Related topics</span></span>

- [<span data-ttu-id="cd208-156">查看和組織 Microsoft Defender for Endpoint 警示佇列</span><span class="sxs-lookup"><span data-stu-id="cd208-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="cd208-157">管理 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="cd208-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="cd208-158">調查 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="cd208-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="cd208-159">調查與 Defender for Endpoint alert 相關聯的檔案</span><span class="sxs-lookup"><span data-stu-id="cd208-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- <span data-ttu-id="cd208-160">[調查 [Defender for Endpoint Devices] 清單中的裝置](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="cd208-160">[Investigate devices in the Defender for Endpoint Devices list](investigate-machines.md)</span></span>
- [<span data-ttu-id="cd208-161">調查與 Defender for Endpoint alert 相關聯的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cd208-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="cd208-162">調查與 Defender for Endpoint alert 相關聯的網域</span><span class="sxs-lookup"><span data-stu-id="cd208-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
