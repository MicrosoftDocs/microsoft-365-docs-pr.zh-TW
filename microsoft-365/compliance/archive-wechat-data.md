---
title: 設定在 Microsoft 365 中封存 WeChat 資料的連接器
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
description: 在 Microsoft 365 合規性中心中設定和使用連接器，以匯入及封存 Microsoft 365 中的 WeChat 資料。
ms.openlocfilehash: e610b58421c2d84402010c9a5d5ad33ec6da5b04
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054623"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a><span data-ttu-id="99c9a-103">設定連接器以封存 WeChat 資料</span><span class="sxs-lookup"><span data-stu-id="99c9a-103">Set up a connector to archive WeChat data</span></span>

<span data-ttu-id="99c9a-104">使用 Microsoft 365 合規性中心中的 TeleMessage 連接器，匯入及封存 WeChat 和 WeCom 通話、聊天、附件、檔案及已召回的郵件。</span><span class="sxs-lookup"><span data-stu-id="99c9a-104">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive WeChat and WeCom calls, chats, attachments, files, and recalled messages.</span></span> <span data-ttu-id="99c9a-105">在您設定及設定連接器之後，它會連線到您組織的 TeleMessage 帳戶，並使用 TeleMessage WeChat 歸檔人員，匯入 Microsoft 365 中信箱的員工行動通訊。</span><span class="sxs-lookup"><span data-stu-id="99c9a-105">After you set up and configure a connector, it connects to your organization's TeleMessage account, and imports the mobile communication of employees using the TeleMessage WeChat Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="99c9a-106">WeChat 歸檔器連接器資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、In-Place 封存、審核、通訊相容性，以及 Microsoft 365 保留原則，以 WeChat 通訊資料。</span><span class="sxs-lookup"><span data-stu-id="99c9a-106">After WeChat Archiver connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to WeChat communication data.</span></span> <span data-ttu-id="99c9a-107">例如，您可以使用內容搜尋來搜尋 WeChat 通訊，或將包含 WeChat 歸檔程式資料的信箱與 Advanced eDiscovery 案例中的保管人相關聯。</span><span class="sxs-lookup"><span data-stu-id="99c9a-107">For example, you can search WeChat communication using Content Search or associate the mailbox that contains the WeChat Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="99c9a-108">在 Microsoft 365 中使用 WeChat 的「歸檔器連接器」匯入和封存資料，可協助您的組織遵守公司控管管理法規和法規原則。</span><span class="sxs-lookup"><span data-stu-id="99c9a-108">Using a WeChat Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with corporate governance regulations and regulatory policies.</span></span>

## <a name="overview-of-archiving-wechat-communication-data"></a><span data-ttu-id="99c9a-109">封存 WeChat 通訊資料的概覽</span><span class="sxs-lookup"><span data-stu-id="99c9a-109">Overview of archiving WeChat communication data</span></span>

<span data-ttu-id="99c9a-110">下列概要說明如何使用連接器封存 Microsoft 365 中 WeChat 通訊資料的處理常式。</span><span class="sxs-lookup"><span data-stu-id="99c9a-110">The following overview explains the process of using a connector to archive WeChat communications data in Microsoft 365.</span></span>

![WeChat 歸檔器資料的封存工作流程](../media/WeChatConnectorWorkflow.png)

1. <span data-ttu-id="99c9a-112">您的組織與 TeleMessage 搭配使用，以設定 WeChat 的歸檔器連接器。</span><span class="sxs-lookup"><span data-stu-id="99c9a-112">Your organization works with TeleMessage to set up a WeChat Archiver connector.</span></span>

2. <span data-ttu-id="99c9a-113">您的組織的 WeChat 資料是即時複製到 TeleMessage 網站。</span><span class="sxs-lookup"><span data-stu-id="99c9a-113">In real time, your organization's WeChat data is copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="99c9a-114">您在 Microsoft 365 合規性中心中建立的 WeChat 歸檔區連接器每天都會連線到 TeleMessage 網站，並將電子郵件訊息從過去24小時內傳送至 Microsoft 雲端中的安全 Azure 儲存體區域。</span><span class="sxs-lookup"><span data-stu-id="99c9a-114">The WeChat Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

