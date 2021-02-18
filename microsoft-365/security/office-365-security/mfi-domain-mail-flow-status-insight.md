---
title: 郵件流程儀表板中的最上層網域郵件流程狀態洞察力
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
description: 系統管理員可以瞭解如何使用安全性 & 規範中心內郵件流程儀表板中的最上層網域郵件流程狀態，來疑難排解與其 MX 記錄相關的郵件流程問題。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ecda78047384a581a1043d0049b8dd25fadbe27
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290618"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="e1112-103">安全性 & 規範中心內的最上層網域郵件流程狀態洞察力</span><span class="sxs-lookup"><span data-stu-id="e1112-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e1112-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="e1112-104">**Applies to**</span></span>
- [<span data-ttu-id="e1112-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e1112-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e1112-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="e1112-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e1112-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1112-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e1112-108">[安全性 & 合規性中心](https://protection.office.com)內的 [郵件流程儀表板](mail-flow-insights-v2.md)中的 **最上層網域郵件流程狀態**，可讓您在組織中取得目前的郵件流程狀態。</span><span class="sxs-lookup"><span data-stu-id="e1112-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="e1112-109">這種洞察力可協助您識別及疑難排解出現 ***郵件流程*** 問題的網域。</span><span class="sxs-lookup"><span data-stu-id="e1112-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="e1112-110">例如，網域無法接收外部電子郵件，因為網域已到期或網域的 MX 記錄不正確。</span><span class="sxs-lookup"><span data-stu-id="e1112-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![安全性 & 規範中心內郵件流程儀表板中的上方網域流程狀態構件](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="e1112-112">當您按一下小工具中的 [ **查看詳細資料** ] 時，會出現一個 **網域狀態** 快顯視窗，顯示每個網域狀態的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="e1112-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="e1112-113">**網域**</span><span class="sxs-lookup"><span data-stu-id="e1112-113">**Domain**</span></span>
- <span data-ttu-id="e1112-114">**先前的 MX 記錄**</span><span class="sxs-lookup"><span data-stu-id="e1112-114">**Previous MX record**</span></span>
- <span data-ttu-id="e1112-115">**目前的 MX 記錄**</span><span class="sxs-lookup"><span data-stu-id="e1112-115">**Current MX record**</span></span>
- <span data-ttu-id="e1112-116">**電子郵件接收狀態**</span><span class="sxs-lookup"><span data-stu-id="e1112-116">**Email receiving status**</span></span>
- <span data-ttu-id="e1112-117">**網域狀態**：綠色核取記號表示在您按下該小工具時 (的目前 MX 記錄，) 符合我們記錄的值，而且該網域已于過去的兩個小時內收到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e1112-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="e1112-118">紅色 X 表示 MX 記錄已變更，而且在過去6個小時內，該網域未收到任何電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e1112-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="e1112-119">這可能表示您的網域已到期，或 MX 記錄的更新錯誤。</span><span class="sxs-lookup"><span data-stu-id="e1112-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="e1112-120">請洽詢網域註冊機構或 DNS 主機服務，以查看網域是否已過期，或網域的 MX 記錄是否不正確。</span><span class="sxs-lookup"><span data-stu-id="e1112-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="e1112-121">您可以按一下 [ **View more** ]，以查看更多網域的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="e1112-121">You can click **View more** to see the same information for more domains.</span></span>

![最上層網域郵件流程狀態洞察力中的詳細資料快顯視窗](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="e1112-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="e1112-123">See also</span></span>

<span data-ttu-id="e1112-124">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="e1112-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
