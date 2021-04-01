---
title: 針對 Mac 的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題疑難排解
description: 本主題說明如何疑難排解 Microsoft Defender for Mac 的雲端連線問題
keywords: microsoft，defender，atp，mac，安裝，部署，卸載，intune，jamf，macos，catalina，mojave，高塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e522495fa86b5a71faa9f25cc863c29cc5d124c0
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476664"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-mac"></a>針對 Mac 的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題疑難排解

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平臺** macOS

本主題說明如何針對 Mac 的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題的疑難排解。

## <a name="run-the-connectivity-test"></a>執行連線測試
若要測試 Mac 版的 Endpoint 是否可以使用目前的網路設定與雲端通訊，請從命令列執行連線測試：

```Bash
mdatp connectivity test
```

期望的輸出：
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

如果連線測試失敗，請檢查裝置是否有網際網路存取權，以及是否有 [任何產品需要的端點](microsoft-defender-endpoint-mac.md#network-connections) ，以供 proxy 或防火牆封鎖。

失敗，包含彎曲錯誤35或60指出憑證鎖定拒絕，這表示 SSL 或 HTTPS 檢查的潛在問題。 請參閱下列有關 SSL 檢查設定的指示。

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>在沒有 proxy 或 Proxy 自動設定 (PAC) 或使用 Web Proxy 自動探索通訊協定 (WPAD) 的情況下疑難排解步驟
請使用下列程式來測試：在沒有 proxy 或 Proxy 自動 (PAC) 或使用 Web Proxy 自動探索通訊協定 (WPAD) 的環境中，未封鎖連線。

如果 proxy 或防火牆封鎖匿名流量，請確定先前所列的 URLs 允許匿名流量。

> [!WARNING]
> 不支援已驗證的 proxy。 確定只使用 PAC、WPAD 或靜態 proxy。 出於安全性原因，也不支援 SSL 檢查和截取 proxy。 設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接將 Microsoft Defender for Mac 的資料傳遞至相關的 URLs，而不需要截獲。 將您的截取憑證新增至全域存放區將不允許截取。
若要測試是否未封鎖連線：在 Microsoft Edge for Mac 或 Safari 開啟和中的瀏覽器 https://x.cp.wd.microsoft.com/api/report 中 https://cdn.x.cp.wd.microsoft.com/ping 。

（選用）在 [終端] 中執行下列命令：

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

此命令的輸出應類似下列所示：
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
