---
title: 評估 Microsoft Defender for Office 365
description: 在評估模式中，Office 365 的 defender 為 Office 365 的電子郵件原則，會記錄 verdicts，例如惡意程式碼，但不會對郵件採取動作。
keywords: 評估 Office 365，Microsoft Defender for Office 365，Office 365 評估，嘗試 Office 365，Microsoft Defender，ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 54acf9d21e3dd935f8b87c6ee4a13ab30e7bc59e
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668070"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="8bf5e-104">評估 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8bf5e-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="8bf5e-105">評估 Microsoft Defender for Office 365 不久會是公開預覽。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-105">Evaluate Microsoft Defender for Office 365 will soon be in public preview.</span></span> <span data-ttu-id="8bf5e-106">在沒有服務等級協定的情況下提供此預覽版本。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-106">This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="8bf5e-107">某些功能可能不受支援，或可能具有有限的功能。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-107">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="8bf5e-108">進行完整的安全性產品評估，可協助您瞭解升級和購買的決策。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-108">Conducting a comprehensive security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="8bf5e-109">它可協助您嘗試安全性產品的功能，以評估其日常工作中的安全性操作小組的運作方式。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-109">It helps to try out the security product's capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="8bf5e-110">[Microsoft Defender For Office 365](office-365-atp.md)評估體驗旨在消除裝置和環境設定的複雜性，使您能夠專注于評估安全性解決方案的功能。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-110">The [Microsoft Defender for Office 365](office-365-atp.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of the security solution.</span></span> <span data-ttu-id="8bf5e-111">它只適用于電子郵件保護，而不是 SharePoint、Office 用戶端或小組。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-111">It only applies to email protection and not SharePoint, Office Clients, or Teams.</span></span>

