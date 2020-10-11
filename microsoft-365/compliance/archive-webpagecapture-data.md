---
title: 設定在 Microsoft 365 中封存網頁數據的連接器
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
description: 系統管理員可在 Microsoft 365 中設定從 Globanet 匯入及封存網頁捕獲資料的連接器。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: b3f622a63e4f4dfe550f481bee6b3a56dfd3bdb1
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409112"
---
# <a name="set-up-a-connector-to-archive-webpage-data-preview"></a><span data-ttu-id="9d579-104">設定連接器以封存網頁數據 (預覽) </span><span class="sxs-lookup"><span data-stu-id="9d579-104">Set up a connector to archive webpage data (preview)</span></span>

<span data-ttu-id="9d579-105">使用 Microsoft 365 規範中心內的 Globanet 連接器，將網頁中的資料匯入至您的 Microsoft 365 組織中的使用者信箱，並將其封存。</span><span class="sxs-lookup"><span data-stu-id="9d579-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from webpages to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="9d579-106">Globanet 提供一個 [網頁捕獲](https://globanet.com/webpage-capture) 連接器，可在特定的網站或整個網域中，捕獲特定網頁 (和這些頁面上的任何連結) 。</span><span class="sxs-lookup"><span data-stu-id="9d579-106">Globanet provides a [Webpage Capture](https://globanet.com/webpage-capture) connector that captures specific webpages (and any links on those pages) in a specific website or an entire domain.</span></span> <span data-ttu-id="9d579-107">連接器會將網頁內容轉換成 PDF、PNG 或自訂檔案格式，然後將轉換的檔案附加到電子郵件，然後將這些電子郵件專案匯入至 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="9d579-107">The connector converts the webpage content to a PDF, PNG, or custom file format and then attaches the converted files to an email message and then imports those email items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="9d579-108">在使用者信箱中儲存網頁內容之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery，以及保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="9d579-108">After webpage content is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="9d579-109">在 Microsoft 365 中使用網頁捕獲連接器匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="9d579-109">Using a Webpage Capture connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webpage-data"></a><span data-ttu-id="9d579-110">封存網頁數據的概覽</span><span class="sxs-lookup"><span data-stu-id="9d579-110">Overview of archiving webpage data</span></span>

<span data-ttu-id="9d579-111">下列概要說明使用連接器在 Microsoft 365 中封存網頁內容的程式。</span><span class="sxs-lookup"><span data-stu-id="9d579-111">The following overview explains the process of using a connector to archive webpage content in Microsoft 365.</span></span>

![網頁數據的封存工作流程](../media/WebPageCaptureConnectorWorkflow.png)

1. <span data-ttu-id="9d579-113">您的組織與網頁來源搭配使用，以設定和設定網頁捕獲網站。</span><span class="sxs-lookup"><span data-stu-id="9d579-113">Your organization works with the webpage source to set up and configure a Webpage Capture site.</span></span>

2. <span data-ttu-id="9d579-114">每24小時一次，網頁來源專案會複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="9d579-114">Once every 24 hours, the webpage sources items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="9d579-115">連接器也會將網頁內容轉換並附加至電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9d579-115">The connector also converts and attaches the content of a webpage to an email message.</span></span>

3. <span data-ttu-id="9d579-116">您在 Microsoft 365 規範中心建立的網頁捕獲連接器，會每天連線到 Globanet Merge1 網站，並將網頁專案傳送至 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="9d579-116">The Webpage Capture connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the webpage items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="9d579-117">連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述的自動使用者對應的*電子郵件*屬性值，將已轉換的網頁專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="9d579-117">The connector imports the converted webpage items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="9d579-118">在使用者信箱中建立名為「 **網頁捕獲** 」的收件匣資料夾中的子資料夾，並且將網頁專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="9d579-118">A subfolder in the Inbox folder named **Webpage Capture** is created in the user mailboxes, and the webpage items are imported to that folder.</span></span> <span data-ttu-id="9d579-119">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="9d579-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="9d579-120">每個網頁專案都包含此屬性，它會填入您在 [步驟 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site)中設定網頁捕獲連接器時所提供的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="9d579-120">Every webpage item contains this property, which is populated with the email addresses provided when you configure the Webpage Capture connector in [Step 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9d579-121">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="9d579-121">Before you begin</span></span>

