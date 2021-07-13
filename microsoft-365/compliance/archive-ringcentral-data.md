---
title: 設定連接器以封存 Microsoft 365 中的 RingCentral 資料
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
description: 系統管理員可以設定連接器，將 RingCentral 資料從 Veritas 匯入至 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、eDiscovery 及保留原則）來管理協力廠商資料。
ms.openlocfilehash: 4fc0b61d5bc47a573da3ef8dd12654316e77d073
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408933"
---
# <a name="set-up-a-connector-to-archive-ringcentral-data-preview"></a><span data-ttu-id="fbf22-105">設定連接器以封存 RingCentral 資料 (預覽) </span><span class="sxs-lookup"><span data-stu-id="fbf22-105">Set up a connector to archive RingCentral data (preview)</span></span>

<span data-ttu-id="fbf22-106">使用 Microsoft 365 合規性中心中的 Veritas 連接器，將 RingCentral 平臺的資料匯入並封存至您 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="fbf22-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the RingCentral platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="fbf22-107">Veritas 提供將 RingCentral 連接器設定為從協力廠商資料來源捕獲專案，並將這些專案匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="fbf22-107">Veritas provides the RingCentral connector that is configured to capture items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="fbf22-108">連接器會將聊天、附件、任務、記事及文章等內容，從 RingCentral 轉換為電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="fbf22-108">The connector converts content such as chats, attachments, tasks, notes, and posts from RingCentral to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="fbf22-109">將 RingCentral 資料儲存在使用者信箱之後，您就可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則及保留標籤。</span><span class="sxs-lookup"><span data-stu-id="fbf22-109">After RingCentral data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="fbf22-110">使用 RingCentral 連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="fbf22-110">Using a RingCentral connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ringcentral-data"></a><span data-ttu-id="fbf22-111">封存 RingCentral 資料一覽</span><span class="sxs-lookup"><span data-stu-id="fbf22-111">Overview of archiving RingCentral data</span></span>

<span data-ttu-id="fbf22-112">下列概要說明如何使用連接器封存 Microsoft 365 中的 RingCentral 資料。</span><span class="sxs-lookup"><span data-stu-id="fbf22-112">The following overview explains the process of using a connector to archive the RingCentral data in Microsoft 365.</span></span>

![RingCentral 資料的封存工作流程](../media/RingCentralConnectorWorkflow.png)

1. <span data-ttu-id="fbf22-114">您的組織與 RingCentral 搭配使用，以設定及設定 RingCentral 網站。</span><span class="sxs-lookup"><span data-stu-id="fbf22-114">Your organization works with RingCentral to set up and configure a RingCentral site.</span></span>

2. <span data-ttu-id="fbf22-115">每24小時一次，RingCentral 專案會複製到 Veritas Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="fbf22-115">Once every 24 hours, RingCentral items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="fbf22-116">連接器也會將 RingCentral 的專案轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="fbf22-116">The connector also converts RingCentral items to an email message format.</span></span>

3. <span data-ttu-id="fbf22-117">您在 Microsoft 365 合規性中心中建立的 RingCentral 連接器會每天連接至 Veritas Merge1 網站，並將 RingCentral 內容傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="fbf22-117">The RingCentral connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the RingCentral content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="fbf22-118">連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述之自動使用者對應的 *電子郵件* 屬性值，將轉換後的專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="fbf22-118">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="fbf22-119">在使用者信箱中建立名為 **RingCentral** 之 [收件匣] 資料夾中的子資料夾，並將專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="fbf22-119">A subfolder in the Inbox folder named **RingCentral** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="fbf22-120">連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。</span><span class="sxs-lookup"><span data-stu-id="fbf22-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="fbf22-121">每個 RingCentral 專案都包含此屬性，它會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="fbf22-121">Every RingCentral item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="fbf22-122">在您設定連接器之前</span><span class="sxs-lookup"><span data-stu-id="fbf22-122">Before you set up a connector</span></span>

- <span data-ttu-id="fbf22-123">建立 Microsoft 連接器的 Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="fbf22-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="fbf22-124">若要建立此帳戶，請與 [Veritas 客戶支援](https://www.veritas.com/form/requestacall/ms-connectors-contact)聯繫。</span><span class="sxs-lookup"><span data-stu-id="fbf22-124">To create this account, contact [Veritas Customer Support](https://www.veritas.com/form/requestacall/ms-connectors-contact).</span></span> <span data-ttu-id="fbf22-125">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="fbf22-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="fbf22-126">建立 RingCentral 應用程式以從您的 RingCentral 帳戶提取資料。</span><span class="sxs-lookup"><span data-stu-id="fbf22-126">Create a RingCentral application to fetch data from your RingCentral account.</span></span> <span data-ttu-id="fbf22-127">如需建立應用程式的逐步指示，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="fbf22-127">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).</span></span>

