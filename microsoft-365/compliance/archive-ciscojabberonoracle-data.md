---
title: '設定連接器以在 Microsoft 365 的 Oracle 資料上封存 Cisco Jabber) '
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
description: 瞭解如何在 Microsoft 365 規範中心內設定和使用連接器，以從 Oracle 到 Microsoft 365 中的 Cisco jabber) 匯入及封存資料。
ms.openlocfilehash: d8e1ba27c4277916614deaa042214ae592bceff2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842755"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data-preview"></a><span data-ttu-id="6c977-103">設定連接器以封存 Oracle 資料 (預覽中的 Cisco Jabber) ) </span><span class="sxs-lookup"><span data-stu-id="6c977-103">Set up a connector to archive Cisco Jabber on Oracle data (preview)</span></span>

<span data-ttu-id="6c977-104">在 Microsoft 365 規範中心使用 Veritas 連接器，將 Oracle 平臺上 Cisco jabber) 的資料匯入並封存至您 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="6c977-104">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber on Oracle platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="6c977-105">Veritas 會在[Oracle 連接器上提供 Cisco jabber) ](https://www.veritas.com/insights/merge1/jabber) ，以設定為定期捕獲協力廠商資料來源中的專案 () 並將這些專案匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6c977-105">Veritas provides a [Cisco Jabber on Oracle](https://www.veritas.com/insights/merge1/jabber) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="6c977-106">連接器會將 Oracle Jabber) 中的檔案和檔案作業、批註和共用內容等內容轉換成電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="6c977-106">The connector converts the content such as files and file operations, comments, and shared content from Cisco Jabber on Oracle to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="6c977-107">Oracle 資料上的 Cisco jabber) 儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則及保留標籤。</span><span class="sxs-lookup"><span data-stu-id="6c977-107">After Cisco Jabber on Oracle data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="6c977-108">使用 Oracle 連接器上的 Cisco jabber) ，在 Microsoft 365 中匯入及封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="6c977-108">Using a Cisco Jabber on Oracle connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a><span data-ttu-id="6c977-109">Oracle 資料上封存 Cisco Jabber) 的概覽</span><span class="sxs-lookup"><span data-stu-id="6c977-109">Overview of archiving Cisco Jabber on Oracle data</span></span>

<span data-ttu-id="6c977-110">下列概要說明如何使用連接器封存 Microsoft 365 中 Oracle 資料上的 Cisco Jabber) 。</span><span class="sxs-lookup"><span data-stu-id="6c977-110">The following overview explains the process of using a connector to archive the Cisco Jabber on Oracle data in Microsoft 365.</span></span>

![Oracle 資料上的 Cisco Jabber) 封存工作流程](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. <span data-ttu-id="6c977-112">您的組織可以搭配 Oracle 的 Cisco Jabber) ，在 Oracle 網站上設定和設定 Cisco Jabber) 。</span><span class="sxs-lookup"><span data-stu-id="6c977-112">Your organization works with Cisco Jabber on Oracle to set up and configure a Cisco Jabber on Oracle site.</span></span>

2. <span data-ttu-id="6c977-113">每隔24小時，Oracle 專案上的 Cisco Jabber) 都會複製到 Veritas Merge1 site。</span><span class="sxs-lookup"><span data-stu-id="6c977-113">Once every 24 hours, Cisco Jabber on Oracle items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="6c977-114">連接器也會將 Oracle 專案上的 Cisco Jabber) 轉換成電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="6c977-114">The connector also converts Cisco Jabber on Oracle items to an email message format.</span></span>

3. <span data-ttu-id="6c977-115">您在 Microsoft 365 規範中心建立的 Oracle 連接器上的 Cisco jabber) ，會每天連線到 Veritas Merge1 網站，並將 jabber) 內容傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="6c977-115">The Cisco Jabber on Oracle connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the Jabber content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="6c977-116">連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述之自動使用者對應的 *電子郵件* 屬性值，將轉換後的專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="6c977-116">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="6c977-117">在使用者信箱中建立名為 **Cisco jabber)** 的 [收件匣] 資料夾中的子資料夾，並將專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="6c977-117">A subfolder in the Inbox folder named **Cisco Jabber on Oracle** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="6c977-118">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6c977-118">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="6c977-119">每個 Jabber) 專案都包含此屬性，它會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6c977-119">Every Jabber item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6c977-120">開始之前</span><span class="sxs-lookup"><span data-stu-id="6c977-120">Before you begin</span></span>

