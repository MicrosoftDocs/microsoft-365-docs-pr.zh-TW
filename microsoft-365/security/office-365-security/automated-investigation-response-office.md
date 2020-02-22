---
title: 自動化的調查和 Office 365 中的回應 （空調）
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 在 Office 365 進階威脅防護計劃 2 中，取得自動化調查及回應能力的概觀。
ms.openlocfilehash: 436d70934e32f8609d35532188ac71cbd590c345
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228579"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="714c2-103">自動化的調查和 Office 365 中的回應 （空調）</span><span class="sxs-lookup"><span data-stu-id="714c2-103">Automated investigation and response (AIR) in Office 365</span></span>

<span data-ttu-id="714c2-104">為會觸發安全性警訊，它會高達您查看這些提醒，並採取步驟來保護您的組織的安全性作業小組。</span><span class="sxs-lookup"><span data-stu-id="714c2-104">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="714c2-105">有時候，安全性作業小組可以覺得負荷量，便會觸發警示。</span><span class="sxs-lookup"><span data-stu-id="714c2-105">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="714c2-106">自動化的調查和 Office 365 中的回應 （空調） 功能可協助。</span><span class="sxs-lookup"><span data-stu-id="714c2-106">Automated investigation and response (AIR) capabilities in Office 365 can help.</span></span> <span data-ttu-id="714c2-107">空調可讓您操作更有效率的安全性作業小組。</span><span class="sxs-lookup"><span data-stu-id="714c2-107">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="714c2-108">空調功能在今日的熟知威脅的回應中包含自動化的調查程序。</span><span class="sxs-lookup"><span data-stu-id="714c2-108">AIR capabilities include automated investigation processes in response to well known threats that exist today.</span></span> <span data-ttu-id="714c2-109">適當的補救動作等候核准，讓您回應偵測到的威脅的安全性作業小組。</span><span class="sxs-lookup"><span data-stu-id="714c2-109">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span> 

