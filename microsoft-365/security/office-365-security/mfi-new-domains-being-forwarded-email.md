---
title: 轉寄的新網域電子郵件深入解析
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以瞭解如何使用「安全性 & 規範中心」中郵件流程儀表板中的新網域，以調查他們的使用者是否要將郵件轉寄給已永不轉寄的外部網域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f3a5f125a045176f152ccd079ebe7f7e40bc39f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203455"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="0b740-103">在安全性 & 規範中心轉寄電子郵件的新網域</span><span class="sxs-lookup"><span data-stu-id="0b740-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0b740-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="0b740-104">**Applies to**</span></span>
- [<span data-ttu-id="0b740-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0b740-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0b740-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="0b740-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0b740-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b740-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0b740-108">將電子郵件轉寄給特定網域中的外部收件者，有一些有效的商業原因。</span><span class="sxs-lookup"><span data-stu-id="0b740-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="0b740-109">不過，當組織中的使用者突然開始將郵件轉送至一個網域，而您的組織中沒有任何人曾經轉送郵件給 (新網域) 時，這是可疑的。</span><span class="sxs-lookup"><span data-stu-id="0b740-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="0b740-110">這種情況可能表示使用者帳戶遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="0b740-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="0b740-111">如果您懷疑帳戶已遭破壞，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="0b740-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="0b740-112">當您組織中的使用者將郵件轉寄給新網域時，在 [安全性 & 合規性中心](https://protection.office.com)**轉寄的新網域** 會通知您。</span><span class="sxs-lookup"><span data-stu-id="0b740-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="0b740-113">這種洞察力只會在偵測到問題時出現，而且會出現在 [ [轉接回報報告](view-mail-flow-reports.md#forwarding-report) ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="0b740-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![轉寄的新網域電子郵件深入解析](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="0b740-115">當您按一下該小工具時，會出現一個快顯視窗，您可以在其中找到有關轉寄郵件的詳細資訊，包括回 [轉送報告](view-mail-flow-reports.md#forwarding-report)的連結。</span><span class="sxs-lookup"><span data-stu-id="0b740-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![在按一下要轉寄電子郵件的新網域後，出現的詳細資料浮出控制項](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="0b740-117">您也可以在 [ (**報表** 儀表板] 或 [) ] 的 [**熱門洞察力 & 建議**] 區域中按一下 [**全部查看**] 之後，取得此詳細資料頁面 \>  <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="0b740-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="0b740-118">若要防止自動將郵件轉送到外部網域，請設定部分或所有外部網域的遠端網域。</span><span class="sxs-lookup"><span data-stu-id="0b740-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="0b740-119">如需詳細資訊，請參閱[管理 Exchange Online 中的遠端網域](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="0b740-119">For more information, see [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0b740-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="0b740-120">Related topics</span></span>

<span data-ttu-id="0b740-121">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="0b740-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>