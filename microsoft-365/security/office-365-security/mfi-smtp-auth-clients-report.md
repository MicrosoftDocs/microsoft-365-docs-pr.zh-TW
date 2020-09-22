---
title: SMTP 驗證用戶端在郵件流程儀表板中瞭解和報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全性 & 合規性中心內郵件流程儀表板中的 SMTP 驗證瞭解和報告，以監視其組織中使用已驗證 SMTP (SMTP 驗證) 傳送電子郵件的電子郵件寄件者。
ms.openlocfilehash: 7ca673e5ecc92c28996a976c26a38ae570f16203
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199238"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="85f12-103">SMTP 驗證用戶端在安全性 & 規範中心內的洞察力和報告</span><span class="sxs-lookup"><span data-stu-id="85f12-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="85f12-104">**Smtp 驗證用戶端**在[郵件流程儀表板](mail-flow-insights-v2.md)中深入瞭解，[安全性 & 規範中心](https://protection.office.com)內的相關聯[SMTP 驗證用戶端報告](#smtp-auth-clients-report)，請強調使用者或組織中的系統帳戶使用 SMTP 驗證用戶端提交通訊協定。</span><span class="sxs-lookup"><span data-stu-id="85f12-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="85f12-105">這種舊版通訊協定 (會使用端點 smtp.office365.com) 僅提供基本驗證，而且很容易遭到受損帳戶使用以傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="85f12-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="85f12-106">「洞察力」和「報告」可讓您檢查是否有不尋常的 SMTP 驗證電子郵件提交活動。</span><span class="sxs-lookup"><span data-stu-id="85f12-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="85f12-107">此外，它也會顯示使用 SMTP 驗證之用戶端或裝置的 TLS 使用狀況資料。</span><span class="sxs-lookup"><span data-stu-id="85f12-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="85f12-108">此小工具會指出過去7天內，已使用 SMTP 驗證通訊協定的使用者或服務帳戶數目。</span><span class="sxs-lookup"><span data-stu-id="85f12-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![安全性 & 規範中心內郵件流程儀表板中的 SMTP 驗證用戶端小工具](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="85f12-110">如果您按一下小工具上的郵件數目，則會出現 **SMTP 驗證用戶端** 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="85f12-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="85f12-111">浮出控制項可提供過去一周之 TLS 使用狀況和磁片區的匯總視圖。</span><span class="sxs-lookup"><span data-stu-id="85f12-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![在郵件流程儀表板中按一下 [SMTP 驗證用戶端] 小工具後的詳細資料浮出控制項](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="85f12-113">您可以按一下 [ **Smtp 驗證用戶端] 報告** 連結，以移至下一節所述的 smtp 驗證用戶端報告。</span><span class="sxs-lookup"><span data-stu-id="85f12-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="85f12-114">SMTP 驗證用戶端報告</span><span class="sxs-lookup"><span data-stu-id="85f12-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="85f12-115">SMTP 驗證用戶端報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="85f12-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="85f12-116">根據預設，報告會顯示過去7天的資料，但資料可用於過去的90天。</span><span class="sxs-lookup"><span data-stu-id="85f12-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="85f12-117">[一覽表] 區段包含下列圖表：</span><span class="sxs-lookup"><span data-stu-id="85f12-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="85f12-118">透過**下列方式來查看資料**：傳送磁片區：依預設，圖表會顯示從所有網域傳送來的 SMTP 驗證用戶端郵件數目 (顯示資料：預設會選取 [**所有寄件者網域**]) 。</span><span class="sxs-lookup"><span data-stu-id="85f12-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="85f12-119">您可以按一下 [ **顯示資料** ]，然後從下拉式清單中選取 [寄件者網域]，將結果篩選為特定寄件者網域。</span><span class="sxs-lookup"><span data-stu-id="85f12-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="85f12-120">如果您將特定資料點懸停 (day) 中，就會顯示訊息的數目。</span><span class="sxs-lookup"><span data-stu-id="85f12-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![在安全性 & 規範中心的 SMTP 驗證用戶端報告中傳送大量視圖](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="85f12-122">**資料查看依據： TLS 使用方式**：此圖表顯示選取時段內所有 SMTP 驗證用戶端郵件的 TLS 使用百分比。</span><span class="sxs-lookup"><span data-stu-id="85f12-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="85f12-123">這張圖表可讓您識別仍然使用舊版 TLS 的使用者和系統帳戶，並對其採取動作。</span><span class="sxs-lookup"><span data-stu-id="85f12-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![安全性 & 規範中心內的 SMTP 驗證用戶端報告中的 TLS 使用狀況視圖](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="85f12-125">如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="85f12-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="85f12-126">按一下 [ **要求報告** ]，以在電子郵件訊息中接收更詳細的報表版本。</span><span class="sxs-lookup"><span data-stu-id="85f12-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="85f12-127">您可以指定日期範圍和接收報告的收件者。</span><span class="sxs-lookup"><span data-stu-id="85f12-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="85f12-128">SMTP 驗證用戶端報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="85f12-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="85f12-129">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="85f12-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="85f12-130">透過**下列方式查看資料**：傳送磁片區：下列資訊會顯示在表格中：</span><span class="sxs-lookup"><span data-stu-id="85f12-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="85f12-131">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="85f12-131">**Sender address**</span></span>
  - <span data-ttu-id="85f12-132">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="85f12-132">**Message count**</span></span>

  <span data-ttu-id="85f12-133">如果您選取某列，則會在飛入的視窗中顯示相同的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="85f12-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="85f12-134">**資料查看依據： TLS 使用方式**：下列資訊會顯示在表格中：</span><span class="sxs-lookup"><span data-stu-id="85f12-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="85f12-135">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="85f12-135">**Sender address**</span></span>
  - <span data-ttu-id="85f12-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="85f12-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="85f12-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="85f12-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="85f12-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="85f12-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="85f12-139">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="85f12-139">**Message count**</span></span>

  <span data-ttu-id="85f12-140"><sup>\*</sup> 此欄位會顯示寄件者的百分比和郵件數目。</span><span class="sxs-lookup"><span data-stu-id="85f12-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="85f12-141">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="85f12-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="85f12-142">如果您選取某列，則會在浮出控制項中顯示類似的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="85f12-142">If you select a row, similar details are shown in a flyout:</span></span>

![來自 SMTP Auth 用戶端報告中 TLS 使用狀況視圖詳細資料表格的詳細資料快顯視窗](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="85f12-144">按一下 [ **要求報告** ]，以在電子郵件訊息中接收更詳細的報表版本。</span><span class="sxs-lookup"><span data-stu-id="85f12-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="85f12-145">您可以指定日期範圍和接收報告的收件者。</span><span class="sxs-lookup"><span data-stu-id="85f12-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="85f12-146">若要回到 [報告] 視圖，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="85f12-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="85f12-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="85f12-147">Related topics</span></span>

<span data-ttu-id="85f12-148">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="85f12-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
