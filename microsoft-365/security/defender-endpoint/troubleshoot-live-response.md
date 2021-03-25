---
title: 疑難排解 Microsoft Defender ATP live response 問題
description: 疑難排解在 Microsoft Defender ATP 中使用 live response 時可能發生的問題
keywords: 疑難排解即時回應、即時、回應、鎖定、檔
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 62525548be777a3187cea5ed4be622ac9d42079b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183812"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>疑難排解 Microsoft Defender 的 Endpoint live 回應問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

此頁面提供疑難排解 live response 問題的詳細步驟。

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>在即時回應會話期間無法存取檔
當您嘗試在 live response session 期間採取動作時，您會遇到錯誤訊息，指出無法存取檔案，您必須使用下列步驟來解決問題。

1. 複製下列腳本代碼片段，並將它儲存為 PS1 檔案：

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. 將腳本新增至 live 回應文件庫。
3. 以一個參數執行腳本：要複製之檔案的檔案路徑。
4. 流覽至您的 TEMP 資料夾。
5. 請執行您想要對複製的檔案採取的動作。

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>在初始連線期間緩慢即時回應會話或延遲
Live response 利用在 Windows 中的 WNS 服務，使用 Defender 進行 Endpoint 感應器註冊。 如果您有即時回應的連線問題，請確認下列詳細資料：
1. `notify.windows.com` 在您的環境中未遭到封鎖。 如需詳細資訊，請參閱 [Configure device proxy And Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。
2. WpnService (Windows 推入通知系統服務) 未停用。

請參閱下列文章，以完全瞭解 WpnService 服務的行為和需求：
- [Windows 推播通知服務 (WNS) 概述](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [支援 WNS 流量的企業防火牆和 Proxy 設定](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Microsoft 推播通知服務 (MPNS) 公用 IP 範圍](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

