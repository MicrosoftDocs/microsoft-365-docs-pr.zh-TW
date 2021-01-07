---
title: Microsoft 365 中優先順序帳戶的安全性建議
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何提升安全性設定，以及如何在 Microsoft 365 組織中提升優先順序帳戶的安全性設定，以及使用報表、警示和調查。
ms.openlocfilehash: 9788131ea881a1cb3c36a60dfaac01ed5daf0901
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769242"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a><span data-ttu-id="240dd-103">Microsoft 365 中優先順序帳戶的安全性建議</span><span class="sxs-lookup"><span data-stu-id="240dd-103">Security recommendations for priority accounts in Microsoft 365</span></span>

<span data-ttu-id="240dd-104">如果您從組織中要求您執行某項緊急的電子郵件，您該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="240dd-104">What would you do if you received an urgent message from an executive in your organization that asked you to do something?</span></span> <span data-ttu-id="240dd-105">您會這麼做嗎？</span><span class="sxs-lookup"><span data-stu-id="240dd-105">Would you do it?</span></span> <span data-ttu-id="240dd-106">大多數人員會遵守要求。</span><span class="sxs-lookup"><span data-stu-id="240dd-106">Most people would comply with the request.</span></span>

<span data-ttu-id="240dd-107">針對攻擊者，強制轉換隨機網路以取得隨機或未知使用者之認證的一般網路釣魚攻擊是低效的。</span><span class="sxs-lookup"><span data-stu-id="240dd-107">For attackers, ordinary phishing attacks that cast a random net to get the credentials of random or unknown users are inefficient.</span></span> <span data-ttu-id="240dd-108">另一方面， _spear 網路釣魚_ 或 _whaling_ 攻擊，其可讓使用者在電源或授權的位置受到攻擊，對攻擊者而言會有更大的回報。</span><span class="sxs-lookup"><span data-stu-id="240dd-108">On the other hand, _spear phishing_ or _whaling_ attacks that target users in positions of power or authority are much more rewarding for attackers.</span></span> <span data-ttu-id="240dd-109">如果這些優先順序帳戶遭到損害，攻擊者可能會利用組織內的系統管理員、財務、產品甚至實體存取能力，取得帳戶的存取權。</span><span class="sxs-lookup"><span data-stu-id="240dd-109">If these priority accounts are compromised, the attacker might gain access to accounts with admin, financial, product, or even physical access capabilities within the organization.</span></span>

<span data-ttu-id="240dd-110">Microsoft 365 和 Microsoft Defender for Office 365 包含許多不同的功能，可協助您為優先順序帳戶提供額外的安全性層級。</span><span class="sxs-lookup"><span data-stu-id="240dd-110">Microsoft 365 and Microsoft Defender for Office 365 contain many different features that can help you to provided additional layers of security for your priority accounts.</span></span> <span data-ttu-id="240dd-111">本文將討論可用的功能及其用法。</span><span class="sxs-lookup"><span data-stu-id="240dd-111">The available features and how to use them are discussed in this article.</span></span>

![圖示表單中安全性建議的摘要](../../media/security-recommendations-for-priority-users.png)

## <a name="increase-sign-in-security-for-priority-accounts"></a><span data-ttu-id="240dd-113">增加優先順序帳戶的登入安全性</span><span class="sxs-lookup"><span data-stu-id="240dd-113">Increase sign-in security for priority accounts</span></span>

<span data-ttu-id="240dd-114">優先順序帳戶需要增加的登入安全性。</span><span class="sxs-lookup"><span data-stu-id="240dd-114">Priority accounts require increased sign-in security.</span></span> <span data-ttu-id="240dd-115">您可以要求多重要素驗證 (MFA) 並停用舊版驗證通訊協定，以提升其登入安全性。</span><span class="sxs-lookup"><span data-stu-id="240dd-115">You can increase their sign-in security by requiring multi-factor authentication (MFA) and disabling legacy authentication protocols.</span></span>

