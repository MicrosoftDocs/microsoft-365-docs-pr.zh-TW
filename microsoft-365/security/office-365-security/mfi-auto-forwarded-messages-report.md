---
title: 自動轉寄訊息深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 系統管理員可以在安全性 & 合規性中心的郵件流程儀表板中瞭解自動轉寄的郵件報告。
ms.openlocfilehash: e9e3a0159671dd4ce62f4fa0b07b7162807fe0e6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949853"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="4af0d-103">在安全性 & 規範中心內，自動轉寄的郵件會深入瞭解</span><span class="sxs-lookup"><span data-stu-id="4af0d-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="4af0d-104">在[Security & 合規性中心](https://protection.office.com)的[郵件流程儀表板](mail-flow-insights-v2.md)中，可洞察的**自動轉寄郵件**會顯示自動從您的組織轉送到外部網域中收件者之郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4af0d-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![安全性 & 規範中心內自動轉寄的郵件小工具](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="4af0d-106">自動轉寄的郵件詳細資料</span><span class="sxs-lookup"><span data-stu-id="4af0d-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="4af0d-107">當您按一下小工具中的郵件數目時，會出現一個彈出窗格，顯示自動轉寄郵件的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="4af0d-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="4af0d-108">透過**轉送方法自動轉寄的郵件**：</span><span class="sxs-lookup"><span data-stu-id="4af0d-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="4af0d-109">**依郵件流程規則**</span><span class="sxs-lookup"><span data-stu-id="4af0d-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="4af0d-110">**依收件匣規則**</span><span class="sxs-lookup"><span data-stu-id="4af0d-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="4af0d-111">**透過 SMTP 轉送**</span><span class="sxs-lookup"><span data-stu-id="4af0d-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="4af0d-112">有關詳細資訊，請查看 [轉接報告](view-mail-flow-reports.md#forwarding-report) 的連結。</span><span class="sxs-lookup"><span data-stu-id="4af0d-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="4af0d-113">**依網域和使用者自動轉寄郵件**：</span><span class="sxs-lookup"><span data-stu-id="4af0d-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="4af0d-114">**前5個網域會轉寄至**</span><span class="sxs-lookup"><span data-stu-id="4af0d-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="4af0d-115">\*\*新的網域 (上周) \*\*</span><span class="sxs-lookup"><span data-stu-id="4af0d-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="4af0d-116">**前5個轉接使用者**</span><span class="sxs-lookup"><span data-stu-id="4af0d-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="4af0d-117">\*\*新使用者 (上周) \*\*</span><span class="sxs-lookup"><span data-stu-id="4af0d-117">**New users (last week)**</span></span>
  - <span data-ttu-id="4af0d-118">有關詳細資訊，請查看「轉寄 [修改」報告](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 的連結。</span><span class="sxs-lookup"><span data-stu-id="4af0d-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![安全性 & 規範中心內自動轉寄郵件報告的詳細資料彈出報告](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="4af0d-120">深入資訊</span><span class="sxs-lookup"><span data-stu-id="4af0d-120">Insights</span></span>

<span data-ttu-id="4af0d-121">這兩種洞察力是根據報表資料產生的：</span><span class="sxs-lookup"><span data-stu-id="4af0d-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="4af0d-122">新增使用者轉送電子郵件</span><span class="sxs-lookup"><span data-stu-id="4af0d-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="4af0d-123">轉寄電子郵件的新網域</span><span class="sxs-lookup"><span data-stu-id="4af0d-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="4af0d-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="4af0d-124">See also</span></span>

<span data-ttu-id="4af0d-125">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="4af0d-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
