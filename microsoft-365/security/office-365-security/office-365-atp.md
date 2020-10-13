---
title: Office 365 進階威脅防護
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Office 365 進階威脅防護包括安全附件、安全連結、進階防網路釣魚工具、報告工具以及威脅情報功能。
ms.openlocfilehash: d66df7cca12b0ddb89dec32fcb96017457712f86
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431024"
---
# <a name="office-365-advanced-threat-protection-atp"></a><span data-ttu-id="b5a2a-103">Office 365 進階威脅防護（ATP）</span><span class="sxs-lookup"><span data-stu-id="b5a2a-103">Office 365 Advanced Threat Protection (ATP)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="b5a2a-104">本文適用於擁有 [Office 365 進階威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)的企業客戶。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="b5a2a-105">如果您使用 Outlook.com、Microsoft 365 家用版或 Microsoft 365 個人版，並且在尋找 Outlook 中的安全連結或安全附件的相關資訊，請參閱[適用於 Microsoft 365 訂閱者的進階 Outlook.com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-105">If you are using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safe Links or Safe Attachments in Outlook, see [Advanced Outlook.com security for Microsoft 365 subscribers](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="b5a2a-106">Office 365 進階威脅防護 (ATP) 可保護組織防範由電子郵件訊息、連結 (URL) 及共同作業工具所造成的惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-106">Office 365 Advanced Threat Protection (ATP) safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="b5a2a-107">ATP 包括：</span><span class="sxs-lookup"><span data-stu-id="b5a2a-107">ATP includes:</span></span>

