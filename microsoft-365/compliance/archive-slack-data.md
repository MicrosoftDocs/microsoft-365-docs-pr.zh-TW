---
title: 設定在 Microsoft 365 中封存寬限資料的連接器
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
description: 系統管理員可以設定連接器，將資料從 Globanet 寬限匯入至 Microsoft 365。 此資料連線器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 7c796c16b5a4b305c5d4b5259337ca28d9bfde9a
ms.sourcegitcommit: 96b4593becc9450af136c528844e858c6e88b5a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269450"
---
# <a name="set-up-a-connector-to-archive-slack-data"></a><span data-ttu-id="60b61-104">設定連接器以封存寬限資料</span><span class="sxs-lookup"><span data-stu-id="60b61-104">Set up a connector to archive Slack data</span></span>

<span data-ttu-id="60b61-105">使用 Microsoft 365 規範中心的 Globanet 連接器，將協力廠商資料從社交媒體、立即訊息及檔共同作業平臺匯入至您的 Microsoft 365 組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="60b61-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive third-party data from social media, instant messaging, and document collaboration platforms to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="60b61-106">Globanet 提供了一個寬延時間連接器，可設定為定期捕獲協力廠商資料來源中的專案 () 然後將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="60b61-106">Globanet provides a Slack connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="60b61-107">時差會從寬限 API 提取郵件和檔案，並將其轉換成電子郵件格式，然後將該專案匯入至使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="60b61-107">Slack pulls messages and files from the Slack API and converts them to an email message format and then imports the item to user mailboxes.</span></span>

<span data-ttu-id="60b61-108">在使用者信箱中儲存時差資料後，您可以套用 Microsoft 365 規範功能（例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性）。</span><span class="sxs-lookup"><span data-stu-id="60b61-108">After Slack data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="60b61-109">使用時差連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="60b61-109">Using a Slack connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-slack-data"></a><span data-ttu-id="60b61-110">封存寬限資料的概覽</span><span class="sxs-lookup"><span data-stu-id="60b61-110">Overview of archiving Slack data</span></span>

<span data-ttu-id="60b61-111">下列概要說明使用連接器封存 Microsoft 365 中的時差資訊的程式。</span><span class="sxs-lookup"><span data-stu-id="60b61-111">The following overview explains the process of using a connector to archive the Slack information in Microsoft 365.</span></span>

![寬限時間封存工作流程](../media/SlackConnectorWorkflow.png)

1. <span data-ttu-id="60b61-113">您的組織使用可寬延時間設定和設定寬限網站。</span><span class="sxs-lookup"><span data-stu-id="60b61-113">Your organization works with Slack to set up and configure a Slack site.</span></span>

2. <span data-ttu-id="60b61-114">每隔24小時會將聊天訊息從寬限時間複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="60b61-114">Once every 24 hours, chat messages from Slack are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="60b61-115">連接器也會將聊天訊息的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="60b61-115">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="60b61-116">您在 Microsoft 365 規範中心內建立的寬延時間連接器會每天連線到 Globanet Merge1 網站，並將聊天訊息傳送至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="60b61-116">The Slack connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the chat messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="60b61-117">連接器會使用 *電子郵件* 屬性和自動使用者對應的值，將已轉換的交談訊息項目匯入至特定使用者的信箱，如步驟3所述。</span><span class="sxs-lookup"><span data-stu-id="60b61-117">The connector imports the converted chat message items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="60b61-118">在使用者信箱中建立名為「 **時差** 」的收件匣資料夾中的新子資料夾，聊天訊息項目將會匯入至該資料夾。</span><span class="sxs-lookup"><span data-stu-id="60b61-118">A new subfolder in the Inbox folder named **Slack** is created in the user mailboxes, and the chat message items will be imported to that folder.</span></span> <span data-ttu-id="60b61-119">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="60b61-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="60b61-120">每個聊天訊息都包含此內容，該屬性會填入聊天訊息每一位參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="60b61-120">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="60b61-121">開始之前</span><span class="sxs-lookup"><span data-stu-id="60b61-121">Before you begin</span></span>

