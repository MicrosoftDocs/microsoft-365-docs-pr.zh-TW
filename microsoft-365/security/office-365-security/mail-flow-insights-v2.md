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
ms.openlocfilehash: 792fb07c1faae54696354619347d1eb5367d45b2
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081433"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="1299a-103">安全性與合規性中心內的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="1299a-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="1299a-104">系統管理員可以使用安全性 & 合規性中心內的郵件流程儀表板來探索趨勢、深入探索，並採取行動以修正 Office 365 組織中與郵件流程相關的問題。</span><span class="sxs-lookup"><span data-stu-id="1299a-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="1299a-105">郵件流程儀表板中提供的洞察力、報告和構件如下：</span><span class="sxs-lookup"><span data-stu-id="1299a-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="1299a-106">郵件流程圖報告</span><span class="sxs-lookup"><span data-stu-id="1299a-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="1299a-107">網域郵件流程狀態洞察力</span><span class="sxs-lookup"><span data-stu-id="1299a-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="1299a-108">SMTP 驗證用戶端報告</span><span class="sxs-lookup"><span data-stu-id="1299a-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="1299a-109">寄件者網域洞察力</span><span class="sxs-lookup"><span data-stu-id="1299a-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="1299a-110">未傳遞回報</span><span class="sxs-lookup"><span data-stu-id="1299a-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="1299a-111">非公認的網域報告</span><span class="sxs-lookup"><span data-stu-id="1299a-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="1299a-112">外寄和內送的郵件流程</span><span class="sxs-lookup"><span data-stu-id="1299a-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="1299a-113">佇列的警示和佇列</span><span class="sxs-lookup"><span data-stu-id="1299a-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="1299a-114">自動轉寄訊息的報告</span><span class="sxs-lookup"><span data-stu-id="1299a-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="1299a-115">郵件迴圈深入解析</span><span class="sxs-lookup"><span data-stu-id="1299a-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="1299a-116">緩慢的郵件流程規則深入解析</span><span class="sxs-lookup"><span data-stu-id="1299a-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="1299a-117">查看郵件流程儀表板所需的許可權</span><span class="sxs-lookup"><span data-stu-id="1299a-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="1299a-118">您可以在郵件流程儀表板上進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="1299a-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="1299a-119">**Office 365 全域系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="1299a-119">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="1299a-120">**Office 365 Exchange 系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="1299a-120">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="1299a-121">安全性 & 合規性中心內的**郵件流程系統管理員角色**的成員。</span><span class="sxs-lookup"><span data-stu-id="1299a-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="1299a-122">如果此角色明確指派給非全域管理員或 Exchange 系統管理員角色成員的使用者：</span><span class="sxs-lookup"><span data-stu-id="1299a-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="1299a-123">使用者必須直接登入安全性 & 合規性中心[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="1299a-123">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="1299a-124">使用者只具有郵件流程儀表板的唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="1299a-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="1299a-125">使用者將無法存取 Office 365 管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="1299a-125">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="1299a-126">如需有關 Office 365 全域系統管理員角色的詳細資訊，請參閱[關於 office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="1299a-126">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="1299a-127">如需將安全性 & 規範中心角色指派給使用者的詳細資訊，請參閱[授與使用者存取 Office 365 Security & 合規性中心](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1299a-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Office 365 Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="1299a-128">哪裡可以找到郵件流程儀表板</span><span class="sxs-lookup"><span data-stu-id="1299a-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="1299a-129">移至安全性 & 合規性中心， [https://protection.office.com](https://protection.office.com)網址為。</span><span class="sxs-lookup"><span data-stu-id="1299a-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="1299a-130">展開 [**郵件流程**]，然後選取 [**儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="1299a-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Office 365 安全性 & 規範中心內的郵件流程儀表板](../../media/mail-flow-dashboard-v2.png)
