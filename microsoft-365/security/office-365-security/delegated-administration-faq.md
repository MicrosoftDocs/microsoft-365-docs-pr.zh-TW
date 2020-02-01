---
title: 委派管理常見問題集
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: 針對想要執行委派的 Office 365 管理工作的 Microsoft 合作夥伴和轉銷售，包括能夠管理其他承租人 (公司) 的 Exchange Online Protection (EOP)，本主題提供常見問題與解答。
ms.openlocfilehash: 2a237da685ae3c3d81c5a0912e15b5e7370e2118
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599480"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="5496e-103">委派管理常見問題集</span><span class="sxs-lookup"><span data-stu-id="5496e-103">Delegated administration FAQ</span></span>

<span data-ttu-id="5496e-104">針對想要執行委派的 Office 365 管理工作的 Microsoft 合作夥伴和轉銷售，包括能夠管理其他承租人 (公司) 的 Exchange Online Protection (EOP)，本主題提供常見問題與解答。</span><span class="sxs-lookup"><span data-stu-id="5496e-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated Office 365 administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>

<span data-ttu-id="5496e-105">**問：我是轉銷商，需要管理客戶的承租人；該怎麼做？**</span><span class="sxs-lookup"><span data-stu-id="5496e-105">**Q. I'm a reseller and I need to manage my customer's tenants; how does this work?**</span></span>

<span data-ttu-id="5496e-106">答：</span><span class="sxs-lookup"><span data-stu-id="5496e-106">A.</span></span> <span data-ttu-id="5496e-107">如果您的 Microsoft 合作夥伴或轉銷商，而且您已簽署最多可為 Microsoft 顧問，您可以要求權限管理在系統管理中心內其租用戶。</span><span class="sxs-lookup"><span data-stu-id="5496e-107">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="5496e-108">這稱為委派管理，以及它可讓您管理其 Office 365 租用戶中 （包括 EOP 設定） 如果當您已在組織內系統管理員。</span><span class="sxs-lookup"><span data-stu-id="5496e-108">This is known as delegated administration, and it allows you to manage their Office 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="5496e-109">執行委派的管理的步驟如下所示：</span><span class="sxs-lookup"><span data-stu-id="5496e-109">The steps for performing delegated administration are as follows:</span></span>

1. <span data-ttu-id="5496e-110">註冊成為 [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits)。</span><span class="sxs-lookup"><span data-stu-id="5496e-110">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="5496e-p102">註冊 Office 365 委派管理。客戶必須將委派管理員的身分授權給您，您才可以開始管理客戶的帳戶。若要取得核准，您需要先[將委派管理的邀請寄給他們](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e)。(您也可以稍後再提供委派管理給客戶。)</span><span class="sxs-lookup"><span data-stu-id="5496e-p102">Sign up for Office 365 delegated administration. Before you can start administering a customer's account, they must authorize you as a delegated administrator. To obtain their approval, you first [send them an offer for delegated administration](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e). (You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="5496e-115">建立委派的管理員帳戶使用中[新增、 變更或刪除訂閱顧問合作夥伴](https://docs.microsoft.com/office365/admin/misc/add-partner)的步驟。</span><span class="sxs-lookup"><span data-stu-id="5496e-115">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](https://docs.microsoft.com/office365/admin/misc/add-partner).</span></span>

<span data-ttu-id="5496e-116">請造訪[合作夥伴： 建立業務以及管理您的 Office 365 合作夥伴訂閱](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319)如需有關如何設定 Office 365 委派管理。</span><span class="sxs-lookup"><span data-stu-id="5496e-116">Visit [Partners: Build your business and administer your Office 365 partner subscription](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up Office 365 delegated administration.</span></span>

<span data-ttu-id="5496e-117">**問：我是客戶，不是轉銷商，該如何為子承租人設定委派的系統管理員？**</span><span class="sxs-lookup"><span data-stu-id="5496e-117">**Q. I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?**</span></span>

<span data-ttu-id="5496e-p103">答：委派的管理目前僅適用於轉銷商和合作夥伴。不過，我們提供範例 Windows PowerShell 指令碼，可協助您將原則套用到您的子承租人 (公司)。如需詳細資訊，請參閱 [套用 EOP 設定至多個承租人的範例指令碼](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="5496e-p103">A. Delegated administration is only available for resellers and partners at this time. However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies). For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

<span data-ttu-id="5496e-122">**問：可以防止我的子承租人管理員修改我的原則嗎？**</span><span class="sxs-lookup"><span data-stu-id="5496e-122">**Q. Can I prevent my sub-tenant admin from modifying my policy?**</span></span>

<span data-ttu-id="5496e-p104">答：Office 365 目前不具備這項功能。</span><span class="sxs-lookup"><span data-stu-id="5496e-p104">A. Office 365 does not currently have this capability.</span></span>

<span data-ttu-id="5496e-125">**問：我可以取得所有子承租人的彙總報告嗎？**</span><span class="sxs-lookup"><span data-stu-id="5496e-125">**Q. Can I get consolidated reporting across all of my sub-tenants?**</span></span>

<span data-ttu-id="5496e-126">答：</span><span class="sxs-lookup"><span data-stu-id="5496e-126">A.</span></span> <span data-ttu-id="5496e-127">跨您管理公司的合併報告不適用於 Microsoft 365 系統管理中心報告這一次。</span><span class="sxs-lookup"><span data-stu-id="5496e-127">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="5496e-128">不過，您可以使用[Microsoft Graph](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="5496e-128">However, you can do this by using [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>
