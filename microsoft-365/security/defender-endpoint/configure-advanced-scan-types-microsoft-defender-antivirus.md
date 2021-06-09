---
title: 設定 Microsoft Defender 防毒軟體的掃描選項
description: 您可以設定 Microsoft Defender AV 掃描電子郵件儲存檔案、備份或重新分析點、網路檔，以及封存的檔案 (例如 .zip 檔案) 。
keywords: 高級掃描、掃描、電子郵件、封存、zip、rar、封存、重新分析掃描
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 34f423222068236271afdda13afb95cffa58b709
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683808"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>設定 Microsoft Defender 防毒軟體掃描選項

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>使用 Microsoft Intune 設定掃描選項

請參閱下列資源： 

- [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure) 
- [在 Intune 中 Microsoft Defender 防毒軟體 Windows 10 裝置限制設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>使用 Microsoft 端點管理員設定掃描選項

請參閱 [如何建立及部署反惡意程式碼原則：掃描設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。

## <a name="use-group-policy-to-configure-scanning-options"></a>使用群組原則設定掃描選項

1. 在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

3. 在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統****管理範本**]。

4. 展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**，然後選取位置 (參閱本文) 的 [設定和位置](#settings-and-locations)。

5. 編輯 policy 物件。 

6. 按一下 **[確定]**，然後對任何其他設定重複此步驟。

### <a name="settings-and-locations"></a>設定和位置

| 原則專案和位置 | 預設設定 (（如果未設定）)  | `Set-MpPreference`Class 的 PowerShell 參數或 WMI 屬性 `MSFT_MpPreference` |
|---|---|---|
| 電子郵件掃描 <p> **掃描**  > **開啟電子郵件掃描**<p>請參閱本文 (的 [電子郵件掃描限制](#email-scanning-limitations))  | 停用 | `-DisableEmailScanning` |
|掃描重新 [分析點](/windows/win32/fileio/reparse-points) <p> **掃描**  > **開啟重新分析點掃描** | 停用 | 無 <p>請參閱重新 [分析點](/windows/win32/fileio/reparse-points)  |
| 掃描對應的網路磁碟機 <p> **掃描**  > **在對應的網路磁碟機上執行完整掃描** | 停用 | `-DisableScanningMappedNetworkDrivesForFullScan`|
| 掃描封存檔案 (例如 .zip 或 .rar 檔) 。  <p> **掃描**  > **掃描封存檔案** | 啟用 | `-DisableArchiveScanning` <p>[副檔名排除清單](configure-extension-file-exclusions-microsoft-defender-antivirus.md)會優先于此設定。|
| 掃描網路上的檔案 <p> **掃描**  > **掃描網路檔** | 停用 | `-DisableScanningNetworkFiles` |
| 掃描打包的可執行檔 <p> **掃描**  > **掃描打包的可執行檔** | 啟用 | 無 |
| 僅在完整掃描期間掃描抽取式磁碟磁碟機 <p> **掃描**  > **掃描可移除的磁片磁碟機** | 停用 | `-DisableRemovableDriveScanning` |
| 指定要掃描之封存資料夾內的子資料夾層級 <p>**掃描**  > **指定掃描封存檔案的最大深度** | 0 | 無法使用 |
| 在掃描期間，指定 CPU 負載 (為百分比) 。 <p> **掃描**  > **指定掃描期間 CPU 使用率的最大百分比** | 50 |  `-ScanAvgCPULoadFactor` <p>**附注**： CPU 負載上限不是硬性限制，但是掃描引擎不會超過平均平均上限的指導。 手動執行掃描將會略過此設定，而不需要任何 CPU 限制即可執行。 |
| 指定應掃描之封存檔的大小上限 (以 kb 為單位）) 。 <p> **掃描**  > **指定要掃描的封存檔案大小上限** | 無限制 | 無 <p>預設值0不會套用任何限制 |
| 設定排程掃描的低 CPU 優先順序 <p> **掃描**  > 設定 **排程掃描的低 CPU 優先順序** | 停用 | 無 |
 
> [!NOTE]
> 如果即時保護已開啟，則會先掃描檔案，再加以存取和執行。 掃描範圍包括所有檔案，包括裝入的卸除式媒體（例如 USB 磁片磁碟機）上的檔案。 如果執行掃描的裝置已開啟即時保護或開啟時保護，則掃描也會包含網路共用。

## <a name="use-powershell-to-configure-scanning-options"></a>使用 PowerShell 設定掃描選項

請參閱下列資源：

- [使用 PowerShell Cmdlet 管理 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender Cmdlet](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>使用 WMI 設定掃描選項

請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="email-scanning-limitations"></a>電子郵件掃描限制

電子郵件掃描可讓 Outlook 和其他郵件客戶程式使用的電子郵件檔案掃描時，進行隨選及排程的掃描。 也會掃描電子郵件 (中的內嵌物件，例如附件及已封存的檔案) 。 您可以掃描和修正下列檔案格式類型：

- Dbx
- MBX
- Mime

Outlook 2003 或舊版 (使用的 PST 檔案，封存類型設為非 unicode) 也會加以掃描，但是 Microsoft Defender 防毒軟體無法修正在 PST 檔案中偵測到的威脅。

如果 Microsoft Defender 防毒軟體偵測到電子郵件中的威脅，它會顯示下列資訊，協助您識別遭到損害的電子郵件，因此您可以手動修正威脅：

- 電子郵件主旨
- 附件名稱

## <a name="see-also"></a>另請參閱

- [自訂、啟動及審閱 Microsoft Defender 防毒軟體掃描和修正的結果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [設定和執行隨選 Microsoft Defender 防毒軟體掃描](run-scan-microsoft-defender-antivirus.md)
- [設定排定的 Microsoft Defender 防毒軟體掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
