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
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086664"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="c6214-104">將 ServiceNow 票證整合至 Microsoft 365 的安全性中心和合規性中心</span><span class="sxs-lookup"><span data-stu-id="c6214-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c6214-105">ServiceNow 是一個流行的雲端計算平臺，可協助公司管理企業作業的數位工作流程。</span><span class="sxs-lookup"><span data-stu-id="c6214-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="c6214-106">其 Now 平臺具有 IT 工作流程、員工工作流程和客戶工作流程。</span><span class="sxs-lookup"><span data-stu-id="c6214-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="c6214-107">深入瞭解 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c6214-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="c6214-108">Microsoft 已與 ServiceNow 合作，讓 IT 系統管理員可輕鬆管理這兩個平臺的票證和工作。</span><span class="sxs-lookup"><span data-stu-id="c6214-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="c6214-109">[Microsoft 365 的安全性中心](overview-security-center.md)和[microsoft 365 規範中心](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center)已增強，可在 ServiceNow 中以本機方式建立及追蹤票證。</span><span class="sxs-lookup"><span data-stu-id="c6214-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="c6214-110">**管理安全性中心的 ServiceNow 票證**</span><span class="sxs-lookup"><span data-stu-id="c6214-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="c6214-111">**管理規範中心的 ServiceNow 入場券**（即將推出）</span><span class="sxs-lookup"><span data-stu-id="c6214-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c6214-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="c6214-112">Prerequisites</span></span>

<span data-ttu-id="c6214-113">可以存取 Microsoft 365 的「安全中心」或「合規性中心」和 ServiceNow 實例，其中包括：</span><span class="sxs-lookup"><span data-stu-id="c6214-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="c6214-114">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="c6214-114">Kingston or higher version</span></span>
* <span data-ttu-id="c6214-115">具有系統管理員高認證</span><span class="sxs-lookup"><span data-stu-id="c6214-115">Have admin HI credentials</span></span>
* <span data-ttu-id="c6214-116">具有目標廠商實例的系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="c6214-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="c6214-117">ServiceNow 建議使用者將預設設定保留在 ServiceNow 實例中。</span><span class="sxs-lookup"><span data-stu-id="c6214-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="c6214-118">在完成安裝檢查清單並與 Microsoft 365 安全性中心整合時，讓自訂動作可能會造成錯誤。</span><span class="sxs-lookup"><span data-stu-id="c6214-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="c6214-119">資料交換</span><span class="sxs-lookup"><span data-stu-id="c6214-119">Data exchange</span></span>

<span data-ttu-id="c6214-120">當您將 Microsoft 365 的安全性中心或規範中心連線至 ServiceNow 時，Microsoft 會收到下列額外的資料：</span><span class="sxs-lookup"><span data-stu-id="c6214-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="c6214-121">ServiceNow 實例名稱</span><span class="sxs-lookup"><span data-stu-id="c6214-121">ServiceNow instance name</span></span>
* <span data-ttu-id="c6214-122">ServiceNow 用戶端識別碼</span><span class="sxs-lookup"><span data-stu-id="c6214-122">ServiceNow client ID</span></span>
* <span data-ttu-id="c6214-123">ServiceNow 用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="c6214-123">ServiceNow client secret</span></span>
* <span data-ttu-id="c6214-124">ServiceNow 存取 & 重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="c6214-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="c6214-125">當您從 Microsoft 365 的「安全中心」或「合規性中心」建立 ServiceNow 票證時，會將下列資料傳送至 ServiceNow：</span><span class="sxs-lookup"><span data-stu-id="c6214-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="c6214-126">啟動票證建立的使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="c6214-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="c6214-127">任務名稱</span><span class="sxs-lookup"><span data-stu-id="c6214-127">Task name</span></span>
* <span data-ttu-id="c6214-128">任務描述</span><span class="sxs-lookup"><span data-stu-id="c6214-128">Task description</span></span>
* <span data-ttu-id="c6214-129">優先順序</span><span class="sxs-lookup"><span data-stu-id="c6214-129">Priority</span></span>
* <span data-ttu-id="c6214-130">到期日</span><span class="sxs-lookup"><span data-stu-id="c6214-130">Due date</span></span>
* <span data-ttu-id="c6214-131">建議來源（使用者建議或 Microsoft 建議）</span><span class="sxs-lookup"><span data-stu-id="c6214-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="c6214-132">建議類別（裝置、資料、應用程式、身分識別、基礎結構）</span><span class="sxs-lookup"><span data-stu-id="c6214-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="c6214-133">連接至 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c6214-133">Connect to ServiceNow</span></span>

