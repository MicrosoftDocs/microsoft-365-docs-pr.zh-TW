---
title: 將 ServiceNow 票證整合至 Microsoft 365 的安全性中心和合規性中心
description: 瞭解如何從 Microsoft 365 的安全性中心和合規性中心開始，在 ServiceNow 中建立及追蹤入場券。
keywords: 安全性，Microsoft 365，M365，合規性中心，安全性中心，ServiceNow，票證，任務，雪，connection
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: ca13234a93ffcc226be45d337880692a3a39c28b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196116"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="b0895-104">將 ServiceNow 票證整合至 Microsoft 365 的安全性中心和合規性中心</span><span class="sxs-lookup"><span data-stu-id="b0895-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b0895-105">ServiceNow 是一個流行的雲端計算平臺，可協助公司管理企業作業的數位工作流程。</span><span class="sxs-lookup"><span data-stu-id="b0895-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="b0895-106">其 Now 平臺具有 IT 工作流程、員工工作流程和客戶工作流程。</span><span class="sxs-lookup"><span data-stu-id="b0895-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="b0895-107">深入瞭解 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="b0895-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="b0895-108">Microsoft 已與 ServiceNow 合作，讓 IT 系統管理員可輕鬆管理這兩個平臺的票證和工作。</span><span class="sxs-lookup"><span data-stu-id="b0895-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="b0895-109">[Microsoft 365 的安全性中心](overview-security-center.md) 和 [microsoft 365 規範中心](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 已增強，可在 ServiceNow 中以本機方式建立及追蹤票證。</span><span class="sxs-lookup"><span data-stu-id="b0895-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="b0895-110">**管理安全性中心的 ServiceNow 票證**</span><span class="sxs-lookup"><span data-stu-id="b0895-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="b0895-111">**在規範中心管理 ServiceNow 入場券** (即將推出) </span><span class="sxs-lookup"><span data-stu-id="b0895-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0895-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="b0895-112">Prerequisites</span></span>

<span data-ttu-id="b0895-113">可以存取 Microsoft 365 的「安全中心」或「合規性中心」和 ServiceNow 實例，其中包括：</span><span class="sxs-lookup"><span data-stu-id="b0895-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="b0895-114">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b0895-114">Kingston or higher version</span></span>
* <span data-ttu-id="b0895-115">具有系統管理員高認證</span><span class="sxs-lookup"><span data-stu-id="b0895-115">Have admin HI credentials</span></span>
* <span data-ttu-id="b0895-116">具有目標廠商實例的系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="b0895-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="b0895-117">ServiceNow 建議使用者將預設設定保留在 ServiceNow 實例中。</span><span class="sxs-lookup"><span data-stu-id="b0895-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="b0895-118">在完成安裝檢查清單並與 Microsoft 365 安全性中心整合時，讓自訂動作可能會造成錯誤。</span><span class="sxs-lookup"><span data-stu-id="b0895-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="b0895-119">資料交換</span><span class="sxs-lookup"><span data-stu-id="b0895-119">Data exchange</span></span>

<span data-ttu-id="b0895-120">當您將 Microsoft 365 的安全性中心或規範中心連線至 ServiceNow 時，Microsoft 會收到下列額外的資料：</span><span class="sxs-lookup"><span data-stu-id="b0895-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="b0895-121">ServiceNow 實例名稱</span><span class="sxs-lookup"><span data-stu-id="b0895-121">ServiceNow instance name</span></span>
* <span data-ttu-id="b0895-122">ServiceNow 用戶端識別碼</span><span class="sxs-lookup"><span data-stu-id="b0895-122">ServiceNow client ID</span></span>
* <span data-ttu-id="b0895-123">ServiceNow 用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="b0895-123">ServiceNow client secret</span></span>
* <span data-ttu-id="b0895-124">ServiceNow 存取 & 重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="b0895-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="b0895-125">當您從 Microsoft 365 的「安全中心」或「合規性中心」建立 ServiceNow 票證時，會將下列資料傳送至 ServiceNow：</span><span class="sxs-lookup"><span data-stu-id="b0895-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="b0895-126">啟動票證建立的使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="b0895-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="b0895-127">任務名稱</span><span class="sxs-lookup"><span data-stu-id="b0895-127">Task name</span></span>
* <span data-ttu-id="b0895-128">任務描述</span><span class="sxs-lookup"><span data-stu-id="b0895-128">Task description</span></span>
* <span data-ttu-id="b0895-129">優先順序</span><span class="sxs-lookup"><span data-stu-id="b0895-129">Priority</span></span>
* <span data-ttu-id="b0895-130">到期日</span><span class="sxs-lookup"><span data-stu-id="b0895-130">Due date</span></span>
* <span data-ttu-id="b0895-131">建議來源 (使用者建議或 Microsoft 建議) </span><span class="sxs-lookup"><span data-stu-id="b0895-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="b0895-132">建議類別 (裝置、資料、應用程式、身分識別、基礎結構) </span><span class="sxs-lookup"><span data-stu-id="b0895-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="b0895-133">連接至 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="b0895-133">Connect to ServiceNow</span></span>

