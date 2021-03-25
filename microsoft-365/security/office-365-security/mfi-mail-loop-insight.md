---
title: 修正可能的郵件迴圈深入解析
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全 & 規範中心內郵件流程儀表板中的 [修正可能的郵件迴圈洞察力]，識別並修正其組織中的郵件迴圈。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204561"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="31631-103">修正安全性 & 規範中心內可能的郵件迴圈洞察力</span><span class="sxs-lookup"><span data-stu-id="31631-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="31631-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="31631-104">**Applies to**</span></span>
- [<span data-ttu-id="31631-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="31631-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="31631-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="31631-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="31631-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31631-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="31631-108">郵件迴圈不正確，原因如下：</span><span class="sxs-lookup"><span data-stu-id="31631-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="31631-109">它們會浪費系統資源。</span><span class="sxs-lookup"><span data-stu-id="31631-109">They waste system resources.</span></span>
- <span data-ttu-id="31631-110">它們會消耗您組織的郵件磁片區配額。</span><span class="sxs-lookup"><span data-stu-id="31631-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="31631-111">它們會傳送令人困惑的未傳遞回報 (也稱為 NDRs 或退回郵件) 給原始郵件寄件者。</span><span class="sxs-lookup"><span data-stu-id="31631-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="31631-112">在您的組織中偵測到郵件迴圈時，在 [安全性 & 合規性中心](https://protection.office.com)的 [[郵件流程儀表板](mail-flow-insights-v2.md)] 中，**建議** 的郵件流程儀表板區域會通知您，以 **修正可能的郵件迴圈**。</span><span class="sxs-lookup"><span data-stu-id="31631-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="31631-113">這種洞察力只會在偵測到條件之後才會出現 (如果您沒有任何郵件迴圈，您就不會看到) 的洞察力。</span><span class="sxs-lookup"><span data-stu-id="31631-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![修正郵件流程儀表板中為您推薦的郵件流程規則的速度](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="31631-115">當您按一下小工具上的 [ **查看詳細資料** ] 時，會出現一個快顯視窗，包含詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="31631-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="31631-116">**網域**</span><span class="sxs-lookup"><span data-stu-id="31631-116">**Domain**</span></span>
- <span data-ttu-id="31631-117">**郵件數目**：您可以按一下 [ **View sample messages** ]，以查看受環路影響之郵件範例的 [郵件追蹤](message-trace-scc.md) 結果。</span><span class="sxs-lookup"><span data-stu-id="31631-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="31631-118">**網欄位型別**"，例如「授權」或「非授權」。</span><span class="sxs-lookup"><span data-stu-id="31631-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="31631-119">**MX 記錄**：主機 (的 **郵件伺服器**) 和網域的 MX 記錄 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="31631-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="31631-120">**迴圈原因** 和 **解決方法**：我們會找出最常見的郵件迴圈案例，並提供建議的動作來修正此迴圈。</span><span class="sxs-lookup"><span data-stu-id="31631-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![在 [修正可能的郵件迴圈真知灼見] 上按一下 [查看詳細資料] 後出現的詳細資料浮出](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="31631-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="31631-122">See also</span></span>

<span data-ttu-id="31631-123">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="31631-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
