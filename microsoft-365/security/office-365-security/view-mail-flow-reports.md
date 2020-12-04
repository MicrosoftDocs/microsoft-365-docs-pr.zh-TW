---
title: 在報告儀表板中查看郵件流程報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
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
ms.openlocfilehash: 701735374e03f2afb91323ceb4b3fbf30988bdcd
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572798"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="2004d-103">在安全性 & 規範中心的報表儀表板中查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="2004d-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2004d-104">除了安全性 & 合規性中心的 [郵件流程儀表板](mail-flow-insights-v2.md) 中所提供的郵件流程報告之外，「報告」儀表板還提供各種額外的郵件流程報告，可協助您監視 Microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="2004d-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="2004d-105">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以移至 [**報表**] 儀表板，在 [安全性 & 規範中心](https://office.protection.com)中查看這些報告 \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2004d-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="2004d-106">若要直接移至 [報告] 儀表板，請開啟] <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="2004d-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全性 & 規範中心內的報告儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="2004d-108">連接器報告</span><span class="sxs-lookup"><span data-stu-id="2004d-108">Connector report</span></span>

<span data-ttu-id="2004d-109">**連接器報告** 會顯示為您的組織設定之 [輸入和輸出連接器](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)上的郵件流程活動。</span><span class="sxs-lookup"><span data-stu-id="2004d-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="2004d-110">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **連接器報告**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="2004d-111">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="2004d-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![報表儀表板中的連接器報表小工具](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="2004d-113">連接器報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="2004d-113">Report view for the Connector report</span></span>

<span data-ttu-id="2004d-114">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="2004d-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="2004d-115">**依下列方式查看資料：郵件流程**：此圖顯示輸入的輸入和輸出郵件數目：</span><span class="sxs-lookup"><span data-stu-id="2004d-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="2004d-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="2004d-116">**Total**</span></span>
  - <span data-ttu-id="2004d-117">**從沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="2004d-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="2004d-118">**沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="2004d-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="2004d-119">您已設定的特定連接器。</span><span class="sxs-lookup"><span data-stu-id="2004d-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="2004d-120">若要隔離圖表中的資料，請使用 [顯示控制項的 **資料** ] 選取其中一個選項或 **所有郵件流程**。</span><span class="sxs-lookup"><span data-stu-id="2004d-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![在連接器報告中透過郵件流程查看資料](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="2004d-122">**資料查看依據： tls 使用狀況**：此圖顯示郵件流程的傳輸層安全性 (TLS) 版本用法的百分比。</span><span class="sxs-lookup"><span data-stu-id="2004d-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="2004d-123">若要隔離圖表中的資料，請使用 [顯示控制項的 **資料** ] 選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="2004d-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="2004d-124">**所有郵件流程**</span><span class="sxs-lookup"><span data-stu-id="2004d-124">**All mail flow**</span></span>
  - <span data-ttu-id="2004d-125">**從沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="2004d-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="2004d-126">**沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="2004d-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="2004d-127">您已設定的特定連接器。</span><span class="sxs-lookup"><span data-stu-id="2004d-127">A specific connector that you've configured.</span></span>

  ![依 TLS 使用量在連接器報告中查看資料](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="2004d-129">如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="2004d-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="2004d-130">連接器報表的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-130">Details table view for the Connector report</span></span>

<span data-ttu-id="2004d-131">如果您按一下報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2004d-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="2004d-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="2004d-132">**Date**</span></span>
- <span data-ttu-id="2004d-133">**連接器的方向和名稱**</span><span class="sxs-lookup"><span data-stu-id="2004d-133">**Connector direction and name**</span></span>
- <span data-ttu-id="2004d-134">**連接器類型**</span><span class="sxs-lookup"><span data-stu-id="2004d-134">**Connector type**</span></span>
- <span data-ttu-id="2004d-135">**強制 TLS？**：值 **True** 或 **False**。</span><span class="sxs-lookup"><span data-stu-id="2004d-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="2004d-136">**沒有 TLS** (百分比) </span><span class="sxs-lookup"><span data-stu-id="2004d-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="2004d-137">**TLS 1.0** (百分比) </span><span class="sxs-lookup"><span data-stu-id="2004d-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="2004d-138">**TLS 1.1** (百分比) </span><span class="sxs-lookup"><span data-stu-id="2004d-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="2004d-139">**TLS 1.2** (百分比) </span><span class="sxs-lookup"><span data-stu-id="2004d-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="2004d-140">**磁片** 區：郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2004d-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="2004d-141">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="2004d-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2004d-142">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="2004d-143">Exchange transport rule 報告</span><span class="sxs-lookup"><span data-stu-id="2004d-143">Exchange transport rule report</span></span>

<span data-ttu-id="2004d-144">**Exchange transport rule report** 會顯示郵件流程規則 (也稱為傳輸規則) 組織中內送和外寄郵件的效果。</span><span class="sxs-lookup"><span data-stu-id="2004d-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="2004d-145">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **Exchange Transport rule**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="2004d-146">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="2004d-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![報告儀表板中的 Exchange transport rule widget](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="2004d-148">Exchange transport rule 報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="2004d-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="2004d-149">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="2004d-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="2004d-150">**資料查看依據： Exchange 傳輸規則** \>**分解方式：方向**：此圖顯示受傳輸規則影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2004d-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="2004d-151">**資料查看依據： Exchange 傳輸規則** \>**分解方式：嚴重性**：此圖表顯示 **高嚴重性** 和 **中低嚴重性** 的數目，以及 **低嚴重性** 郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="2004d-152">您可以將嚴重性層級設定為規則 ([ **以嚴重性層級** 或 _SetAuditSeverity_) 審核此規則] 中的動作。</span><span class="sxs-lookup"><span data-stu-id="2004d-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="2004d-153">如需詳細資訊，請參閱 [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="2004d-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="2004d-154">**依下列方式查看資料： DLP Exchange transport rules** \>**分解方式：方向**：此圖顯示受資料遺失防護 (DLP) 傳輸規則所影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2004d-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="2004d-155">您可以選取下列選項來進一步精煉圖表：</span><span class="sxs-lookup"><span data-stu-id="2004d-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="2004d-156">**顯示資料：所有 DLP transport rules**</span><span class="sxs-lookup"><span data-stu-id="2004d-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="2004d-157">**顯示下列專案的資料：已遭破壞的使用者**</span><span class="sxs-lookup"><span data-stu-id="2004d-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="2004d-158">**顯示資料：偵測到的內容量下限美國愛國法案**</span><span class="sxs-lookup"><span data-stu-id="2004d-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="2004d-159">**依下列方式查看資料： DLP Exchange transport rules** \>**分解方式：方向**：此 View 顯示 **高嚴重性** 和 **中低嚴重性** 的數目，以及受 DLP transport rules 影響的 **低嚴重性** 郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="2004d-160">您可以選取下列選項來進一步精煉圖表：</span><span class="sxs-lookup"><span data-stu-id="2004d-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="2004d-161">**顯示資料：所有 DLP transport rules**</span><span class="sxs-lookup"><span data-stu-id="2004d-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="2004d-162">**顯示下列專案的資料：已遭破壞的使用者**</span><span class="sxs-lookup"><span data-stu-id="2004d-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="2004d-163">**顯示資料：偵測到的內容量下限美國愛國法案**</span><span class="sxs-lookup"><span data-stu-id="2004d-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="2004d-164">如果您按一下報表檢視中的 **篩選器** ，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="2004d-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="2004d-165">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2004d-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="2004d-166">方向值</span><span class="sxs-lookup"><span data-stu-id="2004d-166">Direction values</span></span>
- <span data-ttu-id="2004d-167">嚴重性值</span><span class="sxs-lookup"><span data-stu-id="2004d-167">Severity values</span></span>

![Exchange transport rule 報告中的報表檢視](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="2004d-169">Exchange transport rule 報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="2004d-170">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="2004d-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="2004d-171">**依下列方式查看資料： Exchange Transport rules**：</span><span class="sxs-lookup"><span data-stu-id="2004d-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="2004d-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="2004d-172">**Date**</span></span>
  - <span data-ttu-id="2004d-173">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="2004d-173">**Transport rule**</span></span>
  - <span data-ttu-id="2004d-174">**Subject**</span><span class="sxs-lookup"><span data-stu-id="2004d-174">**Subject**</span></span>
  - <span data-ttu-id="2004d-175">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="2004d-175">**Sender address**</span></span>
  - <span data-ttu-id="2004d-176">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="2004d-176">**Recipient address**</span></span>
  - <span data-ttu-id="2004d-177">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="2004d-177">**Severity**</span></span>
  - <span data-ttu-id="2004d-178">**Direction**</span><span class="sxs-lookup"><span data-stu-id="2004d-178">**Direction**</span></span>

- <span data-ttu-id="2004d-179">透過 **下列方式查看資料： DLP Exchange transport rules**：</span><span class="sxs-lookup"><span data-stu-id="2004d-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="2004d-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="2004d-180">**Date**</span></span>
  - <span data-ttu-id="2004d-181">**DLP 原則**</span><span class="sxs-lookup"><span data-stu-id="2004d-181">**DLP policy**</span></span>
  - <span data-ttu-id="2004d-182">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="2004d-182">**Transport rule**</span></span>
  - <span data-ttu-id="2004d-183">**Subject**</span><span class="sxs-lookup"><span data-stu-id="2004d-183">**Subject**</span></span>
  - <span data-ttu-id="2004d-184">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="2004d-184">**Sender address**</span></span>
  - <span data-ttu-id="2004d-185">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="2004d-185">**Recipient address**</span></span>
  - <span data-ttu-id="2004d-186">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="2004d-186">**Severity**</span></span>
  - <span data-ttu-id="2004d-187">**Direction**</span><span class="sxs-lookup"><span data-stu-id="2004d-187">**Direction**</span></span>

<span data-ttu-id="2004d-188">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="2004d-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2004d-189">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2004d-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="2004d-190">方向值</span><span class="sxs-lookup"><span data-stu-id="2004d-190">Direction values</span></span>
- <span data-ttu-id="2004d-191">嚴重性值</span><span class="sxs-lookup"><span data-stu-id="2004d-191">Severity values</span></span>

<span data-ttu-id="2004d-192">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="2004d-193">轉接報告</span><span class="sxs-lookup"><span data-stu-id="2004d-193">Forwarding report</span></span>

<span data-ttu-id="2004d-194">轉寄 **報告** 顯示組織自動轉寄給來自 Exchange Online 信箱的外部網域的郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="2004d-195">轉寄的郵件可能會造成安全性或規範風險，而且可能會指出已遭破壞的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2004d-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="2004d-196">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **轉接報告**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="2004d-197">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="2004d-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![在報表儀表板中轉發報表小工具](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="2004d-199">轉送報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="2004d-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="2004d-200">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="2004d-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2004d-201">**顯示資料：轉寄方法**：會顯示下列方法：</span><span class="sxs-lookup"><span data-stu-id="2004d-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="2004d-202">**傳輸規則**：也稱為「 [郵件流程規則](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」。</span><span class="sxs-lookup"><span data-stu-id="2004d-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="2004d-203">**信箱規則**：也稱為 [收件匣規則](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="2004d-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![轉寄報告中的轉接方法視圖](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="2004d-205">**顯示下列專案的資料：轉寄網域**：此視圖顯示是轉寄目的地的收件者網域。</span><span class="sxs-lookup"><span data-stu-id="2004d-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![轉寄報告中的轉移網域視圖](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="2004d-207">顯示下列專案的 **資料：轉寄站**：下列是顯示的轉寄站：</span><span class="sxs-lookup"><span data-stu-id="2004d-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="2004d-208">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="2004d-208">**Transport rule**</span></span>
  - <span data-ttu-id="2004d-209">包含轉寄收件匣規則的信箱。</span><span class="sxs-lookup"><span data-stu-id="2004d-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![轉寄報告中的轉送器視圖](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="2004d-211">如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="2004d-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="2004d-212">轉接報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="2004d-213">如果您按一下報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2004d-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="2004d-214">轉送 **器**：值 **傳輸規則** 或包含轉寄收件匣規則的信箱。</span><span class="sxs-lookup"><span data-stu-id="2004d-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="2004d-215">**轉送類型**：值 **信箱規則** 或 **傳輸規則**。</span><span class="sxs-lookup"><span data-stu-id="2004d-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="2004d-216">**收件者名稱**</span><span class="sxs-lookup"><span data-stu-id="2004d-216">**Recipient name**</span></span>
- <span data-ttu-id="2004d-217">**收件者網域**</span><span class="sxs-lookup"><span data-stu-id="2004d-217">**Recipient domain**</span></span>
- <span data-ttu-id="2004d-218">**詳細資料**：這是郵件流程規則的 GUID 值，或收件匣規則的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="2004d-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="2004d-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="2004d-219">**Count**</span></span>
- <span data-ttu-id="2004d-220">**第一個轉寄日期**</span><span class="sxs-lookup"><span data-stu-id="2004d-220">**First forward date**</span></span>

<span data-ttu-id="2004d-221">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="2004d-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2004d-222">若要回到 [報告] 視圖，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="2004d-223">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="2004d-223">Mailflow status report</span></span>

<span data-ttu-id="2004d-224">**郵件流程狀態報表** 類似于 [已傳送及已接收的電子郵件報告](#sent-and-received-email-report)，包含有關在 edge 上允許或封鎖之電子郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2004d-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="2004d-225">這是唯一包含 edge protection 資訊的報告，它會顯示在 Exchange Online Protection (EOP) 中，允許在評估之前封鎖多少封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="2004d-226">請務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="2004d-227">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報表**] \> **儀表板** ，然後選取 [ **郵件流程狀態報表**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="2004d-228">若要直接移至 [ **郵件流程] 狀態報表**，請開啟] <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="2004d-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![報表儀表板中的郵件流程狀態報表小工具](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="2004d-230">郵件流程狀態報表的類型視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="2004d-231">當您開啟報表時，預設會選取 [ **類型** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2004d-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="2004d-232">根據預設，此視圖包含的圖表和使用下列篩選器設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="2004d-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2004d-233">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="2004d-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="2004d-234">**方向**：</span><span class="sxs-lookup"><span data-stu-id="2004d-234">**Direction**:</span></span>

  - <span data-ttu-id="2004d-235">**入境**</span><span class="sxs-lookup"><span data-stu-id="2004d-235">**Inbound**</span></span>
  - <span data-ttu-id="2004d-236">**出境**</span><span class="sxs-lookup"><span data-stu-id="2004d-236">**Outbound**</span></span>
  - <span data-ttu-id="2004d-237">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="2004d-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="2004d-238">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與 **輸入** 和 **輸出**) 分開計數</span><span class="sxs-lookup"><span data-stu-id="2004d-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="2004d-239">**類型**：</span><span class="sxs-lookup"><span data-stu-id="2004d-239">**Type**:</span></span>

  - <span data-ttu-id="2004d-240">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-240">**Good mail**</span></span>
  - <span data-ttu-id="2004d-241">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="2004d-241">**Malware**</span></span>
  - <span data-ttu-id="2004d-242">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-242">**Spam**</span></span>
  - <span data-ttu-id="2004d-243">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="2004d-243">**Edge protection**</span></span>
  - <span data-ttu-id="2004d-244">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="2004d-244">**Rule messages**</span></span>
  - <span data-ttu-id="2004d-245">**網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-245">**Phishing email**</span></span>

<span data-ttu-id="2004d-246">圖表是依 **類型** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="2004d-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="2004d-247">您可以按一下 [ **篩選器** ] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="2004d-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="2004d-248">此資料表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2004d-248">The data table contains the following information:</span></span>

- <span data-ttu-id="2004d-249">**Direction**</span><span class="sxs-lookup"><span data-stu-id="2004d-249">**Direction**</span></span>
- <span data-ttu-id="2004d-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="2004d-250">**Type**</span></span>
- <span data-ttu-id="2004d-251">**24 小時**</span><span class="sxs-lookup"><span data-stu-id="2004d-251">**24 hours**</span></span>
- <span data-ttu-id="2004d-252">**3天**</span><span class="sxs-lookup"><span data-stu-id="2004d-252">**3 days**</span></span>
- <span data-ttu-id="2004d-253">**7 天**</span><span class="sxs-lookup"><span data-stu-id="2004d-253">**7 days**</span></span>
- <span data-ttu-id="2004d-254">**15 天**</span><span class="sxs-lookup"><span data-stu-id="2004d-254">**15 days**</span></span>
- <span data-ttu-id="2004d-255">**30 天**</span><span class="sxs-lookup"><span data-stu-id="2004d-255">**30 days**</span></span>

<span data-ttu-id="2004d-256">如果您按一下 **[選擇類別] 以取得詳細資料**，您可以選取下列值：</span><span class="sxs-lookup"><span data-stu-id="2004d-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="2004d-257">**網路釣魚電子郵件**：這項選擇會帶您前往「 [威脅防護狀態」報告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="2004d-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="2004d-258">**電子郵件中的惡意** 代碼：這項選擇會帶您前往 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="2004d-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="2004d-259">**垃圾郵件** 偵測：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="2004d-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="2004d-260">**Edge 封鎖的垃圾郵件**：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="2004d-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="2004d-261">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="2004d-261">**Export**:</span></span>

<span data-ttu-id="2004d-262">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="2004d-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="2004d-263">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="2004d-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="2004d-264">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="2004d-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2004d-265">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2004d-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="2004d-266">郵件流程狀態報表中的類型視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="2004d-267">郵件流程狀態報表的方向視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="2004d-268">如果您按一下 [ **方向** ] 索引標籤，則會使用 [ **類型** ] 視圖中的相同預設篩選器。</span><span class="sxs-lookup"><span data-stu-id="2004d-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="2004d-269">圖表是依 **方向** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="2004d-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="2004d-270">您可以按一下 [ **篩選器** ] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="2004d-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="2004d-271">會使用 [ **類型** ] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="2004d-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="2004d-272">資料表格包含的資訊來自 **類型** view。</span><span class="sxs-lookup"><span data-stu-id="2004d-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="2004d-273">[ **選擇類別** ] 如需詳細資料，可用的選取專案和行為與「 **類型** 」視圖相同。</span><span class="sxs-lookup"><span data-stu-id="2004d-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="2004d-274">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="2004d-274">**Export**:</span></span>

<span data-ttu-id="2004d-275">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="2004d-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="2004d-276">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="2004d-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="2004d-277">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="2004d-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2004d-278">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2004d-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="2004d-279">郵件流程狀態報表中的方向視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="2004d-280">郵件流程狀態報表的漏斗視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="2004d-281">**漏斗** 視圖顯示 Microsoft 的電子郵件威脅防護功能如何篩選組織中的內送和外寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="2004d-282">它提供有關電子郵件總數的詳細資訊，以及設定的威脅防護功能（包括 edge protection、反惡意程式碼、反網路釣魚、反垃圾郵件和反欺詐）對此計數的影響。</span><span class="sxs-lookup"><span data-stu-id="2004d-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="2004d-283">如果您按一下 [ **漏斗** ] 索引標籤，此 view 預設會包含圖表和使用下列篩選設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="2004d-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2004d-284">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="2004d-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="2004d-285">**方向**：</span><span class="sxs-lookup"><span data-stu-id="2004d-285">**Direction**:</span></span>

  - <span data-ttu-id="2004d-286">**入境**</span><span class="sxs-lookup"><span data-stu-id="2004d-286">**Inbound**</span></span>
  - <span data-ttu-id="2004d-287">**出境**</span><span class="sxs-lookup"><span data-stu-id="2004d-287">**Outbound**</span></span>
  - <span data-ttu-id="2004d-288">**組織內**：此計數是針對在租使用者中傳送的郵件進行計數;亦即，寄件者 abc@domain.com 會傳送給收件者 xyz@domain.com (與輸入和外寄) 分開計數。</span><span class="sxs-lookup"><span data-stu-id="2004d-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="2004d-289">匯總 view 和 data table view 允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="2004d-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="2004d-290">如果您按一下 [ **篩選**]，則可以篩選圖表和資料表格。</span><span class="sxs-lookup"><span data-stu-id="2004d-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="2004d-291">此圖顯示按下列方式組織的電子郵件計數：</span><span class="sxs-lookup"><span data-stu-id="2004d-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="2004d-292">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="2004d-292">**Total email**</span></span>
- <span data-ttu-id="2004d-293">**Edge protection 之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-293">**Email after edge protection**</span></span>
- <span data-ttu-id="2004d-294">**反惡意程式碼、檔信譽、檔案類型封鎖後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="2004d-295">**反網路釣魚、URL 信譽、品牌模擬、反欺騙功能之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="2004d-296">**反垃圾郵件、大宗郵件篩選後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="2004d-297">**使用者和網域模擬1之後的電子郵件**<sup></sup></span><span class="sxs-lookup"><span data-stu-id="2004d-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="2004d-298">檔案 **及 URL 引爆1後的電子郵件**<sup></sup></span><span class="sxs-lookup"><span data-stu-id="2004d-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="2004d-299">**在傳遞投遞後保護後，電子郵件偵測為良性 (URL 按一下時間保護)**</span><span class="sxs-lookup"><span data-stu-id="2004d-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="2004d-300">僅限<sup>1</sup> Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2004d-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="2004d-301">若要分別查看以 EOP 或 Defender for Office 365 篩選的電子郵件，請按一下 [圖表圖例] 中的值。</span><span class="sxs-lookup"><span data-stu-id="2004d-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="2004d-302">此資料表包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="2004d-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="2004d-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="2004d-303">**Date**</span></span>
- <span data-ttu-id="2004d-304">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="2004d-304">**Total email**</span></span>
- <span data-ttu-id="2004d-305">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="2004d-305">**Edge protection**</span></span>
- <span data-ttu-id="2004d-306">**反惡意程式碼、檔信譽、檔案類型封鎖**：</span><span class="sxs-lookup"><span data-stu-id="2004d-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="2004d-307">**檔信譽**：由於其他 Microsoft 客戶附加的檔案識別，因此篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="2004d-308">**檔案類型封鎖**：由於郵件中識別的惡意檔案類型，篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="2004d-309">**反網路釣魚、URL 信譽、品牌模仿、反欺騙**：</span><span class="sxs-lookup"><span data-stu-id="2004d-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="2004d-310">**URL 信譽**：由於其他 Microsoft 客戶的 url 身分識別而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="2004d-311">**品牌** 模擬：因為郵件是由眾所周知的品牌類比寄件者所過濾，所以會加以篩選。</span><span class="sxs-lookup"><span data-stu-id="2004d-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="2004d-312">**反欺騙**：因為郵件企圖哄騙收件者所屬的網域，或是郵件寄件者不會擁有的網域，所以篩選掉郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="2004d-313">**反垃圾郵件，大宗郵件篩選**：</span><span class="sxs-lookup"><span data-stu-id="2004d-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="2004d-314">**大宗郵件篩選**：郵件因嘗試將大宗郵件傳遞給其收件者而加以篩選。</span><span class="sxs-lookup"><span data-stu-id="2004d-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="2004d-315">**適用于 Office 365 (Defender 的使用者和網域模擬)**：</span><span class="sxs-lookup"><span data-stu-id="2004d-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="2004d-316">**使用者** 模擬：郵件因嘗試模擬使用者 (郵件寄件者) （已在反網路釣魚原則的類比保護設定中所定義）而篩選。</span><span class="sxs-lookup"><span data-stu-id="2004d-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="2004d-317">**網域** 模擬：郵件因嘗試模擬防網路釣魚原則之類比保護設定中所定義的網域而篩選出來。</span><span class="sxs-lookup"><span data-stu-id="2004d-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="2004d-318">檔案 **與 URL 引爆 (Office 365 的 Defender)**：</span><span class="sxs-lookup"><span data-stu-id="2004d-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="2004d-319">**檔引爆**：以安全附件原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="2004d-320">**URL 引爆**：以安全連結原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="2004d-321">**投遞後保護和 zap (ATP) 或 zap (EOP)**： zap 表示自動清除零小時。</span><span class="sxs-lookup"><span data-stu-id="2004d-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="2004d-322">如果您選取資料表格中的資料列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="2004d-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="2004d-323">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="2004d-323">**Export**:</span></span>

<span data-ttu-id="2004d-324">在 [**選項**] 下按一下 [**匯出**] 後，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="2004d-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="2004d-325">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="2004d-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="2004d-326">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="2004d-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="2004d-327">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="2004d-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="2004d-328">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2004d-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="2004d-329">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="2004d-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2004d-330">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2004d-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="2004d-331">郵件流程狀態報表中的漏斗圖視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="2004d-332">郵件流程狀態報表的技術視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="2004d-333">**技術視圖** 類似 **漏斗** 圖模式，可提供設定威脅防護功能的更細微細節。</span><span class="sxs-lookup"><span data-stu-id="2004d-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="2004d-334">您可以從圖表中查看郵件如何在威脅防護的不同階段進行分類。</span><span class="sxs-lookup"><span data-stu-id="2004d-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="2004d-335">如果您按一下 [ **技術視圖** ] 索引標籤，此視圖預設會包含圖表和使用下列篩選所設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="2004d-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2004d-336">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="2004d-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="2004d-337">**方向**：</span><span class="sxs-lookup"><span data-stu-id="2004d-337">**Direction**:</span></span>

  - <span data-ttu-id="2004d-338">**入境**</span><span class="sxs-lookup"><span data-stu-id="2004d-338">**Inbound**</span></span>
  - <span data-ttu-id="2004d-339">**出境**</span><span class="sxs-lookup"><span data-stu-id="2004d-339">**Outbound**</span></span>
  - <span data-ttu-id="2004d-340">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="2004d-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="2004d-341">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與輸入和輸出) 分開計數</span><span class="sxs-lookup"><span data-stu-id="2004d-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="2004d-342">匯總 view 和 data table view 允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="2004d-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="2004d-343">如果您按一下 [ **篩選**]，則可以篩選圖表和資料表格。</span><span class="sxs-lookup"><span data-stu-id="2004d-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="2004d-344">此圖顯示組織成下列類別的郵件：</span><span class="sxs-lookup"><span data-stu-id="2004d-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="2004d-345">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="2004d-345">**Total email**</span></span>
- <span data-ttu-id="2004d-346">**Edge 允許** 和 **edge 篩選**</span><span class="sxs-lookup"><span data-stu-id="2004d-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="2004d-347">**非惡意** 代碼、**安全附件偵測** <sup>\*</sup> 、**反惡意程式碼引擎偵測** 和 **規則訊息**</span><span class="sxs-lookup"><span data-stu-id="2004d-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="2004d-348">**不是網路釣魚詐騙**、 **DMARC 失敗**、 **模仿偵測**、 **欺騙偵測** 和 **網路釣魚偵測**</span><span class="sxs-lookup"><span data-stu-id="2004d-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="2004d-349">**沒有偵測 URL 引爆** 及 **url 引爆偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2004d-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="2004d-350">**非垃圾郵件** 和  **垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="2004d-351">**非惡意的電子郵件**、**安全連結偵測** <sup>\*</sup> 和 **ZAP**</span><span class="sxs-lookup"><span data-stu-id="2004d-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="2004d-352"><sup>\*</sup> 適用于 Office 的 Defender 365</span><span class="sxs-lookup"><span data-stu-id="2004d-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="2004d-353">當您將游標移到圖表中的某個類別時，您可以看到該類別中的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2004d-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="2004d-354">此資料表包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="2004d-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="2004d-355">**Date**</span><span class="sxs-lookup"><span data-stu-id="2004d-355">**Date**</span></span>
- <span data-ttu-id="2004d-356">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="2004d-356">**Total email**</span></span>
- <span data-ttu-id="2004d-357">**已篩選 Edge**</span><span class="sxs-lookup"><span data-stu-id="2004d-357">**Edge filtered**</span></span>
- <span data-ttu-id="2004d-358">**反惡意程式碼引擎、安全附件、已篩選的規則**。。</span><span class="sxs-lookup"><span data-stu-id="2004d-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="2004d-359">已 **篩選的規則**：由於郵件流程規則而篩選的郵件 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="2004d-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="2004d-360">**DMARC，類比，欺騙，網路釣魚篩選**：</span><span class="sxs-lookup"><span data-stu-id="2004d-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="2004d-361">**DMARC**：由於郵件失敗的 DMARC 驗證檢查而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="2004d-362">**URL 引爆偵測**</span><span class="sxs-lookup"><span data-stu-id="2004d-362">**URL detonation detection**</span></span>
- <span data-ttu-id="2004d-363">**已篩選的反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="2004d-364">**移除的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="2004d-364">**ZAP removed**</span></span>
- <span data-ttu-id="2004d-365">**安全連結偵測**</span><span class="sxs-lookup"><span data-stu-id="2004d-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="2004d-366">如果您選取資料表格中的資料列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="2004d-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="2004d-367">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="2004d-367">**Export**:</span></span>

<span data-ttu-id="2004d-368">在按一下 [ **匯出**] 的 [ **選項** ] 底下，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="2004d-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="2004d-369">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="2004d-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="2004d-370">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="2004d-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="2004d-371">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="2004d-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="2004d-372">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2004d-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="2004d-373">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="2004d-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2004d-374">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="2004d-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="2004d-375">郵件流程狀態報表中的技術視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="2004d-376">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="2004d-376">Sent and received email report</span></span>

<span data-ttu-id="2004d-377">「 **傳送及接收的電子郵件** 報告」是一個智慧報告，顯示傳入和傳出電子郵件的相關資訊，包括垃圾郵件偵測、惡意程式碼，以及識別為「良好」的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="2004d-378">此報告與 [郵件流程狀態報表](#mailflow-status-report) 之間的差異為：此報告不包含 edge protection 所封鎖之郵件的相關資料。請務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為一封郵件。</span><span class="sxs-lookup"><span data-stu-id="2004d-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="2004d-379">報表的匯總視圖和詳細資料檢視允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="2004d-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="2004d-380">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **已傳送及已接收的電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="2004d-381">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="2004d-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![在報告儀表板中傳送及接收的電子郵件小工具](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="2004d-383">傳送和接收的電子郵件報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="2004d-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="2004d-384">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="2004d-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2004d-385">**分解方式：類型**：圖表會顯示所有可用的類別：</span><span class="sxs-lookup"><span data-stu-id="2004d-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="2004d-386">**Total**</span><span class="sxs-lookup"><span data-stu-id="2004d-386">**Total**</span></span>
  - <span data-ttu-id="2004d-387">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="2004d-387">**Good mail**</span></span>
  - <span data-ttu-id="2004d-388">**惡意程式碼 (反惡意程式碼)** (EOP) </span><span class="sxs-lookup"><span data-stu-id="2004d-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="2004d-389">**垃圾郵件偵測**</span><span class="sxs-lookup"><span data-stu-id="2004d-389">**Spam detections**</span></span>
  - <span data-ttu-id="2004d-390">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="2004d-390">**Rule messages**</span></span>
  - <span data-ttu-id="2004d-391">Microsoft Defender for Office 365 的 **高級惡意** 代碼 () </span><span class="sxs-lookup"><span data-stu-id="2004d-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="2004d-392">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您就可以查看該天的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2004d-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![傳送和接收的電子郵件報告中的類型視圖](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="2004d-394">**分解方式：方向**：圖表會顯示 **總計**、 **輸入** 和 **輸出** 資料。</span><span class="sxs-lookup"><span data-stu-id="2004d-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="2004d-395">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您就可以查看該天的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2004d-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![傳送和接收的電子郵件報告中的方向視圖](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="2004d-397">**向下** \> 鑽取 **惡意軟體 (反惡意程式碼)**：這項選擇會帶您前往 [電子郵件報告中的惡意](view-email-security-reports.md#malware-detections-in-email-report)代碼偵測。</span><span class="sxs-lookup"><span data-stu-id="2004d-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="2004d-398">**向下** \> 鑽取 **垃圾郵件偵測)**：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="2004d-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="2004d-399">如果您按一下報表檢視中的 **篩選器** ，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="2004d-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2004d-400">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2004d-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="2004d-401">方向值</span><span class="sxs-lookup"><span data-stu-id="2004d-401">Direction values</span></span>
- <span data-ttu-id="2004d-402">類型值</span><span class="sxs-lookup"><span data-stu-id="2004d-402">Type values</span></span>

<span data-ttu-id="2004d-403">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="2004d-404">傳送及接收的電子郵件報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="2004d-405">如果您按一下 [按下列方式] 中的 [ **View details table** **：方向** ] 或 [ **分解方式** ]： [方向] 視圖，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2004d-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="2004d-406">**日期 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="2004d-406">**Date (UTC)**</span></span>
- <span data-ttu-id="2004d-407">**Type**</span><span class="sxs-lookup"><span data-stu-id="2004d-407">**Type**</span></span>
- <span data-ttu-id="2004d-408">**Direction**</span><span class="sxs-lookup"><span data-stu-id="2004d-408">**Direction**</span></span>
- <span data-ttu-id="2004d-409">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="2004d-409">**Message count**</span></span>

<span data-ttu-id="2004d-410">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="2004d-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2004d-411">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="2004d-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="2004d-412">方向值</span><span class="sxs-lookup"><span data-stu-id="2004d-412">Direction values</span></span>
- <span data-ttu-id="2004d-413">類型值</span><span class="sxs-lookup"><span data-stu-id="2004d-413">Type values</span></span>

<span data-ttu-id="2004d-414">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="2004d-415">主要寄件者和收件者報表</span><span class="sxs-lookup"><span data-stu-id="2004d-415">Top senders and recipients report</span></span>

<span data-ttu-id="2004d-416">[ **主要寄件者與收件** 者] 報告為圓形圖，顯示您的電子郵件寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="2004d-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="2004d-417">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **主要寄件者和收件** 者]。</span><span class="sxs-lookup"><span data-stu-id="2004d-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="2004d-418">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="2004d-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![報表儀表板中的主要寄件者和收件者小工具](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="2004d-420">主要寄件者和收件者報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="2004d-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="2004d-421">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="2004d-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2004d-422">**顯示 \> 主要郵件寄件者的資料**</span><span class="sxs-lookup"><span data-stu-id="2004d-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="2004d-423">**顯示 \> 主要郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="2004d-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="2004d-424">**顯示 \> 主要垃圾郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="2004d-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="2004d-425">**顯示資料 \> 主要惡意** 代碼收件者 (EOP) </span><span class="sxs-lookup"><span data-stu-id="2004d-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="2004d-426">**顯示主要惡意程式碼收件者的資料 \> (Defender For Office 365)**</span><span class="sxs-lookup"><span data-stu-id="2004d-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="2004d-427">圓形圖的組成會根據這些選取範圍變更。</span><span class="sxs-lookup"><span data-stu-id="2004d-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="2004d-428">當您將游標移到圓形圖中的楔形上方時，您可以看到所傳送或接收的郵件計數。</span><span class="sxs-lookup"><span data-stu-id="2004d-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="2004d-429">如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="2004d-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![在 [主要寄件者和收件者] 報告中的報表檢視中的圓形圖表](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="2004d-431">主要寄件者和收件者報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="2004d-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="2004d-432">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="2004d-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="2004d-433">**顯示 \> 主要郵件寄件者的資料**</span><span class="sxs-lookup"><span data-stu-id="2004d-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="2004d-434">**主要郵件寄件者**</span><span class="sxs-lookup"><span data-stu-id="2004d-434">**Top mail senders**</span></span>
  - <span data-ttu-id="2004d-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="2004d-435">**Count**</span></span>

- <span data-ttu-id="2004d-436">**顯示 \> 主要郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="2004d-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="2004d-437">**主要郵件收件者**</span><span class="sxs-lookup"><span data-stu-id="2004d-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="2004d-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="2004d-438">**Count**</span></span>

- <span data-ttu-id="2004d-439">**顯示 \> 主要垃圾郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="2004d-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="2004d-440">**主要垃圾郵件收件者**</span><span class="sxs-lookup"><span data-stu-id="2004d-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="2004d-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="2004d-441">**Count**</span></span>

- <span data-ttu-id="2004d-442">**顯示資料 \> 主要惡意** 代碼收件者 (EOP) </span><span class="sxs-lookup"><span data-stu-id="2004d-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="2004d-443">**主要惡意程式碼收件者**</span><span class="sxs-lookup"><span data-stu-id="2004d-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="2004d-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="2004d-444">**Count**</span></span>

- <span data-ttu-id="2004d-445">**顯示主要惡意程式碼收件者的資料 \> (Defender For Office 365)**</span><span class="sxs-lookup"><span data-stu-id="2004d-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="2004d-446">**Office 365 (Defender 的主要惡意程式碼收件者)**</span><span class="sxs-lookup"><span data-stu-id="2004d-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="2004d-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="2004d-447">**Count**</span></span>

<span data-ttu-id="2004d-448">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="2004d-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2004d-449">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="2004d-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="2004d-450">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="2004d-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="2004d-451">為了查看和使用本主題中所述的報表，您必須是安全性 & 合規性中心之一的下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="2004d-451">In order to view and use the reports described in this topic, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="2004d-452">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="2004d-452">**Organization Management**</span></span>
- <span data-ttu-id="2004d-453">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="2004d-453">**Security Administrator**</span></span>
- <span data-ttu-id="2004d-454">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="2004d-454">**Security Reader**</span></span>
- <span data-ttu-id="2004d-455">**全域讀取者**</span><span class="sxs-lookup"><span data-stu-id="2004d-455">**Global Reader**</span></span>

<span data-ttu-id="2004d-456">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2004d-456">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="2004d-457">**附注**：將使用者新增至 microsoft 365 系統管理中心的對應 Azure Active Directory 角色，可讓使用者具備安全性 & 合規性中心的許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="2004d-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2004d-458">如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="2004d-458">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2004d-459">相關主題</span><span class="sxs-lookup"><span data-stu-id="2004d-459">Related topics</span></span>

[<span data-ttu-id="2004d-460">安全性與合規性中心內的智慧型報表和深入解析</span><span class="sxs-lookup"><span data-stu-id="2004d-460">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="2004d-461">安全性與合規性中心內的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="2004d-461">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="2004d-462">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="2004d-462">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="2004d-463">查看 Microsoft Defender for Office 365 的報告</span><span class="sxs-lookup"><span data-stu-id="2004d-463">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