<span data-ttu-id="240dd-116">如需相關指示，請參閱 [步驟1。增加具有 MFA 的遠端工作者的登入安全性](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in)。</span><span class="sxs-lookup"><span data-stu-id="240dd-116">For instructions, see [Step 1. Increase sign-in security for remote workers with MFA](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in).</span></span> <span data-ttu-id="240dd-117">雖然本文是有關遠端工作者的資訊，但相同的概念也適用于優先順序使用者。</span><span class="sxs-lookup"><span data-stu-id="240dd-117">Although this article is about remote workers, the same concepts apply to priority users.</span></span>

<span data-ttu-id="240dd-118">**附註**：</span><span class="sxs-lookup"><span data-stu-id="240dd-118">**Notes**:</span></span>

- <span data-ttu-id="240dd-119">在 exchange Online 中，exchange Web 服務 (EWS) 、Exchange ActiveSync、POP3、IMAP4 和遠端 PowerShell 中已被取代的基本驗證。</span><span class="sxs-lookup"><span data-stu-id="240dd-119">Basic authentication is in the process of being deprecated in Exchange Online for Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4, and remote PowerShell.</span></span> <span data-ttu-id="240dd-120">如需詳細資訊，請參閱此 [博客文章](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。</span><span class="sxs-lookup"><span data-stu-id="240dd-120">For details, see this [blog post](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).</span></span>

- <span data-ttu-id="240dd-121">您可以使用 Exchange Online 中的 [驗證原則](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) 和 [用戶端存取規則](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) ，封鎖基本驗證和舊版驗證通訊協定，例如 POP3、IMAP4 和驗證的 SMTP。</span><span class="sxs-lookup"><span data-stu-id="240dd-121">You can use [authentication policies](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) and [Client Access Rules](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online to block Basic authentication and legacy authentication protocols like POP3, IMAP4, and authenticated SMTP.</span></span>

- <span data-ttu-id="240dd-122">您可以停用個別信箱上的 POP3 和 IMAP4 存取權。</span><span class="sxs-lookup"><span data-stu-id="240dd-122">You can disable POP3 and IMAP4 access on individual mailboxes.</span></span> <span data-ttu-id="240dd-123">您可以在組織層級停用已驗證的 SMTP，並在仍需要該 SMTP 的特定信箱上啟用該 SMTP。</span><span class="sxs-lookup"><span data-stu-id="240dd-123">You can disable authenticated SMTP at the organizational level and enable it on specific mailboxes that still require it.</span></span> <span data-ttu-id="240dd-124">如需相關指示，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="240dd-124">For instructions, see the following topics:</span></span>
  - [<span data-ttu-id="240dd-125">啟用或停用使用者 POP3 或 IMAP4 存取權</span><span class="sxs-lookup"><span data-stu-id="240dd-125">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [<span data-ttu-id="240dd-126">啟用或停用已驗證的用戶端 SMTP 提交 (SMTP 驗證) </span><span class="sxs-lookup"><span data-stu-id="240dd-126">Enable or disable authenticated client SMTP submission (SMTP AUTH)</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a><span data-ttu-id="240dd-127">對優先順序帳戶使用嚴格的預先設定安全性原則</span><span class="sxs-lookup"><span data-stu-id="240dd-127">Use Strict preset security policies for priority accounts</span></span>

<span data-ttu-id="240dd-128">優先順序使用者需要更嚴格的動作，以用於 Exchange Online Protection (EOP) 和 Defender for Office 365 中提供的各種保護。</span><span class="sxs-lookup"><span data-stu-id="240dd-128">Priority users require more stringent actions for the various protections that are available in Exchange Online Protection (EOP) and Defender for Office 365.</span></span>

<span data-ttu-id="240dd-129">例如，若要將歸類為垃圾郵件的郵件傳送至 [垃圾郵件] 資料夾，您應該隔離這些相同的郵件（如果它們是用於優先順序帳戶）。</span><span class="sxs-lookup"><span data-stu-id="240dd-129">For example, instead of delivering messages that were classified as spam to the Junk Email folder, you should quarantine those same messages if they're intended for priority accounts.</span></span>

<span data-ttu-id="240dd-130">您可以使用預先設定的安全性原則中的 Strict 設定檔，為優先順序帳戶執行此嚴格的方法。</span><span class="sxs-lookup"><span data-stu-id="240dd-130">You can implement this stringent approach for priority accounts by using the Strict profile in preset security policies.</span></span>

<span data-ttu-id="240dd-131">「預設」安全性原則是一個方便且集中的位置，可將建議的嚴格原則設定套用至 EOP 和 Defender for Office 365 中的所有保護。</span><span class="sxs-lookup"><span data-stu-id="240dd-131">Preset security policies are a convenient and central location to apply our recommended Strict policy settings for all of the protections in EOP and Defender for Office 365.</span></span> <span data-ttu-id="240dd-132">如需詳細資訊，請參閱 [EOP 和 Microsoft Defender For Office 365 中的預先設定安全性原則](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="240dd-132">For more information, see [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).</span></span>

<span data-ttu-id="240dd-133">如需嚴格原則設定與預設和標準原則設定的區別之詳細資訊，請參閱 [EOP 和 Microsoft Defender For Office 365 security 的建議設定](recommended-settings-for-eop-and-office365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="240dd-133">For details about how the Strict policy settings differ from the the default and Standard policy settings, see [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="apply-user-tags-to-priority-accounts"></a><span data-ttu-id="240dd-134">將使用者標記套用至優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="240dd-134">Apply user tags to priority accounts</span></span>

<span data-ttu-id="240dd-135">Microsoft Defender for Office 365 方案 2 (中的使用者標記是 Microsoft 365 E5 或附加元件訂閱) 中的一種方法，可快速識別及分類報告和事件調查中的特定使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="240dd-135">User tags in Microsoft Defender for Office 365 Plan 2 (as part of Microsoft 365 E5 or an add-on subscription) are a way to quickly identify and classify specific users or groups of users in reports and incident investigations.</span></span>

<span data-ttu-id="240dd-136">「**優先順序帳戶**」是一種內建的使用者標記， (稱為 _系統_ 標籤) ，可供您用來識別涉及優先順序帳戶的事件及警示。</span><span class="sxs-lookup"><span data-stu-id="240dd-136">**Priority accounts** is a type of built-in user tag (known as a _system tag_) that you can use to identify incidents and alerts that involve priority accounts.</span></span> <span data-ttu-id="240dd-137">如需 **優先順序帳戶** 的詳細資訊，請參閱 [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="240dd-137">For more information about **priority accounts**, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

<span data-ttu-id="240dd-138">您也可以建立自訂標記，進一步識別和分類您的優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="240dd-138">You can also create custom tags to further identify and classify your priority accounts.</span></span> <span data-ttu-id="240dd-139">如需詳細資訊，請參閱 [User tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="240dd-139">For more information, see [User tags](user-tags.md).</span></span> <span data-ttu-id="240dd-140">請注意，您可以在與自訂使用者標籤位於相同介面中 (系統標記) 管理 **優先順序帳戶** 。</span><span class="sxs-lookup"><span data-stu-id="240dd-140">Note that you can manage **priority accounts** (system tags) in the same interface as custom user tags.</span></span>

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a><span data-ttu-id="240dd-141">監視警示、報告和偵測中的優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="240dd-141">Monitor priority accounts in alerts, reports, and detections</span></span>

<span data-ttu-id="240dd-142">在您保護優先順序使用者並標示其標記之後，您可以使用 EOP 和 Defender for Office 365 中的可用報告、警示和調查，以快速識別涉及優先順序帳戶的事件或偵測。</span><span class="sxs-lookup"><span data-stu-id="240dd-142">After you secure and tag your priority users, you can use the available reports, alerts, and investigations in EOP and Defender for Office 365 to quickly identify incidents or detections that involve priority accounts.</span></span> <span data-ttu-id="240dd-143">下表說明支援使用者標記的功能。</span><span class="sxs-lookup"><span data-stu-id="240dd-143">The features that support user tags are described in the following table.</span></span>

<br>

****

|<span data-ttu-id="240dd-144">功能</span><span class="sxs-lookup"><span data-stu-id="240dd-144">Feature</span></span>|<span data-ttu-id="240dd-145">描述</span><span class="sxs-lookup"><span data-stu-id="240dd-145">Description</span></span>|
|---|---|
|<span data-ttu-id="240dd-146">警示</span><span class="sxs-lookup"><span data-stu-id="240dd-146">Alerts</span></span>|<span data-ttu-id="240dd-147">受影響使用者的使用者標記是可見的，而且在安全性 & 合規性中心的 [ **View alerts** ] 頁面上以篩選器形式提供。</span><span class="sxs-lookup"><span data-stu-id="240dd-147">The user tags of affected users are visible and available as filters on the **View alerts** page in the Security & Compliance Center.</span></span> <span data-ttu-id="240dd-148">如需詳細資訊，請參閱 [查看提醒](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)。</span><span class="sxs-lookup"><span data-stu-id="240dd-148">For more information, see [Viewing alerts](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts).</span></span>|
|<span data-ttu-id="240dd-149">威脅總管</span><span class="sxs-lookup"><span data-stu-id="240dd-149">Threat Explorer</span></span> <p> <span data-ttu-id="240dd-150">即時偵測</span><span class="sxs-lookup"><span data-stu-id="240dd-150">Real-time detections</span></span>|<span data-ttu-id="240dd-151">在 [ **威脅瀏覽器** ] 中 (microsoft Defender for Office 365 plan 2) 或 **即時** 偵測 (Microsoft Defender for office 365 plan 1) ，使用者標記會顯示在 [電子郵件方格] 視圖和 [電子郵件詳細資料] 浮出視窗中。</span><span class="sxs-lookup"><span data-stu-id="240dd-151">In **Threat Explorer** (Microsoft Defender for Office 365 Plan 2) or **Real-time detections** (Microsoft Defender for Office 365 Plan 1), user tags are visible in the Email grid view and the Email details flyout.</span></span> <span data-ttu-id="240dd-152">使用者標記也可以做為可篩選的屬性。</span><span class="sxs-lookup"><span data-stu-id="240dd-152">User tags are also available as a filterable property.</span></span> <span data-ttu-id="240dd-153">如需詳細資訊，請參閱  [威脅資源管理器中的標記](threat-explorer.md#tags-in-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="240dd-153">For more information, see  [Tags in Threat Explorer](threat-explorer.md#tags-in-threat-explorer).</span></span>|
|<span data-ttu-id="240dd-154">行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="240dd-154">Campaign Views</span></span>|<span data-ttu-id="240dd-155">使用者標記是 Microsoft Defender for Office 365 方案2中的眾多可篩選屬性之一。</span><span class="sxs-lookup"><span data-stu-id="240dd-155">User tags are one of many filterable properties in Campaign Views in Microsoft Defender for Office 365 Plan 2.</span></span> <span data-ttu-id="240dd-156">如需詳細資訊，請參閱 [即時檢視](campaigns.md)。</span><span class="sxs-lookup"><span data-stu-id="240dd-156">For more information, see [Campaign Views](campaigns.md).</span></span>|
|<span data-ttu-id="240dd-157">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="240dd-157">Threat protection status report</span></span>|<span data-ttu-id="240dd-158">在實際 **威脅防護狀態報表** 中的所有 views 和詳細資料表格中，您可以依 **優先順序帳戶** 來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="240dd-158">In virtually all of the views and detail tables in the **Threat protection status report**, you can filter the results by **priority accounts**.</span></span> <span data-ttu-id="240dd-159">如需詳細資訊，請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="240dd-159">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="240dd-160">優先順序帳戶報告的電子郵件問題</span><span class="sxs-lookup"><span data-stu-id="240dd-160">Email issues for priority accounts report</span></span>|<span data-ttu-id="240dd-161">Exchange 系統管理中心中「優先順序帳戶」報告的 **電子郵件問題** (EAC) 包含 **優先順序帳戶** 之未傳遞和延遲郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="240dd-161">The **Email issues for priority accounts** report in the Exchange admin center (EAC) contains information about undelivered and delayed messages for **priority accounts**.</span></span> <span data-ttu-id="240dd-162">如需詳細資訊，請參閱 [優先順序帳戶報告的電子郵件問題](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。</span><span class="sxs-lookup"><span data-stu-id="240dd-162">For more information, see [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="240dd-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="240dd-163">See also</span></span>

[<span data-ttu-id="240dd-164">宣告 Office 365 的 Microsoft Defender 優先順序帳戶保護</span><span class="sxs-lookup"><span data-stu-id="240dd-164">Announcing Priority Account Protection in Microsoft Defender for Office 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
