---
title: 建立並追蹤透過 ServiceNow 票證
description: Microsoft 365 安全性中心正在增強原本建立並追蹤票證中 ServiceNow 的能力。 這可讓安全性管理員安全分數建議直接傳送到 ServiceNow 並建立票證。
keywords: 安全性，Microsoft 365，M365，安全分數，安全性中心、 ServiceNow、 票證，工作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350326"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="df08e-105">管理透過 ServiceNow 票證</span><span class="sxs-lookup"><span data-stu-id="df08e-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="df08e-106">Microsoft 365 安全性中心正在增強原本建立並追蹤票證中 ServiceNow 的能力。</span><span class="sxs-lookup"><span data-stu-id="df08e-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="df08e-107">這可讓[Microsoft 安全分數](microsoft-secure-score.md)改進巨集指令直接傳送到 ServiceNow 並建立票證安全性系統管理員。</span><span class="sxs-lookup"><span data-stu-id="df08e-107">This allows security administrators to send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="df08e-108">您可以建立兩個事件管理和變更管理票證。</span><span class="sxs-lookup"><span data-stu-id="df08e-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df08e-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="df08e-109">Prerequisites</span></span>

<span data-ttu-id="df08e-110">可以在 Microsoft 365 安全性中心及以 ServiceNow 執行個體的存取：</span><span class="sxs-lookup"><span data-stu-id="df08e-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="df08e-111">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="df08e-111">Kingston or higher version</span></span>
* <span data-ttu-id="df08e-112">具有系統管理員 HI 認證</span><span class="sxs-lookup"><span data-stu-id="df08e-112">Have admin HI credentials</span></span>
* <span data-ttu-id="df08e-113">在您的目標廠商執行個體上有系統管理員權限</span><span class="sxs-lookup"><span data-stu-id="df08e-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="df08e-114">ServiceNow 建議使用者保留超出] 方塊中的設定 （預設值） ServiceNow 執行個體。</span><span class="sxs-lookup"><span data-stu-id="df08e-114">ServiceNow recommends users keep out of the box settings (default) in your ServiceNow instance.</span></span>  <span data-ttu-id="df08e-115">具有自訂項目可能會造成錯誤中完成安裝檢查清單並與 Microsoft 365 安全性中心整合。</span><span class="sxs-lookup"><span data-stu-id="df08e-115">Having customizations could cause errors in completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="df08e-116">資料交換</span><span class="sxs-lookup"><span data-stu-id="df08e-116">Data exchange</span></span>

<span data-ttu-id="df08e-117">當您在 Microsoft 365 安全性中心連線至 ServiceNow 時，Microsoft 將會收到下列額外的資料：</span><span class="sxs-lookup"><span data-stu-id="df08e-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft will be receiving the following additional data:</span></span>

* <span data-ttu-id="df08e-118">ServiceNow 執行個體名稱</span><span class="sxs-lookup"><span data-stu-id="df08e-118">ServiceNow instance name</span></span>
* <span data-ttu-id="df08e-119">ServiceNow 用戶端識別碼</span><span class="sxs-lookup"><span data-stu-id="df08e-119">ServiceNow client ID</span></span>
* <span data-ttu-id="df08e-120">ServiceNow 用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="df08e-120">ServiceNow client secret</span></span>
* <span data-ttu-id="df08e-121">ServiceNow 存取 & 重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="df08e-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="df08e-122">當您建立 ServiceNow 票證從 Microsoft 365 安全性中心下列資料傳送至 ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="df08e-122">When you create a ServiceNow ticket from the Microsoft 365 security center the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="df08e-123">初始化票證架設的使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="df08e-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="df08e-124">任務名稱</span><span class="sxs-lookup"><span data-stu-id="df08e-124">Task name</span></span>
* <span data-ttu-id="df08e-125">工作描述</span><span class="sxs-lookup"><span data-stu-id="df08e-125">Task description</span></span>
* <span data-ttu-id="df08e-126">優先順序</span><span class="sxs-lookup"><span data-stu-id="df08e-126">Priority</span></span>
* <span data-ttu-id="df08e-127">到期日</span><span class="sxs-lookup"><span data-stu-id="df08e-127">Due date</span></span>
* <span data-ttu-id="df08e-128">建議來源 （使用者建議或 Microsoft 建議）</span><span class="sxs-lookup"><span data-stu-id="df08e-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="df08e-129">建議類別 （裝置、 資料、 應用程式、 身分識別、 基礎結構）</span><span class="sxs-lookup"><span data-stu-id="df08e-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="df08e-130">連線至 ServiceNow 的 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="df08e-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="df08e-131">瀏覽至 Microsoft 365 安全性中心首頁上，您會在其中看到詢問是否您使用 ServiceNow 卡片。</span><span class="sxs-lookup"><span data-stu-id="df08e-131">Navigate to the Microsoft 365 security center home page, where you will see a card asking if you use ServiceNow.</span></span>

