---
title: 從共用信箱中查看和發行隔離的郵件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 使用者可以瞭解如何針對已傳送至其許可權之共用信箱的隔離郵件，查看並採取行動。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9490a9d5b2b4191d6c039be2758e2e0ba0c981cd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203772"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="46ac0-103">從共用信箱中查看和發行隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="46ac0-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="46ac0-104">本文中所述的功能目前在預覽中，無法供所有人使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="46ac0-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="46ac0-105">使用者可以管理被隔離的郵件，而這些郵件是以 [EOP 中的使用者身分發現和發行隔離郵件](find-and-release-quarantined-messages-as-a-user.md)所述的其中一位收件者。</span><span class="sxs-lookup"><span data-stu-id="46ac0-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="46ac0-106">不過，如果使用者擁有信箱的「完整存取」和「代理傳送」或「代理傳送者」許可權（如 [Exchange Online 中的共用信箱](/exchange/collaboration-exo/shared-mailboxes)所述），共用信箱又該如何做呢？</span><span class="sxs-lookup"><span data-stu-id="46ac0-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="46ac0-107">先前，使用者能夠管理傳送至共用信箱的隔離郵件時，系統管理員可以將自動對應啟用，以供系統管理員在使用者存取另一個信箱) 時，預設會啟用該共用 (信箱。</span><span class="sxs-lookup"><span data-stu-id="46ac0-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="46ac0-108">不過，視使用者有權存取的信箱大小和數目而定，當 Outlooks 嘗試開啟使用者可以存取的 *所有* 信箱時，效能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="46ac0-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="46ac0-109">基於這個理由，許多系統管理員會選擇 [移除共用信箱的自動對應](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="46ac0-109">For this reason, many admins choose to [remove automapping for shared mailboxes](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="46ac0-110">現在，使用者不再需要自動對應來管理傳送至共用信箱的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="46ac0-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="46ac0-111">它只適用于運作。</span><span class="sxs-lookup"><span data-stu-id="46ac0-111">It just works.</span></span> <span data-ttu-id="46ac0-112">有兩種不同的方法可以存取已傳送至共用信箱的隔離郵件：</span><span class="sxs-lookup"><span data-stu-id="46ac0-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="46ac0-113">如果系統管理員已在反垃圾郵件原則中 [啟用使用者垃圾郵件通知](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) ，則可以存取共用信箱中使用者垃圾郵件通知的任何使用者，都可以按一下通知中的 [ **檢查** ] 按鈕，以移至安全性 & 規範中心內的隔離。</span><span class="sxs-lookup"><span data-stu-id="46ac0-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="46ac0-114">請注意，此方法只允許使用者管理傳送至共用信箱的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="46ac0-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="46ac0-115">使用者無法在此內容中管理自己的隔離訊息。</span><span class="sxs-lookup"><span data-stu-id="46ac0-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="46ac0-116">使用者可以 [前往安全性 & 規範中心內的隔離](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="46ac0-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="46ac0-117">根據預設，只會顯示傳送給使用者的郵件。</span><span class="sxs-lookup"><span data-stu-id="46ac0-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="46ac0-118">不過，使用者可以變更「**郵件識別碼」按鈕** 的 **排序結果** () **收件者的電子郵件地址**、輸入共用信箱的電子郵件地址，然後 **按一下 [** 重新整理]，以查看已傳送至共用信箱的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="46ac0-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![根據收件者電子郵件地址排序隔離的郵件。](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="46ac0-120">不論方法為何，使用者都可以加入隔離郵件的 **收件** 者欄，以避免混淆。</span><span class="sxs-lookup"><span data-stu-id="46ac0-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="46ac0-121">顯示的最大欄數是7，因此使用者需要按一下 [ **修改欄**]，移除現有的欄 (例如 [ **原則類型**) ]，選取 [ **收件** 者]，然後按一下 [ **儲存** ] 或 [ **另存為預設值**]。</span><span class="sxs-lookup"><span data-stu-id="46ac0-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![移除 [原則類型] 欄，並將 [收件者] 欄新增至隔離區。](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="46ac0-123">必須記住的事項</span><span class="sxs-lookup"><span data-stu-id="46ac0-123">Things to keep in mind</span></span>

- <span data-ttu-id="46ac0-124">第一個作用於隔離郵件的使用者，會決定所有使用共用信箱之使用者的郵件 fate。</span><span class="sxs-lookup"><span data-stu-id="46ac0-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="46ac0-125">例如，如果有10位使用者存取共用信箱，而且使用者決定刪除隔離郵件，則會刪除所有10位使用者的郵件。</span><span class="sxs-lookup"><span data-stu-id="46ac0-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="46ac0-126">同樣地，如果使用者決定要放開郵件，該郵件就會發佈至共用信箱，並可供共用信箱的其他所有使用者存取。</span><span class="sxs-lookup"><span data-stu-id="46ac0-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="46ac0-127">目前已傳送至共用信箱的隔離郵件，[**詳細資料**] 浮出器中無法使用 [**封鎖寄件者**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="46ac0-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="46ac0-128">若要管理 [Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)中共用信箱的隔離郵件 PowerShell，使用者必須使用 [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) Cmdlet 與共享信箱電子郵件 _RecipientAddress_ 位址，以識別郵件。</span><span class="sxs-lookup"><span data-stu-id="46ac0-128">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="46ac0-129">例如：</span><span class="sxs-lookup"><span data-stu-id="46ac0-129">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="46ac0-130">然後，使用者可以從清單中選取隔離的郵件，以查看或採取動作。</span><span class="sxs-lookup"><span data-stu-id="46ac0-130">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="46ac0-131">在這個範例中，會顯示所有已傳送至共用信箱的隔離郵件，然後從隔離區發行清單中的第一封郵件， (清單中的第一個郵件是0，第二個是1，) 依此類推。</span><span class="sxs-lookup"><span data-stu-id="46ac0-131">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="46ac0-132">如需詳細的語法及參數資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="46ac0-132">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="46ac0-133">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="46ac0-133">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="46ac0-134">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="46ac0-134">Get-QuarantineMessageHeader</span></span>](/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="46ac0-135">預覽-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="46ac0-135">Preview-QuarantineMessage</span></span>](/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="46ac0-136">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="46ac0-136">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)