<span data-ttu-id="b0895-134">移至 [[建立並追蹤 Microsoft 365 的安全性中心的 ServiceNow 入場券](tickets-security-center.md) ]，以瞭解如何連線至 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="b0895-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="b0895-135">即將推出從 Microsoft 365 規範中心連線。</span><span class="sxs-lookup"><span data-stu-id="b0895-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b0895-136">疑難排解</span><span class="sxs-lookup"><span data-stu-id="b0895-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="b0895-137">您會在安裝檢查清單的第一個步驟中收到錯誤 (OAuth 建立) </span><span class="sxs-lookup"><span data-stu-id="b0895-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="b0895-138">**錯誤訊息**：從範圍 ' x_mioms_m365ticket ' 對「oauth_entity ' 進行的讀取作業已被拒絕，因為資料表的跨範圍存取原則</span><span class="sxs-lookup"><span data-stu-id="b0895-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="b0895-139">應用程式假設 ServiceNow 實例上的任何系統管理員都可以建立和讀取 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="b0895-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="b0895-140">此錯誤可能是由您的 ServiceNow 實例中的自訂，用以限制誰可以建立或讀取 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="b0895-140">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="b0895-141">**ServiceNow 建議使用者保留預設功能。**</span><span class="sxs-lookup"><span data-stu-id="b0895-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="b0895-142">將 "應用程式註冊表" 資料表設定設為預設值：</span><span class="sxs-lookup"><span data-stu-id="b0895-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="b0895-143">標籤 = 應用程式 Registeries</span><span class="sxs-lookup"><span data-stu-id="b0895-143">Label = Application Registeries</span></span>
* <span data-ttu-id="b0895-144">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="b0895-144">Name = oauth_entity</span></span>
* <span data-ttu-id="b0895-145">從 = 所有應用程式範圍存取</span><span class="sxs-lookup"><span data-stu-id="b0895-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="b0895-146">可讀取 = 核取方塊選取</span><span class="sxs-lookup"><span data-stu-id="b0895-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="b0895-147">如何驗證為 Microsoft 365 Security & 合規性連接器所建立的 OAuth 實體</span><span class="sxs-lookup"><span data-stu-id="b0895-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="b0895-148">移至應用程式註冊表表 (**功能表 > 系統 OAuth > 應用程式** 登錄) ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="b0895-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow.</span></span> <span data-ttu-id="b0895-149">使用您所指派的名稱，尋找您所建立的 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="b0895-149">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="b0895-150">以整合使用者的身分登入</span><span class="sxs-lookup"><span data-stu-id="b0895-150">Signing in as the integration user</span></span>

