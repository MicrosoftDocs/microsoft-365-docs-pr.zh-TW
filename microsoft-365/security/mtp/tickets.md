---
title: 透過 ServiceNow 建立及追蹤入場券
description: Microsoft 365 security center 已增強，可在 ServiceNow 中以本機方式建立及追蹤票證。 安全性管理員可以直接傳送安全得分建議，以 ServiceNow 及建立票證。
keywords: 安全性，Microsoft 365，M365，安全分數，安全性中心，ServiceNow，票證，任務
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
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
ms.openlocfilehash: eb6af6b11d2d932f3bd2165aa3f597c14feb5ae8
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901019"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="22014-105">透過 ServiceNow 管理票證</span><span class="sxs-lookup"><span data-stu-id="22014-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="22014-106">ServiceNow 是一個流行的雲端計算平臺，可協助公司管理企業作業的數位工作流程。</span><span class="sxs-lookup"><span data-stu-id="22014-106">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="22014-107">其 Now 平臺具有 IT 工作流程、員工工作流程和客戶工作流程。</span><span class="sxs-lookup"><span data-stu-id="22014-107">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> <span data-ttu-id="22014-108">Microsoft 已與 ServiceNow 合作，讓 IT 系統管理員可輕鬆管理這兩個平臺的票證和工作。</span><span class="sxs-lookup"><span data-stu-id="22014-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> [<span data-ttu-id="22014-109">深入瞭解 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="22014-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="22014-110">Microsoft 365 的安全性中心現在已增強，可在 ServiceNow 中以本機方式建立及追蹤票證。</span><span class="sxs-lookup"><span data-stu-id="22014-110">Microsoft 365 security center is now enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="22014-111">安全性管理員可以直接傳送[Microsoft Secure 得分](microsoft-secure-score.md)改進動作來 ServiceNow 和建立票證。</span><span class="sxs-lookup"><span data-stu-id="22014-111">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="22014-112">您可以建立事件管理和變更管理票證。</span><span class="sxs-lookup"><span data-stu-id="22014-112">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="22014-113">然後，您可以在 Microsoft 的「安全性中心」首頁中追蹤它們，然後 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="22014-113">They can then be tracked in the Microsoft security center home page, and ServiceNow.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="22014-114">必要條件</span><span class="sxs-lookup"><span data-stu-id="22014-114">Prerequisites</span></span>

<span data-ttu-id="22014-115">可以存取 Microsoft 365 security center 和 ServiceNow 實例，其具有：</span><span class="sxs-lookup"><span data-stu-id="22014-115">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="22014-116">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="22014-116">Kingston or higher version</span></span>
* <span data-ttu-id="22014-117">具有系統管理員高認證</span><span class="sxs-lookup"><span data-stu-id="22014-117">Have admin HI credentials</span></span>
* <span data-ttu-id="22014-118">具有目標廠商實例的系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="22014-118">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="22014-119">ServiceNow 建議使用者將預設設定保留在 ServiceNow 實例中。</span><span class="sxs-lookup"><span data-stu-id="22014-119">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="22014-120">在完成安裝檢查清單並與 Microsoft 365 安全性中心整合時，讓自訂動作可能會造成錯誤。</span><span class="sxs-lookup"><span data-stu-id="22014-120">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="22014-121">資料交換</span><span class="sxs-lookup"><span data-stu-id="22014-121">Data exchange</span></span>

