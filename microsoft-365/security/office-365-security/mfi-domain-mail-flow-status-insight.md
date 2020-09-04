---
title: 郵件流程儀表板中的最上層網域郵件流程狀態洞察力
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
description: 系統管理員可以瞭解如何使用安全性 & 規範中心內郵件流程儀表板中的最上層網域郵件流程狀態，來疑難排解與電子郵件網域中的 MX 記錄相關的郵件流程問題。
ms.openlocfilehash: 34b80bee48bd91524fbd95961c473f50fbe394b7
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358309"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="5655a-103">安全性 & 規範中心內的最上層網域郵件流程狀態洞察力</span><span class="sxs-lookup"><span data-stu-id="5655a-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="5655a-104">[安全性 & 合規性中心](https://protection.office.com)內的[郵件流程儀表板](mail-flow-insights-v2.md)中的**最上層網域郵件流程狀態**，可讓您在郵件流程方面，為您組織的網域提供目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="5655a-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="5655a-105">這種洞察力可協助您識別及疑難排解發生 ***郵件流程影響*** 問題的網域 (例如，無法接收外部電子郵件) ，尤其是網域到期或具有不正確 MX 記錄的網域。</span><span class="sxs-lookup"><span data-stu-id="5655a-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![安全性 & 規範中心內郵件流程儀表板中的上方網域流程狀態構件](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="5655a-107">當您按一下小工具中的 [ **查看詳細資料** ] 時，會出現一個 **網域狀態** 快顯視窗，顯示每個網域狀態的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="5655a-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="5655a-108">**網域**</span><span class="sxs-lookup"><span data-stu-id="5655a-108">**Domain**</span></span>
- <span data-ttu-id="5655a-109">**先前的 MX 記錄**</span><span class="sxs-lookup"><span data-stu-id="5655a-109">**Previous MX record**</span></span>
- <span data-ttu-id="5655a-110">**目前的 MX 記錄**</span><span class="sxs-lookup"><span data-stu-id="5655a-110">**Current MX record**</span></span>
- <span data-ttu-id="5655a-111">**電子郵件接收狀態**</span><span class="sxs-lookup"><span data-stu-id="5655a-111">**Email receiving status**</span></span>
- <span data-ttu-id="5655a-112">**網域狀態**：綠色核取記號表示在您按一下小工具時 (目前的 MX 記錄，) 符合我們記錄的值，而且該網域已于過去的兩個小時內收到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5655a-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="5655a-113">紅色 X 表示 MX 記錄已變更，且在過去6小時內，該網域未收到任何電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5655a-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="5655a-114">這可能表示您的網域已到期，或 MX 記錄的更新錯誤。</span><span class="sxs-lookup"><span data-stu-id="5655a-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="5655a-115">請洽詢網域註冊機構或 DNS 主機服務，以查看網域是否已過期，或網域的 MX 記錄是否不正確。</span><span class="sxs-lookup"><span data-stu-id="5655a-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="5655a-116">您可以按一下 [ **View more** ]，以查看更多網域的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="5655a-116">You can click **View more** to see the same information for more domains.</span></span>

![最上層網域郵件流程狀態洞察力中的詳細資料快顯視窗](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="5655a-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="5655a-118">Related topics</span></span>

<span data-ttu-id="5655a-119">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="5655a-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
