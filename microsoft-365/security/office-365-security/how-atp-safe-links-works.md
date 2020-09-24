---
title: ATP 安全連結的運作方式
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
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 「安全連結」可在 Office 文件和電子郵件訊息中提供點擊超連結時即進行驗證的功能。 請閱讀本文以瞭解 ATP 安全連結的運作方式。
ms.openlocfilehash: e19d3a1f93d11cd9873e6b5fad9952b018e0a481
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245878"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="37756-104">ATP 安全連結的運作方式</span><span class="sxs-lookup"><span data-stu-id="37756-104">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> <span data-ttu-id="37756-105">若要讓 Office 365 ATP 安全連結正確運作，所有服務必須在相同版本。</span><span class="sxs-lookup"><span data-stu-id="37756-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="37756-106">ATP 安全連結如何與 URLs 在電子郵件中運作</span><span class="sxs-lookup"><span data-stu-id="37756-106">How ATP Safe Links works with URLs in email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 <span data-ttu-id="37756-107">在電子郵件中使用 URLs</span><span class="sxs-lookup"><span data-stu-id="37756-107">with URLs in email</span></span>

<span data-ttu-id="37756-108">在較高的層次上，以下是在 Office 365 所主控的電子郵件 (中的 [ATP 安全連結](atp-safe-links.md) 保護的運作方式 URLs，而非內部部署) ：</span><span class="sxs-lookup"><span data-stu-id="37756-108">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="37756-109">人員會收到電子郵件訊息，有些包含 URLs。</span><span class="sxs-lookup"><span data-stu-id="37756-109">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="37756-110">所有電子郵件都會經歷 Exchange Online Protection，其中網際網路通訊協定 (IP) 和信封篩選器、簽章型惡意程式碼防護、反垃圾郵件和反惡意程式碼篩選器。</span><span class="sxs-lookup"><span data-stu-id="37756-110">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="37756-111">電子郵件會送達人員的收件匣。</span><span class="sxs-lookup"><span data-stu-id="37756-111">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="37756-112">使用者登入 Office 365，並進入電子郵件收件匣。</span><span class="sxs-lookup"><span data-stu-id="37756-112">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="37756-113">使用者開啟電子郵件訊息，然後按一下電子郵件訊息中的 URL。</span><span class="sxs-lookup"><span data-stu-id="37756-113">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="37756-114">ATP 安全連結功能會在開啟網站之前立即檢查 URL。</span><span class="sxs-lookup"><span data-stu-id="37756-114">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="37756-115">URL 被識別為封鎖、惡意或安全。</span><span class="sxs-lookup"><span data-stu-id="37756-115">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="37756-116">如果 URL 是在組織的 [ [自訂封鎖 URLs] 清單](set-up-a-custom-blocked-urls-list-atp.md)中所包含的網站上，則會開啟 [ [警告] 頁面](atp-safe-links-warning-pages.md) 。</span><span class="sxs-lookup"><span data-stu-id="37756-116">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="37756-117">如果 URL 指向已確定為惡意的網站，則會開啟 [警告] [頁面](atp-safe-links-warning-pages.md) 。</span><span class="sxs-lookup"><span data-stu-id="37756-117">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="37756-118">若 URL 移至可下載的檔案，且您組織的 [ATP 安全連結原則](set-up-atp-safe-links-policies.md) 已設定為掃描這類內容，便會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="37756-118">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="37756-119">如果此 URL 確定為安全，網站會開啟。</span><span class="sxs-lookup"><span data-stu-id="37756-119">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="37756-120">ATP 安全連結如何與 Office 檔中的 URLs 搭配使用</span><span class="sxs-lookup"><span data-stu-id="37756-120">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="37756-121">在較高的層次上，以下是 Microsoft 365 應用程式中的 [ATP 安全連結](atp-safe-links.md) 保護運作方式的 URLs，適用于適用于企業或商務高級應用程式的 Microsoft 應用程式中，Windows、Mac 或瀏覽器中的 Word、Excel 及 PowerPoint、Office 應用 iOS 程式、windows 上的 Office 應用程式 OneNote 中的 (：</span><span class="sxs-lookup"><span data-stu-id="37756-121">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="37756-122">使用者已在其電腦、smartphone 或平板電腦上安裝 Microsoft 365 應用程式的企業版或商務版。</span><span class="sxs-lookup"><span data-stu-id="37756-122">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="37756-123"> (或在其瀏覽器中使用 Office。 ) </span><span class="sxs-lookup"><span data-stu-id="37756-123">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="37756-124">使用者在瀏覽器) 中開啟 Word、Excel、PowerPoint、OneNote (，或在桌面 (上開啟 Visio) ，然後使用其工作或學校帳戶登入 Office 365 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="37756-124">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="37756-125">檔包含 URLs。</span><span class="sxs-lookup"><span data-stu-id="37756-125">The document contains URLs.</span></span>
    
3. <span data-ttu-id="37756-126">當使用者按一下檔中的 URL 時，ATP 安全連結服務便會檢查此連結。</span><span class="sxs-lookup"><span data-stu-id="37756-126">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="37756-127">如果 URL 是在組織的 [自訂封鎖 URLs] 清單](set-up-a-custom-blocked-urls-list-atp.md)中所包含的網站上，則會移至 [ [警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="37756-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="37756-128">如果 URL 指向已確定為惡意的網站，則會將使用者移至 [ [警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="37756-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="37756-129">若 URL 移至可下載的檔案，且已設定 [ATP 安全連結原則](set-up-atp-safe-links-policies.md) 來掃描這類下載，便會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="37756-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="37756-130">如果此 URL 被視為安全的，使用者會進入網站。</span><span class="sxs-lookup"><span data-stu-id="37756-130">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="37756-131">如果 URL 檢查失敗，安全連結的保護將不會觸發。</span><span class="sxs-lookup"><span data-stu-id="37756-131">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="37756-132">在桌面用戶端上，系統會先提醒使用者，然後再繼續進行網站。</span><span class="sxs-lookup"><span data-stu-id="37756-132">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="37756-133">在每個會話開始時可能需要幾秒鐘，以確認使用者已啟用 Office 的 ATP 安全連結。</span><span class="sxs-lookup"><span data-stu-id="37756-133">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
