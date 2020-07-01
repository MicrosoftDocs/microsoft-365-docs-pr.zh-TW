---
title: 在安全性 & 規範中心內，查看郵件流程報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 瞭解如何尋找及使用組織的郵件流程安全性報告。 郵件流程報告可在安全性 & 規範中心中取得。
ms.custom: ''
ms.openlocfilehash: 70c96bb4f43edb80f98fdc98aa173fed9e54e7d7
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937130"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="778c5-104">在安全性 & 規範中心內，查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="778c5-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="778c5-105">除了安全性 & 合規性中心中提供的[郵件流程洞察力](mail-flow-insights-v2.md)之外，也有許多郵件流程報告可協助您監視 Microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="778c5-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="778c5-106">如果您有[必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以移 <https://office.protection.com> 至 [**報告**] \> **儀表板**，在安全性 & 規範中心中查看這些報告。</span><span class="sxs-lookup"><span data-stu-id="778c5-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="778c5-107">若要直接移至 [報告] 儀表板，請開啟] <https://office.protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="778c5-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![安全性 & 規範中心內的報告儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="778c5-109">連接器報告</span><span class="sxs-lookup"><span data-stu-id="778c5-109">Connector report</span></span>

<span data-ttu-id="778c5-110">**連接器報告**會顯示為您的組織設定之[輸入和輸出連接器](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)上的郵件流程活動。</span><span class="sxs-lookup"><span data-stu-id="778c5-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="778c5-111">若要查看報告，請開啟[安全性 & 規範中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [**連接器報告**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="778c5-112">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="778c5-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![報表儀表板中的連接器報表小工具](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="778c5-114">連接器報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="778c5-114">Report view for the Connector report</span></span>

<span data-ttu-id="778c5-115">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="778c5-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="778c5-116">**依下列方式查看資料：郵件流程**：此圖顯示輸入的輸入和輸出郵件數目：</span><span class="sxs-lookup"><span data-stu-id="778c5-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="778c5-117">**Total**</span><span class="sxs-lookup"><span data-stu-id="778c5-117">**Total**</span></span>
  - <span data-ttu-id="778c5-118">**從沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="778c5-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="778c5-119">**沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="778c5-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="778c5-120">您已設定的特定連接器。</span><span class="sxs-lookup"><span data-stu-id="778c5-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="778c5-121">若要隔離圖表中的資料，請使用 [顯示控制項的**資料**] 選取其中一個選項或**所有郵件流程**。</span><span class="sxs-lookup"><span data-stu-id="778c5-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![在連接器報告中透過郵件流程查看資料](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="778c5-123">**資料查看依據： TLS 使用狀況**：此圖顯示郵件流程的傳輸層安全性（TLS）版本使用百分比。</span><span class="sxs-lookup"><span data-stu-id="778c5-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="778c5-124">若要隔離圖表中的資料，請使用 [顯示控制項的**資料**] 選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="778c5-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="778c5-125">**所有郵件流程**</span><span class="sxs-lookup"><span data-stu-id="778c5-125">**All mail flow**</span></span>
  - <span data-ttu-id="778c5-126">**從沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="778c5-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="778c5-127">**沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="778c5-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="778c5-128">您已設定的特定連接器。</span><span class="sxs-lookup"><span data-stu-id="778c5-128">A specific connector that you've configured.</span></span>

  ![依 TLS 使用量在連接器報告中查看資料](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="778c5-130">如果您按一下報表檢視中的 [**篩選器**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="778c5-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="778c5-131">連接器報表的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="778c5-131">Details table view for the Connector report</span></span>

<span data-ttu-id="778c5-132">如果您按一下報表檢視中的 [**查看詳細資料] 表格**，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="778c5-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="778c5-133">**Date**</span><span class="sxs-lookup"><span data-stu-id="778c5-133">**Date**</span></span>
- <span data-ttu-id="778c5-134">**連接器的方向和名稱**</span><span class="sxs-lookup"><span data-stu-id="778c5-134">**Connector direction and name**</span></span>
- <span data-ttu-id="778c5-135">**連接器類型**</span><span class="sxs-lookup"><span data-stu-id="778c5-135">**Connector type**</span></span>
- <span data-ttu-id="778c5-136">**強制 TLS？**：值**True**或**False**。</span><span class="sxs-lookup"><span data-stu-id="778c5-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="778c5-137">**無 TLS** （百分比）</span><span class="sxs-lookup"><span data-stu-id="778c5-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="778c5-138">**TLS 1.0** （百分比）</span><span class="sxs-lookup"><span data-stu-id="778c5-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="778c5-139">**TLS 1.1** （百分比）</span><span class="sxs-lookup"><span data-stu-id="778c5-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="778c5-140">**TLS 1.2** （百分比）</span><span class="sxs-lookup"><span data-stu-id="778c5-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="778c5-141">**磁片**區：郵件數目。</span><span class="sxs-lookup"><span data-stu-id="778c5-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="778c5-142">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="778c5-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="778c5-143">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="778c5-144">Exchange transport rule 報告</span><span class="sxs-lookup"><span data-stu-id="778c5-144">Exchange transport rule report</span></span>

<span data-ttu-id="778c5-145">**Exchange transport rule report**會顯示郵件流程規則（也稱為傳輸規則）對組織內送和外寄郵件的影響。</span><span class="sxs-lookup"><span data-stu-id="778c5-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="778c5-146">若要查看報告，請開啟[安全性 & 合規性中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [ **Exchange Transport rule**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="778c5-147">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="778c5-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![報告儀表板中的 Exchange transport rule widget](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="778c5-149">Exchange transport rule 報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="778c5-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="778c5-150">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="778c5-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="778c5-151">**資料查看依據： Exchange 傳輸規則** \>**分解方式：方向**：此圖顯示受傳輸規則影響的**輸入**和**輸出**郵件數目。</span><span class="sxs-lookup"><span data-stu-id="778c5-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="778c5-152">**資料查看依據： Exchange 傳輸規則** \>**分解方式：嚴重性**：此圖表顯示**高嚴重性**和**中低嚴重性**的數目，以及**低嚴重性**郵件。</span><span class="sxs-lookup"><span data-stu-id="778c5-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="778c5-153">您可以將嚴重性層級設定為規則中的動作（**以嚴重性層級**或_SetAuditSeverity_來審核此規則）。</span><span class="sxs-lookup"><span data-stu-id="778c5-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="778c5-154">如需詳細資訊，請參閱 [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="778c5-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="778c5-155">**依下列方式查看資料： DLP Exchange transport rules** \>**分解方式：方向**：此圖顯示受資料遺失防護（DLP）傳輸規則影響的**輸入**和**輸出**郵件數目。</span><span class="sxs-lookup"><span data-stu-id="778c5-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="778c5-156">您可以選取下列選項來進一步精煉圖表：</span><span class="sxs-lookup"><span data-stu-id="778c5-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="778c5-157">**顯示資料：所有 DLP transport rules**</span><span class="sxs-lookup"><span data-stu-id="778c5-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="778c5-158">**顯示下列專案的資料：已遭破壞的使用者**</span><span class="sxs-lookup"><span data-stu-id="778c5-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="778c5-159">**顯示資料：偵測到的內容量下限美國愛國法案**</span><span class="sxs-lookup"><span data-stu-id="778c5-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="778c5-160">**依下列方式查看資料： DLP Exchange transport rules** \>**分解方式：方向**：此 View 顯示**高嚴重性**和**中低嚴重性**的數目，以及受 DLP transport rules 影響的**低嚴重性**郵件。</span><span class="sxs-lookup"><span data-stu-id="778c5-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="778c5-161">您可以選取下列選項來進一步精煉圖表：</span><span class="sxs-lookup"><span data-stu-id="778c5-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="778c5-162">**顯示資料：所有 DLP transport rules**</span><span class="sxs-lookup"><span data-stu-id="778c5-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="778c5-163">**顯示下列專案的資料：已遭破壞的使用者**</span><span class="sxs-lookup"><span data-stu-id="778c5-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="778c5-164">**顯示資料：偵測到的內容量下限美國愛國法案**</span><span class="sxs-lookup"><span data-stu-id="778c5-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="778c5-165">如果您按一下報表檢視中的**篩選器**，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="778c5-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="778c5-166">**開始日期**和**結束日期**</span><span class="sxs-lookup"><span data-stu-id="778c5-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="778c5-167">方向值</span><span class="sxs-lookup"><span data-stu-id="778c5-167">Direction values</span></span>
- <span data-ttu-id="778c5-168">嚴重性值</span><span class="sxs-lookup"><span data-stu-id="778c5-168">Severity values</span></span>

![Exchange transport rule 報告中的報表檢視](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="778c5-170">Exchange transport rule 報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="778c5-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="778c5-171">如果您按一下 [**查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="778c5-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="778c5-172">**依下列方式查看資料： Exchange Transport rules**：</span><span class="sxs-lookup"><span data-stu-id="778c5-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="778c5-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="778c5-173">**Date**</span></span>
  - <span data-ttu-id="778c5-174">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="778c5-174">**Transport rule**</span></span>
  - <span data-ttu-id="778c5-175">**主旨**</span><span class="sxs-lookup"><span data-stu-id="778c5-175">**Subject**</span></span>
  - <span data-ttu-id="778c5-176">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="778c5-176">**Sender address**</span></span>
  - <span data-ttu-id="778c5-177">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="778c5-177">**Recipient address**</span></span>
  - <span data-ttu-id="778c5-178">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="778c5-178">**Severity**</span></span>
  - <span data-ttu-id="778c5-179">**方向**</span><span class="sxs-lookup"><span data-stu-id="778c5-179">**Direction**</span></span>

- <span data-ttu-id="778c5-180">透過**下列方式查看資料： DLP Exchange transport rules**：</span><span class="sxs-lookup"><span data-stu-id="778c5-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="778c5-181">**Date**</span><span class="sxs-lookup"><span data-stu-id="778c5-181">**Date**</span></span>
  - <span data-ttu-id="778c5-182">**DLP 原則**</span><span class="sxs-lookup"><span data-stu-id="778c5-182">**DLP policy**</span></span>
  - <span data-ttu-id="778c5-183">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="778c5-183">**Transport rule**</span></span>
  - <span data-ttu-id="778c5-184">**主旨**</span><span class="sxs-lookup"><span data-stu-id="778c5-184">**Subject**</span></span>
  - <span data-ttu-id="778c5-185">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="778c5-185">**Sender address**</span></span>
  - <span data-ttu-id="778c5-186">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="778c5-186">**Recipient address**</span></span>
  - <span data-ttu-id="778c5-187">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="778c5-187">**Severity**</span></span>
  - <span data-ttu-id="778c5-188">**方向**</span><span class="sxs-lookup"><span data-stu-id="778c5-188">**Direction**</span></span>

<span data-ttu-id="778c5-189">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="778c5-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="778c5-190">**開始日期**和**結束日期**</span><span class="sxs-lookup"><span data-stu-id="778c5-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="778c5-191">方向值</span><span class="sxs-lookup"><span data-stu-id="778c5-191">Direction values</span></span>
- <span data-ttu-id="778c5-192">嚴重性值</span><span class="sxs-lookup"><span data-stu-id="778c5-192">Severity values</span></span>

<span data-ttu-id="778c5-193">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="778c5-194">轉接報告</span><span class="sxs-lookup"><span data-stu-id="778c5-194">Forwarding report</span></span>

<span data-ttu-id="778c5-195">轉寄**報告**顯示組織自動轉寄給來自 Exchange Online 信箱的外部網域的郵件。</span><span class="sxs-lookup"><span data-stu-id="778c5-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="778c5-196">轉寄的郵件可能會造成安全性或規範風險，而且可能會指出已遭破壞的帳戶。</span><span class="sxs-lookup"><span data-stu-id="778c5-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="778c5-197">若要查看報告，請開啟[安全性 & 規範中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [**轉接報告**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="778c5-198">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="778c5-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![在報表儀表板中轉發報表小工具](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="778c5-200">轉送報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="778c5-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="778c5-201">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="778c5-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="778c5-202">**顯示資料：轉寄方法**：會顯示下列方法：</span><span class="sxs-lookup"><span data-stu-id="778c5-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="778c5-203">**傳輸規則**：也稱為「[郵件流程規則](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」。</span><span class="sxs-lookup"><span data-stu-id="778c5-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="778c5-204">**信箱規則**：也稱為[收件匣規則](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="778c5-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![轉寄報告中的轉接方法視圖](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="778c5-206">**顯示下列專案的資料：轉寄網域**：此視圖顯示是轉寄目的地的收件者網域。</span><span class="sxs-lookup"><span data-stu-id="778c5-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![轉寄報告中的轉移網域視圖](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="778c5-208">顯示下列專案的**資料：轉寄站**：下列是顯示的轉寄站：</span><span class="sxs-lookup"><span data-stu-id="778c5-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="778c5-209">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="778c5-209">**Transport rule**</span></span>
  - <span data-ttu-id="778c5-210">包含轉寄收件匣規則的信箱。</span><span class="sxs-lookup"><span data-stu-id="778c5-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![轉寄報告中的轉送器視圖](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="778c5-212">如果您按一下報表檢視中的 [**篩選器**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="778c5-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="778c5-213">轉接報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="778c5-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="778c5-214">如果您按一下報表檢視中的 [**查看詳細資料] 表格**，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="778c5-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="778c5-215">轉送**器**：值**傳輸規則**或包含轉寄收件匣規則的信箱。</span><span class="sxs-lookup"><span data-stu-id="778c5-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="778c5-216">**轉送類型**：值**信箱規則**或**傳輸規則**。</span><span class="sxs-lookup"><span data-stu-id="778c5-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="778c5-217">**收件者名稱**</span><span class="sxs-lookup"><span data-stu-id="778c5-217">**Recipient name**</span></span>
- <span data-ttu-id="778c5-218">**收件者網域**</span><span class="sxs-lookup"><span data-stu-id="778c5-218">**Recipient domain**</span></span>
- <span data-ttu-id="778c5-219">**詳細資料**：這是郵件流程規則的 GUID 值，或收件匣規則的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="778c5-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="778c5-220">**Count**</span><span class="sxs-lookup"><span data-stu-id="778c5-220">**Count**</span></span>
- <span data-ttu-id="778c5-221">**第一個轉寄日期**</span><span class="sxs-lookup"><span data-stu-id="778c5-221">**First forward date**</span></span>

<span data-ttu-id="778c5-222">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="778c5-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="778c5-223">若要回到 [報告] 視圖，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="778c5-224">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="778c5-224">Mailflow status report</span></span>

<span data-ttu-id="778c5-225">**郵件流程狀態報表**類似于[已傳送及已接收的電子郵件報告](#sent-and-received-email-report)，包含有關在 edge 上允許或封鎖之電子郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="778c5-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="778c5-226">這是唯一包含 edge protection 資訊的報告，它會顯示 Exchange Online Protection （EOP）允許服務進行評估之前封鎖的電子郵件數量。</span><span class="sxs-lookup"><span data-stu-id="778c5-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="778c5-227">若要查看報告，請開啟[安全性 & 合規性中心](https://protection.office.com)，移至 [**報表**] \> **儀表板**，然後選取 [**郵件流程狀態報表**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="778c5-228">若要直接移至 [**郵件流程] 狀態報表**，請開啟] <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="778c5-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![報表儀表板中的郵件流程狀態報表小工具](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="778c5-230">郵件流程狀態報表的類型視圖</span><span class="sxs-lookup"><span data-stu-id="778c5-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="778c5-231">當您開啟報表時，預設會選取 [**類型**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="778c5-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="778c5-232">根據預設，此視圖包含的圖表和使用下列篩選器設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="778c5-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="778c5-233">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="778c5-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="778c5-234">**方向**：</span><span class="sxs-lookup"><span data-stu-id="778c5-234">**Direction**:</span></span>

  - <span data-ttu-id="778c5-235">**入境**</span><span class="sxs-lookup"><span data-stu-id="778c5-235">**Inbound**</span></span>
  - <span data-ttu-id="778c5-236">**出境**</span><span class="sxs-lookup"><span data-stu-id="778c5-236">**Outbound**</span></span>
  - <span data-ttu-id="778c5-237">**組織內**（與**輸入**和**輸出**分開計數）</span><span class="sxs-lookup"><span data-stu-id="778c5-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="778c5-238">**類型**：</span><span class="sxs-lookup"><span data-stu-id="778c5-238">**Type**:</span></span>

  - <span data-ttu-id="778c5-239">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="778c5-239">**Good mail**</span></span>
  - <span data-ttu-id="778c5-240">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="778c5-240">**Malware**</span></span>
  - <span data-ttu-id="778c5-241">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="778c5-241">**Spam**</span></span>
  - <span data-ttu-id="778c5-242">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="778c5-242">**Edge protection**</span></span>
  - <span data-ttu-id="778c5-243">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="778c5-243">**Rule messages**</span></span>
  - <span data-ttu-id="778c5-244">**網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="778c5-244">**Phishing email**</span></span>

<span data-ttu-id="778c5-245">圖表是依**類型**值進行組織。</span><span class="sxs-lookup"><span data-stu-id="778c5-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="778c5-246">您可以按一下 [**篩選器**] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="778c5-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="778c5-247">此資料表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="778c5-247">The data table contains the following information:</span></span>

- <span data-ttu-id="778c5-248">**方向**</span><span class="sxs-lookup"><span data-stu-id="778c5-248">**Direction**</span></span>
- <span data-ttu-id="778c5-249">**類型**</span><span class="sxs-lookup"><span data-stu-id="778c5-249">**Type**</span></span>
- <span data-ttu-id="778c5-250">**24 小時**</span><span class="sxs-lookup"><span data-stu-id="778c5-250">**24 hours**</span></span>
- <span data-ttu-id="778c5-251">**3天**</span><span class="sxs-lookup"><span data-stu-id="778c5-251">**3 days**</span></span>
- <span data-ttu-id="778c5-252">**7 天**</span><span class="sxs-lookup"><span data-stu-id="778c5-252">**7 days**</span></span>
- <span data-ttu-id="778c5-253">**15 天**</span><span class="sxs-lookup"><span data-stu-id="778c5-253">**15 days**</span></span>
- <span data-ttu-id="778c5-254">**30 天**</span><span class="sxs-lookup"><span data-stu-id="778c5-254">**30 days**</span></span>

<span data-ttu-id="778c5-255">如果您按一下 **[選擇類別] 以取得詳細資料**，您可以選取下列值：</span><span class="sxs-lookup"><span data-stu-id="778c5-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="778c5-256">**網路釣魚電子郵件**：這項選擇會帶您前往「[威脅防護狀態」報告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="778c5-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="778c5-257">**電子郵件中的惡意**代碼：這項選擇會帶您前往[威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="778c5-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="778c5-258">**垃圾郵件**偵測：這項選擇會帶您前往[垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="778c5-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="778c5-259">**Edge 封鎖的垃圾郵件**：這項選擇會帶您前往[垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="778c5-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="778c5-260">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="778c5-260">**Export**:</span></span>

<span data-ttu-id="778c5-261">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="778c5-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="778c5-262">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="778c5-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="778c5-263">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="778c5-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="778c5-264">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="778c5-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="778c5-265">郵件流程狀態報表中的類型視圖</span><span class="sxs-lookup"><span data-stu-id="778c5-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="778c5-266">郵件流程狀態報表的方向視圖</span><span class="sxs-lookup"><span data-stu-id="778c5-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="778c5-267">如果您按一下 [**方向**] 索引標籤，則會使用 [**類型**] 視圖中的相同預設篩選器。</span><span class="sxs-lookup"><span data-stu-id="778c5-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="778c5-268">圖表是依**方向**值進行組織。</span><span class="sxs-lookup"><span data-stu-id="778c5-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="778c5-269">您可以按一下 [**篩選器**] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="778c5-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="778c5-270">會使用 [**類型**] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="778c5-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="778c5-271">資料表格包含的資訊來自**類型**view。</span><span class="sxs-lookup"><span data-stu-id="778c5-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="778c5-272">[**選擇類別**] 如需詳細資料，可用的選取專案和行為與「**類型**」視圖相同。</span><span class="sxs-lookup"><span data-stu-id="778c5-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="778c5-273">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="778c5-273">**Export**:</span></span>

<span data-ttu-id="778c5-274">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="778c5-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="778c5-275">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="778c5-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="778c5-276">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="778c5-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="778c5-277">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="778c5-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="778c5-278">郵件流程狀態報表中的方向視圖</span><span class="sxs-lookup"><span data-stu-id="778c5-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="778c5-279">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="778c5-279">Sent and received email report</span></span>

<span data-ttu-id="778c5-280">「**傳送及接收的電子郵件**報告」是一個智慧報告，顯示傳入和傳出電子郵件的相關資訊，包括垃圾郵件偵測、惡意程式碼，以及識別為「良好」的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="778c5-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="778c5-281">此報告與[郵件流程狀態報表](#mailflow-status-report)之間的差異為：此報告不包含 edge protection 所封鎖之郵件的相關資料。</span><span class="sxs-lookup"><span data-stu-id="778c5-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="778c5-282">報表的匯總視圖和詳細資料檢視允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="778c5-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="778c5-283">若要查看報告，請開啟[安全性 & 規範中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [**已傳送及已接收的電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="778c5-284">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="778c5-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![在報告儀表板中傳送及接收的電子郵件小工具](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="778c5-286">傳送和接收的電子郵件報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="778c5-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="778c5-287">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="778c5-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="778c5-288">**分解方式：類型**：圖表會顯示所有可用的類別：</span><span class="sxs-lookup"><span data-stu-id="778c5-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="778c5-289">**Total**</span><span class="sxs-lookup"><span data-stu-id="778c5-289">**Total**</span></span>
  - <span data-ttu-id="778c5-290">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="778c5-290">**Good mail**</span></span>
  - <span data-ttu-id="778c5-291">**惡意程式碼（反惡意程式碼）** （EOP）</span><span class="sxs-lookup"><span data-stu-id="778c5-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="778c5-292">**垃圾郵件偵測**</span><span class="sxs-lookup"><span data-stu-id="778c5-292">**Spam detections**</span></span>
  - <span data-ttu-id="778c5-293">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="778c5-293">**Rule messages**</span></span>
  - <span data-ttu-id="778c5-294">**高級惡意**代碼（OFFICE 365 ATP）</span><span class="sxs-lookup"><span data-stu-id="778c5-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="778c5-295">當您將游標移到圖表中的某一天（資料點）時，您可以查看該天的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="778c5-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![傳送和接收的電子郵件報告中的類型視圖](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="778c5-297">**分解方式：方向**：圖表會顯示**總計**、**輸入**和**輸出**資料。</span><span class="sxs-lookup"><span data-stu-id="778c5-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="778c5-298">當您將游標移到圖表中的某一天（資料點）時，您可以查看該天的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="778c5-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![傳送和接收的電子郵件報告中的方向視圖](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="778c5-300">**向下** \> 鑽取**惡意程式碼（反惡意程式碼）**：這項選擇會帶您前往[電子郵件報告中的惡意程式碼偵測](view-email-security-reports.md#malware-detection-in-email-report)。</span><span class="sxs-lookup"><span data-stu-id="778c5-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detection in email report](view-email-security-reports.md#malware-detection-in-email-report).</span></span>

- <span data-ttu-id="778c5-301">**向下** \> 鑽取**垃圾郵件**偵測：這項選擇會帶您前往[垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="778c5-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="778c5-302">如果您按一下報表檢視中的**篩選器**，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="778c5-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="778c5-303">**開始日期**和**結束日期**</span><span class="sxs-lookup"><span data-stu-id="778c5-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="778c5-304">方向值</span><span class="sxs-lookup"><span data-stu-id="778c5-304">Direction values</span></span>
- <span data-ttu-id="778c5-305">類型值</span><span class="sxs-lookup"><span data-stu-id="778c5-305">Type values</span></span>

<span data-ttu-id="778c5-306">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="778c5-307">傳送及接收的電子郵件報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="778c5-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="778c5-308">如果您按一下 [按下列方式] 中的 [ **View details table** **：方向**] 或 [**分解方式**]： [方向] 視圖，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="778c5-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="778c5-309">**Date （UTC）**</span><span class="sxs-lookup"><span data-stu-id="778c5-309">**Date (UTC)**</span></span>
- <span data-ttu-id="778c5-310">**類型**</span><span class="sxs-lookup"><span data-stu-id="778c5-310">**Type**</span></span>
- <span data-ttu-id="778c5-311">**方向**</span><span class="sxs-lookup"><span data-stu-id="778c5-311">**Direction**</span></span>
- <span data-ttu-id="778c5-312">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="778c5-312">**Message count**</span></span>

<span data-ttu-id="778c5-313">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="778c5-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="778c5-314">**開始日期**和**結束日期**</span><span class="sxs-lookup"><span data-stu-id="778c5-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="778c5-315">方向值</span><span class="sxs-lookup"><span data-stu-id="778c5-315">Direction values</span></span>
- <span data-ttu-id="778c5-316">類型值</span><span class="sxs-lookup"><span data-stu-id="778c5-316">Type values</span></span>

<span data-ttu-id="778c5-317">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="778c5-318">主要寄件者和收件者報表</span><span class="sxs-lookup"><span data-stu-id="778c5-318">Top senders and recipients report</span></span>

<span data-ttu-id="778c5-319">[**主要寄件者與收件**者] 報告為圓形圖，顯示您的電子郵件寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="778c5-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="778c5-320">若要查看報告，請開啟[安全性 & 規範中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [**主要寄件者和收件**者]。</span><span class="sxs-lookup"><span data-stu-id="778c5-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="778c5-321">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="778c5-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![報表儀表板中的主要寄件者和收件者小工具](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="778c5-323">主要寄件者和收件者報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="778c5-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="778c5-324">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="778c5-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="778c5-325">**顯示 \> 主要郵件寄件者的資料**</span><span class="sxs-lookup"><span data-stu-id="778c5-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="778c5-326">**顯示 \> 主要郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="778c5-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="778c5-327">**顯示 \> 主要垃圾郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="778c5-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="778c5-328">**顯示資料 \>主要惡意**代碼收件者（EOP）</span><span class="sxs-lookup"><span data-stu-id="778c5-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="778c5-329">**顯示資料 \>主要惡意**代碼收件者（atp）（Office 365 atp）</span><span class="sxs-lookup"><span data-stu-id="778c5-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="778c5-330">圓形圖的組成會根據這些選取範圍變更。</span><span class="sxs-lookup"><span data-stu-id="778c5-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="778c5-331">當您將游標移到圓形圖中的楔形上方時，您可以看到所傳送或接收的郵件計數。</span><span class="sxs-lookup"><span data-stu-id="778c5-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="778c5-332">如果您按一下報表檢視中的 [**篩選器**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="778c5-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![在 [主要寄件者和收件者] 報告中的報表檢視中的圓形圖表](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="778c5-334">主要寄件者和收件者報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="778c5-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="778c5-335">如果您按一下 [**查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="778c5-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="778c5-336">**顯示 \> 主要郵件寄件者的資料**</span><span class="sxs-lookup"><span data-stu-id="778c5-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="778c5-337">**主要郵件寄件者**</span><span class="sxs-lookup"><span data-stu-id="778c5-337">**Top mail senders**</span></span>
  - <span data-ttu-id="778c5-338">**Count**</span><span class="sxs-lookup"><span data-stu-id="778c5-338">**Count**</span></span>

- <span data-ttu-id="778c5-339">**顯示 \> 主要郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="778c5-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="778c5-340">**主要郵件收件者**</span><span class="sxs-lookup"><span data-stu-id="778c5-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="778c5-341">**Count**</span><span class="sxs-lookup"><span data-stu-id="778c5-341">**Count**</span></span>

- <span data-ttu-id="778c5-342">**顯示 \> 主要垃圾郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="778c5-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="778c5-343">**主要垃圾郵件收件者**</span><span class="sxs-lookup"><span data-stu-id="778c5-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="778c5-344">**Count**</span><span class="sxs-lookup"><span data-stu-id="778c5-344">**Count**</span></span>

- <span data-ttu-id="778c5-345">**顯示資料 \>主要惡意**代碼收件者（EOP）</span><span class="sxs-lookup"><span data-stu-id="778c5-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="778c5-346">**主要惡意程式碼收件者**</span><span class="sxs-lookup"><span data-stu-id="778c5-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="778c5-347">**Count**</span><span class="sxs-lookup"><span data-stu-id="778c5-347">**Count**</span></span>

- <span data-ttu-id="778c5-348">**顯示資料 \>主要惡意**代碼收件者（atp）（Office 365 atp）</span><span class="sxs-lookup"><span data-stu-id="778c5-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="778c5-349">**主要惡意程式碼收件者（ATP）**</span><span class="sxs-lookup"><span data-stu-id="778c5-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="778c5-350">**Count**</span><span class="sxs-lookup"><span data-stu-id="778c5-350">**Count**</span></span>

<span data-ttu-id="778c5-351">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="778c5-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="778c5-352">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="778c5-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="778c5-353">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="778c5-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="778c5-354">若要查看和使用報表，您必須是在安全性 & 規範中心**和**Exchange Online 中所指定角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="778c5-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="778c5-355">在安全性 & 規範中心，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="778c5-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="778c5-356">-組織管理</span><span class="sxs-lookup"><span data-stu-id="778c5-356">-Organization Management</span></span>

  <span data-ttu-id="778c5-357">-安全性管理員（您也可以在[Azure Active Directory 系統管理中心](https://aad.portal.azure.com)進行此作業-安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="778c5-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="778c5-358">如需詳細資訊，請參閱[安全性與合規性中心中的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="778c5-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="778c5-359">在 Exchange Online 中，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="778c5-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="778c5-360">-組織管理</span><span class="sxs-lookup"><span data-stu-id="778c5-360">-Organization Management</span></span>

  <span data-ttu-id="778c5-361">-僅供查看的組織管理</span><span class="sxs-lookup"><span data-stu-id="778c5-361">-View-only Organization Management</span></span>

  <span data-ttu-id="778c5-362">-View-Only 收件者</span><span class="sxs-lookup"><span data-stu-id="778c5-362">-View-Only Recipients</span></span>

  <span data-ttu-id="778c5-363">-合規性管理</span><span class="sxs-lookup"><span data-stu-id="778c5-363">-Compliance Management</span></span>

<span data-ttu-id="778c5-364">如需詳細資訊，請參閱 exchange online 中的[許可權](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)和[exchange Online 中的管理角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="778c5-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="778c5-365">相關主題</span><span class="sxs-lookup"><span data-stu-id="778c5-365">Related topics</span></span>

[<span data-ttu-id="778c5-366">安全性與合規性中心內的智慧型報表和深入解析</span><span class="sxs-lookup"><span data-stu-id="778c5-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="778c5-367">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="778c5-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
