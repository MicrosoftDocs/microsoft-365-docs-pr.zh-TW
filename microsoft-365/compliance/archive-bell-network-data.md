---
title: 設定連接器以封存短信/彩信網路資料
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
description: 系統管理員可以設定 TeleMessage 連接器，以匯入並封存來自電鈴網路的 SMS 和 MMS 資料。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: bc775a4a1e5494e7e21b272dc6e468a63c18e814
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282641"
---
# <a name="set-up-a-connector-to-archive-bell-network-data-preview"></a><span data-ttu-id="db486-104">設定連接器，以將震鈴網路資料 (預覽) </span><span class="sxs-lookup"><span data-stu-id="db486-104">Set up a connector to archive Bell Network data (preview)</span></span>

<span data-ttu-id="db486-105">使用 Microsoft 365 規範中心內的 TeleMessage 連接器，匯入及封存短信服務 (SMS) 和多媒體訊息服務 (MMS) 來自電鈴網路的郵件。</span><span class="sxs-lookup"><span data-stu-id="db486-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) and Multimedia Messaging Service (MMS) messages from the Bell Network.</span></span> <span data-ttu-id="db486-106">在您設定及設定連接器之後，它每天會連線到您組織的震鈴網路，並將 SMS 和 MMS 郵件匯入至 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="db486-106">After you set up and configure a connector, it connects to your organization's Bell Network once every day, and imports SMS and MMS messages to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="db486-107">在將 SMS 和 MMS 郵件儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、內容搜尋，以及 Microsoft 365 保留原則，以震鈴網路資料。</span><span class="sxs-lookup"><span data-stu-id="db486-107">After the SMS and MMS messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to Bell Network data.</span></span> <span data-ttu-id="db486-108">例如，您可以使用內容搜尋來搜尋鈴聲網路 SMS/MMS，或在高級 eDiscovery 案例中，將包含電鈴網路連接器資料的信箱與保管人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="db486-108">For example, you can search Bell Network SMS/MMS using Content Search or associate the mailbox that contains the Bell Network connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="db486-109">使用鈴聲網路連接器匯入和封存 Microsoft 365 中的資料可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="db486-109">Using a Bell Network connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-bell-network-data"></a><span data-ttu-id="db486-110">封存鈴聲網路資料的概覽</span><span class="sxs-lookup"><span data-stu-id="db486-110">Overview of archiving Bell Network data</span></span>

<span data-ttu-id="db486-111">下列概要說明如何使用連接器封存 Microsoft 365 中的震鈴網路資料。</span><span class="sxs-lookup"><span data-stu-id="db486-111">The following overview explains the process of using a connector to archive Bell Network data in Microsoft 365.</span></span>

![鈴聲網路封存工作流程](../media/BellNetworkConnectorWorkflow.png)

