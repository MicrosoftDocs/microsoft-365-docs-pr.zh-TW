---
title: 建立並追蹤透過 ServiceNow 票證
description: Microsoft 365 安全性中心正在增強原本建立並追蹤票證中 ServiceNow 的能力。 安全性系統管理員可以直接傳送 ServiceNow 安全分數建議，並建立票證。
keywords: 安全性，Microsoft 365，M365，安全分數，安全性中心、 ServiceNow、 票證，工作
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
ms.openlocfilehash: 26e227b4b1e8047ca962ca9e65b139bacae55e03
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599990"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="7b808-105">透過 ServiceNow 管理票證</span><span class="sxs-lookup"><span data-stu-id="7b808-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="7b808-106">Microsoft 365 安全性中心正在增強原本建立並追蹤票證中 ServiceNow 的能力。</span><span class="sxs-lookup"><span data-stu-id="7b808-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="7b808-107">安全性系統管理員可以直接傳送 ServiceNow [Microsoft 安全分數](microsoft-secure-score.md)改進巨集指令，並建立票證。</span><span class="sxs-lookup"><span data-stu-id="7b808-107">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="7b808-108">您可以建立兩個事件管理和變更管理票證。</span><span class="sxs-lookup"><span data-stu-id="7b808-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7b808-109">先決條件</span><span class="sxs-lookup"><span data-stu-id="7b808-109">Prerequisites</span></span>

<span data-ttu-id="7b808-110">可以在 Microsoft 365 安全性中心及以 ServiceNow 執行個體的存取：</span><span class="sxs-lookup"><span data-stu-id="7b808-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="7b808-111">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7b808-111">Kingston or higher version</span></span>
* <span data-ttu-id="7b808-112">具有系統管理員 HI 認證</span><span class="sxs-lookup"><span data-stu-id="7b808-112">Have admin HI credentials</span></span>
* <span data-ttu-id="7b808-113">在您的目標廠商執行個體上有系統管理員權限</span><span class="sxs-lookup"><span data-stu-id="7b808-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="7b808-114">ServiceNow 建議使用者保留預設設定，您 ServiceNow 執行個體中。</span><span class="sxs-lookup"><span data-stu-id="7b808-114">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="7b808-115">具有自訂項目可能會造成錯誤，完成安裝檢查清單並與 Microsoft 365 安全性中心整合時。</span><span class="sxs-lookup"><span data-stu-id="7b808-115">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="7b808-116">資料交換</span><span class="sxs-lookup"><span data-stu-id="7b808-116">Data exchange</span></span>

<span data-ttu-id="7b808-117">當您在 Microsoft 365 安全性中心連線至 ServiceNow 時，Microsoft 會收到下列額外的資料：</span><span class="sxs-lookup"><span data-stu-id="7b808-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="7b808-118">ServiceNow 執行個體名稱</span><span class="sxs-lookup"><span data-stu-id="7b808-118">ServiceNow instance name</span></span>
* <span data-ttu-id="7b808-119">ServiceNow 用戶端識別碼</span><span class="sxs-lookup"><span data-stu-id="7b808-119">ServiceNow client ID</span></span>
* <span data-ttu-id="7b808-120">ServiceNow 用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="7b808-120">ServiceNow client secret</span></span>
* <span data-ttu-id="7b808-121">ServiceNow 存取 & 重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="7b808-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="7b808-122">當您從 Microsoft 365 安全性中心建立 ServiceNow 票證時，下列資料傳送至 ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="7b808-122">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="7b808-123">初始化票證架設的使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="7b808-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="7b808-124">任務名稱</span><span class="sxs-lookup"><span data-stu-id="7b808-124">Task name</span></span>
* <span data-ttu-id="7b808-125">工作描述</span><span class="sxs-lookup"><span data-stu-id="7b808-125">Task description</span></span>
* <span data-ttu-id="7b808-126">優先順序</span><span class="sxs-lookup"><span data-stu-id="7b808-126">Priority</span></span>
* <span data-ttu-id="7b808-127">到期日</span><span class="sxs-lookup"><span data-stu-id="7b808-127">Due date</span></span>
* <span data-ttu-id="7b808-128">建議來源 （使用者建議或 Microsoft 建議）</span><span class="sxs-lookup"><span data-stu-id="7b808-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="7b808-129">建議類別 （裝置、 資料、 應用程式、 身分識別、 基礎結構）</span><span class="sxs-lookup"><span data-stu-id="7b808-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="7b808-130">連線至 ServiceNow 的 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="7b808-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="7b808-131">瀏覽至 Microsoft 365 安全性中心首頁上，若要查看 ServiceNow 連線卡片。</span><span class="sxs-lookup"><span data-stu-id="7b808-131">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![您使用 ServiceNow 嗎](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="7b808-133">選取 「 連線至 ServiceNow 」 移至 [ServiceNow 安裝程式] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="7b808-133">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="7b808-134">依照指示授權的 Microsoft 365 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="7b808-134">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="7b808-135">授權 Microsoft 365 安全性中心與 ServiceNow 之間的連線之前，請確定您使用的整合使用者登入與您在安裝步驟中建立的密碼。</span><span class="sxs-lookup"><span data-stu-id="7b808-135">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="7b808-136">請勿使用個人的認證。</span><span class="sxs-lookup"><span data-stu-id="7b808-136">Do not use your personal credentials.</span></span>

