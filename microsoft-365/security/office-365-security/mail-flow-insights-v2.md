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
description: 系統管理員可以了解安全性 & 合規性中心中的郵件流程儀表板。
ms.openlocfilehash: 0e87fde41c78f46aaac55602175a3716ba54fe7b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599040"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="55a2c-103">安全性與合規性中心內的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="55a2c-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="55a2c-104">系統管理員可以使用郵件流程儀表板中的安全性 & 合規性中心探索趨勢，深入了解，並採取動作，以修正與 Office 365 組織中的郵件流程相關的問題。</span><span class="sxs-lookup"><span data-stu-id="55a2c-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="55a2c-105">深入了解、 報告和郵件流程儀表板中可用的 widget 如下：</span><span class="sxs-lookup"><span data-stu-id="55a2c-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="55a2c-106">郵件流程圖報告</span><span class="sxs-lookup"><span data-stu-id="55a2c-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="55a2c-107">網域郵件流程狀態深入解析</span><span class="sxs-lookup"><span data-stu-id="55a2c-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="55a2c-108">SMTP 驗證用戶端報告</span><span class="sxs-lookup"><span data-stu-id="55a2c-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="55a2c-109">寄件者網域深入解析</span><span class="sxs-lookup"><span data-stu-id="55a2c-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="55a2c-110">未傳遞回報</span><span class="sxs-lookup"><span data-stu-id="55a2c-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="55a2c-111">非公認的網域報告</span><span class="sxs-lookup"><span data-stu-id="55a2c-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="55a2c-112">外寄和內送的郵件流程</span><span class="sxs-lookup"><span data-stu-id="55a2c-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="55a2c-113">佇列的警示和佇列</span><span class="sxs-lookup"><span data-stu-id="55a2c-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="55a2c-114">自動轉寄訊息的報告</span><span class="sxs-lookup"><span data-stu-id="55a2c-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="55a2c-115">郵件迴圈深入解析</span><span class="sxs-lookup"><span data-stu-id="55a2c-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="55a2c-116">緩慢的郵件流程規則深入解析</span><span class="sxs-lookup"><span data-stu-id="55a2c-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="55a2c-117">若要檢視的郵件流程儀表板所需權限</span><span class="sxs-lookup"><span data-stu-id="55a2c-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="55a2c-118">郵件流程儀表板的可：</span><span class="sxs-lookup"><span data-stu-id="55a2c-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="55a2c-119">**Office 365 全域系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="55a2c-119">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="55a2c-120">**Office 365 Exchange 系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="55a2c-120">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="55a2c-121">安全性 & 合規性中心中的**郵件流程系統管理員角色**的成員。</span><span class="sxs-lookup"><span data-stu-id="55a2c-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="55a2c-122">如果不是全域系統管理員或 Exchange 系統管理員角色的成員的使用者明確指派這個角色：</span><span class="sxs-lookup"><span data-stu-id="55a2c-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="55a2c-123">使用者必須登入安全性 & 合規性中心，直接在[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="55a2c-123">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="55a2c-124">使用者將只有郵件流程儀表板的唯讀權限。</span><span class="sxs-lookup"><span data-stu-id="55a2c-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="55a2c-125">使用者無法存取 Office 365 系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="55a2c-125">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="55a2c-126">如需有關 Office 365 全域系統管理員角色的詳細資訊，請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="55a2c-126">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="55a2c-127">將安全性 & 合規性中心角色指派給使用者的詳細資訊，請參閱[讓使用者能夠存取安全性 & 合規性中心](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="55a2c-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="55a2c-128">哪裡可以找到的郵件流程儀表板</span><span class="sxs-lookup"><span data-stu-id="55a2c-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="55a2c-129">移至安全性 & 合規性中心，在 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="55a2c-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="55a2c-130">依序展開 [**郵件流程**，然後選取 [**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="55a2c-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Office 365 安全性 & 規範中心的郵件流程儀表板](../media/mail-flow-dashboard-v2.png)
