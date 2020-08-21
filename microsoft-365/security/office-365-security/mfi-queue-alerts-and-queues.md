---
title: 在郵件流程儀表板中佇列洞察力
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 系統管理員可以瞭解如何使用 Security & 合規性中心內郵件流程儀表板中的 [佇列] 小工具，以透過輸出連接器監視其內部部署或夥伴組織的失敗郵件流程。
ms.openlocfilehash: 79523533306e847988fa0d4e2dd70eca22f7c76c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826902"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="cbe32-103">在安全性 & 規範中心內佇列的洞察力</span><span class="sxs-lookup"><span data-stu-id="cbe32-103">Queues insight in the Security & Compliance Center</span></span>

<span data-ttu-id="cbe32-104">當郵件無法使用連接器從您的組織傳送至您的內部部署或夥伴電子郵件伺服器時，郵件會在 Microsoft 365 中佇列。</span><span class="sxs-lookup"><span data-stu-id="cbe32-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="cbe32-105">導致此狀況的常見範例如下：</span><span class="sxs-lookup"><span data-stu-id="cbe32-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="cbe32-106">連接器設定不正確。</span><span class="sxs-lookup"><span data-stu-id="cbe32-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="cbe32-107">您的內部部署環境中已有網路或防火牆變更。</span><span class="sxs-lookup"><span data-stu-id="cbe32-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="cbe32-108">Microsoft 365 會繼續重新嘗試傳遞24小時。</span><span class="sxs-lookup"><span data-stu-id="cbe32-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="cbe32-109">24小時後，郵件會到期，並且會傳回未傳遞回報中的寄件者 (也稱為 NDRs 或退回的郵件) 。</span><span class="sxs-lookup"><span data-stu-id="cbe32-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="cbe32-110">如果佇列中的電子郵件磁片區超過預先定義的臨界值 (預設值為200郵件) 中，則可在下列位置取得此資訊：</span><span class="sxs-lookup"><span data-stu-id="cbe32-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="cbe32-111">在安全性 & 合規性中心的[郵件流程儀表板](mail-flow-insights-v2.md)中，**佇列**的洞察力。</span><span class="sxs-lookup"><span data-stu-id="cbe32-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="cbe32-112">如需詳細資訊，請參閱本主題中的 [郵件流程儀表板區段中的佇列洞察力](#queues-insight-in-the-mail-flow-dashboard) 。</span><span class="sxs-lookup"><span data-stu-id="cbe32-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="cbe32-113">警示會 **顯示在 [** [安全性 & 規範中心](https://protection.office.com) ] 中的 [提醒] 儀表板 (**警示** \> **儀表板** ] 或 [ <https://protection.office.com/alertsdashboard>) ]。</span><span class="sxs-lookup"><span data-stu-id="cbe32-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![安全性 & 規範中心內的警示儀表板中的最近警示](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="cbe32-115">系統管理員會根據名為 **Messages**的預設警示原則設定，收到電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="cbe32-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="cbe32-116">若要設定此警示的通知設定，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="cbe32-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="cbe32-117">如需警示原則的詳細資訊，請參閱 [安全性 & 合規性中心中的警示原則](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe32-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="cbe32-118">自訂佇列警示</span><span class="sxs-lookup"><span data-stu-id="cbe32-118">Customize queue alerts</span></span>

1. <span data-ttu-id="cbe32-119">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，移至 [ **警示** \> **警示原則** ] 或 [開啟] <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="cbe32-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="cbe32-120">在 [ **警示原則** ] 頁面上，尋找並選取名為 Messages 的原則已 **延遲**。</span><span class="sxs-lookup"><span data-stu-id="cbe32-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="cbe32-121">在 **郵件中已延遲** 開啟的浮出的浮出狀態，您可以開啟或關閉提醒並設定通知設定。</span><span class="sxs-lookup"><span data-stu-id="cbe32-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![郵件已延遲警示原則詳細資訊安全 & 規範中心](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="cbe32-123">**狀態**：您可以開啟或關閉提醒。</span><span class="sxs-lookup"><span data-stu-id="cbe32-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="cbe32-124">**電子郵件** 收件者和 **每日通知限制**：按一下 [ **編輯** ] 以設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="cbe32-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="cbe32-125">若要設定通知設定，請按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="cbe32-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="cbe32-126">在出現的 [ **編輯原則** ] 飛入中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="cbe32-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cbe32-127">**傳送電子郵件通知**：預設值為 on。</span><span class="sxs-lookup"><span data-stu-id="cbe32-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="cbe32-128">**電子郵件**收件者：預設值為 **TenantAdmins**。</span><span class="sxs-lookup"><span data-stu-id="cbe32-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="cbe32-129">**每日通知限制**：預設值為 **無限制**。</span><span class="sxs-lookup"><span data-stu-id="cbe32-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="cbe32-130">**臨界**值：預設值為200。</span><span class="sxs-lookup"><span data-stu-id="cbe32-130">**Threshold**: The default value is 200.</span></span>

   ![郵件中的通知設定已延遲警示原則詳細資訊安全 & 規範中心](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="cbe32-132">完成後，按一下 [ **儲存** 並 **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="cbe32-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="cbe32-133">在郵件流程儀表板中佇列洞察力</span><span class="sxs-lookup"><span data-stu-id="cbe32-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="cbe32-134">即使已排入佇列的郵件磁片區未超出臨界值並產生警示，您仍然可以使用[郵件流程儀表板](mail-flow-insights-v2.md)中的**佇列**洞察力，以查看佇列中超過一小時的郵件，並在佇列郵件數目變得太大之前採取動作。</span><span class="sxs-lookup"><span data-stu-id="cbe32-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![安全性 & 規範中心內的郵件流程儀表板中的佇列小工具](../../media/mfi-queues-widget.png)

<span data-ttu-id="cbe32-136">如果您按一下小工具上的郵件數目，則會出現佇列彈出的 **郵件** ，並顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="cbe32-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="cbe32-137">**佇列中郵件的數目**</span><span class="sxs-lookup"><span data-stu-id="cbe32-137">**Number of queued messages**</span></span>
- <span data-ttu-id="cbe32-138">**連接器名稱**：按一下連接器名稱可管理 Exchange 系統管理中心中的連接器 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="cbe32-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="cbe32-139">**佇列開始時間**</span><span class="sxs-lookup"><span data-stu-id="cbe32-139">**Queue started time**</span></span>
- <span data-ttu-id="cbe32-140">**已超過最舊的郵件**</span><span class="sxs-lookup"><span data-stu-id="cbe32-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="cbe32-141">**目的地伺服器**</span><span class="sxs-lookup"><span data-stu-id="cbe32-141">**Destination server**</span></span>
- <span data-ttu-id="cbe32-142">**最後一個 IP 位址**</span><span class="sxs-lookup"><span data-stu-id="cbe32-142">**Last IP address**</span></span>
- <span data-ttu-id="cbe32-143">**上一個錯誤**</span><span class="sxs-lookup"><span data-stu-id="cbe32-143">**Last error**</span></span>
- <span data-ttu-id="cbe32-144">**如何修正**：共有問題和解決方案可供使用。</span><span class="sxs-lookup"><span data-stu-id="cbe32-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="cbe32-145">如果 [ **立即修復它** ] 連結可用，請按一下它以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="cbe32-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="cbe32-146">否則，請按一下任何可用的連結，以取得有關錯誤及可能解決方案的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cbe32-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![按一下郵件流程儀表板中佇列洞察力之後的詳細資料](../../media/mfi-queues-details.png)

<span data-ttu-id="cbe32-148">在**郵件**的詳細資料中，按一下 [**查看佇列**] 後，就會顯示相同的飛入通知。</span><span class="sxs-lookup"><span data-stu-id="cbe32-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![郵件已延遲安全性 & 規範中心的警示詳細資料](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="cbe32-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cbe32-150">See also</span></span>

<span data-ttu-id="cbe32-151">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe32-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
