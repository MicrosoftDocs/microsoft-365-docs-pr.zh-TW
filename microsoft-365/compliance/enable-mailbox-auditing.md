---
title: 管理信箱稽核
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
description: 信箱稽核記錄 （也稱為預設信箱稽核或信箱的稽核預設情況下） 的 Office 365 中預設已開啟。 這表示信箱擁有者、 代理人和系統管理員所執行的特定動作都會自動記錄在信箱稽核記錄，您可以搜尋的信箱上執行的活動。
ms.openlocfilehash: 059039205e82ea63b1dc14a8be5e768e9cdba069
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515564"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="27d08-104">管理信箱稽核</span><span class="sxs-lookup"><span data-stu-id="27d08-104">Manage mailbox auditing</span></span>

<span data-ttu-id="27d08-105">2019 年 1 月開始，Microsoft 開啟信箱稽核記錄功能預設為所有 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="27d08-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all Office 365 organizations.</span></span> <span data-ttu-id="27d08-106">這表示自動記錄信箱擁有者、 代理人和系統管理員所執行某些動作，以及對應的信箱稽核記錄時，會提供您的信箱稽核記錄中搜尋它們。</span><span class="sxs-lookup"><span data-stu-id="27d08-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="27d08-107">信箱稽核依預設已開啟之前，您必須以手動啟用每個使用者信箱在您的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="27d08-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="27d08-108">以下是一些信箱的稽核預設的優點：</span><span class="sxs-lookup"><span data-stu-id="27d08-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="27d08-109">自動啟用稽核，當您建立新的信箱。</span><span class="sxs-lookup"><span data-stu-id="27d08-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="27d08-110">您不需要以手動啟用為新的使用者。</span><span class="sxs-lookup"><span data-stu-id="27d08-110">You don't need to manually enable it for new users.</span></span>

- <span data-ttu-id="27d08-111">您不需要管理稽核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="27d08-112">一組預先定義的信箱動作會針對每個登入類型 （系統管理員、 代理人和擁有者） 的預設稽核。</span><span class="sxs-lookup"><span data-stu-id="27d08-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>

- <span data-ttu-id="27d08-113">當 Microsoft 發行新的信箱動作 （尤其是動作有助於保護您的組織，並協助鑑定調查） 時，巨集指令會自動新增至預設稽核的信箱動作的清單。</span><span class="sxs-lookup"><span data-stu-id="27d08-113">When Microsoft releases a new mailbox action (particularly actions that help protect your organization and help with forensic investigations), the action is automatically added to the list of mailbox actions that are audited by default.</span></span> <span data-ttu-id="27d08-114">這表示您不需要監視信箱上新增新動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-114">This means you don't need to monitor add new actions on mailboxes.</span></span>

