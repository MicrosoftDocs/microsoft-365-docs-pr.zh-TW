---
title: 自助購買常見問題
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: 尋找有關自助購買的常見問題的答案。
ms.date: 08/12/2020
ms.openlocfilehash: 78a7082a966a866f18ac2aa378198dbb33d8c158
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653698"
---
# <a name="self-service-purchase-faq"></a><span data-ttu-id="ab319-103">自助購買常見問題</span><span class="sxs-lookup"><span data-stu-id="ab319-103">Self-service purchase FAQ</span></span>

<span data-ttu-id="ab319-104">自助購買讓使用者有機會嘗試新的技術，並開發最終受益于組織規模較高的解決方案。</span><span class="sxs-lookup"><span data-stu-id="ab319-104">Self-service purchase gives users a chance to try out new technologies and develop solutions that ultimately benefit their larger organizations.</span></span> <span data-ttu-id="ab319-105">中央採購和 IT 小組可透過<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>購買及部署自助購買解決方案的所有使用者都能看到。</span><span class="sxs-lookup"><span data-stu-id="ab319-105">Central procurement and IT teams have visibility to all users who buy and deploy self-service purchase solutions through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="ab319-106">系統管理員可以透過 PowerShell 關閉以每個產品為基礎的自助購買服務。</span><span class="sxs-lookup"><span data-stu-id="ab319-106">Admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="ab319-107">若要深入瞭解，請參閱[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="ab319-107">To learn more, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

<span data-ttu-id="ab319-108">自助購買可用於 Power Platform (Power BI、Power App 及 Power) 、Project 和 Visio 的自動功能。</span><span class="sxs-lookup"><span data-stu-id="ab319-108">Self-service purchase is available for Power Platform (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span>

> [!NOTE]
> <span data-ttu-id="ab319-109">無法在印度使用自助購買，也無法供政府或教育客戶使用。</span><span class="sxs-lookup"><span data-stu-id="ab319-109">Self-service purchase isn’t available in India, and isn’t available to government or education customers.</span></span>

## <a name="making-a-self-service-purchase"></a><span data-ttu-id="ab319-110">進行自助購買</span><span class="sxs-lookup"><span data-stu-id="ab319-110">Making a self-service purchase</span></span>

### <a name="how-does-a-customer-make-a-self-service-purchase"></a><span data-ttu-id="ab319-111">客戶如何進行自助購買？</span><span class="sxs-lookup"><span data-stu-id="ab319-111">How does a customer make a self-service purchase?</span></span>

<span data-ttu-id="ab319-112">客戶可以從產品網站或從應用程式購買提示中，讓自助購買線上。</span><span class="sxs-lookup"><span data-stu-id="ab319-112">Customers can make a self-service purchase online from the product websites or from in-app purchase prompts.</span></span> <span data-ttu-id="ab319-113">客戶會先要求輸入電子郵件地址，以確保他們是現有 Azure Active Directory (AD) 租使用者中的使用者。</span><span class="sxs-lookup"><span data-stu-id="ab319-113">Customers are first asked to enter an email address to ensure that they're a user in an existing Azure Active Directory (AD) tenant.</span></span> <span data-ttu-id="ab319-114">接下來，他們會使用 Azure AD 認證，導向使用者登入。</span><span class="sxs-lookup"><span data-stu-id="ab319-114">Next, they're directed to sign in by using their Azure AD credentials.</span></span> <span data-ttu-id="ab319-115">登入後，系統會要求客戶選取他們想要購買的訂閱數目，並提供信用卡付款。</span><span class="sxs-lookup"><span data-stu-id="ab319-115">After signing in, the customer is asked to select how many subscriptions they want to buy, and to provide credit card payment.</span></span> <span data-ttu-id="ab319-116">購買完成後，即可開始使用其訂閱。</span><span class="sxs-lookup"><span data-stu-id="ab319-116">When the purchase is complete, they can start using their subscription.</span></span> <span data-ttu-id="ab319-117">買方可以存取<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的有限查看權，讓他們可以將授權指派給組織中的其他人。</span><span class="sxs-lookup"><span data-stu-id="ab319-117">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> where they can assign licenses to the product to other people in their organization.</span></span>

### <a name="what-are-the-payment-options-for-self-service-purchases"></a><span data-ttu-id="ab319-118">自助購買的付款選項為何？</span><span class="sxs-lookup"><span data-stu-id="ab319-118">What are the payment options for self-service purchases?</span></span>

<span data-ttu-id="ab319-119">目前，信用卡是唯一可用的支付方式。</span><span class="sxs-lookup"><span data-stu-id="ab319-119">Currently, credit card is the only available payment method.</span></span> <span data-ttu-id="ab319-120">不支援透過開具發票付款。</span><span class="sxs-lookup"><span data-stu-id="ab319-120">Payment through invoicing isn't supported.</span></span>

### <a name="who-can-buy-through-self-service-purchase"></a><span data-ttu-id="ab319-121">誰可以透過自助購買購買？</span><span class="sxs-lookup"><span data-stu-id="ab319-121">Who can buy through self-service purchase?</span></span>

<span data-ttu-id="ab319-122">在受管理 Azure AD 租使用者中具有非來賓使用者帳戶的任何使用者，都可以進行自助購買。</span><span class="sxs-lookup"><span data-stu-id="ab319-122">Any user with a non-guest user account in a managed Azure AD tenant can make a self-service purchase.</span></span> <span data-ttu-id="ab319-123">「自助購買」不適用於政府或教育組織的承租人。</span><span class="sxs-lookup"><span data-stu-id="ab319-123">Self-service purchasing isn’t available to tenants that are government or education organizations.</span></span> <span data-ttu-id="ab319-124">如果這適用于您的組織，則不需要其他動作即可控制自助購買。</span><span class="sxs-lookup"><span data-stu-id="ab319-124">If this applies to your organization, then no additional action is required to control self-service purchase.</span></span>

<span data-ttu-id="ab319-125">不適合自助購買之組織或市場中的使用者，請參閱訊息要求他們聯繫其 IT 管理員。</span><span class="sxs-lookup"><span data-stu-id="ab319-125">Users in organizations or markets who aren’t eligible for self-service purchase see a message asking them to contact their IT admin.</span></span>

### <a name="can-guest-users-buy-through-self-service-purchase"></a><span data-ttu-id="ab319-126">來賓使用者是否可以透過自助購買購買？</span><span class="sxs-lookup"><span data-stu-id="ab319-126">Can guest users buy through self-service purchase?</span></span>

<span data-ttu-id="ab319-127">否，來賓使用者無法在其為來賓的承租人中完成自助購買。</span><span class="sxs-lookup"><span data-stu-id="ab319-127">No, guest users can’t complete a self-service purchase in a tenant in which they're a guest.</span></span>

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a><span data-ttu-id="ab319-128">使用者是否可以透過自助購買從內部部署的 Active Directory 購買？</span><span class="sxs-lookup"><span data-stu-id="ab319-128">Can users synced from an on-premises Active Directory buy through self-service purchase?</span></span>

<span data-ttu-id="ab319-129">如果使用者在合格的 Azure AD 租使用者中有使用中的使用者帳戶，他們就可以完成自助購買。</span><span class="sxs-lookup"><span data-stu-id="ab319-129">If a user has an active user account in an eligible Azure AD tenant, they can complete a self-service purchase.</span></span>

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a><span data-ttu-id="ab319-130">誰可以自行服務購買指派授權？</span><span class="sxs-lookup"><span data-stu-id="ab319-130">Who can self-service purchasers assign licenses to?</span></span>

<span data-ttu-id="ab319-131">自助購買只能將授權指派給相同 Azure AD 租使用者中的使用者。</span><span class="sxs-lookup"><span data-stu-id="ab319-131">Self-service purchasers can only assign licenses to users in the same Azure AD tenant.</span></span> <span data-ttu-id="ab319-132">買方可以存取<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的有限視圖，以指派授權。</span><span class="sxs-lookup"><span data-stu-id="ab319-132">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> to assign licenses.</span></span> <span data-ttu-id="ab319-133">「購買者」可以將授權指派給他們透過自助購買購買的產品，而且只能將這些授權指派給相同 Azure AD 租使用者中的使用者。</span><span class="sxs-lookup"><span data-stu-id="ab319-133">Purchasers can assign licenses to those products that they've bought through self-service purchase, and can only assign those licenses to users in the same Azure AD tenant.</span></span>

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a><span data-ttu-id="ab319-134">自助買方如何查看和管理其購買情況？</span><span class="sxs-lookup"><span data-stu-id="ab319-134">Where does the self-service purchaser see and manage their purchases?</span></span>

<span data-ttu-id="ab319-135">自助購買可在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的有限顯示中管理其購買。</span><span class="sxs-lookup"><span data-stu-id="ab319-135">Self-service purchasers can manage their purchases in the limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="ab319-136">「購買者」可以從內置於所有 Microsoft 365 和 Dynamics online 應用程式的應用程式啟動器中的系統**管理**磚，取得系統管理員中心的連線。</span><span class="sxs-lookup"><span data-stu-id="ab319-136">Purchasers can always get to the admin center from the **Admin** tile in the app launcher built into all Microsoft 365 and Dynamics online apps.</span></span> <span data-ttu-id="ab319-137">「購買者」可以查看他們所進行的購買、購買相同服務的其他訂閱，並將這些訂閱的授權指派給其組織中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="ab319-137">Purchasers can view the purchases they've made, buy additional subscriptions to the same service, and assign licenses for those subscriptions to other users in their organization.</span></span> <span data-ttu-id="ab319-138">此外，「購買者」可以查看和支付帳單、更新其支付方式，以及取消訂閱。</span><span class="sxs-lookup"><span data-stu-id="ab319-138">Additionally, purchasers can view and pay their bill, update their payment method, and cancel their subscription.</span></span>

## <a name="pricing"></a><span data-ttu-id="ab319-139">定價</span><span class="sxs-lookup"><span data-stu-id="ab319-139">Pricing</span></span>

### <a name="what-is-the-pricing-for-self-service-purchases"></a><span data-ttu-id="ab319-140">自助購買的定價為何？</span><span class="sxs-lookup"><span data-stu-id="ab319-140">What is the pricing for self-service purchases?</span></span>

<span data-ttu-id="ab319-141">Microsoft 網站提供每項自助購買產品的定價。</span><span class="sxs-lookup"><span data-stu-id="ab319-141">Pricing for each of the products for self-service purchase is available on the Microsoft website.</span></span> <span data-ttu-id="ab319-142">當使用者進行自助購買時，價格也會顯示為結帳體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="ab319-142">Prices are also displayed as part of the checkout experience when users make a self-service purchase.</span></span> <span data-ttu-id="ab319-143">這些價格可能會與組織購買合作夥伴所提供的中央購買或價格時所支付的價格不同。</span><span class="sxs-lookup"><span data-stu-id="ab319-143">These prices may differ from the prices an organization pays when making central purchases or prices offered through a partner.</span></span>

### <a name="who-is-responsible-for-payment"></a><span data-ttu-id="ab319-144">誰負責付款？</span><span class="sxs-lookup"><span data-stu-id="ab319-144">Who is responsible for payment?</span></span>

<span data-ttu-id="ab319-145">透過「自助購買」購買訂閱的人員是已記帳的人員，並根據購買的條款及定價負責付款。</span><span class="sxs-lookup"><span data-stu-id="ab319-145">The person who buys the subscription through self-service purchase is the person who is billed and who is responsible for payment based on the terms and pricing of the purchase.</span></span>

## <a name="admin-capabilities"></a><span data-ttu-id="ab319-146">系統管理功能</span><span class="sxs-lookup"><span data-stu-id="ab319-146">Admin capabilities</span></span>

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a><span data-ttu-id="ab319-147">管理員對自助購買有哪些功能？</span><span class="sxs-lookup"><span data-stu-id="ab319-147">What capabilities does an admin have for self-service purchases?</span></span>

<span data-ttu-id="ab319-148">系統管理員可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的組織中，查看其組織中所進行的所有自助購買。</span><span class="sxs-lookup"><span data-stu-id="ab319-148">Admins can view all self-service purchases made in their organization in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="ab319-149">他們可以查看產品、購買購買的訂閱、到期日、訂單記錄、購買價格，以及每個自助購買的指派使用者。</span><span class="sxs-lookup"><span data-stu-id="ab319-149">They can see the product, purchaser name, subscriptions purchased, expiry date, order history, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="ab319-150">在 [電源平臺系統管理中心] 中，系統管理員也可以查看自助購買容量。</span><span class="sxs-lookup"><span data-stu-id="ab319-150">In the Power Platform Admin Center, admins can also view self-service purchases capacity.</span></span> <span data-ttu-id="ab319-151">根據組織的需要，系統管理員可以透過 PowerShell 關閉以每個產品為基礎的自助購買服務。</span><span class="sxs-lookup"><span data-stu-id="ab319-151">If required for their organization, admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="ab319-152">管理員透過自助購買或集中購買的產品，都具有相同的資料管理和存取原則。</span><span class="sxs-lookup"><span data-stu-id="ab319-152">Admins have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="ab319-153">系統管理員也可以控制組織中的使用者是否可以進行自助購買。</span><span class="sxs-lookup"><span data-stu-id="ab319-153">Admins can also control whether users in their organization can make self-service purchases.</span></span> <span data-ttu-id="ab319-154">如需詳細資訊，請參閱[Use AllowSelfServicePurchase For MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="ab319-154">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a><span data-ttu-id="ab319-155">Microsoft 如何透過啟用自助購買來尊重資料控管和合規性？</span><span class="sxs-lookup"><span data-stu-id="ab319-155">How is Microsoft respecting data governance and compliance by enabling self-service purchase?</span></span>

<span data-ttu-id="ab319-156">系統管理員可以根據其資料控管和合規性需求，控制其承租人中提供哪些服務和產品。</span><span class="sxs-lookup"><span data-stu-id="ab319-156">Admins maintain control over what services and products are available within their tenant based on their data governance and compliance requirements.</span></span> <span data-ttu-id="ab319-157">您的組織開啟的所有資料管理和存取原則，都適用于可用的自助購買服務。</span><span class="sxs-lookup"><span data-stu-id="ab319-157">All data management and access policies that your organization turned on apply to available self-service purchased services.</span></span>

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a><span data-ttu-id="ab319-158">誰擁有從自助購買建立的產品資料？</span><span class="sxs-lookup"><span data-stu-id="ab319-158">Who owns the product data created from self-service purchases?</span></span>

<span data-ttu-id="ab319-159">從透過自助購買購買的產品所建立的資料，由組織擁有及控制。</span><span class="sxs-lookup"><span data-stu-id="ab319-159">Data created from products bought through self-service purchase is owned and controlled by the organization.</span></span>

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a><span data-ttu-id="ab319-160">如何集中購買透過「自助購買」所進行的購買？</span><span class="sxs-lookup"><span data-stu-id="ab319-160">How do I centralize the purchases made through self-service purchase?</span></span>

<span data-ttu-id="ab319-161">管理員可以指派現有的授權，或透過現有的合約和定價為指派給自助購買的使用者，購買自助購買產品的其他訂閱。</span><span class="sxs-lookup"><span data-stu-id="ab319-161">Admins can assign existing licenses or buy additional subscriptions of self-service purchase products through existing agreements and pricing for users assigned to self-service purchases.</span></span> <span data-ttu-id="ab319-162">在指派這些已集中購買的授權之後，系統管理員就可以要求購買者取消其現有的訂閱。</span><span class="sxs-lookup"><span data-stu-id="ab319-162">After assigning these centrally purchased licenses, admins can then request that the purchasers cancel their existing subscriptions.</span></span>

### <a name="where-does-the-admin-see-self-service-purchases"></a><span data-ttu-id="ab319-163">系統管理員會在何處購買自助服務？</span><span class="sxs-lookup"><span data-stu-id="ab319-163">Where does the admin see self-service purchases?</span></span>

<span data-ttu-id="ab319-164">通用和計費系統管理員可以查看透過「自助購買」購買的**Billing**訂閱，以在  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>計費您的**產品**。</span><span class="sxs-lookup"><span data-stu-id="ab319-164">Global and billing admins can see subscriptions bought through self-service purchase in **Billing** > **Your products** in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="ab319-165">他們可以篩選 [產品] 清單，只顯示透過中央購買購買的訂閱，或包含透過「自助購買」購買的訂閱。</span><span class="sxs-lookup"><span data-stu-id="ab319-165">They can filter the products list to only show the subscriptions purchased through central procurement, or to include subscriptions bought through self-service purchase.</span></span>

<span data-ttu-id="ab319-166">系統管理員可以查看產品、買方名稱、購買的訂閱、到期日、訂單記錄、購買價格，以及指派的使用者。</span><span class="sxs-lookup"><span data-stu-id="ab319-166">Admins can see the product, purchaser name, subscription purchased, expiry date, order history, the purchase price, and assigned users.</span></span>

## <a name="support-and-training"></a><span data-ttu-id="ab319-167">支援和訓練</span><span class="sxs-lookup"><span data-stu-id="ab319-167">Support and training</span></span>

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a><span data-ttu-id="ab319-168">客戶的 IT 部門或合作夥伴是否預計能夠支援透過自助購買購買的產品？</span><span class="sxs-lookup"><span data-stu-id="ab319-168">Are customers' IT departments or partners expected to support products bought through self-service purchase?</span></span>

<span data-ttu-id="ab319-169">IT 部門和合作夥伴不會期望對透過自助購買購買的產品提供支援。</span><span class="sxs-lookup"><span data-stu-id="ab319-169">IT departments and partners aren't expected to provide support for products bought through self-service purchase.</span></span> <span data-ttu-id="ab319-170">Microsoft 提供自助購買服務的標準支援。</span><span class="sxs-lookup"><span data-stu-id="ab319-170">Microsoft provides standard support for self-service purchasers.</span></span>

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a><span data-ttu-id="ab319-171">如果自助買方致電支援，是否會使用客戶的「Premier 支援」事件？</span><span class="sxs-lookup"><span data-stu-id="ab319-171">If a self-service purchaser calls support, does that use the customer's Premier Support incidents?</span></span>

<span data-ttu-id="ab319-172">自助購買者不會使用客戶的「Premier 支援」事件來接收自助購買的支援。</span><span class="sxs-lookup"><span data-stu-id="ab319-172">Self-service purchasers won't use a customer's Premier Support incidents for receiving support for their self-service purchases.</span></span>

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a><span data-ttu-id="ab319-173">使用者期望透過自助購買購買的產品，如何接收訓練？</span><span class="sxs-lookup"><span data-stu-id="ab319-173">How are users expected to receive training on the products they buy through self-service purchase?</span></span>

<span data-ttu-id="ab319-174">產品網站上提供豐富的使用者訓練。</span><span class="sxs-lookup"><span data-stu-id="ab319-174">Extensive training for users is provided on the product websites.</span></span> <span data-ttu-id="ab319-175">產品已引導教學、檔、範例及強大的社區，以直接從其他使用者取得答案和秘訣。</span><span class="sxs-lookup"><span data-stu-id="ab319-175">The products have guided learning, documentation, samples, and strong communities to get answers and tips directly from other users.</span></span>

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a><span data-ttu-id="ab319-176">使用者離開組織時，自助購買會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="ab319-176">What happens to a self-service purchase if a user leaves the organization?</span></span>

<span data-ttu-id="ab319-177">如果最初購買自助購買產品的人員離開組織，有效的使用者會在訂閱期間繼續完整使用產品。</span><span class="sxs-lookup"><span data-stu-id="ab319-177">If the person who originally bought the self-service purchase product leaves the organization, valid users continue to have full use of the product for the duration of the subscription.</span></span> <span data-ttu-id="ab319-178">在買方直接取消服務，或系統管理員要求取消透過客戶支援的訂閱時，訂閱仍會保持使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="ab319-178">The subscription remains active until the purchaser directly cancels it or an admin requests cancellation of the subscription through customer support.</span></span> <span data-ttu-id="ab319-179">系統管理員也可以選擇將已集中購買的授權指派給已取消之訂閱的使用者。</span><span class="sxs-lookup"><span data-stu-id="ab319-179">Admins may also choose to assign a centrally purchased license to users of the canceled subscription.</span></span>

## <a name="partners"></a><span data-ttu-id="ab319-180">協力程式</span><span class="sxs-lookup"><span data-stu-id="ab319-180">Partners</span></span>

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a><span data-ttu-id="ab319-181">Microsoft 合作夥伴在自助購買方面的角色為何？</span><span class="sxs-lookup"><span data-stu-id="ab319-181">What's the role of Microsoft's partners in self-service purchases?</span></span>

<span data-ttu-id="ab319-182">委派管理許可權的合作夥伴可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>中查看自助購買，就像是管理員一樣。合作夥伴可協助您支援要集中使用自助購買購買的產品的組織。</span><span class="sxs-lookup"><span data-stu-id="ab319-182">Partners who have delegated administration privileges can see self-service purchases in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, just like an admin. Partners can help support an organization that wants to centralize products bought through self-service purchases.</span></span> <span data-ttu-id="ab319-183">此外，協力廠商可提供可擴充自助購買功能的解決方案。</span><span class="sxs-lookup"><span data-stu-id="ab319-183">Additionally, partners may offer solutions to extend the capabilities of a self-service purchase.</span></span>