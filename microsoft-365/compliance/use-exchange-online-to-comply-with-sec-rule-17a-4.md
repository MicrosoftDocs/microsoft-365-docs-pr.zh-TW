---
title: 使用 Exchange Online 和安全性與合規性中心以符合 SEC Rule 17a-4
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 設定 Exchange Online 和合規性中心，以協助符合 CFTC 規則1.31 (c)-(d)、FINRA 規則4511及 SEC 規則 17a-4 要求。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6dc53ec9dd016a2423ca96886bba400e2f17e17a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819073"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="db77f-103">使用 Exchange Online 和安全性與合規性中心以符合 SEC Rule 17a-4</span><span class="sxs-lookup"><span data-stu-id="db77f-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="db77f-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="db77f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="db77f-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="db77f-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span></span> <span data-ttu-id="db77f-106">This includes the ability to retain, audit, search, and export your data.</span><span class="sxs-lookup"><span data-stu-id="db77f-106">This includes the ability to retain, audit, search, and export your data.</span></span> <span data-ttu-id="db77f-107">These capabilities are sufficient to meet the needs of most organizations.</span><span class="sxs-lookup"><span data-stu-id="db77f-107">These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="db77f-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span><span class="sxs-lookup"><span data-stu-id="db77f-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span></span> <span data-ttu-id="db77f-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span><span class="sxs-lookup"><span data-stu-id="db77f-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span></span> <span data-ttu-id="db77f-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span><span class="sxs-lookup"><span data-stu-id="db77f-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="db77f-111">為協助組織更了解如何運用安全性與合規性中心來符合其 Exchange Online 法規義務 (具體而言是與 Rule 17a-4 要求有關)，我們已與 Cohasset Associates 合作發佈評估。</span><span class="sxs-lookup"><span data-stu-id="db77f-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="db77f-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span><span class="sxs-lookup"><span data-stu-id="db77f-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span></span> <span data-ttu-id="db77f-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span><span class="sxs-lookup"><span data-stu-id="db77f-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="db77f-114">下載 Cohasset 評估</span><span class="sxs-lookup"><span data-stu-id="db77f-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="db77f-115">您可以[在這裡下載 Cohasset 評估](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)。</span><span class="sxs-lookup"><span data-stu-id="db77f-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Cohasset Associates 的可下載評估標題頁面](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="db77f-117">這項評估是針對 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="db77f-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="db77f-118">Note that this assessment is specific to Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="db77f-118">Note that this assessment is specific to Exchange Online.</span></span> <span data-ttu-id="db77f-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span><span class="sxs-lookup"><span data-stu-id="db77f-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="db77f-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="db77f-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span></span> <span data-ttu-id="db77f-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span><span class="sxs-lookup"><span data-stu-id="db77f-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="db77f-122">使用保留鎖定是建議設定的關鍵</span><span class="sxs-lookup"><span data-stu-id="db77f-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="db77f-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span><span class="sxs-lookup"><span data-stu-id="db77f-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span></span> <span data-ttu-id="db77f-124">The WORM requirement dictates a storage solution in which a record must be:</span><span class="sxs-lookup"><span data-stu-id="db77f-124">The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="db77f-125">保留一段要求的保留期間，該期間無法縮短，只能增加。</span><span class="sxs-lookup"><span data-stu-id="db77f-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="db77f-126">固定，也就是說，在要求的保留期間內，記錄無法覆寫、清除或變更。</span><span class="sxs-lookup"><span data-stu-id="db77f-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="db77f-127">In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span><span class="sxs-lookup"><span data-stu-id="db77f-127">In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span></span> <span data-ttu-id="db77f-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span><span class="sxs-lookup"><span data-stu-id="db77f-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span></span> <span data-ttu-id="db77f-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span><span class="sxs-lookup"><span data-stu-id="db77f-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="db77f-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span><span class="sxs-lookup"><span data-stu-id="db77f-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span></span> <span data-ttu-id="db77f-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span><span class="sxs-lookup"><span data-stu-id="db77f-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="db77f-132">原則的保留期間只能增加，無法縮短。</span><span class="sxs-lookup"><span data-stu-id="db77f-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="db77f-133">可將使用者新增到原則中，但無法移除任何使用者。</span><span class="sxs-lookup"><span data-stu-id="db77f-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="db77f-134">系統管理員無法刪除保留原則。</span><span class="sxs-lookup"><span data-stu-id="db77f-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="db77f-135">保留鎖定可協助您符合 SEC 17a-4 法規要求。</span><span class="sxs-lookup"><span data-stu-id="db77f-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="db77f-136">如何設定保留鎖定</span><span class="sxs-lookup"><span data-stu-id="db77f-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="db77f-137">您可以使用 PowerShell 鎖定保留原則。</span><span class="sxs-lookup"><span data-stu-id="db77f-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="db77f-138">如需詳細資訊，請參閱[使用保留鎖定以符合法規需求](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)。</span><span class="sxs-lookup"><span data-stu-id="db77f-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="db77f-139">已知限制</span><span class="sxs-lookup"><span data-stu-id="db77f-139">Known limitations</span></span>

<span data-ttu-id="db77f-140">目前，Exchange Online 存在一些限制：</span><span class="sxs-lookup"><span data-stu-id="db77f-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="db77f-141">無法在 Teams 聊天和頻道訊息中使用通訊對話。</span><span class="sxs-lookup"><span data-stu-id="db77f-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="db77f-142">無法保留 Teams 聊天和頻道訊息中的讚。</span><span class="sxs-lookup"><span data-stu-id="db77f-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="db77f-143">項目層級稽核現在可供 Microsoft 365 群組信箱使用。</span><span class="sxs-lookup"><span data-stu-id="db77f-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="db77f-144">如需詳細資訊，請參閱[管理信箱稽核](enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="db77f-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
