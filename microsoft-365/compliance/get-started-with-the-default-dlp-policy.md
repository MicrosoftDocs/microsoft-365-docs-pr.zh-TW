---
title: 開始使用預設的 DLP 原則
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何使用此報告來精煉組織的預設資料遺失防護 (DLP) 原則。
ms.openlocfilehash: 7c8f0460f9cd02ee3d26197965f5ea74737ac833
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817612"
---
# <a name="get-started-with-the-default-dlp-policy"></a>開始使用預設的 DLP 原則

在您甚至建立第一個資料遺失防護 (DLP) 原則之前，DLP 都有助您使用預設原則來保護您的敏感資訊。 此預設原則及其建議 (如下所示) 協助您在組織外的人員共用包含信用卡號碼的電子郵件或檔時通知您，以保障機密內容的安全。 您會在安全性與合規性中心 **的首頁上** 看到此建議 &amp; 。 
  
您可以使用此小工具快速查看共用的敏感資訊的時間和程度，然後只需按一下一次或兩次，以精煉預設 DLP 原則。 您也可以隨時編輯預設 DLP 原則，因為它完全可自訂。 請注意，如果您第一次沒有看到建議，請嘗試按一下 [**建議**] 區段底部的 [**其他**]。 
  
![名為進一步的小工具保護共用內容](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>查看報告並調整預設 DLP 原則

當小工具顯示使用者與組織外部人員共用機密資訊時，請選擇底部的 [ **優化 DLP 原則** ]。 
  
詳細報告會向您顯示過去30天內，包含信用卡號碼共用的內容數量和數目。 請注意，規則相符可能需要長達48小時才能顯示在構件中。
  
為了協助保護機密資訊，預設 DLP 原則為：
  
- 在 Exchange、SharePoint 及包含至少一個信用卡號碼的 OneDrive 中，偵測到組織外部人員共用的內容。
    
- 顯示原則提示，當使用者嘗試與組織外部的人員共用此機密資訊時，將電子郵件通知傳送給他們。 如需這些選項的詳細資訊，請參閱 [傳送電子郵件通知及顯示 DLP 原則的原則秘訣](use-notifications-and-policy-tips.md)。
    
- 產生詳細的活動報告，使您可以追蹤與組織外部的人員共用內容的人員，以及他們的情況。 您可以使用[DLP 報告](view-the-dlp-reports.md)和[審核記錄資料](search-the-audit-log-in-security-and-compliance.md) (其中的**活動**  =  **DLP**) 來查看此資訊。
    
若要快速提煉預設 DLP 原則，您可以選擇讓它具有下列專案：
  
- 當使用者與組織外部的人員共用此機密資訊時，向您傳送附隨報告電子郵件。
    
- 將其他使用者新增至電子郵件附隨報告。
    
- 封鎖存取包含機密資訊的內容，但是允許使用者在需要時覆寫和共用或傳送。
    
如需有關附隨報告或限制存取的詳細資訊，請參閱 [資料遺失防護原則一覽](data-loss-prevention-policies.md)。
  
如果您想要稍後變更這些選項，您可以隨時編輯預設 DLP 原則，請參閱下一節。
  
![名為進一步保護共用內容的小工具設定](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>編輯預設 DLP 原則

這個原則命名為「**預設 DLP 原則**」，而且會出現在安全性與規範中心的 [**原則**] 頁面的 [**資料遺失防護**] 底下 &amp; 。 
  
這個原則可以完全自訂，與您從頭建立的任何 DLP 原則相同。 您也可以關閉或刪除原則，如此一來，您的使用者就不會再收到原則提示或電子郵件通知。
  
![名為預設 DLP 原則的 DLP 原則](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>構件的功能及未出現時

在安全性與合規性中心**首頁的 [** **建議**] 區段中，會顯示名為「**進一步保護共用內容**」的小工具 &amp; 。 
  
只有在下列情況時才會顯示此小工具：
  
- 在安全性與 &amp; 合規性中心或 Exchange 系統管理中心中，沒有任何資料遺失防護原則。 此小工具的目的是協助您開始使用 DLP，所以如果您已有 DLP 原則，就不會顯示。
    
- 在過去30天內，包含至少一張信用卡的內容已與組織外部的人員共用。
    
請注意，可供小工具使用的規則比對可長達48個小時，所以在偵測到外部共用的敏感資訊之後，可能需要長達兩天的時間，建議才會顯示。
  
最後，在您使用小工具來提煉預設的 DLP 原則之後，該構件會從 **首頁** 消失。 
  

