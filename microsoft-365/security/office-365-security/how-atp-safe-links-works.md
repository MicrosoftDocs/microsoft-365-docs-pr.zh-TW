---
title: Office 365 ATP 安全連結的運作方式
f1.keywords:
- NOCSH
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
ms.openlocfilehash: c87eef2afbb3a694d9906de0c6c43bfeb576782b
ms.sourcegitcommit: 004f01fc5d5bdb8aac03d69692d86c38b5e05e14
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "42333680"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="c442d-104">Office 365 ATP 安全連結的運作方式</span><span class="sxs-lookup"><span data-stu-id="c442d-104">How Office 365 ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="c442d-105">針對 Office 365 ATP Safe Links 才能正確運作，所有 Office 365 服務必須在相同的版本。</span><span class="sxs-lookup"><span data-stu-id="c442d-105">For Office 365 ATP Safe Links to operate correctly, all of the Office 365 services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="c442d-106">ATP 安全連結的運作方式與 Url 以電子郵件</span><span class="sxs-lookup"><span data-stu-id="c442d-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="c442d-107">在高的層級，以下是[ATP 安全連結](atp-safe-links.md)保護中的運作方式的 Url （裝載於 Office 365，不在內部） 的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="c442d-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="c442d-108">人員會收到電子郵件訊息，其中有些包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="c442d-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="c442d-109">所有電子郵件通過 Exchange Online Protection，其中網際網路通訊協定 (IP) 及信封篩選，簽章型惡意程式碼防護，反垃圾郵件和反惡意軟體篩選器。</span><span class="sxs-lookup"><span data-stu-id="c442d-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="c442d-110">電子郵件會送達人民收件匣。</span><span class="sxs-lookup"><span data-stu-id="c442d-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="c442d-111">使用者登入 Office 365，並移至其電子郵件收件匣。</span><span class="sxs-lookup"><span data-stu-id="c442d-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="c442d-112">使用者開啟電子郵件訊息，並按一下電子郵件訊息中的 URL。</span><span class="sxs-lookup"><span data-stu-id="c442d-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="c442d-113">ATP 安全連結功能立即檢查才能開啟之網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="c442d-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="c442d-114">URL 被識別為惡意，/ 安全封鎖。</span><span class="sxs-lookup"><span data-stu-id="c442d-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="c442d-115">組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="c442d-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="c442d-116">已判定為惡意的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="c442d-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="c442d-117">如果 URL 會前往可下載的檔案，且貴組織的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類內容，會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="c442d-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="c442d-118">如果 URL 會決定為了安全起見，網站會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="c442d-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="c442d-119">ATP 安全連結的運作方式與 Url 中的 Office 文件</span><span class="sxs-lookup"><span data-stu-id="c442d-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="c442d-120">在高層級，此處的[ATP 安全連結](atp-safe-links.md)保護中的運作方式 Url 的 Office 365 專業增強版或商務進階版的應用程式 （目前版本的 Word、 Excel 及 PowerPoint 在 Windows、 Mac，或在瀏覽器、 Office 應用程式，在 iOS 或 Android 裝置，Visio 在 Windows 上的、 在瀏覽器中的 OneNote）：</span><span class="sxs-lookup"><span data-stu-id="c442d-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="c442d-121">人員擁有其電腦、 智慧型手機或平板電腦上安裝 Office 365 專業增強版或商務進階版。</span><span class="sxs-lookup"><span data-stu-id="c442d-121">People have installed Office 365 ProPlus or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="c442d-122">（或是在其瀏覽器中使用 Office]）。</span><span class="sxs-lookup"><span data-stu-id="c442d-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="c442d-123">使用者 （在桌面上），開啟 Word、 Excel、 PowerPoint、 OneNote （在瀏覽器中） 或 Visio，並為 Office 365 企業版使用其公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="c442d-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="c442d-124">文件中包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="c442d-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="c442d-125">當使用者在 [文件中的 URL 時，連結會檢查 ATP 安全連結服務。</span><span class="sxs-lookup"><span data-stu-id="c442d-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="c442d-126">URL 是包含在組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)的網站，如果使用者不會採取至[警告頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="c442d-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="c442d-127">如果已決定為惡意的網站 URL，使用者會採取至[警告頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="c442d-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="c442d-128">如果 URL 會前往可下載的檔案，且[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類的下載項目，會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="c442d-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="c442d-129">URL 會被視為安全，如果使用者不會採取至網站。</span><span class="sxs-lookup"><span data-stu-id="c442d-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="c442d-130">如果 URL 檢查失敗，將不會觸發安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="c442d-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="c442d-131">在桌面用戶端中，將會繼續透過站台之前警告使用者。</span><span class="sxs-lookup"><span data-stu-id="c442d-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="c442d-132">可能需要幾秒的每個工作階段開頭，若要確認使用者已啟用的 Office 的 ATP 安全連結。</span><span class="sxs-lookup"><span data-stu-id="c442d-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
