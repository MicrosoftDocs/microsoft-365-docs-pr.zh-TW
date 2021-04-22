---
title: 疑難排解 macOS 中的 Microsoft Defender for Endpoint 的內核擴充問題
description: 疑難排解 macOS 中的 Microsoft Defender for Endpoint 中的內核擴充相關問題。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，內核，分機
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
ms.openlocfilehash: 9dc3ee17d79972b5d36c5fff58fbe4cc486027bd
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934270"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-on-macos"></a>疑難排解 macOS 中的 Microsoft Defender for Endpoint 的內核擴充問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [macOS 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本文提供如何疑難排解在 macOS 的 Microsoft Defender for Endpoint 中安裝之核心擴充問題的相關資訊。

從 macOS 高的塞拉里昂 (10.13) 開始，macOS 需要明確核准所有內核擴充，才能允許在裝置上執行。

如果您未在 macOS 上部署/安裝 Microsoft Defender for Endpoint 時核准核心擴充，應用程式會顯示橫幅，提示您加以啟用：

   ![RTP 停用的螢幕擷取畫面](images/mdatp-32-main-app-fix.png)

您也可以執行 ```mdatp health``` 。 它會報告是否已啟用即時保護，但無法使用。 這表示未核准在您的裝置上執行內核擴充。

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

下列各節提供如何解決此問題的指引，取決於您用來在 macOS 上部署 Microsoft Defender for Endpoint 的方法。

## <a name="managed-deployment"></a>受管理的部署

請參閱您用來部署產品的管理工具對應的指示：

- [以 JAMF 為基礎的部署](mac-install-with-jamf.md)
- [Microsoft Intune 型部署](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>手動部署

若自產品安裝後超過30分鐘，請流覽至 [**系統偏好** 設定  >  **安全性] & 隱私權**，您必須從開發人員「Microsoft Corporation」**允許** 系統軟體。

如果您未看到此提示，表示已超過30分鐘或更多分鐘，且尚未核准內核擴充，無法在您的裝置上執行：

![提示到期的螢幕擷取畫面之後的安全性和隱私權視窗](images/mdatp-33-securityprivacysettings-noprompt.png)

在此情況下，您必須執行下列步驟，以再次觸發核准流程。

1. 在終端中，嘗試安裝驅動程式。 下列作業將會失敗，因為未核准在裝置上執行內核擴充。 不過，它會再次觸發核准流程。

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. 從功能表開啟 **系統偏好** 設定  >  **安全性 & 隱私權**。  (先關閉它（如果已開啟）。 ) 

3. **允許** 開發人員「Microsoft Corporation」的系統軟體

4. 在 [終端] 中重新安裝驅動程式。 這次作業會成功：

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    橫幅應該會從 Defender 應用程式中消失， ```mdatp health``` 現在應報告即時保護已啟用且可供使用：

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