![您使用 ServiceNow 嗎](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="df08e-133">從這裡您將會傳送至設定] 頁面上，您會依照授權的 Microsoft 365 連接器應用程式的指示 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="df08e-133">From there you will be sent to the ServiceNow set up page where you'll follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

<span data-ttu-id="df08e-134">當授權 Microsoft 365 安全性中心與 ServiceNow 之間的連線，請確定您使用整合使用者登入和密碼剛才在安裝步驟並不是您個人的認證。</span><span class="sxs-lookup"><span data-stu-id="df08e-134">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

<span data-ttu-id="df08e-135">之後的下列指示和授權的連線，您可以檢視連線狀態，這兩個 Microsoft 365 安全性中心連線] 頁面上和在 ServiceNow Microsoft 365 面臨連接器 App 體驗。</span><span class="sxs-lookup"><span data-stu-id="df08e-135">After following the directions and authorizing the connection, you can view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="df08e-136">現在您所有設為啟動建立工作 ！</span><span class="sxs-lookup"><span data-stu-id="df08e-136">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="df08e-137">建立工作和分享 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="df08e-137">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="df08e-138">一旦設定整合時，您可以建立 ServiceNow 工作根據 Microsoft 安全分數改進的特定動作。</span><span class="sxs-lookup"><span data-stu-id="df08e-138">Once the integration is set up, you can create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="df08e-139">移至任何改進巨集指令中安全分數的 Microsoft 365 安全性中心入口網站中，並選取 「 共用 」 圖示。</span><span class="sxs-lookup"><span data-stu-id="df08e-139">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="df08e-140">其中一個下拉式清單選項是 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="df08e-140">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow 共用安全分數](../images/servicenow-share.png)

<span data-ttu-id="df08e-142">您可以在其中設定優先順序及編輯名稱、 描述、 或到期日，然後就會產生一項工作。</span><span class="sxs-lookup"><span data-stu-id="df08e-142">A task will then be generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="df08e-143">一旦所有必要的欄位已填入，您可以傳送工作給 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="df08e-143">Once all the required fields are filled in, you can send the task to ServiceNow.</span></span>

<span data-ttu-id="df08e-144">工作會顯示在 ServiceNow 做為 Microsoft 365 安全性和組態變更要求。</span><span class="sxs-lookup"><span data-stu-id="df08e-144">The task will be visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="df08e-145">追蹤票證</span><span class="sxs-lookup"><span data-stu-id="df08e-145">Track tickets</span></span>

<span data-ttu-id="df08e-146">一旦 ServiceNow 變更 」 管理模型，並已建立附隨管理票證，則會顯示在 Microsoft 365 安全性中心首頁的卡片上。</span><span class="sxs-lookup"><span data-stu-id="df08e-146">Once ServiceNow change management and incident management tickets have been created, they will be displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="df08e-147">從這些卡] 底下，您可以建立票證、 檢視所有票證，或管理 ServiceNow 組態。</span><span class="sxs-lookup"><span data-stu-id="df08e-147">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 變更管理票證](../images/change-management-375.png)  ![ServiceNow 附隨管理票證](../images/incident-management-375.png)