<span data-ttu-id="22014-122">當您將 Microsoft 365 的安全性中心連線至 ServiceNow 時，Microsoft 會收到下列其他資料：</span><span class="sxs-lookup"><span data-stu-id="22014-122">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="22014-123">ServiceNow 實例名稱</span><span class="sxs-lookup"><span data-stu-id="22014-123">ServiceNow instance name</span></span>
* <span data-ttu-id="22014-124">ServiceNow 用戶端識別碼</span><span class="sxs-lookup"><span data-stu-id="22014-124">ServiceNow client ID</span></span>
* <span data-ttu-id="22014-125">ServiceNow 用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="22014-125">ServiceNow client secret</span></span>
* <span data-ttu-id="22014-126">ServiceNow 存取 & 重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="22014-126">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="22014-127">當您從 Microsoft 365 security center 建立 ServiceNow 票證時，下列資料會傳送至 ServiceNow：</span><span class="sxs-lookup"><span data-stu-id="22014-127">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="22014-128">啟動票證建立的使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="22014-128">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="22014-129">任務名稱</span><span class="sxs-lookup"><span data-stu-id="22014-129">Task name</span></span>
* <span data-ttu-id="22014-130">任務描述</span><span class="sxs-lookup"><span data-stu-id="22014-130">Task description</span></span>
* <span data-ttu-id="22014-131">優先順序</span><span class="sxs-lookup"><span data-stu-id="22014-131">Priority</span></span>
* <span data-ttu-id="22014-132">到期日</span><span class="sxs-lookup"><span data-stu-id="22014-132">Due date</span></span>
* <span data-ttu-id="22014-133">建議來源（使用者建議或 Microsoft 建議）</span><span class="sxs-lookup"><span data-stu-id="22014-133">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="22014-134">建議類別（裝置、資料、應用程式、身分識別、基礎結構）</span><span class="sxs-lookup"><span data-stu-id="22014-134">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="22014-135">將 Microsoft 365 的安全性中心連線至 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="22014-135">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="22014-136">流覽至 Microsoft 365 的「安全性中心」首頁，以查看 ServiceNow 連接卡。</span><span class="sxs-lookup"><span data-stu-id="22014-136">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![您使用 ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="22014-138">選取 [連線至 ServiceNow] 以移至 [ServiceNow 設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="22014-138">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="22014-139">依照指示授權 Microsoft 365 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="22014-139">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="22014-140">在您授權 Microsoft 365 security center 和 ServiceNow 之間的連線之前，請確定您使用您在安裝步驟中建立的整合使用者登入和密碼。</span><span class="sxs-lookup"><span data-stu-id="22014-140">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="22014-141">請勿使用您的個人認證。</span><span class="sxs-lookup"><span data-stu-id="22014-141">Do not use your personal credentials.</span></span>

<span data-ttu-id="22014-142">在您遵循指示和授權連線之後，請在 Microsoft 365 [安全性中心] 連線頁面和 ServiceNow Microsoft 365 票證發放連接器應用程式體驗中查看線上狀態。</span><span class="sxs-lookup"><span data-stu-id="22014-142">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="22014-143">現在，您已全部設定為開始建立任務！</span><span class="sxs-lookup"><span data-stu-id="22014-143">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="22014-144">建立任務並將其共用至 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="22014-144">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="22014-145">整合設定後，根據特定的 Microsoft 安全分數改進動作建立 ServiceNow 工作。</span><span class="sxs-lookup"><span data-stu-id="22014-145">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="22014-146">請移至 Microsoft 365 安全性中心入口網站中安全評分的任何改進動作，然後選取「共用」圖示。</span><span class="sxs-lookup"><span data-stu-id="22014-146">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="22014-147">其中一個 dropdown 選項是 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="22014-147">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow 在安全分數中共用](../../media/servicenow-share.png)

<span data-ttu-id="22014-149">工作會產生，您可以在其中設定優先順序及編輯名稱、描述或到期日。</span><span class="sxs-lookup"><span data-stu-id="22014-149">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="22014-150">填寫所有必要欄位後，將工作傳送至 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="22014-150">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="22014-151">這項工作會顯示在 ServiceNow 成為 Microsoft 365 安全性和設定變更要求。</span><span class="sxs-lookup"><span data-stu-id="22014-151">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="22014-152">追蹤票據</span><span class="sxs-lookup"><span data-stu-id="22014-152">Track tickets</span></span>

<span data-ttu-id="22014-153">一旦 ServiceNow 變更管理和事件管理票證已建立，便會顯示在 Microsoft 365 安全中心首頁的卡片上。</span><span class="sxs-lookup"><span data-stu-id="22014-153">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="22014-154">您可以從這些卡片建立票證、查看所有票證或管理 ServiceNow 設定。</span><span class="sxs-lookup"><span data-stu-id="22014-154">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 變更管理票證](../../media/change-management-375.png)  ![ServiceNow 事件管理票證](../../media/incident-management-375.png)

