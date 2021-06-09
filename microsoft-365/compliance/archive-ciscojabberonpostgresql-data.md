---
title: '設定連接器以封存 Microsoft 365 中 PostgreSQL 資料的 Cisco Jabber) '
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 瞭解如何在 Microsoft 365 規範中心內設定和使用連接器，以在 PostgreSQL 上的 Cisco jabber) 匯入並封存資料，以 Microsoft 365。
ms.openlocfilehash: 06ec56b3b28b28b82554048ec788114a0e5cb389
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842743"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data-preview"></a><span data-ttu-id="0cbc1-103">在 PostgreSQL 資料 (預覽] 中，設定用以封存 Cisco Jabber) 的連接器) </span><span class="sxs-lookup"><span data-stu-id="0cbc1-103">Set up a connector to archive Cisco Jabber on PostgreSQL data (preview)</span></span>

<span data-ttu-id="0cbc1-104">使用 Microsoft 365 規範中心內的 Veritas 連接器，將 Cisco jabber) 平臺的資料匯入並封存至您 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-104">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="0cbc1-105">Veritas 會[在 PostgreSQL 連接器上提供 Cisco jabber) ](https://www.veritas.com/insights/merge1/jabber) ，此連接器是透過設定從協力廠商資料來源 (定期捕獲專案) 並將這些專案匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-105">Veritas provides a [Cisco Jabber on PostgreSQL](https://www.veritas.com/insights/merge1/jabber) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="0cbc1-106">連接器會將郵件、聊天和共用內容等內容從 PostgreSQL 中的 Cisco Jabber) 轉換成電子郵件格式，然後再將這些專案匯入 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-106">The connector converts the content such as messages, chats, and shared content from Cisco Jabber on PostgreSQL to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="0cbc1-107">在 PostgreSQL 資料上的 Cisco jabber) 儲存在使用者信箱中之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-107">After Cisco Jabber on PostgreSQL data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="0cbc1-108">在 PostgreSQL 連接器上使用 Cisco jabber) ，以在 Microsoft 365 中匯入及封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-108">Using a Cisco Jabber on PostgreSQL connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a><span data-ttu-id="0cbc1-109">PostgreSQL 資料上封存 Cisco Jabber) 的概覽</span><span class="sxs-lookup"><span data-stu-id="0cbc1-109">Overview of archiving Cisco Jabber on PostgreSQL data</span></span>

<span data-ttu-id="0cbc1-110">下列概要說明如何使用連接器封存 Microsoft 365 中 PostgreSQL 資料上的 Cisco Jabber) 的處理常式。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-110">The following overview explains the process of using a connector to archive the Cisco Jabber on PostgreSQL data in Microsoft 365.</span></span>

![PostgreSQL 資料上的 Cisco Jabber) 封存工作流程](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. <span data-ttu-id="0cbc1-112">您的組織可以在 PostgreSQL 上使用 Cisco Jabber) ，在 PostgreSQL 網站上安裝和設定 Cisco Jabber) 。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-112">Your organization works with Cisco Jabber on PostgreSQL to set up and configure a Cisco Jabber on PostgreSQL site.</span></span>

2. <span data-ttu-id="0cbc1-113">每隔24小時，PostgreSQL 專案上的 Cisco Jabber) 都會複製到 Veritas Merge1 site。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-113">Once every 24 hours, Cisco Jabber on PostgreSQL items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="0cbc1-114">連接器也會將 PostgreSQL 專案上的 Cisco Jabber) 轉換成電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-114">The connector also converts Cisco Jabber on PostgreSQL items to an email message format.</span></span>

3. <span data-ttu-id="0cbc1-115">您在「Microsoft 365 規範中心」中建立 PostgreSQL 連接器上的 Cisco jabber) ，會每日連接至 Veritas Merge1 網站，並將 jabber) 內容傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-115">The Cisco Jabber on PostgreSQL connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the Jabber content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="0cbc1-116">連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述之自動使用者對應的 *電子郵件* 屬性值，將轉換後的專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-116">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="0cbc1-117">在使用者信箱中建立名為 **Cisco jabber) PostgreSQL 上** 的 [收件匣] 資料夾中的子資料夾，並將專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-117">A subfolder in the Inbox folder named **Cisco Jabber on PostgreSQL** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="0cbc1-118">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-118">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="0cbc1-119">每個 Jabber) 專案都包含此屬性，它會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-119">Every Jabber item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0cbc1-120">開始之前</span><span class="sxs-lookup"><span data-stu-id="0cbc1-120">Before you begin</span></span>

