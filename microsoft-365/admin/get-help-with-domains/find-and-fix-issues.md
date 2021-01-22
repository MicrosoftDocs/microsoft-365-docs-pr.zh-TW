---
title: 尋找並修正新增網域或 DNS 記錄之後所發生的問題
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
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: 瞭解如何確認 DNS 記錄設定正確，以追蹤在設定自訂網域時所遇到之任何問題。
ms.openlocfilehash: 786df75f3f8a514e9b3c2a7666d715c9abd082bd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926387"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="02db0-103">尋找並修正新增網域或 DNS 記錄之後所發生的問題</span><span class="sxs-lookup"><span data-stu-id="02db0-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="02db0-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="02db0-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="02db0-105">設定您的網域以與 Microsoft 365 一起使用可能十分困難。</span><span class="sxs-lookup"><span data-stu-id="02db0-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="02db0-106">使用 DNS 系統的限制頗多，而且您網域的 DNS 設定也會影響到重要的商務活動，例如電子郵件！</span><span class="sxs-lookup"><span data-stu-id="02db0-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="02db0-107">您可以檢查網域的狀態來檢查網域的問題。</span><span class="sxs-lookup"><span data-stu-id="02db0-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="02db0-108">請前往 **設定**  >  **網域**，並查看狀態列中的通知。</span><span class="sxs-lookup"><span data-stu-id="02db0-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="02db0-109">如果您看到問題，請選取 (三個點) ，然後選擇檢查健康 **狀態**。</span><span class="sxs-lookup"><span data-stu-id="02db0-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="02db0-110">開啟的窗格會描述您的網域發生的任何問題。</span><span class="sxs-lookup"><span data-stu-id="02db0-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="02db0-111">What's going on?</span><span class="sxs-lookup"><span data-stu-id="02db0-111">What's going on?</span></span>

