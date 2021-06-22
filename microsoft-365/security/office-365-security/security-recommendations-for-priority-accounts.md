---
title: Microsoft 365 中優先順序帳戶、優先順序帳戶、優先順序帳戶 Office 365、優先順序帳戶中 Microsoft 365 的安全性建議
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
description: 系統管理員可以瞭解如何提升安全性設定，以及如何在其 Microsoft 365 組織中提升優先順序帳戶的安全性設定，以及使用報表、警示和調查。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7617dd5af6a7e3b66fb33818208f01c8d8a338e
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055253"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a><span data-ttu-id="984c5-103">Microsoft 365 中優先順序帳戶的安全性建議</span><span class="sxs-lookup"><span data-stu-id="984c5-103">Security recommendations for priority accounts in Microsoft 365</span></span>

<span data-ttu-id="984c5-104">並非所有的使用者帳戶都可以存取相同的公司資訊。</span><span class="sxs-lookup"><span data-stu-id="984c5-104">Not all user accounts have access to the same company information.</span></span> <span data-ttu-id="984c5-105">有些帳戶可以存取機密資訊，例如財務資料、產品開發資訊、合作夥伴對重要組建系統的存取等等。</span><span class="sxs-lookup"><span data-stu-id="984c5-105">Some accounts have access to sensitive information, such as financial data, product development information, partner access to critical build systems, and more.</span></span> <span data-ttu-id="984c5-106">若遭到損害，具有高度機密資訊存取權的帳戶會帶來嚴重威脅。</span><span class="sxs-lookup"><span data-stu-id="984c5-106">If compromised, accounts that have access to highly confidential information pose a serious threat.</span></span> <span data-ttu-id="984c5-107">我們呼叫這些類型的帳戶 _優先順序帳戶_。</span><span class="sxs-lookup"><span data-stu-id="984c5-107">We call these types of accounts _priority accounts_.</span></span> <span data-ttu-id="984c5-108">優先順序帳戶包括 (但不限於) Ceo、CISOs、CFOs、基礎結構管理員帳戶、組建系統帳戶等等。</span><span class="sxs-lookup"><span data-stu-id="984c5-108">Priority accounts include (but aren't limited to) CEOs, CISOs, CFOs, infrastructure admin accounts, build system accounts, and more.</span></span>

<span data-ttu-id="984c5-109">針對攻擊者，針對一般或未知使用者強制轉換隨機網路的一般網路釣魚攻擊，效率低下。</span><span class="sxs-lookup"><span data-stu-id="984c5-109">For attackers, ordinary phishing attacks that cast a random net for ordinary or unknown users are inefficient.</span></span> <span data-ttu-id="984c5-110">另一方面， _spear 的網路釣魚_ 或 _whaling_ 攻擊會以攻擊者為目標，取得優先順序的帳戶。</span><span class="sxs-lookup"><span data-stu-id="984c5-110">On the other hand, _spear phishing_ or _whaling_ attacks that target priority accounts are very rewarding for attackers.</span></span> <span data-ttu-id="984c5-111">所以，優先順序帳戶需要比一般保護更強，以協助防止帳戶損損。</span><span class="sxs-lookup"><span data-stu-id="984c5-111">So, priority accounts require stronger than ordinary protection to help prevent account compromise.</span></span>

<span data-ttu-id="984c5-112">Microsoft 365 和 Microsoft Defender for Office 365 包含數個主要功能，可為優先順序帳戶提供額外的安全性層級。</span><span class="sxs-lookup"><span data-stu-id="984c5-112">Microsoft 365 and Microsoft Defender for Office 365 contain several key features that provide additional layers of security for your priority accounts.</span></span> <span data-ttu-id="984c5-113">本文說明這些功能及其用法。</span><span class="sxs-lookup"><span data-stu-id="984c5-113">This article describes these capabilities and how to use them.</span></span>

![圖示表單中安全性建議的摘要](../../media/security-recommendations-for-priority-users.png)

<br>

****

|<span data-ttu-id="984c5-115">工作</span><span class="sxs-lookup"><span data-stu-id="984c5-115">Task</span></span>|<span data-ttu-id="984c5-116">所有 Office 365 企業版方案</span><span class="sxs-lookup"><span data-stu-id="984c5-116">All Office 365 Enterprise plans</span></span>|<span data-ttu-id="984c5-117">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="984c5-117">Microsoft 365 E3</span></span>|<span data-ttu-id="984c5-118">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="984c5-118">Microsoft 365 E5</span></span>|
|---|:---:|:---:|:---:|
|[<span data-ttu-id="984c5-119">增加優先順序帳戶的登入安全性</span><span class="sxs-lookup"><span data-stu-id="984c5-119">Increase sign-in security for priority accounts</span></span>](#increase-sign-in-security-for-priority-accounts)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[<span data-ttu-id="984c5-123">對優先順序帳戶使用嚴格的預先設定安全性原則</span><span class="sxs-lookup"><span data-stu-id="984c5-123">Use Strict preset security policies for priority accounts</span></span>](#use-strict-preset-security-policies-for-priority-accounts)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[<span data-ttu-id="984c5-127">將使用者標記套用至優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="984c5-127">Apply user tags to priority accounts</span></span>](#apply-user-tags-to-priority-accounts)|||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[<span data-ttu-id="984c5-129">監視警示、報告和偵測中的優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="984c5-129">Monitor priority accounts in alerts, reports, and detections</span></span>](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[<span data-ttu-id="984c5-131">訓練使用者</span><span class="sxs-lookup"><span data-stu-id="984c5-131">Train users</span></span>](#train-users)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

> [!NOTE]
> <span data-ttu-id="984c5-135">如需 (系統管理員帳戶) 保護 _特權帳戶_ 的詳細資訊，請參閱 [本主題](/azure/architecture/framework/security/critical-impact-accounts)。</span><span class="sxs-lookup"><span data-stu-id="984c5-135">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="increase-sign-in-security-for-priority-accounts"></a><span data-ttu-id="984c5-136">增加優先順序帳戶的登入安全性</span><span class="sxs-lookup"><span data-stu-id="984c5-136">Increase sign-in security for priority accounts</span></span>

<span data-ttu-id="984c5-137">優先順序帳戶需要增加的登入安全性。</span><span class="sxs-lookup"><span data-stu-id="984c5-137">Priority accounts require increased sign-in security.</span></span> <span data-ttu-id="984c5-138">您可以要求多重要素驗證 (MFA) 並停用舊版驗證通訊協定，以提升其登入安全性。</span><span class="sxs-lookup"><span data-stu-id="984c5-138">You can increase their sign-in security by requiring multi-factor authentication (MFA) and disabling legacy authentication protocols.</span></span>

<span data-ttu-id="984c5-139">如需相關指示，請參閱 [步驟1。增加具有 MFA 的遠端工作者的登入安全性](../../solutions/empower-people-to-work-remotely-secure-sign-in.md)。</span><span class="sxs-lookup"><span data-stu-id="984c5-139">For instructions, see [Step 1. Increase sign-in security for remote workers with MFA](../../solutions/empower-people-to-work-remotely-secure-sign-in.md).</span></span> <span data-ttu-id="984c5-140">雖然本文是有關遠端工作者的資訊，但相同的概念也適用于優先順序使用者。</span><span class="sxs-lookup"><span data-stu-id="984c5-140">Although this article is about remote workers, the same concepts apply to priority users.</span></span>

<span data-ttu-id="984c5-141">**附注**：強烈建議您全域停用所有優先順序使用者的舊版驗證通訊協定，如先前的文章所述。</span><span class="sxs-lookup"><span data-stu-id="984c5-141">**Note**: We strongly recommend that you globally disable legacy authentication protocols for all priority users as described in the previous article.</span></span> <span data-ttu-id="984c5-142">如果您的業務需求可防止您這樣做，Exchange Online 會提供下列控制項，以協助限制舊版驗證通訊協定的範圍：</span><span class="sxs-lookup"><span data-stu-id="984c5-142">If your business requirements prevent you from doing so, Exchange Online offers the following controls to help limit the scope of legacy authentication protocols:</span></span>

- <span data-ttu-id="984c5-143">您可以使用 Exchange Online 中的[驗證原則](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)和[用戶端存取規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)，封鎖或允許特定使用者的基本驗證和舊版驗證通訊協定，例如 POP3、IMAP4 和已驗證的 SMTP。</span><span class="sxs-lookup"><span data-stu-id="984c5-143">You can use [authentication policies](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) and [Client Access Rules](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online to block or allow Basic authentication and legacy authentication protocols like POP3, IMAP4, and authenticated SMTP for specific users.</span></span>

- <span data-ttu-id="984c5-144">您可以停用個別信箱上的 POP3 和 IMAP4 存取權。</span><span class="sxs-lookup"><span data-stu-id="984c5-144">You can disable POP3 and IMAP4 access on individual mailboxes.</span></span> <span data-ttu-id="984c5-145">您可以在組織層級停用已驗證的 SMTP，並在仍需要該 SMTP 的特定信箱上啟用該 SMTP。</span><span class="sxs-lookup"><span data-stu-id="984c5-145">You can disable authenticated SMTP at the organizational level and enable it on specific mailboxes that still require it.</span></span> <span data-ttu-id="984c5-146">如需相關指示，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="984c5-146">For instructions, see the following articles:</span></span>
  - [<span data-ttu-id="984c5-147">啟用或停用使用者 POP3 或 IMAP4 存取權</span><span class="sxs-lookup"><span data-stu-id="984c5-147">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [<span data-ttu-id="984c5-148">啟用或停用已驗證的用戶端 SMTP 提交 (SMTP 驗證) </span><span class="sxs-lookup"><span data-stu-id="984c5-148">Enable or disable authenticated client SMTP submission (SMTP AUTH)</span></span>](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

<span data-ttu-id="984c5-149">也值得注意的是，基本驗證在 Exchange Online 中已被取代 Exchange Web 服務 (EWS) 、Exchange ActiveSync、POP3、IMAP4 和遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="984c5-149">It's also worth noting that Basic authentication is in the process of being deprecated in Exchange Online for Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4, and remote PowerShell.</span></span> <span data-ttu-id="984c5-150">如需詳細資訊，請參閱此 [博客文章](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。</span><span class="sxs-lookup"><span data-stu-id="984c5-150">For details, see this [blog post](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).</span></span>

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a><span data-ttu-id="984c5-151">對優先順序帳戶使用嚴格的預先設定安全性原則</span><span class="sxs-lookup"><span data-stu-id="984c5-151">Use Strict preset security policies for priority accounts</span></span>

<span data-ttu-id="984c5-152">優先順序使用者需要更嚴格的動作，以用於 Exchange Online Protection (EOP) 和 Defender for Office 365 中提供的各種保護。</span><span class="sxs-lookup"><span data-stu-id="984c5-152">Priority users require more stringent actions for the various protections that are available in Exchange Online Protection (EOP) and Defender for Office 365.</span></span>

<span data-ttu-id="984c5-153">例如，若要將歸類為垃圾郵件的郵件傳送至 [垃圾郵件] 資料夾，您應該隔離這些相同的郵件（如果它們是用於優先順序帳戶）。</span><span class="sxs-lookup"><span data-stu-id="984c5-153">For example, instead of delivering messages that were classified as spam to the Junk Email folder, you should quarantine those same messages if they're intended for priority accounts.</span></span>

<span data-ttu-id="984c5-154">您可以使用預先設定的安全性原則中的 Strict 設定檔，為優先順序帳戶執行此嚴格的方法。</span><span class="sxs-lookup"><span data-stu-id="984c5-154">You can implement this stringent approach for priority accounts by using the Strict profile in preset security policies.</span></span>

<span data-ttu-id="984c5-155">「預設」安全性原則是一個方便且集中的位置，可將建議的嚴格原則設定套用至 EOP 和 Defender for Office 365 中的所有保護。</span><span class="sxs-lookup"><span data-stu-id="984c5-155">Preset security policies are a convenient and central location to apply our recommended Strict policy settings for all of the protections in EOP and Defender for Office 365.</span></span> <span data-ttu-id="984c5-156">如需詳細資訊，請參閱[EOP 和 Microsoft Defender for Office 365 中的預先設定安全性原則](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="984c5-156">For more information, see [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).</span></span>

<span data-ttu-id="984c5-157">如需嚴格原則設定與預設和標準原則設定的區別之詳細資訊，請參閱[EOP 和 Microsoft Defender 的建議設定，以 Office 365 安全性](recommended-settings-for-eop-and-office365.md)。</span><span class="sxs-lookup"><span data-stu-id="984c5-157">For details about how the Strict policy settings differ from the default and Standard policy settings, see [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="apply-user-tags-to-priority-accounts"></a><span data-ttu-id="984c5-158">將使用者標記套用至優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="984c5-158">Apply user tags to priority accounts</span></span>

<span data-ttu-id="984c5-159">Microsoft Defender 中 Office 365 方案 2 (Microsoft 365 E5 或附加元件訂閱) 的使用者標記，是一種快速識別和分類報告和事件調查中的特定使用者或使用者群組的方式。</span><span class="sxs-lookup"><span data-stu-id="984c5-159">User tags in Microsoft Defender for Office 365 Plan 2 (as part of Microsoft 365 E5 or an add-on subscription) are a way to quickly identify and classify specific users or groups of users in reports and incident investigations.</span></span>

<span data-ttu-id="984c5-160">「**優先順序帳戶**」是一種內建的使用者標記， (稱為 _系統_ 標籤) ，可供您用來識別涉及優先順序帳戶的事件及警示。</span><span class="sxs-lookup"><span data-stu-id="984c5-160">**Priority accounts** is a type of built-in user tag (known as a _system tag_) that you can use to identify incidents and alerts that involve priority accounts.</span></span> <span data-ttu-id="984c5-161">如需 **優先順序帳戶** 的詳細資訊，請參閱 [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="984c5-161">For more information about **priority accounts**, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

<span data-ttu-id="984c5-162">您也可以建立自訂標記，進一步識別和分類您的優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="984c5-162">You can also create custom tags to further identify and classify your priority accounts.</span></span> <span data-ttu-id="984c5-163">如需詳細資訊，請參閱 [User tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="984c5-163">For more information, see [User tags](user-tags.md).</span></span> <span data-ttu-id="984c5-164">您可以在與自訂使用者標籤位於相同介面中 (系統標記) 管理 **優先順序帳戶** 。</span><span class="sxs-lookup"><span data-stu-id="984c5-164">You can manage **priority accounts** (system tags) in the same interface as custom user tags.</span></span>

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a><span data-ttu-id="984c5-165">監視警示、報告和偵測中的優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="984c5-165">Monitor priority accounts in alerts, reports, and detections</span></span>

<span data-ttu-id="984c5-166">在您保護優先順序的使用者並進行標記之後，您可以使用 EOP 和 Defender for Office 365 中的可用報告、警示和調查，以快速識別涉及優先順序帳戶的事件或偵測。</span><span class="sxs-lookup"><span data-stu-id="984c5-166">After you secure and tag your priority users, you can use the available reports, alerts, and investigations in EOP and Defender for Office 365 to quickly identify incidents or detections that involve priority accounts.</span></span> <span data-ttu-id="984c5-167">下表說明支援使用者標記的功能。</span><span class="sxs-lookup"><span data-stu-id="984c5-167">The features that support user tags are described in the following table.</span></span>

<br>

****

|<span data-ttu-id="984c5-168">功能</span><span class="sxs-lookup"><span data-stu-id="984c5-168">Feature</span></span>|<span data-ttu-id="984c5-169">描述</span><span class="sxs-lookup"><span data-stu-id="984c5-169">Description</span></span>|
|---|---|
|<span data-ttu-id="984c5-170">警示</span><span class="sxs-lookup"><span data-stu-id="984c5-170">Alerts</span></span>|<span data-ttu-id="984c5-171">受影響使用者的使用者標記是可見的，而且可在 Microsoft 365 Defender 入口網站的 [**提醒**] 頁面上做為篩選。</span><span class="sxs-lookup"><span data-stu-id="984c5-171">The user tags of affected users are visible and available as filters on the **Alerts** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="984c5-172">如需詳細資訊，請參閱 [查看提醒](../../compliance/alert-policies.md#viewing-alerts)。</span><span class="sxs-lookup"><span data-stu-id="984c5-172">For more information, see [Viewing alerts](../../compliance/alert-policies.md#viewing-alerts).</span></span>|
|<span data-ttu-id="984c5-173">總管</span><span class="sxs-lookup"><span data-stu-id="984c5-173">Explorer</span></span> <p> <span data-ttu-id="984c5-174">即時偵測</span><span class="sxs-lookup"><span data-stu-id="984c5-174">Real-time detections</span></span>|<span data-ttu-id="984c5-175">在 **Explorer** (defender for Office 365 Plan 2) 或 **即時** 偵測 (Defender for Office 365 Plan 1) ，使用者標記會顯示在 [電子郵件格線] 視圖和 [電子郵件詳細資料] 浮出視窗中。</span><span class="sxs-lookup"><span data-stu-id="984c5-175">In **Explorer** (Defender for Office 365 Plan 2) or **Real-time detections** (Defender for Office 365 Plan 1), user tags are visible in the Email grid view and the Email details flyout.</span></span> <span data-ttu-id="984c5-176">使用者標記也可以做為可篩選的屬性。</span><span class="sxs-lookup"><span data-stu-id="984c5-176">User tags are also available as a filterable property.</span></span> <span data-ttu-id="984c5-177">如需詳細資訊，請參閱  [Explorer 中的標記](threat-explorer.md#tags-in-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="984c5-177">For more information, see  [Tags in Explorer](threat-explorer.md#tags-in-threat-explorer).</span></span>|
|<span data-ttu-id="984c5-178">行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="984c5-178">Campaign Views</span></span>|<span data-ttu-id="984c5-179">使用者標記是 Microsoft Defender 的 [市場即時檢視] 中的眾多可篩選屬性之一，用於 Office 365 方案2。</span><span class="sxs-lookup"><span data-stu-id="984c5-179">User tags are one of many filterable properties in Campaign Views in Microsoft Defender for Office 365 Plan 2.</span></span> <span data-ttu-id="984c5-180">如需詳細資訊，請參閱 [即時檢視](campaigns.md)。</span><span class="sxs-lookup"><span data-stu-id="984c5-180">For more information, see [Campaign Views](campaigns.md).</span></span>|
|<span data-ttu-id="984c5-181">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="984c5-181">Threat protection status report</span></span>|<span data-ttu-id="984c5-182">在實際 **威脅防護狀態報表** 中的所有 views 和詳細資料表格中，您可以依 **優先順序帳戶** 來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="984c5-182">In virtually all of the views and detail tables in the **Threat protection status report**, you can filter the results by **priority accounts**.</span></span> <span data-ttu-id="984c5-183">如需詳細資訊，請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="984c5-183">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="984c5-184">優先順序帳戶報告的電子郵件問題</span><span class="sxs-lookup"><span data-stu-id="984c5-184">Email issues for priority accounts report</span></span>|<span data-ttu-id="984c5-185">Exchange 系統管理中心的優先順序帳戶報告 (EAC) 的 **電子郵件問題**，包含 **優先順序帳戶** 之未傳遞和延遲郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="984c5-185">The **Email issues for priority accounts** report in the Exchange admin center (EAC) contains information about undelivered and delayed messages for **priority accounts**.</span></span> <span data-ttu-id="984c5-186">如需詳細資訊，請參閱 [優先順序帳戶報告的電子郵件問題](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。</span><span class="sxs-lookup"><span data-stu-id="984c5-186">For more information, see [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>|
|

## <a name="train-users"></a><span data-ttu-id="984c5-187">訓練使用者</span><span class="sxs-lookup"><span data-stu-id="984c5-187">Train users</span></span>

<span data-ttu-id="984c5-188">訓練具有優先順序帳戶的使用者，可協助儲存這些使用者和安全性作業小組的時間和不滿。</span><span class="sxs-lookup"><span data-stu-id="984c5-188">Training users with priority accounts can help save those users and your security operations team much time and frustration.</span></span> <span data-ttu-id="984c5-189">聰明的使用者不太可能開啟附件或按一下可疑電子郵件訊息中的連結，也很可能避免可疑的網站。</span><span class="sxs-lookup"><span data-stu-id="984c5-189">Savvy users are less likely to open attachments or click links in questionable email messages, and they are more likely to avoid suspicious websites.</span></span>

<span data-ttu-id="984c5-190">Harvard 甘迺迪 School [Cybersecurity 活動手冊](https://www.belfercenter.org/CyberPlaybook) 為您的組織內的安全性感知建立強文化，提供了極佳的指導方針，包括訓練使用者來識別網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="984c5-190">The Harvard Kennedy School [Cybersecurity Campaign Handbook](https://www.belfercenter.org/CyberPlaybook) provides excellent guidance for establishing a strong culture of security awareness within your organization, including training users to identify phishing attacks.</span></span>

<span data-ttu-id="984c5-191">Microsoft 365 提供下列資源，協助您在組織中告知使用者：</span><span class="sxs-lookup"><span data-stu-id="984c5-191">Microsoft 365 provides the following resources to help inform users in your organization:</span></span>

<br>

****

|<span data-ttu-id="984c5-192">概念</span><span class="sxs-lookup"><span data-stu-id="984c5-192">Concept</span></span>|<span data-ttu-id="984c5-193">資源</span><span class="sxs-lookup"><span data-stu-id="984c5-193">Resources</span></span>|<span data-ttu-id="984c5-194">描述</span><span class="sxs-lookup"><span data-stu-id="984c5-194">Description</span></span>|
|---|---|---|
|<span data-ttu-id="984c5-195">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="984c5-195">Microsoft 365</span></span>|[<span data-ttu-id="984c5-196">可自訂的教學路徑</span><span class="sxs-lookup"><span data-stu-id="984c5-196">Customizable learning pathways</span></span>](/office365/customlearning/)|<span data-ttu-id="984c5-197">這些資源可協助您將組織中使用者的訓練放在一起。</span><span class="sxs-lookup"><span data-stu-id="984c5-197">These resources can help you put together training for users in your organization.</span></span>|
|<span data-ttu-id="984c5-198">Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="984c5-198">Microsoft 365 security</span></span>|[<span data-ttu-id="984c5-199">Learning 模組：使用內建的智慧安全性保護組織安全 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="984c5-199">Learning module: Secure your organization with built-in, intelligent security from Microsoft 365</span></span>](/learn/modules/security-with-microsoft-365)|<span data-ttu-id="984c5-200">此模組可讓您描述 Microsoft 365 安全性功能如何協同運作，並闡明這些安全性功能的優點。</span><span class="sxs-lookup"><span data-stu-id="984c5-200">This module enables you to describe how Microsoft 365 security features work together and to articulate the benefits of these security features.</span></span>|
|<span data-ttu-id="984c5-201">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="984c5-201">Multi-factor authentication</span></span>|[<span data-ttu-id="984c5-202">雙步驟驗證：其他驗證頁面為何？</span><span class="sxs-lookup"><span data-stu-id="984c5-202">Two-step verification: What is the additional verification page?</span></span>](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|<span data-ttu-id="984c5-203">本文可協助使用者瞭解哪些多重要素驗證，以及如何在您的組織中使用它。</span><span class="sxs-lookup"><span data-stu-id="984c5-203">This article helps end users understand what multi-factor authentication is and why it's being used at your organization.</span></span>|
|<span data-ttu-id="984c5-204">攻擊模擬訓練</span><span class="sxs-lookup"><span data-stu-id="984c5-204">Attack simulation training</span></span>|[<span data-ttu-id="984c5-205">開始使用攻擊模擬訓練</span><span class="sxs-lookup"><span data-stu-id="984c5-205">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)|<span data-ttu-id="984c5-206">Office 365 方案2的 Microsoft Defender 中的攻擊模擬訓練，可讓系統管理員針對特定使用者群組設定、啟動和追蹤模擬網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="984c5-206">Attack simulation training in Microsoft Defender for Office 365 Plan 2 allows admin to configure, launch, and track simulated phishing attacks against specific groups of users.</span></span>|

<span data-ttu-id="984c5-207">此外，Microsoft 建議使用者採取本文所述的動作： [保護您的帳戶和裝置免受駭客和惡意](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)代碼的攻擊。</span><span class="sxs-lookup"><span data-stu-id="984c5-207">In addition, Microsoft recommends that users take the actions described in this article: [Protect your account and devices from hackers and malware](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6).</span></span> <span data-ttu-id="984c5-208">這些動作包括：</span><span class="sxs-lookup"><span data-stu-id="984c5-208">These actions include:</span></span>

- <span data-ttu-id="984c5-209">使用強式密碼</span><span class="sxs-lookup"><span data-stu-id="984c5-209">Using strong passwords</span></span>
- <span data-ttu-id="984c5-210">保護裝置</span><span class="sxs-lookup"><span data-stu-id="984c5-210">Protecting devices</span></span>
- <span data-ttu-id="984c5-211">啟用非管理裝置的 Windows 10 和 Mac 電腦 (上的安全性功能) </span><span class="sxs-lookup"><span data-stu-id="984c5-211">Enabling security features on Windows 10 and Mac PCs (for unmanaged devices)</span></span>

## <a name="see-also"></a><span data-ttu-id="984c5-212">另請參閱</span><span class="sxs-lookup"><span data-stu-id="984c5-212">See also</span></span>

[<span data-ttu-id="984c5-213">宣佈 Office 365 的 Microsoft Defender 優先順序帳戶保護</span><span class="sxs-lookup"><span data-stu-id="984c5-213">Announcing Priority Account Protection in Microsoft Defender for Office 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