- <span data-ttu-id="0cbc1-121">建立 Microsoft 連接器的 Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-121">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="0cbc1-122">若要這麼做，請與 [Veritas 客戶支援](https://www.veritas.com/content/support/en_US)聯繫。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-122">To do this, contact [Veritas Customer Support](https://www.veritas.com/content/support/en_US).</span></span> <span data-ttu-id="0cbc1-123">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-123">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="0cbc1-124">在步驟 1 (中 PostgreSQL 連接器上建立 Cisco Jabber) ，並在步驟3中完成) 的使用者必須指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-124">The user who creates the Cisco Jabber on PostgreSQL connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="0cbc1-125">在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-125">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0cbc1-126">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-126">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="0cbc1-127">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="0cbc1-128">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="0cbc1-129">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-129">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a><span data-ttu-id="0cbc1-130">步驟1：設定 PostgreSQL connector 上的 Cisco Jabber) </span><span class="sxs-lookup"><span data-stu-id="0cbc1-130">Step 1: Set up the Cisco Jabber on PostgreSQL connector</span></span>

<span data-ttu-id="0cbc1-131">第一步是存取「Microsoft 365 規範中心」中的 [**資料連線器**] 頁面，並建立 jabber) 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-131">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jabber data.</span></span>

1. <span data-ttu-id="0cbc1-132">移至 <https://compliance.microsoft.com> ，然後按一下 &gt; **PostgreSQL 上的**[資料連線器 Cisco jabber) ]。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-132">Go to <https://compliance.microsoft.com> and then click **Data connectors** &gt; **Cisco Jabber on PostgreSQL**.</span></span>

2. <span data-ttu-id="0cbc1-133">在 [PostgreSQL 產品描述] 頁面上的 [ **Cisco jabber)** ] 上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-133">On the **Cisco Jabber on PostgreSQL** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="0cbc1-134">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-134">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="0cbc1-135">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-135">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="0cbc1-136">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-136">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a><span data-ttu-id="0cbc1-137">步驟2：在 Veritas Merge1 網站上的 PostgreSQL 上設定 Cisco Jabber) </span><span class="sxs-lookup"><span data-stu-id="0cbc1-137">Step 2: Configure the Cisco Jabber on PostgreSQL on the Veritas Merge1 site</span></span>

<span data-ttu-id="0cbc1-138">第二個步驟是在 Veritas Merge1 網站上的 PostgreSQL 連接器上設定 Cisco Jabber) 。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-138">The second step is to configure the Cisco Jabber on PostgreSQL connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="0cbc1-139">如需如何在 PostgreSQL 連接器上設定 Cisco Jabber) 的相關資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-139">For information about how to configure the Cisco Jabber on PostgreSQL connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf).</span></span>

<span data-ttu-id="0cbc1-140">按一下 **[儲存] & 完成** 之後，就會顯示「Microsoft 365 規範中心」的 [連接器] 中的 [**使用者對應**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-140">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="0cbc1-141">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="0cbc1-141">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="0cbc1-142">若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0cbc1-142">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="0cbc1-143">在 [ **PostgreSQL 使用者 Microsoft 365 使用者**] 頁面上的 [對應 Cisco jabber) ] 中，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-143">On the **Map Cisco Jabber on PostgreSQL users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="0cbc1-144">PostgreSQL 專案上的 Cisco Jabber) 包含一個名為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-144">The Cisco Jabber on PostgreSQL items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="0cbc1-145">如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-145">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="0cbc1-146">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-146">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a><span data-ttu-id="0cbc1-147">步驟4：在 PostgreSQL 連接器上監視 Cisco Jabber) </span><span class="sxs-lookup"><span data-stu-id="0cbc1-147">Step 4: Monitor the Cisco Jabber on PostgreSQL connector</span></span>

<span data-ttu-id="0cbc1-148">在 PostgreSQL 連接器上建立 Cisco jabber) 後，您可以在 [Microsoft 365 規範中心] 中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-148">After you create the Cisco Jabber on PostgreSQL connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="0cbc1-149">移至 <https://compliance.microsoft.com/> 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-149">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="0cbc1-150">按一下 [ **連接器** ] 索引標籤，然後選取 **PostgreSQL 連接器上的 Cisco jabber)** ，以顯示飛入頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-150">Click the **Connectors** tab and then select the **Cisco Jabber on PostgreSQL** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="0cbc1-151">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-151">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="0cbc1-152">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-152">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0cbc1-153">已知問題</span><span class="sxs-lookup"><span data-stu-id="0cbc1-153">Known issues</span></span>

- <span data-ttu-id="0cbc1-154">此時，我們不支援匯入超過 10 MB 的附件或專案，但較大專案的支援將于之後提供。</span><span class="sxs-lookup"><span data-stu-id="0cbc1-154">At this time, we don't support importing attachments or items larger than 10 MB but support for larger items will be available at a later date.</span></span>
