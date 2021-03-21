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
ms.openlocfilehash: 0a77a5c54ce328a3966a952fc8fef08553f42462
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923483"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="1ecd1-103">Microsoft 365 中的進階稽核</span><span class="sxs-lookup"><span data-stu-id="1ecd1-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="1ecd1-104">Microsoft 365 中的[整合式稽核功能](search-the-audit-log-in-security-and-compliance.md)，可讓組織深入了解 Microsoft 365 中多種不同服務的多個類型的稽核活動。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-104">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365.</span></span> <span data-ttu-id="1ecd1-105">進階稽核經由增加進行調查時所需的稽核記錄保留，提供對有助於判斷危害範圍重要事件的存取，以及快速存取 Office 365 管理活動 API，來幫助組織進行鑑定及合規性調查。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-105">Advanced Audit helps organizations to conduct forensic and compliance investigations by increasing audit log retention required to conduct an investigation, providing access to crucial events that help determine scope of compromise, and faster access to Office 365 Management Activity API.</span></span>

> [!NOTE]
> <span data-ttu-id="1ecd1-106">進階稽核可供具有 Office 365 E5/G5 或 Microsoft 365 企業版 E5/G5 訂閱的組織使用。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-106">Advanced Audit is available for organizations with an Office 365 E5/G5 or Microsoft 365 Enterprise E5/G5 subscription.</span></span> <span data-ttu-id="1ecd1-107">此外，當進階稽核功能需要針對每位使用者進行授權時，您可以將 Microsoft 365 E5 合規性或 E5 電子文件探索和稽核附加元件授權指派給使用者，而針對稽核記錄和存取重要調查事件的長期保留也是如此。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-107">Additionally, a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license can be assigned to users when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations.</span></span> <span data-ttu-id="1ecd1-108">如需有關授權的詳細資訊，請參閱 [Microsoft 365 安全性與合規性的授權指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-108">For more information about licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).</span></span>

<span data-ttu-id="1ecd1-109">本文概述了 [進階稽核] 功能，並向您展示了如何為 [進階稽核] 設定使用者。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-109">This article provides an overview of Advanced Audit capabilities and shows you how to set up users for Advanced Audit.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="1ecd1-110">長期保留稽核記錄</span><span class="sxs-lookup"><span data-stu-id="1ecd1-110">Long-term retention of audit logs</span></span>

<span data-ttu-id="1ecd1-111">進階稽核會保留所有 Exchange、SharePoint 和 Azure Active Directory 稽核記錄，時間為一年。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-111">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="1ecd1-112">這是透過預設的稽核記錄保留原則完成，它會保留包含 **Workload** 屬性 (這指出發生活動所在的服務) 的 **Exchange**、**SharePoint** 或 **AzureActiveDirectory** 的值的任何稽核記錄一年。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-112">This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year.</span></span> <span data-ttu-id="1ecd1-113">保留稽核記錄的時間越長，可協助您進行深入的鑑定或合規性調查。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-113">Retaining audit records for longer periods can help with on-going forensic or compliance investigations.</span></span> <span data-ttu-id="1ecd1-114">如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md#default-audit-log-retention-policy)中的「預設稽核記錄保留原則」章節。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-114">For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

<span data-ttu-id="1ecd1-115">我們也會發佈將稽核記錄保留 10 年的功能。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-115">We're also releasing the capability to retain audit logs for 10 years.</span></span> <span data-ttu-id="1ecd1-116">將稽核記錄保留 10 年可協助支援長期的調查，並回應法規、法律和內部責任。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-116">The 10-year retention of audit logs helps support long running investigations and respond to regulatory, legal, and internal obligations.</span></span>

> [!NOTE]
> <span data-ttu-id="1ecd1-117">保留 10 年的稽核記錄會需要額外的附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-117">Retaining audit logs for 10 years will require an additional add-on license.</span></span> <span data-ttu-id="1ecd1-118">這個新的授權將於 2021 年初提供。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-118">This new license will be available in early 2021.</span></span> <span data-ttu-id="1ecd1-119">如需詳細資訊，請參閱本文中的[進階稽核常見問題集](#faqs-for-advanced-audit)章節。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-119">For more information, see the [FAQs for Advanced Audit](#faqs-for-advanced-audit) section in this article.</span></span>

### <a name="audit-log-retention-policies"></a><span data-ttu-id="1ecd1-120">稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="1ecd1-120">Audit log retention policies</span></span>

<span data-ttu-id="1ecd1-121">在其他服務中產生、未在預設稽核記錄保留原則涵蓋範圍的所有稽核記錄 (如前一節所述)，將會保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-121">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days.</span></span> <span data-ttu-id="1ecd1-122">不過，您可以建立自訂的稽核記錄保留原則，將其他稽核記錄保留更久的時間，最多可達 10 年。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-122">But you can create customized audit log retention policies to retain other audit records for longer periods of time up to 10 years.</span></span> <span data-ttu-id="1ecd1-123">您可以根據下列一或多項準則，建立用來保留稽核記錄的原則：</span><span class="sxs-lookup"><span data-stu-id="1ecd1-123">You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="1ecd1-124">發生已稽核活動的 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-124">The Microsoft 365 service where the audited activities occur.</span></span>

- <span data-ttu-id="1ecd1-125">特定已稽核活動。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-125">Specific audited activities.</span></span>

- <span data-ttu-id="1ecd1-126">執行已稽核活動的使用者。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-126">The user who performs an audited activity.</span></span>

<span data-ttu-id="1ecd1-127">您也可以指定要保留符合原則的稽核記錄的時間長度和優先順序層級，以便特定原則可優先於其他原則。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-127">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies.</span></span> <span data-ttu-id="1ecd1-128">另請注意，如果您需要為組織中的部分或所有使用者保留 Exchange、SharePoint 或 Azure Active Directory 稽核記錄少於一年 (或 10 年)，任何自訂稽核記錄保留原則都會優先於預設的稽核保留原則。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-128">Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year (or for 10 years) for some or all users in your organization.</span></span> <span data-ttu-id="1ecd1-129">如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-129">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="1ecd1-130">存取調查重要事件</span><span class="sxs-lookup"><span data-stu-id="1ecd1-130">Access to crucial events for investigations</span></span>

<span data-ttu-id="1ecd1-131">進階稽核經由提供對重要事件的存取 (例如何時存取郵件項目、何時回覆和轉寄郵件項目以及使用者何時 Exchange Online 和 SharePoint Online 中進行搜尋和搜尋哪些內容)，來幫助組織進行鑑定及合規性調查。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-131">Advanced Audit helps organizations to conduct forensic and compliance investigations by providing access to crucial events such as when mail items were accessed, or when mail items were replied to and forwarded, and when and what a user searched for in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="1ecd1-132">這些重要事件可協助您調查可能的破壞，並判斷危害的範圍。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-132">These crucial events can help you investigate possible breaches and determine the scope of compromise.</span></span>  <span data-ttu-id="1ecd1-133">[進階稽核] 提供下列重要事件：</span><span class="sxs-lookup"><span data-stu-id="1ecd1-133">Advanced Auditing provides the following crucial events:</span></span>

- [<span data-ttu-id="1ecd1-134">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="1ecd1-134">MailItemsAccessed</span></span>](#mailitemsaccessed)

- [<span data-ttu-id="1ecd1-135">Send</span><span class="sxs-lookup"><span data-stu-id="1ecd1-135">Send</span></span>](#send)

- [<span data-ttu-id="1ecd1-136">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="1ecd1-136">SearchQueryInitiatedExchange</span></span>](#searchqueryinitiatedexchange)

- [<span data-ttu-id="1ecd1-137">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="1ecd1-137">SearchQueryInitiatedSharePoint</span></span>](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a><span data-ttu-id="1ecd1-138">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="1ecd1-138">MailItemsAccessed</span></span>

<span data-ttu-id="1ecd1-139">MailItemsAccessed 事件是信箱稽核動作，當郵件資料受郵件通訊協定和郵件用戶端存取時，系統會觸發該事件。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-139">The MailItemsAccessed event is a mailbox auditing action and is triggered when mail data is accessed by mail protocols and mail clients.</span></span> <span data-ttu-id="1ecd1-140">MailItemsAccessed 動作可幫助調查人員識別資料外洩，並判斷可能已遭入侵的郵件範圍。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-140">The MailItemsAccessed action can help investigators identify data breaches and determine the scope of messages that may have been compromised.</span></span> <span data-ttu-id="1ecd1-141">如果攻擊者取得電子郵件訊息，即使沒有明確訊號指出已實際讀取郵件 (也就是說，在稽核記錄中記錄了透過繫結或同步處理之類的存取類型)，將會觸發 MailItemsAccessed 動作。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-141">If an attacker gained access to email messages, the MailItemsAccessed action will be triggered even if there is no explicit signal that messages were actually read (in other words, the type of access such as a bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="1ecd1-142">MailItemsAccessed 信箱動作會取代 Exchange Online 中信箱稽核記錄的 MessageBind，並提供下列改善：</span><span class="sxs-lookup"><span data-stu-id="1ecd1-142">The MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="1ecd1-143">MessageBind 僅可針對 AuditAdmin 使用者登入類型設定；不適用於代理人或擁有者動作。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-143">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions.</span></span> <span data-ttu-id="1ecd1-144">MailItemsAccessed 適用於所有登入類型。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-144">MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="1ecd1-145">MessageBind 僅涵蓋透過郵件用戶端的存取。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-145">MessageBind only covered access by a mail client.</span></span> <span data-ttu-id="1ecd1-146">並不適用同步處理活動。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-146">It didn't apply to sync activities.</span></span> <span data-ttu-id="1ecd1-147">MailItemsAccessed 事件會由繫結和同步處理存取類型觸發。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-147">MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="1ecd1-148">當存取相同的電子郵件訊息時，MessageBind 動作會觸發多個稽核記錄的建立，這會導致稽核的「雜訊」。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-148">MessageBind actions would trigger the creation of multiple audit records when the same email message was accessed, which resulted in auditing "noise".</span></span> <span data-ttu-id="1ecd1-149">相反地，MailItemsAccessed 事件會彙總在較少的稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-149">In contrast, MailItemsAccessed events are aggregated into fewer audit records.</span></span>

<span data-ttu-id="1ecd1-150">如需有關 MailItemsAccessed 活動的稽核記錄資訊，請參閱[使用進階稽核調查遭入侵帳戶](mailitemsaccessed-forensics-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-150">For information about audit records for MailItemsAccessed activities, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>

<span data-ttu-id="1ecd1-151">若要搜尋 MailItemsAccessed 稽核記錄，您可以在 Microsoft 365 合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[Exchange 信箱活動]** 下拉式清單中搜尋 **[已存取的信箱項目]** 活動。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-151">To search for MailItemsAccessed audit records, you can search for the **Accessed mailbox items** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在稽核記錄搜尋工具中搜尋 MailItemsAccessed 動作](../media/AdvAudit_MailItemsAccessed.png)

<span data-ttu-id="1ecd1-153">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-153">You can also run the [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="send"></a><span data-ttu-id="1ecd1-154">傳送</span><span class="sxs-lookup"><span data-stu-id="1ecd1-154">Send</span></span>

<span data-ttu-id="1ecd1-155">Send 事件也是信箱審核動作，當使用者執行下列其中一項動作時，會觸發該事件：</span><span class="sxs-lookup"><span data-stu-id="1ecd1-155">The Send event is also a mailbox auditing action and is triggered when a user performs one of the following actions:</span></span>

- <span data-ttu-id="1ecd1-156">傳送電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="1ecd1-156">Sends an email message</span></span>

- <span data-ttu-id="1ecd1-157">回覆電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="1ecd1-157">Replies to an email message</span></span>

- <span data-ttu-id="1ecd1-158">轉寄電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="1ecd1-158">Forwards an email message</span></span>

<span data-ttu-id="1ecd1-159">調查人員可以使用 Send 事件識別從遭入侵帳戶發送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-159">Investigators can use the Send event to identify email sent from a compromised account.</span></span> <span data-ttu-id="1ecd1-160">Send 事件的稽核記錄中包含郵件的相關資訊，例如郵件傳送的時間、InternetMessage 識別碼、主旨列，以及郵件是否包含附件。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-160">The audit record for a Send event contains information about the message, such as when the message was sent, the InternetMessage ID, the subject line, and if the message contained attachments.</span></span> <span data-ttu-id="1ecd1-161">這項稽核資訊可協助調查人員識別從遭入侵帳戶或攻擊者傳送的電子郵件訊息相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-161">This auditing information can help investigators identify information about email messages sent from a compromised account or sent by an attacker.</span></span> <span data-ttu-id="1ecd1-162">此外，調查人員可以使用 Microsoft 365 或電子文件探索工具來搜尋郵件 (使用主旨列或郵件識別碼)，以找出傳送郵件的收件者，以及傳送郵件的實際內容。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-162">Additionally, investigators can use a Microsoft 365 eDiscovery tool to search for the message (by using the subject line or message ID) to identify the recipients the message was sent to and the actual contents of the sent message.</span></span>

<span data-ttu-id="1ecd1-163">若要搜尋 Send 稽核記錄，您可以在 Microsoft 365 合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[Exchange 信箱活動]** 下拉式清單中搜尋 **[傳送電子郵件]** 活動。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-163">To search for Send audit records, you can search for the **Sent message** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在 [稽核記錄搜尋工具] 中搜尋 [傳送電子郵件] 動作](../media/AdvAudit_SentMessage.png)

<span data-ttu-id="1ecd1-165">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-165">You can also run the [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="searchqueryinitiatedexchange"></a><span data-ttu-id="1ecd1-166">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="1ecd1-166">SearchQueryInitiatedExchange</span></span>

<span data-ttu-id="1ecd1-167">當某人使用 Outlook 在信箱中搜尋項目時，就會觸發 SearchQueryInitiatedExchange 事件。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-167">The SearchQueryInitiatedExchange event is triggered when a person uses Outlook to search for items in a mailbox.</span></span> <span data-ttu-id="1ecd1-168">在下列 Outlook 環境中執行搜尋時，會觸發事件：</span><span class="sxs-lookup"><span data-stu-id="1ecd1-168">Events are triggered when searches are performed in the following Outlook environments:</span></span>

- <span data-ttu-id="1ecd1-169">Outlook (桌面用戶端)</span><span class="sxs-lookup"><span data-stu-id="1ecd1-169">Outlook (desktop client)</span></span>

- <span data-ttu-id="1ecd1-170">Outlook 網頁版 (OWA)</span><span class="sxs-lookup"><span data-stu-id="1ecd1-170">Outlook on the web (OWA)</span></span>

- <span data-ttu-id="1ecd1-171">iOS 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="1ecd1-171">Outlook for iOS</span></span>

- <span data-ttu-id="1ecd1-172">Android 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="1ecd1-172">Outlook for Android</span></span>

- <span data-ttu-id="1ecd1-173">Windows 10 版郵件應用程式</span><span class="sxs-lookup"><span data-stu-id="1ecd1-173">Mail app for Windows 10</span></span>

<span data-ttu-id="1ecd1-174">調查人員可以使用 SearchQueryInitiatedExchange 事件，來判斷可能有遭入侵帳號的攻擊者是否已查看或嘗試存取信箱中的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-174">Investigators can use the SearchQueryInitiatedExchange event to determine if an attacker who may have compromised an account looked for or tried to access sensitive information in the mailbox.</span></span> <span data-ttu-id="1ecd1-175">SearchQueryInitiatedExchange 事件的稽核記錄包含實際的搜尋查詢文字。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-175">The audit record for a SearchQueryInitiatedExchange event contains information such as the actual text of the search query.</span></span> <span data-ttu-id="1ecd1-176">稽核記錄也會指出搜尋執行時所用的 Outlook 環境。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-176">The audit record also indicates the Outlook environment the search was performed in.</span></span> <span data-ttu-id="1ecd1-177">透過查看攻擊者可能執行的搜尋查詢，調查人員可以更能瞭解搜尋的電子郵件資料意圖。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-177">By looking at the search queries that an attacker may have performed, an investigator can better understand the intent of the email data that was searched for.</span></span>

<span data-ttu-id="1ecd1-178">若要搜尋 SearchQueryInitiatedExchange 稽核記錄，您可以在合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[搜尋活動]** 下拉式清單中搜尋 **[執行電子郵件搜尋]** 活動。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-178">To search for SearchQueryInitiatedExchange audit records, you can search for the **Performed email search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在 [稽核記錄搜尋工具] 中搜尋 [執行電子郵件搜尋] 動作](../media/AdvAudit_SearchExchange.png)

<span data-ttu-id="1ecd1-180">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-180">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="1ecd1-p116">您必須在 Exchange Online PowerShell 中執行下列命令，以便在稽核記錄搜尋結果中包含 SearchQueryInitiatedExchange 事件 (由指定的 E5 使用者執行)：`Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-p116">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedExchange events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`. </span></span><br/><br/>
<span data-ttu-id="1ecd1-182">在多地理位置環境中，您必須在使用者信箱所在的樹系中執行 **Set-Mailbox** 命令。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-182">In a multi-geo environment, you must run the **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="1ecd1-183">若要識別使用者的信箱位置，請執行下列命令：`Get-Mailbox <user identity> | FL MailboxLocations`。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-183">To identify the user's mailbox location, run the following command: `Get-Mailbox <user identity> | FL MailboxLocations`.</span></span>
<span data-ttu-id="1ecd1-184">如果 `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` 命令之前曾在與使用者信箱所在位置不同的樹系中執行，則您必須從使用者的信箱移除 SearchQueryInitiated 值 (透過執行 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`)，然後將該命令新增至使用者信箱所在位置樹系中的使用者信箱中。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-184">If the `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` command was previously run in the forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox (by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`) and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

### <a name="searchqueryinitiatedsharepoint"></a><span data-ttu-id="1ecd1-185">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="1ecd1-185">SearchQueryInitiatedSharePoint</span></span>

<span data-ttu-id="1ecd1-186">與搜尋信箱項目類似，當某人搜尋 SharePoint 中的項目時，就會觸發 SearchQueryInitiatedSharePoint 事件。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-186">Similar to searching for mailbox items, the SearchQueryInitiatedSharePoint event is triggered when a person searches for items in SharePoint.</span></span> <span data-ttu-id="1ecd1-187">在下列 SharePoint 網站類型中執行搜尋時，會觸發事件：</span><span class="sxs-lookup"><span data-stu-id="1ecd1-187">Events are triggered when searches are performed in the following types of SharePoint sites:</span></span>

- <span data-ttu-id="1ecd1-188">主網站</span><span class="sxs-lookup"><span data-stu-id="1ecd1-188">Home sites</span></span>

- <span data-ttu-id="1ecd1-189">通訊網站</span><span class="sxs-lookup"><span data-stu-id="1ecd1-189">Communication sites</span></span>

- <span data-ttu-id="1ecd1-190">中樞網站</span><span class="sxs-lookup"><span data-stu-id="1ecd1-190">Hub sites</span></span>

- <span data-ttu-id="1ecd1-191">與 Microsoft Teams 相關聯的網站</span><span class="sxs-lookup"><span data-stu-id="1ecd1-191">Sites associated with Microsoft Teams</span></span>

<span data-ttu-id="1ecd1-192">調查人員可以使用 SearchQueryInitiatedSharePoint 事件來判斷攻擊者是否嘗試在 SharePoint 中尋找 (且可能存取) 敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-192">Investigators can use the SearchQueryInitiatedSharePoint event to determine if an attacker tried to find (and possibly accessed) sensitive information in SharePoint.</span></span> <span data-ttu-id="1ecd1-193">SearchQueryInitiatedSharePoint 事件的稽核記錄也包含實際的搜尋查詢文字。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-193">The audit record for a SearchQueryInitiatedSharePoint event contains also contains the actual text of the search query.</span></span> <span data-ttu-id="1ecd1-194">稽核記錄也會指出已搜尋的 SharePoint 網站類型。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-194">The audit record also indicates the type of SharePoint site that was searched.</span></span> <span data-ttu-id="1ecd1-195">透過查看攻擊者可能執行的搜尋查詢，調查人員可以更能瞭解欲搜尋的檔案資料意圖和範圍。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-195">By looking at the search queries that an attacker may have performed, an investigator can better understand the intent and scope of the file data being searched for.</span></span>

<span data-ttu-id="1ecd1-196">若要搜尋 SearchQueryInitiatedSharePoint 稽核記錄，您可以在合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[搜尋活動]** 下拉式清單中搜尋 **[執行 SharePoint 搜尋]** 活動。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-196">To search for SearchQueryInitiatedSharePoint audit records, you can search for the **Performed SharePoint search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在 [稽核記錄搜尋工具] 中搜尋 [執行 SharePoint 搜尋] 動作](../media/AdvAudit_SearchSharePoint.png)

<span data-ttu-id="1ecd1-198">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-198">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="1ecd1-p120">您必須在 Exchange Online PowerShell 中執行下列命令，以便在稽核記錄搜尋結果中包含 SearchQueryInitiatedExchange 事件 (由指定的 E5 使用者執行)：`Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-p120">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedExchange events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`. </span></span><br/><br/>
<span data-ttu-id="1ecd1-200">在多地理位置環境中，您必須在使用者信箱所在的樹系中執行 **Set-Mailbox** 命令。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-200">In a multi-geo environment, you must run the **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="1ecd1-201">若要識別使用者的信箱位置，請執行下列命令：`Get-Mailbox <user identity> | FL MailboxLocations`。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-201">To identify the user's mailbox location, run the following command: `Get-Mailbox <user identity> | FL MailboxLocations`.</span></span>
<span data-ttu-id="1ecd1-202">如果 `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` 命令之前曾在與使用者信箱所在位置不同的樹系中執行，則您必須從使用者的信箱移除 SearchQueryInitiated 值 (透過執行 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`)，然後將該命令新增至使用者信箱所在位置樹系中的使用者信箱中。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-202">If the `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` command was previously run in the forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox (by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`) and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="1ecd1-203">Office 365 管理活動 API 的高頻寬存取權</span><span class="sxs-lookup"><span data-stu-id="1ecd1-203">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="1ecd1-204">透過 Office 365 管理活動 API 存取稽核記錄的組織，其節流限制會處於發行者層級。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-204">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level.</span></span> <span data-ttu-id="1ecd1-205">這表示，針對代表多個客戶提取資料的發行者，此限制會由所有客戶所共用。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-205">This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="1ecd1-206">隨著進階稽核的推出，我們會將發行者層級限制移至租用戶層級限制。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-206">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit.</span></span> <span data-ttu-id="1ecd1-207">結果是每個組織都會獲得自己完整配置的頻寬配額，以存取其稽核資料。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-207">The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data.</span></span> <span data-ttu-id="1ecd1-208">頻寬不是靜態、預先定義的限制，但是會以一些要素的組合模組化，其中包括組織中的基座數量，以及 E5 組織可獲得較非 E5 組織更多的頻寬。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-208">The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="1ecd1-209">所有組織一開始都會配置每分鐘 2,000 個要求的基準。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-209">All organizations are initially allocated a baseline of 2,000 requests per minute.</span></span> <span data-ttu-id="1ecd1-210">視組織的基座數和授權訂閱而定，此限制將會動態增加。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-210">This limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="1ecd1-211">E5 組織可獲得的頻寬大約可達到非 E5 組織的兩倍。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-211">E5 organizations will get about twice as much bandwidth as non-E5 organizations.</span></span> <span data-ttu-id="1ecd1-212">最大頻寬也會有上限，以保護服務的健康情況。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-212">There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="1ecd1-213">如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)中的「API 節流」一節。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-213">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>

## <a name="set-up-advanced-audit-for-users"></a><span data-ttu-id="1ecd1-214">為使用者設置進階稽核</span><span class="sxs-lookup"><span data-stu-id="1ecd1-214">Set up Advanced Audit for users</span></span>

<span data-ttu-id="1ecd1-215">進階稽核功能，如記錄重要事件 (如 MailItemsAccessed 和 Send) 功能，需要為使用者指派適當的 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-215">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="1ecd1-216">此外，必須為這些使用者啟用 [進階稽核] 應用程式/服務方案。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-216">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="1ecd1-217">要驗證 [進階稽核] 應用程式是否已指派給使用者，請對每個使用者執行以下步驟：</span><span class="sxs-lookup"><span data-stu-id="1ecd1-217">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="1ecd1-218">在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/Adminportal)中，移至 **[使用者]** > **[作用中的使用者]**，然後選取使用者。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-218">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="1ecd1-219">在 [使用者內容] 飛出頁面上，按一下 **[授權和應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-219">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="1ecd1-220">在 **[授權]** 區段，驗證是否為使用者指派了 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-220">In the **Licenses** section, verify that the user is assigned an E5 license.</span></span>

4. <span data-ttu-id="1ecd1-221">展開 **[應用程式]** 區段，並驗證是否選中了 **[Microsoft 365 進階稽核]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-221">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="1ecd1-222">如果沒有選取該核取方塊，請選取它，然後按一下 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-222">If the checkbox isn’t selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="1ecd1-223">將在 24 小時內開始記錄使用者的 MailItemsAccessed、Send 和其他重要事件的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-223">The logging of audit records for MailItemsAccessed, Send, and other crucial events for the user will begin within 24 hours.</span></span>

<span data-ttu-id="1ecd1-224">針對使用以群組為基礎授權之指派授權至使用者群組的組織，請務必關閉該群組的 Microsoft 365 進階稽核授權指派。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-224">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="1ecd1-225">儲存變更之後，請確認已關閉群組的 Microsoft 365 進階稽核。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-225">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="1ecd1-226">然後重新開啟群組的授權指派。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-226">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="1ecd1-227">如需以群組為基礎授權的相關指示，請參閱[在 Azure Active Directory 中以群組成員資格指派授權給使用者](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-227">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="1ecd1-228">此外，如果您已自訂登入到使用者郵箱或共用郵箱的郵箱動作，則不會在這些郵箱上自動稽核新的預設郵箱動作 (如 MailItemsAccessed)。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-228">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, new default mailbox actions such as MailItemsAccessed will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="1ecd1-229">有關變更為每個登入類型稽核的郵箱動作之資訊，請參閱[管理郵箱稽核](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)中的 [變更或還原預設記錄的郵箱動作] 一節。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-229">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="faqs-for-advanced-audit"></a><span data-ttu-id="1ecd1-230">進階稽核的常見問題集</span><span class="sxs-lookup"><span data-stu-id="1ecd1-230">FAQs for Advanced Audit</span></span>

<span data-ttu-id="1ecd1-231">**每位使用者是否需要 E5 授權才能使用進階稽核？**</span><span class="sxs-lookup"><span data-stu-id="1ecd1-231">**Does every user need an E5 license to benefit from Advanced Audit?**</span></span>

<span data-ttu-id="1ecd1-232">若要使用使用者層級的進階稽核功能，使用者必須獲指派 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-232">To benefit from user-level Advanced Audit capabilities, a user needs to be assigned an E5 license.</span></span> <span data-ttu-id="1ecd1-233">部分功能會檢查是否有適當授權，才會開放功能供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-233">There are some capabilities that will check for the appropriate license to expose the feature for the user.</span></span> <span data-ttu-id="1ecd1-234">例如，如果您正嘗試保留使用者的稽核記錄，但該使用者在 90 天內未獲指派 E5 授權，系統將會傳回錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-234">For example, if you're trying to retain the audit records for a user who isn't assigned an E5 license for longer than 90 days, the system will return an error message.</span></span>

<span data-ttu-id="1ecd1-235">**我的組織擁有 E5 訂閱，我是否需要執行任何動作才能存取重要事件的稽核記錄？**</span><span class="sxs-lookup"><span data-stu-id="1ecd1-235">**My organization has an E5 subscription, do I need to do anything to get access to audit records for crucial events?**</span></span>

<span data-ttu-id="1ecd1-236">對於指派了適當授權的合格客戶和使用者，無需任何動作即可存取關鍵稽核事件。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-236">For eligible customers and users that are assigned the appropriate license, there is no action to get access to crucial auditing events.</span></span>

<span data-ttu-id="1ecd1-237">**何時提供新的 10 年稽核記錄保留附加元件授權？**</span><span class="sxs-lookup"><span data-stu-id="1ecd1-237">**When will the new 10-year audit log retention add-on license be available?**</span></span>

<span data-ttu-id="1ecd1-238">新的 10 年稽核記錄保留附加元件將提供給具有 E5 訂閱的客戶購買。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-238">The new 10-year audit log retention add-on is now available for purchase by customers with E5 subscriptions.</span></span>

<span data-ttu-id="1ecd1-239">**如果我建立 10 年稽核記錄保留原則時，此功能已發行至正式版本，但在 2021 年 2 月所需的附加元件授權可使用之前，我組織的稽核記錄資料會產生什麼影響？**</span><span class="sxs-lookup"><span data-stu-id="1ecd1-239">**What happens to my organization's audit log data if I created a 10-year audit log retention policy when the feature was released to general availability but before the required add-on license was made available in February 2021?**</span></span>

<span data-ttu-id="1ecd1-240">您在正式發行之後建立的 10 年稽核記錄保留原則所涵蓋的所有稽核資料，都將保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-240">Any audit log data covered by a 10-year audit log retention policy that you created after general availability will be retained for 10 years.</span></span> <span data-ttu-id="1ecd1-241">當 2021 年初 10 年稽核記錄保留附加元件授權可用時，您將需要為使用現有 10 年稽核記錄保留原則保留稽核資料的使用者購買附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-241">When the 10-year audit log retention add-on license is available in early 2021, you will need to purchase add-on licenses for users who's audit data is being retained by an existing 10-year audit retention policy.</span></span>

<span data-ttu-id="1ecd1-242">**Office 365 管理活動 API 的進階稽核中是否有新的事件？**</span><span class="sxs-lookup"><span data-stu-id="1ecd1-242">**Are the new events in Advanced Audit available in the Office 365 Management Activity API?**</span></span>

<span data-ttu-id="1ecd1-243">是。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-243">Yes.</span></span> <span data-ttu-id="1ecd1-244">只要為具有適當授權的使用者產生稽核記錄，您就可以透過 Office 365 管理活動 API 存取這些記錄。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-244">As long as audit records are generated for users with the appropriate license, you'll be able to access these records via the Office 365 Management Activity API.</span></span>

<span data-ttu-id="1ecd1-245">**頻寬較高代表延遲較好或更高的 SLA 嗎？**</span><span class="sxs-lookup"><span data-stu-id="1ecd1-245">**Does higher bandwidth mean better latency or higher SLA?**</span></span>

<span data-ttu-id="1ecd1-246">目前，高頻寬可提供更好的管道，特別是具有大量稽核訊號和大量消費模式的組織。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-246">At this time, high bandwidth provides a better pipeline, especially for organizations with a high volume of auditing signals and significant consumption patterns.</span></span> <span data-ttu-id="1ecd1-247">更多頻寬可以導致更好的延遲。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-247">More bandwidth can lead to better latency.</span></span> <span data-ttu-id="1ecd1-248">不過 SLA 與高頻寬無關。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-248">But there isn't an SLA associated with high bandwidth.</span></span> <span data-ttu-id="1ecd1-249">標準延遲已予以記錄，且這些延遲在進階稽核推出時不會變更。</span><span class="sxs-lookup"><span data-stu-id="1ecd1-249">Standard latencies are documented, and these latencies don't change with the release of Advanced Audit.</span></span>