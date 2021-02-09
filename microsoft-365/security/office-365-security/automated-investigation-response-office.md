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
ms.openlocfilehash: 97cc2f6bcb066ff2d6f64254add3a57eb27b8828
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142546"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a><span data-ttu-id="06d9f-104">Microsoft Defender for Office 365 的自動化調查和回應運作方式</span><span class="sxs-lookup"><span data-stu-id="06d9f-104">How automated investigation and response works in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="06d9f-105">在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="06d9f-105">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="06d9f-106">在某些情況下，安全性作業小組可能感覺到所觸發的警示數量所淹沒。</span><span class="sxs-lookup"><span data-stu-id="06d9f-106">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="06d9f-107">Microsoft Defender for Office 365 中 (AIR) 功能的自動化調查和回應可提供協助。</span><span class="sxs-lookup"><span data-stu-id="06d9f-107">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span>

<span data-ttu-id="06d9f-108">AIR 可讓您的安全性運作小組更有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="06d9f-108">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="06d9f-109">AIR 功能包括自動調查處理程式，以回應目前存在的已知威脅。</span><span class="sxs-lookup"><span data-stu-id="06d9f-109">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="06d9f-110">適當的修正動作等待核准，讓您的安全性作業小組能夠回應偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="06d9f-110">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span>