- <span data-ttu-id="27d08-115">（因為您正在稽核所有信箱的相同的動作），您可以有整個組織的一致的信箱稽核原則。</span><span class="sxs-lookup"><span data-stu-id="27d08-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!NOTE]
><span data-ttu-id="27d08-116">• 關於信箱的稽核預設版本，請記得重要事情是： 您不需要執行任何動作來管理信箱的稽核。</span><span class="sxs-lookup"><span data-stu-id="27d08-116">• The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="27d08-117">不過，若要了解更多、 自訂預設設定，從信箱稽核或完全將其關閉，本主題可協助您。</span><span class="sxs-lookup"><span data-stu-id="27d08-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this topic can help you.</span></span> <br><br><span data-ttu-id="27d08-118">• 僅信箱稽核事件 E5 使用者都可以在安全 & 與規範中心中或透過 Office 365 管理活動 API 的稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="27d08-118">• Only mailbox audit events for E5 users are available in audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span> <span data-ttu-id="27d08-119">如需詳細資訊，請參閱本主題[的詳細資訊](#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="27d08-119">For more information, see the [More information](#more-information) section in this topic.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="27d08-120">確認信箱的稽核預設已開啟</span><span class="sxs-lookup"><span data-stu-id="27d08-120">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="27d08-121">若要確認該信箱上的預設開啟稽核功能為您的組織， [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="27d08-121">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span></span>

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="27d08-122">**為 False**的值會指出的組織已啟用信箱的稽核預設。</span><span class="sxs-lookup"><span data-stu-id="27d08-122">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="27d08-123">這在預設組織值會覆寫的稽核設定特定信箱上的信箱。</span><span class="sxs-lookup"><span data-stu-id="27d08-123">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="27d08-124">例如，如果停用信箱 （ *AuditEnabled*屬性是**False**信箱） 的信箱稽核，預設信箱動作會仍稽核的信箱，因為信箱的稽核預設的組織已啟用。</span><span class="sxs-lookup"><span data-stu-id="27d08-124">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="27d08-125">若要保留特定信箱的停用信箱稽核，您可以設定信箱稽核略過信箱擁有者，以及已被其他使用者委派信箱存取權。</span><span class="sxs-lookup"><span data-stu-id="27d08-125">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="27d08-126">如需詳細資訊，請參閱本主題中的 [[略過信箱稽核記錄](#bypass-mailbox-audit-logging)] 區段。</span><span class="sxs-lookup"><span data-stu-id="27d08-126">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="27d08-127">當信箱上預設會開啟稽核組織時， *AuditEnabled*屬性信箱的受影響的信箱不會從**False**變更為 **，則為 True**。</span><span class="sxs-lookup"><span data-stu-id="27d08-127">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="27d08-128">換句話說，信箱的稽核依預設會忽略*AuditEnabled*屬性信箱上的信箱。</span><span class="sxs-lookup"><span data-stu-id="27d08-128">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="27d08-129">支援的信箱類型</span><span class="sxs-lookup"><span data-stu-id="27d08-129">Supported mailbox types</span></span>

<span data-ttu-id="27d08-130">下表顯示預設的稽核的信箱目前支援的信箱類型：</span><span class="sxs-lookup"><span data-stu-id="27d08-130">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

|<span data-ttu-id="27d08-131">**信箱類型**</span><span class="sxs-lookup"><span data-stu-id="27d08-131">**Mailbox type**</span></span>|<span data-ttu-id="27d08-132">**支援**</span><span class="sxs-lookup"><span data-stu-id="27d08-132">**Supported**</span></span>|<span data-ttu-id="27d08-133">**不支援**</span><span class="sxs-lookup"><span data-stu-id="27d08-133">**Not supported**</span></span>|
|:---------|:---------:|:---------:|
|<span data-ttu-id="27d08-134">使用者信箱</span><span class="sxs-lookup"><span data-stu-id="27d08-134">User mailboxes</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="27d08-136">共用信箱</span><span class="sxs-lookup"><span data-stu-id="27d08-136">Shared mailboxes</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="27d08-138">Office 365 群組信箱</span><span class="sxs-lookup"><span data-stu-id="27d08-138">Office 365 Group mailboxes</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="27d08-140">資源信箱</span><span class="sxs-lookup"><span data-stu-id="27d08-140">Resource mailboxes</span></span>||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="27d08-142">公用資料夾信箱</span><span class="sxs-lookup"><span data-stu-id="27d08-142">Public folder mailboxes</span></span>||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="27d08-144">登入類型，以及信箱動作</span><span class="sxs-lookup"><span data-stu-id="27d08-144">Logon types and mailbox actions</span></span>

<span data-ttu-id="27d08-145">登入類型分類的使用者，並未在信箱上的稽核的動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-145">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="27d08-146">下列清單說明登入類型的信箱中所使用的稽核記錄：</span><span class="sxs-lookup"><span data-stu-id="27d08-146">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="27d08-147">**擁有者**： 信箱擁有者 （與信箱相關聯的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="27d08-147">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>

- <span data-ttu-id="27d08-148">**委派**：</span><span class="sxs-lookup"><span data-stu-id="27d08-148">**Delegate**:</span></span>

  - <span data-ttu-id="27d08-149">使用者獲指派 SendAs、 SendOnBehalf 或 FullAccess 權限到另一個信箱。</span><span class="sxs-lookup"><span data-stu-id="27d08-149">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>

  - <span data-ttu-id="27d08-150">獲指派的 FullAccess 權限給使用者的信箱是系統管理員。</span><span class="sxs-lookup"><span data-stu-id="27d08-150">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>

- <span data-ttu-id="27d08-151">**系統管理員**：</span><span class="sxs-lookup"><span data-stu-id="27d08-151">**Admin**:</span></span>

  - <span data-ttu-id="27d08-152">信箱搜尋與下列的 Microsoft eDiscovery 工具之一：</span><span class="sxs-lookup"><span data-stu-id="27d08-152">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>

    - <span data-ttu-id="27d08-153">在 「 規範中心中的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="27d08-153">Content Search in the Compliance center.</span></span>

    - <span data-ttu-id="27d08-154">eDiscovery 或規範中心中的進階電子文件。</span><span class="sxs-lookup"><span data-stu-id="27d08-154">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>

    - <span data-ttu-id="27d08-155">Exchange Online 中的就地 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="27d08-155">In-Place eDiscovery in Exchange Online.</span></span>

  - <span data-ttu-id="27d08-156">信箱是藉由使用 Microsoft Exchange Server MAPI 編輯器來存取。</span><span class="sxs-lookup"><span data-stu-id="27d08-156">The mailbox is accessed by using the Microsoft Exchange Server MAPI Editor.</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="27d08-157">代表使用者信箱和共用的信箱的信箱動作</span><span class="sxs-lookup"><span data-stu-id="27d08-157">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="27d08-158">下表說明可用的信箱稽核記錄的使用者信箱以及共用信箱的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-158">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="27d08-159">核取記號 (</span><span class="sxs-lookup"><span data-stu-id="27d08-159">A check mark (</span></span> ![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="27d08-161">) 指示信箱動作可以記錄 （不是所有動作都可用於所有登入類型） 的登入類型。</span><span class="sxs-lookup"><span data-stu-id="27d08-161">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>

- <span data-ttu-id="27d08-162">星號 ( <sup>\*</sup> ) 核取記號表示信箱巨集指令會登入類型的預設記錄之後。</span><span class="sxs-lookup"><span data-stu-id="27d08-162">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>

- <span data-ttu-id="27d08-163">請記住，與信箱完整存取權限的系統管理員會被視為委派。</span><span class="sxs-lookup"><span data-stu-id="27d08-163">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

|<span data-ttu-id="27d08-164">**信箱動作**</span><span class="sxs-lookup"><span data-stu-id="27d08-164">**Mailbox action**</span></span>|<span data-ttu-id="27d08-165">**描述**</span><span class="sxs-lookup"><span data-stu-id="27d08-165">**Description**</span></span>|<span data-ttu-id="27d08-166">**Admin**</span><span class="sxs-lookup"><span data-stu-id="27d08-166">**Admin**</span></span>|<span data-ttu-id="27d08-167">**委派**</span><span class="sxs-lookup"><span data-stu-id="27d08-167">**Delegate**</span></span>|<span data-ttu-id="27d08-168">**Owner**</span><span class="sxs-lookup"><span data-stu-id="27d08-168">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="27d08-169">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="27d08-169">**AddFolderPermissions**</span></span>|<span data-ttu-id="27d08-170">**附註**： 雖然這個值會被接受為信箱的動作，但它已包含在**UpdateFolderPermissions**動作並不分開稽核。</span><span class="sxs-lookup"><span data-stu-id="27d08-170">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="27d08-171">換言之，請勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="27d08-171">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="27d08-172">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="27d08-172">**ApplyRecord**</span></span>|<span data-ttu-id="27d08-173">項目標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-173">An item is labeled as a record.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="27d08-177">**Copy**</span><span class="sxs-lookup"><span data-stu-id="27d08-177">**Copy**</span></span>|<span data-ttu-id="27d08-178">郵件已複製到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="27d08-178">A message was copied to another folder.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="27d08-180">**Create**</span><span class="sxs-lookup"><span data-stu-id="27d08-180">**Create**</span></span>|<span data-ttu-id="27d08-181">在信箱中的 [行事曆、 連絡人、 備忘稿或工作] 資料夾中建立項目 （例如，會建立新的會議邀請）。</span><span class="sxs-lookup"><span data-stu-id="27d08-181">An item was created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox (for example, a new meeting request is created).</span></span> <span data-ttu-id="27d08-182">請注意不稽核建立、 傳送或接收郵件。</span><span class="sxs-lookup"><span data-stu-id="27d08-182">Note that creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="27d08-183">此外，建立信箱資料夾的動作也不會受到稽核。</span><span class="sxs-lookup"><span data-stu-id="27d08-183">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="27d08-184">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-184">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-185">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-185">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="27d08-187">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="27d08-187">**FolderBind**</span></span>|<span data-ttu-id="27d08-188">存取信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="27d08-188">A mailbox folder was accessed.</span></span> <span data-ttu-id="27d08-189">系統管理員或代理人開啟信箱時，也會記錄此巨集指令。</span><span class="sxs-lookup"><span data-stu-id="27d08-189">This action is also logged when the admin or delegate opens the mailbox.</span></span> <br/><br/> <span data-ttu-id="27d08-190">**附註**： 合併委派所執行的資料夾繫結動作的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-190">**Note**: Audit records for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="27d08-191">個別資料夾存取產生一個稽核記錄 24 小時期間內。</span><span class="sxs-lookup"><span data-stu-id="27d08-191">One audit record is generated for individual folder access within 24 hour period.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="27d08-194">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="27d08-194">**HardDelete**</span></span>|<span data-ttu-id="27d08-195">郵件已從 [可復原的項目] 資料夾中清除。</span><span class="sxs-lookup"><span data-stu-id="27d08-195">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="27d08-196">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-196">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-197">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-197">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-198">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-198">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="27d08-199">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="27d08-199">**MailboxLogin**</span></span>|<span data-ttu-id="27d08-200">使用者登入其信箱。</span><span class="sxs-lookup"><span data-stu-id="27d08-200">The user signed into their mailbox.</span></span> |||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="27d08-202">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="27d08-202">**MessageBind**</span></span>|<span data-ttu-id="27d08-203">郵件已在 [預覽] 窗格中檢視，或開啟。</span><span class="sxs-lookup"><span data-stu-id="27d08-203">A message was viewed in the preview pane or opened.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="27d08-205">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="27d08-205">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="27d08-206">**附註**： 雖然這個值會被接受為信箱的動作，但它已包含在**UpdateFolderPermissions**動作並不分開稽核。</span><span class="sxs-lookup"><span data-stu-id="27d08-206">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="27d08-207">換言之，請勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="27d08-207">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="27d08-208">**Move**</span><span class="sxs-lookup"><span data-stu-id="27d08-208">**Move**</span></span>|<span data-ttu-id="27d08-209">郵件已移到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="27d08-209">A message was moved to another folder.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="27d08-213">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="27d08-213">**MoveToDeletedItems**</span></span>|<span data-ttu-id="27d08-214">郵件已遭刪除並移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="27d08-214">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="27d08-215">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-215">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-216">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-216">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-217">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-217">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="27d08-218">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="27d08-218">**RecordDelete**</span></span>|<span data-ttu-id="27d08-219">會標示為記錄的虛刪除 （移至 [可復原的項目] 資料夾） 項目。</span><span class="sxs-lookup"><span data-stu-id="27d08-219">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="27d08-220">標示為記錄的項目無法永久刪除 （清除從 [可復原的項目] 資料夾）。</span><span class="sxs-lookup"><span data-stu-id="27d08-220">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="27d08-224">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="27d08-224">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="27d08-225">**附註**： 雖然這個值會被接受為信箱的動作，但它已包含在**UpdateFolderPermissions**動作並不分開稽核。</span><span class="sxs-lookup"><span data-stu-id="27d08-225">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="27d08-226">換言之，請勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="27d08-226">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="27d08-227">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="27d08-227">**SendAs**</span></span>|<span data-ttu-id="27d08-228">已使用 [傳送為] 權限傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="27d08-228">A message was sent using the SendAs permission.</span></span> <span data-ttu-id="27d08-229">這表示另一位使用者傳送的郵件，就好像它來自信箱擁有者。</span><span class="sxs-lookup"><span data-stu-id="27d08-229">This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="27d08-230">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-230">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-231">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-231">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="27d08-232">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="27d08-232">**SendOnBehalf**</span></span>|<span data-ttu-id="27d08-233">已使用 [代理傳送者] 權限傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="27d08-233">A message was sent using the SendOnBehalf permission.</span></span> <span data-ttu-id="27d08-234">這表示另一位使用者傳送代表信箱擁有者的郵件。</span><span class="sxs-lookup"><span data-stu-id="27d08-234">This means another user sent the message on behalf of the mailbox owner.</span></span> <span data-ttu-id="27d08-235">此郵件會向收件者指出誰代理傳送郵件，以及實際上是誰傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="27d08-235">The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="27d08-236">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-236">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-237">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-237">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="27d08-238">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="27d08-238">**SoftDelete**</span></span>|<span data-ttu-id="27d08-239">郵件已永久刪除或從 [刪除的郵件] 資料夾中刪除。</span><span class="sxs-lookup"><span data-stu-id="27d08-239">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="27d08-240">虛刪除的項目會移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="27d08-240">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="27d08-241">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-241">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-242">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-242">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-243">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-243">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="27d08-244">**更新**</span><span class="sxs-lookup"><span data-stu-id="27d08-244">**Update**</span></span>|<span data-ttu-id="27d08-245">郵件或其屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="27d08-245">A message or its properties was changed.</span></span>|<span data-ttu-id="27d08-246">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-246">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-247">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-247">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-248">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-248">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="27d08-249">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="27d08-249">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="27d08-250">行事曆委派已指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="27d08-250">A calendar delegation was assigned to a mailbox.</span></span> <span data-ttu-id="27d08-251">行事曆代理可讓其他有相同組織權限的人來管理信箱擁有者的行事曆。</span><span class="sxs-lookup"><span data-stu-id="27d08-251">Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="27d08-252">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-252">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||<span data-ttu-id="27d08-253">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-253">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="27d08-254">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="27d08-254">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="27d08-255">資料夾權限已變更。</span><span class="sxs-lookup"><span data-stu-id="27d08-255">A folder permission was changed.</span></span> <span data-ttu-id="27d08-256">資料夾權限可控制組織中的哪些使用者可以存取信箱中的資料夾，以及這些資料夾中的郵件。</span><span class="sxs-lookup"><span data-stu-id="27d08-256">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="27d08-257">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-257">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-258">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-258">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-259">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-259">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="27d08-260">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="27d08-260">**UpdateInboxRules**</span></span>|<span data-ttu-id="27d08-261">收件匣規則已新增、 移除或變更。</span><span class="sxs-lookup"><span data-stu-id="27d08-261">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="27d08-262">收件匣規則用來處理郵件使用者的收件匣根據指定的條件，並符合規則的條件，例如將郵件移至指定資料夾或刪除郵件時採取的動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-262">Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="27d08-263">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-263">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-264">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-264">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-265">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-265">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|

> [!IMPORTANT]
> <span data-ttu-id="27d08-266">如果您自訂信箱来稽核的動作的任何登入類型*之前*的信箱稽核上依預設已啟用組織中，自訂的設定會保留在信箱上並不以覆寫預設信箱動作本節所述。</span><span class="sxs-lookup"><span data-stu-id="27d08-266">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="27d08-267">若要還原為其預設值 （其中您可以在任何時間） 的稽核信箱動作，請參閱本主題稍後的 [[還原預設信箱動作](#restore-the-default-mailbox-actions)] 區段。</span><span class="sxs-lookup"><span data-stu-id="27d08-267">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this topic.</span></span>

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a><span data-ttu-id="27d08-268">Office 365 群組信箱的信箱動作</span><span class="sxs-lookup"><span data-stu-id="27d08-268">Mailbox actions for Office 365 Group mailboxes</span></span>

<span data-ttu-id="27d08-269">信箱稽核上預設會帶信箱稽核登入至 Office 365 群組信箱，但您不能自訂正在記錄的內容 （您無法新增或移除任何登入類型記錄的信箱動作）。</span><span class="sxs-lookup"><span data-stu-id="27d08-269">Mailbox auditing on by default brings mailbox audit logging to Office 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="27d08-270">下表說明每個登入類型的 Office 365 群組信箱上的預設記錄的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-270">The following table describes the mailbox actions that are logged by default on Office 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="27d08-271">請記住，與 Office 365 群組信箱完整存取權限的系統管理員會被視為委派。</span><span class="sxs-lookup"><span data-stu-id="27d08-271">Remember, an admin with Full Access permission to an Office 365 Group mailbox is considered a delegate.</span></span>

|<span data-ttu-id="27d08-272">**信箱動作**</span><span class="sxs-lookup"><span data-stu-id="27d08-272">**Mailbox action**</span></span>|<span data-ttu-id="27d08-273">**描述**</span><span class="sxs-lookup"><span data-stu-id="27d08-273">**Description**</span></span>|<span data-ttu-id="27d08-274">**Admin**</span><span class="sxs-lookup"><span data-stu-id="27d08-274">**Admin**</span></span>|<span data-ttu-id="27d08-275">**委派**</span><span class="sxs-lookup"><span data-stu-id="27d08-275">**Delegate**</span></span>|<span data-ttu-id="27d08-276">**Owner**</span><span class="sxs-lookup"><span data-stu-id="27d08-276">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="27d08-277">**Create**</span><span class="sxs-lookup"><span data-stu-id="27d08-277">**Create**</span></span>|<span data-ttu-id="27d08-278">建立的行事曆項目。</span><span class="sxs-lookup"><span data-stu-id="27d08-278">Creation of a calendar Item.</span></span> <span data-ttu-id="27d08-279">請注意不稽核建立、 傳送或接收郵件。</span><span class="sxs-lookup"><span data-stu-id="27d08-279">Note that creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="27d08-280">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-280">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-281">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-281">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="27d08-282">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="27d08-282">**HardDelete**</span></span>|<span data-ttu-id="27d08-283">郵件已從 [可復原的項目] 資料夾中清除。</span><span class="sxs-lookup"><span data-stu-id="27d08-283">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="27d08-284">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-284">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-285">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-285">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-286">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-286">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="27d08-287">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="27d08-287">**MoveToDeletedItems**</span></span>|<span data-ttu-id="27d08-288">郵件已遭刪除並移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="27d08-288">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="27d08-289">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-289">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-290">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-290">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-291">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-291">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="27d08-292">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="27d08-292">**SendAs**</span></span>|<span data-ttu-id="27d08-293">已使用 [傳送為] 權限傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="27d08-293">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="27d08-294">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-294">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-295">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-295">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="27d08-296">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="27d08-296">**SendOnBehalf**</span></span>|<span data-ttu-id="27d08-297">已使用 [代理傳送者] 權限傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="27d08-297">A message was sent using the SendOnBehalf permission.</span></span> |<span data-ttu-id="27d08-298">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-298">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-299">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-299">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="27d08-300">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="27d08-300">**SoftDelete**</span></span>|<span data-ttu-id="27d08-301">郵件已永久刪除或從 [刪除的郵件] 資料夾中刪除。</span><span class="sxs-lookup"><span data-stu-id="27d08-301">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="27d08-302">虛刪除的項目會移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="27d08-302">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="27d08-303">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-303">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-304">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-304">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-305">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-305">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="27d08-306">**更新**</span><span class="sxs-lookup"><span data-stu-id="27d08-306">**Update**</span></span>|<span data-ttu-id="27d08-307">郵件或其屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="27d08-307">A message or its properties was changed.</span></span>|<span data-ttu-id="27d08-308">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-308">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-309">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-309">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="27d08-310">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27d08-310">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="27d08-311">確認記錄每個登入類型預設信箱動作</span><span class="sxs-lookup"><span data-stu-id="27d08-311">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="27d08-312">信箱的稽核的預設值時，會將新*DefaultAuditSet*屬性新增至所有的信箱。</span><span class="sxs-lookup"><span data-stu-id="27d08-312">Mailbox auditing on by defaults adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="27d08-313">此屬性的值會指出是否要對信箱稽核 （由 Microsoft 管理） 的預設信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-313">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="27d08-314">若要在使用者信箱或共用的信箱上顯示值，取代\<MailboxIdentity\>使用的名稱、 別名，電子郵件地址或使用者主要名稱 （使用者名稱） 的信箱，並在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="27d08-314">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="27d08-315">若要在 Office 365 群組的信箱上顯示值，取代\<MailboxIdentity\>與名稱、 別名或共用的信箱並執行下列命令在 Exchange Online PowerShell 中的電子郵件地址：</span><span class="sxs-lookup"><span data-stu-id="27d08-315">To display the value on Office 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="27d08-316">值`Admin, Delegate, Owner`表示：</span><span class="sxs-lookup"><span data-stu-id="27d08-316">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="27d08-317">要稽核所有三個登入類型的預設信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-317">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="27d08-318">請注意這是您會看到 Office 365 群組信箱的唯一值。</span><span class="sxs-lookup"><span data-stu-id="27d08-318">Note that this is the only value you'll see on Office 365 Group mailboxes.</span></span>

- <span data-ttu-id="27d08-319">*不具有*系統管理變更使用者信箱或共用的信箱上任何登入類型的稽核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-319">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="27d08-320">請注意這是預設狀態之後的信箱上預設開啟稽核功能最初貴組織中。</span><span class="sxs-lookup"><span data-stu-id="27d08-320">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="27d08-321">如果系統管理員具有曾經需要變更稽核登入類型 （藉由**將 Set-mailbox** cmdlet 上使用*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數） 的信箱動作，則此屬性值將會不同。</span><span class="sxs-lookup"><span data-stu-id="27d08-321">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="27d08-322">例如，值`Owner` *DefaultAuditSet*屬性是以使用者的信箱或共用的信箱表示：</span><span class="sxs-lookup"><span data-stu-id="27d08-322">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="27d08-323">要稽核的信箱擁有者的預設信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-323">The default mailbox actions for the mailbox owner are being audited.</span></span>

- <span data-ttu-id="27d08-324">稽核的信箱動作`Delegate`和`Admin`已經變更登入類型從預設動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-324">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="27d08-325">*DefaultAuditSet*屬性空白值表示所有三個登入類型已變更的使用者信箱或共用的信箱的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-325">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="27d08-326">如需詳細資訊，請參閱本主題中的[預設記錄變更或還原的信箱動作](#change-or-restore-mailbox-actions-logged-by-default)」 一節</span><span class="sxs-lookup"><span data-stu-id="27d08-326">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this topic</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="27d08-327">顯示正在登入信箱的信箱動作</span><span class="sxs-lookup"><span data-stu-id="27d08-327">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="27d08-328">若要查看目前登入使用者信箱或共用的信箱的信箱動作，取代\<MailboxIdentity\>使用的名稱、 別名、 電子郵件地址或使用者主要名稱 （使用者名稱），信箱的並在 Exchange Online PowerShell 中執行一或多個下列命令。</span><span class="sxs-lookup"><span data-stu-id="27d08-328">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="27d08-329">雖然您可以加入`-GroupMailbox`切換到 Office 365 群組信箱的下列**Get-mailbox**命令不認為您會看到的值。</span><span class="sxs-lookup"><span data-stu-id="27d08-329">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Office 365 Group mailboxes, don't believe the values you see.</span></span> <span data-ttu-id="27d08-330">預設和 Office 365 群組信箱稽核的靜態的信箱動作稍早在本主題中[的 Office 365 群組信箱的信箱動作](#mailbox-actions-for-office-365-group-mailboxes)節所述。</span><span class="sxs-lookup"><span data-stu-id="27d08-330">The default and static mailbox actions that are audited for Office 365 Group mailboxes are described in the [Mailbox actions for Office 365 Group mailboxes](#mailbox-actions-for-office-365-group-mailboxes) section earlier in this topic.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="27d08-331">擁有者動作</span><span class="sxs-lookup"><span data-stu-id="27d08-331">Owner actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="27d08-332">代理人動作</span><span class="sxs-lookup"><span data-stu-id="27d08-332">Delegate actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="27d08-333">系統管理動作</span><span class="sxs-lookup"><span data-stu-id="27d08-333">Admin actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="27d08-334">變更或還原預設記錄的信箱動作</span><span class="sxs-lookup"><span data-stu-id="27d08-334">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="27d08-335">如同先前的說明，其中一個信箱稽核上具有預設的主要優點是： 您不需要管理稽核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-335">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="27d08-336">Microsoft 會為您，我們將會自動新增新的信箱動作，以稽核依預設，因為它們發行。</span><span class="sxs-lookup"><span data-stu-id="27d08-336">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="27d08-337">不過，您的組織可能需要稽核一組不同的使用者信箱的信箱動作，以及共用信箱。</span><span class="sxs-lookup"><span data-stu-id="27d08-337">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="27d08-338">本節中的程序顯示如何變更每個登入類型，稽核的信箱動作，以及如何回復到 Microsoft 受管理的預設動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-338">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27d08-339">如果您使用下列程序以自訂登入使用者信箱或共用信箱的信箱動作時，由 Microsoft 釋放任何新預設信箱動作將不會自動稽核這些信箱上。</span><span class="sxs-lookup"><span data-stu-id="27d08-339">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="27d08-340">您需要以手動方式將任何新的信箱動作新增至您自訂動作的清單。</span><span class="sxs-lookup"><span data-stu-id="27d08-340">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="27d08-341">變更要稽核的信箱動作</span><span class="sxs-lookup"><span data-stu-id="27d08-341">Change the mailbox actions to audit</span></span>

<span data-ttu-id="27d08-342">您可以使用**Set-mailbox**指令程式上的*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數來變更使用者信箱的稽核和共用信箱 （稽核動作無法自訂信箱的 Office 365 群組） 的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-342">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Office 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="27d08-343">您可以使用兩個不同的方法來指定信箱動作：</span><span class="sxs-lookup"><span data-stu-id="27d08-343">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="27d08-344">*取代*（覆寫） 現有的信箱動作，使用下列語法： `action1,action2,...actionN`。</span><span class="sxs-lookup"><span data-stu-id="27d08-344">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>

- <span data-ttu-id="27d08-345">*新增或移除*信箱動作，而不影響其他現有的值使用下列語法：`@{Add="action1","action2",..."actionN"}`或`@{Remove="action1","action2",..."actionN"}`。</span><span class="sxs-lookup"><span data-stu-id="27d08-345">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="27d08-346">此範例會變更使用來覆寫預設動作 SoftDelete 和 HardDelete 對名為 「 Gabriela Laureano 」 信箱的系統信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-346">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="27d08-347">此範例會新增信箱 laura@contoso.onmicrosoft.com MailboxLogin 擁有者動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-347">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="27d08-348">此範例會移除團隊討論信箱 MoveToDeletedItems 委派巨集指令。</span><span class="sxs-lookup"><span data-stu-id="27d08-348">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="27d08-349">不論您使用的方法，自訂使用者信箱或共用的信箱的稽核的信箱動作有下列結果：</span><span class="sxs-lookup"><span data-stu-id="27d08-349">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="27d08-350">對於您自訂登入類型]，不再是由 Microsoft 管理稽核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-350">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>

- <span data-ttu-id="27d08-351">您自訂的登入類型不再顯示在信箱*DefaultAuditSet*屬性值為[先前所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。</span><span class="sxs-lookup"><span data-stu-id="27d08-351">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="27d08-352">還原預設信箱動作</span><span class="sxs-lookup"><span data-stu-id="27d08-352">Restore the default mailbox actions</span></span>

<span data-ttu-id="27d08-353">如果您自訂稽核使用者信箱或共用的信箱的信箱動作，您可以使用下列語法來還原一個或所有登入類型的預設信箱動作：</span><span class="sxs-lookup"><span data-stu-id="27d08-353">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="27d08-354">您可以指定多個以逗號隔開的*DefaultAuditSet*值</span><span class="sxs-lookup"><span data-stu-id="27d08-354">You can specify multiple *DefaultAuditSet* values separated by commas</span></span>

<span data-ttu-id="27d08-355">**附註**： 下列程序不適用於 Office 365 群組信箱 （它們限制為預設動作為 > 所述[以下](#mailbox-actions-for-office-365-group-mailboxes)）。</span><span class="sxs-lookup"><span data-stu-id="27d08-355">**Note**: The following procedures don't apply to Office 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-office-365-group-mailboxes)).</span></span>

<span data-ttu-id="27d08-356">此範例會還原信箱 mark@contoso.onmicrosoft.com 上的所有登入類型的預設稽核信箱動作。</span><span class="sxs-lookup"><span data-stu-id="27d08-356">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="27d08-357">本範例會還原信箱 chris@contoso.onmicrosoft.com，系統管理員登入類型的預設稽核信箱動作，但其中的代理人和擁有者的自訂稽核的信箱動作登入類型。</span><span class="sxs-lookup"><span data-stu-id="27d08-357">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="27d08-358">還原他稽核的預設信箱動作登入類型有下列結果：</span><span class="sxs-lookup"><span data-stu-id="27d08-358">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="27d08-359">登入類型的預設信箱動作會被取代目前的信箱動作清單。</span><span class="sxs-lookup"><span data-stu-id="27d08-359">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>

- <span data-ttu-id="27d08-360">由 Microsoft 釋放任何新信箱動作會自動新增至登入類型的稽核動作清單。</span><span class="sxs-lookup"><span data-stu-id="27d08-360">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>

- <span data-ttu-id="27d08-361">信箱的*DefaultAuditSet*屬性值會更新以包含已還原的登入類型。</span><span class="sxs-lookup"><span data-stu-id="27d08-361">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="27d08-362">關閉信箱的稽核預設為您的組織</span><span class="sxs-lookup"><span data-stu-id="27d08-362">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="27d08-363">您可以關閉信箱稽核上預設為整個組織的 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="27d08-363">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="27d08-364">關閉信箱的稽核預設具有下列結果：</span><span class="sxs-lookup"><span data-stu-id="27d08-364">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="27d08-365">信箱稽核已停用您的組織。</span><span class="sxs-lookup"><span data-stu-id="27d08-365">Mailbox auditing is disabled for your organization.</span></span>

- <span data-ttu-id="27d08-366">從您停用信箱的稽核依預設，沒有信箱動作稽核，即使稽核 （信箱上的*AuditEnabled*屬性為**True**） 的信箱上啟用。</span><span class="sxs-lookup"><span data-stu-id="27d08-366">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>

- <span data-ttu-id="27d08-367">代表新的信箱和設定*AuditEnabled*屬性信箱上的新的或現有的信箱設**為 True**則會忽略未啟用信箱稽核。</span><span class="sxs-lookup"><span data-stu-id="27d08-367">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>

- <span data-ttu-id="27d08-368">任何信箱稽核略過的關聯 （使用**Set-mailboxauditbypassassociation**指令程式來設定） 的設定會被忽略。</span><span class="sxs-lookup"><span data-stu-id="27d08-368">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>

- <span data-ttu-id="27d08-369">現有的信箱稽核記錄會保留直到稽核記錄檔保留天數到期的記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-369">Existing mailbox audit records are retained until the audit log age limit for the the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="27d08-370">信箱上開啟稽核預設</span><span class="sxs-lookup"><span data-stu-id="27d08-370">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="27d08-371">若要開啟信箱的稽核重新開啟您的組織，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="27d08-371">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="27d08-372">略過信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="27d08-372">Bypass mailbox audit logging</span></span>

<span data-ttu-id="27d08-373">目前，您無法停用信箱稽核特定信箱的信箱上的稽核預設組織中開啟時。</span><span class="sxs-lookup"><span data-stu-id="27d08-373">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="27d08-374">例如， *AuditEnabled*信箱屬性設定為**False**則會忽略。</span><span class="sxs-lookup"><span data-stu-id="27d08-374">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="27d08-375">不過，您可以仍使用**Set-mailboxauditbypassassociation**指令程式在 Exchange Online PowerShell 以防止*任何及所有*的信箱動作所指定的使用者，使登入，不論動作發生的位置。</span><span class="sxs-lookup"><span data-stu-id="27d08-375">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="27d08-376">例如：</span><span class="sxs-lookup"><span data-stu-id="27d08-376">For example:</span></span>

- <span data-ttu-id="27d08-377">略過的使用者所執行的信箱擁有者動作不會記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-377">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>

- <span data-ttu-id="27d08-378">略過的使用者 （包括共用的信箱） 的其他使用者的信箱上所執行的代理人動作不會記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-378">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>

- <span data-ttu-id="27d08-379">略過的使用者所執行的系統管理動作不會記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-379">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="27d08-380">若要略過信箱稽核記錄的特定使用者，取代\<MailboxIdentity\>使用的名稱、 電子郵件地址、 別名或使用者主要名稱 （使用者名稱），使用者的並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="27d08-380">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="27d08-381">若要確認已針對指定的使用者略過的稽核，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="27d08-381">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="27d08-382">**True 是表示**的值會指出該信箱稽核記錄就會略過的使用者。</span><span class="sxs-lookup"><span data-stu-id="27d08-382">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="27d08-383">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="27d08-383">More information</span></span>

- <span data-ttu-id="27d08-384">雖然信箱稽核記錄上預設會啟用所有的組織，只有具備 E5 授權的使用者將會傳回信箱稽核記錄事件，在[稽核記錄搜尋的安全性 & 合規性中心中](search-the-audit-log-in-security-and-compliance.md)或透過[Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="27d08-384">Although mailbox audit logging on by default is enabled for all organizations, only users with E5 licenses will return mailbox audit log events in [audit log searches in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md) or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

  <span data-ttu-id="27d08-385">若要擷取沒有 E5 授權使用者的信箱稽核記錄項目，您可以：</span><span class="sxs-lookup"><span data-stu-id="27d08-385">To retrieve mailbox audit log entries for users without E5 licenses, you can:</span></span>

  - <span data-ttu-id="27d08-386">在 Exchange Online PowerShell 中使用下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="27d08-386">Use the following cmdlets in Exchange Online PowerShell:</span></span>

    - <span data-ttu-id="27d08-387">[Search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)來搜尋信箱稽核記錄檔中的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="27d08-387">[Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) to search the mailbox audit log for specific users.</span></span>

    - <span data-ttu-id="27d08-388">[New-mailboxauditlogsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch)來搜尋信箱稽核記錄，針對特定使用者，並使透過電子郵件傳送給指定的收件者的結果。</span><span class="sxs-lookup"><span data-stu-id="27d08-388">[New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch) to search the mailbox audit log for specific users and to have the results sent via email to specified recipients.</span></span>

  - <span data-ttu-id="27d08-389">Exchange Online 中使用 Exchange 系統管理中心 (EAC)，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="27d08-389">Use the Exchange admin center (EAC) in Exchange Online to do the following actions:</span></span>

    - [<span data-ttu-id="27d08-390">匯出信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="27d08-390">Export mailbox audit logs</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [<span data-ttu-id="27d08-391">執行非擁有者信箱存取報告</span><span class="sxs-lookup"><span data-stu-id="27d08-391">Run a non-owner mailbox access report</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- <span data-ttu-id="27d08-392">根據預設，信箱稽核記錄會保留 90 天在被刪除之前的記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-392">By default, mailbox audit log records are retained for 90 days before they're deleted.</span></span> <span data-ttu-id="27d08-393">您可以在 Exchange Online PowerShell 中的**Set-mailbox**指令程式上使用*AuditLogAgeLimit*參數變更稽核記錄保留天數。</span><span class="sxs-lookup"><span data-stu-id="27d08-393">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="27d08-394">不過，增加此值不會讓您搜尋超過 90 天的 Office 365 稽核記錄中的事件。</span><span class="sxs-lookup"><span data-stu-id="27d08-394">However, increasing this value doesn't allow you to search for events that are older than 90 days in the Office 365 audit log.</span></span>

  <span data-ttu-id="27d08-395">如果您增加保留天數時，您需要使用[Search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)指令程式在 Exchange Online PowerShell 來搜尋使用者的信箱稽核記錄超過 90 天的記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-395">If you increase the age limit, you need to use the [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="27d08-396">如果您已經變更*AuditLogAgeLimit*屬性之前信箱的稽核預設組織正在開啟信箱，現有的信箱稽核記錄保留限制無法變更。</span><span class="sxs-lookup"><span data-stu-id="27d08-396">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="27d08-397">換句話說，信箱的稽核預設不會影響信箱稽核記錄的目前保留限制。</span><span class="sxs-lookup"><span data-stu-id="27d08-397">In other words, mailbox auditing on by default doesn't effect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="27d08-398">若要變更*AuditLogAgeLimit*值位於 Office 365 群組信箱，您必須包含`-GroupMailbox`切換**Set-mailbox**命令中。</span><span class="sxs-lookup"><span data-stu-id="27d08-398">To change the *AuditLogAgeLimit* value on an Office 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="27d08-399">信箱稽核記錄的每位使用者的信箱中 [可復原的項目] 資料夾中 （名為*稽核*） 的子資料夾中儲存的記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-399">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="27d08-400">請謹記下列事項需要注意的信箱稽核記錄和可復原的項目] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="27d08-400">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="27d08-401">[可復原的項目] 資料夾，（[警告] 配額為 20 GB） 的預設為 30 GB 的儲存配額的信箱稽核記錄個數。</span><span class="sxs-lookup"><span data-stu-id="27d08-401">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="27d08-402">儲存配額會自動增加至 100 GB （以 90 GB 警告] 配額） 時：</span><span class="sxs-lookup"><span data-stu-id="27d08-402">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>

    - <span data-ttu-id="27d08-403">保留在信箱上。</span><span class="sxs-lookup"><span data-stu-id="27d08-403">A hold is placed on a mailbox.</span></span>

    - <span data-ttu-id="27d08-404">信箱被指派給 「 規範中心中的保留原則。</span><span class="sxs-lookup"><span data-stu-id="27d08-404">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="27d08-405">信箱稽核記錄也會計入[[可復原的項目] 資料夾的資料夾限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。</span><span class="sxs-lookup"><span data-stu-id="27d08-405">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="27d08-406">最大值為 3 百萬個項目 （稽核記錄） 可以儲存在 [稽核] 子資料夾。</span><span class="sxs-lookup"><span data-stu-id="27d08-406">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27d08-407">它是不太可能會影響信箱的稽核依預設，儲存空間配額或 [可復原的項目] 資料夾的資料夾限制。</span><span class="sxs-lookup"><span data-stu-id="27d08-407">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="27d08-408">您可以執行下列命令在 Exchange Online PowerShell，在 [可復原的項目] 資料夾中的 [稽核] 子資料夾中顯示的大小和項目數：</span><span class="sxs-lookup"><span data-stu-id="27d08-408">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="27d08-409">您無法直接存取稽核記錄檔中記錄 [可復原的項目] 資料夾中。相反地，您會使用**Search-mailboxauditlog**指令程式，或搜尋 Office 365 稽核記錄] 來尋找及檢視信箱稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="27d08-409">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the Office 365 audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="27d08-410">如果信箱會處於暫止狀態或指派給 「 規範中心中的保留原則，稽核記錄會記錄仍會保留該信箱*AuditLogAgeLimit*屬性 （預設為 90 天） 所定義的持續時間。</span><span class="sxs-lookup"><span data-stu-id="27d08-410">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="27d08-411">若要保留稽核記錄會記錄較長的保留的信箱，您需要增加信箱的*AuditLogAgeLimit*值。</span><span class="sxs-lookup"><span data-stu-id="27d08-411">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>
