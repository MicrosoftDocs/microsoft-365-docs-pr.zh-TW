---
title: 設定在 Microsoft 365 中封存 ServiceNow 資料的連接器
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
description: 系統管理員可以設定連接器，將 ServiceNow 資料從 Globanet 匯入至 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: d9cc40e8d7660be96cefb8ec0d13e2b95bb8f31a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925105"
---
# <a name="set-up-a-connector-to-archive-servicenow-data"></a><span data-ttu-id="23770-105">設定連接器以封存 ServiceNow 資料</span><span class="sxs-lookup"><span data-stu-id="23770-105">Set up a connector to archive ServiceNow data</span></span>

<span data-ttu-id="23770-106">使用 Microsoft 365 規範中心內的 Globanet 連接器，將 ServiceNow 平臺的資料匯入至您的 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="23770-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the ServiceNow platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="23770-107">Globanet 提供的 [ServiceNow](https://globanet.com/servicenow/) 連接器會從協力廠商資料來源捕獲專案，並將這些專案匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="23770-107">Globanet provides a [ServiceNow](https://globanet.com/servicenow/) connector that captures items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="23770-108">連接器會將實況郵件、附件及 ServiceNow 文章等內容轉換成電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="23770-108">The connector converts the content such as live messages, attachments, and posts from ServiceNow to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="23770-109">ServiceNow 資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則及保留標籤。</span><span class="sxs-lookup"><span data-stu-id="23770-109">After ServiceNow data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies, and retention labels.</span></span> <span data-ttu-id="23770-110">在 Microsoft 365 中使用 ServiceNow 連接器匯入和封存資料，可協助您的組織符合政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="23770-110">Using a ServiceNow connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-servicenow-data"></a><span data-ttu-id="23770-111">封存 ServiceNow 資料的概覽</span><span class="sxs-lookup"><span data-stu-id="23770-111">Overview of archiving ServiceNow data</span></span>

<span data-ttu-id="23770-112">下列概要說明使用連接器封存 Microsoft 365 中 ServiceNow 資料的程式。</span><span class="sxs-lookup"><span data-stu-id="23770-112">The following overview explains the process of using a connector to archive the ServiceNow data in Microsoft 365.</span></span>

![ServiceNow 資料的封存工作流程](../media/ServiceNowConnectorWorkflow.png)

1. <span data-ttu-id="23770-114">您的組織與 ServiceNow 搭配設定及設定 ServiceNow 網站。</span><span class="sxs-lookup"><span data-stu-id="23770-114">Your organization works with ServiceNow to set up and configure a ServiceNow site.</span></span>

2. <span data-ttu-id="23770-115">每24小時一次，ServiceNow 的專案會複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="23770-115">Once every 24 hours, ServiceNow items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="23770-116">連接線也會將 ServiceNow 專案轉換成電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="23770-116">The connector also converts ServiceNow items to an email message format.</span></span>

3. <span data-ttu-id="23770-117">您在 Microsoft 365 合規性中心建立的 ServiceNow 連接器每天都會連線到 Globanet Merge1 網站，並將 ServiceNow 內容傳送至 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="23770-117">The ServiceNow connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the ServiceNow content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="23770-118">連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述之自動使用者對應的 *電子郵件* 屬性值，將轉換後的專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="23770-118">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="23770-119">在使用者信箱中建立名為 **ServiceNow** [收件匣] 資料夾中的子資料夾，並將專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="23770-119">A subfolder in the Inbox folder named **ServiceNow** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="23770-120">連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。</span><span class="sxs-lookup"><span data-stu-id="23770-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="23770-121">每個 ServiceNow 專案都包含此屬性，其會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="23770-121">Every ServiceNow item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="23770-122">開始之前</span><span class="sxs-lookup"><span data-stu-id="23770-122">Before you begin</span></span>

- <span data-ttu-id="23770-123">建立 Microsoft 連接器的 Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="23770-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="23770-124">若要建立帳戶，請與 [Globanet 客戶支援](https://globanet.com/contact-us/)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="23770-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="23770-125">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="23770-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="23770-126">建立 ServiceNow 的應用程式以從您的 ServiceNow 帳戶取得資料。</span><span class="sxs-lookup"><span data-stu-id="23770-126">Create a ServiceNow application to fetch data from your ServiceNow account.</span></span> <span data-ttu-id="23770-127">如需建立應用程式的逐步指示，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="23770-127">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="23770-128">在步驟 1 (中建立 ServiceNow 連接器，並在步驟3中完成) 的使用者必須指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="23770-128">The user who creates the ServiceNow connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="23770-129">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="23770-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="23770-130">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="23770-130">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="23770-131">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="23770-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="23770-132">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="23770-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="23770-133">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="23770-133">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-servicenow-connector"></a><span data-ttu-id="23770-134">步驟1：設定 ServiceNow 連接器</span><span class="sxs-lookup"><span data-stu-id="23770-134">Step 1: Set up the ServiceNow connector</span></span>

<span data-ttu-id="23770-135">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** 頁面，並為 ServiceNow 資料建立連接器。</span><span class="sxs-lookup"><span data-stu-id="23770-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for ServiceNow data.</span></span>

1. <span data-ttu-id="23770-136">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**]  >  **ServiceNow**。</span><span class="sxs-lookup"><span data-stu-id="23770-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **ServiceNow**.</span></span>

2. <span data-ttu-id="23770-137">在 [ **ServiceNow** 的產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="23770-137">On the **ServiceNow** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="23770-138">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="23770-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="23770-139">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="23770-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="23770-140">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="23770-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-servicenow-on-the-globanet-merge1-site"></a><span data-ttu-id="23770-141">步驟2：設定 Globanet Merge1 網站上的 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="23770-141">Step 2: Configure the ServiceNow on the Globanet Merge1 site</span></span>

<span data-ttu-id="23770-142">第二個步驟是設定 Globanet Merge1 網站上的 ServiceNow 連接器。</span><span class="sxs-lookup"><span data-stu-id="23770-142">The second step is to configure the ServiceNow connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="23770-143">如需如何設定 ServiceNow 連接器的詳細資訊，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="23770-143">For information about how to configure the ServiceNow connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="23770-144">按一下 **[儲存] & 完成之後，** 就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="23770-144">After you click **Save & Finish,** the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="23770-145">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="23770-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="23770-146">若要對應使用者，並完成 Microsoft 365 規範中心內的連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="23770-146">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="23770-147">在 [將 **ServiceNow 使用者至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="23770-147">On the **Map ServiceNow users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="23770-148">ServiceNow 的專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="23770-148">The ServiceNow items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="23770-149">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="23770-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="23770-150">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="23770-150">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-servicenow-connector"></a><span data-ttu-id="23770-151">步驟4：監視 ServiceNow 連接器</span><span class="sxs-lookup"><span data-stu-id="23770-151">Step 4: Monitor the ServiceNow connector</span></span>

<span data-ttu-id="23770-152">在您建立 ServiceNow 連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="23770-152">After you create the ServiceNow connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="23770-153">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="23770-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="23770-154">按一下 [ **連接器** ] 索引標籤，然後選取 **ServiceNow** 連接器以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="23770-154">Click the **Connectors** tab and then select the **ServiceNow** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="23770-155">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="23770-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="23770-156">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="23770-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="23770-157">已知問題</span><span class="sxs-lookup"><span data-stu-id="23770-157">Known issues</span></span>

- <span data-ttu-id="23770-158">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="23770-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="23770-159">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="23770-159">Support for larger items will be available at a later date.</span></span>