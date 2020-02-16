---
title: 開始使用 DLP 原則建議
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: 此深入了解導向建議可協助保護敏感內容安全性，當已儲存，並在 Office 365 中共用的通知您何時中的有可能間隔貴組織 DLP 原則涵蓋範圍。 您會看到這項建議在首頁上的安全性&amp;合規性中心，如果您的文件包含任何的前五個最常見的敏感資訊類型，但不會受到 DLP 原則。
ms.openlocfilehash: 7fb99942a2288a2545123d44ebdfde89b449edc3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073199"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>開始使用 DLP 原則建議

此深入了解導向建議可協助保護敏感內容安全性，當已儲存，並在 Office 365 中共用的通知您何時中的有可能間隔貴組織 DLP 原則涵蓋範圍。 您會看到這項建議在**首頁**上的安全性&amp;合規性中心，如果您的文件包含任何的前五個最常見的敏感資訊類型，但不受保護的資料外洩防護 (DLP) 原則。 
  
您可以使用此 widget 快速地建立自訂的 DLP 原則中按一下 [或兩個，並建立此 DLP 原則之後，它可完全自訂。 請注意，如果您沒有看到一開始，建議嘗試按一下 [ **+ 詳細**底部的 [**為您的建議**] 區段中。 
  
![名為不受保護的敏感資訊的小工具](../media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>建立建議的 DLP 原則

當] 小工具顯示您保護敏感資訊時，請選擇 [快速地建立 DLP 原則底部**開始**。 
  
若要協助保護敏感資訊，此 DLP 原則：
  
- 偵測與組織外部人員共用 Exchange、 SharePoint 和 OneDrive 中包含下列其中一個未受保護的敏感資訊類型的內容。
    
- 讓您可以追蹤之類的使用者與組織外部人員共用內容及他們沒有的時，會產生詳細的活動報告。 您可以使用[DLP 報告](view-the-dlp-reports.md)和[稽核記錄檔資料](search-the-audit-log-in-security-and-compliance.md)(其中**活動** = **DLP**) 若要查看此資訊。
    
您也可以選擇讓 DLP 原則：
  
- 您傳送附隨報告電子郵件時的使用者與組織外部人員共用大量此敏感資訊。
    
- 將其他使用者新增至電子郵件附隨報告。
    
- 顯示原則提示和電子郵件通知傳送給使用者，當使用者嘗試與組織外部人員共用機密資訊。 如需有關這些選項的詳細資訊，請參閱[傳送電子郵件通知並顯示原則提示的 DLP 原則](use-notifications-and-policy-tips.md)。
    
如果您想要稍後變更這些選項，您可以在建立之後編輯 DLP 原則。 例如，您可以讓原則成為更嚴格由即使封鎖從共用內容包含敏感資訊的人員在第一時間-請參閱下一節。
  
![[] 小工具設定名為不受保護的敏感資訊](../media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>編輯建議的 DLP 原則

您使用 [] 小工具來建立 DLP 原則之後，原則會出現在 [**資料外洩防護**] 下的安全性**原則**] 頁面上&amp;合規性中心。 
  
根據預設，原則名為**共用敏感資訊的系統建議的原則**。 此原則可完全自訂，任何，從頭開始建立您自己的 DLP 原則相同。 例如，如果您決定不使用 [] 小工具時，開啟附隨報告 」 和 「 原則提示，您可以一律編輯原則並隨時開啟這些選項。
  
![建議原則共用敏感資訊的系統](../media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>當] 小工具會以及不會出現

名為**不受保護的敏感資訊**的 widget 會出現在 [**為您的建議**] 區段中的 [**首頁**] 頁面上的安全性&amp;合規性中心。 
  
此 widget 出現僅當：
  
- 包含任何的五種最常見的敏感資訊類型的新文件 SharePoint 或 OneDrive 中偵測到過去 30 天。
    
- 現有的 DLP 原則已不受這些敏感資訊。
    
不同經常會掃描您的資料的 DLP 原則，此建議掃描的 DLP 原則涵蓋範圍間斷的傷害大約每隔 48 小時，讓上傳新內容後，它可能需要最多兩天的顯示的建議。
  
最後，您使用 [] 小工具來建立建議的 DLP 原則之後，從 [**首頁**] 頁面會消失] 小工具。 
  

