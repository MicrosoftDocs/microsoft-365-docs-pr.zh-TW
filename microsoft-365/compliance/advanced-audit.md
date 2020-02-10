---
title: Microsoft 365 中的進階稽核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Microsoft 365 中的「進階稽核」提供新的稽核功能，以協助貴組織進行鑑識與合規性調查。
ms.openlocfilehash: 49d2e2bbf7d1c19bb4c282920008a0ca9a34188d
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862383"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="d3aee-103">Microsoft 365 中的進階稽核</span><span class="sxs-lookup"><span data-stu-id="d3aee-103">Advanced audit in Microsoft 365</span></span>

<span data-ttu-id="d3aee-104">Microsoft 365 中的[整合式稽核功能](search-the-audit-log-in-security-and-compliance.md)，可讓組織深入了解 Microsoft 365 中多種不同服務的多個類型的稽核活動。</span><span class="sxs-lookup"><span data-stu-id="d3aee-104">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365.</span></span> <span data-ttu-id="d3aee-105">現在隨著 Microsoft 365 中進階稽核的推出，我們會加入新的稽核功能，以協助貴組織進行鑑識與合規性調查。</span><span class="sxs-lookup"><span data-stu-id="d3aee-105">Now with the release of Advanced audit in Microsoft 365, we're adding new auditing capabilities that can help your organization with forensic and compliance investigations.</span></span>

> [!NOTE]
> <span data-ttu-id="d3aee-106">進階稽核可供具有 Office 365 或 Microsoft 365 企業版 E5 訂閱的組織使用。</span><span class="sxs-lookup"><span data-stu-id="d3aee-106">Advanced audit is available for organizations with an Office 365 or Microsoft 365 Enterprise E5 subscription.</span></span> <span data-ttu-id="d3aee-107">此外，當「進階稽核」功能需要使用每位使用者授權時，您可以將 Microsoft 365 E5 合規性附加元件訂閱指派給使用者，針對稽核記錄和高價值稽核事件的長期保留也是如此。</span><span class="sxs-lookup"><span data-stu-id="d3aee-107">Additionally, a Microsoft 365 E5 Compliance add-on subscription can be assigned to users for when per-user licensing is required for Advanced audit features as is the case for long-term retention of audit logs and high-value audit events.</span></span>

<span data-ttu-id="d3aee-108">本文提供這些「進階稽核」功能的概觀。</span><span class="sxs-lookup"><span data-stu-id="d3aee-108">This article provides an overview of these Advanced audit capabilities.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="d3aee-109">長期保留稽核記錄</span><span class="sxs-lookup"><span data-stu-id="d3aee-109">Long-term retention of audit logs</span></span>

<span data-ttu-id="d3aee-110">「進階稽核」會保留所有 Exchange、SharePoint 和 Azure Active Directory 稽核記錄一年。</span><span class="sxs-lookup"><span data-stu-id="d3aee-110">Advanced audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="d3aee-111">這是透過預設的稽核記錄保留原則完成，它會保留包含 **Workload** 屬性 (這指出發生活動所在的服務) 的 **Exchange**、**SharePoint** 或 **AzureActiveDirectory** 的值的任何稽核記錄一年。</span><span class="sxs-lookup"><span data-stu-id="d3aee-111">This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year.</span></span> <span data-ttu-id="d3aee-112">這可協助進行持續的鑑識或合規性調查。</span><span class="sxs-lookup"><span data-stu-id="d3aee-112">This can help with on-going forensic or compliance investigations.</span></span> <span data-ttu-id="d3aee-113">如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md#default-audit-log-retention-policy)中的「預設稽核記錄保留原則」一節。</span><span class="sxs-lookup"><span data-stu-id="d3aee-113">For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

## <a name="audit-log-retention-policies"></a><span data-ttu-id="d3aee-114">稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="d3aee-114">Audit log retention policies</span></span>

