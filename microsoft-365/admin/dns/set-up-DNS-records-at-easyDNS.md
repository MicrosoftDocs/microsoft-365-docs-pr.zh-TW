---
title: 在 easyDNS 針對 Office 365 建立 DNS 記錄
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
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以便在 Office 365 easyDNS。
ms.openlocfilehash: 9d48896de8f841863e25929a46b2f1d2e1b3ced2
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210549"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a><span data-ttu-id="0b835-103">在 easyDNS 針對 Office 365 建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="0b835-103">Create DNS records at easyDNS for Office 365</span></span>

<span data-ttu-id="0b835-104">如果您找不到所需的專案，[請檢查網域常見問題](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="0b835-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0b835-105">您必須在您的註冊機構網站新增下列所有 DNS 記錄，以將郵件路由傳送至 Office 365，並使用您的網域做為小組和商務用 Skype 等。</span><span class="sxs-lookup"><span data-stu-id="0b835-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Office 365, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="0b835-106">附注： SRV 記錄目前無法在所有 easyDNS service 套件下使用。</span><span class="sxs-lookup"><span data-stu-id="0b835-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="0b835-107">您可能需要使用 easyDNS 升級為較高的服務層級，以新增 Office 365 商務用 Skype 所需的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="0b835-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Office 365 Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="0b835-108">確認您擁有包含 TXT 記錄的網域</span><span class="sxs-lookup"><span data-stu-id="0b835-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="0b835-109">移至[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)並以您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0b835-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="0b835-110">在 [**所有網域**] 標題下，選取 [ **dns]。**</span><span class="sxs-lookup"><span data-stu-id="0b835-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="0b835-111">在 [ **TXT 記錄**] 標題下，選取 [編輯] 按鈕（扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="0b835-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="0b835-112">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="0b835-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="0b835-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="0b835-113">**Host**</span></span>|<span data-ttu-id="0b835-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="0b835-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="0b835-115">MS=msXXXXXXXX （在系統管理中心的 [網域] 頁面上，使用您提供的值）</span><span class="sxs-lookup"><span data-stu-id="0b835-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="0b835-116">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0b835-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="0b835-117">請確認記錄是否正確，然後選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="0b835-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="0b835-118">請等候幾分鐘，再繼續進行，這樣您剛才建立的記錄便可以傳播到網際網路，並由 Office 365 偵測。</span><span class="sxs-lookup"><span data-stu-id="0b835-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.</span></span>
    
8. <span data-ttu-id="0b835-119">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="0b835-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
    
9. <span data-ttu-id="0b835-120">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="0b835-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="0b835-121">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="0b835-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="0b835-122">在 [**安裝**] 頁面上，選取 [**啟動安裝程式]。**</span><span class="sxs-lookup"><span data-stu-id="0b835-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="0b835-123">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b835-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a><span data-ttu-id="0b835-124">新增 MX 記錄以將電子郵件路由傳送至 Office 365</span><span class="sxs-lookup"><span data-stu-id="0b835-124">Add an MX record to route email to Office 365</span></span>

1. <span data-ttu-id="0b835-125">移至[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)並以您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0b835-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="0b835-126">在 [**所有網域**] 標題下，選取 [ **dns]。**</span><span class="sxs-lookup"><span data-stu-id="0b835-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="0b835-127">在 [ **MX 記錄**] 標題下，選取 [編輯] 按鈕（扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="0b835-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="0b835-128">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="0b835-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="0b835-129">**區域的郵件**</span><span class="sxs-lookup"><span data-stu-id="0b835-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="0b835-130">**郵件伺服器**</span><span class="sxs-lookup"><span data-stu-id="0b835-130">**MAIL SERVER**</span></span>|<span data-ttu-id="0b835-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="0b835-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0b835-132">\<網域金鑰\>。 mail.protection.outlook.com （從系統管理中心\<的 [網域\> ] 頁面取得您的網域金鑰值）</span><span class="sxs-lookup"><span data-stu-id="0b835-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="0b835-133">0</span><span class="sxs-lookup"><span data-stu-id="0b835-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="0b835-134">如果您想要儲存其他的 MX 記錄以用於備份目的，請將其複製到某個地方。</span><span class="sxs-lookup"><span data-stu-id="0b835-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="0b835-135">在移動之前，請在這裡移除所有其他 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="0b835-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="0b835-136">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0b835-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="0b835-137">請確認記錄是否正確，然後選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="0b835-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="0b835-138">新增必要的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="0b835-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="0b835-139">移至[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)並以您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0b835-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="0b835-140">在 [**所有網域**] 標題下，選取 [ **dns]。**</span><span class="sxs-lookup"><span data-stu-id="0b835-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="0b835-141">在 [ **CNAME/別名記錄**] 標題下，選取 [編輯] 按鈕（扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="0b835-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="0b835-142">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="0b835-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="0b835-143">**主機**</span><span class="sxs-lookup"><span data-stu-id="0b835-143">**HOST**</span></span>|<span data-ttu-id="0b835-144">**Address （必須以 "." 結尾）**</span><span class="sxs-lookup"><span data-stu-id="0b835-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0b835-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0b835-145">autodiscover</span></span>  <br/> |<span data-ttu-id="0b835-146">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="0b835-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="0b835-147">sip</span><span class="sxs-lookup"><span data-stu-id="0b835-147">sip</span></span>  <br/> |<span data-ttu-id="0b835-148">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="0b835-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="0b835-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0b835-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0b835-150">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="0b835-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="0b835-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0b835-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0b835-152">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="0b835-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="0b835-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0b835-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0b835-154">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="0b835-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="0b835-155">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0b835-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="0b835-156">請確認記錄是否正確，然後選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="0b835-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0b835-157">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="0b835-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="0b835-158">移至[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)並以您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0b835-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="0b835-159">在 [**所有網域**] 標題下，選取 [ **dns]。**</span><span class="sxs-lookup"><span data-stu-id="0b835-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="0b835-160">在 [ **TXT 記錄**] 標題下，選取 [編輯] 按鈕（扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="0b835-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="0b835-161">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="0b835-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="0b835-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="0b835-162">**Host**</span></span>|<span data-ttu-id="0b835-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="0b835-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="0b835-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0b835-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="0b835-165">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0b835-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="0b835-166">請確認記錄是否正確，然後選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="0b835-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="0b835-167">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="0b835-167">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="0b835-168">附注： SRV 記錄目前無法用於 easyDNS ' 網域加服務層級。</span><span class="sxs-lookup"><span data-stu-id="0b835-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="0b835-169">您可能需要使用 easyDNS 來新增 SRV 記錄，以升級至較高的服務層級</span><span class="sxs-lookup"><span data-stu-id="0b835-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="0b835-170">移至[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)並以您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0b835-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="0b835-171">在 [**所有網域**] 標題下，選取 [ **dns]。**</span><span class="sxs-lookup"><span data-stu-id="0b835-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="0b835-172">在 [ **SRV 記錄**] 標題下，選取 [編輯] 按鈕（扳手圖示）。</span><span class="sxs-lookup"><span data-stu-id="0b835-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="0b835-173">在 [文字] 欄位中輸入下列記錄：</span><span class="sxs-lookup"><span data-stu-id="0b835-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="0b835-174">**服務**</span><span class="sxs-lookup"><span data-stu-id="0b835-174">**SERVICE**</span></span>|<span data-ttu-id="0b835-175">**原**</span><span class="sxs-lookup"><span data-stu-id="0b835-175">**PROTO**</span></span>|<span data-ttu-id="0b835-176">**主機**</span><span class="sxs-lookup"><span data-stu-id="0b835-176">**HOST**</span></span>|<span data-ttu-id="0b835-177">**Pri**</span><span class="sxs-lookup"><span data-stu-id="0b835-177">**PRI**</span></span>|<span data-ttu-id="0b835-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="0b835-178">**WGT**</span></span>|<span data-ttu-id="0b835-179">**港口**</span><span class="sxs-lookup"><span data-stu-id="0b835-179">**PORT**</span></span>|<span data-ttu-id="0b835-180">**TARGET （必須以 "." 結尾）**</span><span class="sxs-lookup"><span data-stu-id="0b835-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="0b835-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0b835-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0b835-182">_sip</span><span class="sxs-lookup"><span data-stu-id="0b835-182">_sip</span></span>  <br/> |<span data-ttu-id="0b835-183">TLS</span><span class="sxs-lookup"><span data-stu-id="0b835-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="0b835-184">100</span><span class="sxs-lookup"><span data-stu-id="0b835-184">100</span></span>  <br/> |<span data-ttu-id="0b835-185">1 </span><span class="sxs-lookup"><span data-stu-id="0b835-185">1</span></span>  <br/> |<span data-ttu-id="0b835-186">443</span><span class="sxs-lookup"><span data-stu-id="0b835-186">443</span></span>  <br/> |<span data-ttu-id="0b835-187">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="0b835-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="0b835-188">1800</span><span class="sxs-lookup"><span data-stu-id="0b835-188">1800</span></span>  <br/> |
    |<span data-ttu-id="0b835-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0b835-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="0b835-190">TCP</span><span class="sxs-lookup"><span data-stu-id="0b835-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="0b835-191">100</span><span class="sxs-lookup"><span data-stu-id="0b835-191">100</span></span>  <br/> |<span data-ttu-id="0b835-192">1 </span><span class="sxs-lookup"><span data-stu-id="0b835-192">1</span></span>  <br/> |<span data-ttu-id="0b835-193">5061</span><span class="sxs-lookup"><span data-stu-id="0b835-193">5061</span></span>  <br/> |<span data-ttu-id="0b835-194">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="0b835-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="0b835-195">1800</span><span class="sxs-lookup"><span data-stu-id="0b835-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="0b835-196">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0b835-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="0b835-197">請確認記錄是否正確，然後選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="0b835-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

