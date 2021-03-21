---
title: 設定在&T SMS/MMS 網路資料時封存的連接器
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
description: 系統管理員可以設定 TeleMessage 連接器，以匯入及封存來自&T 行動電話的 SMS 和 MMS 資料。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: b17591b98236ef54f1d1f2cc454653d51f1fae32
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919961"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data"></a><span data-ttu-id="04459-104">設定在&T SMS/MMS 資料時封存的連接器</span><span class="sxs-lookup"><span data-stu-id="04459-104">Set up a connector to archive AT&T SMS/MMS data</span></span>

<span data-ttu-id="04459-105">使用 Microsoft 365 規範中心的 TeleMessage 連接器，從&T 行動電話匯入並封存 SMS 和 MMS 資料。</span><span class="sxs-lookup"><span data-stu-id="04459-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive SMS and MMS data from AT&T Mobile Network.</span></span> <span data-ttu-id="04459-106">在您設定及設定連接器之後，它每天會連線到您的組織&T 網路一次，並將 SMS 和 MMS 資料匯入 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="04459-106">After you set up and configure a connector, it connects to your organization's AT&T Network once every day, and imports SMS and MMS data to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="04459-107">在將 SMS 和 MMS 郵件儲存在使用者信箱之後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋）和 Microsoft 365 保留原則套用至&T 網路資料。</span><span class="sxs-lookup"><span data-stu-id="04459-107">After SMS and MMS messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to AT&T Network data.</span></span> <span data-ttu-id="04459-108">例如，您可以使用內容搜尋來搜尋&T 網路資料，或在高級 eDiscovery 案例中，將包含&T 網路連接器資料的信箱與保管人建立關聯。</span><span class="sxs-lookup"><span data-stu-id="04459-108">For example, you can search AT&T Network data using Content Search or associate the mailbox that contains the AT&T Network connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="04459-109">在 Microsoft 365 中使用 AT&T 網路連接器匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="04459-109">Using a AT&T Network connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-att-network-data"></a><span data-ttu-id="04459-110">在&T 網路資料中封存的概覽</span><span class="sxs-lookup"><span data-stu-id="04459-110">Overview of archiving AT&T Network data</span></span>

<span data-ttu-id="04459-111">下列概要說明如何使用連接器封存 Microsoft 365 中&T 網路資料。</span><span class="sxs-lookup"><span data-stu-id="04459-111">The following overview explains the process of using a connector to archive AT&T Network data in Microsoft 365.</span></span>

![ATT 網路封存工作流程](../media/ATTNetworkConnectorWorkflow.png)

1. <span data-ttu-id="04459-113">您的組織與 TeleMessage 搭配使用，以設定&T 網路連接器。</span><span class="sxs-lookup"><span data-stu-id="04459-113">Your organization works with TeleMessage to set up an AT&T Network connector.</span></span> <span data-ttu-id="04459-114">如需詳細資訊，請參閱 [&T 網路存檔](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/)器。</span><span class="sxs-lookup"><span data-stu-id="04459-114">For information, see [AT&T Network Archiver](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/).</span></span>

2. <span data-ttu-id="04459-115">每24小時一次，來自組織之&T 網路的 SMS 和 MMS 郵件會複製到 TeleMessage 網站。</span><span class="sxs-lookup"><span data-stu-id="04459-115">Once every 24 hours, SMS and MMS messages from your organization’s AT&T Network are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="04459-116">您在 Microsoft 365 合規性中心建立的 AT&T 網路連接器每天會連線至 TeleMessage 網站，並將 SMS 和 MMS 郵件從過去24小時傳送至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="04459-116">The AT&T Network connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the SMS and MMS messages from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="04459-117">連接器也會將 SMS 和 MMS 郵件的內容轉換成電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="04459-117">The connector also converts the content of SMS and MMS messages to an email message format.</span></span>

4. <span data-ttu-id="04459-118">連接器會將行動通訊專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="04459-118">The connector imports the mobile communication items to the mailbox of specific users.</span></span> <span data-ttu-id="04459-119">在使用者的信箱中，會建立名為 **&T SMS/MMS 網路** 上的新資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="04459-119">A new folder named **AT&T SMS/MMS Network Archiver** is created in the user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="04459-120">連接器會使用 *使用者的電子郵件地址* 屬性值來進行對應。</span><span class="sxs-lookup"><span data-stu-id="04459-120">The connector does this mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="04459-121">每個 SMS 和彩信都包含此內容，該屬性會填入郵件的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="04459-121">Every SMS and MMS message contains this property, which is populated with the email address of every participant of the message.</span></span>
 
   <span data-ttu-id="04459-122">除了使用 *使用者之電子郵件地址* 屬性值的自動使用者對應，您也可以透過上載 CSV 對應檔來定義自訂對應。</span><span class="sxs-lookup"><span data-stu-id="04459-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="04459-123">此對應檔包含組織中使用者的行動電話號碼和對應的 Microsoft 365 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="04459-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="04459-124">如果您同時啟用自動使用者對應及自訂對應，連接器會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="04459-124">If you enable both automatic user mapping and custom mapping, for every email item the connector first looks at the custom mapping file.</span></span> <span data-ttu-id="04459-125">如果找不到與行動電話號碼對應的有效 Microsoft 365 使用者，連接器會使用嘗試匯入之專案的電子郵件地址屬性值。</span><span class="sxs-lookup"><span data-stu-id="04459-125">If it doesn't find a valid Microsoft 365 user that corresponds to a mobile phone number, the connector uses the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="04459-126">如果連接器在自訂對應檔案中或電子郵件專案的電子郵件地址屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="04459-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="04459-127">開始之前</span><span class="sxs-lookup"><span data-stu-id="04459-127">Before you begin</span></span>