<span data-ttu-id="7b808-137">您必須遵循指示和授權連線之後，檢視連線狀態，在這兩個 Microsoft 365 安全性中心連線] 頁面上和 ServiceNow Microsoft 365 面臨連接器應用程式的經驗。</span><span class="sxs-lookup"><span data-stu-id="7b808-137">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="7b808-138">現在您所有設為啟動建立工作 ！</span><span class="sxs-lookup"><span data-stu-id="7b808-138">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="7b808-139">建立工作和分享 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7b808-139">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="7b808-140">一旦設定整合時，建立 ServiceNow 工作根據 Microsoft 安全分數改進的特定動作。</span><span class="sxs-lookup"><span data-stu-id="7b808-140">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="7b808-141">移至任何改進巨集指令中安全分數的 Microsoft 365 安全性中心入口網站中，並選取 「 共用 」 圖示。</span><span class="sxs-lookup"><span data-stu-id="7b808-141">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="7b808-142">其中一個下拉式清單選項是 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="7b808-142">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow 共用安全分數](../images/servicenow-share.png)

<span data-ttu-id="7b808-144">您可以在其中設定優先順序及編輯名稱、 描述、 或到期日，就會產生一項工作。</span><span class="sxs-lookup"><span data-stu-id="7b808-144">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="7b808-145">一旦所有必要的欄位中填滿，將工作傳送至 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="7b808-145">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="7b808-146">任務是顯示在 ServiceNow 做為 Microsoft 365 安全性和組態變更要求。</span><span class="sxs-lookup"><span data-stu-id="7b808-146">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="7b808-147">追蹤票證</span><span class="sxs-lookup"><span data-stu-id="7b808-147">Track tickets</span></span>

<span data-ttu-id="7b808-148">一旦 ServiceNow 變更 」 管理模型，並已建立附隨管理票證，它們會顯示在 Microsoft 365 安全性中心首頁的卡片上。</span><span class="sxs-lookup"><span data-stu-id="7b808-148">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="7b808-149">從這些卡] 底下，您可以建立票證、 檢視所有票證，或管理 ServiceNow 組態。</span><span class="sxs-lookup"><span data-stu-id="7b808-149">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 變更管理票證](../images/change-management-375.png)  ![ServiceNow 附隨管理票證](../images/incident-management-375.png)

