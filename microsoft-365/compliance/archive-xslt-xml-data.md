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
description: 系統管理員可以設定連接器，以從 Microsoft 365 中的 Veritas 匯入及封存 XSLT/XML 資料。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 51b05f83c51626bc60dc19b5ec9a63750903281c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163754"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a><span data-ttu-id="bcacd-104">設定連接器以封存 XSLT/XML 資料</span><span class="sxs-lookup"><span data-stu-id="bcacd-104">Set up a connector to archive XSLT/XML data</span></span>

<span data-ttu-id="bcacd-105">使用 Microsoft 365 規範中心內的 Veritas 連接器，將網頁來源的資料匯入和封存至您的 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="bcacd-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Web page source to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="bcacd-106">Veritas 為您提供 [xslt/XML 連接器](https://globanet.com/xslt-xml) ，可讓您快速開發使用 Xslt (可擴充樣式表單語言轉換) 所建立的檔案，將 XML 檔案轉換成其他檔 (格式，例如可以匯入至 Microsoft 365 的 HTML 或文字) 。</span><span class="sxs-lookup"><span data-stu-id="bcacd-106">Veritas provides you with an [XSLT/XML connector](https://globanet.com/xslt-xml) that allows the rapid development of files created by using XSLT (Extensible Style sheet Language Transformations) to transform XML files into other file formats (such as HTML or text) that can be imported to Microsoft 365.</span></span> <span data-ttu-id="bcacd-107">連接器會將專案的內容從 XSLT/XML 來源轉換成電子郵件格式，然後將轉換的專案匯入 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="bcacd-107">The connector converts the content of an item from the XSLT/XML source to an email message format and then imports the converted item to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="bcacd-108">在將 XSLT/XML 資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery，以及保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="bcacd-108">After XSLT/XML data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="bcacd-109">使用 XSLT/XML 連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="bcacd-109">Using an XSLT/XML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-xsltxml-data"></a><span data-ttu-id="bcacd-110">封存 XSLT/XML 資料的概述</span><span class="sxs-lookup"><span data-stu-id="bcacd-110">Overview of archiving XSLT/XML data</span></span>

<span data-ttu-id="bcacd-111">下列概要說明如何使用連接器將 Microsoft 365 中的 XSLT/XML 來來源資料封存。</span><span class="sxs-lookup"><span data-stu-id="bcacd-111">The following overview explains the process of using a connector to archive XSLT/XML source data in Microsoft 365.</span></span>

![XSLT/XML 資料的封存工作流程](../media/XSLT-XMLConnectorWorkflow.png)

1. <span data-ttu-id="bcacd-113">您的組織可以搭配 XSLT/XML 來源來設定及設定 XSLT/XML 網站。</span><span class="sxs-lookup"><span data-stu-id="bcacd-113">Your organization works with the XSLT/XML source to set up and configure an XSLT/XML site.</span></span>

2. <span data-ttu-id="bcacd-114">每24小時一次，會將 XSLT/XML 來源的聊天訊息複製到 Veritas Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="bcacd-114">Once every 24 hours, chat messages from the XSLT/XML source are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="bcacd-115">連接器也會將內容轉換成電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="bcacd-115">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="bcacd-116">您在 Microsoft 365 規範中心建立的 XSLT/XML 連接器，會每天連線到 Veritas Merge1 網站，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="bcacd-116">The XSLT/XML connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="bcacd-117">連接器會使用 [步驟 3] 中所述之自動使用者對應的 *電子郵件* 屬性值，將已轉換的訊息項目匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="bcacd-117">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="bcacd-118">在使用者信箱中建立名為 **XSLT/XML** 的 [收件匣] 資料夾中的新子資料夾，並將訊息項目匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="bcacd-118">A new subfolder in the Inbox folder named **XSLT/XML** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="bcacd-119">連接器會使用 *Email* 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="bcacd-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="bcacd-120">每封郵件都包含此內容，它會填入郵件每一位參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bcacd-120">Every message contains this property, which is populated with the email address of every participant of the message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bcacd-121">開始之前</span><span class="sxs-lookup"><span data-stu-id="bcacd-121">Before you begin</span></span>

