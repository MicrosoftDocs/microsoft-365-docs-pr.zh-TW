---
title: 在 Jamf Pro 中設定裝置群組
description: 瞭解如何在 macOS 上為 Microsoft Defender for Endpoint 設定 Jamf Pro 中的裝置群組
keywords: device，group，microsoft，defender，Microsoft Defender for Endpoint，mac，安裝，部署，卸載，intune，jamfpro，macos，catalina，mojave，高塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 772b67ec84ae9614c9322763c140a60e7884644d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933802"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>在 Jamf Pro 中的 macOS 裝置群組上設定 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

設定裝置群組，類似于群組原則組織統一 (Ou) 、Microsoft 端點 Configuration Manager 的裝置集合，以及 Intune 的裝置群組。

1. 流覽至 [ **靜態電腦群組**]。

2. 選取 [ **新增**]。 

    ![Jamf Pro1 的影像](images/jamf-pro-static-group.png)

3. 提供顯示名稱，然後選取 [ **儲存**]。

    ![Jamf Pro2 的影像](images/jamfpro-machine-group.png)

4. 現在，您會在 [**靜態電腦群組**] 底下看到 **Contoso 的電腦群組**。

    ![Jamf Pro3 的影像](images/contoso-machine-group.png)

## <a name="next-step"></a>下一步
- [在 Jamf Pro 的 macOS 原則上設定 Microsoft Defender for Endpoint](mac-jamfpro-policies.md)
