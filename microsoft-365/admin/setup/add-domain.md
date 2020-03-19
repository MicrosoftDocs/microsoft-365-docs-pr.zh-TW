---
title: 新增網域至 Office 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: 在您的 DNS 主機上新增 DNS 記錄，將您的網域新增至 Microsoft 365 系統管理中心中的 Office 365。 安裝精靈會引導您完成此程式。
ms.openlocfilehash: 86ca8f986624ad37f780961cb58923ea0a1b2308
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857376"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="f4a15-104">新增網域至 Office 365</span><span class="sxs-lookup"><span data-stu-id="f4a15-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="f4a15-105">若您找不到所需功能，請**[檢查網域常見問題集](domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="f4a15-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="f4a15-106">*若要新增、修改或移除網域，您**必須**是[企業或企業方案](https://products.office.com/business/office)的**全域系統管理員**。這些變更會影響整個承租人、*自訂*的系統管理員或*一般使用者*無法進行這些變更。*</span><span class="sxs-lookup"><span data-stu-id="f4a15-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="f4a15-107">請遵循下列步驟來新增、設定或繼續設定網域。</span><span class="sxs-lookup"><span data-stu-id="f4a15-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f4a15-108">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="f4a15-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="f4a15-109">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="f4a15-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f4a15-110">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="f4a15-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="f4a15-111">移至 [**設定** > **網域**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f4a15-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="f4a15-112">選取 [**新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="f4a15-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="f4a15-113">輸入您要新增的功能變數名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4a15-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="f4a15-114">選擇您要如何驗證您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="f4a15-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="f4a15-115">如果您的網域註冊于 GoDaddy 或 1&amp;1，請選取 [登**入** > **] [下一步]** ，Office 365[將會自動設定記錄](../get-help-with-domains/domain-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="f4a15-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Office 365 [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="f4a15-116">您可以傳送一封含有驗證碼的電子郵件給網域的已登記連絡人。</span><span class="sxs-lookup"><span data-stu-id="f4a15-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="f4a15-117">如果您無法辨識或存取記錄中的電子郵件，您可以使用第三個選項。</span><span class="sxs-lookup"><span data-stu-id="f4a15-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="f4a15-118">您可以使用 TXT 記錄來驗證您的網域。</span><span class="sxs-lookup"><span data-stu-id="f4a15-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="f4a15-119">選取 **[下一步]，然後選取 [下一步]** ，查看如何將此 DNS 記錄新增至您註冊機構網站的指示。</span><span class="sxs-lookup"><span data-stu-id="f4a15-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="f4a15-120">在您新增記錄後，可能需要長達30分鐘的時間來進行驗證。</span><span class="sxs-lookup"><span data-stu-id="f4a15-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="f4a15-121">選擇您想要如何進行 DNS 變更，Office 才能使用您的網域。</span><span class="sxs-lookup"><span data-stu-id="f4a15-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="f4a15-122">如果您想要讓 Office 自動設定 DNS，請選擇 [**為我新增 dns 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="f4a15-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="f4a15-123">如果您只想要將特定的 Office 365 服務附加至您的網域，請選擇 [**我要自行新增 DNS 記錄**]，否則請稍後再進行此操作。</span><span class="sxs-lookup"><span data-stu-id="f4a15-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="f4a15-124">**如果您確切知道您在做什麼，請選擇此選項。**</span><span class="sxs-lookup"><span data-stu-id="f4a15-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="f4a15-125">如果您選擇*自行新增 DNS 記錄*，請選取 **[下一步]** ，您將會看到一個頁面，其中包含您需要新增至註冊機構網站以設定網域的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="f4a15-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="f4a15-126">如果入口網站無法辨認您的註冊機構，您可以[遵循這些一般指示](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f4a15-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="f4a15-127">查看我們的[特定主機指示](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) 來尋找您的主機，並遵循步驟來新增您需要的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="f4a15-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="f4a15-128">如果您不知道您網域的 DNS 主機提供者或網域註冊機構，請參閱[尋找您的網域註冊機構或 DNS 主機服務提供者](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="f4a15-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="f4a15-129">如果您想稍後等候，請滾動至底部，然後選取 [**略過此步驟**]。</span><span class="sxs-lookup"><span data-stu-id="f4a15-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="f4a15-130">選取 **[完成]** -您已經完成！</span><span class="sxs-lookup"><span data-stu-id="f4a15-130">Select **Finish** - you're done!</span></span> 

## <a name="related-articles"></a><span data-ttu-id="f4a15-131">相關文章</span><span class="sxs-lookup"><span data-stu-id="f4a15-131">Related articles</span></span>

[<span data-ttu-id="f4a15-132">網域常見問題集</span><span class="sxs-lookup"><span data-stu-id="f4a15-132">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="f4a15-133">什麼是網域？</span><span class="sxs-lookup"><span data-stu-id="f4a15-133">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="f4a15-134">在 Office 365 中購買網域名稱</span><span class="sxs-lookup"><span data-stu-id="f4a15-134">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="f4a15-135">設定您的網域 (主機專用指示)</span><span class="sxs-lookup"><span data-stu-id="f4a15-135">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="f4a15-136">取得 Office 365 網域的說明</span><span class="sxs-lookup"><span data-stu-id="f4a15-136">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.yml)