- [<span data-ttu-id="02db0-112">無法驗證您的網域嗎？</span><span class="sxs-lookup"><span data-stu-id="02db0-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="02db0-113">Outlook 無法正常使用？</span><span class="sxs-lookup"><span data-stu-id="02db0-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="02db0-114">每個人的電子郵件都切換至 Microsoft 365，而您只想切換您的電子郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="02db0-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="02db0-115">無法確認非營利組織或學校帳戶狀態？</span><span class="sxs-lookup"><span data-stu-id="02db0-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="02db0-116">服務無法與網域一起使用嗎？</span><span class="sxs-lookup"><span data-stu-id="02db0-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="02db0-117">無法存取您的網站嗎？</span><span class="sxs-lookup"><span data-stu-id="02db0-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="02db0-118">無法驗證您的網域嗎？</span><span class="sxs-lookup"><span data-stu-id="02db0-118">Can't verify your domain?</span></span>
<span data-ttu-id="02db0-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="02db0-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="02db0-120">網域驗證無法運作的幾個常見原因如下：</span><span class="sxs-lookup"><span data-stu-id="02db0-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="02db0-p103">**驗證記錄值錯誤。** 請仔細檢查您複製並貼入 DNS 主機 TXT 驗證記錄的值是否正確。常見的問題是記錄中未包含 "MS="。我們也需要這個！</span><span class="sxs-lookup"><span data-stu-id="02db0-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="02db0-125">**尚未儲存記錄。**</span><span class="sxs-lookup"><span data-stu-id="02db0-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="02db0-126">在某些 DNS 主機中，您還需要額外採取一個步驟來儲存區域檔案 (DNS 記錄的儲存位置)，以便在網際網路上更新該檔案。</span><span class="sxs-lookup"><span data-stu-id="02db0-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="02db0-127">請確認您儲存了變更，Microsoft 365 才能查看並驗證記錄。</span><span class="sxs-lookup"><span data-stu-id="02db0-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="02db0-128">**記錄尚未在網際網路上更新。**</span><span class="sxs-lookup"><span data-stu-id="02db0-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="02db0-129">通常只需要幾分鐘的時間，我們才能看到新記錄，但有時可能需要幾個小時。</span><span class="sxs-lookup"><span data-stu-id="02db0-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="02db0-130">Outlook 無法運作嗎？</span><span class="sxs-lookup"><span data-stu-id="02db0-130">Outlook isn't working?</span></span>
<span data-ttu-id="02db0-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="02db0-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="02db0-132">如果您已為網域設定正確的 MX 記錄及其他 DNS 記錄，但是郵件無法運作，請讓我們協助您 [修正 Outlook 問題](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。</span><span class="sxs-lookup"><span data-stu-id="02db0-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="02db0-133">每個人的電子郵件都切換至 Microsoft 365，而您只想切換您的電子郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="02db0-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="02db0-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="02db0-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="02db0-135">當您將網域新增到 Microsoft 365 時，網域的 MX 記錄通常會由您或 Microsoft 365) 更新 (以指向 Microsoft 365，而所有寄至該網域的電子郵件都會開始送往 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="02db0-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="02db0-136">變更 MX 記錄之前，請確認您為網域中擁有電子郵件的每個人，在 Microsoft 365 中建立信箱。</span><span class="sxs-lookup"><span data-stu-id="02db0-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="02db0-137">如果您不想將您網域中的每個人的電子郵件移至 Microsoft 365，會如何？</span><span class="sxs-lookup"><span data-stu-id="02db0-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="02db0-138">您可以採取一些步驟，只以幾個電子郵件地址試驗[Microsoft 365。](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="02db0-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="02db0-139">無法確認非營利組織或學校帳戶狀態？</span><span class="sxs-lookup"><span data-stu-id="02db0-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="02db0-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="02db0-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="02db0-141">當您只需要驗證貴組織的網域，而不需要設定任何服務時，有幾個情況。</span><span class="sxs-lookup"><span data-stu-id="02db0-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="02db0-142">例如，向 Microsoft 365 證明貴組織符合學校訂閱的資格。</span><span class="sxs-lookup"><span data-stu-id="02db0-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="02db0-143">查看驗證 [您的 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 網域以證明擁有權、非營利組織版或教育版狀態的指引，或啟用 Yammer 以確保您已完成所有必要的步驟。</span><span class="sxs-lookup"><span data-stu-id="02db0-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="02db0-144">這在每個情況中會有些不同。</span><span class="sxs-lookup"><span data-stu-id="02db0-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="02db0-145">您的網域無法使用服務嗎？</span><span class="sxs-lookup"><span data-stu-id="02db0-145">Services not working with your domain?</span></span>
<span data-ttu-id="02db0-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="02db0-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="02db0-147">我們可以協助您追蹤網域的 DNS 設定問題。</span><span class="sxs-lookup"><span data-stu-id="02db0-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="02db0-148">Microsoft 365 中的網域疑難排解員會顯示任何需要修正的記錄，以及記錄所需的設定。</span><span class="sxs-lookup"><span data-stu-id="02db0-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="02db0-149">已正確設定您的 DNS，但是郵件無法在桌面版 Outlook 正常運作？</span><span class="sxs-lookup"><span data-stu-id="02db0-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="02db0-150">查看您可以使用 [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) 使用的不同郵件流程案例，以確保您的公司設定正確。</span><span class="sxs-lookup"><span data-stu-id="02db0-150">Check out the [different mail flow scenarios you can have with Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="02db0-151">或透過電子郵件，取得下列更多疑難排解說明：[修正 Outlook 問題](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。</span><span class="sxs-lookup"><span data-stu-id="02db0-151">Or get more troubleshooting help with email here: [Fix Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="02db0-152">無法存取您的網站嗎？</span><span class="sxs-lookup"><span data-stu-id="02db0-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="02db0-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="02db0-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="02db0-154">如果您已修正任何 DNS 問題，但是仍有問題，請嘗試下列其中一項動作。</span><span class="sxs-lookup"><span data-stu-id="02db0-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="02db0-155">人員無法進入您的網站 www.mydomain.com：[追蹤網站問題](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="02db0-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span></span>
    
- <span data-ttu-id="02db0-156">無法更新 A 記錄或 CNAME 記錄以指向您的網站：更新[Microsoft 365](../dns/add-or-edit-custom-dns-records.md)中的自訂 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="02db0-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="02db0-157">相關內容</span><span class="sxs-lookup"><span data-stu-id="02db0-157">Related content</span></span>

[<span data-ttu-id="02db0-158">疑難排解：稽核已驗證網域變更的資料</span><span class="sxs-lookup"><span data-stu-id="02db0-158">Troubleshoot: Audit data on verified domain change</span></span>](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
