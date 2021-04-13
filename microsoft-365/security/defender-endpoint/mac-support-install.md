---
title: 疑難排解適用于 Mac 的 Microsoft Defender ATP 安裝問題
description: 疑難排解 Microsoft Defender ATP for Mac 中的安裝問題。
keywords: microsoft、defender、atp、mac、安裝
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
ms.openlocfilehash: 754f389f37bce3be1c5a636f1911b5d0fb3fd29c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689614"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>疑難排解 macOS 上的 Microsoft Defender for Endpoint 的安裝問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [macOS 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>安裝失敗

手動安裝時，安裝精靈的 [摘要] 頁面會說「安裝期間發生錯誤。 安裝程式發生錯誤，導致安裝失敗。 請與軟體製造商聯繫以取得協助。」 針對 MDM 部署，它也會顯示為一般安裝失敗。

雖然使用者未向使用者顯示確切的錯誤，我們還是會保留記錄檔與安裝進度 `/Library/Logs/Microsoft/mdatp/install.log` 。 每個安裝會話都會附加到此記錄檔。 您可以使用 `sed` 僅輸出上一個安裝會話：

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

在此範例中，會將實際原因加上首碼 `[ERROR]` 。
由於不支援這些版本之間的降級，因此安裝失敗。

## <a name="mdatp-install-log-missing-or-not-updated"></a>MDATP 安裝記錄遺失或未更新

在極少的情況下，安裝會在 MDATP 的/Library/Logs/Microsoft/mdatp/install.log 檔案中留下任何追蹤。
您可以在 MDM 部署中查詢 macOS 的記錄檔，確認安裝發生問題，並分析可能的錯誤 (當沒有用戶端 UI) 時，這會很有説明。 建議您使用縮小時間的時段執行查詢，並根據記錄處理常式名稱來篩選，因為會有大量的資訊。

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
