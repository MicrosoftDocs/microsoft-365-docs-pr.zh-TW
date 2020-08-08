---
title: 新增網域至 Microsoft 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: 在您的 DNS 主機上新增 DNS 記錄，將您的網域新增至 Microsoft 365 系統管理中心中的 Microsoft 365。 安裝精靈會引導您完成此程式。
ms.openlocfilehash: 8b70466e5cf82d9cf5be67162263f28ab5bd0d5d
ms.sourcegitcommit: 20c219332270f1013d48b39773dd0e48dabad9e4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2020
ms.locfileid: "46592295"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="5352e-104">新增網域至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5352e-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5352e-105">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="5352e-105">The admin center is changing.</span></span> <span data-ttu-id="5352e-106">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="5352e-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="5352e-107">若您找不到所需內容，請**[查看網域常見問題集](domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="5352e-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="5352e-108">*若要新增、修改或移除網域，您**必須**是[企業或企業方案](https://products.office.com/business/office)的**全域系統管理員**。這些變更會影響整個承租人、*自訂*的系統管理員或*一般使用者*無法進行這些變更。*</span><span class="sxs-lookup"><span data-stu-id="5352e-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="5352e-109">請遵循下列步驟來新增、設定或繼續設定網域。</span><span class="sxs-lookup"><span data-stu-id="5352e-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5352e-110">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="5352e-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="5352e-111">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="5352e-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5352e-112">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="5352e-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="5352e-113">移至 [**設定**  >  **網域**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5352e-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="5352e-114">選取 [**新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="5352e-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="5352e-115">輸入您要新增的功能變數名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5352e-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="5352e-116">選擇您要如何驗證您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="5352e-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="5352e-117">如果您的網域註冊于 GoDaddy 或 1 &amp; 1，請**Sign in**選取  >  **[下一步]** ，Microsoft[將會自動設定記錄](../get-help-with-domains/domain-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="5352e-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="5352e-118">您可以傳送一封含有驗證碼的電子郵件給網域的已登記連絡人。</span><span class="sxs-lookup"><span data-stu-id="5352e-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="5352e-119">如果您無法辨識或存取記錄中的電子郵件，您可以使用第三個選項。</span><span class="sxs-lookup"><span data-stu-id="5352e-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="5352e-120">您可以使用 TXT 記錄來驗證您的網域。</span><span class="sxs-lookup"><span data-stu-id="5352e-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="5352e-121">選取 **[下一步]，然後選取 [下一步]** ，查看如何將此 DNS 記錄新增至您註冊機構網站的指示。</span><span class="sxs-lookup"><span data-stu-id="5352e-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="5352e-122">在您新增記錄後，可能需要長達30分鐘的時間來進行驗證。</span><span class="sxs-lookup"><span data-stu-id="5352e-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="5352e-123">選擇您想要如何進行 DNS 變更，Office 才能使用您的網域。</span><span class="sxs-lookup"><span data-stu-id="5352e-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="5352e-124">如果您想要讓 Office 自動設定 DNS，請選擇 [**為我新增 dns 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="5352e-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="5352e-125">如果您只想要將特定的 Microsoft 365 服務附加至您的網域，請選擇 [**我要自行新增 DNS 記錄**]，否則請稍後再進行此操作。</span><span class="sxs-lookup"><span data-stu-id="5352e-125">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="5352e-126">**如果您確切知道您在做什麼，請選擇此選項。**</span><span class="sxs-lookup"><span data-stu-id="5352e-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="5352e-127">如果您選擇*自行新增 DNS 記錄*，請選取 **[下一步]** ，您將會看到一個頁面，其中包含您需要新增至註冊機構網站以設定網域的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="5352e-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="5352e-128">如果入口網站無法辨認您的註冊機構，您可以[遵循這些一般指示](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="5352e-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="5352e-129">查看我們的[特定主機指示](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) 來尋找您的主機，並遵循步驟來新增您需要的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="5352e-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="5352e-130">如果您不知道您網域的 DNS 主機提供者或網域註冊機構，請參閱[尋找您的網域註冊機構或 DNS 主機服務提供者](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="5352e-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="5352e-131">如果您想稍後等候，請滾動至底部，然後選取 [**略過此步驟**]。</span><span class="sxs-lookup"><span data-stu-id="5352e-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="5352e-132">選取 **[完成]** -您已經完成！</span><span class="sxs-lookup"><span data-stu-id="5352e-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="5352e-133">新增或編輯自訂 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="5352e-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="5352e-134">請遵循下列步驟，為網站或協力廠商服務新增自訂記錄。</span><span class="sxs-lookup"><span data-stu-id="5352e-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="5352e-135">登入 Microsoft 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="5352e-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="5352e-136">移至 [**設定**   >  **網域**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5352e-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="5352e-137">在 [**網域**] 頁面上，選取網域。</span><span class="sxs-lookup"><span data-stu-id="5352e-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="5352e-138">在 [ **DNS 設定**] 底下，選取 [**自訂記錄**]，然後選取 [**新增自訂記錄**]。</span><span class="sxs-lookup"><span data-stu-id="5352e-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="5352e-139">選取您要新增的 DNS 記錄類型，然後輸入新記錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="5352e-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="5352e-140">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5352e-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="5352e-141">使用網域連接的註冊機構</span><span class="sxs-lookup"><span data-stu-id="5352e-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="5352e-142">已啟用[網域](https://www.domainconnect.org/)連線註冊機構可讓您將網域新增至 Microsoft 365，並以三個步驟為單位，以分鐘為單位。</span><span class="sxs-lookup"><span data-stu-id="5352e-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="5352e-143">在 [！附注] 中，我們只會確認您擁有網域，然後自動設定您的網域記錄，所以電子郵件會送出至 Microsoft 365 和其他 Microsoft 365 服務，如小組，請與您的網域合作。</span><span class="sxs-lookup"><span data-stu-id="5352e-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5352e-144">啟動設定精靈之前，務必停用瀏覽器中的所有快顯封鎖程式。</span><span class="sxs-lookup"><span data-stu-id="5352e-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="5352e-145">與 Microsoft 365 整合的網域連接註冊機構</span><span class="sxs-lookup"><span data-stu-id="5352e-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="5352e-146">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="5352e-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="5352e-147">123Reg</span><span class="sxs-lookup"><span data-stu-id="5352e-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="5352e-148">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="5352e-148">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="5352e-149">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="5352e-149">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="5352e-150">Wordpress</span><span class="sxs-lookup"><span data-stu-id="5352e-150">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="5352e-151">Plesk</span><span class="sxs-lookup"><span data-stu-id="5352e-151">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="5352e-152">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="5352e-152">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="5352e-153">使用 SecureServer DNS 主機的 SecureServer 或 WildWestDomains (GoDaddy 轉銷商) </span><span class="sxs-lookup"><span data-stu-id="5352e-153">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="5352e-154">MadDog 網域</span><span class="sxs-lookup"><span data-stu-id="5352e-154">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="5352e-155">CheapNames</span><span class="sxs-lookup"><span data-stu-id="5352e-155">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="5352e-156">我的電子郵件和網站會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="5352e-156">What happens to my email and website?</span></span>

<span data-ttu-id="5352e-157">完成設定之後，您的網域的 MX 記錄會更新，以指向 Microsoft 365，而您網域的所有電子郵件都會開始進入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5352e-157">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="5352e-158">請確認您已新增使用者，並為在您的網域中取得電子郵件的所有人設定 Microsoft 365 中的信箱！</span><span class="sxs-lookup"><span data-stu-id="5352e-158">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="5352e-159">如果您擁有商務用途的網站，該網站將會在原處繼續運作。</span><span class="sxs-lookup"><span data-stu-id="5352e-159">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="5352e-160">網域連接設定步驟不會影響您的網站。</span><span class="sxs-lookup"><span data-stu-id="5352e-160">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5352e-161">相關文章</span><span class="sxs-lookup"><span data-stu-id="5352e-161">Related articles</span></span>

[<span data-ttu-id="5352e-162">網域常見問題集</span><span class="sxs-lookup"><span data-stu-id="5352e-162">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="5352e-163">什麼是網域？</span><span class="sxs-lookup"><span data-stu-id="5352e-163">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="5352e-164">在 Microsoft 365 中購買網域名稱</span><span class="sxs-lookup"><span data-stu-id="5352e-164">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="5352e-165">設定您的網域 (主機專用指示)</span><span class="sxs-lookup"><span data-stu-id="5352e-165">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="5352e-166">取得網域的說明</span><span class="sxs-lookup"><span data-stu-id="5352e-166">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
