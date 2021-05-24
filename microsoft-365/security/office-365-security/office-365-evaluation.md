---
title: 評估 Microsoft Defender 的 Office 365
description: 在評估模式中 Office 365 的 defender 針對記錄 verdicts （例如惡意程式碼，但不會對郵件執行）的 Office 365 電子郵件原則建立 Defender。
keywords: 評估 Office 365，Microsoft Defender for Office 365，office 365 評估，嘗試 office 365，microsoft defender，microsoft defender for Endpoint
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab0f05c45afa6a4ad66c9fc1bf58e69505632171
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624990"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="42333-104">評估 Microsoft Defender 的 Office 365</span><span class="sxs-lookup"><span data-stu-id="42333-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="42333-105">用於 Office 365 評估的 Microsoft Defender 位於公開預覽中。</span><span class="sxs-lookup"><span data-stu-id="42333-105">Microsoft Defender for Office 365 evaluation is in public preview.</span></span> <span data-ttu-id="42333-106">在沒有服務等級協定的情況下提供此預覽版本。</span><span class="sxs-lookup"><span data-stu-id="42333-106">This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="42333-107">某些功能可能不受支援，或可能具有有限的功能。</span><span class="sxs-lookup"><span data-stu-id="42333-107">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="42333-108">進行完整的安全性產品評估，可協助您瞭解升級和購買的決策。</span><span class="sxs-lookup"><span data-stu-id="42333-108">Conducting a thorough security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="42333-109">它可協助您嘗試安全性產品的功能，以評估其日常工作中的安全性操作小組的運作方式。</span><span class="sxs-lookup"><span data-stu-id="42333-109">It helps to try out the security product's capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="42333-110">[Microsoft defender for Office 365](defender-for-office-365.md)評估體驗旨在消除裝置和環境設定的複雜性，使您能夠專注于評估 Microsoft defender 的 Office 365 功能。</span><span class="sxs-lookup"><span data-stu-id="42333-110">The [Microsoft Defender for Office 365](defender-for-office-365.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of Microsoft Defender for Office 365.</span></span> <span data-ttu-id="42333-111">使用評估模式，可以評估所有傳送至 Exchange Online 信箱的郵件，而不需將 MX 記錄指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="42333-111">With evaluation mode, all messages sent to Exchange Online mailboxes can be evaluated without pointing MX records to Microsoft.</span></span> <span data-ttu-id="42333-112">此功能僅適用于電子郵件保護，不會 Office 如 Word、SharePoint 或 Teams 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="42333-112">The feature only applies to email protection and not to Office Clients like Word, SharePoint, or Teams.</span></span>