<span data-ttu-id="c6214-134">移至[[建立並追蹤 Microsoft 365 的安全性中心的 ServiceNow 入場券](tickets-security-center.md)]，以瞭解如何連線至 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="c6214-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="c6214-135">即將推出從 Microsoft 365 規範中心連線。</span><span class="sxs-lookup"><span data-stu-id="c6214-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c6214-136">疑難排解</span><span class="sxs-lookup"><span data-stu-id="c6214-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="c6214-137">安裝檢查清單（OAuth 建立）的第一個步驟中收到錯誤</span><span class="sxs-lookup"><span data-stu-id="c6214-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="c6214-138">**錯誤訊息**：針對來自範圍 ' x_mioms_m365ticket ' 的「oauth_entity ' 的讀取作業已遭到拒絕，因為資料表的跨範圍存取原則</span><span class="sxs-lookup"><span data-stu-id="c6214-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="c6214-139">應用程式假設 ServiceNow 實例上的任何系統管理員都可以建立和讀取 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="c6214-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="c6214-140">這項錯誤可能是由於您的 ServiceNow 實例的自訂專案所造成，其可限制誰可以建立/讀取 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="c6214-140">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="c6214-141">**ServiceNow 建議使用者保留預設功能。**</span><span class="sxs-lookup"><span data-stu-id="c6214-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="c6214-142">將 "應用程式註冊表" 資料表設定設為預設值：</span><span class="sxs-lookup"><span data-stu-id="c6214-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="c6214-143">標籤 = 應用程式 Registeries</span><span class="sxs-lookup"><span data-stu-id="c6214-143">Label = Application Registeries</span></span>
* <span data-ttu-id="c6214-144">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="c6214-144">Name = oauth_entity</span></span>
* <span data-ttu-id="c6214-145">從 = 所有應用程式範圍存取</span><span class="sxs-lookup"><span data-stu-id="c6214-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="c6214-146">可讀取 = 核取方塊選取</span><span class="sxs-lookup"><span data-stu-id="c6214-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="c6214-147">如何驗證為 Microsoft 365 Security & 合規性連接器所建立的 OAuth 實體</span><span class="sxs-lookup"><span data-stu-id="c6214-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="c6214-148">移至 ServiceNow 中的 [應用程式註冊表（**功能表 > 系統 OAuth > 應用程式**登錄）]，並使用您指派它的名稱，尋找您所建立的 OAuth 實體。</span><span class="sxs-lookup"><span data-stu-id="c6214-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="c6214-149">以 integration 使用者的身分登入</span><span class="sxs-lookup"><span data-stu-id="c6214-149">Logging in as the integration user</span></span>

