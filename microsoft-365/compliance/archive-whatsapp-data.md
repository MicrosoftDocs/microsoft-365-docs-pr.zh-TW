---
title: 設定連接器以封存 Microsoft 365 中的 WhatsApp 資料
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
description: 系統管理員可以設定 TeleMessage 連接器，以匯入和封存 Microsoft 365 中的 WhatsApp 資料。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 573316f262295cce417876ef77510da14b877c67
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620179"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a><span data-ttu-id="08d99-104">設定連接器以封存 WhatsApp 資料</span><span class="sxs-lookup"><span data-stu-id="08d99-104">Set up a connector to archive WhatsApp data</span></span>

<span data-ttu-id="08d99-105">使用 Microsoft 365 規範中心內的 TeleMessage 連接器，匯入及封存 WhatsApp 通話、聊天、附件、檔案及已刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="08d99-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive WhatsApp calls, chats, attachments, files, and deleted messages.</span></span> <span data-ttu-id="08d99-106">在您設定及設定連接器之後，它每天會連線到您組織的 TeleMessage 帳戶，並將使用 TeleMessage WhatsApp Phone 歸檔器或 TeleMessage WhatsApp 雲端歸檔人員的員工行動通訊，匯入至 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="08d99-106">After you set up and configure a connector, it connects to your organization's TeleMessage account once every day, and imports the mobile communication of employees using the TeleMessage WhatsApp Phone Archiver or TeleMessage WhatsApp Cloud Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="08d99-107">將 WhatsApp 資料儲存在使用者信箱之後，您可以套用 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋）和 Microsoft 365 保留原則，以 WhatsApp 資料。</span><span class="sxs-lookup"><span data-stu-id="08d99-107">After WhatsApp data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to WhatsApp data.</span></span> <span data-ttu-id="08d99-108">例如，您可以使用內容搜尋來搜尋 WhatsApp 郵件，或在高級 eDiscovery 案例中，將包含 WhatsApp 郵件的信箱與保管人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="08d99-108">For example, you can search WhatsApp messages using Content Search or associate the mailbox that contains WhatsApp messages with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="08d99-109">在 Microsoft 365 中使用 WhatsApp 連接器匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="08d99-109">Using a WhatsApp connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-whatsapp-data"></a><span data-ttu-id="08d99-110">封存 WhatsApp 資料一覽</span><span class="sxs-lookup"><span data-stu-id="08d99-110">Overview of archiving WhatsApp data</span></span>

<span data-ttu-id="08d99-111">下列概要說明如何使用連接器封存 Microsoft 365 中的 WhatsApp 資料。</span><span class="sxs-lookup"><span data-stu-id="08d99-111">The following overview explains the process of using a connector to archive WhatsApp data in Microsoft 365.</span></span>

![WhatsApp 封存工作流程](../media/WhatsAppConnectorWorkflow.png)

