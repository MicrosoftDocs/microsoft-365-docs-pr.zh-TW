---
title: 針對 Linux 上的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題的疑難排解
ms.reviewer: ''
description: 針對 Linux 上的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題的疑難排解
keywords: microsoft，defender，atp，linux，cloud，connectivity，通訊
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 985e4c39c60600da892c010b6ee26e9c98bb0611
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903163"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>針對 Linux 上的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題的疑難排解

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>執行連線測試

若要測試 Linux 的 Defender 是否可以使用目前的網路設定與雲端進行通訊，請從命令列執行連線測試：

```bash
mdatp connectivity test
```

期望的輸出：

```output
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

如果連線測試失敗，請檢查裝置是否有網際網路存取權，以及是否有 [任何產品需要的端點](microsoft-defender-endpoint-linux.md#network-connections) ，以供 proxy 或防火牆封鎖。

失敗的情況下，錯誤35或60，表示憑證鎖定拒絕。 請檢查連接是否低於 SSL 或 HTTPS 檢查。 如果是，請將 Microsoft Defender for 端點新增至允許清單。

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>沒有 proxy 或透明 proxy 環境的疑難排解步驟

若要測試在沒有 proxy 或透明 proxy 的環境中，未封鎖連線，請在 terminal 中執行下列命令：

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

此命令的輸出應類似下列所示：

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>使用靜態 proxy 環境的疑難排解步驟

> [!WARNING]
> 不支援 PAC、WPAD 及已驗證的 proxy。 確定只使用靜態 proxy 或透明 proxy。
>
> 出於安全性原因，也不支援 SSL 檢查和截取 proxy。 設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接透過來自 Linux 的 Defender 的資料傳遞至相關的 URLs，而不需截獲。 將您的截取憑證新增至全域存放區將不允許截取。

若需要靜態 proxy，請將 proxy 參數新增至上述命令，其中會 `proxy_address:port` 對應至 proxy 位址及通訊埠：

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

確定您使用的是檔案中所設定的相同 proxy 位址及埠 `/lib/system/system/mdatp.service` 。 如果上述命令有錯誤，請檢查您的 proxy 設定。

> [!WARNING]
> 靜態 proxy 無法透過全系統 `HTTPS_PROXY` 環境變數進行設定。 相反地，請確定檔案 `HTTPS_PROXY` 中已正確設定 `/lib/system/system/mdatp.service` 。

若要使用靜態 proxy， `mdatp.service` 必須修改檔案。 確定 `#` 已移除前導，以取消注釋下行中的下列各項 `/lib/systemd/system/mdatp.service` ：

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

此外，請確定已填入正確的靜態 proxy 位址進行取代 `address:port` 。

如果此檔案正確，請嘗試在終端中執行下列命令，以針對 Linux 重新載入 Defender for the Endpoint，然後傳播設定：

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

成功時，請從命令列嘗試另一個連線測試：

```bash
mdatp connectivity test
```

如果問題持續發生，請與客戶支援人員聯繫。

## <a name="resources"></a>資源

- 如需如何將產品設定為使用靜態 proxy 的詳細資訊，請參閱 [Configure Microsoft Defender for a Endpoint for static proxy discovery](linux-static-proxy-configuration.md)。
