---
title: 在報告儀表板中查看郵件流程報告
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
description: 系統管理員可以深入瞭解安全性 & 合規性中心的「報告」儀表板中提供的郵件流程報告。
ms.custom: ''
ms.openlocfilehash: 69b2c3383862860b4616d95c2a6a1bb3a525d842
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578015"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="1901a-103">在安全性 & 規範中心的報表儀表板中查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="1901a-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="1901a-104">除了安全性 & 合規性中心的[郵件流程儀表板](mail-flow-insights-v2.md)中所提供的郵件流程報告之外，「報告」儀表板還提供各種額外的郵件流程報告，可協助您監視 Microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="1901a-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="1901a-105">如果您有[必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以移至 [**報表**] 儀表板，在[安全性 & 規範中心](https://office.protection.com)中查看這些報告 \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="1901a-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="1901a-106">若要直接移至 [報告] 儀表板，請開啟] <https://office.protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="1901a-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![安全性 & 規範中心內的報告儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="1901a-108">連接器報告</span><span class="sxs-lookup"><span data-stu-id="1901a-108">Connector report</span></span>

<span data-ttu-id="1901a-109">**連接器報告**會顯示為您的組織設定之[輸入和輸出連接器](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)上的郵件流程活動。</span><span class="sxs-lookup"><span data-stu-id="1901a-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="1901a-110">若要查看報告，請開啟[安全性 & 規範中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [**連接器報告**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="1901a-111">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="1901a-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![報表儀表板中的連接器報表小工具](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="1901a-113">連接器報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="1901a-113">Report view for the Connector report</span></span>

<span data-ttu-id="1901a-114">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="1901a-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="1901a-115">**依下列方式查看資料：郵件流程**：此圖顯示輸入的輸入和輸出郵件數目：</span><span class="sxs-lookup"><span data-stu-id="1901a-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="1901a-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="1901a-116">**Total**</span></span>
  - <span data-ttu-id="1901a-117">**從沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="1901a-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="1901a-118">**沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="1901a-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="1901a-119">您已設定的特定連接器。</span><span class="sxs-lookup"><span data-stu-id="1901a-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="1901a-120">若要隔離圖表中的資料，請使用 [顯示控制項的**資料**] 選取其中一個選項或**所有郵件流程**。</span><span class="sxs-lookup"><span data-stu-id="1901a-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![在連接器報告中透過郵件流程查看資料](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="1901a-122">**資料查看依據： tls 使用狀況**：此圖顯示郵件流程的傳輸層安全性 (TLS) 版本用法的百分比。</span><span class="sxs-lookup"><span data-stu-id="1901a-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="1901a-123">若要隔離圖表中的資料，請使用 [顯示控制項的**資料**] 選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="1901a-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="1901a-124">**所有郵件流程**</span><span class="sxs-lookup"><span data-stu-id="1901a-124">**All mail flow**</span></span>
  - <span data-ttu-id="1901a-125">**從沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="1901a-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="1901a-126">**沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="1901a-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="1901a-127">您已設定的特定連接器。</span><span class="sxs-lookup"><span data-stu-id="1901a-127">A specific connector that you've configured.</span></span>

  ![依 TLS 使用量在連接器報告中查看資料](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="1901a-129">如果您按一下報表檢視中的 [**篩選器**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1901a-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="1901a-130">連接器報表的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="1901a-130">Details table view for the Connector report</span></span>

<span data-ttu-id="1901a-131">如果您按一下報表檢視中的 [**查看詳細資料] 表格**，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1901a-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="1901a-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="1901a-132">**Date**</span></span>
- <span data-ttu-id="1901a-133">**連接器的方向和名稱**</span><span class="sxs-lookup"><span data-stu-id="1901a-133">**Connector direction and name**</span></span>
- <span data-ttu-id="1901a-134">**連接器類型**</span><span class="sxs-lookup"><span data-stu-id="1901a-134">**Connector type**</span></span>
- <span data-ttu-id="1901a-135">**強制 TLS？**：值**True**或**False**。</span><span class="sxs-lookup"><span data-stu-id="1901a-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="1901a-136">**沒有 TLS** (百分比) </span><span class="sxs-lookup"><span data-stu-id="1901a-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="1901a-137">**TLS 1.0** (百分比) </span><span class="sxs-lookup"><span data-stu-id="1901a-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="1901a-138">**TLS 1.1** (百分比) </span><span class="sxs-lookup"><span data-stu-id="1901a-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="1901a-139">**TLS 1.2** (百分比) </span><span class="sxs-lookup"><span data-stu-id="1901a-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="1901a-140">**磁片**區：郵件數目。</span><span class="sxs-lookup"><span data-stu-id="1901a-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="1901a-141">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1901a-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="1901a-142">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="1901a-143">Exchange transport rule 報告</span><span class="sxs-lookup"><span data-stu-id="1901a-143">Exchange transport rule report</span></span>

<span data-ttu-id="1901a-144">**Exchange transport rule report**會顯示郵件流程規則 (也稱為傳輸規則) 組織中內送和外寄郵件的效果。</span><span class="sxs-lookup"><span data-stu-id="1901a-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="1901a-145">若要查看報告，請開啟[安全性 & 合規性中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [ **Exchange Transport rule**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="1901a-146">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="1901a-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![報告儀表板中的 Exchange transport rule widget](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="1901a-148">Exchange transport rule 報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="1901a-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="1901a-149">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="1901a-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="1901a-150">**資料查看依據： Exchange 傳輸規則** \>**分解方式：方向**：此圖顯示受傳輸規則影響的**輸入**和**輸出**郵件數目。</span><span class="sxs-lookup"><span data-stu-id="1901a-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="1901a-151">**資料查看依據： Exchange 傳輸規則** \>**分解方式：嚴重性**：此圖表顯示**高嚴重性**和**中低嚴重性**的數目，以及**低嚴重性**郵件。</span><span class="sxs-lookup"><span data-stu-id="1901a-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="1901a-152">您可以將嚴重性層級設定為規則 ([**以嚴重性層級**或_SetAuditSeverity_) 審核此規則] 中的動作。</span><span class="sxs-lookup"><span data-stu-id="1901a-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="1901a-153">如需詳細資訊，請參閱 [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="1901a-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="1901a-154">**依下列方式查看資料： DLP Exchange transport rules** \>**分解方式：方向**：此圖顯示受資料遺失防護 (DLP) 傳輸規則所影響的**輸入**和**輸出**郵件數目。</span><span class="sxs-lookup"><span data-stu-id="1901a-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="1901a-155">您可以選取下列選項來進一步精煉圖表：</span><span class="sxs-lookup"><span data-stu-id="1901a-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="1901a-156">**顯示資料：所有 DLP transport rules**</span><span class="sxs-lookup"><span data-stu-id="1901a-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="1901a-157">**顯示下列專案的資料：已遭破壞的使用者**</span><span class="sxs-lookup"><span data-stu-id="1901a-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="1901a-158">**顯示資料：偵測到的內容量下限美國愛國法案**</span><span class="sxs-lookup"><span data-stu-id="1901a-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="1901a-159">**依下列方式查看資料： DLP Exchange transport rules** \>**分解方式：方向**：此 View 顯示**高嚴重性**和**中低嚴重性**的數目，以及受 DLP transport rules 影響的**低嚴重性**郵件。</span><span class="sxs-lookup"><span data-stu-id="1901a-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="1901a-160">您可以選取下列選項來進一步精煉圖表：</span><span class="sxs-lookup"><span data-stu-id="1901a-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="1901a-161">**顯示資料：所有 DLP transport rules**</span><span class="sxs-lookup"><span data-stu-id="1901a-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="1901a-162">**顯示下列專案的資料：已遭破壞的使用者**</span><span class="sxs-lookup"><span data-stu-id="1901a-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="1901a-163">**顯示資料：偵測到的內容量下限美國愛國法案**</span><span class="sxs-lookup"><span data-stu-id="1901a-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="1901a-164">如果您按一下報表檢視中的**篩選器**，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="1901a-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="1901a-165">**開始日期**和**結束日期**</span><span class="sxs-lookup"><span data-stu-id="1901a-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="1901a-166">方向值</span><span class="sxs-lookup"><span data-stu-id="1901a-166">Direction values</span></span>
- <span data-ttu-id="1901a-167">嚴重性值</span><span class="sxs-lookup"><span data-stu-id="1901a-167">Severity values</span></span>

![Exchange transport rule 報告中的報表檢視](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="1901a-169">Exchange transport rule 報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="1901a-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="1901a-170">如果您按一下 [**查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="1901a-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1901a-171">**依下列方式查看資料： Exchange Transport rules**：</span><span class="sxs-lookup"><span data-stu-id="1901a-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="1901a-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="1901a-172">**Date**</span></span>
  - <span data-ttu-id="1901a-173">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="1901a-173">**Transport rule**</span></span>
  - <span data-ttu-id="1901a-174">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1901a-174">**Subject**</span></span>
  - <span data-ttu-id="1901a-175">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="1901a-175">**Sender address**</span></span>
  - <span data-ttu-id="1901a-176">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="1901a-176">**Recipient address**</span></span>
  - <span data-ttu-id="1901a-177">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="1901a-177">**Severity**</span></span>
  - <span data-ttu-id="1901a-178">**方向**</span><span class="sxs-lookup"><span data-stu-id="1901a-178">**Direction**</span></span>

- <span data-ttu-id="1901a-179">透過**下列方式查看資料： DLP Exchange transport rules**：</span><span class="sxs-lookup"><span data-stu-id="1901a-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="1901a-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="1901a-180">**Date**</span></span>
  - <span data-ttu-id="1901a-181">**DLP 原則**</span><span class="sxs-lookup"><span data-stu-id="1901a-181">**DLP policy**</span></span>
  - <span data-ttu-id="1901a-182">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="1901a-182">**Transport rule**</span></span>
  - <span data-ttu-id="1901a-183">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1901a-183">**Subject**</span></span>
  - <span data-ttu-id="1901a-184">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="1901a-184">**Sender address**</span></span>
  - <span data-ttu-id="1901a-185">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="1901a-185">**Recipient address**</span></span>
  - <span data-ttu-id="1901a-186">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="1901a-186">**Severity**</span></span>
  - <span data-ttu-id="1901a-187">**方向**</span><span class="sxs-lookup"><span data-stu-id="1901a-187">**Direction**</span></span>

<span data-ttu-id="1901a-188">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="1901a-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1901a-189">**開始日期**和**結束日期**</span><span class="sxs-lookup"><span data-stu-id="1901a-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="1901a-190">方向值</span><span class="sxs-lookup"><span data-stu-id="1901a-190">Direction values</span></span>
- <span data-ttu-id="1901a-191">嚴重性值</span><span class="sxs-lookup"><span data-stu-id="1901a-191">Severity values</span></span>

<span data-ttu-id="1901a-192">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="1901a-193">轉接報告</span><span class="sxs-lookup"><span data-stu-id="1901a-193">Forwarding report</span></span>

<span data-ttu-id="1901a-194">轉寄**報告**顯示組織自動轉寄給來自 Exchange Online 信箱的外部網域的郵件。</span><span class="sxs-lookup"><span data-stu-id="1901a-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="1901a-195">轉寄的郵件可能會造成安全性或規範風險，而且可能會指出已遭破壞的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1901a-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="1901a-196">若要查看報告，請開啟[安全性 & 規範中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [**轉接報告**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="1901a-197">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="1901a-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![在報表儀表板中轉發報表小工具](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="1901a-199">轉送報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="1901a-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="1901a-200">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="1901a-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="1901a-201">**顯示資料：轉寄方法**：會顯示下列方法：</span><span class="sxs-lookup"><span data-stu-id="1901a-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="1901a-202">**傳輸規則**：也稱為「[郵件流程規則](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」。</span><span class="sxs-lookup"><span data-stu-id="1901a-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="1901a-203">**信箱規則**：也稱為[收件匣規則](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="1901a-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![轉寄報告中的轉接方法視圖](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="1901a-205">**顯示下列專案的資料：轉寄網域**：此視圖顯示是轉寄目的地的收件者網域。</span><span class="sxs-lookup"><span data-stu-id="1901a-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![轉寄報告中的轉移網域視圖](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="1901a-207">顯示下列專案的**資料：轉寄站**：下列是顯示的轉寄站：</span><span class="sxs-lookup"><span data-stu-id="1901a-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="1901a-208">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="1901a-208">**Transport rule**</span></span>
  - <span data-ttu-id="1901a-209">包含轉寄收件匣規則的信箱。</span><span class="sxs-lookup"><span data-stu-id="1901a-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![轉寄報告中的轉送器視圖](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="1901a-211">如果您按一下報表檢視中的 [**篩選器**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1901a-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="1901a-212">轉接報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="1901a-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="1901a-213">如果您按一下報表檢視中的 [**查看詳細資料] 表格**，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1901a-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="1901a-214">轉送**器**：值**傳輸規則**或包含轉寄收件匣規則的信箱。</span><span class="sxs-lookup"><span data-stu-id="1901a-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="1901a-215">**轉送類型**：值**信箱規則**或**傳輸規則**。</span><span class="sxs-lookup"><span data-stu-id="1901a-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="1901a-216">**收件者名稱**</span><span class="sxs-lookup"><span data-stu-id="1901a-216">**Recipient name**</span></span>
- <span data-ttu-id="1901a-217">**收件者網域**</span><span class="sxs-lookup"><span data-stu-id="1901a-217">**Recipient domain**</span></span>
- <span data-ttu-id="1901a-218">**詳細資料**：這是郵件流程規則的 GUID 值，或收件匣規則的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="1901a-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="1901a-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="1901a-219">**Count**</span></span>
- <span data-ttu-id="1901a-220">**第一個轉寄日期**</span><span class="sxs-lookup"><span data-stu-id="1901a-220">**First forward date**</span></span>

<span data-ttu-id="1901a-221">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1901a-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="1901a-222">若要回到 [報告] 視圖，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="1901a-223">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="1901a-223">Mailflow status report</span></span>

<span data-ttu-id="1901a-224">**郵件流程狀態報表**類似于[已傳送及已接收的電子郵件報告](#sent-and-received-email-report)，包含有關在 edge 上允許或封鎖之電子郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1901a-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="1901a-225">這是唯一包含 edge protection 資訊的報告，它會顯示在 Exchange Online Protection (EOP) 中，允許在評估之前封鎖多少封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1901a-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="1901a-226">若要查看報告，請開啟[安全性 & 合規性中心](https://protection.office.com)，移至 [**報表**] \> **儀表板**，然後選取 [**郵件流程狀態報表**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-226">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="1901a-227">若要直接移至 [**郵件流程] 狀態報表**，請開啟] <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="1901a-227">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![報表儀表板中的郵件流程狀態報表小工具](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="1901a-229">郵件流程狀態報表的類型視圖</span><span class="sxs-lookup"><span data-stu-id="1901a-229">Type view for the Mailflow status report</span></span>

<span data-ttu-id="1901a-230">當您開啟報表時，預設會選取 [**類型**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1901a-230">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="1901a-231">根據預設，此視圖包含的圖表和使用下列篩選器設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="1901a-231">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="1901a-232">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="1901a-232">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="1901a-233">**方向**：</span><span class="sxs-lookup"><span data-stu-id="1901a-233">**Direction**:</span></span>

  - <span data-ttu-id="1901a-234">**入境**</span><span class="sxs-lookup"><span data-stu-id="1901a-234">**Inbound**</span></span>
  - <span data-ttu-id="1901a-235">**出境**</span><span class="sxs-lookup"><span data-stu-id="1901a-235">**Outbound**</span></span>
  - <span data-ttu-id="1901a-236">**組織內** (會與**輸入**和**輸出**) 分開計數</span><span class="sxs-lookup"><span data-stu-id="1901a-236">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="1901a-237">**類型**：</span><span class="sxs-lookup"><span data-stu-id="1901a-237">**Type**:</span></span>

  - <span data-ttu-id="1901a-238">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="1901a-238">**Good mail**</span></span>
  - <span data-ttu-id="1901a-239">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="1901a-239">**Malware**</span></span>
  - <span data-ttu-id="1901a-240">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1901a-240">**Spam**</span></span>
  - <span data-ttu-id="1901a-241">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="1901a-241">**Edge protection**</span></span>
  - <span data-ttu-id="1901a-242">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="1901a-242">**Rule messages**</span></span>
  - <span data-ttu-id="1901a-243">**網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="1901a-243">**Phishing email**</span></span>

<span data-ttu-id="1901a-244">圖表是依**類型**值進行組織。</span><span class="sxs-lookup"><span data-stu-id="1901a-244">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="1901a-245">您可以按一下 [**篩選器**] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="1901a-245">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="1901a-246">此資料表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1901a-246">The data table contains the following information:</span></span>

- <span data-ttu-id="1901a-247">**方向**</span><span class="sxs-lookup"><span data-stu-id="1901a-247">**Direction**</span></span>
- <span data-ttu-id="1901a-248">**Type**</span><span class="sxs-lookup"><span data-stu-id="1901a-248">**Type**</span></span>
- <span data-ttu-id="1901a-249">**24 小時**</span><span class="sxs-lookup"><span data-stu-id="1901a-249">**24 hours**</span></span>
- <span data-ttu-id="1901a-250">**3天**</span><span class="sxs-lookup"><span data-stu-id="1901a-250">**3 days**</span></span>
- <span data-ttu-id="1901a-251">**7 天**</span><span class="sxs-lookup"><span data-stu-id="1901a-251">**7 days**</span></span>
- <span data-ttu-id="1901a-252">**15 天**</span><span class="sxs-lookup"><span data-stu-id="1901a-252">**15 days**</span></span>
- <span data-ttu-id="1901a-253">**30 天**</span><span class="sxs-lookup"><span data-stu-id="1901a-253">**30 days**</span></span>

<span data-ttu-id="1901a-254">如果您按一下 **[選擇類別] 以取得詳細資料**，您可以選取下列值：</span><span class="sxs-lookup"><span data-stu-id="1901a-254">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="1901a-255">**網路釣魚電子郵件**：這項選擇會帶您前往「[威脅防護狀態」報告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="1901a-255">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="1901a-256">**電子郵件中的惡意**代碼：這項選擇會帶您前往[威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="1901a-256">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="1901a-257">**垃圾郵件**偵測：這項選擇會帶您前往[垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="1901a-257">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="1901a-258">**Edge 封鎖的垃圾郵件**：這項選擇會帶您前往[垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="1901a-258">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="1901a-259">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="1901a-259">**Export**:</span></span>

<span data-ttu-id="1901a-260">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="1901a-260">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="1901a-261">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="1901a-261">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="1901a-262">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="1901a-262">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="1901a-263">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1901a-263">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="1901a-264">郵件流程狀態報表中的類型視圖</span><span class="sxs-lookup"><span data-stu-id="1901a-264">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="1901a-265">郵件流程狀態報表的方向視圖</span><span class="sxs-lookup"><span data-stu-id="1901a-265">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="1901a-266">如果您按一下 [**方向**] 索引標籤，則會使用 [**類型**] 視圖中的相同預設篩選器。</span><span class="sxs-lookup"><span data-stu-id="1901a-266">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="1901a-267">圖表是依**方向**值進行組織。</span><span class="sxs-lookup"><span data-stu-id="1901a-267">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="1901a-268">您可以按一下 [**篩選器**] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="1901a-268">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="1901a-269">會使用 [**類型**] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="1901a-269">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="1901a-270">資料表格包含的資訊來自**類型**view。</span><span class="sxs-lookup"><span data-stu-id="1901a-270">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="1901a-271">[**選擇類別**] 如需詳細資料，可用的選取專案和行為與「**類型**」視圖相同。</span><span class="sxs-lookup"><span data-stu-id="1901a-271">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="1901a-272">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="1901a-272">**Export**:</span></span>

<span data-ttu-id="1901a-273">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="1901a-273">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="1901a-274">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="1901a-274">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="1901a-275">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="1901a-275">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="1901a-276">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1901a-276">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="1901a-277">郵件流程狀態報表中的方向視圖</span><span class="sxs-lookup"><span data-stu-id="1901a-277">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="1901a-278">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="1901a-278">Sent and received email report</span></span>

<span data-ttu-id="1901a-279">「**傳送及接收的電子郵件**報告」是一個智慧報告，顯示傳入和傳出電子郵件的相關資訊，包括垃圾郵件偵測、惡意程式碼，以及識別為「良好」的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1901a-279">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="1901a-280">此報告與[郵件流程狀態報表](#mailflow-status-report)之間的差異為：此報告不包含 edge protection 所封鎖之郵件的相關資料。</span><span class="sxs-lookup"><span data-stu-id="1901a-280">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="1901a-281">報表的匯總視圖和詳細資料檢視允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="1901a-281">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="1901a-282">若要查看報告，請開啟[安全性 & 規範中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [**已傳送及已接收的電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-282">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="1901a-283">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="1901a-283">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![在報告儀表板中傳送及接收的電子郵件小工具](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="1901a-285">傳送和接收的電子郵件報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="1901a-285">Report view for the Sent and received email report</span></span>

<span data-ttu-id="1901a-286">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="1901a-286">The following charts are available in the report view:</span></span>

- <span data-ttu-id="1901a-287">**分解方式：類型**：圖表會顯示所有可用的類別：</span><span class="sxs-lookup"><span data-stu-id="1901a-287">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="1901a-288">**Total**</span><span class="sxs-lookup"><span data-stu-id="1901a-288">**Total**</span></span>
  - <span data-ttu-id="1901a-289">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="1901a-289">**Good mail**</span></span>
  - <span data-ttu-id="1901a-290">\*\*惡意程式碼 (反惡意程式碼) \*\* (EOP) </span><span class="sxs-lookup"><span data-stu-id="1901a-290">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="1901a-291">**垃圾郵件偵測**</span><span class="sxs-lookup"><span data-stu-id="1901a-291">**Spam detections**</span></span>
  - <span data-ttu-id="1901a-292">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="1901a-292">**Rule messages**</span></span>
  - <span data-ttu-id="1901a-293"> (Office 365 ATP) 的**高級惡意**代碼</span><span class="sxs-lookup"><span data-stu-id="1901a-293">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="1901a-294">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您就可以查看該天的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1901a-294">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![傳送和接收的電子郵件報告中的類型視圖](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="1901a-296">**分解方式：方向**：圖表會顯示**總計**、**輸入**和**輸出**資料。</span><span class="sxs-lookup"><span data-stu-id="1901a-296">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="1901a-297">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您就可以查看該天的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1901a-297">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![傳送和接收的電子郵件報告中的方向視圖](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="1901a-299">**向下** \> 鑽取\*\*惡意軟體 (反惡意程式碼) \*\*：這項選擇會帶您前往[電子郵件報告中的惡意](view-email-security-reports.md#malware-detections-in-email-report)代碼偵測。</span><span class="sxs-lookup"><span data-stu-id="1901a-299">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="1901a-300">**向下** \> 鑽取\*\*垃圾郵件偵測) \*\*：這項選擇會帶您前往[垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="1901a-300">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="1901a-301">如果您按一下報表檢視中的**篩選器**，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="1901a-301">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1901a-302">**開始日期**和**結束日期**</span><span class="sxs-lookup"><span data-stu-id="1901a-302">**Start date** and **End date**</span></span>
- <span data-ttu-id="1901a-303">方向值</span><span class="sxs-lookup"><span data-stu-id="1901a-303">Direction values</span></span>
- <span data-ttu-id="1901a-304">類型值</span><span class="sxs-lookup"><span data-stu-id="1901a-304">Type values</span></span>

<span data-ttu-id="1901a-305">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-305">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="1901a-306">傳送及接收的電子郵件報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="1901a-306">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="1901a-307">如果您按一下 [按下列方式] 中的 [ **View details table** **：方向**] 或 [**分解方式**]： [方向] 視圖，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1901a-307">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="1901a-308">\*\*日期 (UTC) \*\*</span><span class="sxs-lookup"><span data-stu-id="1901a-308">**Date (UTC)**</span></span>
- <span data-ttu-id="1901a-309">**Type**</span><span class="sxs-lookup"><span data-stu-id="1901a-309">**Type**</span></span>
- <span data-ttu-id="1901a-310">**方向**</span><span class="sxs-lookup"><span data-stu-id="1901a-310">**Direction**</span></span>
- <span data-ttu-id="1901a-311">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="1901a-311">**Message count**</span></span>

<span data-ttu-id="1901a-312">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="1901a-312">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1901a-313">**開始日期**和**結束日期**</span><span class="sxs-lookup"><span data-stu-id="1901a-313">**Start date** and **End date**</span></span>
- <span data-ttu-id="1901a-314">方向值</span><span class="sxs-lookup"><span data-stu-id="1901a-314">Direction values</span></span>
- <span data-ttu-id="1901a-315">類型值</span><span class="sxs-lookup"><span data-stu-id="1901a-315">Type values</span></span>

<span data-ttu-id="1901a-316">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-316">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="1901a-317">主要寄件者和收件者報表</span><span class="sxs-lookup"><span data-stu-id="1901a-317">Top senders and recipients report</span></span>

<span data-ttu-id="1901a-318">[**主要寄件者與收件**者] 報告為圓形圖，顯示您的電子郵件寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="1901a-318">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="1901a-319">若要查看報告，請開啟[安全性 & 規範中心](https://protection.office.com)，移至 [**報告**] \> **儀表板**，然後選取 [**主要寄件者和收件**者]。</span><span class="sxs-lookup"><span data-stu-id="1901a-319">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="1901a-320">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="1901a-320">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![報表儀表板中的主要寄件者和收件者小工具](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="1901a-322">主要寄件者和收件者報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="1901a-322">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="1901a-323">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="1901a-323">The following charts are available in the report view:</span></span>

- <span data-ttu-id="1901a-324">**顯示 \> 主要郵件寄件者的資料**</span><span class="sxs-lookup"><span data-stu-id="1901a-324">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="1901a-325">**顯示 \> 主要郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="1901a-325">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="1901a-326">**顯示 \> 主要垃圾郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="1901a-326">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="1901a-327">**顯示資料 \>主要惡意**代碼收件者 (EOP) </span><span class="sxs-lookup"><span data-stu-id="1901a-327">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="1901a-328">**顯示資料 \>主要惡意**代碼收件者 (atp)  (Office 365 ATP) </span><span class="sxs-lookup"><span data-stu-id="1901a-328">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="1901a-329">圓形圖的組成會根據這些選取範圍變更。</span><span class="sxs-lookup"><span data-stu-id="1901a-329">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="1901a-330">當您將游標移到圓形圖中的楔形上方時，您可以看到所傳送或接收的郵件計數。</span><span class="sxs-lookup"><span data-stu-id="1901a-330">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="1901a-331">如果您按一下報表檢視中的 [**篩選器**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1901a-331">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![在 [主要寄件者和收件者] 報告中的報表檢視中的圓形圖表](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="1901a-333">主要寄件者和收件者報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="1901a-333">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="1901a-334">如果您按一下 [**查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="1901a-334">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1901a-335">**顯示 \> 主要郵件寄件者的資料**</span><span class="sxs-lookup"><span data-stu-id="1901a-335">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="1901a-336">**主要郵件寄件者**</span><span class="sxs-lookup"><span data-stu-id="1901a-336">**Top mail senders**</span></span>
  - <span data-ttu-id="1901a-337">**Count**</span><span class="sxs-lookup"><span data-stu-id="1901a-337">**Count**</span></span>

- <span data-ttu-id="1901a-338">**顯示 \> 主要郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="1901a-338">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="1901a-339">**主要郵件收件者**</span><span class="sxs-lookup"><span data-stu-id="1901a-339">**Top mail recipients**</span></span>
  - <span data-ttu-id="1901a-340">**Count**</span><span class="sxs-lookup"><span data-stu-id="1901a-340">**Count**</span></span>

- <span data-ttu-id="1901a-341">**顯示 \> 主要垃圾郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="1901a-341">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="1901a-342">**主要垃圾郵件收件者**</span><span class="sxs-lookup"><span data-stu-id="1901a-342">**Top spam recipients**</span></span>
  - <span data-ttu-id="1901a-343">**Count**</span><span class="sxs-lookup"><span data-stu-id="1901a-343">**Count**</span></span>

- <span data-ttu-id="1901a-344">**顯示資料 \>主要惡意**代碼收件者 (EOP) </span><span class="sxs-lookup"><span data-stu-id="1901a-344">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="1901a-345">**主要惡意程式碼收件者**</span><span class="sxs-lookup"><span data-stu-id="1901a-345">**Top malware recipients**</span></span>
  - <span data-ttu-id="1901a-346">**Count**</span><span class="sxs-lookup"><span data-stu-id="1901a-346">**Count**</span></span>

- <span data-ttu-id="1901a-347">**顯示資料 \>主要惡意**代碼收件者 (atp)  (Office 365 ATP) </span><span class="sxs-lookup"><span data-stu-id="1901a-347">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="1901a-348">\*\*主要惡意程式碼收件者 (ATP) \*\*</span><span class="sxs-lookup"><span data-stu-id="1901a-348">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="1901a-349">**Count**</span><span class="sxs-lookup"><span data-stu-id="1901a-349">**Count**</span></span>

<span data-ttu-id="1901a-350">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1901a-350">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="1901a-351">若要回到報表檢視，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="1901a-351">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="1901a-352">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="1901a-352">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="1901a-353">若要查看和使用報表，您必須是在安全性 & 規範中心**和**Exchange Online 中所指定角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1901a-353">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="1901a-354">在安全性 & 規範中心，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="1901a-354">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="1901a-355">-組織管理-安全性管理員 (您也可以在[Azure Active Directory 系統管理中心](https://aad.portal.azure.com)進行此作業-安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="1901a-355">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="1901a-356">如需詳細資訊，請參閱[安全性與合規性中心中的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="1901a-356">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="1901a-357">在 Exchange Online 中，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="1901a-357">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="1901a-358">-組織管理-僅限查看組織管理-View-Only 收件者-合規性管理</span><span class="sxs-lookup"><span data-stu-id="1901a-358">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="1901a-359">如需詳細資訊，請參閱 exchange online 中的[許可權](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)和[exchange Online 中的管理角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="1901a-359">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1901a-360">相關主題</span><span class="sxs-lookup"><span data-stu-id="1901a-360">Related topics</span></span>

[<span data-ttu-id="1901a-361">安全性與合規性中心內的智慧型報表和深入解析</span><span class="sxs-lookup"><span data-stu-id="1901a-361">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="1901a-362">安全性與合規性中心內的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="1901a-362">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="1901a-363">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="1901a-363">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="1901a-364">檢視 Office 365 進階威脅防護的報告</span><span class="sxs-lookup"><span data-stu-id="1901a-364">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
