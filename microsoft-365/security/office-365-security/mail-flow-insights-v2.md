---
title: 安全性與合規性中心內的郵件流程深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 系統管理員可以深入瞭解安全性 & 規範中心內的郵件流程儀表板。
ms.openlocfilehash: 64bf1f2af967f841cd4c21be19fce914df136815
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630464"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="b2bd9-103">安全性與合規性中心內的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="b2bd9-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="b2bd9-104">系統管理員可以使用安全性 & 合規性中心內的郵件流程儀表板來探索趨勢、深入探索，並採取行動以修正組織中與郵件流程相關的問題。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their organization.</span></span>

<span data-ttu-id="b2bd9-105">郵件流程儀表板中提供的洞察力、報告和構件如下：</span><span class="sxs-lookup"><span data-stu-id="b2bd9-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="b2bd9-106">郵件流程圖報告</span><span class="sxs-lookup"><span data-stu-id="b2bd9-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="b2bd9-107">網域郵件流程狀態洞察力</span><span class="sxs-lookup"><span data-stu-id="b2bd9-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="b2bd9-108">SMTP 驗證用戶端報告</span><span class="sxs-lookup"><span data-stu-id="b2bd9-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="b2bd9-109">寄件者網域洞察力</span><span class="sxs-lookup"><span data-stu-id="b2bd9-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="b2bd9-110">未傳遞回報</span><span class="sxs-lookup"><span data-stu-id="b2bd9-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="b2bd9-111">非公認的網域報告</span><span class="sxs-lookup"><span data-stu-id="b2bd9-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="b2bd9-112">外寄和內送的郵件流程</span><span class="sxs-lookup"><span data-stu-id="b2bd9-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="b2bd9-113">佇列的警示和佇列</span><span class="sxs-lookup"><span data-stu-id="b2bd9-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="b2bd9-114">自動轉寄訊息的報告</span><span class="sxs-lookup"><span data-stu-id="b2bd9-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="b2bd9-115">郵件迴圈深入解析</span><span class="sxs-lookup"><span data-stu-id="b2bd9-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="b2bd9-116">緩慢的郵件流程規則深入解析</span><span class="sxs-lookup"><span data-stu-id="b2bd9-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="b2bd9-117">查看郵件流程儀表板所需的許可權</span><span class="sxs-lookup"><span data-stu-id="b2bd9-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="b2bd9-118">您可以在郵件流程儀表板上進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b2bd9-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="b2bd9-119">**全域系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-119">Members of the **global administrator** role.</span></span>

- <span data-ttu-id="b2bd9-120">**Exchange 系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-120">Members of **Exchange administrator** role.</span></span>

- <span data-ttu-id="b2bd9-121">安全性 & 合規性中心內的**郵件流程系統管理員角色**的成員。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="b2bd9-122">如果此角色明確指派給非全域管理員或 Exchange 系統管理員角色成員的使用者：</span><span class="sxs-lookup"><span data-stu-id="b2bd9-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="b2bd9-123">使用者必須直接登入安全性 & 合規性中心[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-123">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="b2bd9-124">使用者只具有郵件流程儀表板的唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="b2bd9-125">使用者將無法存取 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-125">The user won't have access to the Microsoft 365 admin center.</span></span>

<span data-ttu-id="b2bd9-126">如需全域系統管理員角色的詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-126">For more information about the global administrator role, see [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="b2bd9-127">如需將安全性 & 規範中心角色指派給使用者的詳細資訊，請參閱[授與使用者存取安全性 & 規範中心](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="b2bd9-128">哪裡可以找到郵件流程儀表板</span><span class="sxs-lookup"><span data-stu-id="b2bd9-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="b2bd9-129">移至安全性 & 合規性中心， [https://protection.office.com](https://protection.office.com)網址為。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="b2bd9-130">展開 [**郵件流程**]，然後選取 [**儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="b2bd9-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![安全性 & 規範中心內的郵件流程儀表板](../../media/mail-flow-dashboard-v2.png)
