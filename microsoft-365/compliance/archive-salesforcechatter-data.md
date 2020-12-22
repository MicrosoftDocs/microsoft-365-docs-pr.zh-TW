---
title: 設定連接器以封存 Microsoft 365 中的 Salesforce 交談資料
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
description: 系統管理員可以設定連接器，將 Salesforce 交談資料從 Globanet 匯入至 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: 60d86cd01ef8da3a02839d4a3f815be02dc1ee01
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722971"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data-preview"></a><span data-ttu-id="4fa04-105">設定連接器以封存 Salesforce 交談資料 (預覽) </span><span class="sxs-lookup"><span data-stu-id="4fa04-105">Set up a connector to archive Salesforce Chatter data (preview)</span></span>

<span data-ttu-id="4fa04-106">使用 Microsoft 365 規範中心內的 Globanet 連接器，從 Salesforce 交談平臺匯入並封存資料至您的 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="4fa04-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Salesforce Chatter platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="4fa04-107">Globanet 提供 [Salesforce 交談](http://globanet.com/chatter/) 連接器，可從協力廠商資料來源捕獲專案，並將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4fa04-107">Globanet provides a [Salesforce Chatter](http://globanet.com/chatter/) connector that captures items from the third-party data source and imports those items to Microsoft 365.</span></span> <span data-ttu-id="4fa04-108">連接器會將聊天、附件和張貼等內容轉換為電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="4fa04-108">The connector converts the content such as chats, attachments, and posts from Salesforce Chatter to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="4fa04-109">將 Salesforce 交談資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="4fa04-109">After Salesforce Chatter data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="4fa04-110">使用 Salesforce 交談連接器匯入和封存 Microsoft 365 中的資料可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="4fa04-110">Using a Salesforce Chatter connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-salesforce-chatter-data"></a><span data-ttu-id="4fa04-111">封存 Salesforce 交談資料的概覽</span><span class="sxs-lookup"><span data-stu-id="4fa04-111">Overview of archiving Salesforce Chatter data</span></span>

<span data-ttu-id="4fa04-112">下列概要說明如何使用連接器封存 Microsoft 365 中的 Salesforce 交談資料。</span><span class="sxs-lookup"><span data-stu-id="4fa04-112">The following overview explains the process of using a connector to archive the Salesforce Chatter data in Microsoft 365.</span></span>

![Salesforce 交談資料的封存工作流程](../media/SalesforceChatterConnectorWorkflow.png)

1. <span data-ttu-id="4fa04-114">您的組織與 Salesforce 交談搭配使用，以設定和設定 Salesforce 交談網站。</span><span class="sxs-lookup"><span data-stu-id="4fa04-114">Your organization works with Salesforce Chatter to set up and configure a Salesforce Chatter site.</span></span>

2. <span data-ttu-id="4fa04-115">每24小時一次，Salesforce 交談專案會複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="4fa04-115">Once every 24 hours, Salesforce Chatter items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="4fa04-116">連接器也會將交談專案 Salesforce 為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="4fa04-116">The connector also Salesforce Chatter items to an email message format.</span></span>

3. <span data-ttu-id="4fa04-117">您在 Microsoft 365 規範中心建立的 Salesforce 交談連接器會每天連線到 Globanet Merge1 網站，並將交談內容傳送至 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="4fa04-117">The Salesforce Chatter connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the Chatter content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="4fa04-118">連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述之自動使用者對應的 *電子郵件* 屬性值，將轉換後的專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="4fa04-118">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="4fa04-119">在使用者信箱中建立名為 [ **Salesforce 交談** ] 的 [收件匣] 資料夾中的子資料夾，並將專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="4fa04-119">A subfolder in the Inbox folder named **Salesforce Chatter** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="4fa04-120">連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。</span><span class="sxs-lookup"><span data-stu-id="4fa04-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="4fa04-121">每個交談專案都包含此屬性，它會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4fa04-121">Every Chatter item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4fa04-122">開始之前</span><span class="sxs-lookup"><span data-stu-id="4fa04-122">Before you begin</span></span>

- <span data-ttu-id="4fa04-123">建立 Microsoft 連接器的 Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="4fa04-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="4fa04-124">若要建立帳戶，請與 [Globanet 客戶支援](https://globanet.com/contact-us/)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="4fa04-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="4fa04-125">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="4fa04-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="4fa04-126">建立 Salesforce 應用程式，並在中取得權杖 [https://salesforce.com](https://salesforce.com) 。</span><span class="sxs-lookup"><span data-stu-id="4fa04-126">Create a Salesforce application and acquire a token at [https://salesforce.com](https://salesforce.com).</span></span> <span data-ttu-id="4fa04-127">您必須以系統管理員身分登入 Salesforce 帳戶，並取得使用者個人 token 以匯入資料。</span><span class="sxs-lookup"><span data-stu-id="4fa04-127">You'll need to log into the Salesforce account as an admin and get a user personal token to import data.</span></span> <span data-ttu-id="4fa04-128">此外，觸發器必須在交談網站上發佈，以捕獲更新、刪除及編輯。</span><span class="sxs-lookup"><span data-stu-id="4fa04-128">Also, triggers need to be published on the Chatter site to capture updates, deletes, and edits.</span></span> <span data-ttu-id="4fa04-129">這些觸發器會在通道上建立文章，Merge1 將會從通道中捕獲資訊。</span><span class="sxs-lookup"><span data-stu-id="4fa04-129">These triggers will create a post on a channel, and Merge1 will capture the information from the channel.</span></span> <span data-ttu-id="4fa04-130">如需如何建立應用程式並取得權杖的逐步指示，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="4fa04-130">For step-by-step instructions about how to create the application and acquire the token, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="4fa04-131">在步驟1中建立 Salesforce 交談連接器的使用者 (，並在步驟 3) 中完成，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="4fa04-131">The user who creates the Salesforce Chatter connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="4fa04-132">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="4fa04-132">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4fa04-133">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="4fa04-133">By default, this role isn’t assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="4fa04-134">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="4fa04-134">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="4fa04-135">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="4fa04-135">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="4fa04-136">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="4fa04-136">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a><span data-ttu-id="4fa04-137">步驟1：設定 Salesforce 交談連接器</span><span class="sxs-lookup"><span data-stu-id="4fa04-137">Step 1: Set up the Salesforce Chatter connector</span></span>

<span data-ttu-id="4fa04-138">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** 頁面，並建立交談資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="4fa04-138">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Chatter data.</span></span>

1. <span data-ttu-id="4fa04-139">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **Salesforce 交談**]。</span><span class="sxs-lookup"><span data-stu-id="4fa04-139">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Salesforce Chatter**.</span></span>

