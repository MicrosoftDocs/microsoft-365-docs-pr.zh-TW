---
title: Office 365 影片的常見問題
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: 在頻寬規劃、加密 & 服務利用內容傳遞網路 (Cdn) 的方式，尋找一些常見問題的答案。
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921567"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Office 365 影片的常見問題

Office 365 影片存放庫及流式處理服務可讓組織內的儲存及流式處理影片輕鬆。 [有關 Office 365 影片](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)的許多重要資訊，請這種網路常見問題的設計是針對頻寬規劃、加密，以及服務利用[內容傳遞網路](content-delivery-networks.md) (cdn) 的最常見問題進行解答。
  
如果您還沒有完全瞭解影片上載或播放的方式，請參閱這段影片：我們將影片放在一起，將 [影片檔上傳至 Office 365 影片時會發生什麼情況](https://www.youtube.com/watch?v=HXSZ0jYBKlM)。
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Office 365 的影片頻寬需求為何？

有許多支援的 [影片格式](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) 可上傳至 Office 365。 然後，會將每個影片檔編碼為具有多種不同影片品質的標準格式，以供播放。 Office 365 影片使用自我調整高位元速率資料流程，根據可用的網路頻寬和影片大小，選取最佳的影片播放品質。 若要這麼做，播放者最初會要求最低的播放品質。 然後，此服務會開始傳送2秒的影片片段到影片播放機。 然後，播放機便可根據每次傳遞每個片段的速度來要求較高或較低的播放品質。
  
自我調整高位元速率流式處理會在後臺執行，但播放頻率最少的中斷或緩衝。 在影片播放期間，影片播放機可讓 viewer 手動覆寫自動播放品質，以選取特定的影片播放品質。
  
以下是概述每個影片播放品質之網路需求的快速表格。 播放影片所需的每個人最小頻寬是802Kbps。
  
| 播放品質 | 網路速度 |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1.2 Mbps  <br/> |
|576p  <br/> |2.5 Mbps  <br/> |
|720p  <br/> |3.8 Mbps  <br/> |

 ([回到頁首](office-365-video-networking-faq.md)) 
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>內容傳遞網路如何 (Cdn) 協助影片播放？

如果相同地理位置內來自相同組織的多個人員已使用相同的影片 (s) 中，則 Cdn 會將這些影片的副本儲存在距離該地理區域更近的位置。 在儲存的影片上，或快取至最接近的位置時，每個人會從最接近的位置，而不是從遠處的位置流向影片。 Office 365 影片使用 Azure 媒體服務來管理 Azure Cdn 中快取的內容，以及多長的時間。 Azure 媒體服務可使用任何 [AZURE CDN 位置](/azure/cdn/cdn-pop-locations) ，將影片片段和資訊清單快取幾天。 如果您組織中的人員繼續觀賞快取的快取影片。 如果沒有人存取影片一天內，則會最後從快取中刪除影片。 下一次有人嘗試觀賞影片時，它會再次快取到最近的 CDN 位置。
  
在內容快取時，嘗試觀賞影片的每個人都會從影片中快取較近的位置，而在大多數情況下則不會有較低的躍點。 這會改善影片播放速度;不過，它不會變更網路需求以播放影片。
  
> [!NOTE]
> 在某些情況下（例如，我們已達到容量限制），在達到三天之後可能會移除影片。
  
 ([回到頁首](office-365-video-networking-faq.md)) 
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>我是否可以在本機快取影片以取得更快的播放功能？

是。 Office 365 不會防止您使用本機 CDN 或快取 proxy 將影片或其他 Office 365 內容帶入您的本機網路，以加快存取速度。 有幾種方式可以在您的網路上實施本機快取解決方案，最常用的方法是使用可在本機快取內容的 proxy 解決方案。 當 proxy 或私人 CDN 快取了影片片段和資訊清單之後，對透過 proxy 或私人 CDN 路由傳送的檔案，以後的要求會從本機快取中取出，而不是從網際網路位置提取。 在規劃像這樣的解決方案時，請考慮網路頻寬、容量和影片播放併發性。
  
 ([回到頁首](office-365-video-networking-faq.md)) 
  
## <a name="how-videos-are-encrypted-and-secured"></a>如何加密及保護影片的方式？

Office 365 影片知道保護資料安全和私人的重要程度。 [Microsoft 信任中心](https://products.office.com/business/office-365-trust-center-welcome) 描述我們對內容隱私權和安全性的承諾。 透過影片播放，速度對於良好的經驗很重要;不過，我們並未以 exchange 為速度降低您的安全性或隱私權。 以下是我們如何適應速度、安全性和隱私權。
  
當您或貴組織中的人員上傳新影片時，該影片會 transcoded、加密 AES-128 加密，並儲存在 Azure Media Services 中。 這表示影片會在傳輸和靜止時加密。
  
當您組織中的某人嘗試觀賞新影片時，請遵循下列步驟：
  
1. 如果他們具有查看影片的許可權，請詢問 SharePoint 線上。

2. 線上 SharePoint 會使用檔案許可權來判斷人員是否可以收看影片。

3. 如果允許，SharePoint 線上從 Azure 檢索權杖，以提供給影片播放機。

4. 然後，影片播放機會使用權杖從 Azure 要求解密金鑰。

5. 使用「解密金鑰」時，影片播放機便可以對流進行播放。

![O365 影片播放](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
 ([回到頁首](office-365-video-networking-faq.md)) 
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>播放 Office 365 影片的需求為何？

Office 365 影片支援的作業系統和網頁瀏覽器與 [office 365 系統需求](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45)的 SharePoint 線上需求相同。 根據您所擁有的作業系統和網頁瀏覽器設定，會決定影片播放機的特定需求。 以下是有關 [影片播放需求](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)的詳細資訊。
  
 ([回到頁首](office-365-video-networking-faq.md)) 
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>我無法讓 Office 365 影片正常運作，我應該從何處開始？

疑難排解 Office 365 影片的連線問題包括疑難排解您的網路、您的 ISP (s) ，以及您設定的 Office 365。 開始的第一個位置是服務健康情況儀表板。 這會告訴您 Office 365 影片有問題。 如果一切看起來很不錯，以下是一些額外的資源可協助您。
  
- 請確定您可以連線到 [Office 365 影片所需的網路端點](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)。

- 使用 [Office 365 網路疑難排解指南](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)，檢查您的網路連線能力。

- 請參閱我們 [在慢速網路上使用 Office 365 的最佳作法](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)。

- [尋找有關 Office 365 影片](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)設定的說明。

 ([回到頁首](office-365-video-networking-faq.md)) 
  
## <a name="office-365-video-resources"></a>Office 365 影片資源

以下是協助您成功部署和使用 Office 365 影片的其他一些資源：
  
[尋找 Office 365 影片設定的說明](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[符合 Office 365 影片](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[在 Office 365 影片中建立及管理通道](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[管理 Office 365 影片入口網站](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[在 Office 365 影片中運作的影片格式](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
 ([回到頁首](office-365-video-networking-faq.md)) 
  
您可以使用下列短連結返回這裡：[https://aka.ms/video365networkfaq]()