<span data-ttu-id="42333-113">如果您尚無支援 Microsoft Defender for Office 365 的授權，您可以開始[30 天的試用評估](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)，並在 Office 365 安全性 & 規範中心 (中測試功能 https://protection.office.com/homepage) 。</span><span class="sxs-lookup"><span data-stu-id="42333-113">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="42333-114">您將會喜歡快速設定，必要時您可以輕鬆關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="42333-114">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="42333-115">如果您是在整合的 Microsoft 365 安全性入口網站中 (security.microsoft.com) 您可以在這裡為 Office 365 評估啟動 Defender：電子郵件 & 共同作業 > 原則 & 規則 > 其他原則 > 威脅原則。</span><span class="sxs-lookup"><span data-stu-id="42333-115">If you're in the unified Microsoft 365 security portal (security.microsoft.com) you can start a Defender for Office 365 evaluation here: Email & Collaboration > Policies & Rules > Threat Policies > Additional Policies.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="42333-116">評估的運作方式</span><span class="sxs-lookup"><span data-stu-id="42333-116">How the evaluation works</span></span>

<span data-ttu-id="42333-117">在評估模式中 Office 365 的 defender 針對記錄 verdicts （例如惡意程式碼，但不會對郵件執行）的 Office 365 電子郵件原則建立 Defender。</span><span class="sxs-lookup"><span data-stu-id="42333-117">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don't act on messages.</span></span> <span data-ttu-id="42333-118">您不需要變更 MX 記錄設定。</span><span class="sxs-lookup"><span data-stu-id="42333-118">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="42333-119">使用評估模式時，會替您設定 [安全附件](safe-attachments.md)、 [安全連結](safe-links.md)和 [信箱智慧類比原則](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。</span><span class="sxs-lookup"><span data-stu-id="42333-119">With evaluation mode, [Safe Attachments](safe-attachments.md), [Safe Links](safe-links.md), and [mailbox intelligence based impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are set up on your behalf.</span></span> <span data-ttu-id="42333-120">所有 Office 365 原則的 Defender 都是在後臺非強制模式中建立，對您看不到。</span><span class="sxs-lookup"><span data-stu-id="42333-120">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="42333-121">在設定過程中，評估模式也會為 [連接器設定增強型篩選](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="42333-121">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="42333-122">它會透過保留 IP 位址和寄件者資訊來提升篩選精確度，當郵件透過電子郵件安全性閘道 (ESG) 在 Office 365 之前，就會遺失。</span><span class="sxs-lookup"><span data-stu-id="42333-122">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="42333-123">針對連接器的增強篩選也會提升現有 Exchange Online Protection (EOP) 反垃圾郵件和反網路釣魚原則的篩選精確性。</span><span class="sxs-lookup"><span data-stu-id="42333-123">Enhanced Filtering for Connectors also improves the filtering accuracy for your existing Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="42333-124">啟用增強型連接器的增強篩選功能可提升篩選精確度，但如果您在 Office 365 的上有 ESG，而且目前不會略過 EOP 篩選，則可能會變更特定郵件的 deliverability。</span><span class="sxs-lookup"><span data-stu-id="42333-124">Enabled Enhanced Filtering for Connectors improves filtering accuracy but may alter deliverability for certain messages if you have an ESG in front of Defender for Office 365, and currently do not bypass EOP filtering.</span></span> <span data-ttu-id="42333-125">影響限制為 EOP 原則;在評估中建立的 MDO 原則安裝會以非強制模式建立。</span><span class="sxs-lookup"><span data-stu-id="42333-125">The impact is limited to EOP policies; MDO policies setup as part of the evaluation are created in non-enforcement mode.</span></span> <span data-ttu-id="42333-126">若要將潛在的實際影響降至最低，您可以建立傳輸規則，將垃圾郵件信賴等級設定 (SCL) 為-1，以略過所有的 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="42333-126">To minimize potential production impact, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="42333-127">請參閱 [使用 EAC 建立郵件流程規則，設定](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)郵件的 SCL 的   詳細資料。</span><span class="sxs-lookup"><span data-stu-id="42333-127">See [Use the EAC to create a mail flow rule that sets the SCL of a message](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="42333-128">當評估模式已設定時，每日會更新一份報告，其中包含超過90天的資料，量化當原則實施 (例如「刪除」、「傳送至垃圾、隔離」) 時，可能會封鎖的郵件。</span><span class="sxs-lookup"><span data-stu-id="42333-128">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked if the policies were implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="42333-129">針對 Office 365 和 EOP 偵測的所有 Defender 產生報告。</span><span class="sxs-lookup"><span data-stu-id="42333-129">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="42333-130">它們會根據偵測技術匯總 (例如，模擬) ，並且可依時間範圍篩選。</span><span class="sxs-lookup"><span data-stu-id="42333-130">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="42333-131">此外，您也可以根據需要建立郵件報告，以建立自訂透視或使用威脅瀏覽器深入瞭解郵件。</span><span class="sxs-lookup"><span data-stu-id="42333-131">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="42333-132">透過簡化的設定體驗，您可以將重點放在：</span><span class="sxs-lookup"><span data-stu-id="42333-132">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="42333-133">執行評估</span><span class="sxs-lookup"><span data-stu-id="42333-133">Running the evaluation</span></span>
- <span data-ttu-id="42333-134">取得詳細報告</span><span class="sxs-lookup"><span data-stu-id="42333-134">Getting a detailed report</span></span>
- <span data-ttu-id="42333-135">分析動作報告</span><span class="sxs-lookup"><span data-stu-id="42333-135">Analyzing the report for action</span></span>
- <span data-ttu-id="42333-136">展示評估結果</span><span class="sxs-lookup"><span data-stu-id="42333-136">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="42333-137">開始之前</span><span class="sxs-lookup"><span data-stu-id="42333-137">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="42333-138">授權</span><span class="sxs-lookup"><span data-stu-id="42333-138">Licensing</span></span>

<span data-ttu-id="42333-139">若要存取評估，您必須符合授權要求。</span><span class="sxs-lookup"><span data-stu-id="42333-139">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="42333-140">下列任何授權均可運作：</span><span class="sxs-lookup"><span data-stu-id="42333-140">Any of the following licenses will work:</span></span>

- <span data-ttu-id="42333-141">適用於 Office 365 的 Microsoft Defender 方案 1</span><span class="sxs-lookup"><span data-stu-id="42333-141">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="42333-142">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="42333-142">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="42333-143">Microsoft 365 E5，Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="42333-143">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="42333-144">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="42333-144">Office 365 E5</span></span>

<span data-ttu-id="42333-145">如果您沒有其中一個授權，您必須取得試用版授權。</span><span class="sxs-lookup"><span data-stu-id="42333-145">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="42333-146">試用</span><span class="sxs-lookup"><span data-stu-id="42333-146">Trial</span></span>

<span data-ttu-id="42333-147">若要取得 Microsoft Defender for Office 365 的試用版授權，您必須具有「**帳單管理員」角色** 或「**全域系統管理員」角色**。</span><span class="sxs-lookup"><span data-stu-id="42333-147">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="42333-148">向具有全域系統管理員角色的使用者要求許可權。</span><span class="sxs-lookup"><span data-stu-id="42333-148">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="42333-149">深入瞭解訂閱與授權</span><span class="sxs-lookup"><span data-stu-id="42333-149">Learn about subscriptions and licenses</span></span>](../../commerce/licenses/subscriptions-and-licenses.md)

