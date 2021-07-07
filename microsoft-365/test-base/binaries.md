---
title: Upload應用程式二進位
description: 如何開始使用 M365 的測試基底
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322606"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>步驟3： Upload 二進位檔案、相依性及腳本

在此索引標籤上，您會上載單一的 zip 套件，其中包含您的二進位檔案、相依性及腳本，用來執行測試套件。

## <a name="upload-package-zip-file"></a>Upload 套件 zip 檔案

![Upload 二進位檔](Media/AddBinaries.png)

  - 上傳的相依性可以包含測試框架、腳本引擎或將存取以執行應用程式或測試案例的資料。 例如，您可以上傳 Selenium 及 webdriver 安裝程式，以協助執行瀏覽器型測試。
  - 最佳作法是確保您的腳本活動保持在模組式（亦即，）。 
    - ```Install```腳本只會執行安裝作業。
    - ```Launch```腳本只會啟動應用程式。
    - ```Close```腳本只會關閉應用程式。
    - 選用的 ```Uninstall``` 腳本只會卸載應用程式。

**目前，此入口網站只支援 PowerShell 腳本。**


## <a name="next-steps"></a>後續步驟 

繼續進行下一篇文章，移至步驟4： **設定測試工作**。
> [!div class="nextstepaction"]
> [回去](uploadApplication.md)
> [!div class="nextstepaction"]
> [下一步](testtask.md)

