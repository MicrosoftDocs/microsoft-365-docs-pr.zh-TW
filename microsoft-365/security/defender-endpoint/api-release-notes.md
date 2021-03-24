---
title: Microsoft Defender for Endpoint API 發行附注
description: Microsoft Defender APIs 的端點集合所進行的更新的版本資訊。
keywords: microsoft defender for endpoint api 發行附注、mde、api、mdatp api、更新、記事、版本
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: e37841fa17a5998c431c6a76b878f20ef1b06d10
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057164"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Microsoft Defender for Endpoint API 發行附注

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

下列資訊會列出對 Microsoft Defender for Endpoint APIs 所做的更新，以及所進行的日期。


> [!TIP]
> RSS 摘要：將下列 URL 複製並貼到您的摘要讀取器時，獲得此頁面的通知： 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a>10.02.2021
<hr>

- 新增 API： [批次更新提醒](batch-update-alerts.md)。 

<br>

### <a name="25012021"></a>25.01.2021
<hr>

- 將 [高級搜尋 API](run-advanced-query-api.md) 的更新率限制從15個要求的每分鐘的45個要求。 

<br>

### <a name="21012021"></a>21.01.2021
<hr>

- 新增 API：依標籤 [尋找裝置](machine-tags.md)。 
- 新增 API：匯 [入指示器](import-ti-indicators.md)。 

<br>

### <a name="03012021"></a>03.01.2021
<hr>

- 更新的警示證據：新增 ***detectionStatus** _、 _*_ParentProcessFilePath_*_ 和 _ *_parentProcessFileName_** 屬性。
- 已更新的 [警示實體](alerts.md)：新增 ***detectorId*** 屬性。

<br>

### <a name="15122020"></a>15.12.2020
<hr>

- 已更新 [裝置](machine.md) 實體：新增 ***IpInterfaces*** 清單。 請參閱 [清單裝置](get-machines.md)。

<br>

### <a name="04112020"></a>04.11.2020
<hr>

- 新增 API： [Set device value](set-device-value.md)。
- 已更新 [裝置](machine.md) 實體：新增 ***deviceValue*** 屬性。

<br>

### <a name="01092020"></a>01.09.2020
<hr>

- 新增選項，以使用其相關的證據來擴充警示實體。 請參閱 [清單提醒](get-alerts.md)。

<br>
<br>