<span data-ttu-id="c6214-150">在您授權 Microsoft 365 security center 和 ServiceNow 之間的連線之前，請確定您使用您在安裝步驟中建立的整合使用者登入和密碼。</span><span class="sxs-lookup"><span data-stu-id="c6214-150">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="c6214-151">請勿使用您的個人認證。</span><span class="sxs-lookup"><span data-stu-id="c6214-151">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="c6214-152">前往 ServiceNow 中的 [授權] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c6214-152">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="c6214-153">如果您是以您的個人認證登入，請選取右上角的 [**不**] 連結。</span><span class="sxs-lookup"><span data-stu-id="c6214-153">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="c6214-154">以您先前從安裝檢查清單建立的整合使用者身分登入 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="c6214-154">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="c6214-155">在 [ServiceNow] 頁面中選取 [**允許**]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6214-155">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="c6214-156">繼續執行設定步驟。</span><span class="sxs-lookup"><span data-stu-id="c6214-156">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="c6214-157">如何驗證使用 Microsoft 365 Security & 合規性連接器安裝檢查清單所建立的整合使用者</span><span class="sxs-lookup"><span data-stu-id="c6214-157">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="c6214-158">移至 ServiceNow 中的 [使用者] 表格 **（[功能表 > 使用者管理 > 使用者**）]，並尋找您用來指定的整合使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="c6214-158">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="c6214-159">您的公司啟用單一登入，可防止您透過 Microsoft 365 安全中心連線到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="c6214-159">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="c6214-160">如果貴公司已啟用單一登入，但收到錯誤或登入失敗，請遵循這兩種方案之一。</span><span class="sxs-lookup"><span data-stu-id="c6214-160">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="c6214-161">以 integration 使用者的身分登入 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c6214-161">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="c6214-162">向後流覽至 ServiceNow 中的 [授權] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c6214-162">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="c6214-163">選取右上角的 [**不**] 連結。</span><span class="sxs-lookup"><span data-stu-id="c6214-163">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="c6214-164">以您先前從安裝檢查清單建立的整合使用者身分登入 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="c6214-164">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="c6214-165">在 [ServiceNow] 頁面中選取 [**允許**]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6214-165">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="c6214-166">繼續執行設定步驟。</span><span class="sxs-lookup"><span data-stu-id="c6214-166">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="c6214-167">建立安全性系統管理員使用者</span><span class="sxs-lookup"><span data-stu-id="c6214-167">Create a security admin user</span></span>

1. <span data-ttu-id="c6214-168">在 Azure Active Directory 中建立具有安全性系統管理員許可權的使用者。</span><span class="sxs-lookup"><span data-stu-id="c6214-168">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="c6214-169">使用者必須具有與您從安裝檢查清單中所建立的整合使用者相同的名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="c6214-169">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="c6214-170">登入和連線完成後，您就可以移除安全性系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="c6214-170">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="c6214-171">以此使用者的身分登入 Microsoft 365 安全中心，然後依照設定步驟進行。</span><span class="sxs-lookup"><span data-stu-id="c6214-171">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="c6214-172">IP 篩選</span><span class="sxs-lookup"><span data-stu-id="c6214-172">IP filtering</span></span>

<span data-ttu-id="c6214-173">如果您已啟用 IP 篩選，您可能需要明確允許 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c6214-173">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="c6214-174">如需如何在 ServiceNow 中允許 IP 範圍的資訊，請參閱[IP 位址存取控制](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html)。</span><span class="sxs-lookup"><span data-stu-id="c6214-174">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="c6214-175">請參閱[AZURE Ip 範圍和服務標籤-公用雲端](https://www.microsoft.com/en-us/download/details.aspx?id=56519)以取得允許的 IP 位址清單。</span><span class="sxs-lookup"><span data-stu-id="c6214-175">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="c6214-176">安裝已完成，但看不到票證，而且無法共用</span><span class="sxs-lookup"><span data-stu-id="c6214-176">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="c6214-177">如果已完成安裝和設定步驟，但是您沒有在首頁上看到 ServiceNow 卡片，而且無法從 Microsoft 安全分數 ServiceNow 共用，請檢查 [布建] 頁面的狀態 https://security.microsoft.com/ticketProvisioning 。</span><span class="sxs-lookup"><span data-stu-id="c6214-177">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="c6214-178">選取 [**授權**]，然後回到首頁。</span><span class="sxs-lookup"><span data-stu-id="c6214-178">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="c6214-179">應該會出現卡。</span><span class="sxs-lookup"><span data-stu-id="c6214-179">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="c6214-180">資源</span><span class="sxs-lookup"><span data-stu-id="c6214-180">Resources</span></span>

- [<span data-ttu-id="c6214-181">管理安全性中心的 ServiceNow 票證</span><span class="sxs-lookup"><span data-stu-id="c6214-181">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)