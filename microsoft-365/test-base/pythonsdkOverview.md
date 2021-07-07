---
title: 針對 Python 測試基底 SDK
description: 瞭解有關瞭解測試基底的 Python SDK 的詳細資料
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322599"
---
# <a name="test-base-sdk-for-python"></a>針對 Python 測試基底 SDK

## <a name="overview"></a>概觀
測試基底 SDK 可用於與 Azure 測試基底資源進行互動。  (例如，管理您的應用程式套件、包含建立套件、編輯套件和刪除套件) 

透過 SDK，可獲得的測試摘要和分析結果包括： scriptExecution、可靠性、memoryUtilization、cpuUtilization、memoryRegression、cpuRegression。

透過測試基底 SDK，您可以整合 CI/CD 管線中的測試基底。

## <a name="client-library"></a>用戶端程式庫

安裝含 pip 的測試基底套件。

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>範例
