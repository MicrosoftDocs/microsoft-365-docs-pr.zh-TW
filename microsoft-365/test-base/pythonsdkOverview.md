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
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="75fea-103">針對 Python 測試基底 SDK</span><span class="sxs-lookup"><span data-stu-id="75fea-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="75fea-104">概觀</span><span class="sxs-lookup"><span data-stu-id="75fea-104">Overview</span></span>
<span data-ttu-id="75fea-105">測試基底 SDK 可用於與 Azure 測試基底資源進行互動。</span><span class="sxs-lookup"><span data-stu-id="75fea-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="75fea-106"> (例如，管理您的應用程式套件、包含建立套件、編輯套件和刪除套件) </span><span class="sxs-lookup"><span data-stu-id="75fea-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="75fea-107">透過 SDK，可獲得的測試摘要和分析結果包括： scriptExecution、可靠性、memoryUtilization、cpuUtilization、memoryRegression、cpuRegression。</span><span class="sxs-lookup"><span data-stu-id="75fea-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="75fea-108">透過測試基底 SDK，您可以整合 CI/CD 管線中的測試基底。</span><span class="sxs-lookup"><span data-stu-id="75fea-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="75fea-109">用戶端程式庫</span><span class="sxs-lookup"><span data-stu-id="75fea-109">Client Library</span></span>

<span data-ttu-id="75fea-110">安裝含 pip 的測試基底套件。</span><span class="sxs-lookup"><span data-stu-id="75fea-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="75fea-111">範例</span><span class="sxs-lookup"><span data-stu-id="75fea-111">Example</span></span>
