---
title: 佇列警示和佇列
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 系統管理員可以在安全性 & 規範中心的郵件流程儀表板中瞭解佇列警示和佇列。
ms.openlocfilehash: 7bb103bad89ee39991a5c16d7101ab4658842479
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635181"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="423f0-103">佇列警示和佇列</span><span class="sxs-lookup"><span data-stu-id="423f0-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="423f0-104">佇列警示</span><span class="sxs-lookup"><span data-stu-id="423f0-104">Queue alerts</span></span>

<span data-ttu-id="423f0-105">當郵件無法使用連接器從您的組織傳送至您的內部部署或夥伴電子郵件伺服器時，郵件會在 Office 365 中排入佇列。</span><span class="sxs-lookup"><span data-stu-id="423f0-105">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="423f0-106">導致此狀況的常見範例如下：</span><span class="sxs-lookup"><span data-stu-id="423f0-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="423f0-107">連接器設定不正確。</span><span class="sxs-lookup"><span data-stu-id="423f0-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="423f0-108">您的內部部署環境中已有網路或防火牆變更。</span><span class="sxs-lookup"><span data-stu-id="423f0-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="423f0-109">Microsoft 365 會繼續重新嘗試傳遞24小時。</span><span class="sxs-lookup"><span data-stu-id="423f0-109">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="423f0-110">24小時後，郵件會到期，並且會傳回至未傳遞回報（也稱為 NDRs 或退回的郵件）中的寄件者。</span><span class="sxs-lookup"><span data-stu-id="423f0-110">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="423f0-111">若佇列中的電子郵件磁片區超過預先定義的臨界值（預設值為2000訊息），則會在郵件流程儀表板中的**最近的提醒**中使用提醒，系統管理員會收到電子郵件通知（傳送到他們的其他電子郵件地址）。</span><span class="sxs-lookup"><span data-stu-id="423f0-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="423f0-112">若要設定警示閾值、每日通知限制，以及（或）警示的收件者，請參閱下方的 [**自訂佇列提醒**] 區段。</span><span class="sxs-lookup"><span data-stu-id="423f0-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![在安全性 & 合規性中心的郵件流程儀表板的 [最近的提醒] 區域中佇列警示](../../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="423f0-114">自訂佇列警示</span><span class="sxs-lookup"><span data-stu-id="423f0-114">Customize queue alerts</span></span>

<span data-ttu-id="423f0-115">郵件流程 insights 建立名為「郵件」的警示**原則，已\*\*\*\*延遲** **（在下列** \>範例螢幕擷取畫面中）的 [**傳送電子郵件通知**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="423f0-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="423f0-116">您可以按一下原則來修改閾值和警示收件者。</span><span class="sxs-lookup"><span data-stu-id="423f0-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![提醒導覽](../../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="423f0-118">您將會看到新的原則資訊 blade，現在您可以按一下 [**編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="423f0-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![編輯原則](../../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="423f0-120">資訊 blade 會變更為**編輯原則**。</span><span class="sxs-lookup"><span data-stu-id="423f0-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="423f0-121">您現在可以變更提醒電子郵件的收件者、每天傳送的通知數目限制，以及觸發警示的最小臨界值（200或以上）。</span><span class="sxs-lookup"><span data-stu-id="423f0-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![編輯原則 Blade](../../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="423f0-123">佇列警示詳細資料</span><span class="sxs-lookup"><span data-stu-id="423f0-123">Queue alert details</span></span>

<span data-ttu-id="423f0-124">當您按一下警示時，警示詳細資料會出現在飛入窗格中。</span><span class="sxs-lookup"><span data-stu-id="423f0-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![在安全性 & 規範中心的郵件流程儀表板的 [最近的提醒] 區域中，選取佇列警示。](../../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![安全性 & 規範中心內的佇列警示詳細資料浮出](../../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="423f0-127">您可以按一下 [警示詳細資料] 中的 [**查看佇列**]，以查看佇列詳細資料、問題，以及新飛入窗格中可用之修正程式的連結。</span><span class="sxs-lookup"><span data-stu-id="423f0-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![安全性 & 規範中心內的佇列警示詳細資料浮出](../../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![在 [警示詳細資料] 中查看佇列](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="423f0-130">佇列</span><span class="sxs-lookup"><span data-stu-id="423f0-130">Queues</span></span>

<span data-ttu-id="423f0-131">即使佇列郵件磁片區未超出臨界值，仍然可以使用郵件流程儀表板的 [**佇列**] 區域，以查看已排入佇列的郵件超過一小時。</span><span class="sxs-lookup"><span data-stu-id="423f0-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="423f0-132">您可以使用 [**佇列**] 區域來監視佇列中的郵件數目（值為0表示郵件流程是正常的），並在佇列郵件數目變得太大之前採取動作。</span><span class="sxs-lookup"><span data-stu-id="423f0-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![安全性 & 規範中心內的郵件流程儀表板中的佇列](../../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="423f0-134">當您按一下**佇列**中已排入佇列的郵件數目時，佇列詳細資料及如何修正問題的指導將會出現在飛入窗格中（在佇列警示的詳細資料中，按一下 [**查看佇列**] 後出現的相同浮出）。</span><span class="sxs-lookup"><span data-stu-id="423f0-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![佇列詳細資料](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="423f0-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="423f0-136">See also</span></span>

<span data-ttu-id="423f0-137">如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="423f0-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