- <span data-ttu-id="b5a2a-108">**[威脅防護原則](#configure-atp-policies)**：定義威脅防護原則，用來為組織設定適當的保護層級。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-108">**[Threat protection policies](#configure-atp-policies)**: Define threat-protection policies to set the appropriate level of protection for your organization.</span></span>

- <span data-ttu-id="b5a2a-109">**[報告](#view-office-365-atp-reports)**：檢視即時報告來監控組織中 ATP 的效能。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-109">**[Reports](#view-office-365-atp-reports)**: View real-time reports to monitor ATP performance in your organization.</span></span>

- <span data-ttu-id="b5a2a-110">**[威脅調查與回應功能](#use-threat-investigation-and-response-capabilities)**：使用先進的工具來調查、了解、模擬以及防止潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-110">**[Threat investigation and response capabilities](#use-threat-investigation-and-response-capabilities)**: Use leading-edge tools to investigate, understand, simulate, and prevent threats.</span></span>

- <span data-ttu-id="b5a2a-111">**[自動化調查及回應功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**：節省調查和減輕威脅的時間和精力。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-111">**[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**: Save time and effort investigating and mitigating threats.</span></span>

## <a name="getting-started"></a><span data-ttu-id="b5a2a-112">快速入門</span><span class="sxs-lookup"><span data-stu-id="b5a2a-112">Getting Started</span></span>

<span data-ttu-id="b5a2a-113">如果您剛開始使用 Office 365 進階威脅防護，或欲透過*實際操作* 來瞭解，則您可以使用本文作為參考資料，將初始 ATP 設定分成區塊、調查和查看報告，並從中受益。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-113">If you're new to Office 365 Advanced Threat Protection or learn best by *doing*, you may benefit from breaking initial ATP configuration into chunks, investigating, and viewing reports using this article as a reference.</span></span> <span data-ttu-id="b5a2a-114">以下是邏輯早期設定區塊:</span><span class="sxs-lookup"><span data-stu-id="b5a2a-114">Here are logical early configuration chunks:</span></span>

- <span data-ttu-id="b5a2a-115">設定名稱中含有「*反*」的所有專案。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-115">Configure everything with '*anti*' in the name.</span></span>
    - <span data-ttu-id="b5a2a-116">反惡意軟體</span><span class="sxs-lookup"><span data-stu-id="b5a2a-116">anti-malware</span></span>
    - <span data-ttu-id="b5a2a-117">反網路釣魚</span><span class="sxs-lookup"><span data-stu-id="b5a2a-117">anti-phishing</span></span>
    - <span data-ttu-id="b5a2a-118">反垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="b5a2a-118">anti-spam</span></span>
- <span data-ttu-id="b5a2a-119">設定名稱中含有「*安全*」的所有專案。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-119">Set up everything with '*safe*' in the name.</span></span>
    - <span data-ttu-id="b5a2a-120">安全連結</span><span class="sxs-lookup"><span data-stu-id="b5a2a-120">safe links</span></span>
    - <span data-ttu-id="b5a2a-121">安全附件</span><span class="sxs-lookup"><span data-stu-id="b5a2a-121">safe attachments</span></span>
- <span data-ttu-id="b5a2a-122">保護工作負載 (例如:</span><span class="sxs-lookup"><span data-stu-id="b5a2a-122">Defend the workloads (ex.</span></span> <span data-ttu-id="b5a2a-123">SharePoint Online、OneDrive 和 Teams)</span><span class="sxs-lookup"><span data-stu-id="b5a2a-123">SharePoint Online, OneDrive, and Teams)</span></span> 
- <span data-ttu-id="b5a2a-124">使用 [零時差自動清除] 進行保護</span><span class="sxs-lookup"><span data-stu-id="b5a2a-124">Protect with Zero-Hour auto purge</span></span>

<span data-ttu-id="b5a2a-125">若要透過實際操作來瞭解，請 [按一下這個連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-125">To learn by doing, [click this link](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide&preserve-view=true).</span></span> 

> [!NOTE]
> <span data-ttu-id="b5a2a-126">ATP 包含兩個不同的 [方案] 類型。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-126">ATP comes in two different Plan types.</span></span> <span data-ttu-id="b5a2a-127">如果您有「即時偵測」，則您具有 **方案 1** ，而如果你有「威脅瀏覽器」，則您具有 **方案 2**。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-127">You can tell if you have **Plan 1** if you have 'Real-time Detections', and **Plan 2**, if you have Threat Explorer.</span></span> <span data-ttu-id="b5a2a-128">您所看到的 [方案] 會影響您能看到的工具，因此請確定您瞭解您的 [方案]。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-128">The Plan you have influences the tools you will see, so be certain that you're aware of your Plan as you learn.</span></span>

## <a name="office-365-atp-plan-1-and-plan-2"></a><span data-ttu-id="b5a2a-129">Office 365 ATP 方案 1 與方案 2</span><span class="sxs-lookup"><span data-stu-id="b5a2a-129">Office 365 ATP Plan 1 and Plan 2</span></span>

<span data-ttu-id="b5a2a-130">下表摘要列出每個方案所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-130">The following table summarizes what's included in each plan.</span></span>

****

|<span data-ttu-id="b5a2a-131">Office 365 ATP 方案 1</span><span class="sxs-lookup"><span data-stu-id="b5a2a-131">Office 365 ATP Plan 1</span></span>|<span data-ttu-id="b5a2a-132">Office 365 ATP 方案 2</span><span class="sxs-lookup"><span data-stu-id="b5a2a-132">Office 365 ATP Plan 2</span></span>|
|---|---|
|<br/><span data-ttu-id="b5a2a-133">設定、保護和偵測功能：</span><span class="sxs-lookup"><span data-stu-id="b5a2a-133">Configuration, protection, and detection capabilities:</span></span> <ul><li>[<span data-ttu-id="b5a2a-134">安全附件</span><span class="sxs-lookup"><span data-stu-id="b5a2a-134">Safe Attachments</span></span>](atp-safe-attachments.md)</li><li>[<span data-ttu-id="b5a2a-135">安全連結</span><span class="sxs-lookup"><span data-stu-id="b5a2a-135">Safe Links</span></span>](atp-safe-links.md)</li><li>[<span data-ttu-id="b5a2a-136">適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="b5a2a-136">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)</li><li>[<span data-ttu-id="b5a2a-137">ATP 防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="b5a2a-137">ATP anti-phishing protection</span></span>](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[<span data-ttu-id="b5a2a-138">即時偵測</span><span class="sxs-lookup"><span data-stu-id="b5a2a-138">Real-time detections</span></span>](threat-explorer.md)</li></ul>|<span data-ttu-id="b5a2a-139">Office 365 ATP 方案 1 功能</span><span class="sxs-lookup"><span data-stu-id="b5a2a-139">Office 365 ATP Plan 1 capabilities</span></span><br/><span data-ttu-id="b5a2a-140">--- 以及 ---</span><span class="sxs-lookup"><span data-stu-id="b5a2a-140">--- plus ---</span></span><br/><span data-ttu-id="b5a2a-141">自動化、調查、補救和教育功能：</span><span class="sxs-lookup"><span data-stu-id="b5a2a-141">Automation, investigation, remediation, and education capabilities:</span></span></li><li>[<span data-ttu-id="b5a2a-142">威脅追蹤工具</span><span class="sxs-lookup"><span data-stu-id="b5a2a-142">Threat Trackers</span></span>](threat-trackers.md)</li><li>[<span data-ttu-id="b5a2a-143">威脅總管</span><span class="sxs-lookup"><span data-stu-id="b5a2a-143">Threat Explorer</span></span>](threat-explorer.md)</li><li>[<span data-ttu-id="b5a2a-144">自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="b5a2a-144">Automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[<span data-ttu-id="b5a2a-145">攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="b5a2a-145">Attack Simulator</span></span>](attack-simulator.md)</li></ul>|
|

- <span data-ttu-id="b5a2a-146">Office 365 E5、Office 365 A5、Microsoft 365 E5 安全性和 Microsoft 365 E5 中皆含有 Office 365 ATP 方案2。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-146">Office 365 ATP Plan 2 is included in Office 365 E5, Office 365 A5, Microsoft 365 E5 Security, and Microsoft 365 E5.</span></span>

- <span data-ttu-id="b5a2a-147">Office 365 ATP 方案 1 包含在 Microsoft 365 商務進階版中。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-147">Office 365 ATP Plan 1 is included in Microsoft 365 Business Premium.</span></span>

- <span data-ttu-id="b5a2a-148">Office 365 ATP 方案 1 和 Office 365 ATP 方案 2 各以某些訂閱附加元件的形式提供使用。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-148">Office 365 ATP Plan 1 and Office 365 ATP Plan 2 are each available as an add-on for certain subscriptions.</span></span> <span data-ttu-id="b5a2a-149">若要深入了解，請參閱 [ATP 方案中功能的可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-149">To learn more, see [Feature availability across ATP plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

- <span data-ttu-id="b5a2a-150">只有 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權的使用者才能使用[安全文件](safe-docs.md)功能 (不包含在 Office 365 ATP 方案中)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-150">The [Safe Documents](safe-docs.md) feature is only available to users with the Microsoft 365 E5 or Microsoft 365 E5 Security licenses (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="b5a2a-151">如果您目前的訂閱未包含 Office 365 ATP，請[與銷售人員連絡以開始試用](https://go.microsoft.com/fwlink/p/?LinkId=518644)，並了解 ATP 如何能幫助您的組織。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-151">If your current subscription does not include Office 365 ATP, [contact sales to start a trial](https://go.microsoft.com/fwlink/p/?LinkId=518644), and see how ATP can work for your organization.</span></span>

## <a name="configure-atp-policies"></a><span data-ttu-id="b5a2a-152">設定 ATP 原則</span><span class="sxs-lookup"><span data-stu-id="b5a2a-152">Configure ATP policies</span></span>

<span data-ttu-id="b5a2a-153">有了 Office 365 ATP，貴組織的安全性小組就能在安全性與合規性中心中定義原則來設定防護 (請移至[https://protection.office.com](https://protection.office.com)  >  [威脅管理]\*\*\*\*  >  [原則]\*\*\*\*。)</span><span class="sxs-lookup"><span data-stu-id="b5a2a-153">With Office 365 ATP, your organization's security team can configure protection by defining policies in the Security & Compliance Center (Go to [https://protection.office.com](https://protection.office.com) > **Threat management** > **Policy**.)</span></span>

> [!TIP]
> <span data-ttu-id="b5a2a-154">如需定義的原則快速清單，請參閱[防範威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-154">For a quick list of policies to define, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="advanced-threat-protection-policies"></a><span data-ttu-id="b5a2a-155">進階威脅防護原則</span><span class="sxs-lookup"><span data-stu-id="b5a2a-155">Advanced Threat Protection Policies</span></span>

<span data-ttu-id="b5a2a-156">為您組織定義的原則會決定預先定義之威脅的行為和保護層級。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-156">The policies that are defined for your organization determine the behavior and protection level for predefined threats.</span></span> <span data-ttu-id="b5a2a-157">原則選項極具彈性。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-157">Policy options are extremely flexible.</span></span> <span data-ttu-id="b5a2a-158">例如，組織的安全性小組也可以在使用者、組織、收件者和網域層級設定微調的威脅防護。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-158">For example, your organization's security team can set fine-grained threat protection at the user, organization, recipient, and domain level.</span></span> <span data-ttu-id="b5a2a-159">因為新威脅及挑戰每天都會出現，請務必定期檢閱您的原則。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-159">It is important to review your policies regularly because new threats and challenges emerge daily.</span></span>

- <span data-ttu-id="b5a2a-160">**[安全附件](atp-safe-attachments.md)**：透過檢查電子郵件附件中的惡意內容，提供零時差保護，以保護您的郵件系統。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-160">**[Safe Attachments](atp-safe-attachments.md)**: Provides zero-day protection to safeguard your messaging system, by checking email attachments for malicious content.</span></span> <span data-ttu-id="b5a2a-161">它會將沒有病毒/惡意程式碼簽章的所有郵件與附件路由傳送至特殊的環境，然後使用機器學習和分析技術來偵測惡意意圖。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-161">It routes all messages and attachments that do not have a virus/malware signature to a special environment, and then uses machine learning and analysis techniques to detect malicious intent.</span></span> <span data-ttu-id="b5a2a-162">如果找不到任何可疑的活動，便會將郵件轉寄到信箱。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-162">If no suspicious activity is found, the message is forwarded to the mailbox.</span></span> <span data-ttu-id="b5a2a-163">若要深入了解，請參閱[設定安全附件原則](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-163">To learn more, see [Set up Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

- <span data-ttu-id="b5a2a-164">**[安全連結](atp-safe-links.md)**：提供 URL 的點擊時驗證 (例如在電子郵件訊息和 Office 檔案中)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-164">**[Safe Links](atp-safe-links.md)**: Provides time-of-click verification of URLs, for example, in emails messages and Office files.</span></span> <span data-ttu-id="b5a2a-165">保護會持續進行，並在您郵件和 Office 環境間套用。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-165">Protection is ongoing and applies across your messaging and Office environment.</span></span> <span data-ttu-id="b5a2a-166">每次按一下連結時掃描：安全連結仍保持可存取，並且以動態方式封鎖惡意連結。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-166">Links are scanned for each click: safe links remain accessible and malicious links are dynamically blocked.</span></span> <span data-ttu-id="b5a2a-167">若要深入了解，請參閱[設定安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-167">To learn more, see [Set up Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="b5a2a-168">**[適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)**：透過找出並封鎖小組網站和文件庫中的惡意檔案，在使用者共同作業及共用檔案時保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-168">**[ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)**: Protects your organization when users collaborate and share files, by identifying and blocking malicious files in team sites and document libraries.</span></span> <span data-ttu-id="b5a2a-169">若要深入了解，請參閱[為 SharePoint、OneDrive 和 Microsoft Teams 開啟 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-169">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

- <span data-ttu-id="b5a2a-170">**[ATP 防網路釣魚保護](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**：偵測模擬使用者和內部或自訂網域的嘗試。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-170">**[ATP anti-phishing protection](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**: Detects attempts to impersonate your users and internal or custom domains.</span></span> <span data-ttu-id="b5a2a-171">適用於電腦學習模型和進階模擬偵測演算法，以避免網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-171">It applies machine learning models and advanced impersonation-detection algorithms to avert phishing attacks.</span></span> <span data-ttu-id="b5a2a-172">若要深入了解，請參閱[在 Office 365 中設定 ATP 防網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-172">To learn more, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="view-office-365-atp-reports"></a><span data-ttu-id="b5a2a-173">查看 Office 365 ATP 報告</span><span class="sxs-lookup"><span data-stu-id="b5a2a-173">View Office 365 ATP reports</span></span>

<span data-ttu-id="b5a2a-174">Office 365 ATP 包含進階的[報告儀表板](view-reports-for-atp.md)以監控 ATP 效能。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-174">Office 365 ATP includes an advanced [reporting dashboard](view-reports-for-atp.md) to monitor your ATP performance.</span></span> <span data-ttu-id="b5a2a-175">您可以在安全性與合規性中心的 [報告] \*\*\*\* >  [儀表板]\*\*\*\* 存取它。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-175">You can access it at **Reports** > **Dashboard** in the Security & Compliance Center.</span></span>

<span data-ttu-id="b5a2a-176">報告會即時更新，提供您最新的深入解析。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-176">Reports update in real-time, providing you with the latest insights.</span></span> <span data-ttu-id="b5a2a-177">這些報告也提供建議並警示您即將發生的潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-177">These reports also provide recommendations and alert you to imminent threats.</span></span> <span data-ttu-id="b5a2a-178">預先定義的報告包括下列：</span><span class="sxs-lookup"><span data-stu-id="b5a2a-178">Predefined reports include the following:</span></span>

- [<span data-ttu-id="b5a2a-179">威脅總管 (或即時偵測)</span><span class="sxs-lookup"><span data-stu-id="b5a2a-179">Threat Explorer (or real-time detections)</span></span>](threat-explorer.md)

- [<span data-ttu-id="b5a2a-180">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="b5a2a-180">Threat protection status report</span></span>](view-reports-for-atp.md#threat-protection-status-report)

- [<span data-ttu-id="b5a2a-181">進階威脅防護檔案類型報告</span><span class="sxs-lookup"><span data-stu-id="b5a2a-181">Advanced Threat Protection file types report</span></span>](view-reports-for-atp.md#advanced-threat-protection-file-types-report)

- [<span data-ttu-id="b5a2a-182">進階威脅防護郵件處置報告</span><span class="sxs-lookup"><span data-stu-id="b5a2a-182">Advanced Threat Protection message disposition report</span></span>](view-reports-for-atp.md#advanced-threat-protection-message-disposition-report)

- <span data-ttu-id="b5a2a-183">... 還有更多功能。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-183">... and several more.</span></span>

## <a name="use-threat-investigation-and-response-capabilities"></a><span data-ttu-id="b5a2a-184">使用威脅調查及回應功能</span><span class="sxs-lookup"><span data-stu-id="b5a2a-184">Use threat investigation and response capabilities</span></span>

<span data-ttu-id="b5a2a-185">Office 365 ATP 方案 2 中包含業界最佳[威脅調查及回應工具](office-365-ti.md)，可讓組織的安全性小組預期、了解和防止惡意攻擊。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-185">Office 365 ATP Plan 2 includes best-of-class [threat investigation and response tools](office-365-ti.md) that enable your organization's security team to anticipate, understand, and prevent malicious attacks.</span></span>

- <span data-ttu-id="b5a2a-186">**[威脅追蹤工具](threat-trackers.md)** 提供有關戰勝網路安全性問題的最新情報。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-186">**[Threat trackers](threat-trackers.md)** provide the latest intelligence on prevailing cybersecurity issues.</span></span> <span data-ttu-id="b5a2a-187">例如，您可以檢視有關最新惡意程式碼的資訊，並在它成為組織的實際威脅之前便採取措施。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-187">For example, you can view information about the latest malware, and take countermeasures before it becomes an actual threat to your organization.</span></span> <span data-ttu-id="b5a2a-188">可用的追蹤器包括：[值得注意的追蹤器](threat-trackers.md#noteworthy-trackers)、[趨勢追蹤器](threat-trackers.md#trending-trackers)、[追蹤的查詢](threat-trackers.md#tracked-queries)和[已儲存的查詢](threat-trackers.md#saved-queries)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-188">Available trackers include [Noteworthy trackers](threat-trackers.md#noteworthy-trackers), [Trending trackers](threat-trackers.md#trending-trackers), [Tracked queries](threat-trackers.md#tracked-queries), and [Saved queries](threat-trackers.md#saved-queries).</span></span>

- <span data-ttu-id="b5a2a-189">**[威脅總管 (或即時偵測)](threat-explorer.md)** (也稱為檔案總管) 是即時的報告，可讓您識別並分析最近的威脅。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-189">**[Threat Explorer (or real-time detections)](threat-explorer.md)** (also referred to as Explorer) is a real-time report that allows you to identify and analyze recent threats.</span></span> <span data-ttu-id="b5a2a-190">您可以設定檔案總管來顯示自訂期間的資料。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-190">You can configure Explorer to show data for custom periods.</span></span>

- <span data-ttu-id="b5a2a-191">**[攻擊模擬器](attack-simulator.md)** 可讓您在組織中執行真實化攻擊案例以找出漏洞。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-191">**[Attack Simulator](attack-simulator.md)** allows you to run realistic attack scenarios in your organization to identify vulnerabilities.</span></span> <span data-ttu-id="b5a2a-192">目前攻擊類型的模擬已可供使用，包括魚叉式網路釣魚憑證竊取和附件攻擊，以及密碼噴濺和暴力密碼破解攻擊等。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-192">Simulations of current types of attacks are available, including spear phishing credential harvest and attachment attacks, and password spray and brute force password attacks.</span></span>

## <a name="save-time-with-automated-investigation-and-response"></a><span data-ttu-id="b5a2a-193">利用自動調查及回應節省時間</span><span class="sxs-lookup"><span data-stu-id="b5a2a-193">Save time with automated investigation and response</span></span>

<span data-ttu-id="b5a2a-194">(**新增！**) 調查潛在的網路攻擊時，時間是關鍵。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-194">(**NEW!**) When you are investigating a potential cyberattack, time is of the essence.</span></span> <span data-ttu-id="b5a2a-195">愈快找出並減輕威脅，您組織的處境會愈好。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-195">The sooner you can identify and mitigate threats, the better off your organization will be.</span></span> <span data-ttu-id="b5a2a-196">[自動化調查和回應](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) 功能包含一組可以自動啟動 (例如當警示觸發時) 或手動啟動 (例如從檔案總管中的檢視) 的安全性劇本。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-196">[Automated investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) capabilities include a set of security playbooks that can be launched automatically, such as when an alert is triggered, or manually, such as from a view in Explorer.</span></span> <span data-ttu-id="b5a2a-197">AIR 可以在緩和威脅方面有效也有效率地節省您安全性作業小組的時間和精力。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-197">AIR can save your security operations team time and effort in mitigating threats effectively and efficiently.</span></span> <span data-ttu-id="b5a2a-198">若要深入了解，請參閱 [Office 365 中的AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-198">To learn more, see [AIR in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span>

## <a name="permissions-required-to-use-atp-features"></a><span data-ttu-id="b5a2a-199">使用 ATP 功能所需的權限</span><span class="sxs-lookup"><span data-stu-id="b5a2a-199">Permissions required to use ATP features</span></span>

<span data-ttu-id="b5a2a-200">若要存取安全性與合規性中心的 ATP 功能，您必須獲指派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-200">To access ATP features in the Security & Compliance Center, you must be assigned an appropriate role.</span></span> <span data-ttu-id="b5a2a-201">下表包括一些範例：</span><span class="sxs-lookup"><span data-stu-id="b5a2a-201">The following table includes some examples:</span></span>

|<span data-ttu-id="b5a2a-202">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="b5a2a-202">Role or role group</span></span>|<span data-ttu-id="b5a2a-203">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="b5a2a-203">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="b5a2a-204">全域系統管理員 (可在 Azure Active Directory 或安全性與合規性中心指派)</span><span class="sxs-lookup"><span data-stu-id="b5a2a-204">global administrator (this can be assigned in either Azure Active Directory or in the Security & Compliance Center)</span></span>|[<span data-ttu-id="b5a2a-205">關於 Microsoft 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="b5a2a-205">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="b5a2a-206">安全性系統管理員 (可在 Azure Active Directory 或安全性與合規性中心指派)</span><span class="sxs-lookup"><span data-stu-id="b5a2a-206">Security Administrator (this can be assigned in either Azure Active Directory or the Security & Compliance Center)</span></span>|[<span data-ttu-id="b5a2a-207">Azure Active Directory 中的系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="b5a2a-207">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[<span data-ttu-id="b5a2a-208">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="b5a2a-208">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)|
|<span data-ttu-id="b5a2a-209">Exchange Online 組織管理 (這是在 Exchange Online 中指派)</span><span class="sxs-lookup"><span data-stu-id="b5a2a-209">Exchange Online Organization Management (this is assigned in Exchange Online)</span></span>|[<span data-ttu-id="b5a2a-210">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="b5a2a-210">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [<span data-ttu-id="b5a2a-211">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5a2a-211">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|<span data-ttu-id="b5a2a-212">搜尋和清除 (僅能在安全性與合規性中心指派)</span><span class="sxs-lookup"><span data-stu-id="b5a2a-212">Search and Purge (this is assigned only in the Security & Compliance Center)</span></span>|[<span data-ttu-id="b5a2a-213">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="b5a2a-213">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)|

<span data-ttu-id="b5a2a-214">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-214">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-office-365-atp"></a><span data-ttu-id="b5a2a-215">取得 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b5a2a-215">Get Office 365 ATP</span></span>

<span data-ttu-id="b5a2a-216">Office 365 ATP 包含在某些訂閱中，例如 Microsoft 365 E5、Office 365 E5、Office 365 A5 和 Microsoft 365 商務進階版。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-216">Office 365 ATP is included in certain subscriptions, such as Microsoft 365 E5, Office 365 E5, Office 365 A5, and Microsoft 365 Business Premium.</span></span> <span data-ttu-id="b5a2a-217">如果您的訂閱不包含 Office 365 ATP，您可以以附加元件形式為特定訂閱購買 ATP 方案 1 或 ATP 方案 2。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-217">If your subscription does not include Office 365 ATP, you can purchase ATP Plan 1 or ATP Plan 2 as an add-on to certain subscriptions.</span></span> <span data-ttu-id="b5a2a-218">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="b5a2a-218">To learn more, see the following resources:</span></span>

- <span data-ttu-id="b5a2a-219">[Office 365 進階威脅防護 (ATP) 可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)，以取得包含 ATP 方案的訂閱清單。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-219">[Office 365 Advanced Threat Protection availability](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) for a list of subscriptions that include ATP plans.</span></span>

- <span data-ttu-id="b5a2a-220">[各進階威脅防護 (ATP) 計劃中可用的功能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)，以取得方案 1 和 2 中包含的功能清單。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-220">[Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) for a list of features included in Plan 1 and 2.</span></span>

- <span data-ttu-id="b5a2a-221">[取得適合的 Office 365 進階威脅防護](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)，以比較方案及購買 Office 365 ATP。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-221">[Get the right Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) to compare plans and purchase Office 365 ATP.</span></span>

- [<span data-ttu-id="b5a2a-222">開始免費試用</span><span class="sxs-lookup"><span data-stu-id="b5a2a-222">Start a free trial</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a><span data-ttu-id="b5a2a-223">Office 365 ATP 中的新功能</span><span class="sxs-lookup"><span data-stu-id="b5a2a-223">New features in Office 365 ATP</span></span>

<span data-ttu-id="b5a2a-224">新功能會持續新增至 Office 365 ATP。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-224">New features are added to Office 365 ATP continually.</span></span> <span data-ttu-id="b5a2a-225">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="b5a2a-225">To learn more, see the following resources:</span></span>

- <span data-ttu-id="b5a2a-226">[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)提供開發中和正在推出的新功能清單。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-226">[Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) provides a list of new features in development and rolling out.</span></span>

- <span data-ttu-id="b5a2a-227">[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)描述各 ATP 方案的功能和可用性。</span><span class="sxs-lookup"><span data-stu-id="b5a2a-227">[Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) describes features and availability across ATP plans.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5a2a-228">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b5a2a-228">See also</span></span>

- [<span data-ttu-id="b5a2a-229">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="b5a2a-229">Microsoft Threat Protection</span></span>](../mtp/microsoft-threat-protection.md)

- [<span data-ttu-id="b5a2a-230">Microsoft 威脅防護中的自動化調查及回應 (AIR)</span><span class="sxs-lookup"><span data-stu-id="b5a2a-230">Automated investigation and response (AIR) in Microsoft Threat Protection</span></span>](../mtp/mtp-autoir.md)