<span data-ttu-id="42333-150">當您擁有適當的角色後，建議的路徑是取得 Microsoft Defender 的試用版授權，以供 Microsoft 365 系統管理中心的 Office 365 (Plan 2) ，請移至帳單 > 購買服務。</span><span class="sxs-lookup"><span data-stu-id="42333-150">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="42333-151">試用期包括30天的免費試用版，取得25個授權。</span><span class="sxs-lookup"><span data-stu-id="42333-151">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="42333-152">[Office 365 (計畫 2) 中取得 Microsoft Defender 的試用版](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。</span><span class="sxs-lookup"><span data-stu-id="42333-152">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="42333-153">您將會有30天的時段，其評估是用來監視和報告高級威脅。</span><span class="sxs-lookup"><span data-stu-id="42333-153">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="42333-154">如果您想要 Office 365 功能的完整版，您也可以選擇購買付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="42333-154">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="42333-155">角色</span><span class="sxs-lookup"><span data-stu-id="42333-155">Roles</span></span>

<span data-ttu-id="42333-156">在評估模式中設定 Office 365 的 Defender **時，需要 Exchange Online 角色**。</span><span class="sxs-lookup"><span data-stu-id="42333-156">**Exchange Online roles are required** to set up Defender for Office 365 in evaluation mode.</span></span> <span data-ttu-id="42333-157">指派 Microsoft 365 合規性或安全性系統管理員角色將無法運作。</span><span class="sxs-lookup"><span data-stu-id="42333-157">Assigning a Microsoft 365 compliance or security admin role won't work.</span></span>

- [<span data-ttu-id="42333-158">深入瞭解 Exchange Online 中的許可權</span><span class="sxs-lookup"><span data-stu-id="42333-158">Learn about permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
- [<span data-ttu-id="42333-159">深入瞭解指派系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="42333-159">Learn about assigning admin roles</span></span>](../../admin/add-users/assign-admin-roles.md)

<span data-ttu-id="42333-160">下列角色是必要的：</span><span class="sxs-lookup"><span data-stu-id="42333-160">The following roles are needed:</span></span>

|<span data-ttu-id="42333-161">工作</span><span class="sxs-lookup"><span data-stu-id="42333-161">Task</span></span>|<span data-ttu-id="42333-162">Exchange Online) 中的角色 (</span><span class="sxs-lookup"><span data-stu-id="42333-162">Role (in Exchange Online)</span></span>|
|---|---|
|<span data-ttu-id="42333-163">取得免費試用版或購買適用于 Office 365 (計畫 2) 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="42333-163">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>|<span data-ttu-id="42333-164">計費系統管理員角色或全域系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="42333-164">Billing admin role OR Global admin role</span></span>|
|<span data-ttu-id="42333-165">建立評估原則</span><span class="sxs-lookup"><span data-stu-id="42333-165">Create evaluation policy</span></span>|<span data-ttu-id="42333-166">遠端和公認的網域角色;安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="42333-166">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="42333-167">編輯評估原則</span><span class="sxs-lookup"><span data-stu-id="42333-167">Edit evaluation policy</span></span>|<span data-ttu-id="42333-168">遠端和公認的網域角色;安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="42333-168">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="42333-169">刪除評估原則</span><span class="sxs-lookup"><span data-stu-id="42333-169">Delete evaluation policy</span></span>|<span data-ttu-id="42333-170">遠端和公認的網域角色;安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="42333-170">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="42333-171">查看評估報告</span><span class="sxs-lookup"><span data-stu-id="42333-171">View evaluation report</span></span>|<span data-ttu-id="42333-172">安全性管理員角色或安全性讀者角色</span><span class="sxs-lookup"><span data-stu-id="42333-172">Security admin role OR Security reader role</span></span>|
|

### <a name="enhanced-filtering"></a><span data-ttu-id="42333-173">增強型篩選</span><span class="sxs-lookup"><span data-stu-id="42333-173">Enhanced filtering</span></span>

<span data-ttu-id="42333-174">您的 Exchange Online Protection 原則（如大量和垃圾郵件保護）將保持不變。</span><span class="sxs-lookup"><span data-stu-id="42333-174">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="42333-175">不過，評估會針對連接器開啟增強型篩選功能，這可能會影響郵件流程和 Exchange Online Protection 原則，除非略過。</span><span class="sxs-lookup"><span data-stu-id="42333-175">However, the evaluation turns on enhanced filtering for connectors, which may impact your mail flow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="42333-176">連接器的增強型篩選功能允許承租人使用反欺騙保護。</span><span class="sxs-lookup"><span data-stu-id="42333-176">Enhanced filtering for connectors allows tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="42333-177">如果您使用的電子郵件安全性閘道 (ESG) 但未開啟「增強型連接器」篩選，則不支援反欺騙。</span><span class="sxs-lookup"><span data-stu-id="42333-177">Anti-spoofing is not supported if you're using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="42333-178">URL</span><span class="sxs-lookup"><span data-stu-id="42333-178">URLs</span></span>

<span data-ttu-id="42333-179">郵件流程期間會引爆 URLs。</span><span class="sxs-lookup"><span data-stu-id="42333-179">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="42333-180">如果您不想要引爆特定的 URLs，請適當地管理您的允許 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="42333-180">If you don't want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="42333-181">如需詳細資訊，請參閱 [管理租使用者 Allow/封鎖清單](tenant-allow-block-list.md) 。</span><span class="sxs-lookup"><span data-stu-id="42333-181">See [Manage the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="42333-182">電子郵件內文中的 URL 連結將不會換行，以減少對客戶的影響。</span><span class="sxs-lookup"><span data-stu-id="42333-182">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="42333-183">電子郵件路由</span><span class="sxs-lookup"><span data-stu-id="42333-183">Email routing</span></span>

<span data-ttu-id="42333-184">準備要設定電子郵件目前如何路由的對應詳細資料，包括路由傳送郵件之輸入連接器的名稱。</span><span class="sxs-lookup"><span data-stu-id="42333-184">Prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="42333-185">如果您只是使用 Exchange Online Protection，則不會有連接器。 [深入瞭解郵件流程和電子郵件路由](/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="42333-185">If you are just using Exchange Online Protection, you won't have a connector. [Learn about mail flow and email routing](/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="42333-186">支援的電子郵件路由案例包括：</span><span class="sxs-lookup"><span data-stu-id="42333-186">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="42333-187">**協力廠商的合作夥伴和/或內部部署服務提供者**：您要評估的輸入連接器使用協力廠商提供者和/或您正在使用內部部署電子郵件安全性的解決方案。</span><span class="sxs-lookup"><span data-stu-id="42333-187">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you're using a solution for email security on-premises.</span></span>
- <span data-ttu-id="42333-188">**僅 Microsoft Exchange Online 保護**：您要評估的承租人會使用 Office 365 進行電子郵件安全性和郵件 Exchange (MX) 記錄點至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="42333-188">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="42333-189">電子郵件安全性閘道</span><span class="sxs-lookup"><span data-stu-id="42333-189">Email security gateway</span></span>

<span data-ttu-id="42333-190">如果您正在使用協力廠商電子郵件安全性閘道 (ESG) ，您必須知道提供者的名稱。</span><span class="sxs-lookup"><span data-stu-id="42333-190">If you're using a third-party email security gateway (ESG), you'll need to know the provider's name.</span></span> <span data-ttu-id="42333-191">如果您使用的是 ESG 內部部署或不受支援的廠商，您必須知道裝置的公用 IP 位址 (es) 。</span><span class="sxs-lookup"><span data-stu-id="42333-191">If you're using an ESG on-premises or non-supported vendors, you'll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="42333-192">支援的協力廠商合作夥伴包括：</span><span class="sxs-lookup"><span data-stu-id="42333-192">Supported third-party partners include:</span></span>

- <span data-ttu-id="42333-193">梭魚</span><span class="sxs-lookup"><span data-stu-id="42333-193">Barracuda</span></span>
- <span data-ttu-id="42333-194">IronPort</span><span class="sxs-lookup"><span data-stu-id="42333-194">IronPort</span></span>
- <span data-ttu-id="42333-195">Mimecast</span><span class="sxs-lookup"><span data-stu-id="42333-195">Mimecast</span></span>
- <span data-ttu-id="42333-196">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="42333-196">Proofpoint</span></span>
- <span data-ttu-id="42333-197">Sophos</span><span class="sxs-lookup"><span data-stu-id="42333-197">Sophos</span></span>
- <span data-ttu-id="42333-198">賽門鐵克</span><span class="sxs-lookup"><span data-stu-id="42333-198">Symantec</span></span>
- <span data-ttu-id="42333-199">走向微</span><span class="sxs-lookup"><span data-stu-id="42333-199">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="42333-200">範圍</span><span class="sxs-lookup"><span data-stu-id="42333-200">Scoping</span></span>

<span data-ttu-id="42333-201">您將能夠將評估的範圍限定為輸入連接器。</span><span class="sxs-lookup"><span data-stu-id="42333-201">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="42333-202">若未設定連接器，評估範圍將允許系統管理員從您租使用者中的任何使用者收集資料，以評估 Office 365 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="42333-202">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="42333-203">評估入門</span><span class="sxs-lookup"><span data-stu-id="42333-203">Get started with the evaluation</span></span>

<span data-ttu-id="42333-204">在 Office 365 安全性 & 規範中心 (https://protection.office.com/homepage) 從三個存取點，尋找 Microsoft Defender Office 365 評估設定卡：</span><span class="sxs-lookup"><span data-stu-id="42333-204">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="42333-205">威脅管理 > 儀表板</span><span class="sxs-lookup"><span data-stu-id="42333-205">Threat management > Dashboard</span></span>
- <span data-ttu-id="42333-206">威脅管理 > 原則</span><span class="sxs-lookup"><span data-stu-id="42333-206">Threat management > Policy</span></span>
- <span data-ttu-id="42333-207">報表 > 儀表板</span><span class="sxs-lookup"><span data-stu-id="42333-207">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="42333-208">設定評估</span><span class="sxs-lookup"><span data-stu-id="42333-208">Setting up the evaluation</span></span>

<span data-ttu-id="42333-209">當您為評估啟動設定流程之後，您會有兩個路由選項。</span><span class="sxs-lookup"><span data-stu-id="42333-209">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="42333-210">根據組織的郵件路由設定和評估需求，您可以選取使用協力廠商和/或內部部署服務提供者，還是只有 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="42333-210">Depending on your organization's mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="42333-211">如果您使用協力廠商的合作夥伴和/或內部部署服務提供者，您必須從下拉式功能表中選取廠商的名稱。</span><span class="sxs-lookup"><span data-stu-id="42333-211">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="42333-212">提供其他連接器相關的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="42333-212">Provide the other connector-related details.</span></span>

- <span data-ttu-id="42333-213">若 MX 記錄指向 Microsoft，而且您有 Exchange Online 信箱，請選取 [Microsoft Exchange Online]。</span><span class="sxs-lookup"><span data-stu-id="42333-213">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="42333-214">請複查您的設定，並視需要進行編輯。</span><span class="sxs-lookup"><span data-stu-id="42333-214">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="42333-215">然後，選取 [ **建立評估**]。</span><span class="sxs-lookup"><span data-stu-id="42333-215">Then, select **Create evaluation**.</span></span> <span data-ttu-id="42333-216">您應該會收到確認訊息，指出您已完成設定。</span><span class="sxs-lookup"><span data-stu-id="42333-216">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="42333-217">您的 Microsoft Defender for Office 365 評估報告每天會產生一次。</span><span class="sxs-lookup"><span data-stu-id="42333-217">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="42333-218">最多可能需要24小時的時間來填入資料。</span><span class="sxs-lookup"><span data-stu-id="42333-218">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="42333-219">Exchange 規則 (選用) </span><span class="sxs-lookup"><span data-stu-id="42333-219">Exchange rules (optional)</span></span>

<span data-ttu-id="42333-220">如果您有現有的閘道，啟用評估模式將會啟用連接器的增強篩選功能。</span><span class="sxs-lookup"><span data-stu-id="42333-220">If you have an existing gateway, enabling evaluation mode will activate enhanced filtering for connectors.</span></span> <span data-ttu-id="42333-221">這會變更傳入寄件者的 IP 位址，以提升篩選精確度。</span><span class="sxs-lookup"><span data-stu-id="42333-221">This improves filtering accuracy by altering the incoming sender IP address.</span></span> <span data-ttu-id="42333-222">這可能會變更篩選 verdicts，但如果您不是略過 Exchange Online Protection 則可能會變更特定郵件的 deliverability。</span><span class="sxs-lookup"><span data-stu-id="42333-222">This may change the filter verdicts and if you are not bypassing Exchange Online Protection this may alter deliverability for certain messages.</span></span> <span data-ttu-id="42333-223">在此情況下，您可能會想要暫時略過篩選以分析影響。</span><span class="sxs-lookup"><span data-stu-id="42333-223">In this case you might want to temporarily bypass filtering to analyze impact.</span></span> <span data-ttu-id="42333-224">若要略過，請流覽至 Exchange 系統管理中心，並建立 SCL-1 (的原則（如果您尚沒有一個) ）。</span><span class="sxs-lookup"><span data-stu-id="42333-224">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don't already have one).</span></span> <span data-ttu-id="42333-225">如需規則元件及其運作方式的詳細資訊，請參閱 Mail flow rules (transport rules) in Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="42333-225">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="42333-226">評估功能</span><span class="sxs-lookup"><span data-stu-id="42333-226">Evaluate capabilities</span></span>

<span data-ttu-id="42333-227">產生評估報告之後，請查看組織中的電子郵件和共同作業工作區中識別的高級威脅連結、高級威脅附件及可能的 impersonations 數目。</span><span class="sxs-lookup"><span data-stu-id="42333-227">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>

<span data-ttu-id="42333-228">試用期到期後，您可以繼續存取90天的報告。</span><span class="sxs-lookup"><span data-stu-id="42333-228">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="42333-229">不過，它不會收集任何其他資訊。</span><span class="sxs-lookup"><span data-stu-id="42333-229">However, it won't collect any more information.</span></span> <span data-ttu-id="42333-230">如果您想要在試用期到期之後繼續使用 microsoft defender Office 365，請確定您為[microsoft defender 購買付費訂閱 for Office 365 (Plan 2) ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。</span><span class="sxs-lookup"><span data-stu-id="42333-230">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="42333-231">您可以移至 **設定** 更新您的路由，也可以隨時關閉評估。</span><span class="sxs-lookup"><span data-stu-id="42333-231">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="42333-232">不過，如果您決定在關閉評估之後繼續評估，您必須重新執行相同的設定程式。</span><span class="sxs-lookup"><span data-stu-id="42333-232">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="42333-233">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="42333-233">Provide feedback</span></span>

<span data-ttu-id="42333-234">您的意見反應可協助我們在保護您的環境時免受高級攻擊。</span><span class="sxs-lookup"><span data-stu-id="42333-234">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="42333-235">分享產品功能和評估結果的經驗和印象。</span><span class="sxs-lookup"><span data-stu-id="42333-235">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="42333-236">選取 [ **提供意見** 反應]，讓我們知道您的想法。</span><span class="sxs-lookup"><span data-stu-id="42333-236">Select **Give feedback** to let us know what you think.</span></span>