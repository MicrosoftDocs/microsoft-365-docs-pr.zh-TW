---
title: 設定從 Microsoft 365 中的 Facebook 資料封存工作區的連接器
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
ROBOTS: NOINDEX, NOFOLLOW
description: 管理員可以設定連接器，將來自于 Globanet 之 Merge1 網站上的 Facebook 的資料匯入和封存至 Microsoft 365。 設定連接器需要您使用 Globanet 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: b57ad60133fdb7cee7db24781755bda032b10a89
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47362002"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data-preview"></a><span data-ttu-id="80351-104">設定從 Facebook 資料 (預覽中封存工作場所的連接器) </span><span class="sxs-lookup"><span data-stu-id="80351-104">Set up a connector to archive Workplace from Facebook data (preview)</span></span>

<span data-ttu-id="80351-105">使用 Microsoft 365 規範中心內的 Globanet 連接器，從 Facebook 將工作地點的資料匯入至您的 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="80351-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Workplace from Facebook to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="80351-106">Globanet 提供 [來自 Facebook 連接器的工作區](https://globanet.com/workplace/) ，其設定為定期捕獲協力廠商資料來源中的專案 () 並將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="80351-106">Globanet provides a [Workplace from Facebook](https://globanet.com/workplace/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="80351-107">連接器會將聊天、附件、帖子和影片等內容轉換成電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="80351-107">The connector converts the content such as chats, attachments, posts, and videos from Workplace to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="80351-108">將工作場所資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="80351-108">After Workplace data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="80351-109">使用來自 Facebook connector 的工作場所，在 Microsoft 365 中匯入及封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="80351-109">Using Workplace from Facebook connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-workplace-from-facebook-data"></a><span data-ttu-id="80351-110">從 Facebook 資料封存工作場所的概覽</span><span class="sxs-lookup"><span data-stu-id="80351-110">Overview of archiving Workplace from Facebook data</span></span>

<span data-ttu-id="80351-111">下列概要說明如何使用連接器封存 Microsoft 365 中的工作場所資料。</span><span class="sxs-lookup"><span data-stu-id="80351-111">The following overview explains the process of using a connector to archive Workplace data in Microsoft 365.</span></span>

![從 Facebook 資料封存工作流程](../media/WorkplaceConnectorWorkflow.png)

1. <span data-ttu-id="80351-113">您的組織使用來自 Facebook 的工作區來設定及設定工作場所網站。</span><span class="sxs-lookup"><span data-stu-id="80351-113">Your organization works with Workplace from Facebook to set up and configure a Workplace site.</span></span>

2. <span data-ttu-id="80351-114">每24小時一次，工作場所的專案會複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="80351-114">Once every 24 hours, items from Workplace are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="80351-115">連接器也會將這些專案的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="80351-115">The connector also converts the content of these items to an email message format.</span></span>

3. <span data-ttu-id="80351-116">您在 Microsoft 365 規範中心內建立的 Facebook 連接器中的工作區，會每天連線到 Globanet Merge1，並將工作區專案傳送至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="80351-116">The Workplace from Facebook connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the Workplace items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="80351-117">連接器會使用 [步驟 3] 中所述之自動使用者對應的 *電子郵件* 屬性值，將轉換後的專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="80351-117">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="80351-118">建立從 Facebook 中名為 **Workplace 之** [收件匣] 資料夾中的子資料夾，並將工作區專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="80351-118">A subfolder in the Inbox folder named **Workplace from Facebook** is created, and the Workplace items are imported to that folder.</span></span> <span data-ttu-id="80351-119">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="80351-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="80351-120">每個 Workplace 專案都包含此屬性，其是以每個聊天或張貼參與者的電子郵件地址填入。</span><span class="sxs-lookup"><span data-stu-id="80351-120">Every Workplace item contains this property, which is populated with the email address of every chat or post participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="80351-121">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="80351-121">Before you begin</span></span>

