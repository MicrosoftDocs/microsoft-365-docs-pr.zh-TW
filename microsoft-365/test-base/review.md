---
title: 檢閱
description: 上架之後的回顧區段。
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322642"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>步驟6：檢查您的選擇以建立套件。

1.  在此索引標籤上，服務會顯示您的測試詳細資料，並執行快速完整性檢查。 

    A ```Validation passed``` 或 ```Validation failed``` message 顯示是否可以繼續進行下一個步驟。

2.  請複查您的測試詳細資料，如果滿意，請按一下 ```Create``` 按鈕。 

![View 驗證](Media/validation.png)

3.  這會將套件上架到測試基底環境。 如果您已成功建立套件，則會觸發 verifys 您套件是否可以在 Azure 上成功執行的自動測試。

![成功的結果](Media/successful.png)

> [!Note]
> 您將會收到 Azure 入口網站的通知，以在套件驗證成功或失敗時通知您。 
>
> 請注意，此程式最多可能需要24小時，因此如果您的網頁不在使用中，則您的網頁很可能會超時，但通知將不會通知您已完成該隨選即用。 

  - Peradventure 在這種情況下，您可以在索引標籤上查看套件的狀態 ```Manage packages``` 。

![管理套件的影像](Media/managepackages.png)

  - 若要取得成功的測試，其結果可以透過及排程的間隔來查看，您可以在 ```Test Summary``` ```Security Updates Results``` ```Feature Updates Results``` 上傳的幾天之後經常開始。
  
  - 測試失敗時，需要您上傳新的套件。 
  
    您可以從「 ```test logs``` 和頁面下載進行進一步的 ```Security update results``` 分析 ```Feature updates results``` 。

  - 如果您經歷重複的測試失敗，請與您的錯誤詳細資料聯繫 testbasepreview@microsoft.com。 

## <a name="next-steps"></a>後續步驟

透過下列連結探索我們的內容指導方針。
> [!div class="nextstepaction"]
> [下一步](contentguideline.md)
