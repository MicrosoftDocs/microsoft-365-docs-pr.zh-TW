---
title: 設定連接器以封存 Microsoft 365 中的 XSLT/XML 資料
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
description: 系統管理員可以設定連接器，以從 Microsoft 365 的 Globanet 匯入及封存 XSLT/XML 資料。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 20d24e919c0fe045e487c41e42745f73acb521ad
ms.sourcegitcommit: 16cbac5eacadd7b30cbca1fd2435ba9098de5e1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785495"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a><span data-ttu-id="ad5e1-104">設定連接器以封存 XSLT/XML 資料</span><span class="sxs-lookup"><span data-stu-id="ad5e1-104">Set up a connector to archive XSLT/XML data</span></span>

<span data-ttu-id="ad5e1-105">使用 Microsoft 365 規範中心內的 Globanet 連接器，將網頁來源的資料匯入至您的 Microsoft 365 組織中的使用者信箱，並將其封存。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Web page source to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="ad5e1-106">Globanet 為您提供 [xslt/XML 連接器](https://globanet.com/xslt-xml) ，可讓您快速開發使用 Xslt (可擴充樣式表單語言轉換) 所建立的檔案，將 XML 檔案轉換成其他檔 (格式，例如可以匯入至 Microsoft 365 的 HTML 或文字) 。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-106">Globanet provides you with an [XSLT/XML connector](https://globanet.com/xslt-xml) that allows the rapid development of files created by using XSLT (Extensible Style sheet Language Transformations) to transform XML files into other file formats (such as HTML or text) that can be imported to Microsoft 365.</span></span> <span data-ttu-id="ad5e1-107">連接器會將專案的內容從 XSLT/XML 來源轉換成電子郵件格式，然後將轉換的專案匯入 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-107">The connector converts the content of an item from the XSLT/XML source to an email message format and then imports the converted item to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="ad5e1-108">在將 XSLT/XML 資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery，以及保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-108">After XSLT/XML data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="ad5e1-109">使用 XSLT/XML 連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-109">Using an XSLT/XML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-xsltxml-data"></a><span data-ttu-id="ad5e1-110">封存 XSLT/XML 資料的概述</span><span class="sxs-lookup"><span data-stu-id="ad5e1-110">Overview of archiving XSLT/XML data</span></span>

<span data-ttu-id="ad5e1-111">下列概要說明如何使用連接器將 Microsoft 365 中的 XSLT/XML 來來源資料封存。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-111">The following overview explains the process of using a connector to archive XSLT/XML source data in Microsoft 365.</span></span>

![XSLT/XML 資料的封存工作流程](../media/XSLT-XMLConnectorWorkflow.png)

1. <span data-ttu-id="ad5e1-113">您的組織可以搭配 XSLT/XML 來源來設定及設定 XSLT/XML 網站。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-113">Your organization works with the XSLT/XML source to set up and configure an XSLT/XML site.</span></span>

2. <span data-ttu-id="ad5e1-114">每24小時一次，來自 XSLT/XML 來源的聊天訊息會複製到 Globanet Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-114">Once every 24 hours, chat messages from the XSLT/XML source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="ad5e1-115">連接器也會將內容轉換成電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-115">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="ad5e1-116">您在 Microsoft 365 規範中心建立的 XSLT/XML 連接器，會每天連線到 Globanet Merge1 網站，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-116">The XSLT/XML connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="ad5e1-117">連接器會使用 [步驟 3] 中所述之自動使用者對應的 *電子郵件* 屬性值，將已轉換的訊息項目匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-117">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="ad5e1-118">在使用者信箱中建立名為 **XSLT/XML** 的 [收件匣] 資料夾中的新子資料夾，並將訊息項目匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-118">A new subfolder in the Inbox folder named **XSLT/XML** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="ad5e1-119">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="ad5e1-120">每封郵件都包含此內容，它會填入郵件每一位參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-120">Every message contains this property, which is populated with the email address of every participant of the message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ad5e1-121">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="ad5e1-121">Before you begin</span></span>

- <span data-ttu-id="ad5e1-122">為 Microsoft connector 建立 Globanet Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="ad5e1-123">若要這麼做，請與 [Globanet 客戶支援](https://globanet.com/contact-us/)部門聯繫。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-123">To do this, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="ad5e1-124">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="ad5e1-125">在步驟1中建立 XSLT/XML 連接器 (並在步驟 3) 中完成的使用者，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-125">The user who creates the XSLT/XML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="ad5e1-126">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ad5e1-127">根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-127">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="ad5e1-128">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="ad5e1-129">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="ad5e1-130">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-xsltxml-connector"></a><span data-ttu-id="ad5e1-131">步驟1：設定 XSLT/XML 連接器</span><span class="sxs-lookup"><span data-stu-id="ad5e1-131">Step 1: Set up an XSLT/XML connector</span></span>

<span data-ttu-id="ad5e1-132">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** ，並建立 XSLT/XML 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-132">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for XSLT/XML data.</span></span>

1. <span data-ttu-id="ad5e1-133">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [ **資料連線器**  >  **XSLT/XML** ]。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **XSLT/XML** .</span></span>

2. <span data-ttu-id="ad5e1-134">在 [ **XSLT/XML** 產品描述] 頁面上，按一下 [ **新增連接器** ]。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-134">On the **XSLT/XML** product description page, click **Add new connector** .</span></span>

3. <span data-ttu-id="ad5e1-135">在 [ **服務條款** ] 頁面上，按一下 [ **接受** ]。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-135">On the **Terms of service** page, click **Accept** .</span></span>

4. <span data-ttu-id="ad5e1-136">輸入識別連接器的唯一名稱，然後按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-136">Enter a unique name that identifies the connector, and then click **Next** .</span></span>

5. <span data-ttu-id="ad5e1-137">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-an-xsltxml-connector"></a><span data-ttu-id="ad5e1-138">步驟2：設定 XSLT/XML 連接器</span><span class="sxs-lookup"><span data-stu-id="ad5e1-138">Step 2: Configure an XSLT/XML connector</span></span>

<span data-ttu-id="ad5e1-139">第二個步驟是設定 Merge1 網站上的 XSLT/XML 連接器。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-139">The second step is to configure the XSLT/XML connector on the Merge1 site.</span></span> <span data-ttu-id="ad5e1-140">如需如何在 Globanet Merge1 網站上設定 XSLT/XML 連接器的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-140">For information about how to configure the XSLT/XML connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="ad5e1-141">在您按一下 **[儲存] & 完成** 之後，您會回到 Microsoft 365 規範中心，移至 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-141">After you click **Save & Finish** , you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="ad5e1-142">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="ad5e1-142">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="ad5e1-143">若要對應使用者，並完成 Microsoft 365 規範中心內的連接器設定，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ad5e1-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

2. <span data-ttu-id="ad5e1-144">在 [將 **XSLT/XML 使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-144">On the **Map XSLT/XML users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="ad5e1-145">XSLT/XML 專案包括稱為「 *電子郵件* 」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-145">The XSLT/XML items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="ad5e1-146">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

3. <span data-ttu-id="ad5e1-147">在 [系統 **管理員同意** ] 頁面上，按一下 [ **提供同意** ]。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-147">On the **Admin Consent** page, click **Provide Consent** .</span></span> <span data-ttu-id="ad5e1-148">您將會重新導向至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="ad5e1-149">按一下 [ **接受** ] 以提供同意。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="ad5e1-150">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="ad5e1-151">若要提供系統管理員同意，您必須使用 Microsoft 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="ad5e1-152">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

4. <span data-ttu-id="ad5e1-153">按 **[下一步]** ，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-153">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xsltxml-connector"></a><span data-ttu-id="ad5e1-154">步驟4：監視 XSLT/XML 連接器</span><span class="sxs-lookup"><span data-stu-id="ad5e1-154">Step 4: Monitor the XSLT/XML connector</span></span>

<span data-ttu-id="ad5e1-155">在您建立 XSLT/XML 連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-155">After you create the XSLT/XML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="ad5e1-156">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ad5e1-157">按一下 [ **連接器** ] 索引標籤，然後選取 **XSLT/XML** 連接器以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-157">Click the **Connectors** tab and then select the **XSLT/XML** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="ad5e1-158">在 [ **連接器狀態與來源** ] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-158">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="ad5e1-159">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-159">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ad5e1-160">已知問題</span><span class="sxs-lookup"><span data-stu-id="ad5e1-160">Known issues</span></span>

- <span data-ttu-id="ad5e1-161">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-161">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="ad5e1-162">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="ad5e1-162">Support for larger items will be available at a later date.</span></span>
