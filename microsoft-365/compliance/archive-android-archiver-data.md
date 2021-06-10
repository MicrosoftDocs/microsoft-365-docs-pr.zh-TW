---
title: 設定連接器以封存 Android 行動電話資料
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
description: 系統管理員可以設定 TeleMessage 連接器，以匯入和封存來自 Android 行動電話的簡訊、MMS 及語音通話。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，這樣您就可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 6a70d57c5728b5e69df09a523f865d7e8beb8130
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822223"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a><span data-ttu-id="fe945-104">設定連接器以封存 Android 行動電話資料</span><span class="sxs-lookup"><span data-stu-id="fe945-104">Set up a connector to archive Android mobile data</span></span>

<span data-ttu-id="fe945-105">使用 Microsoft 365 規範中心內的 TeleMessage 連接器，匯入及封存來自 Android 行動電話的簡訊、MMS、語音通話及通話記錄。</span><span class="sxs-lookup"><span data-stu-id="fe945-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive SMS, MMS, voice calls, and call logs from Android mobile phones.</span></span> <span data-ttu-id="fe945-106">在您設定及設定連接器之後，它每天會連線到您組織的 TeleMessage 帳戶，並將使用 TeleMessage Android 歸檔人員在 Microsoft 365 中的信箱，匯入員工的移動通訊。</span><span class="sxs-lookup"><span data-stu-id="fe945-106">After you set up and configure a connector, it connects to your organization's TeleMessage account once every day, and imports the mobile communication of employees using the TeleMessage Android Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="fe945-107">當 android 行動電話中的資料儲存在使用者信箱之後，您就可以將 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋）和 Microsoft 365 保留原則套用至 android 歸檔資料。</span><span class="sxs-lookup"><span data-stu-id="fe945-107">After data from Android mobile phones is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to Android Archiver data.</span></span> <span data-ttu-id="fe945-108">例如，您可以使用內容搜尋來搜尋 android 記錄器行動通訊，或在 Advanced eDiscovery 案例中，將包含 Android 歸檔程式資料的信箱與保管人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="fe945-108">For example, you can search Android Archiver mobile communication using Content Search or associate the mailbox that contains the Android Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="fe945-109">使用 Android 歸檔連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="fe945-109">Using an Android Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-android-mobile-data"></a><span data-ttu-id="fe945-110">Android mobile 資料封存簡介</span><span class="sxs-lookup"><span data-stu-id="fe945-110">Overview of archiving Android mobile data</span></span>

<span data-ttu-id="fe945-111">下列概要說明如何使用連接器封存 Microsoft 365 中的 Android mobile 資料。</span><span class="sxs-lookup"><span data-stu-id="fe945-111">The following overview explains the process of using a connector to archive Android mobile data in Microsoft 365.</span></span>

![Android 歸檔器連接器工作流程](../media/AndroidArchiverConnectorWorkflow.png)

