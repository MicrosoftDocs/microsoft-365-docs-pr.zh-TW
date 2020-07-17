---
title: 讓使用者重設自己的密碼
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 瞭解如何使用自助密碼重設工具來重設密碼。
ms.openlocfilehash: 288613023ee61626bf12f7090ad0ff73139ef06d
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780586"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="cc14b-103">讓使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="cc14b-103">Let users reset their own passwords</span></span>

<span data-ttu-id="cc14b-104">您是否對大量的重設密碼要求感到不勝其擾？</span><span class="sxs-lookup"><span data-stu-id="cc14b-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="cc14b-105">做為 Microsoft 365 系統管理員，您可以讓使用者使用[自助密碼重設工具](https://go.microsoft.com/fwlink/p/?LinkId=522677)，這樣您就不需要重設密碼。</span><span class="sxs-lookup"><span data-stu-id="cc14b-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="cc14b-106">這可為您分擔一些工作！</span><span class="sxs-lookup"><span data-stu-id="cc14b-106">Less work for you!</span></span> 
  
<span data-ttu-id="cc14b-107">以下是一些您需要知道的事項：</span><span class="sxs-lookup"><span data-stu-id="cc14b-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="cc14b-108">您可以使用任何 Microsoft 365 商務版、教育版或非**盈利性的收費**方案，為雲端使用者取得自助密碼重設。</span><span class="sxs-lookup"><span data-stu-id="cc14b-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="cc14b-109">它不會與 Microsoft 365 試用版搭配使用。</span><span class="sxs-lookup"><span data-stu-id="cc14b-109">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="cc14b-110">該工具會使用 Azure。</span><span class="sxs-lookup"><span data-stu-id="cc14b-110">It uses Azure.</span></span> <span data-ttu-id="cc14b-111">當您執行這些步驟時，您將會在 Azure 中自動**免費**取得此項功能。</span><span class="sxs-lookup"><span data-stu-id="cc14b-111">You'll automatically get this feature in Azure for **free** when you do these steps.</span></span> <span data-ttu-id="cc14b-112">如果您不使用其他的 Azure 功能，開啟自助密碼重設不會花費您任何費用。</span><span class="sxs-lookup"><span data-stu-id="cc14b-112">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="cc14b-113">**如果您使用的是內部部署 Active Directory**，則不會套用上述兩個點。</span><span class="sxs-lookup"><span data-stu-id="cc14b-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="cc14b-114">相反地，您可以設定此設定，但**需要使用 AZURE AD Premium 付費訂閱**。</span><span class="sxs-lookup"><span data-stu-id="cc14b-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="cc14b-115">觀賞有關讓使用者重設其自己密碼的簡短影片。</span><span class="sxs-lookup"><span data-stu-id="cc14b-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="cc14b-116">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="cc14b-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="cc14b-117">讓使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="cc14b-117">Let people reset their own passwords</span></span>

<span data-ttu-id="cc14b-118">下列步驟會針對公司中的所有人員開啟自助密碼重設。</span><span class="sxs-lookup"><span data-stu-id="cc14b-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="cc14b-119">在系統<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>中，移至 [**設定** > **組織設定**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cc14b-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cc14b-120">在系統<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [**設定** \> **安全性 &amp; 隱私權**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cc14b-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cc14b-121">在系統<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [**設定** \> **設定** \> **安全性 &amp; 隱私權**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cc14b-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="cc14b-122">在 [**組織設定**] 頁面的頂端，選取 [**安全性 & 隱私權**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cc14b-122">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="cc14b-123">選取 [**自助密碼重設**]。</span><span class="sxs-lookup"><span data-stu-id="cc14b-123">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="cc14b-124">在 [**自助密碼重設**] 下，選取 **[移至 Azure 入口網站] 以開啟自助密碼重設**。</span><span class="sxs-lookup"><span data-stu-id="cc14b-124">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="cc14b-125">在左功能窗格中，選取 [**使用者**]，然後在 [**使用者] | [所有使用者**] 頁面上，選取 [**密碼重設**]。</span><span class="sxs-lookup"><span data-stu-id="cc14b-125">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="cc14b-126">在 [**屬性**] 頁面上，選取 [**全部**] 以針對您公司內的每個人啟用它，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cc14b-126">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="cc14b-127">當您的使用者登入時，系統會提示他們輸入其他連絡人資訊，以協助他們日後重設其密碼。</span><span class="sxs-lookup"><span data-stu-id="cc14b-127">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cc14b-128">相關文章</span><span class="sxs-lookup"><span data-stu-id="cc14b-128">Related articles</span></span>

[<span data-ttu-id="cc14b-129">設定組織的密碼到期原則</span><span class="sxs-lookup"><span data-stu-id="cc14b-129">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="cc14b-130">設定個別使用者的密碼永不過期</span><span class="sxs-lookup"><span data-stu-id="cc14b-130">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="cc14b-131">Microsoft 365 商務版訓練影片</span><span class="sxs-lookup"><span data-stu-id="cc14b-131">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
