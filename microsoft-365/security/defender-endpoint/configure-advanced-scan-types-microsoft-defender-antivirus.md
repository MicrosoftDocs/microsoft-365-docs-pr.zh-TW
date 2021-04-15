---
title: 設定 Microsoft Defender AV 的掃描選項
description: 您可以設定 Microsoft Defender AV 掃描電子郵件儲存檔案、備份或重新分析點、網路檔案，以及封存的檔案 (例如 .zip 檔案) 。
keywords: 高級掃描、掃描、電子郵件、封存、zip、rar、封存、重新分析掃描
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 72d5024446e56cc7fa1d94a7b9402cbe898db2a8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764852"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>設定 Microsoft Defender 防病毒掃描選項

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>使用 Microsoft Intune 設定掃描選項

如需詳細資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure) 及 [Intune 中 Windows 10 的 Microsoft Defender 防病毒裝置限制設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 。

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>使用 Microsoft 端點管理員設定掃描選項

請參閱 [如何建立及部署反惡意程式碼原則：掃描設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) ，以取得設定 Microsoft 端點管理員 (目前分支) 的詳細資料。

## <a name="use-group-policy-to-configure-scanning-options"></a>使用群組原則設定掃描選項

若要設定下表所述的群組原則設定：

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統****管理範本**]。

3. 在 [ **Microsoft Defender 防病毒 >** ] 的 [Windows 元件] 中，展開樹狀目錄，然後展開下表中所指定的 **位置** 。

4. 按兩下下表中所指定的原則 **設定** ，並將選項設定為您想要的設定。 按一下 **[確定]**，然後對任何其他設定重複此步驟。

描述 | 位置和設定 | 預設設定 (（如果未設定）)  | `Set-MpPreference`Class 的 PowerShell 參數或 WMI 屬性 `MSFT_MpPreference`
---|---|---|---
電子郵件掃描請參閱 [電子郵件掃描限制](#ref1)| 掃描 > 開啟電子郵件掃描 | 已停用 | `-DisableEmailScanning`
掃描重新 [分析點](/windows/win32/fileio/reparse-points) | 掃描 > 開啟重新分析點掃描 | 已停用 | 無
掃描對應的網路磁碟機 | 掃描 > 在對應的網路磁碟機上執行完整掃描 | 已停用 | `-DisableScanningMappedNetworkDrivesForFullScan`
 掃描封存檔案 (例如 .zip 或 rar 檔案) 。 [副檔名排除清單](configure-extension-file-exclusions-microsoft-defender-antivirus.md)會優先于此設定。 | 掃描 > 掃描封存檔案 | Enabled | `-DisableArchiveScanning`
掃描網路上的檔案 | 掃描 > 掃描網路檔 | 已停用 | `-DisableScanningNetworkFiles`
掃描打包的可執行檔 | 掃描 > 掃描打包的可執行檔 | Enabled | 無
僅在完整掃描期間掃描抽取式磁碟磁碟機 | 掃描 > 掃描可移除磁片磁碟機 | 已停用 | `-DisableRemovableDriveScanning`
指定要掃描之封存資料夾內的子資料夾層級 | 掃描 > 指定掃描封存檔案的最大深度 | 0 | 無法使用
 在掃描期間，指定 CPU 負載 (為百分比) 。 注意：這不是硬性限制，但掃描引擎的指導方針不會超過平均這一上限。 | 掃描 > 指定掃描期間 CPU 使用率的最大百分比 | 50 |  `-ScanAvgCPULoadFactor`
 指定應掃描之封存檔的大小上限 (以 kb 為單位）) 。 預設值為 **0**，套用無限制 | 掃描 > 指定要掃描的封存檔案大小上限 | 無限制 | 無
 設定排程掃描的低 CPU 優先順序 | 掃描 > 設定排程掃描的低 CPU 優先順序 | 已停用 | 無
 
> [!NOTE]
> 如果即時保護已開啟，則會先掃描檔案，再加以存取和執行。 掃描範圍包括所有檔案，包括裝入的卸除式媒體（例如 USB 磁片磁碟機）上的檔案。 如果執行掃描的裝置已開啟即時保護或開啟時保護，則掃描也會包含網路共用。

## <a name="use-powershell-to-configure-scanning-options"></a>使用 PowerShell 設定掃描選項

如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [管理含 PowerShell Cmdlet 的 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlet](/powershell/module/defender/) 。

## <a name="use-wmi-to-configure-scanning-options"></a>使用 WMI 設定掃描選項

如需使用 WMI 類別，請參閱 [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>電子郵件掃描限制

電子郵件掃描可讓 Outlook 和其他郵件用戶端在按需求和排程掃描期間使用的電子郵件檔案進行掃描。 也會掃描電子郵件檔案中的內嵌物件 (例如附件及封存的檔案) 。 您可以掃描和修正下列檔案格式類型：

- Dbx
- MBX
- Mime

Outlook 2003 或舊版 (所使用的 PST 檔案，其封存類型設為非 unicode) 也會進行掃描，但是 Windows Defender 無法修正在 PST 檔案中偵測到的威脅。

如果 Microsoft Defender 防毒程式偵測到電子郵件內的威脅，它會顯示下列資訊以協助您識別遭到損害的電子郵件，因此您可以手動修正威脅：

- 電子郵件主旨
- 附件名稱

## <a name="related-topics"></a>相關主題

- [自訂、啟動和審閱 Microsoft Defender 防病毒掃描和修正的結果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [設定及執行隨選 Microsoft Defender 防毒程式掃描](run-scan-microsoft-defender-antivirus.md)
- [設定排定的 Microsoft Defender 防病毒掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)