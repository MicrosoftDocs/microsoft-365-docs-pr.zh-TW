---
title: 管理帳單的設定檔
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
description: 了解如何帳單 profiles 支援發票。
keywords: 帳單設定檔、 發票、 費用，受管理的費用
ms.openlocfilehash: 4b46709cf877ea8689f72b66d5ac357272e4737d
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753542"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="95e1d-104">管理帳單的設定檔</span><span class="sxs-lookup"><span data-stu-id="95e1d-104">Manage billing profiles</span></span>
<span data-ttu-id="95e1d-105">從 Microsoft 購買產品和服務的商業客戶，「 帳單設定檔 」 可讓您自訂哪些項目會包含在您的帳單和支付您發票的方式。</span><span class="sxs-lookup"><span data-stu-id="95e1d-105">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="95e1d-106">帳單設定檔包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="95e1d-106">Billing profiles include the following information:</span></span>

- <span data-ttu-id="95e1d-107">**計費帳戶**&ndash;設定檔與相關的帳單帳戶名稱</span><span class="sxs-lookup"><span data-stu-id="95e1d-107">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="95e1d-108">**付款方式**&ndash;信用卡或轉帳卡、 銀行帳戶、 存回或線路傳輸</span><span class="sxs-lookup"><span data-stu-id="95e1d-108">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="95e1d-109">**連絡人資訊**&ndash;帳單地址與連絡人的名稱</span><span class="sxs-lookup"><span data-stu-id="95e1d-109">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="95e1d-110">**發票設定**&ndash;貨幣根據帳單帳戶、 選用的 PO 編號，以及收到以電子郵件附件形式的發票的選項的國家/地區</span><span class="sxs-lookup"><span data-stu-id="95e1d-110">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="95e1d-111">**權限**&ndash;的權限可讓您變更帳單的設定檔，支付帳單，或購買商品帳單的設定檔上使用付款方式</span><span class="sxs-lookup"><span data-stu-id="95e1d-111">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="95e1d-112">用於控制您購買並自訂您的帳單計費的設定檔。</span><span class="sxs-lookup"><span data-stu-id="95e1d-112">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="95e1d-113">每月的發票付款與帳單的設定檔所購買的產品為產生。</span><span class="sxs-lookup"><span data-stu-id="95e1d-113">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="95e1d-114">您可以自訂發票，例如更新購買訂單號碼和電子郵件發票喜好設定。</span><span class="sxs-lookup"><span data-stu-id="95e1d-114">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="95e1d-115">在第一個購買期間帳單帳戶會自動建立帳單的設定檔。</span><span class="sxs-lookup"><span data-stu-id="95e1d-115">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="95e1d-116">您可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">設定檔] [帳單</a>] 頁面上設定多個發票建立帳單的設定檔。</span><span class="sxs-lookup"><span data-stu-id="95e1d-116">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="95e1d-117">例如，您可以使用不同的帳單設定檔，當您在組織中每個部門的購買。</span><span class="sxs-lookup"><span data-stu-id="95e1d-117">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="95e1d-118">在您下一步帳單日期後，您會收到每個計費的設定檔的發票。</span><span class="sxs-lookup"><span data-stu-id="95e1d-118">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="95e1d-119">帳單的設定檔角色</span><span class="sxs-lookup"><span data-stu-id="95e1d-119">Billing profile roles</span></span>

<span data-ttu-id="95e1d-120">在帳單設定檔的角色具有權限來控制購買，檢視及管理發票。</span><span class="sxs-lookup"><span data-stu-id="95e1d-120">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="95e1d-121">將這些角色指派給追蹤、 組織及支付發票，像是組織中的採購小組成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="95e1d-121">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="95e1d-122">角色</span><span class="sxs-lookup"><span data-stu-id="95e1d-122">Role</span></span>                          | <span data-ttu-id="95e1d-123">描述</span><span class="sxs-lookup"><span data-stu-id="95e1d-123">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="95e1d-124">帳單的設定檔擁有者</span><span class="sxs-lookup"><span data-stu-id="95e1d-124">Billing profile owner</span></span>         | <span data-ttu-id="95e1d-125">管理帳單的設定檔的所有項目</span><span class="sxs-lookup"><span data-stu-id="95e1d-125">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="95e1d-126">帳單的設定檔參與者</span><span class="sxs-lookup"><span data-stu-id="95e1d-126">Billing profile contributor</span></span>   | <span data-ttu-id="95e1d-127">管理帳單的設定檔中的權限以外的項目</span><span class="sxs-lookup"><span data-stu-id="95e1d-127">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="95e1d-128">帳單的設定檔讀取者</span><span class="sxs-lookup"><span data-stu-id="95e1d-128">Billing profile reader</span></span>        | <span data-ttu-id="95e1d-129">唯讀] 檢視帳單的設定檔中的所有項目</span><span class="sxs-lookup"><span data-stu-id="95e1d-129">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="95e1d-130">發票管理員</span><span class="sxs-lookup"><span data-stu-id="95e1d-130">Invoice manager</span></span>               | <span data-ttu-id="95e1d-131">檢視和支付帳單，和帳單的設定檔中有唯讀] 檢視的每個項目</span><span class="sxs-lookup"><span data-stu-id="95e1d-131">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="95e1d-132">檢視帳單的設定檔</span><span class="sxs-lookup"><span data-stu-id="95e1d-132">View billing profiles</span></span>

1. <span data-ttu-id="95e1d-133">在 [系統管理中心中，移至**帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">帳單 & 付款</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="95e1d-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="95e1d-134">選擇 [**計費設定檔**，然後從清單中選擇 [帳單的設定檔。</span><span class="sxs-lookup"><span data-stu-id="95e1d-134">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="95e1d-135">[**概觀**] 索引標籤中，您可以編輯帳單設定檔的詳細資訊，並開啟或關閉傳送電子郵件的發票。</span><span class="sxs-lookup"><span data-stu-id="95e1d-135">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="95e1d-136">[**權限**] 索引標籤中，您可以將角色指派給使用者，讓支付發票。</span><span class="sxs-lookup"><span data-stu-id="95e1d-136">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="95e1d-137">在**Azure 信用達到負載平衡**] 索引標籤，Azure 客戶可以看到該帳單的設定檔使用 Azure 信用額度交易平衡歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="95e1d-137">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="95e1d-138">在**Azure 的信用額度**] 索引標籤，Azure 客戶可以看到該帳單的設定檔，以及其到期日期相關聯的 Azure 點數的清單。</span><span class="sxs-lookup"><span data-stu-id="95e1d-138">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95e1d-139">如果您沒有任何 Azure 的信用額度，不會看到 [ **Azure 信用達到負載平衡**或**Azure 信用額度**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="95e1d-139">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="95e1d-140">需要說明嗎？</span><span class="sxs-lookup"><span data-stu-id="95e1d-140">Need help?</span></span> <span data-ttu-id="95e1d-141">連絡客戶支援。</span><span class="sxs-lookup"><span data-stu-id="95e1d-141">Contact support.</span></span>

<span data-ttu-id="95e1d-142">如果您有任何疑問，或需要與您 Azure 的費用，<a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">建立 Azure 支援的支援要求</a>協助。</span><span class="sxs-lookup"><span data-stu-id="95e1d-142">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="95e1d-143">如果您有任何疑問，或需要您帳單的設定檔，在 Microsoft 365 系統管理中心，[請連絡商務產品的支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="95e1d-143">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>