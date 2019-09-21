---
title: Office 365 ATP 安全連結的運作方式
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 安全連結功能提供 Office 文件和電子郵件訊息中的超連結的時間按一下 [的驗證。 閱讀本篇文章以了解 ATP 安全連結的運作方式。
ms.openlocfilehash: 45053b51bb5a91698d90f61567aa7f5577518587
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076848"
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
    
    - 如果 URL 包含在[自訂 「 不要重寫 」 Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，網站會隨即開啟。 
    
    - 組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。 
    
    - 已判定為惡意的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。 
    
    - 如果 URL 會前往可下載的檔案，且貴組織的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類內容，會檢查可下載的檔案。 
    
    - 如果 URL 會決定為了安全起見，網站會隨即開啟。
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>ATP 安全連結的運作方式與 Url 中的 Office 文件

在高的層級，以下是[ATP 安全連結](atp-safe-links.md)保護中的運作方式 Url 的 Office 365 專業增強版的應用程式 (目前版本的 Word、 Excel 及 PowerPoint Windows 或 Mac、 iOS 或 Android 裝置，windows，在瀏覽器] 的 OneNote Visio 的 Office 應用程式和Office 的瀏覽器中):
  
1. 人員在其電腦、 智慧型手機或平板電腦上安裝 Office 365 專業增強版。 （或是在其瀏覽器中使用 Office]）。
    
2. 使用者開啟 Word、 Excel、 PowerPoint 或 Visio，並為 Office 365 企業版使用其公司或學校帳戶登入。 文件中包含的 Url。
    
3. 當使用者在 [文件中的 URL 時，連結會檢查 ATP 安全連結服務。
    
      - 如果 URL 是包含在[自訂 「 不要重寫 」 Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，該使用者不會採取至網站。 
    
      - URL 是包含在組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)的網站，如果使用者不會採取至[警告頁面](atp-safe-links-warning-pages.md)。
    
      - 如果已決定為惡意的網站 URL，使用者會採取至[警告頁面](atp-safe-links-warning-pages.md)。
    
      - 如果 URL 會前往可下載的檔案，且[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類的下載項目，會檢查可下載的檔案。 
    
      - URL 會被視為安全，如果使用者不會採取至網站。