1. <span data-ttu-id="08d99-113">您的組織與 TeleMessage 搭配使用，以設定 WhatsApp 的歸檔器連接器。</span><span class="sxs-lookup"><span data-stu-id="08d99-113">Your organization works with TeleMessage to set up a WhatsApp Archiver connector.</span></span> <span data-ttu-id="08d99-114">如需詳細資訊，請參閱 [WhatsApp 歸檔](https://www.telemessage.com/office365-activation-for-whatsapp-archiver)器。</span><span class="sxs-lookup"><span data-stu-id="08d99-114">For more information, see [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).</span></span>

2. <span data-ttu-id="08d99-115">每24小時一次，您組織的 WhatsApp 資料會複製到 TeleMessage 網站。</span><span class="sxs-lookup"><span data-stu-id="08d99-115">Once every 24 hours, your organization’s WhatsApp data is copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="08d99-116">您在 Microsoft 365 合規性中心建立的 WhatsApp 連接器每天會連線至 TeleMessage 網站，並將 WhatsApp 資料從前24小時傳輸至 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="08d99-116">The WhatsApp connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers WhatsApp data from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="08d99-117">連接器也會將內容 WhatsApp 資料轉換成電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="08d99-117">The connector also converts the content WhatsApp data to an email message format.</span></span>

4. <span data-ttu-id="08d99-118">連接器會將 WhatsApp 資料匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="08d99-118">The connector imports WhatsApp data to the mailbox of a specific user.</span></span> <span data-ttu-id="08d99-119">在特定使用者的信箱中建立名為 **WhatsApp** 的新資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="08d99-119">A new folder named **WhatsApp Archiver** is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="08d99-120">連接器會使用 *使用者的電子郵件地址* 屬性值來進行對應。</span><span class="sxs-lookup"><span data-stu-id="08d99-120">The connector does this mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="08d99-121">每個 WhatsApp 郵件都包含此內容，該屬性會填入郵件每一位參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="08d99-121">Every WhatsApp message contains this property, which is populated with the email address of every participant of the message.</span></span>

   <span data-ttu-id="08d99-122">除了使用 *使用者的電子郵件地址* 屬性值進行自動使用者對應之外，您也可以透過上載 CSV 對應檔來執行自訂對應。</span><span class="sxs-lookup"><span data-stu-id="08d99-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also implement custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="08d99-123">此對應檔包含組織中使用者的行動電話號碼和對應的 Microsoft 365 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="08d99-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="08d99-124">如果您為每個 WhatsApp 專案啟用自動使用者對應及自訂對應，連接器會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="08d99-124">If you enable both automatic user mapping and custom mapping, for every WhatsApp item the connector first looks at custom mapping file.</span></span> <span data-ttu-id="08d99-125">如果找不到對應至使用者行動電話號碼的有效 Microsoft 365 使用者，連接器會使用嘗試匯入之專案的電子郵件地址屬性值。</span><span class="sxs-lookup"><span data-stu-id="08d99-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile phone number, the connector will use the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="08d99-126">如果連接器在自訂對應檔案或 WhatsApp 專案的電子郵件地址屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="08d99-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the WhatsApp item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="08d99-127">開始之前</span><span class="sxs-lookup"><span data-stu-id="08d99-127">Before you begin</span></span>

<span data-ttu-id="08d99-128">封存 WhatsApp 通訊資料所需的部分執行步驟是 Microsoft 365 的外部，必須先完成，您才能在規範中心建立連接器。</span><span class="sxs-lookup"><span data-stu-id="08d99-128">Some of the implementation steps required to archive WhatsApp communication data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="08d99-129">[從 TeleMessage 定購 WhatsApp 歸檔服務](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)，並為您的組織取得有效的管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="08d99-129">Order the [WhatsApp Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="08d99-130">當您在規範中心建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="08d99-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="08d99-131">在 TeleMessage 帳戶中，註冊所有需要 WhatsApp 封存的使用者。</span><span class="sxs-lookup"><span data-stu-id="08d99-131">Register all users that require WhatsApp archiving in the TeleMessage account.</span></span> <span data-ttu-id="08d99-132">註冊使用者時，請務必使用與 Microsoft 365 帳戶所用相同的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="08d99-132">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="08d99-133">在您員工的行動電話上安裝 TeleMessage [WhatsApp 電話歸檔器應用程式](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) ，並加以啟動。</span><span class="sxs-lookup"><span data-stu-id="08d99-133">Install the TeleMessage [WhatsApp Phone Archiver app](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) on the mobile phones of your employees and activate it.</span></span> <span data-ttu-id="08d99-134">或者，您也可以在您員工的行動電話上安裝一般 WhatsApp 或 WhatsApp 商務應用程式，並在 TeleMessage 網站上掃描 QR 碼，以啟動 WhatsApp 雲端歸檔服務。</span><span class="sxs-lookup"><span data-stu-id="08d99-134">Alternatively, you can install the regular WhatsApp or WhatsApp Business apps on the mobile phones of your employees and activate the WhatsApp Cloud Archiver service by scanning a QR code on the TeleMessage website.</span></span> <span data-ttu-id="08d99-135">如需詳細資訊，請參閱 [WhatsApp Cloud 存檔](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/)器。</span><span class="sxs-lookup"><span data-stu-id="08d99-135">For more information, see [WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).</span></span>

- <span data-ttu-id="08d99-136">在 Exchange Online 中，必須對建立 Verizon 網路連接器的使用者指派「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="08d99-136">The user who creates a Verizon Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="08d99-137">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面中新增連接器時，這是必要的。</span><span class="sxs-lookup"><span data-stu-id="08d99-137">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="08d99-138">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="08d99-138">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="08d99-139">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="08d99-139">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="08d99-140">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="08d99-140">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="08d99-141">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="08d99-141">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-whatsapp-archiver-connector"></a><span data-ttu-id="08d99-142">建立 WhatsApp 的歸檔器連接器</span><span class="sxs-lookup"><span data-stu-id="08d99-142">Create a WhatsApp Archiver connector</span></span>

<span data-ttu-id="08d99-143">在您完成上一節所述的必要條件之後，您可以在 Microsoft 365 規範中心建立 WhatsApp 連接器。</span><span class="sxs-lookup"><span data-stu-id="08d99-143">After you've completed the prerequisites described in the previous section, you can create the WhatsApp connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="08d99-144">連接器會使用您提供的資訊來連線至 TeleMessage 網站，並將 WhatsApp 資料傳送至 Microsoft 365 中對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="08d99-144">The connector uses the information you provide to connect to the TeleMessage site and transfer the WhatsApp data to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="08d99-145">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **WhatsApp 歸檔** 器]。</span><span class="sxs-lookup"><span data-stu-id="08d99-145">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **WhatsApp Archiver**.</span></span>

2. <span data-ttu-id="08d99-146">在 [ **WhatsApp 歸檔** 器產品描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="08d99-146">On the **WhatsApp Archiver** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="08d99-147">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="08d99-147">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="08d99-148">在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="08d99-148">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="08d99-149">使用者 **名稱：** 您的 TeleMessage 使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="08d99-149">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="08d99-150">**密碼：** 您的 TeleMessage 密碼。</span><span class="sxs-lookup"><span data-stu-id="08d99-150">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="08d99-151">建立連接器之後，您可以關閉快顯視窗，然後移至下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="08d99-151">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="08d99-152">在 [ **使用者對應** ] 頁面上啟用 [自動使用者對應]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="08d99-152">On the **User mapping** page, enable automatic user mapping and click **Next**.</span></span> <span data-ttu-id="08d99-153">如果您需要自訂對應，請上載 CSV 檔案，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="08d99-153">In case you need custom mapping upload a CSV file, and click **Next**.</span></span>

7. <span data-ttu-id="08d99-154">請複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="08d99-154">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="08d99-155">移至 [ **資料連線器** ] 頁面中的 [連接器] 索引標籤，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="08d99-155">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="08d99-156">已知問題</span><span class="sxs-lookup"><span data-stu-id="08d99-156">Known issues</span></span>

- <span data-ttu-id="08d99-157">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="08d99-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="08d99-158">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="08d99-158">Support for larger items will be available at a later date.</span></span>