<span data-ttu-id="714c2-110">本文提供空調和其元件的概觀。</span><span class="sxs-lookup"><span data-stu-id="714c2-110">This article provides an overview of AIR and its components.</span></span> <span data-ttu-id="714c2-111">當您準備好要開始使用空調時，請參閱[自動調查及回應 Office 365 中的威脅](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="714c2-111">When you're ready to get started using AIR, see [Automatically investigate and respond to threats in Office 365](office-365-air.md).</span></span>

> [!TIP]
> <span data-ttu-id="714c2-112">您有 Microsoft 365 E5 或 Microsoft 365 E3 以及身分識別與威脅防護產品？</span><span class="sxs-lookup"><span data-stu-id="714c2-112">Do you have Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection?</span></span> <span data-ttu-id="714c2-113">考慮嘗試 [Microsoft 威脅防護](../mtp/microsoft-threat-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="714c2-113">Consider trying [Microsoft Threat Protection](../mtp/microsoft-threat-protection.md).</span></span>

## <a name="at-a-high-level"></a><span data-ttu-id="714c2-114">在高層級</span><span class="sxs-lookup"><span data-stu-id="714c2-114">At a high level</span></span>

<span data-ttu-id="714c2-115">為會觸發警訊，安全性 playbooks 會進入效果。</span><span class="sxs-lookup"><span data-stu-id="714c2-115">As alerts are triggered, security playbooks go into effect.</span></span> <span data-ttu-id="714c2-116">根據情況而異，就可以開始[自動的調查程序](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。</span><span class="sxs-lookup"><span data-stu-id="714c2-116">Depending on the situation, an [automated investigation process](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) can begin.</span></span> <span data-ttu-id="714c2-117">期間和之後自動調查，被建議的[修復動作](air-remediation-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="714c2-117">During and after an automated investigation, [remediation actions](air-remediation-actions.md) are recommended.</span></span> <span data-ttu-id="714c2-118">Office 365 進階威脅防護中自動不採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="714c2-118">No actions are taken automatically in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="714c2-119">您的安全性操作小組評論，然後再[核准或拒絕每個修復動作](air-remediation-actions.md#approve-or-reject-pending-actions)，並完成時，每個調查完成。</span><span class="sxs-lookup"><span data-stu-id="714c2-119">Your security operations team reviews, and then [approves or rejects each remediation action](air-remediation-actions.md#approve-or-reject-pending-actions), and when this is done, each investigation completes.</span></span> <span data-ttu-id="714c2-120">所有這些活動追蹤和檢視位於 Office 365 安全性 & 合規性中心 （請參閱[檢視調查的詳細資料](air-view-investigation-results.md#view-details-of-an-investigation)）。</span><span class="sxs-lookup"><span data-stu-id="714c2-120">All of these activities are tracked and viewable in the Office 365 Security & Compliance Center (see [View details of an investigation](air-view-investigation-results.md#view-details-of-an-investigation)).</span></span>

<span data-ttu-id="714c2-121">下列各節提供更多詳細資訊提醒、 安全性 playbooks 和空調的巨集指令中的範例。</span><span class="sxs-lookup"><span data-stu-id="714c2-121">The following sections provide more details about alerts, security playbooks, and examples of AIR in action.</span></span>

## <a name="alerts"></a><span data-ttu-id="714c2-122">警示</span><span class="sxs-lookup"><span data-stu-id="714c2-122">Alerts</span></span>

<span data-ttu-id="714c2-123">[提醒](../../compliance/alert-policies.md#viewing-alerts)代表觸發程序適用於安全性事件回應作業小組工作流程。</span><span class="sxs-lookup"><span data-stu-id="714c2-123">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="714c2-124">排列優先順序的調查，同時確保沒有威脅 unaddressed 提醒右組是一項挑戰。</span><span class="sxs-lookup"><span data-stu-id="714c2-124">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="714c2-125">時以手動方式執行提醒到調查，安全性作業小組必須搜尋，並與相互關聯實體 （例如內容、 裝置及使用者） 威脅的風險。</span><span class="sxs-lookup"><span data-stu-id="714c2-125">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (such as content, devices and users) at risk from threats.</span></span> <span data-ttu-id="714c2-126">這類任務及工作流程可很耗時及牽涉到多個工具和系統。</span><span class="sxs-lookup"><span data-stu-id="714c2-126">Such tasks and workflows can be very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="714c2-127">空調、 調查與 Office 365 安全性事件回應會自動完成察覺主要的安全性與威脅管理警報自動觸發安全性回應 playbooks。</span><span class="sxs-lookup"><span data-stu-id="714c2-127">With AIR, investigation and response for Office 365 security events are automated by having key security and threat management alerts trigger security response playbooks automatically.</span></span> 

<span data-ttu-id="714c2-128">目前的空調，從下列幾種類型的警示原則中產生警示，可自動調查：</span><span class="sxs-lookup"><span data-stu-id="714c2-128">Currently for AIR, alerts generated from the following kinds of alert policies are auto-investigated:</span></span>  

- <span data-ttu-id="714c2-129">偵測到有潛在的惡意 URL 點擊</span><span class="sxs-lookup"><span data-stu-id="714c2-129">A potentially malicious URL click was detected</span></span>
- <span data-ttu-id="714c2-130">報告的釣魚程式 \* 作為使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="714c2-130">Email reported by user as phish\*</span></span>
- <span data-ttu-id="714c2-131">電子郵件包含惡意程式碼傳遞 \* 後移除</span><span class="sxs-lookup"><span data-stu-id="714c2-131">Email messages containing malware removed after delivery\*</span></span>
- <span data-ttu-id="714c2-132">電子郵件訊息包含傳遞 \* 後移除的釣魚程式 Url</span><span class="sxs-lookup"><span data-stu-id="714c2-132">Email messages containing phish URLs removed after delivery\*</span></span>
- <span data-ttu-id="714c2-133">傳送模式偵測到可疑的電子郵件#</span><span class="sxs-lookup"><span data-stu-id="714c2-133">Suspicious email sending patterns detected#</span></span>
- <span data-ttu-id="714c2-134">使用者限制而無法傳送電子郵件#</span><span class="sxs-lookup"><span data-stu-id="714c2-134">User restricted from sending email#</span></span>

> [!NOTE]
> <span data-ttu-id="714c2-135">以星號 （*） 標記的警示關閉的電子郵件通知與指派安全性 & 合規性中心，各自的警示原則*提示資訊\*嚴重性。</span><span class="sxs-lookup"><span data-stu-id="714c2-135">The alerts marked with an asterisk (\*) are assigned an *Informational* severity in the respective alert policies within the Security & Compliance Center, with email notifications turned off.</span></span> <span data-ttu-id="714c2-136">電子郵件通知可以開啟透過[警示原則設定](../../compliance/alert-policies.md#alert-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="714c2-136">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span> <span data-ttu-id="714c2-137">以雜湊 （#） 標記的提醒是通常可公開預覽 playbooks 相關聯的提醒。</span><span class="sxs-lookup"><span data-stu-id="714c2-137">Alerts marked with a hash (#) are generally available alerts associated with public preview playbooks.</span></span>

<span data-ttu-id="714c2-138">若要檢視提醒，安全性 & 合規性中心中，選擇 [**提醒** > **檢視警示**。</span><span class="sxs-lookup"><span data-stu-id="714c2-138">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="714c2-139">選取警示若要檢視其詳細資料，並從該處，使用的**檢視調查**連結移至對應的[調查](air-view-investigation-results.md#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="714c2-139">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](air-view-investigation-results.md#investigation-graph).</span></span>  

> [!NOTE]
> <span data-ttu-id="714c2-140">預設為 [警示] 檢視中隱藏資訊警示。</span><span class="sxs-lookup"><span data-stu-id="714c2-140">Informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="714c2-141">若要查看它們，請變更篩選功能，包括資訊警示的警示。</span><span class="sxs-lookup"><span data-stu-id="714c2-141">To see them, change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="714c2-142">如果您的組織管理您的安全性提醒透過警示管理系統、 服務管理系統或安全性資訊和事件管理 (SIEM) 的系統，您可以透過 [電子郵件通知，或是透過[Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)該系統傳送 Office 365 警示。</span><span class="sxs-lookup"><span data-stu-id="714c2-142">If your organization manages your security alerts through an alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send Office 365 alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="714c2-143">透過電子郵件或 API 調查警示通知包含連結來存取安全性 & 合規性中心，啟用快速瀏覽到調查指派的安全性系統管理員中的警示。</span><span class="sxs-lookup"><span data-stu-id="714c2-143">The investigation alert notifications via email or API include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![連結至調查的提醒](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="714c2-145">安全性 playbooks</span><span class="sxs-lookup"><span data-stu-id="714c2-145">Security playbooks</span></span>

<span data-ttu-id="714c2-146">安全性 playbooks 所面臨的自動化 Office 進階威脅防護和 Microsoft 威脅防護中的核心的後端原則。</span><span class="sxs-lookup"><span data-stu-id="714c2-146">Security playbooks are back-end policies that are at the heart of automation in Office Advanced Threat Protection and Microsoft Threat Protection.</span></span> <span data-ttu-id="714c2-147">根據常見的真實世界的安全性案例 playbooks 空調中所提供且開發安全性為基礎的意見反應安全性作業小組。</span><span class="sxs-lookup"><span data-stu-id="714c2-147">The security playbooks provided in AIR are based on common real-world security scenarios and developed based on feedback from Security Operations teams.</span></span> <span data-ttu-id="714c2-148">當組織內會觸發特定的警示時，就會自動啟動安全性 playbook。</span><span class="sxs-lookup"><span data-stu-id="714c2-148">A security playbook is launched automatically when specific alerts are triggered within your organization.</span></span> <span data-ttu-id="714c2-149">之後會觸發警示，相關聯的 playbook 執行自動化調查及回應 （空調） 系統。</span><span class="sxs-lookup"><span data-stu-id="714c2-149">Once the alert triggers, the associated playbook is run by the Automated Investigation and Response (AIR) system.</span></span> <span data-ttu-id="714c2-150">調查步驟透過分析根據該特定警示 playbook，查看所有關聯的中繼資料 （包括電子郵件、 使用者、 主旨、 寄件者等等） 的提醒。</span><span class="sxs-lookup"><span data-stu-id="714c2-150">The investigation steps through analysis of the alert based on that particular alert's playbook, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="714c2-151">根據調查 playbook 的結果，空調建議一組的動作，貴組織的安全性小組可以採取控制項，並降低威脅。</span><span class="sxs-lookup"><span data-stu-id="714c2-151">Based on the investigation playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="714c2-152">您會看到與空調安全性 playbooks 被設計來處理最常見的威脅組織遇到今天的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="714c2-152">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations encounter today with email.</span></span> <span data-ttu-id="714c2-153">他們根據安全性作業和事件回應小組，包括協助防禦 Microsoft 和我們的客戶資產的輸入。</span><span class="sxs-lookup"><span data-stu-id="714c2-153">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers' assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="714c2-154">安全性 playbooks 已推出階段</span><span class="sxs-lookup"><span data-stu-id="714c2-154">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="714c2-155">航空的一部分，安全性 playbooks 已推出階段。</span><span class="sxs-lookup"><span data-stu-id="714c2-155">As part of AIR, security playbooks are rolling out in phases.</span></span> <span data-ttu-id="714c2-156">階段 1 是現在可使用，並包含數個 playbooks 提供建議的安全性系統管理員可以檢閱和核准的動作：</span><span class="sxs-lookup"><span data-stu-id="714c2-156">Phase 1 is now generally available and includes several playbooks that provide recommendations for actions that security administrators can review and approve:</span></span>
- <span data-ttu-id="714c2-157">使用者報告的釣魚程式訊息</span><span class="sxs-lookup"><span data-stu-id="714c2-157">User-reported phish message</span></span>
- <span data-ttu-id="714c2-158">URL 按一下 verdict 變更</span><span class="sxs-lookup"><span data-stu-id="714c2-158">URL click verdict change</span></span>
- <span data-ttu-id="714c2-159">偵測到的惡意程式碼後傳遞 （惡意程式碼時能量光束）</span><span class="sxs-lookup"><span data-stu-id="714c2-159">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="714c2-160">釣魚程式偵測到後續傳遞 ZAP （Phish 時能量光束）</span><span class="sxs-lookup"><span data-stu-id="714c2-160">Phish detected post-delivery ZAP (Phish ZAP)</span></span>

<span data-ttu-id="714c2-161">階段 1 也包含觸發的系統管理員的電子郵件調查 （使用[威脅總管](threat-explorer.md)） 的支援。</span><span class="sxs-lookup"><span data-stu-id="714c2-161">Phase 1 also includes support for administrator triggered e-mail investigations (using [Threat Explorer](threat-explorer.md)).</span></span>

<span data-ttu-id="714c2-162">階段 2 現在是與**公開預覽**中提供建議的動作，並在調查問題達到安全性管理員下列 playbooks 的進度：</span><span class="sxs-lookup"><span data-stu-id="714c2-162">Phase 2 is now progress with the following playbooks in **public preview**, providing recommendations for actions and aiding security administrators in investigating issues:</span></span>
- <span data-ttu-id="714c2-163">使用者回報為遭入侵 （公用預覽）</span><span class="sxs-lookup"><span data-stu-id="714c2-163">User reported as compromised (public preview)</span></span>

<span data-ttu-id="714c2-164">將發行進一步 playbooks，因為它們已完成。</span><span class="sxs-lookup"><span data-stu-id="714c2-164">Further playbooks will be released as they are completed.</span></span> <span data-ttu-id="714c2-165">請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)請參閱什麼是計劃的及接下來推出。</span><span class="sxs-lookup"><span data-stu-id="714c2-165">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="714c2-166">Playbooks 包括調查與建議</span><span class="sxs-lookup"><span data-stu-id="714c2-166">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="714c2-167">在空調，每個安全性 playbook 包括：</span><span class="sxs-lookup"><span data-stu-id="714c2-167">In AIR, each security playbook includes:</span></span> 
- <span data-ttu-id="714c2-168">根調查的電子郵件的實體 （檔案、 Url、 收件者、 IP 位址等等。），</span><span class="sxs-lookup"><span data-stu-id="714c2-168">a root investigation of an email's entities (files, URLs, recipients, IP addresses, etc.),</span></span>
- <span data-ttu-id="714c2-169">進一步四處尋找類似組織所接收的電子郵件</span><span class="sxs-lookup"><span data-stu-id="714c2-169">further hunting for similar emails received by the organization</span></span> 
- <span data-ttu-id="714c2-170">識別並對應其他潛在威脅，所採取的步驟和</span><span class="sxs-lookup"><span data-stu-id="714c2-170">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="714c2-171">建議的威脅修復動作。</span><span class="sxs-lookup"><span data-stu-id="714c2-171">recommended threat remediation actions.</span></span>

<span data-ttu-id="714c2-172">每個高階步驟皆包含一些 substeps 執行提供深層、 詳細又詳盡回應威脅。</span><span class="sxs-lookup"><span data-stu-id="714c2-172">Each high-level step includes a number of substeps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="714c2-173">範例： 使用者回報的釣魚程式訊息啟動調查 playbook</span><span class="sxs-lookup"><span data-stu-id="714c2-173">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="714c2-174">當您組織中的使用者送出的電子郵件訊息和報告至 Microsoft，請使用[報告訊息增益集以進行 Outlook 或 Outlook Web App](enable-the-report-message-add-in.md)，報告也會傳送到您的系統，且使用者報告檢視中顯示在檔案總管。</span><span class="sxs-lookup"><span data-stu-id="714c2-174">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web App](enable-the-report-message-add-in.md), the report is also sent to your system and is visible in Explorer in the User-reported view.</span></span> <span data-ttu-id="714c2-175">此使用者回報郵件現在會觸發系統架構資訊警示，這會自動啟動 [調查 playbook。</span><span class="sxs-lookup"><span data-stu-id="714c2-175">This user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="714c2-176">在根調查階段中，會評估的電子郵件的各個層面。</span><span class="sxs-lookup"><span data-stu-id="714c2-176">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="714c2-177">包括：</span><span class="sxs-lookup"><span data-stu-id="714c2-177">These include:</span></span>
- <span data-ttu-id="714c2-178">可能需有哪些類型的威脅它決定;</span><span class="sxs-lookup"><span data-stu-id="714c2-178">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="714c2-179">寄件者; 它</span><span class="sxs-lookup"><span data-stu-id="714c2-179">Who sent it;</span></span>
- <span data-ttu-id="714c2-180">其中電子郵件寄件地 （傳送基礎結構）;</span><span class="sxs-lookup"><span data-stu-id="714c2-180">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="714c2-181">電子郵件的其他執行個體是否已傳遞或封鎖;</span><span class="sxs-lookup"><span data-stu-id="714c2-181">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="714c2-182">從我們分析師; 評估</span><span class="sxs-lookup"><span data-stu-id="714c2-182">An assessment from our analysts;</span></span>
- <span data-ttu-id="714c2-183">是否任何已知的行銷活動; 相關聯的電子郵件</span><span class="sxs-lookup"><span data-stu-id="714c2-183">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="714c2-184">等等。</span><span class="sxs-lookup"><span data-stu-id="714c2-184">and more.</span></span>

<span data-ttu-id="714c2-185">根調查完成後，playbook 會提供建議的動作，才會在原始的電子郵件和與它相關聯的實體清單。</span><span class="sxs-lookup"><span data-stu-id="714c2-185">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="714c2-186">接下來，數個威脅調查並狩獵步驟執行：</span><span class="sxs-lookup"><span data-stu-id="714c2-186">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="714c2-187">透過電子郵件叢集搜尋識別類似的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="714c2-187">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="714c2-188">其他平台，例如[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)可共用接收的訊號。</span><span class="sxs-lookup"><span data-stu-id="714c2-188">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="714c2-189">決定在任何使用者是否按下可疑的電子郵件訊息中任何前往惡意連結。</span><span class="sxs-lookup"><span data-stu-id="714c2-189">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="714c2-190">檢查完成跨 Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) 和 Office 365 進階威脅防護 ([ATP](office-365-atp.md))，以查看是否有任何其他類似的訊息報告的使用者。</span><span class="sxs-lookup"><span data-stu-id="714c2-190">A check is done across Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="714c2-191">若要查看是否使用者已遭洩露完成查核。</span><span class="sxs-lookup"><span data-stu-id="714c2-191">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="714c2-192">這項檢查跨 Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)，相互關聯任何相關的使用者活動異常運用訊號。</span><span class="sxs-lookup"><span data-stu-id="714c2-192">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="714c2-193">狩獵階段風險和威脅指派給各種狩獵步驟。</span><span class="sxs-lookup"><span data-stu-id="714c2-193">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="714c2-194">修復為 playbook 的最後一個階段。</span><span class="sxs-lookup"><span data-stu-id="714c2-194">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="714c2-195">在這個階段，採取補救步驟為止，根據調查和狩獵階段。</span><span class="sxs-lookup"><span data-stu-id="714c2-195">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="714c2-196">範例： 安全性系統管理員會觸發從威脅總管調查</span><span class="sxs-lookup"><span data-stu-id="714c2-196">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="714c2-197">除了警示所觸發的自動調查，貴組織的安全性作業小組可以觸發自動進行調查，從[威脅總管](threat-explorer.md)] 中檢視。</span><span class="sxs-lookup"><span data-stu-id="714c2-197">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>

<span data-ttu-id="714c2-198">例如，假設您正在檢視的資料在檔案總管中關於使用者報告的郵件。</span><span class="sxs-lookup"><span data-stu-id="714c2-198">For example, suppose that you are viewing data in Explorer about user-reported messages.</span></span> <span data-ttu-id="714c2-199">您可以在結果清單中選取項目，然後按一下 [從 （假設您具備適當的補救權限） 的 [動作] 功能表的 [**調查]** 。</span><span class="sxs-lookup"><span data-stu-id="714c2-199">You can select an item in the list of results, and then click **Investigate** from the action menu (assuming you have appropriate remediation permissions).</span></span>

![使用者報告中的郵件檔案總管與調查] 按鈕](../../media/Explorer-UserReported-Investigate.png)

<span data-ttu-id="714c2-201">另一個範例，假設您正在檢視包含惡意程式碼，偵測到的電子郵件的相關資料，並有幾個偵測為包含惡意程式碼的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="714c2-201">As another example, suppose you are viewing data about email messages detected as containing malware, and there are several email messages detected as containing malware.</span></span> <span data-ttu-id="714c2-202">您可以選取 [**電子郵件**] 索引標籤，選取一或多個電子郵件訊息，然後在 [**動作**] 功能表上選取 [**調查]**。</span><span class="sxs-lookup"><span data-stu-id="714c2-202">You can select the **Email** tab, select one or more email messages, and then, on the **Actions** menu, select **Investigate**.</span></span> 

![在檔案總管中開始進行調查，惡意程式碼](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="714c2-204">類似於 playbooks 觸發警示的通知，會觸發從瀏覽器中檢視的自動調查包含根目錄和調查]，以找出並相互關聯的威脅，步驟及建議的動作來減輕這些威脅。</span><span class="sxs-lookup"><span data-stu-id="714c2-204">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="next-steps"></a><span data-ttu-id="714c2-205">後續步驟</span><span class="sxs-lookup"><span data-stu-id="714c2-205">Next steps</span></span>

- [<span data-ttu-id="714c2-206">開始使用 Office 365 中的空調</span><span class="sxs-lookup"><span data-stu-id="714c2-206">Get started using AIR in Office 365</span></span>](office-365-air.md)

- [<span data-ttu-id="714c2-207">造訪 Microsoft 365 藍圖，查看即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="714c2-207">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

