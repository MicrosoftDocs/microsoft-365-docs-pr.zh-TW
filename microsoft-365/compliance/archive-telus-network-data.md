---
title: 設定在 Microsoft 365 中封存 TELUS 網路資料的連接器
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
description: 系統管理員可以設定 TeleMessage 連接器，以從 Microsoft 365 中的 TELUS 網路匯入及封存 SMS 資料。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: f52ead856aeaabdf229a4798359042fd2651f777
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282654"
---
# <a name="set-up-a-connector-to-archive-telus-network-data-preview"></a><span data-ttu-id="d1f76-104">設定連接器以封存 TELUS 網路資料 (預覽) </span><span class="sxs-lookup"><span data-stu-id="d1f76-104">Set up a connector to archive TELUS Network data (preview)</span></span>

<span data-ttu-id="d1f76-105">使用 Microsoft 365 規範中心內的 TeleMessage 連接器，匯入及封存短信服務 (SMS) 組織的 TELUS 網路中的資料。</span><span class="sxs-lookup"><span data-stu-id="d1f76-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) data from your organization's TELUS Network.</span></span> <span data-ttu-id="d1f76-106">在您設定及設定連接器之後，它每天會連線到您組織的 TELUS 網路，並將 SMS 資料匯入至 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="d1f76-106">After you set up and configure a connector, it connects to your organization's TELUS Network once every day, and imports SMS data to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="d1f76-107">將 SMS 郵件儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、內容搜尋，以及 Microsoft 365 保留原則，以 TELUS 資料。</span><span class="sxs-lookup"><span data-stu-id="d1f76-107">After SMS messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to TELUS data.</span></span> <span data-ttu-id="d1f76-108">例如，您可以使用內容搜尋來搜尋 TELUS SMS 訊息，或將包含 TELUS 資料的信箱與高級 eDiscovery 案例中的保管人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d1f76-108">For example, you can search TELUS SMS messages using Content Search or associate the mailbox that contains the TELUS data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="d1f76-109">使用 TELUS 網路連接器匯入和封存 Microsoft 365 中的資料可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="d1f76-109">Using a TELUS Network connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-telus-network-data"></a><span data-ttu-id="d1f76-110">封存 TELUS 網路資料的概覽</span><span class="sxs-lookup"><span data-stu-id="d1f76-110">Overview of archiving TELUS Network data</span></span>

<span data-ttu-id="d1f76-111">下列概要說明如何使用連接器封存 Microsoft 365 中的 TELUS 網路資料。</span><span class="sxs-lookup"><span data-stu-id="d1f76-111">The following overview explains the process of using a connector to archive TELUS Network data in Microsoft 365.</span></span>

![TELUS 網路封存工作流程](../media/TelusNetworkConnectorWorkflow.png)

