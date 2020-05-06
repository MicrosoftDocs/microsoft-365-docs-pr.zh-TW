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
ms.custom:
- seo-marvel-apr2020
description: 本主題為想要執行委派 Microsoft 365 管理工作的 Microsoft 合作夥伴和轉銷商提供 FAQs 和解答。
ms.openlocfilehash: d2411734e583cce2be817793e2b39abba2b186a5
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036460"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="5b777-103">委派管理常見問題集</span><span class="sxs-lookup"><span data-stu-id="5b777-103">Delegated administration FAQ</span></span>

<span data-ttu-id="5b777-104">本主題針對想要執行委派管理工作（包括管理其他租使用者（公司）的 Exchange Online Protection （EOP）的 Microsoft 合作夥伴和轉銷商提供常見問題和解答。</span><span class="sxs-lookup"><span data-stu-id="5b777-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>

<span data-ttu-id="5b777-105">**問：我是轉銷商，需要管理客戶的承租人；該怎麼做？**</span><span class="sxs-lookup"><span data-stu-id="5b777-105">**Q. I'm a reseller and I need to manage my customer's tenants; how does this work?**</span></span>

<span data-ttu-id="5b777-106">答：</span><span class="sxs-lookup"><span data-stu-id="5b777-106">A.</span></span> <span data-ttu-id="5b777-107">如果您是 Microsoft 合作夥伴或轉銷商，而且您已註冊成為 Microsoft advisor，您可以在系統管理中心中要求管理其租使用者的許可權。</span><span class="sxs-lookup"><span data-stu-id="5b777-107">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="5b777-108">這稱為「委派管理」，可讓您管理其 Microsoft 365 租使用者（包括 EOP 設定），如同您是組織內的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="5b777-108">This is known as delegated administration, and it allows you to manage their Microsoft 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="5b777-109">執行委派管理的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="5b777-109">The steps for performing delegated administration are as follows:</span></span>

1. <span data-ttu-id="5b777-110">註冊成為 [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits)。</span><span class="sxs-lookup"><span data-stu-id="5b777-110">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="5b777-111">註冊委派管理。</span><span class="sxs-lookup"><span data-stu-id="5b777-111">Sign up for delegated administration.</span></span> <span data-ttu-id="5b777-112">在您開始管理客戶的帳戶之前，必須以委派的管理員身分授權。</span><span class="sxs-lookup"><span data-stu-id="5b777-112">Before you can start administering a customer's account, they must authorize you as a delegated administrator.</span></span> <span data-ttu-id="5b777-113">若要取得他們的核准，您必須先[傳送給他們，以取得委派管理的服務](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e)。</span><span class="sxs-lookup"><span data-stu-id="5b777-113">To obtain their approval, you first [send them an offer for delegated administration](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> <span data-ttu-id="5b777-114">（您也可以稍後為客戶提供委派管理）。</span><span class="sxs-lookup"><span data-stu-id="5b777-114">(You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="5b777-115">使用[新增、變更或刪除訂閱顧問合作夥伴](https://docs.microsoft.com/office365/admin/misc/add-partner)中的步驟，建立委派的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="5b777-115">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](https://docs.microsoft.com/office365/admin/misc/add-partner).</span></span>

<span data-ttu-id="5b777-116">請造訪協力廠商[：組建您的商務和管理合作夥伴訂閱](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319)，以取得如何設定委派管理的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5b777-116">Visit [Partners: Build your business and administer partner subscription](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up delegated administration.</span></span>

<span data-ttu-id="5b777-117">**問：我是客戶，不是轉銷商，該如何為子承租人設定委派的系統管理員？**</span><span class="sxs-lookup"><span data-stu-id="5b777-117">**Q. I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?**</span></span>

<span data-ttu-id="5b777-p103">答：委派的管理目前僅適用於轉銷商和合作夥伴。不過，我們提供範例 Windows PowerShell 指令碼，可協助您將原則套用到您的子承租人 (公司)。如需詳細資訊，請參閱 [套用 EOP 設定至多個承租人的範例指令碼](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="5b777-p103">A. Delegated administration is only available for resellers and partners at this time. However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies). For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

<span data-ttu-id="5b777-122">**問：可以防止我的子承租人管理員修改我的原則嗎？**</span><span class="sxs-lookup"><span data-stu-id="5b777-122">**Q. Can I prevent my sub-tenant admin from modifying my policy?**</span></span>

<span data-ttu-id="5b777-123">答：</span><span class="sxs-lookup"><span data-stu-id="5b777-123">A.</span></span> <span data-ttu-id="5b777-124">Microsoft 365 目前並未具備這項功能。</span><span class="sxs-lookup"><span data-stu-id="5b777-124">Microsoft 365 does not currently have this capability.</span></span>

<span data-ttu-id="5b777-125">**問：我可以取得所有子承租人的彙總報告嗎？**</span><span class="sxs-lookup"><span data-stu-id="5b777-125">**Q. Can I get consolidated reporting across all of my sub-tenants?**</span></span>

<span data-ttu-id="5b777-126">答：</span><span class="sxs-lookup"><span data-stu-id="5b777-126">A.</span></span> <span data-ttu-id="5b777-127">目前您管理的公司內的整合報告無法供 Microsoft 365 系統管理中心報告使用。</span><span class="sxs-lookup"><span data-stu-id="5b777-127">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="5b777-128">不過，您可以使用[Microsoft Graph](https://docs.microsoft.com/graph/overview)來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="5b777-128">However, you can do this by using [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>
