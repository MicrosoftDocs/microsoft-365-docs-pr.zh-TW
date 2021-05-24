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
description: 瞭解如何設定原則，讓使用者可以使用自助密碼重設工具來重設自己的密碼。
ms.openlocfilehash: 81fbe1949b8d5e4a601411703d86165f95cc7b7f
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634265"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="f251f-103">讓使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="f251f-103">Let users reset their own passwords</span></span>

<span data-ttu-id="f251f-104">就像 Microsoft 365 管理員一樣，您可以讓人員使用[自助密碼重設工具](https://go.microsoft.com/fwlink/p/?LinkId=522677)，這樣您就不需要重設密碼。</span><span class="sxs-lookup"><span data-stu-id="f251f-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="f251f-105">這可為您分擔一些工作！</span><span class="sxs-lookup"><span data-stu-id="f251f-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="f251f-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="f251f-106">Before you begin</span></span>
  
- <span data-ttu-id="f251f-107">您可以使用任何 Microsoft 365 商務、教育或非盈利性收費方案，**免費** 為雲端使用者取得自助密碼重設。</span><span class="sxs-lookup"><span data-stu-id="f251f-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="f251f-108">它不會與 Microsoft 365 試用版搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f251f-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="f251f-109">該工具會使用 Azure。</span><span class="sxs-lookup"><span data-stu-id="f251f-109">It uses Azure.</span></span> <span data-ttu-id="f251f-110">當您執行這些步驟時，您將會在 Azure 中自動 **免費** 取得此項功能。</span><span class="sxs-lookup"><span data-stu-id="f251f-110">You'll automatically get this feature in Azure for **free** when you do these steps.</span></span> <span data-ttu-id="f251f-111">如果您不使用其他的 Azure 功能，開啟自助密碼重設不會花費您任何費用。</span><span class="sxs-lookup"><span data-stu-id="f251f-111">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="f251f-112">**如果您使用的是內部部署 Active Directory**，則不會套用上述兩個點。</span><span class="sxs-lookup"><span data-stu-id="f251f-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="f251f-113">相反地，您可以設定此設定，但 **需要對 AZURE AD 進階版付費訂閱**。</span><span class="sxs-lookup"><span data-stu-id="f251f-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="f251f-114">本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。</span><span class="sxs-lookup"><span data-stu-id="f251f-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="f251f-115">若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="f251f-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="f251f-116">什麼是系統管理員帳戶？</span><span class="sxs-lookup"><span data-stu-id="f251f-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="f251f-117">您必須是 [全域系統管理員或密碼系統管理員](about-admin-roles.md) ，才可執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="f251f-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="f251f-118">觀賞：讓使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="f251f-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="f251f-119">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](../../business-video/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="f251f-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="f251f-120">步驟：讓使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="f251f-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="f251f-121">下列步驟會針對公司中的所有人員開啟自助密碼重設。</span><span class="sxs-lookup"><span data-stu-id="f251f-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="f251f-122">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>中，移至 [**設定** 的  >  **組織設定**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f251f-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="f251f-123">在 [ **組織設定** ] 頁面的頂端，選取 [ **安全性 & 隱私權** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f251f-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="f251f-124">選取 [ **自助密碼重設**]。</span><span class="sxs-lookup"><span data-stu-id="f251f-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="f251f-125">在 [ **自助密碼重設**] 下，選取 **[移至 Azure 入口網站] 以開啟自助密碼重設**。</span><span class="sxs-lookup"><span data-stu-id="f251f-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="f251f-126">在左功能窗格中，選取 [ **使用者**]，然後在 [ **使用者] | [所有使用者** ] 頁面上，選取 [ **密碼重設**]。</span><span class="sxs-lookup"><span data-stu-id="f251f-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="f251f-127">在 [ **屬性** ] 頁面上，選取 [ **全部** ] 以針對您公司內的每個人啟用它，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f251f-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="f251f-128">當您的使用者登入時，系統會提示他們輸入其他連絡人資訊，以協助他們日後重設其密碼。</span><span class="sxs-lookup"><span data-stu-id="f251f-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="f251f-129">相關內容</span><span class="sxs-lookup"><span data-stu-id="f251f-129">Related content</span></span>

<span data-ttu-id="f251f-130">為[您的組織設定密碼到期原則](../manage/set-password-expiration-policy.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="f251f-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>\
<span data-ttu-id="f251f-131">[將個別使用者的密碼設為永不過期](set-password-to-never-expire.md) (篇文章) </span><span class="sxs-lookup"><span data-stu-id="f251f-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>\
<span data-ttu-id="f251f-132">[Microsoft 365 商務版訓練](../../business-video/index.yml)影片 (連結] 頁面) </span><span class="sxs-lookup"><span data-stu-id="f251f-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
