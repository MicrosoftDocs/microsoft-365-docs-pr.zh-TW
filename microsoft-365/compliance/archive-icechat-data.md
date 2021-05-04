---
title: 設定連接器以封存「我的冰激淩」聊天資料
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
description: 系統管理員可以設定連接器，將「ICE 聊天」工具中的資料匯入並封存至 Microsoft 365。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，這樣您就可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 958a6dde0a4f23933ef6328719fbf43265420c7c
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077298"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a><span data-ttu-id="8aac6-104">設定連接器以封存「我的冰激淩」聊天資料</span><span class="sxs-lookup"><span data-stu-id="8aac6-104">Set up a connector to archive ICE Chat data</span></span>

<span data-ttu-id="8aac6-105">使用 Microsoft 365 規範中心內的原生連接器，從「ICE 聊天共同作業」工具匯入及封存金融服務聊天資料。</span><span class="sxs-lookup"><span data-stu-id="8aac6-105">Use a native connector in the Microsoft 365 compliance center to import and archive financial services chat data from the ICE Chat collaboration tool.</span></span> <span data-ttu-id="8aac6-106">在您設定及設定連接器之後，它會連線到您組織的冰激淩聊天安全 FTP (SFTP) 網站一次，將聊天訊息的內容轉換成電子郵件格式，然後將這些專案匯入 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-106">After you set up and configure a connector, it connects to your organization's ICE Chat secure FTP (SFTP) site once every day, converts the content of chat messages to an email message format, and then import those items to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="8aac6-107">將「冰聊天」資料儲存在使用者信箱中之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、封存、審核、通訊合規性，以及 Microsoft 365 保留原則，以用於冰聊天資料。</span><span class="sxs-lookup"><span data-stu-id="8aac6-107">After ICE chat data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as litigation hold, eDiscovery, archiving, auditing, communication compliance, and Microsoft 365 retention policies to ICE Chat data.</span></span> <span data-ttu-id="8aac6-108">例如，您可以使用內容搜尋來搜尋「ice 聊天」訊息，或在 Advanced eDiscovery 案例中，將包含 ICE 聊天資料的信箱與保管人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="8aac6-108">For example, you can search ICE Chat messages using content search or associate the mailbox that contains the ICE Chat data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="8aac6-109">使用 ICE 聊天連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="8aac6-109">Using an ICE Chat connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ice-chat-data"></a><span data-ttu-id="8aac6-110">封存的冰激淩聊天資料</span><span class="sxs-lookup"><span data-stu-id="8aac6-110">Overview of archiving ICE Chat data</span></span>

<span data-ttu-id="8aac6-111">下列概要說明如何使用連接器封存 Microsoft 365 中的「冰交談」資料。</span><span class="sxs-lookup"><span data-stu-id="8aac6-111">The following overview explains the process of using a connector to archive ICE chat data in Microsoft 365.</span></span>

![ICE 聊天封存工作流程](../media/ICEChatConnectorWorkflow.png)

1. <span data-ttu-id="8aac6-113">您的組織可以搭配「ICE 聊天」來設定冰激淩聊天的 SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="8aac6-113">Your organization works with ICE Chat to set up an ICE Chat SFTP site.</span></span> <span data-ttu-id="8aac6-114">您也可以使用 ICE 聊天設定冰激淩聊天，將聊天訊息複製到您的 ICE 聊天網站。</span><span class="sxs-lookup"><span data-stu-id="8aac6-114">You'll also work with ICE Chat to configure ICE Chat to copy chat messages to your ICE Chat SFTP site.</span></span>

2. <span data-ttu-id="8aac6-115">每24小時一次，聊天訊息會複製到您的 ICE 聊天網站。</span><span class="sxs-lookup"><span data-stu-id="8aac6-115">Once every 24 hours, chat messages from ICE Chat are copied to your ICE Chat SFTP site.</span></span>

3. <span data-ttu-id="8aac6-116">您在 Microsoft 365 合規性中心內建立的 ice 聊天連接器會每日連線到「ice 聊天 SFTP」網站，並將聊天訊息從過去24小時內傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="8aac6-116">The ICE Chat connector that you create in the Microsoft 365 compliance center connects to the ICE Chat SFTP site every day and transfers the chat messages from the previous 24 hours to a secure Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="8aac6-117">連接器也會將聊天室 massage 的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="8aac6-117">The connector also converts the content of a chat massage to an email message format.</span></span>

