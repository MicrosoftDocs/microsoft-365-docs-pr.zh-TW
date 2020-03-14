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
description: 「安全連結」可在 Office 文件和電子郵件訊息中提供點擊超連結時即進行驗證的功能。 請閱讀本文以瞭解 ATP 安全連結的運作方式。
ms.openlocfilehash: c87eef2afbb3a694d9906de0c6c43bfeb576782b
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633971"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="b5f9f-104">Office 365 ATP 安全連結的運作方式</span><span class="sxs-lookup"><span data-stu-id="b5f9f-104">How Office 365 ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="b5f9f-105">為了讓 Office 365 ATP 安全連結正確運作，所有的 Office 365 服務都必須在相同版本。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-105">For Office 365 ATP Safe Links to operate correctly, all of the Office 365 services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="b5f9f-106">ATP 安全連結如何與 URLs 在電子郵件中運作</span><span class="sxs-lookup"><span data-stu-id="b5f9f-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="b5f9f-107">在高層次上，以下是[ATP 安全連結](atp-safe-links.md)保護如何針對電子郵件中的 URLs 運作（主控于 Office 365，而非內部部署）：</span><span class="sxs-lookup"><span data-stu-id="b5f9f-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="b5f9f-108">人員會收到電子郵件訊息，有些包含 URLs。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="b5f9f-109">所有電子郵件都會經歷 Exchange Online Protection，其中會套用到網際網路通訊協定（IP）和信封篩選器、簽名型惡意程式碼防護、反垃圾郵件和反惡意程式碼篩選器。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="b5f9f-110">電子郵件會送達人員的收件匣。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="b5f9f-111">使用者登入 Office 365，並進入電子郵件收件匣。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="b5f9f-112">使用者開啟電子郵件訊息，然後按一下電子郵件訊息中的 URL。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="b5f9f-113">ATP 安全連結功能會在開啟網站之前立即檢查 URL。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="b5f9f-114">URL 被識別為封鎖、惡意或安全。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="b5f9f-115">如果 URL 是在組織的 [[自訂封鎖 URLs] 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中所包含的網站上，則會開啟 [[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="b5f9f-116">如果 URL 指向已確定為惡意的網站，則會開啟 [警告][頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="b5f9f-117">若 URL 移至可下載的檔案，且您組織的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)已設定為掃描這類內容，便會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="b5f9f-118">如果此 URL 確定為安全，網站會開啟。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="b5f9f-119">ATP 安全連結如何與 Office 檔中的 URLs 搭配使用</span><span class="sxs-lookup"><span data-stu-id="b5f9f-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="b5f9f-120">在高層次上，以下是在 Office 365 ProPlus 或商務精品應用程式（Windows、Mac 上的目前版本 Word、Excel 及 PowerPoint 中的 Office iOS 應用程式、在 Windows 上的 Visio，OneNote 于瀏覽器中）的 URLs 的[ATP 安全連結](atp-safe-links.md)保護如何運作：</span><span class="sxs-lookup"><span data-stu-id="b5f9f-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="b5f9f-121">使用者已在其電腦、smartphone 或平板電腦上安裝 Office 365 ProPlus 或商務版。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-121">People have installed Office 365 ProPlus or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="b5f9f-122">（或者，他們會在其瀏覽器中使用 Office。）</span><span class="sxs-lookup"><span data-stu-id="b5f9f-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="b5f9f-123">使用者開啟 Word、Excel、PowerPoint、OneNote （在瀏覽器中）或 Visio （在桌面上），並使用公司或學校帳戶登入 Office 365 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="b5f9f-124">檔包含 URLs。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="b5f9f-125">當使用者按一下檔中的 URL 時，ATP 安全連結服務便會檢查此連結。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="b5f9f-126">如果 URL 是在組織的[自訂封鎖 URLs] 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中所包含的網站上，則會移至 [[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="b5f9f-127">如果 URL 指向已確定為惡意的網站，則會將使用者移至 [[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="b5f9f-128">若 URL 移至可下載的檔案，且已設定[ATP 安全連結原則](set-up-atp-safe-links-policies.md)來掃描這類下載，便會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="b5f9f-129">如果此 URL 被視為安全的，使用者會進入網站。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="b5f9f-130">如果 URL 檢查失敗，安全連結的保護將不會觸發。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="b5f9f-131">在桌面用戶端上，系統會先提醒使用者，然後再繼續進行網站。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="b5f9f-132">在每個會話開始時可能需要幾秒鐘，以確認使用者已啟用 Office 的 ATP 安全連結。</span><span class="sxs-lookup"><span data-stu-id="b5f9f-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
