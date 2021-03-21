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
description: 系統管理員可以設定連接器，將資料從 Globanet Symphony 匯入 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: 5a23e88b0240bd47b552aa62cd704a0560b01206
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925027"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a><span data-ttu-id="d4da6-105">設定連接器以封存 Symphony 資料</span><span class="sxs-lookup"><span data-stu-id="d4da6-105">Set up a connector to archive Symphony data</span></span>

<span data-ttu-id="d4da6-106">使用 Microsoft 365 規範中心內的 Globanet 連接器，將 Symphony 資料匯入至您的 Microsoft 365 組織中的使用者信箱，並將其封存。</span><span class="sxs-lookup"><span data-stu-id="d4da6-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive Symphony data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="d4da6-107">Symphony 是金融服務行業中使用的訊息和共同作業平臺。</span><span class="sxs-lookup"><span data-stu-id="d4da6-107">Symphony is a messaging and collaboration platform used in the financial services industry.</span></span> <span data-ttu-id="d4da6-108">Globanet 提供 [Symphony](https://globanet.com/symphony) 的 Microsoft 365 規範中心中的資料連線器，您可以設定定期從協力廠商資料來源捕獲專案 () ，然後將這些專案匯入至使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="d4da6-108">Globanet provides a [Symphony](https://globanet.com/symphony) data connector in the Microsoft 365 compliance center that you can configure to capture items from the third-party data source (on a regular basis) and then import those items to user mailboxes.</span></span> <span data-ttu-id="d4da6-109">連接器會將專案的內容從 Symphony 帳戶轉換成電子郵件格式，然後將該專案匯入 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="d4da6-109">The connector converts the content of an item from the Symphony account to an email message format and then imports the item to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="d4da6-110">在使用者信箱中儲存 Symphony 通訊之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="d4da6-110">After Symphony communications are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="d4da6-111">在 Microsoft 365 中使用 Symphony 連接器匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="d4da6-111">Using a Symphony connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-symphony-data"></a><span data-ttu-id="d4da6-112">封存 Symphony 資料一覽</span><span class="sxs-lookup"><span data-stu-id="d4da6-112">Overview of archiving Symphony data</span></span>

<span data-ttu-id="d4da6-113">下列概要說明如何使用資料連線器封存 Microsoft 365 中的 Symphony 通訊。</span><span class="sxs-lookup"><span data-stu-id="d4da6-113">The following overview explains the process of using a data connector to archive Symphony communications in Microsoft 365.</span></span>

![Symphony 封存工作流程](../media/SymphonyConnectorWorkflow.png)

1. <span data-ttu-id="d4da6-115">您的組織與 Symphony 搭配使用，以設定及設定 Symphony 網站。</span><span class="sxs-lookup"><span data-stu-id="d4da6-115">Your organization works with Symphony to set up and configure a Symphony site.</span></span>

2. <span data-ttu-id="d4da6-116">每隔24小時，就會將 Symphony 的聊天訊息複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="d4da6-116">Once every 24 hours, chat messages from Symphony are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="d4da6-117">連接器也會將聊天訊息的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="d4da6-117">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="d4da6-118">您在 Microsoft 365 規範中心建立的 Symphony 連接器會每天連線到 Globanet Merge1 網站，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="d4da6-118">The Symphony connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="d4da6-119">連接器會使用 [步驟 3] 中所述之自動使用者對應的 *電子郵件* 屬性值，將已轉換的訊息項目匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="d4da6-119">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="d4da6-120">在使用者信箱中建立名為 **Symphony** 之 [收件匣] 資料夾中的新子資料夾，並將訊息項目匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="d4da6-120">A new subfolder in the Inbox folder named **Symphony** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="d4da6-121">連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。</span><span class="sxs-lookup"><span data-stu-id="d4da6-121">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="d4da6-122">每個聊天訊息都包含此內容，該屬性會填入每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d4da6-122">Every chat message contains this property, which is populated with the email address for every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d4da6-123">開始之前</span><span class="sxs-lookup"><span data-stu-id="d4da6-123">Before you begin</span></span>

