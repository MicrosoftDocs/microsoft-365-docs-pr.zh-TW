---
title: 設定連接器以封存 Microsoft 365 中的 Symphony 資料
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
ROBOTS: NOINDEX, NOFOLLOW
description: 系統管理員可以設定連接器，將資料從 Globanet Symphony 匯入 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 29af0cda6d1f6b194c13047382ab7e01b6b200dc
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361794"
---
# <a name="set-up-a-connector-to-archive-symphony-data-preview"></a><span data-ttu-id="cd877-104">設定連接器以封存 Symphony 資料 (預覽) </span><span class="sxs-lookup"><span data-stu-id="cd877-104">Set up a connector to archive Symphony data (preview)</span></span>

<span data-ttu-id="cd877-105">使用 Microsoft 365 規範中心內的 Globanet 連接器，將 Symphony 資料匯入至您的 Microsoft 365 組織中的使用者信箱，並將其封存。</span><span class="sxs-lookup"><span data-stu-id="cd877-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive Symphony data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="cd877-106">Symphony 是金融服務行業中使用的訊息和共同作業平臺。</span><span class="sxs-lookup"><span data-stu-id="cd877-106">Symphony is a messaging and collaboration platform used in the financial services industry.</span></span> <span data-ttu-id="cd877-107">Globanet 提供 Symphony 的 Microsoft 365 規範中心中的 [資料連線器](https://globanet.com/symphony) ，您可以設定為定期捕獲協力廠商資料來源中的專案 () 然後將這些專案匯入至使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="cd877-107">Globanet provides a [Symphony data connector](https://globanet.com/symphony) in the Microsoft 365 compliance center that you can configured to capture items from the third-party data source (on a regular basis) and then import those items to user mailboxes.</span></span> <span data-ttu-id="cd877-108">連接器會將專案的內容從 Symphony 帳戶轉換成電子郵件格式，然後將該專案匯入 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="cd877-108">The connector converts the content of an item from the Symphony account to an email message format and then imports the item to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="cd877-109">在使用者信箱中儲存 Symphony 通訊之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="cd877-109">After Symphony communications are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="cd877-110">在 Microsoft 365 中使用 Symphony 連接器匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="cd877-110">Using a Symphony connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-symphony-data"></a><span data-ttu-id="cd877-111">封存 Symphony 資料一覽</span><span class="sxs-lookup"><span data-stu-id="cd877-111">Overview of archiving Symphony data</span></span>

<span data-ttu-id="cd877-112">下列概要說明如何使用資料連線器封存 Microsoft 365 中的 Symphony 通訊。</span><span class="sxs-lookup"><span data-stu-id="cd877-112">The following overview explains the process of using a data connector to archive Symphony communications in Microsoft 365.</span></span>

![Symphony 封存工作流程](../media/SymphonyConnectorWorkflow.png)

1. <span data-ttu-id="cd877-114">您的組織與 Symphony 搭配使用，以設定及設定 Symphony 網站。</span><span class="sxs-lookup"><span data-stu-id="cd877-114">Your organization works with Symphony to set up and configure a Symphony site.</span></span>

2. <span data-ttu-id="cd877-115">每隔24小時，就會將 Symphony 的聊天訊息複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="cd877-115">Once every 24 hours, chat messages from Symphony are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="cd877-116">連接器也會將聊天訊息的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="cd877-116">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="cd877-117">您在 Microsoft 365 規範中心建立的 Symphony 連接器會每天連線到 Globanet Merge1 網站，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="cd877-117">The Symphony connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="cd877-118">連接器會使用 [步驟 3] 中所述之自動使用者對應的 *電子郵件* 屬性值，將已轉換的訊息項目匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="cd877-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="cd877-119">在使用者信箱中建立名為 **Symphony** 之 [收件匣] 資料夾中的新子資料夾，並將訊息項目匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="cd877-119">A new subfolder in the Inbox folder named **Symphony** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="cd877-120">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="cd877-120">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="cd877-121">每個聊天訊息都包含此內容，該屬性會填入聊天訊息每一位參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cd877-121">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cd877-122">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="cd877-122">Before you begin</span></span>

