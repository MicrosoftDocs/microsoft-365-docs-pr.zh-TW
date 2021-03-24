---
title: Microsoft 365 Defender APIs 授權和使用條款
description: Microsoft 365 Defender 中 APIs 授權與使用條款的描述
keywords: api、api、授權、條款、api、法律、通知、行為準則
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9b70311726b6c1c5bedf34a18ee1763255c93ba3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057279"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender APIs 授權和使用條款

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。 Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。

## <a name="official-terms"></a>官方字詞

Microsoft 365 Defender APIs 受 [microsoft APIs 授權和使用條款的](/legal/microsoft-apis/terms-of-use)制約。

## <a name="legal-notices"></a>法律通知

Microsoft 和任何投稿人會授與您對 [此存放庫](https://github.com/MicrosoftDocs/microsoft-365-docs)中的 Microsoft 檔及其他內容的授權，在 [創造性 Commons 特性4.0 國際公開授權] 底下。 如需詳細資訊，請參閱 [授權](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) 檔案。

檔中參考的 microsoft、Windows、Microsoft Azure 和/或其他 Microsoft 產品及服務，都可能是美國及/或其他國家/地區之 Microsoft 的商標或注冊商標。

此專案的授權不會授與您使用任何 Microsoft 名稱、徽標或商標的權利。 您可以在 [Microsoft 商標](https://go.microsoft.com/fwlink/?LinkID=254653)上找到 microsoft 的一般商標指導方針。

您可以在 [Microsoft](https://privacy.microsoft.com)上找到隱私權資訊。

Microsoft 和任何投稿人都會保留所有其他權力，不論是在各自的版權、專利或商標，不論是以暗示、estoppel 還是其他方式。

## <a name="other-restrictions"></a>其他限制

「高級搜尋」 API 對傳回的結果數目有一些 [限制](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) ，以及可以查詢的資料。

1. 您只能查詢過去30天的資料。
1. 結果最多會包含100000列。

### <a name="quotas-and-resource-allocation"></a>配額和資源配置

Microsoft 365 Defender APIs 具有節流閾值。

- **事件 API**：每分鐘最多50個通話或每小時1500個通話。
- **高級搜尋 API**：每分鐘最多15個通話、每小時10分鐘的執行時間，以及每天的執行時間4小時。

指出節流的 HTTP 回應狀態碼為 `429` 。

如果您的要求遭到限制，回應內文會指出您可以再次開始進行要求的時間。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender APIs 概述](api-overview.md)
- [支援的 Microsoft 365 Defender API](api-supported.md)
- [存取 Microsoft 365 Defender APIs](api-access.md)