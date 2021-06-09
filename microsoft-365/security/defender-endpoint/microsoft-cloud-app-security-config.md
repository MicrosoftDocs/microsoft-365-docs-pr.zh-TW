---
title: 設定 Microsoft Cloud App Security 整合
ms.reviewer: ''
description: 瞭解如何開啟設定，以啟用 Microsoft Defender 與 Microsoft Cloud App Security 的端點整合。
keywords: 雲端，應用程式，安全性，設定，整合，探索，報表
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
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844751"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中設定 Microsoft Cloud App Security

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


若要從 Microsoft Defender 受益于 Endpoint cloud 應用程式探索信號，請開啟 Microsoft Cloud App Security 整合。

>[!NOTE]
>您可以在執行 Windows 10 的裝置上使用[Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)的 E5 授權，取得此項功能; 版本 1709 (os 組建 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)) ，Windows 10，版本 1803 (os 組建 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)) ，Windows 10，版本 1809 (os 組建17763.379 搭配[KB4489899](https://support.microsoft.com/help/4489899)) 或更新版本。

> 請參閱[microsoft defender for endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) ，以取得 Microsoft defender for endpoint with Microsoft Cloud App Security 的詳細整合。 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中啟用 Microsoft Cloud App Security

1. 在功能窗格中，選取 [**喜好設定**] [  >  **高級功能**]。
2. 選取 [ **Microsoft Cloud App Security** ]，然後切換至 [**開啟**]。
3. 按一下 [ **儲存喜好** 設定]。

一旦啟動，Microsoft Defender for Endpoint 便會立即開始轉寄探索信號給雲端 App 安全性。

## <a name="view-the-data-collected"></a>查看收集的資料

若要在 microsoft Cloud Apps Security 中查看和存取 microsoft Defender for Endpoint data，請參閱[調查裝置 in 雲端 App 安全性](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。


如需雲端探索的詳細資訊，請參閱使用已 [探索的應用程式](/cloud-app-security/discovered-apps)。

如果您有興趣嘗試 Microsoft Cloud App Security，請參閱[Microsoft Cloud App Security 試用版](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。

## <a name="related-topic"></a>相關主題
- [Microsoft Cloud App Security 整合](microsoft-cloud-app-security-integration.md)
