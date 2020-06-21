---
title: 上層網域郵件流程狀態深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解安全性 & 規範中心的郵件流程儀表板中的最上層網域郵件流程狀態。
ms.openlocfilehash: 22b0f8cefe8baacac682550126de55dcbf880d73
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818588"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="34268-103">上層網域郵件流程狀態深入解析</span><span class="sxs-lookup"><span data-stu-id="34268-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="34268-104">**最上層的網域郵件流程狀態**真知灼見可讓您在郵件流程方面，為您組織的網域提供目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="34268-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="34268-105">這種洞察力可協助您識別及疑難排解發生***郵件流程影響***問題的網域（例如，無法接收外部電子郵件），尤其是網域到期或具有不正確 MX 記錄的網域。</span><span class="sxs-lookup"><span data-stu-id="34268-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![安全性 & 規範中心內郵件流程儀表板中的最上層網域流程狀態洞察力](../../media/domain-mail-flow-status-selected.png)

<span data-ttu-id="34268-107">當您按一下真知灼見中的 [**查看詳細資料**] 時，會出現一個快顯視窗，顯示每個網域狀態的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="34268-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="34268-108">網域的綠色核取記號表示目前的 MX 記錄（當您流覽至 [郵件流程深入儀表板]）與我們記錄的值相符，而且該網域已于過去兩小時內收到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="34268-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="34268-109">網域的紅色 x 表示 MX 記錄已變更，而且在過去6小時內，該網域未收到任何電子郵件。</span><span class="sxs-lookup"><span data-stu-id="34268-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="34268-110">這可能表示您的網域已到期，或 MX 記錄的更新錯誤。</span><span class="sxs-lookup"><span data-stu-id="34268-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="34268-111">請洽詢網域註冊機構或 DNS 主機服務，以查看網域是否已過期，或網域的 MX 記錄是否不正確。</span><span class="sxs-lookup"><span data-stu-id="34268-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![最上層網域流程狀態洞察力中的詳細資料快顯視窗](../../media/domain-mail-flow-status-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="34268-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="34268-113">Related topics</span></span>

<span data-ttu-id="34268-114">如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="34268-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
