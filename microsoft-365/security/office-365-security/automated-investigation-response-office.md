---
title: Microsoft Defender for Office 365 的自動化調查和回應運作方式
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自動化的事件回應、調查、修正及威脅防護
ms.date: 01/29/2021
description: 請參閱 Office 365 的 Microsoft Defender 中的自動化調查和回應功能的運作方式
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5a1384208141a42459c009952f89d18498cc21e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287922"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a><span data-ttu-id="49169-104">Microsoft Defender for Office 365 的自動化調查和回應運作方式</span><span class="sxs-lookup"><span data-stu-id="49169-104">How automated investigation and response works in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="49169-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="49169-105">**Applies to**</span></span>
- [<span data-ttu-id="49169-106">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="49169-106">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="49169-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49169-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="49169-108">在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="49169-108">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="49169-109">在某些情況下，安全性作業小組可能感覺到所觸發的警示數量所淹沒。</span><span class="sxs-lookup"><span data-stu-id="49169-109">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="49169-110">Microsoft Defender for Office 365 中 (AIR) 功能的自動化調查和回應可提供協助。</span><span class="sxs-lookup"><span data-stu-id="49169-110">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span>

<span data-ttu-id="49169-111">AIR 可讓您的安全性運作小組更有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="49169-111">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="49169-112">AIR 功能包括自動調查處理程式，以回應目前存在的已知威脅。</span><span class="sxs-lookup"><span data-stu-id="49169-112">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="49169-113">適當的修正動作等待核准，讓您的安全性作業小組能夠回應偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="49169-113">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span>

<span data-ttu-id="49169-114">本文說明 AIR 如何透過數個範例運作。</span><span class="sxs-lookup"><span data-stu-id="49169-114">This article describes how AIR works through several examples.</span></span> <span data-ttu-id="49169-115">當您準備好開始使用 AIR 時，請參閱 [自動調查和回應威脅](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="49169-115">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

- [<span data-ttu-id="49169-116">範例1：使用者報告的網路釣魚郵件啟動調查行動手冊</span><span class="sxs-lookup"><span data-stu-id="49169-116">Example 1: A user-reported phish message launches an investigation playbook</span></span>](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [<span data-ttu-id="49169-117">範例2：安全性管理員會觸發來自威脅瀏覽器的調查</span><span class="sxs-lookup"><span data-stu-id="49169-117">Example 2: A security administrator triggers an investigation from Threat Explorer</span></span>](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [<span data-ttu-id="49169-118">範例3：安全操作小組使用 Office 365 管理活動 API，將 AIR 與其 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="49169-118">Example 3: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="49169-119">範例：使用者報告的網路釣魚郵件啟動調查行動手冊</span><span class="sxs-lookup"><span data-stu-id="49169-119">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="49169-120">假設組織中的使用者收到他們認為是網路釣魚企圖的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="49169-120">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="49169-121">使用者在報告這類訊息時，會使用 [報告訊息增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md) 將其傳送至 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="49169-121">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="49169-122">提交也會傳送至您的系統，而且會顯示在 **提交** 視圖中 (先前稱為 **使用者報告** 的 view) 。</span><span class="sxs-lookup"><span data-stu-id="49169-122">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="49169-123">此外，使用者報告的訊息現在會觸發以系統為基礎的資訊性警示，這會自動啟動調查行動手冊。</span><span class="sxs-lookup"><span data-stu-id="49169-123">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="49169-124">在根調查階段中，會評估電子郵件的各個層面。</span><span class="sxs-lookup"><span data-stu-id="49169-124">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="49169-125">這些方面包括：</span><span class="sxs-lookup"><span data-stu-id="49169-125">These aspects include:</span></span>

- <span data-ttu-id="49169-126">決定可能的威脅類型;</span><span class="sxs-lookup"><span data-stu-id="49169-126">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="49169-127">誰送出;</span><span class="sxs-lookup"><span data-stu-id="49169-127">Who sent it;</span></span>
- <span data-ttu-id="49169-128">電子郵件傳送來源的 (傳送基礎結構) ;</span><span class="sxs-lookup"><span data-stu-id="49169-128">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="49169-129">電子郵件的其他實例是否已傳遞或封鎖;</span><span class="sxs-lookup"><span data-stu-id="49169-129">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="49169-130">我們分析員的評估;</span><span class="sxs-lookup"><span data-stu-id="49169-130">An assessment from our analysts;</span></span>
- <span data-ttu-id="49169-131">電子郵件是否與任何已知的市場活動相關聯;</span><span class="sxs-lookup"><span data-stu-id="49169-131">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="49169-132">等等。</span><span class="sxs-lookup"><span data-stu-id="49169-132">and more.</span></span>

<span data-ttu-id="49169-133">完成根調查之後，「行動手冊」會提供建議執行的動作清單，以供原始電子郵件和與其相關聯的實體使用。</span><span class="sxs-lookup"><span data-stu-id="49169-133">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>

<span data-ttu-id="49169-134">接下來，會執行數個威脅調查和搜尋步驟：</span><span class="sxs-lookup"><span data-stu-id="49169-134">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="49169-135">類似的電子郵件會透過電子郵件聚簇搜尋加以識別。</span><span class="sxs-lookup"><span data-stu-id="49169-135">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="49169-136">此信號是與其他平臺（例如 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共用。</span><span class="sxs-lookup"><span data-stu-id="49169-136">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="49169-137">決定是否任何使用者已透過可疑電子郵件訊息中的任何惡意連結進行按一下。</span><span class="sxs-lookup"><span data-stu-id="49169-137">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="49169-138">在 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 ([Microsoft Defender for Office 365](office-365-atp.md)) 中進行檢查，以查看使用者是否已報告任何其他類似的郵件。</span><span class="sxs-lookup"><span data-stu-id="49169-138">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and ([Microsoft Defender for Office 365](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="49169-139">會執行檢查以查看使用者是否遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="49169-139">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="49169-140">這種檢查會利用跨 Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)的信號，以關聯任何相關的使用者活動異常。</span><span class="sxs-lookup"><span data-stu-id="49169-140">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="49169-141">在搜尋階段中，會將風險和威脅指派給各種搜尋步驟。</span><span class="sxs-lookup"><span data-stu-id="49169-141">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>

<span data-ttu-id="49169-142">修正是行動手冊的最後階段。</span><span class="sxs-lookup"><span data-stu-id="49169-142">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="49169-143">在此階段中，會根據調查和搜尋階段採取補救措施。</span><span class="sxs-lookup"><span data-stu-id="49169-143">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span>

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="49169-144">範例：安全性管理員會觸發來自威脅瀏覽器的調查</span><span class="sxs-lookup"><span data-stu-id="49169-144">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="49169-145">除了警示所觸發的自動調查之外，您的組織的安全性運作小組也可在 [威脅瀏覽器](threat-explorer.md)的視圖中觸發自動調查。</span><span class="sxs-lookup"><span data-stu-id="49169-145">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="49169-146">這種調查也會建立警示，使 Microsoft Defender 事件和外部 SIEM 工具可以查看已觸發此調查。</span><span class="sxs-lookup"><span data-stu-id="49169-146">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span>

<span data-ttu-id="49169-147">例如，假設您在瀏覽器中使用 **惡意** 代碼視圖。</span><span class="sxs-lookup"><span data-stu-id="49169-147">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="49169-148">您可以使用圖表下方的索引標籤，選取 [ **電子郵件** ] 索引標籤。如果您選取清單中的一或多個專案，則會啟動 **+ 動作** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="49169-148">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span>

![具有選取郵件的 Explorer](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="49169-150">您可以使用 [ **動作** ] 功能表，選取 [ **觸發調查**]。</span><span class="sxs-lookup"><span data-stu-id="49169-150">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![選取郵件的動作功能表](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="49169-152">類似于警示所觸發的行動行動方式，從瀏覽器中的視圖觸發的自動調查包括根調查、識別和關聯威脅的步驟，以及緩解這些威脅的建議動作。</span><span class="sxs-lookup"><span data-stu-id="49169-152">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="49169-153">範例：使用 Office 365 管理活動 API，安全性運作小組與其 SIEM 整合 AIR</span><span class="sxs-lookup"><span data-stu-id="49169-153">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="49169-154">Microsoft Defender for Office 365 中的 AIR 功能包括 [報告 & 詳細資料](air-view-investigation-results.md) ，安全性作業小組可用以監視和處理威脅。</span><span class="sxs-lookup"><span data-stu-id="49169-154">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="49169-155">不過，您也可以整合 AIR 功能與其他解決方案。</span><span class="sxs-lookup"><span data-stu-id="49169-155">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="49169-156">範例包括安全性資訊和事件管理 (SIEM) 系統、案例管理系統或自訂報告解決方案。</span><span class="sxs-lookup"><span data-stu-id="49169-156">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="49169-157">您可以使用 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)來完成這些類型的整合。</span><span class="sxs-lookup"><span data-stu-id="49169-157">These kinds of integrations can be done by using the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="49169-158">例如，在最近，組織會設定安全性作業小組的方式，以查看已由 AIR 處理的使用者報告網路釣魚警報。</span><span class="sxs-lookup"><span data-stu-id="49169-158">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="49169-159">其解決方案會將相關的警示與組織的 SIEM 伺服器及其案例管理系統整合在一起。</span><span class="sxs-lookup"><span data-stu-id="49169-159">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="49169-160">此解決方案大幅減少誤報的數目，讓他們的安全性運作小組能夠專注于實際威脅的時間和工作。</span><span class="sxs-lookup"><span data-stu-id="49169-160">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="49169-161">若要深入瞭解此自訂解決方案，請參閱 [技術社區博客：使用 Microsoft Defender For Office 365 和 O365 管理 API，改善 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="49169-161">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="49169-162">後續步驟</span><span class="sxs-lookup"><span data-stu-id="49169-162">Next steps</span></span>

- [<span data-ttu-id="49169-163">開始使用 AIR</span><span class="sxs-lookup"><span data-stu-id="49169-163">Get started using AIR</span></span>](office-365-air.md)
- [<span data-ttu-id="49169-164">查看擱置中或已完成的修復動作</span><span class="sxs-lookup"><span data-stu-id="49169-164">View pending or completed remediation actions</span></span>](air-review-approve-pending-completed-actions.md)
