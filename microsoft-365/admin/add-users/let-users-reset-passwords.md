---
title: 讓使用者在 Office 365 中自行重設密碼
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 了解如何重設密碼使用自助密碼重設工具。
ms.openlocfilehash: 87accc393d08b922ebc3f75ef1aa5ddb2d0b2955
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239366"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="c2fea-103">讓使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="c2fea-103">Let users reset their own passwords</span></span>

<span data-ttu-id="c2fea-104">您是否對大量的重設密碼要求感到不勝其擾？</span><span class="sxs-lookup"><span data-stu-id="c2fea-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="c2fea-105">Microsoft 365 系統管理員，您可以讓人員使用[自助密碼重設工具](https://go.microsoft.com/fwlink/p/?LinkId=522677)因此您不需要為他們重設密碼。</span><span class="sxs-lookup"><span data-stu-id="c2fea-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="c2fea-106">這可為您分擔一些工作！</span><span class="sxs-lookup"><span data-stu-id="c2fea-106">Less work for you!</span></span> 
  
<span data-ttu-id="c2fea-107">以下是一些您需要知道的事項：</span><span class="sxs-lookup"><span data-stu-id="c2fea-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="c2fea-108">您收到自助密碼重設雲端使用者**免費**與 Office 365 商務、 教育或非營利組織付費的方案。</span><span class="sxs-lookup"><span data-stu-id="c2fea-108">You get self-service password reset for cloud users **free** with any Office 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="c2fea-109">此工具無法搭配 Office 365 試用版。</span><span class="sxs-lookup"><span data-stu-id="c2fea-109">It doesn't work with Office 365 trial.</span></span> 
    
- <span data-ttu-id="c2fea-110">該工具會使用 Azure。</span><span class="sxs-lookup"><span data-stu-id="c2fea-110">It uses Azure.</span></span> <span data-ttu-id="c2fea-111">您將會自動取得這項功能在 Azure 中的**免費**當您執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="c2fea-111">You'll automatically get this feature in Azure for **free** when you do these steps.</span></span> <span data-ttu-id="c2fea-112">如果您不使用其他的 Azure 功能，開啟自助密碼重設不會花費您任何費用。</span><span class="sxs-lookup"><span data-stu-id="c2fea-112">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="c2fea-113">**如果您使用內部部署 Active Directory**，則不適用上述兩個點。</span><span class="sxs-lookup"><span data-stu-id="c2fea-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="c2fea-114">相反地，您可以設定此但**需要 Azure AD Premium 的付費的訂閱**。</span><span class="sxs-lookup"><span data-stu-id="c2fea-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="c2fea-115">觀看短片讓使用者重設自己的密碼。</span><span class="sxs-lookup"><span data-stu-id="c2fea-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="c2fea-116">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="c2fea-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="c2fea-117">讓人員重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="c2fea-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="c2fea-118">下列步驟會針對公司中的所有人員開啟自助密碼重設。</span><span class="sxs-lookup"><span data-stu-id="c2fea-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1.  <span data-ttu-id="c2fea-119">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全性 & 隱私權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c2fea-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c2fea-120">在<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">系統管理中心</a>，移至 [**設定** \> **安全性&amp;隱私權**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c2fea-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c2fea-121">在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">系統管理中心</a>，移至 [**設定** \> **安全性&amp;隱私權**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c2fea-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="c2fea-122">[**讓人員自行重設密碼**，請選取**Azure AD 系統管理中心**] 的連結。</span><span class="sxs-lookup"><span data-stu-id="c2fea-122">Under **Let your people reset their own passwords**, select the link for the **Azure AD admin center**.</span></span> <span data-ttu-id="c2fea-123">您將能免費取得 Azure！</span><span class="sxs-lookup"><span data-stu-id="c2fea-123">You'll get Azure for free!</span></span>
  
3. <span data-ttu-id="c2fea-124">在左導覽中，選取**使用者**，然後選取 [**重設密碼**。</span><span class="sxs-lookup"><span data-stu-id="c2fea-124">Select **Users** in the left navigation, and then select **Password reset**.</span></span>
  
4. <span data-ttu-id="c2fea-125">在 [屬性] 頁面上選取 [**所有**貴公司中的所有人啟用它，然後選取 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="c2fea-125">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="c2fea-126">當使用者登入 Office 365 時，系統將提示使用者輸入額外的連絡資訊以協助日後重設使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="c2fea-126">When your users sign in to Office 365, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c2fea-127">相關文章</span><span class="sxs-lookup"><span data-stu-id="c2fea-127">Related articles</span></span>

[<span data-ttu-id="c2fea-128">設定組織的密碼到期原則</span><span class="sxs-lookup"><span data-stu-id="c2fea-128">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="c2fea-129">設定個別使用者的密碼永不過期</span><span class="sxs-lookup"><span data-stu-id="c2fea-129">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="c2fea-130">Microsoft 365 商務版訓練影片</span><span class="sxs-lookup"><span data-stu-id="c2fea-130">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
