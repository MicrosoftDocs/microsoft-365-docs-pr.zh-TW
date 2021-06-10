---
title: 設定連接器以封存 Microsoft 365 中的 CellTrust 資料
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
description: 系統管理員可以設定連接器，將 CellTrust 資料從 Veritas 匯入至 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: 855d48303c7c35c32951105799aa117675820420
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164384"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a><span data-ttu-id="42f07-105">設定連接器以封存 CellTrust 資料</span><span class="sxs-lookup"><span data-stu-id="42f07-105">Set up a connector to archive CellTrust data</span></span>

<span data-ttu-id="42f07-106">在 Microsoft 365 規範中心使用 Veritas connector，將 CellTrust 平臺的資料匯入並封存到 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="42f07-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the CellTrust platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="42f07-107">Veritas 提供[CellTrust](https://globanet.com/celltrust/)連接器，可從協力廠商資料來源捕獲專案，並將這些專案匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="42f07-107">Veritas provides a [CellTrust](https://globanet.com/celltrust/) connector that captures items from the third-party data source and imports those items to Microsoft 365.</span></span> <span data-ttu-id="42f07-108">連接器會將簡訊郵件的內容從 CellTrust 帳戶轉換成電子郵件格式，然後將這些專案匯入 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="42f07-108">The connector converts the content of SMS messages from CellTrust accounts to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="42f07-109">將 CellTrust 資料儲存在使用者信箱之後，您就可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="42f07-109">After CellTrust data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="42f07-110">使用 CellTrust 連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="42f07-110">Using a CellTrust connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-celltrust-data"></a><span data-ttu-id="42f07-111">封存 CellTrust 資料一覽</span><span class="sxs-lookup"><span data-stu-id="42f07-111">Overview of archiving CellTrust data</span></span>

<span data-ttu-id="42f07-112">下列概要說明如何使用連接器封存 Microsoft 365 中的 CellTrust 資料。</span><span class="sxs-lookup"><span data-stu-id="42f07-112">The following overview explains the process of using a connector to archive CellTrust data in Microsoft 365.</span></span>

![CellTrust 資料的封存工作流程](../media/CellTrustConnectorWorkflow.png)

1. <span data-ttu-id="42f07-114">您的組織與 CellTrust 搭配使用，以設定及設定 CellTrust 網站。</span><span class="sxs-lookup"><span data-stu-id="42f07-114">Your organization works with CellTrust to set up and configure a CellTrust site.</span></span>

