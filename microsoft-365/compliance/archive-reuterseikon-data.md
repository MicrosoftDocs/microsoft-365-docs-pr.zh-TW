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
description: 系統管理員可以設定連接器，以從 Microsoft 365 的 Globanet 匯入及封存 Reuters Eikon 資料。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 3d890baddb0bf10e5659c72d06868f1ce97b3e21
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408733"
---
# <a name="set-up-a-connector-to-archive-reuters-eikon-data"></a><span data-ttu-id="1d5c9-104">設定連接器以封存 Reuters Eikon 資料</span><span class="sxs-lookup"><span data-stu-id="1d5c9-104">Set up a connector to archive Reuters Eikon data</span></span>

<span data-ttu-id="1d5c9-105">使用 Microsoft 365 規範中心內的 Globanet 連接器，將 Reuters Eikon 平臺的資料匯入和封存至您的 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters Eikon platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="1d5c9-106">Globanet 提供 [Reuters Eikon](https://globanet.com/eikon/) 連接器，該連接器設定為定期從協力廠商資料來源捕獲專案 () 並將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-106">Globanet provides a [Reuters Eikon](https://globanet.com/eikon/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="1d5c9-107">連接器會將使用者的 Reuters Eikon 帳戶的人員對個人訊息、群組聊天、附件和免責聲明等內容轉換成電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-107">The connector converts the content such as person-to-person messages, group chats, attachments, and disclaimers from a user's Reuters Eikon account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="1d5c9-108">Reuters Eikon 資料儲存在使用者信箱之後，您就可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-108">After Reuters Eikon data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="1d5c9-109">在 Microsoft 365 中使用 Reuters Eikon connector 匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-109">Using a Reuters Eikon connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-eikon-data"></a><span data-ttu-id="1d5c9-110">封存 Reuters Eikon 資料的概覽</span><span class="sxs-lookup"><span data-stu-id="1d5c9-110">Overview of archiving Reuters Eikon data</span></span>

<span data-ttu-id="1d5c9-111">下列概要說明使用連接器封存 Microsoft 365 中 Reuters Eikon 資料的程式。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-111">The following overview explains the process of using a connector to archive Reuters Eikon data in Microsoft 365.</span></span>

![Reuters Eikon 資料的封存工作流程](../media/ReutersEikonConnectorWorkflow.png)

1. <span data-ttu-id="1d5c9-113">您的組織與 Reuters Eikon 搭配使用，以設定及設定 Reuters Eikon 網站。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-113">Your organization works with Reuters Eikon to set up and configure a Reuters Eikon site.</span></span>

2. <span data-ttu-id="1d5c9-114">每24小時一次，Reuters Eikon 專案會複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-114">Once every 24 hours, Reuters Eikon items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="1d5c9-115">連接器也會將 Reuters Eikon 專案轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-115">The connector also converts Reuters Eikon items to an email message format.</span></span>

3. <span data-ttu-id="1d5c9-116">您在 Microsoft 365 合規性中心建立的 Reuters Eikon 連接器每天會連線至 Globanet Merge1 網站，並將內容傳送至 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-116">The Reuters Eikon connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="1d5c9-117">連接器會使用自動使用者對應的 *電子郵件* 屬性值，將專案匯入至特定使用者的信箱，如 [步驟 3](#step-3-map-users-and-complete-the-connector-setup)所述。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="1d5c9-118">在使用者信箱中建立名為 **Reuters Eikon** 之 [收件匣] 資料夾中的子資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-118">A subfolder in the Inbox folder named **Reuters Eikon** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="1d5c9-119">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="1d5c9-120">每個 Reuters Eikon 專案都包含此屬性，它會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-120">Every Reuters Eikon item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1d5c9-121">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="1d5c9-121">Before you begin</span></span>

- <span data-ttu-id="1d5c9-122">為 Microsoft connector 建立 Globanet Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="1d5c9-123">若要這麼做，請與 [Globanet 客戶支援](https://globanet.com/ms-connectors-contact)部門聯繫。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="1d5c9-124">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="1d5c9-125">在步驟1中建立 Reuters Eikon 連接器的使用者 (，並在步驟 3) 中完成，則必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-125">The user who creates the Reuters Eikon connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="1d5c9-126">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1d5c9-127">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-127">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="1d5c9-128">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="1d5c9-129">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="1d5c9-130">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-reuters-eikon-connector"></a><span data-ttu-id="1d5c9-131">步驟1：設定 Reuters Eikon connector</span><span class="sxs-lookup"><span data-stu-id="1d5c9-131">Step 1: Set up the Reuters Eikon connector</span></span>

<span data-ttu-id="1d5c9-132">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** 頁面，並建立 Reuters Eikon 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Reuters Eikon data.</span></span>

1. <span data-ttu-id="1d5c9-133">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **Reuters] Eikon**。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Eikon**.</span></span>

2. <span data-ttu-id="1d5c9-134">在 [ **Reuters Eikon** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-134">On the **Reuters Eikon** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="1d5c9-135">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="1d5c9-136">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="1d5c9-137">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-eikon-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="1d5c9-138">步驟2：設定 Globanet Merge1 網站上的 Reuters Eikon 連接器</span><span class="sxs-lookup"><span data-stu-id="1d5c9-138">Step 2: Configure the Reuters Eikon connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="1d5c9-139">第二個步驟是設定 Merge1 網站上的 Reuters Eikon 連接器。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-139">The second step is to configure the Reuters Eikon connector on the Merge1 site.</span></span> <span data-ttu-id="1d5c9-140">如需如何在 Globanet Merge1 網站上設定 Reuters Eikon connector 的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-140">For information about how to configure the Reuters Eikon connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="1d5c9-141">在您按一下 **[儲存] & 完成**之後，您會回到 Microsoft 365 規範中心，移至 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-141">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="1d5c9-142">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="1d5c9-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="1d5c9-143">若要對應使用者，並完成 Microsoft 365 規範中心內的連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1d5c9-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="1d5c9-144">在 [將 **外部使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-144">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="1d5c9-145">Reuters Eikon 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-145">The Reuters Eikon items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="1d5c9-146">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="1d5c9-147">在 [系統 **管理員同意** ] 頁面上，按一下 [ **提供同意**]。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-147">On the **Admin Consent** page, click **Provide Consent**.</span></span> <span data-ttu-id="1d5c9-148">您將會重新導向至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="1d5c9-149">按一下 [ **接受** ] 以提供同意。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="1d5c9-150">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="1d5c9-151">若要提供系統管理員同意，您必須使用 Microsoft 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="1d5c9-152">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="1d5c9-153">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-153">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-eikon-connector"></a><span data-ttu-id="1d5c9-154">步驟4：監視 Reuters Eikon connector</span><span class="sxs-lookup"><span data-stu-id="1d5c9-154">Step 4: Monitor the Reuters Eikon connector</span></span>

<span data-ttu-id="1d5c9-155">在您建立 Reuters Eikon 連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-155">After you create the Reuters Eikon connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="1d5c9-156">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="1d5c9-157">按一下 [ **連接器** ] 索引標籤，然後選取 [ **Reuters] Eikon** 連接器以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-157">Click the **Connectors** tab and then select the **Reuters Eikon** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="1d5c9-158">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="1d5c9-159">此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-159">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="1d5c9-160">已知問題</span><span class="sxs-lookup"><span data-stu-id="1d5c9-160">Known issues</span></span>

- <span data-ttu-id="1d5c9-161">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-161">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="1d5c9-162">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="1d5c9-162">Support for larger items will be available at a later date.</span></span>