<span data-ttu-id="7b808-152">若要重新佈建或管理 Microsoft 365 安全性中心您 ServiceNow 整合，請選取**管理 ServiceNow 設定**上的卡片。</span><span class="sxs-lookup"><span data-stu-id="7b808-152">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="7b808-153">從那裡，移除目前的 ServiceNow 連線和自訂票證狀態名稱。</span><span class="sxs-lookup"><span data-stu-id="7b808-153">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="7b808-154">ServiceNow 票證可見 Microsoft 365 安全中心內與您的任務 live 就地其中他們可追蹤並處理時，以及其他安全性儀表板的項目。</span><span class="sxs-lookup"><span data-stu-id="7b808-154">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7b808-155">疑難排解</span><span class="sxs-lookup"><span data-stu-id="7b808-155">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="7b808-156">安裝檢查清單 （OAuth 建立） 的第一個步驟中收到錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="7b808-156">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="7b808-157">**錯誤訊息**： 讀取作業對 'oauth_entity' 從範圍 'x_mioms_m365ticket' 已拒絕因為該資料表的跨範圍存取原則</span><span class="sxs-lookup"><span data-stu-id="7b808-157">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="7b808-158">應用程式假設 ServiceNow 執行個體上的任何系統管理員可以建立及讀取 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="7b808-158">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="7b808-159">由於 ServiceNow，這會限制可以建立/讀取 OAuth 實體執行個體上的自訂，可能會發生這個錯誤。</span><span class="sxs-lookup"><span data-stu-id="7b808-159">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="7b808-160">**ServiceNow 建議使用者保留預設功能。**</span><span class="sxs-lookup"><span data-stu-id="7b808-160">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="7b808-161">設定 「 應用程式登錄 」 資料表設定為預設值：</span><span class="sxs-lookup"><span data-stu-id="7b808-161">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="7b808-162">標籤 = 應用程式 Registeries</span><span class="sxs-lookup"><span data-stu-id="7b808-162">Label = Application Registeries</span></span>
* <span data-ttu-id="7b808-163">名稱 = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="7b808-163">Name = oauth_entity</span></span>
* <span data-ttu-id="7b808-164">從存取 = 應用程式的所有範圍</span><span class="sxs-lookup"><span data-stu-id="7b808-164">Accessible from = All application scopes</span></span>
* <span data-ttu-id="7b808-165">可以讀取 = 選取核取方塊</span><span class="sxs-lookup"><span data-stu-id="7b808-165">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="7b808-166">如何驗證建立 Microsoft 365 安全性 & 規範連接器的 OAuth 實體</span><span class="sxs-lookup"><span data-stu-id="7b808-166">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="7b808-167">前往 [ServiceNow 中的 [應用程式登錄表格 (**功能表 > 系統 OAuth > Application Registry**)，並找出您建立的您將其指派的名稱與 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="7b808-167">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="7b808-168">整合使用者身分登入</span><span class="sxs-lookup"><span data-stu-id="7b808-168">Logging in as the integration user</span></span>

<span data-ttu-id="7b808-169">授權 Microsoft 365 安全性中心與 ServiceNow 之間的連線之前，請確定您使用的整合使用者登入與您在安裝步驟中建立的密碼。</span><span class="sxs-lookup"><span data-stu-id="7b808-169">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="7b808-170">請勿使用個人的認證。</span><span class="sxs-lookup"><span data-stu-id="7b808-170">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="7b808-171">移 ServiceNow 中的 [授權] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7b808-171">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="7b808-172">如果您已登入您個人的認證，選取 [**不是您**連結中右上角。</span><span class="sxs-lookup"><span data-stu-id="7b808-172">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="7b808-173">您先前建立的安裝檢查清單從整合使用者身分登入 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="7b808-173">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="7b808-174">在詢問安全性 + 規範連接器可以連線到您 ServiceNow 帳戶 ServiceNow] 頁面上，選取 [**允許**。</span><span class="sxs-lookup"><span data-stu-id="7b808-174">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="7b808-175">繼續進行設定的步驟。</span><span class="sxs-lookup"><span data-stu-id="7b808-175">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="7b808-176">如何驗證整合使用者建立與 Microsoft 365 安全性 & 規範連接器的安裝檢查清單</span><span class="sxs-lookup"><span data-stu-id="7b808-176">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="7b808-177">前往 [Users Table **(功能表 > 使用者管理 > 使用者**) 中 ServiceNow] 和 [尋找整合使用者所建立，與您指派的名稱。</span><span class="sxs-lookup"><span data-stu-id="7b808-177">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="7b808-178">您的公司具有單一登入已啟用阻止您連線至 ServiceNow 透過 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="7b808-178">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="7b808-179">如果貴公司已啟用單一登入，您會收到錯誤或登入未成功，請遵循下列其中一個兩個解決方案。</span><span class="sxs-lookup"><span data-stu-id="7b808-179">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="7b808-180">整合使用者身分登入 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7b808-180">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="7b808-181">瀏覽回 ServiceNow 中的 [授權] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="7b808-181">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="7b808-182">選取 [**不是您**連結中右上角。</span><span class="sxs-lookup"><span data-stu-id="7b808-182">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="7b808-183">您先前建立的安裝檢查清單從整合使用者身分登入 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="7b808-183">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="7b808-184">在詢問安全性 + 規範連接器可以連線到您 ServiceNow 帳戶 ServiceNow] 頁面上，選取 [**允許**。</span><span class="sxs-lookup"><span data-stu-id="7b808-184">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="7b808-185">繼續進行設定的步驟。</span><span class="sxs-lookup"><span data-stu-id="7b808-185">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="7b808-186">建立安全性系統管理使用者</span><span class="sxs-lookup"><span data-stu-id="7b808-186">Create a security admin user</span></span>

1. <span data-ttu-id="7b808-187">建立使用者具有安全性系統管理員權限在 Azure Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="7b808-187">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="7b808-188">使用者必須與您建立安裝檢查清單從整合使用者具有相同的名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7b808-188">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="7b808-189">一旦登入和連線完成後，您可以移除安全性系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="7b808-189">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="7b808-190">登入為此使用者在 Microsoft 365 安全性管理中心並遵循設定步驟。</span><span class="sxs-lookup"><span data-stu-id="7b808-190">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="7b808-191">安裝完成時，但看不到票證，而且無法共用</span><span class="sxs-lookup"><span data-stu-id="7b808-191">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="7b808-192">如果已完成的安裝和設定步驟，但您看不到 ServiceNow 卡在首頁上，而且無法共用 ServiceNow 要從 Microsoft 安全分數，檢查狀態的佈建頁面上的https://security.microsoft.com/ticketProvisioning。</span><span class="sxs-lookup"><span data-stu-id="7b808-192">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="7b808-193">選取 [**授權]，** 並返回 [首頁] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7b808-193">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="7b808-194">卡應該會出現。</span><span class="sxs-lookup"><span data-stu-id="7b808-194">The cards should appear.</span></span>

