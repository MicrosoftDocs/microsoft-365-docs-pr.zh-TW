---
title: 讓使用者重設自己的密碼
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 瞭解如何使用自助密碼重設工具重設密碼。
ms.openlocfilehash: c777b9d840e0e9e467c1283fff94eca9a061ee73
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925551"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="238f9-103">讓使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="238f9-103">Let users reset their own passwords</span></span>

<span data-ttu-id="238f9-104">做為 Microsoft 365 系統管理員，您可以讓人員[](https://go.microsoft.com/fwlink/p/?LinkId=522677)使用自助密碼重設工具，如此一來，就不必重設他們的密碼。</span><span class="sxs-lookup"><span data-stu-id="238f9-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="238f9-105">這可為您分擔一些工作！</span><span class="sxs-lookup"><span data-stu-id="238f9-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="238f9-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="238f9-106">Before you begin</span></span>
  
- <span data-ttu-id="238f9-107">您可以使用任何 Microsoft 365商務、教育或非營利組織付費方案免費取得雲端使用者的自助密碼重設。</span><span class="sxs-lookup"><span data-stu-id="238f9-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="238f9-108">它無法與 Microsoft 365 試用版一起使用。</span><span class="sxs-lookup"><span data-stu-id="238f9-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="238f9-109">該工具會使用 Azure。</span><span class="sxs-lookup"><span data-stu-id="238f9-109">It uses Azure.</span></span> <span data-ttu-id="238f9-110">當您執行下列步驟時，會自動在 Azure **中免費** 取得這項功能。</span><span class="sxs-lookup"><span data-stu-id="238f9-110">You'll automatically get this feature in Azure for **free** when you do these steps.</span></span> <span data-ttu-id="238f9-111">如果您不使用其他的 Azure 功能，開啟自助密碼重設不會花費您任何費用。</span><span class="sxs-lookup"><span data-stu-id="238f9-111">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="238f9-112">**如果您使用的是內部部署 Active Directory，** 則不適用上述兩點。</span><span class="sxs-lookup"><span data-stu-id="238f9-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="238f9-113">不過，您可以設定此設定，但需要 **Azure AD Premium** 的付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="238f9-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="238f9-114">本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。</span><span class="sxs-lookup"><span data-stu-id="238f9-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="238f9-115">若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="238f9-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="238f9-116">什麼是系統管理員帳戶？</span><span class="sxs-lookup"><span data-stu-id="238f9-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="238f9-117">您必須是全域 [系統管理員或密碼系統管理員](about-admin-roles.md) 才能執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="238f9-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="238f9-118">觀看：讓使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="238f9-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="238f9-119">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="238f9-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="238f9-120">步驟：讓人員重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="238f9-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="238f9-121">下列步驟會針對公司中的所有人員開啟自助密碼重設。</span><span class="sxs-lookup"><span data-stu-id="238f9-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="238f9-122">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心中</a>， **前往設定** > **組織設定** 頁面。</span><span class="sxs-lookup"><span data-stu-id="238f9-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="238f9-123">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心中</a>，前往設定 \> **安全性 &amp; 隱私權** 頁面。</span><span class="sxs-lookup"><span data-stu-id="238f9-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="238f9-124">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心中</a>，前往設定 **設定** \>  \> **安全性 &amp; 隱私權** 頁面。</span><span class="sxs-lookup"><span data-stu-id="238f9-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="238f9-125">在組織設定 **頁面頂端**，選取安全性與隱私權 **&。**</span><span class="sxs-lookup"><span data-stu-id="238f9-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="238f9-126">選取 **自助密碼重設**。</span><span class="sxs-lookup"><span data-stu-id="238f9-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="238f9-127">在 **自助密碼重設** 下，選取前往 **Azure 入口網站以開啟自助密碼重設**。</span><span class="sxs-lookup"><span data-stu-id="238f9-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="238f9-128">在左側流覽窗格中，選取使用者 **，然後在** 使用者| **所有使用者頁面** ，選取密碼 **重設**。</span><span class="sxs-lookup"><span data-stu-id="238f9-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="238f9-129">在屬性 **頁面上\*\*\*\*，選取全部** 以針對公司中的每個人啟用，**然後選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="238f9-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="238f9-130">當您的使用者進行登錄時，系統會提示使用者輸入其他連絡人資訊，協助他們日後重設密碼。</span><span class="sxs-lookup"><span data-stu-id="238f9-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="238f9-131">相關內容</span><span class="sxs-lookup"><span data-stu-id="238f9-131">Related content</span></span>

[<span data-ttu-id="238f9-132">設定組織的密碼到期原則</span><span class="sxs-lookup"><span data-stu-id="238f9-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="238f9-133">設定個別使用者的密碼永不過期</span><span class="sxs-lookup"><span data-stu-id="238f9-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="238f9-134">Microsoft 365 商務版訓練影片</span><span class="sxs-lookup"><span data-stu-id="238f9-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
