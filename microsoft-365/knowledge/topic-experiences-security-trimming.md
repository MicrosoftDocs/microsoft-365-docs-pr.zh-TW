---
title: Microsoft Viva 主題安全性調整
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: 瞭解如何使用安全性來查看主題。
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939620"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Microsoft Viva 主題安全性調整 

Viva 主題使用者無法在主題中查看其現有 Office 365 許可權可防止他們看到的資訊。 使用者在主題頁面上看到的所有內容 (例如 SharePoint 網站、文件、檔案) 將是他們獲允許可看到的資訊。 Viva Topics 不會變更任何現有的權限。

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>為何兩位使用者可能會有不同的相同主題視圖

透過 AI 或手動策劃建立主題時，可以包含主題描述、替代名稱、與主題相關聯的人員，以及與該主題相關的網站、頁面和檔案。 當您在主題頁面上查看這項資訊時，可能是兩位查看相同主題的使用者看不到相同的資訊。
  
例如，當使用者 1 檢視海王星主題頁面時，他們可能會看到此主題頁面檢視。

![使用者1的 Neptune 主題](../media/knowledge-management/user2-topic-view.png) </br> 

不過，當使用者2查看同一個 Neptune 主題頁面時，其視圖與使用者1不同。  使用者2能夠在主題頁面的 [已固定的檔案 **及頁面**] 區段中查看 *DG-2000 產品概述* 檔案，但不會針對使用者1顯示此頁面。 

![使用者2的 Neptune 主題](../media/knowledge-management/user1-topic-view.png) </br> 

使用者在相同主題上看到的不同之處在于，使用者可能沒有查看相關網站或檔案的 Office 365 許可權。  Viva 主題會尊重為主題中的專案設定的許可權，而且無法變更其存取權。 在我們的範例中，使用者1無法在 Neptune 的 [主題] 頁面中查看 *DG-2000 產品概述* 檔案，因為使用者1沒有查看檔案的 Office 365 許可權。

如果使用者無法在主題中看到足夠的資訊供其使用，則使用者將無法使用該主題。 發生這種情況時，使用者將不會看到反白顯示的主題。 另一位擁有主題中更多資訊權限的使用者，將能看到該主題。


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>知識管理員和主題參與者的主題許可權

指派管理主題許可權的使用者-知識主管，只能夠查看其具有在主題中查看之許可權的資訊。

同樣地，具有「建立及編輯」主題許可權的使用者-主題投稿者-只能夠查看其具有在主題中查看之許可權的資訊。 


## <a name="ai-versus-manually-curated-topic-information"></a>AI 與手動策劃的主題資訊

主題可以包含 AI 所產生的資訊，以及主題投稿者或知識主管新增或編輯的資訊。

 - AI 新增的主題資訊只有擁有來源內容存取權的人才能看到。
 - 主題描述和人員資訊，由主題投稿人或知識管理員手動新增或編輯，可供每個可以查看主題的人看到。
 - 不論是使用來源內容的許可權，還是透過 AI 手動新增或新增檔、頁面和網站，都只會看到這些使用者。

下表說明哪些使用者-主題查看者、投稿人和知識管理員-根據其許可權，可在指定的主題中查看。

|主題項目|使用者可以看到的內容|
|:---------|:------------------|
|主題名稱|使用者可以查看主題中心主題的主題名稱。 若使用者沒有來源內容的許可權或對使用者的關聯性很低，某些主題可能不會顯示。|
|主題描述|僅具有來源內容存取權限的使用者可以看到 AI 產生的描述。 所有使用者都可以看到手動輸入或編輯的描述。|
|人員|所有使用者都可以看到釘選人員。 僅具有來源內容存取權限的使用者可以看到建議人員。|
|檔案|僅具有來源內容存取權限的使用者可以看到檔案。|
|頁面|僅具有來源內容存取權限的使用者可以看到頁面。|
|網站|僅具有來源內容存取權限的使用者可以看到網站。|




## <a name="see-also"></a>請參閱

