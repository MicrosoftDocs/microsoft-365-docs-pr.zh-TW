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
ms.custom: seo-marvel-apr2020
description: 瞭解如何使用合規性中心來啟用封存信箱，以便支援組織的郵件保留、電子文件探索和保留需求。
ms.openlocfilehash: d7506b92cc16120f1d40a6d5a1744ab38d446a76
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233813"
---
# <a name="enable-archive-mailboxes-in-the-compliance-center"></a><span data-ttu-id="3a378-103">啟用合規性中心的封存信箱</span><span class="sxs-lookup"><span data-stu-id="3a378-103">Enable archive mailboxes in the compliance center</span></span>

<span data-ttu-id="3a378-104">Microsoft 365 中的封存 (也稱為 *就地封存*) 可為使用者提供額外的信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="3a378-104">Archiving in Microsoft 365 (also called *In-Place Archiving*) provides users with additional mailbox storage space.</span></span> <span data-ttu-id="3a378-105">開啟封存信箱後，使用者只要使用 Microsoft Outlook 和 Outlook 網頁版 (其前身為 Outlook Web App) 即可存取及儲存封存信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="3a378-105">After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="3a378-106">使用者也可以在其主要信箱和封存信箱之間移動或複製郵件。</span><span class="sxs-lookup"><span data-stu-id="3a378-106">Users can also move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="3a378-107">除此之外，他們也可以使用「復原刪除的郵件」工具復原其封存信箱的 [可復原的項目] 資料夾中的已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="3a378-107">They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span>

