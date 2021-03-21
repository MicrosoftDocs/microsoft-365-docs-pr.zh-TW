---
title: 設定從 TeleMessage 企業數位檔案器封存資料的連接器
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
description: 系統管理員可以設定連接器，以匯入及封存來自 TeleMessage Enterprise Number archive 的 SMS 和 MMS 資料。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 1322cafad94c8b2163c38e3c988feefc4ff1221a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921743"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a><span data-ttu-id="a5fc1-104">設定連接器以封存企業數位資料</span><span class="sxs-lookup"><span data-stu-id="a5fc1-104">Set up a connector to archive Enterprise Number data</span></span>

<span data-ttu-id="a5fc1-105">使用 Microsoft 365 規範中心內的 TeleMessage 連接器，匯入及封存短信服務 (SMS) 和多媒體訊息服務， (MMS) 郵件、聊天訊息、語音通話記錄，以及來自企業號碼記錄器的語音通話記錄。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) and Multimedia Messaging Service (MMS) messages, chat messages, voice call recordings, and voice call logs from the Enterprise Number Archiver.</span></span> <span data-ttu-id="a5fc1-106">在您設定及設定連接器之後，它每天會連線到您組織的 TeleMessage 帳戶，並將使用 TeleMessage 企業數位歸檔人員的員工行動通訊資料匯入 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-106">After you set up and configure a connector, it connects to your organization's TeleMessage account once every day and imports the mobile communication data of employees using the TeleMessage Enterprise Number Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="a5fc1-107">在 TeleMessage 企業編號歸檔器連接器資料儲存在使用者信箱之後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋、In-Place 封存、審核、通訊法規遵從性及 Microsoft 365 保留原則）套用至企業編號歸檔資料。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-107">After the TeleMessage Enterprise Number Archiver connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to Enterprise Number Archiver data.</span></span> <span data-ttu-id="a5fc1-108">例如，您可以使用內容搜尋來搜尋 TeleMessage Enterprise Number 記錄器的 SMS、MMS 和 Voice 通話，或在高級 eDiscovery 案例中，將包含企業號碼記錄器連接器資料的信箱與保管人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-108">For example, you can search the TeleMessage Enterprise Number Archiver SMS, MMS, and Voice Call using Content Search or associate the mailbox that contains the Enterprise Number Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="a5fc1-109">在 Microsoft 365 中使用企業編號檔案器以匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-109">Using an Enterprise Number Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-enterprise-number-data"></a><span data-ttu-id="a5fc1-110">封存企業數位資料</span><span class="sxs-lookup"><span data-stu-id="a5fc1-110">Overview of archiving Enterprise Number data</span></span>

<span data-ttu-id="a5fc1-111">下列概要說明如何使用連接器封存 Microsoft 365 中的商業網路資料。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-111">The following overview explains the process of using a connector to archive Enterprise Network data in Microsoft 365.</span></span>

![企業數位封存工作流程](../media/EnterpriseNumberConnectorWorkflow.png)

1. <span data-ttu-id="a5fc1-113">您的組織與 TeleMessage 搭配使用，以設定企業數位歸檔器連接器。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-113">Your organization works with TeleMessage to set up an Enterprise Number Archiver connector.</span></span> <span data-ttu-id="a5fc1-114">如需詳細資訊，請參閱 [此處](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/)。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-114">For more details refer to [here](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).</span></span>

2. <span data-ttu-id="a5fc1-115">您在 Microsoft 365 合規性中心內建立的企業編號歸檔連接器會每天連線到 TeleMessage 網站，並將電子郵件訊息從過去24小時內傳送至 Microsoft 雲端中的 secure Azure Storage 區域。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-115">The Enterprise Number Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

