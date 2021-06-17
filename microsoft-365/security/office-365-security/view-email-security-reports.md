---
title: 在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 瞭解如何尋找及使用貴組織的電子郵件安全性報告。 電子郵件安全性報告可在 Microsoft 365 Defender 入口網站中取得。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985202"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2a45b-104">在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2a45b-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="2a45b-105">**Applies to**</span></span>
- [<span data-ttu-id="2a45b-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2a45b-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2a45b-107">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="2a45b-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2a45b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2a45b-109">Microsoft 365 Defender 入口網站提供各種報告 <https://security.microsoft.com> ，可協助您觀察電子郵件安全性功能（例如 Microsoft 365 中的反垃圾郵件、反惡意程式碼和加密功能）如何保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="2a45b-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="2a45b-110">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以在 Microsoft 365 Defender 入口網站中查看這些報告，方式是要 **報告** \> **電子郵件 &** 共同作業 & 共同作業 \> **報告**。</span><span class="sxs-lookup"><span data-stu-id="2a45b-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="2a45b-111">若要直接移至 [ **電子郵件 &** 共同作業報告] 頁面上，開啟 <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender 入口網站中的電子郵件 & 共同作業報告] 頁面](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="2a45b-113">[ **電子郵件 & 協同報告** ] 頁面上的某些報告需要 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="2a45b-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="2a45b-114">如需這些報告的詳細資訊，請參閱 [在 Microsoft 365 Defender 入口網站中查看 Office 365 報告的 Defender](view-reports-for-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="2a45b-115">與郵件流程相關的報告現在位於 Exchange 系統管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="2a45b-116">如需這些報告的詳細資訊，請參閱 [新 Exchange 系統管理中心的郵件流程報告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="2a45b-117">已遭破壞的使用者報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="2a45b-118">這份報告可在 Microsoft 365 組織中使用 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="2a45b-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="2a45b-119">在獨立 Exchange Online Protection (EOP) 組織中無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="2a45b-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="2a45b-120">「已 **遭破壞的使用者** 報告」顯示顯示過去7天內已標示為 **可疑** 或 **限制** 的使用者帳戶數目。</span><span class="sxs-lookup"><span data-stu-id="2a45b-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="2a45b-121">在上述任一狀態的帳戶都有問題或甚至遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="2a45b-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="2a45b-122">在經常使用的情況下，您可以使用報表來找出峰值，甚至是趨勢，也就是可疑或受限制的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2a45b-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="2a45b-123">如需遭到破壞之使用者的詳細資訊，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![「電子郵件 & 共同作業報告」頁面上已遭破壞的使用者小工具](../../media/compromised-users-report-widget.png)

<span data-ttu-id="2a45b-125">匯總視圖會顯示過去90天的資料，詳細資料檢視會顯示過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="2a45b-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="2a45b-126">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="2a45b-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="2a45b-127">在已 **遭破壞的使用者** 上，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="2a45b-128">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="2a45b-129">按一下 [ **查看詳細資料**] 之後，您可以按一下 [ **篩選** ]，然後在出現的浮出控制項中選取下列一或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="2a45b-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="2a45b-130">**日期 (UTC)**： **開始日期** 和 **結束日期**。</span><span class="sxs-lookup"><span data-stu-id="2a45b-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="2a45b-131">**活動**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-131">**Activity**:</span></span>
  - <span data-ttu-id="2a45b-132">**可疑**：使用者帳戶已傳送可疑的電子郵件，而且受到限制傳送電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="2a45b-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="2a45b-133">**限制**：由於高度可疑的模式，使用者帳戶已限制傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="2a45b-134">完成篩選後， **請按一下 [** 套用] 或 [ **取消**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![已遭破壞之使用者報告中的報表檢視](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="2a45b-136">在圖形下方的表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="2a45b-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="2a45b-137">**建立時間**</span><span class="sxs-lookup"><span data-stu-id="2a45b-137">**Creation time**</span></span>
- <span data-ttu-id="2a45b-138">**User ID**</span><span class="sxs-lookup"><span data-stu-id="2a45b-138">**User ID**</span></span>
- <span data-ttu-id="2a45b-139">**Action**</span><span class="sxs-lookup"><span data-stu-id="2a45b-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="2a45b-140">Exchange transport rule 報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-140">Exchange transport rule report</span></span>

<span data-ttu-id="2a45b-141">**Exchange transport rule** report 會顯示郵件流程規則 (也稱為傳輸規則) 組織中內送和外寄郵件的效果。</span><span class="sxs-lookup"><span data-stu-id="2a45b-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="2a45b-142">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="2a45b-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="2a45b-143">在 **Exchange transport rule** 上，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="2a45b-144">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![「電子郵件 & 共同作業報告」頁面上的 Exchange 傳輸規則小工具](../../media/transport-rule-report-widget.png)

<span data-ttu-id="2a45b-146">按一下 [ **查看詳細** 資料] 之後，即可使用下列圖表和資料：</span><span class="sxs-lookup"><span data-stu-id="2a45b-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="2a45b-147">**依 Exchange 傳輸規則** \> 查看資料 **依方向的圖表細目**：此圖顯示受郵件流程規則影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2a45b-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="2a45b-148">**依 Exchange 傳輸規則** \> 查看資料 **依嚴重性顯示圖表細目**：此圖顯示 **高嚴重性**、 **中嚴重性** 和 **低嚴重性** 郵件的數目。</span><span class="sxs-lookup"><span data-stu-id="2a45b-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="2a45b-149">您可以將嚴重性層級設定為規則 ([ **以嚴重性層級** 或 _SetAuditSeverity_) 審核此規則] 中的動作。</span><span class="sxs-lookup"><span data-stu-id="2a45b-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="2a45b-150">如需詳細資訊，請參閱 [Exchange Online 中的郵件流程規則動作](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="2a45b-151">**按 DLP Exchange transport Rules** \> 查看資料 **依方向的圖表分解**：此圖顯示受資料遺失防護 (DLP) 郵件流程規則所影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2a45b-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="2a45b-152">**按 DLP Exchange transport Rules** \> 查看資料 **依嚴重性顯示圖表細目**：此視圖顯示受 DLP 郵件流程規則影響的 **高嚴重性**、 **中嚴重性** 和 **低嚴重性** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2a45b-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="2a45b-153">如需 **Exchange transport rules 選項的查看資料** ，下列資訊會顯示在圖形下方的詳細資料表格中：</span><span class="sxs-lookup"><span data-stu-id="2a45b-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="2a45b-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-154">**Date**</span></span>
- <span data-ttu-id="2a45b-155">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="2a45b-155">**Transport rule**</span></span>
- <span data-ttu-id="2a45b-156">**主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-156">**Subject**</span></span>
- <span data-ttu-id="2a45b-157">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="2a45b-157">**Sender address**</span></span>
- <span data-ttu-id="2a45b-158">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="2a45b-158">**Recipient address**</span></span>
- <span data-ttu-id="2a45b-159">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="2a45b-159">**Severity**</span></span>
- <span data-ttu-id="2a45b-160">**方向**</span><span class="sxs-lookup"><span data-stu-id="2a45b-160">**Direction**</span></span>

<span data-ttu-id="2a45b-161">若要讓 **DLP Exchange transport rules 選項查看資料** ，下列資訊會顯示在圖形下方的詳細資料表格中：</span><span class="sxs-lookup"><span data-stu-id="2a45b-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="2a45b-162">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-162">**Date**</span></span>
- <span data-ttu-id="2a45b-163">**DLP 原則**</span><span class="sxs-lookup"><span data-stu-id="2a45b-163">**DLP policy**</span></span>
- <span data-ttu-id="2a45b-164">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="2a45b-164">**Transport rule**</span></span>
- <span data-ttu-id="2a45b-165">**主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-165">**Subject**</span></span>
- <span data-ttu-id="2a45b-166">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="2a45b-166">**Sender address**</span></span>
- <span data-ttu-id="2a45b-167">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="2a45b-167">**Recipient address**</span></span>
- <span data-ttu-id="2a45b-168">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="2a45b-168">**Severity**</span></span>
- <span data-ttu-id="2a45b-169">**方向**</span><span class="sxs-lookup"><span data-stu-id="2a45b-169">**Direction**</span></span>

<span data-ttu-id="2a45b-170">您可以在出現的浮出控制項中按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="2a45b-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="2a45b-171">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-172">**方向**： **輸出** 和 **輸入**</span><span class="sxs-lookup"><span data-stu-id="2a45b-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="2a45b-173">**嚴重性**： **高嚴重性**、 **中低嚴重性** 和 **低嚴重性**</span><span class="sxs-lookup"><span data-stu-id="2a45b-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Exchange transport rule 報告中的報表檢視](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="2a45b-175">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="2a45b-175">Mailflow status report</span></span>

<span data-ttu-id="2a45b-176">**郵件流程狀態報表** 是一個智慧報告，顯示傳入和傳出電子郵件、垃圾郵件偵測、惡意程式碼、識別為「良好」之電子郵件的相關資訊，以及有關允許或封鎖在 edge 上之電子郵件的資訊。</span><span class="sxs-lookup"><span data-stu-id="2a45b-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="2a45b-177">這是唯一包含 edge protection 資訊的報告，它會顯示在 Exchange Online Protection (EOP) 中，允許在評估之前封鎖多少封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="2a45b-178">請務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="2a45b-179">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="2a45b-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="2a45b-180">在 **郵件流程狀態摘要** 上，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="2a45b-181">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![[電子郵件 & 共同作業報告] 頁面上的 [郵件流程狀態摘要] 小工具](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="2a45b-183">郵件流程狀態報表的類型視圖</span><span class="sxs-lookup"><span data-stu-id="2a45b-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="2a45b-184">當您開啟報表時，預設會選取 [ **類型** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2a45b-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="2a45b-185">根據預設，此視圖包含的圖表和使用下列篩選器設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="2a45b-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2a45b-186">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="2a45b-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="2a45b-187">**郵件方向**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-187">**Mail direction**:</span></span>
  - <span data-ttu-id="2a45b-188">**入境**</span><span class="sxs-lookup"><span data-stu-id="2a45b-188">**Inbound**</span></span>
  - <span data-ttu-id="2a45b-189">**出境**</span><span class="sxs-lookup"><span data-stu-id="2a45b-189">**Outbound**</span></span>
  - <span data-ttu-id="2a45b-190">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="2a45b-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="2a45b-191">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與 **輸入** 和 **輸出**) 分開計數</span><span class="sxs-lookup"><span data-stu-id="2a45b-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="2a45b-192">**類型**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-192">**Type**:</span></span>
  - <span data-ttu-id="2a45b-193">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-193">**Good mail**</span></span>
  - <span data-ttu-id="2a45b-194">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="2a45b-194">**Malware**</span></span>
  - <span data-ttu-id="2a45b-195">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-195">**Spam**</span></span>
  - <span data-ttu-id="2a45b-196">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="2a45b-196">**Edge protection**</span></span>
  - <span data-ttu-id="2a45b-197">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="2a45b-197">**Rule messages**</span></span>
  - <span data-ttu-id="2a45b-198">**網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-198">**Phishing email**</span></span>
- <span data-ttu-id="2a45b-199">**網域**： **全部**</span><span class="sxs-lookup"><span data-stu-id="2a45b-199">**Domain**: **All**</span></span>

<span data-ttu-id="2a45b-200">圖表是依 **類型** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="2a45b-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="2a45b-201">您可以按一下 [ **篩選器** ] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="2a45b-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="2a45b-202">此資料表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-202">The data table contains the following information:</span></span>

- <span data-ttu-id="2a45b-203">**方向**</span><span class="sxs-lookup"><span data-stu-id="2a45b-203">**Direction**</span></span>
- <span data-ttu-id="2a45b-204">**類型**</span><span class="sxs-lookup"><span data-stu-id="2a45b-204">**Type**</span></span>
- <span data-ttu-id="2a45b-205">**24 小時**</span><span class="sxs-lookup"><span data-stu-id="2a45b-205">**24 hours**</span></span>
- <span data-ttu-id="2a45b-206">**3天**</span><span class="sxs-lookup"><span data-stu-id="2a45b-206">**3 days**</span></span>
- <span data-ttu-id="2a45b-207">**7 天**</span><span class="sxs-lookup"><span data-stu-id="2a45b-207">**7 days**</span></span>
- <span data-ttu-id="2a45b-208">**15 天**</span><span class="sxs-lookup"><span data-stu-id="2a45b-208">**15 days**</span></span>
- <span data-ttu-id="2a45b-209">**30天**</span><span class="sxs-lookup"><span data-stu-id="2a45b-209">**30 days**</span></span>

<span data-ttu-id="2a45b-210">如果您按一下 **[選擇類別] 以取得詳細資料**，您可以選取下列值：</span><span class="sxs-lookup"><span data-stu-id="2a45b-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="2a45b-211">**網路釣魚電子郵件**：這項選擇會帶您前往「 [威脅防護狀態」報告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="2a45b-212">**電子郵件中的惡意** 代碼：這項選擇會帶您前往 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="2a45b-213">**垃圾郵件** 偵測：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="2a45b-214">**Edge 封鎖的垃圾郵件**：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="2a45b-215">從類型視圖匯出</span><span class="sxs-lookup"><span data-stu-id="2a45b-215">Export from Type view</span></span>

<span data-ttu-id="2a45b-216">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="2a45b-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="2a45b-217">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="2a45b-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="2a45b-218">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="2a45b-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2a45b-219">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2a45b-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![郵件流程狀態報表中的類型視圖](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="2a45b-221">郵件流程狀態報表的方向視圖</span><span class="sxs-lookup"><span data-stu-id="2a45b-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="2a45b-222">如果您按一下 [ **方向** ] 索引標籤，則會使用 [ **類型** ] 視圖中的相同預設篩選器。</span><span class="sxs-lookup"><span data-stu-id="2a45b-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="2a45b-223">圖表是依 **方向** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="2a45b-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="2a45b-224">您可以按一下 [ **篩選器** ] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="2a45b-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="2a45b-225">會使用 [ **類型** ] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="2a45b-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="2a45b-226">資料表格包含的資訊來自 **類型** view。</span><span class="sxs-lookup"><span data-stu-id="2a45b-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="2a45b-227">[ **選擇類別** ] 如需詳細資料，可用的選取專案和行為與「 **類型** 」視圖相同。</span><span class="sxs-lookup"><span data-stu-id="2a45b-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="2a45b-228">從方向視圖匯出</span><span class="sxs-lookup"><span data-stu-id="2a45b-228">Export from Direction view</span></span>

<span data-ttu-id="2a45b-229">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="2a45b-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="2a45b-230">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="2a45b-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="2a45b-231">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="2a45b-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2a45b-232">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2a45b-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![郵件流程狀態報表中的方向視圖](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="2a45b-234">郵件流程狀態報表的漏斗視圖</span><span class="sxs-lookup"><span data-stu-id="2a45b-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="2a45b-235">**漏斗** 視圖顯示 Microsoft 的電子郵件威脅防護功能如何篩選組織中的內送和外寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="2a45b-236">它提供有關電子郵件總數的詳細資訊，以及設定的威脅防護功能（包括 edge protection、反惡意程式碼、反網路釣魚、反垃圾郵件和反欺詐）對此計數的影響。</span><span class="sxs-lookup"><span data-stu-id="2a45b-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="2a45b-237">如果您按一下 [ **漏斗** ] 索引標籤，此 view 預設會包含圖表和使用下列篩選設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="2a45b-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2a45b-238">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="2a45b-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="2a45b-239">**方向**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-239">**Direction**:</span></span>

  - <span data-ttu-id="2a45b-240">**入境**</span><span class="sxs-lookup"><span data-stu-id="2a45b-240">**Inbound**</span></span>
  - <span data-ttu-id="2a45b-241">**出境**</span><span class="sxs-lookup"><span data-stu-id="2a45b-241">**Outbound**</span></span>
  - <span data-ttu-id="2a45b-242">**組織內**：此計數是針對在租使用者中傳送的郵件進行計數;亦即，寄件者 abc@domain.com 會傳送給收件者 xyz@domain.com (與輸入和外寄) 分開計數。</span><span class="sxs-lookup"><span data-stu-id="2a45b-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="2a45b-243">匯總 view 和 data table view 允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="2a45b-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="2a45b-244">如果您按一下 [ **篩選**]，則可以篩選圖表和資料表格。</span><span class="sxs-lookup"><span data-stu-id="2a45b-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="2a45b-245">此圖顯示按下列方式組織的電子郵件計數：</span><span class="sxs-lookup"><span data-stu-id="2a45b-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="2a45b-246">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="2a45b-246">**Total email**</span></span>
- <span data-ttu-id="2a45b-247">**Edge protection 之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-247">**Email after edge protection**</span></span>
- <span data-ttu-id="2a45b-248">**傳輸規則** (郵件流程規則之後的電子郵件) </span><span class="sxs-lookup"><span data-stu-id="2a45b-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="2a45b-249">**反惡意程式碼、檔信譽、檔案類型封鎖後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="2a45b-250">**反網路釣魚、URL 信譽、品牌模擬、反欺騙功能之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="2a45b-251">**反垃圾郵件、大宗郵件篩選後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="2a45b-252">**使用者和網域模擬後的電子郵件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="2a45b-253">**檔案及 URL 引爆後的電子郵件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="2a45b-254">**在傳遞投遞後保護後，電子郵件偵測為良性 (URL 按一下時間保護)**</span><span class="sxs-lookup"><span data-stu-id="2a45b-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="2a45b-255"><sup>\*</sup>僅限 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="2a45b-256">若要個別查看以 EOP 或 Defender 為 Office 365 篩選的電子郵件，請按一下 [圖表圖例] 中的值。</span><span class="sxs-lookup"><span data-stu-id="2a45b-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="2a45b-257">此資料表包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="2a45b-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="2a45b-258">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-258">**Date**</span></span>
- <span data-ttu-id="2a45b-259">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="2a45b-259">**Total email**</span></span>
- <span data-ttu-id="2a45b-260">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="2a45b-260">**Edge protection**</span></span>
- <span data-ttu-id="2a45b-261">**反惡意程式碼、檔信譽、檔案類型封鎖**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="2a45b-262">**檔信譽**：由於其他 Microsoft 客戶附加的檔案識別，因此篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="2a45b-263">**檔案類型封鎖**：由於郵件中識別的惡意檔案類型，篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="2a45b-264">**反網路釣魚、URL 信譽、品牌模仿、反欺騙**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="2a45b-265">**URL 信譽**：由於其他 Microsoft 客戶的 url 身分識別而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="2a45b-266">**品牌** 模擬：因為郵件是由眾所周知的品牌類比寄件者所過濾，所以會加以篩選。</span><span class="sxs-lookup"><span data-stu-id="2a45b-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="2a45b-267">**反欺騙**：因為郵件企圖哄騙收件者所屬的網域，或是郵件寄件者不會擁有的網域，所以篩選掉郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="2a45b-268">**反垃圾郵件，大宗郵件篩選**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="2a45b-269">**大宗郵件篩選**：在反垃圾郵件原則中依據大量抱怨層級 (BCL) 臨界值篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="2a45b-270">**Office 365) 的使用者和網域模擬 (Defender**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="2a45b-271">**使用者** 模擬：郵件因嘗試模擬使用者 (郵件寄件者) （已在反網路釣魚原則的類比保護設定中所定義）而篩選。</span><span class="sxs-lookup"><span data-stu-id="2a45b-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="2a45b-272">**網域** 模擬：郵件因嘗試模擬防網路釣魚原則之類比保護設定中所定義的網域而篩選出來。</span><span class="sxs-lookup"><span data-stu-id="2a45b-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="2a45b-273">檔案 **及 URL 引爆 (Defender for Office 365)**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="2a45b-274">檔案 **引爆**：以 Safe 附件原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="2a45b-275">**URL 引爆**：透過 Safe 連結原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="2a45b-276">**投遞後保護和 zap (ATP) 或 zap (EOP)**：零小時自動清除 (針對惡意程式碼、垃圾郵件和網路釣魚的 ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="2a45b-277">如果您選取資料表格中的資料列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="2a45b-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="2a45b-278">從漏斗視圖匯出</span><span class="sxs-lookup"><span data-stu-id="2a45b-278">Export from Funnel view</span></span>

<span data-ttu-id="2a45b-279">在 [**選項**] 下按一下 [**匯出**] 後，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="2a45b-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="2a45b-280">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="2a45b-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="2a45b-281">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="2a45b-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="2a45b-282">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="2a45b-283">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2a45b-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="2a45b-284">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="2a45b-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2a45b-285">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2a45b-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![郵件流程狀態報表中的漏斗圖視圖](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="2a45b-287">郵件流程狀態報表的技術視圖</span><span class="sxs-lookup"><span data-stu-id="2a45b-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="2a45b-288">**技術視圖** 類似 **漏斗** 圖模式，可提供設定威脅防護功能的更細微細節。</span><span class="sxs-lookup"><span data-stu-id="2a45b-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="2a45b-289">您可以從圖表中查看郵件如何在威脅防護的不同階段進行分類。</span><span class="sxs-lookup"><span data-stu-id="2a45b-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="2a45b-290">如果您按一下 [ **技術視圖** ] 索引標籤，此視圖預設會包含圖表和使用下列篩選所設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="2a45b-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2a45b-291">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="2a45b-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="2a45b-292">**方向**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-292">**Direction**:</span></span>

  - <span data-ttu-id="2a45b-293">**入境**</span><span class="sxs-lookup"><span data-stu-id="2a45b-293">**Inbound**</span></span>
  - <span data-ttu-id="2a45b-294">**出境**</span><span class="sxs-lookup"><span data-stu-id="2a45b-294">**Outbound**</span></span>
  - <span data-ttu-id="2a45b-295">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="2a45b-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="2a45b-296">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與輸入和輸出) 分開計數</span><span class="sxs-lookup"><span data-stu-id="2a45b-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="2a45b-297">匯總 view 和 data table view 允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="2a45b-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="2a45b-298">如果您按一下 [ **篩選**]，則可以篩選圖表和資料表格。</span><span class="sxs-lookup"><span data-stu-id="2a45b-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="2a45b-299">此圖顯示組織成下列類別的郵件：</span><span class="sxs-lookup"><span data-stu-id="2a45b-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="2a45b-300">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="2a45b-300">**Total email**</span></span>
- <span data-ttu-id="2a45b-301">**Edge 允許** 和 **edge 篩選**</span><span class="sxs-lookup"><span data-stu-id="2a45b-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="2a45b-302">已篩選的 **傳輸規則允許** 和 **傳輸規則** (郵件流程規則) </span><span class="sxs-lookup"><span data-stu-id="2a45b-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="2a45b-303">**非惡意** 代碼、 **Safe 附件偵測** <sup>\*</sup> 和 **反惡意程式碼引擎偵測**</span><span class="sxs-lookup"><span data-stu-id="2a45b-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="2a45b-304">**不是網路釣魚詐騙**、 **DMARC 失敗**、**模仿偵測** <sup>\*</sup> 、**欺騙偵測** 和 **網路釣魚偵測**</span><span class="sxs-lookup"><span data-stu-id="2a45b-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="2a45b-305">**沒有偵測 URL 引爆** 及 **url 引爆偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="2a45b-306">**非垃圾郵件** 和  **垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="2a45b-307">**非惡意的電子郵件**、 **Safe 連結偵測** <sup>\*</sup> 和 **ZAP**</span><span class="sxs-lookup"><span data-stu-id="2a45b-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="2a45b-308"><sup>\*</sup>Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="2a45b-309">當您將游標移到圖表中的某個類別時，您可以看到該類別中的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2a45b-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="2a45b-310">此資料表包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="2a45b-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="2a45b-311">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-311">**Date**</span></span>
- <span data-ttu-id="2a45b-312">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="2a45b-312">**Total email**</span></span>
- <span data-ttu-id="2a45b-313">**已篩選 Edge**</span><span class="sxs-lookup"><span data-stu-id="2a45b-313">**Edge filtered**</span></span>
- <span data-ttu-id="2a45b-314">**規則郵件**：由於郵件流程規則而篩選的郵件 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="2a45b-315">**反惡意程式碼引擎**， **Safe 附件** <sup>\*</sup> ：</span><span class="sxs-lookup"><span data-stu-id="2a45b-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="2a45b-316">**DMARC，類比** <sup>\*</sup> ，**欺騙**，**網路釣魚篩選**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="2a45b-317">**DMARC**：由於郵件失敗的 DMARC 驗證檢查而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="2a45b-318">**URL 引爆偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="2a45b-319">**已篩選的反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="2a45b-320">**移除的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="2a45b-320">**ZAP removed**</span></span>
- <span data-ttu-id="2a45b-321">**Safe 連結偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="2a45b-322"><sup>\*</sup>Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="2a45b-323">如果您選取資料表格中的資料列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="2a45b-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="2a45b-324">從技術視圖匯出</span><span class="sxs-lookup"><span data-stu-id="2a45b-324">Export from Tech view</span></span>

<span data-ttu-id="2a45b-325">在按一下 [ **匯出**] 的 [ **選項** ] 底下，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="2a45b-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="2a45b-326">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="2a45b-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="2a45b-327">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="2a45b-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="2a45b-328">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="2a45b-329">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2a45b-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="2a45b-330">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="2a45b-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2a45b-331">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2a45b-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![郵件流程狀態報表中的技術視圖](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="2a45b-333">惡意程式碼檢測報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-333">Malware detections report</span></span>

<span data-ttu-id="2a45b-334">**惡意軟體偵測報告** 會顯示 Exchange Online Protection 或 EOP) 所偵測到的內送和外寄電子郵件， (惡意軟體偵測的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2a45b-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="2a45b-335">如需 EOP 中惡意程式碼保護的詳細資訊，請參閱 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="2a45b-336">匯總 view 篩選允許90天，而 [詳細資料表格篩選] 只允許10天。</span><span class="sxs-lookup"><span data-stu-id="2a45b-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="2a45b-337">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="2a45b-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="2a45b-338">在 **電子郵件中偵測到惡意** 代碼，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="2a45b-339">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![電子郵件 & 協同報告] 頁面上電子郵件小工具中的惡意程式碼偵測](../../media/malware-detections-widget.png)

<span data-ttu-id="2a45b-341">按一下 [ **查看詳細資料**] 之後，您可以按一下 [ **篩選** ] 並選取 [篩選]，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="2a45b-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="2a45b-342">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-343">**方向**： **輸入** 和 **輸出**</span><span class="sxs-lookup"><span data-stu-id="2a45b-343">**Direction**: **Inbound** and **Outbound**</span></span>

![電子郵件中的惡意程式碼偵測報表檢視](../../media/malware-detections-report-view.png)

<span data-ttu-id="2a45b-345">在圖形下方的 [詳細資料] 表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="2a45b-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="2a45b-346">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-346">**Date**</span></span>
- <span data-ttu-id="2a45b-347">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="2a45b-347">**Sender address**</span></span>
- <span data-ttu-id="2a45b-348">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="2a45b-348">**Recipient address**</span></span>
- <span data-ttu-id="2a45b-349">**郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2a45b-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="2a45b-350">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="2a45b-351">**主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-351">**Subject**</span></span>
- <span data-ttu-id="2a45b-352">**Filename**</span><span class="sxs-lookup"><span data-stu-id="2a45b-352">**Filename**</span></span>
- <span data-ttu-id="2a45b-353">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="2a45b-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="2a45b-354">郵件延遲報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-354">Mail latency report</span></span>

<span data-ttu-id="2a45b-355">Office 365 的「中的 **郵件延遲報告**] 包含組織內的郵件傳遞和引爆延遲的資訊。</span><span class="sxs-lookup"><span data-stu-id="2a45b-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="2a45b-356">如需詳細資訊，請參閱 [郵件延遲報告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="2a45b-357">垃圾郵件偵測報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="2a45b-358">在2021年6月30日， **垃圾郵件偵測報告** 將會消失。</span><span class="sxs-lookup"><span data-stu-id="2a45b-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="2a45b-359">「 [威脅防護狀態」報告](#threat-protection-status-report)中提供相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="2a45b-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="2a45b-360">欺騙偵測報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="2a45b-361">本文中所述的 [已改進的欺騙偵測報告] 是預覽中所述，視情況而變更，並非所有組織都提供這些報告。</span><span class="sxs-lookup"><span data-stu-id="2a45b-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="2a45b-362">較舊的報表版本只會顯示 **良好的郵件** ，而且會被 **視為垃圾** 郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="2a45b-363">**欺騙** 偵測報告會顯示因欺騙性而封鎖或允許的郵件相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2a45b-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="2a45b-364">如需有關電子欺騙的詳細資訊，請參閱 [EOP 中的反欺騙防護](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="2a45b-365">報表的匯總視圖允許45天的篩選 <sup>\*</sup> ，而詳細資料檢視只允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="2a45b-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="2a45b-366"><sup>\*</sup> 最後，您將可以使用超過90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="2a45b-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="2a45b-367">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="2a45b-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="2a45b-368">在 **欺騙** 偵測上，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="2a45b-369">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![電子郵件 & 協同報告] 頁面上的欺騙偵測小工具](../../media/spoof-detections-widget.png)

<span data-ttu-id="2a45b-371">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您可以看到偵測到的冒牌郵件數目及原因。</span><span class="sxs-lookup"><span data-stu-id="2a45b-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="2a45b-372">按一下 [ **查看詳細資料**] 之後，您可以按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="2a45b-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="2a45b-373">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-374">**結果**：</span><span class="sxs-lookup"><span data-stu-id="2a45b-374">**Result**:</span></span>
  - <span data-ttu-id="2a45b-375">**通過**</span><span class="sxs-lookup"><span data-stu-id="2a45b-375">**Pass**</span></span>
  - <span data-ttu-id="2a45b-376">**失敗**</span><span class="sxs-lookup"><span data-stu-id="2a45b-376">**Fail**</span></span>
  - <span data-ttu-id="2a45b-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="2a45b-377">**SoftPass**</span></span>
  - <span data-ttu-id="2a45b-378">**無**</span><span class="sxs-lookup"><span data-stu-id="2a45b-378">**None**</span></span>
  - <span data-ttu-id="2a45b-379">**其他**</span><span class="sxs-lookup"><span data-stu-id="2a45b-379">**Other**</span></span>
- <span data-ttu-id="2a45b-380">**哄騙類型**： **Internal** 和 **External**</span><span class="sxs-lookup"><span data-stu-id="2a45b-380">**Spoof type**: **Internal** and **External**</span></span>

![Microsoft 365 Defender 入口網站中的 [偽造郵件報告] 頁面](../../media/spoof-detections-report-page.png)

<span data-ttu-id="2a45b-382">在圖形下方的表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="2a45b-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="2a45b-383">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-383">**Date**</span></span>
- <span data-ttu-id="2a45b-384">**偽裝的使用者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-384">**Spoofed user**</span></span>
- <span data-ttu-id="2a45b-385">**傳送基礎結構**</span><span class="sxs-lookup"><span data-stu-id="2a45b-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="2a45b-386">**哄騙類型**</span><span class="sxs-lookup"><span data-stu-id="2a45b-386">**Spoof type**</span></span>
- <span data-ttu-id="2a45b-387">**結果**</span><span class="sxs-lookup"><span data-stu-id="2a45b-387">**Result**</span></span>
- <span data-ttu-id="2a45b-388">**結果代碼**</span><span class="sxs-lookup"><span data-stu-id="2a45b-388">**Result code**</span></span>
- <span data-ttu-id="2a45b-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="2a45b-389">**SPF**</span></span>
- <span data-ttu-id="2a45b-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="2a45b-390">**DKIM**</span></span>
- <span data-ttu-id="2a45b-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="2a45b-391">**DMARC**</span></span>
- <span data-ttu-id="2a45b-392">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="2a45b-392">**Message count**</span></span>

<span data-ttu-id="2a45b-393">如需複合驗證結果代碼的詳細資訊，請參閱[反垃圾郵件郵件頭 in Microsoft 365](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="2a45b-394">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-394">Threat protection status report</span></span>

<span data-ttu-id="2a45b-395">「**威脅防護狀態**」報告適用于 EOP 和 Defender Office 365;不過，報告包含不同的資料。</span><span class="sxs-lookup"><span data-stu-id="2a45b-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="2a45b-396">例如，EOP 客戶可以查看在電子郵件中偵測到惡意程式碼的相關資訊，但不會[Safe SharePoint、OneDrive 及 Microsoft Teams 的附件](mdo-for-spo-odb-and-teams.md)所偵測到之惡意檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2a45b-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="2a45b-397">該報告提供包含惡意內容的電子郵件統計，例如檔案或網站位址 (URLs 反惡意程式碼引擎封鎖的) 、[零小時的自動清除 (ZAP) ](zero-hour-auto-purge.md)，以及[在反網路釣魚原則中](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)Office 365[連結](safe-links.md)、 [Safe 附件](safe-attachments.md)和模擬保護功能等 Safe 功能。</span><span class="sxs-lookup"><span data-stu-id="2a45b-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="2a45b-398">您可以使用此資訊來識別趨勢，或判斷組織原則是否需要調整。</span><span class="sxs-lookup"><span data-stu-id="2a45b-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="2a45b-399">**附注：請** 務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="2a45b-400">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="2a45b-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="2a45b-401">在 [ **威脅防護狀態**] 中，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="2a45b-402">若要直接前往報告，請開啟下列其中一個 URLs：</span><span class="sxs-lookup"><span data-stu-id="2a45b-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="2a45b-403">Office 365 的 Defender：<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="2a45b-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="2a45b-404">EOP <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="2a45b-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![「電子郵件 & 協同報告」頁面上的威脅防護狀態構件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="2a45b-406">依預設，按一下 [ **查看詳細** 資料] 之後，圖表會顯示過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="2a45b-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="2a45b-407">如果您按一下 [ **篩選**]，可以選取90天的日期範圍 (試用訂閱可能限制為30天) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="2a45b-408">[詳細資料] 表格允許篩選30天。</span><span class="sxs-lookup"><span data-stu-id="2a45b-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="2a45b-409">下列各節將說明可用的視圖。</span><span class="sxs-lookup"><span data-stu-id="2a45b-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="2a45b-410">依概覽查看資料</span><span class="sxs-lookup"><span data-stu-id="2a45b-410">View data by Overview</span></span>

![威脅防護狀態報表中的一覽視圖](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="2a45b-412">在 [ **依一覽查看資料** ] 視圖中，下列偵測資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="2a45b-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="2a45b-413">**電子郵件惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="2a45b-413">**Email malware**</span></span>
- <span data-ttu-id="2a45b-414">**電子郵件網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="2a45b-414">**Email phish**</span></span>
- <span data-ttu-id="2a45b-415">**內容惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="2a45b-415">**Content malware**</span></span>

<span data-ttu-id="2a45b-416">圖表下沒有詳細資料表格可用。</span><span class="sxs-lookup"><span data-stu-id="2a45b-416">No details table is available below the chart.</span></span>

<span data-ttu-id="2a45b-417">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="2a45b-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="2a45b-418">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-419">**偵測**：**電子郵件惡意** 代碼、**電子郵件網路釣魚** 或 **內容惡意** 代碼</span><span class="sxs-lookup"><span data-stu-id="2a45b-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="2a45b-420">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="2a45b-421">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="2a45b-422">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="2a45b-423">**方向**</span><span class="sxs-lookup"><span data-stu-id="2a45b-423">**Direction**</span></span>
- <span data-ttu-id="2a45b-424">**網域**</span><span class="sxs-lookup"><span data-stu-id="2a45b-424">**Domain**</span></span>
- <span data-ttu-id="2a45b-425">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="2a45b-425">**Policy type**</span></span>

<span data-ttu-id="2a45b-426">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="2a45b-427">透過偵測技術透過電子郵件 \> 網路釣魚和圖表細目來查看資料</span><span class="sxs-lookup"><span data-stu-id="2a45b-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![威脅防護狀態報表中網路釣魚電子郵件的偵測技術視圖](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="2a45b-429">在 [透過 **電子郵件 \> 網路釣魚詐騙** ] 和 [ **依偵測方式顯示圖表明細] 技術** 視圖中，下列資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="2a45b-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="2a45b-430">**URL 惡意信譽** <sup>\*</sup> ：從其他 Microsoft 365 客戶的 Office 365 detonations 中的 Defender 產生惡意 URL 信譽。</span><span class="sxs-lookup"><span data-stu-id="2a45b-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="2a45b-431">**Advanced filter**：以機器學習為基礎的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="2a45b-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="2a45b-432">**一般篩選**：根據分析規則的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="2a45b-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="2a45b-433">**組織內的欺騙**：寄件者嘗試欺騙收件者網域。</span><span class="sxs-lookup"><span data-stu-id="2a45b-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="2a45b-434">**欺騙外部網域**：寄件者正嘗試哄騙其他一些網域。</span><span class="sxs-lookup"><span data-stu-id="2a45b-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="2a45b-435">**哄騙 DMARC**：郵件上的 DMARC 驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="2a45b-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="2a45b-436">模擬 **商標**：模擬以寄件者為基礎的知名品牌。</span><span class="sxs-lookup"><span data-stu-id="2a45b-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="2a45b-437">**混合式分析偵測**</span><span class="sxs-lookup"><span data-stu-id="2a45b-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="2a45b-438">**檔信譽**</span><span class="sxs-lookup"><span data-stu-id="2a45b-438">**File reputation**</span></span>
- <span data-ttu-id="2a45b-439">**指紋比對**</span><span class="sxs-lookup"><span data-stu-id="2a45b-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="2a45b-440">**URL 引爆信譽**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="2a45b-441">**URL 引爆**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="2a45b-442">**類比使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="2a45b-443">**類比網域** <sup>\*</sup> ：模仿客戶擁有或定義的網域。</span><span class="sxs-lookup"><span data-stu-id="2a45b-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="2a45b-444">**信箱智慧** 模擬 <sup>\*</sup> ：由系統管理員定義或透過信箱智慧學出的使用者類比。</span><span class="sxs-lookup"><span data-stu-id="2a45b-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="2a45b-445">**檔引爆**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="2a45b-446">**運動**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="2a45b-447">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="2a45b-448">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-448">**Date**</span></span>
- <span data-ttu-id="2a45b-449">**主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-449">**Subject**</span></span>
- <span data-ttu-id="2a45b-450">**Sender**</span><span class="sxs-lookup"><span data-stu-id="2a45b-450">**Sender**</span></span>
- <span data-ttu-id="2a45b-451">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-451">**Recipients**</span></span>
- <span data-ttu-id="2a45b-452">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="2a45b-452">**Detected by**</span></span>
- <span data-ttu-id="2a45b-453">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="2a45b-453">**Delivery Status**</span></span>
- <span data-ttu-id="2a45b-454">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="2a45b-454">**Source of Compromise**</span></span>
- <span data-ttu-id="2a45b-455">**標記**</span><span class="sxs-lookup"><span data-stu-id="2a45b-455">**Tags**</span></span>

<span data-ttu-id="2a45b-456">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="2a45b-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="2a45b-457">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-458">**偵測**</span><span class="sxs-lookup"><span data-stu-id="2a45b-458">**Detection**</span></span>
- <span data-ttu-id="2a45b-459">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="2a45b-460">**方向**</span><span class="sxs-lookup"><span data-stu-id="2a45b-460">**Direction**</span></span>
- <span data-ttu-id="2a45b-461">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="2a45b-462">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="2a45b-463">**網域**</span><span class="sxs-lookup"><span data-stu-id="2a45b-463">**Domain**</span></span>
- <span data-ttu-id="2a45b-464">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="2a45b-464">**Policy type**</span></span>
- <span data-ttu-id="2a45b-465">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="2a45b-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="2a45b-466">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-466">**Recipients**</span></span>

<span data-ttu-id="2a45b-467">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="2a45b-468">透過電子郵件 \> 惡意程式碼和偵測技術的圖表細目來查看資料</span><span class="sxs-lookup"><span data-stu-id="2a45b-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![威脅防護狀態報表中惡意程式碼的偵測技術視圖](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="2a45b-470">在 [透過 **電子郵件 \> 惡意** 代碼和 **依偵測方式顯示圖表的** 資料] 技術視圖中，下列資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="2a45b-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="2a45b-471">檔案 **引爆** <sup>\*</sup> ： Safe 附件的偵測。</span><span class="sxs-lookup"><span data-stu-id="2a45b-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="2a45b-472">檔案 **引爆信譽** <sup>\*</sup> ：所有由 Defender 為 Office 365 detonations 所產生的惡意檔信譽。</span><span class="sxs-lookup"><span data-stu-id="2a45b-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="2a45b-473">**檔信譽**</span><span class="sxs-lookup"><span data-stu-id="2a45b-473">**File reputation**</span></span>
- <span data-ttu-id="2a45b-474">**反惡意程式碼引擎** <sup>\*</sup> ：從反惡意程式碼引擎偵測。</span><span class="sxs-lookup"><span data-stu-id="2a45b-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="2a45b-475">**反惡意程式碼原則檔案類型封鎖**：由於郵件中所識別的惡意檔案類型，郵件會篩選掉這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2a45b-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="2a45b-476">**URL 惡意信譽**</span><span class="sxs-lookup"><span data-stu-id="2a45b-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="2a45b-477">**URL 引爆**</span><span class="sxs-lookup"><span data-stu-id="2a45b-477">**URL detonation**</span></span>
- <span data-ttu-id="2a45b-478">**URL 引爆信譽**</span><span class="sxs-lookup"><span data-stu-id="2a45b-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="2a45b-479">**行銷活動**</span><span class="sxs-lookup"><span data-stu-id="2a45b-479">**Campaign**</span></span>

<span data-ttu-id="2a45b-480">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="2a45b-481">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-481">**Date**</span></span>
- <span data-ttu-id="2a45b-482">**主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-482">**Subject**</span></span>
- <span data-ttu-id="2a45b-483">**Sender**</span><span class="sxs-lookup"><span data-stu-id="2a45b-483">**Sender**</span></span>
- <span data-ttu-id="2a45b-484">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-484">**Recipients**</span></span>
- <span data-ttu-id="2a45b-485">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="2a45b-485">**Detected by**</span></span>
- <span data-ttu-id="2a45b-486">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="2a45b-486">**Delivery Status**</span></span>
- <span data-ttu-id="2a45b-487">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="2a45b-487">**Source of Compromise**</span></span>
- <span data-ttu-id="2a45b-488">**標記**</span><span class="sxs-lookup"><span data-stu-id="2a45b-488">**Tags**</span></span>

<span data-ttu-id="2a45b-489">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="2a45b-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="2a45b-490">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-491">**偵測**</span><span class="sxs-lookup"><span data-stu-id="2a45b-491">**Detection**</span></span>
- <span data-ttu-id="2a45b-492">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="2a45b-493">**方向**</span><span class="sxs-lookup"><span data-stu-id="2a45b-493">**Direction**</span></span>
- <span data-ttu-id="2a45b-494">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="2a45b-495">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="2a45b-496">**網域**</span><span class="sxs-lookup"><span data-stu-id="2a45b-496">**Domain**</span></span>
- <span data-ttu-id="2a45b-497">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="2a45b-497">**Policy type**</span></span>
- <span data-ttu-id="2a45b-498">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="2a45b-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="2a45b-499">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-499">**Recipients**</span></span>

<span data-ttu-id="2a45b-500">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="2a45b-501">依電子郵件 \> 網路釣魚或透過電子郵件惡意程式碼查看資料的方式，依原則類型分類的圖表 \></span><span class="sxs-lookup"><span data-stu-id="2a45b-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威脅防護狀態報表中的網路釣魚電子郵件或惡意程式碼電子郵件的原則類型查看](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="2a45b-503">在 [ **依原則類型的圖表分解** ] 和 [透過電子郵件惡意程式碼 **查看資料 \>** ] 或 [透過 **電子郵件 \> 惡意程式碼查看資料** ] 視圖中，圖表會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="2a45b-504">**反惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="2a45b-504">**Anti-malware**</span></span>
- <span data-ttu-id="2a45b-505">**Safe附件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a45b-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="2a45b-506">**反網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="2a45b-506">**Anti-phish**</span></span>
- <span data-ttu-id="2a45b-507">**反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-507">**Anti-spam**</span></span>
- <span data-ttu-id="2a45b-508">**郵件流程規則** (也稱為傳輸規則) </span><span class="sxs-lookup"><span data-stu-id="2a45b-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="2a45b-509">**別人**</span><span class="sxs-lookup"><span data-stu-id="2a45b-509">**Others**</span></span>

<span data-ttu-id="2a45b-510">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="2a45b-511">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-511">**Date**</span></span>
- <span data-ttu-id="2a45b-512">**主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-512">**Subject**</span></span>
- <span data-ttu-id="2a45b-513">**Sender**</span><span class="sxs-lookup"><span data-stu-id="2a45b-513">**Sender**</span></span>
- <span data-ttu-id="2a45b-514">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-514">**Recipients**</span></span>
- <span data-ttu-id="2a45b-515">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="2a45b-515">**Detected by**</span></span>
- <span data-ttu-id="2a45b-516">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="2a45b-516">**Delivery Status**</span></span>
- <span data-ttu-id="2a45b-517">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="2a45b-517">**Source of Compromise**</span></span>
- <span data-ttu-id="2a45b-518">**標記**</span><span class="sxs-lookup"><span data-stu-id="2a45b-518">**Tags**</span></span>

<span data-ttu-id="2a45b-519">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="2a45b-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="2a45b-520">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-521">**偵測**</span><span class="sxs-lookup"><span data-stu-id="2a45b-521">**Detection**</span></span>
- <span data-ttu-id="2a45b-522">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="2a45b-523">**方向**</span><span class="sxs-lookup"><span data-stu-id="2a45b-523">**Direction**</span></span>
- <span data-ttu-id="2a45b-524">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="2a45b-525">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="2a45b-526">**網域**</span><span class="sxs-lookup"><span data-stu-id="2a45b-526">**Domain**</span></span>
- <span data-ttu-id="2a45b-527">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="2a45b-527">**Policy type**</span></span>
- <span data-ttu-id="2a45b-528">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="2a45b-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="2a45b-529">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-529">**Recipients**</span></span>

<span data-ttu-id="2a45b-530">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="2a45b-531">透過電子郵件 \> 網路釣魚或透過電子郵件惡意程式碼查看資料，依傳遞狀態與查看資料的圖表細目 \></span><span class="sxs-lookup"><span data-stu-id="2a45b-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威脅防護狀態報表中的網路釣魚電子郵件和惡意程式碼電子郵件的傳遞狀態視圖](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="2a45b-533">在 **圖表** 中透過 **電子郵件 \> 網路釣魚** 或透過電子郵件 **\> 惡意** 代碼查看資料來查看資料，圖表會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="2a45b-534">**主控信箱：收件匣**</span><span class="sxs-lookup"><span data-stu-id="2a45b-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="2a45b-535">**主控信箱：垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="2a45b-536">**主控信箱：自訂資料夾**</span><span class="sxs-lookup"><span data-stu-id="2a45b-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="2a45b-537">**主控信箱：刪除的郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="2a45b-538">**轉發**</span><span class="sxs-lookup"><span data-stu-id="2a45b-538">**Forwarded**</span></span>
- <span data-ttu-id="2a45b-539">**內部部署伺服器：已傳送**</span><span class="sxs-lookup"><span data-stu-id="2a45b-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="2a45b-540">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="2a45b-540">**Quarantine**</span></span>
- <span data-ttu-id="2a45b-541">**傳遞失敗**</span><span class="sxs-lookup"><span data-stu-id="2a45b-541">**Delivery failed**</span></span>
- <span data-ttu-id="2a45b-542">**下降**</span><span class="sxs-lookup"><span data-stu-id="2a45b-542">**Dropped**</span></span>

<span data-ttu-id="2a45b-543">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="2a45b-544">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-544">**Date**</span></span>
- <span data-ttu-id="2a45b-545">**主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-545">**Subject**</span></span>
- <span data-ttu-id="2a45b-546">**Sender**</span><span class="sxs-lookup"><span data-stu-id="2a45b-546">**Sender**</span></span>
- <span data-ttu-id="2a45b-547">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-547">**Recipients**</span></span>
- <span data-ttu-id="2a45b-548">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="2a45b-548">**Detected by**</span></span>
- <span data-ttu-id="2a45b-549">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="2a45b-549">**Delivery Status**</span></span>
- <span data-ttu-id="2a45b-550">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="2a45b-550">**Source of Compromise**</span></span>
- <span data-ttu-id="2a45b-551">**標記**</span><span class="sxs-lookup"><span data-stu-id="2a45b-551">**Tags**</span></span>

<span data-ttu-id="2a45b-552">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="2a45b-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="2a45b-553">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-554">**偵測**</span><span class="sxs-lookup"><span data-stu-id="2a45b-554">**Detection**</span></span>
- <span data-ttu-id="2a45b-555">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="2a45b-556">**方向**</span><span class="sxs-lookup"><span data-stu-id="2a45b-556">**Direction**</span></span>
- <span data-ttu-id="2a45b-557">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="2a45b-558">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="2a45b-559">**網域**</span><span class="sxs-lookup"><span data-stu-id="2a45b-559">**Domain**</span></span>
- <span data-ttu-id="2a45b-560">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="2a45b-560">**Policy type**</span></span>
- <span data-ttu-id="2a45b-561">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="2a45b-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="2a45b-562">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-562">**Recipients**</span></span>

<span data-ttu-id="2a45b-563">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="2a45b-564">依惡意程式碼查看資料 \></span><span class="sxs-lookup"><span data-stu-id="2a45b-564">View data by Content \> Malware</span></span>

![威脅防護狀態報表中的內容惡意程式碼視圖](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="2a45b-566">在 [**依內容 \> 惡意** 代碼查看資料] 視圖中，下列資訊會顯示在適用于 Office 365 組織的 Microsoft Defender 圖表中：</span><span class="sxs-lookup"><span data-stu-id="2a45b-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="2a45b-567">**反惡意程式碼引擎**： [Microsoft 365 中內建的病毒偵測](virus-detection-in-spo.md)，在 Sharepoint、OneDrive 及 Microsoft Teams 中偵測到惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="2a45b-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="2a45b-568">檔案 **引爆**： [Safe SharePoint、OneDrive 及 Microsoft Teams 的附件](mdo-for-spo-odb-and-teams.md)所偵測到的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="2a45b-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="2a45b-569">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="2a45b-570">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-571">**位置**</span><span class="sxs-lookup"><span data-stu-id="2a45b-571">**Location**</span></span>
- <span data-ttu-id="2a45b-572">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="2a45b-572">**Detected by**</span></span>
- <span data-ttu-id="2a45b-573">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="2a45b-573">**Malware name**</span></span>

<span data-ttu-id="2a45b-574">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="2a45b-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="2a45b-575">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-576">**偵測**： **反惡意程式碼引擎** 或 **檔引爆**</span><span class="sxs-lookup"><span data-stu-id="2a45b-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="2a45b-577">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="2a45b-578">依系統覆寫查看資料</span><span class="sxs-lookup"><span data-stu-id="2a45b-578">View data by System override</span></span>

![威脅防護狀態報表中的郵件覆寫視圖](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="2a45b-580">在 [ **依系統覆寫查看資料** ] 視圖中，下列的覆寫原因資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="2a45b-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="2a45b-581">**內部部署略過**</span><span class="sxs-lookup"><span data-stu-id="2a45b-581">**On-premises skip**</span></span>
- <span data-ttu-id="2a45b-582">**IP 允許**</span><span class="sxs-lookup"><span data-stu-id="2a45b-582">**IP allow**</span></span>
- <span data-ttu-id="2a45b-583">**Exchange 郵件傳輸規則** (郵件流程規則) </span><span class="sxs-lookup"><span data-stu-id="2a45b-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="2a45b-584">**組織允許的寄件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="2a45b-585">**組織允許的網域**</span><span class="sxs-lookup"><span data-stu-id="2a45b-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="2a45b-586">**未啟用的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="2a45b-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="2a45b-587">**未啟用垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="2a45b-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="2a45b-588">**使用者 Safe 寄件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-588">**User Safe Sender**</span></span>
- <span data-ttu-id="2a45b-589">**使用者 Safe 網域**</span><span class="sxs-lookup"><span data-stu-id="2a45b-589">**User Safe Domain**</span></span>

<span data-ttu-id="2a45b-590">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="2a45b-591">**Date**</span><span class="sxs-lookup"><span data-stu-id="2a45b-591">**Date**</span></span>
- <span data-ttu-id="2a45b-592">**主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-592">**Subject**</span></span>
- <span data-ttu-id="2a45b-593">**Sender**</span><span class="sxs-lookup"><span data-stu-id="2a45b-593">**Sender**</span></span>
- <span data-ttu-id="2a45b-594">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-594">**Recipients**</span></span>
- <span data-ttu-id="2a45b-595">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="2a45b-595">**Detected by**</span></span>
- <span data-ttu-id="2a45b-596">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="2a45b-596">**Delivery Status**</span></span>
- <span data-ttu-id="2a45b-597">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="2a45b-597">**Source of Compromise**</span></span>
- <span data-ttu-id="2a45b-598">**標記**</span><span class="sxs-lookup"><span data-stu-id="2a45b-598">**Tags**</span></span>

<span data-ttu-id="2a45b-599">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="2a45b-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="2a45b-600">**日期**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="2a45b-601">**偵測**</span><span class="sxs-lookup"><span data-stu-id="2a45b-601">**Detection**</span></span>
- <span data-ttu-id="2a45b-602">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="2a45b-603">**方向**</span><span class="sxs-lookup"><span data-stu-id="2a45b-603">**Direction**</span></span>
- <span data-ttu-id="2a45b-604">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="2a45b-605">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="2a45b-606">**網域**</span><span class="sxs-lookup"><span data-stu-id="2a45b-606">**Domain**</span></span>
- <span data-ttu-id="2a45b-607">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="2a45b-607">**Policy type**</span></span>
- <span data-ttu-id="2a45b-608">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="2a45b-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="2a45b-609">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-609">**Recipients**</span></span>

<span data-ttu-id="2a45b-610">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="2a45b-611"><sup>\*</sup>僅限 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="2a45b-612">主要惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-612">Top malware report</span></span>

<span data-ttu-id="2a45b-613">**主要惡意** 代碼報告會顯示 [EOP 中的反惡意程式碼防護](anti-malware-protection.md)所偵測到的各種惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="2a45b-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="2a45b-614">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="2a45b-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="2a45b-615">在 [ **主要惡意** 代碼] 上，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="2a45b-616">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![「電子郵件 & 協同報告」頁面上的主要惡意程式碼小工具](../../media/top-malware-report-widget.png)

<span data-ttu-id="2a45b-618">當您將游標移到圓形圖中的楔形上方時，您可以看到惡意程式碼類型的名稱，以及偵測到該惡意程式碼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2a45b-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="2a45b-619">按一下 [ **查看詳細資料**] 之後，報表頁面上便會顯示較大的餅版本圖表。圖表下方的 [詳細資料] 表格會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2a45b-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="2a45b-620">**主要惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="2a45b-620">**Top malware**</span></span>
- <span data-ttu-id="2a45b-621">**Count**</span><span class="sxs-lookup"><span data-stu-id="2a45b-621">**Count**</span></span>

<span data-ttu-id="2a45b-622">如果您按一下 [ **篩選**]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="2a45b-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![主要惡意程式碼報表檢視](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="2a45b-624">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-624">URL threat protection report</span></span>

<span data-ttu-id="2a45b-625">Office 365 的「 **URL 威脅防護」報告** 可用於的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="2a45b-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="2a45b-626">如需詳細資訊，請參閱 [URL 威脅防護報告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="2a45b-627">使用者報告的訊息報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a45b-628">為了讓 **使用者報告的訊息** 報告正確運作，必須為您的 Microsoft 365 環境 **開啟審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="2a45b-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="2a45b-629">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="2a45b-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="2a45b-630">如需詳細資訊，請參閱[開啟或關閉 Microsoft 365 審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="2a45b-631">「 **使用者報告的訊息** 報告」顯示使用者已使用 [報告郵件增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)舉報為垃圾郵件、網路釣魚企圖或良好郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2a45b-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="2a45b-632">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 & 共同作業報告** \> **使用者報告的訊息**。</span><span class="sxs-lookup"><span data-stu-id="2a45b-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="2a45b-633">在 [ **使用者報告的郵件**] 上，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="2a45b-634">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="2a45b-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="2a45b-635">若要移至 [Microsoft 365 Defender 入口網站中的系統管理提交](admin-submission.md)，按一下 [**移至提交**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![「電子郵件 & 共同作業報告」頁面上的使用者報告的訊息小工具](../../media/user-reported-messages-widget.png)

<span data-ttu-id="2a45b-637">按一下 [ **查看詳細資料**] 之後，您可以按一下 [ **篩選** ]，然後在出現的浮出控制項中選取下列一或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="2a45b-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="2a45b-638">**報告日期**： **開始時間** 和 **結束時間**</span><span class="sxs-lookup"><span data-stu-id="2a45b-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="2a45b-639">**報告者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-639">**Reported by**</span></span>
- <span data-ttu-id="2a45b-640">**電子郵件主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-640">**Email subject**</span></span>
- <span data-ttu-id="2a45b-641">**訊息報告識別碼**</span><span class="sxs-lookup"><span data-stu-id="2a45b-641">**Message reported ID**</span></span>
- <span data-ttu-id="2a45b-642">**網路消息識別碼**</span><span class="sxs-lookup"><span data-stu-id="2a45b-642">**Network Message ID**</span></span>
- <span data-ttu-id="2a45b-643">**Sender**</span><span class="sxs-lookup"><span data-stu-id="2a45b-643">**Sender**</span></span>
- <span data-ttu-id="2a45b-644">**報告原因**</span><span class="sxs-lookup"><span data-stu-id="2a45b-644">**Reported reason**</span></span>
  - <span data-ttu-id="2a45b-645">**非垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-645">**Not junk**</span></span>
  - <span data-ttu-id="2a45b-646">**網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="2a45b-646">**Phish**</span></span>
  - <span data-ttu-id="2a45b-647">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2a45b-647">**Spam**</span></span>
- <span data-ttu-id="2a45b-648">**網路釣魚模擬**： **是** 或 **否**</span><span class="sxs-lookup"><span data-stu-id="2a45b-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="2a45b-649">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="2a45b-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="2a45b-650">若要群組專案，請按一下 [ **群組** ]，然後從下拉式清單中選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="2a45b-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="2a45b-651">**無**</span><span class="sxs-lookup"><span data-stu-id="2a45b-651">**None**</span></span>
- <span data-ttu-id="2a45b-652">**原因**</span><span class="sxs-lookup"><span data-stu-id="2a45b-652">**Reason**</span></span>
- <span data-ttu-id="2a45b-653">**Sender**</span><span class="sxs-lookup"><span data-stu-id="2a45b-653">**Sender**</span></span>
- <span data-ttu-id="2a45b-654">**報告者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-654">**Reported by**</span></span>
- <span data-ttu-id="2a45b-655">**重新掃描結果**</span><span class="sxs-lookup"><span data-stu-id="2a45b-655">**Rescan result**</span></span>
- <span data-ttu-id="2a45b-656">**網路釣魚模擬模擬**</span><span class="sxs-lookup"><span data-stu-id="2a45b-656">**Phish simulation**</span></span>

![使用者報告的訊息報告](../../media/user-reported-messages-report.png)

<span data-ttu-id="2a45b-658">在圖形下方的表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="2a45b-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="2a45b-659">**電子郵件主旨**</span><span class="sxs-lookup"><span data-stu-id="2a45b-659">**Email subject**</span></span>
- <span data-ttu-id="2a45b-660">**報告者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-660">**Reported by**</span></span>
- <span data-ttu-id="2a45b-661">**報告日期**</span><span class="sxs-lookup"><span data-stu-id="2a45b-661">**Date reported**</span></span>
- <span data-ttu-id="2a45b-662">**Sender**</span><span class="sxs-lookup"><span data-stu-id="2a45b-662">**Sender**</span></span>
- <span data-ttu-id="2a45b-663">**報告原因**</span><span class="sxs-lookup"><span data-stu-id="2a45b-663">**Reported reason**</span></span>
- <span data-ttu-id="2a45b-664">**重新掃描結果**</span><span class="sxs-lookup"><span data-stu-id="2a45b-664">**Rescan result**</span></span>
- <span data-ttu-id="2a45b-665">**標記**</span><span class="sxs-lookup"><span data-stu-id="2a45b-665">**Tags**</span></span>

<span data-ttu-id="2a45b-666">若要將郵件提交給 Microsoft 進行分析，請選取表格中的訊息項目，按一下 [ **提交給 Microsoft 進行分析** ]，然後從下拉式清單中選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="2a45b-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="2a45b-667">**報告清理**</span><span class="sxs-lookup"><span data-stu-id="2a45b-667">**Report clean**</span></span>
- <span data-ttu-id="2a45b-668">**報告網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="2a45b-668">**Report phishing**</span></span>
- <span data-ttu-id="2a45b-669">**報告惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="2a45b-669">**Report malware**</span></span>
- <span data-ttu-id="2a45b-670">**報告垃圾郵件**'</span><span class="sxs-lookup"><span data-stu-id="2a45b-670">**Report spam**'</span></span>
- <span data-ttu-id="2a45b-671">Office 365) 的 **觸發調查** (Defender</span><span class="sxs-lookup"><span data-stu-id="2a45b-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="2a45b-672">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="2a45b-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="2a45b-673">為了查看和使用本文所述的報表，您必須是 Microsoft 365 Defender 入口網站中下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="2a45b-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="2a45b-674">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="2a45b-674">**Organization Management**</span></span>
- <span data-ttu-id="2a45b-675">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="2a45b-675">**Security Administrator**</span></span>
- <span data-ttu-id="2a45b-676">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="2a45b-676">**Security Reader**</span></span>
- <span data-ttu-id="2a45b-677">**全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="2a45b-677">**Global Reader**</span></span>

<span data-ttu-id="2a45b-678">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="2a45b-679">**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="2a45b-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2a45b-680">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="2a45b-681">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="2a45b-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="2a45b-682">如果您未看到報表中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="2a45b-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="2a45b-683">若要深入瞭解，請參閱 [防禦威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="2a45b-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a45b-684">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a45b-684">Related topics</span></span>

[<span data-ttu-id="2a45b-685">EOP 中的反垃圾郵件和反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="2a45b-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="2a45b-686">Microsoft 365 Defender 入口網站中的智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="2a45b-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="2a45b-687">在 Microsoft 365 Defender 入口網站中查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="2a45b-688">View Office 365 的 Defender 報告</span><span class="sxs-lookup"><span data-stu-id="2a45b-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
