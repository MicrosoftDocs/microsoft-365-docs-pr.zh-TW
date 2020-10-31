---
title: 設定連接器，以在 Microsoft 365 中封存縮放會議資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 系統管理員可以設定連接器，將資料從 Globanet 縮放會議匯入 Microsoft 365。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: fbedf0521464e5faa0f74e6429d12a3eaa1d0f12
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816716"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a><span data-ttu-id="2e5b9-104">設定連接器以封存縮放會議資料</span><span class="sxs-lookup"><span data-stu-id="2e5b9-104">Set up a connector to archive Zoom Meetings data</span></span>

<span data-ttu-id="2e5b9-105">使用 Microsoft 365 規範中心內的 Globanet 連接器，將資料從縮放會議匯入至您的 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Zoom Meetings to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="2e5b9-106">Globanet 提供的 [縮放會議](https://globanet.com/zoom/) 連接器會設定為定期從協力廠商資料來源捕獲專案 () 並將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-106">Globanet provides a [Zoom Meetings](https://globanet.com/zoom/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="2e5b9-107">連接器會將會議的內容， (包括聊天、錄製的檔案，以及從「縮放會議」帳戶) 的中繼資料轉換為電子郵件訊息格式，然後再將這些專案匯入 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-107">The connector converts the content of the meetings (including chats, recorded files, and metadata) from the Zoom Meetings account to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="2e5b9-108">在縮放會議資料儲存在使用者信箱中之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-108">After Zoom Meetings data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="2e5b9-109">在 Microsoft 365 中使用「縮放會議連接器」匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-meetings-data"></a><span data-ttu-id="2e5b9-110">封存縮放會議資料的概述</span><span class="sxs-lookup"><span data-stu-id="2e5b9-110">Overview of archiving Zoom Meetings data</span></span>

<span data-ttu-id="2e5b9-111">下列概要說明如何使用連接器封存 Microsoft 365 中的「縮放會議」資料。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-111">The following overview explains the process of using a connector to archive Zoom Meetings data in Microsoft 365.</span></span>

![縮放會議封存工作流程](../media/ZoomMeetingsConnectorWorkflow.png)

1. <span data-ttu-id="2e5b9-113">您的組織與「縮放會議」搭配設定和設定縮放會議網站。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-113">Your organization works with Zoom Meetings to set up and configure a Zoom Meetings site.</span></span>

2. <span data-ttu-id="2e5b9-114">每24小時一次，來自縮放會議的會議專案會複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-114">Once every 24 hours, meeting items from Zoom Meetings are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="2e5b9-115">連接線也會將會議內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-115">The connector also converts the content of the meetings to an email message format.</span></span>

3. <span data-ttu-id="2e5b9-116">您在 Microsoft 365 規範中心建立的「縮放會議」連接器，會每天連線到 Globanet Merge1，並將會議郵件傳送至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-116">The Zoom Meetings connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the meeting messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="2e5b9-117">連接器會使用 *電子郵件* 屬性和自動使用者對應的值，將已轉換的會議專案匯入到特定使用者的信箱，如步驟3所述。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-117">The connector imports the converted meeting items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="2e5b9-118">在使用者信箱中建立名為「 **縮放會議** 」的 [收件匣] 資料夾中的新子資料夾，並將會議專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-118">A new subfolder in the Inbox folder named **Zoom Meetings** is created in user mailboxes, and the meeting items are imported to that folder.</span></span> <span data-ttu-id="2e5b9-119">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="2e5b9-120">每個會議專案都包含此屬性，其會填入會議每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-120">Every meeting item contains this property, which is populated with the email address of every participant of the meeting.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2e5b9-121">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="2e5b9-121">Before you begin</span></span>

- <span data-ttu-id="2e5b9-122">為 Microsoft connector 建立 Globanet Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="2e5b9-123">若要建立此帳戶，請與 [Globanet 客戶支援](https://globanet.com/ms-connectors-contact)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-123">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="2e5b9-124">當您在步驟1中建立連接器時，您會登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="2e5b9-125">取得組織的「縮放商務」或「縮放企業」企業帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-125">Obtain the username and password for your organization's Zoom Business or Zoom Enterprise account.</span></span> <span data-ttu-id="2e5b9-126">當您設定縮放會議連接器時，您必須在步驟2中登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-126">You'll need to sign into this account in Step 2 when you configure the Zoom Meetings connector.</span></span>

- <span data-ttu-id="2e5b9-127">在 [縮放 Marketplace](https://marketplace.zoom.us)中建立下列應用程式：</span><span class="sxs-lookup"><span data-stu-id="2e5b9-127">Create the following applications in the [Zoom Marketplace](https://marketplace.zoom.us):</span></span>

  - <span data-ttu-id="2e5b9-128">OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="2e5b9-128">OAuth application</span></span>

  - <span data-ttu-id="2e5b9-129">JWT 應用程式</span><span class="sxs-lookup"><span data-stu-id="2e5b9-129">JWT application</span></span>

  <span data-ttu-id="2e5b9-130">在您建立這些應用程式之後，縮放平臺會產生一組唯一的認證，用以產生權杖。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-130">After you create these applications, the Zoom platform generates a set of unique credentials used to generate the tokens.</span></span> <span data-ttu-id="2e5b9-131">當連接至縮放帳戶時，會使用這些權杖來驗證連接器，並將專案複製到 Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-131">These tokens are used to authenticate the connector when it connects to your Zoom account and copies items to the Merge1 site.</span></span> <span data-ttu-id="2e5b9-132">當您在步驟2中設定縮放連接器時，您將會使用這些標記。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-132">You will use these tokens when you configure the Zoom connector in Step 2.</span></span>

  <span data-ttu-id="2e5b9-133">如需如何建立 OAuth 和 JWT 應用程式的逐步指示，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-133">For step-by step instructions on how to create the OAuth and JWT applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="2e5b9-134">在步驟1中建立縮放會議連接器的使用者 (，並在步驟 3) 中完成，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-134">The user who creates the Zoom Meetings connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="2e5b9-135">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-135">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2e5b9-136">根據預設，此角色不會指派給 Exchange Online 中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-136">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="2e5b9-137">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="2e5b9-138">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="2e5b9-139">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-139">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-zoom-meetings-connector"></a><span data-ttu-id="2e5b9-140">步驟1：設定縮放會議連接器</span><span class="sxs-lookup"><span data-stu-id="2e5b9-140">Step 1: Set up the Zoom Meetings connector</span></span>

<span data-ttu-id="2e5b9-141">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** ，並建立縮放會議連接器。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-141">The first step is to access the **Data Connectors** in the Microsoft 365 compliance center and create a Zoom Meetings connector.</span></span>

1. <span data-ttu-id="2e5b9-142">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [ **資料連線線**  >  **縮放會議** ]。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-142">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Zoom Meetings** .</span></span>

2. <span data-ttu-id="2e5b9-143">在 [ **縮放會議** 產品描述] 頁面上，按一下 [ **新增連接器** ]。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-143">On the **Zoom Meetings** product description page, click **Add connector** .</span></span>

3. <span data-ttu-id="2e5b9-144">在 [ **服務條款** ] 頁面上，按一下 [ **接受** ]。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-144">On the **Terms of service** page, click **Accept** .</span></span>

4. <span data-ttu-id="2e5b9-145">輸入識別連接器的唯一名稱，然後按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-145">Enter a unique name that identifies the connector, and then click **Next** .</span></span>

5. <span data-ttu-id="2e5b9-146">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-146">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-zoom-meetings-connector"></a><span data-ttu-id="2e5b9-147">步驟2：設定縮放會議連接器</span><span class="sxs-lookup"><span data-stu-id="2e5b9-147">Step 2: Configure the Zoom Meetings connector</span></span>

<span data-ttu-id="2e5b9-148">第二個步驟是在 Merge1 網站上設定縮放會議連接器。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-148">The second step is to configure the Zoom Meetings connector on the Merge1 site.</span></span> <span data-ttu-id="2e5b9-149">如需如何在 Globanet Merge1 網站上設定縮放會議連接器的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-149">For more information about how to configure the Zoom Meetings connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="2e5b9-150">按一下 **[儲存] & 完成** 之後，就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-150">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="2e5b9-151">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="2e5b9-151">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="2e5b9-152">在 [將 **外部使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-152">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="2e5b9-153">[縮放會議專案] 包含稱為「 *電子郵件* 」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-153">Zoom Meetings items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="2e5b9-154">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入到該使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-154">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox</span></span>

2. <span data-ttu-id="2e5b9-155">在 [系統 **管理員同意** ] 頁面上，按一下 [ **提供同意** ]。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-155">On the **Admin Consent** page, click **Provide Consent** .</span></span> <span data-ttu-id="2e5b9-156">您將會重新導向至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-156">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="2e5b9-157">按一下 [ **接受** ] 以提供同意。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-157">Click **Accept** to provide the consent.</span></span>
  
   <span data-ttu-id="2e5b9-158">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-158">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="2e5b9-159">若要提供系統管理員同意，您必須使用 Microsoft 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-159">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="2e5b9-160">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-160">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="2e5b9-161">按 **[下一步]** ，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-161">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-zoom-meetings-connector"></a><span data-ttu-id="2e5b9-162">步驟4：監視縮放會議連接器</span><span class="sxs-lookup"><span data-stu-id="2e5b9-162">Step 4: Monitor the Zoom Meetings connector</span></span>

<span data-ttu-id="2e5b9-163">在您建立縮放會議連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-163">After you create the Zoom Meetings connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="2e5b9-164">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-164">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="2e5b9-165">按一下 [ **連接器** ] 索引標籤，然後選取 [ **縮放會議** ] 連接器以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-165">Click the **Connectors** tab and then select the **Zoom Meetings** connector to display the flyout page.</span></span> <span data-ttu-id="2e5b9-166">此頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-166">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="2e5b9-167">在 [ **連接器狀態與來源** ] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-167">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="2e5b9-168">此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-168">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2e5b9-169">已知問題</span><span class="sxs-lookup"><span data-stu-id="2e5b9-169">Known issues</span></span>

- <span data-ttu-id="2e5b9-170">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-170">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="2e5b9-171">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-171">Support for larger items will be available at a later date.</span></span>

- <span data-ttu-id="2e5b9-172">若要使縮放會議連接器能夠運作，您必須在設定縮放會議時啟用錄製。</span><span class="sxs-lookup"><span data-stu-id="2e5b9-172">For the Zoom Meetings connector to work, you must enable recordings when setting up Zoom Meetings.</span></span>
