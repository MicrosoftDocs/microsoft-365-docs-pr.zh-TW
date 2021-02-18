---
title: 自動轉寄訊息深入解析
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 系統管理員可以在安全性 & 合規性中心的郵件流程儀表板中瞭解自動轉寄的郵件報告。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290630"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="9dad0-103">在安全性 & 規範中心內，自動轉寄的郵件會深入瞭解</span><span class="sxs-lookup"><span data-stu-id="9dad0-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9dad0-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="9dad0-104">**Applies to**</span></span>
- [<span data-ttu-id="9dad0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9dad0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9dad0-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="9dad0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9dad0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9dad0-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="9dad0-108">在 [Security & 合規性中心](https://protection.office.com)的 [郵件流程儀表板](mail-flow-insights-v2.md)中，可洞察的 **自動轉寄郵件** 會顯示自動從您的組織轉送到外部網域中收件者之郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9dad0-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![安全性 & 規範中心內自動轉寄的郵件小工具](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="9dad0-110">自動轉寄的郵件詳細資料</span><span class="sxs-lookup"><span data-stu-id="9dad0-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="9dad0-111">當您按一下小工具中的郵件數目時，會出現一個彈出窗格，顯示自動轉寄郵件的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="9dad0-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="9dad0-112">透過 **轉送方法自動轉寄的郵件**：</span><span class="sxs-lookup"><span data-stu-id="9dad0-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="9dad0-113">**依郵件流程規則**</span><span class="sxs-lookup"><span data-stu-id="9dad0-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="9dad0-114">**依收件匣規則**</span><span class="sxs-lookup"><span data-stu-id="9dad0-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="9dad0-115">透過 **SMTP** 轉寄：此方法會指出系統管理員可以在信箱上設定的自動轉寄，如 [設定信箱的電子郵件](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)轉寄中所述。</span><span class="sxs-lookup"><span data-stu-id="9dad0-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="9dad0-116">有關詳細資訊，請查看 [轉接報告](view-mail-flow-reports.md#forwarding-report) 的連結。</span><span class="sxs-lookup"><span data-stu-id="9dad0-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="9dad0-117">**依網域和使用者自動轉寄郵件**：</span><span class="sxs-lookup"><span data-stu-id="9dad0-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="9dad0-118">**前5個網域會轉寄至**</span><span class="sxs-lookup"><span data-stu-id="9dad0-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="9dad0-119">**新的網域 (上周)**</span><span class="sxs-lookup"><span data-stu-id="9dad0-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="9dad0-120">**前5個轉接使用者**</span><span class="sxs-lookup"><span data-stu-id="9dad0-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="9dad0-121">**新使用者 (上周)**</span><span class="sxs-lookup"><span data-stu-id="9dad0-121">**New users (last week)**</span></span>
  - <span data-ttu-id="9dad0-122">有關詳細資訊，請查看「轉寄 [修改」報告](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 的連結。</span><span class="sxs-lookup"><span data-stu-id="9dad0-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![安全性 & 規範中心內自動轉寄郵件報告的詳細資料彈出報告](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="9dad0-124">深入解析</span><span class="sxs-lookup"><span data-stu-id="9dad0-124">Insights</span></span>

<span data-ttu-id="9dad0-125">這兩種洞察力是根據報表資料產生的：</span><span class="sxs-lookup"><span data-stu-id="9dad0-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="9dad0-126">新增使用者轉送電子郵件</span><span class="sxs-lookup"><span data-stu-id="9dad0-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="9dad0-127">轉寄電子郵件的新網域</span><span class="sxs-lookup"><span data-stu-id="9dad0-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="9dad0-128">請參閱</span><span class="sxs-lookup"><span data-stu-id="9dad0-128">See also</span></span>

<span data-ttu-id="9dad0-129">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="9dad0-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
