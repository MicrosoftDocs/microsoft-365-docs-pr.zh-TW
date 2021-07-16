---
title: 設定在 Microsoft 365 中封存連線聊天資料的連接器
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
description: 瞭解如何設定和使用17a-4 冰連線 chat DataParser connector，以匯入和封存 Microsoft 365 中的冰激淩連線聊天資料。
ms.openlocfilehash: 0aac5c701f122eaf99497635281ebc07d835fc2e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454478"
---
# <a name="set-up-a-connector-to-archive-ice-connect-chat-data"></a><span data-ttu-id="95320-103">設定連接器以封存連線聊天資料中的冰激淩</span><span class="sxs-lookup"><span data-stu-id="95320-103">Set up a connector to archive ICE Connect Chat data</span></span>

<span data-ttu-id="95320-104">使用來自 17a-4 LLC 的[冰 DataParser](https://www.17a-4.com/ice-dataparser/) ，以匯入和封存資料從 ICE 連線聊天至 Microsoft 365 組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="95320-104">Use the [ICE DataParser](https://www.17a-4.com/ice-dataparser/) from 17a-4 LLC to import and archive data from ICE Connect Chat to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="95320-105">DataParser 包含的 ICE 聊天連接器設定為從協力廠商資料來源捕獲專案，並將這些專案匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="95320-105">The DataParser includes an ICE Chat connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="95320-106">冰 DataParser 連接器會將冰連線聊天資料轉換成電子郵件訊息格式，然後將這些專案匯入 Microsoft 365 中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="95320-106">The ICE DataParser connector converts ICE Connect Chat data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="95320-107">冰連線聊天資料儲存在使用者信箱中之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="95320-107">After ICE Connect Chat data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="95320-108">使用 ICE DataParser 連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="95320-108">Using an ICE DataParser connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ice-chat-data"></a><span data-ttu-id="95320-109">封存的冰激淩聊天資料</span><span class="sxs-lookup"><span data-stu-id="95320-109">Overview of archiving ICE Chat data</span></span>

<span data-ttu-id="95320-110">下列概要說明使用資料連線器封存 Microsoft 365 中連線聊天資料之冰的程式。</span><span class="sxs-lookup"><span data-stu-id="95320-110">The following overview explains the process of using a data connector to archive ICE Connect Chat data in Microsoft 365.</span></span>

![從17a-4 連線聊天資料的冰封存工作流程](../media/ICEChatDataParserConnectorWorkflow.png)

1. <span data-ttu-id="95320-112">您的組織可以搭配17a-4 來設定和設定冰 DataParser。</span><span class="sxs-lookup"><span data-stu-id="95320-112">Your organization works with 17a-4 to set up and configure the ICE DataParser.</span></span>

2. <span data-ttu-id="95320-113">冰連線聊天專案是定期 DataParser 收集。</span><span class="sxs-lookup"><span data-stu-id="95320-113">On a regular basis, ICE Connect Chat items are collected by the DataParser.</span></span> <span data-ttu-id="95320-114">DataParser 也會將郵件的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="95320-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="95320-115">您在 Microsoft 365 合規性中心中建立的 ICE DataParser 連接器會連接到 DataParser，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="95320-115">The ICE DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="95320-116">在使用者信箱中建立名為「**冰激淩 DataParser** 」的收件匣資料夾中的子資料夾，並且將「冰」連線聊天專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="95320-116">A subfolder in the Inbox folder named **ICE DataParser** is created in the user mailboxes, and the ICE Connect Chat items are imported to that folder.</span></span> <span data-ttu-id="95320-117">連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。</span><span class="sxs-lookup"><span data-stu-id="95320-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="95320-118">每個 ICE 連線聊天室專案都包含此屬性，它會填入每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="95320-118">Every ICE Connect Chat item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="95320-119">在您設定連接器之前</span><span class="sxs-lookup"><span data-stu-id="95320-119">Before you set up a connector</span></span>

- <span data-ttu-id="95320-120">建立 Microsoft 連接器的 DataParser 帳戶。</span><span class="sxs-lookup"><span data-stu-id="95320-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="95320-121">若要這麼做，請與我們聯繫 [-4 LLC](https://www.17a-4.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="95320-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="95320-122">當您在步驟1中建立連接器時，您必須登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="95320-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="95320-123">在步驟1中建立冰 DataParser 連接器的使用者 (，並在步驟 3) 中完成，必須指派 Exchange Online 中的「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="95320-123">The user who creates the ICE DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="95320-124">在 Microsoft 365 合規性中心中的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="95320-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="95320-125">根據預設，此角色不會指派給 Exchange Online 中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="95320-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="95320-126">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="95320-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="95320-127">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="95320-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="95320-128">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="95320-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-ice-dataparser-connector"></a><span data-ttu-id="95320-129">步驟1：設定冰 DataParser 連接器</span><span class="sxs-lookup"><span data-stu-id="95320-129">Step 1: Set up an ICE DataParser connector</span></span>

<span data-ttu-id="95320-130">第一步是存取 Microsoft 365 合規性中心中的資料連線器頁面，並為 ICE 連線聊天資料建立17a-4 連接器。</span><span class="sxs-lookup"><span data-stu-id="95320-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for ICE Connect Chat data.</span></span>

1. <span data-ttu-id="95320-131">移至 <https://compliance.microsoft.com> ，然後按一下 [**資料連線器**  >  **冰 DataParser**]。</span><span class="sxs-lookup"><span data-stu-id="95320-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **ICE DataParser**.</span></span>

2. <span data-ttu-id="95320-132">在 [ **冰 DataParser** 產品描述] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="95320-132">On the **ICE DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="95320-133">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="95320-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="95320-134">輸入識別連接器的唯一名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="95320-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="95320-135">登入您的17a-4 帳戶，並完成 [ICE DataParser 連線嚮導] 中的步驟。</span><span class="sxs-lookup"><span data-stu-id="95320-135">Sign in to your 17a-4 account and complete the steps in the ICE DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-ice-dataparser-connector"></a><span data-ttu-id="95320-136">步驟2：設定冰 DataParser 連接器</span><span class="sxs-lookup"><span data-stu-id="95320-136">Step 2: Configure the ICE DataParser connector</span></span>

<span data-ttu-id="95320-137">使用17a-4 支援來設定冰 DataParser 連接器。</span><span class="sxs-lookup"><span data-stu-id="95320-137">Work with 17a-4 Support to configure the ICE DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="95320-138">步驟3：對應使用者</span><span class="sxs-lookup"><span data-stu-id="95320-138">Step 3: Map users</span></span>

<span data-ttu-id="95320-139">冰 DataParser 連接器會在將資料匯入 Microsoft 365 之前，自動將使用者對應至其 Microsoft 365 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="95320-139">The ICE DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-ice-dataparser-connector"></a><span data-ttu-id="95320-140">步驟4：監控冰 DataParser 連接器</span><span class="sxs-lookup"><span data-stu-id="95320-140">Step 4: Monitor the ICE DataParser connector</span></span>

<span data-ttu-id="95320-141">在您建立冰 DataParser 連接器之後，您可以在 Microsoft 365 合規性中心中查看連接器狀態。</span><span class="sxs-lookup"><span data-stu-id="95320-141">After you create an ICE DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="95320-142">移至 <https://compliance.microsoft.com> 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="95320-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="95320-143">按一下 [ **連接器** ] 索引標籤，然後選取您建立的冰 DataParser 連接器，以顯示飛出頁面，該頁面包含連接器的屬性和資訊。</span><span class="sxs-lookup"><span data-stu-id="95320-143">Click the **Connectors** tab and then select the ICE DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="95320-144">在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。</span><span class="sxs-lookup"><span data-stu-id="95320-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="95320-145">此記錄檔包含已匯入至 Microsoft 雲端的資料。</span><span class="sxs-lookup"><span data-stu-id="95320-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="95320-146">已知問題</span><span class="sxs-lookup"><span data-stu-id="95320-146">Known issues</span></span>

<span data-ttu-id="95320-147">此時，我們不支援匯入大於 10 MB 的附件或專案。</span><span class="sxs-lookup"><span data-stu-id="95320-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="95320-148">稍後將提供對較大專案的支援。</span><span class="sxs-lookup"><span data-stu-id="95320-148">Support for larger items will be available at a later date.</span></span>
