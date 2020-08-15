---
title: 使用 PowerShell 將 IMAP 移轉至 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: 瞭解如何使用 PowerShell 來執行網際網路郵件存取通訊協定 (IMAP) 遷移至 Microsoft 365。
ms.openlocfilehash: 6eb422455d0bdf31fa1859bd0231b68e5568748c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688674"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="42d4f-103">使用 PowerShell 將 IMAP 移轉至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42d4f-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="42d4f-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="42d4f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="42d4f-105">在部署 Microsoft 365 的過程中，您可以選擇將使用者信箱的內容從網際網路郵件存取通訊協定（ (IMAP) 電子郵件服務）遷移到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="42d4f-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="42d4f-106">本文會引導您使用 Exchange Online PowerShell 來進行電子郵件 IMAP 移轉的工作。</span><span class="sxs-lookup"><span data-stu-id="42d4f-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="42d4f-107">您也可以使用 Exchange 系統管理中心來執行 IMAP 移轉。</span><span class="sxs-lookup"><span data-stu-id="42d4f-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="42d4f-108">請參閱 [遷移 IMAP 信箱](https://go.microsoft.com/fwlink/p/?LinkId=536685)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-108">See [Migrate your IMAP mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=536685).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="42d4f-109">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="42d4f-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="42d4f-110">完成此工作的預估時間：2-5 分鐘來建立遷移批次。</span><span class="sxs-lookup"><span data-stu-id="42d4f-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="42d4f-111">啟動移轉批次之後，移轉所需的時間會依批次中的信箱數目、每個信箱的大小和可用的網路容量而有所不同。</span><span class="sxs-lookup"><span data-stu-id="42d4f-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="42d4f-112">如需其他影響將信箱遷移至 Microsoft 365 的因素的詳細資訊，請參閱 [遷移效能](https://go.microsoft.com/fwlink/p/?LinkId=275079)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="42d4f-p104">您必須已獲指派的權限，才能執行此程序。若要查看您需要哪些權限，請參閱[收件者權限](https://go.microsoft.com/fwlink/p/?LinkId=534105)主題中所含表格的「移轉」項目。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="42d4f-p105">若要使用 Exchange Online PowerShell Cmdlet，您需要登入系統，並將 Cmdlet 匯入您的本機 Windows PowerShell 工作階段。請參閱[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121) 的指示。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="42d4f-117">若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=534750)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-117">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="42d4f-118">下列限制適用於 IMAP 移轉：</span><span class="sxs-lookup"><span data-stu-id="42d4f-118">The following restrictions apply to IMAP migrations:</span></span>
  
- <span data-ttu-id="42d4f-p106">僅能移轉使用者收件匣或其他郵件資料夾中的項目。您無法移轉連絡人、行事曆項目或工作。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p106">Only items in a user's inbox or other mail folders can be migrated. You can't migrate contacts, calendar items, or tasks.</span></span>
    
- <span data-ttu-id="42d4f-121">最多只能從使用者信箱移轉 500,000 個項目。</span><span class="sxs-lookup"><span data-stu-id="42d4f-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>
    
- <span data-ttu-id="42d4f-122">可移轉的郵件大小上限為 35 MB。</span><span class="sxs-lookup"><span data-stu-id="42d4f-122">The maximum message size that can be migrated is 35 MB.</span></span>
    
## <a name="migration-steps"></a><span data-ttu-id="42d4f-123">移轉步驟</span><span class="sxs-lookup"><span data-stu-id="42d4f-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="42d4f-124">步驟 1：準備進行 IMAP 移轉</span><span class="sxs-lookup"><span data-stu-id="42d4f-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="42d4f-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="42d4f-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="42d4f-126">**如果您有 IMAP 組織的網域，請將其新增為 Microsoft 365 組織的公認網域。**</span><span class="sxs-lookup"><span data-stu-id="42d4f-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="42d4f-127">如果您想要使用您的 Microsoft 365 信箱已經擁有的相同網域，您必須先將其新增為 Microsoft 365 的公認網域。</span><span class="sxs-lookup"><span data-stu-id="42d4f-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="42d4f-128">新增後，您可以在 Microsoft 365 中建立使用者。</span><span class="sxs-lookup"><span data-stu-id="42d4f-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="42d4f-129">如需詳細資訊，請參閱[驗證您的網域](https://go.microsoft.com/fwlink/p/?LinkId=534110)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-129">For more information, see[Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>
    
- <span data-ttu-id="42d4f-130">**將每位使用者新增至 Microsoft 365，讓他們擁有信箱。**</span><span class="sxs-lookup"><span data-stu-id="42d4f-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="42d4f-131">如需相關指示，請參閱[將使用者新增至 Microsoft 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=535065)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-131">For instructions, see[Add users to Microsoft 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=535065).</span></span>
    
- <span data-ttu-id="42d4f-p109">**取得 IMAP 伺服器的 FQDN**。您必須提供 IMAP 伺服器的完整網域名稱 (FQDN) (也稱為「完整電腦名稱」)，當您建立 IMAP 移轉端點時，將會從此伺服器移轉信箱資料。使用 IMAP 用戶端或 PING 命令，確認是否可以使用 FQDN，透過網際網路與 IMAP 伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p109">**Obtain the FQDN of the IMAP server**. You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint. Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>
    
- <span data-ttu-id="42d4f-p110">**設定防火牆來允許 IMAP 連線**。您可能必須開啟主控 IMAP 伺服器之組織的防火牆中的通訊埠，以便允許移轉期間源自 Microsoft 資料中心的網路流量進入主控 IMAP 伺服器的組織。如需 Microsoft 資料中心所使用的 IP 位址清單，請參閱 [Office 365 URL 與 IP 位址範圍](https://go.microsoft.com/fwlink/p/?LinkId=535066)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p110">**Configure the firewall to allow IMAP connections**. You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server. For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](https://go.microsoft.com/fwlink/p/?LinkId=535066).</span></span>
    
- <span data-ttu-id="42d4f-p111">**指派系統管理員帳戶權限來存取 IMAP 組織中的信箱**。如果您在 CSV 檔案中使用系統管理員認證，您所使用的帳戶必須具有能存取內部部署信箱的必要權限。存取使用者信箱所需的權限是由特定的 IMAP 伺服器決定。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p111">**Assign the administrator account permissions to access mailboxes in your IMAP organization**. If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes. The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span> 
    
- <span data-ttu-id="42d4f-p112">**若要使用 Exchange Online PowerShell Cmdlet**，您需要登入系統，並將 Cmdlet 匯入您的本機 Windows PowerShell 工作階段。請參閱[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121) 的指示。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p112">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
    
    <span data-ttu-id="42d4f-143">若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=534750)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-143">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
    
- <span data-ttu-id="42d4f-p113">**確認您可以連線至 IMAP 伺服器**。在 Exchange Online PowerShell 中執行下列命令，測試 IMAP 伺服器的連線設定。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p113">**Verify that you can connect to your IMAP server**. Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="42d4f-146">對於 **Port** 參數的值，通常是使用 143 來進行未加密或傳輸層安全性 (TLS) 連線，以及使用 993 來進行 SSL 連線。</span><span class="sxs-lookup"><span data-stu-id="42d4f-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="42d4f-147">步驟 2：建立 CSV 檔案供 IMAP 移轉批次使用</span><span class="sxs-lookup"><span data-stu-id="42d4f-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="42d4f-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="42d4f-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="42d4f-p114">識別您想要在 IMAP 移轉批次中移轉其信箱的使用者群組。CSV 檔案中的每一列包含連線至 IMAP 郵件系統中的信箱所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p114">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch. Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>
  
<span data-ttu-id="42d4f-151">以下是供每個使用者使用的必要屬性。</span><span class="sxs-lookup"><span data-stu-id="42d4f-151">Here are the required attributes for each user:</span></span> 
  
- <span data-ttu-id="42d4f-152">**EmailAddress** 會指定使用者的 Microsoft 365 信箱的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="42d4f-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>
    
- <span data-ttu-id="42d4f-153">**UserName** 會指定帳戶在存取 IMAP 伺服器上的信箱時所使用的登入名稱。</span><span class="sxs-lookup"><span data-stu-id="42d4f-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>
    
- <span data-ttu-id="42d4f-154">**Password** 會指定 **UserName** 欄中之帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="42d4f-154">**Password** specifies the password for the account in the **UserName** column.</span></span>
    
<span data-ttu-id="42d4f-p115">以下是 CSV 檔案的格式範例：在此範例中，會移轉三個信箱：</span><span class="sxs-lookup"><span data-stu-id="42d4f-p115">Here's an example of the format for the CSV file. In this example, three mailboxes are migrated:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="42d4f-157">若是 **UserName** 屬性，除了使用者名稱，您還可以使用已指派必要權限的帳戶認證來存取 IMAP 伺服器上的信箱，以下是一些 IMAP 伺服器使用的特定格式：</span><span class="sxs-lookup"><span data-stu-id="42d4f-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>
  
 <span data-ttu-id="42d4f-158">**Microsoft Exchange：**</span><span class="sxs-lookup"><span data-stu-id="42d4f-158">**Microsoft Exchange:**</span></span>
  
<span data-ttu-id="42d4f-p116">如果您要從 Microsoft Exchange 的 IMAP 實作中移轉電子郵件，請針對 CSV 檔案中的 **UserName** 屬性使用 **Domain/Admin_UserName/User_UserName** 格式。假設您要從 Exchange 中移轉 Terry Adams、Ann Beebe 和 Paul Cannon 的電子郵件。您具有郵件系統管理員帳戶，其使用者名稱為 **mailadmin** ，而密碼為 **P@ssw0rd** 。以下是您 CSV 檔的外觀：</span><span class="sxs-lookup"><span data-stu-id="42d4f-p116">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file. Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon. You have a mail administrator account, where the user name is **mailadmin** and the password is **P@ssw0rd**. Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="42d4f-163">**Dovecot：**</span><span class="sxs-lookup"><span data-stu-id="42d4f-163">**Dovecot:**</span></span>
  
<span data-ttu-id="42d4f-p117">若為支援簡單驗證及安全性階層 (SASL) 的 IMAP 伺服器 (例如 Dovecot IMAP 伺服器)，請使用 **User_UserName\*Admin_UserName** 格式，其中星號 (\*) 是可設定的分隔字元。假設您要使用系統管理員認證 **mailadmin** 和 **P@ssw0rd** ，從 Dovecot IMAP 伺服器中移轉相同使用者的電子郵件。以下是您 CSV 檔的外觀：</span><span class="sxs-lookup"><span data-stu-id="42d4f-p117">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character. Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P@ssw0rd**. Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="42d4f-167">**Mirapoint：**</span><span class="sxs-lookup"><span data-stu-id="42d4f-167">**Mirapoint:**</span></span>
  
<span data-ttu-id="42d4f-p118">如果您要從 Mirapoint Message Server 中移轉電子郵件，請針對系統管理員認證使用 **#user@domain#Admin_UserName#** 格式。若要使用系統管理員認證 **mailadmin** 和 **P@ssw0rd** ，從 Mirapoint 中移轉電子郵件，您 CSV 檔的外觀如下：</span><span class="sxs-lookup"><span data-stu-id="42d4f-p118">If you're migrating email from Mirapoint Message Server, use the format **#user@domain#Admin_UserName#** for the administrator credentials. To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P@ssw0rd**, your CSV file would look like this:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="42d4f-170">**Courier-IMAP：**</span><span class="sxs-lookup"><span data-stu-id="42d4f-170">**Courier IMAP:**</span></span>
  
<span data-ttu-id="42d4f-171">有些來源電子郵件系統（例如「宋體」）不支援使用信箱系統管理員認證，將信箱遷移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="42d4f-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="42d4f-172">相反地，您可以設定來源電子郵件系統來使用虛擬共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="42d4f-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="42d4f-173">藉由使用虛擬共用資料夾，您可以使用信箱管理員認證來存取來源電子郵件系統上的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="42d4f-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="42d4f-174">如需如何設定適用於 Courier IMAP 的虛擬共用資料夾的詳細資訊，請參閱[共用資料夾](https://go.microsoft.com/fwlink/p/?LinkId=398870)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>
  
<span data-ttu-id="42d4f-p120">若要在來源電子郵件系統上設定虛擬共用資料夾之後移轉信箱，您必須在移轉檔案中加入選擇性屬性 **UserRoot** 。此屬性會指定每個使用者信箱在來源電子郵件系統之虛擬共用資料夾結構中的位置。例如，前往 Terry 信箱的路徑是 /users/terry.adams。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p120">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file. This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system. For example, the path to Terry's mailbox is /users/terry.adams.</span></span>
  
<span data-ttu-id="42d4f-178">以下是包含 **UserRoot** 屬性之 CSV 檔案的範例：</span><span class="sxs-lookup"><span data-stu-id="42d4f-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="42d4f-179">步驟 3：建立 IMAP 移轉端點</span><span class="sxs-lookup"><span data-stu-id="42d4f-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="42d4f-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="42d4f-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="42d4f-181">若要成功遷移電子郵件，Microsoft 365 必須連線到來源電子郵件系統，並與其通訊。</span><span class="sxs-lookup"><span data-stu-id="42d4f-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="42d4f-182">若要這樣做，Microsoft 365 會使用遷移端點。</span><span class="sxs-lookup"><span data-stu-id="42d4f-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="42d4f-183">移轉端點也會定義要同時移轉的信箱數目，以及要在每 24 小時執行一次的增量同步處理期間同時同步處理的信箱數目。</span><span class="sxs-lookup"><span data-stu-id="42d4f-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="42d4f-184">若要建立 IMAP 移轉的移轉端點，請先[連線至 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="42d4f-185">若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=534750)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-185">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="42d4f-186">若要在 Exchange Online PowerShell 中建立名為 "IMAPEndpoint" 的 IMAP 移轉端點，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="42d4f-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="42d4f-p122">您也可以新增參數來指定同時移轉、同時增量移轉和要使用的通訊埠。下列 Exchange Online PowerShell 命令會建立名為 "IMAPEndpoint" 的 IMAP 移轉端點，該端點支援 50 件同時移轉，以及最多 25 件同時增量同步處理。它也會將端點設定為使用通訊埠 143 來進行 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p122">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use. The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations. It also configures the endpoint to use port 143 for TLS encryption.</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="42d4f-190">如需 **New-MigrationEndpoint** Cmdlet 的詳細資訊，請參閱[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="42d4f-191">確認是否正常運作</span><span class="sxs-lookup"><span data-stu-id="42d4f-191">Verify it worked</span></span>

<span data-ttu-id="42d4f-192">在 Exchange Online PowerShell 中執行下列命令來顯示 "IMAPEndpoint" 的資訊：</span><span class="sxs-lookup"><span data-stu-id="42d4f-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="42d4f-193">步驟 4：建立並啟動 IMAP 移轉批次</span><span class="sxs-lookup"><span data-stu-id="42d4f-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="42d4f-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="42d4f-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="42d4f-p123">您可以使用 [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) Cmdlet 來建立 IMAP 移轉的移轉批次。您可以建立移轉批次，並加上 _AutoStart_ 參數來自動啟動它。或者，您可以建立移轉批次，之後再使用[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) Cmdlet 來啟動該批次。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p123">You can use the [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) cmdlet to create a migration batch for an IMAP migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) cmdlet.</span></span>
  
<span data-ttu-id="42d4f-198">下列 Exchange Online PowerShell 命令將會使用名為 "IMAPEndpoint" 的 IMAP 端點自動啟動名為 "IMAPBatch1" 的移轉批次：</span><span class="sxs-lookup"><span data-stu-id="42d4f-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="42d4f-199">確認是否正常運作</span><span class="sxs-lookup"><span data-stu-id="42d4f-199">Verify it worked</span></span>

<span data-ttu-id="42d4f-200">執行 [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) Cmdlet 來顯示 "IMAPBatch1" 的資訊：</span><span class="sxs-lookup"><span data-stu-id="42d4f-200">Run the [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) cmdlet to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="42d4f-201">您也可以執行下列命令來確認批次已啟動：</span><span class="sxs-lookup"><span data-stu-id="42d4f-201">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="42d4f-202">步驟5：將電子郵件路由傳送至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42d4f-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="42d4f-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="42d4f-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="42d4f-204">電子郵件系統使用稱為 MX 記錄的 DNS 記錄來找出要將電子郵件傳遞到哪裡。</span><span class="sxs-lookup"><span data-stu-id="42d4f-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="42d4f-205">在電子郵件移轉過程中，您的 MX 記錄指向來源電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="42d4f-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="42d4f-206">現在，已完成將電子郵件遷移至 Microsoft 365，您可以將您的 MX 記錄指向 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="42d4f-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="42d4f-207">這可協助確定電子郵件已傳遞至您的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="42d4f-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="42d4f-208">藉由移動 MX 記錄，您也可以在準備好時關閉舊的電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="42d4f-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="42d4f-209">我們針對許多 DNS 提供者提供變更 MX 記錄的特定指示。</span><span class="sxs-lookup"><span data-stu-id="42d4f-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="42d4f-210">如果您的 DNS 提供者不在其中，或如果您想要了解一般指示，我們也提供[在任一 DNS 主機服務提供者建立 Office 365 的 DNS 記錄](https://go.microsoft.com/fwlink/?LinkId=397449)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="42d4f-p126">您的客戶與合作夥伴的電子郵件系統最多可能需要 72 小時才能辨識已變更的 MX 記錄。請至少等待 72 小時，再繼續進行下一個工作：步驟 6：刪除 IMAP 移轉批次。</span><span class="sxs-lookup"><span data-stu-id="42d4f-p126">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span> 
  
### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="42d4f-213">步驟 6：刪除 IMAP 移轉批次</span><span class="sxs-lookup"><span data-stu-id="42d4f-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="42d4f-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="42d4f-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="42d4f-215">在您變更 MX 記錄，並確認所有電子郵件都會路由傳送至 Microsoft 365 信箱之後，請通知使用者他們的郵件即將移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="42d4f-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="42d4f-216">在此之後，您便可以刪除 IMAP 移轉批次。</span><span class="sxs-lookup"><span data-stu-id="42d4f-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="42d4f-217">在刪除移轉批次之前，請先確認下列事項。</span><span class="sxs-lookup"><span data-stu-id="42d4f-217">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="42d4f-218">所有使用者都使用 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="42d4f-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="42d4f-219">刪除批次之後，傳送至內部部署 Exchange 伺服器上之信箱的郵件不會複製到對應的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="42d4f-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="42d4f-220">當郵件開始直接傳送給他們之後，Microsoft 365 信箱會至少同步處理一次。</span><span class="sxs-lookup"><span data-stu-id="42d4f-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="42d4f-221">若要這麼做，請確定遷移批次的 [上次同步處理時間] 方塊中的值比直接路由傳送至 Microsoft 365 信箱的時間晚。</span><span class="sxs-lookup"><span data-stu-id="42d4f-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="42d4f-222">若要在 Exchange Online PowerShell 中刪除 "IMAPBatch1" 移轉批次，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="42d4f-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="42d4f-223">如需 **Remove-MigrationBatch** Cmdlet 的詳細資訊，請參閱[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="42d4f-224">確認是否正常運作</span><span class="sxs-lookup"><span data-stu-id="42d4f-224">Verify it worked</span></span>

<span data-ttu-id="42d4f-225">在 Exchange Online PowerShell 中執行下列命令來顯示 "IMAPBatch1" 的資訊：</span><span class="sxs-lookup"><span data-stu-id="42d4f-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="42d4f-226">此命令會傳回狀態為 **Removing** 的移轉批次，或傳回錯誤，指出找不到移轉批次而需確認該批次是否已刪除。</span><span class="sxs-lookup"><span data-stu-id="42d4f-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="42d4f-227">如需 **Get-MigrationBatch** Cmdlet 的詳細資訊，請參閱[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)。</span><span class="sxs-lookup"><span data-stu-id="42d4f-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="42d4f-228">另請參閱</span><span class="sxs-lookup"><span data-stu-id="42d4f-228">See also</span></span>

[<span data-ttu-id="42d4f-229">IMAP 移轉疑難排解員</span><span class="sxs-lookup"><span data-stu-id="42d4f-229">IMAP Migration Troubleshooter</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536482)

