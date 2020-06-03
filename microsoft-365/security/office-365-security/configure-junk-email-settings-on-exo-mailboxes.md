---
title: 設定 Exchange Online 信箱上的垃圾郵件設定
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Exchange Online 信箱中設定垃圾郵件設定。 在 Outlook 或 web 上的 Outlook 中，使用者可以使用許多這些設定。
ms.openlocfilehash: 40364db9d4af9e093d8f2f74ee3c0f0373b1671a
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498660"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a><span data-ttu-id="e3f9a-104">設定 Exchange Online 信箱上的垃圾郵件設定</span><span class="sxs-lookup"><span data-stu-id="e3f9a-104">Configure junk email settings on Exchange Online mailboxes</span></span>

<span data-ttu-id="e3f9a-105">在 Exchange Online 中有信箱的 Microsoft 365 組織中，組織的反垃圾郵件設定是由 Exchange Online Protection （EOP）控制。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-105">In Microsoft 365 organizations with mailboxes in Exchange Online, organizational anti-spam settings are controlled by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="e3f9a-106">如需詳細資訊，請參閱[EOP 中的反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-106">For more information, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

<span data-ttu-id="e3f9a-107">不過，系統管理員也可以在 Exchange Online 中個別的信箱上設定特定的反垃圾郵件設定：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-107">But, there are also specific anti-spam settings that admins can configure on individual mailboxes in Exchange Online:</span></span>

- <span data-ttu-id="e3f9a-108">**啟用或停用垃圾郵件規則**：「垃圾郵件規則」是一種隱藏的收件匣規則，名稱為「垃圾郵件規則」預設會在每個信箱中啟用。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-108">**Enable or disable the junk email rule**: The junk email rule is a hidden Inbox rule named Junk E-mail Rule that's enabled by default in every mailbox.</span></span> <span data-ttu-id="e3f9a-109">垃圾郵件規則會控制下列功能：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-109">The junk email rule controls the following features:</span></span>

  - <span data-ttu-id="e3f9a-110">**根據反垃圾郵件原則將郵件移至 [垃圾郵件] 資料夾**：當反垃圾郵件原則使用 [**將郵件移至垃圾郵件] 資料夾**設定為垃圾郵件篩選判定時，垃圾郵件篩選規則會在郵件傳遞至信箱之後，將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-110">**Move messages to the Junk Email folder based on anti-spam policies**: When an anti-spam policy is configured with the action **Move message to Junk Email folder** for a spam filtering verdict, the junk email filter rule moves the message to the Junk Email folder after the message is delivered to the mailbox.</span></span> <span data-ttu-id="e3f9a-111">如需反垃圾郵件原則中垃圾郵件篩選 verdicts 的詳細資訊，請參閱[設定 EOP 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-111">For more information about spam filtering verdicts in anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="e3f9a-112">同樣地，如果零小時自動清除（ZAP）決定傳遞的郵件為垃圾郵件或網路釣魚，垃圾郵件篩選規則會將郵件移至 [垃圾郵件] 資料夾，將**郵件移至**[垃圾郵件] 資料夾。垃圾郵件篩選判定的動作。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-112">Similarly, if zero-hour auto purge (ZAP) determines a delivered message is spam or phish, the junk email filter rule moves the message to the Junk Email folder for **Move message to Junk Email folder** spam filtering verdict actions.</span></span> <span data-ttu-id="e3f9a-113">如需有關 ZAP 的詳細資訊，請參閱[在 Exchange Online 中以零小時自動清除（ZAP）](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-113">For more information about ZAP, see [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).</span></span>
  
  - <span data-ttu-id="e3f9a-114">**使用者在 outlook 或網頁型 outlook 中為自己自行設定的垃圾郵件設定**：安全_組集合_為安全寄件者清單、安全收件者清單，以及每個信箱上的封鎖寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-114">**Junk email settings that users configure for themselves in Outlook or Outlook on the web**: The _safelist collection_ is the Safe Senders list, the Safe Recipients list, and the Block senders list on each mailbox.</span></span> <span data-ttu-id="e3f9a-115">這些清單中的專案會決定垃圾郵件規則是否會將郵件移至 [收件匣] 或 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-115">The entries in these lists determine whether the junk email rule moves the message to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="e3f9a-116">使用者可以在 Outlook 或網頁型 outlook （先前稱為 Outlook Web App）中為自己的信箱設定安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-116">Users can configure the safelist collection for their own mailbox in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="e3f9a-117">系統管理員可以在任何使用者的信箱上設定安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-117">Admins can configure the safelist collection on any user's mailbox.</span></span>

