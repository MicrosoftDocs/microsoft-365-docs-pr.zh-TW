---
title: 設定連接器以封存 Reuters 處理 Microsoft 365 中的資料
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
description: 系統管理員可以設定連接器，以匯入及封存 Reuters，將資料從 Globanet 處理至 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: bd3eefb1054d8ef9302ffa6f94ddce740bd55a70
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002754"
---
# <a name="set-up-a-connector-to-archive-reuters-dealing-data-preview"></a><span data-ttu-id="770c2-105">設定連接器，封存 Reuters 處理資料 (預覽) </span><span class="sxs-lookup"><span data-stu-id="770c2-105">Set up a connector to archive Reuters Dealing data (preview)</span></span>

<span data-ttu-id="770c2-106">使用 Microsoft 365 規範中心內的 Globanet 連接器，從處理 Microsoft 365 組織中的使用者信箱的 Reuters 匯入及封存資料。</span><span class="sxs-lookup"><span data-stu-id="770c2-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters Dealing platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="770c2-107">Globanet 為您提供 [Reuters 處理](https://globanet.com/reuters-dealing/) 連接器，該連接器設定為定期從協力廠商資料來源捕獲專案 () ，然後將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="770c2-107">Globanet provides you with a [Reuters Dealing](https://globanet.com/reuters-dealing/) connector that's configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="770c2-108">連接器會將 Reuters 處理帳戶的通訊，轉換為電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="770c2-108">The connector converts Dealing communications from the Reuters Dealing account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="770c2-109">Reuters 處理資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="770c2-109">After Reuters Dealing data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="770c2-110">使用 Reuters 處理連接器，以在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="770c2-110">Using a Reuters Dealing connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-dealing-data"></a><span data-ttu-id="770c2-111">處理資料的封存 Reuters</span><span class="sxs-lookup"><span data-stu-id="770c2-111">Overview of archiving Reuters Dealing data</span></span>

<span data-ttu-id="770c2-112">下列概要說明使用連接器封存在 Microsoft 365 中處理資料之 Reuters 的處理常式。</span><span class="sxs-lookup"><span data-stu-id="770c2-112">The following overview explains the process of using a connector to archive the Reuters Dealing data in Microsoft 365.</span></span>

![處理資料的 Reuters 封存工作流程](../media/ReuetersDealingConnectorWorkflow.png)

1. <span data-ttu-id="770c2-114">您的組織可以搭配 Reuters 處理設定和設定 Reuters 處理網站的功能。</span><span class="sxs-lookup"><span data-stu-id="770c2-114">Your organization works with Reuters Dealing to set up and configure a Reuters Dealing site.</span></span>

2. <span data-ttu-id="770c2-115">每24小時一次，Reuters 處理專案會複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="770c2-115">Once every 24 hours, Reuters Dealing items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="770c2-116">連接線也會將專案轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="770c2-116">The connector also converts the items to an email message format.</span></span>

