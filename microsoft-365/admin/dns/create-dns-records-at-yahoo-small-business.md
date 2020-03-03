---
title: 在 Yahoo! Small Business 建立 Office 365 的 DNS 記錄
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 034bd7bc-b098-4c4d-8a93-4d74ff24532a
description: 了解如何驗證您的網域，並設定 DNS 記錄的電子郵件、 商務用 Skype 線上商務和其他服務在 yahoo ！ Small Business 建立 Office 365。
ms.openlocfilehash: c178afeb309fba9515e01155a43d5e6b97d1136f
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362638"
---
# <a name="create-dns-records-at-yahoo-small-business-for-office-365"></a><span data-ttu-id="b82b6-105">在 Yahoo!</span><span class="sxs-lookup"><span data-stu-id="b82b6-105">Create DNS records at Yahoo!</span></span> <span data-ttu-id="b82b6-106">Small Business 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="b82b6-106">Small Business for Office 365</span></span>

 <span data-ttu-id="b82b6-107">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="b82b6-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b82b6-p104">如果 Yahoo! Small Business 一直是您的 DNS 主機服務提供者，請注意，您的提供者現在應該是 Aabaco Small Business。</span><span class="sxs-lookup"><span data-stu-id="b82b6-p104">If Yahoo! Small Business has been your DNS hosting provider, you should be aware that your provider is now Aabaco Small Business.</span></span>
  
<span data-ttu-id="b82b6-110">請依照本文中的步驟建立 Aabaco 帳戶，以在 Aabaco 變更 DNS 設定並為您的網域續約。</span><span class="sxs-lookup"><span data-stu-id="b82b6-110">Follow the steps in this article to create an account at Aabaco, where you can make DNS changes and renew your domain or domains.</span></span>
  
<span data-ttu-id="b82b6-111">您可以[建立 DNS 記錄](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)之前，您必須建立 Aabaco 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b82b6-111">You must create your Aabaco account before you can [create DNS records](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

  
## <a name="create-an-aabaco-small-business-account"></a><span data-ttu-id="b82b6-112">建立 Aabaco Small Business 帳戶</span><span class="sxs-lookup"><span data-stu-id="b82b6-112">Create an Aabaco Small Business account</span></span>

