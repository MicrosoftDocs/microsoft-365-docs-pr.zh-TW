---
title: Microsoft Defender ATP for Linux 靜態 proxy 探索
ms.reviewer: ''
description: 說明如何設定 Microsoft Defender ATP 以進行靜態 proxy 探索。
keywords: microsoft、defender、atp、linux、安裝、proxy
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
ms.openlocfilehash: 841e5d5169469edb804514458760c5f52e66edaa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059120"
---
# <a name="configure-microsoft-defender-for-endpoint-for-linux-for-static-proxy-discovery"></a>針對靜態 proxy 探索，設定 Microsoft Defender for Linux 的端點

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender ATP 可以使用環境變數探索 proxy 伺服器 ```HTTPS_PROXY``` 。 此設定 **必須在安裝** 時和產品安裝之後設定。

## <a name="installation-time-configuration"></a>安裝時間設定

在安裝期間， ```HTTPS_PROXY``` 環境變數必須傳遞給套件管理員。 套件管理員可以採用下列任何一種方式讀取此變數：

- ```HTTPS_PROXY```變數是以 ```/etc/environment``` 下列行定義的：

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- `HTTPS_PROXY`變數是以 package 管理員全域設定定義。 例如，在 Ubuntu 18.04 中，您可以將下列行新增到 `/etc/apt/apt.conf.d/proxy.conf` ：
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > 請注意，上述兩種方法可能會定義 proxy，以用於系統上的其他應用程式。 請謹慎使用此方法，或僅限這種方式是一般全域設定。
  
- `HTTPS_PROXY`變數預先安裝或卸載命令。 例如，使用 APT 套件管理員時，會在安裝 Microsoft Defender for Endpoint 時，按下列方式前置變數： 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > 請勿在環境變數定義和 apt 之間新增 sudo，否則將不會傳播此變數。

`HTTPS_PROXY`環境變數可能會在卸載期間定義。

請注意，如果需要 proxy 但未設定，則安裝和卸載不一定會失敗。 不過，遙測將不會送出，而且作業可能需要很長的時間，因為網路超時。

## <a name="post-installation-configuration"></a>安裝後的設定
  
安裝後， `HTTPS_PROXY` 環境變數必須在 Endpoint service 檔案中定義。 若要這麼做，請 `/lib/systemd/system/mdatp.service` 在文字編輯器中開啟以根使用者的模式。 然後，您可以採用下列其中一種方式將變數傳播至服務：

- 取消注釋該行 `#Environment="HTTPS_PROXY=http://address:port"` ，並指定您的靜態 proxy 位址。

- 新增一行 `EnvironmentFile=/path/to/env/file` 。 此路徑可以指向 `/etc/environment` 或自訂檔案，其中一個需要新增下列行：
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

修改檔案之後 `mdatp.service` ，儲存並關閉該檔案。 重新開機服務，以便可以套用變更。 在 Ubuntu 中，這包括兩個命令：  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