4. <span data-ttu-id="99c9a-115">連接器會將行動通訊專案匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="99c9a-115">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="99c9a-116">會在特定使用者的信箱中建立名為 WeChat 的歸檔檔，並將這些專案匯入其中。</span><span class="sxs-lookup"><span data-stu-id="99c9a-116">A new folder named WeChat Archiver will be created in the specific user's mailbox and the items will be imported to it.</span></span> <span data-ttu-id="99c9a-117">連接器會使用 *使用者的電子郵件地址* 屬性值進行對應。</span><span class="sxs-lookup"><span data-stu-id="99c9a-117">The connector does mapping by using the value of the *User's Email address* property.</span></span> <span data-ttu-id="99c9a-118">每封電子郵件都包含此內容，該屬性會填入電子郵件的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="99c9a-118">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="99c9a-119">除了使用 *使用者之電子郵件地址* 屬性值的自動使用者對應，您也可以透過上載 CSV 對應檔來定義自訂對應。</span><span class="sxs-lookup"><span data-stu-id="99c9a-119">In addition to automatic user mapping using the value of the *User's Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="99c9a-120">這個對應檔案應該包含使用者的行動電話號碼，以及每位使用者對應的 Microsoft 365 信箱位址。</span><span class="sxs-lookup"><span data-stu-id="99c9a-120">This mapping file should contain User's mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="99c9a-121">如果您啟用自動使用者對應，並提供自訂對應，則每個電子郵件專案連接器都會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="99c9a-121">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="99c9a-122">如果找不到有效的 Microsoft 365 使用者與使用者的行動電話號碼對應，連接器會使用該電子郵件專案的使用者電子郵件地址屬性。</span><span class="sxs-lookup"><span data-stu-id="99c9a-122">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="99c9a-123">如果連接器沒有在自訂對應檔案或電子郵件專案的 *使用者電子郵件地址* 屬性中找到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="99c9a-123">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user's email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="99c9a-124">在您設定連接器之前</span><span class="sxs-lookup"><span data-stu-id="99c9a-124">Before you set up a connector</span></span>

- <span data-ttu-id="99c9a-125">與 TeleMessage 搭配使用，以設定 WeChat 的封存連接器。</span><span class="sxs-lookup"><span data-stu-id="99c9a-125">Work with TeleMessage to set up a WeChat archive connector.</span></span> <span data-ttu-id="99c9a-126">如需詳細資訊，請參閱[啟用 Microsoft 365 的 TeleMessage WeChat 歸檔](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)器。</span><span class="sxs-lookup"><span data-stu-id="99c9a-126">For more information, see [Activating the TeleMessage WeChat Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/).</span></span>

- <span data-ttu-id="99c9a-127">設定 Microsoft 365 的 TeleMessage 連接器，並取得有效的公司管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="99c9a-127">Set up a TeleMessage connector for Microsoft 365 and get a valid company administration account.</span></span> <span data-ttu-id="99c9a-128">如需詳細資訊，請參閱[Order Microsoft 365 Mobile](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)封存。</span><span class="sxs-lookup"><span data-stu-id="99c9a-128">For more information, see [Order Microsoft 365 Mobile Archiving](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/).</span></span>

- <span data-ttu-id="99c9a-129">以使用者 Microsoft 365 帳戶所用的相同電子郵件地址，註冊 TeleMessage 帳戶中需要 WeChat 封存的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="99c9a-129">Register all users that require WeChat archiving in the TeleMessage account with the same email address that is used for the user's Microsoft 365 account.</span></span>

- <span data-ttu-id="99c9a-130">您必須在組織中使用者的行動電話上安裝 Tencent WeCom 應用程式，並加以啟動。</span><span class="sxs-lookup"><span data-stu-id="99c9a-130">You'll need to install the Tencent WeCom app on the mobile phones of users in your organization and activate it.</span></span> <span data-ttu-id="99c9a-131">WeCom 應用程式可讓使用者與其他 WeChat 和 WeCom 使用者通訊和聊天。</span><span class="sxs-lookup"><span data-stu-id="99c9a-131">The WeCom app lets users communicate and chat with other WeChat and WeCom users.</span></span>