<span data-ttu-id="22014-157">若要在 Microsoft 365 的安全性中心重新布建或管理您的 ServiceNow 整合，請選取 [管理任何卡片上的**ServiceNow**設定]。</span><span class="sxs-lookup"><span data-stu-id="22014-157">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="22014-158">從那裡移除目前的 ServiceNow 連線，並自訂票證狀態名稱。</span><span class="sxs-lookup"><span data-stu-id="22014-158">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="22014-159">使用 Microsoft 365 security center 中顯示的 ServiceNow 入場券，您的工作可以在一個位置進行追蹤，並依據其他安全性儀表板專案進行處理。</span><span class="sxs-lookup"><span data-stu-id="22014-159">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="22014-160">疑難排解</span><span class="sxs-lookup"><span data-stu-id="22014-160">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="22014-161">安裝檢查清單（OAuth 建立）的第一個步驟中收到錯誤</span><span class="sxs-lookup"><span data-stu-id="22014-161">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="22014-162">**錯誤訊息**：針對來自範圍 ' x_mioms_m365ticket ' 的「oauth_entity ' 的讀取作業已遭到拒絕，因為資料表的跨範圍存取原則</span><span class="sxs-lookup"><span data-stu-id="22014-162">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="22014-163">應用程式假設 ServiceNow 實例上的任何系統管理員都可以建立和讀取 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="22014-163">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="22014-164">這項錯誤可能是由於您的 ServiceNow 實例的自訂專案所造成，其可限制誰可以建立/讀取 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="22014-164">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="22014-165">**ServiceNow 建議使用者保留預設功能。**</span><span class="sxs-lookup"><span data-stu-id="22014-165">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="22014-166">將 "應用程式註冊表" 資料表設定設為預設值：</span><span class="sxs-lookup"><span data-stu-id="22014-166">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="22014-167">標籤 = 應用程式 Registeries</span><span class="sxs-lookup"><span data-stu-id="22014-167">Label = Application Registeries</span></span>
* <span data-ttu-id="22014-168">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="22014-168">Name = oauth_entity</span></span>
* <span data-ttu-id="22014-169">從 = 所有應用程式範圍存取</span><span class="sxs-lookup"><span data-stu-id="22014-169">Accessible from = All application scopes</span></span>
* <span data-ttu-id="22014-170">可讀取 = 核取方塊選取</span><span class="sxs-lookup"><span data-stu-id="22014-170">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="22014-171">如何驗證為 Microsoft 365 Security & 合規性連接器所建立的 OAuth 實體</span><span class="sxs-lookup"><span data-stu-id="22014-171">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="22014-172">移至 ServiceNow 中的 [應用程式註冊表（**功能表 > 系統 OAuth > 應用程式**登錄）]，並使用您指派它的名稱，尋找您所建立的 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="22014-172">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="22014-173">以 integration 使用者的身分登入</span><span class="sxs-lookup"><span data-stu-id="22014-173">Logging in as the integration user</span></span>