3. <span data-ttu-id="a5fc1-116">連接器會將行動通訊專案匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-116">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="a5fc1-117">在特定使用者的信箱中建立名為 Enterprise Number 的新資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-117">A new folder named Enterprise Number Archiver is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="a5fc1-118">連接器會使用 *使用者的電子郵件地址* 屬性值進行對應。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-118">The connector does mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="a5fc1-119">每封電子郵件都包含此內容，該屬性會填入電子郵件的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-119">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="a5fc1-120">除了使用 *使用者之電子郵件地址* 屬性值的自動使用者對應，您也可以透過上載 CSV 對應檔來定義自訂對應。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-120">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="a5fc1-121">這個對應檔案應該包含使用者的行動電話號碼，以及每位使用者對應的 Microsoft 365 信箱位址。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-121">This mapping file should contain User’s mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="a5fc1-122">如果您啟用自動使用者對應，並提供自訂對應，則每個電子郵件專案連接器都會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-122">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="a5fc1-123">如果找不到與使用者的行動電話號碼相對應的有效 Microsoft 365 使用者，連接器會使用該電子郵件專案的使用者電子郵件地址屬性。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-123">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="a5fc1-124">如果連接器在自訂對應檔案或電子郵件專案的 [ *電子郵件地址* ] 屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-124">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user’s email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a5fc1-125">開始之前</span><span class="sxs-lookup"><span data-stu-id="a5fc1-125">Before you begin</span></span>

<span data-ttu-id="a5fc1-126">封存企業數位記錄器資料所需的一些執行步驟是 Microsoft 365 的外部，必須先完成，您才能在規範中心建立連接器。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-126">Some of the implementation steps required to archive Enterprise Number Archiver data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="a5fc1-127">[從 TeleMessage 訂購企業號碼歸檔服務](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)，並為您的組織取得有效的管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-127">Order the [Enterprise Number Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="a5fc1-128">當您在規範中心建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-128">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="a5fc1-129">在 TeleMessage 帳戶中，註冊所有需要 Enterprise Number SMS/MMS 網路封存的使用者。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-129">Register all users that require Enterprise Number SMS/MMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="a5fc1-130">註冊使用者時，請務必使用與 Microsoft 365 帳戶所用相同的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-130">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="a5fc1-131">在您員工的行動電話上安裝及啟動 TeleMessage 企業數位歸檔器應用程式。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-131">Install and activate the TeleMessage Enterprise Number Archiver app on the mobile phones of your employees.</span></span>

- <span data-ttu-id="a5fc1-132">在 Exchange Online 中，必須將信箱匯入匯出角色指派給建立企業號碼歸檔器連接器的使用者。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-132">The user who creates a Enterprise Number Archiver connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a5fc1-133">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面中新增連接器時，這是必要的。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-133">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a5fc1-134">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-134">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="a5fc1-135">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-135">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a5fc1-136">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-136">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a5fc1-137">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-137">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-an-enterprise-number-archiver-connector"></a><span data-ttu-id="a5fc1-138">建立企業編號歸檔器連接器</span><span class="sxs-lookup"><span data-stu-id="a5fc1-138">Create an Enterprise Number Archiver connector</span></span>

<span data-ttu-id="a5fc1-139">在您完成上一節所述的必要條件之後，您可以在 Microsoft 365 規範中心內建立企業編號歸檔器連接器。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-139">After you've completed the prerequisites described in the previous section, you can create an Enterprise Number Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a5fc1-140">連接器會使用您提供的資訊來連線至 TeleMessage 網站，並將 SMS、MMS 和語音電話訊息轉接至 Microsoft 365 中對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-140">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS, MMS, and voice call messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="a5fc1-141">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [ **資料連線器** \> **企業數位歸檔** 器]。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-141">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **Enterprise Number Archiver**.</span></span>

2. <span data-ttu-id="a5fc1-142">在 [**企業編號歸檔** 器產品描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="a5fc1-142">On the **Enterprise Number Archiver** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="a5fc1-143">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-143">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="a5fc1-144">在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-144">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="a5fc1-145">使用者 **名稱：** 您的 TeleMessage 使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-145">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="a5fc1-146">**密碼：** 您的 TeleMessage 密碼。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-146">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="a5fc1-147">建立連接器之後，您可以關閉快顯視窗，然後移至下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-147">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="a5fc1-148">在 [ **使用者對應** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-148">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="a5fc1-149">若要啟用自訂對應，請上傳包含使用者對應資訊的 CSV 檔案，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-149">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="a5fc1-150">請複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-150">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="a5fc1-151">移至 [ **資料連線器** ] 頁面中的 [連接器] 索引標籤，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-151">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a5fc1-152">已知問題</span><span class="sxs-lookup"><span data-stu-id="a5fc1-152">Known issues</span></span>

- <span data-ttu-id="a5fc1-153">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-153">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="a5fc1-154">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="a5fc1-154">Support for larger items will be available at a later date.</span></span>