4. <span data-ttu-id="8aac6-118">連接器會將聊天訊息項目匯入到特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-118">The connector imports chat message items to the mailboxes of specific users.</span></span> <span data-ttu-id="8aac6-119">會在使用者信箱中建立名為「 **ICE 聊天** 」的新資料夾，並將聊天訊息項目匯入該資料夾。</span><span class="sxs-lookup"><span data-stu-id="8aac6-119">A new folder named **ICE Chat** is created in the user mailboxes and the chat message items are imported to that folder.</span></span> <span data-ttu-id="8aac6-120">連接器會使用 *SenderEmail* 和 *RecipientEmail* 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="8aac6-120">The connector does by using the value of the *SenderEmail* and *RecipientEmail* properties.</span></span> <span data-ttu-id="8aac6-121">每個聊天訊息都包含這些內容，這些屬性會填入寄件者的電子郵件地址，以及聊天訊息的每個收件者/參與者。</span><span class="sxs-lookup"><span data-stu-id="8aac6-121">Every chat message contains these properties, which are populated with email address of the sender and every recipient/participant of the chat message.</span></span>

   <span data-ttu-id="8aac6-122">除了使用 *SenderEmail* 和 *RecipientEmail* (屬性之值的自動使用者對應，也意味著該連接器會將聊天訊息匯入寄件者的信箱，並將每個收件者) 的信箱匯入，您也可以透過上載 CSV 對應檔來定義自訂使用者對應。</span><span class="sxs-lookup"><span data-stu-id="8aac6-122">In addition to automatic user mapping that uses the values of the *SenderEmail* and *RecipientEmail* property (which means that the connector imports a chat message to the sender's mailbox and the mailboxes of every recipient), you can also define custom user mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="8aac6-123">這個對應檔案包含組織中每位使用者的「冰激淩聊天 *ImId* 」和對應的 Microsoft 365 信箱位址。</span><span class="sxs-lookup"><span data-stu-id="8aac6-123">This mapping file contains the ICE Chat *ImId* and the corresponding Microsoft 365 mailbox address for every user in your organization.</span></span> <span data-ttu-id="8aac6-124">如果您啟用自動使用者對應，並提供自訂對應檔案，則每個聊天專案連接器都會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="8aac6-124">If you enable automatic user mapping and provide a custom-mapping file, for every chat item the connector will first look at the custom-mapping file.</span></span> <span data-ttu-id="8aac6-125">如果找不到與使用者的「交談」 ImId 相對應的有效 Microsoft 365 使用者帳戶，連接器會使用聊天室專案的 *SenderEmail* 和 *RecipientEmail* 屬性，將專案匯入聊天室參與者的信箱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-125">If it doesn't find a valid Microsoft 365 user account that corresponds to a user's ICE Chat ImId, the connector will use the *SenderEmail* and *RecipientEmail* properties of the chat item to import the item to the mailboxes of the chat participants.</span></span> <span data-ttu-id="8aac6-126">如果連接器在自訂對應檔或 *SenderEmail* 及 *RecipientEmail* 屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="8aac6-126">If the connector doesn't find a valid Microsoft 365 user in either the custom-mapping file or the *SenderEmail* and *RecipientEmail* properties, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="8aac6-127">在您設定連接器之前</span><span class="sxs-lookup"><span data-stu-id="8aac6-127">Before you set up a connector</span></span>

<span data-ttu-id="8aac6-128">封存「交談」資料所需的部分執行步驟是 Microsoft 365 外部的，必須先完成，您才能在規範中心建立連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-128">Some of the implementation steps required to archive ICE Chat data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="8aac6-129">冰聊天會向客戶收取外部法規遵從性的費用。</span><span class="sxs-lookup"><span data-stu-id="8aac6-129">ICE Chat charges their customers a fee for external compliance.</span></span> <span data-ttu-id="8aac6-130">您的組織應該聯繫「保密協定研討」銷售群組，以討論和簽署「保密協定聊天資料服務」合約，您可以在這裡取得 [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="8aac6-130">Your organization should contact the ICE Chat sales group to discuss, and to sign the ICE Chat data services agreement, which you can obtain at [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf).</span></span> <span data-ttu-id="8aac6-131">這種合約是在冰聊天和您的組織之間，不包含 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="8aac6-131">This agreement is between ICE Chat and your organization and does not involve Microsoft.</span></span> <span data-ttu-id="8aac6-132">當您在步驟2中設定冰 Chat SFTP 網站之後，「ICE 聊天」會直接向您的組織提供 FTP 認證。</span><span class="sxs-lookup"><span data-stu-id="8aac6-132">After you set up an ICE Chat SFTP site in Step 2, ICE Chat provides the FTP credentials directly to your organization.</span></span> <span data-ttu-id="8aac6-133">然後，當您在步驟3中設定連接器時，會將這些認證提供給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="8aac6-133">Then you who would provide those credentials to Microsoft when setting up the connector in Step 3.</span></span>

- <span data-ttu-id="8aac6-134">在步驟3中建立連接器之前，您必須先設定 ICE 聊天 SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="8aac6-134">You must set up an ICE Chat SFTP site before creating the connector in Step 3.</span></span> <span data-ttu-id="8aac6-135">在使用「ICE 聊天」設定 SFTP 網站之後，每日會將 ICE 聊天中的資料上傳到 SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="8aac6-135">After working with ICE Chat to set up the SFTP site, data from ICE Chat is uploaded to the SFTP site every day.</span></span> <span data-ttu-id="8aac6-136">您在步驟3中建立的連接器會連接到此 SFTP 網站，並將聊天資料傳送至 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-136">The connector you create in Step 3 connects to this SFTP site and transfers the chat data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="8aac6-137">SFTP 也會加密在傳輸過程中傳送至信箱的 ICE 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="8aac6-137">SFTP also encrypts the ICE Chat data that's sent to mailboxes during the transfer process.</span></span>

- <span data-ttu-id="8aac6-138">若要設定 ICE 聊天連接器，您必須使用金鑰和金鑰密碼短語，以取得非常好的隱私權 (PGP) 和安全命令介面 (SSH) 。</span><span class="sxs-lookup"><span data-stu-id="8aac6-138">To set up an ICE Chat connector, you have to use keys and key passphrases for Pretty Good Privacy (PGP) and Secure Shell (SSH).</span></span> <span data-ttu-id="8aac6-139">這些機碼是用來設定冰激淩聊天 SFTP 網站，並由連接器用來連接到「ICE 聊天 SFTP」網站，將資料匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8aac6-139">These keys are used to configure the ICE Chat SFTP site and used by the connector to connect to the ICE Chat SFTP site to import data to Microsoft 365.</span></span> <span data-ttu-id="8aac6-140">PGP 金鑰是用來設定從「ICE 聊天 SFTP」網站傳輸到 Microsoft 365 的資料加密。</span><span class="sxs-lookup"><span data-stu-id="8aac6-140">The PGP key is used to configure the encryption of data that's transferred from the ICE Chat SFTP site to Microsoft 365.</span></span> <span data-ttu-id="8aac6-141">SSH 金鑰是用來設定安全命令介面，以在連接器連線至 ICE 聊天 SFTP 網站時，啟用安全的遠端登入。</span><span class="sxs-lookup"><span data-stu-id="8aac6-141">The SSH key is used to configure secure shell to enable a secure remote login when the connector connects to the ICE Chat SFTP site.</span></span>

  <span data-ttu-id="8aac6-142">當您設定連接器時，可以選擇使用 Microsoft 提供的公開金鑰和金鑰密碼，也可以使用您自己的私密金鑰和密碼。</span><span class="sxs-lookup"><span data-stu-id="8aac6-142">When setting up a connector, you have the option to use public keys and key passphrases provided by Microsoft or you can use your own private keys and passphrases.</span></span> <span data-ttu-id="8aac6-143">建議您使用 Microsoft 提供的公用金鑰。</span><span class="sxs-lookup"><span data-stu-id="8aac6-143">We recommend that you use the public keys provided by Microsoft.</span></span> <span data-ttu-id="8aac6-144">不過，如果您的組織已使用私密金鑰設定了 ICE 聊天 SFTP 網站，則可以使用這些相同的私密金鑰建立連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-144">However, if your organization has already configured an ICE Chat SFTP site using private keys, then you can create a connector using these same private keys.</span></span>

- <span data-ttu-id="8aac6-145">「ICE 聊天連接器」可以在一天內匯入200000項總計。</span><span class="sxs-lookup"><span data-stu-id="8aac6-145">The ICE Chat connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="8aac6-146">如果 SFTP 網站上的專案超過200000個，將不會將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8aac6-146">If there are more than 200,000 items on the SFTP site, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="8aac6-147">在步驟 3 (及下載步驟 1) 中的公開金鑰及 IP 位址的系統管理員，必須在 Exchange Online 中指派「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="8aac6-147">The admin who creates the ICE Chat connector in Step 3 (and who downloads the public keys and IP address in Step 1) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="8aac6-148">在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。</span><span class="sxs-lookup"><span data-stu-id="8aac6-148">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8aac6-149">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="8aac6-149">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="8aac6-150">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="8aac6-150">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="8aac6-151">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="8aac6-151">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="8aac6-152">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。</span><span class="sxs-lookup"><span data-stu-id="8aac6-152">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="set-up-a-connector-using-public-keys"></a><span data-ttu-id="8aac6-153">使用公開金鑰設定連接器</span><span class="sxs-lookup"><span data-stu-id="8aac6-153">Set up a connector using public keys</span></span>

<span data-ttu-id="8aac6-154">本節中的步驟將告訴您如何使用適用于極佳隱私權 (PGP) 和安全命令介面 (SSH) 的公開金鑰來設定 ICE 聊天連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-154">The steps in this section show you how to set up an ICE Chat connector using the public keys for Pretty Good Privacy (PGP) and Secure Shell (SSH).</span></span>

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a><span data-ttu-id="8aac6-155">步驟1：取得 PGP 和 SSH 公開金鑰</span><span class="sxs-lookup"><span data-stu-id="8aac6-155">Step 1: Obtain PGP and SSH public keys</span></span>

<span data-ttu-id="8aac6-156">第一步是取得正確隱私權的公開金鑰複本 (PGP) 和安全命令介面 (SSH) 。</span><span class="sxs-lookup"><span data-stu-id="8aac6-156">The first step is to obtain a copy of the public keys for Pretty Good Privacy (PGP) and Secure Shell (SSH).</span></span> <span data-ttu-id="8aac6-157">您可以在步驟2中使用這些機碼，將「ice 聊天 SFTP」網站設定為允許您在步驟) 3 中建立的連接器 (，以連線到 SFTP 網站，並將「ICE 聊天」資料轉接至 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-157">You use these keys in Step 2 to configure the ICE Chat SFTP site to allow the connector (that you create in Step 3) to connect to the SFTP site and transfer the ICE Chat data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="8aac6-158">您也會在此步驟中取得 IP 位址，當您設定 ICE 聊天 SFTP 網站時，您可以使用此位址。</span><span class="sxs-lookup"><span data-stu-id="8aac6-158">You will also obtain an IP address in this step, which you use when configuring the ICE Chat SFTP site.</span></span>

1. <span data-ttu-id="8aac6-159">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-159">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8aac6-160">在 [**冰激淩聊天**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-160">On the **Data connectors** page under **ICE Chat**, click **View**.</span></span>

3. <span data-ttu-id="8aac6-161">在 [ **ICE 聊天** ] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-161">On the **ICE Chat** page, click **Add connector**.</span></span>

4. <span data-ttu-id="8aac6-162">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-162">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="8aac6-163">在 [ **新增內容來源的認證** ] 頁面上，按一下 [ **我想要使用 MICROSOFT 提供的 PGP 和 SSH 公開金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-163">On the **Add credentials for content source** page, click **I want to use PGP and SSH public keys provided by Microsoft**.</span></span>

   ![選取使用公開金鑰的選項](../media/ICEChatPublicKeysOption.png)

6. <span data-ttu-id="8aac6-165">在 [步驟 1] 下，按一下 [ **下載 SSH 金鑰**]、[ **下載 PGP 金鑰**] 和 [ **下載 IP 位址** ] 連結，將每個檔案的副本儲存到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="8aac6-165">Under step 1, click the **Download SSH key**, **Download PGP key**, and **Download IP address** links to save a copy of each file to your local computer.</span></span>

   ![下載公開金鑰及 IP 位址的連結](../media/ICEChatPublicKeyDownloadLinks.png)

   <span data-ttu-id="8aac6-167">這些檔案包含下列專案，可用來設定步驟2中的 ICE 聊天 SFTP 網站：</span><span class="sxs-lookup"><span data-stu-id="8aac6-167">These files contain the following items that are used to configure the ICE Chat SFTP site in Step 2:</span></span>

   - <span data-ttu-id="8aac6-168">PGP 公開金鑰：此機碼是用來設定從「ICE 聊天 SFTP」網站傳輸到 Microsoft 365 的資料加密。</span><span class="sxs-lookup"><span data-stu-id="8aac6-168">PGP public key: This key is used to configure the encryption of data that's transferred from the ICE Chat SFTP site to Microsoft 365.</span></span>

   - <span data-ttu-id="8aac6-169">SSH 公開金鑰：此機碼用於設定安全的 SSH，以在連接器連線至 ICE 聊天 SFTP 網站時，啟用安全的遠端登入。</span><span class="sxs-lookup"><span data-stu-id="8aac6-169">SSH public key: This key is used to configure Secure SSH to enable a secure remote login when the connector connects to the ICE Chat SFTP site.</span></span>

   - <span data-ttu-id="8aac6-170">IP 位址：「ICE 聊天 SFTP」網站已設定為只接受來自此 IP 位址的連線要求，該要求是由您在步驟3中建立的 ICE 聊天連接器所使用。</span><span class="sxs-lookup"><span data-stu-id="8aac6-170">IP address: The ICE Chat SFTP site is configured to accept a connection request only from this IP address, which is used by the ICE Chat connector that you create in Step 3.</span></span>

7. <span data-ttu-id="8aac6-171">按一下 [ **取消** ] 關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="8aac6-171">Click **Cancel** to close the wizard.</span></span> <span data-ttu-id="8aac6-172">您會回到步驟3中的這個嚮導，以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-172">You come back to this wizard in Step 3 to create the connector.</span></span>

### <a name="step-2-configure-the-ice-chat-sftp-site"></a><span data-ttu-id="8aac6-173">步驟2：設定 ICE 聊天 SFTP 網站</span><span class="sxs-lookup"><span data-stu-id="8aac6-173">Step 2: Configure the ICE Chat SFTP site</span></span>

<span data-ttu-id="8aac6-174">下一個步驟是使用您在步驟1中取得的 PGP 和 SSH 公開金鑰及 IP 位址，來設定用於 ICE 聊天室網站的 PGP 加密和 SSH 驗證。</span><span class="sxs-lookup"><span data-stu-id="8aac6-174">The next step is to use the PGP and SSH public keys and the IP address that you obtained in Step 1 to configure PGP encryption and SSH authentication for the ICE Chat SFTP site.</span></span> <span data-ttu-id="8aac6-175">這可讓您在步驟3中建立的 ICE 聊天連接器連線到「ICE 聊天 SFTP」網站，並將「冰交談」資料轉接至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8aac6-175">This lets the ICE Chat connector that you create in Step 3 connect to the ICE Chat SFTP site and transfer ICE Chat data to Microsoft 365.</span></span> <span data-ttu-id="8aac6-176">您必須使用 [ICE 聊天] 客戶支援來設定您的冰激淩聊天網站。</span><span class="sxs-lookup"><span data-stu-id="8aac6-176">You need to work with ICE Chat customer support to set up your ICE Chat SFTP site.</span></span>

### <a name="step-3-create-an-ice-chat-connector"></a><span data-ttu-id="8aac6-177">步驟3：建立 ICE 聊天連接器</span><span class="sxs-lookup"><span data-stu-id="8aac6-177">Step 3: Create an ICE Chat connector</span></span>

<span data-ttu-id="8aac6-178">最後一個步驟是在 Microsoft 365 規範中心建立 ICE 聊天連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-178">The last step is to create an ICE Chat connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8aac6-179">連接器會使用您提供的資訊來連線至「ICE 聊天 SFTP」網站，並將交談郵件轉接至 Microsoft 365 中對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="8aac6-179">The connector uses the information you provide to connect to the ICE Chat SFTP site and transfer chat messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="8aac6-180">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-180">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8aac6-181">在 [**冰激淩聊天**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-181">On the **Data connectors** page under **ICE Chat**, click **View**.</span></span>

3. <span data-ttu-id="8aac6-182">在 [ **ICE 聊天** ] 頁面上，按一下 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-182">On the **ICE Chat** page, click **Add connector**.</span></span>

4. <span data-ttu-id="8aac6-183">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-183">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="8aac6-184">在 [ **新增內容來源的認證** ] 頁面上，按一下 [ **我想要使用 PGP 和 SSH 公開金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-184">On the **Add credentials for content source** page, click **I want to use PGP and SSH public keys**.</span></span>

6. <span data-ttu-id="8aac6-185">在 [步驟 3] 底下的下列方塊中，輸入必要的資訊，然後按一下 [ **驗證** 連線]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-185">Under Step 3, enter the required information in the following boxes and then click **Validate connection**.</span></span>

   - <span data-ttu-id="8aac6-186">**確認程式碼：** 您的組織的識別碼，用來做為 ICE 聊天 SFTP 網站的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-186">**Firm code:** The ID for your organization, which is used as the username for the ICE Chat SFTP site.</span></span>

   - <span data-ttu-id="8aac6-187">**密碼：** 您的 ICE 聊天 SFTP 網站的密碼。</span><span class="sxs-lookup"><span data-stu-id="8aac6-187">**Password:** The password for your ICE Chat SFTP site.</span></span>

   - <span data-ttu-id="8aac6-188">**SFTP URL:** 「冰聊天 SFTP」網站的 URL (例如， `sftp.theice.com`) 。</span><span class="sxs-lookup"><span data-stu-id="8aac6-188">**SFTP URL:** The URL for the ICE Chat SFTP site (for example, `sftp.theice.com`).</span></span> <span data-ttu-id="8aac6-189">您也可以使用此值的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8aac6-189">You can also use an IP address for this value.</span></span>

   - <span data-ttu-id="8aac6-190">**SFTP 埠：** ICE 聊天 SFTP 網站的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="8aac6-190">**SFTP port:** The port number for the ICE Chat SFTP site.</span></span> <span data-ttu-id="8aac6-191">連接器會使用此埠連接到 SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="8aac6-191">The connector uses this port to connect to the SFTP site.</span></span>

7. <span data-ttu-id="8aac6-192">成功驗證成功後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8aac6-192">After the connection is successfully validated, click **Next**.</span></span>

8. <span data-ttu-id="8aac6-193">在 [將 **外部使用者對應至 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]，並視需要提供自訂使用者對應。</span><span class="sxs-lookup"><span data-stu-id="8aac6-193">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping and provide custom user mapping as required.</span></span> <span data-ttu-id="8aac6-194">您可以在此頁面上下載使用者對應的 CSV 檔案複本。</span><span class="sxs-lookup"><span data-stu-id="8aac6-194">You can download a copy of the user-mapping CSV file on this page.</span></span> <span data-ttu-id="8aac6-195">您可以將使用者對應新增至檔案，然後將其上傳。</span><span class="sxs-lookup"><span data-stu-id="8aac6-195">You can add the user mappings to the file and then upload it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8aac6-196">如先前所述，自訂對應檔 CSV 檔案包含每位使用者的「ICE 聊天 imid」和對應的 Microsoft 365 信箱位址。</span><span class="sxs-lookup"><span data-stu-id="8aac6-196">As previously explained, custom mapping file CSV file contains the ICE Chat imid and corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="8aac6-197">如果您啟用自動使用者對應，並提供每個聊天室專案的自訂對應，連接器會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="8aac6-197">If you enable automatic user mapping and provide a custom mapping, for every chat item, the connector will first look at custom mapping file.</span></span> <span data-ttu-id="8aac6-198">如果找不到與使用者的「交談」 imid 相對應的有效 Microsoft 365 使用者，連接器會將該專案匯入至聊天室專案的 *SenderEmail* 和 *RecipientEmail* 屬性中所指定之使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-198">If it doesn't find a valid Microsoft 365 user that corresponds to a user's ICE Chat imid, the connector will import the item to the mailboxes for the users specified in the *SenderEmail* and *RecipientEmail* properties of the chat item.</span></span> <span data-ttu-id="8aac6-199">如果連接器沒有透過自動或自訂使用者對應找到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="8aac6-199">If the connector doesn't find a valid Microsoft 365 user by either automatic or custom user mapping, the item won't be imported.</span></span>

9. <span data-ttu-id="8aac6-200">按 **[下一步]**，複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-200">Click **Next**, review your settings, and then click **Finish** to create the connector.</span></span>

10. <span data-ttu-id="8aac6-201">移至 [ **資料連線器** ] 頁面，查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="8aac6-201">Go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="set-up-a-connector-using-private-keys"></a><span data-ttu-id="8aac6-202">使用私密金鑰設定連接器</span><span class="sxs-lookup"><span data-stu-id="8aac6-202">Set up a connector using private keys</span></span>

<span data-ttu-id="8aac6-203">本節中的步驟說明如何使用 PGP 和 SSH 私密金鑰設定 ICE 聊天連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-203">The steps in this section show you how to set up an ICE Chat connector using PGP and SSH private keys.</span></span> <span data-ttu-id="8aac6-204">此連接器設定選項適用于已使用私密金鑰設定冰聊天 SFTP 網站的組織。</span><span class="sxs-lookup"><span data-stu-id="8aac6-204">This connector setup option is intended for organizations that have already configured an ICE Chat SFTP site using private keys.</span></span>

### <a name="step-1-obtain-an-ip-address-to-configure-the-ice-chat-sftp-site"></a><span data-ttu-id="8aac6-205">步驟1：取得 IP 位址以設定 ICE 聊天 SFTP 網站</span><span class="sxs-lookup"><span data-stu-id="8aac6-205">Step 1: Obtain an IP address to configure the ICE Chat SFTP site</span></span>

<span data-ttu-id="8aac6-206">如果您的組織已使用 PGP 和 SSH 私密金鑰來設定 ICE 聊天室網站，則您必須取得 IP 位址，並提供給「ICE 聊天客戶支援」。</span><span class="sxs-lookup"><span data-stu-id="8aac6-206">If your organization has used PGP and SSH private keys to set up an ICE Chat SFTP site, then you have to obtain an IP address and provide it to ICE Chat customer support.</span></span> <span data-ttu-id="8aac6-207">必須將「ICE 聊天 SFTP」網站設定為接受來自此 IP 位址的連線要求。</span><span class="sxs-lookup"><span data-stu-id="8aac6-207">The ICE Chat SFTP site must be configured to accept  connection requests from this IP address.</span></span> <span data-ttu-id="8aac6-208">「ICE 聊天連接器」會使用相同的 IP 位址來連線到 SFTP 網站，並將「ICE 聊天」資料轉接至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8aac6-208">The same IP address is used by the ICE Chat connector to connect to the SFTP site and transfer ICE Chat data to Microsoft 365.</span></span>

<span data-ttu-id="8aac6-209">若要取得 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="8aac6-209">To obtain the IP address:</span></span>

1. <span data-ttu-id="8aac6-210">移至 <https://compliance.microsoft.com> 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-210">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8aac6-211">在 [**冰激淩聊天**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-211">On the **Data connectors** page under **ICE Chat**, click **View**.</span></span>

3. <span data-ttu-id="8aac6-212">在 [ **ICE 聊天** 產品描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="8aac6-212">On the **ICE Chat** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="8aac6-213">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-213">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="8aac6-214">在 [ **新增內容來源的認證** ] 頁面上，按一下 [ **我想要使用 PGP 和 SSH 私密金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-214">On the **Add credentials for content source** page, click **I want to use PGP and SSH private keys**.</span></span>

   ![選取使用私密金鑰的選項](../media/ICEChatPrivateKeysOption.png)

6. <span data-ttu-id="8aac6-216">在 [步驟 1] 底下，按一下 [ **下載 ip 位址** ]，將 ip 位址檔案的副本儲存到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="8aac6-216">Under step 1, click **Download IP address** to save a copy of the IP address file to your local computer.</span></span>

   ![下載 IP 位址](../media/ICEChatConnectorIPAddress.png)

7. <span data-ttu-id="8aac6-218">按一下 [ **取消** ] 關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="8aac6-218">Click **Cancel** to close the wizard.</span></span> <span data-ttu-id="8aac6-219">您會回到步驟2中的這個嚮導，以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-219">You come back to this wizard in Step 2 to create the connector.</span></span>

<span data-ttu-id="8aac6-220">您必須使用 ICE 聊天客戶支援，設定您的 ICE 聊天 SFTP 網站，以接受來自此 IP 位址的連線要求。</span><span class="sxs-lookup"><span data-stu-id="8aac6-220">You need to work with ICE Chat customer support to configure your ICE Chat SFTP site to accept connection requests from this IP address.</span></span>

### <a name="step-2-create-an-ice-chat-connector"></a><span data-ttu-id="8aac6-221">步驟2：建立 ICE 聊天連接器</span><span class="sxs-lookup"><span data-stu-id="8aac6-221">Step 2: Create an ICE Chat connector</span></span>

<span data-ttu-id="8aac6-222">設定您的 ICE 聊天 SFTP 網站後，下一步是在 Microsoft 365 規範中心建立 ICE 聊天連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-222">After your ICE Chat SFTP site is configured, the next step is to create an ICE Chat connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8aac6-223">連接器會使用您提供的資訊來連線至「ICE 聊天 SFTP」網站，並將電子郵件傳送至 Microsoft 365 中對應的使用者信箱方塊。</span><span class="sxs-lookup"><span data-stu-id="8aac6-223">The connector uses the information you provide to connect to the ICE Chat SFTP site and transfer email messages to the corresponding user mailbox boxes in Microsoft 365.</span></span> <span data-ttu-id="8aac6-224">若要完成此步驟，請務必具有您用來設定您的冰激淩聊天 SFTP 網站之相同私密金鑰和金鑰密碼的副本。</span><span class="sxs-lookup"><span data-stu-id="8aac6-224">To complete this step, be sure to have copies of the same private keys and key passphrases that you used to set up your ICE Chat SFTP site.</span></span>

1. <span data-ttu-id="8aac6-225">移至 <https://compliance.microsoft.com> 並按一下左側導覽中的 [ **資料連線器** ]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-225">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8aac6-226">在 [**冰激淩聊天**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-226">On the **Data connectors** page under **ICE Chat**, click **View**.</span></span>

3. <span data-ttu-id="8aac6-227">在 [ **ICE 聊天** 產品描述] 頁面上，按一下 [**新增連接器**]</span><span class="sxs-lookup"><span data-stu-id="8aac6-227">On the **ICE Chat** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="8aac6-228">在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-228">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="8aac6-229">在 [ **新增內容來源的認證** ] 頁面上，按一下 [ **我想要使用 PGP 和 SSH 私密金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-229">On the **Add credentials for content source** page, click **I want to use PGP and SSH private keys**.</span></span>

6. <span data-ttu-id="8aac6-230">在 [步驟 3] 底下的下列方塊中，輸入必要的資訊，然後按一下 [ **驗證** 連線]。</span><span class="sxs-lookup"><span data-stu-id="8aac6-230">Under Step 3, enter the required information in the following boxes and then click **Validate connection**.</span></span>

      - <span data-ttu-id="8aac6-231">**名稱：** 連接器的名稱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-231">**Name:** The name for the connector.</span></span> <span data-ttu-id="8aac6-232">它在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8aac6-232">It must be unique in your organization.</span></span>

      - <span data-ttu-id="8aac6-233">**確認程式碼：** 組織的識別碼，用來做為冰激淩的「聊天 SFTP」網站的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-233">**Firm code:** The ID for your organization that is used as the username for the ICE Chat SFTP site.</span></span>

      - <span data-ttu-id="8aac6-234">**密碼：** 組織的冰激淩聊天網站的密碼。</span><span class="sxs-lookup"><span data-stu-id="8aac6-234">**Password:** The password for your organization's ICE Chat SFTP site.</span></span>

      - <span data-ttu-id="8aac6-235">**SFTP URL:** 「冰聊天 SFTP」網站的 URL (例如， `sftp.theice.com`) 。</span><span class="sxs-lookup"><span data-stu-id="8aac6-235">**SFTP URL:** The URL for the ICE Chat SFTP site (for example, `sftp.theice.com`).</span></span> <span data-ttu-id="8aac6-236">您也可以使用此值的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8aac6-236">You can also use an IP address for this value.</span></span>

      - <span data-ttu-id="8aac6-237">**SFTP 埠：** ICE 聊天 SFTP 網站的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="8aac6-237">**SFTP port:** The port number for the ICE Chat SFTP site.</span></span> <span data-ttu-id="8aac6-238">連接器會使用此埠連接到 SFTP 網站。</span><span class="sxs-lookup"><span data-stu-id="8aac6-238">The connector uses this port to connect to the SFTP site.</span></span>

      - <span data-ttu-id="8aac6-239">**PGP 私密金鑰：** 冰激淩聊天室網站的 PGP 私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="8aac6-239">**PGP private key:** The PGP private key for the ICE Chat SFTP site.</span></span> <span data-ttu-id="8aac6-240">請務必加入整個私密金鑰值，包括按鍵區塊的開始和結束行。</span><span class="sxs-lookup"><span data-stu-id="8aac6-240">Be sure to include the entire private key value, including the beginning and ending lines of the key block.</span></span>

      - <span data-ttu-id="8aac6-241">**PGP 金鑰複雜密碼：** PGP 私密金鑰的複雜密碼。</span><span class="sxs-lookup"><span data-stu-id="8aac6-241">**PGP key passphrase:** The passphrase for the PGP private key.</span></span>

      - <span data-ttu-id="8aac6-242">**SSH 私密金鑰：** ICE 聊天室網站的 SSH 私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="8aac6-242">**SSH private key:** The SSH private key for the ICE Chat SFTP site.</span></span> <span data-ttu-id="8aac6-243">請務必加入整個私密金鑰值，包括按鍵區塊的開始和結束行。</span><span class="sxs-lookup"><span data-stu-id="8aac6-243">Be sure to include the entire private key value, including the beginning and ending lines of the key block.</span></span>

      - <span data-ttu-id="8aac6-244">**SSH 金鑰密碼短語：** SSH 私密金鑰的複雜密碼。</span><span class="sxs-lookup"><span data-stu-id="8aac6-244">**SSH key passphrase:** The passphrase for the SSH private key.</span></span>

7. <span data-ttu-id="8aac6-245">成功驗證成功後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8aac6-245">After the connection is successfully validated, click **Next**.</span></span>

8. <span data-ttu-id="8aac6-246">在 [將 **ICE 聊天使用者 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]，並視需要提供自訂使用者對應。</span><span class="sxs-lookup"><span data-stu-id="8aac6-246">On the **Map ICE Chat users to Microsoft 365 users** page, enable automatic user mapping and provide custom user mapping as required.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8aac6-247">如先前所述，自訂對應檔 CSV 檔案包含每位使用者的「ICE 聊天 imid」和對應的 Microsoft 365 信箱位址。</span><span class="sxs-lookup"><span data-stu-id="8aac6-247">As previously explained, custom mapping file CSV file contains the ICE Chat imid and corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="8aac6-248">如果您啟用自動使用者對應，並提供每個聊天室專案的自訂對應，連接器會先查看自訂對應檔案。</span><span class="sxs-lookup"><span data-stu-id="8aac6-248">If you enable automatic user mapping and provide a custom mapping, for every chat item, the connector will first look at custom mapping file.</span></span> <span data-ttu-id="8aac6-249">如果找不到與使用者的「交談」 imid 相對應的有效 Microsoft 365 使用者，連接器會將該專案匯入至聊天室專案的 *SenderEmail* 和 *RecipientEmail* 屬性中所指定之使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="8aac6-249">If it doesn't find a valid Microsoft 365 user that corresponds to a user's ICE Chat imid, the connector will import the item to the mailboxes for the users specified in the *SenderEmail* and *RecipientEmail* properties of the chat item.</span></span> <span data-ttu-id="8aac6-250">如果連接器沒有透過自動或自訂使用者對應找到有效的 Microsoft 365 使用者，則不會匯入該專案。</span><span class="sxs-lookup"><span data-stu-id="8aac6-250">If the connector doesn't find a valid Microsoft 365 user by either automatic or custom user mapping, the item won't be imported.</span></span>

9. <span data-ttu-id="8aac6-251">按 **[下一步]**，複查您的設定，然後按一下 **[完成]** 以建立連接器。</span><span class="sxs-lookup"><span data-stu-id="8aac6-251">Click **Next**, review your settings, and then click **Finish** to create the connector.</span></span>

10. <span data-ttu-id="8aac6-252">移至 [ **資料連線器** ] 頁面，查看新連接器的匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="8aac6-252">Go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span> <span data-ttu-id="8aac6-253">按一下連接線以顯示飛出頁面，該頁面包含連接器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8aac6-253">Click the connector to display the flyout page, which contains information about the connector.</span></span>