<span data-ttu-id="22014-174">在您授權 Microsoft 365 security center 和 ServiceNow 之間的連線之前，請確定您使用您在安裝步驟中建立的整合使用者登入和密碼。</span><span class="sxs-lookup"><span data-stu-id="22014-174">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="22014-175">請勿使用您的個人認證。</span><span class="sxs-lookup"><span data-stu-id="22014-175">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="22014-176">前往 ServiceNow 中的 [授權] 頁面。</span><span class="sxs-lookup"><span data-stu-id="22014-176">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="22014-177">如果您是以您的個人認證登入，請選取右上角的 [**不**] 連結。</span><span class="sxs-lookup"><span data-stu-id="22014-177">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="22014-178">以您先前從安裝檢查清單建立的整合使用者身分登入 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="22014-178">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="22014-179">在 [ServiceNow] 頁面中選取 [**允許**]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。</span><span class="sxs-lookup"><span data-stu-id="22014-179">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="22014-180">繼續執行設定步驟。</span><span class="sxs-lookup"><span data-stu-id="22014-180">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="22014-181">如何驗證使用 Microsoft 365 Security & 合規性連接器安裝檢查清單所建立的整合使用者</span><span class="sxs-lookup"><span data-stu-id="22014-181">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="22014-182">移至 ServiceNow 中的 [使用者] 表格 **（[功能表 > 使用者管理 > 使用者**）]，並尋找您用來指定的整合使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="22014-182">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="22014-183">您的公司啟用單一登入，可防止您透過 Microsoft 365 安全中心連線到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="22014-183">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="22014-184">如果貴公司已啟用單一登入，但收到錯誤或登入失敗，請遵循這兩種方案之一。</span><span class="sxs-lookup"><span data-stu-id="22014-184">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="22014-185">以 integration 使用者的身分登入 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="22014-185">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="22014-186">向後流覽至 ServiceNow 中的 [授權] 頁面。</span><span class="sxs-lookup"><span data-stu-id="22014-186">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="22014-187">選取右上角的 [**不**] 連結。</span><span class="sxs-lookup"><span data-stu-id="22014-187">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="22014-188">以您先前從安裝檢查清單建立的整合使用者身分登入 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="22014-188">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="22014-189">在 [ServiceNow] 頁面中選取 [**允許**]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。</span><span class="sxs-lookup"><span data-stu-id="22014-189">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="22014-190">繼續執行設定步驟。</span><span class="sxs-lookup"><span data-stu-id="22014-190">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="22014-191">建立安全性系統管理員使用者</span><span class="sxs-lookup"><span data-stu-id="22014-191">Create a security admin user</span></span>

1. <span data-ttu-id="22014-192">在 Azure Active Directory 中建立具有安全性系統管理員許可權的使用者。</span><span class="sxs-lookup"><span data-stu-id="22014-192">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="22014-193">使用者必須具有與您從安裝檢查清單中所建立的整合使用者相同的名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="22014-193">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="22014-194">登入和連線完成後，您就可以移除安全性系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="22014-194">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="22014-195">以此使用者的身分登入 Microsoft 365 安全中心，然後依照設定步驟進行。</span><span class="sxs-lookup"><span data-stu-id="22014-195">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="22014-196">IP 篩選</span><span class="sxs-lookup"><span data-stu-id="22014-196">IP filtering</span></span>

<span data-ttu-id="22014-197">如果您已啟用 IP 篩選，您可能需要明確允許 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="22014-197">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="22014-198">如需如何在 ServiceNow 中允許 IP 範圍的資訊，請參閱[IP 位址存取控制](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html)。</span><span class="sxs-lookup"><span data-stu-id="22014-198">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="22014-199">請參閱[AZURE Ip 範圍和服務標籤-公用雲端](https://www.microsoft.com/en-us/download/details.aspx?id=56519)以取得允許的 IP 位址清單。</span><span class="sxs-lookup"><span data-stu-id="22014-199">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="22014-200">安裝已完成，但看不到票證，而且無法共用</span><span class="sxs-lookup"><span data-stu-id="22014-200">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="22014-201">如果已完成安裝和設定步驟，但是您沒有在首頁上看到 ServiceNow 卡片，而且無法從 Microsoft 安全分數 ServiceNow 共用，請檢查 [布建] 頁面的狀態https://security.microsoft.com/ticketProvisioning。</span><span class="sxs-lookup"><span data-stu-id="22014-201">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="22014-202">選取 [**授權**]，然後回到首頁。</span><span class="sxs-lookup"><span data-stu-id="22014-202">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="22014-203">應該會出現卡。</span><span class="sxs-lookup"><span data-stu-id="22014-203">The cards should appear.</span></span>

