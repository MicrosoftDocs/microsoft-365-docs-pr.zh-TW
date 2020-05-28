---
title: 為您的組織管理軟體即服務應用程式
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 瞭解如何在 Microsoft 365 系統管理中心中啟動和管理協力廠商應用程式。
ms.openlocfilehash: ed1a88345ae5cc135a43f4297ce518b444eaabe7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402579"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="e0b68-103">管理組織的協力廠商應用程式訂閱</span><span class="sxs-lookup"><span data-stu-id="e0b68-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e0b68-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="e0b68-104">The admin center is changing.</span></span> <span data-ttu-id="e0b68-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="e0b68-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e0b68-106">您可以在已開啟預覽模式的 Microsoft 365 系統管理中心中管理協力廠商應用程式的授權和帳單。</span><span class="sxs-lookup"><span data-stu-id="e0b68-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="e0b68-107">更新的功能包括增強型訂閱管理、改進的計費資訊存取，以及更高的管理帳單的彈性。</span><span class="sxs-lookup"><span data-stu-id="e0b68-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="e0b68-108">訂閱管理是以 Microsoft 更新的商務平臺為基礎。</span><span class="sxs-lookup"><span data-stu-id="e0b68-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="e0b68-109">這適用于客戶直接購買的軟體即服務應用程式，或來自協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="e0b68-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="e0b68-110">如何取得軟體即服務應用程式</span><span class="sxs-lookup"><span data-stu-id="e0b68-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="e0b68-111">有幾種方式可購買協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="e0b68-112">**直接購買**–客戶可以直接從[Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)購買訂閱，或[AppSource](https://www.appsource.com/)。</span><span class="sxs-lookup"><span data-stu-id="e0b68-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="e0b68-113">**合作夥伴購買**–透過合作夥伴中心與合作夥伴合作以購買訂閱。</span><span class="sxs-lookup"><span data-stu-id="e0b68-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="e0b68-114">**Microsoft 策劃書**–從 Microsoft Sales （包括協力廠商應用程式）回應提案。</span><span class="sxs-lookup"><span data-stu-id="e0b68-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="e0b68-115">一旦客戶購買應用程式並接受 Microsoft 客戶合約，他們就可以在 Microsoft 365 系統管理中心或 Microsoft Store for Business 中進行管理。</span><span class="sxs-lookup"><span data-stu-id="e0b68-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="e0b68-116">應用程式提供者會以平面的速率（或透過購買使用者的授權）來銷售其應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="e0b68-117">**平直率**–也稱為以網站為基礎的定價，應用程式會以月度或每年價格定價。</span><span class="sxs-lookup"><span data-stu-id="e0b68-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="e0b68-118">在 [應用程式] 頁面上，授權數量是無限期列出。</span><span class="sxs-lookup"><span data-stu-id="e0b68-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="e0b68-119">**授權**–依授權定價應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="e0b68-120">客戶將授權指派給其組織中的每個使用者</span><span class="sxs-lookup"><span data-stu-id="e0b68-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="e0b68-121">支援的地區</span><span class="sxs-lookup"><span data-stu-id="e0b68-121">Supported regions</span></span>

<span data-ttu-id="e0b68-122">您可以在下列地區取得協力廠商應用程式的支援：</span><span class="sxs-lookup"><span data-stu-id="e0b68-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="e0b68-123">阿根廷</span><span class="sxs-lookup"><span data-stu-id="e0b68-123">Argentina</span></span>
- <span data-ttu-id="e0b68-124">澳洲</span><span class="sxs-lookup"><span data-stu-id="e0b68-124">Australia</span></span>
- <span data-ttu-id="e0b68-125">加拿大</span><span class="sxs-lookup"><span data-stu-id="e0b68-125">Canada</span></span>
- <span data-ttu-id="e0b68-126">智利</span><span class="sxs-lookup"><span data-stu-id="e0b68-126">Chile</span></span>
- <span data-ttu-id="e0b68-127">法國</span><span class="sxs-lookup"><span data-stu-id="e0b68-127">France</span></span>
- <span data-ttu-id="e0b68-128">德國</span><span class="sxs-lookup"><span data-stu-id="e0b68-128">Germany</span></span>
- <span data-ttu-id="e0b68-129">希臘</span><span class="sxs-lookup"><span data-stu-id="e0b68-129">Greece</span></span>
- <span data-ttu-id="e0b68-130">波多黎各</span><span class="sxs-lookup"><span data-stu-id="e0b68-130">Puerto Rico</span></span>
- <span data-ttu-id="e0b68-131">南非</span><span class="sxs-lookup"><span data-stu-id="e0b68-131">South Africa</span></span>
- <span data-ttu-id="e0b68-132">英國</span><span class="sxs-lookup"><span data-stu-id="e0b68-132">United Kingdom</span></span>
- <span data-ttu-id="e0b68-133">美國</span><span class="sxs-lookup"><span data-stu-id="e0b68-133">United States</span></span>
- <span data-ttu-id="e0b68-134">西歐</span><span class="sxs-lookup"><span data-stu-id="e0b68-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="e0b68-135">啟動協力廠商應用程式</span><span class="sxs-lookup"><span data-stu-id="e0b68-135">Activate third-party apps</span></span>

<span data-ttu-id="e0b68-136">系統管理員必須先啟動協力廠商應用程式，才能將其指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="e0b68-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="e0b68-137">這些應用程式會在協力廠商發行者的入口網站中啟用。</span><span class="sxs-lookup"><span data-stu-id="e0b68-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="e0b68-138">在系統管理中心中，移至 [**帳單**  >  **產品**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">應用程式</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e0b68-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e0b68-139">尋找並選取您要管理的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e0b68-140">在 [**設定] & 動作**] 底下，選取 **[在 publisher 的入口網站中管理]**。</span><span class="sxs-lookup"><span data-stu-id="e0b68-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="e0b68-141">您將會被導向至應用程式發行者的網站，您可以在其中啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="e0b68-142">管理協力廠商應用程式</span><span class="sxs-lookup"><span data-stu-id="e0b68-142">Manage third-party apps</span></span>

<span data-ttu-id="e0b68-143">系統管理員會在兩個位置管理協力廠商應用程式： Microsoft 365 系統管理中心和協力廠商應用程式提供者的入口網站。</span><span class="sxs-lookup"><span data-stu-id="e0b68-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="e0b68-144">以下是您可以在每個入口網站中執行的動作。</span><span class="sxs-lookup"><span data-stu-id="e0b68-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="e0b68-145">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e0b68-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="e0b68-146">應用程式發行者入口網站</span><span class="sxs-lookup"><span data-stu-id="e0b68-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="e0b68-147">變更授權數量</span><span class="sxs-lookup"><span data-stu-id="e0b68-147">Change license quantity</span></span> <br> <span data-ttu-id="e0b68-148">管理帳單的支付方式</span><span class="sxs-lookup"><span data-stu-id="e0b68-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="e0b68-149">管理帳單的支付方式</span><span class="sxs-lookup"><span data-stu-id="e0b68-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="e0b68-150">變更支付方式（信用卡）</span><span class="sxs-lookup"><span data-stu-id="e0b68-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="e0b68-151">查看發票</span><span class="sxs-lookup"><span data-stu-id="e0b68-151">View invoice</span></span> <br> <span data-ttu-id="e0b68-152">取消應用程式訂閱</span><span class="sxs-lookup"><span data-stu-id="e0b68-152">Cancel app subscription</span></span> | <span data-ttu-id="e0b68-153">設定應用程式（每個應用程式一次）</span><span class="sxs-lookup"><span data-stu-id="e0b68-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="e0b68-154">將授權指派給使用者</span><span class="sxs-lookup"><span data-stu-id="e0b68-154">Assign licenses to users</span></span> <br> <span data-ttu-id="e0b68-155">技術支援</span><span class="sxs-lookup"><span data-stu-id="e0b68-155">Technical support</span></span> |

<span data-ttu-id="e0b68-156">在應用程式啟動之後，除非取消啟用、到期或付款未保持使用，否則它會保持使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="e0b68-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="e0b68-157">這些事件會將應用程式狀態變更為 [停用]。</span><span class="sxs-lookup"><span data-stu-id="e0b68-157">These events change the app status to disabled.</span></span> <span data-ttu-id="e0b68-158">在應用程式停用之後，就無法再重新開機。</span><span class="sxs-lookup"><span data-stu-id="e0b68-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="e0b68-159">若要繼續使用此應用程式，請購買其另一個複本。</span><span class="sxs-lookup"><span data-stu-id="e0b68-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="e0b68-160">指派授權</span><span class="sxs-lookup"><span data-stu-id="e0b68-160">Assign licenses</span></span>

<span data-ttu-id="e0b68-161">系統管理員必須先啟動協力廠商應用程式，再將其指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="e0b68-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="e0b68-162">它們會在協力廠商發行者的入口網站中啟用。</span><span class="sxs-lookup"><span data-stu-id="e0b68-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="e0b68-163">在 [應用程式] 頁面的 [**設定] & 動作**] 底下，選取要指派授權的連結。</span><span class="sxs-lookup"><span data-stu-id="e0b68-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="e0b68-164">在系統管理中心中，移至 [**帳單**  >  **產品**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">應用程式</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e0b68-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e0b68-165">尋找並選取您要管理的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e0b68-166">在 [**設定 & 動作**] 底下，選取要**在 publisher 入口網站中管理**的連結。</span><span class="sxs-lookup"><span data-stu-id="e0b68-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="e0b68-167">變更授權數量</span><span class="sxs-lookup"><span data-stu-id="e0b68-167">Change license quantity</span></span>

<span data-ttu-id="e0b68-168">系統管理員可以變更其組織所擁有的授權數目。</span><span class="sxs-lookup"><span data-stu-id="e0b68-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="e0b68-169">這只適用于以以座位為基礎的定價所購買的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="e0b68-170">在系統管理中心中，移至 [**帳單**  >  **產品**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">應用程式</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e0b68-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e0b68-171">尋找並選取您要管理的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e0b68-172">選取 [**變更授權數量**]。</span><span class="sxs-lookup"><span data-stu-id="e0b68-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="e0b68-173">管理付款方式</span><span class="sxs-lookup"><span data-stu-id="e0b68-173">Manage payment methods</span></span>

<span data-ttu-id="e0b68-174">軟體即服務應用程式中，每個應用程式都有指派計費設定檔。</span><span class="sxs-lookup"><span data-stu-id="e0b68-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="e0b68-175">計費設定檔可讓您自訂發票上包含的產品，以及您支付發票的方式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="e0b68-176">其中包含：</span><span class="sxs-lookup"><span data-stu-id="e0b68-176">They include:</span></span>

- <span data-ttu-id="e0b68-177">**支付方式**–信用卡或支票/連線轉接</span><span class="sxs-lookup"><span data-stu-id="e0b68-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="e0b68-178">**連絡人資訊**–帳單位址和連絡人名稱</span><span class="sxs-lookup"><span data-stu-id="e0b68-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="e0b68-179">**角色**–可讓您變更帳單設定檔、支付帳單或使用計費設定檔中的付款條件進行購買的角色。</span><span class="sxs-lookup"><span data-stu-id="e0b68-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="e0b68-180">如需計費設定檔的詳細資訊，請參閱[瞭解計費設定檔](https://docs.microsoft.com/microsoft-store/billing-profile)。</span><span class="sxs-lookup"><span data-stu-id="e0b68-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="e0b68-181">變更軟體即服務應用程式訂閱上的帳單設定檔</span><span class="sxs-lookup"><span data-stu-id="e0b68-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="e0b68-182">在系統管理中心中，移至 [**帳單**  >  **產品**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">應用程式</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e0b68-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e0b68-183">尋找並選取您要管理的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e0b68-184">選取 [**帳單設定檔**] 旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e0b68-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="e0b68-185">如需發票的詳細資訊，請參閱[瞭解您的帳單或發票](billing-and-payments/understand-your-invoice.md)。</span><span class="sxs-lookup"><span data-stu-id="e0b68-185">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="e0b68-186">取消軟體即服務應用程式訂閱</span><span class="sxs-lookup"><span data-stu-id="e0b68-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="e0b68-187">您可以從 [應用程式] 頁面取消軟體即服務應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="e0b68-188">在系統管理中心中，移至 [**帳單**  >  **產品**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">應用程式</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e0b68-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e0b68-189">尋找並選取您要管理的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0b68-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e0b68-190">在 [**設定] & 動作**] 下，選取 [**取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="e0b68-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
