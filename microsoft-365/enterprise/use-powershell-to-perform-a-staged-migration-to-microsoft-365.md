---
title: 使用 PowerShell 以階段移轉至 Microsoft 365
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
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: 瞭解如何使用 PowerShell，透過一段時間將內容從來源電子郵件系統移轉至 Microsoft 365。
ms.openlocfilehash: ebf2067fe7ae9fc2d2b58d0aa804c7843295b38a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688405"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a><span data-ttu-id="08316-103">使用 PowerShell 以階段移轉至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="08316-103">Use PowerShell to perform a staged migration to Microsoft 365</span></span>

<span data-ttu-id="08316-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="08316-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="08316-105">您可以使用分段遷移，將使用者信箱的內容從來源電子郵件系統移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="08316-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 over time using a staged migration.</span></span>
  
<span data-ttu-id="08316-106">本文將引導您逐步完成使用 Exchange Online PowerShell 進行分段電子郵件遷移所涉及的工作。</span><span class="sxs-lookup"><span data-stu-id="08316-106">This article walks you through the tasks involved with for a staged email migration using Exchange Online PowerShell.</span></span> <span data-ttu-id="08316-107">主題是 [分步電子郵件遷移所需注意的事項](https://go.microsoft.com/fwlink/p/?LinkId=536487)，可讓您瞭解遷移程式。</span><span class="sxs-lookup"><span data-stu-id="08316-107">The topic, [What you need to know about a staged email migration](https://go.microsoft.com/fwlink/p/?LinkId=536487), gives you an overview of the migration process.</span></span> <span data-ttu-id="08316-108">在熟悉該文章的內容後，請使用此主題來開始在不同電子郵件系統中移轉信箱。</span><span class="sxs-lookup"><span data-stu-id="08316-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>
  
> [!NOTE]
> <span data-ttu-id="08316-109">您也可以使用 Exchange 系統管理中心來執行分段移轉。</span><span class="sxs-lookup"><span data-stu-id="08316-109">You can also use the Exchange admin center to perform staged migration.</span></span> <span data-ttu-id="08316-110">請參閱 [執行將電子郵件分段遷移至 Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536687)。</span><span class="sxs-lookup"><span data-stu-id="08316-110">See [Perform a staged migration of email to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536687).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="08316-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="08316-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="08316-112">完成此工作的預估時間：2-5 分鐘來建立遷移批次。</span><span class="sxs-lookup"><span data-stu-id="08316-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="08316-113">啟動移轉批次之後，移轉所需的時間會依批次中的信箱數目、每個信箱的大小和可用的網路容量而有所不同。</span><span class="sxs-lookup"><span data-stu-id="08316-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="08316-114">如需其他影響將信箱遷移至 Microsoft 365 的因素的詳細資訊，請參閱 [遷移效能](https://go.microsoft.com/fwlink/p/?LinkId=275079)。</span><span class="sxs-lookup"><span data-stu-id="08316-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="08316-p104">您必須已獲指派的權限，才能執行此程序。若要查看您需要哪些權限，請參閱[收件者權限](https://go.microsoft.com/fwlink/p/?LinkId=534105)主題中的「移轉」項目。</span><span class="sxs-lookup"><span data-stu-id="08316-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="08316-p105">若要使用 Exchange Online PowerShell Cmdlet，您需要登入系統，並將 Cmdlet 匯入您的本機 Windows PowerShell 工作階段。請參閱[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121) 的指示。</span><span class="sxs-lookup"><span data-stu-id="08316-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="08316-119">若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=534750)。</span><span class="sxs-lookup"><span data-stu-id="08316-119">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
## <a name="migration-steps"></a><span data-ttu-id="08316-120">移轉步驟</span><span class="sxs-lookup"><span data-stu-id="08316-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-staged-migration"></a><span data-ttu-id="08316-121">步驟 1：準備分段移轉</span><span class="sxs-lookup"><span data-stu-id="08316-121">Step 1: Prepare for a staged migration</span></span>

<span data-ttu-id="08316-122">使用分段遷移將信箱遷移至 Microsoft 365 之前，您必須對 Exchange 環境進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="08316-122">Before you migrate mailboxes to Microsoft 365 by using a staged migration, there are a few changes you must make to your Exchange environment.</span></span>
  
 <span data-ttu-id="08316-p106">在您的內部部署 Exchange Server 上 **設定** Outlook 無所不在 電子郵件移轉服務會使用 Outlook 無所不在 (也稱為 RPC over HTTP) 來連線至您的內部部署 Exchange Server。如需如何針對 Exchange Server 2007 和 Exchange 2003 設定 Outlook 無所不在 的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="08316-p106">**Configure Outlook Anywhere on your on-premises Exchange Server** The email migration service uses Outlook Anywhere (also known as RPC over HTTP), to connect to your on-premises Exchange Server. For information about how to set up Outlook Anywhere for Exchange Server 2007, and Exchange 2003, see the following:</span></span>
  
- [<span data-ttu-id="08316-125">Exchange 2007：如何啟用 Outlook 無所不在</span><span class="sxs-lookup"><span data-stu-id="08316-125">Exchange 2007: How to Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=167210)
    
- [<span data-ttu-id="08316-126">如何使用 Exchange 2003 設定 Outlook 無所不在</span><span class="sxs-lookup"><span data-stu-id="08316-126">How to configure Outlook Anywhere with Exchange 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=167209)
    
> [!IMPORTANT]
> <span data-ttu-id="08316-p107">您必須在設定 Outlook 無所不在時使用信任的憑證授權單位 (CA) 所發行的憑證。您無法使用自我簽署憑證設定 Outlook 無所不在。如需詳細資訊，請參閱[如何為 Outlook 無所不在設定 SSL](https://go.microsoft.com/fwlink/?LinkID=80875)。</span><span class="sxs-lookup"><span data-stu-id="08316-p107">You must use a certificate issued by a trusted certification authority (CA) with your Outlook Anywhere configuration. Outlook Anywhere can't be configured with a self-signed certificate. For more information, see [How to configure SSL for Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875).</span></span> 
  
 <span data-ttu-id="08316-130">**選擇性：確認可以使用 Outlook 無所不在**連線至您的 Exchange 組織 嘗試使用下列其中一種方法來測試連線設定。</span><span class="sxs-lookup"><span data-stu-id="08316-130">**Optional: Verify that you can connect to your Exchange organization using Outlook Anywhere** Try one of the following methods to test your connection settings.</span></span>
  
- <span data-ttu-id="08316-131">從公司網路之外使用 Outlook 連線至您的內部部署 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="08316-131">Use Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>
    
- <span data-ttu-id="08316-132">使用 [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) 來測試您的連線設定。</span><span class="sxs-lookup"><span data-stu-id="08316-132">Use the [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) to test your connection settings.</span></span> <span data-ttu-id="08316-133">使用 Outlook 無所不在 (RPC over HTTP) 或 Outlook 自動探索測試。</span><span class="sxs-lookup"><span data-stu-id="08316-133">Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>
    
- <span data-ttu-id="08316-134">在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="08316-134">Run the following commands in Exchange Online PowerShell:</span></span>
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 <span data-ttu-id="08316-135">**設定許可權** 您用來連線至內部部署 Exchange 組織的內部部署使用者帳戶 (也稱為「遷移系統管理員」) 必須具備必要的許可權，才能存取您要遷移至 Microsoft 365 的內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="08316-135">**Set permissions** The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="08316-136">當您在此程序稍後建立移轉端點以連線到電子郵件系統時，將會用到此使用者帳戶 ([步驟 3：建立移轉端點](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint))。</span><span class="sxs-lookup"><span data-stu-id="08316-136">This user account is used when you connect to your email system by creating a migration endpoint later in this procedure ([Step 3: Create a migration endpoint](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).</span></span>
  
<span data-ttu-id="08316-137">若要移轉信箱，系統管理員必須具備下列其中一組權限：</span><span class="sxs-lookup"><span data-stu-id="08316-137">To migrate the mailboxes, the admin must have one of the following permission sets:</span></span>
  
- <span data-ttu-id="08316-138">屬於內部部署組織中 Active Directory 內的 **Domain Admins** 群組成員。</span><span class="sxs-lookup"><span data-stu-id="08316-138">Be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>
    
    <span data-ttu-id="08316-139">或 </span><span class="sxs-lookup"><span data-stu-id="08316-139">or</span></span>
    
- <span data-ttu-id="08316-140">獲得每個內部部署信箱的 **FullAccess** 權限，以及用來修改內部部署使用者帳戶的 **TargetAddress** 內容的 **WriteProperty** 權限。</span><span class="sxs-lookup"><span data-stu-id="08316-140">Be assigned the **FullAccess** permission for each on-premises mailbox and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>
    
    <span data-ttu-id="08316-141">或 </span><span class="sxs-lookup"><span data-stu-id="08316-141">or</span></span>
    
- <span data-ttu-id="08316-142">獲得儲存使用者信箱的內部部署信箱資料庫的 **Receive As** 權限，以及用來修改內部部署使用者帳戶的 **TargetAddress** 內容的 **WriteProperty** 權限。</span><span class="sxs-lookup"><span data-stu-id="08316-142">Be assigned the **Receive As** permission on the on-premises mailbox database that stores user mailboxes and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>
    
<span data-ttu-id="08316-143">如需如何設定這些許可權的指示，請參閱 [指派將信箱遷移至 Microsoft 365 的許可權](https://go.microsoft.com/fwlink/?LinkId=521656)。</span><span class="sxs-lookup"><span data-stu-id="08316-143">For instructions about how to set these permissions, see [Assign permissions to migrate mailboxes to Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=521656).</span></span>
  
 <span data-ttu-id="08316-p110">**停用整合通訊 (UM)** 如果您要移轉的內部部署信箱已開啟 UM，請先關閉 UM 再進行移轉。移轉完成後再開啟信箱的 UM。如需操作步驟，請參閱[如何對使用者停用整合通訊](https://go.microsoft.com/fwlink/?LinkId=521891)。</span><span class="sxs-lookup"><span data-stu-id="08316-p110">**Disable Unified Messaging (UM)** If UM is turned on for the on-premises mailboxes you're migrating, turn off UM before migration. Turn on UM for the mailboxes after migration is complete. For how-to steps, see[disable unified messaging](https://go.microsoft.com/fwlink/?LinkId=521891).</span></span>
  
 <span data-ttu-id="08316-147">**使用目錄同步處理來建立 Microsoft 365 中的新使用者。**</span><span class="sxs-lookup"><span data-stu-id="08316-147">**Use directory synchronization to create new users in Microsoft 365.**</span></span> <span data-ttu-id="08316-148">您可以使用目錄同步處理來建立 Microsoft 365 組織中的所有內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="08316-148">You use directory synchronization to create all the on-premises users in your Microsoft 365 organization.</span></span>
  
<span data-ttu-id="08316-p112">您必須授權已建立的使用者。您必須在建立使用者後的 30 天內增加授權。若要增加授權的步驟，請參閱[步驟 8：完成移轉後工作](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration)。</span><span class="sxs-lookup"><span data-stu-id="08316-p112">You need to license the users after they're created. You have 30 days to add licenses after the users are created. For steps to add licenses, see [Step 8: Complete post-migration tasks](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).</span></span>
  
 <span data-ttu-id="08316-152">您可以使用 Microsoft Azure Active Directory (Azure AD) 同步處理工具或 Microsoft Azure AD Sync 服務同步處理，並在 Microsoft 365 中建立內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="08316-152">You can use either the Microsoft Azure Active Directory (Azure AD) Synchronization Tool or the Microsoft Azure AD Sync Services  to synchronize and create your on-premises users in Microsoft 365.</span></span> <span data-ttu-id="08316-153">將信箱遷移至 Microsoft 365 之後，您可以在內部部署組織中管理使用者帳戶，並與您的 Microsoft 365 組織同步處理。</span><span class="sxs-lookup"><span data-stu-id="08316-153">After mailboxes are migrated to Microsoft 365, you manage user accounts in your on-premises organization, and they're synchronized with your Microsoft 365 organization.</span></span> <span data-ttu-id="08316-154">如需詳細資訊，請參閱[目錄整合](https://go.microsoft.com/fwlink/?LinkId=521788)。</span><span class="sxs-lookup"><span data-stu-id="08316-154">For more information, see[Directory Integration](https://go.microsoft.com/fwlink/?LinkId=521788) .</span></span>
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a><span data-ttu-id="08316-155">步驟 2：建立分段移轉批次所需的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="08316-155">Step 2: Create a CSV file for a staged migration batch</span></span>

<span data-ttu-id="08316-156">在您識別想要將其內部部署信箱遷移至 Microsoft 365 的使用者之後，您可以使用以逗號分隔的值 (CSV ) 檔案來建立遷移批次。</span><span class="sxs-lookup"><span data-stu-id="08316-156">After you identify the users whose on-premises mailboxes you want to migrate to Microsoft 365, you use a comma separated value (CSV ) file to create a migration batch.</span></span> <span data-ttu-id="08316-157">CSV 檔案中的每一列（Microsoft 365 用來執行遷移）包含內部部署信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="08316-157">Each row in the CSV file—used by Microsoft 365 to run the migration—contains information about an on-premises mailbox.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="08316-158">您可以使用分段遷移將信箱遷移至 Microsoft 365 的信箱數目不受限制。</span><span class="sxs-lookup"><span data-stu-id="08316-158">There isn't a limit for the number of mailboxes that you can migrate to Microsoft 365 using a staged migration.</span></span> <span data-ttu-id="08316-159">移轉批次的 CSV 檔案最多可包含 2,000 列。</span><span class="sxs-lookup"><span data-stu-id="08316-159">The CSV file for a migration batch can contain a maximum of 2,000 rows.</span></span> <span data-ttu-id="08316-160">若要移轉超過 2,000 個信箱，請建立其他 CSV 檔案並使用各個檔案建立新的移轉批次。</span><span class="sxs-lookup"><span data-stu-id="08316-160">To migrate more than 2,000 mailboxes, create additional CSV files and use each file to create a new migration batch.</span></span> 
  
 <span data-ttu-id="08316-161">**支援的屬性**</span><span class="sxs-lookup"><span data-stu-id="08316-161">**Supported attributes**</span></span>
  
<span data-ttu-id="08316-p116">分段移轉的 CSV 檔案支援下列三個屬性。CSV 檔案中的每一列都對應至一個信箱，而且必須包含這些屬性的值。</span><span class="sxs-lookup"><span data-stu-id="08316-p116">The CSV file for a staged migration supports the following three attributes. Each row in the CSV file corresponds to a mailbox and must contain a value for each of these attributes.</span></span>
  
|<span data-ttu-id="08316-164">**屬性**</span><span class="sxs-lookup"><span data-stu-id="08316-164">**Attribute**</span></span>|<span data-ttu-id="08316-165">**描述**</span><span class="sxs-lookup"><span data-stu-id="08316-165">**Description**</span></span>|<span data-ttu-id="08316-166">**Required?**</span><span class="sxs-lookup"><span data-stu-id="08316-166">**Required?**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08316-167">EmailAddress</span><span class="sxs-lookup"><span data-stu-id="08316-167">EmailAddress</span></span>  <br/> |<span data-ttu-id="08316-168">指定內部部署信箱的主要 SMTP 電子郵件地址，例如 pilarp@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="08316-168">Specifies the primary SMTP email address, for example, pilarp@contoso.com, for on-premises mailboxes.</span></span>  <br/> <span data-ttu-id="08316-169">使用內部部署信箱的主要 SMTP 位址，而非來自 Microsoft 365 的使用者 IDs。</span><span class="sxs-lookup"><span data-stu-id="08316-169">Use the primary SMTP address for on-premises mailboxes and not user IDs from the Microsoft 365.</span></span> <span data-ttu-id="08316-170">例如，如果內部部署網域命名為 contoso.com，但 Microsoft 365 電子郵件網域命名為 service.contoso.com，則會在 CSV 檔案中使用電子郵件地址的 contoso.com 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="08316-170">For example, if the on-premises domain is named contoso.com but the Microsoft 365 email domain is named service.contoso.com, you would use the contoso.com domain name for email addresses in the CSV file.</span></span>  <br/> |<span data-ttu-id="08316-171">必要</span><span class="sxs-lookup"><span data-stu-id="08316-171">Required</span></span>  <br/> |
|<span data-ttu-id="08316-172">密碼</span><span class="sxs-lookup"><span data-stu-id="08316-172">Password</span></span>  <br/> |<span data-ttu-id="08316-173">要為新的 Microsoft 365 信箱設定的密碼。</span><span class="sxs-lookup"><span data-stu-id="08316-173">The password to be set for the new Microsoft 365 mailbox.</span></span> <span data-ttu-id="08316-174">套用至您的 Microsoft 365 組織的任何密碼限制，也會套用到 CSV 檔案中包含的密碼。</span><span class="sxs-lookup"><span data-stu-id="08316-174">Any password restrictions that are applied to your Microsoft 365 organization also apply to the passwords included in the CSV file.</span></span>  <br/> |<span data-ttu-id="08316-175">選用</span><span class="sxs-lookup"><span data-stu-id="08316-175">Optional</span></span>  <br/> |
|<span data-ttu-id="08316-176">ForceChangePassword</span><span class="sxs-lookup"><span data-stu-id="08316-176">ForceChangePassword</span></span>  <br/> |<span data-ttu-id="08316-177">指定使用者第一次登入新的 Microsoft 365 信箱時，是否必須變更密碼。</span><span class="sxs-lookup"><span data-stu-id="08316-177">Specifies whether a user must change the password the first time they sign in to their new Microsoft 365 mailbox.</span></span> <span data-ttu-id="08316-178">使用 **True** 或 **False** 作為此參數的值。</span><span class="sxs-lookup"><span data-stu-id="08316-178">Use **True** or **False** for the value of this parameter.</span></span> <br/> <span data-ttu-id="08316-179">> [!NOTE]> 如果您已在內部部署組織中部署 Active Directory Federation Services (AD FS) 或更新版本來實作單一登入 (SSO) 解決方案，則必須使用 **False** 作為 **ForceChangePassword** 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="08316-179">> [!NOTE]> If you've implemented a single sign-on (SSO) solution by deploying Active Directory Federation Services (AD FS) or greater in your on-premises organization, you must use **False** for the value of the **ForceChangePassword** attribute.</span></span>          |<span data-ttu-id="08316-180">選用</span><span class="sxs-lookup"><span data-stu-id="08316-180">Optional</span></span>  <br/> |
   
 <span data-ttu-id="08316-181">**CSV 檔案格式**</span><span class="sxs-lookup"><span data-stu-id="08316-181">**CSV file format**</span></span>
  
<span data-ttu-id="08316-182">以下是 CSV 檔案的格式範例：</span><span class="sxs-lookup"><span data-stu-id="08316-182">Here's an example of the format for the CSV file.</span></span> <span data-ttu-id="08316-183">在此範例中，會將三個內部部署信箱遷移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="08316-183">In this example, three on-premises mailboxes are migrated to Microsoft 365.</span></span>
  
<span data-ttu-id="08316-p121">CSV 檔案的第一個資料列 (也稱為「標題列」) 會列出在後續幾列上指定的屬性或欄位名稱。每個屬性名稱都會以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="08316-p121">The first row, or header row, of the CSV file lists the names of the attributes, or fields, specified in the rows that follow. Each attribute name is separated by a comma.</span></span>
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

<span data-ttu-id="08316-p122">標頭列底下的每一個資料列都代表一個使用者，而且會提供移轉該使用者信箱所使用的詳細資訊。每一個資料列中屬性值的順序必須與標頭列中所列屬性名稱的順序相同。</span><span class="sxs-lookup"><span data-stu-id="08316-p122">Each row under the header row represents one user and supplies the information that will be used to migrate the user's mailbox. The attribute values in each row must be in the same order as the attribute names in the header row.</span></span> 
  
<span data-ttu-id="08316-p123">使用任何文字編輯器或 Excel 之類的應用程式來建立 CSV 檔案。將檔案儲存為 .csv 或 .txt 檔。</span><span class="sxs-lookup"><span data-stu-id="08316-p123">Use any text editor, or an application like Excel , to create the CSV file. Save the file as a .csv or .txt file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="08316-p124">如果 CSV 檔案包含非 ASCII 或特殊字元，請以 UTF-8 或其他 Unicode 編碼儲存該 CSV 檔案。依應用程式而定，當電腦的系統地區設定與 CSV 檔中所用的語言相符時，以 UTF-8 或其他 Unicode 編碼儲存 CSV 檔可能會比較容易。</span><span class="sxs-lookup"><span data-stu-id="08316-p124">If the CSV file contains non-ASCII or special characters, save the CSV file with UTF-8 or other Unicode encoding. Depending on the application, saving the CSV file with UTF-8 or other Unicode encoding can be easier when the system locale of the computer matches the language used in the CSV file.</span></span> 
  
### <a name="step-3-create-a-migration-endpoint"></a><span data-ttu-id="08316-192">步驟 3：建立移轉端點</span><span class="sxs-lookup"><span data-stu-id="08316-192">Step 3: Create a migration endpoint</span></span>
<span data-ttu-id="08316-193"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="08316-193"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="08316-194">若要成功遷移電子郵件，Microsoft 365 必須與來源電子郵件系統連線並進行通訊。</span><span class="sxs-lookup"><span data-stu-id="08316-194">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="08316-195">若要這樣做，Microsoft 365 會使用遷移端點。</span><span class="sxs-lookup"><span data-stu-id="08316-195">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="08316-196">若要使用 PowerShell 建立 Outlook 無所不在移轉端點以進行分段移轉，請先[連線至 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121)。</span><span class="sxs-lookup"><span data-stu-id="08316-196">To create an Outlook Anywhere migration endpoint by using PowerShell, for staged migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="08316-197">若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=534750)。</span><span class="sxs-lookup"><span data-stu-id="08316-197">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="08316-198">若要在 Exchange Online PowerShell 中建立名為 "StagedEndpoint" 的 Outlook 無所不在移轉端點，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="08316-198">To create an Outlook Anywhere migration endpoint called "StagedEndpoint" in Exchange Online PowerShell, run the following commands:</span></span>
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

<span data-ttu-id="08316-199">如需 **New-MigrationEndpoint** Cmdlet 的詳細資訊，請參閱[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437)。</span><span class="sxs-lookup"><span data-stu-id="08316-199">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
> [!NOTE]
> <span data-ttu-id="08316-p126">藉由使用 **-TargetDatabase** 選項，可以使用 **New-MigrationEndpoint** Cmdlet 來指定要使用之服務的資料庫。否則系統會從管理信箱所在的 Active Directory Federation Services (AD FS) 2.0 網站隨機指派資料庫。</span><span class="sxs-lookup"><span data-stu-id="08316-p126">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="08316-202">確認是否正常運作</span><span class="sxs-lookup"><span data-stu-id="08316-202">Verify it worked</span></span>

<span data-ttu-id="08316-203">在 Exchange Online PowerShell 中執行下列命令來顯示 "StagedEndpoint" 移轉端點的資訊：</span><span class="sxs-lookup"><span data-stu-id="08316-203">In Exchange Online PowerShell, run the following command to display information about the "StagedEndpoint" migration endpoint:</span></span>
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a><span data-ttu-id="08316-204">步驟 4：建立並啟動分段移轉批次</span><span class="sxs-lookup"><span data-stu-id="08316-204">Step 4: Create and start a stage migration batch</span></span>
<span data-ttu-id="08316-205"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="08316-205"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="08316-p127">您可以在 Exchange Online PowerShell 中使用 **New-MigrationBatch** Cmdlet，為完全移轉建立移轉批次。您可以建立移轉批次，並加上 _AutoStart_ 參數來自動啟動它。或者，您也可以先建立移轉批次，以後再手動使用 **Start-MigrationBatch** Cmdlet 啟動它。本範例會建立名為 "StagedBatch1" 的移轉批次，並使用上一個步驟中建立的移轉端點。</span><span class="sxs-lookup"><span data-stu-id="08316-p127">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step.</span></span>
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

<span data-ttu-id="08316-p128">本範例也會建立名為 "StagedBatch1" 的移轉批次，並使用上一個步驟中建立的移轉端點。因為其中並未加上  _AutoStart_ 參數，所以需要在移轉儀表板上或使用 **Start-MigrationBatch** Cmdlet 來手動啟動此移轉批次。如前所述，一次只能有一個完全移轉批次。</span><span class="sxs-lookup"><span data-stu-id="08316-p128">This example also creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="08316-213">確認是否正常運作</span><span class="sxs-lookup"><span data-stu-id="08316-213">Verify it worked</span></span>

<span data-ttu-id="08316-214">在 Exchange Online PowerShell 中執行下列命令來顯示 "StagedBatch1" 的資訊：</span><span class="sxs-lookup"><span data-stu-id="08316-214">Run the following command in Exchange Online PowerShell to display information about the "StagedBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

<span data-ttu-id="08316-215">您也可以執行下列命令來確認批次已啟動：</span><span class="sxs-lookup"><span data-stu-id="08316-215">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

<span data-ttu-id="08316-216">如需 **Get-MigrationBatch** Cmdlet 的詳細資訊，請參閱[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)。</span><span class="sxs-lookup"><span data-stu-id="08316-216">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a><span data-ttu-id="08316-217">步驟 5：將內部部署信箱轉換成擁有郵件功能的使用者</span><span class="sxs-lookup"><span data-stu-id="08316-217">Step 5: Convert on-premises mailboxes to mail-enabled users</span></span>
<span data-ttu-id="08316-218"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="08316-218"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="08316-219">成功移轉信箱批次之後，您必須有方法能讓使用者存取他們的郵件。</span><span class="sxs-lookup"><span data-stu-id="08316-219">After you have successfully migrated a batch of mailboxes, you need some way to let users get to their mail.</span></span> <span data-ttu-id="08316-220">已遷移之信箱的使用者現在具有內部部署信箱，另一個是 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="08316-220">A user whose mailbox has been migrated now has both a mailbox on-premises and one in Microsoft 365.</span></span> <span data-ttu-id="08316-221">在 Microsoft 365 中擁有信箱的使用者，將會停止接收內部部署信箱中的新郵件。</span><span class="sxs-lookup"><span data-stu-id="08316-221">Users who have a mailbox in Microsoft 365 will stop receiving new mail in their on-premises mailbox.</span></span> 
  
<span data-ttu-id="08316-222">因為您未進行遷移，所以尚未準備好將所有使用者指引至其電子郵件的 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="08316-222">Because you are not done with your migrations, you are not yet ready to direct all users to Microsoft 365 for their email.</span></span> <span data-ttu-id="08316-223">所以該如何處理同時擁有兩個信箱的使用者？</span><span class="sxs-lookup"><span data-stu-id="08316-223">So what do you do for those people who have both?</span></span> <span data-ttu-id="08316-224">您可以變更已移轉至「啟用郵件功能的使用者」的內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="08316-224">What you can do is change the on-premises mailboxes that you've already migrated to mail-enabled users.</span></span> <span data-ttu-id="08316-225">當您從信箱變更為擁有郵件功能的使用者時，您可以將使用者導向電子郵件給 Microsoft 365，而不是移至其內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="08316-225">When you change from a mailbox to a mail-enabled user, you can direct the user to Microsoft 365 for their email instead of going to their on-premises mailbox.</span></span> 
  
<span data-ttu-id="08316-226">將內部部署信箱轉換成擁有郵件功能的使用者的另一個重要原因是，將 proxy 位址複製到啟用郵件功能的使用者，以保留 Microsoft 365 信箱的 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="08316-226">Another important reason to convert on-premises mailboxes to mail-enabled users is to retain proxy addresses from the Microsoft 365 mailboxes by copying proxy addresses to the mail-enabled users.</span></span> <span data-ttu-id="08316-227">如此可讓您使用 Active Directory 從內部部署組織管理雲端使用者。</span><span class="sxs-lookup"><span data-stu-id="08316-227">This lets you manage cloud-based users from your on-premises organization by using Active Directory.</span></span> <span data-ttu-id="08316-228">此外，如果您決定在將所有信箱遷移至 Microsoft 365 之後解除委任內部部署 Exchange Server 組織，您已複製到擁有郵件功能之使用者的 proxy 位址仍會保留在您的內部部署 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="08316-228">Also, if you decide to decommission your on-premises Exchange Server organization after all mailboxes are migrated to Microsoft 365, the proxy addresses you've copied to the mail-enabled users will remain in your on-premises Active Directory.</span></span>
    
### <a name="step-6-delete-a-staged-migration-batch"></a><span data-ttu-id="08316-229">步驟 6：刪除分段移轉批次</span><span class="sxs-lookup"><span data-stu-id="08316-229">Step 6: Delete a staged migration batch</span></span>
<span data-ttu-id="08316-230"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="08316-230"><a name="BK_Endpoint"> </a></span></span>

 <span data-ttu-id="08316-231">將移轉批次中的所有信箱順利移轉，並將批次中的內部部署信箱轉換成擁有郵件功能的使用者後，就可以刪除分段移轉批次。</span><span class="sxs-lookup"><span data-stu-id="08316-231">After all mailboxes in a migration batch have been successfully migrated, and you've converted the on-premises mailboxes in the batch to mail-enabled users, you're ready to delete a staged migration batch.</span></span> <span data-ttu-id="08316-232">請務必確認郵件已轉送至遷移批次中的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="08316-232">Be sure to verify that mail is being forwarded to the Microsoft 365 mailboxes in the migration batch.</span></span> <span data-ttu-id="08316-233">當您刪除分段移轉批次時，移轉服務會清除與該移轉批次相關的所有記錄，並刪除該移轉批次。</span><span class="sxs-lookup"><span data-stu-id="08316-233">When you delete a staged migration batch, the migration service cleans up any records related to the migration batch and deletes the migration batch.</span></span>
  
<span data-ttu-id="08316-234">若要刪除 Exchange Online PowerShell 中的 "StagedBatch1" 移轉批次，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="08316-234">To delete the "StagedBatch1" migration batch in Exchange Online PowerShell, run the following command.</span></span>
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

<span data-ttu-id="08316-235">如需 **Remove-MigrationBatch** Cmdlet 的詳細資訊，請參閱[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481)。</span><span class="sxs-lookup"><span data-stu-id="08316-235">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="08316-236">確認是否正常運作</span><span class="sxs-lookup"><span data-stu-id="08316-236">Verify it worked</span></span>

<span data-ttu-id="08316-237">在 Exchange Online PowerShell 中執行下列命令來顯示 "IMAPBatch1" 的資訊：</span><span class="sxs-lookup"><span data-stu-id="08316-237">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch StagedBatch1
```

<span data-ttu-id="08316-238">此命令會傳回狀態為 **Removing** 的移轉批次，或傳回錯誤，指出找不到移轉批次而需確認該批次是否已刪除。</span><span class="sxs-lookup"><span data-stu-id="08316-238">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="08316-239">如需 **Get-MigrationBatch** Cmdlet 的詳細資訊，請參閱[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)。</span><span class="sxs-lookup"><span data-stu-id="08316-239">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a><span data-ttu-id="08316-240">Step7：將授權指派給 Microsoft 365 使用者</span><span class="sxs-lookup"><span data-stu-id="08316-240">Step7: Assign licenses to Microsoft 365 users</span></span>
<span data-ttu-id="08316-241"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="08316-241"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="08316-242">指派授權，為遷移的帳戶啟動 Microsoft 365 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="08316-242">Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.</span></span> <span data-ttu-id="08316-243">如果您未指派授權，則當寬限期 (30 天) 結束時就會停用信箱。</span><span class="sxs-lookup"><span data-stu-id="08316-243">If you don't assign a license, the mailbox is disabled when the grace period (30 days) ends.</span></span> <span data-ttu-id="08316-244">若要在 Microsoft 365 系統管理中心中指派授權，請參閱 [指派或取消指派授權](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="08316-244">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
  
### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="08316-245">步驟 8：完成移轉後工作</span><span class="sxs-lookup"><span data-stu-id="08316-245">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="08316-246"><a name="BK_Postmigration"> </a></span><span class="sxs-lookup"><span data-stu-id="08316-246"><a name="BK_Postmigration"> </a></span></span>

- <span data-ttu-id="08316-247">**建立自動探索 DNS 記錄，讓使用者可以輕鬆存取信箱。**</span><span class="sxs-lookup"><span data-stu-id="08316-247">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="08316-248">在所有內部部署信箱遷移至 Microsoft 365 之後，您可以設定 Microsoft 365 組織的自動探索 DNS 記錄，讓使用者能夠使用 Outlook 和行動用戶端輕鬆連線到其新的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="08316-248">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="08316-249">這個新的自動探索 DNS 記錄必須使用您的 Microsoft 365 組織所使用的相同命名空間。</span><span class="sxs-lookup"><span data-stu-id="08316-249">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="08316-250">舉例來說，如果您的雲端架構命名空間是 cloud.contoso.com，則您需要建立的自動探索 DNS 記錄是 autodiscover.cloud.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="08316-250">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>
    
    <span data-ttu-id="08316-251">Microsoft 365 使用 CNAME 記錄來實施 Outlook 和行動用戶端的自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="08316-251">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="08316-252">自動探索 CNAME 記錄必須包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="08316-252">The Autodiscover CNAME record must contain the following information:</span></span>
    
  - <span data-ttu-id="08316-253">**別名：** 自動探索</span><span class="sxs-lookup"><span data-stu-id="08316-253">**Alias:** autodiscover</span></span>
    
  - <span data-ttu-id="08316-254">**目標：** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="08316-254">**Target:** autodiscover.outlook.com</span></span>
    
    <span data-ttu-id="08316-255">如需詳細資訊，請參閱 [新增 DNS 記錄以連接您的網域](https://go.microsoft.com/fwlink/p/?LinkId=535028)。</span><span class="sxs-lookup"><span data-stu-id="08316-255">For more information, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span></span>
    
- <span data-ttu-id="08316-256">**解除委任內部部署 Exchange 伺服器。**</span><span class="sxs-lookup"><span data-stu-id="08316-256">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="08316-257">在您確認所有電子郵件都直接路由傳送至 Microsoft 365 信箱之後，如果您不再需要維護內部部署電子郵件組織，或不計畫實施 SSO 解決方案，您可以從伺服器卸載 Exchange，並移除內部部署 Exchange 組織。</span><span class="sxs-lookup"><span data-stu-id="08316-257">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing an SSO solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>
    
    <span data-ttu-id="08316-258">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="08316-258">For more information, see the following:</span></span>
    
  - [<span data-ttu-id="08316-259">修改及移除 Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="08316-259">Modify or Remove Exchange 2010</span></span>](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [<span data-ttu-id="08316-260">如何移除 Exchange 2007 組織</span><span class="sxs-lookup"><span data-stu-id="08316-260">How to Remove an Exchange 2007 Organization</span></span>](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [<span data-ttu-id="08316-261">如何解除安裝 Exchange Server 2003</span><span class="sxs-lookup"><span data-stu-id="08316-261">How to Uninstall Exchange Server 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=56561)
    

