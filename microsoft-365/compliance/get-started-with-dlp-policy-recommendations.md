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
description: 此深入瞭解導向的建議可協助您的組織在您的 DLP 原則覆蓋範圍內有可能的缺口時，通知您，以保護機密內容365的安全。 您會在安全性&amp;與合規性中心的首頁上看到此建議功能（如果您的檔包含任何最常見類型的敏感資訊，但不會受到 DLP 原則保護）。
ms.openlocfilehash: 73c45c477942533d5668c225144950a0fde4279b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632464"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>開始使用 DLP 原則建議

此深入瞭解導向的建議可協助您的組織在您的 DLP 原則覆蓋範圍內有可能的缺口時，通知您，以保護機密內容365的安全。 您將會在安全性&amp;與合規性中心的首頁上看到此建議，如果您的檔包含任何最常見類型的敏感資訊，但未受到資料遺失防護（DLP）原則的保護。 **Home** 
  
您可以使用此小工具，只要按一下一次或兩次，即可快速建立自訂的 DLP 原則，而且在您建立此 DLP 原則之後，即可完全自訂。 請注意，如果您第一次沒有看到建議，請嘗試按一下 [**建議**] 區段底部的 [**其他**]。 
  
![稱為未受保護的敏感資訊的小工具](../media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>建立建議的 DLP 原則

當小工具顯示您未受保護的機密資訊時，請選擇底部的 [**開始**使用] 快速建立 DLP 原則。 
  
為了協助保護機密資訊，此 DLP 原則包括：
  
- 在 Exchange、SharePoint 及包含其中一種未受保護的敏感資訊類型的 OneDrive 中，偵測到組織外部人員共用的內容。
    
- 產生詳細的活動報告，使您可以追蹤與組織外部的人員共用內容的人員，以及他們的情況。 您可以使用[DLP 報告](view-the-dlp-reports.md)和[審核記錄資料](search-the-audit-log-in-security-and-compliance.md)（其中**活動** = **DLP**）來查看此資訊。
    
您也可以選擇讓 DLP 原則執行下列作業：
  
- 當使用者與組織外部的人員共用大量的敏感資訊時，向您傳送附隨報告電子郵件。
    
- 將其他使用者新增至電子郵件附隨報告。
    
- 當使用者嘗試與組織外部的人員共用此機密資訊時，顯示原則提示並傳送電子郵件通知給使用者。 如需這些選項的詳細資訊，請參閱[傳送電子郵件通知及顯示 DLP 原則的原則秘訣](use-notifications-and-policy-tips.md)。
    
如果您想要稍後變更這些選項，您可以在建立 DLP 原則之後進行編輯。 例如，您可以讓原則更具限制性，甚至只封鎖人員在第一個位置中包含敏感資訊的共用內容中，請參閱下一節。
  
![名為「不受保護的敏感資訊」的小工具設定](../media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>編輯建議的 DLP 原則

使用小工具建立 DLP 原則之後，原則會出現在安全性&amp;與規範中心的 [**原則**] 頁面的 [**資料遺失防護**] 底下。 
  
根據預設，此原則稱為「**系統建議」原則，用來共用機密資訊**。 這個原則可以完全自訂，與您從頭建立的任何 DLP 原則相同。 例如，如果您決定在使用小工具時未開啟附隨報告和原則提示，您可以隨時編輯原則並開啟這些選項。
  
![用於共用機密資訊的系統建議原則](../media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>構件的功能及未出現時

名為「未**受保護的敏感資訊**」的小工具會出現在安全性&amp;與規範**中心首頁的**[**建議供您使用**] 區段中。 
  
只有在下列情況時才會顯示此小工具：
  
- 在過去30天內，會偵測到包含任何五種最常見類型的敏感資訊的新檔，SharePoint 或 OneDrive。
    
- 機密資訊尚未受到現有 DLP 原則的保護。
    
不同于持續掃描資料的 DLP 原則，此建議會掃描 DLP 原則覆蓋範圍中每隔48小時的間隙，因此在上傳新內容之後，可能需要長達兩天的時間，建議才會顯示。
  
最後，在您使用小工具建立建議的 DLP 原則之後，該構件會從**首頁**消失。 
  

