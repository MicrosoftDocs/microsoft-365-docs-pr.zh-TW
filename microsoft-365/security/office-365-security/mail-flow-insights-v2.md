---
title: 安全性與合規性中心內的郵件流程深入解析
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 系統管理員可以了解安全性 & 合規性中心中的郵件流程儀表板。
ms.openlocfilehash: a8bc8dbc2dcd25e3b26b35221cadf9534f9f668b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076796"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="05dfc-103">安全性與合規性中心內的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="05dfc-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="05dfc-104">系統管理員可以使用郵件流程儀表板中的安全性 & 合規性中心探索趨勢，深入了解，並採取動作，以修正與 Office 365 組織中的郵件流程相關的問題。</span><span class="sxs-lookup"><span data-stu-id="05dfc-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="05dfc-105">深入了解、 報告和郵件流程儀表板中可用的 widget 如下：</span><span class="sxs-lookup"><span data-stu-id="05dfc-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="05dfc-106">郵件流程地圖報表</span><span class="sxs-lookup"><span data-stu-id="05dfc-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="05dfc-107">網域郵件流程狀態深入解析</span><span class="sxs-lookup"><span data-stu-id="05dfc-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="05dfc-108">SMTP 驗證的用戶端報告</span><span class="sxs-lookup"><span data-stu-id="05dfc-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="05dfc-109">寄件者網域深入解析</span><span class="sxs-lookup"><span data-stu-id="05dfc-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="05dfc-110">未傳遞報告</span><span class="sxs-lookup"><span data-stu-id="05dfc-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="05dfc-111">非公認的網域報表</span><span class="sxs-lookup"><span data-stu-id="05dfc-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="05dfc-112">外寄和內送的郵件流程</span><span class="sxs-lookup"><span data-stu-id="05dfc-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="05dfc-113">佇列的警示和佇列</span><span class="sxs-lookup"><span data-stu-id="05dfc-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="05dfc-114">自動轉寄訊息的報告</span><span class="sxs-lookup"><span data-stu-id="05dfc-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="05dfc-115">郵件迴圈深入解析</span><span class="sxs-lookup"><span data-stu-id="05dfc-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="05dfc-116">緩慢的郵件流程規則深入解析</span><span class="sxs-lookup"><span data-stu-id="05dfc-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="05dfc-117">若要檢視的郵件流程儀表板所需權限</span><span class="sxs-lookup"><span data-stu-id="05dfc-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="05dfc-118">郵件流程儀表板的可：</span><span class="sxs-lookup"><span data-stu-id="05dfc-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="05dfc-119">**Office 365 全域系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="05dfc-119">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="05dfc-120">**Office 365 Exchange 系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="05dfc-120">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="05dfc-121">安全性 & 合規性中心中的**郵件流程系統管理員角色**的成員。</span><span class="sxs-lookup"><span data-stu-id="05dfc-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="05dfc-122">如果不是全域系統管理員或 Exchange 系統管理員角色的成員的使用者明確指派這個角色：</span><span class="sxs-lookup"><span data-stu-id="05dfc-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="05dfc-123">使用者必須登入安全性 & 合規性中心，直接在[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="05dfc-123">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="05dfc-124">使用者將只有郵件流程儀表板的唯讀權限。</span><span class="sxs-lookup"><span data-stu-id="05dfc-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="05dfc-125">使用者無法存取 Office 365 系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="05dfc-125">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="05dfc-126">如需有關 Office 365 全域系統管理員角色的詳細資訊，請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="05dfc-126">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="05dfc-127">將安全性 & 合規性中心角色指派給使用者的詳細資訊，請參閱[讓使用者能夠存取安全性 & 合規性中心](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="05dfc-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="05dfc-128">哪裡可以找到的郵件流程儀表板</span><span class="sxs-lookup"><span data-stu-id="05dfc-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="05dfc-129">移至安全性 & 合規性中心，在 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="05dfc-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="05dfc-130">依序展開 [**郵件流程**，然後選取 [**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="05dfc-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Office 365 安全性 & 規範中心的郵件流程儀表板](../media/mail-flow-dashboard-v2.png)