- <span data-ttu-id="bcacd-122">建立 Microsoft 連接器的 Veritas Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="bcacd-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="bcacd-123">若要建立此帳戶，請與 [Veritas 客戶支援](https://www.veritas.com/content/support/)聯繫。</span><span class="sxs-lookup"><span data-stu-id="bcacd-123">To create this account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="bcacd-124">當您在步驟1中建立連接器時，您會登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="bcacd-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="bcacd-125">在步驟1中建立 XSLT/XML 連接器 (並在步驟 3) 中完成的使用者，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="bcacd-125">The user who creates the XSLT/XML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="bcacd-126">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="bcacd-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="bcacd-127">根據預設，此角色不會指派給 Exchange Online 中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="bcacd-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="bcacd-128">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="bcacd-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="bcacd-129">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="bcacd-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="bcacd-130">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="bcacd-130">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-xsltxml-connector"></a><span data-ttu-id="bcacd-131">步驟1：設定 XSLT/XML 連接器</span><span class="sxs-lookup"><span data-stu-id="bcacd-131">Step 1: Set up an XSLT/XML connector</span></span>

<span data-ttu-id="bcacd-132">第一步是存取 Microsoft 365 規範中心內的 **資料連線器** ，並建立 XSLT/XML 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="bcacd-132">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for XSLT/XML data.</span></span>

1. <span data-ttu-id="bcacd-133">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **XSLT/XML**]。</span><span class="sxs-lookup"><span data-stu-id="bcacd-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **XSLT/XML**.</span></span>

2. <span data-ttu-id="bcacd-134">在 [ **XSLT/XML** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="bcacd-134">On the **XSLT/XML** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="bcacd-135">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="bcacd-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="bcacd-136">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bcacd-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="bcacd-137">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="bcacd-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-an-xsltxml-connector"></a><span data-ttu-id="bcacd-138">步驟2：設定 XSLT/XML 連接器</span><span class="sxs-lookup"><span data-stu-id="bcacd-138">Step 2: Configure an XSLT/XML connector</span></span>

<span data-ttu-id="bcacd-139">第二個步驟是設定 Merge1 網站上的 XSLT/XML 連接器。</span><span class="sxs-lookup"><span data-stu-id="bcacd-139">The second step is to configure the XSLT/XML connector on the Merge1 site.</span></span> <span data-ttu-id="bcacd-140">如需如何在 Veritas Merge1 網站上設定 XSLT/XML 連接器的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="bcacd-140">For information about how to configure the XSLT/XML connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="bcacd-141">按一下 **[儲存] & 完成** 之後，就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="bcacd-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="bcacd-142">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="bcacd-142">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="bcacd-143">若要對應使用者，並完成 Microsoft 365 規範中心內的連接器設定，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bcacd-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

2. <span data-ttu-id="bcacd-144">在 [將 **XSLT/XML 使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="bcacd-144">On the **Map XSLT/XML users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="bcacd-145">XSLT/XML 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bcacd-145">The XSLT/XML items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="bcacd-146">如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="bcacd-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

3. <span data-ttu-id="bcacd-147">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="bcacd-147">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xsltxml-connector"></a><span data-ttu-id="bcacd-148">步驟4：監視 XSLT/XML 連接器</span><span class="sxs-lookup"><span data-stu-id="bcacd-148">Step 4: Monitor the XSLT/XML connector</span></span>

<span data-ttu-id="bcacd-149">在您建立 XSLT/XML 連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="bcacd-149">After you create the XSLT/XML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="bcacd-150">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="bcacd-150">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="bcacd-151">按一下 [ **連接器** ] 索引標籤，然後選取 **XSLT/XML** 連接器以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="bcacd-151">Click the **Connectors** tab and then select the **XSLT/XML** connector to display the flyout page.</span></span> <span data-ttu-id="bcacd-152">此頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="bcacd-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="bcacd-153">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="bcacd-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="bcacd-154">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="bcacd-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="bcacd-155">已知問題</span><span class="sxs-lookup"><span data-stu-id="bcacd-155">Known issues</span></span>

- <span data-ttu-id="bcacd-156">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="bcacd-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="bcacd-157">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="bcacd-157">Support for larger items will be available at a later date.</span></span>