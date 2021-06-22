---
title: 設定連接器以在 Microsoft 365 中封存信號通訊資料
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
description: 系統管理員可以設定 TeleMessage 連接器，以匯入和封存 Microsoft 365 中的信號通訊資料。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，這樣您就可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: a779cb312e20fdf5fac0987a33734e7e81ba9c74
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054826"
---
# <a name="set-up-a-connector-to-archive-signal-communications-data-preview"></a><span data-ttu-id="0e8e3-104">設定連接器以封存信號通訊資料 (預覽) </span><span class="sxs-lookup"><span data-stu-id="0e8e3-104">Set up a connector to archive Signal communications data (preview)</span></span>

<span data-ttu-id="0e8e3-105">使用 Microsoft 365 合規性中心中的 TeleMessage 連接器，可匯入及封存信號聊天、附件、檔案及已刪除的郵件和通話。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive Signal chats, attachments, files, and deleted messages and calls.</span></span> <span data-ttu-id="0e8e3-106">在您設定及設定連接器之後，它會連線到您組織的 TeleMessage 帳戶，並將使用 TeleMessage 信號歸檔器的員工行動通訊，匯入至 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-106">After you set up and configure a connector, it connects to your organization's TeleMessage account, and imports the mobile communication of employees using the TeleMessage Signal Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="0e8e3-107">在將信號歸檔檔連接器資料儲存在使用者信箱之後，您就可以套用 Microsoft 365 合規性功能，例如訴訟暫止、內容搜尋，以及 Microsoft 365 保留原則，以通知通訊資料。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-107">After Signal Archiver connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content search, and Microsoft 365 retention policies to Signal communications data.</span></span> <span data-ttu-id="0e8e3-108">例如，您可以使用內容搜尋來搜尋信號通訊，或在 Advanced eDiscovery 案例中，將包含「傳輸」資料記錄的信箱，與系統管理員相關聯。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-108">For example, you can search Signal communication using Content search or associate the mailbox that contains the Signal Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="0e8e3-109">使用信號歸檔器連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守公司控管管理法規和法規原則。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-109">Using a Signal Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with corporate governance regulations and regulatory policies.</span></span>

## <a name="overview-of-archiving-signal-communications-data"></a><span data-ttu-id="0e8e3-110">封存信號通訊資料的概述</span><span class="sxs-lookup"><span data-stu-id="0e8e3-110">Overview of archiving Signal communications data</span></span>

<span data-ttu-id="0e8e3-111">下列概要說明如何使用連接器來封存 Microsoft 365 中的信號通訊資料。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-111">The following overview explains the process of using a connector to archive  Signal communication data in Microsoft 365.</span></span>

![信號通訊封存工作流程](../media/SignalConnectorWorkflow.png)

1. <span data-ttu-id="0e8e3-113">您的組織與 TeleMessage 搭配使用，以設定信號歸檔器連接器。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-113">Your organization works with TeleMessage to set up a Signal Archiver connector.</span></span> <span data-ttu-id="0e8e3-114">如需詳細資訊，請參閱[啟用 Microsoft 365 的 TeleMessage 信號歸檔](https://www.telemessage.com/microsoft-365-activation-for-signal-archiver/)器。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-114">For more information, see [Activating the TeleMessage Signal Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-signal-archiver/).</span></span>

2. <span data-ttu-id="0e8e3-115">您的組織的信號資料會即時複製到 TeleMessage 網站。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-115">In real time, your organization's Signal data is copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="0e8e3-116">您在 Microsoft 365 合規性中心中建立的信號歸檔區連接器每天會連線至 TeleMessage 網站，並將電子郵件訊息從過去24小時內傳送至 Microsoft 雲端中的安全 Azure 儲存體區域。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-116">The Signal Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

4. <span data-ttu-id="0e8e3-117">連接器會將行動通訊專案匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-117">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="0e8e3-118">會在特定使用者的信箱中建立名為「信號」的新資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-118">A new folder named Signal Archiver will be created in the specific user's mailbox and the items will be imported to it.</span></span> <span data-ttu-id="0e8e3-119">連接器會使用 *使用者的電子郵件地址* 屬性值來進行對應。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-119">The connector does the mapping by using the value of the *User's Email address* property.</span></span> <span data-ttu-id="0e8e3-120">每封電子郵件都包含此內容，該屬性會填入電子郵件的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-120">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span>