- <span data-ttu-id="60b61-122">為 Microsoft connector 建立 Globanet Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="60b61-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="60b61-123">若要這麼做，請與 [Globanet 客戶支援](https://globanet.com/ms-connectors-contact)部門聯繫。</span><span class="sxs-lookup"><span data-stu-id="60b61-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="60b61-124">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="60b61-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="60b61-125">取得組織的寬限時間企業帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="60b61-125">Obtain the username and password for your organization's Slack enterprise account.</span></span> <span data-ttu-id="60b61-126">當您設定寬限時間時，您必須在步驟2中登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="60b61-126">You'll need to sign into this account in Step 2 when you configure Slack.</span></span>

- <span data-ttu-id="60b61-127">在步驟1中建立時差連接器的使用者 (，並在步驟 3) 中完成，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="60b61-127">The user who creates the Slack connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="60b61-128">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="60b61-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="60b61-129">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="60b61-129">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="60b61-130">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="60b61-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="60b61-131">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="60b61-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="60b61-132">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="60b61-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-slack-connector"></a><span data-ttu-id="60b61-133">步驟1：設定時差連接器</span><span class="sxs-lookup"><span data-stu-id="60b61-133">Step 1: Set up the Slack connector</span></span>

<span data-ttu-id="60b61-134">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** 頁面，並為寬限資料建立連接器。</span><span class="sxs-lookup"><span data-stu-id="60b61-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Slack data.</span></span>

1. <span data-ttu-id="60b61-135">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **寬限時間**]。</span><span class="sxs-lookup"><span data-stu-id="60b61-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Slack**.</span></span>

2. <span data-ttu-id="60b61-136">在 [ **時差** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="60b61-136">On the **Slack** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="60b61-137">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="60b61-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="60b61-138">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="60b61-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="60b61-139">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="60b61-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-slack"></a><span data-ttu-id="60b61-140">步驟2：設定寬限時間</span><span class="sxs-lookup"><span data-stu-id="60b61-140">Step 2: Configure Slack</span></span>

<span data-ttu-id="60b61-141">第二個步驟是設定 Merge1 網站上的寬延時間連接器。</span><span class="sxs-lookup"><span data-stu-id="60b61-141">The second step is to configure the Slack connector on the Merge1 site.</span></span> <span data-ttu-id="60b61-142">如需如何在 Globanet Merge1 網站上設定寬限時間連接器的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="60b61-142">For more information about how to configure the Slack connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span></span>

<span data-ttu-id="60b61-143">在您按一下 **[儲存] & 完成**之後，您會回到 Microsoft 365 規範中心，移至 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="60b61-143">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="60b61-144">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="60b61-144">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="60b61-145">在 [將 **外部使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="60b61-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="60b61-146">[寬限時間] 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="60b61-146">Slack items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="60b61-147">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="60b61-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="60b61-148">在 [系統 **管理員同意** ] 頁面上，按一下 [ **提供同意** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="60b61-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="60b61-149">您將會重新導向至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="60b61-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="60b61-150">按一下 [ **接受** ] 以提供同意。</span><span class="sxs-lookup"><span data-stu-id="60b61-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="60b61-151">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="60b61-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="60b61-152">若要提供系統管理員同意，您必須使用 Microsoft 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="60b61-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="60b61-153">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="60b61-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="60b61-154">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="60b61-154">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-slack-connector"></a><span data-ttu-id="60b61-155">步驟4：監控寬限連接線</span><span class="sxs-lookup"><span data-stu-id="60b61-155">Step 4: Monitor the Slack connector</span></span>

<span data-ttu-id="60b61-156">在您建立寬限時間連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="60b61-156">After you create the Slack connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="60b61-157">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="60b61-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="60b61-158">按一下 [ **連接器** ] 索引標籤，然後選取 [ **時差** ] 連接器以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="60b61-158">Click the **Connectors** tab and then select the **Slack** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="60b61-159">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="60b61-159">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="60b61-160">此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="60b61-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="60b61-161">已知問題</span><span class="sxs-lookup"><span data-stu-id="60b61-161">Known issues</span></span>

- <span data-ttu-id="60b61-162">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="60b61-162">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="60b61-163">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="60b61-163">Support for larger items will be available at a later date.</span></span>