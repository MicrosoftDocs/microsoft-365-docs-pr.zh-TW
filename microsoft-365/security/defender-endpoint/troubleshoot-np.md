---
title: 疑難排解網路保護的問題
description: 用於疑難排解 Microsoft Defender for Endpoint 中的網路保護問題的資源和範例程式碼。
keywords: 疑難排解，錯誤，修正，windows defender 例如，asr，rules，hips，疑難排解，審核，排除，錯誤正值，已中斷，封鎖，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 481a8f15d6a41bda8dc866ce40d98c4f3717223d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844051"
---
# <a name="troubleshoot-network-protection"></a>疑難排解網路保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


當您使用 [網路保護](network-protection.md) 時，可能會發生問題，例如：

- 網路保護會封鎖安全 (誤報) 的網站
- 網路保護無法封鎖可疑或已知惡意的網站 (false 負數) 

疑難排解這些問題有四個步驟：

1. 確認必要條件
2. 使用稽核模式來測試規則
3. 針對誤報) 新增指定之規則 (的排除
4. 提交支援記錄檔

## <a name="confirm-prerequisites"></a>確認必要條件

只有在下列情況下，網路保護才能在裝置上運作：

>[!div class="checklist"]
> - 端點執行 Windows 10 專業版或 Enterprise edition 版本版本1709或更新版本。
> - 端點使用 Microsoft Defender 防毒軟體作為獨立的防防毒保護應用程式。 [請參閱使用非 Microsoft 防病毒方案時會發生什麼情況](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。
> - 已啟用[即時保護](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。
> - 已啟用[雲端傳送保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)功能。
> - 未啟用稽核模式。 使用 [群組原則](enable-network-protection.md#group-policy) 將規則設定為 **停用** (值： **0**) 。

## <a name="use-audit-mode"></a>使用稽核模式

您可以在稽核模式中啟用網路保護，然後再流覽我們所建立的網站，以示範該功能。 網路保護將允許所有的網站連線，但是會記錄事件，以指出在啟用網路保護時，任何已封鎖的連線。

1. 將 [網路保護] 設定為 [ **稽核模式]**。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. 執行導致問題的連線活動 (例如，嘗試訪問網站，或連線至您要封鎖) 的 IP 位址。

3. [查看網路保護事件記錄](network-protection.md#review-network-protection-events-in-windows-event-viewer) 檔，以查看該功能是否已設定為 **啟用**，以查看該功能是否會封鎖連線。
   
   如果網路保護未封鎖您期望它封鎖的連線，請啟用該功能。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>報告誤報或 false 負數

如果您已使用示範網站和審計模式來測試功能，且網路保護在預先設定的案例上運作，但未如預期的那樣運作，請使用[Windows Defender 安全性智慧 web 提交表單](https://www.microsoft.com/wdsi/filesubmission)報告 false 負數或 false 正值 for a network protection。 透過 E5 訂閱，您也可以 [提供任何相關聯警示的連結](alerts-queue.md)。

請參閱 [Microsoft Defender For Endpoint 中的 Address false 陽性/負片](defender-endpoint-false-positives-negatives.md)。

## <a name="exclude-website-from-network-protection-scope"></a>從網路保護範圍排除網站

若要允許封鎖的網站 (誤報) ，請將其 URL 新增至信任的 [網站清單](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)。 來自此清單的網頁資源略過網路保護檢查。

## <a name="collect-diagnostic-data-for-file-submissions"></a>收集診斷資料以取得檔提交

當您報告網路保護的問題時，系統會要求您收集並提交可供 Microsoft 支援人員和工程團隊使用的診斷資料，以協助疑難排解問題。

1. 開啟提升許可權的命令提示字元，並變更為 Windows Defender 目錄：

   ```console
   cd c:\program files\windows defender
   ```

2. 執行下列命令以產生診斷記錄：

   ```console
   mpcmdrun -getfiles
   ```

3. 將檔案附加到提交表單。 根據預設，診斷記錄會儲存在 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>解決 (E5 客戶之網路保護的連線問題) 

由於網路保護的執行環境，Microsoft 無法看到您的作業系統 proxy 設定。 在某些情況下，網路保護用戶端無法到達雲端服務。 若要解決網路保護的連線問題，請設定下列其中一個登錄機碼，讓網路防護知道 proxy 設定：

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

---或---


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

您可以使用 PowerShell、Microsoft 端點管理員或群組原則來設定登錄機碼。 以下是一些可協助的資源：
- [使用登錄機碼](/powershell/scripting/samples/working-with-registry-keys)
- [設定 Endpoint Protection 的自訂用戶端設定](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [使用群組原則設定來管理 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>另請參閱

- [網路保護](network-protection.md)
- [評估網路保護](evaluate-network-protection.md)
- [啟用網路保護](enable-network-protection.md)
- [在 Defender 中為端點處理誤報/負片](defender-endpoint-false-positives-negatives.md)
