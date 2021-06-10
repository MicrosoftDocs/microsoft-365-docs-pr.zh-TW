---
title: 設定在 Microsoft 365 中封存 Reuters Eikon 資料的連接器
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
description: 系統管理員可以從 Microsoft 365 中的 Veritas 設定要匯入及封存 Reuters Eikon 資料的連接器。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: f3e0c9d542f54a46703b4acd0c1f154d3ab84cb8
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164095"
---
# <a name="set-up-a-connector-to-archive-reuters-eikon-data"></a><span data-ttu-id="e623a-105">設定連接器以封存 Reuters Eikon 資料</span><span class="sxs-lookup"><span data-stu-id="e623a-105">Set up a connector to archive Reuters Eikon data</span></span>

<span data-ttu-id="e623a-106">在 Microsoft 365 規範中心使用 Veritas connector，將 Reuters Eikon 平臺的資料匯入和封存至您 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="e623a-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Reuters Eikon platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="e623a-107">Veritas 會提供一個[Reuters Eikon](https://globanet.com/eikon/)連接器，設定為定期從協力廠商資料來源捕獲專案 () ，並將這些專案匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e623a-107">Veritas provides a [Reuters Eikon](https://globanet.com/eikon/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="e623a-108">連接器會將使用者的 Reuters Eikon 帳戶的人員對個人訊息、群組聊天、附件及免責聲明等內容轉換成電子郵件訊息格式，然後再將這些專案匯入 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="e623a-108">The connector converts the content such as person-to-person messages, group chats, attachments, and disclaimers from a user's Reuters Eikon account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="e623a-109">在將 Reuters Eikon 資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則及保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="e623a-109">After Reuters Eikon data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="e623a-110">使用 Reuters Eikon connector 在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="e623a-110">Using a Reuters Eikon connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-eikon-data"></a><span data-ttu-id="e623a-111">封存 Reuters Eikon 資料的概覽</span><span class="sxs-lookup"><span data-stu-id="e623a-111">Overview of archiving Reuters Eikon data</span></span>

<span data-ttu-id="e623a-112">下列概要說明如何使用連接器封存 Microsoft 365 中的 Reuters Eikon 資料。</span><span class="sxs-lookup"><span data-stu-id="e623a-112">The following overview explains the process of using a connector to archive Reuters Eikon data in Microsoft 365.</span></span>

![Reuters Eikon 資料的封存工作流程](../media/ReutersEikonConnectorWorkflow.png)

1. <span data-ttu-id="e623a-114">您的組織與 Reuters Eikon 搭配使用，以設定及設定 Reuters Eikon 網站。</span><span class="sxs-lookup"><span data-stu-id="e623a-114">Your organization works with Reuters Eikon to set up and configure a Reuters Eikon site.</span></span>

2. <span data-ttu-id="e623a-115">每24小時一次，Reuters Eikon 專案會複製到 Veritas Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="e623a-115">Once every 24 hours, Reuters Eikon items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="e623a-116">連接器也會將 Reuters Eikon 專案轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="e623a-116">The connector also converts Reuters Eikon items to an email message format.</span></span>

3. <span data-ttu-id="e623a-117">您在 Microsoft 365 合規性中心建立的 Reuters Eikon 連接器每天會連線至 Veritas Merge1 網站，並將內容傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="e623a-117">The Reuters Eikon connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="e623a-118">連接器會使用自動使用者對應的 *電子郵件* 屬性值，將專案匯入至特定使用者的信箱，如 [步驟 3](#step-3-map-users-and-complete-the-connector-setup)所述。</span><span class="sxs-lookup"><span data-stu-id="e623a-118">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="e623a-119">在使用者信箱中建立名為 **Reuters Eikon** 之 [收件匣] 資料夾中的子資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="e623a-119">A subfolder in the Inbox folder named **Reuters Eikon** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="e623a-120">連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。</span><span class="sxs-lookup"><span data-stu-id="e623a-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="e623a-121">每個 Reuters Eikon 專案都包含此屬性，它會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e623a-121">Every Reuters Eikon item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e623a-122">開始之前</span><span class="sxs-lookup"><span data-stu-id="e623a-122">Before you begin</span></span>

- <span data-ttu-id="e623a-123">建立 Microsoft 連接器的 Veritas Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="e623a-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="e623a-124">若要建立帳戶，請與 [Veritas 客戶支援](https://globanet.com/ms-connectors-contact)聯繫。</span><span class="sxs-lookup"><span data-stu-id="e623a-124">To create an account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="e623a-125">當您在步驟1中建立連接器時，您會登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="e623a-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="e623a-126">在步驟1中建立 Reuters Eikon 連接器的使用者 (，並在步驟 3) 中完成，必須指派 Exchange Online 中的「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="e623a-126">The user who creates the Reuters Eikon connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="e623a-127">在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="e623a-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e623a-128">根據預設，此角色不會指派給 Exchange Online 中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="e623a-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="e623a-129">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="e623a-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="e623a-130">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="e623a-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="e623a-131">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="e623a-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-reuters-eikon-connector"></a><span data-ttu-id="e623a-132">步驟1：設定 Reuters Eikon connector</span><span class="sxs-lookup"><span data-stu-id="e623a-132">Step 1: Set up the Reuters Eikon connector</span></span>

<span data-ttu-id="e623a-133">第一步是存取「Microsoft 365 規範中心」中的 [**資料連線器**] 頁面，並建立 Reuters Eikon 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="e623a-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Reuters Eikon data.</span></span>

1. <span data-ttu-id="e623a-134">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **Reuters] Eikon**。</span><span class="sxs-lookup"><span data-stu-id="e623a-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Eikon**.</span></span>

2. <span data-ttu-id="e623a-135">在 [ **Reuters Eikon** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="e623a-135">On the **Reuters Eikon** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="e623a-136">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="e623a-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="e623a-137">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e623a-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="e623a-138">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="e623a-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-eikon-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="e623a-139">步驟2：設定 Veritas Merge1 site 上的 Reuters Eikon connector</span><span class="sxs-lookup"><span data-stu-id="e623a-139">Step 2: Configure the Reuters Eikon connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="e623a-140">第二個步驟是設定 Merge1 網站上的 Reuters Eikon 連接器。</span><span class="sxs-lookup"><span data-stu-id="e623a-140">The second step is to configure the Reuters Eikon connector on the Merge1 site.</span></span> <span data-ttu-id="e623a-141">如需如何在 Veritas Merge1 網站上設定 Reuters Eikon connector 的相關資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="e623a-141">For information about how to configure the Reuters Eikon connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="e623a-142">按一下 **[儲存] & 完成** 之後，就會顯示「Microsoft 365 規範中心」的 [連接器] 中的 [**使用者對應**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e623a-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="e623a-143">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="e623a-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="e623a-144">若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e623a-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="e623a-145">在 [將 **外部使用者對應至 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]。</span><span class="sxs-lookup"><span data-stu-id="e623a-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="e623a-146">Reuters Eikon 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e623a-146">The Reuters Eikon items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="e623a-147">如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="e623a-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="e623a-148">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="e623a-148">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-eikon-connector"></a><span data-ttu-id="e623a-149">步驟4：監視 Reuters Eikon connector</span><span class="sxs-lookup"><span data-stu-id="e623a-149">Step 4: Monitor the Reuters Eikon connector</span></span>

<span data-ttu-id="e623a-150">在您建立 Reuters Eikon 連接器之後，您可以在 [Microsoft 365 規範中心] 中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="e623a-150">After you create the Reuters Eikon connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="e623a-151">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="e623a-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="e623a-152">按一下 [ **連接器** ] 索引標籤，然後選取 [ **Reuters Eikon** 連接器] 以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="e623a-152">Click the **Connectors** tab and then select the **Reuters Eikon** connector to display the flyout page.</span></span> <span data-ttu-id="e623a-153">此頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="e623a-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="e623a-154">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="e623a-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="e623a-155">此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e623a-155">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e623a-156">已知問題</span><span class="sxs-lookup"><span data-stu-id="e623a-156">Known issues</span></span>

- <span data-ttu-id="e623a-157">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="e623a-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="e623a-158">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="e623a-158">Support for larger items will be available at a later date.</span></span>