2. <span data-ttu-id="42f07-115">每24小時一次，CellTrust 專案會複製到 Veritas Merge1 網站。</span><span class="sxs-lookup"><span data-stu-id="42f07-115">Once every 24 hours, CellTrust items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="42f07-116">連接器也會將郵件的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="42f07-116">The connector also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="42f07-117">您在 Microsoft 365 合規性中心建立的 CellTrust 連接器每天都會連線到 Veritas Merge1 網站，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="42f07-117">The CellTrust connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="42f07-118">自動使用者對應為連接器會使用 [步驟 3](#step-3-map-users-and-complete-the-connector-setup)中所述的 *Email* 屬性值，將專案匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="42f07-118">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="42f07-119">在使用者信箱中建立名為 **CellTrust** 之 [收件匣] 資料夾中的子資料夾，並將訊息項目匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="42f07-119">A subfolder in the Inbox folder named **CellTrust** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="42f07-120">連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。</span><span class="sxs-lookup"><span data-stu-id="42f07-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="42f07-121">每個 CellTrust 專案都包含此屬性，其是以每位參與者的電子郵件地址填入。</span><span class="sxs-lookup"><span data-stu-id="42f07-121">Every CellTrust item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="42f07-122">開始之前</span><span class="sxs-lookup"><span data-stu-id="42f07-122">Before you begin</span></span>

- <span data-ttu-id="42f07-123">建立 Microsoft 連接器的 Merge1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="42f07-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="42f07-124">若要建立帳戶，請與 [Veritas 客戶支援](https://www.veritas.com/content/support/)聯繫。</span><span class="sxs-lookup"><span data-stu-id="42f07-124">To create an account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="42f07-125">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="42f07-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="42f07-126">在步驟1中建立 CellTrust 連接器的使用者 (，並在步驟 3) 中完成，必須指派 Exchange Online 中的「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="42f07-126">The user who creates the CellTrust connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="42f07-127">在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="42f07-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="42f07-128">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="42f07-128">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="42f07-129">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="42f07-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="42f07-130">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="42f07-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="42f07-131">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="42f07-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-celltrust-connector"></a><span data-ttu-id="42f07-132">步驟1：設定 CellTrust 連接器</span><span class="sxs-lookup"><span data-stu-id="42f07-132">Step 1: Set up the CellTrust connector</span></span>

<span data-ttu-id="42f07-133">第一步是存取 Microsoft 365 規範中心內的 **資料連線器**，並建立 CellTrust 資料的連接器。</span><span class="sxs-lookup"><span data-stu-id="42f07-133">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for CellTrust data.</span></span>

1. <span data-ttu-id="42f07-134">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [ **資料連線器** \> **CellTrust**]。</span><span class="sxs-lookup"><span data-stu-id="42f07-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **CellTrust**.</span></span>

2. <span data-ttu-id="42f07-135">在 [ **CellTrust** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="42f07-135">On the **CellTrust** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="42f07-136">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="42f07-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="42f07-137">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42f07-137">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="42f07-138">登入您的 Merge1 帳戶以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="42f07-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-celltrust-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="42f07-139">步驟2：設定 Veritas Merge1 site 上的 CellTrust 連接器</span><span class="sxs-lookup"><span data-stu-id="42f07-139">Step 2: Configure the CellTrust connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="42f07-140">第二個步驟是在 Veritas Merge1 網站上設定 CellTrust 連接器。</span><span class="sxs-lookup"><span data-stu-id="42f07-140">The second step is to configure the CellTrust connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="42f07-141">如需如何設定 CellTrust 連接器的詳細資訊，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="42f07-141">For information about how to configure the CellTrust connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="42f07-142">按一下 **[儲存] & 完成** 之後，就會顯示「Microsoft 365 規範中心」的 [連接器] 中的 [**使用者對應**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="42f07-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="42f07-143">步驟3：對應使用者並完成連接器設定</span><span class="sxs-lookup"><span data-stu-id="42f07-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="42f07-144">若要對應使用者並完成 Microsoft 365 規範中心內的連接器設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="42f07-144">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="42f07-145">在 [將 **CellTrust 使用者對應至 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]。</span><span class="sxs-lookup"><span data-stu-id="42f07-145">On the **Map CellTrust users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="42f07-146">CellTrust 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="42f07-146">The CellTrust items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="42f07-147">如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="42f07-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="42f07-148">按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="42f07-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-celltrust-connector"></a><span data-ttu-id="42f07-149">步驟4：監控 CellTrust 連接器</span><span class="sxs-lookup"><span data-stu-id="42f07-149">Step 4: Monitor the CellTrust connector</span></span>

<span data-ttu-id="42f07-150">在您建立 CellTrust 連接器之後，您可以在 [Microsoft 365 規範中心] 中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="42f07-150">After you create the CellTrust connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="42f07-151">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="42f07-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="42f07-152">按一下 [ **連接器** ] 索引標籤，然後選取 **CellTrust** 連接器以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="42f07-152">Click the **Connectors** tab and then select the **CellTrust** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="42f07-153">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="42f07-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="42f07-154">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="42f07-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="42f07-155">已知問題</span><span class="sxs-lookup"><span data-stu-id="42f07-155">Known issues</span></span>

- <span data-ttu-id="42f07-156">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="42f07-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="42f07-157">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="42f07-157">Support for larger items will be available at a later date.</span></span>