1. <span data-ttu-id="db486-113">您的組織與 TeleMessage 和電鈴搭配使用，以設定電鈴網路連接器。</span><span class="sxs-lookup"><span data-stu-id="db486-113">Your organization works with TeleMessage and Bell to set up a Bell Network connector.</span></span> <span data-ttu-id="db486-114">如需詳細資訊，請參閱 [鈴聲網路存檔](https://www.telemessage.com/office365-activation-for-bell-network-archiver)器。</span><span class="sxs-lookup"><span data-stu-id="db486-114">For more information, see [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver).</span></span>

2. <span data-ttu-id="db486-115">每24小時一次，來自組織的鈴聲網路的 SMS 和 MMS 郵件會複製到 TeleMessage 網站。</span><span class="sxs-lookup"><span data-stu-id="db486-115">Once every 24 hours, SMS and MMS messages from your organization’s Bell Network are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="db486-116">您在 Microsoft 365 合規性中心建立的電鈴網路連接器每天會連線至 TeleMessage 網站，並將 SMS 和 MMS 郵件從過去24小時傳送至 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="db486-116">The Bell Network connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the SMS and MMS messages from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="db486-117">連接器也會將 SMS 和 MMS 郵件的內容轉換成電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="db486-117">The connector also converts the content of SMS and MMS messages to an email message format.</span></span>

4. <span data-ttu-id="db486-118">連接器會將行動通訊專案匯入至特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="db486-118">The connector imports the mobile communication items to the mailbox of specific users.</span></span> <span data-ttu-id="db486-119">在特定使用者的信箱中建立一個名為「 **電鈴 SMS/MMS 網路存檔** 」的新資料夾，並將這些專案匯入至該資料夾。</span><span class="sxs-lookup"><span data-stu-id="db486-119">A new folder named **Bell SMS/MMS Network Archiver** is created in a specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="db486-120">連接器會使用 *使用者的電子郵件地址* 屬性值來進行對應。</span><span class="sxs-lookup"><span data-stu-id="db486-120">The connector does this mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="db486-121">每個 SMS 和彩信都包含此內容，該屬性會填入郵件的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="db486-121">Every SMS and MMS message contains this property, which is populated with the email address of every participant of the message.</span></span>

   <span data-ttu-id="db486-122">除了使用 *使用者之電子郵件地址* 屬性值的自動使用者對應，您也可以透過上載 CSV 對應檔來定義自訂對應。</span><span class="sxs-lookup"><span data-stu-id="db486-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="db486-123">此對應檔包含組織中使用者的行動電話號碼和對應的 Microsoft 365 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="db486-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="db486-124">如果您為每個電鈴網路專案啟用自動使用者對應及自訂對應，連接器會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="db486-124">If you enable both automatic user mapping and custom mapping, for every Bell Network item the connector first looks at custom mapping file.</span></span> <span data-ttu-id="db486-125">如果找不到對應至使用者行動電話號碼的有效 Microsoft 365 使用者，連接器會使用嘗試匯入之專案的電子郵件地址屬性值。</span><span class="sxs-lookup"><span data-stu-id="db486-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile phone number, the connector will use the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="db486-126">如果連接器在自訂對應檔或 [電鈴網路專案] 的 [電子郵件地址] 屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="db486-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the Bell Network item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="db486-127">開始之前</span><span class="sxs-lookup"><span data-stu-id="db486-127">Before you begin</span></span>

<span data-ttu-id="db486-128">封存鈴聲網路資料所需的許多執行步驟，都是 Microsoft 365 的外部，必須先完成，您才能在規範中心內建立連接器。</span><span class="sxs-lookup"><span data-stu-id="db486-128">Many of the implementation steps required to archive Bell Network data are external to Microsoft 365 and must be completed before you can create a connector in the compliance center.</span></span>

- <span data-ttu-id="db486-129">[從 TeleMessage 定購電鈴網路歸檔服務](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)，並取得組織的有效管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="db486-129">Order the [Bell Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization.</span></span> <span data-ttu-id="db486-130">當您在規範中心建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="db486-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="db486-131">取得您的鈴聲網路帳戶和計費連絡人詳細資料，以便您可以填寫 TeleMessage 上架表單，並從電鈴訂購郵件封存服務。</span><span class="sxs-lookup"><span data-stu-id="db486-131">Obtain your Bell Network account and billing contact details so you can fill-out the TeleMessage onboarding forms and order the message archiving service from Bell.</span></span>

- <span data-ttu-id="db486-132">在 TeleMessage 帳戶中，註冊所有需要震鈴 SMS/MMS 網路封存的使用者。</span><span class="sxs-lookup"><span data-stu-id="db486-132">Register all users that require Bell SMS/MMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="db486-133">註冊使用者時，請務必使用與 Microsoft 365 帳戶所用相同的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="db486-133">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="db486-134">您的員工在鈴行動網路上必須擁有公司擁有和公司的行動電話。</span><span class="sxs-lookup"><span data-stu-id="db486-134">Your employees must have corporate-owned and corporate-liable mobile phones on the Bell mobile network.</span></span> <span data-ttu-id="db486-135">在 Microsoft 365 中封存郵件無法供員工擁有，或「帶您自己的裝置 (BYOD) 裝置。</span><span class="sxs-lookup"><span data-stu-id="db486-135">Archiving messages in Microsoft 365 isn't available for employee-owned or "Bring Your Own Devices (BYOD) devices.</span></span>

- <span data-ttu-id="db486-136">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="db486-136">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="db486-137">當您建立連接器時，將需要提供此同意。</span><span class="sxs-lookup"><span data-stu-id="db486-137">You will need to provide this consent when you create the connector.</span></span> <span data-ttu-id="db486-138">若要同意此要求，請移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Office 365 全域管理員的認證登入，然後接受要求。</span><span class="sxs-lookup"><span data-stu-id="db486-138">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span> <span data-ttu-id="db486-139">您必須先完成此步驟，才可成功建立電鈴網路連接器。</span><span class="sxs-lookup"><span data-stu-id="db486-139">You have to complete this step before you can successfully create a Bell Network connector.</span></span>

- <span data-ttu-id="db486-140">在 Exchange Online 中，必須將信箱匯入匯出角色指派給建立電鈴網路連接器的使用者。</span><span class="sxs-lookup"><span data-stu-id="db486-140">The user who creates a Bell Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="db486-141">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面中新增連接器時，這是必要的。</span><span class="sxs-lookup"><span data-stu-id="db486-141">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="db486-142">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="db486-142">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="db486-143">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="db486-143">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="db486-144">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="db486-144">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="db486-145">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="db486-145">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-bell-network-connector"></a><span data-ttu-id="db486-146">建立電鈴網路連接器</span><span class="sxs-lookup"><span data-stu-id="db486-146">Create a Bell Network connector</span></span>

<span data-ttu-id="db486-147">最後一個步驟是在 Microsoft 365 規範中心建立電鈴網路連接器。</span><span class="sxs-lookup"><span data-stu-id="db486-147">The last step is to create a Bell Network connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="db486-148">連接器會使用您提供的資訊來連線至 TeleMessage 網站，並將 SMS/MMS 郵件轉接至 Microsoft 365 中對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="db486-148">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS/ MMS messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="db486-149">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下 [**資料連線器**]  >  **鈴聲 SMS/MMS 網路**記錄器。</span><span class="sxs-lookup"><span data-stu-id="db486-149">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** > **Bell SMS/MMS Network Archiver**.</span></span>

2. <span data-ttu-id="db486-150">在 [**鈴聲網路**產品描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="db486-150">On the **Bell Network** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="db486-151">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="db486-151">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="db486-152">在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="db486-152">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="db486-153">使用者**名稱：** 您的 TeleMessage 使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="db486-153">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="db486-154">**密碼：** 您的 TeleMessage 密碼。</span><span class="sxs-lookup"><span data-stu-id="db486-154">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="db486-155">建立連接器之後，您可以關閉快顯視窗，然後移至下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="db486-155">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="db486-156">在 [ **使用者對應** ] 頁面上，啟用自動使用者對應。</span><span class="sxs-lookup"><span data-stu-id="db486-156">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="db486-157">若要啟用自訂對應，請上傳包含使用者對應資訊的 CSV 檔案，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="db486-157">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="db486-158">提供系統管理員同意，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="db486-158">Provide admin consent and then click **Next**.</span></span>

   <span data-ttu-id="db486-159">若要提供系統管理員同意，您必須以 Office 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="db486-159">To provide admin consent, you must be signed in with the credentials of an Office 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="db486-160">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="db486-160">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign-in using global admin credentials to accept the request.</span></span>

8. <span data-ttu-id="db486-161">請複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="db486-161">Review your settings, and then click **Finish** to create the connector.</span></span>

9. <span data-ttu-id="db486-162">移至「規範中心」的 [**資料連線器**] 頁面上的 [**連接器**] 索引標籤，以查看新連接器的匯入程式的處理進度。</span><span class="sxs-lookup"><span data-stu-id="db486-162">Go to the **Connectors** tab on the **Data connectors** page in the compliance center to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="db486-163">已知問題</span><span class="sxs-lookup"><span data-stu-id="db486-163">Known issues</span></span>

- <span data-ttu-id="db486-164">連接器不會匯入大於 10 MB 的任何專案。</span><span class="sxs-lookup"><span data-stu-id="db486-164">The connector doesn’t import any item larger than 10 MB.</span></span>
