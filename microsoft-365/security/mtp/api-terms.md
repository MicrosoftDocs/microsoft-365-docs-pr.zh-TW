---
title: Microsoft 365 Defender API 授權與使用條款
description: Microsoft 365 Defender 中 API 授權和使用規定的說明
keywords: api、apis、授權、條款、apis、法律、聲明、管理規定
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 82f31c449ae2e102ac7464e0fef75277660844d1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930951"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender API 授權與使用條款

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>官方條款

Microsoft 365 Defender API 受 [Microsoft API 授權與使用條款所規範](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)。

## <a name="legal-notices"></a>法律聲明

Microsoft 和任何投稿人根據 Creative Commons Attribution [ ](https://github.com/MicrosoftDocs/microsoft-365-docs)4.0 國際公用授權，授予您此存放庫中 Microsoft 檔和其他內容的許可權。 有關詳細資訊，請參閱 [授權](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) 檔案。

檔中參照的 Microsoft、Windows、Microsoft Azure 及/或其他 Microsoft 產品與服務可能是 Microsoft 在美國及/或其他國家/地區所商標或注冊商標。

此專案授權未授予您使用任何 Microsoft 名稱、標誌或商標的權利。 Microsoft 的一般商標指導方針可以在 [Microsoft 商標上找到](https://go.microsoft.com/fwlink/?LinkID=254653)。

隱私權資訊可在 Microsoft 的 [隱私權中找到](https://privacy.microsoft.com)。

Microsoft 和任何投稿人保留所有其他權利，不論是根據其各自的著作權、保護法或商標權，無論是暗示、反反言或其他方式均保留。

## <a name="other-restrictions"></a>其他限制

進位搜尋 API[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations)對於所發回的結果數量及可查詢的資料有一些限制。

1. 您僅能查詢過去 30 天內的資料。
1. 結果將包含最多 100，000 列。

### <a name="quotas-and-resource-allocation"></a>配額和資源配置

Microsoft 365 Defender API 具有節流閾值。

- **事件 API：** 每分鐘最多 50 個通話或每小時 1500 個通話。
- **進一** 步搜尋 API：每分鐘最多 15 個通話、每小時 10 分鐘的執行時間，以及每天 4 小時的執行時間。

指出節流是 HTTP 回應狀態碼 `429` 。

如果您的要求受到節流控制，回復內體會指出您可以開始再次提出要求的時間。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender API 概觀](api-overview.md)
- [支援的 Microsoft 365 Defender API](api-supported.md)
- [存取 Microsoft 365 Defender API](api-access.md)
