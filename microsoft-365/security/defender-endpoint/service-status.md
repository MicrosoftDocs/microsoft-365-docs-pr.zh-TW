---
title: 檢查 Microsoft Defender ATP 服務健康情況
description: 檢查 [Microsoft Defender ATP service health]，查看服務是否發生問題，並檢查先前已解決的問題。
keywords: 儀表板、服務、問題、服務健康情況、目前狀態、狀態史、影響摘要、初始根本原因、解析度、解決時間、預期的解決時間
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 45782fcce51e15adf61757d836d313d229558571
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058700"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a>檢查 Microsoft Defender for Endpoint service health

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)



>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

**服務健康** 情況提供有關 Endpoint Service 之 Defender 的目前狀態資訊。 您可以驗證服務健康情況是否良好，或是否有目前的問題。 如果發生問題，您會看到資訊，例如偵測到問題的時間、初級的根本原因以及預期的解決時間。

您也會看到已解決之歷史問題的資訊，以及解決問題的日期和時間等詳細資訊。 當服務沒有問題時，您會看到 [狀況良好] 狀態。

您可以從 [ **安全性作業] 儀表板** 上按一下 [磚]，或從功能窗格中選取 [ **服務健康** 情況] 功能表，以查看服務健康情況的詳細資料。

[ **服務狀況** 詳細資料] 頁面包含下列索引標籤：

- **目前狀態**
- **狀態歷程記錄**

## <a name="current-status"></a>目前狀態
[ **目前狀態** ] 索引標籤會顯示端點服務之 Defender 的目前狀態。 當服務執行順利時，就會顯示 [狀況良好的服務健康情況]。 如果出現問題，將會顯示下列服務詳細資料，以協助您深入瞭解問題：

- 偵測到問題的日期和時間
- 問題的簡短描述
- 更新時間
- 影響摘要
- 初步的根本原因
- 後續步驟
- 預期的解決時間

當問題解決時，在問題的進度上的更新會在頁面上反映出來。 您會看到更新的資訊，例如更新的估算解析度時間或後續步驟。

當問題解決時，它會記錄在 [ **狀態史** ] 索引標籤中。

## <a name="status-history"></a>狀態歷程記錄
[ **狀態記錄** ] 索引標籤會反映已出現及已解決的所有歷史問題。 您會看到已解決問題的詳細資料，以及解決問題時所包含的其他資訊。

### <a name="related-topic"></a>相關主題
- [View the Security operations 儀表板](security-operations-dashboard.md)