<span data-ttu-id="d3aee-115">在其他服務中產生、未在預設稽核記錄保留原則涵蓋範圍的所有稽核記錄 (如前一節所述)，將會保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="d3aee-115">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days.</span></span> <span data-ttu-id="d3aee-116">不過，您現在可以建立自訂的稽核記錄保留原則，以保留其他稽核記錄最多達一年。</span><span class="sxs-lookup"><span data-stu-id="d3aee-116">However, now you can create customized audit log retention policies to retain other audit records for up to one year.</span></span> <span data-ttu-id="d3aee-117">您可以根據下列一或多項準則，建立用來保留稽核記錄的原則：</span><span class="sxs-lookup"><span data-stu-id="d3aee-117">You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="d3aee-118">稽核活動發生所在的 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="d3aee-118">The Microsoft 365 service where the audited activities occur</span></span>

- <span data-ttu-id="d3aee-119">特定已稽核活動</span><span class="sxs-lookup"><span data-stu-id="d3aee-119">Specific audited activities</span></span>

- <span data-ttu-id="d3aee-120">執行已稽核活動的使用者</span><span class="sxs-lookup"><span data-stu-id="d3aee-120">The user who performs an audited activity</span></span>

<span data-ttu-id="d3aee-121">您也可以指定要保留符合原則的稽核記錄的時間長度和優先順序層級，以便特定原則可優先於其他原則。</span><span class="sxs-lookup"><span data-stu-id="d3aee-121">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies.</span></span> <span data-ttu-id="d3aee-122">另請注意，如果您需要為組織中的部分或所有使用者保留 Exchange、SharePoint 或 Azure Active Directory 稽核記錄少於一年，任何自訂稽核記錄保留原則都會優先於預設的稽核保留原則。</span><span class="sxs-lookup"><span data-stu-id="d3aee-122">Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year for some or all the users in your organization.</span></span> <span data-ttu-id="d3aee-123">如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d3aee-123">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="high-value-audit-events"></a><span data-ttu-id="d3aee-124">高價值稽核活動</span><span class="sxs-lookup"><span data-stu-id="d3aee-124">High-value audit events</span></span>

<span data-ttu-id="d3aee-125">高價值安全性與合規性相關的稽核事件，可協助您調查可能的外洩或其他與鑑識相關的調查。</span><span class="sxs-lookup"><span data-stu-id="d3aee-125">High-value security- and compliance-related audit events are ones that can help you investigate possible breaches or other forensic-related investigations.</span></span> <span data-ttu-id="d3aee-126">我們要發佈的第一個這類高價值事件是 *MailItemsAccessed* 信箱稽核事件。</span><span class="sxs-lookup"><span data-stu-id="d3aee-126">The first such high-value event that we're releasing is the *MailItemsAccessed* mailbox auditing event.</span></span> <span data-ttu-id="d3aee-127">當郵件資料由郵件通訊協定和用戶端存取時，即會觸發此事件。</span><span class="sxs-lookup"><span data-stu-id="d3aee-127">This event is trigger when mail data is accessed by mail protocols and clients.</span></span> <span data-ttu-id="d3aee-128">MailItemsAccessed 事件可協助調查人員識別資料外洩，並判斷可能已遭入侵的郵件範圍。</span><span class="sxs-lookup"><span data-stu-id="d3aee-128">The MailItemsAccessed event can help investigators identify data breaches and determine the scope of messages that may have been compromised.</span></span> <span data-ttu-id="d3aee-129">如果攻擊者取得電子郵件訊息，即使沒有明確訊號指出已實際讀取 (也就是說，在稽核記錄中記錄了透過繫結或同步處理之類的存取類型)，也會觸發 MailItemsAccessed 事件。</span><span class="sxs-lookup"><span data-stu-id="d3aee-129">If an attacker gained access to email messages, MailItemsAccessed event will be triggered even if there is no explicit signal that it was actually read (in other words, the type of access such as via bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="d3aee-130">新的 MailItemsAccessed 信箱動作會取代 Exchange Online 中信箱稽核記錄的 MessageBind，並提供下列改善：</span><span class="sxs-lookup"><span data-stu-id="d3aee-130">The new MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="d3aee-131">MessageBind 僅可針對 AuditAdmin 使用者登入類型設定；不適用於代理人或擁有者動作。</span><span class="sxs-lookup"><span data-stu-id="d3aee-131">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions.</span></span> <span data-ttu-id="d3aee-132">MailItemsAccessed 適用於所有登入類型。</span><span class="sxs-lookup"><span data-stu-id="d3aee-132">MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="d3aee-133">MessageBind 僅涵蓋透過郵件用戶端的存取。</span><span class="sxs-lookup"><span data-stu-id="d3aee-133">MessageBind only covered access by a mail client.</span></span> <span data-ttu-id="d3aee-134">並不適用同步處理活動。</span><span class="sxs-lookup"><span data-stu-id="d3aee-134">It didn't apply to sync activities.</span></span> <span data-ttu-id="d3aee-135">MailItemsAccessed 事件會由繫結和同步處理存取類型觸發。</span><span class="sxs-lookup"><span data-stu-id="d3aee-135">MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="d3aee-136">當存取相同的電子郵件訊息時，MessageBind 動作會觸發多個稽核記錄，這會導致稽核的「雜訊」。</span><span class="sxs-lookup"><span data-stu-id="d3aee-136">MessageBind actions would trigger multiple audit records to be created when the same email message was accessed, which resulted in auditing "noise".</span></span> <span data-ttu-id="d3aee-137">相反地，MailItemsAccessed 事件會彙總在較少的稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="d3aee-137">In contrast, MailItemsAccessed events are aggregated in fewer audit records.</span></span>