- <span data-ttu-id="80351-122">從 Facebook connector 接收工作區的條款及條件，以建立 Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="80351-122">Create a Merge1 account by accepting their terms and conditions for the Workplace from Facebook connector.</span></span> <span data-ttu-id="80351-123">您將需要與 [Globanet 客戶支援](https://globanet.com/contact-us/)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="80351-123">Here you will need to contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="80351-124">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="80351-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="80351-125">從 APIs 建立自訂整合， https://my.workplace.com/work/admin/apps/ 以透過相容性和 eDiscovery 目的從工作場所取得資料。</span><span class="sxs-lookup"><span data-stu-id="80351-125">Create a custom integration at https://my.workplace.com/work/admin/apps/ to retrieve data from Workplace via APIs for compliance and eDiscovery purposes.</span></span>

   <span data-ttu-id="80351-126">建立整合時，工作場所平臺會產生一組唯一的認證，用來產生驗證所用的權杖。</span><span class="sxs-lookup"><span data-stu-id="80351-126">When creating the integration, the Workplace platform generates a set of unique credentials used to generate tokens that are used for authentication.</span></span> <span data-ttu-id="80351-127">這些標記是在步驟2中從 Facebook 連接器設定向導的工作區使用。</span><span class="sxs-lookup"><span data-stu-id="80351-127">These tokens are used in the Workplace from Facebook connector configuration wizard in Step 2.</span></span> <span data-ttu-id="80351-128">如需如何建立應用程式的逐步指示，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="80351-128">For step-by step instructions about how to create the applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="80351-129">在步驟1中從 Facebook 連接器建立工作區的使用者 (，並在步驟 3) 中完成，則必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="80351-129">The user who creates the Workplace from Facebook connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="80351-130">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="80351-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="80351-131">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="80351-131">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="80351-132">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="80351-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="80351-133">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="80351-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="80351-134">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="80351-134">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a><span data-ttu-id="80351-135">步驟1：從 Facebook connector 設定工作區</span><span class="sxs-lookup"><span data-stu-id="80351-135">Step 1: Set up the Workplace from Facebook connector</span></span>

<span data-ttu-id="80351-136">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** 頁面，並建立工作場所資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="80351-136">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Workplace data.</span></span>

1. <span data-ttu-id="80351-137">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 並按一下 Facebook 中的 [**資料連線器**]  >  **工作區**。</span><span class="sxs-lookup"><span data-stu-id="80351-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Workplace from Facebook**.</span></span>

2. <span data-ttu-id="80351-138">在 [ **從 Facebook 產品的工作場所** 描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="80351-138">On the **Workplace from Facebook** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="80351-139">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="80351-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="80351-140">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="80351-140">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="80351-141">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="80351-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="80351-142">步驟2：在 Globanet Merge1 網站上設定 Facebook connector 中的工作區</span><span class="sxs-lookup"><span data-stu-id="80351-142">Step 2: Configure the Workplace from Facebook connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="80351-143">第二個步驟是在 Merge1 網站上設定 Facebook connector 中的工作區。</span><span class="sxs-lookup"><span data-stu-id="80351-143">The second step is to configure the Workplace from Facebook connector on the Merge1 site.</span></span> <span data-ttu-id="80351-144">如需如何從 Facebook 連接器設定工作場所的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="80351-144">For information about how to configure the Workplace from Facebook connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="80351-145">在您按一下 **[儲存] & 完成**之後，您會回到 Microsoft 365 規範中心，移至 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="80351-145">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="80351-146">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="80351-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="80351-147">若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="80351-147">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="80351-148">在 [將 **外部使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="80351-148">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="80351-149">工作場所專案包括一個稱為「 *電子郵件* 」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="80351-149">The Workplace items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="80351-150">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="80351-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="80351-151">在 [系統 **管理員同意** ] 頁面上，按一下 [ **提供同意** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="80351-151">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="80351-152">您將會重新導向至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="80351-152">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="80351-153">按一下 [ **接受** ] 以提供同意。</span><span class="sxs-lookup"><span data-stu-id="80351-153">Click **Accept** to provide the consent.</span></span>
  
   <span data-ttu-id="80351-154">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="80351-154">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="80351-155">若要提供系統管理員同意，您必須使用 Microsoft 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="80351-155">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="80351-156">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="80351-156">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="80351-157">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="80351-157">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a><span data-ttu-id="80351-158">步驟4：從 Facebook connector 監控工作場所</span><span class="sxs-lookup"><span data-stu-id="80351-158">Step 4: Monitor the Workplace from Facebook connector</span></span>

<span data-ttu-id="80351-159">在您從 Facebook connector 建立工作區之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="80351-159">After you create the Workplace from Facebook connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="80351-160">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="80351-160">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="80351-161">按一下 [ **連接器** ] 索引標籤，然後選取 [Facebook connector] **中的工作區** ，以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="80351-161">Click the **Connectors** tab and then select the **Workplace from Facebook** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="80351-162">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="80351-162">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="80351-163">此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="80351-163">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="80351-164">已知問題</span><span class="sxs-lookup"><span data-stu-id="80351-164">Known issues</span></span>

- <span data-ttu-id="80351-165">此時，我們不支援匯入大於 10 MB 的附件，但較大專案的支援將于之後提供。</span><span class="sxs-lookup"><span data-stu-id="80351-165">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>