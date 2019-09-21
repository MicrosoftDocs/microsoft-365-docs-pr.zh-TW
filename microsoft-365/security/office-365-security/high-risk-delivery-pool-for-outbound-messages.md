---
title: 高風險傳遞集區的外寄郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 當客戶的電子郵件系統已經受到惡意程式碼或惡意垃圾郵件攻擊，且它傳送到託管的篩選服務的輸出垃圾郵件時，這可能導致各別列出協力廠商區塊上的 Office 365 資料中心伺服器的 IP 位址列出。
ms.openlocfilehash: 5b9241dead5b40e9f216ecd3023d6f8b86fb0205
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076851"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>高風險傳遞集區的外寄郵件

當客戶的電子郵件系統已經受到惡意程式碼或惡意垃圾郵件攻擊，且它傳送到託管的篩選服務的輸出垃圾郵件時，這可能導致各別列出協力廠商區塊上的 Office 365 資料中心伺服器的 IP 位址列出。 執行動作的目的伺服器不使用託管的篩選服務，但不要使用這些封鎖清單，拒絕從任何已新增至這些清單託管篩選 IP 位址傳送的所有電子郵件。 為避免這種情況，超出垃圾郵件閾值的所有外寄郵件傳送到高風險傳遞集區。 此次要的外寄電子郵件集區只能用來傳送郵件，可能的低品質。 這有助於防止其餘的網路傳送更有可能導致傳送的 IP 位址遭到封鎖的郵件。
  
使用專用的高風險傳遞集區可協助確保標準輸出集區僅傳送已知的高品質的郵件。 使用此次要 IP 集區可協助降低新增至封鎖清單的一般的輸出 IP 集區的機率。 要放在封鎖清單上的高風險傳遞集區的可能性會維持風險。 這是預設的設計。
  
在傳送網域出具有任何地址記錄 （A 記錄），可讓您網域的 IP 位址和任何 MX 記錄，可將郵件導向至 DNS 中應收到特別網域之郵件伺服器，郵件會一律透過路由傳送無論其垃圾郵件處理高風險傳遞集區。
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>了解傳遞狀態通知 (DSN) 郵件

讓輸出的高風險傳遞集區可管理所有 「 被退回 」 或 「 失敗 」 (DSN) 郵件的傳遞。
  
DSN 郵件激增的可能原因包括下列：
  
- 詐騙活動影響到使用服務的其中一位客戶
    
- 目錄搜集攻擊
    
- 垃圾郵件攻擊
    
- 惡意 SMTP 伺服器
    
所有這些問題都可能導致服務處理的 DSN 郵件數量突然增多。 許多時候，這些 DSN 郵件看起來會對其他電子郵件伺服器和服務的垃圾郵件。
  
## <a name="for-more-information"></a>如需詳細資訊

[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)
  
[反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)
  