<span data-ttu-id="b0895-151">在您授權 Microsoft 365 security center 和 ServiceNow 之間的連線之前，請確定您使用您在安裝步驟中建立的整合使用者登入和密碼。</span><span class="sxs-lookup"><span data-stu-id="b0895-151">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="b0895-152">請勿使用您的個人認證。</span><span class="sxs-lookup"><span data-stu-id="b0895-152">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="b0895-153">前往 ServiceNow 中的 [授權] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b0895-153">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="b0895-154">如果您是以您的個人認證登入，請選取右上角的 [ **不** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="b0895-154">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="b0895-155">以您先前從安裝檢查清單建立的整合使用者身分，登入 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="b0895-155">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="b0895-156">在 [ServiceNow] 頁面中選取 [ **允許** ]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b0895-156">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="b0895-157">繼續執行設定步驟。</span><span class="sxs-lookup"><span data-stu-id="b0895-157">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="b0895-158">如何驗證使用 Microsoft 365 Security & 合規性連接器安裝檢查清單所建立的整合使用者</span><span class="sxs-lookup"><span data-stu-id="b0895-158">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="b0895-159">移至 [使用者] 表格 \*\* (功能表中 > 使用者管理 > 使用者\*\*) 在 ServiceNow 中，並尋找您所指定的整合使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="b0895-159">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="b0895-160">您的公司啟用單一登入，可防止您透過 Microsoft 365 安全中心連線到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="b0895-160">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="b0895-161">如果貴公司已啟用單一登入，但收到錯誤或登入失敗，請遵循這兩種方案之一。</span><span class="sxs-lookup"><span data-stu-id="b0895-161">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="b0895-162">以 integration 使用者的身分登入 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="b0895-162">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="b0895-163">向後流覽至 ServiceNow 中的 [授權] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b0895-163">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="b0895-164">選取右上角的 [ **不** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="b0895-164">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="b0895-165">以您先前從安裝檢查清單建立的整合使用者身分，登入 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="b0895-165">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="b0895-166">在 [ServiceNow] 頁面中選取 [ **允許** ]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b0895-166">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="b0895-167">繼續執行設定步驟。</span><span class="sxs-lookup"><span data-stu-id="b0895-167">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="b0895-168">建立安全性系統管理員使用者</span><span class="sxs-lookup"><span data-stu-id="b0895-168">Create a security admin user</span></span>

1. <span data-ttu-id="b0895-169">在 Azure Active Directory 中建立具有安全性系統管理員許可權的使用者。</span><span class="sxs-lookup"><span data-stu-id="b0895-169">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="b0895-170">使用者必須具有與您從安裝檢查清單中所建立的整合使用者相同的名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b0895-170">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="b0895-171">登入和連線完成後，您就可以移除安全性系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="b0895-171">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="b0895-172">請以此使用者身分登入 Microsoft 365 安全中心，然後執行安裝步驟。</span><span class="sxs-lookup"><span data-stu-id="b0895-172">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="b0895-173">IP 篩選</span><span class="sxs-lookup"><span data-stu-id="b0895-173">IP filtering</span></span>

<span data-ttu-id="b0895-174">如果您已啟用 IP 篩選，您可能需要明確允許 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b0895-174">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="b0895-175">如需如何在 ServiceNow 中允許 IP 範圍的資訊，請參閱 [IP 位址存取控制](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) 。</span><span class="sxs-lookup"><span data-stu-id="b0895-175">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="b0895-176">請參閱 [AZURE Ip 範圍和服務標籤-公用雲端](https://www.microsoft.com/en-us/download/details.aspx?id=56519) 以取得允許的 IP 位址清單。</span><span class="sxs-lookup"><span data-stu-id="b0895-176">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="b0895-177">安裝已完成，但看不到票證，而且無法共用</span><span class="sxs-lookup"><span data-stu-id="b0895-177">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="b0895-178">如果已完成安裝和設定步驟，但是您沒有在首頁上看到 ServiceNow 卡片，而且無法從 Microsoft 安全分數 ServiceNow 共用，請檢查 [布建] 頁面的狀態 https://security.microsoft.com/ticketProvisioning 。</span><span class="sxs-lookup"><span data-stu-id="b0895-178">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="b0895-179">選取 [ **授權** ]，然後回到首頁。</span><span class="sxs-lookup"><span data-stu-id="b0895-179">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="b0895-180">應該會出現卡。</span><span class="sxs-lookup"><span data-stu-id="b0895-180">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="b0895-181">資源</span><span class="sxs-lookup"><span data-stu-id="b0895-181">Resources</span></span>

- [<span data-ttu-id="b0895-182">管理安全性中心的 ServiceNow 票證</span><span class="sxs-lookup"><span data-stu-id="b0895-182">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)
