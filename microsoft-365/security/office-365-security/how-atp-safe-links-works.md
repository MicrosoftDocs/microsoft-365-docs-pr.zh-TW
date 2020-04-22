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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 「安全連結」可在 Office 文件和電子郵件訊息中提供點擊超連結時即進行驗證的功能。 請閱讀本文以瞭解 ATP 安全連結的運作方式。
ms.openlocfilehash: b77ab718afdc4f68d8120e11fa5d1a321b66f32e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638007"
---
# <a name="how-atp-safe-links-works"></a>ATP 安全連結的運作方式
> [!IMPORTANT] 
> 若要讓 Office 365 ATP 安全連結正確運作，所有服務必須在相同版本。
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>ATP 安全連結如何與 URLs 在電子郵件中運作

在高層次上，以下是[ATP 安全連結](atp-safe-links.md)保護如何針對電子郵件中的 URLs 運作（主控于 Office 365，而非內部部署）：
  
1. 人員會收到電子郵件訊息，有些包含 URLs。
    
2. 所有電子郵件都會經歷 Exchange Online Protection，其中會套用到網際網路通訊協定（IP）和信封篩選器、簽名型惡意程式碼防護、反垃圾郵件和反惡意程式碼篩選器。 
    
3. 電子郵件會送達人員的收件匣。
    
4. 使用者登入 Office 365，並進入電子郵件收件匣。
    
5. 使用者開啟電子郵件訊息，然後按一下電子郵件訊息中的 URL。
    
6. ATP 安全連結功能會在開啟網站之前立即檢查 URL。 URL 被識別為封鎖、惡意或安全。
        
   - 如果 URL 是在組織的 [[自訂封鎖 URLs] 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中所包含的網站上，則會開啟 [[警告] 頁面](atp-safe-links-warning-pages.md)。 
    
   - 如果 URL 指向已確定為惡意的網站，則會開啟 [警告][頁面](atp-safe-links-warning-pages.md)。 
    
   - 若 URL 移至可下載的檔案，且您組織的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)已設定為掃描這類內容，便會檢查可下載的檔案。 
    
   - 如果此 URL 確定為安全，網站會開啟。
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>ATP 安全連結如何與 Office 檔中的 URLs 搭配使用 

在較高的層次上，以下是針對企業或商務版應用程式365中的 URLs 的[ATP 安全連結](atp-safe-links.md)保護的運作方式（Windows、Mac 或瀏覽器中的 Word、Excel 及 PowerPoint 的目前版本、Office 應用 iOS 程式、windows 上的 Visio，OneNote 在瀏覽器中）：
  
1. 使用者已在其電腦、smartphone 或平板電腦上安裝 Microsoft 365 應用程式的企業版或商務版。 （或者，他們會在其瀏覽器中使用 Office。）
    
2. 使用者開啟 Word、Excel、PowerPoint、OneNote （在瀏覽器中）或 Visio （在桌面上），並使用公司或學校帳戶登入 Office 365 Enterprise。 檔包含 URLs。
    
3. 當使用者按一下檔中的 URL 時，ATP 安全連結服務便會檢查此連結。
    
   - 如果 URL 是在組織的[自訂封鎖 URLs] 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中所包含的網站上，則會移至 [[警告] 頁面](atp-safe-links-warning-pages.md)。
    
   - 如果 URL 指向已確定為惡意的網站，則會將使用者移至 [[警告] 頁面](atp-safe-links-warning-pages.md)。
    
   - 若 URL 移至可下載的檔案，且已設定[ATP 安全連結原則](set-up-atp-safe-links-policies.md)來掃描這類下載，便會檢查可下載的檔案。 
    
   - 如果此 URL 被視為安全的，使用者會進入網站。
      
   - 如果 URL 檢查失敗，安全連結的保護將不會觸發。 在桌面用戶端上，系統會先提醒使用者，然後再繼續進行網站。
      
> [!NOTE]
> 在每個會話開始時可能需要幾秒鐘，以確認使用者已啟用 Office 的 ATP 安全連結。 
      