- <span data-ttu-id="6c977-121">建立 Microsoft 連接器的 Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="6c977-121">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="6c977-122">若要這麼做，請與 [Veritas 客戶支援](https://www.veritas.com/content/support/en_US)聯繫。</span><span class="sxs-lookup"><span data-stu-id="6c977-122">To do this, contact [Veritas Customer Support](https://www.veritas.com/content/support/en_US).</span></span> <span data-ttu-id="6c977-123">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="6c977-123">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="6c977-124">在步驟 (1 中的 Oracle 連接器上建立 Cisco Jabber) 的使用者，在步驟3中建立 Cisco，) 必須指派給 Exchange Online 中的「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="6c977-124">The user who creates the Cisco Jabber on Oracle connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6c977-125">在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="6c977-125">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6c977-126">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="6c977-126">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="6c977-127">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="6c977-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6c977-128">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="6c977-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6c977-129">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="6c977-129">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a><span data-ttu-id="6c977-130">步驟1：設定 Oracle 連接器上的 Cisco Jabber) </span><span class="sxs-lookup"><span data-stu-id="6c977-130">Step 1: Set up the Cisco Jabber on Oracle connector</span></span>

<span data-ttu-id="6c977-131">第一步是存取「Microsoft 365 規範中心」中的 [**資料連線器**] 頁面，並建立 jabber) 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="6c977-131">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jabber data.</span></span>

1. <span data-ttu-id="6c977-132">移至 <https://compliance.microsoft.com> ，然後按一下 Oracle 上的 [**資料連線器**  >  **Cisco jabber)**]。</span><span class="sxs-lookup"><span data-stu-id="6c977-132">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Cisco Jabber on Oracle**.</span></span>

2. <span data-ttu-id="6c977-133">在 [Oracle 產品描述] 頁面上的 **Cisco jabber)** 中，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="6c977-133">On the **Cisco Jabber on Oracle** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="6c977-134">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="6c977-134">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="6c977-135">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6c977-135">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="6c977-136">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="6c977-136">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a><span data-ttu-id="6c977-137">步驟2：在 Veritas Merge1 網站上的 Oracle 上設定 Cisco Jabber) </span><span class="sxs-lookup"><span data-stu-id="6c977-137">Step 2: Configure the Cisco Jabber on Oracle on the Veritas Merge1 site</span></span>

<span data-ttu-id="6c977-138">第二個步驟是在 Veritas Merge1 網站上的 Oracle 連接器上設定 Cisco Jabber) 。</span><span class="sxs-lookup"><span data-stu-id="6c977-138">The second step is to configure the Cisco Jabber on Oracle connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="6c977-139">如需如何設定 Oracle 連接器上 Cisco Jabber) 的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="6c977-139">For information about how to configure the Cisco Jabber on Oracle connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf).</span></span>

<span data-ttu-id="6c977-140">按一下 **[儲存] & 完成** 之後，就會顯示「Microsoft 365 規範中心」的 [連接器] 中的 [**使用者對應**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="6c977-140">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="6c977-141">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="6c977-141">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="6c977-142">若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6c977-142">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="6c977-143">在 [將 **Oracle 使用者上的 Cisco jabber) 對應至 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]。</span><span class="sxs-lookup"><span data-stu-id="6c977-143">On the **Map Cisco Jabber on Oracle users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="6c977-144">Oracle 專案上的 Cisco Jabber) 包含一個名為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6c977-144">The Cisco Jabber on Oracle items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="6c977-145">如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="6c977-145">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="6c977-146">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="6c977-146">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a><span data-ttu-id="6c977-147">步驟4：監視 Oracle 連接器上的 Cisco Jabber) </span><span class="sxs-lookup"><span data-stu-id="6c977-147">Step 4: Monitor the Cisco Jabber on Oracle connector</span></span>

<span data-ttu-id="6c977-148">在 Oracle 連接器上建立 Cisco jabber) 之後，您可以在 [Microsoft 365 規範中心] 中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="6c977-148">After you create the Cisco Jabber on Oracle connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="6c977-149">移至 <https://compliance.microsoft.com/> 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="6c977-149">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="6c977-150">按一下 [ **連接器** ] 索引標籤，然後選取 [Oracle 連接器] **上的 Cisco jabber)** ，以顯示飛入頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="6c977-150">Click the **Connectors** tab and then select the **Cisco Jabber on Oracle** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="6c977-151">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="6c977-151">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="6c977-152">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="6c977-152">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6c977-153">已知問題</span><span class="sxs-lookup"><span data-stu-id="6c977-153">Known issues</span></span>

- <span data-ttu-id="6c977-154">此時，我們不支援匯入超過 10 MB 的附件或專案，但較大專案的支援將于之後提供。</span><span class="sxs-lookup"><span data-stu-id="6c977-154">At this time, we don't support importing attachments or items larger than 10 MB but support for larger items will be available at a later date.</span></span>
