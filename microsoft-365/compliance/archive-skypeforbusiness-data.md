---
title: 設定在 Microsoft 365 中封存商務用 Skype 資料的連接器
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
description: 瞭解如何在 Microsoft 365 合規性中心中設定和使用連接器，以匯入商務用 Skype 中的資料並將其封存至 Microsoft 365。
ms.openlocfilehash: 4a66ee19530860bd482168297a8c935153442fee
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339451"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data"></a><span data-ttu-id="8929a-103">設定連接器以封存商務用 Skype 資料</span><span class="sxs-lookup"><span data-stu-id="8929a-103">Set up a connector to archive Skype for Business data</span></span>

<span data-ttu-id="8929a-104">使用 Microsoft 365 合規性中心中的 Veritas 連接器，將商務用 Skype 平臺的資料匯入至 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="8929a-104">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Skype for Business platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="8929a-105">Veritas 提供一種[商務用 Skype](https://www.veritas.com/en/au/insights/merge1/skype-for-business)連接器，可設定為定期從協力廠商資料來源捕獲專案 () 並將這些專案匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8929a-105">Veritas provides a [Skype for Business](https://www.veritas.com/en/au/insights/merge1/skype-for-business) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="8929a-106">連接器會將使用者、持續交談及會議訊息之間的內容，從商務用 Skype 轉換成電子郵件訊息格式，然後再將這些專案匯入 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="8929a-106">The connector converts the content such as messages between users, persistent chats, and conference messages from Skype for Business to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="8929a-107">商務用 Skype 資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則及保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8929a-107">After Skype for Business data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="8929a-108">使用商務用 Skype 連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="8929a-108">Using a Skype for Business connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-skype-for-business-data"></a><span data-ttu-id="8929a-109">封存商務用 Skype 資料的概覽</span><span class="sxs-lookup"><span data-stu-id="8929a-109">Overview of archiving Skype for Business data</span></span>

<span data-ttu-id="8929a-110">下列概要說明使用連接器封存 Microsoft 365 中商務用 Skype 資料的程式。</span><span class="sxs-lookup"><span data-stu-id="8929a-110">The following overview explains the process of using a connector to archive the Skype for Business data in Microsoft 365.</span></span>

![商務用 Skype 資料的封存工作流程](../media/SkypeforBusinessConnectorWorkflow.png)

1. <span data-ttu-id="8929a-112">您的組織與商務用 Skype 搭配設定及設定商務用 Skype 網站。</span><span class="sxs-lookup"><span data-stu-id="8929a-112">Your organization works with Skype for Business to set up and configure a Skype for Business site.</span></span>

2. <span data-ttu-id="8929a-113">每24小時一次，商務用 Skype 的專案會複製到 Veritas Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="8929a-113">Once every 24 hours, Skype for Business items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="8929a-114">連接線也會將商務用 Skype 專案轉換成電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="8929a-114">The connector also converts Skype for Business items to an email message format.</span></span>

3. <span data-ttu-id="8929a-115">您在 Microsoft 365 合規性中心中建立的商務用 Skype 連接器會每天連線到 Veritas Merge1 網站，並將商務用 Skype 內容傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="8929a-115">The Skype for Business connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the Skype for Business content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="8929a-116">連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述之自動使用者對應的 *電子郵件* 屬性值，將轉換後的專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="8929a-116">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="8929a-117">在使用者信箱中建立名為 **商務用 Skype** [收件匣] 資料夾中的子資料夾，並將專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="8929a-117">A subfolder in the Inbox folder named **Skype for Business** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="8929a-118">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="8929a-118">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="8929a-119">每個商務用 Skype 專案都包含此屬性，其會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8929a-119">Every Skype for Business item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="8929a-120">在您設定連接器之前</span><span class="sxs-lookup"><span data-stu-id="8929a-120">Before you set up a connector</span></span>

- <span data-ttu-id="8929a-121">建立 Microsoft 連接器的 Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="8929a-121">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="8929a-122">若要這麼做，請與 [Veritas 客戶支援](https://www.veritas.com/form/requestacall/ms-connectors-contact.html)聯繫。</span><span class="sxs-lookup"><span data-stu-id="8929a-122">To do this, contact [Veritas Customer Support](https://www.veritas.com/form/requestacall/ms-connectors-contact.html).</span></span> <span data-ttu-id="8929a-123">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="8929a-123">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="8929a-124">在步驟 1 (中建立商務用 Skype 連接器，並在步驟3中完成) 的使用者必須指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="8929a-124">The user who creates the Skype for Business connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="8929a-125">在 Microsoft 365 合規性中心中的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="8929a-125">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8929a-126">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="8929a-126">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="8929a-127">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="8929a-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="8929a-128">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="8929a-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="8929a-129">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="8929a-129">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-skype-for-business-connector"></a><span data-ttu-id="8929a-130">步驟1：設定商務用 Skype 連接器</span><span class="sxs-lookup"><span data-stu-id="8929a-130">Step 1: Set up the Skype for Business connector</span></span>

<span data-ttu-id="8929a-131">第一步是存取 [Microsoft 365 合規性中心中的 **資料連線器**] 頁面，並建立商務用 Skype 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="8929a-131">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Skype for Business data.</span></span>

1. <span data-ttu-id="8929a-132">移至 <https://compliance.microsoft.com> 並按一下 [**資料連線器**]  >  **商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="8929a-132">Go to <https://compliance.microsoft.com> and click **Data connectors** > **Skype for Business**.</span></span>

2. <span data-ttu-id="8929a-133">在 [**商務用 Skype** 的產品描述] 頁面上，按一下 [**新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="8929a-133">On the **Skype for Business** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="8929a-134">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="8929a-134">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="8929a-135">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8929a-135">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="8929a-136">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="8929a-136">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a><span data-ttu-id="8929a-137">步驟2：設定 Veritas Merge1 網站上的商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="8929a-137">Step 2: Configure the Skype for Business on the Veritas Merge1 site</span></span>

<span data-ttu-id="8929a-138">第二個步驟是設定 Veritas Merge1 網站上的商務用 Skype 連接器。</span><span class="sxs-lookup"><span data-stu-id="8929a-138">The second step is to configure the Skype for Business connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="8929a-139">如需如何設定商務用 Skype 連接器的詳細資訊，請參閱[Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="8929a-139">For information about how to configure the Skype for Business connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf).</span></span>

<span data-ttu-id="8929a-140">按一下 **[儲存] & 完成** 之後，就會顯示 Microsoft 365 合規性中心中 [連接器] 嚮導中的 [**使用者對應**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="8929a-140">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="8929a-141">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="8929a-141">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="8929a-142">若要對應使用者並完成 Microsoft 365 合規性中心中的連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8929a-142">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="8929a-143">在 [**對應商務用 Skype 使用者 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]。</span><span class="sxs-lookup"><span data-stu-id="8929a-143">On the **Map Skype for Business users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="8929a-144">商務用 Skype 的專案包括稱為「*電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8929a-144">The Skype for Business items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="8929a-145">如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="8929a-145">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="8929a-146">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="8929a-146">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-skype-for-business-connector"></a><span data-ttu-id="8929a-147">步驟4：監視商務用 Skype 連接器</span><span class="sxs-lookup"><span data-stu-id="8929a-147">Step 4: Monitor the Skype for Business connector</span></span>

<span data-ttu-id="8929a-148">在您建立商務用 Skype 連接器之後，您可以在 Microsoft 365 合規性中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="8929a-148">After you create the Skype for Business connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="8929a-149">移至 <https://compliance.microsoft.com/> 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="8929a-149">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8929a-150">按一下 [**連接器**] 索引標籤，然後選取 **商務用 Skype** 連接器以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="8929a-150">Click the **Connectors** tab and then select the **Skype for Business** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="8929a-151">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="8929a-151">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="8929a-152">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="8929a-152">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8929a-153">已知問題</span><span class="sxs-lookup"><span data-stu-id="8929a-153">Known issues</span></span>

- <span data-ttu-id="8929a-154">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="8929a-154">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="8929a-155">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="8929a-155">Support for larger items will be available at a later date.</span></span>