<span data-ttu-id="e3f9a-118">當信箱上已啟用垃圾郵件規則時，EOP 可以根據垃圾郵件篩選判定動作將郵件移至 [垃圾郵件] 資料夾，並將郵件移至 [垃圾郵件]**資料夾**或信箱上的 [封鎖寄件者] 清單，並防止郵件傳遞至 [垃圾郵件] 資料夾（根據信箱上的 [安全的寄件者] 清單）。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-118">When the junk email rule is enabled on the mailbox, EOP is able to move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the Blocked Senders list on the mailbox, and prevent messages from being delivered to the Junk Email folder (based on the Safe Senders list on the mailbox).</span></span>

 <span data-ttu-id="e3f9a-119">當信箱上的垃圾郵件規則停用時，EOP 無法根據垃圾郵件篩選判定動作將郵件移至垃圾郵件資料夾。**將郵件移至垃圾郵件資料夾**或信箱上的安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-119">When the junk email rule is disabled on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="e3f9a-120">系統管理員可以使用 Exchange Online PowerShell 來停用、啟用和查看信箱上垃圾郵件規則的狀態。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-120">Admins can use Exchange Online PowerShell to disable, enable, and view the status of the junk email rule on mailboxes.</span></span> <span data-ttu-id="e3f9a-121">系統管理員也可以使用 Exchange Online PowerShell 來設定信箱上的安全清單集合中的專案（[安全寄件者] 清單、[安全的收件者] 清單和 [封鎖寄件者] 清單）。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-121">Admins can also use Exchange Online PowerShell to configure entries in the safelist collection on mailboxes (the Safe Senders list, the Safe Recipients list, and the Block senders list).</span></span>

