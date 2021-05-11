---
title: Microsoft 365 中的進階稽核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 中的進階稽核提供新的稽核功能，以協助組織進行鑑識與合規性調查。
ms.openlocfilehash: 3c91a388bc01a5531309b556a5a8532cb2efbaa6
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311733"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="739f5-103">Microsoft 365 中的進階稽核</span><span class="sxs-lookup"><span data-stu-id="739f5-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="739f5-104">Microsoft 365 中的[整合式稽核功能](search-the-audit-log-in-security-and-compliance.md)，可讓組織深入了解 Microsoft 365 中多種不同服務的多個類型的稽核活動。</span><span class="sxs-lookup"><span data-stu-id="739f5-104">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365.</span></span> <span data-ttu-id="739f5-105">進階稽核經由增加進行調查時所需的稽核記錄保留，提供對有助於判斷危害範圍重要事件的存取，以及快速存取 Office 365 管理活動 API，來幫助組織進行鑑定及合規性調查。</span><span class="sxs-lookup"><span data-stu-id="739f5-105">Advanced Audit helps organizations to conduct forensic and compliance investigations by increasing audit log retention required to conduct an investigation, providing access to crucial events that help determine scope of compromise, and faster access to Office 365 Management Activity API.</span></span>

> [!NOTE]
> <span data-ttu-id="739f5-106">進階稽核可供具有 Office 365 E5/A5/G5 或 Microsoft 365 企業版 E5/A5/G5 訂閱的組織使用。</span><span class="sxs-lookup"><span data-stu-id="739f5-106">Advanced Audit is available for organizations with an Office 365 E5/A5/G5 or Microsoft 365 Enterprise E5/A5/G5 subscription.</span></span> <span data-ttu-id="739f5-107">此外，當 [進階稽核] 功能需要針對每位使用者進行授權時，您可以將 Microsoft 365 E5/A5/G5 合規性或 E5/A5/G5 電子文件探索和 [稽核] 附加元件授權指派給使用者，而針對稽核記錄和存取重要調查事件的長期保留也是如此。</span><span class="sxs-lookup"><span data-stu-id="739f5-107">Additionally, a Microsoft 365 E5/A5/G5 Compliance or E5/A5/G5 eDiscovery and Audit add-on license can be assigned to users when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations.</span></span> <span data-ttu-id="739f5-108">如需授權的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="739f5-108">For more information about licensing, see:</span></span><br/><span data-ttu-id="739f5-109">- [進階稽核授權需求](auditing-solutions-overview.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="739f5-109">- [Advanced Audit licensing requirements](auditing-solutions-overview.md#licensing-requirements)</span></span><br/><span data-ttu-id="739f5-110">- [Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)。</span><span class="sxs-lookup"><span data-stu-id="739f5-110">- [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).</span></span>

<span data-ttu-id="739f5-111">本文概述了 [進階稽核] 功能，並向您展示了如何為 [進階稽核] 設定使用者。</span><span class="sxs-lookup"><span data-stu-id="739f5-111">This article provides an overview of Advanced Audit capabilities and shows you how to set up users for Advanced Audit.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="739f5-112">長期保留稽核記錄</span><span class="sxs-lookup"><span data-stu-id="739f5-112">Long-term retention of audit logs</span></span>

<span data-ttu-id="739f5-113">進階稽核會保留所有 Exchange、SharePoint 和 Azure Active Directory 稽核記錄，時間為一年。</span><span class="sxs-lookup"><span data-stu-id="739f5-113">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="739f5-114">這是透過預設的稽核記錄保留原則完成，它會保留包含 **Workload** 屬性 (這指出發生活動所在的服務) 的 **Exchange**、**SharePoint** 或 **AzureActiveDirectory** 的值的任何稽核記錄一年。</span><span class="sxs-lookup"><span data-stu-id="739f5-114">This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year.</span></span> <span data-ttu-id="739f5-115">保留稽核記錄的時間越長，可協助您進行深入的鑑定或合規性調查。</span><span class="sxs-lookup"><span data-stu-id="739f5-115">Retaining audit records for longer periods can help with on-going forensic or compliance investigations.</span></span> <span data-ttu-id="739f5-116">如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md#default-audit-log-retention-policy)中的「預設稽核記錄保留原則」章節。</span><span class="sxs-lookup"><span data-stu-id="739f5-116">For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

<span data-ttu-id="739f5-117">我們也會發佈將稽核記錄保留 10 年的功能。</span><span class="sxs-lookup"><span data-stu-id="739f5-117">We're also releasing the capability to retain audit logs for 10 years.</span></span> <span data-ttu-id="739f5-118">將稽核記錄保留 10 年可協助支援長期的調查，並回應法規、法律和內部責任。</span><span class="sxs-lookup"><span data-stu-id="739f5-118">The 10-year retention of audit logs helps support long running investigations and respond to regulatory, legal, and internal obligations.</span></span>

> [!NOTE]
> <span data-ttu-id="739f5-119">保留 10 年的稽核記錄會需要額外的附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="739f5-119">Retaining audit logs for 10 years will require an additional add-on license.</span></span> <span data-ttu-id="739f5-120">如需詳細資訊，請參閱本文中的[進階稽核常見問題集](#faqs-for-advanced-audit)章節。</span><span class="sxs-lookup"><span data-stu-id="739f5-120">For more information, see the [FAQs for Advanced Audit](#faqs-for-advanced-audit) section in this article.</span></span>

### <a name="audit-log-retention-policies"></a><span data-ttu-id="739f5-121">稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="739f5-121">Audit log retention policies</span></span>

<span data-ttu-id="739f5-122">在其他服務中產生、未在預設稽核記錄保留原則涵蓋範圍的所有稽核記錄 (如前一節所述)，將會保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="739f5-122">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days.</span></span> <span data-ttu-id="739f5-123">不過，您可以建立自訂的稽核記錄保留原則，將其他稽核記錄保留更久的時間，最多可達 10 年。</span><span class="sxs-lookup"><span data-stu-id="739f5-123">But you can create customized audit log retention policies to retain other audit records for longer periods of time up to 10 years.</span></span> <span data-ttu-id="739f5-124">您可以根據下列一或多項準則，建立用來保留稽核記錄的原則：</span><span class="sxs-lookup"><span data-stu-id="739f5-124">You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="739f5-125">發生已稽核活動的 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="739f5-125">The Microsoft 365 service where the audited activities occur.</span></span>

- <span data-ttu-id="739f5-126">特定已稽核活動。</span><span class="sxs-lookup"><span data-stu-id="739f5-126">Specific audited activities.</span></span>

- <span data-ttu-id="739f5-127">執行已稽核活動的使用者。</span><span class="sxs-lookup"><span data-stu-id="739f5-127">The user who performs an audited activity.</span></span>

<span data-ttu-id="739f5-128">您也可以指定要保留符合原則的稽核記錄的時間長度和優先順序層級，以便特定原則可優先於其他原則。</span><span class="sxs-lookup"><span data-stu-id="739f5-128">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies.</span></span> <span data-ttu-id="739f5-129">另請注意，如果您需要為組織中的部分或所有使用者保留 Exchange、SharePoint 或 Azure Active Directory 稽核記錄少於一年 (或 10 年)，任何自訂稽核記錄保留原則都會優先於預設的稽核保留原則。</span><span class="sxs-lookup"><span data-stu-id="739f5-129">Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year (or for 10 years) for some or all users in your organization.</span></span> <span data-ttu-id="739f5-130">如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="739f5-130">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="739f5-131">存取調查重要事件</span><span class="sxs-lookup"><span data-stu-id="739f5-131">Access to crucial events for investigations</span></span>

<span data-ttu-id="739f5-132">進階稽核經由提供對重要事件的存取 (例如何時存取郵件項目、何時回覆和轉寄郵件項目以及使用者何時 Exchange Online 和 SharePoint Online 中進行搜尋和搜尋哪些內容)，來幫助組織進行鑑定及合規性調查。</span><span class="sxs-lookup"><span data-stu-id="739f5-132">Advanced Audit helps organizations to conduct forensic and compliance investigations by providing access to crucial events such as when mail items were accessed, or when mail items were replied to and forwarded, and when and what a user searched for in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="739f5-133">這些重要事件可協助您調查可能的破壞，並判斷危害的範圍。</span><span class="sxs-lookup"><span data-stu-id="739f5-133">These crucial events can help you investigate possible breaches and determine the scope of compromise.</span></span>  <span data-ttu-id="739f5-134">[進階稽核] 提供下列重要事件：</span><span class="sxs-lookup"><span data-stu-id="739f5-134">Advanced Auditing provides the following crucial events:</span></span>

- [<span data-ttu-id="739f5-135">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="739f5-135">MailItemsAccessed</span></span>](#mailitemsaccessed)

- [<span data-ttu-id="739f5-136">Send</span><span class="sxs-lookup"><span data-stu-id="739f5-136">Send</span></span>](#send)

- <span data-ttu-id="739f5-137">[SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="739f5-137">[SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)<sup>\*</sup></span></span>

- <span data-ttu-id="739f5-138">[SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="739f5-138">[SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)<sup>\*</sup></span></span>

> [!NOTE]
> <span data-ttu-id="739f5-139"><sup>\*</sup> 目前，此活動不適用於 Office 365 和 Microsoft 365 政府環境。</span><span class="sxs-lookup"><span data-stu-id="739f5-139"><sup>\*</sup> At this time, this event isn't available in Office 365 and Microsoft 365 Government environments.</span></span> <span data-ttu-id="739f5-140">這包括 GCC、GCC High 和 DoD 環境。</span><span class="sxs-lookup"><span data-stu-id="739f5-140">This includes GCC, GCC High, and DoD environments.</span></span>

### <a name="mailitemsaccessed"></a><span data-ttu-id="739f5-141">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="739f5-141">MailItemsAccessed</span></span>

<span data-ttu-id="739f5-142">MailItemsAccessed 事件是信箱稽核動作，當郵件資料受郵件通訊協定和郵件用戶端存取時，系統會觸發該事件。</span><span class="sxs-lookup"><span data-stu-id="739f5-142">The MailItemsAccessed event is a mailbox auditing action and is triggered when mail data is accessed by mail protocols and mail clients.</span></span> <span data-ttu-id="739f5-143">MailItemsAccessed 動作可幫助調查人員識別資料外洩，並判斷可能已遭入侵的郵件範圍。</span><span class="sxs-lookup"><span data-stu-id="739f5-143">The MailItemsAccessed action can help investigators identify data breaches and determine the scope of messages that may have been compromised.</span></span> <span data-ttu-id="739f5-144">如果攻擊者取得電子郵件訊息，即使沒有明確訊號指出已實際讀取郵件 (也就是說，在稽核記錄中記錄了透過繫結或同步處理之類的存取類型)，將會觸發 MailItemsAccessed 動作。</span><span class="sxs-lookup"><span data-stu-id="739f5-144">If an attacker gained access to email messages, the MailItemsAccessed action will be triggered even if there is no explicit signal that messages were actually read (in other words, the type of access such as a bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="739f5-145">MailItemsAccessed 信箱動作會取代 Exchange Online 中信箱稽核記錄的 MessageBind，並提供下列改善：</span><span class="sxs-lookup"><span data-stu-id="739f5-145">The MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="739f5-146">MessageBind 僅可針對 AuditAdmin 使用者登入類型設定；不適用於代理人或擁有者動作。</span><span class="sxs-lookup"><span data-stu-id="739f5-146">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions.</span></span> <span data-ttu-id="739f5-147">MailItemsAccessed 適用於所有登入類型。</span><span class="sxs-lookup"><span data-stu-id="739f5-147">MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="739f5-148">MessageBind 僅涵蓋透過郵件用戶端的存取。</span><span class="sxs-lookup"><span data-stu-id="739f5-148">MessageBind only covered access by a mail client.</span></span> <span data-ttu-id="739f5-149">並不適用同步處理活動。</span><span class="sxs-lookup"><span data-stu-id="739f5-149">It didn't apply to sync activities.</span></span> <span data-ttu-id="739f5-150">MailItemsAccessed 事件會由繫結和同步處理存取類型觸發。</span><span class="sxs-lookup"><span data-stu-id="739f5-150">MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="739f5-151">當存取相同的電子郵件訊息時，MessageBind 動作會觸發多個稽核記錄的建立，這會導致稽核的「雜訊」。</span><span class="sxs-lookup"><span data-stu-id="739f5-151">MessageBind actions would trigger the creation of multiple audit records when the same email message was accessed, which resulted in auditing "noise".</span></span> <span data-ttu-id="739f5-152">相反地，MailItemsAccessed 事件會彙總在較少的稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="739f5-152">In contrast, MailItemsAccessed events are aggregated into fewer audit records.</span></span>

<span data-ttu-id="739f5-153">如需有關 MailItemsAccessed 活動的稽核記錄資訊，請參閱[使用進階稽核調查遭入侵帳戶](mailitemsaccessed-forensics-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="739f5-153">For information about audit records for MailItemsAccessed activities, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>

<span data-ttu-id="739f5-154">若要搜尋 MailItemsAccessed 稽核記錄，您可以在 Microsoft 365 合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[Exchange 信箱活動]** 下拉式清單中搜尋 **[已存取的信箱項目]** 活動。</span><span class="sxs-lookup"><span data-stu-id="739f5-154">To search for MailItemsAccessed audit records, you can search for the **Accessed mailbox items** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在稽核記錄搜尋工具中搜尋 MailItemsAccessed 動作](../media/AdvAudit_MailItemsAccessed.png)

<span data-ttu-id="739f5-156">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="739f5-156">You can also run the [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="send"></a><span data-ttu-id="739f5-157">傳送</span><span class="sxs-lookup"><span data-stu-id="739f5-157">Send</span></span>

<span data-ttu-id="739f5-158">Send 事件也是信箱審核動作，當使用者執行下列其中一項動作時，會觸發該事件：</span><span class="sxs-lookup"><span data-stu-id="739f5-158">The Send event is also a mailbox auditing action and is triggered when a user performs one of the following actions:</span></span>

- <span data-ttu-id="739f5-159">傳送電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="739f5-159">Sends an email message</span></span>

- <span data-ttu-id="739f5-160">回覆電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="739f5-160">Replies to an email message</span></span>

- <span data-ttu-id="739f5-161">轉寄電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="739f5-161">Forwards an email message</span></span>

<span data-ttu-id="739f5-162">調查人員可以使用 Send 事件識別從遭入侵帳戶發送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="739f5-162">Investigators can use the Send event to identify email sent from a compromised account.</span></span> <span data-ttu-id="739f5-163">Send 事件的稽核記錄中包含郵件的相關資訊，例如郵件傳送的時間、InternetMessage 識別碼、主旨列，以及郵件是否包含附件。</span><span class="sxs-lookup"><span data-stu-id="739f5-163">The audit record for a Send event contains information about the message, such as when the message was sent, the InternetMessage ID, the subject line, and if the message contained attachments.</span></span> <span data-ttu-id="739f5-164">這項稽核資訊可協助調查人員識別從遭入侵帳戶或攻擊者傳送的電子郵件訊息相關資訊。</span><span class="sxs-lookup"><span data-stu-id="739f5-164">This auditing information can help investigators identify information about email messages sent from a compromised account or sent by an attacker.</span></span> <span data-ttu-id="739f5-165">此外，調查人員可以使用 Microsoft 365 或電子文件探索工具來搜尋郵件 (使用主旨列或郵件識別碼)，以找出傳送郵件的收件者，以及傳送郵件的實際內容。</span><span class="sxs-lookup"><span data-stu-id="739f5-165">Additionally, investigators can use a Microsoft 365 eDiscovery tool to search for the message (by using the subject line or message ID) to identify the recipients the message was sent to and the actual contents of the sent message.</span></span>

<span data-ttu-id="739f5-166">若要搜尋 Send 稽核記錄，您可以在 Microsoft 365 合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[Exchange 信箱活動]** 下拉式清單中搜尋 **[傳送電子郵件]** 活動。</span><span class="sxs-lookup"><span data-stu-id="739f5-166">To search for Send audit records, you can search for the **Sent message** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在 [稽核記錄搜尋工具] 中搜尋 [傳送電子郵件] 動作](../media/AdvAudit_SentMessage.png)

<span data-ttu-id="739f5-168">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="739f5-168">You can also run the [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="searchqueryinitiatedexchange"></a><span data-ttu-id="739f5-169">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="739f5-169">SearchQueryInitiatedExchange</span></span>

<span data-ttu-id="739f5-170">當某人使用 Outlook 在信箱中搜尋項目時，就會觸發 SearchQueryInitiatedExchange 事件。</span><span class="sxs-lookup"><span data-stu-id="739f5-170">The SearchQueryInitiatedExchange event is triggered when a person uses Outlook to search for items in a mailbox.</span></span> <span data-ttu-id="739f5-171">在下列 Outlook 環境中執行搜尋時，會觸發事件：</span><span class="sxs-lookup"><span data-stu-id="739f5-171">Events are triggered when searches are performed in the following Outlook environments:</span></span>

- <span data-ttu-id="739f5-172">Outlook (桌面用戶端)</span><span class="sxs-lookup"><span data-stu-id="739f5-172">Outlook (desktop client)</span></span>

- <span data-ttu-id="739f5-173">Outlook 網頁版 (OWA)</span><span class="sxs-lookup"><span data-stu-id="739f5-173">Outlook on the web (OWA)</span></span>

- <span data-ttu-id="739f5-174">iOS 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="739f5-174">Outlook for iOS</span></span>

- <span data-ttu-id="739f5-175">Android 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="739f5-175">Outlook for Android</span></span>

- <span data-ttu-id="739f5-176">Windows 10 版郵件應用程式</span><span class="sxs-lookup"><span data-stu-id="739f5-176">Mail app for Windows 10</span></span>

<span data-ttu-id="739f5-177">調查人員可以使用 SearchQueryInitiatedExchange 事件，來判斷可能有遭入侵帳號的攻擊者是否已查看或嘗試存取信箱中的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="739f5-177">Investigators can use the SearchQueryInitiatedExchange event to determine if an attacker who may have compromised an account looked for or tried to access sensitive information in the mailbox.</span></span> <span data-ttu-id="739f5-178">SearchQueryInitiatedExchange 事件的稽核記錄包含實際的搜尋查詢文字。</span><span class="sxs-lookup"><span data-stu-id="739f5-178">The audit record for a SearchQueryInitiatedExchange event contains information such as the actual text of the search query.</span></span> <span data-ttu-id="739f5-179">稽核記錄也會指出搜尋執行時所用的 Outlook 環境。</span><span class="sxs-lookup"><span data-stu-id="739f5-179">The audit record also indicates the Outlook environment the search was performed in.</span></span> <span data-ttu-id="739f5-180">透過查看攻擊者可能執行的搜尋查詢，調查人員可以更能瞭解搜尋的電子郵件資料意圖。</span><span class="sxs-lookup"><span data-stu-id="739f5-180">By looking at the search queries that an attacker may have performed, an investigator can better understand the intent of the email data that was searched for.</span></span>

<span data-ttu-id="739f5-181">若要搜尋 SearchQueryInitiatedExchange 稽核記錄，您可以在合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[搜尋活動]** 下拉式清單中搜尋 **[執行電子郵件搜尋]** 活動。</span><span class="sxs-lookup"><span data-stu-id="739f5-181">To search for SearchQueryInitiatedExchange audit records, you can search for the **Performed email search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在 [稽核記錄搜尋工具] 中搜尋 [執行電子郵件搜尋] 動作](../media/AdvAudit_SearchExchange.png)

<span data-ttu-id="739f5-183">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="739f5-183">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="739f5-184">您必須啟用要記錄的 SearchQueryInitiatedExchange，才能在稽核記錄中搜尋此事件。</span><span class="sxs-lookup"><span data-stu-id="739f5-184">You must enable SearchQueryInitiatedExchange to be logged so you can search for this event in the audit log.</span></span> <span data-ttu-id="739f5-185">如需指示，請參閱[設定進階稽核](set-up-advanced-audit.md#step-2-enable-crucial-events)。</span><span class="sxs-lookup"><span data-stu-id="739f5-185">For instructions, see [Set up Advanced Audit](set-up-advanced-audit.md#step-2-enable-crucial-events).</span></span>

### <a name="searchqueryinitiatedsharepoint"></a><span data-ttu-id="739f5-186">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="739f5-186">SearchQueryInitiatedSharePoint</span></span>

<span data-ttu-id="739f5-187">與搜尋信箱項目類似，當某人搜尋 SharePoint 中的項目時，就會觸發 SearchQueryInitiatedSharePoint 事件。</span><span class="sxs-lookup"><span data-stu-id="739f5-187">Similar to searching for mailbox items, the SearchQueryInitiatedSharePoint event is triggered when a person searches for items in SharePoint.</span></span> <span data-ttu-id="739f5-188">在下列 SharePoint 網站類型中執行搜尋時，會觸發事件：</span><span class="sxs-lookup"><span data-stu-id="739f5-188">Events are triggered when searches are performed in the following types of SharePoint sites:</span></span>

- <span data-ttu-id="739f5-189">主網站</span><span class="sxs-lookup"><span data-stu-id="739f5-189">Home sites</span></span>

- <span data-ttu-id="739f5-190">通訊網站</span><span class="sxs-lookup"><span data-stu-id="739f5-190">Communication sites</span></span>

- <span data-ttu-id="739f5-191">中樞網站</span><span class="sxs-lookup"><span data-stu-id="739f5-191">Hub sites</span></span>

- <span data-ttu-id="739f5-192">與 Microsoft Teams 相關聯的網站</span><span class="sxs-lookup"><span data-stu-id="739f5-192">Sites associated with Microsoft Teams</span></span>

<span data-ttu-id="739f5-193">調查人員可以使用 SearchQueryInitiatedSharePoint 事件來判斷攻擊者是否嘗試在 SharePoint 中尋找 (且可能存取) 敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="739f5-193">Investigators can use the SearchQueryInitiatedSharePoint event to determine if an attacker tried to find (and possibly accessed) sensitive information in SharePoint.</span></span> <span data-ttu-id="739f5-194">SearchQueryInitiatedSharePoint 事件的稽核記錄也包含實際的搜尋查詢文字。</span><span class="sxs-lookup"><span data-stu-id="739f5-194">The audit record for a SearchQueryInitiatedSharePoint event contains also contains the actual text of the search query.</span></span> <span data-ttu-id="739f5-195">稽核記錄也會指出已搜尋的 SharePoint 網站類型。</span><span class="sxs-lookup"><span data-stu-id="739f5-195">The audit record also indicates the type of SharePoint site that was searched.</span></span> <span data-ttu-id="739f5-196">透過查看攻擊者可能執行的搜尋查詢，調查人員可以更能瞭解欲搜尋的檔案資料意圖和範圍。</span><span class="sxs-lookup"><span data-stu-id="739f5-196">By looking at the search queries that an attacker may have performed, an investigator can better understand the intent and scope of the file data being searched for.</span></span>

<span data-ttu-id="739f5-197">若要搜尋 SearchQueryInitiatedSharePoint 稽核記錄，您可以在合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[搜尋活動]** 下拉式清單中搜尋 **[執行 SharePoint 搜尋]** 活動。</span><span class="sxs-lookup"><span data-stu-id="739f5-197">To search for SearchQueryInitiatedSharePoint audit records, you can search for the **Performed SharePoint search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在 [稽核記錄搜尋工具] 中搜尋 [執行 SharePoint 搜尋] 動作](../media/AdvAudit_SearchSharePoint.png)

<span data-ttu-id="739f5-199">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="739f5-199">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="739f5-200">您必須啟用要記錄的 SearchQueryInitiatedSharePoint，才能在稽核記錄中搜尋此事件。</span><span class="sxs-lookup"><span data-stu-id="739f5-200">You must enable SearchQueryInitiatedSharePoint to be logged so you can search for this event in the audit log.</span></span> <span data-ttu-id="739f5-201">如需指示，請參閱[設定進階稽核](set-up-advanced-audit.md#step-2-enable-crucial-events)。</span><span class="sxs-lookup"><span data-stu-id="739f5-201">For instructions, see [Set up Advanced Audit](set-up-advanced-audit.md#step-2-enable-crucial-events).</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="739f5-202">Office 365 管理活動 API 的高頻寬存取權</span><span class="sxs-lookup"><span data-stu-id="739f5-202">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="739f5-203">透過 Office 365 管理活動 API 存取稽核記錄的組織，其節流限制會處於發行者層級。</span><span class="sxs-lookup"><span data-stu-id="739f5-203">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level.</span></span> <span data-ttu-id="739f5-204">這表示，針對代表多個客戶提取資料的發行者，此限制會由所有客戶所共用。</span><span class="sxs-lookup"><span data-stu-id="739f5-204">This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="739f5-205">隨著進階稽核的推出，我們會將發行者層級限制移至租用戶層級限制。</span><span class="sxs-lookup"><span data-stu-id="739f5-205">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit.</span></span> <span data-ttu-id="739f5-206">結果是每個組織都會獲得自己完整配置的頻寬配額，以存取其稽核資料。</span><span class="sxs-lookup"><span data-stu-id="739f5-206">The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data.</span></span> <span data-ttu-id="739f5-207">頻寬不是靜態、預先定義的限制，但是會以一些要素的組合模組化，其中包括組織中的基座數量，而 E5/A5/G5 組織可獲得較非 E5/A5/G5 組織更多的頻寬。</span><span class="sxs-lookup"><span data-stu-id="739f5-207">The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5/A5/G5 organizations will get more bandwidth than non-E5/A5/G5 organizations.</span></span>

<span data-ttu-id="739f5-208">所有組織一開始都會配置每分鐘 2,000 個要求的基準。</span><span class="sxs-lookup"><span data-stu-id="739f5-208">All organizations are initially allocated a baseline of 2,000 requests per minute.</span></span> <span data-ttu-id="739f5-209">視組織的基座數和授權訂閱而定，此限制將會動態增加。</span><span class="sxs-lookup"><span data-stu-id="739f5-209">This limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="739f5-210">E5/A5/G5 組織可獲得的頻寬大約是非 E5/A5/G5 組織的兩倍。</span><span class="sxs-lookup"><span data-stu-id="739f5-210">E5/A5/G5 organizations will get about twice as much bandwidth as non-E5/A5/G5 organizations.</span></span> <span data-ttu-id="739f5-211">最大頻寬也會有上限，以保護服務的健康情況。</span><span class="sxs-lookup"><span data-stu-id="739f5-211">There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="739f5-212">如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)中的「API 節流」一節。</span><span class="sxs-lookup"><span data-stu-id="739f5-212">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>

## <a name="faqs-for-advanced-audit"></a><span data-ttu-id="739f5-213">進階稽核的常見問題集</span><span class="sxs-lookup"><span data-stu-id="739f5-213">FAQs for Advanced Audit</span></span>

<span data-ttu-id="739f5-214">**每位使用者都需要 E5/A5/G5 授權才能使用進階稽核嗎？**</span><span class="sxs-lookup"><span data-stu-id="739f5-214">**Does every user need an E5/A5/G5 license to benefit from Advanced Audit?**</span></span>

<span data-ttu-id="739f5-215">若要使用使用者層級的進階稽核功能，使用者必須獲派 E5/A5/G5 授權。</span><span class="sxs-lookup"><span data-stu-id="739f5-215">To benefit from user-level Advanced Audit capabilities, a user needs to be assigned an E5/A5/G5 license.</span></span> <span data-ttu-id="739f5-216">部分功能會檢查是否有適當授權，才會開放功能供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="739f5-216">There are some capabilities that will check for the appropriate license to expose the feature for the user.</span></span> <span data-ttu-id="739f5-217">例如，如果您正嘗試保留使用者的稽核記錄，但該使用者在 90 天內未獲派適當授權，則系統將會傳回錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="739f5-217">For example, if you're trying to retain the audit records for a user who isn't assigned the appropriate license for longer than 90 days, the system will return an error message.</span></span>

<span data-ttu-id="739f5-218">**我的組織擁有 E5/A5/G5 訂閱，我是否需要執行任何動作才能存取重要事件的稽核記錄？**</span><span class="sxs-lookup"><span data-stu-id="739f5-218">**My organization has an E5/A5/G5 subscription, do I need to do anything to get access to audit records for crucial events?**</span></span>

<span data-ttu-id="739f5-219">對於指派了適當授權的合格客戶和使用者，無需任何動作即可存取關鍵稽核事件。</span><span class="sxs-lookup"><span data-stu-id="739f5-219">For eligible customers and users that are assigned the appropriate license, there is no action to get access to crucial auditing events.</span></span>

<span data-ttu-id="739f5-220">**如果我建立 10 年稽核記錄保留原則時，此功能已發行至正式版本，但在所需的附加元件授權可使用之前，我組織的稽核記錄資料會產生什麼影響？**</span><span class="sxs-lookup"><span data-stu-id="739f5-220">**What happens to my organization's audit log data if I created a 10-year audit log retention policy when the feature was released to general availability but before the required add-on license was made available?**</span></span>

<span data-ttu-id="739f5-221">在此功能於 2020 年最後一季發行至正式版本之後，您建立的 10 年稽核記錄保留原則所涵蓋的任何稽核資料，都將保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="739f5-221">Any audit log data covered by a 10-year audit log retention policy that you created after the feature was released to general availability in the last quarter of 2020 will be retained for 10 years.</span></span> <span data-ttu-id="739f5-222">這包括在發行購買所需的附加元件授權之前所建立 10 年稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="739f5-222">This includes 10-yr audit log retention policies that were created before the required add-on license was released for purchase.</span></span> <span data-ttu-id="739f5-223">不過，由於現在可以使用 10 年稽核記錄保留附加元件授權，您將需要為 10 年稽核記錄保留原則所涵蓋之稽核資料的使用者購買並指派這些附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="739f5-223">However, since the 10-Year Audit Log Retention Add On license is now available, you'll need to purchase and assign those add-on licenses for any users whose audit data is covered by a 10-year audit retention policy.</span></span>

<span data-ttu-id="739f5-224">**Office 365 管理活動 API 的進階稽核中是否有新的事件？**</span><span class="sxs-lookup"><span data-stu-id="739f5-224">**Are the new events in Advanced Audit available in the Office 365 Management Activity API?**</span></span>

<span data-ttu-id="739f5-p126">是的。只要為具有適當授權的使用者產生稽核記錄，您就可以透過 Office 365 管理活動 API 存取這些記錄。</span><span class="sxs-lookup"><span data-stu-id="739f5-p126">Yes. As long as audit records are generated for users with the appropriate license, you'll be able to access these records via the Office 365 Management Activity API.</span></span>

<span data-ttu-id="739f5-227">**頻寬較高代表延遲較好或更高的 SLA 嗎？**</span><span class="sxs-lookup"><span data-stu-id="739f5-227">**Does higher bandwidth mean better latency or higher SLA?**</span></span>

<span data-ttu-id="739f5-228">目前，高頻寬可提供更好的管道，特別是具有大量稽核訊號和大量消費模式的組織。</span><span class="sxs-lookup"><span data-stu-id="739f5-228">At this time, high bandwidth provides a better pipeline, especially for organizations with a high volume of auditing signals and significant consumption patterns.</span></span> <span data-ttu-id="739f5-229">更多頻寬可以導致更好的延遲。</span><span class="sxs-lookup"><span data-stu-id="739f5-229">More bandwidth can lead to better latency.</span></span> <span data-ttu-id="739f5-230">不過 SLA 與高頻寬無關。</span><span class="sxs-lookup"><span data-stu-id="739f5-230">But there isn't an SLA associated with high bandwidth.</span></span> <span data-ttu-id="739f5-231">標準延遲已予以記錄，且這些延遲在進階稽核推出時不會變更。</span><span class="sxs-lookup"><span data-stu-id="739f5-231">Standard latencies are documented, and these latencies don't change with the release of Advanced Audit.</span></span>