> <span data-ttu-id="0e8e3-121">除了使用 *使用者之電子郵件地址* 屬性值的自動使用者對應，您也可以透過上載 CSV 對應檔來定義自訂對應。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-121">In addition to automatic user mapping using the value of the *User's Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="0e8e3-122">這個對應檔案應該包含使用者的行動電話號碼，以及每位使用者對應的 Microsoft 365 信箱位址。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-122">This mapping file should contain User's mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="0e8e3-123">如果您啟用自動使用者對應，並提供自訂對應，則每個電子郵件專案連接器都會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-123">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="0e8e3-124">如果找不到有效的 Microsoft 365 使用者與使用者的行動電話號碼對應，連接器會使用該電子郵件專案的使用者電子郵件地址屬性。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-124">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="0e8e3-125">如果連接器沒有在自訂對應檔案或電子郵件專案的 *使用者電子郵件地址* 屬性中找到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-125">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user's email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="0e8e3-126">在您設定連接器之前</span><span class="sxs-lookup"><span data-stu-id="0e8e3-126">Before you set up a connector</span></span>

- <span data-ttu-id="0e8e3-127">[從 TeleMessage 排序信號歸檔服務](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)，並取得組織的有效管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-127">Order the [Signal Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization.</span></span> <span data-ttu-id="0e8e3-128">當您在規範中心建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-128">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="0e8e3-129">在 TeleMessage 帳戶中，註冊所有需要信號封存的使用者。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-129">Register all users that require Signal archiving in the TeleMessage account.</span></span> <span data-ttu-id="0e8e3-130">註冊使用者時，請務必使用與其 Microsoft 365 帳戶相同的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-130">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="0e8e3-131">在您員工的行動電話上安裝信號歸檔器應用程式，並加以啟動。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-131">Install the Signal Archiver app on the mobile phones of your employees and activate it.</span></span> <span data-ttu-id="0e8e3-132">「信號探索」應用程式可讓他們與其他信號使用者通訊和聊天。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-132">The Signal Archiver app allows them to communicate and chat with other Signal users.</span></span>

- <span data-ttu-id="0e8e3-133">在步驟3中建立信號歸檔器連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-133">The user who creates a Signal Archiver connector in Step 3 must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="0e8e3-134">在 Microsoft 365 合規性中心的 [**資料連線器**] 頁面中新增連接器時，這是必要的。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-134">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0e8e3-135">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-135">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="0e8e3-136">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-136">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="0e8e3-137">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-137">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="0e8e3-138">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-138">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-signal-archiver-connector"></a><span data-ttu-id="0e8e3-139">建立信號歸檔器連接器</span><span class="sxs-lookup"><span data-stu-id="0e8e3-139">Create a Signal Archiver connector</span></span>

<span data-ttu-id="0e8e3-140">在您完成上一節所述的必要條件後，您就可以在 Microsoft 365 合規性中心中建立信號歸檔器連接器。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-140">After you've completed the prerequisites described in the previous section, you can create the Signal Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0e8e3-141">連接器會使用您提供的資訊來連線至 TeleMessage 網站，並將信號通訊資料傳送至 Microsoft 365 中對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-141">The connector uses the information you provide to connect to the TeleMessage site and transfers Signal communications data to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="0e8e3-142">移至 <https://compliance.microsoft.com> ，然後按一下 [**資料連線器**] [  >  **信號歸檔** 器]。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-142">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Signal Archiver**.</span></span>

2. <span data-ttu-id="0e8e3-143">在 [ **信號歸檔** 器產品描述] 頁面上，按一下 [ **新增連接器]。**</span><span class="sxs-lookup"><span data-stu-id="0e8e3-143">On the **Signal Archiver** product description page, click **Add connector.**</span></span>

3. <span data-ttu-id="0e8e3-144">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="0e8e3-145">在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-145">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

    - <span data-ttu-id="0e8e3-146">使用者 **名稱：** 您的 TeleMessage 使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-146">**Username:** Your TeleMessage username.</span></span>

    - <span data-ttu-id="0e8e3-147">**密碼：** 您的 TeleMessage 密碼。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-147">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="0e8e3-148">建立連接器之後，您可以關閉快顯視窗，然後移至下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-148">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="0e8e3-149">在 [ **使用者對應** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-149">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="0e8e3-150">若要啟用自訂對應，請上傳包含使用者對應資訊的 CSV 檔案，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-150">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="0e8e3-151">請複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-151">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="0e8e3-152">移至 [ **資料連線器** ] 頁面中的 [連接器] 索引標籤，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-152">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0e8e3-153">已知問題</span><span class="sxs-lookup"><span data-stu-id="0e8e3-153">Known issues</span></span>

- <span data-ttu-id="0e8e3-154">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-154">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="0e8e3-155">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="0e8e3-155">Support for larger items will be available at a later date.</span></span>
