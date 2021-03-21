---
title: 使用 PowerShell 以完全移轉至 Microsoft 365
ms.author: sirkkuw
author: sirkkuw
manager: laurawi
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
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: 瞭解如何使用 PowerShell 一次從來源電子郵件系統移動內容，方法是對 Microsoft 365 執行完全遷移。
ms.openlocfilehash: 60bd3cb246e04aba37be06f7a951abbf25708412
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924801"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="88bda-103">使用 PowerShell 以完全移轉至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88bda-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="88bda-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="88bda-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="88bda-105">您可以使用完全遷移，將使用者信箱的內容從來源電子郵件系統移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="88bda-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="88bda-106">本文會引導您使用 Exchange Online PowerShell 來進行電子郵件完全移轉的工作。</span><span class="sxs-lookup"><span data-stu-id="88bda-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span>

<span data-ttu-id="88bda-107">透過複習主題， [您需要瞭解如何將電子郵件遷移到 Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)，您就可以瞭解遷移程式的概況。</span><span class="sxs-lookup"><span data-stu-id="88bda-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration), you can get an overview of the migration process.</span></span> <span data-ttu-id="88bda-108">在熟悉該文章的內容後，請使用此主題來開始在不同電子郵件系統中移轉信箱。</span><span class="sxs-lookup"><span data-stu-id="88bda-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>

> [!NOTE]
> <span data-ttu-id="88bda-109">您也可以使用 Exchange 系統管理中心來執行完全移轉。</span><span class="sxs-lookup"><span data-stu-id="88bda-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="88bda-110">請參閱 [執行電子郵件的完全遷移至 Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="88bda-110">See [Perform a cutover migration of email to Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="88bda-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="88bda-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="88bda-112">完成此工作的預估時間：2-5 分鐘來建立遷移批次。</span><span class="sxs-lookup"><span data-stu-id="88bda-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="88bda-113">啟動移轉批次之後，移轉所需的時間會依批次中的信箱數目、每個信箱的大小和可用的網路容量而有所不同。</span><span class="sxs-lookup"><span data-stu-id="88bda-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="88bda-114">如需其他影響將信箱遷移至 Microsoft 365 的因素的詳細資訊，請參閱 [遷移效能](/Exchange/mailbox-migration/office-365-migration-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="88bda-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>

<span data-ttu-id="88bda-p105">您必須已獲指派的權限，才能執行此程序。若要查看您需要哪些權限，請參閱[收件者權限](/exchange/recipients-permissions-exchange-2013-help)主題中所含表格的「移轉」項目。</span><span class="sxs-lookup"><span data-stu-id="88bda-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>

<span data-ttu-id="88bda-p106">若要使用 Exchange Online PowerShell Cmdlet，您需要登入系統，並將 Cmdlet 匯入您的本機 Windows PowerShell 工作階段。請參閱[使用遠端 PowerShell 連線到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) 的指示。</span><span class="sxs-lookup"><span data-stu-id="88bda-p106">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

<span data-ttu-id="88bda-119">若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](/powershell/exchange/)。</span><span class="sxs-lookup"><span data-stu-id="88bda-119">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

## <a name="migration-steps"></a><span data-ttu-id="88bda-120">移轉步驟</span><span class="sxs-lookup"><span data-stu-id="88bda-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="88bda-121">步驟 1：準備完全移轉</span><span class="sxs-lookup"><span data-stu-id="88bda-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="88bda-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="88bda-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="88bda-123">**將您的內部部署 Exchange 組織新增為 Microsoft 365 組織公認的網域。**</span><span class="sxs-lookup"><span data-stu-id="88bda-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="88bda-124">遷移服務會使用內部部署信箱的 SMTP 位址，為新的 Microsoft 365 信箱建立 Microsoft 線上服務使用者識別碼和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="88bda-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="88bda-125">如果您的 Exchange 網域不是 Microsoft 365 組織的公認網域或主域，遷移將會失敗。</span><span class="sxs-lookup"><span data-stu-id="88bda-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="88bda-126">如需詳細資訊，請參閱 [驗證您的網域](../admin/setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="88bda-126">For more information, see [Verify your domain](../admin/setup/add-domain.md).</span></span>

