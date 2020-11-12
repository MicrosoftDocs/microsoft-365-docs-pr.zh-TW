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
ms.openlocfilehash: bd7b4f78d37feddd7c66322460a6532a77045ba2
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988665"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="517c5-103">Microsoft 365 中的進階稽核</span><span class="sxs-lookup"><span data-stu-id="517c5-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="517c5-p101">Microsoft 365 中的[整合式稽核功能](search-the-audit-log-in-security-and-compliance.md)，可讓組織深入了解 Microsoft 365 中多種不同服務的多個類型的稽核活動。進階稽核經由增加進行調查時所需的稽核記錄保留，提供對有助於判斷危害範圍重要事件的存取，以及快速存取 Office 365 管理活動 API，來幫助組織進行鑑定及合規性調查。</span><span class="sxs-lookup"><span data-stu-id="517c5-p101">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365. Advanced Audit helps organizations to conduct forensic and compliance investigations by increasing audit log retention required to conduct an investigation, providing access to crucial events that help determine scope of compromise, and faster access to Office 365 Management Activity API.</span></span>

> [!NOTE]
> <span data-ttu-id="517c5-p102">進階稽核可供具有 Office 365 E5/G5 或 Microsoft 365 企業版 E5/G5 訂閱的組織使用。此外，當進階稽核功能需要針對每位使用者進行授權時，您可以將 Microsoft 365 E5 合規性或 E5 電子文件探索和稽核附加元件授權指派給使用者，而針對稽核記錄和存取重要調查事件的長期保留也是如此。如需有關授權的詳細資訊，請參閱 [Microsoft 365 安全性與合規性的授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)。</span><span class="sxs-lookup"><span data-stu-id="517c5-p102">Advanced Audit is available for organizations with an Office 365 E5/G5 or Microsoft 365 Enterprise E5/G5 subscription. Additionally, a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license can be assigned to users when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations. For more information about licensing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).</span></span>

<span data-ttu-id="517c5-109">本文提供進階稽核功能的概觀。</span><span class="sxs-lookup"><span data-stu-id="517c5-109">This article provides an overview of Advanced Audit capabilities.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="517c5-110">長期保留稽核記錄</span><span class="sxs-lookup"><span data-stu-id="517c5-110">Long-term retention of audit logs</span></span>