<span data-ttu-id="8bf5e-112">如果您還沒有支援 Microsoft Defender for Office 365 的授權，您可以開始 [30 天的試用版評估](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) ，並測試 Office 365 安全性 & 規範中心 (中的功能 https://protection.office.com/homepage) 。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-112">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="8bf5e-113">您將會喜歡快速設定，必要時您可以輕鬆關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-113">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="8bf5e-114">評估的運作方式</span><span class="sxs-lookup"><span data-stu-id="8bf5e-114">How the evaluation works</span></span>

<span data-ttu-id="8bf5e-115">在評估模式中，Office 365 的 defender 為 Office 365 的電子郵件原則，會記錄 verdicts，例如惡意程式碼，但不會對郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-115">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don't act on messages.</span></span> <span data-ttu-id="8bf5e-116">您不需要變更 MX 記錄設定。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-116">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="8bf5e-117">使用評估模式時，會替您設定 [安全附件](atp-safe-attachments.md)、 [安全連結](atp-safe-links.md)和 [反網路釣魚模擬原則](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-117">With evaluation mode, [Safe Attachments](atp-safe-attachments.md), [Safe Links](atp-safe-links.md), and [anti-phishing impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are setup on your behalf.</span></span> <span data-ttu-id="8bf5e-118">所有的 Office 365 原則都是在後臺非強制模式中建立，對您看不到。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-118">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="8bf5e-119">在設定過程中，評估模式也會為 [連接器設定增強型篩選](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-119">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="8bf5e-120">它會透過保留 IP 位址和寄件者資訊，提高篩選精確度，當郵件透過電子郵件安全性閘道 (ESG) 在 Office 365 的前端時，就會遺失。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-120">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="8bf5e-121">這也會提升 Exchange Online Protection (EOP) 反垃圾郵件和反網路釣魚原則的篩選準確性。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-121">This also improves the filtering accuracy for your Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="8bf5e-122">若要將潛在的實際執行影響降至不支援的案例，您可以建立傳輸規則，將垃圾郵件信賴等級設定 (SCL) 設定為-1，以略過所有的 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-122">To minimize potential production impact on some unsupported scenarios, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="8bf5e-123">請參閱 [使用 EAC 建立郵件流程規則，設定](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)郵件的 SCL 的   詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-123">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="8bf5e-124">當評估模式已設定時，每日會更新一份報告，其中包含超過90天的資料量化，以量化已封鎖的郵件，並已執行 (例如「刪除」、「傳送至垃圾、隔離」) 等原則。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-124">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked had the policies been made and implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="8bf5e-125">報告是針對所有的 Defender for Office 365 和 EOP 偵測產生。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-125">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="8bf5e-126">它們會根據偵測技術匯總 (例如，模擬) ，並且可依時間範圍篩選。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-126">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="8bf5e-127">此外，您也可以根據需要建立郵件報告，以建立自訂透視或使用威脅瀏覽器深入瞭解郵件。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-127">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="8bf5e-128">透過簡化的設定體驗，您可以將重點放在：</span><span class="sxs-lookup"><span data-stu-id="8bf5e-128">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="8bf5e-129">執行評估</span><span class="sxs-lookup"><span data-stu-id="8bf5e-129">Running the evaluation</span></span>
- <span data-ttu-id="8bf5e-130">取得詳細報告</span><span class="sxs-lookup"><span data-stu-id="8bf5e-130">Getting a detailed report</span></span>
- <span data-ttu-id="8bf5e-131">分析動作報告</span><span class="sxs-lookup"><span data-stu-id="8bf5e-131">Analyzing the report for action</span></span>
- <span data-ttu-id="8bf5e-132">展示評估結果</span><span class="sxs-lookup"><span data-stu-id="8bf5e-132">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8bf5e-133">開始之前</span><span class="sxs-lookup"><span data-stu-id="8bf5e-133">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="8bf5e-134">授權</span><span class="sxs-lookup"><span data-stu-id="8bf5e-134">Licensing</span></span>

<span data-ttu-id="8bf5e-135">若要存取評估，您必須符合授權要求。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-135">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="8bf5e-136">下列任何授權均可運作：</span><span class="sxs-lookup"><span data-stu-id="8bf5e-136">Any of the following licenses will work:</span></span>

- <span data-ttu-id="8bf5e-137">適用於 Office 365 的 Microsoft Defender 方案 1</span><span class="sxs-lookup"><span data-stu-id="8bf5e-137">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="8bf5e-138">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="8bf5e-138">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="8bf5e-139">Microsoft 365 E5，Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="8bf5e-139">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="8bf5e-140">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="8bf5e-140">Office 365 E5</span></span>

<span data-ttu-id="8bf5e-141">如果您沒有其中一個授權，您必須取得試用版授權。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-141">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="8bf5e-142">試用</span><span class="sxs-lookup"><span data-stu-id="8bf5e-142">Trial</span></span>

<span data-ttu-id="8bf5e-143">若要取得 Microsoft Defender for Office 365 的試用版授權，您必須具有「 **帳單管理員」角色** 或「 **全域系統管理員」角色**。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-143">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="8bf5e-144">向具有全域系統管理員角色的使用者要求許可權。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-144">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="8bf5e-145">深入瞭解訂閱與授權</span><span class="sxs-lookup"><span data-stu-id="8bf5e-145">Learn about subscriptions and licenses</span></span>](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

<span data-ttu-id="8bf5e-146">當您擁有適當的角色後，建議的路徑是取得 Microsoft Defender for Office 365 的試用版授權 (方案 2) 在 Microsoft 365 系統管理中心，請移至帳單 > 購買服務。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-146">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="8bf5e-147">試用期包括30天的免費試用版，取得25個授權。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-147">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="8bf5e-148">[取得 Microsoft Defender For Office 365 的試用版 (方案 2) ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-148">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="8bf5e-149">您將會有30天的時段，其評估是用來監視和報告高級威脅。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-149">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="8bf5e-150">如果您想要完整的 Office 365 功能，您也可以選擇購買付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-150">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="8bf5e-151">角色</span><span class="sxs-lookup"><span data-stu-id="8bf5e-151">Roles</span></span>

<span data-ttu-id="8bf5e-152">在評估模式中，需要有 Exchange Online 角色才能設定 Office 365 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-152">Exchange Online roles are required to set up Defender for Office 365 in evaluation mode.</span></span> <span data-ttu-id="8bf5e-153">下列角色是必要的：</span><span class="sxs-lookup"><span data-stu-id="8bf5e-153">The following roles are needed:</span></span>

|<span data-ttu-id="8bf5e-154">工作</span><span class="sxs-lookup"><span data-stu-id="8bf5e-154">Task</span></span>|<span data-ttu-id="8bf5e-155">角色</span><span class="sxs-lookup"><span data-stu-id="8bf5e-155">Role</span></span>|
|---|---|
|<span data-ttu-id="8bf5e-156">取得免費試用版或購買 Microsoft Defender for Office 365 (方案 2) </span><span class="sxs-lookup"><span data-stu-id="8bf5e-156">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>|<span data-ttu-id="8bf5e-157">計費系統管理員角色或全域系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="8bf5e-157">Billing admin role OR Global admin role</span></span>|
|<span data-ttu-id="8bf5e-158">建立評估原則</span><span class="sxs-lookup"><span data-stu-id="8bf5e-158">Create evaluation policy</span></span>|<span data-ttu-id="8bf5e-159">遠端和公認的網域角色;安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="8bf5e-159">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="8bf5e-160">編輯評估原則</span><span class="sxs-lookup"><span data-stu-id="8bf5e-160">Edit evaluation policy</span></span>|<span data-ttu-id="8bf5e-161">遠端和公認的網域角色;安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="8bf5e-161">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="8bf5e-162">刪除評估原則</span><span class="sxs-lookup"><span data-stu-id="8bf5e-162">Delete evaluation policy</span></span>|<span data-ttu-id="8bf5e-163">遠端和公認的網域角色;安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="8bf5e-163">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="8bf5e-164">查看評估報告</span><span class="sxs-lookup"><span data-stu-id="8bf5e-164">View evaluation report</span></span>|<span data-ttu-id="8bf5e-165">安全性管理員角色或安全性讀者角色</span><span class="sxs-lookup"><span data-stu-id="8bf5e-165">Security admin role OR Security reader role</span></span>|
|

### <a name="enhanced-filtering"></a><span data-ttu-id="8bf5e-166">增強型篩選</span><span class="sxs-lookup"><span data-stu-id="8bf5e-166">Enhanced filtering</span></span>

<span data-ttu-id="8bf5e-167">您的 Exchange Online Protection 原則（如大量和垃圾郵件保護）將保持不變。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-167">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="8bf5e-168">郵件傳遞也會保持不變。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-168">Message delivery will also remain the same.</span></span> <span data-ttu-id="8bf5e-169">不過，評估會對連接器開啟增強型篩選功能，除非略過，否則會影響您的郵件流程和 Exchange Online Protection 原則。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-169">However, the evaluation turns on enhanced filtering for connectors, which will impact your mailflow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="8bf5e-170">連接器的增強篩選功能將允許承租人使用反欺騙保護。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-170">Enhanced filtering for connectors will allow tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="8bf5e-171">如果您使用的電子郵件安全性閘道 (ESG) 但未開啟「增強型連接器」篩選，則不支援反欺騙。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-171">Anti-spoofing is not supported if you're using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="8bf5e-172">URL</span><span class="sxs-lookup"><span data-stu-id="8bf5e-172">URLs</span></span>

<span data-ttu-id="8bf5e-173">郵件流程期間會引爆 URLs。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-173">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="8bf5e-174">如果您不想要引爆特定的 URLs，請適當地管理您的允許 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-174">If you don't want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="8bf5e-175">如需詳細資訊，請參閱 [Manage URLs In 承租人 Allow/封鎖清單](tenant-allow-block-list.md) 。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-175">See [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="8bf5e-176">電子郵件內文中的 URL 連結將不會換行，以減少對客戶的影響。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-176">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="8bf5e-177">電子郵件路由</span><span class="sxs-lookup"><span data-stu-id="8bf5e-177">Email routing</span></span>

<span data-ttu-id="8bf5e-178">您必須準備必要的相關詳細資料，以便設定您的電子郵件目前的路由，包括路由傳送郵件的輸入連接器的名稱。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-178">You need to prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="8bf5e-179">如果您只是使用 Exchange Online Protection，則不會有連接器。 [深入瞭解郵件流程和電子郵件路由](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="8bf5e-179">If you are just using Exchange Online Protection, you won't have a connector. [Learn about mail flow and email routing](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="8bf5e-180">支援的電子郵件路由案例包括：</span><span class="sxs-lookup"><span data-stu-id="8bf5e-180">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="8bf5e-181">**協力廠商的合作夥伴和/或內部部署服務提供者**：您要評估的輸入連接器使用協力廠商提供者和/或您正在使用內部部署電子郵件安全性的解決方案。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-181">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you're using a solution for email security on-premises.</span></span>
- <span data-ttu-id="8bf5e-182">**僅限 Microsoft Exchange Online Protection**：您要評估的承租人使用 Office 365 進行電子郵件安全性和郵件交換 (MX) 記錄指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-182">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="8bf5e-183">電子郵件安全性閘道</span><span class="sxs-lookup"><span data-stu-id="8bf5e-183">Email security gateway</span></span>

<span data-ttu-id="8bf5e-184">如果您正在使用協力廠商電子郵件安全性閘道 (ESG) ，您必須知道提供者的名稱。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-184">If you're using a third-party email security gateway (ESG), you'll need to know the provider's name.</span></span> <span data-ttu-id="8bf5e-185">如果您使用的是 ESG 內部部署或不受支援的廠商，您必須知道裝置的公用 IP 位址 (es) 。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-185">If you're using an ESG on-premises or non-supported vendors, you'll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="8bf5e-186">支援的協力廠商合作夥伴包括：</span><span class="sxs-lookup"><span data-stu-id="8bf5e-186">Supported third-party partners include:</span></span>

- <span data-ttu-id="8bf5e-187">梭魚</span><span class="sxs-lookup"><span data-stu-id="8bf5e-187">Barracuda</span></span>
- <span data-ttu-id="8bf5e-188">IronPort</span><span class="sxs-lookup"><span data-stu-id="8bf5e-188">IronPort</span></span>
- <span data-ttu-id="8bf5e-189">Mimecast</span><span class="sxs-lookup"><span data-stu-id="8bf5e-189">Mimecast</span></span>
- <span data-ttu-id="8bf5e-190">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="8bf5e-190">Proofpoint</span></span>
- <span data-ttu-id="8bf5e-191">Sophos</span><span class="sxs-lookup"><span data-stu-id="8bf5e-191">Sophos</span></span>
- <span data-ttu-id="8bf5e-192">賽門鐵克</span><span class="sxs-lookup"><span data-stu-id="8bf5e-192">Symantec</span></span>
- <span data-ttu-id="8bf5e-193">走向微</span><span class="sxs-lookup"><span data-stu-id="8bf5e-193">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="8bf5e-194">範圍</span><span class="sxs-lookup"><span data-stu-id="8bf5e-194">Scoping</span></span>

<span data-ttu-id="8bf5e-195">您將能夠將評估的範圍限定為輸入連接器。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-195">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="8bf5e-196">若未設定連接器，評估範圍將允許系統管理員從您租使用者中的任何使用者收集資料，以評估 Office 365 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-196">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="8bf5e-197">評估入門</span><span class="sxs-lookup"><span data-stu-id="8bf5e-197">Get started with the evaluation</span></span>

<span data-ttu-id="8bf5e-198">在 Office 365 安全性 & 合規性中心 (https://protection.office.com/homepage) 三個存取點中，尋找 Microsoft Defender For office 365 評估設定卡。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-198">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="8bf5e-199">威脅管理 > 儀表板</span><span class="sxs-lookup"><span data-stu-id="8bf5e-199">Threat management > Dashboard</span></span>
- <span data-ttu-id="8bf5e-200">威脅管理 > 原則</span><span class="sxs-lookup"><span data-stu-id="8bf5e-200">Threat management > Policy</span></span>
- <span data-ttu-id="8bf5e-201">報表 > 儀表板</span><span class="sxs-lookup"><span data-stu-id="8bf5e-201">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="8bf5e-202">設定評估</span><span class="sxs-lookup"><span data-stu-id="8bf5e-202">Setting up the evaluation</span></span>

<span data-ttu-id="8bf5e-203">當您為評估啟動設定流程之後，您會有兩個路由選項。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-203">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="8bf5e-204">根據組織的郵件路由設定和評估需求，您可以選擇是否使用協力廠商和/或內部部署服務提供者或僅限 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-204">Depending on your organization's mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="8bf5e-205">如果您使用協力廠商的合作夥伴和/或內部部署服務提供者，您必須從下拉式功能表中選取廠商的名稱。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-205">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="8bf5e-206">提供其他連接器相關的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-206">Provide the other connector-related details.</span></span>

- <span data-ttu-id="8bf5e-207">若 MX 記錄指向 Microsoft，而且您有 Exchange Online 信箱，請選取 [Microsoft Exchange Online]。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-207">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="8bf5e-208">請複查您的設定，並視需要進行編輯。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-208">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="8bf5e-209">然後，選取 [ **建立評估**]。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-209">Then, select **Create evaluation**.</span></span> <span data-ttu-id="8bf5e-210">您應該會收到確認訊息，指出您已完成設定。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-210">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="8bf5e-211">您的 Microsoft Defender for Office 365 評估報告每天產生一次。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-211">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="8bf5e-212">最多可能需要24小時的時間來填入資料。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-212">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="8bf5e-213">Exchange 規則 (選用) </span><span class="sxs-lookup"><span data-stu-id="8bf5e-213">Exchange rules (optional)</span></span>

<span data-ttu-id="8bf5e-214">如果您有現有的閘道，您可能想要略過篩選，因為它會啟用連接器的增強篩選，並變更傳入寄件者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-214">If you have an existing gateway, you might want to bypass filtering because it will activate enhanced filtering for connectors and alter the incoming sender IP address.</span></span> <span data-ttu-id="8bf5e-215">若要略過，請流覽至 Exchange 系統管理中心，並建立 SCL-1 (的原則（如果您尚沒有) ）。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-215">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don't already have one).</span></span> <span data-ttu-id="8bf5e-216">如需規則元件及其運作方式的詳細資訊，請參閱 Mail flow rules (transport rules) in Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-216">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="8bf5e-217">評估功能</span><span class="sxs-lookup"><span data-stu-id="8bf5e-217">Evaluate capabilities</span></span>

<span data-ttu-id="8bf5e-218">產生評估報告之後，請查看組織中的電子郵件和共同作業工作區中識別的高級威脅連結、高級威脅附件及可能的 impersonations 數目。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-218">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>

<span data-ttu-id="8bf5e-219">試用期到期後，您可以繼續存取90天的報告。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-219">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="8bf5e-220">不過，它不會收集任何其他資訊。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-220">However, it won't collect any more information.</span></span> <span data-ttu-id="8bf5e-221">如果您想要在試用期到期後繼續使用 Microsoft Defender for Office 365，請確定您 [購買了適用于 office 365 的 Microsoft defender 訂閱 (方案 2) ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-221">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="8bf5e-222">您可以在任何時間，移至 [ **設定** ] 以更新您的路由或關閉評估。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-222">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="8bf5e-223">不過，如果您決定在關閉評估之後繼續評估，您必須重新執行相同的設定程式。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-223">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="8bf5e-224">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="8bf5e-224">Provide feedback</span></span>

<span data-ttu-id="8bf5e-225">您的意見反應可協助我們在保護您的環境時免受高級攻擊。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-225">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="8bf5e-226">分享產品功能和評估結果的經驗和印象。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-226">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="8bf5e-227">選取 [ **提供意見** 反應]，讓我們知道您的想法。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-227">Select **Give feedback** to let us know what you think.</span></span>