- <span data-ttu-id="fbf22-128">在步驟1中建立 RingCentral 連接器的使用者 (，並在步驟 3) 中完成，必須指派 Exchange Online 中的「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="fbf22-128">The user who creates the RingCentral connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fbf22-129">在 Microsoft 365 合規性中心中的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="fbf22-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fbf22-130">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="fbf22-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="fbf22-131">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="fbf22-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fbf22-132">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="fbf22-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fbf22-133">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="fbf22-133">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-ringcentral-connector"></a><span data-ttu-id="fbf22-134">步驟1：設定 RingCentral 連接器</span><span class="sxs-lookup"><span data-stu-id="fbf22-134">Step 1: Set up the RingCentral connector</span></span>

<span data-ttu-id="fbf22-135">第一步是存取 [Microsoft 365 合規性中心中的 **資料連線器**] 頁面，並建立 RingCentral 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="fbf22-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for RingCentral data.</span></span>

1. <span data-ttu-id="fbf22-136">移至 <https://compliance.microsoft.com> ，然後按一下 [**資料連線器**  >  **RingCentral**]。</span><span class="sxs-lookup"><span data-stu-id="fbf22-136">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **RingCentral**.</span></span>

2. <span data-ttu-id="fbf22-137">在 [ **RingCentral** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="fbf22-137">On the **RingCentral** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="fbf22-138">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="fbf22-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fbf22-139">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fbf22-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="fbf22-140">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="fbf22-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-ringcentral-on-the-veritas-merge1-site"></a><span data-ttu-id="fbf22-141">步驟2：設定 Veritas Merge1 site 上的 RingCentral</span><span class="sxs-lookup"><span data-stu-id="fbf22-141">Step 2: Configure the RingCentral on the Veritas Merge1 site</span></span>

<span data-ttu-id="fbf22-142">第二個步驟是在 Veritas Merge1 網站上設定 RingCentral 連接器。</span><span class="sxs-lookup"><span data-stu-id="fbf22-142">The second step is to configure the RingCentral connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="fbf22-143">如需如何設定 RingCentral 連接器的詳細資訊，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="fbf22-143">For information about how to configure the RingCentral connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).</span></span>

<span data-ttu-id="fbf22-144">按一下 **[儲存] & 完成之後，** 就會顯示 Microsoft 365 合規性中心中 [連接器] 嚮導中的 [**使用者對應**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="fbf22-144">After you click **Save & Finish,** the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="fbf22-145">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="fbf22-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="fbf22-146">若要對應使用者並完成 Microsoft 365 合規性中心中的連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fbf22-146">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="fbf22-147">在 [將 **RingCentral 使用者對應至 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]。</span><span class="sxs-lookup"><span data-stu-id="fbf22-147">On the **Map RingCentral users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="fbf22-148">RingCentral 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="fbf22-148">The RingCentral items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="fbf22-149">如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="fbf22-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="fbf22-150">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="fbf22-150">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-ringcentral-connector"></a><span data-ttu-id="fbf22-151">步驟4：監控 RingCentral 連接器</span><span class="sxs-lookup"><span data-stu-id="fbf22-151">Step 4: Monitor the RingCentral connector</span></span>

<span data-ttu-id="fbf22-152">在您建立 RingCentral 連接器之後，您可以在 Microsoft 365 合規性中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="fbf22-152">After you create the RingCentral connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="fbf22-153">移至 <https://compliance.microsoft.com/> 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="fbf22-153">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="fbf22-154">按一下 [ **連接器** ] 索引標籤，然後選取 **RingCentral** 連接器以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="fbf22-154">Click the **Connectors** tab and then select the **RingCentral** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="fbf22-155">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="fbf22-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="fbf22-156">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="fbf22-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fbf22-157">已知問題</span><span class="sxs-lookup"><span data-stu-id="fbf22-157">Known issues</span></span>

- <span data-ttu-id="fbf22-158">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="fbf22-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="fbf22-159">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="fbf22-159">Support for larger items will be available at a later date.</span></span>
