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
ms.openlocfilehash: 7b1c1368b274bbbb6dc7a5b760de4968575962fa
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599200"
---
# <a name="how-office-365-atp-safe-links-works"></a>Office 365 ATP 安全連結的運作方式
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>ATP 安全連結的運作方式與 Url 以電子郵件

在高的層級，以下是[ATP 安全連結](atp-safe-links.md)保護中的運作方式的 Url （裝載於 Office 365，不在內部） 的電子郵件：
  
1. 人員會收到電子郵件訊息，其中有些包含的 Url。
    
2. 所有電子郵件通過 Exchange Online Protection，其中網際網路通訊協定 (IP) 及信封篩選，簽章型惡意程式碼防護，反垃圾郵件和反惡意軟體篩選器。 
    
3. 電子郵件會送達人民收件匣。
    
4. 使用者登入 Office 365，並移至其電子郵件收件匣。
    
5. 使用者開啟電子郵件訊息，並按一下電子郵件訊息中的 URL。
    
6. ATP 安全連結功能立即檢查才能開啟之網站的 URL。 URL 被識別為惡意，/ 安全封鎖。
        
   - 組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。 
    
   - 已判定為惡意的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。 
    
   - 如果 URL 會前往可下載的檔案，且貴組織的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類內容，會檢查可下載的檔案。 
    
   - 如果 URL 會決定為了安全起見，網站會隨即開啟。
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>ATP 安全連結的運作方式與 Url 中的 Office 文件 

在高層級，此處的[ATP 安全連結](atp-safe-links.md)保護中的運作方式 Url 的 Office 365 專業增強版或商務進階版的應用程式 （目前版本的 Word、 Excel 及 PowerPoint 在 Windows、 Mac，或在瀏覽器、 Office 應用程式，在 iOS 或 Android 裝置，Visio 在 Windows 上的、 在瀏覽器中的 OneNote）：
  
1. 人員擁有其電腦、 智慧型手機或平板電腦上安裝 Office 365 專業增強版或商務進階版。 （或是在其瀏覽器中使用 Office]）。
    
2. 使用者 （在桌面上），開啟 Word、 Excel、 PowerPoint、 OneNote （在瀏覽器中） 或 Visio，並為 Office 365 企業版使用其公司或學校帳戶登入。 文件中包含的 Url。
    
3. 當使用者在 [文件中的 URL 時，連結會檢查 ATP 安全連結服務。
    
   - URL 是包含在組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)的網站，如果使用者不會採取至[警告頁面](atp-safe-links-warning-pages.md)。
    
   - 如果已決定為惡意的網站 URL，使用者會採取至[警告頁面](atp-safe-links-warning-pages.md)。
    
   - 如果 URL 會前往可下載的檔案，且[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類的下載項目，會檢查可下載的檔案。 
    
   - URL 會被視為安全，如果使用者不會採取至網站。
      
   - 如果 URL 檢查失敗，將不會觸發安全連結保護。 在桌面用戶端中，將會繼續透過站台之前警告使用者。
      
> [!NOTE]
> 可能需要幾秒的每個工作階段開頭，若要確認使用者已啟用的 Office 的 ATP 安全連結。 
      
