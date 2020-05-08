---
title: 管理帳單設定檔
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 瞭解帳單設定檔如何支援發票。
keywords: 計費設定檔、發票、費用、受管理的費用
ms.openlocfilehash: f93ca5af11ba416fecd13fcceffe75055a776553
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140887"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="94421-104">管理帳單設定檔</span><span class="sxs-lookup"><span data-stu-id="94421-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="94421-105">系統管理中心變更。</span><span class="sxs-lookup"><span data-stu-id="94421-105">The admin center is changing.</span></span> <span data-ttu-id="94421-106">[！附注] 如果您的經驗不符合這裡所述的詳細資料，請參閱[關於新的 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="94421-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="94421-107">針對從 Microsoft 購買產品和服務的商業客戶，計費設定檔可讓您自訂發票上包含的專案，以及您支付發票的方式。</span><span class="sxs-lookup"><span data-stu-id="94421-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="94421-108">計費設定檔包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="94421-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="94421-109">與設定檔相關之帳單帳戶的**帳單帳戶** &ndash;名稱</span><span class="sxs-lookup"><span data-stu-id="94421-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="94421-110">**支付方式** &ndash;信用卡或轉帳卡、銀行帳戶、支票或電匯卡</span><span class="sxs-lookup"><span data-stu-id="94421-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="94421-111">**連絡人資訊** &ndash;的帳單位址和連絡人名稱</span><span class="sxs-lookup"><span data-stu-id="94421-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="94421-112">根據帳單帳戶的國家/地區、選擇性的 PO 編號，以及以電子郵件附件形式接收發票的選項的**發票設定** &ndash;貨幣</span><span class="sxs-lookup"><span data-stu-id="94421-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="94421-113">**許可權** &ndash;許可權，可讓您變更帳單設定檔、支付帳單或使用計費設定檔上的付款條件進行購買</span><span class="sxs-lookup"><span data-stu-id="94421-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="94421-114">使用計費設定檔來控制購買及自訂發票。</span><span class="sxs-lookup"><span data-stu-id="94421-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="94421-115">每月發票會產生為以帳單設定檔購買的產品。</span><span class="sxs-lookup"><span data-stu-id="94421-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="94421-116">您可以自訂發票，例如更新採購訂單編號和電子郵件發票偏好設定。</span><span class="sxs-lookup"><span data-stu-id="94421-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="94421-117">您第一次購買時，會自動為您的帳單帳戶建立帳單設定檔。</span><span class="sxs-lookup"><span data-stu-id="94421-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="94421-118">您可以在 [<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">帳單設定檔</a>] 頁面上建立計費設定檔，以設定更多發票。</span><span class="sxs-lookup"><span data-stu-id="94421-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="94421-119">例如，您可以在您為組織中的每個部門進行購買時使用不同的帳單設定檔。</span><span class="sxs-lookup"><span data-stu-id="94421-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="94421-120">在您下一個帳單日期，您會收到每個帳單設定檔的發票。</span><span class="sxs-lookup"><span data-stu-id="94421-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="94421-121">計費設定檔角色</span><span class="sxs-lookup"><span data-stu-id="94421-121">Billing profile roles</span></span>

<span data-ttu-id="94421-122">計費設定檔上的角色具有控制購買的許可權，以及查看和管理發票。</span><span class="sxs-lookup"><span data-stu-id="94421-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="94421-123">將這些角色指派給追蹤、組織和支付發票的使用者，例如組織中的採購團隊成員。</span><span class="sxs-lookup"><span data-stu-id="94421-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="94421-124">角色</span><span class="sxs-lookup"><span data-stu-id="94421-124">Role</span></span>                          | <span data-ttu-id="94421-125">描述</span><span class="sxs-lookup"><span data-stu-id="94421-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="94421-126">計費設定檔擁有者</span><span class="sxs-lookup"><span data-stu-id="94421-126">Billing profile owner</span></span>         | <span data-ttu-id="94421-127">管理帳單設定檔的所有專案</span><span class="sxs-lookup"><span data-stu-id="94421-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="94421-128">帳單設定檔參與者</span><span class="sxs-lookup"><span data-stu-id="94421-128">Billing profile contributor</span></span>   | <span data-ttu-id="94421-129">管理帳單設定檔中的許可權以外的所有專案</span><span class="sxs-lookup"><span data-stu-id="94421-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="94421-130">計費設定檔讀取器</span><span class="sxs-lookup"><span data-stu-id="94421-130">Billing profile reader</span></span>        | <span data-ttu-id="94421-131">計費設定檔中所有專案的唯讀視圖</span><span class="sxs-lookup"><span data-stu-id="94421-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="94421-132">發票管理員</span><span class="sxs-lookup"><span data-stu-id="94421-132">Invoice manager</span></span>               | <span data-ttu-id="94421-133">查看和支付帳單，且具有記帳設定檔中所有專案的唯讀視圖</span><span class="sxs-lookup"><span data-stu-id="94421-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="94421-134">查看帳單設定檔</span><span class="sxs-lookup"><span data-stu-id="94421-134">View billing profiles</span></span>

1. <span data-ttu-id="94421-135">在系統管理中心中，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">[帳單與付款]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="94421-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="94421-136">選擇 [**帳單設定檔**]，然後從清單中選擇帳單設定檔。</span><span class="sxs-lookup"><span data-stu-id="94421-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="94421-137">在 [**概覽**] 索引標籤上，您可以編輯帳單設定檔詳細資料，並開啟或關閉透過電子郵件傳送發票的功能。</span><span class="sxs-lookup"><span data-stu-id="94421-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="94421-138">在 [**許可權**] 索引標籤上，您可以將角色指派給使用者以支付發票。</span><span class="sxs-lookup"><span data-stu-id="94421-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="94421-139">在 [ **azure 信用平衡**] 索引標籤上，Azure 客戶可以查看該帳單設定檔使用之 Azure 點數的交易餘額歷史記錄。</span><span class="sxs-lookup"><span data-stu-id="94421-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="94421-140">在 [ **azure 信用**] 索引標籤上，Azure 客戶可以查看與該帳單設定檔相關聯的 Azure 信用名單及其到期日期。</span><span class="sxs-lookup"><span data-stu-id="94421-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94421-141">如果您沒有任何 Azure 信用，您就不會看到 [ **azure 貸方餘額**] 或 [ **azure 信用**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="94421-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="94421-142">需要協助嗎？</span><span class="sxs-lookup"><span data-stu-id="94421-142">Need help?</span></span> <span data-ttu-id="94421-143">連絡客戶支援。</span><span class="sxs-lookup"><span data-stu-id="94421-143">Contact support.</span></span>

<span data-ttu-id="94421-144">如果您有任何問題或需要協助您的 Azure 費用，請<a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">建立支援 azure 支援的支援要求</a>。</span><span class="sxs-lookup"><span data-stu-id="94421-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="94421-145">如果您有任何疑問或需要協助您使用 Microsoft 365 系統管理中心的帳單設定檔，請[聯繫商務產品支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)人員。</span><span class="sxs-lookup"><span data-stu-id="94421-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
