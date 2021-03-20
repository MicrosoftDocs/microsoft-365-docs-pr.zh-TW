---
title: 設定連接器以在 Microsoft 365 中封存 Jive 資料
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
description: 系統管理員可以設定連接器，以從 Microsoft 365 的 Globanet 匯入及封存 Jive 資料。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 0c533b8b5b241db8bd51b7a1d90717ff9543b393
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908615"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a><span data-ttu-id="a7ef5-104">設定連接器以封存 Jive 資料</span><span class="sxs-lookup"><span data-stu-id="a7ef5-104">Set up a connector to archive Jive data</span></span>

<span data-ttu-id="a7ef5-105">使用 Microsoft 365 規範中心內的 Globanet 連接器，將共同作業平臺的資料匯入和封存至您的 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the collaboration platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="a7ef5-106">Globanet 提供一個 [Jive](https://globanet.com/jive/) 連接器，可設定為定期從協力廠商資料來源捕獲專案 () 然後將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-106">Globanet provides a [Jive](https://globanet.com/jive/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="a7ef5-107">連接器會將電子郵件、聊天和附件等內容，從使用者的 Jive 帳戶轉換為電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-107">The connector converts content such as email messages, chats, and attachments from a user's Jive account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="a7ef5-108">在使用者信箱中儲存 Jive 資料後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-108">After Jive data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="a7ef5-109">在 Microsoft 365 中使用 Jive 連接器匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-109">Using a Jive connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-jive-data"></a><span data-ttu-id="a7ef5-110">封存 Jive 資料的概覽</span><span class="sxs-lookup"><span data-stu-id="a7ef5-110">Overview of archiving Jive data</span></span>

<span data-ttu-id="a7ef5-111">下列概要說明如何使用連接器封存 Microsoft 365 中的 Jive 資料。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-111">The following overview explains the process of using a connector to archive the Jive data in Microsoft 365.</span></span>

![用於 Jive 資料的封存工作流程](../media/JiveConnectorWorkflow.png)

1. <span data-ttu-id="a7ef5-113">您的組織與 Jive 搭配使用，以安裝及設定 Jive 網站。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-113">Your organization works with Jive to set up and configure a Jive site.</span></span>

2. <span data-ttu-id="a7ef5-114">每24小時一次，將 Jive 中的專案複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-114">Once every 24 hours, items from Jive are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="a7ef5-115">連接器也會將 Jive 專案的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-115">The connector also converts the content of Jive items to an email message format.</span></span>

3. <span data-ttu-id="a7ef5-116">您在 Microsoft 365 規範中心建立的 Jive 連接器每天都會連線到 Globanet Merge1 網站，並將內容傳送至 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-116">The Jive connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="a7ef5-117">連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述的自動使用者對應的 *電子郵件* 屬性值，將已轉換的專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-117">The connector imports the converted items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="a7ef5-118">在使用者信箱中建立名為 **Jive** 之 [收件匣] 資料夾中的新子資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-118">A new subfolder in the Inbox folder named **Jive** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="a7ef5-119">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="a7ef5-120">每個 Jive 專案都包含此屬性，其會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-120">Every Jive item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a7ef5-121">開始之前</span><span class="sxs-lookup"><span data-stu-id="a7ef5-121">Before you begin</span></span>

- <span data-ttu-id="a7ef5-122">為 Microsoft connector 建立 Globanet Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="a7ef5-123">若要建立此帳戶，請與 [globanet 客戶支援](https://globanet.com/ms-connectors-contact/)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-123">To create this account, contact [globanet customer support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="a7ef5-124">當您在步驟1中建立連接器時，您會登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="a7ef5-125">在步驟1中建立 Jive 連接器的使用者 (，並在步驟 3) 中完成，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-125">The user who creates the Jive connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a7ef5-126">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a7ef5-127">根據預設，此角色不會指派給 Exchange Online 中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="a7ef5-128">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a7ef5-129">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a7ef5-130">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-130">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-jive-connector"></a><span data-ttu-id="a7ef5-131">步驟1：設定 Jive 連接器</span><span class="sxs-lookup"><span data-stu-id="a7ef5-131">Step 1: Set up the Jive connector</span></span>

<span data-ttu-id="a7ef5-132">第一步是存取 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面，並建立用於 Jive 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jive data.</span></span>

1. <span data-ttu-id="a7ef5-133">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **Jive**]。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Jive**.</span></span>

2. <span data-ttu-id="a7ef5-134">在 [ **Jive** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-134">On the **Jive** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="a7ef5-135">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="a7ef5-136">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="a7ef5-137">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-jive-connector"></a><span data-ttu-id="a7ef5-138">步驟2：設定 Jive 連接器</span><span class="sxs-lookup"><span data-stu-id="a7ef5-138">Step 2: Configure the Jive connector</span></span>

<span data-ttu-id="a7ef5-139">第二個步驟是設定 Merge1 網站上的 Jive 連接器。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-139">The second step is to configure the Jive connector on the Merge1 site.</span></span> <span data-ttu-id="a7ef5-140">如需如何設定 Jive 連接器的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-140">For information about how to configure the Jive connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf).</span></span>

<span data-ttu-id="a7ef5-141">按一下 **[儲存] & 完成** 之後，就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="a7ef5-142">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="a7ef5-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="a7ef5-143">若要對應使用者，並完成 Microsoft 365 規範中心內的連接器設定，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a7ef5-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="a7ef5-144">在 [將 **Jive 使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用 [自動使用者對應]。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-144">On the **Map Jive users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="a7ef5-145">Jive 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-145">The Jive items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="a7ef5-146">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="a7ef5-147">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-147">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-jive-connector"></a><span data-ttu-id="a7ef5-148">步驟4：監視 Jive 連接器</span><span class="sxs-lookup"><span data-stu-id="a7ef5-148">Step 4: Monitor the Jive connector</span></span>

<span data-ttu-id="a7ef5-149">在您建立 Jive 連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-149">After you create the Jive connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="a7ef5-150">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-150">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a7ef5-151">按一下 [ **連接器** ] 索引標籤，然後選取 [ **Jive** 連接器] 以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-151">Click the **Connectors** tab and then select the **Jive** connector to display the flyout page.</span></span> <span data-ttu-id="a7ef5-152">此頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="a7ef5-153">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="a7ef5-154">此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-154">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a7ef5-155">已知問題</span><span class="sxs-lookup"><span data-stu-id="a7ef5-155">Known issues</span></span>

- <span data-ttu-id="a7ef5-156">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="a7ef5-157">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="a7ef5-157">Support for larger items will be available at a later date.</span></span>