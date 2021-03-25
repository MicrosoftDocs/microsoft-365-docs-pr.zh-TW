---
title: 設定 Microsoft Cloud App Security 整合
ms.reviewer: ''
description: 瞭解如何開啟設定，以啟用 Microsoft Defender for Endpoint 與 Microsoft Cloud App Security 的整合。
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
ms.openlocfilehash: f5e2919ae3fcbbb443f6d160c68633ee3427ae5a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187526"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中設定 Microsoft Cloud App Security

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


若要受益于 Microsoft Defender for Endpoint cloud 應用程式探索信號，請開啟 Microsoft Cloud App Security integration。

>[!NOTE]
>這項功能可[搭配使用 Windows](https://support.microsoft.com/help/4493441) 10、版本 1709 (os 組建16299.1085 （) 含[KB4493464](https://support.microsoft.com/help/4493464)) 1809，windows 10，version 1803 (Os 組建17134.704 搭配[KB4489899](https://support.microsoft.com/help/4489899) (或更新版本的 windows 10 版本）之裝置上的[企業行動](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)裝置和安全性的 E5 授權。

> 如需 microsoft cloud app security 的 Microsoft Defender for Endpoint 的詳細整合，請參閱 [Microsoft defender For endpoint integration With Microsoft Cloud App security](https://docs.microsoft.com/cloud-app-security/mde-integration) 。 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中啟用 Microsoft Cloud App Security

1. 在功能窗格中，選取 [**喜好設定**] [  >  **高級功能**]。
2. 選取 [ **Microsoft Cloud App Security** ]，然後切換至 [ **開啟**]。
3. 按一下 [ **儲存喜好** 設定]。

一旦啟動，Microsoft Defender for Endpoint 便會立即開始將探索信號轉送至 Cloud App Security。

## <a name="view-the-data-collected"></a>查看收集的資料

若要在 Microsoft Cloud Apps Security 中查看和存取 Microsoft Defender for Endpoint data，請參閱 [在 Cloud App security 中調查裝置](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。


如需雲端探索的詳細資訊，請參閱使用已 [探索的應用程式](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

如果您有興趣嘗試 Microsoft Cloud App Security，請參閱 [Microsoft Cloud App Security 試用版](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。

## <a name="related-topic"></a>相關主題
- [Microsoft Cloud App Security 整合](microsoft-cloud-app-security-integration.md)
