---
title: 自助購買常見問題
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: 尋找有關自助購買的常見問題的答案。
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333191"
---
# <a name="self-service-purchase-faq"></a><span data-ttu-id="94e61-103">自助購買常見問題</span><span class="sxs-lookup"><span data-stu-id="94e61-103">Self-service purchase FAQ</span></span>

<span data-ttu-id="94e61-104">自助購買讓使用者有機會嘗試新的技術，並開發最終受益于組織規模較高的解決方案。</span><span class="sxs-lookup"><span data-stu-id="94e61-104">Self-service purchase gives users a chance to try out new technologies and develop solutions that ultimately benefit their larger organizations.</span></span> <span data-ttu-id="94e61-105">中央採購和 IT 小組可透過 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>購買及部署自助購買解決方案的所有使用者都能看到。</span><span class="sxs-lookup"><span data-stu-id="94e61-105">Central procurement and IT teams have visibility to all users who buy and deploy self-service purchase solutions through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="94e61-106">系統管理員可以透過 PowerShell 關閉以每個產品為基礎的自助購買服務。</span><span class="sxs-lookup"><span data-stu-id="94e61-106">Admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="94e61-107">若要深入瞭解，請參閱 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="94e61-107">To learn more, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

<span data-ttu-id="94e61-108">自助購買可用於 Power Platform (Power BI、Power App 及 Power) 、Project 和 Visio 的自動功能。</span><span class="sxs-lookup"><span data-stu-id="94e61-108">Self-service purchase is available for Power Platform (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span>

> [!NOTE]
> <span data-ttu-id="94e61-109">在印度或政府或教育版客戶中，無法使用自助購買服務。</span><span class="sxs-lookup"><span data-stu-id="94e61-109">Self-service purchase isn’t available in India or for government or education customers.</span></span> <span data-ttu-id="94e61-110">Project 和 Visio 不適用於巴西的自助購買和剛果民主共和國。</span><span class="sxs-lookup"><span data-stu-id="94e61-110">Project and Visio are not available for self-service purchase in Brazil and the Democratic Republic of Congo.</span></span>

## <a name="making-a-self-service-purchase"></a><span data-ttu-id="94e61-111">進行自助購買</span><span class="sxs-lookup"><span data-stu-id="94e61-111">Making a self-service purchase</span></span>

### <a name="how-does-a-customer-make-a-self-service-purchase"></a><span data-ttu-id="94e61-112">客戶如何進行自助購買？</span><span class="sxs-lookup"><span data-stu-id="94e61-112">How does a customer make a self-service purchase?</span></span>

<span data-ttu-id="94e61-113">客戶可以從產品網站或從應用程式購買提示中，讓自助購買線上。</span><span class="sxs-lookup"><span data-stu-id="94e61-113">Customers can make a self-service purchase online from the product websites or from in-app purchase prompts.</span></span> <span data-ttu-id="94e61-114">客戶會先要求輸入電子郵件地址，以確保他們是現有 Azure Active Directory (AD) 租使用者中的使用者。</span><span class="sxs-lookup"><span data-stu-id="94e61-114">Customers are first asked to enter an email address to ensure that they're a user in an existing Azure Active Directory (AD) tenant.</span></span> <span data-ttu-id="94e61-115">接下來，他們會使用 Azure AD 認證，導向使用者登入。</span><span class="sxs-lookup"><span data-stu-id="94e61-115">Next, they're directed to sign in by using their Azure AD credentials.</span></span> <span data-ttu-id="94e61-116">登入後，系統會要求客戶選取他們想要購買的訂閱數目，並提供信用卡付款。</span><span class="sxs-lookup"><span data-stu-id="94e61-116">After signing in, the customer is asked to select how many subscriptions they want to buy, and to provide credit card payment.</span></span> <span data-ttu-id="94e61-117">購買完成後，即可開始使用其訂閱。</span><span class="sxs-lookup"><span data-stu-id="94e61-117">When the purchase is complete, they can start using their subscription.</span></span> <span data-ttu-id="94e61-118">買方可以存取 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a> 的有限查看權，讓他們可以將授權指派給組織中的其他人。</span><span class="sxs-lookup"><span data-stu-id="94e61-118">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> where they can assign licenses to the product to other people in their organization.</span></span>

### <a name="what-are-the-payment-options-for-self-service-purchases"></a><span data-ttu-id="94e61-119">自助購買的付款選項為何？</span><span class="sxs-lookup"><span data-stu-id="94e61-119">What are the payment options for self-service purchases?</span></span>

<span data-ttu-id="94e61-120">目前，信用卡是唯一可用的支付方式。</span><span class="sxs-lookup"><span data-stu-id="94e61-120">Currently, credit card is the only available payment method.</span></span> <span data-ttu-id="94e61-121">不支援透過開具發票付款。</span><span class="sxs-lookup"><span data-stu-id="94e61-121">Payment through invoicing isn't supported.</span></span>

### <a name="who-can-buy-through-self-service-purchase"></a><span data-ttu-id="94e61-122">誰可以透過自助購買購買？</span><span class="sxs-lookup"><span data-stu-id="94e61-122">Who can buy through self-service purchase?</span></span>

<span data-ttu-id="94e61-123">在受管理 Azure AD 租使用者中具有非來賓使用者帳戶的任何使用者，都可以進行自助購買。</span><span class="sxs-lookup"><span data-stu-id="94e61-123">Any user with a non-guest user account in a managed Azure AD tenant can make a self-service purchase.</span></span> <span data-ttu-id="94e61-124">「自助購買」不適用於政府或教育組織的承租人。</span><span class="sxs-lookup"><span data-stu-id="94e61-124">Self-service purchasing isn’t available to tenants that are government or education organizations.</span></span> <span data-ttu-id="94e61-125">如果這適用于您的組織，則不需要其他動作即可控制自助購買。</span><span class="sxs-lookup"><span data-stu-id="94e61-125">If this applies to your organization, then no additional action is required to control self-service purchase.</span></span>

<span data-ttu-id="94e61-126">不適合自助購買之組織或市場中的使用者，請參閱訊息要求他們聯繫其 IT 管理員。</span><span class="sxs-lookup"><span data-stu-id="94e61-126">Users in organizations or markets who aren’t eligible for self-service purchase see a message asking them to contact their IT admin.</span></span>

### <a name="can-guest-users-buy-through-self-service-purchase"></a><span data-ttu-id="94e61-127">來賓使用者是否可以透過自助購買購買？</span><span class="sxs-lookup"><span data-stu-id="94e61-127">Can guest users buy through self-service purchase?</span></span>

<span data-ttu-id="94e61-128">否，來賓使用者無法在其為來賓的承租人中完成自助購買。</span><span class="sxs-lookup"><span data-stu-id="94e61-128">No, guest users can’t complete a self-service purchase in a tenant in which they're a guest.</span></span>

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a><span data-ttu-id="94e61-129">使用者是否可以透過自助購買從內部部署的 Active Directory 購買？</span><span class="sxs-lookup"><span data-stu-id="94e61-129">Can users synced from an on-premises Active Directory buy through self-service purchase?</span></span>

<span data-ttu-id="94e61-130">如果使用者在合格的 Azure AD 租使用者中有使用中的使用者帳戶，他們就可以完成自助購買。</span><span class="sxs-lookup"><span data-stu-id="94e61-130">If a user has an active user account in an eligible Azure AD tenant, they can complete a self-service purchase.</span></span>

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a><span data-ttu-id="94e61-131">誰可以自行服務購買指派授權？</span><span class="sxs-lookup"><span data-stu-id="94e61-131">Who can self-service purchasers assign licenses to?</span></span>

<span data-ttu-id="94e61-132">自助購買只能將授權指派給相同 Azure AD 租使用者中的使用者。</span><span class="sxs-lookup"><span data-stu-id="94e61-132">Self-service purchasers can only assign licenses to users in the same Azure AD tenant.</span></span> <span data-ttu-id="94e61-133">買方可以存取 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a> 的有限視圖，以指派授權。</span><span class="sxs-lookup"><span data-stu-id="94e61-133">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> to assign licenses.</span></span> <span data-ttu-id="94e61-134">「購買者」可以將授權指派給他們透過自助購買購買的產品，而且只能將這些授權指派給相同 Azure AD 租使用者中的使用者。</span><span class="sxs-lookup"><span data-stu-id="94e61-134">Purchasers can assign licenses to those products that they've bought through self-service purchase, and can only assign those licenses to users in the same Azure AD tenant.</span></span>

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a><span data-ttu-id="94e61-135">自助買方如何查看和管理其購買情況？</span><span class="sxs-lookup"><span data-stu-id="94e61-135">Where does the self-service purchaser see and manage their purchases?</span></span>

<span data-ttu-id="94e61-136">自助購買可在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的有限顯示中管理其購買。</span><span class="sxs-lookup"><span data-stu-id="94e61-136">Self-service purchasers can manage their purchases in the limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="94e61-137">「購買者」可以從內置於所有 Microsoft 365 和 Dynamics online 應用程式的應用程式啟動器中的系統 **管理** 磚，取得系統管理員中心的連線。</span><span class="sxs-lookup"><span data-stu-id="94e61-137">Purchasers can always get to the admin center from the **Admin** tile in the app launcher built into all Microsoft 365 and Dynamics online apps.</span></span> <span data-ttu-id="94e61-138">「購買者」可以查看他們所進行的購買、購買相同服務的其他訂閱，並將這些訂閱的授權指派給其組織中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="94e61-138">Purchasers can view the purchases they've made, buy additional subscriptions to the same service, and assign licenses for those subscriptions to other users in their organization.</span></span> <span data-ttu-id="94e61-139">此外，「購買者」可以查看和支付帳單、更新其支付方式，以及取消訂閱。</span><span class="sxs-lookup"><span data-stu-id="94e61-139">Additionally, purchasers can view and pay their bill, update their payment method, and cancel their subscription.</span></span>

## <a name="pricing"></a><span data-ttu-id="94e61-140">定價</span><span class="sxs-lookup"><span data-stu-id="94e61-140">Pricing</span></span>

### <a name="what-is-the-pricing-for-self-service-purchases"></a><span data-ttu-id="94e61-141">自助購買的定價為何？</span><span class="sxs-lookup"><span data-stu-id="94e61-141">What is the pricing for self-service purchases?</span></span>

<span data-ttu-id="94e61-142">Microsoft 網站提供每項自助購買產品的定價。</span><span class="sxs-lookup"><span data-stu-id="94e61-142">Pricing for each of the products for self-service purchase is available on the Microsoft website.</span></span> <span data-ttu-id="94e61-143">當使用者進行自助購買時，價格也會顯示為結帳體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="94e61-143">Prices are also displayed as part of the checkout experience when users make a self-service purchase.</span></span> <span data-ttu-id="94e61-144">這些價格可能會與組織購買合作夥伴所提供的中央購買或價格時所支付的價格不同。</span><span class="sxs-lookup"><span data-stu-id="94e61-144">These prices may differ from the prices an organization pays when making central purchases or prices offered through a partner.</span></span>

### <a name="who-is-responsible-for-payment"></a><span data-ttu-id="94e61-145">誰負責付款？</span><span class="sxs-lookup"><span data-stu-id="94e61-145">Who is responsible for payment?</span></span>

<span data-ttu-id="94e61-146">透過「自助購買」購買訂閱的人員是已記帳的人員，並根據購買的條款及定價負責付款。</span><span class="sxs-lookup"><span data-stu-id="94e61-146">The person who buys the subscription through self-service purchase is the person who is billed and who is responsible for payment based on the terms and pricing of the purchase.</span></span>

## <a name="admin-capabilities"></a><span data-ttu-id="94e61-147">系統管理功能</span><span class="sxs-lookup"><span data-stu-id="94e61-147">Admin capabilities</span></span>

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a><span data-ttu-id="94e61-148">管理員對自助購買有哪些功能？</span><span class="sxs-lookup"><span data-stu-id="94e61-148">What capabilities does an admin have for self-service purchases?</span></span>

<span data-ttu-id="94e61-149">系統管理員可以在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的組織中，查看其組織中所進行的所有自助購買。</span><span class="sxs-lookup"><span data-stu-id="94e61-149">Admins can view all self-service purchases made in their organization in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="94e61-150">他們可以查看產品、購買購買的訂閱、到期日、訂單記錄、購買價格，以及每個自助購買的指派使用者。</span><span class="sxs-lookup"><span data-stu-id="94e61-150">They can see the product, purchaser name, subscriptions purchased, expiry date, order history, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="94e61-151">在 [電源平臺系統管理中心] 中，系統管理員也可以查看自助購買容量。</span><span class="sxs-lookup"><span data-stu-id="94e61-151">In the Power Platform Admin Center, admins can also view self-service purchases capacity.</span></span> <span data-ttu-id="94e61-152">根據組織的需要，系統管理員可以透過 PowerShell 關閉以每個產品為基礎的自助購買服務。</span><span class="sxs-lookup"><span data-stu-id="94e61-152">If required for their organization, admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="94e61-153">管理員透過自助購買或集中購買的產品，都具有相同的資料管理和存取原則。</span><span class="sxs-lookup"><span data-stu-id="94e61-153">Admins have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="94e61-154">系統管理員也可以控制組織中的使用者是否可以進行自助購買。</span><span class="sxs-lookup"><span data-stu-id="94e61-154">Admins can also control whether users in their organization can make self-service purchases.</span></span> <span data-ttu-id="94e61-155">如需詳細資訊，請參閱 [Use AllowSelfServicePurchase For MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="94e61-155">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a><span data-ttu-id="94e61-156">Microsoft 如何透過啟用自助購買來尊重資料控管和合規性？</span><span class="sxs-lookup"><span data-stu-id="94e61-156">How is Microsoft respecting data governance and compliance by enabling self-service purchase?</span></span>

<span data-ttu-id="94e61-157">系統管理員可以根據其資料控管和合規性需求，控制其承租人中提供哪些服務和產品。</span><span class="sxs-lookup"><span data-stu-id="94e61-157">Admins maintain control over what services and products are available within their tenant based on their data governance and compliance requirements.</span></span> <span data-ttu-id="94e61-158">您的組織開啟的所有資料管理和存取原則，都適用于可用的自助購買服務。</span><span class="sxs-lookup"><span data-stu-id="94e61-158">All data management and access policies that your organization turned on apply to available self-service purchased services.</span></span>

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a><span data-ttu-id="94e61-159">誰擁有從自助購買建立的產品資料？</span><span class="sxs-lookup"><span data-stu-id="94e61-159">Who owns the product data created from self-service purchases?</span></span>

<span data-ttu-id="94e61-160">從透過自助購買購買的產品所建立的資料，由組織擁有及控制。</span><span class="sxs-lookup"><span data-stu-id="94e61-160">Data created from products bought through self-service purchase is owned and controlled by the organization.</span></span>

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a><span data-ttu-id="94e61-161">如何集中購買透過「自助購買」所進行的購買？</span><span class="sxs-lookup"><span data-stu-id="94e61-161">How do I centralize the purchases made through self-service purchase?</span></span>

<span data-ttu-id="94e61-162">管理員可以指派現有的授權，或透過現有的合約和定價為指派給自助購買的使用者，購買自助購買產品的其他訂閱。</span><span class="sxs-lookup"><span data-stu-id="94e61-162">Admins can assign existing licenses or buy additional subscriptions of self-service purchase products through existing agreements and pricing for users assigned to self-service purchases.</span></span> <span data-ttu-id="94e61-163">在指派這些已集中購買的授權之後，系統管理員就可以要求購買者取消其現有的訂閱。</span><span class="sxs-lookup"><span data-stu-id="94e61-163">After assigning these centrally purchased licenses, admins can then request that the purchasers cancel their existing subscriptions.</span></span>

### <a name="where-does-the-admin-see-self-service-purchases"></a><span data-ttu-id="94e61-164">系統管理員會在何處購買自助服務？</span><span class="sxs-lookup"><span data-stu-id="94e61-164">Where does the admin see self-service purchases?</span></span>

<span data-ttu-id="94e61-165">通用和計費系統管理員可以查看透過「自助購買」購買的訂閱，以在  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>計費您的 **產品**。</span><span class="sxs-lookup"><span data-stu-id="94e61-165">Global and billing admins can see subscriptions bought through self-service purchase in **Billing** > **Your products** in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="94e61-166">他們可以篩選 [產品] 清單，只顯示透過中央購買購買的訂閱，或包含透過「自助購買」購買的訂閱。</span><span class="sxs-lookup"><span data-stu-id="94e61-166">They can filter the products list to only show the subscriptions purchased through central procurement, or to include subscriptions bought through self-service purchase.</span></span>

<span data-ttu-id="94e61-167">系統管理員可以查看產品、買方名稱、購買的訂閱、到期日、訂單記錄、購買價格，以及指派的使用者。</span><span class="sxs-lookup"><span data-stu-id="94e61-167">Admins can see the product, purchaser name, subscription purchased, expiry date, order history, the purchase price, and assigned users.</span></span>

## <a name="support-and-training"></a><span data-ttu-id="94e61-168">支援和訓練</span><span class="sxs-lookup"><span data-stu-id="94e61-168">Support and training</span></span>

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a><span data-ttu-id="94e61-169">客戶的 IT 部門或合作夥伴是否預計能夠支援透過自助購買購買的產品？</span><span class="sxs-lookup"><span data-stu-id="94e61-169">Are customers' IT departments or partners expected to support products bought through self-service purchase?</span></span>

<span data-ttu-id="94e61-170">IT 部門和合作夥伴不會期望對透過自助購買購買的產品提供支援。</span><span class="sxs-lookup"><span data-stu-id="94e61-170">IT departments and partners aren't expected to provide support for products bought through self-service purchase.</span></span> <span data-ttu-id="94e61-171">Microsoft 提供自助購買服務的標準支援。</span><span class="sxs-lookup"><span data-stu-id="94e61-171">Microsoft provides standard support for self-service purchasers.</span></span>

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a><span data-ttu-id="94e61-172">如果自助買方致電支援，是否會使用客戶的「Premier 支援」事件？</span><span class="sxs-lookup"><span data-stu-id="94e61-172">If a self-service purchaser calls support, does that use the customer's Premier Support incidents?</span></span>

<span data-ttu-id="94e61-173">自助購買者不會使用客戶的「Premier 支援」事件來接收自助購買的支援。</span><span class="sxs-lookup"><span data-stu-id="94e61-173">Self-service purchasers won't use a customer's Premier Support incidents for receiving support for their self-service purchases.</span></span>

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a><span data-ttu-id="94e61-174">使用者期望透過自助購買購買的產品，如何接收訓練？</span><span class="sxs-lookup"><span data-stu-id="94e61-174">How are users expected to receive training on the products they buy through self-service purchase?</span></span>

<span data-ttu-id="94e61-175">產品網站上提供豐富的使用者訓練。</span><span class="sxs-lookup"><span data-stu-id="94e61-175">Extensive training for users is provided on the product websites.</span></span> <span data-ttu-id="94e61-176">產品已引導教學、檔、範例及強大的社區，以直接從其他使用者取得答案和秘訣。</span><span class="sxs-lookup"><span data-stu-id="94e61-176">The products have guided learning, documentation, samples, and strong communities to get answers and tips directly from other users.</span></span>

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a><span data-ttu-id="94e61-177">使用者離開組織時，自助購買會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="94e61-177">What happens to a self-service purchase if a user leaves the organization?</span></span>

<span data-ttu-id="94e61-178">如果最初購買自助購買產品的人員離開組織，有效的使用者會在訂閱期間繼續完整使用產品。</span><span class="sxs-lookup"><span data-stu-id="94e61-178">If the person who originally bought the self-service purchase product leaves the organization, valid users continue to have full use of the product for the duration of the subscription.</span></span> <span data-ttu-id="94e61-179">在買方直接取消服務，或系統管理員要求取消透過客戶支援的訂閱時，訂閱仍會保持使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="94e61-179">The subscription remains active until the purchaser directly cancels it or an admin requests cancellation of the subscription through customer support.</span></span> <span data-ttu-id="94e61-180">系統管理員也可以選擇將已集中購買的授權指派給已取消之訂閱的使用者。</span><span class="sxs-lookup"><span data-stu-id="94e61-180">Admins may also choose to assign a centrally purchased license to users of the canceled subscription.</span></span>

## <a name="partners"></a><span data-ttu-id="94e61-181">協力程式</span><span class="sxs-lookup"><span data-stu-id="94e61-181">Partners</span></span>

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a><span data-ttu-id="94e61-182">Microsoft 合作夥伴在自助購買方面的角色為何？</span><span class="sxs-lookup"><span data-stu-id="94e61-182">What's the role of Microsoft's partners in self-service purchases?</span></span>

<span data-ttu-id="94e61-183">委派管理許可權的合作夥伴可以在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>中查看自助購買，就像是管理員一樣。合作夥伴可協助您支援要集中使用自助購買購買的產品的組織。</span><span class="sxs-lookup"><span data-stu-id="94e61-183">Partners who have delegated administration privileges can see self-service purchases in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, just like an admin. Partners can help support an organization that wants to centralize products bought through self-service purchases.</span></span> <span data-ttu-id="94e61-184">此外，協力廠商可提供可擴充自助購買功能的解決方案。</span><span class="sxs-lookup"><span data-stu-id="94e61-184">Additionally, partners may offer solutions to extend the capabilities of a self-service purchase.</span></span>