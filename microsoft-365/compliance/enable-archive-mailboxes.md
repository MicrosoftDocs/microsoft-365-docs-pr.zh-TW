---
title: 啟用「安全性與合規性中心」的封存信箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: 使用 Office 365 中的「安全性與合規性中心」來啟用封存信箱，以便支援組織的郵件保留、電子文件探索和保留需求。
ms.openlocfilehash: 36a5f2003232d55fd82965773b38a26c4fa29b33
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074722"
---
# <a name="enable-archive-mailboxes-in-the-security--compliance-center"></a><span data-ttu-id="a0ef3-103">啟用「安全性與合規性中心」的封存信箱</span><span class="sxs-lookup"><span data-stu-id="a0ef3-103">Enable archive mailboxes in the Security & Compliance Center</span></span>
  
<span data-ttu-id="a0ef3-104">Office 365 中的封存 (稱為就地封存) 可為使用者提供額外的信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-104">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space.</span></span> <span data-ttu-id="a0ef3-105">開啟封存信箱後，使用者只要使用 Microsoft Outlook 和 Outlook 網頁版 (其前身為 Outlook Web App) 即可存取及儲存封存信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-105">After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="a0ef3-106">使用者也可以在其主要信箱和封存信箱之間移動或複製郵件。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-106">Users can also move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="a0ef3-107">除此之外，他們也可以使用「復原刪除的郵件」工具復原其封存信箱的 [可復原的項目] 資料夾中的已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-107">They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a0ef3-108">Office 365 中的自動展開封存功能提供封存信箱的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-108">The auto-expanding archiving feature in Office 365 provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="a0ef3-109">如果已開啟自動展開封存功能，當使用者封存信箱的初始儲存配額已滿時，Office 365 會自動新增額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-109">When auto-expanding  archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space.</span></span> <span data-ttu-id="a0ef3-110">也就是說，使用者的信箱儲存空間將不會用盡，若您一開始就啟用封存信箱並為組織開啟自動展開封存功能，之後就能高枕無憂。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-110">This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization.</span></span> <span data-ttu-id="a0ef3-111">如需詳細資訊，請參閱[在 Office 365 中的無限制封存的概觀](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-111">For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="a0ef3-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="a0ef3-112">Before you begin</span></span>

<span data-ttu-id="a0ef3-113">您必須在 Exchange Online 中獲派郵件收件者角色，以便啟用或停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-113">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes.</span></span> <span data-ttu-id="a0ef3-114">根據預設，系統會將這個角色指派給 Exchange 系統管理中心 [權限]\*\*\*\* 頁面上的 [收件者管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-114">By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="a0ef3-115">如果您在「安全性與合規性中心」看不到 [封存]\*\*\*\* 頁面，請要求系統管理員指派必要權限給您。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-115">If you don't see the **Archive** page in the Security & Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="a0ef3-116">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="a0ef3-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="a0ef3-117">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="a0ef3-118">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="a0ef3-119">在「安全性與合規性中心」的左窗格中，按一下 **[資料控管]** \> **[封存]**。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-119">In the left pane of the Security & Compliance Center, click **Information governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="a0ef3-p104">[封存]\*\*\*\* 頁面隨即出現。[封存信箱] \*\*\*\* 欄會指出每個使用者的封存信箱是啟用還是停用。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="a0ef3-122">在信箱清單中，選取要為其啟用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![在選取使用者的詳細資料窗格中按一下 [啟用]，以啟用封存信箱](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="a0ef3-124">在所選使用者的詳細資料窗格中按一下 [啟用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="a0ef3-125">系統會顯示警告訊息，提醒您如果啟用封存信箱，系統會將使用者信箱中超過指派給信箱之封存原則的郵件移至新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-125">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox.</span></span> <span data-ttu-id="a0ef3-126">預設的封存原則 (該原則屬於指派給 Exchange Online 信箱之保留原則的一部分) 會在將郵件傳遞至信箱或使用者建立郵件當日的兩年後，將郵件移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-126">The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="a0ef3-127">如需詳細資訊，請參閱本文中的 [其他資訊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-127">For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="a0ef3-128">按一下 [是] 啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="a0ef3-129">可能需要一些時間才能建立封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-129">It might take a few moments to create the archive mailbox.</span></span> <span data-ttu-id="a0ef3-130">建立封存信箱後，您可在選取使用者的詳細資料窗格中看到 [封存信箱：已啟用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-130">When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="a0ef3-131">您可能需要按一下 [重新整理]\*\*\*\* ![重新整理圖示](../media/O365-MDM-Policy-RefreshIcon.gif)，以便更新詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-131">You might have to click **Refresh** ![Refresh icon](../media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="a0ef3-p107">您也可以選取多個信箱 (使用 Shift 或 Ctrl 鍵) 來大量啟用封存。選取多個信箱後，按一下詳細資料窗格中的 [啟用]。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="a0ef3-134">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="a0ef3-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="a0ef3-135">您也可以使用「安全性與合規性中心」中的 [封存]\*\*\*\* 頁面來停用使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-135">You can also use the **Archive** page in the Security & Compliance Center to disable a user's archive mailbox.</span></span> <span data-ttu-id="a0ef3-136">停用封存信箱之後，可以在停用它的 30 天內重新連線至使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-136">After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it.</span></span> <span data-ttu-id="a0ef3-137">在此情況下，系統會還原封存信箱的原始內容。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-137">In this case, the original contents of the archive mailbox are restored.</span></span> <span data-ttu-id="a0ef3-138">30 天後，便會永久刪除原始封存信箱的內容，無法再復原。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-138">After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered.</span></span> <span data-ttu-id="a0ef3-139">因此，如果您在停用封存超過 30 天之後才重新啟用它，系統會建立新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-139">So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="a0ef3-140">請注意，在郵件傳遞當日的兩年後，指派給使用者信箱的預設封存原則會將郵件移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-140">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered.</span></span> <span data-ttu-id="a0ef3-141">即使您將使用者的封存信箱停用，也不會對信箱郵件造成影響，系統會將這些郵件保留在使用者的主要信箱中。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-141">If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="a0ef3-142">若要停用封存信箱：</span><span class="sxs-lookup"><span data-stu-id="a0ef3-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="a0ef3-143">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="a0ef3-144">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="a0ef3-145">在「安全性與合規性中心」的左窗格中，按一下 **[資料控管]** \> **[封存]**。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-145">In the left pane of the Security & Compliance Center, click **Information governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="a0ef3-p110">[封存]\*\*\*\* 頁面隨即出現。[封存信箱] \*\*\*\* 欄會指出每個使用者的封存信箱是啟用還是停用。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="a0ef3-148">在信箱清單中，選取要為其停用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="a0ef3-149">在詳細資料窗格中，按一下 [停用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="a0ef3-150">系統會顯示警告訊息，提醒您有 30 天的時間可以重新啟用封存信箱，30 天之後，系統將會永久刪除封存中的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="a0ef3-151">按一下 [是] 停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="a0ef3-152">可能需要一些時間才能停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-152">It might take a few moments to disable the archive mailbox.</span></span> <span data-ttu-id="a0ef3-153">停用封存信箱後，您可在選取使用者的詳細資料窗格中看到 [封存信箱：已停用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-153">When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="a0ef3-154">您可能需要按一下 [重新整理]\*\*\*\* ![重新整理圖示](../media/O365-MDM-Policy-RefreshIcon.gif)，以便更新詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-154">You might have to click **Refresh** ![Refresh icon](../media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="a0ef3-p112">您也可以選取多個已啟用封存信箱的使用者 (使用 Shift 或 Ctrl 鍵) 來大量停用封存信箱。選取多個信箱後，按一下詳細資料窗格中的 [停用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="a0ef3-157">使用 Exchange Online PowerShell 來啟用或停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="a0ef3-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="a0ef3-158">您也可以使用 Exchange Online PowerShell 來啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-158">You can also use Exchange Online PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="a0ef3-159">使用 PowerShell 的主要原因是您可以為組織中的所有使用者快速啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-159">The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="a0ef3-160">第一個步驟是連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-160">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="a0ef3-161">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-161">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="a0ef3-162">連線到 Exchange Online 後，您可以執行下列各節中的命令，以便啟用或停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="a0ef3-163">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="a0ef3-163">Enable archive mailboxes</span></span>

<span data-ttu-id="a0ef3-164">執行下列命令，以便啟用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```powershell
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="a0ef3-165">執行下列命令，以便啟用組織中所有使用者的封存信箱 (針對目前尚未啟用封存信箱者)。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```powershell
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```

### <a name="disable-archive-mailboxes"></a><span data-ttu-id="a0ef3-166">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="a0ef3-166">Disable archive mailboxes</span></span>

<span data-ttu-id="a0ef3-167">執行下列命令，以便停用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```powershell
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="a0ef3-168">執行下列命令，以便停用組織中所有使用者的封存信箱 (針對目前已啟用封存信箱者)。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```powershell
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="a0ef3-169">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a0ef3-169">More information</span></span>
  
- <span data-ttu-id="a0ef3-170">當封存信箱啟用時，使用者可以將郵件儲存在其封存信箱中。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-170">When an archive mailbox is enabled, users can store messages in their archive mailbox.</span></span> <span data-ttu-id="a0ef3-171">使用者可以使用 Microsoft Outlook 和 Outlook 網頁版來存取其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-171">Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web.</span></span> <span data-ttu-id="a0ef3-172">只要使用這些用戶端應用程式，使用者就能檢視其封存信箱中的郵件，並且在其主要信箱與其封存信箱之間移動或複製郵件。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-172">Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="a0ef3-173">使用者也可以使用「復原刪除的郵件」工具復原其封存信箱的 [可復原的項目] 資料夾中的已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-173">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span>

   <span data-ttu-id="a0ef3-174">如需支援就地封存的 Outlook 授權清單，請參閱[Exchange 功能的 Outlook 授權需求](https://support.office.com/article/outlook-license-requirements-for-exchange-features-46b6b7c5-c3ca-43e5-8424-1e2807917c99)。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-174">For a list of Outlook licenses that support In-Place Archiving, see [Outlook license requirements for Exchange features](https://support.office.com/article/outlook-license-requirements-for-exchange-features-46b6b7c5-c3ca-43e5-8424-1e2807917c99).</span></span>

- <span data-ttu-id="a0ef3-175">封存信箱可協助您和您的使用者符合組織的保留、電子文件探索和保留需求。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-175">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements.</span></span> <span data-ttu-id="a0ef3-176">例如，您可以使用組織的 Exchange 保留原則，將信箱內容移至使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-176">For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox.</span></span> <span data-ttu-id="a0ef3-177">使用「安全性與合規性中心」的「內容搜尋」工具搜尋使用者信箱的特定內容時，系統也會一併搜尋使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-177">When you use the Content Search tool in the Security & Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched.</span></span> <span data-ttu-id="a0ef3-178">此外，當您加入訴訟資料暫留或是將 Office 365 保留原則套用至使用者的信箱時，系統也會保留封存信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-178">And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="a0ef3-179">啟用封存信箱後，您的組織即可使用自動指派給每個信箱的預設 Exchange 保留原則 (也稱為「通訊記錄管理」或 MRM 原則)。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-179">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox.</span></span> <span data-ttu-id="a0ef3-180">啟用封存信箱時，預設 Exchange 保留原則會自動執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a0ef3-180">When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="a0ef3-181">將使用者主要信箱中兩年以上的郵件移到其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-181">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="a0ef3-182">將使用者主要信箱的 [可復原的項目] 資料夾中 14 天以上的郵件移至其封存信箱的 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a0ef3-182">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="a0ef3-183">如需封存信箱及 Exchange 保留原則的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="a0ef3-183">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
    
  - [<span data-ttu-id="a0ef3-184">保留標記和保留原則</span><span class="sxs-lookup"><span data-stu-id="a0ef3-184">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="a0ef3-185">Exchange Online 中的預設保留原則</span><span class="sxs-lookup"><span data-stu-id="a0ef3-185">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="a0ef3-186">設定您 Office 365 組織中的信箱封存和刪除原則</span><span class="sxs-lookup"><span data-stu-id="a0ef3-186">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
