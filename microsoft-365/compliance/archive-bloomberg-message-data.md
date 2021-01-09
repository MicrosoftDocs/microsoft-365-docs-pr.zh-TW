---
title: 設定連接器以封存 Bloomberg 郵件資料
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
description: 管理員可以設定資料連線器，將 Bloomberg 郵件電子郵件工具中的資料匯入和封存至 Microsoft 365。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: f9b082dace9301f5a664078e9028c646ffa28483
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790113"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a><span data-ttu-id="6900f-104">設定連接器以封存 Bloomberg 郵件資料</span><span class="sxs-lookup"><span data-stu-id="6900f-104">Set up a connector to archive Bloomberg Message data</span></span>

<span data-ttu-id="6900f-105">使用 Microsoft 365 規範中心的資料連線器，從 [Bloomberg 郵件](https://www.bloomberg.com/professional/product/collaboration/) 共同作業工具匯入及封存金融服務電子郵件資料。</span><span class="sxs-lookup"><span data-stu-id="6900f-105">Use a data connector in the Microsoft 365 compliance center to import and archive financial services email data from the [Bloomberg Message](https://www.bloomberg.com/professional/product/collaboration/) collaboration tool.</span></span> <span data-ttu-id="6900f-106">在您設定及設定連接器之後，它會連線到您組織的 Bloomberg secure FTP (SFTP) 網站一次，並將電子郵件專案匯入 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="6900f-106">After you set up and configure a connector, it connects to your organization's Bloomberg secure FTP (SFTP) site once every day, and imports email items to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="6900f-107">將 Bloomberg 郵件資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、內容搜尋、就地封存、審核、通訊法規遵從性，以及 Microsoft 365 保留原則，以 Bloomberg 郵件資料。</span><span class="sxs-lookup"><span data-stu-id="6900f-107">After Bloomberg Message data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation hold, content search, In-place archiving, auditing, Communication compliance, and Microsoft 365 retention policies to Bloomberg Message data.</span></span> <span data-ttu-id="6900f-108">例如，您可以使用內容搜尋工具搜尋 Bloomberg 郵件電子郵件，或在高級 eDiscovery 案例中關聯包含 Bloomberg 郵件資料與保管人的信箱。</span><span class="sxs-lookup"><span data-stu-id="6900f-108">For example, you can search Bloomberg Message emails using the content search tool or associate the mailbox that contains the Bloomberg Message data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="6900f-109">使用 Bloomberg 郵件連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="6900f-109">Using a Bloomberg Message connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-bloomberg-message-data"></a><span data-ttu-id="6900f-110">封存 Bloomberg 訊息資料的概覽</span><span class="sxs-lookup"><span data-stu-id="6900f-110">Overview of archiving Bloomberg Message data</span></span>

<span data-ttu-id="6900f-111">下列概要說明如何使用連接器封存 Microsoft 365 中的 Bloomberg 郵件資料。</span><span class="sxs-lookup"><span data-stu-id="6900f-111">The following overview explains the process of using a connector to archive Bloomberg Message data in Microsoft 365.</span></span>

![Bloomberg 郵件匯入和封存處理常式](../media/BloombergMessageArchiving.png)

1. <span data-ttu-id="6900f-113">您的組織與 Bloomberg 搭配使用，以設定 Bloomberg SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-113">Your organization works with Bloomberg to set up a Bloomberg SFTP site.</span></span> <span data-ttu-id="6900f-114">您也可以使用 Bloomberg 設定 Bloomberg 郵件，將電子郵件傳送至 Bloomberg SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-114">You'll also work with Bloomberg to configure Bloomberg Message to copy email messages to the Bloomberg SFTP site.</span></span>

2. <span data-ttu-id="6900f-115">每24小時一次，Bloomberg 郵件的電子郵件會複製到 Bloomberg SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-115">Once every 24 hours, email messages from Bloomberg Message are copied to the Bloomberg SFTP site.</span></span>

3. <span data-ttu-id="6900f-116">您在 Microsoft 365 合規性中心建立的 Bloomberg 郵件連接器每天會連線至 Bloomberg SFTP 網站，並將電子郵件訊息從過去24小時傳送至 Microsoft 雲端中的 secure Azure Storage 區域。</span><span class="sxs-lookup"><span data-stu-id="6900f-116">The Bloomberg Message connector that you create in the Microsoft 365 compliance center connects to the Bloomberg SFTP site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

4. <span data-ttu-id="6900f-117">連接器會將電子郵件專案匯入特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="6900f-117">The connector imports the email message items to the mailbox of a specific user.</span></span> <span data-ttu-id="6900f-118">在特定使用者的信箱中建立名為 BloombergMessage 的新資料夾，並將這些專案匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="6900f-118">A new folder named BloombergMessage is created in the specific user's mailbox and the items will be imported to it.</span></span> 

   <span data-ttu-id="6900f-119">連接器會使用 CorporateEmailAddress 屬性的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6900f-119">The connector does this by using the value of the CorporateEmailAddress property.</span></span> <span data-ttu-id="6900f-120">每封電子郵件都包含此內容，該屬性會填入電子郵件的每個參與者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6900f-120">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="6900f-121">除了使用 *CorporateEmailAddress* 屬性的值進行自動使用者對應之外，您也可以透過上載 CSV 對應檔來定義自訂對應。</span><span class="sxs-lookup"><span data-stu-id="6900f-121">In addition to automatic user mapping using the value of the *CorporateEmailAddress* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="6900f-122">此對應檔包含組織中每位使用者的 Bloomberg UUID 和對應的 Microsoft 365 信箱位址。</span><span class="sxs-lookup"><span data-stu-id="6900f-122">This mapping file contains a Bloomberg UUID and the corresponding Microsoft 365 mailbox address for each user in your organization.</span></span> <span data-ttu-id="6900f-123">如果您啟用自動使用者對應，並提供自訂對應，則每個電子郵件專案連接器都會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="6900f-123">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at the custom-mapping file.</span></span> <span data-ttu-id="6900f-124">如果找不到對應至使用者 Bloomberg UUID 的有效 Microsoft 365 使用者，連接器會使用電子郵件專案的 *CorporateEmailAddress* 屬性。</span><span class="sxs-lookup"><span data-stu-id="6900f-124">If it doesn't find a valid Microsoft 365 user that corresponds to a user's Bloomberg UUID, the connector uses the *CorporateEmailAddress* property of the email item.</span></span> <span data-ttu-id="6900f-125">如果連接器在自訂對應檔案或電子郵件專案的 *CorporateEmailAddress* 屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="6900f-125">If the connector doesn't find a valid Microsoft 365 user in either the custom-mapping file or the *CorporateEmailAddress* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6900f-126">開始之前</span><span class="sxs-lookup"><span data-stu-id="6900f-126">Before you begin</span></span>

<span data-ttu-id="6900f-127">封存 Bloomberg 郵件資料所需的部分執行步驟是 Microsoft 365 的外部，必須先完成，您才能在規範中心建立連接器。</span><span class="sxs-lookup"><span data-stu-id="6900f-127">Some of the implementation steps required to archive Bloomberg Message data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="6900f-128">訂閱 [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)。</span><span class="sxs-lookup"><span data-stu-id="6900f-128">Subscribe to [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA).</span></span> <span data-ttu-id="6900f-129">這是必要的，讓您可以登入 Bloomberg 無所不在，以存取您必須設定及設定的 Bloomberg SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-129">This is required so that you can log in to Bloomberg Anywhere to access the Bloomberg SFTP site that you have to set up and configure.</span></span>

- <span data-ttu-id="6900f-130">設定 Bloomberg SFTP (安全檔案傳輸通訊協定) 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-130">Set up a Bloomberg SFTP (Secure file transfer protocol) site.</span></span> <span data-ttu-id="6900f-131">使用 Bloomberg 來設定 SFTP 網站後，每日會將 Bloomberg 郵件的資料上傳到 SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-131">After working with Bloomberg to set up the SFTP site, data from Bloomberg Message is uploaded to the SFTP site every day.</span></span> <span data-ttu-id="6900f-132">您在步驟2中建立的連接器會連接到此 SFTP 網站，並將電子郵件資料傳送至 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="6900f-132">The connector you create in Step 2 connects to this SFTP site and transfers the email data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="6900f-133">在傳輸過程中，SFTP 也會加密傳送至信箱的 Bloomberg 郵件資料。</span><span class="sxs-lookup"><span data-stu-id="6900f-133">SFTP also encrypts the Bloomberg Message data that is sent to mailboxes during the transfer process.</span></span>

  <span data-ttu-id="6900f-134">如需 Bloomberg SFTP (也稱為 *BB-SFTP*) 的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="6900f-134">For information about Bloomberg SFTP (also called *BB-SFTP*):</span></span>

  - <span data-ttu-id="6900f-135">請參閱 [Bloomberg 支援部門](https://www.bloomberg.com/professional/support/documentation/)的「SFTP Connectivity 標準」檔。</span><span class="sxs-lookup"><span data-stu-id="6900f-135">See the "SFTP Connectivity Standards" document at [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/).</span></span>

  - <span data-ttu-id="6900f-136">請與 [Bloomberg 客戶支援](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="6900f-136">Contact [Bloomberg customer support](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).</span></span>

   > [!NOTE]
   > <span data-ttu-id="6900f-137">如果您的組織已部署一個連接器，以封存立即 Bloomberg 資料，您不需要設定另一個 SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-137">If your organization already deployed a connector to archive Instant Bloomberg data, you don't need to set up another SFTP site.</span></span> <span data-ttu-id="6900f-138">您可以使用相同的 SFTP 網站來 Bloomberg 消息連接器。</span><span class="sxs-lookup"><span data-stu-id="6900f-138">You can use the same SFTP site for the Bloomberg Message connector.</span></span>

- <span data-ttu-id="6900f-139">當您使用 Bloomberg 設定 SFTP 網站後，Bloomberg 會在您回應 Bloomberg 的實施電子郵件訊息之後，為您提供一些資訊。</span><span class="sxs-lookup"><span data-stu-id="6900f-139">After you work with Bloomberg to set up an SFTP site, Bloomberg will provide some information to you after you respond to the Bloomberg implementation email message.</span></span> <span data-ttu-id="6900f-140">儲存下列資訊的複本。</span><span class="sxs-lookup"><span data-stu-id="6900f-140">Save a copy of the following information.</span></span> <span data-ttu-id="6900f-141">您可以使用它在步驟3中設定連接器。</span><span class="sxs-lookup"><span data-stu-id="6900f-141">You use it to set up a connector in Step 3.</span></span>

  - <span data-ttu-id="6900f-142">公司的程式碼，也就是您組織的識別碼，用來登入 Bloomberg SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-142">Firm code, which is an ID for your organization and is used to log in to the Bloomberg SFTP site.</span></span>

  - <span data-ttu-id="6900f-143">Bloomberg SFTP 網站的密碼</span><span class="sxs-lookup"><span data-stu-id="6900f-143">Password for your Bloomberg SFTP site</span></span>

  - <span data-ttu-id="6900f-144">Bloomberg SFTP 網站 (的 URL，例如，sftp.bloomberg.com) 。</span><span class="sxs-lookup"><span data-stu-id="6900f-144">URL for Bloomberg SFTP site (for example, sftp.bloomberg.com).</span></span> <span data-ttu-id="6900f-145">此外，Bloomberg 也可以為 Bloomberg SFTP 網站提供對應的 IP 位址，也可以用來設定連接器。</span><span class="sxs-lookup"><span data-stu-id="6900f-145">In addition, Bloomberg may also provide a corresponding IP address for the Bloomberg SFTP site, which also can be used to set up the connector.</span></span>

  - <span data-ttu-id="6900f-146">Bloomberg SFTP 網站的埠號碼</span><span class="sxs-lookup"><span data-stu-id="6900f-146">Port number for Bloomberg SFTP site</span></span>

- <span data-ttu-id="6900f-147">在一天內，Bloomberg 郵件連接器可匯入全部200000專案。</span><span class="sxs-lookup"><span data-stu-id="6900f-147">The Bloomberg Message connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="6900f-148">如果 SFTP 網站上的專案超過200000個，將不會將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6900f-148">If there are more than 200,000 items on the SFTP site, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="6900f-149">在步驟 3 (中建立 Bloomberg 郵件連接器，並在步驟 1) 中下載公開金鑰及 IP 位址的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="6900f-149">The user who creates a Bloomberg Message connector in Step 3 (and who downloads the public keys and IP address in Step 1) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6900f-150">在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面中新增連接器時，這是必要的。</span><span class="sxs-lookup"><span data-stu-id="6900f-150">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6900f-151">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="6900f-151">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="6900f-152">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="6900f-152">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6900f-153">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="6900f-153">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6900f-154">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="6900f-154">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a><span data-ttu-id="6900f-155">步驟1：取得 SSH 和 PGP 公開金鑰</span><span class="sxs-lookup"><span data-stu-id="6900f-155">Step 1: Obtain SSH and PGP public keys</span></span>

<span data-ttu-id="6900f-156">第一步是取得公開金鑰的副本，以取得安全命令介面 (SSH) 和非常好的隱私權 (PGP) 。</span><span class="sxs-lookup"><span data-stu-id="6900f-156">The first step is to obtain a copy of the public keys for Secure Shell (SSH) and Pretty Good Privacy (PGP).</span></span> <span data-ttu-id="6900f-157">您可以在步驟2中使用這些機碼來設定 Bloomberg SFTP 網站，以允許您在步驟3中建立的連接器 () 連線到 SFTP 網站，以及將 Bloomberg 郵件電子郵件資料轉移至 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="6900f-157">You use these keys in Step 2 to configure the Bloomberg SFTP site to allow the connector (that you create in Step 3) to connect to the SFTP site and transfer the Bloomberg Message email data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="6900f-158">您也可以在此步驟中取得 IP 位址，當您設定 Bloomberg SFTP 網站時，您可以使用此位址。</span><span class="sxs-lookup"><span data-stu-id="6900f-158">You also obtain an IP address in this step, which you use when configuring the Bloomberg SFTP site.</span></span>

1. <span data-ttu-id="6900f-159">移至 [ https://compliance.microsoft.com\ ] (https://compliance.microsoft.com) ，然後按一下左導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="6900f-159">Go to [https://compliance.microsoft.com\](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="6900f-160">在 [ **Bloomberg 郵件**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="6900f-160">On the **Data connectors** page under **Bloomberg Message**, click **View**.</span></span>

3. <span data-ttu-id="6900f-161">在 [ **Bloomberg 訊息** 產品描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="6900f-161">On the **Bloomberg Message** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="6900f-162">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="6900f-162">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="6900f-163">在 [步驟 1] 底下的 [ **新增 BLOOMBERG SFTP 網站認證** ] 中，按一下 [ **下載 SSH 金鑰**]、[ **下載 PGP 金鑰**] 和 [ **下載 IP 位址** ] 連結，將每個檔案的副本儲存到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="6900f-163">On the **Add credentials for Bloomberg SFTP site** under step 1, click the **Download SSH key**, **Download PGP key**, and **Download IP address** links to save a copy of each file to your local computer.</span></span> <span data-ttu-id="6900f-164">這些檔案包含下列專案，可用來設定步驟2中的 Bloomberg SFTP 網站：</span><span class="sxs-lookup"><span data-stu-id="6900f-164">These files contain the following items that are used to configure the Bloomberg SFTP site in Step 2:</span></span>

   - <span data-ttu-id="6900f-165">SSH 公開金鑰：此機碼用來設定安全命令介面 (SSH) ，以在連接器連線至 Bloomberg SFTP 網站時，啟用安全的遠端登入。</span><span class="sxs-lookup"><span data-stu-id="6900f-165">SSH public key: This key is used to configure Secure Shell (SSH) to enable a secure remote login when the connector connects to the Bloomberg SFTP site.</span></span>

   - <span data-ttu-id="6900f-166">PGP 公開金鑰：此機碼是用來設定從 Bloomberg SFTP 網站傳輸至 Microsoft 365 的資料加密。</span><span class="sxs-lookup"><span data-stu-id="6900f-166">PGP public key: This key is used to configure the encryption of data that's transferred from the Bloomberg SFTP site to Microsoft 365.</span></span>

   - <span data-ttu-id="6900f-167">IP 位址： Bloomberg SFTP 網站已設定為只接受來自此 IP 位址的連線要求，該要求是由您在步驟3中建立的 Bloomberg 郵件連接器所使用。</span><span class="sxs-lookup"><span data-stu-id="6900f-167">IP address: The Bloomberg SFTP site is configured to accept a connection request only from this IP address, which is used by the Bloomberg Message connector that you create in Step 3.</span></span>

6. <span data-ttu-id="6900f-168">按一下 [ **取消** ] 關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="6900f-168">Click **Cancel** to close the wizard.</span></span> <span data-ttu-id="6900f-169">您會回到步驟3中的這個嚮導，以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="6900f-169">You come back to this wizard in Step 3 to create the connector.</span></span>

## <a name="step-2-configure-the-bloomberg-sftp-site"></a><span data-ttu-id="6900f-170">步驟2：設定 Bloomberg SFTP 網站</span><span class="sxs-lookup"><span data-stu-id="6900f-170">Step 2: Configure the Bloomberg SFTP site</span></span>

> [!NOTE]
> <span data-ttu-id="6900f-171">如先前所述，如果您的組織先前已設定 Bloomberg SFTP 網站封存立即 Bloomberg 資料，您就不需要設定另一個。</span><span class="sxs-lookup"><span data-stu-id="6900f-171">As previously stated, if you're organization has previously set up a Bloomberg SFTP site to archive Instant Bloomberg data, you don't have to set up another one.</span></span> <span data-ttu-id="6900f-172">當您在步驟3中建立連接器時，您可以指定相同的 SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-172">You can specify the same SFTP site when you create the connector in Step 3.</span></span>

<span data-ttu-id="6900f-173">下一步是使用 SSH 和 PGP 公開金鑰和您在步驟1中取得的 IP 位址，為 Bloomberg SFTP 網站設定 SSH 驗證和 PGP 加密。</span><span class="sxs-lookup"><span data-stu-id="6900f-173">The next step is to use the SSH and PGP public keys and the IP address that you obtained in Step 1 to configure SSH authentication and PGP encryption for the Bloomberg SFTP site.</span></span> <span data-ttu-id="6900f-174">這可讓您在步驟3中建立的 Bloomberg 郵件連接器連線至 Bloomberg SFTP 網站，並將 Bloomberg 郵件資料傳輸至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6900f-174">This lets the Bloomberg Message connector that you create in Step 3 connect to the Bloomberg SFTP site and transfer Bloomberg Message data to Microsoft 365.</span></span> <span data-ttu-id="6900f-175">您需要與 Bloomberg 客戶支援合作，以設定 Bloomberg SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-175">You need to work with Bloomberg customer support to set up your Bloomberg SFTP site.</span></span> <span data-ttu-id="6900f-176">請與 [Bloomberg 客戶支援](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 部門聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="6900f-176">Contact [Bloomberg customer support](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) for assistance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6900f-177">Bloomberg 建議您將您在步驟1中下載的三個檔案附加到電子郵件訊息，並將其傳送給他們的客戶支援小組，以設定 Bloomberg SFTP 網站時使用這些檔案。</span><span class="sxs-lookup"><span data-stu-id="6900f-177">Bloomberg recommends that you attach the three files that you downloaded in Step 1 to an email message and send it to their customer support team when working with them to set up your Bloomberg SFTP site.</span></span>

## <a name="step-3-create-a-bloomberg-message-connector"></a><span data-ttu-id="6900f-178">步驟3：建立 Bloomberg 郵件連接器</span><span class="sxs-lookup"><span data-stu-id="6900f-178">Step 3: Create a Bloomberg Message connector</span></span>

<span data-ttu-id="6900f-179">最後一個步驟是在 Microsoft 365 規範中心建立 Bloomberg 郵件連接器。</span><span class="sxs-lookup"><span data-stu-id="6900f-179">The last step is to create a Bloomberg Message connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6900f-180">連接器會使用您提供的資訊來連線至 Bloomberg SFTP 網站，並將電子郵件傳送至 Microsoft 365 中對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="6900f-180">The connector uses the information you provide to connect to the Bloomberg SFTP site and transfer email messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="6900f-181">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="6900f-181">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="6900f-182">在 [ **Bloomberg 郵件**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="6900f-182">On the **Data connectors** page under **Bloomberg Message**, click **View**.</span></span>

3. <span data-ttu-id="6900f-183">在 [ **Bloomberg 訊息** 產品描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="6900f-183">On the **Bloomberg Message** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="6900f-184">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="6900f-184">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="6900f-185">在 [ **新增 BLOOMBERG SFTP 網站的認證** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6900f-185">On the **Add credentials for Bloomberg SFTP site** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

      - <span data-ttu-id="6900f-186">**確認程式碼：** 組織的識別碼，用作 Bloomberg SFTP 網站的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="6900f-186">**Firm code:** The ID for your organization that is used as the username for the Bloomberg SFTP site.</span></span>

      - <span data-ttu-id="6900f-187">**密碼：** 組織之 Bloomberg SFTP 網站的密碼。</span><span class="sxs-lookup"><span data-stu-id="6900f-187">**Password:** The password for your organization's Bloomberg SFTP site.</span></span>

      - <span data-ttu-id="6900f-188">**SFTP URL:** Bloomberg SFTP 網站的 URL (例如，sftp.bloomberg.com) 。</span><span class="sxs-lookup"><span data-stu-id="6900f-188">**SFTP URL:** The URL for the Bloomberg SFTP site (for example, sftp.bloomberg.com).</span></span>

      - <span data-ttu-id="6900f-189">**SFTP 埠：** Bloomberg SFTP 網站的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="6900f-189">**SFTP port:** The port number for the Bloomberg SFTP site.</span></span> <span data-ttu-id="6900f-190">連接器會使用此埠連接到 SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="6900f-190">The connector uses this port to connect to the SFTP site.</span></span>

6. <span data-ttu-id="6900f-191">在 [ **使用者對應** ] 頁面上，啟用自動使用者對應，並視需要提供自訂使用者對應</span><span class="sxs-lookup"><span data-stu-id="6900f-191">On the **User-mapping** page, enable automatic user mapping and provide custom user mapping as required</span></span>

7. <span data-ttu-id="6900f-192">按 **[下一步]**，複查您的設定，然後按一下 [準備] 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="6900f-192">Click **Next**, review your settings, and then click prepare to create the connector.</span></span>

8. <span data-ttu-id="6900f-193">移至 [ **資料連線器** ] 頁面，查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="6900f-193">Go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6900f-194">已知問題</span><span class="sxs-lookup"><span data-stu-id="6900f-194">Known issues</span></span>

- <span data-ttu-id="6900f-195">不支援匯入 Bloomberg 郵件電子郵件至 Microsoft 365 的執行緒。</span><span class="sxs-lookup"><span data-stu-id="6900f-195">Threading of Bloomberg Message email imported to Microsoft 365 isn't supported.</span></span> <span data-ttu-id="6900f-196">傳送給個人的個別郵件會匯入，但不會出現線上程交談中。</span><span class="sxs-lookup"><span data-stu-id="6900f-196">Individual messages sent to a person are imported, but they aren't presented in a threaded conversation.</span></span> <span data-ttu-id="6900f-197">Microsoft 正致力於支援 Bloomberg 郵件資料連線器的後續版本中的執行緒。</span><span class="sxs-lookup"><span data-stu-id="6900f-197">Microsoft is working to support threading in later versions of the Bloomberg Message data connector.</span></span>