<span data-ttu-id="517c5-p103">進階稽核會保留所有 Exchange、SharePoint 和 Azure Active Directory 稽核記錄，時間為一年。這是透過預設的稽核記錄保留原則完成，它會保留包含 **Workload** 屬性 (這指出發生活動所在的服務) 的 **Exchange** 、 **SharePoint** 或 **AzureActiveDirectory** 的值的任何稽核記錄一年。保留稽核記錄的時間越長，可協助您進行深入的鑑定或合規性調查。有關更多資訊，請在 [管理稽核記錄保留原則](audit-log-retention-policies.md#default-audit-log-retention-policy) 中查看「預設稽核記錄保留原則 一節。</span><span class="sxs-lookup"><span data-stu-id="517c5-p103">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year. This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange** , **SharePoint** , or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year. Retaining audit records for longer periods can help with on-going forensic or compliance investigations. For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

<span data-ttu-id="517c5-p104">我們也會發佈將稽核記錄保留 10 年的功能。保留 10 年的稽核記錄有助於支援長期執行的調查，並應對法規、法律和內部責任。</span><span class="sxs-lookup"><span data-stu-id="517c5-p104">We're also releasing the capability to retain audit logs for 10 years. The 10-year retention of audit logs helps support long running investigations and respond to regulatory, legal, and internal obligations.</span></span>

> [!NOTE]
> <span data-ttu-id="517c5-p105">保留 10 年的稽核記錄會需要額外的附加元件授權。這個新的授權將於 2021 年初提供。如需詳細資訊，請參閱本文中的[進階稽核常見問題集](#faqs-for-advanced-audit)章節。</span><span class="sxs-lookup"><span data-stu-id="517c5-p105">Retaining audit logs for 10 years will require an additional add-on license. This new license will be available in early 2021. For more information, see the [FAQs for Advanced Audit](#faqs-for-advanced-audit) section in this article.</span></span>

### <a name="audit-log-retention-policies"></a><span data-ttu-id="517c5-120">稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="517c5-120">Audit log retention policies</span></span>

<span data-ttu-id="517c5-p106">在其他服務中產生、未在預設稽核記錄保留原則涵蓋範圍的所有稽核記錄 (如前一節所述)，將會保留 90 天。不過，您可以建立自訂的稽核記錄保留原則，將其他稽核記錄保留更久的時間，最多可達 10 年。您可以根據下列一或多項準則，建立用來保留稽核記錄的原則：</span><span class="sxs-lookup"><span data-stu-id="517c5-p106">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days. But you can create customized audit log retention policies to retain other audit records for longer periods of time up to 10 years. You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="517c5-124">發生已稽核活動的 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="517c5-124">The Microsoft 365 service where the audited activities occur.</span></span>

- <span data-ttu-id="517c5-125">特定已稽核活動。</span><span class="sxs-lookup"><span data-stu-id="517c5-125">Specific audited activities.</span></span>

- <span data-ttu-id="517c5-126">執行已稽核活動的使用者。</span><span class="sxs-lookup"><span data-stu-id="517c5-126">The user who performs an audited activity.</span></span>

<span data-ttu-id="517c5-p107">您也可以指定要保留符合原則的稽核記錄的時間長度和優先順序層級，以便特定原則可優先於其他原則。另請注意，如果您需要為組織中的部分或所有使用者保留 Exchange、SharePoint 或 Azure Active Directory 稽核記錄少於一年 (或 10 年)，任何自訂稽核記錄保留原則都會優先於預設的稽核保留原則。如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="517c5-p107">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies. Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year (or for 10 years) for some or all users in your organization. For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="517c5-130">存取調查重要事件</span><span class="sxs-lookup"><span data-stu-id="517c5-130">Access to crucial events for investigations</span></span>

<span data-ttu-id="517c5-p108">進階稽核經由提供對重要事件的存取 (例如何時存取郵件項目、何時回覆和轉寄郵件項目以及使用者何時 Exchange Online 和 SharePoint Online 中進行搜尋和搜尋哪些內容)，來幫助組織進行鑑定及合規性調查。這些重要事件可協助您調查可能的破壞，並判斷危害的範圍。[進階稽核] 提供下列重要事件：</span><span class="sxs-lookup"><span data-stu-id="517c5-p108">Advanced Audit helps organizations to conduct forensic and compliance investigations by providing access to crucial events such as when mail items were accessed, or when mail items were replied to and forwarded, and when and what a user searched for in Exchange Online and SharePoint Online. These crucial events can help you investigate possible breaches and determine the scope of compromise.  Advanced Auditing provides the following crucial events:</span></span>

- [<span data-ttu-id="517c5-134">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="517c5-134">MailItemsAccessed</span></span>](#mailitemsaccessed)

- [<span data-ttu-id="517c5-135">Send</span><span class="sxs-lookup"><span data-stu-id="517c5-135">Send</span></span>](#send)

- [<span data-ttu-id="517c5-136">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="517c5-136">SearchQueryInitiatedExchange</span></span>](#searchqueryinitiatedexchange)

- [<span data-ttu-id="517c5-137">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="517c5-137">SearchQueryInitiatedSharePoint</span></span>](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a><span data-ttu-id="517c5-138">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="517c5-138">MailItemsAccessed</span></span>

<span data-ttu-id="517c5-p109">MailItemsAccessed 事件是信箱稽核動作，當郵件資料受郵件通訊協定和郵件用戶端存取時，系統會觸發該事件。MailItemsAccessed 動作可幫助調查人員識別資料外洩，並判斷可能已遭入侵的郵件範圍。如果攻擊者取得電子郵件訊息，即使沒有明確訊號指出已實際讀取郵件 (也就是說，在稽核記錄中記錄了透過繫結或同步處理之類的存取類型)，將會觸發 MailItemsAccessed 動作。</span><span class="sxs-lookup"><span data-stu-id="517c5-p109">The MailItemsAccessed event is a mailbox auditing action and is triggered when mail data is accessed by mail protocols and mail clients. The MailItemsAccessed action can help investigators identify data breaches and determine the scope of messages that may have been compromised. If an attacker gained access to email messages, the MailItemsAccessed action will be triggered even if there is no explicit signal that messages were actually read (in other words, the type of access such as a bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="517c5-142">MailItemsAccessed 信箱動作會取代 Exchange Online 中信箱稽核記錄的 MessageBind，並提供下列改善：</span><span class="sxs-lookup"><span data-stu-id="517c5-142">The MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="517c5-p110">MessageBind 僅適用于 AuditAdmin 使用者登入類型；不適用於代理人或擁有者動作。MailItemsAccessed 適用於所有登入類型。</span><span class="sxs-lookup"><span data-stu-id="517c5-p110">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions. MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="517c5-p111">MessageBind 僅涵蓋透過郵件用戶端的存取。並不適用同步處理活動。MailItemsAccessed 事件會由繫結和同步處理存取類型觸發。</span><span class="sxs-lookup"><span data-stu-id="517c5-p111">MessageBind only covered access by a mail client. It didn't apply to sync activities. MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="517c5-p112">當存取相同的電子郵件訊息時，MessageBind 動作會觸發多個稽核記錄的建立，這會導致稽核的「雜訊」。相反地，MailItemsAccessed 事件會彙總在較少的稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="517c5-p112">MessageBind actions would trigger the creation of multiple audit records when the same email message was accessed, which resulted in auditing "noise". In contrast, MailItemsAccessed events are aggregated into fewer audit records.</span></span>

<span data-ttu-id="517c5-150">如需有關 MailItemsAccessed 活動的稽核記錄資訊，請參閱[使用進階稽核調查遭入侵帳戶](mailitemsaccessed-forensics-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="517c5-150">For information about audit records for MailItemsAccessed activities, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>

<span data-ttu-id="517c5-151">若要搜尋 MailItemsAccessed 稽核記錄，您可以在 Microsoft 365 合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[Exchange 信箱活動]** 下拉式清單中搜尋 **[已存取的信箱項目]** 活動。</span><span class="sxs-lookup"><span data-stu-id="517c5-151">To search for MailItemsAccessed audit records, you can search for the **Accessed mailbox items** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在稽核記錄搜尋工具中搜尋 MailItemsAccessed 動作](../media/AdvAudit_MailItemsAccessed.png)

<span data-ttu-id="517c5-153">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="517c5-153">You can also run the [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="send"></a><span data-ttu-id="517c5-154">傳送</span><span class="sxs-lookup"><span data-stu-id="517c5-154">Send</span></span>

<span data-ttu-id="517c5-155">Send 事件也是信箱審核動作，當使用者執行下列其中一項動作時，會觸發該事件：</span><span class="sxs-lookup"><span data-stu-id="517c5-155">The Send event is also a mailbox auditing action and is triggered when a user performs one of the following actions:</span></span>

- <span data-ttu-id="517c5-156">傳送電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="517c5-156">Sends an email message</span></span>

- <span data-ttu-id="517c5-157">回覆電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="517c5-157">Replies to an email message</span></span>

- <span data-ttu-id="517c5-158">轉寄電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="517c5-158">Forwards an email message</span></span>

<span data-ttu-id="517c5-p113">調查人員可以使用 Send 事件識別從遭入侵帳戶發送的電子郵件。Send 事件的稽核記錄中包含郵件的相關資訊，例如郵件傳送的時間、InternetMessage 識別碼、主旨列，以及郵件是否包含附件。這項稽核資訊可協助調查人員識別從遭入侵帳戶或攻擊者傳送的電子郵件訊息相關資訊。此外，調查人員可以使用 Microsoft 365 或電子文件探索工具來搜尋郵件 (使用主旨列或郵件識別碼)，以找出傳送郵件的收件者，以及傳送郵件的實際內容。</span><span class="sxs-lookup"><span data-stu-id="517c5-p113">Investigators can use the Send event to identify email sent from a compromised account. The audit record for a Send event contains information about the message, such as when the message was sent, the InternetMessage ID, the subject line, and if the message contained attachments. This auditing information can help investigators identify information about email messages sent from a compromised account or sent by an attacker. Additionally, investigators can use a Microsoft 365 eDiscovery tool to search for the message (by using the subject line or message ID) to identify the recipients the message was sent to and the actual contents of the sent message.</span></span>

<span data-ttu-id="517c5-163">若要搜尋 Send 稽核記錄，您可以在 Microsoft 365 合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[Exchange 信箱活動]** 下拉式清單中搜尋 **[傳送電子郵件]** 活動。</span><span class="sxs-lookup"><span data-stu-id="517c5-163">To search for Send audit records, you can search for the **Sent message** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在 [稽核記錄搜尋工具] 中搜尋 [傳送電子郵件] 動作](../media/AdvAudit_SentMessage.png)

<span data-ttu-id="517c5-165">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="517c5-165">You can also run the [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="searchqueryinitiatedexchange"></a><span data-ttu-id="517c5-166">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="517c5-166">SearchQueryInitiatedExchange</span></span>

<span data-ttu-id="517c5-p114">當某人在 Outlook 網頁版 (OWA) 中使用 [搜尋列] 來搜尋信箱中的項目時，就會觸發 SearchQueryInitiatedExchange 事件。調查人員可以使用 SearchQueryInitiatedExchange 事件，來判斷可能已入侵帳號的攻擊者是否已查看或嘗試存取信箱中的敏感性資訊。SearchQueryInitiatedExchange 事件的稽核記錄包含實際的搜尋查詢文字。透過查看攻擊者可能執行的搜尋查詢，調查人員可以更能瞭解搜尋的電子郵件資料意圖。</span><span class="sxs-lookup"><span data-stu-id="517c5-p114">The SearchQueryInitiatedExchange event is triggered when a person uses the Search bar in Outlook on the web (OWA) to search for items in a mailbox. Investigators can use the SearchQueryInitiatedExchange event to determine if an attacker who may have compromised an account looked for or tried to access sensitive information in the mailbox. The audit record for a SearchQueryInitiatedExchange event contains information such as the actual text of the search query. By looking at the search queries that an attacker may have performed, an investigator can better understand the intent of the email data that was searched for.</span></span>

<span data-ttu-id="517c5-171">若要搜尋 SearchQueryInitiatedExchange 稽核記錄，您可以在合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[搜尋活動]** 下拉式清單中搜尋 **[執行電子郵件搜尋]** 活動。</span><span class="sxs-lookup"><span data-stu-id="517c5-171">To search for SearchQueryInitiatedExchange audit records, you can search for the **Performed email search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在 [稽核記錄搜尋工具] 中搜尋 [執行電子郵件搜尋] 動作](../media/AdvAudit_SearchExchange.png)

<span data-ttu-id="517c5-173">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="517c5-173">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="517c5-174">您必須在 Exchange Online PowerShell 中執行下列命令，以便在稽核記錄搜尋結果中包含 SearchQueryInitiatedExchange 事件 (由指定的 E5 使用者執行)：`Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="517c5-174">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedExchange events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.</span></span>

### <a name="searchqueryinitiatedsharepoint"></a><span data-ttu-id="517c5-175">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="517c5-175">SearchQueryInitiatedSharePoint</span></span>

<span data-ttu-id="517c5-p115">與搜尋信箱項目類似，當某人搜尋貴組織中 SharePoint 主網站中的項目時，就會觸發 SearchQueryInitiatedSharePoint 事件。調查人員可以使用 SearchQueryInitiatedSharePoint 事件來判斷攻擊者是否嘗試在 SharePoint 中尋找 (且可能存取) 敏感性資訊。SearchQueryInitiatedSharePoint 事件的稽核記錄也包含實際的搜尋查詢文字。透過查看攻擊者可能已執行的搜尋查詢，調查人員可以更能了解他們搜尋檔案資料的意圖和範圍。</span><span class="sxs-lookup"><span data-stu-id="517c5-p115">Similar to searching for mailbox items, the SearchQueryInitiatedSharePoint event is triggered when a person searches for items in the SharePoint home site for your organization. Investigators can use the SearchQueryInitiatedSharePoint event to determine if an attacker tried to find (and possibly accessed) sensitive information in SharePoint. The audit record for a SearchQueryInitiatedSharePoint event contains also contains the actual text of the search query. By looking at the search queries that an attacker may have performed, an investigator can better understand the intent and scope of the file data being searched for.</span></span>

<span data-ttu-id="517c5-180">若要搜尋 SearchQueryInitiatedSharePoint 稽核記錄，您可以在合規性中心的 [稽核記錄搜尋工具](search-the-audit-log-in-security-and-compliance.md)中，在 **[搜尋活動]** 下拉式清單中搜尋 **[執行 SharePoint 搜尋]** 活動。</span><span class="sxs-lookup"><span data-stu-id="517c5-180">To search for SearchQueryInitiatedSharePoint audit records, you can search for the **Performed SharePoint search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在 [稽核記錄搜尋工具] 中搜尋 [執行 SharePoint 搜尋] 動作](../media/AdvAudit_SearchSharePoint.png)

<span data-ttu-id="517c5-182">您也可以在 Exchange Online PowerShell 中執行 [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="517c5-182">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="517c5-183">您必須在 Exchange Online PowerShell 中執行下列命令，以便在稽核記錄搜尋結果中包含 SearchQueryInitiatedSharePoint 事件 (由指定的 E5 使用者執行)：`Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="517c5-183">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedSharePoint events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="517c5-184">Office 365 管理活動 API 的高頻寬存取權</span><span class="sxs-lookup"><span data-stu-id="517c5-184">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="517c5-p116">透過 Office 365 管理活動 API 存取稽核記錄的組織，其節流限制會處於發行者層級。這表示，針對代表多個客戶提取資料的發行者，此限制會由所有客戶所共用。</span><span class="sxs-lookup"><span data-stu-id="517c5-p116">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level. This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="517c5-p117">隨著進階稽核的推出，我們會將發行者層級限制移至租用戶層級限制。結果是每個組織都會獲得自己完整配置的頻寬配額，以存取其稽核資料。頻寬不是靜態、預先定義的限制，但是會以一些要素的組合模組化，其中包括組織中的基座數量，以及 E5 組織可獲得較非 E5 組織更多的頻寬。</span><span class="sxs-lookup"><span data-stu-id="517c5-p117">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit. The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data. The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="517c5-p118">所有組織一開始都會配置每分鐘 2,000 個要求的基準。視組織的基座數和授權訂閱而定，此限制將會動態增加。E5 組織可獲得的頻寬大約可達到非 E5 組織的兩倍。最大頻寬也會有上限，以保護服務的健康情況。</span><span class="sxs-lookup"><span data-stu-id="517c5-p118">All organizations are initially allocated a baseline of 2,000 requests per minute. This limit will dynamically increase depending on an organization's seat count and their licensing subscription. E5 organizations will get about twice as much bandwidth as non-E5 organizations. There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="517c5-194">如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)中的「API 節流」一節。</span><span class="sxs-lookup"><span data-stu-id="517c5-194">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>

## <a name="faqs-for-advanced-audit"></a><span data-ttu-id="517c5-195">進階稽核的常見問題集</span><span class="sxs-lookup"><span data-stu-id="517c5-195">FAQs for Advanced Audit</span></span>

<span data-ttu-id="517c5-196">**每位使用者是否需要 E5 授權才能使用進階稽核？**</span><span class="sxs-lookup"><span data-stu-id="517c5-196">**Does every user need an E5 license to benefit from Advanced Audit?**</span></span>

<span data-ttu-id="517c5-p119">若要使用使用者層級的進階稽核功能，使用者必須獲指派 E5 授權。部分功能會檢查是否有適當授權，才會開放功能供使用者使用。例如，如果您正嘗試保留使用者的稽核記錄，但該使用者在 90 天內未獲指派 E5 授權，系統將會傳回錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="517c5-p119">To benefit from user-level Advanced Audit capabilities, a user needs to be assigned an E5 license. There are some capabilities that will check for the appropriate license to expose the feature for the user. For example, if you're trying to retain the audit records for a user who isn't assigned an E5 license for longer than 90 days, the system will return an error message.</span></span>

<span data-ttu-id="517c5-200">**我的組織擁有 E5 訂閱，我是否需要執行任何動作才能存取重要事件的稽核記錄？**</span><span class="sxs-lookup"><span data-stu-id="517c5-200">**My organization has an E5 subscription, do I need to do anything to get access to audit records for crucial events?**</span></span>

<span data-ttu-id="517c5-201">對於指派了適當授權的合格客戶和使用者，無需任何動作即可存取關鍵稽核事件。</span><span class="sxs-lookup"><span data-stu-id="517c5-201">For eligible customers and users that are assigned the appropriate license, there is no action to get access to crucial auditing events.</span></span>

<span data-ttu-id="517c5-202">**何時提供新的 10 年稽核記錄保留附加元件授權？**</span><span class="sxs-lookup"><span data-stu-id="517c5-202">**When will the new 10-year audit log retention add-on license be available?**</span></span>

<span data-ttu-id="517c5-203">新的 10 年稽核記錄保留附加元件將於 2021 年初提供給 E5 訂閱的客戶購買。</span><span class="sxs-lookup"><span data-stu-id="517c5-203">The new 10-year audit log retention add-on will be available for purchase by customers with E5 subscriptions in early 2021.</span></span>

<span data-ttu-id="517c5-204">**如果我建立了 10 年稽核記錄保留原則，此功能已發發布至正式版本，但在 2021 年初所需的附加元件授權可使用之前，系統會對我組織的稽核記錄資料產生什麼影響？**</span><span class="sxs-lookup"><span data-stu-id="517c5-204">**What happens to my organization's audit log data if I create 10-year audit log retention policy the feature is released to general availability but before the required add-on license is available in early 2021?**</span></span>

<span data-ttu-id="517c5-205">您在正式發行之後建立的 10 年稽核記錄保留原則所涵蓋的所有稽核資料，都將保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="517c5-205">Any audit log data covered by a 10-year audit log retention policy that you create after general availability will be retained for 10 years.</span></span> <span data-ttu-id="517c5-206">當 2021 年初 10 年稽核記錄保留附加元件授權可用時，您將需要為使用現有 10 年稽核記錄保留原則保留稽核資料的使用者購買附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="517c5-206">When the 10-year audit log retention add-on license is available in early 2021, you will need to purchase add-on licenses for users who's audit data is being retained by an existing 10-year audit retention policy.</span></span> <span data-ttu-id="517c5-207">此外，只要 2021 年初附加元件授權可用時，當您建立新的 10 年稽核紀錄保留原則時，系統就會強制執行適當的授權。</span><span class="sxs-lookup"><span data-stu-id="517c5-207">Also, once the add-on license is available in early 2021, the appropriate licensing will be enforced when you create new 10-year audit log retention policies.</span></span>

<span data-ttu-id="517c5-208">**Office 365 管理活動 API 的進階稽核中是否有新的事件？**</span><span class="sxs-lookup"><span data-stu-id="517c5-208">**Are the new events in Advanced Audit available in the Office 365 Management Activity API?**</span></span>

<span data-ttu-id="517c5-209">是。</span><span class="sxs-lookup"><span data-stu-id="517c5-209">Yes.</span></span> <span data-ttu-id="517c5-210">只要為具有適當授權的使用者產生稽核記錄，您就可以透過 Office 365 管理活動 API 存取這些記錄。</span><span class="sxs-lookup"><span data-stu-id="517c5-210">As long as audit records are generated for users with the appropriate license, you'll be able to access these records via the Office 365 Management Activity API.</span></span>

<span data-ttu-id="517c5-211">**頻寬較高代表延遲較好或更高的 SLA 嗎？**</span><span class="sxs-lookup"><span data-stu-id="517c5-211">**Does higher bandwidth mean better latency or higher SLA?**</span></span>

<span data-ttu-id="517c5-212">目前，高頻寬可提供更好的管道，特別是具有大量稽核訊號和大量消費模式的組織。</span><span class="sxs-lookup"><span data-stu-id="517c5-212">At this time, high bandwidth provides a better pipeline, especially for organizations with a high volume of auditing signals and significant consumption patterns.</span></span> <span data-ttu-id="517c5-213">更多頻寬可以導致更好的延遲。</span><span class="sxs-lookup"><span data-stu-id="517c5-213">More bandwidth can lead to better latency.</span></span> <span data-ttu-id="517c5-214">不過 SLA 與高頻寬無關。</span><span class="sxs-lookup"><span data-stu-id="517c5-214">But there isn't an SLA associated with high bandwidth.</span></span> <span data-ttu-id="517c5-215">標準延遲已予以記錄，且這些延遲在進階稽核推出時不會變更。</span><span class="sxs-lookup"><span data-stu-id="517c5-215">Standard latencies are documented, and these latencies don't change with the release of Advanced Audit.</span></span>
