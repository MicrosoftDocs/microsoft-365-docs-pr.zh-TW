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
ms.openlocfilehash: ad5a9f0d87902deb1985daebfa61cd733d22cbec
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029547"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="1fd6b-103">在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1fd6b-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-104">**Applies to**</span></span>
- [<span data-ttu-id="1fd6b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1fd6b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1fd6b-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="1fd6b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1fd6b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1fd6b-108">Microsoft 365 Defender 入口網站提供各種報告 <https://security.microsoft.com> ，可協助您觀察電子郵件安全性功能（例如 Microsoft 365 中的反垃圾郵件、反惡意程式碼和加密功能）如何保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="1fd6b-109">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以在 Microsoft 365 Defender 入口網站中查看這些報告，方式是要 **報告** \> **電子郵件 &** 共同作業 & 共同作業 \> **報告**。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-110">若要直接移至 [ **電子郵件 &** 共同作業報告] 頁面上，開啟 <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender 入口網站中的電子郵件 & 共同作業報告] 頁面](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="1fd6b-112">[ **電子郵件 & 協同報告** ] 頁面上的某些報告需要 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="1fd6b-113">如需這些報告的詳細資訊，請參閱 [在 Microsoft 365 Defender 入口網站中查看 Office 365 報告的 Defender](view-reports-for-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="1fd6b-114">與郵件流程相關的報告現在位於 Exchange 系統管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="1fd6b-115">如需這些報告的詳細資訊，請參閱 [新 Exchange 系統管理中心的郵件流程報告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="1fd6b-116">已遭破壞的使用者報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="1fd6b-117">這份報告可在 Microsoft 365 組織中使用 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="1fd6b-118">在獨立 Exchange Online Protection (EOP) 組織中無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="1fd6b-119">「已 **遭破壞的使用者** 報告」顯示顯示過去7天內已標示為 **可疑** 或 **限制** 的使用者帳戶數目。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="1fd6b-120">在上述任一狀態的帳戶都有問題或甚至遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="1fd6b-121">在經常使用的情況下，您可以使用報表來找出峰值，甚至是趨勢，也就是可疑或受限制的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="1fd6b-122">如需遭到破壞之使用者的詳細資訊，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![「電子郵件 & 共同作業報告」頁面上已遭破壞的使用者小工具](../../media/compromised-users-report-widget.png)

<span data-ttu-id="1fd6b-124">匯總視圖會顯示過去90天的資料，詳細資料檢視會顯示過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="1fd6b-125">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-126">在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 **遭破壞的使用者** ，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="1fd6b-127">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="1fd6b-128">在 [已 **遭破壞的使用者** ] 頁面上，您可以按一下 [ **篩選** ]，然後在出現的飛出視窗中，選取下列一或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="1fd6b-129">**日期 (UTC)**： **開始日期** 和 **結束日期**。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="1fd6b-130">**活動**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-130">**Activity**:</span></span>
  - <span data-ttu-id="1fd6b-131">**可疑**：使用者帳戶已傳送可疑的電子郵件，而且受到限制傳送電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="1fd6b-132">**限制**：由於高度可疑的模式，使用者帳戶已限制傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="1fd6b-133">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![已遭破壞之使用者報告中的報表檢視](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="1fd6b-135">在圖形下方的 [詳細資料] 表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="1fd6b-136">**建立時間**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-136">**Creation time**</span></span>
- <span data-ttu-id="1fd6b-137">**User ID**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-137">**User ID**</span></span>
- <span data-ttu-id="1fd6b-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="1fd6b-139">Exchange transport rule 報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-139">Exchange transport rule report</span></span>

<span data-ttu-id="1fd6b-140">**Exchange transport rule** report 會顯示郵件流程規則 (也稱為傳輸規則) 組織中內送和外寄郵件的效果。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="1fd6b-141">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-142">在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 [ **Exchange transport rule** ]，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="1fd6b-143">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![「電子郵件 & 共同作業報告」頁面上的 Exchange 傳輸規則小工具](../../media/transport-rule-report-widget.png)

<span data-ttu-id="1fd6b-145">在 [ **Exchange transport rule 報告** ] 頁面上，下列各節將說明可用的圖表和資料。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="1fd6b-146">依方向的圖表分解</span><span class="sxs-lookup"><span data-stu-id="1fd6b-146">Chart breakdown by Direction</span></span>

![Exchange transport rule 報告中 Exchange Transport rules 的方向視圖](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="1fd6b-148">如果您 **依方向選取 [圖表分解**]，可使用下列圖表：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="1fd6b-149">透過 **Exchange 傳輸規則來查看資料**：受郵件流程規則影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="1fd6b-150">**以 DLP Exchange 傳輸規則來查看資料**：受資料遺失防護 (DLP) 郵件流程規則所影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="1fd6b-151">下列資訊會顯示在圖形下方的詳細資料表格中：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="1fd6b-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-152">**Date**</span></span>
- <span data-ttu-id="1fd6b-153">**Dlp 原則** (只 **依 dlp Exchange Transport rules 來查看資料**) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="1fd6b-154">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-154">**Transport rule**</span></span>
- <span data-ttu-id="1fd6b-155">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-155">**Subject**</span></span>
- <span data-ttu-id="1fd6b-156">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-156">**Sender address**</span></span>
- <span data-ttu-id="1fd6b-157">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-157">**Recipient address**</span></span>
- <span data-ttu-id="1fd6b-158">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-158">**Severity**</span></span>
- <span data-ttu-id="1fd6b-159">**方向**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-159">**Direction**</span></span>

<span data-ttu-id="1fd6b-160">您可以在出現的浮出控制項中按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="1fd6b-161">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-162">**方向**： **輸出** 和 **輸入**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="1fd6b-163">**嚴重性**： **高嚴重性**、 **中低嚴重性** 和 **低嚴重性**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="1fd6b-164">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="1fd6b-165">依嚴重性的圖表細目</span><span class="sxs-lookup"><span data-stu-id="1fd6b-165">Chart breakdown by Severity</span></span>

![Exchange transport rule 報告中 Exchange Transport rules 的嚴重性視圖](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="1fd6b-167">如果您 **依嚴重性選取 [圖表分解**]，可使用下列圖表：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="1fd6b-168">透過 **Exchange 傳輸規則來查看資料**：**高嚴重性**、**中嚴重性** 和 **低嚴重性** 郵件的數目。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="1fd6b-169">您可以將嚴重性層級設定為規則 ([ **以嚴重性層級** 或 _SetAuditSeverity_) 審核此規則] 中的動作。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="1fd6b-170">如需詳細資訊，請參閱 [Exchange Online 中的郵件流程規則動作](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="1fd6b-171">**按 Dlp Exchange transport rules 來查看資料**：受 dlp 郵件流程規則影響的 **高嚴重性**、 **中嚴重性** 和 **低嚴重性** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="1fd6b-172">下列資訊會顯示在圖形下方的詳細資料表格中：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="1fd6b-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-173">**Date**</span></span>
- <span data-ttu-id="1fd6b-174">**Dlp 原則** (只 **依 dlp Exchange Transport rules 來查看資料**) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="1fd6b-175">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-175">**Transport rule**</span></span>
- <span data-ttu-id="1fd6b-176">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-176">**Subject**</span></span>
- <span data-ttu-id="1fd6b-177">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-177">**Sender address**</span></span>
- <span data-ttu-id="1fd6b-178">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-178">**Recipient address**</span></span>
- <span data-ttu-id="1fd6b-179">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-179">**Severity**</span></span>
- <span data-ttu-id="1fd6b-180">**方向**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-180">**Direction**</span></span>

<span data-ttu-id="1fd6b-181">您可以在出現的浮出控制項中按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="1fd6b-182">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-183">**方向**： **輸出** 和 **輸入**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="1fd6b-184">**嚴重性**： **高嚴重性**、 **中低嚴重性** 和 **低嚴重性**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="1fd6b-185">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="1fd6b-186">轉接報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="1fd6b-187">您現在可以在 EAC 中使用轉寄 **報告** 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="1fd6b-188">如需詳細資訊，請參閱 [新 EAC 中的自動轉寄郵件報告](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="1fd6b-189">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="1fd6b-189">Mailflow status report</span></span>

<span data-ttu-id="1fd6b-190">**郵件流程狀態報表** 是一個智慧報告，顯示傳入和傳出電子郵件、垃圾郵件偵測、惡意程式碼、識別為「良好」之電子郵件的相關資訊，以及有關允許或封鎖在 edge 上之電子郵件的資訊。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="1fd6b-191">這是唯一包含 edge protection 資訊的報告，它會顯示在 Exchange Online Protection (EOP) 中，允許在評估之前封鎖多少封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="1fd6b-192">請務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="1fd6b-193">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-194">在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 **郵件流程狀態摘要** ，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="1fd6b-195">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![[電子郵件 & 共同作業報告] 頁面上的 [郵件流程狀態摘要] 小工具](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="1fd6b-197">郵件流程狀態報表的類型視圖</span><span class="sxs-lookup"><span data-stu-id="1fd6b-197">Type view for the Mailflow status report</span></span>

![郵件流程狀態報表中的類型視圖](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="1fd6b-199">在 [ **郵件流程狀態報表** ] 頁面上，預設會選取 [ **類型** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="1fd6b-200">根據預設，此視圖包含的圖表和詳細資料表格已設定為下列篩選：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="1fd6b-201">**日期 (UTC)** 過去7天。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="1fd6b-202">**郵件方向**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-202">**Mail direction**:</span></span>
  - <span data-ttu-id="1fd6b-203">**入境**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-203">**Inbound**</span></span>
  - <span data-ttu-id="1fd6b-204">**出境**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-204">**Outbound**</span></span>
  - <span data-ttu-id="1fd6b-205">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="1fd6b-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="1fd6b-206">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與 **輸入** 和 **輸出**) 分開計數</span><span class="sxs-lookup"><span data-stu-id="1fd6b-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="1fd6b-207">**類型**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-207">**Type**:</span></span>
  - <span data-ttu-id="1fd6b-208">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-208">**Good mail**</span></span>
  - <span data-ttu-id="1fd6b-209">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-209">**Malware**</span></span>
  - <span data-ttu-id="1fd6b-210">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-210">**Spam**</span></span>
  - <span data-ttu-id="1fd6b-211">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-211">**Edge protection**</span></span>
  - <span data-ttu-id="1fd6b-212">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-212">**Rule messages**</span></span>
  - <span data-ttu-id="1fd6b-213">**網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-213">**Phishing email**</span></span>
- <span data-ttu-id="1fd6b-214">**網域**： **全部**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-214">**Domain**: **All**</span></span>

<span data-ttu-id="1fd6b-215">圖表是依 **類型** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="1fd6b-216">您可以按一下 [ **篩選**] 以變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="1fd6b-217">下列資訊會顯示在圖形下方的詳細資料表格中：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="1fd6b-218">**方向**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-218">**Direction**</span></span>
- <span data-ttu-id="1fd6b-219">**類型**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-219">**Type**</span></span>
- <span data-ttu-id="1fd6b-220">**24 小時**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-220">**24 hours**</span></span>
- <span data-ttu-id="1fd6b-221">**3天**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-221">**3 days**</span></span>
- <span data-ttu-id="1fd6b-222">**7 天**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-222">**7 days**</span></span>
- <span data-ttu-id="1fd6b-223">**15 天**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-223">**15 days**</span></span>
- <span data-ttu-id="1fd6b-224">**30天**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-224">**30 days**</span></span>

<span data-ttu-id="1fd6b-225">如果您按一下 **[選擇類別] 以取得詳細資料**，您可以選取下列值：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="1fd6b-226">**網路釣魚電子郵件**：這項選擇會帶您前往「 [威脅防護狀態」報告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="1fd6b-227">**電子郵件中的惡意** 代碼：這項選擇會帶您前往 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="1fd6b-228">**垃圾郵件** 偵測：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="1fd6b-229">**Edge 封鎖的垃圾郵件**：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="1fd6b-230">從類型視圖匯出</span><span class="sxs-lookup"><span data-stu-id="1fd6b-230">Export from Type view</span></span>

<span data-ttu-id="1fd6b-231">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="1fd6b-232">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="1fd6b-233">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="1fd6b-234">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="1fd6b-235">郵件流程狀態報表的方向視圖</span><span class="sxs-lookup"><span data-stu-id="1fd6b-235">Direction view for the Mailflow status report</span></span>

![郵件流程狀態報表中的方向視圖](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="1fd6b-237">如果您按一下 [ **方向** ] 索引標籤，則會使用 [ **類型** ] 視圖中的相同預設篩選器。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="1fd6b-238">圖表是依 **方向** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="1fd6b-239">您可以按一下 [ **篩選**] 以變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="1fd6b-240">會使用 [ **類型** ] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="1fd6b-241">詳細資料表格包含的資訊來自 **類型** view。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="1fd6b-242">[ **選擇類別** ] 如需詳細資料，可用的選取專案和行為與「 **類型** 」視圖相同。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="1fd6b-243">從方向視圖匯出</span><span class="sxs-lookup"><span data-stu-id="1fd6b-243">Export from Direction view</span></span>

<span data-ttu-id="1fd6b-244">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="1fd6b-245">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="1fd6b-246">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="1fd6b-247">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="1fd6b-248">郵件流程狀態報表的漏斗視圖</span><span class="sxs-lookup"><span data-stu-id="1fd6b-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="1fd6b-249">**漏斗** 視圖顯示 Microsoft 的電子郵件威脅防護功能如何篩選組織中的內送和外寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="1fd6b-250">它提供有關電子郵件總數的詳細資訊，以及設定的威脅防護功能（包括 edge protection、反惡意程式碼、反網路釣魚、反垃圾郵件和反欺詐）對此計數的影響。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![郵件流程狀態報表中的漏斗圖視圖](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="1fd6b-252">如果您按一下 [ **漏斗** ] 索引標籤，此 view 預設會包含 [圖表] 和 [詳細資料] 表格設定為下列篩選：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="1fd6b-253">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="1fd6b-254">**方向**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-254">**Direction**:</span></span>
  - <span data-ttu-id="1fd6b-255">**入境**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-255">**Inbound**</span></span>
  - <span data-ttu-id="1fd6b-256">**出境**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-256">**Outbound**</span></span>
  - <span data-ttu-id="1fd6b-257">**組織內**：此計數是針對在租使用者中傳送的郵件進行計數;亦即，寄件者 abc@domain.com 會傳送給收件者 xyz@domain.com (與輸入和外寄) 分開計數。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="1fd6b-258">匯總視圖和詳細資料表格視圖允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="1fd6b-259">您可以按一下 [ **篩選**] 以變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="1fd6b-260">會使用 [ **類型** ] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="1fd6b-261">此圖顯示按下列方式組織的電子郵件計數：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="1fd6b-262">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-262">**Total email**</span></span>
- <span data-ttu-id="1fd6b-263">**Edge protection 之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-263">**Email after edge protection**</span></span>
- <span data-ttu-id="1fd6b-264">**傳輸規則** (郵件流程規則之後的電子郵件) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="1fd6b-265">**反惡意程式碼、檔信譽、檔案類型封鎖後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="1fd6b-266">**反網路釣魚、URL 信譽、品牌模擬、反欺騙功能之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="1fd6b-267">**反垃圾郵件、大宗郵件篩選後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="1fd6b-268">**使用者和網域模擬後的電子郵件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="1fd6b-269">**檔案及 URL 引爆後的電子郵件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="1fd6b-270">**在傳遞投遞後保護後，電子郵件偵測為良性 (URL 按一下時間保護)**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="1fd6b-271"><sup>\*</sup>僅限 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="1fd6b-272">若要個別查看以 EOP 或 Defender 為 Office 365 篩選的電子郵件，請按一下 [圖表圖例] 中的值。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="1fd6b-273">[詳細資料] 表格包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="1fd6b-274">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-274">**Date**</span></span>
- <span data-ttu-id="1fd6b-275">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-275">**Total email**</span></span>
- <span data-ttu-id="1fd6b-276">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-276">**Edge protection**</span></span>
- <span data-ttu-id="1fd6b-277">**反惡意程式碼、檔信譽、檔案類型封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="1fd6b-278">**檔信譽**：由於其他 Microsoft 客戶附加的檔案識別，因此篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="1fd6b-279">**檔案類型封鎖**：由於郵件中識別的惡意檔案類型，篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="1fd6b-280">**反網路釣魚、URL 信譽、品牌模仿、反欺騙**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="1fd6b-281">**URL 信譽**：由於其他 Microsoft 客戶的 url 身分識別而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="1fd6b-282">**品牌** 模擬：因為郵件是由眾所周知的品牌類比寄件者所過濾，所以會加以篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="1fd6b-283">**反欺騙**：因為郵件企圖哄騙收件者所屬的網域，或是郵件寄件者不會擁有的網域，所以篩選掉郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="1fd6b-284">**反垃圾郵件，大宗郵件篩選**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="1fd6b-285">**大宗郵件篩選**：在反垃圾郵件原則中依據大量抱怨層級 (BCL) 臨界值篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="1fd6b-286">**Office 365) 的使用者和網域模擬 (Defender**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="1fd6b-287">**使用者** 模擬：郵件因嘗試模擬使用者 (郵件寄件者) （已在反網路釣魚原則的類比保護設定中所定義）而篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="1fd6b-288">**網域** 模擬：郵件因嘗試模擬防網路釣魚原則之類比保護設定中所定義的網域而篩選出來。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="1fd6b-289">檔案 **及 URL 引爆 (Defender for Office 365)**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="1fd6b-290">檔案 **引爆**：以 Safe 附件原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="1fd6b-291">**URL 引爆**：透過 Safe 連結原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="1fd6b-292">**投遞後保護和 zap (ATP) 或 zap (EOP)**：零小時自動清除 (針對惡意程式碼、垃圾郵件和網路釣魚的 ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="1fd6b-293">如果您選取 [詳細資料] 表格中的列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="1fd6b-294">從漏斗視圖匯出</span><span class="sxs-lookup"><span data-stu-id="1fd6b-294">Export from Funnel view</span></span>

<span data-ttu-id="1fd6b-295">在 [**選項**] 下按一下 [**匯出**] 後，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="1fd6b-296">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="1fd6b-297">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="1fd6b-298">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="1fd6b-299">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="1fd6b-300">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="1fd6b-301">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="1fd6b-302">郵件流程狀態報表的技術視圖</span><span class="sxs-lookup"><span data-stu-id="1fd6b-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="1fd6b-303">**技術視圖** 類似 **漏斗** 圖模式，可提供設定威脅防護功能的更細微細節。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="1fd6b-304">您可以從圖表中查看郵件如何在威脅防護的不同階段進行分類。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="1fd6b-305">如果您按一下 [ **技術視圖** ] 索引標籤，此視圖預設會包含 [圖表] 和 [詳細資料] 表格設定為下列篩選：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="1fd6b-306">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="1fd6b-307">**方向**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-307">**Direction**:</span></span>
  - <span data-ttu-id="1fd6b-308">**入境**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-308">**Inbound**</span></span>
  - <span data-ttu-id="1fd6b-309">**出境**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-309">**Outbound**</span></span>
  - <span data-ttu-id="1fd6b-310">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="1fd6b-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="1fd6b-311">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與輸入和輸出) 分開計數</span><span class="sxs-lookup"><span data-stu-id="1fd6b-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="1fd6b-312">匯總視圖和詳細資料表格視圖允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="1fd6b-313">您可以按一下 [ **篩選**] 以變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="1fd6b-314">會使用 [ **類型** ] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="1fd6b-315">此圖顯示組織成下列類別的郵件：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="1fd6b-316">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-316">**Total email**</span></span>
- <span data-ttu-id="1fd6b-317">**Edge 允許** 和 **edge 篩選**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="1fd6b-318">已篩選的 **傳輸規則允許** 和 **傳輸規則** (郵件流程規則) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="1fd6b-319">**非惡意** 代碼、 **Safe 附件偵測** <sup>\*</sup> 和 **反惡意程式碼引擎偵測**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="1fd6b-320">**不是網路釣魚詐騙**、 **DMARC 失敗**、**模仿偵測** <sup>\*</sup> 、**欺騙偵測** 和 **網路釣魚偵測**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="1fd6b-321">**沒有偵測 URL 引爆** 及 **url 引爆偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="1fd6b-322">**非垃圾郵件** 和  **垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="1fd6b-323">**非惡意的電子郵件**、 **Safe 連結偵測** <sup>\*</sup> 和 **ZAP**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="1fd6b-324"><sup>\*</sup>Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="1fd6b-325">當您將游標移到圖表中的某個類別時，您可以看到該類別中的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="1fd6b-326">[詳細資料] 表格包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="1fd6b-327">**日期 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-327">**Date (UTC)**</span></span>
- <span data-ttu-id="1fd6b-328">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-328">**Total email**</span></span>
- <span data-ttu-id="1fd6b-329">**已篩選 Edge**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-329">**Edge filtered**</span></span>
- <span data-ttu-id="1fd6b-330">**規則郵件**：由於郵件流程規則而篩選的郵件 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="1fd6b-331">**反惡意程式碼引擎**， **Safe 附件** <sup>\*</sup> ：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="1fd6b-332">**DMARC，類比** <sup>\*</sup> ，**欺騙**，**網路釣魚篩選**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="1fd6b-333">**DMARC**：由於郵件失敗的 DMARC 驗證檢查而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="1fd6b-334">**URL 引爆偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="1fd6b-335">**已篩選的反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="1fd6b-336">**移除的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-336">**ZAP removed**</span></span>
- <span data-ttu-id="1fd6b-337">**Safe 連結偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="1fd6b-338"><sup>\*</sup>Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="1fd6b-339">如果您選取 [詳細資料] 表格中的列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="1fd6b-340">從技術視圖匯出</span><span class="sxs-lookup"><span data-stu-id="1fd6b-340">Export from Tech view</span></span>

<span data-ttu-id="1fd6b-341">在按一下 [ **匯出**] 的 [ **選項** ] 底下，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="1fd6b-342">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="1fd6b-343">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="1fd6b-344">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="1fd6b-345">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="1fd6b-346">每個匯出的 .csv 檔會限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="1fd6b-347">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![郵件流程狀態報表中的技術視圖](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="1fd6b-349">惡意程式碼檢測報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-349">Malware detections report</span></span>

<span data-ttu-id="1fd6b-350">**惡意軟體偵測報告** 會顯示 Exchange Online Protection 或 EOP) 所偵測到的內送和外寄電子郵件， (惡意軟體偵測的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="1fd6b-351">如需 EOP 中惡意程式碼保護的詳細資訊，請參閱 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="1fd6b-352">匯總 view 篩選允許90天，而 [詳細資料表格篩選] 只允許10天。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="1fd6b-353">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-354">在 [**電子郵件 &** 共同作業報告] 頁面上，尋找 [**在電子郵件中偵測到惡意** 代碼]，然後按一下 [ **View**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="1fd6b-355">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![電子郵件 & 協同報告] 頁面上電子郵件小工具中的惡意程式碼偵測](../../media/malware-detections-widget.png)

<span data-ttu-id="1fd6b-357">在 [ **惡意** 代碼偵測報告] 頁面上，您可以按一下 [ **篩選** ] 並選取下列其中一個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="1fd6b-358">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-359">**方向**： **輸入** 和 **輸出**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-359">**Direction**: **Inbound** and **Outbound**</span></span>

![電子郵件中的惡意程式碼偵測報表檢視](../../media/malware-detections-report-view.png)

<span data-ttu-id="1fd6b-361">在圖形下方的 [詳細資料] 表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="1fd6b-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-362">**Date**</span></span>
- <span data-ttu-id="1fd6b-363">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-363">**Sender address**</span></span>
- <span data-ttu-id="1fd6b-364">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-364">**Recipient address**</span></span>
- <span data-ttu-id="1fd6b-365">**郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="1fd6b-366">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="1fd6b-367">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-367">**Subject**</span></span>
- <span data-ttu-id="1fd6b-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-368">**Filename**</span></span>
- <span data-ttu-id="1fd6b-369">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="1fd6b-370">郵件延遲報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-370">Mail latency report</span></span>

<span data-ttu-id="1fd6b-371">Office 365 的「中的 **郵件延遲報告**] 包含組織內的郵件傳遞和引爆延遲的資訊。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="1fd6b-372">如需詳細資訊，請參閱 [郵件延遲報告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="1fd6b-373">垃圾郵件偵測報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="1fd6b-374">**垃圾郵件偵測報告** 會最後移出。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="1fd6b-375">「 [威脅防護狀態」報告](#threat-protection-status-report)中提供相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="1fd6b-376">欺騙偵測報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="1fd6b-377">本文中所述的 [已改進的欺騙偵測報告] 是預覽中所述，視情況而變更，並非所有組織都提供這些報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="1fd6b-378">較舊的報表版本只會顯示 **良好的郵件** ，而且會被 **視為垃圾** 郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="1fd6b-379">**欺騙** 偵測報告會顯示因欺騙性而封鎖或允許的郵件相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="1fd6b-380">如需有關電子欺騙的詳細資訊，請參閱 [EOP 中的反欺騙防護](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="1fd6b-381">報表的匯總視圖允許45天的篩選 <sup>\*</sup> ，而詳細資料檢視只允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="1fd6b-382"><sup>\*</sup> 最後，您將可以使用超過90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="1fd6b-383">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-384">在 [ **電子郵件 &** 共同作業報告] 頁面上，找出 **欺騙** 偵測，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="1fd6b-385">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![電子郵件 & 協同報告] 頁面上的欺騙偵測小工具](../../media/spoof-detections-widget.png)

<span data-ttu-id="1fd6b-387">此圖表顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-387">The chart shows the following information:</span></span>

- <span data-ttu-id="1fd6b-388">**通過**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-388">**Pass**</span></span>
- <span data-ttu-id="1fd6b-389">**失敗**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-389">**Fail**</span></span>
- <span data-ttu-id="1fd6b-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-390">**SoftPass**</span></span>
- <span data-ttu-id="1fd6b-391">**無**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-391">**None**</span></span>
- <span data-ttu-id="1fd6b-392">**其他**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-392">**Other**</span></span>

<span data-ttu-id="1fd6b-393">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您可以看到偵測到的冒牌郵件數目及原因。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="1fd6b-394">在 [ **偽造郵件報告** ] 頁面上，您可以按一下 [ **篩選** ]，然後選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="1fd6b-395">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-396">**結果**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-396">**Result**:</span></span>
  - <span data-ttu-id="1fd6b-397">**通過**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-397">**Pass**</span></span>
  - <span data-ttu-id="1fd6b-398">**失敗**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-398">**Fail**</span></span>
  - <span data-ttu-id="1fd6b-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-399">**SoftPass**</span></span>
  - <span data-ttu-id="1fd6b-400">**無**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-400">**None**</span></span>
  - <span data-ttu-id="1fd6b-401">**其他**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-401">**Other**</span></span>
- <span data-ttu-id="1fd6b-402">**哄騙類型**： **Internal** 和 **External**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-402">**Spoof type**: **Internal** and **External**</span></span>

![Microsoft 365 Defender 入口網站中的 [偽造郵件報告] 頁面](../../media/spoof-detections-report-page.png)

<span data-ttu-id="1fd6b-404">在圖形下方的 [詳細資料] 表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="1fd6b-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-405">**Date**</span></span>
- <span data-ttu-id="1fd6b-406">**偽裝的使用者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-406">**Spoofed user**</span></span>
- <span data-ttu-id="1fd6b-407">**傳送基礎結構**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="1fd6b-408">**哄騙類型**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-408">**Spoof type**</span></span>
- <span data-ttu-id="1fd6b-409">**結果**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-409">**Result**</span></span>
- <span data-ttu-id="1fd6b-410">**結果代碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-410">**Result code**</span></span>
- <span data-ttu-id="1fd6b-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-411">**SPF**</span></span>
- <span data-ttu-id="1fd6b-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-412">**DKIM**</span></span>
- <span data-ttu-id="1fd6b-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-413">**DMARC**</span></span>
- <span data-ttu-id="1fd6b-414">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-414">**Message count**</span></span>

<span data-ttu-id="1fd6b-415">如需複合驗證結果代碼的詳細資訊，請參閱[反垃圾郵件郵件頭 in Microsoft 365](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="1fd6b-416">提交報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-416">Submissions report</span></span>

<span data-ttu-id="1fd6b-417">**提交** 報告會顯示系統管理員針對分析報告之專案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="1fd6b-418">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="1fd6b-419">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-420">在 [ **電子郵件 &** 共同作業報告] 頁面上，找到 [ **提交** ]，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="1fd6b-421">若要直接前往報表，請開啟 <https://security.microsoft.com/adminSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="1fd6b-422">若要移至 [Microsoft 365 Defender 入口網站中的系統管理提交](admin-submission.md)，按一下 [**移至提交**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![電子郵件 & 協同報告] 頁面上的提交小工具](../../media/submissions-report-widget.png)

<span data-ttu-id="1fd6b-424">此圖表顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-424">The chart shows the following information:</span></span>

- <span data-ttu-id="1fd6b-425">**等待**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-425">**Pending**</span></span>
- <span data-ttu-id="1fd6b-426">**已完成**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-426">**Completed**</span></span>

<span data-ttu-id="1fd6b-427">在 [ **提交** ] 頁面上，您可以按一下 [ **篩選** ]，然後選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="1fd6b-428">**報告日期**： **開始時間** 和 **結束時間**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="1fd6b-429">**提交類型**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-429">**Submission type**:</span></span>
  - <span data-ttu-id="1fd6b-430">**電子郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-430">**Email**</span></span>
  - <span data-ttu-id="1fd6b-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-431">**URL**</span></span>
  - <span data-ttu-id="1fd6b-432">**檔案**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-432">**File**</span></span>
- <span data-ttu-id="1fd6b-433">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-433">**Submission ID**</span></span>
- <span data-ttu-id="1fd6b-434">**網路消息識別碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-434">**Network Message ID**</span></span>
- <span data-ttu-id="1fd6b-435">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-435">**Sender**</span></span>
- <span data-ttu-id="1fd6b-436">**名稱**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-436">**Name**</span></span>
- <span data-ttu-id="1fd6b-437">**提交者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-437">**Submitted by**</span></span>
- <span data-ttu-id="1fd6b-438">**提交原因**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="1fd6b-439">**非垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-439">**Not junk**</span></span>
  - <span data-ttu-id="1fd6b-440">**網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-440">**Phish**</span></span>
  - <span data-ttu-id="1fd6b-441">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-441">**Malware**</span></span>
  - <span data-ttu-id="1fd6b-442">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-442">**Spam**</span></span>
- <span data-ttu-id="1fd6b-443">**重新掃描狀態**：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-443">**Rescan status**:</span></span>
  - <span data-ttu-id="1fd6b-444">**等待**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-444">**Pending**</span></span>
  - <span data-ttu-id="1fd6b-445">**已完成**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-445">**Completed**</span></span>

<span data-ttu-id="1fd6b-446">圖表下方的 [詳細資料] 表格會顯示相同的資訊，並具有相同的 **群組** 或 **自訂欄** 選項，與在 **電子郵件 &** 共同作業報送中 **提交的 [分析**] 索引標籤 \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="1fd6b-447">如需詳細資訊，請參閱 [View admin 報送 To Microsoft](admin-submission.md#view-admin-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Microsoft 365 Defender 入口網站中的「提交報告」頁面](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="1fd6b-449">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-449">Threat protection status report</span></span>

<span data-ttu-id="1fd6b-450">「**威脅防護狀態**」報告適用于 EOP 和 Defender Office 365;不過，報告包含不同的資料。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="1fd6b-451">例如，EOP 客戶可以查看在電子郵件中偵測到惡意程式碼的相關資訊，但不會[Safe SharePoint、OneDrive 及 Microsoft Teams 的附件](mdo-for-spo-odb-and-teams.md)所偵測到之惡意檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="1fd6b-452">該報告提供包含惡意內容的電子郵件統計，例如檔案或網站位址 (URLs 反惡意程式碼引擎封鎖的) 、[零小時的自動清除 (ZAP) ](zero-hour-auto-purge.md)，以及[在反網路釣魚原則中](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)Office 365[連結](safe-links.md)、 [Safe 附件](safe-attachments.md)和模擬保護功能等 Safe 功能。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="1fd6b-453">您可以使用此資訊來識別趨勢，或判斷組織原則是否需要調整。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="1fd6b-454">**附注：請** 務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="1fd6b-455">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-456">在 [ **電子郵件 & 協同報告** ] 頁面上，找出 **威脅防護狀態** ，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="1fd6b-457">若要直接前往報告，請開啟下列其中一個 URLs：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="1fd6b-458">Office 365 的 Defender：<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="1fd6b-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="1fd6b-459">EOP <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="1fd6b-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![「電子郵件 & 協同報告」頁面上的威脅防護狀態構件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="1fd6b-461">根據預設，圖表會顯示過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="1fd6b-462">如果您按一下 [**威脅防護狀態報表**] 頁面上的 [**篩選**]，您可以選取90天的日期範圍 (試用訂閱可能限制為30天) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="1fd6b-463">[詳細資料] 表格允許篩選30天。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="1fd6b-464">下列各節將說明可用的視圖。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="1fd6b-465">依概覽查看資料</span><span class="sxs-lookup"><span data-stu-id="1fd6b-465">View data by Overview</span></span>

![威脅防護狀態報表中的一覽視圖](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="1fd6b-467">在 [ **依一覽查看資料** ] 視圖中，下列偵測資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="1fd6b-468">**電子郵件惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-468">**Email malware**</span></span>
- <span data-ttu-id="1fd6b-469">**電子郵件網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-469">**Email phish**</span></span>
- <span data-ttu-id="1fd6b-470">**內容惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-470">**Content malware**</span></span>

<span data-ttu-id="1fd6b-471">圖表下沒有詳細資料表格可用。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-471">No details table is available below the chart.</span></span>

<span data-ttu-id="1fd6b-472">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="1fd6b-473">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-474">**偵測**：**電子郵件惡意** 代碼、**電子郵件網路釣魚** 或 **內容惡意** 代碼</span><span class="sxs-lookup"><span data-stu-id="1fd6b-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="1fd6b-475">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="1fd6b-476">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1fd6b-477">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="1fd6b-478">**方向**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-478">**Direction**</span></span>
- <span data-ttu-id="1fd6b-479">**網域**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-479">**Domain**</span></span>
- <span data-ttu-id="1fd6b-480">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-480">**Policy type**</span></span>

<span data-ttu-id="1fd6b-481">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="1fd6b-482">透過偵測技術透過電子郵件 \> 網路釣魚和圖表細目來查看資料</span><span class="sxs-lookup"><span data-stu-id="1fd6b-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![威脅防護狀態報表中網路釣魚電子郵件的偵測技術視圖](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="1fd6b-484">在 [透過 **電子郵件 \> 網路釣魚詐騙** ] 和 [ **依偵測方式顯示圖表明細] 技術** 視圖中，下列資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="1fd6b-485">**URL 惡意信譽** <sup>\*</sup> ：從其他 Microsoft 365 客戶的 Office 365 detonations 中的 Defender 產生惡意 URL 信譽。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="1fd6b-486">**Advanced filter**：以機器學習為基礎的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="1fd6b-487">**一般篩選**：根據分析規則的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="1fd6b-488">**組織內的欺騙**：寄件者嘗試欺騙收件者網域。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="1fd6b-489">**欺騙外部網域**：寄件者正嘗試哄騙其他一些網域。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="1fd6b-490">**哄騙 DMARC**：郵件上的 DMARC 驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="1fd6b-491">模擬 **商標**：模擬以寄件者為基礎的知名品牌。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="1fd6b-492">**混合式分析偵測**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="1fd6b-493">**檔信譽**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-493">**File reputation**</span></span>
- <span data-ttu-id="1fd6b-494">**指紋比對**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="1fd6b-495">**URL 引爆信譽**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="1fd6b-496">**URL 引爆**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="1fd6b-497">**類比使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="1fd6b-498">**類比網域** <sup>\*</sup> ：模仿客戶擁有或定義的網域。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="1fd6b-499">**信箱智慧** 模擬 <sup>\*</sup> ：由系統管理員定義或透過信箱智慧學出的使用者類比。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="1fd6b-500">**檔引爆**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="1fd6b-501">**運動**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="1fd6b-502">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="1fd6b-503">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-503">**Date**</span></span>
- <span data-ttu-id="1fd6b-504">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-504">**Subject**</span></span>
- <span data-ttu-id="1fd6b-505">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-505">**Sender**</span></span>
- <span data-ttu-id="1fd6b-506">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-506">**Recipients**</span></span>
- <span data-ttu-id="1fd6b-507">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-507">**Detected by**</span></span>
- <span data-ttu-id="1fd6b-508">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-508">**Delivery Status**</span></span>
- <span data-ttu-id="1fd6b-509">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-509">**Source of Compromise**</span></span>
- <span data-ttu-id="1fd6b-510">**標記**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-510">**Tags**</span></span>

<span data-ttu-id="1fd6b-511">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="1fd6b-512">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-513">**偵測**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-513">**Detection**</span></span>
- <span data-ttu-id="1fd6b-514">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="1fd6b-515">**方向**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-515">**Direction**</span></span>
- <span data-ttu-id="1fd6b-516">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1fd6b-517">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="1fd6b-518">**網域**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-518">**Domain**</span></span>
- <span data-ttu-id="1fd6b-519">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-519">**Policy type**</span></span>
- <span data-ttu-id="1fd6b-520">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="1fd6b-521">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-521">**Recipients**</span></span>

<span data-ttu-id="1fd6b-522">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="1fd6b-523">透過電子郵件 \> 惡意程式碼和偵測技術的圖表細目來查看資料</span><span class="sxs-lookup"><span data-stu-id="1fd6b-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![威脅防護狀態報表中惡意程式碼的偵測技術視圖](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="1fd6b-525">在 [透過 **電子郵件 \> 惡意** 代碼和 **依偵測方式顯示圖表的** 資料] 技術視圖中，下列資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="1fd6b-526">檔案 **引爆** <sup>\*</sup> ： Safe 附件的偵測。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="1fd6b-527">檔案 **引爆信譽** <sup>\*</sup> ：所有由 Defender 為 Office 365 detonations 所產生的惡意檔信譽。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="1fd6b-528">**檔信譽**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-528">**File reputation**</span></span>
- <span data-ttu-id="1fd6b-529">**反惡意程式碼引擎** <sup>\*</sup> ：從反惡意程式碼引擎偵測。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="1fd6b-530">**反惡意程式碼原則檔案類型封鎖**：由於郵件中所識別的惡意檔案類型，郵件會篩選掉這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="1fd6b-531">**URL 惡意信譽**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="1fd6b-532">**URL 引爆**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-532">**URL detonation**</span></span>
- <span data-ttu-id="1fd6b-533">**URL 引爆信譽**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="1fd6b-534">**行銷活動**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-534">**Campaign**</span></span>

<span data-ttu-id="1fd6b-535">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="1fd6b-536">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-536">**Date**</span></span>
- <span data-ttu-id="1fd6b-537">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-537">**Subject**</span></span>
- <span data-ttu-id="1fd6b-538">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-538">**Sender**</span></span>
- <span data-ttu-id="1fd6b-539">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-539">**Recipients**</span></span>
- <span data-ttu-id="1fd6b-540">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-540">**Detected by**</span></span>
- <span data-ttu-id="1fd6b-541">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-541">**Delivery Status**</span></span>
- <span data-ttu-id="1fd6b-542">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-542">**Source of Compromise**</span></span>
- <span data-ttu-id="1fd6b-543">**標記**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-543">**Tags**</span></span>

<span data-ttu-id="1fd6b-544">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="1fd6b-545">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-546">**偵測**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-546">**Detection**</span></span>
- <span data-ttu-id="1fd6b-547">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="1fd6b-548">**方向**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-548">**Direction**</span></span>
- <span data-ttu-id="1fd6b-549">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1fd6b-550">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="1fd6b-551">**網域**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-551">**Domain**</span></span>
- <span data-ttu-id="1fd6b-552">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-552">**Policy type**</span></span>
- <span data-ttu-id="1fd6b-553">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="1fd6b-554">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-554">**Recipients**</span></span>

<span data-ttu-id="1fd6b-555">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="1fd6b-556">依電子郵件 \> 網路釣魚或透過電子郵件惡意程式碼查看資料的方式，依原則類型分類的圖表 \></span><span class="sxs-lookup"><span data-stu-id="1fd6b-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威脅防護狀態報表中的網路釣魚電子郵件或惡意程式碼電子郵件的原則類型查看](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="1fd6b-558">在 [ **依原則類型的圖表分解** ] 和 [透過電子郵件惡意程式碼 **查看資料 \>** ] 或 [透過 **電子郵件 \> 惡意程式碼查看資料** ] 視圖中，圖表會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="1fd6b-559">**反惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-559">**Anti-malware**</span></span>
- <span data-ttu-id="1fd6b-560">**Safe附件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fd6b-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="1fd6b-561">**反網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-561">**Anti-phish**</span></span>
- <span data-ttu-id="1fd6b-562">**反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-562">**Anti-spam**</span></span>
- <span data-ttu-id="1fd6b-563">**郵件流程規則** (也稱為傳輸規則) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="1fd6b-564">**別人**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-564">**Others**</span></span>

<span data-ttu-id="1fd6b-565">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="1fd6b-566">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-566">**Date**</span></span>
- <span data-ttu-id="1fd6b-567">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-567">**Subject**</span></span>
- <span data-ttu-id="1fd6b-568">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-568">**Sender**</span></span>
- <span data-ttu-id="1fd6b-569">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-569">**Recipients**</span></span>
- <span data-ttu-id="1fd6b-570">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-570">**Detected by**</span></span>
- <span data-ttu-id="1fd6b-571">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-571">**Delivery Status**</span></span>
- <span data-ttu-id="1fd6b-572">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-572">**Source of Compromise**</span></span>
- <span data-ttu-id="1fd6b-573">**標記**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-573">**Tags**</span></span>

<span data-ttu-id="1fd6b-574">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="1fd6b-575">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-576">**偵測**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-576">**Detection**</span></span>
- <span data-ttu-id="1fd6b-577">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="1fd6b-578">**方向**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-578">**Direction**</span></span>
- <span data-ttu-id="1fd6b-579">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1fd6b-580">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="1fd6b-581">**網域**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-581">**Domain**</span></span>
- <span data-ttu-id="1fd6b-582">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-582">**Policy type**</span></span>
- <span data-ttu-id="1fd6b-583">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="1fd6b-584">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-584">**Recipients**</span></span>

<span data-ttu-id="1fd6b-585">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="1fd6b-586">透過電子郵件 \> 網路釣魚或透過電子郵件惡意程式碼查看資料，依傳遞狀態與查看資料的圖表細目 \></span><span class="sxs-lookup"><span data-stu-id="1fd6b-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威脅防護狀態報表中的網路釣魚電子郵件和惡意程式碼電子郵件的傳遞狀態視圖](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="1fd6b-588">在 **圖表** 中透過 **電子郵件 \> 網路釣魚** 或透過電子郵件 **\> 惡意** 代碼查看資料來查看資料，圖表會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="1fd6b-589">**主控信箱：收件匣**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="1fd6b-590">**主控信箱：垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="1fd6b-591">**主控信箱：自訂資料夾**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="1fd6b-592">**主控信箱：刪除的郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="1fd6b-593">**轉發**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-593">**Forwarded**</span></span>
- <span data-ttu-id="1fd6b-594">**內部部署伺服器：已傳送**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="1fd6b-595">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-595">**Quarantine**</span></span>
- <span data-ttu-id="1fd6b-596">**傳遞失敗**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-596">**Delivery failed**</span></span>
- <span data-ttu-id="1fd6b-597">**下降**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-597">**Dropped**</span></span>

<span data-ttu-id="1fd6b-598">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="1fd6b-599">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-599">**Date**</span></span>
- <span data-ttu-id="1fd6b-600">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-600">**Subject**</span></span>
- <span data-ttu-id="1fd6b-601">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-601">**Sender**</span></span>
- <span data-ttu-id="1fd6b-602">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-602">**Recipients**</span></span>
- <span data-ttu-id="1fd6b-603">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-603">**Detected by**</span></span>
- <span data-ttu-id="1fd6b-604">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-604">**Delivery Status**</span></span>
- <span data-ttu-id="1fd6b-605">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-605">**Source of Compromise**</span></span>
- <span data-ttu-id="1fd6b-606">**標記**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-606">**Tags**</span></span>

<span data-ttu-id="1fd6b-607">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="1fd6b-608">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-609">**偵測**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-609">**Detection**</span></span>
- <span data-ttu-id="1fd6b-610">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="1fd6b-611">**方向**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-611">**Direction**</span></span>
- <span data-ttu-id="1fd6b-612">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1fd6b-613">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="1fd6b-614">**網域**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-614">**Domain**</span></span>
- <span data-ttu-id="1fd6b-615">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-615">**Policy type**</span></span>
- <span data-ttu-id="1fd6b-616">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="1fd6b-617">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-617">**Recipients**</span></span>

<span data-ttu-id="1fd6b-618">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="1fd6b-619">依惡意程式碼查看資料 \></span><span class="sxs-lookup"><span data-stu-id="1fd6b-619">View data by Content \> Malware</span></span>

![威脅防護狀態報表中的內容惡意程式碼視圖](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="1fd6b-621">在 [**依內容 \> 惡意** 代碼查看資料] 視圖中，下列資訊會顯示在適用于 Office 365 組織的 Microsoft Defender 圖表中：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="1fd6b-622">**反惡意程式碼引擎**： [Microsoft 365 中內建的病毒偵測](virus-detection-in-spo.md)，在 Sharepoint、OneDrive 及 Microsoft Teams 中偵測到惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="1fd6b-623">檔案 **引爆**： [Safe SharePoint、OneDrive 及 Microsoft Teams 的附件](mdo-for-spo-odb-and-teams.md)所偵測到的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="1fd6b-624">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="1fd6b-625">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-626">**位置**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-626">**Location**</span></span>
- <span data-ttu-id="1fd6b-627">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-627">**Detected by**</span></span>
- <span data-ttu-id="1fd6b-628">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-628">**Malware name**</span></span>

<span data-ttu-id="1fd6b-629">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="1fd6b-630">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-631">**偵測**： **反惡意程式碼引擎** 或 **檔引爆**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="1fd6b-632">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="1fd6b-633">依系統覆寫查看資料</span><span class="sxs-lookup"><span data-stu-id="1fd6b-633">View data by System override</span></span>

![威脅防護狀態報表中的郵件覆寫視圖](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="1fd6b-635">在 [ **依系統覆寫查看資料** ] 視圖中，下列的覆寫原因資訊會顯示在圖表中：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="1fd6b-636">**內部部署略過**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-636">**On-premises skip**</span></span>
- <span data-ttu-id="1fd6b-637">**IP 允許**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-637">**IP allow**</span></span>
- <span data-ttu-id="1fd6b-638">**Exchange 郵件傳輸規則** (郵件流程規則) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="1fd6b-639">**組織允許的寄件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="1fd6b-640">**組織允許的網域**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="1fd6b-641">**未啟用的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="1fd6b-642">**未啟用垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="1fd6b-643">**使用者 Safe 寄件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-643">**User Safe Sender**</span></span>
- <span data-ttu-id="1fd6b-644">**使用者 Safe 網域**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-644">**User Safe Domain**</span></span>

<span data-ttu-id="1fd6b-645">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="1fd6b-646">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-646">**Date**</span></span>
- <span data-ttu-id="1fd6b-647">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-647">**Subject**</span></span>
- <span data-ttu-id="1fd6b-648">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-648">**Sender**</span></span>
- <span data-ttu-id="1fd6b-649">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-649">**Recipients**</span></span>
- <span data-ttu-id="1fd6b-650">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-650">**Detected by**</span></span>
- <span data-ttu-id="1fd6b-651">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-651">**Delivery Status**</span></span>
- <span data-ttu-id="1fd6b-652">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-652">**Source of Compromise**</span></span>
- <span data-ttu-id="1fd6b-653">**標記**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-653">**Tags**</span></span>

<span data-ttu-id="1fd6b-654">如果您按一下 [ **篩選**]，則可以使用下列篩選器：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="1fd6b-655">**日期 (UTC)** **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="1fd6b-656">**偵測**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-656">**Detection**</span></span>
- <span data-ttu-id="1fd6b-657">**受保護**： **MDO** (Office 365) 或 **EOP** 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="1fd6b-658">**方向**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-658">**Direction**</span></span>
- <span data-ttu-id="1fd6b-659">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1fd6b-660">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="1fd6b-661">**網域**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-661">**Domain**</span></span>
- <span data-ttu-id="1fd6b-662">**原則類型**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-662">**Policy type**</span></span>
- <span data-ttu-id="1fd6b-663">**原則名稱** (詳細資料] 表格) </span><span class="sxs-lookup"><span data-stu-id="1fd6b-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="1fd6b-664">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-664">**Recipients**</span></span>

<span data-ttu-id="1fd6b-665">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="1fd6b-666"><sup>\*</sup>僅限 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="1fd6b-667">主要惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-667">Top malware report</span></span>

<span data-ttu-id="1fd6b-668">**主要惡意** 代碼報告會顯示 [EOP 中的反惡意程式碼防護](anti-malware-protection.md)所偵測到的各種惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="1fd6b-669">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-670">在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 [ **主要惡意** 代碼]，然後按一下 [ **詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="1fd6b-671">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![「電子郵件 & 協同報告」頁面上的主要惡意程式碼小工具](../../media/top-malware-report-widget.png)

<span data-ttu-id="1fd6b-673">當您將游標移到圓形圖中的楔形上方時，您可以看到惡意程式碼類型的名稱，以及偵測到該惡意程式碼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="1fd6b-674">在「 **主要惡意程式碼報告** 」頁面上，報表頁面上會顯示較大的餅版本圖表。圖表下方的 [詳細資料] 表格會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="1fd6b-675">**主要惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-675">**Top malware**</span></span>
- <span data-ttu-id="1fd6b-676">**Count**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-676">**Count**</span></span>

<span data-ttu-id="1fd6b-677">如果您按一下 [ **篩選**]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![主要惡意程式碼報表檢視](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="1fd6b-679">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-679">URL threat protection report</span></span>

<span data-ttu-id="1fd6b-680">**URL 威脅防護報告** 只適用于 Office 365 的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="1fd6b-681">如需詳細資訊，請參閱 [URL 威脅防護報告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="1fd6b-682">使用者報告的訊息報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fd6b-683">為了讓 **使用者報告的訊息** 報告正確運作，必須為您的 Microsoft 365 環境 **開啟審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="1fd6b-684">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="1fd6b-685">如需詳細資訊，請參閱[開啟或關閉 Microsoft 365 審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="1fd6b-686">「 **使用者報告的訊息** 報告」顯示使用者已使用 [報告郵件增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)舉報為垃圾郵件、網路釣魚企圖或良好郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="1fd6b-687">若要在 Microsoft 365 Defender 入口網站中查看報告，請移至 **Reports** \> **email & 協同** \> **電子郵件 &** 共同作業報告。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="1fd6b-688">在 [ **電子郵件 &** 共同作業報告] 頁面上，找出 **使用者報告的訊息** ，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="1fd6b-689">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="1fd6b-690">若要移至 [Microsoft 365 Defender 入口網站中的系統管理提交](admin-submission.md)，按一下 [**移至提交**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![「電子郵件 & 共同作業報告」頁面上的使用者報告的訊息小工具](../../media/user-reported-messages-widget.png)

<span data-ttu-id="1fd6b-692">在 [ **使用者報告的郵件** ] 頁面上，您可以按一下 [ **篩選** ]，然後在出現的浮出控制項中，選取下列一或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="1fd6b-693">**報告日期**： **開始時間** 和 **結束時間**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="1fd6b-694">**報告者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-694">**Reported by**</span></span>
- <span data-ttu-id="1fd6b-695">**電子郵件主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-695">**Email subject**</span></span>
- <span data-ttu-id="1fd6b-696">**訊息報告識別碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-696">**Message reported ID**</span></span>
- <span data-ttu-id="1fd6b-697">**網路消息識別碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-697">**Network Message ID**</span></span>
- <span data-ttu-id="1fd6b-698">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-698">**Sender**</span></span>
- <span data-ttu-id="1fd6b-699">**報告原因**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-699">**Reported reason**</span></span>
  - <span data-ttu-id="1fd6b-700">**非垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-700">**Not junk**</span></span>
  - <span data-ttu-id="1fd6b-701">**網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-701">**Phish**</span></span>
  - <span data-ttu-id="1fd6b-702">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-702">**Spam**</span></span>
- <span data-ttu-id="1fd6b-703">**網路釣魚模擬**： **是** 或 **否**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="1fd6b-704">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="1fd6b-705">若要群組專案，請按一下 [ **群組** ]，然後從下拉式清單中選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="1fd6b-706">**無**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-706">**None**</span></span>
- <span data-ttu-id="1fd6b-707">**原因**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-707">**Reason**</span></span>
- <span data-ttu-id="1fd6b-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-708">**Sender**</span></span>
- <span data-ttu-id="1fd6b-709">**報告者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-709">**Reported by**</span></span>
- <span data-ttu-id="1fd6b-710">**重新掃描結果**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-710">**Rescan result**</span></span>
- <span data-ttu-id="1fd6b-711">**網路釣魚模擬模擬**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-711">**Phish simulation**</span></span>

![使用者報告的訊息報告](../../media/user-reported-messages-report.png)

<span data-ttu-id="1fd6b-713">在圖形下方的 [詳細資料] 表格中，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="1fd6b-714">**電子郵件主旨**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-714">**Email subject**</span></span>
- <span data-ttu-id="1fd6b-715">**報告者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-715">**Reported by**</span></span>
- <span data-ttu-id="1fd6b-716">**報告日期**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-716">**Date reported**</span></span>
- <span data-ttu-id="1fd6b-717">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-717">**Sender**</span></span>
- <span data-ttu-id="1fd6b-718">**報告原因**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-718">**Reported reason**</span></span>
- <span data-ttu-id="1fd6b-719">**重新掃描結果**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-719">**Rescan result**</span></span>
- <span data-ttu-id="1fd6b-720">**標記**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-720">**Tags**</span></span>

<span data-ttu-id="1fd6b-721">若要將郵件提交給 Microsoft 進行分析，請選取表格中的訊息項目，按一下 [ **提交給 Microsoft 進行分析** ]，然後從下拉式清單中選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="1fd6b-722">**報告清理**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-722">**Report clean**</span></span>
- <span data-ttu-id="1fd6b-723">**報告網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-723">**Report phishing**</span></span>
- <span data-ttu-id="1fd6b-724">**報告惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-724">**Report malware**</span></span>
- <span data-ttu-id="1fd6b-725">**報告垃圾郵件**'</span><span class="sxs-lookup"><span data-stu-id="1fd6b-725">**Report spam**'</span></span>
- <span data-ttu-id="1fd6b-726">Office 365) 的 **觸發調查** (Defender</span><span class="sxs-lookup"><span data-stu-id="1fd6b-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="1fd6b-727">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="1fd6b-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="1fd6b-728">為了查看和使用本文所述的報表，您必須是 Microsoft 365 Defender 入口網站中下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="1fd6b-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="1fd6b-729">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-729">**Organization Management**</span></span>
- <span data-ttu-id="1fd6b-730">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-730">**Security Administrator**</span></span>
- <span data-ttu-id="1fd6b-731">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-731">**Security Reader**</span></span>
- <span data-ttu-id="1fd6b-732">**全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="1fd6b-732">**Global Reader**</span></span>

<span data-ttu-id="1fd6b-733">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="1fd6b-734">**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1fd6b-735">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="1fd6b-736">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="1fd6b-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="1fd6b-737">如果您未看到報表中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="1fd6b-738">若要深入瞭解，請參閱 [防禦威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6b-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1fd6b-739">相關主題</span><span class="sxs-lookup"><span data-stu-id="1fd6b-739">Related topics</span></span>

[<span data-ttu-id="1fd6b-740">EOP 中的反垃圾郵件和反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="1fd6b-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="1fd6b-741">Microsoft 365 Defender 入口網站中的智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="1fd6b-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="1fd6b-742">在 Microsoft 365 Defender 入口網站中查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="1fd6b-743">View Office 365 的 Defender 報告</span><span class="sxs-lookup"><span data-stu-id="1fd6b-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
