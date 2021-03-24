---
title: 郵件流程儀表板中的未傳遞回報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用 [安全性 & 合規性中心內的郵件流程儀表板中的 [未傳遞詳細資料] 報告，以監視未傳遞回報中最常遇到的錯誤碼 (也稱為 NDRs 或退回的郵件) 來自組織中的寄件者。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057860"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="9b384-103">安全性 & 規範中心內的未傳遞回報</span><span class="sxs-lookup"><span data-stu-id="9b384-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9b384-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="9b384-104">**Applies to**</span></span>
- [<span data-ttu-id="9b384-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9b384-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9b384-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="9b384-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9b384-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b384-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9b384-108">在 [Security & 合規性中心](https://protection.office.com)的 [郵件流程儀表板](mail-flow-insights-v2.md)中，**未傳遞** 回報會顯示未傳遞回報中最常遇到的錯誤碼 (也稱為 NDRs 或退回的郵件) 針對您組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="9b384-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="9b384-109">此報告顯示 NDRs 的詳細資料，以便您能夠疑難排解電子郵件傳遞問題。</span><span class="sxs-lookup"><span data-stu-id="9b384-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![安全性 & 規範中心內郵件流程儀表板中的未傳遞回報小工具](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="9b384-111">未傳遞回報的報表檢視</span><span class="sxs-lookup"><span data-stu-id="9b384-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="9b384-112">按一下 [ **未傳遞** 回報] 小工具時，將會帶您前往 **未傳遞** 回報的報告。</span><span class="sxs-lookup"><span data-stu-id="9b384-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="9b384-113">依預設，會顯示所有錯誤碼的活動。</span><span class="sxs-lookup"><span data-stu-id="9b384-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="9b384-114">如果您按一下 [ **顯示資料**]，您可以從下拉式清單中選取特定的錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="9b384-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="9b384-115">如果您將滑鼠停留在特定色彩上 (錯誤碼) 在圖表中的某一天，您就會看到錯誤的郵件總數。</span><span class="sxs-lookup"><span data-stu-id="9b384-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![不接受的網域報告中的報表檢視](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="9b384-117">未傳遞回報的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="9b384-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="9b384-118">如果您按一下報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="9b384-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="9b384-119">**Date**</span><span class="sxs-lookup"><span data-stu-id="9b384-119">**Date**</span></span>
- <span data-ttu-id="9b384-120">**未傳遞回報碼**</span><span class="sxs-lookup"><span data-stu-id="9b384-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="9b384-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="9b384-121">**Count**</span></span>
- <span data-ttu-id="9b384-122">**範例郵件**：郵件 IDs 受影響郵件的範例。</span><span class="sxs-lookup"><span data-stu-id="9b384-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="9b384-123">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="9b384-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9b384-124">若要將特定日期範圍的報告傳送至一或多個收件者，請按一下 [ **要求下載**]。</span><span class="sxs-lookup"><span data-stu-id="9b384-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="9b384-125">當您選取表格中的一列時，會出現一個快顯視窗，其中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="9b384-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="9b384-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="9b384-126">**Date**</span></span>
- <span data-ttu-id="9b384-127">**未傳遞回報碼**：您可以按一下連結，以尋找特定錯誤碼的原因和解決方案的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9b384-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="9b384-128">**Count**</span><span class="sxs-lookup"><span data-stu-id="9b384-128">**Count**</span></span>
- <span data-ttu-id="9b384-129">**範例郵件**：您可以按一下 [ **View sample messages** ]，以查看受影響郵件之範例的 [郵件追蹤](message-trace-scc.md) 結果。</span><span class="sxs-lookup"><span data-stu-id="9b384-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![在未傳遞回報中，選取 [詳細資料表格] 視圖中的列之後的詳細資料浮出控制項](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="9b384-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="9b384-131">Related topics</span></span>

<span data-ttu-id="9b384-132">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="9b384-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
