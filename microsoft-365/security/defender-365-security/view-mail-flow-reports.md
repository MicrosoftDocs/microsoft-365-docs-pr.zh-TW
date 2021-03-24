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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以深入瞭解安全性 & 合規性中心的「報告」儀表板中提供的郵件流程報告。
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13871908c3b09660906b9233d23495830cf31ba9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057731"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="943c5-103">在安全性 & 規範中心的報表儀表板中查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="943c5-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="943c5-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="943c5-104">**Applies to**</span></span>
- [<span data-ttu-id="943c5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="943c5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="943c5-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="943c5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="943c5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="943c5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="943c5-108">除了安全性 & 合規性中心的 [郵件流程儀表板](mail-flow-insights-v2.md) 中所提供的郵件流程報告之外，「報告」儀表板還提供各種額外的郵件流程報告，可協助您監視 Microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="943c5-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="943c5-109">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以移至 [**報表**] 儀表板，在 [安全性 & 規範中心](https://protection.office.com)中查看這些報告 \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="943c5-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="943c5-110">若要直接移至 [報告] 儀表板，請開啟] <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="943c5-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全性 & 規範中心內的報告儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="943c5-112">連接器報告</span><span class="sxs-lookup"><span data-stu-id="943c5-112">Connector report</span></span>