<span data-ttu-id="06d9f-111">本文說明 AIR 如何透過數個範例運作。</span><span class="sxs-lookup"><span data-stu-id="06d9f-111">This article describes how AIR works through several examples.</span></span> <span data-ttu-id="06d9f-112">當您準備好開始使用 AIR 時，請參閱 [自動調查和回應威脅](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="06d9f-112">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

- [<span data-ttu-id="06d9f-113">範例1：使用者報告的網路釣魚郵件啟動調查行動手冊</span><span class="sxs-lookup"><span data-stu-id="06d9f-113">Example 1: A user-reported phish message launches an investigation playbook</span></span>](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [<span data-ttu-id="06d9f-114">範例2：安全性管理員會觸發來自威脅瀏覽器的調查</span><span class="sxs-lookup"><span data-stu-id="06d9f-114">Example 2: A security administrator triggers an investigation from Threat Explorer</span></span>](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [<span data-ttu-id="06d9f-115">範例3：安全操作小組使用 Office 365 管理活動 API，將 AIR 與其 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="06d9f-115">Example 3: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="06d9f-116">範例：使用者報告的網路釣魚郵件啟動調查行動手冊</span><span class="sxs-lookup"><span data-stu-id="06d9f-116">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="06d9f-117">假設組織中的使用者收到他們認為是網路釣魚企圖的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="06d9f-117">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="06d9f-118">使用者在報告這類訊息時，會使用 [報告訊息增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md) 將其傳送至 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="06d9f-118">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="06d9f-119">提交也會傳送至您的系統，而且會顯示在 **提交** 視圖中 (先前稱為 **使用者報告** 的 view) 。</span><span class="sxs-lookup"><span data-stu-id="06d9f-119">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="06d9f-120">此外，使用者報告的訊息現在會觸發以系統為基礎的資訊性警示，這會自動啟動調查行動手冊。</span><span class="sxs-lookup"><span data-stu-id="06d9f-120">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="06d9f-121">在根調查階段中，會評估電子郵件的各個層面。</span><span class="sxs-lookup"><span data-stu-id="06d9f-121">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="06d9f-122">這些方面包括：</span><span class="sxs-lookup"><span data-stu-id="06d9f-122">These aspects include:</span></span>

- <span data-ttu-id="06d9f-123">決定可能的威脅類型;</span><span class="sxs-lookup"><span data-stu-id="06d9f-123">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="06d9f-124">誰送出;</span><span class="sxs-lookup"><span data-stu-id="06d9f-124">Who sent it;</span></span>
- <span data-ttu-id="06d9f-125">電子郵件傳送來源的 (傳送基礎結構) ;</span><span class="sxs-lookup"><span data-stu-id="06d9f-125">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="06d9f-126">電子郵件的其他實例是否已傳遞或封鎖;</span><span class="sxs-lookup"><span data-stu-id="06d9f-126">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="06d9f-127">我們分析員的評估;</span><span class="sxs-lookup"><span data-stu-id="06d9f-127">An assessment from our analysts;</span></span>
- <span data-ttu-id="06d9f-128">電子郵件是否與任何已知的市場活動相關聯;</span><span class="sxs-lookup"><span data-stu-id="06d9f-128">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="06d9f-129">等等。</span><span class="sxs-lookup"><span data-stu-id="06d9f-129">and more.</span></span>

<span data-ttu-id="06d9f-130">完成根調查之後，「行動手冊」會提供建議執行的動作清單，以供原始電子郵件和與其相關聯的實體使用。</span><span class="sxs-lookup"><span data-stu-id="06d9f-130">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>

<span data-ttu-id="06d9f-131">接下來，會執行數個威脅調查和搜尋步驟：</span><span class="sxs-lookup"><span data-stu-id="06d9f-131">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="06d9f-132">類似的電子郵件會透過電子郵件聚簇搜尋加以識別。</span><span class="sxs-lookup"><span data-stu-id="06d9f-132">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="06d9f-133">此信號是與其他平臺（例如 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共用。</span><span class="sxs-lookup"><span data-stu-id="06d9f-133">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="06d9f-134">決定是否任何使用者已透過可疑電子郵件訊息中的任何惡意連結進行按一下。</span><span class="sxs-lookup"><span data-stu-id="06d9f-134">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="06d9f-135">在 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 ([Microsoft Defender for Office 365](office-365-atp.md)) 中進行檢查，以查看使用者是否已報告任何其他類似的郵件。</span><span class="sxs-lookup"><span data-stu-id="06d9f-135">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and ([Microsoft Defender for Office 365](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="06d9f-136">會執行檢查以查看使用者是否遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="06d9f-136">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="06d9f-137">這種檢查會利用跨 Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)的信號，以關聯任何相關的使用者活動異常。</span><span class="sxs-lookup"><span data-stu-id="06d9f-137">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="06d9f-138">在搜尋階段中，會將風險和威脅指派給各種搜尋步驟。</span><span class="sxs-lookup"><span data-stu-id="06d9f-138">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>

<span data-ttu-id="06d9f-139">修正是行動手冊的最後階段。</span><span class="sxs-lookup"><span data-stu-id="06d9f-139">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="06d9f-140">在此階段中，會根據調查和搜尋階段採取補救措施。</span><span class="sxs-lookup"><span data-stu-id="06d9f-140">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span>

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="06d9f-141">範例：安全性管理員會觸發來自威脅瀏覽器的調查</span><span class="sxs-lookup"><span data-stu-id="06d9f-141">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="06d9f-142">除了警示所觸發的自動調查之外，您的組織的安全性運作小組也可在 [威脅瀏覽器](threat-explorer.md)的視圖中觸發自動調查。</span><span class="sxs-lookup"><span data-stu-id="06d9f-142">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="06d9f-143">這種調查也會建立警示，使 Microsoft Defender 事件和外部 SIEM 工具可以查看已觸發此調查。</span><span class="sxs-lookup"><span data-stu-id="06d9f-143">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span>

<span data-ttu-id="06d9f-144">例如，假設您在瀏覽器中使用 **惡意** 代碼視圖。</span><span class="sxs-lookup"><span data-stu-id="06d9f-144">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="06d9f-145">您可以使用圖表下方的索引標籤，選取 [ **電子郵件** ] 索引標籤。如果您選取清單中的一或多個專案，則會啟動 **+ 動作** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="06d9f-145">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span>

![具有選取郵件的 Explorer](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="06d9f-147">您可以使用 [ **動作** ] 功能表，選取 [ **觸發調查**]。</span><span class="sxs-lookup"><span data-stu-id="06d9f-147">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![選取郵件的動作功能表](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="06d9f-149">類似于警示所觸發的行動行動方式，從瀏覽器中的視圖觸發的自動調查包括根調查、識別和關聯威脅的步驟，以及緩解這些威脅的建議動作。</span><span class="sxs-lookup"><span data-stu-id="06d9f-149">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="06d9f-150">範例：使用 Office 365 管理活動 API，安全性運作小組與其 SIEM 整合 AIR</span><span class="sxs-lookup"><span data-stu-id="06d9f-150">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="06d9f-151">Microsoft Defender for Office 365 中的 AIR 功能包括 [報告 & 詳細資料](air-view-investigation-results.md) ，安全性作業小組可用以監視和處理威脅。</span><span class="sxs-lookup"><span data-stu-id="06d9f-151">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="06d9f-152">不過，您也可以整合 AIR 功能與其他解決方案。</span><span class="sxs-lookup"><span data-stu-id="06d9f-152">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="06d9f-153">範例包括安全性資訊和事件管理 (SIEM) 系統、案例管理系統或自訂報告解決方案。</span><span class="sxs-lookup"><span data-stu-id="06d9f-153">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="06d9f-154">您可以使用 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)來完成這些類型的整合。</span><span class="sxs-lookup"><span data-stu-id="06d9f-154">These kinds of integrations can be done by using the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="06d9f-155">例如，在最近，組織會設定安全性作業小組的方式，以查看已由 AIR 處理的使用者報告網路釣魚警報。</span><span class="sxs-lookup"><span data-stu-id="06d9f-155">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="06d9f-156">其解決方案會將相關的警示與組織的 SIEM 伺服器及其案例管理系統整合在一起。</span><span class="sxs-lookup"><span data-stu-id="06d9f-156">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="06d9f-157">此解決方案大幅減少誤報的數目，讓他們的安全性運作小組能夠專注于實際威脅的時間和工作。</span><span class="sxs-lookup"><span data-stu-id="06d9f-157">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="06d9f-158">若要深入瞭解此自訂解決方案，請參閱 [技術社區博客：使用 Microsoft Defender For Office 365 和 O365 管理 API，改善 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="06d9f-158">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="06d9f-159">後續步驟</span><span class="sxs-lookup"><span data-stu-id="06d9f-159">Next steps</span></span>

- [<span data-ttu-id="06d9f-160">開始使用 AIR</span><span class="sxs-lookup"><span data-stu-id="06d9f-160">Get started using AIR</span></span>](office-365-air.md)
- [<span data-ttu-id="06d9f-161">查看擱置中或已完成的修復動作</span><span class="sxs-lookup"><span data-stu-id="06d9f-161">View pending or completed remediation actions</span></span>](air-review-approve-pending-completed-actions.md)
