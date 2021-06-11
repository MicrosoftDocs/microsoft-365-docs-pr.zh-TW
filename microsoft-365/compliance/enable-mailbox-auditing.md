---
title: 管理信箱稽核
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: Microsoft 365 (也稱為預設信箱審計或信箱審核，預設會在) 上啟用信箱審計記錄。 這表示信箱擁有者、代理人和系統管理員所執行的某些動作會自動記錄在信箱審核記錄檔中，您可以在此搜尋在信箱上執行的活動。
ms.openlocfilehash: 859bd0dc633ece887fe11d57068fab4eb1395cdd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311169"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="f158d-104">管理信箱稽核</span><span class="sxs-lookup"><span data-stu-id="f158d-104">Manage mailbox auditing</span></span>

<span data-ttu-id="f158d-105">從2019年1月開始，Microsoft 預設會針對所有組織開啟信箱審核記錄。</span><span class="sxs-lookup"><span data-stu-id="f158d-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all organizations.</span></span> <span data-ttu-id="f158d-106">這表示會自動記錄信箱擁有者、代理人和系統管理員所執行的某些動作，當您在信箱審核記錄檔中搜尋對應的信箱審核記錄時，就會提供這些記錄。</span><span class="sxs-lookup"><span data-stu-id="f158d-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="f158d-107">在信箱審核預設為開啟狀態之前，您必須針對組織中的每個使用者信箱手動啟用它。</span><span class="sxs-lookup"><span data-stu-id="f158d-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="f158d-108">以下是信箱審核的一些優點：</span><span class="sxs-lookup"><span data-stu-id="f158d-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="f158d-109">當您建立新的信箱時，會自動啟用審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="f158d-110">您不需要為新使用者手動啟用它。</span><span class="sxs-lookup"><span data-stu-id="f158d-110">You don't need to manually enable it for new users.</span></span>

- <span data-ttu-id="f158d-111">您不需要管理所審核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="f158d-112">預設會針對每個登入類型 (系統管理員、委派及擁有者) ，對預先定義的一組信箱動作進行審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>

- <span data-ttu-id="f158d-113">當 Microsoft 發行新的信箱動作時，此動作可能會自動新增至預設會進行審核的信箱動作清單中 (服從具有適當授權) 的使用者。</span><span class="sxs-lookup"><span data-stu-id="f158d-113">When Microsoft releases a new mailbox action, the action might be automatically added to the list of mailbox actions that are audited by default (subject to the user having the appropriate license).</span></span> <span data-ttu-id="f158d-114">這表示您不需要在信箱上監視新增的動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-114">This means you don't need to monitor add new actions on mailboxes.</span></span>

