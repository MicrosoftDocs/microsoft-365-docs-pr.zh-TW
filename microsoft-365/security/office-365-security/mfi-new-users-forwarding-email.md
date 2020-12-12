---
title: 新使用者轉寄電子郵件深入解析
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以瞭解如何使用「安全性 & 規範中心」中的新使用者轉寄電子郵件，以調查組織中的使用者將郵件轉寄給新網域的時間。
ms.openlocfilehash: cf1852169279e19ac00e5e29dd1c26e155936039
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660014"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="e4aa6-103">新的使用者在安全性 & 合規性中心轉寄電子郵件洞察力</span><span class="sxs-lookup"><span data-stu-id="e4aa6-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e4aa6-104">當您組織中的新使用者帳戶突然開始將電子郵件轉送至外部網域時，它會是可疑的。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="e4aa6-105">當您組織中新建立的使用者將郵件轉寄給外部網域時，在 [安全性 & 合規性中心](https://protection.office.com)內 **轉寄的新網域** 會通知您。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="e4aa6-106">這種情況可能表示使用已遭到損害的系統管理員帳戶來建立新的使用者。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="e4aa6-107">如果您懷疑帳戶已遭破壞，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="e4aa6-108">這種洞察力只會在偵測到問題時出現，而且會出現在 [ [轉接回報報告](view-mail-flow-reports.md#forwarding-report) ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新使用者轉寄電子郵件深入解析](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="e4aa6-110">當您按一下該小工具時，會出現一個快顯視窗，您可以在其中找到轉送郵件的詳細資料，包括「轉寄 [修改」報告](#forwarding-modifications-report) 的連結（如本文稍後所述）。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![按一下新的使用者轉寄電子郵件功能之後顯示的詳細資料浮出控制項](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="e4aa6-112">您也可以在 [ (**報表** 儀表板] 或 [) ] 的 [**熱門洞察力 & 建議**] 區域中按一下 [**全部查看**] 之後，取得此詳細資料頁面 \>  <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="e4aa6-113">您可以按一下 [ **參閱與真知灼見相關的報告** ] 連結，以移至下一節所述的「轉寄 **修改」報告** 。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="e4aa6-114">轉送修改報告</span><span class="sxs-lookup"><span data-stu-id="e4aa6-114">Forwarding modifications report</span></span>

<span data-ttu-id="e4aa6-115">[轉寄 **修改] 報告** 顯示從組織中寄件者自動轉寄之郵件的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="e4aa6-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="e4aa6-116">將郵件轉送至外部網域的新建立帳戶。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="e4aa6-117">將郵件轉寄給外部網域的帳戶，而這些網域從未由組織中的其他寄件者轉寄。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="e4aa6-118">這類轉寄郵件可能會帶來安全性或合規性風險，而且可能會指出已遭破壞的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="e4aa6-119">報告包含多達90天的資料。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="e4aa6-120">根據預設，報告會顯示過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="e4aa6-121">在 [郵件流程儀表板](mail-flow-insights-v2.md) 或 [報表儀表板](view-mail-flow-reports.md)中，無法直接使用此報告。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="e4aa6-122">除了按一下 **新使用者轉寄電子郵件** 內容中的 **真知灼見連結相關聯的參閱報告** 之外，您還可以透過下列方式取得報告：</span><span class="sxs-lookup"><span data-stu-id="e4aa6-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="e4aa6-123">按一下 [要轉寄電子郵件網路洞察力之新網域](mfi-new-domains-being-forwarded-email.md)詳細資料中的「轉寄 **通知報告**」連結。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="e4aa6-124">開啟 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="e4aa6-125">「轉寄修改」報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="e4aa6-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="e4aa6-126">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="e4aa6-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e4aa6-127">**顯示下列專案的資料：新增轉接使用者**：</span><span class="sxs-lookup"><span data-stu-id="e4aa6-127">**Show data for: New forwarding users**:</span></span>

  ![「轉發修改」報告中的新轉寄使用者視圖](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="e4aa6-129">**顯示下列專案的資料：新增轉送網域**：</span><span class="sxs-lookup"><span data-stu-id="e4aa6-129">**Show data for: New forwarding domains**:</span></span>

  ![「轉發修改」報告中的新轉寄網域視圖](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="e4aa6-131">如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="e4aa6-132">「轉寄修改」報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="e4aa6-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="e4aa6-133">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="e4aa6-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e4aa6-134">**顯示下列專案的資料：新增轉接使用者**：</span><span class="sxs-lookup"><span data-stu-id="e4aa6-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="e4aa6-135">**名稱**：寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="e4aa6-136">**轉送類型**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-136">**Forwarding type**</span></span>
  - <span data-ttu-id="e4aa6-137">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-137">**Recipient address**</span></span>
  - <span data-ttu-id="e4aa6-138">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-138">**Details**</span></span>
  - <span data-ttu-id="e4aa6-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-139">**Count**</span></span>
  - <span data-ttu-id="e4aa6-140">**第一個轉寄日期**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-140">**First forward date**</span></span>

- <span data-ttu-id="e4aa6-141">**顯示下列專案的資料：新增轉送網域**：</span><span class="sxs-lookup"><span data-stu-id="e4aa6-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="e4aa6-142">**名稱**：寄件者的電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="e4aa6-143">**轉送類型**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-143">**Forwarding type**</span></span>
  - <span data-ttu-id="e4aa6-144">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-144">**Recipient address**</span></span>
  - <span data-ttu-id="e4aa6-145">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-145">**Details**</span></span>
  - <span data-ttu-id="e4aa6-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-146">**Count**</span></span>
  - <span data-ttu-id="e4aa6-147">**第一個轉寄日期**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-147">**First forward date**</span></span>

<span data-ttu-id="e4aa6-148">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e4aa6-149">如果您從表格選取某一列，則會顯示 **詳細資料** 快顯視窗，並顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="e4aa6-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="e4aa6-150">**名稱**：這是寄件者的電子郵件地址 (來自 **：新增轉寄使用者** ] view) 或寄件者的電子郵件網域 (**顯示下列的資料：新增轉寄網域** view) 。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="e4aa6-151">**轉送類型**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-151">**Forwarding type**</span></span>
- <span data-ttu-id="e4aa6-152">**收件者**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-152">**Recipient**</span></span>
- <span data-ttu-id="e4aa6-153">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-153">**Details**</span></span>
- <span data-ttu-id="e4aa6-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-154">**Count**</span></span>
- <span data-ttu-id="e4aa6-155">**開始日期**</span><span class="sxs-lookup"><span data-stu-id="e4aa6-155">**Start date**</span></span>
- <span data-ttu-id="e4aa6-156">**建議**：從這裡，您可以按一下 [Microsoft 365 系統管理中心] 中的 [管理使用者] 連結。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![「轉發修改」報告中新轉寄使用者 view 的詳細資料表格中的詳細資料。](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="e4aa6-158">若要回到 [報告] 視圖，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4aa6-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="e4aa6-159">Related topics</span></span>

<span data-ttu-id="e4aa6-160">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="e4aa6-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
