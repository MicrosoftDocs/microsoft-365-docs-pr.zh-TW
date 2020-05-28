---
title: 適用于商業客戶的支付服務指令2和強客戶驗證
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 從2019年9月14日開始，您必須先確認進行線上購買之人員的身分識別，才能處理付款。
keywords: 付款服務指令程式2、強客戶驗證、多重要素驗證
ms.openlocfilehash: 571664736ac4c6e825398a076597bf4b69ec31a8
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402211"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="b4d67-104">適用于商業客戶的支付服務指令2和強客戶驗證</span><span class="sxs-lookup"><span data-stu-id="b4d67-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="b4d67-105">從2019年9月14日開始，您必須先確認進行線上購買之人員的身分識別，才能處理付款。</span><span class="sxs-lookup"><span data-stu-id="b4d67-105">Starting on September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="b4d67-106">這種驗證需要多重要素驗證，以協助確保您的線上購買安全且受到保護。</span><span class="sxs-lookup"><span data-stu-id="b4d67-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="b4d67-107">某些國家/地區的此驗證要求的日期會延遲。</span><span class="sxs-lookup"><span data-stu-id="b4d67-107">The date for this verification requirement will be delayed for some countries.</span></span> 

<span data-ttu-id="b4d67-108">如需詳細資訊，請參閱[Microsoft 有關付款服務指令程式的常見問題解答2和強客戶驗證](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)。</span><span class="sxs-lookup"><span data-stu-id="b4d67-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="b4d67-109">需要多重要素驗證時？</span><span class="sxs-lookup"><span data-stu-id="b4d67-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="b4d67-110">目前，使用多重要素驗證的此指令的驗證需求只適用于使用信用卡在歐洲經濟區域的31個國家/地區的客戶。</span><span class="sxs-lookup"><span data-stu-id="b4d67-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="b4d67-111">有時候會因其採取的動作而提示客戶，而且有時候會因現有訂閱或服務的事件而提示他們。</span><span class="sxs-lookup"><span data-stu-id="b4d67-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="b4d67-112">客戶動作</span><span class="sxs-lookup"><span data-stu-id="b4d67-112">Customer Actions</span></span>

<span data-ttu-id="b4d67-113">您的銀行可能需要透過多重要素驗證進行驗證。</span><span class="sxs-lookup"><span data-stu-id="b4d67-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="b4d67-114">一些範例包括：</span><span class="sxs-lookup"><span data-stu-id="b4d67-114">Some examples include:</span></span>
- <span data-ttu-id="b4d67-115">註冊新訂閱</span><span class="sxs-lookup"><span data-stu-id="b4d67-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="b4d67-116">將授權新增至訂閱</span><span class="sxs-lookup"><span data-stu-id="b4d67-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="b4d67-117">新增或取代用來支付訂閱或服務的信用卡</span><span class="sxs-lookup"><span data-stu-id="b4d67-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="b4d67-118">新增或取代帳單設定檔上的信用卡卡</span><span class="sxs-lookup"><span data-stu-id="b4d67-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="b4d67-119">購買應用程式</span><span class="sxs-lookup"><span data-stu-id="b4d67-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="b4d67-120">訂閱生命週期事件</span><span class="sxs-lookup"><span data-stu-id="b4d67-120">Subscription lifecycle events</span></span>

<span data-ttu-id="b4d67-121">經常性付款的費用可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="b4d67-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="b4d67-122">如果是的話，您會收到一封電子郵件，其中有指示遵循的指示。</span><span class="sxs-lookup"><span data-stu-id="b4d67-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="b4d67-123">系統會提示您回應驗證要求並進行您目前的付款。</span><span class="sxs-lookup"><span data-stu-id="b4d67-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="b4d67-124">需要其他協助嗎？</span><span class="sxs-lookup"><span data-stu-id="b4d67-124">Need more help?</span></span>

<span data-ttu-id="b4d67-125">您的金融機構是下列案例的最佳連絡方式：</span><span class="sxs-lookup"><span data-stu-id="b4d67-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="b4d67-126">您沒有收到驗證碼。</span><span class="sxs-lookup"><span data-stu-id="b4d67-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="b4d67-127">在您提交驗證碼之後，驗證程式無法運作。</span><span class="sxs-lookup"><span data-stu-id="b4d67-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="b4d67-128">您不確定信用卡的連絡人資訊正確無誤。</span><span class="sxs-lookup"><span data-stu-id="b4d67-128">You're not sure if the contact info for your credit card is correct.</span></span>