2. <span data-ttu-id="4fa04-140">在 [ **Salesforce 交談** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="4fa04-140">On the **Salesforce Chatter** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="4fa04-141">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="4fa04-141">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="4fa04-142">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4fa04-142">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="4fa04-143">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="4fa04-143">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-salesforce-chatter-on-the-globanet-merge1-site"></a><span data-ttu-id="4fa04-144">步驟2：設定 Globanet Merge1 網站上的 Salesforce 交談</span><span class="sxs-lookup"><span data-stu-id="4fa04-144">Step 2: Configure the Salesforce Chatter on the Globanet Merge1 site</span></span>

<span data-ttu-id="4fa04-145">第二個步驟是設定 Globanet Merge1 網站上的 Salesforce 交談連接器。</span><span class="sxs-lookup"><span data-stu-id="4fa04-145">The second step is to configure the Salesforce Chatter connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="4fa04-146">如需如何設定 Salesforce 交談連接器的詳細資訊，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="4fa04-146">For information about how to configure the Salesforce Chatter connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="4fa04-147">按一下 **[儲存] & 完成之後，** 就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4fa04-147">After you click **Save & Finish,** the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="4fa04-148">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="4fa04-148">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="4fa04-149">若要對應使用者，並完成 Microsoft 365 規範中心內的連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="4fa04-149">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="4fa04-150">在 [將 **Salesforce 交談使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="4fa04-150">On the **Map Salesforce Chatter users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="4fa04-151">[Salesforce 交談] 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4fa04-151">The Salesforce Chatter items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="4fa04-152">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="4fa04-152">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="4fa04-153">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="4fa04-153">click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a><span data-ttu-id="4fa04-154">步驟4：監控 Salesforce 交談連接器</span><span class="sxs-lookup"><span data-stu-id="4fa04-154">Step 4: Monitor the Salesforce Chatter connector</span></span>

<span data-ttu-id="4fa04-155">在您建立 Salesforce 交談連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="4fa04-155">After you create the Salesforce Chatter connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="4fa04-156">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="4fa04-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="4fa04-157">按一下 [ **連接器** ] 索引標籤，然後按一下 [ **Salesforce 交談** 連接器] 以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="4fa04-157">click the **Connectors** tab and then click the **Salesforce Chatter** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="4fa04-158">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="4fa04-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="4fa04-159">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="4fa04-159">This log contains data that's been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="4fa04-160">已知問題</span><span class="sxs-lookup"><span data-stu-id="4fa04-160">Known issues</span></span>

- <span data-ttu-id="4fa04-161">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="4fa04-161">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="4fa04-162">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="4fa04-162">Support for larger items will be available at a later date.</span></span>