- <span data-ttu-id="cd877-123">透過接受 Symphony 連接器的條款及條件來建立 Globanet Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="cd877-123">Create a Globanet Merge1 account by accepting the terms and conditions for the Symphony connector.</span></span> <span data-ttu-id="cd877-124">若要這麼做，請與 [Globanet 客戶支援](https://globanet.com/contact-us)部門聯繫。</span><span class="sxs-lookup"><span data-stu-id="cd877-124">To do this, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="cd877-125">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="cd877-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="cd877-126">在步驟1中建立 Symphony 連接器的使用者 (，並在步驟 3) 中完成，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="cd877-126">The user who creates the Symphony connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="cd877-127">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="cd877-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="cd877-128">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="cd877-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="cd877-129">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="cd877-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="cd877-130">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="cd877-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="cd877-131">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="cd877-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-symphony-connector"></a><span data-ttu-id="cd877-132">步驟1：設定 Symphony 連接器</span><span class="sxs-lookup"><span data-stu-id="cd877-132">Step 1: Set up the Symphony connector</span></span>

<span data-ttu-id="cd877-133">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** 頁面，並建立 Symphony 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="cd877-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Symphony data.</span></span>

1. <span data-ttu-id="cd877-134">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **Symphony**]。</span><span class="sxs-lookup"><span data-stu-id="cd877-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Symphony**.</span></span>

2. <span data-ttu-id="cd877-135">在 [ **Symphony** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="cd877-135">On the **Symphony** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="cd877-136">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="cd877-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="cd877-137">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cd877-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="cd877-138">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="cd877-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="configure-the-symphony-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="cd877-139">設定 Globanet Merge1 網站上的 Symphony 連接器</span><span class="sxs-lookup"><span data-stu-id="cd877-139">Configure the Symphony connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="cd877-140">第二個步驟是設定 Merge1 網站上的 Symphony 連接器。</span><span class="sxs-lookup"><span data-stu-id="cd877-140">The second step is to configure the Symphony connector on the Merge1 site.</span></span> <span data-ttu-id="cd877-141">如需在 Globanet Merge1 網站中設定 Symphony 連接器的詳細資訊，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="cd877-141">For information about configuring  the Symphony connector in the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="cd877-142">在您按一下 **[儲存] & 完成**之後，您會傳回 Microsoft 365 規範中心至 [連接器] 嚮導的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cd877-142">After you click **Save & Finish**, you are returned to the Microsoft 365 compliance center, to the **User mapping** page of the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="cd877-143">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="cd877-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="cd877-144">若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cd877-144">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="cd877-145">在 [將 **外部使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="cd877-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="cd877-146">Symphony 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cd877-146">The Symphony items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="cd877-147">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="cd877-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="cd877-148">在 [系統 **管理員同意** ] 頁面上，按一下 [ **提供同意** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="cd877-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="cd877-149">您將會重新導向至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="cd877-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="cd877-150">按一下 [ **接受** ] 以提供同意。</span><span class="sxs-lookup"><span data-stu-id="cd877-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="cd877-151">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="cd877-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="cd877-152">若要提供系統管理員同意，您必須使用 Microsoft 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="cd877-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="cd877-153">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="cd877-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="cd877-154">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="cd877-154">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-symphony-connector"></a><span data-ttu-id="cd877-155">步驟4：監控 Symphony 連接器</span><span class="sxs-lookup"><span data-stu-id="cd877-155">Step 4: Monitor the Symphony connector</span></span>

<span data-ttu-id="cd877-156">在您建立 Symphony 連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="cd877-156">After you create the Symphony connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="cd877-157">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="cd877-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="cd877-158">按一下 [ **連接器** ] 索引標籤，然後選取 **Symphony** 連接器以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="cd877-158">Click the **Connectors** tab and then select the **Symphony** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="cd877-159">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="cd877-159">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="cd877-160">此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="cd877-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="cd877-161">已知問題</span><span class="sxs-lookup"><span data-stu-id="cd877-161">Known issues</span></span>

- <span data-ttu-id="cd877-162">此時，我們不支援匯入大於 10 MB 的附件，但較大專案的支援將于之後提供。</span><span class="sxs-lookup"><span data-stu-id="cd877-162">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>