> [!NOTE]
> <span data-ttu-id="3a378-108">Microsoft 365 中的自動展開封存功能提供封存信箱額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="3a378-108">The auto-expanding archiving feature in Microsoft 365 provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="3a378-109">如果已開啟自動展開封存功能，當使用者封存信箱的初始儲存配額已滿時，Microsoft 365 會自動新增額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="3a378-109">When auto-expanding  archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Microsoft 365 automatically adds additional storage space.</span></span> <span data-ttu-id="3a378-110">也就是說，使用者的信箱儲存空間將不會用盡，若您一開始就啟用封存信箱並為組織開啟自動展開封存功能，之後就能高枕無憂。</span><span class="sxs-lookup"><span data-stu-id="3a378-110">This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization.</span></span> <span data-ttu-id="3a378-111">如需詳細資訊，請參閱 [無限制封存的概觀](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="3a378-111">For more information, see [Overview of unlimited archiving](unlimited-archiving.md).</span></span>

## <a name="get-the-necessary-permissions"></a><span data-ttu-id="3a378-112">獲取必要權限</span><span class="sxs-lookup"><span data-stu-id="3a378-112">Get the necessary permissions</span></span>

<span data-ttu-id="3a378-113">您必須在 Exchange Online 中獲派郵件收件者角色，以便啟用或停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-113">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes.</span></span> <span data-ttu-id="3a378-114">根據預設，系統會將這個角色指派給 Exchange 系統管理中心 [權限] 頁面上的 [收件者管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="3a378-114">By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="3a378-115">如果您在「安全性與合規性中心」看不到 [封存] 頁面，請要求系統管理員指派必要權限給您。</span><span class="sxs-lookup"><span data-stu-id="3a378-115">If you don't see the **Archive** page in the Security & Compliance Center, ask your administrator to assign you the necessary permissions.</span></span>

## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="3a378-116">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="3a378-116">Enable an archive mailbox</span></span>

1. <span data-ttu-id="3a378-117">移至<https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="3a378-117">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="3a378-118">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3a378-118">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="3a378-119">在「安全性與合規性中心」的左窗格中，按一下 **[資料控管]** \> **[封存]**。</span><span class="sxs-lookup"><span data-stu-id="3a378-119">In the left pane of the Security & Compliance Center, click **Information governance** \> **Archive**.</span></span>

   <span data-ttu-id="3a378-p104">[封存] 頁面隨即出現。[封存信箱] 欄會指出每個使用者的封存信箱是啟用還是停用。</span><span class="sxs-lookup"><span data-stu-id="3a378-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3a378-122">**[封存]** 頁面最多顯示500個使用者。</span><span class="sxs-lookup"><span data-stu-id="3a378-122">The **Archive** page shows a maximum of 500 users.</span></span>

4. <span data-ttu-id="3a378-123">在信箱清單中，選取要為其啟用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="3a378-123">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>

   ![在選取使用者的詳細資料窗格中按一下 [啟用]，以啟用封存信箱](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)

5. <span data-ttu-id="3a378-125">在所選使用者的詳細資料窗格中按一下 [啟用]。</span><span class="sxs-lookup"><span data-stu-id="3a378-125">In the details pane for the selected user, click **Enable**.</span></span>

   <span data-ttu-id="3a378-126">系統會顯示警告訊息，提醒您如果啟用封存信箱，系統會將使用者信箱中超過指派給信箱之封存原則的郵件移至新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-126">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox.</span></span> <span data-ttu-id="3a378-127">預設的封存原則 (該原則屬於指派給 Exchange Online 信箱之保留原則的一部分) 會在將郵件傳遞至信箱或使用者建立郵件當日的兩年後，將郵件移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-127">The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="3a378-128">如需詳細資訊，請參閱本文中的 [其他資訊]。</span><span class="sxs-lookup"><span data-stu-id="3a378-128">For more information, see the **More info** section in this article.</span></span>

6. <span data-ttu-id="3a378-129">按一下 [是] 啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-129">Click **Yes** to enable the archive mailbox.</span></span>

   <span data-ttu-id="3a378-130">可能需要一些時間才能建立封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-130">It might take a few moments to create the archive mailbox.</span></span> <span data-ttu-id="3a378-131">建立封存信箱後，您可在選取使用者的詳細資料窗格中看到 [封存信箱：已啟用]。</span><span class="sxs-lookup"><span data-stu-id="3a378-131">When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="3a378-132">您可能需要按一下 [重新整理] ![重新整理圖示](../media/O365-MDM-Policy-RefreshIcon.gif)，以便更新詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="3a378-132">You might have to click **Refresh** ![Refresh icon](../media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span>

> [!TIP]
> <span data-ttu-id="3a378-p107">您也可以選取多個信箱 (使用 Shift 或 Ctrl 鍵) 來大量啟用封存。選取多個信箱後，按一下詳細資料窗格中的 [啟用]。</span><span class="sxs-lookup"><span data-stu-id="3a378-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span>

## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="3a378-135">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="3a378-135">Disable an archive mailbox</span></span>

<span data-ttu-id="3a378-136">您也可以使用「安全性與合規性中心」中的 [封存] 頁面來停用使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-136">You can also use the **Archive** page in the Security & Compliance Center to disable a user's archive mailbox.</span></span> <span data-ttu-id="3a378-137">停用封存信箱之後，可以在停用它的 30 天內重新連線至使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-137">After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it.</span></span> <span data-ttu-id="3a378-138">在此情況下，系統會還原封存信箱的原始內容。</span><span class="sxs-lookup"><span data-stu-id="3a378-138">In this case, the original contents of the archive mailbox are restored.</span></span> <span data-ttu-id="3a378-139">30 天後，便會永久刪除原始封存信箱的內容，無法再復原。</span><span class="sxs-lookup"><span data-stu-id="3a378-139">After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered.</span></span> <span data-ttu-id="3a378-140">因此，如果您在停用封存超過 30 天之後才重新啟用它，系統會建立新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-140">So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span>

<span data-ttu-id="3a378-141">在郵件傳遞當日的兩年後，指派給使用者信箱的預設封存原則會將郵件移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-141">The default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered.</span></span> <span data-ttu-id="3a378-142">即使您將使用者的封存信箱停用，也不會對信箱郵件造成影響，系統會將這些郵件保留在使用者的主要信箱中。</span><span class="sxs-lookup"><span data-stu-id="3a378-142">If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>

<span data-ttu-id="3a378-143">若要停用封存信箱：</span><span class="sxs-lookup"><span data-stu-id="3a378-143">To disable an archive mailbox:</span></span>

1. <span data-ttu-id="3a378-144">移至<https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="3a378-144">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="3a378-145">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3a378-145">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="3a378-146">在「安全性與合規性中心」的左窗格中，按一下 **[資料控管]** \> **[封存]**。</span><span class="sxs-lookup"><span data-stu-id="3a378-146">In the left pane of the Security & Compliance Center, click **Information governance** \> **Archive**.</span></span>

   <span data-ttu-id="3a378-p110">[封存] 頁面隨即出現。[封存信箱] 欄會指出每個使用者的封存信箱是啟用還是停用。</span><span class="sxs-lookup"><span data-stu-id="3a378-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3a378-149">**[封存]** 頁面最多顯示500個使用者。</span><span class="sxs-lookup"><span data-stu-id="3a378-149">The **Archive** page shows a maximum of 500 users.</span></span>

4. <span data-ttu-id="3a378-150">在信箱清單中，選取要為其停用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="3a378-150">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>

5. <span data-ttu-id="3a378-151">在詳細資料窗格中，按一下 [停用]。</span><span class="sxs-lookup"><span data-stu-id="3a378-151">In the details pane, click **Disable**.</span></span>

   <span data-ttu-id="3a378-152">系統會顯示警告訊息，提醒您有 30 天的時間可以重新啟用封存信箱，30 天之後，系統將會永久刪除封存中的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="3a378-152">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span>

6. <span data-ttu-id="3a378-153">按一下 [是] 停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-153">Click **Yes** to disable the archive mailbox.</span></span>

   <span data-ttu-id="3a378-154">可能需要一些時間才能停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-154">It might take a few moments to disable the archive mailbox.</span></span> <span data-ttu-id="3a378-155">停用封存信箱後，您可在選取使用者的詳細資料窗格中看到 [封存信箱：已停用]。</span><span class="sxs-lookup"><span data-stu-id="3a378-155">When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="3a378-156">您可能需要按一下 [重新整理] ![重新整理圖示](../media/O365-MDM-Policy-RefreshIcon.gif)，以便更新詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="3a378-156">You might have to click **Refresh** ![Refresh icon](../media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span>

> [!TIP]
> <span data-ttu-id="3a378-p112">您也可以選取多個已啟用封存信箱的使用者 (使用 Shift 或 Ctrl 鍵) 來大量停用封存信箱。選取多個信箱後，按一下詳細資料窗格中的 [停用]。</span><span class="sxs-lookup"><span data-stu-id="3a378-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="3a378-159">使用 Exchange Online PowerShell 來啟用或停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="3a378-159">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="3a378-160">您也可以使用 Exchange Online PowerShell 來啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-160">You can also use Exchange Online PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="3a378-161">使用 PowerShell 的主要原因是您可以為組織中的所有使用者快速啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-161">The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="3a378-162">第一個步驟是連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3a378-162">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="3a378-163">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3a378-163">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="3a378-164">連線到 Exchange Online 後，您可以執行下列各節中的命令，以便啟用或停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-164">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="3a378-165">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="3a378-165">Enable archive mailboxes</span></span>

<span data-ttu-id="3a378-166">執行下列命令，以便啟用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-166">Run the following command to enable the archive mailbox for a single user.</span></span>

```powershell
Enable-Mailbox -Identity <username> -Archive
```

<span data-ttu-id="3a378-167">執行下列命令，以便啟用組織中所有使用者的封存信箱 (針對目前尚未啟用封存信箱者)。</span><span class="sxs-lookup"><span data-stu-id="3a378-167">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>

```powershell
Get-Mailbox -Filter {ArchiveGuid -Eq "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Enable-Mailbox -Archive
```

### <a name="disable-archive-mailboxes"></a><span data-ttu-id="3a378-168">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="3a378-168">Disable archive mailboxes</span></span>

<span data-ttu-id="3a378-169">執行下列命令，以便停用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-169">Run the following command to disable the archive mailbox for a single user.</span></span>

```powershell
Disable-Mailbox -Identity <username> -Archive
```

<span data-ttu-id="3a378-170">執行下列命令，以便停用組織中所有使用者的封存信箱 (針對目前已啟用封存信箱者)。</span><span class="sxs-lookup"><span data-stu-id="3a378-170">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>

```powershell
Get-Mailbox -Filter {ArchiveGuid -Ne "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Disable-Mailbox -Archive
```

## <a name="more-information"></a><span data-ttu-id="3a378-171">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3a378-171">More information</span></span>

- <span data-ttu-id="3a378-172">當封存信箱啟用時，使用者可以將郵件儲存在其封存信箱中。</span><span class="sxs-lookup"><span data-stu-id="3a378-172">When an archive mailbox is enabled, users can store messages in their archive mailbox.</span></span> <span data-ttu-id="3a378-173">使用者可以使用 Microsoft Outlook 和 Outlook 網頁版來存取其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-173">Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web.</span></span> <span data-ttu-id="3a378-174">只要使用這些用戶端應用程式，使用者就能檢視其封存信箱中的郵件，並且在其主要信箱與其封存信箱之間移動或複製郵件。</span><span class="sxs-lookup"><span data-stu-id="3a378-174">Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="3a378-175">使用者也可以使用「復原刪除的郵件」工具復原其封存信箱的 [可復原的項目] 資料夾中的已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="3a378-175">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span>

  <span data-ttu-id="3a378-176">如需支援就地封存的 Outlook 授權清單，請參閱[Exchange 功能的 Outlook 授權需求](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99)。</span><span class="sxs-lookup"><span data-stu-id="3a378-176">For a list of Outlook licenses that support In-Place Archiving, see [Outlook license requirements for Exchange features](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99).</span></span>

- <span data-ttu-id="3a378-177">封存信箱可協助您和您的使用者符合組織的保留、電子文件探索和保留需求。</span><span class="sxs-lookup"><span data-stu-id="3a378-177">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements.</span></span> <span data-ttu-id="3a378-178">例如，您可以使用組織的 Exchange 保留原則，將信箱內容移至使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-178">For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox.</span></span> <span data-ttu-id="3a378-179">使用「安全性與合規性中心」的「內容搜尋」工具搜尋使用者信箱的特定內容時，系統也會一併搜尋使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-179">When you use the Content Search tool in the Security & Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched.</span></span> <span data-ttu-id="3a378-180">此外，當您採行訴訟資料暫留或是將保留原則套用至使用者的信箱時，系統也會保留封存信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="3a378-180">And, when you place a Litigation Hold or apply a retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>

- <span data-ttu-id="3a378-181">啟用封存信箱後，您的組織即可使用自動指派給每個信箱的預設 Exchange 保留原則 (也稱為「通訊記錄管理」或 MRM 原則)。</span><span class="sxs-lookup"><span data-stu-id="3a378-181">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox.</span></span> <span data-ttu-id="3a378-182">啟用封存信箱時，預設 Exchange 保留原則會自動執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3a378-182">When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span>

  - <span data-ttu-id="3a378-183">將使用者主要信箱中兩年以上的郵件移到其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="3a378-183">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span>

  - <span data-ttu-id="3a378-184">將使用者主要信箱的 [可復原的項目] 資料夾中 14 天以上的郵件移至其封存信箱的 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="3a378-184">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>

- <span data-ttu-id="3a378-185">如需封存信箱及 Exchange 保留原則的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="3a378-185">For more information about archive mailboxes and Exchange retention policies, see:</span></span>

  - [<span data-ttu-id="3a378-186">Exchange Online 中的保留標記和保留原則</span><span class="sxs-lookup"><span data-stu-id="3a378-186">Retention tags and retention policies in Exchange Online</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

  - [<span data-ttu-id="3a378-187">Exchange Online 中的預設保留原則</span><span class="sxs-lookup"><span data-stu-id="3a378-187">Default Retention Policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

  - [<span data-ttu-id="3a378-188">設定組織中的信箱封存和刪除原則</span><span class="sxs-lookup"><span data-stu-id="3a378-188">Set up an archive and deletion policy for mailboxes in your organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