<span data-ttu-id="04459-128">在&T 網路資料上封存所需的部分執行步驟是 Microsoft 365 的外部，必須先完成，您才能在規範中心建立連接器。</span><span class="sxs-lookup"><span data-stu-id="04459-128">Some of the implementation steps required to archive AT&T Network data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="04459-129">從 TeleMessage 定購行動性 [歸檔服務](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) ，並為您的組織取得有效的管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="04459-129">Order the [mobile archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization.</span></span> <span data-ttu-id="04459-130">當您在規範中心建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="04459-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="04459-131">在&T 帳戶和計費連絡人詳細資料中取得您的，這樣您就可以在&T 上填滿 TeleMessage 上架表單並排序郵件封存服務。</span><span class="sxs-lookup"><span data-stu-id="04459-131">Obtain your AT&T account and billing contact details so you can fill-out the TeleMessage onboarding forms and order the message archiving service from AT&T.</span></span>

- <span data-ttu-id="04459-132">在 TeleMessage 帳戶中，註冊所有需要&T SMS/MMS 網路封存的使用者。</span><span class="sxs-lookup"><span data-stu-id="04459-132">Register all users that require AT&T SMS/MMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="04459-133">註冊使用者時，請務必使用與 Microsoft 365 帳戶所用相同的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="04459-133">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="04459-134">您的員工在&T 行動電話上必須擁有公司擁有及公司的行動電話。</span><span class="sxs-lookup"><span data-stu-id="04459-134">Your employees must have corporate-owned and corporate-liable mobile phones on the AT&T mobile network.</span></span> <span data-ttu-id="04459-135">在 Microsoft 365 中封存郵件無法供員工擁有，或「帶您自己的裝置 (BYOD) 裝置。</span><span class="sxs-lookup"><span data-stu-id="04459-135">Archiving messages in Microsoft 365 isn't available for employee-owned or "Bring Your Own Devices (BYOD) devices.</span></span>

- <span data-ttu-id="04459-136">在 Exchange Online 中，您必須將信箱匯入匯出角色指派給在&T 網路連接器上建立的使用者。</span><span class="sxs-lookup"><span data-stu-id="04459-136">The user who creates a AT&T Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="04459-137">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面中新增連接器時，這是必要的。</span><span class="sxs-lookup"><span data-stu-id="04459-137">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="04459-138">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="04459-138">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="04459-139">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="04459-139">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="04459-140">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="04459-140">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="04459-141">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="04459-141">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-att-network-connector"></a><span data-ttu-id="04459-142">在&T 網路連接器上建立</span><span class="sxs-lookup"><span data-stu-id="04459-142">Create a AT&T Network connector</span></span>

<span data-ttu-id="04459-143">在您完成上一節所述的必要條件之後，您可以在 Microsoft 365 規範中心內建立「&T 網路連接器」。</span><span class="sxs-lookup"><span data-stu-id="04459-143">After you've completed the prerequisites described in the previous section, you can create an AT&T Network connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="04459-144">連接器會使用您提供的資訊來連線至 TeleMessage 網站，並將 SMS 和 MMS 郵件轉接至 Microsoft 365 中對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="04459-144">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS and MMS messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="04459-145">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**]，然後按一下 [  \  **&T 網路**]。</span><span class="sxs-lookup"><span data-stu-id="04459-145">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \ **AT&T Network**.</span></span>

2. <span data-ttu-id="04459-146">在 [ **&T 網路產品** 描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="04459-146">On the **AT&T Network product** description page, click **Add connector**</span></span>

3. <span data-ttu-id="04459-147">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="04459-147">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="04459-148">在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04459-148">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="04459-149">使用者 **名稱：** 您的 TeleMessage 使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="04459-149">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="04459-150">**密碼：** 您的 TeleMessage 密碼。</span><span class="sxs-lookup"><span data-stu-id="04459-150">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="04459-151">建立連接器之後，您可以關閉快顯視窗，然後移至下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="04459-151">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="04459-152">在 [ **使用者對應** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="04459-152">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="04459-153">若要啟用自訂對應，請上傳包含使用者對應資訊的 CSV 檔案，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04459-153">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="04459-154">請複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="04459-154">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="04459-155">移至「規範中心」的 [**資料連線器**] 頁面上的 [**連接器**] 索引標籤，以查看新連接器的匯入程式的處理進度。</span><span class="sxs-lookup"><span data-stu-id="04459-155">Go to the **Connectors** tab on the **Data connectors** page in the compliance center to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="04459-156">已知問題</span><span class="sxs-lookup"><span data-stu-id="04459-156">Known issues</span></span>

- <span data-ttu-id="04459-157">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="04459-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="04459-158">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="04459-158">Support for larger items will be available at a later date.</span></span>