> [!NOTE]
> <span data-ttu-id="e3f9a-122">來自使用者已新增至自己安全寄件者清單中寄件者的郵件，將會略過連線篩選做為 EOP 的一部分（SCL 為-1）。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-122">Messages from senders that users have added to their own Safe Senders lists will skip connection filtering as part of EOP (the SCL is -1).</span></span> <span data-ttu-id="e3f9a-123">若要防止使用者將專案新增至 Outlook 的安全寄件者清單，請使用本主題稍後的 [[關於 Outlook 中的垃圾郵件設定](#about-junk-email-settings-in-outlook)] 區段中所述的群組原則。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-123">To prevent users from adding entries to their Safe Senders list in Outlook, use Group Policy as mentioned in the  [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section later in this topic.</span></span> <span data-ttu-id="e3f9a-124">原則篩選、內容篩選和高級威脅防護（ATP）檢查仍會套用到郵件。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-124">Policy filtering, Content filtering and Advanced Threat Protection (ATP) checks will still be applied to the messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e3f9a-125">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="e3f9a-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e3f9a-126">您只可以使用 Exchange Online PowerShell 來執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-126">You can only use Exchange Online PowerShell to perform these procedures.</span></span> <span data-ttu-id="e3f9a-127">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e3f9a-128">您必須已獲指派許可權，才能執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-128">You need to be assigned permissions before you can do these procedures.</span></span> <span data-ttu-id="e3f9a-129">具體而言，您需要 **「郵件**收件者」角色（預設會指派給**組織管理**、**收件者管理**和**自訂郵件**收件者角色群組）或 [**使用者選項**] 角色（預設會指派給「**組織管理** **」和「服務台」** 角色群組）。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-129">Specifically, you need the **Mail Recipients** role (which is assigned to the **Organization Management**, **Recipient Management**, and **Custom Mail Recipients** role groups by default) or the **User Options** role (which is assigned to the **Organization Management** and **Help Desk** role groups by default).</span></span> <span data-ttu-id="e3f9a-130">若要將使用者新增至 Exchange Online 中的角色群組，請參閱[Modify role groups In Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-130">To add users to role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span> <span data-ttu-id="e3f9a-131">請注意，具有預設許可權的使用者可以在自己的信箱上執行這些相同的程式，只要他們可以[存取 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-131">Note that a user with default permissions can do these same procedures on their own mailbox, as long as they have [access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e3f9a-132">在獨立版 EOP 環境中，EOP 會保護內部部署 Exchange 信箱，您必須在內部部署 Exchange 中設定郵件流程規則 (又稱為傳輸規則) 以轉譯 EOP 垃圾郵件篩選裁決，這樣垃圾郵件規則才可以將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-132">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="e3f9a-133">如需詳細資訊，請參閱[設定獨立版 EOP 將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-133">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

- <span data-ttu-id="e3f9a-134">共用信箱的安全寄件者不會與 Azure AD 同步處理，也不會 EOP 設計。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-134">Safe Senders for shared mailboxes are not synchronized to Azure AD and EOP by design.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a><span data-ttu-id="e3f9a-135">使用 Exchange Online PowerShell 啟用或停用信箱中的垃圾郵件規則</span><span class="sxs-lookup"><span data-stu-id="e3f9a-135">Use Exchange Online PowerShell to enable or disable the junk email rule in a mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="e3f9a-136">您只能使用 **Set-MailboxJunkEmailConfiguration** Cmdlet 來停用已在 Outlook (在快取 Exchange 模式) 或 網頁型 Outlook 中開啟的信箱的垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-136">You can only use the **Set-MailboxJunkEmailConfiguration** cmdlet to disable the junk email rule on a mailbox that's been opened in Outlook (in Cached Exchange mode) or Outlook on the web.</span></span> <span data-ttu-id="e3f9a-137">若尚未開啟信箱，您會收到錯誤： `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` 如果您想要針對大量作業隱藏此錯誤，您可以將此錯誤新增 `-ErrorAction SlientlyContinue` 至**Set-MailboxJunkEmailConfiguration**命令。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-137">If the mailbox hasn't been opened, you'll receive the error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` If you want to suppress this error for bulk operations, you can add `-ErrorAction SlientlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

<span data-ttu-id="e3f9a-138">若要啟用或停用信箱中的垃圾郵件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-138">To enable or disable the junk email rule on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

<span data-ttu-id="e3f9a-139">本範例會停用 Ori Epstein 的信箱上的垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-139">This example disables the junk email rule on Ori Epstein's mailbox.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

<span data-ttu-id="e3f9a-140">本範例會停用組織中所有使用者信箱的垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-140">This example disables the junk email rule on all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

<span data-ttu-id="e3f9a-141">如需詳細的語法及參數資訊，請參閱[Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-141">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="e3f9a-142">如果使用者從未開啟其信箱，當您執行先前的命令時，可能會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-142">If the user has never opened their mailbox, you might receive an error when you run the previous command.</span></span> <span data-ttu-id="e3f9a-143">若要抑制大量作業的此錯誤，請新增 `-ErrorAction SlientlyContinue` 至**Set-MailboxJunkEmailConfiguration**命令。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-143">To suppress this error for bulk operations, add `-ErrorAction SlientlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
> 
> - <span data-ttu-id="e3f9a-144">即使您停用垃圾郵件規則，Outlook 垃圾郵件篩選器（取決於其設定方式）也可以判斷郵件是否為垃圾郵件，以及是否可以將郵件移至 [收件匣] 或 [垃圾郵件] 資料夾（根據其本身的垃圾郵件，以及信箱上的安全清單集合）。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-144">Even if you disable the junk email rule, the Outlook Junk Email Filter (depending on how it's configured) can also determine whether a message is spam, and can move messages to the Inbox or Junk Email folder based on it's own spam verdict and the the safelist collection on the mailbox.</span></span> <span data-ttu-id="e3f9a-145">如需詳細資訊，請參閱本主題中的＜[關於 Outlook 中的垃圾郵件設定](#about-junk-email-settings-in-outlook)＞章節。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-145">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e3f9a-146">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="e3f9a-146">How do you know this worked?</span></span>

<span data-ttu-id="e3f9a-147">若要確認您已成功啟用或停用信箱上的垃圾郵件規則，請使用下列程序：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-147">To verify that you have successfully enabled or disabled the junk email rule on a mailbox, use any of the following procedures:</span></span>

- <span data-ttu-id="e3f9a-148">_\<MailboxIdentity\>_ 以信箱的名稱、別名或電子郵件地址取代，並執行下列命令來驗證**Enabled**屬性值：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-148">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a><span data-ttu-id="e3f9a-149">使用 Exchange Online PowerShell 設定信箱上的安全清單集合</span><span class="sxs-lookup"><span data-stu-id="e3f9a-149">Use Exchange Online PowerShell to configure the safelist collection on a mailbox</span></span>

<span data-ttu-id="e3f9a-150">信箱上的安全清單集合包含 [安全寄件者] 清單、[安全收件者] 清單及 [封鎖寄件者] 清單。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-150">The safelist collection on a mailbox includes the Safe Senders list, the Safe Recipients list, and the Blocked Senders list.</span></span> <span data-ttu-id="e3f9a-151">根據預設，使用者可以在 Outlook 或網頁型 Outlook 中設定自己信箱上的安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-151">By default, users can configure the safelist collection on their own mailbox in Outlook or Outlook on the web.</span></span> <span data-ttu-id="e3f9a-152">系統管理員可以使用 **Set-MailboxJunkEmailConfiguration** Cmdlet 上的對應參數，在使用者的信箱上設定安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-152">Administrators can use the corresponding parameters on the **Set-MailboxJunkEmailConfiguration** cmdlet to configure the safelist collection on a user's mailbox.</span></span> <span data-ttu-id="e3f9a-153">下表將說明這些參數。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-153">These parameters are described in the following table.</span></span>

|||
|---|---|
|<span data-ttu-id="e3f9a-154">**Set-MailboxJunkEmailConfiguration 的參數**</span><span class="sxs-lookup"><span data-stu-id="e3f9a-154">**Parameter on Set-MailboxJunkEmailConfiguration**</span></span>|<span data-ttu-id="e3f9a-155">**網頁上的 Outlook 設定**</span><span class="sxs-lookup"><span data-stu-id="e3f9a-155">**Outlook on the web setting**</span></span>|
|<span data-ttu-id="e3f9a-156">_BlockedSendersAndDomains_</span><span class="sxs-lookup"><span data-stu-id="e3f9a-156">_BlockedSendersAndDomains_</span></span>|<span data-ttu-id="e3f9a-157">**將來自這些寄件者或網域的電子郵件移至我的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="e3f9a-157">**Move email from these senders or domains to my Junk Email folder**</span></span>|
|<span data-ttu-id="e3f9a-158">_ContactsTrusted_</span><span class="sxs-lookup"><span data-stu-id="e3f9a-158">_ContactsTrusted_</span></span>|<span data-ttu-id="e3f9a-159">**信任來自我的連絡人的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="e3f9a-159">**Trust email from my contacts**</span></span>|
|<span data-ttu-id="e3f9a-160">_TrustedListsOnly_</span><span class="sxs-lookup"><span data-stu-id="e3f9a-160">_TrustedListsOnly_</span></span>|<span data-ttu-id="e3f9a-161">**只信任「我的安全寄件者和網域」清單中的電子郵件和安全郵寄清單中的位址**</span><span class="sxs-lookup"><span data-stu-id="e3f9a-161">**Only trust email from addresses in my Safe senders and domains list and Safe mailing lists**</span></span>|
|<span data-ttu-id="e3f9a-162">_TrustedSendersAndDomains_<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3f9a-162">_TrustedSendersAndDomains_<sup>\*</sup></span></span>|<span data-ttu-id="e3f9a-163">**不將這些寄件者的電子郵件移至我的垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="e3f9a-163">**Don't move email from these senders to my Junk Email folder**</span></span>|
|

<span data-ttu-id="e3f9a-164"><sup>\*</sup>**附注**：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-164"><sup>\*</sup> **Notes**:</span></span>

- <span data-ttu-id="e3f9a-165">在 Exchange Online 中，無法辨識 [安全的寄件者] 清單或 [ _TrustedSendersAndDomains_ ] 參數中的**網域專案**，因此只會使用電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-165">In Exchange Online, **domain entries** in the Safe Senders list or _TrustedSendersAndDomains_ parameter aren't recognized, so only use email addresses.</span></span> <span data-ttu-id="e3f9a-166">在具有目錄同步處理的獨立 EOP 中，預設不會同步處理網域專案，但您可以啟用網域的同步處理。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-166">In standalone EOP with directory synchronization, domain entries aren't synchronized by default, but you can enable synchronization for domains.</span></span> <span data-ttu-id="e3f9a-167">如需詳細資訊，請參閱[KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-167">For more information, see [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange).</span></span>

- <span data-ttu-id="e3f9a-168">您無法使用**Set-MailboxJunkEmailConfiguration** Cmdlet 直接修改 [安全的收件者] 清單（ _TrustedRecipientsAndDomains_參數無法使用）。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-168">You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work).</span></span> <span data-ttu-id="e3f9a-169">修改 [安全寄件者] 清單中，這些變更就會同步處理至 [安全收件者] 清單。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-169">You modify the Safe Senders list, and those changes are synchronized to the Safe Recipients list.</span></span>

<span data-ttu-id="e3f9a-170">若要設定信箱上的安全清單集合，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-170">To configure the safelist collection on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

<span data-ttu-id="e3f9a-171">若要輸入多個值，並覆寫_BlockedSendersAndDomains_和_TrustedSendersAndDomains_參數的任何現有專案，請使用下列語法： `"<Value1>","<Value2>"...` 。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-171">To enter multiple values and overwrite any existing entries for the _BlockedSendersAndDomains_ and _TrustedSendersAndDomains_ parameters, use the following syntax: `"<Value1>","<Value2>"...`.</span></span> <span data-ttu-id="e3f9a-172">若要新增或移除一個或多個值，而不影響其他現有的專案，請使用下列語法：`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span><span class="sxs-lookup"><span data-stu-id="e3f9a-172">To add or remove one or more values without affecting other existing entries, use the following syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span></span>

<span data-ttu-id="e3f9a-173">本範例會將 Ori Epstein 信箱上的安全清單集合設定為下列設定：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-173">This example configures the following settings for the safelist collection on Ori Epstein's mailbox:</span></span>

- <span data-ttu-id="e3f9a-174">將 shopping@fabrikam.com 值新增至 [封鎖的寄件者] 清單。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-174">Add the value shopping@fabrikam.com to the Blocked Senders list.</span></span>

- <span data-ttu-id="e3f9a-175">從 [安全的寄件者] 清單和 [安全的收件者] 清單中移除 value chris@fourthcoffee.com。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-175">Remove the value chris@fourthcoffee.com from the Safe Senders list and the Safe Recipients list.</span></span>

- <span data-ttu-id="e3f9a-176">設定要視為受信任寄件者的 [連絡人] 資料夾中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-176">Configures contacts in the Contacts folder to be treated as trusted senders.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

<span data-ttu-id="e3f9a-177">這個範例會移除組織中所有使用者信箱的 [封鎖寄件者] 清單中的網域 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-177">This example removes the domain contoso.com from the Blocked Senders list in all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

<span data-ttu-id="e3f9a-178">如需詳細的語法及參數資訊，請參閱[Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-178">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="e3f9a-179">如果使用者從未開啟其信箱，當您執行先前的命令時，可能會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-179">If the user has never opened their mailbox, you might receive an error when you run the previous commands.</span></span> <span data-ttu-id="e3f9a-180">若要抑制大量作業的此錯誤，請新增 `-ErrorAction SlientlyContinue` 至**Set-MailboxJunkEmailConfiguration**命令。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-180">To suppress this error for bulk operations, add `-ErrorAction SlientlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
> 
> - <span data-ttu-id="e3f9a-181">即使停用信箱上的垃圾郵件規則，仍然可以設定安全清單集合，而 Outlook 垃圾郵件篩選器可以將郵件移至收件匣或 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-181">Even if the junk email rule is disabled on the mailbox, you can still configure the safelist collection, and the Outlook Junk Email Filter is able to move messages to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="e3f9a-182">如需詳細資訊，請參閱本主題中的＜[關於 Outlook 中的垃圾郵件設定](#about-junk-email-settings-in-outlook)＞章節。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-182">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>
> 
> - <span data-ttu-id="e3f9a-183">Outlook 垃圾郵件篩選器有其他安全清單集合設定（例如，**自動將我的電子郵件新增至安全寄件者清單**）。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-183">The Outlook Junk Email Filter has additional safelist collection settings (for example, **Automatically add people I email to the Safe Senders list**).</span></span> <span data-ttu-id="e3f9a-184">如需詳細資訊，請參閱＜[使用垃圾郵件篩選器來控制要查看的訊息](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077)＞。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-184">For more information, see [Use Junk Email Filters to control which messages you see](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e3f9a-185">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="e3f9a-185">How do you know this worked?</span></span>

<span data-ttu-id="e3f9a-186">若要驗證您是否已成功設定信箱上的安全清單集合，請使用任何下列程序：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-186">To verify that you have successfully configured the safelist collection on a mailbox, use any of following procedures:</span></span>

- <span data-ttu-id="e3f9a-187">取代 _\<MailboxIdentity\>_ 信箱的名稱、別名或電子郵件地址，並執行下列命令來驗證屬性值：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-187">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the property values:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  <span data-ttu-id="e3f9a-188">如果值清單過長，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-188">If the list of values is too long, use this syntax:</span></span>

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a><span data-ttu-id="e3f9a-189">關於 Outlook 中的垃圾郵件設定</span><span class="sxs-lookup"><span data-stu-id="e3f9a-189">About junk email settings in Outlook</span></span>

<span data-ttu-id="e3f9a-190">若要啟用、停用及設定 Outlook 中可用的用戶端垃圾郵件篩選器設定，請使用「群組」原則。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-190">To enable, disable, and configure the client-side Junk Email Filter settings that are available in Outlook, use Group Policy.</span></span> <span data-ttu-id="e3f9a-191">如需詳細資訊，請參閱系統[管理範本檔案（ADMX/ADML）和 Office 自訂365工具（適用于企業、office 2019 及 office 2016](https://www.microsoft.com/download/details.aspx?id=49030) ）和[如何使用群組原則部署垃圾郵件設定，例如安全寄件者清單](https://support.microsoft.com/help/2252421/how-to-deploy-junk-email-settings-such-as-the-safe-senders-list-by-usi)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-191">For more information, see [Administrative Template files (ADMX/ADML) and Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) and [How to deploy junk email settings, such as the Safe Senders list, by using Group Policy](https://support.microsoft.com/help/2252421/how-to-deploy-junk-email-settings-such-as-the-safe-senders-list-by-usi).</span></span>

<span data-ttu-id="e3f9a-192">當 outlook 垃圾郵件篩選器設定為預設值時，**不會自動篩選\*\*\*\*家用** \> **垃圾** \> **郵件 E-Mail 選項** \> **選項**，Outlook 不會嘗試將 massages 歸類為垃圾郵件，但仍然使用安全性群組集合（安全的寄件者清單、安全的收件者清單和封鎖的寄件者清單）將郵件移至 [垃圾郵件] 資料夾傳送後。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-192">When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook doesn't attempt to classify massages as spam, but still uses the safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery.</span></span> <span data-ttu-id="e3f9a-193">如需這些設定的詳細資訊，請參閱[垃圾郵件篩選程式的概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-193">For more information about these settings, see [Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

<span data-ttu-id="e3f9a-194">當 Outlook 垃圾郵件篩選器設定為 **[低]** 或 **[高]** 時，Outlook [垃圾郵件篩選器] 會使用它自己的 SmartScreen 篩選技術來進行識別，並將垃圾郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-194">When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span></span> <span data-ttu-id="e3f9a-195">這種垃圾郵件分類與 EOP 所決定的垃圾郵件信賴等級（SCL）不同。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-195">This spam classification is separate from the spam confidence level (SCL) that's determined by EOP.</span></span> <span data-ttu-id="e3f9a-196">實際上，Outlook 會忽略 SCL EOP （除非 EOP 標示郵件以略過垃圾郵件篩選），並使用其自己的準則來判斷郵件是否為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-196">In fact, Outlook ignores the SCL from EOP (unless EOP marked the message to skip spam filtering) and uses its own criteria to determine whether the message is spam.</span></span> <span data-ttu-id="e3f9a-197">當然，EOP 和 Outlook 的垃圾郵件可能都是相同的。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-197">Of course, it's possible that the spam verdict from EOP and Outlook might be the same.</span></span> <span data-ttu-id="e3f9a-198">如需這些設定的詳細資訊，請參閱[變更垃圾郵件篩選器中的保護層級](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-198">For more information about these settings, see [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b).</span></span>

> [!NOTE]
> <span data-ttu-id="e3f9a-199">在11月2016中，Microsoft 已停止為 Exchange 和 Outlook 中的 SmartScreen 篩選器產生垃圾郵件定義更新。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-199">In November 2016, Microsoft stopped producing spam definition updates for the SmartScreen filters in Exchange and Outlook.</span></span> <span data-ttu-id="e3f9a-200">現有的 SmartScreen 垃圾郵件定義會保留，但其效果可能會隨著時間降低。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-200">The existing SmartScreen spam definitions were left in place, but their effectiveness will likely degrade over time.</span></span> <span data-ttu-id="e3f9a-201">如需詳細資訊，請參閱 [Outlook 和 Exchange 中 SmartScreen 的取代支援](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-201">For more information, see [Deprecating support for SmartScreen in Outlook and Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).</span></span>

<span data-ttu-id="e3f9a-202">因此，Outlook 垃圾郵件篩選器可以使用信箱的安全清單集合和其自己的垃圾郵件分類，將郵件移至 [垃圾郵件] 資料夾，即使信箱中已停用垃圾郵件規則也是一樣。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-202">So, the Outlook Junk Email Filter is able to use the mailbox's safelist collection and its own spam classification to move messages to the Junk Email folder, even if the junk email rule is disabled in the mailbox.</span></span>

<span data-ttu-id="e3f9a-203">Outlook 和 網頁型 Outlook 兩者都支援安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-203">Outlook and Outlook on the web both support the safelist collection.</span></span> <span data-ttu-id="e3f9a-204">安全清單集合會儲存在 Exchange Online 信箱中，所以 Outlook 中的安全清單集合變更會顯示在 Outlook 網頁版中，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-204">The safelist collection is saved in the Exchange Online mailbox, so changes to the safelist collection in Outlook appear in Outlook on the web, and vice-versa.</span></span>

## <a name="limits-for-junk-email-settings"></a><span data-ttu-id="e3f9a-205">垃圾郵件設定的限制</span><span class="sxs-lookup"><span data-stu-id="e3f9a-205">Limits for junk email settings</span></span>

<span data-ttu-id="e3f9a-206">儲存在使用者信箱中的安全清單集合（[安全的寄件者] 清單、[安全的收件者] 清單和 [封鎖的寄件者] 清單）也會同步處理至 EOP。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-206">The safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) that's stored in the user's mailbox is also synchronized to EOP.</span></span> <span data-ttu-id="e3f9a-207">使用目錄同步作業時，安全清單集合會同步至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-207">With directory synchronization, the safelist collection is synchronized to Azure AD.</span></span>

- <span data-ttu-id="e3f9a-208">使用者信箱中的安全清單集合具有 510 KB 的限制，其中包括所有清單，再加上其他垃圾郵件篩選設定。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-208">The safelist collection in the user's mailbox has a limit of 510 KB, which includes all lists, plus additional junk email filter settings.</span></span> <span data-ttu-id="e3f9a-209">如果使用者超過此限制，將會收到類似以下的 Outlook 錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-209">If a user exceeds this limit, they will receive an Outlook error that looks like this:</span></span>

  > <span data-ttu-id="e3f9a-210">無法/無法新增至 [伺服器] [垃圾郵件] 清單。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-210">Cannot/Unable add to the server Junk E-mail lists.</span></span> <span data-ttu-id="e3f9a-211">您可以在伺服器上的大小超過所允許的大小。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-211">You are over the size allowed on the server.</span></span> <span data-ttu-id="e3f9a-212">除非您的垃圾郵件清單縮小為伺服器允許的大小，否則伺服器上的垃圾郵件篩選器將會停用。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-212">The Junk E-mail filter on the server will be disabled until your Junk E-mail lists have been reduced to the size allowed by the server.</span></span>

  <span data-ttu-id="e3f9a-213">如需此限制及其變更方式的詳細資訊，請參閱[KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit)。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-213">For more information about this limit and how to change it, see [KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit).</span></span>

- <span data-ttu-id="e3f9a-214">EOP 中的同步安全清單集合具有下列同步處理限制：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-214">The synchronized safelist collection in EOP has the following synchronization limits:</span></span>

  - <span data-ttu-id="e3f9a-215">1024 [安全寄件者] 清單、[安全的收件者] 清單和外部連絡人（如果啟用 [**來自我的連絡人的信任電子郵件**]）的專案總數</span><span class="sxs-lookup"><span data-stu-id="e3f9a-215">1024 total entries in the Safe Senders list, the Safe Recipients list, and external contacts if **Trust email from my contacts** is enabled.</span></span>
  - <span data-ttu-id="e3f9a-216">500封鎖的寄件者清單與封鎖的網域清單中的專案總數。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-216">500 total entries in the Blocked Senders list and Blocked Domains list.</span></span>

  <span data-ttu-id="e3f9a-217">達到1024專案限制時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-217">When the 1024 entry limit is reached, the following things happen:</span></span>
  
  - <span data-ttu-id="e3f9a-218">清單會停止接受 PowerShell 和 Outlook 網頁版中的專案，但不會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-218">The list stops accepting entries in PowerShell and Outlook on the web, but no error is displayed.</span></span>

    <span data-ttu-id="e3f9a-219">Outlook 使用者可以繼續加入超過1024個專案，直到達到 Outlook 限制 510 KB 為止。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-219">Outlook users can continue to add more than 1024 entries until they reach the Outlook limit of 510 KB.</span></span> <span data-ttu-id="e3f9a-220">EOP 篩選傳遞至信箱（郵件流程規則、反欺騙等等）之後，Outlook 可以使用這些額外的專案。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-220">Outlook can use these additional entries, as long as an EOP filter doesn't block the message before delivery to the mailbox (mail flow rules, anti-spoofing, etc.).</span></span>

- <span data-ttu-id="e3f9a-221">透過目錄同步作業，專案會依照下列順序同步到 Azure AD：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-221">With directory synchronization, the entries are synchronized to Azure AD in the following order:</span></span>

  1. <span data-ttu-id="e3f9a-222">如果已啟用 [**來自我的連絡人的信任電子郵件**]，則為郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-222">Mail contacts if **Trust email from my contacts** is enabled.</span></span>
  2. <span data-ttu-id="e3f9a-223">每當為第一個1024專案進行變更時，安全寄件者清單及安全收件者清單都會加上重複記錄，並依字母順序排序。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-223">The Safe Sender list and Safe Recipient list are combined, de-duplicated, and sorted alphabetically whenever a change is made for the first 1024 entries.</span></span>

  <span data-ttu-id="e3f9a-224">使用第一個1024專案，並在郵件頭中戳相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-224">The first 1024 entries are used, and relevant information is stamped in the message headers.</span></span>
  
  <span data-ttu-id="e3f9a-225">超過1024的專案（未同步至 Azure AD）是由 Outlook 處理（而不是網頁上的 Outlook），而且不會在郵件頭中標記任何資訊。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-225">Entries over 1024 that weren't synchronized to Azure AD are processed by Outlook (not Outlook on the web), and no information is stamped in the message headers.</span></span>

<span data-ttu-id="e3f9a-226">如您所見，啟用 [**來自我的連絡人的信任電子郵件**] 設定會減少安全寄件者的數目，以及可同步處理的安全收件者數目。</span><span class="sxs-lookup"><span data-stu-id="e3f9a-226">As you can see, enabling the **Trust email from my contacts** setting reduces the number of Safe Senders and Safe Recipients that can be synchronized.</span></span> <span data-ttu-id="e3f9a-227">如果有問題，我們建議使用「群組原則」關閉此功能：</span><span class="sxs-lookup"><span data-stu-id="e3f9a-227">If this is a concern, then we recommend using Group Policy to turn this feature off:</span></span>

- <span data-ttu-id="e3f9a-228">檔案名： outlk16。 opax</span><span class="sxs-lookup"><span data-stu-id="e3f9a-228">File name: outlk16.opax</span></span>
- <span data-ttu-id="e3f9a-229">原則設定：**信任來自連絡人的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="e3f9a-229">Policy setting: **Trust e-mail from contacts**</span></span>