- <span data-ttu-id="88bda-p108">**在內部部署 Exchange 伺服器上設定 Outlook 無所不在。** 電子郵件移轉服務會使用 RPC over HTTP (或 Outlook 無所不在) 連線至您的內部部署 Exchange 伺服器。如需如何為 Exchange 2010、Exchange 2007 和 Exchange 2003 設定 Outlook 無所不在的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="88bda-p108">**Configure Outlook Anywhere on your on-premises Exchange server.** The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server. For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>

  - <span data-ttu-id="88bda-130">[Exchange 2010：啟用 Outlook 無所不在](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="88bda-130">[Exchange 2010: Enable Outlook Anywhere](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span></span>

  - <span data-ttu-id="88bda-131">[Exchange 2007：如何啟用 Outlook 無所不在](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="88bda-131">[Exchange 2007: How to Enable Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span></span>

  - <span data-ttu-id="88bda-132">[Exchange 2003：RPC over HTTP 的部署案例](/previous-versions/tn-archive/bb124876(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="88bda-132">[Exchange 2003: Deployment Scenarios for RPC over HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span></span>

  - <span data-ttu-id="88bda-133">[如何使用 Exchange 2003 設定 Outlook 無所不在](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="88bda-133">[How to Configure Outlook Anywhere with Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="88bda-p109">您的 Outlook 無所不在組態必須以信任的憑證授權單位 (CA) 所核發的憑證設定。它無法以自我簽署的憑證設定。如需詳細資訊，請參閱[如何為 Outlook 無所不在設定 SSL](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))。</span><span class="sxs-lookup"><span data-stu-id="88bda-p109">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA). It can't be configured with a self-signed certificate. For more information, see [How to Configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span></span>

- <span data-ttu-id="88bda-p110">**確認您可以使用 Outlook 無所不在連線至 Exchange 組織。** 嘗試下列其中一種方法測試您的連線設定：</span><span class="sxs-lookup"><span data-stu-id="88bda-p110">**Verify that you can connect to your Exchange organization using Outlook Anywhere.** Try one of these methods to test your connection settings:</span></span>

  - <span data-ttu-id="88bda-139">從公司網路之外使用 Microsoft Outlook 連線至內部部署 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="88bda-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>

  - <span data-ttu-id="88bda-p111">使用 Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) 測試連線設定。使用 Outlook 無所不在 (RPC over HTTP) 或 Outlook 自動探索測試。</span><span class="sxs-lookup"><span data-stu-id="88bda-p111">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings. Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>

  - <span data-ttu-id="88bda-142">在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="88bda-142">Run the following commands in Exchange Online PowerShell.</span></span>

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="88bda-143">**指派必要權限給內部部署使用者帳戶來存取 Exchange 組織中的信箱。**</span><span class="sxs-lookup"><span data-stu-id="88bda-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="88bda-144">您用來連線至內部部署 Exchange 組織的內部部署使用者帳戶 (也稱為「遷移系統管理員」) 必須具備必要的許可權，才能存取您要遷移至 Microsoft 365 的內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="88bda-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="88bda-145">此使用者帳戶可用來建立內部部署組織的移轉端點。</span><span class="sxs-lookup"><span data-stu-id="88bda-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>

    <span data-ttu-id="88bda-p113">下列清單顯示使用完全移轉來移轉信箱時所需的系統管理權限。有三個可能的選項。</span><span class="sxs-lookup"><span data-stu-id="88bda-p113">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration. There are three possible options.</span></span>

  - <span data-ttu-id="88bda-148">移轉系統管理員在內部部署組織的 Active Directory 中必須是 **Domain Admins** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="88bda-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>

    <span data-ttu-id="88bda-149">或</span><span class="sxs-lookup"><span data-stu-id="88bda-149">Or</span></span>

  - <span data-ttu-id="88bda-150">移轉系統管理員必須具有每個內部部署信箱的 **FullAccess** 權限。</span><span class="sxs-lookup"><span data-stu-id="88bda-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>

    <span data-ttu-id="88bda-151">或</span><span class="sxs-lookup"><span data-stu-id="88bda-151">Or</span></span>

  - <span data-ttu-id="88bda-152">在儲存使用者信箱的內部部署信箱資料庫上，移轉系統管理員必須具有 **[以下列接收]** 權限。</span><span class="sxs-lookup"><span data-stu-id="88bda-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>

- <span data-ttu-id="88bda-p114">**停用整合通訊。** 如果您要移轉的內部部署信箱已啟用整合通訊 (UM)，則移轉之前必須先在信箱上停用 UM。您可以在移轉完成之後，再於信箱上啟用 UM。</span><span class="sxs-lookup"><span data-stu-id="88bda-p114">**Disable Unified Messaging.** If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them. You can then enable UM on the mailboxes after the migration is complete.</span></span>

- <span data-ttu-id="88bda-156">**安全性群組和代理人** 電子郵件遷移服務無法偵測內部部署 Active Directory 群組是否為安全性群組，所以無法將任何遷移的群組布建為 Microsoft 365 中的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="88bda-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="88bda-157">如果您想要在 Microsoft 365 承租人中擁有安全性群組，您必須先在您的 Microsoft 365 租使用者中布建已啟用郵件功能的安全性群組，再開始完全遷移。</span><span class="sxs-lookup"><span data-stu-id="88bda-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="88bda-158">此外，此移轉方法只會移動信箱、郵件使用者、郵件連絡人和擁有郵件功能的群組。</span><span class="sxs-lookup"><span data-stu-id="88bda-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="88bda-159">如果有任何其他 Active Directory 物件（例如未遷移至 Microsoft 365 的使用者）被指派為要遷移之物件的管理員或代理人，必須先將其從物件中移除才能進行遷移。</span><span class="sxs-lookup"><span data-stu-id="88bda-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>

### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="88bda-160">步驟 2：建立移轉端點</span><span class="sxs-lookup"><span data-stu-id="88bda-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="88bda-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="88bda-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="88bda-162">若要成功遷移電子郵件，Microsoft 365 必須與來源電子郵件系統連線並進行通訊。</span><span class="sxs-lookup"><span data-stu-id="88bda-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="88bda-163">若要這樣做，Microsoft 365 會使用遷移端點。</span><span class="sxs-lookup"><span data-stu-id="88bda-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="88bda-164">若要建立 Outlook 無所不在移轉端點以進行分段移轉，請先[連線至 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="88bda-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="88bda-165">若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](/powershell/exchange/)。</span><span class="sxs-lookup"><span data-stu-id="88bda-165">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="88bda-166">在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="88bda-166">Run the following commands in Exchange Online PowerShell:</span></span>

```powershell
$Credentials = Get-Credential
```

<span data-ttu-id="88bda-167">此範例使用 [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) Cmdlet 來取得並測試內部部署 Exchange 伺服器的連線設定，然後使用那些連線設定來建立名為 "CutoverEndpoint" 的移轉端點。</span><span class="sxs-lookup"><span data-stu-id="88bda-167">The example uses the [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="88bda-p117">藉由使用 **-TargetDatabase** 選項，可以使用 **New-MigrationEndpoint** Cmdlet 來指定要使用之服務的資料庫。否則系統會從管理信箱所在的 Active Directory Federation Services (AD FS) 2.0 網站隨機指派資料庫。</span><span class="sxs-lookup"><span data-stu-id="88bda-p117">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="88bda-170">確認是否正常運作</span><span class="sxs-lookup"><span data-stu-id="88bda-170">Verify it worked</span></span>

<span data-ttu-id="88bda-171">在 Exchange Online PowerShell 中執行下列命令來顯示 "CutoverEndpoint" 移轉端點的資訊：</span><span class="sxs-lookup"><span data-stu-id="88bda-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="88bda-172">步驟 3：建立完全移轉批次</span><span class="sxs-lookup"><span data-stu-id="88bda-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="88bda-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="88bda-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="88bda-p118">您可以在 Exchange Online PowerShell 中使用 **New-MigrationBatch** Cmdlet，為完全移轉建立移轉批次。您可以建立移轉批次，並加上 _AutoStart_ 參數來自動啟動它。或者，您也可以先建立移轉批次，以後再手動使用 **Start-MigrationBatch** Cmdlet 啟動它。本範例會建立名為 "CutoverBatch" 的移轉批次，並使用上一個步驟中建立的移轉端點。</span><span class="sxs-lookup"><span data-stu-id="88bda-p118">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="88bda-p119">本範例也會建立名為 "CutoverBatch" 的移轉批次，並使用上一個步驟中建立的移轉端點。因為其中並未加上  _AutoStart_ 參數，所以需要在移轉儀表板上或使用 **Start-MigrationBatch** Cmdlet 來手動啟動此移轉批次。如前所述，一次只能有一個完全移轉批次。</span><span class="sxs-lookup"><span data-stu-id="88bda-p119">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="88bda-181">確認是否正常運作</span><span class="sxs-lookup"><span data-stu-id="88bda-181">Verify it worked</span></span>

<span data-ttu-id="88bda-182">若要確認您已順利為完全移轉建立移轉批次，請在 Exchange Online PowerShell 中執行下列命令來顯示新移轉批次的資訊：</span><span class="sxs-lookup"><span data-stu-id="88bda-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="88bda-183">步驟 4：啟動完全移轉批次</span><span class="sxs-lookup"><span data-stu-id="88bda-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="88bda-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="88bda-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="88bda-p120">若要在 Exchange Online PowerShell 中啟動移轉批次，請執行下列命令。這樣會建立名為 "CutoverBatch" 的移轉批次。</span><span class="sxs-lookup"><span data-stu-id="88bda-p120">To start the migration batch in Exchange Online PowerShell, run the following command. This will create a migration batch called "CutoverBatch".</span></span>

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="88bda-187">確認是否正常運作</span><span class="sxs-lookup"><span data-stu-id="88bda-187">Verify it worked</span></span>

<span data-ttu-id="88bda-p121">如果移轉批次已順利啟動，則其在移轉儀表板上的狀態會指定為「正在同步處理」。若要確認您已使用 Exchange Online PowerShell 成功啟動移轉批次，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="88bda-p121">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing. To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="88bda-190">步驟5：將電子郵件路由傳送至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88bda-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="88bda-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="88bda-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="88bda-192">電子郵件系統使用稱為 MX 記錄的 DNS 記錄來找出要將電子郵件傳遞到哪裡。</span><span class="sxs-lookup"><span data-stu-id="88bda-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="88bda-193">在電子郵件移轉過程中，您的 MX 記錄指向來源電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="88bda-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="88bda-194">現在，已完成將電子郵件遷移至 Microsoft 365，您可以將您的 MX 記錄指向 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="88bda-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="88bda-195">這可協助確定電子郵件已傳遞至您的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="88bda-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="88bda-196">藉由移動 MX 記錄，您也可以在準備好時關閉舊的電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="88bda-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span>

<span data-ttu-id="88bda-197">我們針對許多 DNS 提供者提供變更 MX 記錄的特定指示。</span><span class="sxs-lookup"><span data-stu-id="88bda-197">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="88bda-198">如果您的 DNS 提供者不包含在內，或者如果您想要了解一般指示，我們也會提供[一般 MX 記錄指示](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx)。</span><span class="sxs-lookup"><span data-stu-id="88bda-198">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) are provided as well.</span></span>

<span data-ttu-id="88bda-p124">您的客戶與合作夥伴的電子郵件系統最多可能需要 72 小時才能辨識已變更的 MX 記錄。請至少等待 72 小時，再繼續進行下一個工作： [步驟 6：刪除完全移轉批次](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span><span class="sxs-lookup"><span data-stu-id="88bda-p124">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span>

### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="88bda-201">步驟 6：刪除完全移轉批次</span><span class="sxs-lookup"><span data-stu-id="88bda-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="88bda-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="88bda-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="88bda-203">在您變更 MX 記錄，並確認所有電子郵件都會路由傳送至 Microsoft 365 信箱之後，請通知使用者他們的郵件即將移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="88bda-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="88bda-204">在此之後，您便可以刪除完全移轉批次。</span><span class="sxs-lookup"><span data-stu-id="88bda-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="88bda-205">在刪除移轉批次之前，請先確認下列事項。</span><span class="sxs-lookup"><span data-stu-id="88bda-205">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="88bda-206">所有使用者都使用 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="88bda-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="88bda-207">刪除批次之後，傳送至內部部署 Exchange 伺服器上之信箱的郵件不會複製到對應的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="88bda-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="88bda-208">當郵件開始直接傳送給他們之後，Microsoft 365 信箱會至少同步處理一次。</span><span class="sxs-lookup"><span data-stu-id="88bda-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="88bda-209">若要這麼做，請確定遷移批次的 [上次同步處理時間] 方塊中的值比直接路由傳送至 Microsoft 365 信箱的時間晚。</span><span class="sxs-lookup"><span data-stu-id="88bda-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="88bda-210">若要在 Exchange Online PowerShell 中刪除 "CutoverBatch" 移轉批次，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="88bda-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="88bda-211">第 7 節：指派使用者授權</span><span class="sxs-lookup"><span data-stu-id="88bda-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="88bda-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="88bda-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="88bda-213">**指派授權，為遷移的帳戶啟動 Microsoft 365 使用者帳戶。**</span><span class="sxs-lookup"><span data-stu-id="88bda-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="88bda-214">如果您未指派授權，則當寬限期 (30 天) 結束時就會停用信箱。</span><span class="sxs-lookup"><span data-stu-id="88bda-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="88bda-215">若要在 Microsoft 365 系統管理中心中指派授權，請參閱 [指派或取消指派授權](../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="88bda-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).</span></span>

### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="88bda-216">步驟 8：完成移轉後工作</span><span class="sxs-lookup"><span data-stu-id="88bda-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="88bda-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="88bda-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="88bda-218">**建立自動探索 DNS 記錄，讓使用者可以輕鬆存取信箱。**</span><span class="sxs-lookup"><span data-stu-id="88bda-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="88bda-219">在所有內部部署信箱遷移至 Microsoft 365 之後，您可以設定 Microsoft 365 組織的自動探索 DNS 記錄，讓使用者能夠使用 Outlook 和行動用戶端輕鬆連線到其新的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="88bda-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="88bda-220">這個新的自動探索 DNS 記錄必須使用您的 Microsoft 365 組織所使用的相同命名空間。</span><span class="sxs-lookup"><span data-stu-id="88bda-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="88bda-221">舉例來說，如果您的雲端架構命名空間是 cloud.contoso.com，則您需要建立的自動探索 DNS 記錄是 autodiscover.cloud.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="88bda-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>

    <span data-ttu-id="88bda-222">如果您保留 Exchange 伺服器，也應確定在遷移後，在內部和外部 DNS 中，自動探索 DNS CNAME 記錄必須指向 Microsoft 365，以便讓 Outlook 用戶端能夠連線到正確的信箱。</span><span class="sxs-lookup"><span data-stu-id="88bda-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="88bda-223">在 Exchange 2007、Exchange 2010 和 Exchange 2013 中，您也應該將  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` 設為 `Null`。</span><span class="sxs-lookup"><span data-stu-id="88bda-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span>

    <span data-ttu-id="88bda-224">Microsoft 365 使用 CNAME 記錄來實施 Outlook 和行動用戶端的自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="88bda-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="88bda-225">自動探索 CNAME 記錄必須包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="88bda-225">The Autodiscover CNAME record must contain the following information:</span></span>

  - <span data-ttu-id="88bda-226">**別名：** 自動探索</span><span class="sxs-lookup"><span data-stu-id="88bda-226">**Alias:** autodiscover</span></span>

  - <span data-ttu-id="88bda-227">**目標：** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="88bda-227">**Target:** autodiscover.outlook.com</span></span>

    <span data-ttu-id="88bda-228">如需詳細資訊，請參閱 [新增 DNS 記錄以連接您的網域](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="88bda-228">For more information, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="88bda-229">**解除委任內部部署 Exchange 伺服器。**</span><span class="sxs-lookup"><span data-stu-id="88bda-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="88bda-230">在您確認所有電子郵件都直接路由傳送至 Microsoft 365 信箱之後，如果您不再需要維護內部部署電子郵件組織，或不需要維護單一登入 (SSO) 解決方案，您可以從伺服器卸載 Exchange，並移除內部部署 Exchange 組織。</span><span class="sxs-lookup"><span data-stu-id="88bda-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>

    <span data-ttu-id="88bda-231">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="88bda-231">For more information, see the following:</span></span>

  - <span data-ttu-id="88bda-232">[修改及移除 Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="88bda-232">[Modify or Remove Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span></span>

  - <span data-ttu-id="88bda-233">[如何移除 Exchange 2007 組織](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="88bda-233">[How to Remove an Exchange 2007 Organization](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span></span>

  - <span data-ttu-id="88bda-234">[如何解除安裝 Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="88bda-234">[How to Uninstall Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span></span>