---
title: Office 365 ATP 安全連結的運作方式
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 「安全連結」可在 Office 文件和電子郵件訊息中提供點擊超連結時即進行驗證的功能。 閱讀本篇文章以了解 ATP 安全連結的運作方式。
ms.openlocfilehash: 56b9ce71ed0f695e2f9ee7d833ecbc980a94edd8
ms.sourcegitcommit: 7705fdbcee4f8714ce044c9e120a431023f7a367
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2020
ms.locfileid: "41230181"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="e463a-104">Office 365 ATP 安全連結的運作方式</span><span class="sxs-lookup"><span data-stu-id="e463a-104">How Office 365 ATP Safe Links works</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="e463a-105">ATP 安全連結的運作方式與 Url 以電子郵件</span><span class="sxs-lookup"><span data-stu-id="e463a-105">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="e463a-106">在高的層級，以下是[ATP 安全連結](atp-safe-links.md)保護中的運作方式的 Url （裝載於 Office 365，不在內部） 的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="e463a-106">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="e463a-107">人員會收到電子郵件訊息，其中有些包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="e463a-107">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="e463a-108">所有電子郵件通過 Exchange Online Protection，其中網際網路通訊協定 (IP) 及信封篩選，簽章型惡意程式碼防護，反垃圾郵件和反惡意軟體篩選器。</span><span class="sxs-lookup"><span data-stu-id="e463a-108">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="e463a-109">電子郵件會送達人民收件匣。</span><span class="sxs-lookup"><span data-stu-id="e463a-109">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="e463a-110">使用者登入 Office 365，並移至其電子郵件收件匣。</span><span class="sxs-lookup"><span data-stu-id="e463a-110">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="e463a-111">使用者開啟電子郵件訊息，並按一下電子郵件訊息中的 URL。</span><span class="sxs-lookup"><span data-stu-id="e463a-111">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="e463a-112">ATP 安全連結功能立即檢查才能開啟之網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="e463a-112">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="e463a-113">URL 被識別為惡意，/ 安全封鎖。</span><span class="sxs-lookup"><span data-stu-id="e463a-113">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="e463a-114">組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="e463a-114">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="e463a-115">已判定為惡意的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="e463a-115">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="e463a-116">如果 URL 會前往可下載的檔案，且貴組織的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類內容，會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="e463a-116">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="e463a-117">如果 URL 會決定為了安全起見，網站會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="e463a-117">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="e463a-118">ATP 安全連結的運作方式與 Url 中的 Office 文件</span><span class="sxs-lookup"><span data-stu-id="e463a-118">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="e463a-119">在高層級，此處的[ATP 安全連結](atp-safe-links.md)保護中的運作方式 Url 的 Office 365 專業增強版或商務進階版的應用程式 （目前版本的 Word、 Excel 及 PowerPoint 在 Windows、 Mac，或在瀏覽器、 Office 應用程式，在 iOS 或 Android 裝置，Visio 在 Windows 上的、 在瀏覽器中的 OneNote）：</span><span class="sxs-lookup"><span data-stu-id="e463a-119">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="e463a-120">人員擁有其電腦、 智慧型手機或平板電腦上安裝 Office 365 專業增強版或商務進階版。</span><span class="sxs-lookup"><span data-stu-id="e463a-120">People have installed Office 365 ProPlus or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="e463a-121">（或是在其瀏覽器中使用 Office]）。</span><span class="sxs-lookup"><span data-stu-id="e463a-121">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="e463a-122">使用者 （在桌面上），開啟 Word、 Excel、 PowerPoint、 OneNote （在瀏覽器中） 或 Visio，並為 Office 365 企業版使用其公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="e463a-122">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="e463a-123">文件中包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="e463a-123">The document contains URLs.</span></span>
    
3. <span data-ttu-id="e463a-124">當使用者在 [文件中的 URL 時，連結會檢查 ATP 安全連結服務。</span><span class="sxs-lookup"><span data-stu-id="e463a-124">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="e463a-125">如果 URL 是包含在[自訂 「 不要重寫 」 Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，該使用者不會採取至網站。</span><span class="sxs-lookup"><span data-stu-id="e463a-125">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
   - <span data-ttu-id="e463a-126">URL 是包含在組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)的網站，如果使用者不會採取至[警告頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="e463a-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="e463a-127">如果已決定為惡意的網站 URL，使用者會採取至[警告頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="e463a-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="e463a-128">如果 URL 會前往可下載的檔案，且[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類的下載項目，會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="e463a-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="e463a-129">URL 會被視為安全，如果使用者不會採取至網站。</span><span class="sxs-lookup"><span data-stu-id="e463a-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="e463a-130">如果 URL 檢查失敗，將不會觸發安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="e463a-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="e463a-131">在桌面用戶端中，將會繼續透過站台之前警告使用者。</span><span class="sxs-lookup"><span data-stu-id="e463a-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="e463a-132">可能需要幾秒的每個工作階段開頭，若要確認使用者已啟用的 Office 的 ATP 安全連結。</span><span class="sxs-lookup"><span data-stu-id="e463a-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
