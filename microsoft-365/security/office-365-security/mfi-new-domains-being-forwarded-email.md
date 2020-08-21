---
title: 轉寄的新網域電子郵件深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以瞭解如何使用現代 Exchange 系統管理中心中已轉寄的電子郵件功能，調查組織中的使用者將郵件轉寄給已永不轉寄的外部網域。
ms.openlocfilehash: 0b4cd0490feebc8e05deb889b3cf54e1ea9f5928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826926"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="20c1f-103">在安全性 & 規範中心轉寄電子郵件的新網域</span><span class="sxs-lookup"><span data-stu-id="20c1f-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="20c1f-104">雖然您可以將電子郵件轉寄至特定網域中的外部收件者，但在組織中的使用者突然開始將郵件轉送至外部網域，而組織中的使用者卻沒有任何人轉寄郵件給這些網域，但在 (新的網域) 之前，這是可疑的業務原因。</span><span class="sxs-lookup"><span data-stu-id="20c1f-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="20c1f-105">這種情況可能表示使用者帳戶遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="20c1f-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="20c1f-106">如果您懷疑帳戶已遭破壞，請參閱 [回應遭到破壞的電子郵件帳戶](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)。</span><span class="sxs-lookup"><span data-stu-id="20c1f-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="20c1f-107">當您組織中的使用者將郵件轉送至新網域時， **正轉送的新網域** 會告訴您。</span><span class="sxs-lookup"><span data-stu-id="20c1f-107">The **New domains being forwarded email** insight notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="20c1f-108">這種洞察力只會在偵測到問題時出現，而且會出現在 [ [轉接回報報告](view-mail-flow-reports.md#forwarding-report) ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="20c1f-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![轉寄的新網域電子郵件深入解析](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="20c1f-110">當您按一下該小工具時，會出現一個快顯視窗，您可以在其中找到有關轉寄郵件的詳細資訊，包括回 [轉送報告](view-mail-flow-reports.md#forwarding-report)的連結。</span><span class="sxs-lookup"><span data-stu-id="20c1f-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![在按一下要轉寄電子郵件的新網域後，出現的詳細資料浮出控制項](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="20c1f-112">您也可以在 [ (**報表**儀表板] 或 [) ] 的 [**熱門洞察力 & 建議**] 區域中按一下 [**全部查看**] 之後，取得此詳細資料頁面 \> **Dashboard** <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="20c1f-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="20c1f-113">若要防止自動將郵件轉送到外部網域，請設定部分或所有外部網域的遠端網域。</span><span class="sxs-lookup"><span data-stu-id="20c1f-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="20c1f-114">如需詳細資訊，請參閱 [管理 Exchange Online 中的遠端網域](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="20c1f-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="20c1f-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="20c1f-115">Related topics</span></span>

<span data-ttu-id="20c1f-116">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="20c1f-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