3. <span data-ttu-id="770c2-117">在 Microsoft 365 合規性中心建立的 Reuters 會連線至 Globanet Merge1 網站，並將內容傳送至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="770c2-117">The Reuters Dealing connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="770c2-118">連接器會使用自動使用者對應的 *電子郵件* 屬性值，將專案匯入至特定使用者的信箱，如 [步驟 3](#step-3-map-users-and-complete-the-connector-setup)所述。</span><span class="sxs-lookup"><span data-stu-id="770c2-118">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="770c2-119">在使用者信箱中建立名為 **Reuters 處理** 的收件匣資料夾中的子資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="770c2-119">A subfolder in the Inbox folder named **Reuters Dealing** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="770c2-120">連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。</span><span class="sxs-lookup"><span data-stu-id="770c2-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="770c2-121">每個 Reuters 處理的專案都包含此屬性，它會填入專案的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="770c2-121">Every Reuters Dealing item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="770c2-122">開始之前</span><span class="sxs-lookup"><span data-stu-id="770c2-122">Before you begin</span></span>

- <span data-ttu-id="770c2-123">為 Microsoft connector 建立 Globanet Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="770c2-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="770c2-124">若要建立帳戶，請與 [Globanet 客戶支援](https://globanet.com/contact-us)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="770c2-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="770c2-125">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="770c2-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="770c2-126">在步驟1中建立 Reuters 處理連接器的使用者 (，並在步驟 3) 中完成，則必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="770c2-126">The user who creates the Reuters Dealing connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="770c2-127">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="770c2-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="770c2-128">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="770c2-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="770c2-129">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="770c2-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="770c2-130">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="770c2-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="770c2-131">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="770c2-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article “Manage role groups in Exchange Online”.</span></span>

## <a name="step-1-set-up-the-reuters-dealing-connector"></a><span data-ttu-id="770c2-132">步驟1：設定 Reuters 處理連接器</span><span class="sxs-lookup"><span data-stu-id="770c2-132">Step 1: Set up the Reuters Dealing connector</span></span>

<span data-ttu-id="770c2-133">第一步是存取 Microsoft 365 中的 [ **資料連線器** ] 頁面，並建立 Reuters 處理資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="770c2-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 and create a connector for Reuters Dealing data.</span></span>

1. <span data-ttu-id="770c2-134">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [ **資料連線器** ]  >  **Reuters 處理** 。</span><span class="sxs-lookup"><span data-stu-id="770c2-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Dealing**.</span></span>

2. <span data-ttu-id="770c2-135">在 [ **Reuters 處理** 產品描述] 頁面上，按一下 [ **新增連接器** ]。</span><span class="sxs-lookup"><span data-stu-id="770c2-135">On the **Reuters Dealing** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="770c2-136">在 [ **服務條款** ] 頁面上，按一下 [ **接受** ]。</span><span class="sxs-lookup"><span data-stu-id="770c2-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="770c2-137">輸入識別連接器的唯一名稱，然後按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="770c2-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="770c2-138">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="770c2-138">Sign to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-dealing-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="770c2-139">步驟2：設定 Globanet Merge1 網站上的 Reuters 處理連接器</span><span class="sxs-lookup"><span data-stu-id="770c2-139">Step 2: Configure the Reuters Dealing connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="770c2-140">第二個步驟是設定 Globanet Merge1 網站上的 Reuters 處理連接器。</span><span class="sxs-lookup"><span data-stu-id="770c2-140">The second step is to configure the Reuters Dealing connector on Globanet the Merge1 site.</span></span> <span data-ttu-id="770c2-141">如需設定 Reuters 處理連接器的詳細資訊，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="770c2-141">For information about configuring the Reuters Dealing connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="770c2-142">按一下 **[儲存] & 完成** 之後，就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="770c2-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="770c2-143">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="770c2-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="770c2-144">若要對應使用者，並完成 Microsoft 365 規範中心內的連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="770c2-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="770c2-145">在 [將 **使用者處理為 Microsoft 365 使用者** ] 頁面上的 [對應] Reuters 中，啟用 [自動使用者對應]。</span><span class="sxs-lookup"><span data-stu-id="770c2-145">On the **Map Reuters Dealing users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="770c2-146">Reuters 處理的專案包括稱為「 *電子郵件* 」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="770c2-146">Reuters Dealing items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="770c2-147">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="770c2-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="770c2-148">在 [系統 **管理員同意** ] 頁面上，按一下 [ **提供同意** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="770c2-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="770c2-149">您將會重新導向至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="770c2-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="770c2-150">按一下 [ **接受** ] 以提供同意。</span><span class="sxs-lookup"><span data-stu-id="770c2-150">Click **Accept** to provide the consent.</span></span>

    <span data-ttu-id="770c2-151">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="770c2-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="770c2-152">若要提供系統管理員同意，您必須使用 Microsoft 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="770c2-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="770c2-153">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="770c2-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="770c2-154">按 **[下一步]** ，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="770c2-154">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-dealing-connector"></a><span data-ttu-id="770c2-155">步驟4：監控 Reuters 處理連接器</span><span class="sxs-lookup"><span data-stu-id="770c2-155">Step 4: Monitor the Reuters Dealing connector</span></span>

<span data-ttu-id="770c2-156">在您建立 Reuters 處理連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="770c2-156">After you create the Reuters Dealing connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="770c2-157">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="770c2-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="770c2-158">按一下 [ **連接器** ] 索引標籤，然後選取 [ **Reuters 處理** 連接器] 以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="770c2-158">Click the **Connectors** tab and then select the **Reuters Dealing** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="770c2-159">在 [ **連接器狀態與來源** ] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="770c2-159">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="770c2-160">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="770c2-160">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="770c2-161">已知問題</span><span class="sxs-lookup"><span data-stu-id="770c2-161">Known issues</span></span>

- <span data-ttu-id="770c2-162">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="770c2-162">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="770c2-163">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="770c2-163">Support for larger items will be available at a later date.</span></span>
