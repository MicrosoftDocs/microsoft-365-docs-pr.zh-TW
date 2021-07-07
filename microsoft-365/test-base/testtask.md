---
title: 設定測試工作
description: 設定測試工作
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322561"
---
# <a name="step-4-the-tasks-tab"></a>步驟4： [任務] 索引標籤

在 [任務] 索引標籤上，您會在 [二進位] 索引標籤底下的 [zip] 資料夾中，提供您測試腳本的路徑。

  - 無 **箱的測試腳本：** 輸入您安裝、啟動、關閉及卸載腳本的相對路徑。 您也可以選擇安裝腳本的其他設定。
  - **功能測試腳本：** 輸入每個已上傳的功能測試腳本的相對路徑。 您可以使用按鈕新增其他功能測試腳本 ```Add Script``` 。 您至少需要一個 (1) 腳本，最多可以新增八個 (8) 功能測試腳本。 
  
    腳本會在上傳順序中執行，在特定腳本中的失敗將會停止執行後續的腳本。
    您也可以選擇為每個提供的腳本選取其他設定。

## <a name="set-script-path"></a>設定腳本路徑

![測試工作的影像](Media/testtask.png)

如何在下列位置提供資料夾結構的相對路徑的範例：

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** 會有。 _ScriptX.ps1_ 做為相對路徑。
  - **Script.ps1** 會將 _folder1/script.ps1_ 當做相對路徑。


## <a name="next-steps"></a>後續步驟

查看下一篇文章中 [測試選項] 索引標籤的詳細資料 
> [!div class="nextstepaction"]
> [下一步](testoptions.md)