1. <span data-ttu-id="d1f76-113">您的組織與 TeleMessage 和 TELUS 搭配使用，以設定 TELUS 網路連接器。</span><span class="sxs-lookup"><span data-stu-id="d1f76-113">Your organization works with TeleMessage and TELUS to set up a TELUS Network connector.</span></span> <span data-ttu-id="d1f76-114">如需詳細資訊，請參閱 [TELUS Network 存檔](https://www.telemessage.com/office365-activation-for-telus-network-archiver/)器。</span><span class="sxs-lookup"><span data-stu-id="d1f76-114">For more information, see [TELUS Network Archiver](https://www.telemessage.com/office365-activation-for-telus-network-archiver/).</span></span>

2. <span data-ttu-id="d1f76-115">每24小時一次，來自組織之 TELUS 網路的 SMS 訊息會複製到 TeleMessage 網站。</span><span class="sxs-lookup"><span data-stu-id="d1f76-115">Once every 24 hours, SMS messages from your organization’s TELUS Network are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="d1f76-116">您在 Microsoft 365 合規性中心建立的 TELUS 網路連接器每天會連線至 TeleMessage 網站，並將 SMS 郵件從過去24小時傳送至 Microsoft 雲端中的安全 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="d1f76-116">The TELUS Network connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the SMS messages from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="d1f76-117">連接器也會將 SMS 郵件的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="d1f76-117">The connector also converts the content of SMS messages to an email message format.</span></span>

4. <span data-ttu-id="d1f76-118">連接器會將行動通訊專案匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="d1f76-118">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="d1f76-119">在特定使用者的信箱中建立名為 **TELUS SMS 網路存檔** 的新資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="d1f76-119">A new folder named **TELUS SMS Network Archiver** is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="d1f76-120">連接器會使用 *使用者的電子郵件地址* 屬性值進行對應。</span><span class="sxs-lookup"><span data-stu-id="d1f76-120">The connector does mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="d1f76-121">每個 SMS 郵件都包含此內容，該屬性會填入 SMS 訊息每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d1f76-121">Every SMS message contains this property, which is populated with the email address of every participant of the SMS message.</span></span>

   <span data-ttu-id="d1f76-122">除了使用 *使用者的電子郵件地址* 屬性值進行自動使用者對應之外，您也可以透過上載 CSV 對應檔來執行自訂對應。</span><span class="sxs-lookup"><span data-stu-id="d1f76-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also implement custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="d1f76-123">此對應檔包含組織中使用者的行動電話號碼和對應的 Microsoft 365 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d1f76-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="d1f76-124">如果您為每個 TELUS 專案啟用自動使用者對應及自訂對應，連接器會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="d1f76-124">If you enable both automatic user mapping and custom mapping, for every TELUS item the connector first looks at custom mapping file.</span></span> <span data-ttu-id="d1f76-125">如果找不到對應至使用者行動電話號碼的有效 Microsoft 365 使用者，連接器會使用嘗試匯入之專案的電子郵件地址屬性值。</span><span class="sxs-lookup"><span data-stu-id="d1f76-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile phone number, the connector will use the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="d1f76-126">如果連接器在自訂對應檔案或 TELUS 專案的電子郵件地址屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="d1f76-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the TELUS item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d1f76-127">開始之前</span><span class="sxs-lookup"><span data-stu-id="d1f76-127">Before you begin</span></span>

<span data-ttu-id="d1f76-128">封存 TELUS 網路資料所需的許多執行步驟都是 Microsoft 365 的外部，必須先完成，您才能在規範中心建立連接器。</span><span class="sxs-lookup"><span data-stu-id="d1f76-128">Many of the implementation steps required to archive TELUS Network data are external to Microsoft 365 and must be completed before you can create a connector in the compliance center.</span></span>

- <span data-ttu-id="d1f76-129">[從 TeleMessage 定購 TELUS 網路歸檔服務](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)，並為您的組織取得有效的管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="d1f76-129">Order the [TELUS Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="d1f76-130">當您在規範中心建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="d1f76-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="d1f76-131">取得您的 TELUS 網路帳戶和計費連絡人詳細資料，以便您可以在 TELUS 中填寫 TeleMessage 上架表單，並訂購郵件封存服務。</span><span class="sxs-lookup"><span data-stu-id="d1f76-131">Obtain your TELUS Network account and billing contact details so you can fill-out the TeleMessage onboarding forms and order the message archiving service from TELUS.</span></span>

- <span data-ttu-id="d1f76-132">在 TeleMessage 帳戶中，註冊所有需要 TELUS SMS 網路封存的使用者。</span><span class="sxs-lookup"><span data-stu-id="d1f76-132">Register all users that require TELUS SMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="d1f76-133">註冊使用者時，請務必使用與 Microsoft 365 帳戶所用相同的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d1f76-133">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="d1f76-134">您的員工在 theTELUS 行動網路上必須擁有公司擁有及公司的行動電話。</span><span class="sxs-lookup"><span data-stu-id="d1f76-134">Your employees must have corporate-owned and corporate-liable mobile phones on theTELUS mobile network.</span></span> <span data-ttu-id="d1f76-135">在 Microsoft 365 中封存郵件無法供員工擁有，也不會讓您自己的裝置 (BYOD) 裝置。</span><span class="sxs-lookup"><span data-stu-id="d1f76-135">Archiving messages in Microsoft 365 isn't available for employee-owned or Bring Your Own Devices (BYOD) devices.</span></span>

- <span data-ttu-id="d1f76-136">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="d1f76-136">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="d1f76-137">當您建立連接器時，將需要提供此同意。</span><span class="sxs-lookup"><span data-stu-id="d1f76-137">You will need to provide this consent when you create the connector.</span></span> <span data-ttu-id="d1f76-138">若要同意此要求，請移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Office 365 全域管理員的認證登入，然後接受要求。</span><span class="sxs-lookup"><span data-stu-id="d1f76-138">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span> <span data-ttu-id="d1f76-139">您必須完成此步驟，才能成功建立 TELUS 網路連接器。</span><span class="sxs-lookup"><span data-stu-id="d1f76-139">You have to complete this step before you can successfully create TELUS Network connector.</span></span>

- <span data-ttu-id="d1f76-140">在 Exchange Online 中，必須對建立 TELUS 網路連接器的使用者指派「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="d1f76-140">The user who creates a TELUS Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d1f76-141">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面中新增連接器時，這是必要的。</span><span class="sxs-lookup"><span data-stu-id="d1f76-141">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d1f76-142">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="d1f76-142">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d1f76-143">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="d1f76-143">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d1f76-144">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="d1f76-144">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d1f76-145">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="d1f76-145">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-telus-network-connector"></a><span data-ttu-id="d1f76-146">建立 TELUS 網路連接器</span><span class="sxs-lookup"><span data-stu-id="d1f76-146">Create a TELUS Network connector</span></span>

<span data-ttu-id="d1f76-147">在您完成上一節所述的必要條件之後，您可以在 Microsoft 365 規範中心建立 TELUS 網路連接器。</span><span class="sxs-lookup"><span data-stu-id="d1f76-147">After you've completed the prerequisites described in the previous section, you can create TELUS Network connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d1f76-148">連接器會使用您提供的資訊來連線至 TeleMessage 網站，並將 SMS 郵件轉接至 Microsoft 365 中對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="d1f76-148">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="d1f76-149">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **TELUS 網路**]。</span><span class="sxs-lookup"><span data-stu-id="d1f76-149">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **TELUS Network**.</span></span>

2. <span data-ttu-id="d1f76-150">在 [ **TELUS 網路**產品描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="d1f76-150">On the **TELUS Network** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="d1f76-151">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="d1f76-151">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d1f76-152">在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d1f76-152">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="d1f76-153">使用者**名稱：** 您的 TeleMessage 使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="d1f76-153">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="d1f76-154">**密碼：** 您的 TeleMessage 密碼。</span><span class="sxs-lookup"><span data-stu-id="d1f76-154">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="d1f76-155">建立連接器之後，您可以關閉快顯視窗，然後移至下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="d1f76-155">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="d1f76-156">在 [ **使用者對應** ] 頁面上啟用 [自動使用者對應]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d1f76-156">On the **User mapping** page, enable automatic user mapping and click **Next**.</span></span> <span data-ttu-id="d1f76-157">如果您需要自訂對應，請上載 CSV 檔案，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d1f76-157">In case you need custom mapping upload a CSV file, and click **Next**.</span></span>

7. <span data-ttu-id="d1f76-158">提供系統管理員同意，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d1f76-158">Provide admin consent and then click **Next**.</span></span>

   <span data-ttu-id="d1f76-159">若要提供系統管理員同意，您必須以 Office 365 全域管理員的認證登入，然後接受同意要求。</span><span class="sxs-lookup"><span data-stu-id="d1f76-159">To provide admin consent, you must be signed in with the credentials of an Office 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="d1f76-160">如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。</span><span class="sxs-lookup"><span data-stu-id="d1f76-160">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign-in using global admin credentials to accept the request.</span></span>

8. <span data-ttu-id="d1f76-161">請複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="d1f76-161">Review your settings, and then click **Finish** to create the connector.</span></span>

9. <span data-ttu-id="d1f76-162">移至 [ **資料連線器** ] 頁面中的 [連接器] 索引標籤，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="d1f76-162">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d1f76-163">已知問題</span><span class="sxs-lookup"><span data-stu-id="d1f76-163">Known issues</span></span>

- <span data-ttu-id="d1f76-164">連接器不會匯入大於 10 MB 的任何專案。</span><span class="sxs-lookup"><span data-stu-id="d1f76-164">The connector doesn’t import any item larger than 10 MB.</span></span>
