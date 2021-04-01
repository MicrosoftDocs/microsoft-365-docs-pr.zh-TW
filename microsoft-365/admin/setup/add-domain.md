---
title: 新增網域至 Microsoft 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.openlocfilehash: 747de5f61dc9fce53f82f52b65f701572a56f8d4
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470878"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="3754b-104">新增網域至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3754b-104">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="3754b-105">若您找不到所需內容，請 **[查看網域常見問題集](domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="3754b-105">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="3754b-106">*若要新增、修改或移除網域，您 **必須** 是 [企業或企業方案](https://products.office.com/business/office)的 **全域系統管理員**。這些變更會影響整個承租人、*自訂\* 的系統管理員或 *一般使用者* 無法進行這些變更。\*</span><span class="sxs-lookup"><span data-stu-id="3754b-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="3754b-107">請遵循下列步驟來新增、設定或繼續設定網域。</span><span class="sxs-lookup"><span data-stu-id="3754b-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3754b-108">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="3754b-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="3754b-109">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="3754b-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3754b-110">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="3754b-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="3754b-111">移至 [**設定**  >  **網域**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3754b-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="3754b-112">選取 [ **新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="3754b-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="3754b-113">輸入您要新增的功能變數名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3754b-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="3754b-114">選擇您要如何驗證您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="3754b-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="3754b-115">如果您的網域註冊機構使用 [網域 Connect](#domain-connect-registrars-integrating-with-microsoft-365)，Microsoft 將會您登入您的註冊機構，並確認 microsoft 365 的連線，以 [自動設定您的記錄](../get-help-with-domains/domain-connect.md) 。</span><span class="sxs-lookup"><span data-stu-id="3754b-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="3754b-116">您將會傳回系統管理中心，然後 Microsoft 將會自動驗證您的網域。</span><span class="sxs-lookup"><span data-stu-id="3754b-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="3754b-117">您可以使用 TXT 記錄來驗證您的網域。</span><span class="sxs-lookup"><span data-stu-id="3754b-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="3754b-118">選取 **[下一步]，然後選取 [下一步]** ，查看如何將此 DNS 記錄新增至您註冊機構網站的指示。</span><span class="sxs-lookup"><span data-stu-id="3754b-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="3754b-119">在您新增記錄後，可能需要長達30分鐘的時間來進行驗證。</span><span class="sxs-lookup"><span data-stu-id="3754b-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="3754b-120">您可以將文字檔新增至您網域的網站。</span><span class="sxs-lookup"><span data-stu-id="3754b-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="3754b-121">從安裝精靈選取並下載 .txt 檔案，然後將檔案上傳至網站的最上層資料夾。</span><span class="sxs-lookup"><span data-stu-id="3754b-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="3754b-122">檔案的路徑看起來應該類似下列所示： `http://mydomain.com/ms39978200.txt` 。</span><span class="sxs-lookup"><span data-stu-id="3754b-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="3754b-123">我們會在您的網站上尋找檔案，以確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="3754b-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="3754b-124">選擇您想要如何進行 DNS 變更，Microsoft 才能使用您的網域。</span><span class="sxs-lookup"><span data-stu-id="3754b-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="3754b-125">如果您的註冊機構支援網域連線，請選擇 [ **為我新增 DNS 記錄** []](#domain-connect-registrars-integrating-with-microsoft-365)，Microsoft 將會您登入註冊機構，並確認 microsoft 365 的連線，以 [自動設定您的記錄](../get-help-with-domains/domain-connect.md) 。</span><span class="sxs-lookup"><span data-stu-id="3754b-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="3754b-126">如果您只想要將特定的 Microsoft 365 服務附加至您的網域，請選擇 [ **我要自行新增 DNS 記錄** ]，否則請稍後再進行此操作。</span><span class="sxs-lookup"><span data-stu-id="3754b-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="3754b-127">**如果您確切知道您在做什麼，請選擇此選項。**</span><span class="sxs-lookup"><span data-stu-id="3754b-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="3754b-128">如果您選擇 *自行新增 DNS 記錄*  ，請選取 **[下一步]** ，您將會看到一個頁面，其中包含您需要新增至註冊機構網站以設定網域的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="3754b-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="3754b-129">如果入口網站無法辨認您的註冊機構，您可以[遵循這些一般指示](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="3754b-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="3754b-130">查看我們的[特定主機指示](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 來尋找您的主機，並遵循步驟來新增您需要的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="3754b-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="3754b-131">如果您不知道您網域的 DNS 主機提供者或網域註冊機構，請參閱[尋找您的網域註冊機構或 DNS 主機服務提供者](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="3754b-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="3754b-132">若要稍等片刻，請取消選取 [所有服務]，然後按一下 [ **繼續**]，或在先前的網域連線步驟中，選取 [ **更多選項** ]，然後選取 [ **立即略過此** 項]。</span><span class="sxs-lookup"><span data-stu-id="3754b-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="3754b-133">選取 **[完成]** -您已經完成！</span><span class="sxs-lookup"><span data-stu-id="3754b-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="3754b-134">新增或編輯自訂 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="3754b-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="3754b-135">請遵循下列步驟，為網站或協力廠商服務新增自訂記錄。</span><span class="sxs-lookup"><span data-stu-id="3754b-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="3754b-136">登入 Microsoft 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="3754b-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="3754b-137">移至 [**設定**   >  **網域**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3754b-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="3754b-138">在 [ **網域** ] 頁面上，選取網域。</span><span class="sxs-lookup"><span data-stu-id="3754b-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="3754b-139">在 [ **DNS 設定**] 底下，選取 [ **自訂記錄**]，然後選取 [ **新增自訂記錄**]。</span><span class="sxs-lookup"><span data-stu-id="3754b-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="3754b-140">選取您要新增的 DNS 記錄類型，然後輸入新記錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="3754b-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="3754b-141">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="3754b-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="3754b-142">使用網域連接的註冊機構</span><span class="sxs-lookup"><span data-stu-id="3754b-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="3754b-143">已啟用[網域](https://www.domainconnect.org/)連線註冊機構可讓您將網域新增至 Microsoft 365，並以三個步驟為單位，以分鐘為單位。</span><span class="sxs-lookup"><span data-stu-id="3754b-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="3754b-144">在 [！附注] 中，我們只會確認您擁有網域，然後自動設定您的網域記錄，所以電子郵件會送出至 Microsoft 365 和其他 Microsoft 365 服務，如小組，請與您的網域合作。</span><span class="sxs-lookup"><span data-stu-id="3754b-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3754b-145">啟動設定精靈之前，務必停用瀏覽器中的所有快顯封鎖程式。</span><span class="sxs-lookup"><span data-stu-id="3754b-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="3754b-146">與 Microsoft 365 整合的網域連接註冊機構</span><span class="sxs-lookup"><span data-stu-id="3754b-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="3754b-147">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="3754b-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="3754b-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="3754b-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="3754b-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="3754b-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="3754b-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="3754b-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="3754b-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="3754b-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="3754b-152">Plesk</span><span class="sxs-lookup"><span data-stu-id="3754b-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="3754b-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="3754b-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="3754b-154">使用 SecureServer DNS 主機的 SecureServer 或 WildWestDomains (GoDaddy 轉銷商) </span><span class="sxs-lookup"><span data-stu-id="3754b-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="3754b-155">範例：</span><span class="sxs-lookup"><span data-stu-id="3754b-155">Examples:</span></span>
        - [<span data-ttu-id="3754b-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="3754b-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="3754b-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="3754b-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="3754b-158">我的電子郵件和網站會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="3754b-158">What happens to my email and website?</span></span>

<span data-ttu-id="3754b-159">完成設定之後，您的網域的 MX 記錄會更新，以指向 Microsoft 365，而您網域的所有電子郵件都會開始進入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3754b-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="3754b-160">請確認您已新增使用者，並為在您的網域中取得電子郵件的所有人設定 Microsoft 365 中的信箱！</span><span class="sxs-lookup"><span data-stu-id="3754b-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="3754b-161">如果您擁有商務用途的網站，該網站將會在原處繼續運作。</span><span class="sxs-lookup"><span data-stu-id="3754b-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="3754b-162">網域連接設定步驟不會影響您的網站。</span><span class="sxs-lookup"><span data-stu-id="3754b-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3754b-163">相關文章</span><span class="sxs-lookup"><span data-stu-id="3754b-163">Related articles</span></span>

[<span data-ttu-id="3754b-164">網域常見問題集</span><span class="sxs-lookup"><span data-stu-id="3754b-164">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="3754b-165">什麼是網域？</span><span class="sxs-lookup"><span data-stu-id="3754b-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="3754b-166">在 Microsoft 365 中購買網域名稱</span><span class="sxs-lookup"><span data-stu-id="3754b-166">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="3754b-167">設定您的網域 (主機專用指示)</span><span class="sxs-lookup"><span data-stu-id="3754b-167">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)