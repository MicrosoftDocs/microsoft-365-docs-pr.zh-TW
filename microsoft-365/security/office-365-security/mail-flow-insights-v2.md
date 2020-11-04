---
title: 郵件流程儀表板中的郵件流程洞察力
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 系統管理員可以深入瞭解安全性 & 規範中心的郵件流程儀表板中提供的真知灼見和報告。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d252b9d898d4ee5a0df854a871f821c2b02bb482
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877774"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="352b8-103">安全性與合規性中心內的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="352b8-103">Mail flow insights in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="352b8-104">系統管理員可以使用安全性 & 合規性中心內的郵件流程儀表板來探索趨勢、深入資訊，並採取行動來修正組織中與郵件流程相關的問題。</span><span class="sxs-lookup"><span data-stu-id="352b8-104">Admins can use Mail flow dashboard in the Security & Compliance Center to discover trends, insights, and take actions to fix issues related to mail flow in their organization.</span></span>

![安全性 & 規範中心內的郵件流程儀表板](../../media/mail-flow-dashboard-v2.png)

<span data-ttu-id="352b8-106">可用的真知灼見包括：</span><span class="sxs-lookup"><span data-stu-id="352b8-106">The available insights are:</span></span>

- [<span data-ttu-id="352b8-107">自動轉寄訊息深入解析</span><span class="sxs-lookup"><span data-stu-id="352b8-107">Auto-forwarded messages insight</span></span>](mfi-auto-forwarded-messages-report.md)

