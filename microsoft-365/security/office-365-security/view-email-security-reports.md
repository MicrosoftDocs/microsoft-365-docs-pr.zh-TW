---
title: 檢視電子郵件安全性報告
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
description: 系統管理員可以瞭解如何尋找及使用 Microsoft 365 Defender 入口網站中提供的電子郵件安全性報告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3dcf533c232a89adf0dc1ff3fcc7c2ca4fc5d8f
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022912"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="73e7f-103">在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="73e7f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="73e7f-104">**Applies to**</span></span>
- [<span data-ttu-id="73e7f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="73e7f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="73e7f-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="73e7f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="73e7f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="73e7f-108">Microsoft 365 Defender 入口網站提供各種報告 <https://security.microsoft.com> ，可協助您觀察電子郵件安全性功能（例如 Microsoft 365 中的反垃圾郵件、反惡意程式碼和加密功能）如何保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="73e7f-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="73e7f-109">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以在 Microsoft 365 Defender 入口網站中查看這些報告，方式是要 **報告** \> **電子郵件 &** 共同作業 & 共同作業 \> **報告**。</span><span class="sxs-lookup"><span data-stu-id="73e7f-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-110">若要直接移至 [ **電子郵件 &** 共同作業報告] 頁面上，開啟 <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender 入口網站中的電子郵件 & 共同作業報告] 頁面](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="73e7f-112">[ **電子郵件 & 協同報告** ] 頁面上的某些報告需要 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="73e7f-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="73e7f-113">如需這些報告的詳細資訊，請參閱 [在 Microsoft 365 Defender 入口網站中查看 Office 365 報告的 Defender](view-reports-for-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="73e7f-114">與郵件流程相關的報告現在位於 Exchange 系統管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="73e7f-115">如需這些報告的詳細資訊，請參閱 [新 Exchange 系統管理中心的郵件流程報告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="73e7f-116">已遭破壞的使用者報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="73e7f-117">這份報告可在 Microsoft 365 組織中使用 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="73e7f-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="73e7f-118">在獨立 Exchange Online Protection (EOP) 組織中無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="73e7f-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="73e7f-119">「已 **遭破壞的使用者** 報告」顯示顯示過去7天內已標示為 **可疑** 或 **限制** 的使用者帳戶數目。</span><span class="sxs-lookup"><span data-stu-id="73e7f-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="73e7f-120">在上述任一狀態的帳戶都有問題或甚至遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="73e7f-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="73e7f-121">在經常使用的情況下，您可以使用報表來找出峰值，甚至是趨勢，也就是可疑或受限制的帳戶。</span><span class="sxs-lookup"><span data-stu-id="73e7f-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="73e7f-122">如需遭到破壞之使用者的詳細資訊，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![「電子郵件 & 共同作業報告」頁面上已遭破壞的使用者小工具](../../media/compromised-users-report-widget.png)

<span data-ttu-id="73e7f-124">匯總視圖會顯示過去90天的資料，詳細資料檢視會顯示過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="73e7f-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="73e7f-125">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-126">在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 **遭破壞的使用者** ，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="73e7f-127">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="73e7f-128">在 [已 **遭破壞的使用者** ] 頁面上，您可以按一下 [ **篩選** ]，然後在出現的飛出視窗中，選取下列一或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="73e7f-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="73e7f-129">**日期 (UTC)**： **開始日期** 和 **結束日期**。</span><span class="sxs-lookup"><span data-stu-id="73e7f-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="73e7f-130">**活動**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-130">**Activity**:</span></span>
  - <span data-ttu-id="73e7f-131">**可疑**：使用者帳戶已傳送可疑的電子郵件，而且受到限制傳送電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="73e7f-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="73e7f-132">**限制**：由於高度可疑的模式，使用者帳戶已限制傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="73e7f-133">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![已遭破壞之使用者報告中的報表檢視](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="73e7f-135">在圖形下方的 [詳細資料] 表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="73e7f-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="73e7f-136">**建立時間**</span><span class="sxs-lookup"><span data-stu-id="73e7f-136">**Creation time**</span></span>
- <span data-ttu-id="73e7f-137">**User ID**</span><span class="sxs-lookup"><span data-stu-id="73e7f-137">**User ID**</span></span>
- <span data-ttu-id="73e7f-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="73e7f-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="73e7f-139">Exchange transport rule 報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-139">Exchange transport rule report</span></span>

<span data-ttu-id="73e7f-140">**Exchange transport rule** report 會顯示郵件流程規則 (也稱為傳輸規則) 組織中內送和外寄郵件的效果。</span><span class="sxs-lookup"><span data-stu-id="73e7f-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="73e7f-141">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-142">在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 [ **Exchange transport rule** ]，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="73e7f-143">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![「電子郵件 & 共同作業報告」頁面上的 Exchange 傳輸規則小工具](../../media/transport-rule-report-widget.png)

<span data-ttu-id="73e7f-145">在 [ **Exchange transport rule 報告** ] 頁面上，下列各節將說明可用的圖表和資料。</span><span class="sxs-lookup"><span data-stu-id="73e7f-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="73e7f-146">依方向的圖表分解</span><span class="sxs-lookup"><span data-stu-id="73e7f-146">Chart breakdown by Direction</span></span>

![Exchange transport rule 報告中 Exchange Transport rules 的方向視圖](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="73e7f-148">如果您 **依方向選取 [圖表分解**]，可使用下列圖表：</span><span class="sxs-lookup"><span data-stu-id="73e7f-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="73e7f-149">透過 **Exchange 傳輸規則來查看資料**：受郵件流程規則影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="73e7f-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="73e7f-150">**以 DLP Exchange 傳輸規則來查看資料**：受資料遺失防護 (DLP) 郵件流程規則所影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="73e7f-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="73e7f-151">下列資訊會顯示在圖形下方的詳細資料表格中：</span><span class="sxs-lookup"><span data-stu-id="73e7f-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="73e7f-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-152">**Date**</span></span>
- <span data-ttu-id="73e7f-153">**Dlp 原則** (只 **依 dlp Exchange Transport rules 來查看資料**) </span><span class="sxs-lookup"><span data-stu-id="73e7f-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="73e7f-154">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="73e7f-154">**Transport rule**</span></span>
- <span data-ttu-id="73e7f-155">**主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-155">**Subject**</span></span>
- <span data-ttu-id="73e7f-156">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="73e7f-156">**Sender address**</span></span>
- <span data-ttu-id="73e7f-157">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="73e7f-157">**Recipient address**</span></span>
- <span data-ttu-id="73e7f-158">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="73e7f-158">**Severity**</span></span>
- <span data-ttu-id="73e7f-159">**方向**</span><span class="sxs-lookup"><span data-stu-id="73e7f-159">**Direction**</span></span>

<span data-ttu-id="73e7f-160">您可以在出現的浮出控制項中按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="73e7f-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="73e7f-161">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-162">**方向**： **輸出** 和 **輸入**</span><span class="sxs-lookup"><span data-stu-id="73e7f-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="73e7f-163">**嚴重性**： **高嚴重性**、 **中低嚴重性** 和 **低嚴重性**</span><span class="sxs-lookup"><span data-stu-id="73e7f-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="73e7f-164">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="73e7f-165">依嚴重性的圖表細目</span><span class="sxs-lookup"><span data-stu-id="73e7f-165">Chart breakdown by Severity</span></span>

![Exchange transport rule 報告中 Exchange Transport rules 的嚴重性視圖](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="73e7f-167">如果您 **依嚴重性選取 [圖表分解**]，可使用下列圖表：</span><span class="sxs-lookup"><span data-stu-id="73e7f-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="73e7f-168">透過 **Exchange 傳輸規則來查看資料**：**高嚴重性**、**中嚴重性** 和 **低嚴重性** 郵件的數目。</span><span class="sxs-lookup"><span data-stu-id="73e7f-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="73e7f-169">您可以將嚴重性層級設定為規則 ([ **以嚴重性層級** 或 _SetAuditSeverity_) 審核此規則] 中的動作。</span><span class="sxs-lookup"><span data-stu-id="73e7f-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="73e7f-170">如需詳細資訊，請參閱 [Exchange Online 中的郵件流程規則動作](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="73e7f-171">**按 Dlp Exchange transport rules 來查看資料**：受 dlp 郵件流程規則影響的 **高嚴重性**、 **中嚴重性** 和 **低嚴重性** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="73e7f-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="73e7f-172">下列資訊會顯示在圖形下方的詳細資料表格中：</span><span class="sxs-lookup"><span data-stu-id="73e7f-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="73e7f-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-173">**Date**</span></span>
- <span data-ttu-id="73e7f-174">**Dlp 原則** (只 **依 dlp Exchange Transport rules 來查看資料**) </span><span class="sxs-lookup"><span data-stu-id="73e7f-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="73e7f-175">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="73e7f-175">**Transport rule**</span></span>
- <span data-ttu-id="73e7f-176">**主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-176">**Subject**</span></span>
- <span data-ttu-id="73e7f-177">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="73e7f-177">**Sender address**</span></span>
- <span data-ttu-id="73e7f-178">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="73e7f-178">**Recipient address**</span></span>
- <span data-ttu-id="73e7f-179">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="73e7f-179">**Severity**</span></span>
- <span data-ttu-id="73e7f-180">**方向**</span><span class="sxs-lookup"><span data-stu-id="73e7f-180">**Direction**</span></span>

<span data-ttu-id="73e7f-181">您可以在出現的浮出控制項中按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="73e7f-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="73e7f-182">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-183">**方向**： **輸出** 和 **輸入**</span><span class="sxs-lookup"><span data-stu-id="73e7f-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="73e7f-184">**嚴重性**： **高嚴重性**、 **中低嚴重性** 和 **低嚴重性**</span><span class="sxs-lookup"><span data-stu-id="73e7f-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="73e7f-185">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="73e7f-186">轉接報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="73e7f-187">您現在可以在 EAC 中使用轉寄 **報告** 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="73e7f-188">如需詳細資訊，請參閱 [新 EAC 中的自動轉寄郵件報告](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="73e7f-189">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="73e7f-189">Mailflow status report</span></span>

<span data-ttu-id="73e7f-190">**郵件流程狀態報表** 是一個智慧報告，顯示傳入和傳出電子郵件、垃圾郵件偵測、惡意程式碼、識別為「良好」之電子郵件的相關資訊，以及有關允許或封鎖在 edge 上之電子郵件的資訊。</span><span class="sxs-lookup"><span data-stu-id="73e7f-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="73e7f-191">這是唯一包含 edge protection 資訊的報告，它會顯示在 Exchange Online Protection (EOP) 中，允許在評估之前封鎖多少封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="73e7f-192">請務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="73e7f-193">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-194">在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 **郵件流程狀態摘要** ，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="73e7f-195">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![[電子郵件 & 共同作業報告] 頁面上的 [郵件流程狀態摘要] 小工具](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="73e7f-197">郵件流程狀態報表的類型視圖</span><span class="sxs-lookup"><span data-stu-id="73e7f-197">Type view for the Mailflow status report</span></span>

<span data-ttu-id="73e7f-198">當您開啟報表時，預設會選取 [ **類型** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="73e7f-198">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="73e7f-199">根據預設，此視圖包含的圖表和詳細資料表格已設定為下列篩選：</span><span class="sxs-lookup"><span data-stu-id="73e7f-199">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="73e7f-200">**日期 (UTC)** 過去7天。</span><span class="sxs-lookup"><span data-stu-id="73e7f-200">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="73e7f-201">**郵件方向**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-201">**Mail direction**:</span></span>
  - <span data-ttu-id="73e7f-202">**入境**</span><span class="sxs-lookup"><span data-stu-id="73e7f-202">**Inbound**</span></span>
  - <span data-ttu-id="73e7f-203">**出境**</span><span class="sxs-lookup"><span data-stu-id="73e7f-203">**Outbound**</span></span>
  - <span data-ttu-id="73e7f-204">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="73e7f-204">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="73e7f-205">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與 **輸入** 和 **輸出**) 分開計數</span><span class="sxs-lookup"><span data-stu-id="73e7f-205">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="73e7f-206">**類型**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-206">**Type**:</span></span>
  - <span data-ttu-id="73e7f-207">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-207">**Good mail**</span></span>
  - <span data-ttu-id="73e7f-208">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-208">**Malware**</span></span>
  - <span data-ttu-id="73e7f-209">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-209">**Spam**</span></span>
  - <span data-ttu-id="73e7f-210">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="73e7f-210">**Edge protection**</span></span>
  - <span data-ttu-id="73e7f-211">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="73e7f-211">**Rule messages**</span></span>
  - <span data-ttu-id="73e7f-212">**網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-212">**Phishing email**</span></span>
- <span data-ttu-id="73e7f-213">**網域**： **全部**</span><span class="sxs-lookup"><span data-stu-id="73e7f-213">**Domain**: **All**</span></span>

<span data-ttu-id="73e7f-214">圖表是依 **類型** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="73e7f-214">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="73e7f-215">您可以按一下 [ **篩選器** ] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-215">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="73e7f-216">下列資訊會顯示在圖形下方的詳細資料表格中：</span><span class="sxs-lookup"><span data-stu-id="73e7f-216">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="73e7f-217">**方向**</span><span class="sxs-lookup"><span data-stu-id="73e7f-217">**Direction**</span></span>
- <span data-ttu-id="73e7f-218">**類型**</span><span class="sxs-lookup"><span data-stu-id="73e7f-218">**Type**</span></span>
- <span data-ttu-id="73e7f-219">**24 小時**</span><span class="sxs-lookup"><span data-stu-id="73e7f-219">**24 hours**</span></span>
- <span data-ttu-id="73e7f-220">**3天**</span><span class="sxs-lookup"><span data-stu-id="73e7f-220">**3 days**</span></span>
- <span data-ttu-id="73e7f-221">**7 天**</span><span class="sxs-lookup"><span data-stu-id="73e7f-221">**7 days**</span></span>
- <span data-ttu-id="73e7f-222">**15 天**</span><span class="sxs-lookup"><span data-stu-id="73e7f-222">**15 days**</span></span>
- <span data-ttu-id="73e7f-223">**30天**</span><span class="sxs-lookup"><span data-stu-id="73e7f-223">**30 days**</span></span>

<span data-ttu-id="73e7f-224">如果您按一下 **[選擇類別] 以取得詳細資料**，您可以選取下列值：</span><span class="sxs-lookup"><span data-stu-id="73e7f-224">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="73e7f-225">**網路釣魚電子郵件**：這項選擇會帶您前往「 [威脅防護狀態」報告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-225">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="73e7f-226">**電子郵件中的惡意** 代碼：這項選擇會帶您前往 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-226">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="73e7f-227">**垃圾郵件** 偵測：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-227">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="73e7f-228">**Edge 封鎖的垃圾郵件**：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-228">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="73e7f-229">從類型視圖匯出</span><span class="sxs-lookup"><span data-stu-id="73e7f-229">Export from Type view</span></span>

<span data-ttu-id="73e7f-230">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="73e7f-230">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="73e7f-231">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="73e7f-231">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="73e7f-232">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="73e7f-232">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="73e7f-233">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="73e7f-233">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![郵件流程狀態報表中的類型視圖](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="73e7f-235">郵件流程狀態報表的方向視圖</span><span class="sxs-lookup"><span data-stu-id="73e7f-235">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="73e7f-236">如果您按一下 [ **方向** ] 索引標籤，則會使用 [ **類型** ] 視圖中的相同預設篩選器。</span><span class="sxs-lookup"><span data-stu-id="73e7f-236">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="73e7f-237">圖表是依 **方向** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="73e7f-237">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="73e7f-238">您可以按一下 [ **篩選**] 以變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-238">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="73e7f-239">會使用 [ **類型** ] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="73e7f-239">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="73e7f-240">詳細資料表格包含的資訊來自 **類型** view。</span><span class="sxs-lookup"><span data-stu-id="73e7f-240">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="73e7f-241">[ **選擇類別** ] 如需詳細資料，可用的選取專案和行為與「 **類型** 」視圖相同。</span><span class="sxs-lookup"><span data-stu-id="73e7f-241">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="73e7f-242">從方向視圖匯出</span><span class="sxs-lookup"><span data-stu-id="73e7f-242">Export from Direction view</span></span>

<span data-ttu-id="73e7f-243">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="73e7f-243">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="73e7f-244">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="73e7f-244">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="73e7f-245">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="73e7f-245">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="73e7f-246">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="73e7f-246">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![郵件流程狀態報表中的方向視圖](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="73e7f-248">郵件流程狀態報表的漏斗視圖</span><span class="sxs-lookup"><span data-stu-id="73e7f-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="73e7f-249">**漏斗** 視圖顯示 Microsoft 的電子郵件威脅防護功能如何篩選組織中的內送和外寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="73e7f-250">它提供有關電子郵件總數的詳細資訊，以及設定的威脅防護功能（包括 edge protection、反惡意程式碼、反網路釣魚、反垃圾郵件和反欺詐）對此計數的影響。</span><span class="sxs-lookup"><span data-stu-id="73e7f-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="73e7f-251">如果您按一下 [ **漏斗** ] 索引標籤，此 view 預設會包含 [圖表] 和 [詳細資料] 表格設定為下列篩選：</span><span class="sxs-lookup"><span data-stu-id="73e7f-251">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="73e7f-252">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="73e7f-252">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="73e7f-253">**方向**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-253">**Direction**:</span></span>
  - <span data-ttu-id="73e7f-254">**入境**</span><span class="sxs-lookup"><span data-stu-id="73e7f-254">**Inbound**</span></span>
  - <span data-ttu-id="73e7f-255">**出境**</span><span class="sxs-lookup"><span data-stu-id="73e7f-255">**Outbound**</span></span>
  - <span data-ttu-id="73e7f-256">**組織內**：此計數是針對在租使用者中傳送的郵件進行計數;亦即，寄件者 abc@domain.com 會傳送給收件者 xyz@domain.com (與輸入和外寄) 分開計數。</span><span class="sxs-lookup"><span data-stu-id="73e7f-256">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="73e7f-257">匯總視圖和詳細資料表格視圖允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-257">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="73e7f-258">您可以按一下 [ **篩選**] 以變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-258">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="73e7f-259">會使用 [ **類型** ] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="73e7f-259">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="73e7f-260">此圖顯示按下列方式組織的電子郵件計數：</span><span class="sxs-lookup"><span data-stu-id="73e7f-260">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="73e7f-261">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="73e7f-261">**Total email**</span></span>
- <span data-ttu-id="73e7f-262">**Edge protection 之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-262">**Email after edge protection**</span></span>
- <span data-ttu-id="73e7f-263">**傳輸規則** (郵件流程規則之後的電子郵件) </span><span class="sxs-lookup"><span data-stu-id="73e7f-263">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="73e7f-264">**反惡意程式碼、檔信譽、檔案類型封鎖後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-264">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="73e7f-265">**反網路釣魚、URL 信譽、品牌模擬、反欺騙功能之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-265">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="73e7f-266">**反垃圾郵件、大宗郵件篩選後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-266">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="73e7f-267">**使用者和網域模擬後的電子郵件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-267">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="73e7f-268">**檔案及 URL 引爆後的電子郵件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-268">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="73e7f-269">**在傳遞投遞後保護後，電子郵件偵測為良性 (URL 按一下時間保護)**</span><span class="sxs-lookup"><span data-stu-id="73e7f-269">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="73e7f-270"><sup>\*</sup>僅限 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-270"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="73e7f-271">若要個別查看以 EOP 或 Defender 為 Office 365 篩選的電子郵件，請按一下 [圖表圖例] 中的值。</span><span class="sxs-lookup"><span data-stu-id="73e7f-271">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="73e7f-272">[詳細資料] 表格包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="73e7f-272">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="73e7f-273">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-273">**Date**</span></span>
- <span data-ttu-id="73e7f-274">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="73e7f-274">**Total email**</span></span>
- <span data-ttu-id="73e7f-275">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="73e7f-275">**Edge protection**</span></span>
- <span data-ttu-id="73e7f-276">**反惡意程式碼、檔信譽、檔案類型封鎖**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-276">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="73e7f-277">**檔信譽**：由於其他 Microsoft 客戶附加的檔案識別，因此篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-277">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="73e7f-278">**檔案類型封鎖**：由於郵件中識別的惡意檔案類型，篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-278">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="73e7f-279">**反網路釣魚、URL 信譽、品牌模仿、反欺騙**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-279">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="73e7f-280">**URL 信譽**：由於其他 Microsoft 客戶的 url 身分識別而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-280">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="73e7f-281">**品牌** 模擬：因為郵件是由眾所周知的品牌類比寄件者所過濾，所以會加以篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-281">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="73e7f-282">**反欺騙**：因為郵件企圖哄騙收件者所屬的網域，或是郵件寄件者不會擁有的網域，所以篩選掉郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-282">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="73e7f-283">**反垃圾郵件，大宗郵件篩選**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-283">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="73e7f-284">**大宗郵件篩選**：在反垃圾郵件原則中依據大量抱怨層級 (BCL) 臨界值篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-284">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="73e7f-285">**Office 365) 的使用者和網域模擬 (Defender**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-285">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="73e7f-286">**使用者** 模擬：郵件因嘗試模擬使用者 (郵件寄件者) （已在反網路釣魚原則的類比保護設定中所定義）而篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-286">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="73e7f-287">**網域** 模擬：郵件因嘗試模擬防網路釣魚原則之類比保護設定中所定義的網域而篩選出來。</span><span class="sxs-lookup"><span data-stu-id="73e7f-287">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="73e7f-288">檔案 **及 URL 引爆 (Defender for Office 365)**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-288">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="73e7f-289">檔案 **引爆**：以 Safe 附件原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-289">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="73e7f-290">**URL 引爆**：透過 Safe 連結原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-290">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="73e7f-291">**投遞後保護和 zap (ATP) 或 zap (EOP)**：零小時自動清除 (針對惡意程式碼、垃圾郵件和網路釣魚的 ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-291">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="73e7f-292">如果您選取 [詳細資料] 表格中的列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="73e7f-292">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="73e7f-293">從漏斗視圖匯出</span><span class="sxs-lookup"><span data-stu-id="73e7f-293">Export from Funnel view</span></span>

<span data-ttu-id="73e7f-294">在 [**選項**] 下按一下 [**匯出**] 後，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="73e7f-294">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="73e7f-295">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="73e7f-295">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="73e7f-296">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="73e7f-296">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="73e7f-297">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-297">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="73e7f-298">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="73e7f-298">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="73e7f-299">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="73e7f-299">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="73e7f-300">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="73e7f-300">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![郵件流程狀態報表中的漏斗圖視圖](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="73e7f-302">郵件流程狀態報表的技術視圖</span><span class="sxs-lookup"><span data-stu-id="73e7f-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="73e7f-303">**技術視圖** 類似 **漏斗** 圖模式，可提供設定威脅防護功能的更細微細節。</span><span class="sxs-lookup"><span data-stu-id="73e7f-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="73e7f-304">您可以從圖表中查看郵件如何在威脅防護的不同階段進行分類。</span><span class="sxs-lookup"><span data-stu-id="73e7f-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="73e7f-305">如果您按一下 [ **技術視圖** ] 索引標籤，此視圖預設會包含 [圖表] 和 [詳細資料] 表格設定為下列篩選：</span><span class="sxs-lookup"><span data-stu-id="73e7f-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="73e7f-306">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="73e7f-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="73e7f-307">**方向**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-307">**Direction**:</span></span>
  - <span data-ttu-id="73e7f-308">**入境**</span><span class="sxs-lookup"><span data-stu-id="73e7f-308">**Inbound**</span></span>
  - <span data-ttu-id="73e7f-309">**出境**</span><span class="sxs-lookup"><span data-stu-id="73e7f-309">**Outbound**</span></span>
  - <span data-ttu-id="73e7f-310">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="73e7f-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="73e7f-311">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與輸入和輸出) 分開計數</span><span class="sxs-lookup"><span data-stu-id="73e7f-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="73e7f-312">匯總視圖和詳細資料表格視圖允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="73e7f-313">您可以按一下 [ **篩選**] 以變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="73e7f-314">會使用 [ **類型** ] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="73e7f-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="73e7f-315">此圖顯示組織成下列類別的郵件：</span><span class="sxs-lookup"><span data-stu-id="73e7f-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="73e7f-316">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="73e7f-316">**Total email**</span></span>
- <span data-ttu-id="73e7f-317">**Edge 允許** 和 **edge 篩選**</span><span class="sxs-lookup"><span data-stu-id="73e7f-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="73e7f-318">已篩選的 **傳輸規則允許** 和 **傳輸規則** (郵件流程規則) </span><span class="sxs-lookup"><span data-stu-id="73e7f-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="73e7f-319">**非惡意** 代碼、 **Safe 附件偵測** <sup>\*</sup> 和 **反惡意程式碼引擎偵測**</span><span class="sxs-lookup"><span data-stu-id="73e7f-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="73e7f-320">**不是網路釣魚詐騙**、 **DMARC 失敗**、**模仿偵測** <sup>\*</sup> 、**欺騙偵測** 和 **網路釣魚偵測**</span><span class="sxs-lookup"><span data-stu-id="73e7f-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="73e7f-321">**沒有偵測 URL 引爆** 及 **url 引爆偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="73e7f-322">**非垃圾郵件** 和  **垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="73e7f-323">**非惡意的電子郵件**、 **Safe 連結偵測** <sup>\*</sup> 和 **ZAP**</span><span class="sxs-lookup"><span data-stu-id="73e7f-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="73e7f-324"><sup>\*</sup>Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="73e7f-325">當您將游標移到圖表中的某個類別時，您可以看到該類別中的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="73e7f-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="73e7f-326">[詳細資料] 表格包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="73e7f-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="73e7f-327">**日期 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="73e7f-327">**Date (UTC)**</span></span>
- <span data-ttu-id="73e7f-328">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="73e7f-328">**Total email**</span></span>
- <span data-ttu-id="73e7f-329">**已篩選 Edge**</span><span class="sxs-lookup"><span data-stu-id="73e7f-329">**Edge filtered**</span></span>
- <span data-ttu-id="73e7f-330">**規則郵件**：由於郵件流程規則而篩選的郵件 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="73e7f-331">**反惡意程式碼引擎**， **Safe 附件** <sup>\*</sup> ：</span><span class="sxs-lookup"><span data-stu-id="73e7f-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="73e7f-332">**DMARC，類比** <sup>\*</sup> ，**欺騙**，**網路釣魚篩選**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="73e7f-333">**DMARC**：由於郵件失敗的 DMARC 驗證檢查而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="73e7f-334">**URL 引爆偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="73e7f-335">**已篩選的反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="73e7f-336">**移除的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="73e7f-336">**ZAP removed**</span></span>
- <span data-ttu-id="73e7f-337">**Safe 連結偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="73e7f-338"><sup>\*</sup>Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="73e7f-339">如果您選取 [詳細資料] 表格中的列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="73e7f-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="73e7f-340">從技術視圖匯出</span><span class="sxs-lookup"><span data-stu-id="73e7f-340">Export from Tech view</span></span>

<span data-ttu-id="73e7f-341">在按一下 [ **匯出**] 的 [ **選項** ] 底下，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="73e7f-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="73e7f-342">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="73e7f-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="73e7f-343">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="73e7f-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="73e7f-344">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="73e7f-345">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="73e7f-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="73e7f-346">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="73e7f-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="73e7f-347">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="73e7f-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![郵件流程狀態報表中的技術視圖](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="73e7f-349">惡意程式碼檢測報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-349">Malware detections report</span></span>

<span data-ttu-id="73e7f-350">**惡意軟體偵測報告** 會顯示 Exchange Online Protection 或 EOP) 所偵測到的內送和外寄電子郵件， (惡意軟體偵測的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="73e7f-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="73e7f-351">如需 EOP 中惡意程式碼保護的詳細資訊，請參閱 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="73e7f-352">匯總 view 篩選允許90天，而 [詳細資料表格篩選] 只允許10天。</span><span class="sxs-lookup"><span data-stu-id="73e7f-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="73e7f-353">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-354">在 [**電子郵件 &** 共同作業報告] 頁面上，尋找 [**在電子郵件中偵測到惡意** 代碼]，然後按一下 [ **View**</span><span class="sxs-lookup"><span data-stu-id="73e7f-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="73e7f-355">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![電子郵件 & 協同報告] 頁面上電子郵件小工具中的惡意程式碼偵測](../../media/malware-detections-widget.png)

<span data-ttu-id="73e7f-357">在 [ **惡意** 代碼偵測報告] 頁面上，您可以按一下 [ **篩選** ] 並選取下列其中一個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="73e7f-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="73e7f-358">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-359">**方向**： **輸入** 和 **輸出**</span><span class="sxs-lookup"><span data-stu-id="73e7f-359">**Direction**: **Inbound** and **Outbound**</span></span>

![電子郵件中的惡意程式碼偵測報表檢視](../../media/malware-detections-report-view.png)

<span data-ttu-id="73e7f-361">在圖形下方的 [詳細資料] 表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="73e7f-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="73e7f-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-362">**Date**</span></span>
- <span data-ttu-id="73e7f-363">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="73e7f-363">**Sender address**</span></span>
- <span data-ttu-id="73e7f-364">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="73e7f-364">**Recipient address**</span></span>
- <span data-ttu-id="73e7f-365">**郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。</span><span class="sxs-lookup"><span data-stu-id="73e7f-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="73e7f-366">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="73e7f-367">**主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-367">**Subject**</span></span>
- <span data-ttu-id="73e7f-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="73e7f-368">**Filename**</span></span>
- <span data-ttu-id="73e7f-369">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="73e7f-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="73e7f-370">郵件延遲報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-370">Mail latency report</span></span>

<span data-ttu-id="73e7f-371">Office 365 的「中的 **郵件延遲報告**] 包含組織內的郵件傳遞和引爆延遲的資訊。</span><span class="sxs-lookup"><span data-stu-id="73e7f-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="73e7f-372">如需詳細資訊，請參閱 [郵件延遲報告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="73e7f-373">垃圾郵件偵測報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="73e7f-374">**垃圾郵件偵測報告** 會最後移出。</span><span class="sxs-lookup"><span data-stu-id="73e7f-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="73e7f-375">「 [威脅防護狀態」報告](#threat-protection-status-report)中提供相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="73e7f-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="73e7f-376">欺騙偵測報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="73e7f-377">本文中所述的 [已改進的欺騙偵測報告] 是預覽中所述，視情況而變更，並非所有組織都提供這些報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="73e7f-378">較舊的報表版本只會顯示 **良好的郵件** ，而且會被 **視為垃圾** 郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="73e7f-379">**欺騙** 偵測報告會顯示因欺騙性而封鎖或允許的郵件相關資訊。</span><span class="sxs-lookup"><span data-stu-id="73e7f-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="73e7f-380">如需有關電子欺騙的詳細資訊，請參閱 [EOP 中的反欺騙防護](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="73e7f-381">報表的匯總視圖允許45天的篩選 <sup>\*</sup> ，而詳細資料檢視只允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="73e7f-382"><sup>\*</sup> 最後，您將可以使用超過90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="73e7f-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="73e7f-383">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-384">在 [ **電子郵件 &** 共同作業報告] 頁面上，找出 **欺騙** 偵測，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="73e7f-385">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![電子郵件 & 協同報告] 頁面上的欺騙偵測小工具](../../media/spoof-detections-widget.png)

<span data-ttu-id="73e7f-387">此圖表顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-387">The chart shows the following information:</span></span>

- <span data-ttu-id="73e7f-388">**通過**</span><span class="sxs-lookup"><span data-stu-id="73e7f-388">**Pass**</span></span>
- <span data-ttu-id="73e7f-389">**失敗**</span><span class="sxs-lookup"><span data-stu-id="73e7f-389">**Fail**</span></span>
- <span data-ttu-id="73e7f-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="73e7f-390">**SoftPass**</span></span>
- <span data-ttu-id="73e7f-391">**無**</span><span class="sxs-lookup"><span data-stu-id="73e7f-391">**None**</span></span>
- <span data-ttu-id="73e7f-392">**其他**</span><span class="sxs-lookup"><span data-stu-id="73e7f-392">**Other**</span></span>

<span data-ttu-id="73e7f-393">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您可以看到偵測到的冒牌郵件數目及原因。</span><span class="sxs-lookup"><span data-stu-id="73e7f-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="73e7f-394">在 [ **偽造郵件報告** ] 頁面上，您可以按一下 [ **篩選** ]，然後選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="73e7f-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="73e7f-395">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-396">**結果**：</span><span class="sxs-lookup"><span data-stu-id="73e7f-396">**Result**:</span></span>
  - <span data-ttu-id="73e7f-397">**通過**</span><span class="sxs-lookup"><span data-stu-id="73e7f-397">**Pass**</span></span>
  - <span data-ttu-id="73e7f-398">**失敗**</span><span class="sxs-lookup"><span data-stu-id="73e7f-398">**Fail**</span></span>
  - <span data-ttu-id="73e7f-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="73e7f-399">**SoftPass**</span></span>
  - <span data-ttu-id="73e7f-400">**無**</span><span class="sxs-lookup"><span data-stu-id="73e7f-400">**None**</span></span>
  - <span data-ttu-id="73e7f-401">**其他**</span><span class="sxs-lookup"><span data-stu-id="73e7f-401">**Other**</span></span>
- <span data-ttu-id="73e7f-402">**哄騙類型**： **Internal** 和 **External**</span><span class="sxs-lookup"><span data-stu-id="73e7f-402">**Spoof type**: **Internal** and **External**</span></span>

![Microsoft 365 Defender 入口網站中的 [偽造郵件報告] 頁面](../../media/spoof-detections-report-page.png)

<span data-ttu-id="73e7f-404">在圖形下方的 [詳細資料] 表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="73e7f-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="73e7f-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-405">**Date**</span></span>
- <span data-ttu-id="73e7f-406">**偽裝的使用者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-406">**Spoofed user**</span></span>
- <span data-ttu-id="73e7f-407">**傳送基礎結構**</span><span class="sxs-lookup"><span data-stu-id="73e7f-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="73e7f-408">**哄騙類型**</span><span class="sxs-lookup"><span data-stu-id="73e7f-408">**Spoof type**</span></span>
- <span data-ttu-id="73e7f-409">**結果**</span><span class="sxs-lookup"><span data-stu-id="73e7f-409">**Result**</span></span>
- <span data-ttu-id="73e7f-410">**結果代碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-410">**Result code**</span></span>
- <span data-ttu-id="73e7f-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="73e7f-411">**SPF**</span></span>
- <span data-ttu-id="73e7f-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="73e7f-412">**DKIM**</span></span>
- <span data-ttu-id="73e7f-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="73e7f-413">**DMARC**</span></span>
- <span data-ttu-id="73e7f-414">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="73e7f-414">**Message count**</span></span>

<span data-ttu-id="73e7f-415">如需複合驗證結果代碼的詳細資訊，請參閱[反垃圾郵件郵件頭 in Microsoft 365](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="73e7f-416">提交報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-416">Submissions report</span></span>

<span data-ttu-id="73e7f-417">**提交** 報告會顯示系統管理員針對分析報告之專案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="73e7f-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="73e7f-418">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="73e7f-419">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-420">在 [ **電子郵件 &** 共同作業報告] 頁面上，找到 [ **提交** ]，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="73e7f-421">若要直接前往報表，請開啟 <https://security.microsoft.com/adminSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="73e7f-422">若要移至 [Microsoft 365 Defender 入口網站中的系統管理提交](admin-submission.md)，按一下 [**移至提交**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![電子郵件 & 協同報告] 頁面上的提交小工具](../../media/submissions-report-widget.png)

<span data-ttu-id="73e7f-424">此圖表顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-424">The chart shows the following information:</span></span>

- <span data-ttu-id="73e7f-425">**等待**</span><span class="sxs-lookup"><span data-stu-id="73e7f-425">**Pending**</span></span>
- <span data-ttu-id="73e7f-426">**已完成**</span><span class="sxs-lookup"><span data-stu-id="73e7f-426">**Completed**</span></span>

<span data-ttu-id="73e7f-427">在 [ **提交** ] 頁面上，您可以按一下 [ **篩選** ]，然後選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="73e7f-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="73e7f-428">**報告日期**： **開始時間** 和 **結束時間**</span><span class="sxs-lookup"><span data-stu-id="73e7f-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="73e7f-429">**提交類型**： **電子郵件**、 **URL** 或 **檔案**</span><span class="sxs-lookup"><span data-stu-id="73e7f-429">**Submission type**: **Email**, **URL**, or **File**</span></span>
- <span data-ttu-id="73e7f-430">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-430">**Submission ID**</span></span>
- <span data-ttu-id="73e7f-431">**網路消息識別碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-431">**Network Message ID**</span></span>
- <span data-ttu-id="73e7f-432">**Sender**</span><span class="sxs-lookup"><span data-stu-id="73e7f-432">**Sender**</span></span>
- <span data-ttu-id="73e7f-433">**名稱**</span><span class="sxs-lookup"><span data-stu-id="73e7f-433">**Name**</span></span>
- <span data-ttu-id="73e7f-434">**提交者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-434">**Submitted by**</span></span>
- <span data-ttu-id="73e7f-435">**提交原因**： **非垃圾郵件**、 **網路釣魚詐騙**、 **惡意** 代碼或 **垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-435">**Reason for submitting**: **Not junk**, **Phish**, **Malware**, or **Spam**</span></span>
- <span data-ttu-id="73e7f-436">**重新掃描狀態**： **擱置** 或 **已完成**</span><span class="sxs-lookup"><span data-stu-id="73e7f-436">**Rescan status**: **Pending** or **Completed**</span></span>

<span data-ttu-id="73e7f-437">圖表下方的 [詳細資料] 表格會顯示相同的資訊，並具有相同的 **群組** 或 **自訂欄** 選項，與在 **電子郵件 &** 共同作業報送中 **提交的 [分析**] 索引標籤 \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73e7f-437">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="73e7f-438">如需詳細資訊，請參閱 [View admin 報送 To Microsoft](admin-submission.md#view-admin-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-438">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Microsoft 365 Defender 入口網站中的「提交報告」頁面](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="73e7f-440">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-440">Threat protection status report</span></span>

<span data-ttu-id="73e7f-441">「**威脅防護狀態**」報告適用于 EOP 和 Defender Office 365;不過，報告包含不同的資料。</span><span class="sxs-lookup"><span data-stu-id="73e7f-441">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="73e7f-442">例如，EOP 客戶可以查看在電子郵件中偵測到惡意程式碼的相關資訊，但不會[Safe SharePoint、OneDrive 及 Microsoft Teams 的附件](mdo-for-spo-odb-and-teams.md)所偵測到之惡意檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="73e7f-442">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="73e7f-443">該報告提供包含惡意內容的電子郵件統計，例如檔案或網站位址 (URLs 反惡意程式碼引擎封鎖的) 、[零小時的自動清除 (ZAP) ](zero-hour-auto-purge.md)，以及[在反網路釣魚原則中](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)Office 365[連結](safe-links.md)、 [Safe 附件](safe-attachments.md)和模擬保護功能等 Safe 功能。</span><span class="sxs-lookup"><span data-stu-id="73e7f-443">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="73e7f-444">您可以使用此資訊來識別趨勢，或判斷組織原則是否需要調整。</span><span class="sxs-lookup"><span data-stu-id="73e7f-444">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="73e7f-445">**附注：請** 務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-445">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="73e7f-446">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-446">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-447">在 [ **電子郵件 & 協同報告** ] 頁面上，找出 **威脅防護狀態** ，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-447">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="73e7f-448">若要直接前往報告，請開啟下列其中一個 URLs：</span><span class="sxs-lookup"><span data-stu-id="73e7f-448">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="73e7f-449">Office 365 的 Defender：<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="73e7f-449">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="73e7f-450">EOP <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="73e7f-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![「電子郵件 & 協同報告」頁面上的威脅防護狀態構件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="73e7f-452">根據預設，圖表會顯示過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="73e7f-452">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="73e7f-453">如果您按一下 [**威脅防護狀態報表**] 頁面上的 [**篩選**]，您可以選取90天的日期範圍 (試用訂閱可能限制為30天) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-453">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="73e7f-454">[詳細資料] 表格允許篩選30天。</span><span class="sxs-lookup"><span data-stu-id="73e7f-454">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="73e7f-455">下列各節將說明可用的視圖。</span><span class="sxs-lookup"><span data-stu-id="73e7f-455">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="73e7f-456">依概覽查看資料</span><span class="sxs-lookup"><span data-stu-id="73e7f-456">View data by Overview</span></span>

![威脅防護狀態報表中的一覽視圖](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="73e7f-458">在 [ **依一覽查看資料** ] 視圖中，下列偵測資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="73e7f-458">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="73e7f-459">**電子郵件惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-459">**Email malware**</span></span>
- <span data-ttu-id="73e7f-460">**電子郵件網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="73e7f-460">**Email phish**</span></span>
- <span data-ttu-id="73e7f-461">**內容惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-461">**Content malware**</span></span>

<span data-ttu-id="73e7f-462">圖表下沒有詳細資料表格可用。</span><span class="sxs-lookup"><span data-stu-id="73e7f-462">No details table is available below the chart.</span></span>

<span data-ttu-id="73e7f-463">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="73e7f-463">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="73e7f-464">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-464">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-465">**偵測**：**電子郵件惡意** 代碼、**電子郵件網路釣魚** 或 **內容惡意** 代碼</span><span class="sxs-lookup"><span data-stu-id="73e7f-465">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="73e7f-466">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-466">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="73e7f-467">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-467">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="73e7f-468">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-468">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="73e7f-469">**方向**</span><span class="sxs-lookup"><span data-stu-id="73e7f-469">**Direction**</span></span>
- <span data-ttu-id="73e7f-470">**網域**</span><span class="sxs-lookup"><span data-stu-id="73e7f-470">**Domain**</span></span>
- <span data-ttu-id="73e7f-471">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="73e7f-471">**Policy type**</span></span>

<span data-ttu-id="73e7f-472">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-472">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="73e7f-473">透過偵測技術透過電子郵件 \> 網路釣魚和圖表細目來查看資料</span><span class="sxs-lookup"><span data-stu-id="73e7f-473">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![威脅防護狀態報表中網路釣魚電子郵件的偵測技術視圖](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="73e7f-475">在 [透過 **電子郵件 \> 網路釣魚詐騙** ] 和 [ **依偵測方式顯示圖表明細] 技術** 視圖中，下列資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="73e7f-475">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="73e7f-476">**URL 惡意信譽** <sup>\*</sup> ：從其他 Microsoft 365 客戶的 Office 365 detonations 中的 Defender 產生惡意 URL 信譽。</span><span class="sxs-lookup"><span data-stu-id="73e7f-476">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="73e7f-477">**Advanced filter**：以機器學習為基礎的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="73e7f-477">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="73e7f-478">**一般篩選**：根據分析規則的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="73e7f-478">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="73e7f-479">**組織內的欺騙**：寄件者嘗試欺騙收件者網域。</span><span class="sxs-lookup"><span data-stu-id="73e7f-479">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="73e7f-480">**欺騙外部網域**：寄件者正嘗試哄騙其他一些網域。</span><span class="sxs-lookup"><span data-stu-id="73e7f-480">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="73e7f-481">**哄騙 DMARC**：郵件上的 DMARC 驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="73e7f-481">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="73e7f-482">模擬 **商標**：模擬以寄件者為基礎的知名品牌。</span><span class="sxs-lookup"><span data-stu-id="73e7f-482">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="73e7f-483">**混合式分析偵測**</span><span class="sxs-lookup"><span data-stu-id="73e7f-483">**Mixed analysis detection**</span></span>
- <span data-ttu-id="73e7f-484">**檔信譽**</span><span class="sxs-lookup"><span data-stu-id="73e7f-484">**File reputation**</span></span>
- <span data-ttu-id="73e7f-485">**指紋比對**</span><span class="sxs-lookup"><span data-stu-id="73e7f-485">**Fingerprint matching**</span></span>
- <span data-ttu-id="73e7f-486">**URL 引爆信譽**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-486">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="73e7f-487">**URL 引爆**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-487">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="73e7f-488">**類比使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-488">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="73e7f-489">**類比網域** <sup>\*</sup> ：模仿客戶擁有或定義的網域。</span><span class="sxs-lookup"><span data-stu-id="73e7f-489">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="73e7f-490">**信箱智慧** 模擬 <sup>\*</sup> ：由系統管理員定義或透過信箱智慧學出的使用者類比。</span><span class="sxs-lookup"><span data-stu-id="73e7f-490">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="73e7f-491">**檔引爆**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-491">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="73e7f-492">**運動**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-492">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="73e7f-493">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-493">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="73e7f-494">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-494">**Date**</span></span>
- <span data-ttu-id="73e7f-495">**主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-495">**Subject**</span></span>
- <span data-ttu-id="73e7f-496">**Sender**</span><span class="sxs-lookup"><span data-stu-id="73e7f-496">**Sender**</span></span>
- <span data-ttu-id="73e7f-497">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-497">**Recipients**</span></span>
- <span data-ttu-id="73e7f-498">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="73e7f-498">**Detected by**</span></span>
- <span data-ttu-id="73e7f-499">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="73e7f-499">**Delivery Status**</span></span>
- <span data-ttu-id="73e7f-500">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="73e7f-500">**Source of Compromise**</span></span>
- <span data-ttu-id="73e7f-501">**標記**</span><span class="sxs-lookup"><span data-stu-id="73e7f-501">**Tags**</span></span>

<span data-ttu-id="73e7f-502">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="73e7f-502">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="73e7f-503">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-503">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-504">**偵測**</span><span class="sxs-lookup"><span data-stu-id="73e7f-504">**Detection**</span></span>
- <span data-ttu-id="73e7f-505">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-505">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="73e7f-506">**方向**</span><span class="sxs-lookup"><span data-stu-id="73e7f-506">**Direction**</span></span>
- <span data-ttu-id="73e7f-507">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-507">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="73e7f-508">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-508">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="73e7f-509">**網域**</span><span class="sxs-lookup"><span data-stu-id="73e7f-509">**Domain**</span></span>
- <span data-ttu-id="73e7f-510">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="73e7f-510">**Policy type**</span></span>
- <span data-ttu-id="73e7f-511">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="73e7f-511">**Policy name** (details table only)</span></span>
- <span data-ttu-id="73e7f-512">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-512">**Recipients**</span></span>

<span data-ttu-id="73e7f-513">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-513">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="73e7f-514">透過電子郵件 \> 惡意程式碼和偵測技術的圖表細目來查看資料</span><span class="sxs-lookup"><span data-stu-id="73e7f-514">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![威脅防護狀態報表中惡意程式碼的偵測技術視圖](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="73e7f-516">在 [透過 **電子郵件 \> 惡意** 代碼和 **依偵測方式顯示圖表的** 資料] 技術視圖中，下列資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="73e7f-516">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="73e7f-517">檔案 **引爆** <sup>\*</sup> ： Safe 附件的偵測。</span><span class="sxs-lookup"><span data-stu-id="73e7f-517">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="73e7f-518">檔案 **引爆信譽** <sup>\*</sup> ：所有由 Defender 為 Office 365 detonations 所產生的惡意檔信譽。</span><span class="sxs-lookup"><span data-stu-id="73e7f-518">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="73e7f-519">**檔信譽**</span><span class="sxs-lookup"><span data-stu-id="73e7f-519">**File reputation**</span></span>
- <span data-ttu-id="73e7f-520">**反惡意程式碼引擎** <sup>\*</sup> ：從反惡意程式碼引擎偵測。</span><span class="sxs-lookup"><span data-stu-id="73e7f-520">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="73e7f-521">**反惡意程式碼原則檔案類型封鎖**：由於郵件中所識別的惡意檔案類型，郵件會篩選掉這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="73e7f-521">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="73e7f-522">**URL 惡意信譽**</span><span class="sxs-lookup"><span data-stu-id="73e7f-522">**URL malicious reputation**</span></span>
- <span data-ttu-id="73e7f-523">**URL 引爆**</span><span class="sxs-lookup"><span data-stu-id="73e7f-523">**URL detonation**</span></span>
- <span data-ttu-id="73e7f-524">**URL 引爆信譽**</span><span class="sxs-lookup"><span data-stu-id="73e7f-524">**URL detonation reputation**</span></span>
- <span data-ttu-id="73e7f-525">**行銷活動**</span><span class="sxs-lookup"><span data-stu-id="73e7f-525">**Campaign**</span></span>

<span data-ttu-id="73e7f-526">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-526">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="73e7f-527">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-527">**Date**</span></span>
- <span data-ttu-id="73e7f-528">**主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-528">**Subject**</span></span>
- <span data-ttu-id="73e7f-529">**Sender**</span><span class="sxs-lookup"><span data-stu-id="73e7f-529">**Sender**</span></span>
- <span data-ttu-id="73e7f-530">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-530">**Recipients**</span></span>
- <span data-ttu-id="73e7f-531">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="73e7f-531">**Detected by**</span></span>
- <span data-ttu-id="73e7f-532">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="73e7f-532">**Delivery Status**</span></span>
- <span data-ttu-id="73e7f-533">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="73e7f-533">**Source of Compromise**</span></span>
- <span data-ttu-id="73e7f-534">**標記**</span><span class="sxs-lookup"><span data-stu-id="73e7f-534">**Tags**</span></span>

<span data-ttu-id="73e7f-535">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="73e7f-535">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="73e7f-536">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-536">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-537">**偵測**</span><span class="sxs-lookup"><span data-stu-id="73e7f-537">**Detection**</span></span>
- <span data-ttu-id="73e7f-538">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-538">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="73e7f-539">**方向**</span><span class="sxs-lookup"><span data-stu-id="73e7f-539">**Direction**</span></span>
- <span data-ttu-id="73e7f-540">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-540">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="73e7f-541">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-541">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="73e7f-542">**網域**</span><span class="sxs-lookup"><span data-stu-id="73e7f-542">**Domain**</span></span>
- <span data-ttu-id="73e7f-543">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="73e7f-543">**Policy type**</span></span>
- <span data-ttu-id="73e7f-544">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="73e7f-544">**Policy name** (details table only)</span></span>
- <span data-ttu-id="73e7f-545">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-545">**Recipients**</span></span>

<span data-ttu-id="73e7f-546">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-546">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="73e7f-547">依電子郵件 \> 網路釣魚或透過電子郵件惡意程式碼查看資料的方式，依原則類型分類的圖表 \></span><span class="sxs-lookup"><span data-stu-id="73e7f-547">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威脅防護狀態報表中的網路釣魚電子郵件或惡意程式碼電子郵件的原則類型查看](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="73e7f-549">在 [ **依原則類型的圖表分解** ] 和 [透過電子郵件惡意程式碼 **查看資料 \>** ] 或 [透過 **電子郵件 \> 惡意程式碼查看資料** ] 視圖中，圖表會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-549">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="73e7f-550">**反惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-550">**Anti-malware**</span></span>
- <span data-ttu-id="73e7f-551">**Safe附件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="73e7f-551">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="73e7f-552">**反網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="73e7f-552">**Anti-phish**</span></span>
- <span data-ttu-id="73e7f-553">**反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-553">**Anti-spam**</span></span>
- <span data-ttu-id="73e7f-554">**郵件流程規則** (也稱為傳輸規則) </span><span class="sxs-lookup"><span data-stu-id="73e7f-554">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="73e7f-555">**別人**</span><span class="sxs-lookup"><span data-stu-id="73e7f-555">**Others**</span></span>

<span data-ttu-id="73e7f-556">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-556">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="73e7f-557">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-557">**Date**</span></span>
- <span data-ttu-id="73e7f-558">**主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-558">**Subject**</span></span>
- <span data-ttu-id="73e7f-559">**Sender**</span><span class="sxs-lookup"><span data-stu-id="73e7f-559">**Sender**</span></span>
- <span data-ttu-id="73e7f-560">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-560">**Recipients**</span></span>
- <span data-ttu-id="73e7f-561">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="73e7f-561">**Detected by**</span></span>
- <span data-ttu-id="73e7f-562">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="73e7f-562">**Delivery Status**</span></span>
- <span data-ttu-id="73e7f-563">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="73e7f-563">**Source of Compromise**</span></span>
- <span data-ttu-id="73e7f-564">**標記**</span><span class="sxs-lookup"><span data-stu-id="73e7f-564">**Tags**</span></span>

<span data-ttu-id="73e7f-565">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="73e7f-565">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="73e7f-566">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-566">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-567">**偵測**</span><span class="sxs-lookup"><span data-stu-id="73e7f-567">**Detection**</span></span>
- <span data-ttu-id="73e7f-568">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-568">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="73e7f-569">**方向**</span><span class="sxs-lookup"><span data-stu-id="73e7f-569">**Direction**</span></span>
- <span data-ttu-id="73e7f-570">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-570">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="73e7f-571">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-571">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="73e7f-572">**網域**</span><span class="sxs-lookup"><span data-stu-id="73e7f-572">**Domain**</span></span>
- <span data-ttu-id="73e7f-573">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="73e7f-573">**Policy type**</span></span>
- <span data-ttu-id="73e7f-574">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="73e7f-574">**Policy name** (details table only)</span></span>
- <span data-ttu-id="73e7f-575">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-575">**Recipients**</span></span>

<span data-ttu-id="73e7f-576">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-576">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="73e7f-577">透過電子郵件 \> 網路釣魚或透過電子郵件惡意程式碼查看資料，依傳遞狀態與查看資料的圖表細目 \></span><span class="sxs-lookup"><span data-stu-id="73e7f-577">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威脅防護狀態報表中的網路釣魚電子郵件和惡意程式碼電子郵件的傳遞狀態視圖](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="73e7f-579">在 **圖表** 中透過 **電子郵件 \> 網路釣魚** 或透過電子郵件 **\> 惡意** 代碼查看資料來查看資料，圖表會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-579">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="73e7f-580">**主控信箱：收件匣**</span><span class="sxs-lookup"><span data-stu-id="73e7f-580">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="73e7f-581">**主控信箱：垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-581">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="73e7f-582">**主控信箱：自訂資料夾**</span><span class="sxs-lookup"><span data-stu-id="73e7f-582">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="73e7f-583">**主控信箱：刪除的郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-583">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="73e7f-584">**轉發**</span><span class="sxs-lookup"><span data-stu-id="73e7f-584">**Forwarded**</span></span>
- <span data-ttu-id="73e7f-585">**內部部署伺服器：已傳送**</span><span class="sxs-lookup"><span data-stu-id="73e7f-585">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="73e7f-586">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="73e7f-586">**Quarantine**</span></span>
- <span data-ttu-id="73e7f-587">**傳遞失敗**</span><span class="sxs-lookup"><span data-stu-id="73e7f-587">**Delivery failed**</span></span>
- <span data-ttu-id="73e7f-588">**下降**</span><span class="sxs-lookup"><span data-stu-id="73e7f-588">**Dropped**</span></span>

<span data-ttu-id="73e7f-589">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-589">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="73e7f-590">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-590">**Date**</span></span>
- <span data-ttu-id="73e7f-591">**主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-591">**Subject**</span></span>
- <span data-ttu-id="73e7f-592">**Sender**</span><span class="sxs-lookup"><span data-stu-id="73e7f-592">**Sender**</span></span>
- <span data-ttu-id="73e7f-593">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-593">**Recipients**</span></span>
- <span data-ttu-id="73e7f-594">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="73e7f-594">**Detected by**</span></span>
- <span data-ttu-id="73e7f-595">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="73e7f-595">**Delivery Status**</span></span>
- <span data-ttu-id="73e7f-596">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="73e7f-596">**Source of Compromise**</span></span>
- <span data-ttu-id="73e7f-597">**標記**</span><span class="sxs-lookup"><span data-stu-id="73e7f-597">**Tags**</span></span>

<span data-ttu-id="73e7f-598">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="73e7f-598">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="73e7f-599">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-599">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-600">**偵測**</span><span class="sxs-lookup"><span data-stu-id="73e7f-600">**Detection**</span></span>
- <span data-ttu-id="73e7f-601">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-601">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="73e7f-602">**方向**</span><span class="sxs-lookup"><span data-stu-id="73e7f-602">**Direction**</span></span>
- <span data-ttu-id="73e7f-603">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-603">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="73e7f-604">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-604">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="73e7f-605">**網域**</span><span class="sxs-lookup"><span data-stu-id="73e7f-605">**Domain**</span></span>
- <span data-ttu-id="73e7f-606">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="73e7f-606">**Policy type**</span></span>
- <span data-ttu-id="73e7f-607">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="73e7f-607">**Policy name** (details table only)</span></span>
- <span data-ttu-id="73e7f-608">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-608">**Recipients**</span></span>

<span data-ttu-id="73e7f-609">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-609">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="73e7f-610">依惡意程式碼查看資料 \></span><span class="sxs-lookup"><span data-stu-id="73e7f-610">View data by Content \> Malware</span></span>

![威脅防護狀態報表中的內容惡意程式碼視圖](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="73e7f-612">在 [**依內容 \> 惡意** 代碼查看資料] 視圖中，下列資訊會顯示在適用于 Office 365 組織的 Microsoft Defender 圖表中：</span><span class="sxs-lookup"><span data-stu-id="73e7f-612">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="73e7f-613">**反惡意程式碼引擎**： [Microsoft 365 中內建的病毒偵測](virus-detection-in-spo.md)，在 Sharepoint、OneDrive 及 Microsoft Teams 中偵測到惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="73e7f-613">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="73e7f-614">檔案 **引爆**： [Safe SharePoint、OneDrive 及 Microsoft Teams 的附件](mdo-for-spo-odb-and-teams.md)所偵測到的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="73e7f-614">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="73e7f-615">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-615">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="73e7f-616">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-616">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-617">**位置**</span><span class="sxs-lookup"><span data-stu-id="73e7f-617">**Location**</span></span>
- <span data-ttu-id="73e7f-618">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="73e7f-618">**Detected by**</span></span>
- <span data-ttu-id="73e7f-619">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="73e7f-619">**Malware name**</span></span>

<span data-ttu-id="73e7f-620">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="73e7f-620">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="73e7f-621">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-621">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-622">**偵測**： **反惡意程式碼引擎** 或 **檔引爆**</span><span class="sxs-lookup"><span data-stu-id="73e7f-622">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="73e7f-623">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-623">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="73e7f-624">依系統覆寫查看資料</span><span class="sxs-lookup"><span data-stu-id="73e7f-624">View data by System override</span></span>

![威脅防護狀態報表中的郵件覆寫視圖](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="73e7f-626">在 [ **依系統覆寫查看資料** ] 視圖中，下列的覆寫原因資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="73e7f-626">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="73e7f-627">**內部部署略過**</span><span class="sxs-lookup"><span data-stu-id="73e7f-627">**On-premises skip**</span></span>
- <span data-ttu-id="73e7f-628">**IP 允許**</span><span class="sxs-lookup"><span data-stu-id="73e7f-628">**IP allow**</span></span>
- <span data-ttu-id="73e7f-629">**Exchange 郵件傳輸規則** (郵件流程規則) </span><span class="sxs-lookup"><span data-stu-id="73e7f-629">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="73e7f-630">**組織允許的寄件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-630">**Organization allowed senders**</span></span>
- <span data-ttu-id="73e7f-631">**組織允許的網域**</span><span class="sxs-lookup"><span data-stu-id="73e7f-631">**Organization allowed domains**</span></span>
- <span data-ttu-id="73e7f-632">**未啟用的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="73e7f-632">**ZAP not enabled**</span></span>
- <span data-ttu-id="73e7f-633">**未啟用垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="73e7f-633">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="73e7f-634">**使用者 Safe 寄件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-634">**User Safe Sender**</span></span>
- <span data-ttu-id="73e7f-635">**使用者 Safe 網域**</span><span class="sxs-lookup"><span data-stu-id="73e7f-635">**User Safe Domain**</span></span>

<span data-ttu-id="73e7f-636">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-636">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="73e7f-637">**Date**</span><span class="sxs-lookup"><span data-stu-id="73e7f-637">**Date**</span></span>
- <span data-ttu-id="73e7f-638">**主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-638">**Subject**</span></span>
- <span data-ttu-id="73e7f-639">**Sender**</span><span class="sxs-lookup"><span data-stu-id="73e7f-639">**Sender**</span></span>
- <span data-ttu-id="73e7f-640">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-640">**Recipients**</span></span>
- <span data-ttu-id="73e7f-641">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="73e7f-641">**Detected by**</span></span>
- <span data-ttu-id="73e7f-642">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="73e7f-642">**Delivery Status**</span></span>
- <span data-ttu-id="73e7f-643">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="73e7f-643">**Source of Compromise**</span></span>
- <span data-ttu-id="73e7f-644">**標記**</span><span class="sxs-lookup"><span data-stu-id="73e7f-644">**Tags**</span></span>

<span data-ttu-id="73e7f-645">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="73e7f-645">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="73e7f-646">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-646">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="73e7f-647">**偵測**</span><span class="sxs-lookup"><span data-stu-id="73e7f-647">**Detection**</span></span>
- <span data-ttu-id="73e7f-648">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-648">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="73e7f-649">**方向**</span><span class="sxs-lookup"><span data-stu-id="73e7f-649">**Direction**</span></span>
- <span data-ttu-id="73e7f-650">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-650">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="73e7f-651">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-651">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="73e7f-652">**網域**</span><span class="sxs-lookup"><span data-stu-id="73e7f-652">**Domain**</span></span>
- <span data-ttu-id="73e7f-653">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="73e7f-653">**Policy type**</span></span>
- <span data-ttu-id="73e7f-654">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="73e7f-654">**Policy name** (details table only)</span></span>
- <span data-ttu-id="73e7f-655">**收件者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-655">**Recipients**</span></span>

<span data-ttu-id="73e7f-656">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-656">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="73e7f-657"><sup>\*</sup>僅限 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-657"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="73e7f-658">主要惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-658">Top malware report</span></span>

<span data-ttu-id="73e7f-659">**主要惡意** 代碼報告會顯示 [EOP 中的反惡意程式碼防護](anti-malware-protection.md)所偵測到的各種惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="73e7f-659">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="73e7f-660">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-660">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-661">在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 [ **主要惡意** 代碼]，然後按一下 [ **詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-661">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="73e7f-662">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-662">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![「電子郵件 & 協同報告」頁面上的主要惡意程式碼小工具](../../media/top-malware-report-widget.png)

<span data-ttu-id="73e7f-664">當您將游標移到圓形圖中的楔形上方時，您可以看到惡意程式碼類型的名稱，以及偵測到該惡意程式碼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="73e7f-664">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="73e7f-665">在「 **主要惡意程式碼報告** 」頁面上，報表頁面上會顯示較大的餅版本圖表。圖表下方的 [詳細資料] 表格會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="73e7f-665">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="73e7f-666">**主要惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-666">**Top malware**</span></span>
- <span data-ttu-id="73e7f-667">**Count**</span><span class="sxs-lookup"><span data-stu-id="73e7f-667">**Count**</span></span>

<span data-ttu-id="73e7f-668">如果您按一下 [ **篩選**]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="73e7f-668">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![主要惡意程式碼報表檢視](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="73e7f-670">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-670">URL threat protection report</span></span>

<span data-ttu-id="73e7f-671">Office 365 的「 **URL 威脅防護」報告** 可用於的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="73e7f-671">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="73e7f-672">如需詳細資訊，請參閱 [URL 威脅防護報告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-672">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="73e7f-673">使用者報告的訊息報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-673">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73e7f-674">為了讓 **使用者報告的訊息** 報告正確運作，必須為您的 Microsoft 365 環境 **開啟審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="73e7f-674">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="73e7f-675">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="73e7f-675">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="73e7f-676">如需詳細資訊，請參閱[開啟或關閉 Microsoft 365 審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-676">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="73e7f-677">「 **使用者報告的訊息** 報告」顯示使用者已使用 [報告郵件增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)舉報為垃圾郵件、網路釣魚企圖或良好郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="73e7f-677">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="73e7f-678">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="73e7f-678">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="73e7f-679">在 [ **電子郵件 &** 共同作業報告] 頁面上，找出 **使用者報告的訊息** ，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-679">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="73e7f-680">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="73e7f-680">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="73e7f-681">若要移至 [Microsoft 365 Defender 入口網站中的系統管理提交](admin-submission.md)，按一下 [**移至提交**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-681">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![「電子郵件 & 共同作業報告」頁面上的使用者報告的訊息小工具](../../media/user-reported-messages-widget.png)

<span data-ttu-id="73e7f-683">在 [ **使用者報告的郵件** ] 頁面上，您可以按一下 [ **篩選** ]，然後在出現的浮出控制項中，選取下列一或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="73e7f-683">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="73e7f-684">**報告日期**： **開始時間** 和 **結束時間**</span><span class="sxs-lookup"><span data-stu-id="73e7f-684">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="73e7f-685">**報告者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-685">**Reported by**</span></span>
- <span data-ttu-id="73e7f-686">**電子郵件主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-686">**Email subject**</span></span>
- <span data-ttu-id="73e7f-687">**訊息報告識別碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-687">**Message reported ID**</span></span>
- <span data-ttu-id="73e7f-688">**網路消息識別碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-688">**Network Message ID**</span></span>
- <span data-ttu-id="73e7f-689">**Sender**</span><span class="sxs-lookup"><span data-stu-id="73e7f-689">**Sender**</span></span>
- <span data-ttu-id="73e7f-690">**報告原因**</span><span class="sxs-lookup"><span data-stu-id="73e7f-690">**Reported reason**</span></span>
  - <span data-ttu-id="73e7f-691">**非垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-691">**Not junk**</span></span>
  - <span data-ttu-id="73e7f-692">**網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="73e7f-692">**Phish**</span></span>
  - <span data-ttu-id="73e7f-693">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="73e7f-693">**Spam**</span></span>
- <span data-ttu-id="73e7f-694">**網路釣魚模擬**： **是** 或 **否**</span><span class="sxs-lookup"><span data-stu-id="73e7f-694">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="73e7f-695">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="73e7f-695">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="73e7f-696">若要群組專案，請按一下 [ **群組** ]，然後從下拉式清單中選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="73e7f-696">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="73e7f-697">**無**</span><span class="sxs-lookup"><span data-stu-id="73e7f-697">**None**</span></span>
- <span data-ttu-id="73e7f-698">**原因**</span><span class="sxs-lookup"><span data-stu-id="73e7f-698">**Reason**</span></span>
- <span data-ttu-id="73e7f-699">**Sender**</span><span class="sxs-lookup"><span data-stu-id="73e7f-699">**Sender**</span></span>
- <span data-ttu-id="73e7f-700">**報告者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-700">**Reported by**</span></span>
- <span data-ttu-id="73e7f-701">**重新掃描結果**</span><span class="sxs-lookup"><span data-stu-id="73e7f-701">**Rescan result**</span></span>
- <span data-ttu-id="73e7f-702">**網路釣魚模擬模擬**</span><span class="sxs-lookup"><span data-stu-id="73e7f-702">**Phish simulation**</span></span>

![使用者報告的訊息報告](../../media/user-reported-messages-report.png)

<span data-ttu-id="73e7f-704">在圖形下方的 [詳細資料] 表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="73e7f-704">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="73e7f-705">**電子郵件主旨**</span><span class="sxs-lookup"><span data-stu-id="73e7f-705">**Email subject**</span></span>
- <span data-ttu-id="73e7f-706">**報告者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-706">**Reported by**</span></span>
- <span data-ttu-id="73e7f-707">**報告日期**</span><span class="sxs-lookup"><span data-stu-id="73e7f-707">**Date reported**</span></span>
- <span data-ttu-id="73e7f-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="73e7f-708">**Sender**</span></span>
- <span data-ttu-id="73e7f-709">**報告原因**</span><span class="sxs-lookup"><span data-stu-id="73e7f-709">**Reported reason**</span></span>
- <span data-ttu-id="73e7f-710">**重新掃描結果**</span><span class="sxs-lookup"><span data-stu-id="73e7f-710">**Rescan result**</span></span>
- <span data-ttu-id="73e7f-711">**標記**</span><span class="sxs-lookup"><span data-stu-id="73e7f-711">**Tags**</span></span>

<span data-ttu-id="73e7f-712">若要將郵件提交給 Microsoft 進行分析，請選取表格中的訊息項目，按一下 [ **提交給 Microsoft 進行分析** ]，然後從下拉式清單中選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="73e7f-712">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="73e7f-713">**報告清理**</span><span class="sxs-lookup"><span data-stu-id="73e7f-713">**Report clean**</span></span>
- <span data-ttu-id="73e7f-714">**報告網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="73e7f-714">**Report phishing**</span></span>
- <span data-ttu-id="73e7f-715">**報告惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="73e7f-715">**Report malware**</span></span>
- <span data-ttu-id="73e7f-716">**報告垃圾郵件**'</span><span class="sxs-lookup"><span data-stu-id="73e7f-716">**Report spam**'</span></span>
- <span data-ttu-id="73e7f-717">Office 365) 的 **觸發調查** (Defender</span><span class="sxs-lookup"><span data-stu-id="73e7f-717">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="73e7f-718">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="73e7f-718">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="73e7f-719">為了查看和使用本文所述的報表，您必須是 Microsoft 365 Defender 入口網站中下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="73e7f-719">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="73e7f-720">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="73e7f-720">**Organization Management**</span></span>
- <span data-ttu-id="73e7f-721">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="73e7f-721">**Security Administrator**</span></span>
- <span data-ttu-id="73e7f-722">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="73e7f-722">**Security Reader**</span></span>
- <span data-ttu-id="73e7f-723">**全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="73e7f-723">**Global Reader**</span></span>

<span data-ttu-id="73e7f-724">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-724">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="73e7f-725">**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="73e7f-725">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="73e7f-726">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-726">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="73e7f-727">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="73e7f-727">What if the reports aren't showing data?</span></span>

<span data-ttu-id="73e7f-728">如果您未看到報表中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="73e7f-728">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="73e7f-729">若要深入瞭解，請參閱 [防禦威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="73e7f-729">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="73e7f-730">相關主題</span><span class="sxs-lookup"><span data-stu-id="73e7f-730">Related topics</span></span>

[<span data-ttu-id="73e7f-731">EOP 中的反垃圾郵件和反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="73e7f-731">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="73e7f-732">Microsoft 365 Defender 入口網站中的智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="73e7f-732">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="73e7f-733">在 Microsoft 365 Defender 入口網站中查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-733">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="73e7f-734">View Office 365 的 Defender 報告</span><span class="sxs-lookup"><span data-stu-id="73e7f-734">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
