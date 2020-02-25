---
title: 在 easyDNS 建立 Office 365 的 DNS 記錄
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 easyDNS 其他服務的 DNS 記錄。
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251724"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a><span data-ttu-id="28134-103">在 easyDNS 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="28134-103">Create DNS records at easyDNS for Office 365</span></span>

<span data-ttu-id="28134-104">[檢查網域常見問題集](../setup/domains-faq.md)找不到您要尋找。</span><span class="sxs-lookup"><span data-stu-id="28134-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="28134-105">您將需要將所有的下列 DNS 記錄，在您的註冊機構網站新增至郵件路由傳送至 Office 365，您的網域用於 Teams 與 Skype for Business，依此類推。</span><span class="sxs-lookup"><span data-stu-id="28134-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Office 365, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="28134-106">附註： SRV 記錄不目前在所有的 Dns 服務套件。</span><span class="sxs-lookup"><span data-stu-id="28134-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="28134-107">您可能需要升級至較高的服務層級與 easyDNS 新增所需的商務用 Office 365 Skype SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="28134-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Office 365 Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="28134-108">驗證您擁有網域的 TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="28134-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="28134-109">移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="28134-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="28134-110">在**所有網域**標題下，選取 [ **dns。**</span><span class="sxs-lookup"><span data-stu-id="28134-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="28134-111">[ **TXT 記錄**] 標題下，選取 [編輯] 按鈕 （扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="28134-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="28134-112">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="28134-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="28134-113">**Host (主機)**</span><span class="sxs-lookup"><span data-stu-id="28134-113">**Host**</span></span>|<span data-ttu-id="28134-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="28134-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="28134-115">MS = msXXXXXXXX （使用提供給您在系統管理中心的網域] 頁面上的參數值）</span><span class="sxs-lookup"><span data-stu-id="28134-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="28134-116">選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="28134-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="28134-117">請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。</span><span class="sxs-lookup"><span data-stu-id="28134-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="28134-118">請稍候幾分鐘再繼續進行，以便您剛剛建立的記錄可以後於網際網路和 Office 365 所偵測到。</span><span class="sxs-lookup"><span data-stu-id="28134-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.</span></span>
    
8. <span data-ttu-id="28134-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="28134-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
    
9. <span data-ttu-id="28134-120">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="28134-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="28134-121">在 [**網域**] 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="28134-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="28134-122">在 [**安裝**] 頁面上，選取 [**啟動安裝程式。**</span><span class="sxs-lookup"><span data-stu-id="28134-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="28134-123">在 [**驗證網域**] 頁面上，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="28134-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a><span data-ttu-id="28134-124">新增 MX 記錄以將電子郵件路由傳送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="28134-124">Add an MX record to route email to Office 365</span></span>

1. <span data-ttu-id="28134-125">移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="28134-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="28134-126">在**所有網域**標題下，選取 [ **dns。**</span><span class="sxs-lookup"><span data-stu-id="28134-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="28134-127">在**MX 記錄**標題下，選取 [編輯] 按鈕 （扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="28134-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="28134-128">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="28134-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="28134-129">**郵件的區域**</span><span class="sxs-lookup"><span data-stu-id="28134-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="28134-130">**郵件伺服器**</span><span class="sxs-lookup"><span data-stu-id="28134-130">**MAIL SERVER**</span></span>|<span data-ttu-id="28134-131">**依慣用順序排列**</span><span class="sxs-lookup"><span data-stu-id="28134-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="28134-132">\<網域金鑰\>。 mail.protection.outlook.com (取得您\<網域金鑰\>從管理中心的網域] 頁面上的值)</span><span class="sxs-lookup"><span data-stu-id="28134-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="28134-133">0</span><span class="sxs-lookup"><span data-stu-id="28134-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="28134-134">如果您想要儲存備份的用途您其他的 MX 記錄，請將其複製下某處。</span><span class="sxs-lookup"><span data-stu-id="28134-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="28134-135">才可繼續，移除所有其他的 MX 記錄在這裡。</span><span class="sxs-lookup"><span data-stu-id="28134-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="28134-136">選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="28134-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="28134-137">請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。</span><span class="sxs-lookup"><span data-stu-id="28134-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="28134-138">新增所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="28134-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="28134-139">移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="28134-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="28134-140">在**所有網域**標題下，選取 [ **dns。**</span><span class="sxs-lookup"><span data-stu-id="28134-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="28134-141">在**CNAME/別名記錄**標題下，選取 [編輯] 按鈕 （扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="28134-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="28134-142">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="28134-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="28134-143">**主應用程式**</span><span class="sxs-lookup"><span data-stu-id="28134-143">**HOST**</span></span>|<span data-ttu-id="28134-144">**地址 (的結尾必須是 「。 」)**</span><span class="sxs-lookup"><span data-stu-id="28134-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="28134-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="28134-145">autodiscover</span></span>  <br/> |<span data-ttu-id="28134-146">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="28134-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="28134-147">sip</span><span class="sxs-lookup"><span data-stu-id="28134-147">sip</span></span>  <br/> |<span data-ttu-id="28134-148">sipdir.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="28134-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="28134-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="28134-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="28134-150">webdir.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="28134-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="28134-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="28134-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="28134-152">enterpriseregistration.windows.net>。</span><span class="sxs-lookup"><span data-stu-id="28134-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="28134-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="28134-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="28134-154">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="28134-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="28134-155">選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="28134-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="28134-156">請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。</span><span class="sxs-lookup"><span data-stu-id="28134-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="28134-157">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="28134-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="28134-158">移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="28134-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="28134-159">在**所有網域**標題下，選取 [ **dns。**</span><span class="sxs-lookup"><span data-stu-id="28134-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="28134-160">[ **TXT 記錄**] 標題下，選取 [編輯] 按鈕 （扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="28134-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="28134-161">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="28134-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="28134-162">**Host (主機)**</span><span class="sxs-lookup"><span data-stu-id="28134-162">**Host**</span></span>|<span data-ttu-id="28134-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="28134-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="28134-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="28134-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="28134-165">選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="28134-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="28134-166">請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。</span><span class="sxs-lookup"><span data-stu-id="28134-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="28134-167">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="28134-167">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="28134-168">附註： SRV 記錄不目前在 easyDNS' 網域加上的服務層級。</span><span class="sxs-lookup"><span data-stu-id="28134-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="28134-169">您可能需要升級至較高的服務層級使用 Dns 來新增 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="28134-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="28134-170">移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="28134-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="28134-171">在**所有網域**標題下，選取 [ **dns。**</span><span class="sxs-lookup"><span data-stu-id="28134-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="28134-172">在**SRV 記錄**標題下，選取 [編輯] 按鈕 （扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="28134-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="28134-173">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="28134-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="28134-174">**服務**</span><span class="sxs-lookup"><span data-stu-id="28134-174">**SERVICE**</span></span>|<span data-ttu-id="28134-175">**通訊協定**</span><span class="sxs-lookup"><span data-stu-id="28134-175">**PROTO**</span></span>|<span data-ttu-id="28134-176">**主應用程式**</span><span class="sxs-lookup"><span data-stu-id="28134-176">**HOST**</span></span>|<span data-ttu-id="28134-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="28134-177">**PRI**</span></span>|<span data-ttu-id="28134-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="28134-178">**WGT**</span></span>|<span data-ttu-id="28134-179">**連接埠**</span><span class="sxs-lookup"><span data-stu-id="28134-179">**PORT**</span></span>|<span data-ttu-id="28134-180">**目標 (的結尾必須是 「。 」)**</span><span class="sxs-lookup"><span data-stu-id="28134-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="28134-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="28134-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="28134-182">_sip</span><span class="sxs-lookup"><span data-stu-id="28134-182">_sip</span></span>  <br/> |<span data-ttu-id="28134-183">TLS</span><span class="sxs-lookup"><span data-stu-id="28134-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="28134-184">100</span><span class="sxs-lookup"><span data-stu-id="28134-184">100</span></span>  <br/> |<span data-ttu-id="28134-185">1</span><span class="sxs-lookup"><span data-stu-id="28134-185">1</span></span>  <br/> |<span data-ttu-id="28134-186">443</span><span class="sxs-lookup"><span data-stu-id="28134-186">443</span></span>  <br/> |<span data-ttu-id="28134-187">sipdir.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="28134-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="28134-188">1800</span><span class="sxs-lookup"><span data-stu-id="28134-188">1800</span></span>  <br/> |
    |<span data-ttu-id="28134-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="28134-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="28134-190">TCP</span><span class="sxs-lookup"><span data-stu-id="28134-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="28134-191">100</span><span class="sxs-lookup"><span data-stu-id="28134-191">100</span></span>  <br/> |<span data-ttu-id="28134-192">1</span><span class="sxs-lookup"><span data-stu-id="28134-192">1</span></span>  <br/> |<span data-ttu-id="28134-193">5061</span><span class="sxs-lookup"><span data-stu-id="28134-193">5061</span></span>  <br/> |<span data-ttu-id="28134-194">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="28134-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="28134-195">1800</span><span class="sxs-lookup"><span data-stu-id="28134-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="28134-196">選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="28134-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="28134-197">請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。</span><span class="sxs-lookup"><span data-stu-id="28134-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

