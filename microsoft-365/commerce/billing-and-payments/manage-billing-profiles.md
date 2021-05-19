---
title: 了解帳單設定檔
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: 瞭解帳單設定檔如何支援發票。
ms.date: 04/02/2021
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537328"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="c8c43-103">了解帳單設定檔</span><span class="sxs-lookup"><span data-stu-id="c8c43-103">Understand billing profiles</span></span>

<span data-ttu-id="c8c43-104">計費設定檔包含付款條件、帳單資訊和其他發票設定，例如購買訂單編號和電子郵件發票偏好設定。</span><span class="sxs-lookup"><span data-stu-id="c8c43-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="c8c43-105">您可以使用計費設定檔來支付您從 Microsoft 購買的產品。</span><span class="sxs-lookup"><span data-stu-id="c8c43-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="c8c43-106">當使用者進行自助購買時，會自動建立帳單設定檔。</span><span class="sxs-lookup"><span data-stu-id="c8c43-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="c8c43-107">每個帳單設定檔都是分開開票的。</span><span class="sxs-lookup"><span data-stu-id="c8c43-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="c8c43-108">從 Microsoft.com 購買產品和服務的客戶或是在 Microsoft 365 系統管理中心的 [**購買服務**] 頁面上，都無法使用計費設定檔。</span><span class="sxs-lookup"><span data-stu-id="c8c43-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="c8c43-109">什麼是計費設定檔角色？</span><span class="sxs-lookup"><span data-stu-id="c8c43-109">What are billing profile roles?</span></span>

<span data-ttu-id="c8c43-110">計費設定檔上的角色具有控制購買的許可權，以及查看和管理發票。</span><span class="sxs-lookup"><span data-stu-id="c8c43-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="c8c43-111">將這些角色指派給追蹤、組織及支付發票的使用者。</span><span class="sxs-lookup"><span data-stu-id="c8c43-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="c8c43-112">例如，您組織中的採購團隊成員。</span><span class="sxs-lookup"><span data-stu-id="c8c43-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="c8c43-113">角色</span><span class="sxs-lookup"><span data-stu-id="c8c43-113">Role</span></span>                         | <span data-ttu-id="c8c43-114">描述</span><span class="sxs-lookup"><span data-stu-id="c8c43-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="c8c43-115">計費設定檔擁有者</span><span class="sxs-lookup"><span data-stu-id="c8c43-115">Billing profile owner</span></span>        | <span data-ttu-id="c8c43-116">管理帳單設定檔的所有專案</span><span class="sxs-lookup"><span data-stu-id="c8c43-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="c8c43-117">帳單設定檔參與者</span><span class="sxs-lookup"><span data-stu-id="c8c43-117">Billing profile contributor</span></span>  | <span data-ttu-id="c8c43-118">管理帳單設定檔中的許可權以外的所有專案</span><span class="sxs-lookup"><span data-stu-id="c8c43-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="c8c43-119">計費設定檔讀取器</span><span class="sxs-lookup"><span data-stu-id="c8c43-119">Billing profile reader</span></span>       | <span data-ttu-id="c8c43-120">計費設定檔中所有專案的唯讀視圖</span><span class="sxs-lookup"><span data-stu-id="c8c43-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="c8c43-121">發票管理員</span><span class="sxs-lookup"><span data-stu-id="c8c43-121">Invoice manager</span></span>              | <span data-ttu-id="c8c43-122">查看和支付帳單，且具有記帳設定檔中所有專案的唯讀視圖</span><span class="sxs-lookup"><span data-stu-id="c8c43-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="c8c43-123">查看我的計費設定檔</span><span class="sxs-lookup"><span data-stu-id="c8c43-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="c8c43-124">如果您遵循這些步驟，且計費配置檔案清單是空的，則表示您沒有帳單設定檔，且無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="c8c43-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="c8c43-125">在系統管理中心中，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[帳單與付款]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c8c43-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="c8c43-126">選取 [ **帳單設定檔** ] 索引標籤，然後從清單中選取帳單設定檔。</span><span class="sxs-lookup"><span data-stu-id="c8c43-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="c8c43-127">每個帳單設定檔都包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c8c43-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="c8c43-128">**計費設定檔名稱和狀態** &ndash; 計費設定檔的唯一名稱，以及計費設定檔是否為使用中或已停用購買的狀態。</span><span class="sxs-lookup"><span data-stu-id="c8c43-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="c8c43-129">**發票設定** &ndash; 以計費帳戶所在國家/地區為基礎的貨幣、發票頻率和日期的相關資訊、以電子郵件附件形式接收發票的選項，以及選用的 [PO 號碼] 欄位。</span><span class="sxs-lookup"><span data-stu-id="c8c43-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="c8c43-130">**付款條件** &ndash; 顯示設定檔的主要和備份付款條件（如果有的話）</span><span class="sxs-lookup"><span data-stu-id="c8c43-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="c8c43-131">**計費帳戶** &ndash; 與設定檔相關的帳單帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="c8c43-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="c8c43-132">如需計費帳戶的詳細資訊，請參閱 [瞭解帳單帳戶](../manage-billing-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="c8c43-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="c8c43-133">**連絡人資訊** &ndash; 帳單位址和連絡人名稱和電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="c8c43-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="c8c43-134">**計費設定檔角色** &ndash; 指派其中一個計費設定檔角色以執行該設定檔的人員清單。</span><span class="sxs-lookup"><span data-stu-id="c8c43-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="c8c43-135">例如，支付帳單、新增 PO 號碼或取代用來進行購買的支付方式。</span><span class="sxs-lookup"><span data-stu-id="c8c43-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="c8c43-136">您只可以將計費設定檔角色指派給組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="c8c43-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="c8c43-137">需要協助？</span><span class="sxs-lookup"><span data-stu-id="c8c43-137">Need help?</span></span> <span data-ttu-id="c8c43-138">連絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="c8c43-138">Contact support</span></span>

<span data-ttu-id="c8c43-139">如果您有任何問題或需要協助您的 Azure 費用，請 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">建立支援 azure 支援的支援要求</a>。</span><span class="sxs-lookup"><span data-stu-id="c8c43-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="c8c43-140">如果您有任何問題或需要協助您 Microsoft 365 系統管理中心的帳單設定檔，請[與支援人員聯繫](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="c8c43-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="c8c43-141">相關內容</span><span class="sxs-lookup"><span data-stu-id="c8c43-141">Related content</span></span>

<span data-ttu-id="c8c43-142">[如何使用計費設定檔支付訂閱](pay-for-subscription-billing-profile.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="c8c43-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="c8c43-143">[瞭解帳單帳戶](../manage-billing-accounts.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="c8c43-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="c8c43-144">[管理支付方式](manage-payment-methods.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="c8c43-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