<span data-ttu-id="943c5-113">**連接器報告** 會顯示為您的組織設定之 [輸入和輸出連接器](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)上的郵件流程活動。</span><span class="sxs-lookup"><span data-stu-id="943c5-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="943c5-114">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **連接器報告**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="943c5-115">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="943c5-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![報表儀表板中的連接器報表小工具](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="943c5-117">連接器報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="943c5-117">Report view for the Connector report</span></span>

<span data-ttu-id="943c5-118">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="943c5-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="943c5-119">**依下列方式查看資料：郵件流程**：此圖顯示輸入的輸入和輸出郵件數目：</span><span class="sxs-lookup"><span data-stu-id="943c5-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="943c5-120">**Total**</span><span class="sxs-lookup"><span data-stu-id="943c5-120">**Total**</span></span>
  - <span data-ttu-id="943c5-121">**從沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="943c5-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="943c5-122">**沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="943c5-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="943c5-123">您已設定的特定連接器。</span><span class="sxs-lookup"><span data-stu-id="943c5-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="943c5-124">若要隔離圖表中的資料，請使用 [顯示控制項的 **資料** ] 選取其中一個選項或 **所有郵件流程**。</span><span class="sxs-lookup"><span data-stu-id="943c5-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![在連接器報告中透過郵件流程查看資料](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="943c5-126">**資料查看依據： tls 使用狀況**：此圖顯示郵件流程的傳輸層安全性 (TLS) 版本用法的百分比。</span><span class="sxs-lookup"><span data-stu-id="943c5-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="943c5-127">若要隔離圖表中的資料，請使用 [顯示控制項的 **資料** ] 選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="943c5-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="943c5-128">**所有郵件流程**</span><span class="sxs-lookup"><span data-stu-id="943c5-128">**All mail flow**</span></span>
  - <span data-ttu-id="943c5-129">**從沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="943c5-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="943c5-130">**沒有連接器的網際網路**</span><span class="sxs-lookup"><span data-stu-id="943c5-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="943c5-131">您已設定的特定連接器。</span><span class="sxs-lookup"><span data-stu-id="943c5-131">A specific connector that you've configured.</span></span>

  ![依 TLS 使用量在連接器報告中查看資料](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="943c5-133">如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="943c5-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="943c5-134">連接器報表的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-134">Details table view for the Connector report</span></span>

<span data-ttu-id="943c5-135">如果您按一下報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="943c5-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="943c5-136">**Date**</span><span class="sxs-lookup"><span data-stu-id="943c5-136">**Date**</span></span>
- <span data-ttu-id="943c5-137">**連接器的方向和名稱**</span><span class="sxs-lookup"><span data-stu-id="943c5-137">**Connector direction and name**</span></span>
- <span data-ttu-id="943c5-138">**連接器類型**</span><span class="sxs-lookup"><span data-stu-id="943c5-138">**Connector type**</span></span>
- <span data-ttu-id="943c5-139">**強制 TLS？**：值 **True** 或 **False**。</span><span class="sxs-lookup"><span data-stu-id="943c5-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="943c5-140">**沒有 TLS** (百分比) </span><span class="sxs-lookup"><span data-stu-id="943c5-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="943c5-141">**TLS 1.0** (百分比) </span><span class="sxs-lookup"><span data-stu-id="943c5-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="943c5-142">**TLS 1.1** (百分比) </span><span class="sxs-lookup"><span data-stu-id="943c5-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="943c5-143">**TLS 1.2** (百分比) </span><span class="sxs-lookup"><span data-stu-id="943c5-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="943c5-144">**磁片** 區：郵件數目。</span><span class="sxs-lookup"><span data-stu-id="943c5-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="943c5-145">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="943c5-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="943c5-146">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="943c5-147">Exchange transport rule 報告</span><span class="sxs-lookup"><span data-stu-id="943c5-147">Exchange transport rule report</span></span>

<span data-ttu-id="943c5-148">**Exchange transport rule report** 會顯示郵件流程規則 (也稱為傳輸規則) 組織中內送和外寄郵件的效果。</span><span class="sxs-lookup"><span data-stu-id="943c5-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="943c5-149">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **Exchange Transport rule**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="943c5-150">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="943c5-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![報告儀表板中的 Exchange transport rule widget](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="943c5-152">Exchange transport rule 報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="943c5-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="943c5-153">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="943c5-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="943c5-154">**資料查看依據： Exchange 傳輸規則** \>**分解方式：方向**：此圖顯示受傳輸規則影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="943c5-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="943c5-155">**資料查看依據： Exchange 傳輸規則** \>**分解方式：嚴重性**：此圖表顯示 **高嚴重性** 和 **中低嚴重性** 的數目，以及 **低嚴重性** 郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="943c5-156">您可以將嚴重性層級設定為規則 ([ **以嚴重性層級** 或 _SetAuditSeverity_) 審核此規則] 中的動作。</span><span class="sxs-lookup"><span data-stu-id="943c5-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="943c5-157">如需詳細資訊，請參閱 [Exchange Online 中的郵件流程規則動作](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="943c5-157">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="943c5-158">**依下列方式查看資料： DLP Exchange transport rules** \>**分解方式：方向**：此圖顯示受資料遺失防護 (DLP) 傳輸規則所影響的 **輸入** 和 **輸出** 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="943c5-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="943c5-159">您可以選取下列選項來進一步精煉圖表：</span><span class="sxs-lookup"><span data-stu-id="943c5-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="943c5-160">**顯示資料：所有 DLP transport rules**</span><span class="sxs-lookup"><span data-stu-id="943c5-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="943c5-161">**顯示下列專案的資料：已遭破壞的使用者**</span><span class="sxs-lookup"><span data-stu-id="943c5-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="943c5-162">**顯示資料：偵測到的內容量下限美國愛國法案**</span><span class="sxs-lookup"><span data-stu-id="943c5-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="943c5-163">**依下列方式查看資料： DLP Exchange transport rules** \>**分解方式：方向**：此 View 顯示 **高嚴重性** 和 **中低嚴重性** 的數目，以及受 DLP transport rules 影響的 **低嚴重性** 郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="943c5-164">您可以選取下列選項來進一步精煉圖表：</span><span class="sxs-lookup"><span data-stu-id="943c5-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="943c5-165">**顯示資料：所有 DLP transport rules**</span><span class="sxs-lookup"><span data-stu-id="943c5-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="943c5-166">**顯示下列專案的資料：已遭破壞的使用者**</span><span class="sxs-lookup"><span data-stu-id="943c5-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="943c5-167">**顯示資料：偵測到的內容量下限美國愛國法案**</span><span class="sxs-lookup"><span data-stu-id="943c5-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="943c5-168">如果您按一下報表檢視中的 **篩選器** ，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="943c5-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="943c5-169">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="943c5-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="943c5-170">方向值</span><span class="sxs-lookup"><span data-stu-id="943c5-170">Direction values</span></span>
- <span data-ttu-id="943c5-171">嚴重性值</span><span class="sxs-lookup"><span data-stu-id="943c5-171">Severity values</span></span>

![Exchange transport rule 報告中的報表檢視](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="943c5-173">Exchange transport rule 報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="943c5-174">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="943c5-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="943c5-175">**依下列方式查看資料： Exchange Transport rules**：</span><span class="sxs-lookup"><span data-stu-id="943c5-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="943c5-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="943c5-176">**Date**</span></span>
  - <span data-ttu-id="943c5-177">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="943c5-177">**Transport rule**</span></span>
  - <span data-ttu-id="943c5-178">**主旨**</span><span class="sxs-lookup"><span data-stu-id="943c5-178">**Subject**</span></span>
  - <span data-ttu-id="943c5-179">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="943c5-179">**Sender address**</span></span>
  - <span data-ttu-id="943c5-180">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="943c5-180">**Recipient address**</span></span>
  - <span data-ttu-id="943c5-181">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="943c5-181">**Severity**</span></span>
  - <span data-ttu-id="943c5-182">**方向**</span><span class="sxs-lookup"><span data-stu-id="943c5-182">**Direction**</span></span>

- <span data-ttu-id="943c5-183">透過 **下列方式查看資料： DLP Exchange transport rules**：</span><span class="sxs-lookup"><span data-stu-id="943c5-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="943c5-184">**Date**</span><span class="sxs-lookup"><span data-stu-id="943c5-184">**Date**</span></span>
  - <span data-ttu-id="943c5-185">**DLP 原則**</span><span class="sxs-lookup"><span data-stu-id="943c5-185">**DLP policy**</span></span>
  - <span data-ttu-id="943c5-186">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="943c5-186">**Transport rule**</span></span>
  - <span data-ttu-id="943c5-187">**主旨**</span><span class="sxs-lookup"><span data-stu-id="943c5-187">**Subject**</span></span>
  - <span data-ttu-id="943c5-188">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="943c5-188">**Sender address**</span></span>
  - <span data-ttu-id="943c5-189">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="943c5-189">**Recipient address**</span></span>
  - <span data-ttu-id="943c5-190">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="943c5-190">**Severity**</span></span>
  - <span data-ttu-id="943c5-191">**方向**</span><span class="sxs-lookup"><span data-stu-id="943c5-191">**Direction**</span></span>

<span data-ttu-id="943c5-192">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="943c5-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="943c5-193">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="943c5-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="943c5-194">方向值</span><span class="sxs-lookup"><span data-stu-id="943c5-194">Direction values</span></span>
- <span data-ttu-id="943c5-195">嚴重性值</span><span class="sxs-lookup"><span data-stu-id="943c5-195">Severity values</span></span>

<span data-ttu-id="943c5-196">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="943c5-197">轉接報告</span><span class="sxs-lookup"><span data-stu-id="943c5-197">Forwarding report</span></span>

<span data-ttu-id="943c5-198">轉寄 **報告** 顯示組織自動轉寄給來自 Exchange Online 信箱的外部網域的郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="943c5-199">轉寄的郵件可能會造成安全性或規範風險，而且可能會指出已遭破壞的帳戶。</span><span class="sxs-lookup"><span data-stu-id="943c5-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="943c5-200">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **轉接報告**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="943c5-201">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="943c5-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![在報表儀表板中轉發報表小工具](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="943c5-203">轉送報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="943c5-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="943c5-204">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="943c5-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="943c5-205">**顯示資料：轉寄方法**：會顯示下列方法：</span><span class="sxs-lookup"><span data-stu-id="943c5-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="943c5-206">**傳輸規則**：也稱為「 [郵件流程規則](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」。</span><span class="sxs-lookup"><span data-stu-id="943c5-206">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="943c5-207">**信箱規則**：也稱為 [收件匣規則](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="943c5-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![轉寄報告中的轉接方法視圖](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="943c5-209">**顯示下列專案的資料：轉寄網域**：此視圖顯示是轉寄目的地的收件者網域。</span><span class="sxs-lookup"><span data-stu-id="943c5-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![轉寄報告中的轉移網域視圖](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="943c5-211">顯示下列專案的 **資料：轉寄站**：下列是顯示的轉寄站：</span><span class="sxs-lookup"><span data-stu-id="943c5-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="943c5-212">**傳輸規則**</span><span class="sxs-lookup"><span data-stu-id="943c5-212">**Transport rule**</span></span>
  - <span data-ttu-id="943c5-213">包含轉寄收件匣規則的信箱。</span><span class="sxs-lookup"><span data-stu-id="943c5-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![轉寄報告中的轉送器視圖](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="943c5-215">如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="943c5-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="943c5-216">轉接報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="943c5-217">如果您按一下報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="943c5-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="943c5-218">轉送 **器**：值 **傳輸規則** 或包含轉寄收件匣規則的信箱。</span><span class="sxs-lookup"><span data-stu-id="943c5-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="943c5-219">**轉送類型**：值 **信箱規則** 或 **傳輸規則**。</span><span class="sxs-lookup"><span data-stu-id="943c5-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="943c5-220">**收件者名稱**</span><span class="sxs-lookup"><span data-stu-id="943c5-220">**Recipient name**</span></span>
- <span data-ttu-id="943c5-221">**收件者網域**</span><span class="sxs-lookup"><span data-stu-id="943c5-221">**Recipient domain**</span></span>
- <span data-ttu-id="943c5-222">**詳細資料**：這是郵件流程規則的 GUID 值，或收件匣規則的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="943c5-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="943c5-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="943c5-223">**Count**</span></span>
- <span data-ttu-id="943c5-224">**第一個轉寄日期**</span><span class="sxs-lookup"><span data-stu-id="943c5-224">**First forward date**</span></span>

<span data-ttu-id="943c5-225">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="943c5-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="943c5-226">若要回到 [報告] 視圖，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="943c5-227">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="943c5-227">Mailflow status report</span></span>

<span data-ttu-id="943c5-228">**郵件流程狀態報表** 類似于 [已傳送及已接收的電子郵件報告](#sent-and-received-email-report)，包含有關在 edge 上允許或封鎖之電子郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="943c5-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="943c5-229">這是唯一包含 edge protection 資訊的報告，它會顯示在 Exchange Online Protection (EOP) 中，允許在評估之前封鎖多少封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="943c5-230">請務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="943c5-231">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報表**] \> **儀表板** ，然後選取 [ **郵件流程狀態報表**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="943c5-232">若要直接移至 [ **郵件流程] 狀態報表**，請開啟] <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="943c5-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![報表儀表板中的郵件流程狀態報表小工具](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="943c5-234">郵件流程狀態報表的類型視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="943c5-235">當您開啟報表時，預設會選取 [ **類型** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="943c5-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="943c5-236">根據預設，此視圖包含的圖表和使用下列篩選器設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="943c5-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="943c5-237">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="943c5-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="943c5-238">**方向**：</span><span class="sxs-lookup"><span data-stu-id="943c5-238">**Direction**:</span></span>

  - <span data-ttu-id="943c5-239">**入境**</span><span class="sxs-lookup"><span data-stu-id="943c5-239">**Inbound**</span></span>
  - <span data-ttu-id="943c5-240">**出境**</span><span class="sxs-lookup"><span data-stu-id="943c5-240">**Outbound**</span></span>
  - <span data-ttu-id="943c5-241">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="943c5-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="943c5-242">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與 **輸入** 和 **輸出**) 分開計數</span><span class="sxs-lookup"><span data-stu-id="943c5-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="943c5-243">**類型**：</span><span class="sxs-lookup"><span data-stu-id="943c5-243">**Type**:</span></span>

  - <span data-ttu-id="943c5-244">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-244">**Good mail**</span></span>
  - <span data-ttu-id="943c5-245">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="943c5-245">**Malware**</span></span>
  - <span data-ttu-id="943c5-246">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-246">**Spam**</span></span>
  - <span data-ttu-id="943c5-247">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="943c5-247">**Edge protection**</span></span>
  - <span data-ttu-id="943c5-248">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="943c5-248">**Rule messages**</span></span>
  - <span data-ttu-id="943c5-249">**網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-249">**Phishing email**</span></span>

<span data-ttu-id="943c5-250">圖表是依 **類型** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="943c5-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="943c5-251">您可以按一下 [ **篩選器** ] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="943c5-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="943c5-252">此資料表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="943c5-252">The data table contains the following information:</span></span>

- <span data-ttu-id="943c5-253">**方向**</span><span class="sxs-lookup"><span data-stu-id="943c5-253">**Direction**</span></span>
- <span data-ttu-id="943c5-254">**Type**</span><span class="sxs-lookup"><span data-stu-id="943c5-254">**Type**</span></span>
- <span data-ttu-id="943c5-255">**24 小時**</span><span class="sxs-lookup"><span data-stu-id="943c5-255">**24 hours**</span></span>
- <span data-ttu-id="943c5-256">**3天**</span><span class="sxs-lookup"><span data-stu-id="943c5-256">**3 days**</span></span>
- <span data-ttu-id="943c5-257">**7 天**</span><span class="sxs-lookup"><span data-stu-id="943c5-257">**7 days**</span></span>
- <span data-ttu-id="943c5-258">**15 天**</span><span class="sxs-lookup"><span data-stu-id="943c5-258">**15 days**</span></span>
- <span data-ttu-id="943c5-259">**30 天**</span><span class="sxs-lookup"><span data-stu-id="943c5-259">**30 days**</span></span>

<span data-ttu-id="943c5-260">如果您按一下 **[選擇類別] 以取得詳細資料**，您可以選取下列值：</span><span class="sxs-lookup"><span data-stu-id="943c5-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="943c5-261">**網路釣魚電子郵件**：這項選擇會帶您前往「 [威脅防護狀態」報告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="943c5-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="943c5-262">**電子郵件中的惡意** 代碼：這項選擇會帶您前往 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="943c5-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="943c5-263">**垃圾郵件** 偵測：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="943c5-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="943c5-264">**Edge 封鎖的垃圾郵件**：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="943c5-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="943c5-265">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="943c5-265">**Export**:</span></span>

<span data-ttu-id="943c5-266">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="943c5-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="943c5-267">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="943c5-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="943c5-268">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="943c5-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="943c5-269">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="943c5-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="943c5-270">郵件流程狀態報表中的類型視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="943c5-271">郵件流程狀態報表的方向視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="943c5-272">如果您按一下 [ **方向** ] 索引標籤，則會使用 [ **類型** ] 視圖中的相同預設篩選器。</span><span class="sxs-lookup"><span data-stu-id="943c5-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="943c5-273">圖表是依 **方向** 值進行組織。</span><span class="sxs-lookup"><span data-stu-id="943c5-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="943c5-274">您可以按一下 [ **篩選器** ] 或按一下 [圖表圖例] 中的值來變更這些篩選。</span><span class="sxs-lookup"><span data-stu-id="943c5-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="943c5-275">會使用 [ **類型** ] 視圖中的相同篩選器。</span><span class="sxs-lookup"><span data-stu-id="943c5-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="943c5-276">資料表格包含的資訊來自 **類型** view。</span><span class="sxs-lookup"><span data-stu-id="943c5-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="943c5-277">[ **選擇類別** ] 如需詳細資料，可用的選取專案和行為與「 **類型** 」視圖相同。</span><span class="sxs-lookup"><span data-stu-id="943c5-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="943c5-278">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="943c5-278">**Export**:</span></span>

<span data-ttu-id="943c5-279">在 [詳細資料] 視圖中，您只能匯出一天的資料。</span><span class="sxs-lookup"><span data-stu-id="943c5-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="943c5-280">因此，如果您想要匯出資料7天，您必須做7種不同的匯出動作。</span><span class="sxs-lookup"><span data-stu-id="943c5-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="943c5-281">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="943c5-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="943c5-282">如果該天的資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="943c5-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="943c5-283">郵件流程狀態報表中的方向視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="943c5-284">郵件流程狀態報表的漏斗視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="943c5-285">**漏斗** 視圖顯示 Microsoft 的電子郵件威脅防護功能如何篩選組織中的內送和外寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="943c5-286">它提供有關電子郵件總數的詳細資訊，以及設定的威脅防護功能（包括 edge protection、反惡意程式碼、反網路釣魚、反垃圾郵件和反欺詐）對此計數的影響。</span><span class="sxs-lookup"><span data-stu-id="943c5-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="943c5-287">如果您按一下 [ **漏斗** ] 索引標籤，此 view 預設會包含圖表和使用下列篩選設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="943c5-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="943c5-288">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="943c5-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="943c5-289">**方向**：</span><span class="sxs-lookup"><span data-stu-id="943c5-289">**Direction**:</span></span>

  - <span data-ttu-id="943c5-290">**入境**</span><span class="sxs-lookup"><span data-stu-id="943c5-290">**Inbound**</span></span>
  - <span data-ttu-id="943c5-291">**出境**</span><span class="sxs-lookup"><span data-stu-id="943c5-291">**Outbound**</span></span>
  - <span data-ttu-id="943c5-292">**組織內**：此計數是針對在租使用者中傳送的郵件進行計數;亦即，寄件者 abc@domain.com 會傳送給收件者 xyz@domain.com (與輸入和外寄) 分開計數。</span><span class="sxs-lookup"><span data-stu-id="943c5-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="943c5-293">匯總 view 和 data table view 允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="943c5-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="943c5-294">如果您按一下 [ **篩選**]，則可以篩選圖表和資料表格。</span><span class="sxs-lookup"><span data-stu-id="943c5-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="943c5-295">此圖顯示按下列方式組織的電子郵件計數：</span><span class="sxs-lookup"><span data-stu-id="943c5-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="943c5-296">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="943c5-296">**Total email**</span></span>
- <span data-ttu-id="943c5-297">**Edge protection 之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-297">**Email after edge protection**</span></span>
- <span data-ttu-id="943c5-298">**反惡意程式碼、檔信譽、檔案類型封鎖後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="943c5-299">**反網路釣魚、URL 信譽、品牌模擬、反欺騙功能之後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="943c5-300">**反垃圾郵件、大宗郵件篩選後的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="943c5-301">**使用者和網域模擬1之後的電子郵件**<sup></sup></span><span class="sxs-lookup"><span data-stu-id="943c5-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="943c5-302">檔案 **及 URL 引爆1後的電子郵件**<sup></sup></span><span class="sxs-lookup"><span data-stu-id="943c5-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="943c5-303">**在傳遞投遞後保護後，電子郵件偵測為良性 (URL 按一下時間保護)**</span><span class="sxs-lookup"><span data-stu-id="943c5-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="943c5-304">僅限<sup>1</sup> Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="943c5-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="943c5-305">若要分別查看以 EOP 或 Defender for Office 365 篩選的電子郵件，請按一下 [圖表圖例] 中的值。</span><span class="sxs-lookup"><span data-stu-id="943c5-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="943c5-306">此資料表包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="943c5-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="943c5-307">**Date**</span><span class="sxs-lookup"><span data-stu-id="943c5-307">**Date**</span></span>
- <span data-ttu-id="943c5-308">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="943c5-308">**Total email**</span></span>
- <span data-ttu-id="943c5-309">**Edge protection**</span><span class="sxs-lookup"><span data-stu-id="943c5-309">**Edge protection**</span></span>
- <span data-ttu-id="943c5-310">**反惡意程式碼、檔信譽、檔案類型封鎖**：</span><span class="sxs-lookup"><span data-stu-id="943c5-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="943c5-311">**檔信譽**：由於其他 Microsoft 客戶附加的檔案識別，因此篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="943c5-312">**檔案類型封鎖**：由於郵件中識別的惡意檔案類型，篩選郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="943c5-313">**反網路釣魚、URL 信譽、品牌模仿、反欺騙**：</span><span class="sxs-lookup"><span data-stu-id="943c5-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="943c5-314">**URL 信譽**：由於其他 Microsoft 客戶的 url 身分識別而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="943c5-315">**品牌** 模擬：因為郵件是由眾所周知的品牌類比寄件者所過濾，所以會加以篩選。</span><span class="sxs-lookup"><span data-stu-id="943c5-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="943c5-316">**反欺騙**：因為郵件企圖哄騙收件者所屬的網域，或是郵件寄件者不會擁有的網域，所以篩選掉郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="943c5-317">**反垃圾郵件，大宗郵件篩選**：</span><span class="sxs-lookup"><span data-stu-id="943c5-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="943c5-318">**大宗郵件篩選**：郵件因嘗試將大宗郵件傳遞給其收件者而加以篩選。</span><span class="sxs-lookup"><span data-stu-id="943c5-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="943c5-319">**適用于 Office 365 (Defender 的使用者和網域模擬)**：</span><span class="sxs-lookup"><span data-stu-id="943c5-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="943c5-320">**使用者** 模擬：郵件因嘗試模擬使用者 (郵件寄件者) （已在反網路釣魚原則的類比保護設定中所定義）而篩選。</span><span class="sxs-lookup"><span data-stu-id="943c5-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="943c5-321">**網域** 模擬：郵件因嘗試模擬防網路釣魚原則之類比保護設定中所定義的網域而篩選出來。</span><span class="sxs-lookup"><span data-stu-id="943c5-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="943c5-322">檔案 **與 URL 引爆 (Office 365 的 Defender)**：</span><span class="sxs-lookup"><span data-stu-id="943c5-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="943c5-323">**檔引爆**：以安全附件原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="943c5-324">**URL 引爆**：以安全連結原則篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="943c5-325">**投遞後保護和 zap (ATP) 或 zap (EOP)**： zap 表示自動清除零小時。</span><span class="sxs-lookup"><span data-stu-id="943c5-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="943c5-326">如果您選取資料表格中的資料列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="943c5-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="943c5-327">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="943c5-327">**Export**:</span></span>

<span data-ttu-id="943c5-328">在 [**選項**] 下按一下 [**匯出**] 後，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="943c5-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="943c5-329">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="943c5-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="943c5-330">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="943c5-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="943c5-331">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="943c5-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="943c5-332">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="943c5-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="943c5-333">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="943c5-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="943c5-334">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="943c5-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="943c5-335">郵件流程狀態報表中的漏斗圖視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="943c5-336">郵件流程狀態報表的技術視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="943c5-337">**技術視圖** 類似 **漏斗** 圖模式，可提供設定威脅防護功能的更細微細節。</span><span class="sxs-lookup"><span data-stu-id="943c5-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="943c5-338">您可以從圖表中查看郵件如何在威脅防護的不同階段進行分類。</span><span class="sxs-lookup"><span data-stu-id="943c5-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="943c5-339">如果您按一下 [ **技術視圖** ] 索引標籤，此視圖預設會包含圖表和使用下列篩選所設定的資料表：</span><span class="sxs-lookup"><span data-stu-id="943c5-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="943c5-340">**日期**：過去7天。</span><span class="sxs-lookup"><span data-stu-id="943c5-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="943c5-341">**方向**：</span><span class="sxs-lookup"><span data-stu-id="943c5-341">**Direction**:</span></span>

  - <span data-ttu-id="943c5-342">**入境**</span><span class="sxs-lookup"><span data-stu-id="943c5-342">**Inbound**</span></span>
  - <span data-ttu-id="943c5-343">**出境**</span><span class="sxs-lookup"><span data-stu-id="943c5-343">**Outbound**</span></span>
  - <span data-ttu-id="943c5-344">**組織內**：此計數是針對承租人中的郵件，亦即</span><span class="sxs-lookup"><span data-stu-id="943c5-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="943c5-345">寄件者 abc@domain.com 會傳送至收件者 xyz@domain.com (與輸入和輸出) 分開計數</span><span class="sxs-lookup"><span data-stu-id="943c5-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="943c5-346">匯總 view 和 data table view 允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="943c5-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="943c5-347">如果您按一下 [ **篩選**]，則可以篩選圖表和資料表格。</span><span class="sxs-lookup"><span data-stu-id="943c5-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="943c5-348">此圖顯示組織成下列類別的郵件：</span><span class="sxs-lookup"><span data-stu-id="943c5-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="943c5-349">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="943c5-349">**Total email**</span></span>
- <span data-ttu-id="943c5-350">**Edge 允許** 和 **edge 篩選**</span><span class="sxs-lookup"><span data-stu-id="943c5-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="943c5-351">**非惡意** 代碼、**安全附件偵測** <sup>\*</sup> 、**反惡意程式碼引擎偵測** 和 **規則訊息**</span><span class="sxs-lookup"><span data-stu-id="943c5-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="943c5-352">**不是網路釣魚詐騙**、 **DMARC 失敗**、 **模仿偵測**、 **欺騙偵測** 和 **網路釣魚偵測**</span><span class="sxs-lookup"><span data-stu-id="943c5-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="943c5-353">**沒有偵測 URL 引爆** 及 **url 引爆偵測**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="943c5-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="943c5-354">**非垃圾郵件** 和  **垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="943c5-355">**非惡意的電子郵件**、**安全連結偵測** <sup>\*</sup> 和 **ZAP**</span><span class="sxs-lookup"><span data-stu-id="943c5-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="943c5-356"><sup>\*</sup> 適用于 Office 的 Defender 365</span><span class="sxs-lookup"><span data-stu-id="943c5-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="943c5-357">當您將游標移到圖表中的某個類別時，您可以看到該類別中的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="943c5-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="943c5-358">此資料表包含下列資訊（以遞減的日期順序顯示）：</span><span class="sxs-lookup"><span data-stu-id="943c5-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="943c5-359">**Date**</span><span class="sxs-lookup"><span data-stu-id="943c5-359">**Date**</span></span>
- <span data-ttu-id="943c5-360">**電子郵件總數**</span><span class="sxs-lookup"><span data-stu-id="943c5-360">**Total email**</span></span>
- <span data-ttu-id="943c5-361">**已篩選 Edge**</span><span class="sxs-lookup"><span data-stu-id="943c5-361">**Edge filtered**</span></span>
- <span data-ttu-id="943c5-362">**反惡意程式碼引擎、安全附件、已篩選的規則**。。</span><span class="sxs-lookup"><span data-stu-id="943c5-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="943c5-363">已 **篩選的規則**：由於郵件流程規則而篩選的郵件 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="943c5-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="943c5-364">**DMARC，類比，欺騙，網路釣魚篩選**：</span><span class="sxs-lookup"><span data-stu-id="943c5-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="943c5-365">**DMARC**：由於郵件失敗的 DMARC 驗證檢查而篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="943c5-366">**URL 引爆偵測**</span><span class="sxs-lookup"><span data-stu-id="943c5-366">**URL detonation detection**</span></span>
- <span data-ttu-id="943c5-367">**已篩選的反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="943c5-368">**移除的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="943c5-368">**ZAP removed**</span></span>
- <span data-ttu-id="943c5-369">**安全連結偵測**</span><span class="sxs-lookup"><span data-stu-id="943c5-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="943c5-370">如果您選取資料表格中的資料列，則會在飛入的電子郵件計數中顯示進一步細分。</span><span class="sxs-lookup"><span data-stu-id="943c5-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="943c5-371">**匯出**：</span><span class="sxs-lookup"><span data-stu-id="943c5-371">**Export**:</span></span>

<span data-ttu-id="943c5-372">在按一下 [ **匯出**] 的 [ **選項** ] 底下，您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="943c5-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="943c5-373">**資料摘要 (，最多) 過去90天的資料**</span><span class="sxs-lookup"><span data-stu-id="943c5-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="943c5-374">**詳細資料 (過去30天的資料，最多)**</span><span class="sxs-lookup"><span data-stu-id="943c5-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="943c5-375">在 [ **日期**] 下，選擇範圍，然後 **按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="943c5-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="943c5-376">目前篩選的資料會匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="943c5-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="943c5-377">每個匯出的 .csv 檔案限制為150000列。</span><span class="sxs-lookup"><span data-stu-id="943c5-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="943c5-378">如果資料包含超過150000列，則會建立多個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="943c5-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="943c5-379">郵件流程狀態報表中的技術視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="943c5-380">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="943c5-380">Sent and received email report</span></span>

<span data-ttu-id="943c5-381">「 **傳送及接收的電子郵件** 報告」是一個智慧報告，顯示傳入和傳出電子郵件的相關資訊，包括垃圾郵件偵測、惡意程式碼，以及識別為「良好」的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="943c5-382">此報告與 [郵件流程狀態報表](#mailflow-status-report) 之間的差異為：此報告不包含 edge protection 所封鎖之郵件的相關資料。請務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為一封郵件。</span><span class="sxs-lookup"><span data-stu-id="943c5-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="943c5-383">報表的匯總視圖和詳細資料檢視允許90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="943c5-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="943c5-384">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **已傳送及已接收的電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="943c5-385">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="943c5-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![在報告儀表板中傳送及接收的電子郵件小工具](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="943c5-387">傳送和接收的電子郵件報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="943c5-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="943c5-388">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="943c5-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="943c5-389">**分解方式：類型**：圖表會顯示所有可用的類別：</span><span class="sxs-lookup"><span data-stu-id="943c5-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="943c5-390">**Total**</span><span class="sxs-lookup"><span data-stu-id="943c5-390">**Total**</span></span>
  - <span data-ttu-id="943c5-391">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="943c5-391">**Good mail**</span></span>
  - <span data-ttu-id="943c5-392">**惡意程式碼 (反惡意程式碼)** (EOP) </span><span class="sxs-lookup"><span data-stu-id="943c5-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="943c5-393">**垃圾郵件偵測**</span><span class="sxs-lookup"><span data-stu-id="943c5-393">**Spam detections**</span></span>
  - <span data-ttu-id="943c5-394">**規則訊息**</span><span class="sxs-lookup"><span data-stu-id="943c5-394">**Rule messages**</span></span>
  - <span data-ttu-id="943c5-395">Microsoft Defender for Office 365 的 **高級惡意** 代碼 () </span><span class="sxs-lookup"><span data-stu-id="943c5-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="943c5-396">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您就可以查看該天的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="943c5-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![傳送和接收的電子郵件報告中的類型視圖](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="943c5-398">**分解方式：方向**：圖表會顯示 **總計**、 **輸入** 和 **輸出** 資料。</span><span class="sxs-lookup"><span data-stu-id="943c5-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="943c5-399">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您就可以查看該天的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="943c5-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![傳送和接收的電子郵件報告中的方向視圖](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="943c5-401">**向下** \> 鑽取 **惡意軟體 (反惡意程式碼)**：這項選擇會帶您前往 [電子郵件報告中的惡意](view-email-security-reports.md#malware-detections-in-email-report)代碼偵測。</span><span class="sxs-lookup"><span data-stu-id="943c5-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="943c5-402">**向下** \> 鑽取 **垃圾郵件偵測)**：這項選擇會帶您前往 [垃圾郵件偵測報告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="943c5-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="943c5-403">如果您按一下報表檢視中的 **篩選器** ，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="943c5-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="943c5-404">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="943c5-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="943c5-405">方向值</span><span class="sxs-lookup"><span data-stu-id="943c5-405">Direction values</span></span>
- <span data-ttu-id="943c5-406">類型值</span><span class="sxs-lookup"><span data-stu-id="943c5-406">Type values</span></span>

<span data-ttu-id="943c5-407">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="943c5-408">傳送及接收的電子郵件報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="943c5-409">如果您按一下 [按下列方式] 中的 [ **View details table** **：方向** ] 或 [ **分解方式** ]： [方向] 視圖，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="943c5-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="943c5-410">**日期 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="943c5-410">**Date (UTC)**</span></span>
- <span data-ttu-id="943c5-411">**Type**</span><span class="sxs-lookup"><span data-stu-id="943c5-411">**Type**</span></span>
- <span data-ttu-id="943c5-412">**方向**</span><span class="sxs-lookup"><span data-stu-id="943c5-412">**Direction**</span></span>
- <span data-ttu-id="943c5-413">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="943c5-413">**Message count**</span></span>

<span data-ttu-id="943c5-414">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="943c5-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="943c5-415">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="943c5-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="943c5-416">方向值</span><span class="sxs-lookup"><span data-stu-id="943c5-416">Direction values</span></span>
- <span data-ttu-id="943c5-417">類型值</span><span class="sxs-lookup"><span data-stu-id="943c5-417">Type values</span></span>

<span data-ttu-id="943c5-418">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="943c5-419">主要寄件者和收件者報表</span><span class="sxs-lookup"><span data-stu-id="943c5-419">Top senders and recipients report</span></span>

<span data-ttu-id="943c5-420">[ **主要寄件者與收件** 者] 報告為圓形圖，顯示您的電子郵件寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="943c5-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="943c5-421">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **主要寄件者和收件** 者]。</span><span class="sxs-lookup"><span data-stu-id="943c5-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="943c5-422">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="943c5-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![報表儀表板中的主要寄件者和收件者小工具](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="943c5-424">主要寄件者和收件者報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="943c5-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="943c5-425">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="943c5-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="943c5-426">**顯示 \> 主要郵件寄件者的資料**</span><span class="sxs-lookup"><span data-stu-id="943c5-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="943c5-427">**顯示 \> 主要郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="943c5-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="943c5-428">**顯示 \> 主要垃圾郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="943c5-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="943c5-429">**顯示資料 \> 主要惡意** 代碼收件者 (EOP) </span><span class="sxs-lookup"><span data-stu-id="943c5-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="943c5-430">**顯示主要惡意程式碼收件者的資料 \> (Defender For Office 365)**</span><span class="sxs-lookup"><span data-stu-id="943c5-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="943c5-431">圓形圖的組成會根據這些選取範圍變更。</span><span class="sxs-lookup"><span data-stu-id="943c5-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="943c5-432">當您將游標移到圓形圖中的楔形上方時，您可以看到所傳送或接收的郵件計數。</span><span class="sxs-lookup"><span data-stu-id="943c5-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="943c5-433">如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="943c5-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![在 [主要寄件者和收件者] 報告中的報表檢視中的圓形圖表](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="943c5-435">主要寄件者和收件者報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="943c5-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="943c5-436">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="943c5-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="943c5-437">**顯示 \> 主要郵件寄件者的資料**</span><span class="sxs-lookup"><span data-stu-id="943c5-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="943c5-438">**主要郵件寄件者**</span><span class="sxs-lookup"><span data-stu-id="943c5-438">**Top mail senders**</span></span>
  - <span data-ttu-id="943c5-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="943c5-439">**Count**</span></span>

- <span data-ttu-id="943c5-440">**顯示 \> 主要郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="943c5-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="943c5-441">**主要郵件收件者**</span><span class="sxs-lookup"><span data-stu-id="943c5-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="943c5-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="943c5-442">**Count**</span></span>

- <span data-ttu-id="943c5-443">**顯示 \> 主要垃圾郵件收件者的資料**</span><span class="sxs-lookup"><span data-stu-id="943c5-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="943c5-444">**主要垃圾郵件收件者**</span><span class="sxs-lookup"><span data-stu-id="943c5-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="943c5-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="943c5-445">**Count**</span></span>

- <span data-ttu-id="943c5-446">**顯示資料 \> 主要惡意** 代碼收件者 (EOP) </span><span class="sxs-lookup"><span data-stu-id="943c5-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="943c5-447">**主要惡意程式碼收件者**</span><span class="sxs-lookup"><span data-stu-id="943c5-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="943c5-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="943c5-448">**Count**</span></span>

- <span data-ttu-id="943c5-449">**顯示主要惡意程式碼收件者的資料 \> (Defender For Office 365)**</span><span class="sxs-lookup"><span data-stu-id="943c5-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="943c5-450">**Office 365 (Defender 的主要惡意程式碼收件者)**</span><span class="sxs-lookup"><span data-stu-id="943c5-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="943c5-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="943c5-451">**Count**</span></span>

<span data-ttu-id="943c5-452">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="943c5-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="943c5-453">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="943c5-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="943c5-454">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="943c5-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="943c5-455">為了查看和使用本文所述的報表，您必須是安全性 & 合規性中心之一的下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="943c5-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="943c5-456">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="943c5-456">**Organization Management**</span></span>
- <span data-ttu-id="943c5-457">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="943c5-457">**Security Administrator**</span></span>
- <span data-ttu-id="943c5-458">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="943c5-458">**Security Reader**</span></span>
- <span data-ttu-id="943c5-459">**全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="943c5-459">**Global Reader**</span></span>

<span data-ttu-id="943c5-460">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="943c5-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="943c5-461">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="943c5-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="943c5-462">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="943c5-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="943c5-463">相關主題</span><span class="sxs-lookup"><span data-stu-id="943c5-463">Related topics</span></span>

[<span data-ttu-id="943c5-464">安全性與合規性中心內的智慧型報表和深入解析</span><span class="sxs-lookup"><span data-stu-id="943c5-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="943c5-465">安全性與合規性中心內的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="943c5-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="943c5-466">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="943c5-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="943c5-467">查看 Microsoft Defender for Office 365 的報告</span><span class="sxs-lookup"><span data-stu-id="943c5-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