- <span data-ttu-id="f158d-115">您的組織中的信箱審核原則都是一致的 (，因為您正在審核所有信箱) 的相同動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!NOTE]
>* <span data-ttu-id="f158d-116">根據預設，應記住的信箱審核版本的重要事項是：您不需要執行任何動作來管理信箱審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-116">The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="f158d-117">不過，若要深入瞭解，請自訂信箱審核的預設設定，或完全關閉，本主題可協助您。</span><span class="sxs-lookup"><span data-stu-id="f158d-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this topic can help you.</span></span>
>- <span data-ttu-id="f158d-118">根據預設，只有 E5 使用者的信箱審核事件可在安全性 & 合規性中心或「Office 365 管理」活動 API 中的審計記錄搜尋中取得。</span><span class="sxs-lookup"><span data-stu-id="f158d-118">By default, only mailbox audit events for E5 users are available in audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span> <span data-ttu-id="f158d-119">如需詳細資訊，請參閱本主題中的 [詳細資訊](#more-information) 一節。</span><span class="sxs-lookup"><span data-stu-id="f158d-119">For more information, see the [More information](#more-information) section in this topic.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="f158d-120">確認信箱稽核預設為開啟</span><span class="sxs-lookup"><span data-stu-id="f158d-120">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="f158d-121">若要確認您組織的預設信箱審核已開啟，請在[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f158d-121">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="f158d-122">值 **為 False** 表示組織啟用預設的信箱審計。</span><span class="sxs-lookup"><span data-stu-id="f158d-122">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="f158d-123">依預設，組織值會覆寫特定信箱上的信箱審核設定。</span><span class="sxs-lookup"><span data-stu-id="f158d-123">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="f158d-124">例如，如果已停用信箱的信箱審核功能 (*AuditEnabled* 屬性在信箱) 上為 **False** ，則預設信箱動作仍會針對信箱進行審核，因為預設會為組織啟用信箱審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-124">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="f158d-125">若要將特定信箱的信箱審核停用，您可以為信箱擁有人或已被委派存取信箱之其他使用者設定信箱審核旁路。</span><span class="sxs-lookup"><span data-stu-id="f158d-125">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="f158d-126">如需詳細資訊，請參閱本主題中的「 [略過信箱審核記錄](#bypass-mailbox-audit-logging) 」一節。</span><span class="sxs-lookup"><span data-stu-id="f158d-126">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="f158d-127">當組織的預設信箱審核為開啟狀態時，受影響的信箱的 *AuditEnabled* 屬性不會從 **False** 變更為 **True**。</span><span class="sxs-lookup"><span data-stu-id="f158d-127">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="f158d-128">換句話說，依預設，信箱審核會忽略信箱上的 *AuditEnabled* 屬性。</span><span class="sxs-lookup"><span data-stu-id="f158d-128">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="f158d-129">支援的信箱類型</span><span class="sxs-lookup"><span data-stu-id="f158d-129">Supported mailbox types</span></span>

<span data-ttu-id="f158d-130">下表顯示預設情況下，信箱審核目前支援的信箱類型：</span><span class="sxs-lookup"><span data-stu-id="f158d-130">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

|<span data-ttu-id="f158d-131">**信箱類型**</span><span class="sxs-lookup"><span data-stu-id="f158d-131">**Mailbox type**</span></span>|<span data-ttu-id="f158d-132">**支援**</span><span class="sxs-lookup"><span data-stu-id="f158d-132">**Supported**</span></span>|<span data-ttu-id="f158d-133">**不支援**</span><span class="sxs-lookup"><span data-stu-id="f158d-133">**Not supported**</span></span>|
|:---------|:---------:|:---------:|
|<span data-ttu-id="f158d-134">使用者信箱</span><span class="sxs-lookup"><span data-stu-id="f158d-134">User mailboxes</span></span>|![核取記號](../media/checkmark.png)||
|<span data-ttu-id="f158d-136">共用信箱</span><span class="sxs-lookup"><span data-stu-id="f158d-136">Shared mailboxes</span></span>|![核取記號](../media/checkmark.png)||
|<span data-ttu-id="f158d-138">Microsoft 365群組信箱</span><span class="sxs-lookup"><span data-stu-id="f158d-138">Microsoft 365 Group mailboxes</span></span>|![核取記號](../media/checkmark.png)||
|<span data-ttu-id="f158d-140">資源信箱</span><span class="sxs-lookup"><span data-stu-id="f158d-140">Resource mailboxes</span></span>||![核取記號](../media/checkmark.png)|
|<span data-ttu-id="f158d-142">公用資料夾信箱</span><span class="sxs-lookup"><span data-stu-id="f158d-142">Public folder mailboxes</span></span>||![核取記號](../media/checkmark.png)|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="f158d-144">登入類型和信箱動作</span><span class="sxs-lookup"><span data-stu-id="f158d-144">Logon types and mailbox actions</span></span>

<span data-ttu-id="f158d-145">登入類型會分類已在信箱上進行審核動作的使用者。</span><span class="sxs-lookup"><span data-stu-id="f158d-145">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="f158d-146">下列清單說明用於信箱審核記錄的登入類型：</span><span class="sxs-lookup"><span data-stu-id="f158d-146">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="f158d-147">**擁有** 者：信箱擁有人 (與信箱) 相關聯的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f158d-147">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>

- <span data-ttu-id="f158d-148">**委派**：</span><span class="sxs-lookup"><span data-stu-id="f158d-148">**Delegate**:</span></span>

  - <span data-ttu-id="f158d-149">已獲指派 SendAs、SendOnBehalf 或 FullAccess 許可權給另一個信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="f158d-149">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>

  - <span data-ttu-id="f158d-150">已獲指派 FullAccess 許可權給使用者信箱的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f158d-150">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>

- <span data-ttu-id="f158d-151">系統 **管理員**：</span><span class="sxs-lookup"><span data-stu-id="f158d-151">**Admin**:</span></span>

  - <span data-ttu-id="f158d-152">使用下列其中一個 Microsoft eDiscovery 工具來搜尋信箱：</span><span class="sxs-lookup"><span data-stu-id="f158d-152">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>

    - <span data-ttu-id="f158d-153">規範中心的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="f158d-153">Content Search in the Compliance center.</span></span>

    - <span data-ttu-id="f158d-154">規範中心的 eDiscovery 或 Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="f158d-154">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>

    - <span data-ttu-id="f158d-155">In-Place Exchange Online 中的 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="f158d-155">In-Place eDiscovery in Exchange Online.</span></span>

  - <span data-ttu-id="f158d-156">信箱是透過使用 Microsoft Exchange Server MAPI 編輯器來存取。</span><span class="sxs-lookup"><span data-stu-id="f158d-156">The mailbox is accessed by using the Microsoft Exchange Server MAPI Editor.</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="f158d-157">使用者信箱和共用信箱的信箱動作</span><span class="sxs-lookup"><span data-stu-id="f158d-157">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="f158d-158">下表說明信箱審核記錄中的使用者信箱和共用信箱可用的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-158">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="f158d-159">核取記號 (</span><span class="sxs-lookup"><span data-stu-id="f158d-159">A check mark (</span></span> ![核取記號](../media/checkmark.png)<span data-ttu-id="f158d-161">) 表示可以記錄登入類型的信箱動作 (並非所有動作都可用於所有的登入類型) 。</span><span class="sxs-lookup"><span data-stu-id="f158d-161">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>

- <span data-ttu-id="f158d-162"><sup>\*</sup>核取記號之後的星號 ( ) 表示登入類型的預設記錄為 [信箱] 動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-162">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>

- <span data-ttu-id="f158d-163">請記住，對信箱具有「完整存取」許可權的系統管理員會被視為代理人。</span><span class="sxs-lookup"><span data-stu-id="f158d-163">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

|<span data-ttu-id="f158d-164">**信箱動作**</span><span class="sxs-lookup"><span data-stu-id="f158d-164">**Mailbox action**</span></span>|<span data-ttu-id="f158d-165">**描述**</span><span class="sxs-lookup"><span data-stu-id="f158d-165">**Description**</span></span>|<span data-ttu-id="f158d-166">**Admin**</span><span class="sxs-lookup"><span data-stu-id="f158d-166">**Admin**</span></span>|<span data-ttu-id="f158d-167">**委託**</span><span class="sxs-lookup"><span data-stu-id="f158d-167">**Delegate**</span></span>|<span data-ttu-id="f158d-168">**Owner**</span><span class="sxs-lookup"><span data-stu-id="f158d-168">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="f158d-169">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="f158d-169">**AddFolderPermissions**</span></span>|<span data-ttu-id="f158d-170">**附注**：雖然此值接受為信箱動作，但它已包含在 **UpdateFolderPermissions** 動作中，而且不會個別進行審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-170">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="f158d-171">換句話說，請勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="f158d-171">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="f158d-172">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="f158d-172">**ApplyRecord**</span></span>|<span data-ttu-id="f158d-173">專案標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="f158d-173">An item is labeled as a record.</span></span>|<span data-ttu-id="f158d-174">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-174">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-175">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-175">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-176">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-176">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-177">**Copy**</span><span class="sxs-lookup"><span data-stu-id="f158d-177">**Copy**</span></span>|<span data-ttu-id="f158d-178">郵件已複製到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="f158d-178">A message was copied to another folder.</span></span>|![核取記號](../media/checkmark.png)|||
|<span data-ttu-id="f158d-180">**Create**</span><span class="sxs-lookup"><span data-stu-id="f158d-180">**Create**</span></span>|<span data-ttu-id="f158d-181">在 [信箱] 中的 [行事曆]、[連絡人]、[記事] 或 [任務] 資料夾中建立專案時 (例如，) 中建立新的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="f158d-181">An item was created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox (for example, a new meeting request is created).</span></span> <span data-ttu-id="f158d-182">建立、傳送或接收郵件的動作並不會受到稽核。</span><span class="sxs-lookup"><span data-stu-id="f158d-182">Creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="f158d-183">此外，建立信箱資料夾的動作也不會受到稽核。</span><span class="sxs-lookup"><span data-stu-id="f158d-183">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="f158d-184">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-184">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-185">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-185">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|![核取記號](../media/checkmark.png)|
|<span data-ttu-id="f158d-187">**Default**</span><span class="sxs-lookup"><span data-stu-id="f158d-187">**Default**</span></span>||![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|
|<span data-ttu-id="f158d-191">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="f158d-191">**FolderBind**</span></span>|<span data-ttu-id="f158d-192">已存取信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="f158d-192">A mailbox folder was accessed.</span></span> <span data-ttu-id="f158d-193">當系統管理員或代理人開啟信箱時，也會記錄此動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-193">This action is also logged when the admin or delegate opens the mailbox.</span></span> <br/><br/> <span data-ttu-id="f158d-194">**附注**：合併委派所執行之資料夾系結動作的審計記錄。</span><span class="sxs-lookup"><span data-stu-id="f158d-194">**Note**: Audit records for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="f158d-195">在24小時內，會為個別資料夾存取產生一個審計記錄。</span><span class="sxs-lookup"><span data-stu-id="f158d-195">One audit record is generated for individual folder access within a 24-hour period.</span></span>|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|<span data-ttu-id="f158d-198">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="f158d-198">**HardDelete**</span></span>|<span data-ttu-id="f158d-199">已從 [可復原的專案] 資料夾中清除郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-199">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="f158d-200">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-200">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-201">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-201">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-202">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-202">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-203">**MailItemsAccessed**</span><span class="sxs-lookup"><span data-stu-id="f158d-203">**MailItemsAccessed**</span></span>|<span data-ttu-id="f158d-204">郵件資料是由郵件通訊協定和用戶端存取。</span><span class="sxs-lookup"><span data-stu-id="f158d-204">Mail data is accessed by mail protocols and clients.</span></span> <span data-ttu-id="f158d-205">這個值只適用于 E5 或 E5 相容性附加元件訂閱使用者。</span><span class="sxs-lookup"><span data-stu-id="f158d-205">This value is only available for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="f158d-206">如需詳細資訊，請參閱 [設定高級審計 ](set-up-advanced-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="f158d-206">For more information, see [Set up Advanced Audit ](set-up-advanced-audit.md).</span></span>|<span data-ttu-id="f158d-207">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-207">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-208">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-208">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-209">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-209">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-210">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="f158d-210">**MailboxLogin**</span></span>|<span data-ttu-id="f158d-211">使用者已登入其信箱。</span><span class="sxs-lookup"><span data-stu-id="f158d-211">The user signed into their mailbox.</span></span> |||![核取記號](../media/checkmark.png)|
|<span data-ttu-id="f158d-213">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="f158d-213">**MessageBind**</span></span>|<span data-ttu-id="f158d-214">在 [預覽] 窗格中查看或由系統管理員開啟的訊息。 **請注意**：雖然此值接受為信箱動作，但不再記錄這些動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-214">A message was viewed in the preview pane or opened by an admin. **Note**: Although this value is accepted as a mailbox action, these actions are no longer logged.</span></span>|![核取記號](../media/checkmark.png)|||
|<span data-ttu-id="f158d-216">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="f158d-216">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="f158d-217">**附注**：雖然此值接受為信箱動作，但它已包含在 **UpdateFolderPermissions** 動作中，而且不會個別進行審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-217">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="f158d-218">換句話說，請勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="f158d-218">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="f158d-219">**Move**</span><span class="sxs-lookup"><span data-stu-id="f158d-219">**Move**</span></span>|<span data-ttu-id="f158d-220">郵件已移到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="f158d-220">A message was moved to another folder.</span></span>|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|
|<span data-ttu-id="f158d-224">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="f158d-224">**MoveToDeletedItems**</span></span>|<span data-ttu-id="f158d-225">郵件已遭刪除並移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f158d-225">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="f158d-226">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-226">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-227">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-227">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-228">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-228">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-229">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="f158d-229">**RecordDelete**</span></span>|<span data-ttu-id="f158d-230">已虛刪除標示為記錄的專案 (移至 [可復原的專案] 資料夾) 。</span><span class="sxs-lookup"><span data-stu-id="f158d-230">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="f158d-231">無法從 [可復原的專案] 資料夾中永久刪除標示為記錄的專案 () 。</span><span class="sxs-lookup"><span data-stu-id="f158d-231">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|
|<span data-ttu-id="f158d-235">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="f158d-235">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="f158d-236">**附注**：雖然此值接受為信箱動作，但它已包含在 **UpdateFolderPermissions** 動作中，而且不會個別進行審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-236">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="f158d-237">換句話說，請勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="f158d-237">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="f158d-238">**Send**</span><span class="sxs-lookup"><span data-stu-id="f158d-238">**Send**</span></span>|<span data-ttu-id="f158d-239">使用者傳送電子郵件訊息、回復電子郵件訊息或轉寄電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="f158d-239">The user sends an email message, replies to an email message, or forwards an email message.</span></span> <span data-ttu-id="f158d-240">這個值只適用于 E5 或 E5 相容性附加元件訂閱使用者。</span><span class="sxs-lookup"><span data-stu-id="f158d-240">This value is only available for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="f158d-241">如需詳細資訊，請參閱為 [使用者設定高級審核](set-up-advanced-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="f158d-241">For more information, see [Set up Advanced Audit for users](set-up-advanced-audit.md).</span></span>|<span data-ttu-id="f158d-242">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-242">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-243">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-243">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-244">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-244">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-245">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="f158d-245">**SendAs**</span></span>|<span data-ttu-id="f158d-246">已使用 [傳送為] 權限傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-246">A message was sent using the SendAs permission.</span></span> <span data-ttu-id="f158d-247">這表示另一位使用者已傳送郵件，就好像它來自信箱擁有者。</span><span class="sxs-lookup"><span data-stu-id="f158d-247">This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="f158d-248">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-248">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-249">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-249">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="f158d-250">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="f158d-250">**SendOnBehalf**</span></span>|<span data-ttu-id="f158d-251">已使用 [代理傳送者] 權限傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-251">A message was sent using the SendOnBehalf permission.</span></span> <span data-ttu-id="f158d-252">這表示另一位使用者代表信箱擁有者傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-252">This means another user sent the message on behalf of the mailbox owner.</span></span> <span data-ttu-id="f158d-253">此郵件會向收件者指出誰代理傳送郵件，以及實際上是誰傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-253">The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="f158d-254">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-254">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-255">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-255">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="f158d-256">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="f158d-256">**SoftDelete**</span></span>|<span data-ttu-id="f158d-257">郵件已永久刪除或從 [刪除的郵件] 資料夾中刪除。</span><span class="sxs-lookup"><span data-stu-id="f158d-257">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="f158d-258">虛刪除的專案會移至 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f158d-258">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="f158d-259">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-259">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-260">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-260">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-261">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-261">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-262">**更新**</span><span class="sxs-lookup"><span data-stu-id="f158d-262">**Update**</span></span>|<span data-ttu-id="f158d-263">郵件或其屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="f158d-263">A message or its properties was changed.</span></span>|<span data-ttu-id="f158d-264">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-264">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-265">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-265">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-266">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-266">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-267">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="f158d-267">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="f158d-268">已將行事曆委派指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="f158d-268">A calendar delegation was assigned to a mailbox.</span></span> <span data-ttu-id="f158d-269">行事曆代理可讓其他有相同組織權限的人來管理信箱擁有者的行事曆。</span><span class="sxs-lookup"><span data-stu-id="f158d-269">Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="f158d-270">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-270">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||<span data-ttu-id="f158d-271">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-271">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-272">**UpdateComplianceTag**</span><span class="sxs-lookup"><span data-stu-id="f158d-272">**UpdateComplianceTag**</span></span>|<span data-ttu-id="f158d-273">其他保留標籤會套用至訊息項目 (專案只能將一個保留標籤指派給它) 。</span><span class="sxs-lookup"><span data-stu-id="f158d-273">A different retention label is applied to a mail item (an item can only have one retention label assigned to it).</span></span>|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|
|<span data-ttu-id="f158d-277">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="f158d-277">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="f158d-278">資料夾權限已變更。</span><span class="sxs-lookup"><span data-stu-id="f158d-278">A folder permission was changed.</span></span> <span data-ttu-id="f158d-279">資料夾權限可控制組織中的哪些使用者可以存取信箱中的資料夾，以及這些資料夾中的郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-279">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="f158d-280">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-280">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-281">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-281">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-282">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-282">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-283">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="f158d-283">**UpdateInboxRules**</span></span>|<span data-ttu-id="f158d-284">新增、移除或變更收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="f158d-284">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="f158d-285">[收件匣] 規則是用來根據指定的條件處理使用者收件匣中的郵件，並在符合規則條件時採取動作，例如將郵件移至指定的資料夾或刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-285">Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="f158d-286">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-286">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-287">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-287">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-288">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-288">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|

> [!IMPORTANT]
> <span data-ttu-id="f158d-289">如果您自訂在組織中啟用信箱審核 *之前* 針對任何登入類型進行審核的信箱動作，則自訂設定會保留在信箱上，而且不會以本節所述的預設信箱動作覆寫。</span><span class="sxs-lookup"><span data-stu-id="f158d-289">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="f158d-290">若要將「審核信箱」動作還原為預設值 (可在任何時間) 進行，請參閱本主題稍後的 [還原預設信箱動作](#restore-the-default-mailbox-actions) 一節。</span><span class="sxs-lookup"><span data-stu-id="f158d-290">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this topic.</span></span>

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a><span data-ttu-id="f158d-291">Microsoft 365 群組信箱的信箱動作</span><span class="sxs-lookup"><span data-stu-id="f158d-291">Mailbox actions for Microsoft 365 Group mailboxes</span></span>

<span data-ttu-id="f158d-292">信箱審核預設會將信箱審核記錄的內容提供給 Microsoft 365 群組信箱，但您無法自訂要登入的專案 (無法新增或移除針對任何登入類型) 所記錄的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-292">Mailbox auditing on by default brings mailbox audit logging to Microsoft 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="f158d-293">下表說明預設在每個登入類型的 Microsoft 365 群組信箱上記錄的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-293">The following table describes the mailbox actions that are logged by default on Microsoft 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="f158d-294">請記住，對 Microsoft 365 群組信箱具有「完整存取」許可權的系統管理員會被視為代理人。</span><span class="sxs-lookup"><span data-stu-id="f158d-294">Remember, an admin with Full Access permission to a Microsoft 365 Group mailbox is considered a delegate.</span></span>

|<span data-ttu-id="f158d-295">**信箱動作**</span><span class="sxs-lookup"><span data-stu-id="f158d-295">**Mailbox action**</span></span>|<span data-ttu-id="f158d-296">**描述**</span><span class="sxs-lookup"><span data-stu-id="f158d-296">**Description**</span></span>|<span data-ttu-id="f158d-297">**Admin**</span><span class="sxs-lookup"><span data-stu-id="f158d-297">**Admin**</span></span>|<span data-ttu-id="f158d-298">**委託**</span><span class="sxs-lookup"><span data-stu-id="f158d-298">**Delegate**</span></span>|<span data-ttu-id="f158d-299">**Owner**</span><span class="sxs-lookup"><span data-stu-id="f158d-299">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="f158d-300">**Create**</span><span class="sxs-lookup"><span data-stu-id="f158d-300">**Create**</span></span>|<span data-ttu-id="f158d-301">建立行事曆專案。</span><span class="sxs-lookup"><span data-stu-id="f158d-301">Creation of a calendar Item.</span></span> <span data-ttu-id="f158d-302">建立、傳送或接收郵件的動作並不會受到稽核。</span><span class="sxs-lookup"><span data-stu-id="f158d-302">Creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="f158d-303">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-303">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-304">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-304">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="f158d-305">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="f158d-305">**HardDelete**</span></span>|<span data-ttu-id="f158d-306">已從 [可復原的專案] 資料夾中清除郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-306">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="f158d-307">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-307">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-308">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-308">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-309">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-309">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-310">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="f158d-310">**MoveToDeletedItems**</span></span>|<span data-ttu-id="f158d-311">郵件已遭刪除並移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f158d-311">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="f158d-312">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-312">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-313">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-313">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-314">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-314">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-315">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="f158d-315">**SendAs**</span></span>|<span data-ttu-id="f158d-316">已使用 [傳送為] 權限傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-316">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="f158d-317">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-317">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-318">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-318">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="f158d-319">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="f158d-319">**SendOnBehalf**</span></span>|<span data-ttu-id="f158d-320">已使用 [代理傳送者] 權限傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="f158d-320">A message was sent using the SendOnBehalf permission.</span></span> |<span data-ttu-id="f158d-321">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-321">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-322">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-322">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="f158d-323">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="f158d-323">**SoftDelete**</span></span>|<span data-ttu-id="f158d-324">郵件已永久刪除或從 [刪除的郵件] 資料夾中刪除。</span><span class="sxs-lookup"><span data-stu-id="f158d-324">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="f158d-325">虛刪除的專案會移至 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f158d-325">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="f158d-326">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-326">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-327">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-327">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-328">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-328">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="f158d-329">**更新**</span><span class="sxs-lookup"><span data-stu-id="f158d-329">**Update**</span></span>|<span data-ttu-id="f158d-330">郵件或其屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="f158d-330">A message or its properties was changed.</span></span>|<span data-ttu-id="f158d-331">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-331">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-332">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-332">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="f158d-333">![核取記號](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f158d-333">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="f158d-334">確認每個登入類型的預設信箱動作都會進行記錄</span><span class="sxs-lookup"><span data-stu-id="f158d-334">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="f158d-335">信箱審核的預設值會將新的 *DefaultAuditSet* 屬性加入至所有信箱。</span><span class="sxs-lookup"><span data-stu-id="f158d-335">Mailbox auditing on by defaults adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="f158d-336">此屬性的值會指出是否要在信箱上審核預設的信箱動作 (由 Microsoft) 管理。</span><span class="sxs-lookup"><span data-stu-id="f158d-336">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="f158d-337">若要在使用者信箱或共用信箱上顯示值，請以 \<MailboxIdentity\> 名稱、別名、電子郵件地址或使用者主要名稱取代， (信箱的使用者名稱) ，並在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f158d-337">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="f158d-338">若要在 Microsoft 365 群組信箱上顯示值，請以 \<MailboxIdentity\> 共用信箱的名稱、別名或電子郵件地址加以取代，並在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f158d-338">To display the value on Microsoft 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="f158d-339">此值 `Admin, Delegate, Owner` 表示：</span><span class="sxs-lookup"><span data-stu-id="f158d-339">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="f158d-340">所有三種登入類型的預設信箱動作都會進行審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-340">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="f158d-341">這是您可以在 Microsoft 365 群組信箱上看到的唯一值。</span><span class="sxs-lookup"><span data-stu-id="f158d-341">This is the only value you'll see on Microsoft 365 Group mailboxes.</span></span>

- <span data-ttu-id="f158d-342">*管理員尚未* 變更使用者信箱或共用信箱上任何登入類型的已審核信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-342">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="f158d-343">附注：這是預設會在您的組織中開啟信箱審核之後的預設狀態。</span><span class="sxs-lookup"><span data-stu-id="f158d-343">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="f158d-344">如果系統管理員曾經使用 **Set-Mailbox** Cmdlet) 上的 *AuditAdmin*、 *AuditDelegate* 或 *AuditOwner* 參數變更為登入 (類型所審核的信箱動作，屬性值將會不同。</span><span class="sxs-lookup"><span data-stu-id="f158d-344">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="f158d-345">例如， `Owner` 使用者信箱或共用信箱上之 *DefaultAuditSet* 屬性的值會指出：</span><span class="sxs-lookup"><span data-stu-id="f158d-345">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="f158d-346">會審核信箱擁有者的預設信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-346">The default mailbox actions for the mailbox owner are being audited.</span></span>

- <span data-ttu-id="f158d-347">針對和登入類型所審核的信箱動作 `Delegate` ，已 `Admin` 從預設動作變更。</span><span class="sxs-lookup"><span data-stu-id="f158d-347">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="f158d-348">*DefaultAuditSet* 屬性的空白值表示所有三種登入類型的信箱動作都已在使用者信箱或共用信箱上變更。</span><span class="sxs-lookup"><span data-stu-id="f158d-348">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="f158d-349">如需詳細資訊，請參閱本主題中的 [變更或還原依預設所記錄的信箱動作](#change-or-restore-mailbox-actions-logged-by-default) 一節。</span><span class="sxs-lookup"><span data-stu-id="f158d-349">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this topic</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="f158d-350">顯示正在登入信箱的信箱動作</span><span class="sxs-lookup"><span data-stu-id="f158d-350">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="f158d-351">若要查看目前登入使用者信箱或共用信箱的信箱動作，請以 \<MailboxIdentity\> 名稱、別名、電子郵件地址或使用者主要名稱取代，以 (信箱的使用者名稱) ，然後在 Exchange Online PowerShell 中執行下列其中一個或多個命令。</span><span class="sxs-lookup"><span data-stu-id="f158d-351">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="f158d-352">雖然您可以將 `-GroupMailbox` 參數新增至 Microsoft 365 群組信箱的下列 **Get-Mailbox** 命令，但不會相信傳回的值。</span><span class="sxs-lookup"><span data-stu-id="f158d-352">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Microsoft 365 Group mailboxes, don't believe the values that are returned.</span></span> <span data-ttu-id="f158d-353">本主題稍早[Microsoft 365 群組信箱的信箱動作](#mailbox-actions-for-microsoft-365-group-mailboxes)一節說明 Microsoft 365 群組信箱所審核的預設和靜態信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-353">The default and static mailbox actions that are audited for Microsoft 365 Group mailboxes are described in the [Mailbox actions for Microsoft 365 Group mailboxes](#mailbox-actions-for-microsoft-365-group-mailboxes) section earlier in this topic.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="f158d-354">擁有者動作</span><span class="sxs-lookup"><span data-stu-id="f158d-354">Owner actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="f158d-355">委派動作</span><span class="sxs-lookup"><span data-stu-id="f158d-355">Delegate actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="f158d-356">系統管理動作</span><span class="sxs-lookup"><span data-stu-id="f158d-356">Admin actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="f158d-357">變更或還原預設所記錄的信箱動作</span><span class="sxs-lookup"><span data-stu-id="f158d-357">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="f158d-358">如先前所述，預設會啟用信箱審核的其中一個重要優點是：您不需要管理所審核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-358">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="f158d-359">Microsoft 會為您做這種情況，而且在發佈新的信箱動作時，系統會自動將其新增為待審計。</span><span class="sxs-lookup"><span data-stu-id="f158d-359">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="f158d-360">不過，您的組織可能需要針對使用者信箱和共用信箱，審核一組不同的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-360">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="f158d-361">本節中的程式說明如何變更針對每一種登入類型所審核的信箱動作，以及如何回復至 Microsoft 受管理的預設動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-361">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f158d-362">如果您使用下列程式自訂使用者信箱或共用信箱上所記錄的信箱動作，Microsoft 所發行的任何新預設信箱動作都不會自動在這些信箱上進行審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-362">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="f158d-363">您必須手動將任何新的信箱動作新增至自訂動作清單。</span><span class="sxs-lookup"><span data-stu-id="f158d-363">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="f158d-364">變更要審核的信箱動作</span><span class="sxs-lookup"><span data-stu-id="f158d-364">Change the mailbox actions to audit</span></span>

<span data-ttu-id="f158d-365">您可以使用 **Set-Mailbox** Cmdlet 上的 *AuditAdmin*、 *AuditDelegate* 或 *AuditOwner* 參數，來變更針對使用者信箱和共用信箱所審核的信箱動作 (Microsoft 365 群組信箱的已審核動作無法自訂) 。</span><span class="sxs-lookup"><span data-stu-id="f158d-365">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Microsoft 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="f158d-366">您可以使用兩種不同的方法來指定信箱動作：</span><span class="sxs-lookup"><span data-stu-id="f158d-366">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="f158d-367">使用下列語法 *取代* (覆寫) 現有的信箱動作： `action1,action2,...actionN` 。</span><span class="sxs-lookup"><span data-stu-id="f158d-367">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>

- <span data-ttu-id="f158d-368">使用下列語法，*新增或移除* 不會影響其他現有值的信箱動作： `@{Add="action1","action2",..."actionN"}` 或 `@{Remove="action1","action2",..."actionN"}` 。</span><span class="sxs-lookup"><span data-stu-id="f158d-368">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="f158d-369">在這個範例中，會使用 SoftDelete 和 HardDelete 覆寫預設動作，以變更名為 "Gabriela Laureano" 之信箱的系統管理員信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-369">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="f158d-370">本範例會將 MailboxLogin 的擁有者動作新增至信箱 laura@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="f158d-370">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="f158d-371">本範例會移除小組討論信箱的 MoveToDeletedItems 委派動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-371">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="f158d-372">不論使用哪一種方法，自訂使用者信箱或共用信箱上的已審核信箱動作都有下列結果：</span><span class="sxs-lookup"><span data-stu-id="f158d-372">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="f158d-373">針對您自訂的登入類型，會不再由 Microsoft 管理已審核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-373">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>

- <span data-ttu-id="f158d-374">您自訂的登入類型不再如 [先前所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)，顯示在信箱的 *DefaultAuditSet* 屬性值中。</span><span class="sxs-lookup"><span data-stu-id="f158d-374">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="f158d-375">還原預設的信箱動作</span><span class="sxs-lookup"><span data-stu-id="f158d-375">Restore the default mailbox actions</span></span>

<span data-ttu-id="f158d-376">如果您自訂在使用者信箱或共用信箱上進行審核的信箱動作，您可以使用下列語法還原一或所有登入類型的預設信箱動作：</span><span class="sxs-lookup"><span data-stu-id="f158d-376">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="f158d-377">您可以指定多個以逗號分隔的 *DefaultAuditSet* 值。</span><span class="sxs-lookup"><span data-stu-id="f158d-377">You can specify multiple *DefaultAuditSet* values separated by commas</span></span>

<span data-ttu-id="f158d-378">**附注**：下列程式不適用於 Microsoft 365 群組信箱， (其受限於預設動作) [這裡](#mailbox-actions-for-microsoft-365-group-mailboxes)所述。</span><span class="sxs-lookup"><span data-stu-id="f158d-378">**Note**: The following procedures don't apply to Microsoft 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-microsoft-365-group-mailboxes)).</span></span>

<span data-ttu-id="f158d-379">本範例會在信箱 mark@contoso.onmicrosoft.com 上還原所有登入類型的預設已審核信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-379">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="f158d-380">此範例會還原信箱 chris@contoso.onmicrosoft.com 上系統管理員登入類型的預設已審核信箱動作，但會將委派及擁有者登入類型的自訂已審核信箱動作保留。</span><span class="sxs-lookup"><span data-stu-id="f158d-380">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="f158d-381">還原登入類型的預設已審核信箱動作具有下列結果：</span><span class="sxs-lookup"><span data-stu-id="f158d-381">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="f158d-382">目前的信箱動作清單會取代為登入類型的預設信箱動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-382">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>

- <span data-ttu-id="f158d-383">Microsoft 所發行的任何新信箱動作都會自動新增至登入類型的已審核動作清單。</span><span class="sxs-lookup"><span data-stu-id="f158d-383">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>

- <span data-ttu-id="f158d-384">信箱的 *DefaultAuditSet* 屬性值會更新，以包含還原的登入類型。</span><span class="sxs-lookup"><span data-stu-id="f158d-384">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="f158d-385">針對您的組織，關閉預設的信箱審計</span><span class="sxs-lookup"><span data-stu-id="f158d-385">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="f158d-386">您可以在 Exchange Online 中執行下列命令，關閉整個組織的預設信箱審核 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f158d-386">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="f158d-387">預設關閉信箱審核的結果如下：</span><span class="sxs-lookup"><span data-stu-id="f158d-387">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="f158d-388">您的組織已停用信箱審核。</span><span class="sxs-lookup"><span data-stu-id="f158d-388">Mailbox auditing is disabled for your organization.</span></span>

- <span data-ttu-id="f158d-389">從您已停用的信箱審核預設情況下，即使信箱上已啟用審核，也不會審核任何信箱動作 (信箱上 *AuditEnabled* 屬性為 **True**) 。</span><span class="sxs-lookup"><span data-stu-id="f158d-389">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>

- <span data-ttu-id="f158d-390">信箱審核未啟用新信箱，並將新的或現有的信箱上的 *AuditEnabled* 屬性設定為 True，則會忽略此 **值** 。</span><span class="sxs-lookup"><span data-stu-id="f158d-390">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>

- <span data-ttu-id="f158d-391">會忽略任何使用 **Set-MailboxAuditBypassAssociation** 指令程式) 設定 (的信箱審核略過關聯設定。</span><span class="sxs-lookup"><span data-stu-id="f158d-391">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>

- <span data-ttu-id="f158d-392">現有的信箱審計記錄會保留，直到記錄的「審核記錄保留時間上限」到期為止。</span><span class="sxs-lookup"><span data-stu-id="f158d-392">Existing mailbox audit records are retained until the audit log age limit for the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="f158d-393">依預設開啟信箱審計</span><span class="sxs-lookup"><span data-stu-id="f158d-393">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="f158d-394">若要為您的組織開啟信箱審核，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f158d-394">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="f158d-395">略過信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="f158d-395">Bypass mailbox audit logging</span></span>

<span data-ttu-id="f158d-396">目前，當貴組織預設開啟信箱稽核時，您無法停用特定信箱的信箱稽核。</span><span class="sxs-lookup"><span data-stu-id="f158d-396">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="f158d-397">例如，會忽略將 *AuditEnabled* 信箱屬性設定為 **False** 。</span><span class="sxs-lookup"><span data-stu-id="f158d-397">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="f158d-398">不過，您仍然可以在 Exchange Online PowerShell 中使用 **Set-MailboxAuditBypassAssociation** Cmdlet，以防止指定的使用者登入 *任何和所有* 信箱動作，不論動作發生的位置為何。</span><span class="sxs-lookup"><span data-stu-id="f158d-398">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="f158d-399">例如：</span><span class="sxs-lookup"><span data-stu-id="f158d-399">For example:</span></span>

- <span data-ttu-id="f158d-400">未記錄略過使用者執行的信箱擁有者動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-400">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>

- <span data-ttu-id="f158d-401">委派由其他使用者信箱上的封鎖使用者執行的動作 (包括共用信箱) 不會登入。</span><span class="sxs-lookup"><span data-stu-id="f158d-401">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>

- <span data-ttu-id="f158d-402">不會記錄略過使用者執行的系統管理員動作。</span><span class="sxs-lookup"><span data-stu-id="f158d-402">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="f158d-403">若要略過特定使用者的信箱審核記錄，請將 \<MailboxIdentity\> 名稱、電子郵件地址、別名或使用者主要名稱取代 (使用者的使用者名稱) ，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f158d-403">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="f158d-404">若要驗證已針對指定的使用者略過稽核，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f158d-404">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="f158d-405">值 **為 True** 表示使用者略過信箱審核記錄。</span><span class="sxs-lookup"><span data-stu-id="f158d-405">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="f158d-406">其他資訊</span><span class="sxs-lookup"><span data-stu-id="f158d-406">More information</span></span>

- <span data-ttu-id="f158d-407">雖然預設會為所有組織啟用信箱審核記錄，但只有具有 E5 授權的使用者才會在 [安全性 & 合規性中心](search-the-audit-log-in-security-and-compliance.md)或 **預設** 會透過 [Office 365 管理活動 API](/office/office-365-management-api/office-365-management-activity-api-reference)中，傳回審核記錄搜尋中的信箱審核記錄事件。</span><span class="sxs-lookup"><span data-stu-id="f158d-407">Although mailbox audit logging on by default is enabled for all organizations, only users with E5 licenses will return mailbox audit log events in [audit log searches in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md) or via the [Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-reference) **by default**.</span></span>

  <span data-ttu-id="f158d-408">若要取得沒有 E5 授權之使用者的信箱審計記錄專案，您可以：</span><span class="sxs-lookup"><span data-stu-id="f158d-408">To retrieve mailbox audit log entries for users without E5 licenses, you can:</span></span>

  - <span data-ttu-id="f158d-409">手動啟用個別信箱上的信箱審計 (執行命令，請 `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`) 。</span><span class="sxs-lookup"><span data-stu-id="f158d-409">Manually enable mailbox auditing on individual mailboxes (run the command, `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`).</span></span> <span data-ttu-id="f158d-410">完成之後，您可以在安全性 & 規範中心或透過 Office 365 管理活動 API 中使用審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="f158d-410">After you do this, you can use audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="f158d-411">如果信箱審核似乎已在信箱上啟用，但是您的搜尋未傳回任何結果，請將 _AuditEnabled_ 參數的值變更為 `$false` 後再移回來 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="f158d-411">If mailbox auditing already appears to be enabled on the mailbox, but your searches return no results, change the value of the _AuditEnabled_ parameter to `$false` and then back to `$true`.</span></span>
  
  - <span data-ttu-id="f158d-412">在 Exchange Online 中使用下列 Cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f158d-412">Use the following cmdlets in Exchange Online PowerShell:</span></span>

    - <span data-ttu-id="f158d-413">[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) 搜尋特定使用者的信箱審核記錄。</span><span class="sxs-lookup"><span data-stu-id="f158d-413">[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) to search the mailbox audit log for specific users.</span></span>

    - <span data-ttu-id="f158d-414">[New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) 搜尋特定使用者的信箱審核記錄，並將結果透過電子郵件傳送給指定的收件者。</span><span class="sxs-lookup"><span data-stu-id="f158d-414">[New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) to search the mailbox audit log for specific users and to have the results sent via email to specified recipients.</span></span>

  - <span data-ttu-id="f158d-415">使用 Exchange 系統管理中心 (EAC) Exchange Online 執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f158d-415">Use the Exchange admin center (EAC) in Exchange Online to do the following actions:</span></span>

    - [<span data-ttu-id="f158d-416">匯出信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="f158d-416">Export mailbox audit logs</span></span>](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [<span data-ttu-id="f158d-417">執行非擁有者信箱存取報告</span><span class="sxs-lookup"><span data-stu-id="f158d-417">Run a non-owner mailbox access report</span></span>](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- <span data-ttu-id="f158d-418">依預設，信箱審核記錄記錄會在刪除之前保留90天。</span><span class="sxs-lookup"><span data-stu-id="f158d-418">By default, mailbox audit log records are retained for 90 days before they're deleted.</span></span> <span data-ttu-id="f158d-419">您可以使用 Exchange Online PowerShell 中 **Set-Mailbox** Cmdlet 上的 *AuditLogAgeLimit* 參數，來變更審核記錄記錄的保留天數限制。</span><span class="sxs-lookup"><span data-stu-id="f158d-419">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="f158d-420">不過，增加此值不會讓您在審核記錄中搜尋超過90天的事件。</span><span class="sxs-lookup"><span data-stu-id="f158d-420">However, increasing this value doesn't allow you to search for events that are older than 90 days in the audit log.</span></span>

  <span data-ttu-id="f158d-421">如果您增加保留天數，您必須在 Exchange Online PowerShell 中使用[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog)指令程式，以便在使用者的信箱審核記錄中搜尋超過90天的記錄。</span><span class="sxs-lookup"><span data-stu-id="f158d-421">If you increase the age limit, you need to use the [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="f158d-422">如果您已在信箱審核之前將信箱的 *AuditLogAgeLimit* 屬性變更為已開啟組織的預設值，則信箱的現有審核記錄保留時間限制不會變更。</span><span class="sxs-lookup"><span data-stu-id="f158d-422">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="f158d-423">換句話說，依預設，信箱審計不會影響信箱審計記錄的目前保留限制。</span><span class="sxs-lookup"><span data-stu-id="f158d-423">In other words, mailbox auditing on by default doesn't affect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="f158d-424">若要變更 Microsoft 365 群組信箱上的 *AuditLogAgeLimit* 值，您必須 `-GroupMailbox` 在 **Set-Mailbox** 命令中包含該參數。</span><span class="sxs-lookup"><span data-stu-id="f158d-424">To change the *AuditLogAgeLimit* value on a Microsoft 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="f158d-425">信箱審計記錄檔會儲存在每個使用者信箱的 [可復原的專案] 資料夾中 (名為「 *審計* 」) 子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f158d-425">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="f158d-426">請記住下列有關信箱審計記錄和 [可復原的專案] 資料夾的事項：</span><span class="sxs-lookup"><span data-stu-id="f158d-426">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="f158d-427">信箱審計記錄會根據 [可復原的專案] 資料夾的儲存配額進行計數（預設值為 30 GB (警告配額為 20 GB) 。</span><span class="sxs-lookup"><span data-stu-id="f158d-427">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30 GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="f158d-428">在下列情況) ，儲存配額會以 90 GB 的警告配額自動增加為 100 GB (：</span><span class="sxs-lookup"><span data-stu-id="f158d-428">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>

    - <span data-ttu-id="f158d-429">保留是放在信箱上。</span><span class="sxs-lookup"><span data-stu-id="f158d-429">A hold is placed on a mailbox.</span></span>

    - <span data-ttu-id="f158d-430">信箱會指派給規範中心內的保留原則。</span><span class="sxs-lookup"><span data-stu-id="f158d-430">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="f158d-431">信箱審計記錄也會計入 [[可復原的專案] 資料夾的資料夾限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。</span><span class="sxs-lookup"><span data-stu-id="f158d-431">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="f158d-432">) 可以儲存在「審計] 子資料夾中 (的審計記錄中，最多可以儲存3000000個專案。</span><span class="sxs-lookup"><span data-stu-id="f158d-432">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f158d-433">根據預設，信箱審核可能會影響儲存配額或 [可復原的專案] 資料夾的資料夾限制。</span><span class="sxs-lookup"><span data-stu-id="f158d-433">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="f158d-434">您可以在 Exchange Online PowerShell 中執行下列命令，在 [可復原的專案] 資料夾的 [審計] 子資料夾中顯示專案的大小和數目：</span><span class="sxs-lookup"><span data-stu-id="f158d-434">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="f158d-435">您無法直接存取 [可復原的專案] 資料夾中的審計記錄記錄;相反地，您可以使用 **Search-MailboxAuditLog** Cmdlet 或搜尋審核記錄檔，以尋找及查看信箱審計記錄。</span><span class="sxs-lookup"><span data-stu-id="f158d-435">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="f158d-436">如果信箱處於保留狀態或指派給規範中心內的保留原則，則在信箱的 *AuditLogAgeLimit* 屬性定義的期間內，仍然會保留審計記錄檔 () 預設為90天。</span><span class="sxs-lookup"><span data-stu-id="f158d-436">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="f158d-437">若要保留長期保留信箱的審計記錄檔，您需要增加信箱的 *AuditLogAgeLimit* 值。</span><span class="sxs-lookup"><span data-stu-id="f158d-437">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>

- <span data-ttu-id="f158d-438">在地理位置環境中，不支援跨地理位置信箱稽核。</span><span class="sxs-lookup"><span data-stu-id="f158d-438">In a multi-geo environment, cross-geo mailbox auditing is not supported.</span></span> <span data-ttu-id="f158d-439">例如，如果指派給使用者的權限可以存取不同地理位置的共用信箱，則該使用者執行的信箱動作不會記錄在共用信箱的信箱稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="f158d-439">For example, if a user is assigned permissions to access a shared mailbox in a different geo location, mailbox actions performed by that user are not logged in the mailbox audit log of the shared mailbox.</span></span>