- <span data-ttu-id="99c9a-132">在 Microsoft 365 合規性中心中建立 WeChat 的歸檔器連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="99c9a-132">The user who creates a WeChat Archiver connector in the Microsoft 365 compliance center must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="99c9a-133">在 [規範中心] 的 [ **資料連線器** ] 頁面中新增連接器時，這是必要的動作。</span><span class="sxs-lookup"><span data-stu-id="99c9a-133">This is required to add connectors in the **Data connectors** page in the compliance center.</span></span> <span data-ttu-id="99c9a-134">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="99c9a-134">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="99c9a-135">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="99c9a-135">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="99c9a-136">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="99c9a-136">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="99c9a-137">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="99c9a-137">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="99c9a-138">您可以在 Microsoft 365 美國政府雲端的 GCC 環境中使用此資料連線器。</span><span class="sxs-lookup"><span data-stu-id="99c9a-138">This data connector is available in GCC environments in the Microsoft 365 US Government cloud.</span></span> <span data-ttu-id="99c9a-139">協力廠商應用程式和服務可能會涉及在 Microsoft 365 基礎結構以外的協力廠商系統上儲存、傳送和處理組織的客戶資料，因此不會受到 Microsoft 365 法規遵從性和資料保護承諾。</span><span class="sxs-lookup"><span data-stu-id="99c9a-139">Third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Microsoft 365 infrastructure and therefore are not covered by the Microsoft 365 compliance and data protection commitments.</span></span> <span data-ttu-id="99c9a-140">Microsoft 沒有任何表示使用此產品連接至協力廠商應用程式，表示協力廠商應用程式 FEDRAMP 相容性。</span><span class="sxs-lookup"><span data-stu-id="99c9a-140">Microsoft makes no representation that use of this product to connect to third-party applications implies that those third-party applications are FEDRAMP compliant.</span></span>

## <a name="create-a-wechat-archiver-connector"></a><span data-ttu-id="99c9a-141">建立 WeChat 的歸檔器連接器</span><span class="sxs-lookup"><span data-stu-id="99c9a-141">Create a WeChat Archiver connector</span></span>

<span data-ttu-id="99c9a-142">請遵循本節中的步驟，在 Microsoft 365 合規性中心中建立 WeChat 的歸檔器連接器。</span><span class="sxs-lookup"><span data-stu-id="99c9a-142">Follow the steps in this section to create a WeChat Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="99c9a-143">連接器會使用您提供的資訊來連線至 TeleMessage 網站，並將 WeChat 通訊資料傳送至 Microsoft 365 中對應的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="99c9a-143">The connector uses the information you provide to connect to the TeleMessage site and transfer WeChat communications data to the corresponding user mailboxes in Microsoft 365.</span></span>

1. <span data-ttu-id="99c9a-144">移至 <https://compliance.microsoft.com> ，然後按一下 [**資料連線器**]  >  **WeChat 的歸檔** 器。</span><span class="sxs-lookup"><span data-stu-id="99c9a-144">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **WeChat Archiver**.</span></span>

2. <span data-ttu-id="99c9a-145">在 [ **WeChat 歸檔** 器產品描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="99c9a-145">On the **WeChat Archiver** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="99c9a-146">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="99c9a-146">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="99c9a-147">在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="99c9a-147">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

    - <span data-ttu-id="99c9a-148">**Username**：您的 TeleMessage 使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="99c9a-148">**Username**: Your TeleMessage user name.</span></span>

    - <span data-ttu-id="99c9a-149">**密碼**：您的 TeleMessage 密碼。</span><span class="sxs-lookup"><span data-stu-id="99c9a-149">**Password**: Your TeleMessage password.</span></span>

5. <span data-ttu-id="99c9a-150">建立連接器之後，您可以關閉快顯視窗，移至下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="99c9a-150">After the connector is created, you can close the pop-up window go to the next page.</span></span>

6. <span data-ttu-id="99c9a-151">在 [ **使用者對應** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="99c9a-151">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="99c9a-152">您也可以上傳自訂使用者對應 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="99c9a-152">You can also upload a custom user mapping CSV file.</span></span>

7. <span data-ttu-id="99c9a-153">按 **[下一步]**，複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="99c9a-153">Click **Next**, review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="99c9a-154">移至 [**資料連線器**] 頁面上的 [**連接器**] 索引標籤，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="99c9a-154">Go to the **Connectors** tab on **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="99c9a-155">已知問題</span><span class="sxs-lookup"><span data-stu-id="99c9a-155">Known issues</span></span>

- <span data-ttu-id="99c9a-156">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="99c9a-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="99c9a-157">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="99c9a-157">Support for larger items will be available at a later date.</span></span>