- <span data-ttu-id="9d579-122">為 Microsoft connector 建立 Globanet Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="9d579-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="9d579-123">若要這麼做，請與 [Globanet 客戶支援](https://globanet.com/ms-connectors-contact/)部門聯繫。</span><span class="sxs-lookup"><span data-stu-id="9d579-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="9d579-124">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="9d579-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="9d579-125">您必須使用 Globanet 支援來設定自訂的檔案格式，將網頁專案轉換成。</span><span class="sxs-lookup"><span data-stu-id="9d579-125">You need to work with Globanet support to set up a custom file format to convert the webpage items to.</span></span> <span data-ttu-id="9d579-126">如需詳細資訊，請參閱 Merge1 Third-Party connector User Guide in in</span><span class="sxs-lookup"><span data-stu-id="9d579-126">For more information, see the Merge1 Third-Party Connectors User Guide in</span></span> 

- <span data-ttu-id="9d579-127">在步驟1中建立網頁捕獲連接器的使用者 (，並在步驟 3) 中完成，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="9d579-127">The user who creates the Webpage Capture connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="9d579-128">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="9d579-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9d579-129">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="9d579-129">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="9d579-130">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="9d579-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="9d579-131">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="9d579-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="9d579-132">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="9d579-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webpage-capture-connector"></a><span data-ttu-id="9d579-133">步驟1：設定網頁捕獲連接器</span><span class="sxs-lookup"><span data-stu-id="9d579-133">Step 1: Set up the Webpage Capture connector</span></span>

<span data-ttu-id="9d579-134">第一步是存取 **資料連線器** ，並建立網頁來來源資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="9d579-134">The first step is to access to the **Data Connectors** and create a connector for Web Page source data.</span></span>

1. <span data-ttu-id="9d579-135">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**]  >  **網頁獲取區**。</span><span class="sxs-lookup"><span data-stu-id="9d579-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webpage Capture**.</span></span>

2. <span data-ttu-id="9d579-136">在 [ **網頁捕獲** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="9d579-136">On the **Webpage Capture** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="9d579-137">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="9d579-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="9d579-138">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9d579-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="9d579-139">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="9d579-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="9d579-140">步驟2：在 Globanet Merge1 網站上設定網頁捕獲連接器</span><span class="sxs-lookup"><span data-stu-id="9d579-140">Step 2: Configure the Webpage Capture connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="9d579-141">第二個步驟是在 Globanet Merge1 網站上設定網頁捕獲連接器。</span><span class="sxs-lookup"><span data-stu-id="9d579-141">The second step is to configure the Webpage Capture connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="9d579-142">如需如何設定網頁 Capture connector 的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="9d579-142">For information about how to configure the Webpage Capture connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="9d579-143">在您按一下 **[儲存] & 完成**之後，您會回到 Microsoft 365 規範中心，移至 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9d579-143">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="9d579-144">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="9d579-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="9d579-145">若要對應使用者，並完成 Microsoft 365 規範中心內的連接器設定，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9d579-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="9d579-146">在 [地圖] 網頁上的 [ **將使用者捕獲至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="9d579-146">On the **Map Webpage Capture users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="9d579-147">網頁捕獲專案包括一個稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="9d579-147">The Webpage Capture items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="9d579-148">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="9d579-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="9d579-149">在 [系統 **管理員同意** ] 頁面上，按一下 [ **提供同意**]。</span><span class="sxs-lookup"><span data-stu-id="9d579-149">On the **Admin Consent** page, click **Provide Consent**.</span></span> <span data-ttu-id="9d579-150">您將會重新導向至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="9d579-150">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="9d579-151">按一下 [ **接受** ] 以提供同意。</span><span class="sxs-lookup"><span data-stu-id="9d579-151">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="9d579-152">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="9d579-152">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="9d579-153">若要提供系統管理員同意，您必須使用 Microsoft 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="9d579-153">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="9d579-154">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="9d579-154">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="9d579-155">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="9d579-155">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webpage-capture-connector"></a><span data-ttu-id="9d579-156">步驟4：監視網頁捕獲連接器</span><span class="sxs-lookup"><span data-stu-id="9d579-156">Step 4: Monitor the Webpage Capture connector</span></span>

<span data-ttu-id="9d579-157">在您建立網頁捕獲連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="9d579-157">After you create the Webpage Capture connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="9d579-158">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="9d579-158">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="9d579-159">按一下 [ **連接器** ] 索引標籤，然後選取 **網頁捕獲** 連接器以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="9d579-159">Click the **Connectors** tab and then select the **Webpage Capture** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="9d579-160">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="9d579-160">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="9d579-161">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="9d579-161">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="9d579-162">已知問題</span><span class="sxs-lookup"><span data-stu-id="9d579-162">Known issues</span></span>

- <span data-ttu-id="9d579-163">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="9d579-163">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="9d579-164">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="9d579-164">Support for larger items will be available at a later date.</span></span>
