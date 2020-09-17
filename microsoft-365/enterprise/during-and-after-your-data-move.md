---
title: 資料移動期間和之後
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: 資料移動是指 Microsoft 將租使用者的服務和相關資料移至新的資料中心地理位置時，會發生後端作業。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: acd2601d32617c56019ca8b4bf8688ce40f5d76a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950269"
---
# <a name="during-and-after-your-data-move"></a>資料移動期間和之後

資料移動是後端作業，對使用者的影響最小。 Microsoft 將租使用者的每一個服務和相關資料移至新的資料中心地理位置時，不需要執行任何動作。 資料傳輸和驗證會在背景中預先進行，並將對使用者的影響降至最低。
  
> [!NOTE]
> 每個服務的移動發生在不同的時間。 因此，您會在不同的時間看到每個服務所述的簡化功能。 
  
觀賞 Microsoft 365 訊息中心，以在每個 Exchange Online 移動時進行確認（SharePoint 線上、小組和商務用 Skype 皆已完成）。 如下表所示，在註冊期間結束後，最多可能需要24個月才能完成所有要求的資料移動，以供特定地理位置的所有客戶使用。 如果您在移動之後看到您的承租人發生任何問題，請聯繫我們 [技術支援](https://go.microsoft.com/fwlink/p/?LinkID=522459) 以取得協助。 
  

|**在中使用註冊國家/地區的客戶**|**所有移動完成者**|
|:-----|:-----|
|澳大利亞，紐西蘭，斐濟  <br/> |2022年7月1日  <br/> |
|日本  <br/> |2022年7月1日  <br/> |
|印度  <br/> |2022年7月1日  <br/> |
|加拿大  <br/> |2022年7月1日  <br/> |
|南韓  <br/> |2022年7月1日  <br/> |
|英國  <br/> |2022年7月1日  <br/> |
|法國  <br/> |2022年7月1日  <br/> |
|阿拉伯聯合大公國  <br/> |2022年7月1日  <br/> |
|南非  <br/> |2022年7月1日  <br/> |
|瑞士，列支敦斯登  <br/> |2022年7月1日  <br/> |
|挪威  <br/> |2022年11月1日  <br/> |
|德國  <br/> |計畫  <br/> |

## <a name="exchange-online"></a>Exchange Online

由於將每一位使用者移至單一租使用者的新資料中心地理位置，有些使用者仍會在移動期間保留在舊的資料中心地理位置，而其他使用者則是在新的資料中心地理位置。 這表示一些涉及存取多個信箱的功能可能無法在移動程式期間內完全運作，這可能是過去一周。 這些功能將在下列各節中說明。
  
### <a name="open-shared-folder-in-outlook-web-access"></a>在 Outlook Web Access 中開啟「共用資料夾」

部分使用者使用「共用資料夾」功能，從其他信箱 (開啟共用郵件資料夾，該使用者具有在 Outlook Web Access 中) 讀取或寫入權限。 下表說明在信箱移動期間，共用資料夾的存取如何運作。 請注意，在移動期間，具有共用信箱的完整許可權的使用者可以使用 Outlook Web Access 開啟信箱。 
  
|**設定**|**描述**|
|:-----|:-----|
|使用者擁有其他信箱的信箱資料夾許可權  <br/> |可能限制。  <br/> 如果使用者 a 和信箱 B 在租使用者移動期間不在相同的地理位置，使用者 A 只有信箱 B 中特定資料夾的許可權，才能在 Outlook Web Access 中開啟信箱 B 的資料夾。  <br/> 若要新增共用資料夾，請以滑鼠右鍵按一下左導覽面板中的使用者名稱，然後選取 [ **新增共用資料夾**]。  <br/> |
|具有其他信箱之完整信箱許可權的使用者  <br/> |完全支援。  <br/> 如果使用者 A 對信箱 B 具有「完整存取」許可權，則使用者 A 可以在 Outlook Web Access 的左導覽窗格中按一下共用資料夾，以開啟顯示信箱 B 的視窗。 使用者可以在移動期間使用 Outlook Web Access 開啟共用信箱，而不會有任何不良影響。 限制僅適用于信箱中的資料夾層級共用。           |
  
## <a name="sharepoint-online"></a>SharePoint Online

移動 SharePoint 線上時，也會移動下列服務的資料：
  
- 商務用 OneDrive
    
- Project Online
    
- Microsoft 365 的專案
    
- Microsoft 365 影片服務
    
- 瀏覽器中的 Office
    
- Microsoft 365 Apps 企業版
    
- Visio Pro for Microsoft 365
    
完成移動 SharePoint 線上資料之後，您可能會看到下列部分效果。
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 影片服務

- 影片的資料移動所用的時間會比在 SharePoint Online 中，移動其他內容的時間長。
    
- SharePoint 線上內容移動之後，將會有一個時間範圍無法播放影片。
    
- 我們正在從舊版資料中心移除交易編碼複本，並在新的資料中心內再將其轉換。
    
### <a name="search"></a>搜尋

在移動 SharePoint 線上資料的過程中，我們會將您的搜尋索引和搜尋設定遷移至新的位置。 在 **完成** SharePoint 線上資料的移動之前，我們會繼續為您的使用者提供原始位置的索引。 在新位置時，搜尋會在完成移動 SharePoint 線上資料之後，自動開始編目您的內容。 從這個點開始，我們會從已遷移的索引為您的使用者提供服務。 在進行編目挑選之前，遷移之後所發生的內容變更將不會包含在遷移後的索引中。 大部分的客戶不會注意到，當我們已完成移動 SharePoint 線上資料後，結果會變得不夠全新，但是某些客戶可能會在前24-48 小時內經歷低的新鮮度。 
  
下列搜尋功能會受到影響：
  
- 搜尋結果和搜尋網頁元件：結果不包含遷移之後所發生的變更，直到編目進行挑選為止。 
    
- Delve： Delve 不包含遷移之後所發生的變更，直到編目進行挑選為止。
    
- 網站的普及狀況和搜尋報告：在新位置的 Excel 報表計數中，只會包含在完成移動 SharePoint 線上資料之後所執行的流量報告中的已遷移計數和計數。 來自過渡期間的任何計數都會遺失，且無法復原。 此期間通常是幾天。 有些客戶可能會經歷較短或更長的遺失。
    
- 影片入口網站：查看影片入口網站的計數和統計資料取決於 Excel 報表的統計資料，因此，影片的查看計數和統計資料會隨著 Excel 報表的時間週期而遺失。
    
- eDiscovery：在編目挑選變更之前，不會顯示在遷移期間變更的專案。
    
- 資料遺失防護 (DLP) ：原則不會對變更的專案執行，直到編目拾取變更為止。

## <a name="microsoft-teams"></a>Microsoft Teams

除了 Exchange Online、SharePoint Online 和商務 OneDrive，Microsoft 也會將小組資料移轉至本機資料中心。

- 小組會聊天訊息，包括私人郵件和通道訊息。
- 在聊天中使用的小組圖像。

小組檔案會儲存在 SharePoint 線上中，小組聊天檔會儲存在商務 OneDrive 中。 語音信箱、行事曆、聊天記錄和連絡人會儲存在 Exchange Online 中。 在許多情況下，使用者已在本機資料中心地理位置中使用 Exchange Online、SharePoint 線上和商務 OneDrive，而且也是適用于合格客戶國家/地區的 Microsoft 365 遷移計畫的一部分。

## <a name="skype-for-business"></a>商務用 Skype

商務用 Skype 移動可用於澳大利亞、日本、印度、加拿大、英國和韓國。

在剪下時，所有使用者都將從商務用 Skype 用戶端軟體登出。 自動登入會在兩分鐘內重新連線使用者。
  
|**在整個移動期間可運作的功能**|**移動部分期間可能會限制的功能**|
|:-----|:-----|
| 立即訊息和語音通話  <br/>  使用者可以新增連絡人、新增連絡人群組、新增會議、設定其位置，以及變更「今天所發生的情形」。  <br/>  音訊會議提供者 (ACP) 設定會複製到目標資料中心地理位置。 如果目標資料中心存在 ACP 提供者，則會運作。 否則，它將不會。  <br/> | 承租人 Admin TRPS (承租人 Remote PowerShell) 將無法供系統管理員建立會話。  <br/>  租使用者系統管理員 LAC 將無法供系統管理員登入和變更使用者設定。  <br/> |
   
|**移動後**|
|:-----|
| 會議資料 (上傳的簡報等 ) 不會移動，也不需要重新上傳。  <br/>  舊版的 Lync 用戶端（例如 Lync 2010 用戶端和 Lync for Mac 2011 用戶端）會被稱為快取 DNS 資訊至導致登入問題的服務。 如果使用者不在最新的商務用 Skype Windows 用戶端，則可能需要清除 DNS 快取。 請參閱 [Office 365 中的商務用 Skype ONLINE DNS 設定問題疑難排解](https://docs.microsoft.com/skypeforbusiness/troubleshoot/online-configuration/dns-configuration-issue)。 Lync for Mac 用戶端使用者應遵循 [這些指示](https://support.microsoft.com/kb/2629861)。  <br/> |
   
### <a name="skype-for-business-moves-that-involve-a-third-party-audio-conferencing-provider"></a>涉及協力廠商音訊會議提供者的商務用 Skype 移動
適用于商務用 Skype 的協力廠商音訊會議提供者附加元件服務，不適用於位於新地理位置特定資料中心的使用者。  使用協力廠商音訊會議提供者服務的現有客戶不應要求移至新的地理特定資料中心。  新的特定地理位置資料中心部署的新客戶必須要求移至地區資料中心，才能使用協力廠商音訊會議提供者。
  
## <a name="related-topics"></a>相關主題 
 
[如何要求資料移動](request-your-data-move.md)
    
[資料移動一般常見問題集](data-move-faq.md)
  
[Microsoft Dynamics CRM Online 的新 datacenter geos](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[依地區的 Azure 服務](https://azure.microsoft.com/regions/)