1. <span data-ttu-id="fe945-113">您的組織與 TeleMessage 搭配使用，以設定 Android 的歸檔連接器。</span><span class="sxs-lookup"><span data-stu-id="fe945-113">Your organization works with TeleMessage to set up an Android Archiver connector.</span></span> <span data-ttu-id="fe945-114">如需詳細資訊，請參閱 [Android 歸檔](https://www.telemessage.com/office365-activation-for-android-archiver/)程式。</span><span class="sxs-lookup"><span data-stu-id="fe945-114">For more information, see [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).</span></span>

2. <span data-ttu-id="fe945-115">從組織的 Android 行動電話中即時、簡訊、MMS、語音通話及通話記錄會複製到 TeleMessage 網站。</span><span class="sxs-lookup"><span data-stu-id="fe945-115">In real time, SMS, MMS, voice calls, and call logs from your organization's Android mobile phones are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="fe945-116">您在 Microsoft 365 合規性中心建立的 Android 歸檔連接器會每天連線到 TeleMessage 網站，並將以前24小時的 android 資料傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="fe945-116">The Android Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the Android data from the previous 24 hours to a secure Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="fe945-117">連接器也會將 Android 資料轉換成電子郵件格式。</span><span class="sxs-lookup"><span data-stu-id="fe945-117">The connector also converts the Android data to an email message format.</span></span>

4. <span data-ttu-id="fe945-118">連接器會將行動通訊專案匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="fe945-118">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="fe945-119">在特定使用者的信箱中建立名為 Android 建立器的新資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="fe945-119">A new folder named Android Archiver is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="fe945-120">連接器會使用 *使用者的電子郵件地址* 屬性值進行對應。</span><span class="sxs-lookup"><span data-stu-id="fe945-120">The connector does mapping by using the value of the *User's Email address* property.</span></span> <span data-ttu-id="fe945-121">每封電子郵件都包含此內容，該屬性會填入電子郵件的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="fe945-121">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="fe945-122">除了使用 *使用者之電子郵件地址* 屬性值的自動使用者對應，您也可以透過上載 CSV 對應檔來定義自訂對應。</span><span class="sxs-lookup"><span data-stu-id="fe945-122">In addition to automatic user mapping using the value of the *User's Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="fe945-123">這個對應檔案應該包含每位使用者的行動電話號碼和對應的 Microsoft 365 信箱位址。</span><span class="sxs-lookup"><span data-stu-id="fe945-123">This mapping file should contain the mobile number and corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="fe945-124">如果您啟用自動使用者對應，並提供自訂對應，則每個電子郵件專案連接器都會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="fe945-124">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="fe945-125">如果找不到有效的 Microsoft 365 使用者與使用者的行動電話號碼對應，連接器會使用該電子郵件專案的使用者電子郵件地址屬性。</span><span class="sxs-lookup"><span data-stu-id="fe945-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the user's email address property of the email item.</span></span> <span data-ttu-id="fe945-126">如果連接器沒有在自訂對應檔案或電子郵件專案的 *使用者電子郵件地址* 屬性中找到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="fe945-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *User's email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="fe945-127">在您設定連接器之前</span><span class="sxs-lookup"><span data-stu-id="fe945-127">Before you set up a connector</span></span>

<span data-ttu-id="fe945-128">封存 Android 通訊資料所需的部分執行步驟是 Microsoft 365 外部的，必須先完成，您才能在規範中心建立連接器。</span><span class="sxs-lookup"><span data-stu-id="fe945-128">Some of the implementation steps required to archive Android communication data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="fe945-129">[從 TeleMessage 訂購 Android 歸檔服務](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)，並取得組織的有效管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="fe945-129">Order the [Android Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="fe945-130">您必須在建立連接器時登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="fe945-130">You'll need to sign into this account when you create the connector.</span></span>

- <span data-ttu-id="fe945-131">在 TeleMessage 帳戶中，註冊所有需要 Android 歸檔服務的使用者。</span><span class="sxs-lookup"><span data-stu-id="fe945-131">Register all users that require the Android Archiver service in the TeleMessage account.</span></span> <span data-ttu-id="fe945-132">註冊使用者時，請務必使用與其 Microsoft 365 帳戶相同的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="fe945-132">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="fe945-133">在您員工的行動電話上安裝及啟用 TeleMessage Android 歸檔應用程式。</span><span class="sxs-lookup"><span data-stu-id="fe945-133">Install and activate the TeleMessage Android Archiver app on the mobile phones of your employees.</span></span>

- <span data-ttu-id="fe945-134">在 Exchange Online 中，必須為建立 Android 歸檔連接器的使用者指派「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="fe945-134">The user who creates a Android Archiver connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fe945-135">在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面中新增連接器時，這是必要的。</span><span class="sxs-lookup"><span data-stu-id="fe945-135">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fe945-136">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="fe945-136">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="fe945-137">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="fe945-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fe945-138">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="fe945-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fe945-139">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="fe945-139">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="fe945-140">您可以在 Microsoft 365 美國政府雲端的 GCC 環境中使用此資料連線器。</span><span class="sxs-lookup"><span data-stu-id="fe945-140">This data connector is available in GCC environments in the Microsoft 365 US Government cloud.</span></span> <span data-ttu-id="fe945-141">協力廠商應用程式和服務可能會涉及在 Microsoft 365 基礎結構以外的協力廠商系統上儲存、傳送和處理組織的客戶資料，因此不會受到 Microsoft 365 法規遵從性和資料保護承諾。</span><span class="sxs-lookup"><span data-stu-id="fe945-141">Third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Microsoft 365 infrastructure and therefore are not covered by the Microsoft 365 compliance and data protection commitments.</span></span> <span data-ttu-id="fe945-142">Microsoft 沒有任何表示使用此產品連接至協力廠商應用程式，表示協力廠商應用程式 FEDRAMP 相容性。</span><span class="sxs-lookup"><span data-stu-id="fe945-142">Microsoft makes no representation that use of this product to connect to third-party applications implies that those third-party applications are FEDRAMP compliant.</span></span>

## <a name="create-an-android-archiver-connector"></a><span data-ttu-id="fe945-143">建立 Android 歸檔連接器</span><span class="sxs-lookup"><span data-stu-id="fe945-143">Create an Android Archiver connector</span></span>

<span data-ttu-id="fe945-144">最後一個步驟是在 Microsoft 365 規範中心建立 Android 歸檔連接器。</span><span class="sxs-lookup"><span data-stu-id="fe945-144">The last step is to create an Android Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fe945-145">連接器會使用您提供的資訊來連線至 TeleMessage 網站，並在 Microsoft 365 中將 Android 通訊轉移至對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="fe945-145">The connector uses the information you provide to connect to the TeleMessage site and transfer Android communication to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="fe945-146">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下 [**資料連線器**  >  **Android 歸檔** 器]。</span><span class="sxs-lookup"><span data-stu-id="fe945-146">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** > **Android Archiver**.</span></span>

2. <span data-ttu-id="fe945-147">在 [ **Android 歸檔** 器產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="fe945-147">On the **Android Archiver** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="fe945-148">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="fe945-148">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fe945-149">在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fe945-149">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="fe945-150">使用者 **名稱：** 您的 TeleMessage 使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="fe945-150">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="fe945-151">**密碼：** 您的 TeleMessage 密碼。</span><span class="sxs-lookup"><span data-stu-id="fe945-151">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="fe945-152">建立連接器之後，關閉快顯視窗，然後按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="fe945-152">After the connector is created, close the pop-up window and click **Next**.</span></span>

6. <span data-ttu-id="fe945-153">在 [ **使用者對應** ] 頁面上啟用 [自動使用者對應]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fe945-153">On the **User mapping** page, enable automatic user mapping and click **Next**.</span></span> <span data-ttu-id="fe945-154">如果您需要自訂對應，請上載 CSV 檔案，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fe945-154">In case you need custom mapping upload a CSV file, and click **Next**.</span></span>

7. <span data-ttu-id="fe945-155">請複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="fe945-155">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="fe945-156">移至 [ **資料連線器** ] 頁面中的 [連接器] 索引標籤，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="fe945-156">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fe945-157">已知問題</span><span class="sxs-lookup"><span data-stu-id="fe945-157">Known issues</span></span>

- <span data-ttu-id="fe945-158">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="fe945-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="fe945-159">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="fe945-159">Support for larger items will be available at a later date.</span></span>