- <span data-ttu-id="352b8-108">[修正可能的郵件迴圈真知灼見](mfi-mail-loop-insight.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="352b8-108">[Fix possible mail loop insight](mfi-mail-loop-insight.md)<sup>1</sup></span></span>

- <span data-ttu-id="352b8-109">[修正郵件流程規則真知灼見](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>的速度</span><span class="sxs-lookup"><span data-stu-id="352b8-109">[Fix slow mail flow rules insight](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup></span></span>

- [<span data-ttu-id="352b8-110">郵件流程圖</span><span class="sxs-lookup"><span data-stu-id="352b8-110">Mail flow map</span></span>](mfi-mail-flow-map-report.md)

- <span data-ttu-id="352b8-111">[轉寄的新網域電子郵件洞察力](mfi-new-domains-being-forwarded-email.md)<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="352b8-111">[New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup></span></span>

- <span data-ttu-id="352b8-112">[新使用者轉寄電子郵件真知灼見](mfi-new-users-forwarding-email.md)<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="352b8-112">[New users forwarding email insight](mfi-new-users-forwarding-email.md)<sup>2</sup></span></span>

- [<span data-ttu-id="352b8-113">非公認的網域報告</span><span class="sxs-lookup"><span data-stu-id="352b8-113">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="352b8-114">未傳遞回報</span><span class="sxs-lookup"><span data-stu-id="352b8-114">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="352b8-115">外寄和內送郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="352b8-115">Outbound and inbound mail flow insight</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="352b8-116">佇列深入解析</span><span class="sxs-lookup"><span data-stu-id="352b8-116">Queues insight</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="352b8-117">SMTP 驗證用戶端深入解析和報告</span><span class="sxs-lookup"><span data-stu-id="352b8-117">SMTP Auth clients insight and report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="352b8-118">上層網域郵件流程狀態深入解析</span><span class="sxs-lookup"><span data-stu-id="352b8-118">Top domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

<span data-ttu-id="352b8-119"><sup>1</sup> 當偵測到問題之後，就會在 [郵件流程] 儀表板的 [ **建議** ] 區域中顯示此真知灼見。</span><span class="sxs-lookup"><span data-stu-id="352b8-119"><sup>1</sup> This insight appears in the **Recommended for you** area of the Mail flow dashboard only after the issue is detected.</span></span> <span data-ttu-id="352b8-120">否則，您將看不到它。</span><span class="sxs-lookup"><span data-stu-id="352b8-120">Otherwise, you won't see it.</span></span>

<span data-ttu-id="352b8-121"><sup>2</sup> 郵件流程儀表板上不會顯示這種觀點，但在偵測到問題之後，會在 [轉寄 [報告](view-mail-flow-reports.md#forwarding-report) ] 頁面上顯示。</span><span class="sxs-lookup"><span data-stu-id="352b8-121"><sup>2</sup> This insight doesn't appear on the Mail flow dashboard, but is visible on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page after the issue is detected.</span></span> <span data-ttu-id="352b8-122">否則，您將看不到它。</span><span class="sxs-lookup"><span data-stu-id="352b8-122">Otherwise, you won't see it.</span></span>

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="352b8-123">查看郵件流程儀表板所需的許可權</span><span class="sxs-lookup"><span data-stu-id="352b8-123">Permissions required to view the Mail flow dashboard</span></span>

<span data-ttu-id="352b8-124">郵件流程儀表板可用於下列角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="352b8-124">The Mail flow dashboard is available to members of the following role groups:</span></span>

- <span data-ttu-id="352b8-125">安全性 & 規範中心內的 **組織管理** (全域管理員) 。</span><span class="sxs-lookup"><span data-stu-id="352b8-125">**Organization Management** in the Security & Compliance Center (global admins).</span></span>

- <span data-ttu-id="352b8-126">Azure Active Directory 中的 **[Exchange 系統管理員](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** 。</span><span class="sxs-lookup"><span data-stu-id="352b8-126">**[Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure Active Directory.</span></span>

- <span data-ttu-id="352b8-127">郵件流程 Security & 合規性中心內的 **系統管理員** ：如果此角色群組的成員不是全域系統管理員或 Exchange 系統管理員角色群組的成員，請注意下列問題和需求：</span><span class="sxs-lookup"><span data-stu-id="352b8-127">**MailFlow Administrator** in the Security & Compliance Center: If a member of this role group is not also a member of the global administrator or Exchange administrator role groups, then note the following issues and requirements:</span></span>

  - <span data-ttu-id="352b8-128">使用者必須直接登入安全性 & 合規性中心 <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="352b8-128">The user must log in to the Security & Compliance Center directly at <https://protection.office.com>.</span></span>
  - <span data-ttu-id="352b8-129">使用者只具有郵件流程儀表板的唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="352b8-129">The user will only have read-only permission to the Mail flow dashboard.</span></span>
  - <span data-ttu-id="352b8-130">使用者將無法存取 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="352b8-130">The user won't have access to the Microsoft 365 admin center.</span></span>

<span data-ttu-id="352b8-131">如需安全性 & 規範中心中許可權的詳細資訊，請參閱 [安全性 & 規範中心中的許可權](permissions-in-the-security-and-compliance-center.md) ，並 [授與使用者對安全性 & 規範中心的存取權](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="352b8-131">For more information about permissions in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Give users access to the Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="352b8-132">哪裡可以找到郵件流程儀表板</span><span class="sxs-lookup"><span data-stu-id="352b8-132">Where to find the Mail flow dashboard</span></span>

<span data-ttu-id="352b8-133">開啟安全性 & 合規性中心 <https://protection.office.com> ，展開 [ **郵件流程** ]，然後選取 [ **儀表板** ]。</span><span class="sxs-lookup"><span data-stu-id="352b8-133">Open the Security & Compliance Center at <https://protection.office.com>, expand **Mail flow** , and then select **Dashboard**.</span></span>

<span data-ttu-id="352b8-134">若要直接移至 [郵件流程] 儀表板，請開啟] <https://protection.office.com/mailflow/dashboard> 。</span><span class="sxs-lookup"><span data-stu-id="352b8-134">To go directly to the Mail flow dashboard, open <https://protection.office.com/mailflow/dashboard>.</span></span>