- <span data-ttu-id="d4da6-124">為 Microsoft connector 建立 Globanet Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="d4da6-124">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="d4da6-125">若要建立帳戶，請與 [Globanet 客戶支援](https://globanet.com/ms-connectors-contact)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="d4da6-125">To create an account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="d4da6-126">當您在步驟1中建立連接器時，您會登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="d4da6-126">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="d4da6-127">在步驟1中建立 Symphony 連接器的使用者 (，並在步驟 3) 中完成，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="d4da6-127">The user who creates the Symphony connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d4da6-128">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="d4da6-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d4da6-129">根據預設，此角色不會指派給 Exchange Online 中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="d4da6-129">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="d4da6-130">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="d4da6-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d4da6-131">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="d4da6-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d4da6-132">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="d4da6-132">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-symphony-connector"></a><span data-ttu-id="d4da6-133">步驟1：設定 Symphony 連接器</span><span class="sxs-lookup"><span data-stu-id="d4da6-133">Step 1: Set up the Symphony connector</span></span>

<span data-ttu-id="d4da6-134">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** 頁面，並建立 Symphony 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="d4da6-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Symphony data.</span></span>

1. <span data-ttu-id="d4da6-135">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **Symphony**]。</span><span class="sxs-lookup"><span data-stu-id="d4da6-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Symphony**.</span></span>

2. <span data-ttu-id="d4da6-136">在 [ **Symphony** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="d4da6-136">On the **Symphony** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="d4da6-137">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="d4da6-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d4da6-138">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4da6-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="d4da6-139">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="d4da6-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="configure-the-symphony-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="d4da6-140">設定 Globanet Merge1 網站上的 Symphony 連接器</span><span class="sxs-lookup"><span data-stu-id="d4da6-140">Configure the Symphony connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="d4da6-141">第二個步驟是設定 Merge1 網站上的 Symphony 連接器。</span><span class="sxs-lookup"><span data-stu-id="d4da6-141">The second step is to configure the Symphony connector on the Merge1 site.</span></span> <span data-ttu-id="d4da6-142">如需在 Globanet Merge1 網站上設定 Symphony 連接器的詳細資訊，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="d4da6-142">For information about configuring  the Symphony connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="d4da6-143">按一下 **[儲存] & 完成** 之後，就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d4da6-143">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="d4da6-144">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="d4da6-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="d4da6-145">若要對應使用者，並完成 Microsoft 365 規範中心內的連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d4da6-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="d4da6-146">在 [將 **外部使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="d4da6-146">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="d4da6-147">Symphony 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d4da6-147">The Symphony items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="d4da6-148">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="d4da6-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="d4da6-149">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="d4da6-149">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-symphony-connector"></a><span data-ttu-id="d4da6-150">步驟4：監控 Symphony 連接器</span><span class="sxs-lookup"><span data-stu-id="d4da6-150">Step 4: Monitor the Symphony connector</span></span>

<span data-ttu-id="d4da6-151">在您建立 Symphony 連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="d4da6-151">After you create the Symphony connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d4da6-152">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="d4da6-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d4da6-153">按一下 [ **連接器** ] 索引標籤，然後選取 **Symphony** 連接器以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="d4da6-153">Click the **Connectors** tab and then select the **Symphony** connector to display the flyout page.</span></span> <span data-ttu-id="d4da6-154">此頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="d4da6-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="d4da6-155">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="d4da6-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="d4da6-156">此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d4da6-156">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d4da6-157">已知問題</span><span class="sxs-lookup"><span data-stu-id="d4da6-157">Known issues</span></span>

- <span data-ttu-id="d4da6-158">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="d4da6-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="d4da6-159">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="d4da6-159">Support for larger items will be available at a later date.</span></span>