<span data-ttu-id="d3aee-138">如需有關信箱稽核記錄的詳細資訊，請參閱[管理信箱稽核](enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="d3aee-138">For more information about mailbox auditing logging, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="d3aee-139">Office 365 管理活動 API 的高頻寬存取權</span><span class="sxs-lookup"><span data-stu-id="d3aee-139">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="d3aee-140">透過 Office 365 管理活動 API 存取稽核記錄的組織，其節流限制會處於發行者層級。</span><span class="sxs-lookup"><span data-stu-id="d3aee-140">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level.</span></span> <span data-ttu-id="d3aee-141">這表示，針對代表多個客戶提取資料的發行者，此限制會由所有客戶所共用。</span><span class="sxs-lookup"><span data-stu-id="d3aee-141">This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="d3aee-142">隨著進階稽核的推出，我們會將發行者層級限制移至租用戶層級限制。</span><span class="sxs-lookup"><span data-stu-id="d3aee-142">With the release of Advanced audit, we're moving from a publisher-level limit to a tenant-level limit.</span></span> <span data-ttu-id="d3aee-143">結果是每個組織都會獲得自己完整配置的頻寬配額，以存取其稽核資料。</span><span class="sxs-lookup"><span data-stu-id="d3aee-143">The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data.</span></span> <span data-ttu-id="d3aee-144">頻寬不是靜態、預先定義的限制，但是會以一些要素的組合模組化，其中包括組織中的基座數量，以及 E5 組織可獲得較非 E5 組織更多的頻寬。</span><span class="sxs-lookup"><span data-stu-id="d3aee-144">The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="d3aee-145">所有組織一開始都會配置每分鐘 2,000 個要求的基準。</span><span class="sxs-lookup"><span data-stu-id="d3aee-145">All organizations are initially allocated a baseline of 2,000 requests per minute.</span></span> <span data-ttu-id="d3aee-146">視組織的基座數和授權訂閱而定，此限制將會動態增加。</span><span class="sxs-lookup"><span data-stu-id="d3aee-146">This limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="d3aee-147">E5 組織可獲得的頻寬大約可達到非 E5 組織的兩倍。</span><span class="sxs-lookup"><span data-stu-id="d3aee-147">E5 organizations will get approximately twice as much bandwidth as non-E5 organizations.</span></span> <span data-ttu-id="d3aee-148">最大頻寬也會有上限，以保護服務的健康情況。</span><span class="sxs-lookup"><span data-stu-id="d3aee-148">There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="d3aee-149">如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)中的「API 節流」一節。</span><span class="sxs-lookup"><span data-stu-id="d3aee-149">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>