<span data-ttu-id="df08e-150">若要重新佈建或管理 Microsoft 365 安全性中心您 ServiceNow 整合，請選取**管理 ServiceNow 設定**上的卡片。</span><span class="sxs-lookup"><span data-stu-id="df08e-150">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="df08e-151">從該處可以移除目前的 ServiceNow 連線和自訂票證狀態名稱。</span><span class="sxs-lookup"><span data-stu-id="df08e-151">From there you can  remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="df08e-152">ServiceNow 票證可見 Microsoft 365 安全中心內與您的工作會 live 就地其中他們可追蹤並處理時，以及其他安全性儀表板的項目。</span><span class="sxs-lookup"><span data-stu-id="df08e-152">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks will live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="df08e-153">常見問題集</span><span class="sxs-lookup"><span data-stu-id="df08e-153">Frequently asked questions</span></span>

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="df08e-154">我在安裝檢查清單 （OAuth 建立） 的第一個步驟中收到錯誤</span><span class="sxs-lookup"><span data-stu-id="df08e-154">I am receiving an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="df08e-155">**錯誤訊息**： 讀取作業對 'oauth_entity' 從範圍 'x_mioms_m365ticket' 已拒絕因為該資料表的跨範圍存取原則</span><span class="sxs-lookup"><span data-stu-id="df08e-155">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="df08e-156">我們 app 假設 ServiceNow 執行個體上的任何系統管理員可以建立及讀取 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="df08e-156">Our app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="df08e-157">由於 ServiceNow，這會限制可以建立/讀取 OAuth 實體執行個體上的自訂，可能會發生這個錯誤。</span><span class="sxs-lookup"><span data-stu-id="df08e-157">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span> <span data-ttu-id="df08e-158">ServiceNow 建議使用者保留超出方塊的功能 （預設值）。</span><span class="sxs-lookup"><span data-stu-id="df08e-158">ServiceNow recommends users keep out of the box functionality (default).</span></span>

<span data-ttu-id="df08e-159">設定 「 應用程式登錄 」 資料表設定為預設值：</span><span class="sxs-lookup"><span data-stu-id="df08e-159">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="df08e-160">標籤 = 應用程式 Registeries</span><span class="sxs-lookup"><span data-stu-id="df08e-160">Label = Application Registeries</span></span>
* <span data-ttu-id="df08e-161">名稱 = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="df08e-161">Name = oauth_entity</span></span>
* <span data-ttu-id="df08e-162">從存取 = 應用程式的所有範圍</span><span class="sxs-lookup"><span data-stu-id="df08e-162">Accessible from = All application scopes</span></span>
* <span data-ttu-id="df08e-163">可以讀取 = 選取核取方塊</span><span class="sxs-lookup"><span data-stu-id="df08e-163">Can read = check box selected</span></span>

<span data-ttu-id="df08e-164">**ServiceNow 建議使用者保留超出方塊的功能 （預設值）。**</span><span class="sxs-lookup"><span data-stu-id="df08e-164">**ServiceNow recommends users keep out of the box functionality (default).**</span></span>

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="df08e-165">如何驗證 OAuth 實體建立 Microsoft 365 安全性 & 規範連接器？</span><span class="sxs-lookup"><span data-stu-id="df08e-165">How do I validate the OAuth entity created for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="df08e-166">前往 [ServiceNow 中的 [應用程式登錄表格 (功能表 > 系統 OAuth > Application Registry)，並找出您 （您指派的名稱） 所建立的 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="df08e-166">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="df08e-167">如何驗證 Microsoft 365 安全性 & 規範連接器安裝檢查清單的兩個步驟中建立之整合使用者？</span><span class="sxs-lookup"><span data-stu-id="df08e-167">How do I validate the Integration User created in step two of installation checklist for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="df08e-168">前往 ServiceNow 中的使用者表格 (功能表 > 使用者管理 > 使用者)，並找出整合使用者建立由您 （您指派的名稱）。</span><span class="sxs-lookup"><span data-stu-id="df08e-168">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="df08e-169">當授權 Microsoft 365 安全性中心與 ServiceNow 之間的連線，請確定您使用整合使用者登入和密碼剛才在安裝步驟並不是您個人的認證。</span><span class="sxs-lookup"><span data-stu-id="df08e-169">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a><span data-ttu-id="df08e-170">我已完成安裝和設定步驟，但我無法看到 ServiceNow 卡在首頁上，而且無法看到 Microsoft 安全分數的共用圖示</span><span class="sxs-lookup"><span data-stu-id="df08e-170">I have completed the installation and set up steps, but I am unable to see the ServiceNow cards on the home page and cannot see the Share icon in Microsoft Secure Score</span></span>

<span data-ttu-id="df08e-171">檢查 [佈建] 頁面上的狀態移至https://security.microsoft.com/ticketProvisioning。</span><span class="sxs-lookup"><span data-stu-id="df08e-171">Check the status of the provisioning page by going to https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="df08e-172">選取 [**儲存**]，並回到 [首頁] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="df08e-172">Select **Save** and return to the home page.</span></span> <span data-ttu-id="df08e-173">卡應該會出現。</span><span class="sxs-lookup"><span data-stu-id="df08e-173">The cards should appear.</span></span>