1. <span data-ttu-id="b82b6-113">若要開始，移至您的網域頁面，以在 Aabaco [使用[此連結](https://www.luminate.com/services/)，然後選取 [**設定您的 Aabaco Small Business 帳戶**。</span><span class="sxs-lookup"><span data-stu-id="b82b6-113">To get started, go to your domains page at Aabaco by using [this link](https://www.luminate.com/services/), and select **Setup your Aabaco Small Business account**.</span></span>
    
    ![選取 [設定您的 Aabaco Small Business 帳戶](../../media/d708f272-d42f-40a1-9aaf-d05d8cfd55cf.png)
  
2. <span data-ttu-id="b82b6-115">提供您的 Yahoo!</span><span class="sxs-lookup"><span data-stu-id="b82b6-115">Provide your Yahoo!</span></span> <span data-ttu-id="b82b6-116">Small Business**電子郵件 /yahoo 識別碼**，，然後選取 [ **I 'm not a robot 不**。</span><span class="sxs-lookup"><span data-stu-id="b82b6-116">Small Business **Email/Yahoo ID**, and then select **I'm not a robot**.</span></span>
    
    ![Select I am not a robot](../../media/ded4b5dd-4e04-4baa-ae31-8426b5799151.png)
  
3. <span data-ttu-id="b82b6-118">選取 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="b82b6-118">Select **Get started**.</span></span>
    
    ![選取 [快速入門](../../media/6674707d-c222-4f0d-bec4-229d39ab2499.png)
  
4. <span data-ttu-id="b82b6-120">登入您的 Yahoo!</span><span class="sxs-lookup"><span data-stu-id="b82b6-120">Sign in to your Yahoo!</span></span> <span data-ttu-id="b82b6-121">Small Business 電子郵件帳戶，並從 Aabaco Small Business 開啟新的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b82b6-121">Small Business email account and open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b82b6-122">重新傳送郵件，若有必要，請選擇 [**重新傳送電子郵件連結**在**您已取得最新產品郵件**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="b82b6-122">Resend the message, if necessary, by choosing the **resend the email link** on the **You've got mail** page.</span></span> 
  
    ![The You've got mail page](../../media/2e02fc30-6cca-40d6-bb64-131a41b4a369.png)
  
5. <span data-ttu-id="b82b6-124">在 Aabaco**確認您的電子郵件地址，若要繼續執行安裝程式**電子郵件訊息中，選取 [**確認電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="b82b6-124">In the Aabaco **Confirm your email address to continue setup** email message, select **Confirm email**.</span></span>
    
    ![選取確認電子郵件](../../media/eb5f5526-6f90-4a10-83a7-5249a1ebd562.png)
  
6. <span data-ttu-id="b82b6-126">在 [**選擇您的密碼**] 頁面中，輸入或複製並貼上您想要使用的 Aabaco 帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="b82b6-126">On the **Choose your password** page, type or copy and paste the password that you want to use for your Aabaco account.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b82b6-p107">您可以使用與 Yahoo! Small Business 帳戶相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="b82b6-p107">You can use the same password that you used with your Yahoo! Small Business account.</span></span> 
  
    ![The Choose your password page](../../media/cc592345-72d1-4a41-9410-a1f3345cfd1d.png)
  
7. <span data-ttu-id="b82b6-130">選取 [**我同意這些條款和條件**]，然後再選取 [**建立密碼**。</span><span class="sxs-lookup"><span data-stu-id="b82b6-130">Select **I agree to the terms and conditions**, and then select **Create password**.</span></span>
    
    ![選取 [建立密碼](../../media/434aa6a3-076e-4abf-a9cf-31145786e819.png)
  
8. <span data-ttu-id="b82b6-132">登入您的 Yahoo!</span><span class="sxs-lookup"><span data-stu-id="b82b6-132">Sign in to your Yahoo!</span></span> <span data-ttu-id="b82b6-133">Small Business 電子郵件帳戶，然後從 Aabaco Small Business 開啟新的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b82b6-133">Small Business email account, and then open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b82b6-134">重新傳送郵件，如有必要，選擇 [上的 [**重新傳送電子郵件連結\*\*\*\*幾乎大功告成 ！**</span><span class="sxs-lookup"><span data-stu-id="b82b6-134">Resend the message, if necessary, by choosing the **resend the email link** on the **You're almost done!**</span></span> <span data-ttu-id="b82b6-135">頁面。</span><span class="sxs-lookup"><span data-stu-id="b82b6-135">page.</span></span> 
  
    ![The You're almost done page](../../media/1a4142a3-e140-48a8-9c80-aa126ff08179.png)
  
9. <span data-ttu-id="b82b6-137">在 Aabaco**後幾乎有**電子郵件訊息中，選取 [**啟用我的帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="b82b6-137">In the Aabaco **You're almost there** email message, select **Activate my account**.</span></span>
    
    ![選取 [啟動我帳戶](../../media/e76d5edc-d8ba-4d8d-872d-d916716c3618.png)
  
10. <span data-ttu-id="b82b6-139">登入您的 Aabaco Small Business 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b82b6-139">Sign in to your Aabaco Small Business account.</span></span>
    
    ![The sign-in page for Aabaco Small Business](../../media/4ef3cfc3-26da-4e03-932b-9346ef217848.png)
  
<span data-ttu-id="b82b6-141">現在您已建立 Aabaco 帳戶，接著可以[在 Aabaco Small Business for Office 365 建立 DNS記錄](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="b82b6-141">Now that you have created your Aabaco account, you can [Create DNS records at Aabaco Small Business for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
