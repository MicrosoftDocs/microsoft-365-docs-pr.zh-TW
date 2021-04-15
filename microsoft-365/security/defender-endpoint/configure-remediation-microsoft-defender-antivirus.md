---
title: 設定 Microsoft Defender 防病毒偵測的修正
description: 在偵測到威脅時，設定 Microsoft Defender 防毒軟體應執行的動作，以及隔離檔案應該在隔離資料夾中保留多久
keywords: 修正、修正、移除、威脅、隔離、掃描、還原
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98bc079bcfd772ada52d699d5f873a187d4ab4c1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765056"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>設定 Microsoft Defender 防病毒偵測的修正

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

當 Microsoft Defender 防病毒執行掃描時，它會嘗試修正或移除所偵測到的威脅。 您可以設定 Microsoft Defender 防毒軟體應如何解決特定威脅、是否應該在修正之前建立還原點，以及何時應移除威脅。

本文說明如何使用群組原則來設定這些設定，但是您也可以使用 [Microsoft 端點 Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) 和 [microsoft Intune](/intune/device-restrictions-configure)。 

您也可以使用[ `Set-MpPreference` PowerShell Cmdlet](/powershell/module/defender/set-mppreference)或[ `MSFT_MpPreference` WMI 類別](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)來設定這些設定。

## <a name="configure-remediation-options"></a>設定修正選項

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。

3. 將樹狀目錄展開為  >  **microsoft Defender 防毒軟體** 的 Windows 元件。 

4. 使用下表，選取位置，然後視需要編輯原則。 

5. 選取 **[確定]**。

|位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|:---|:---|:---|:---|
|掃描 | 建立系統還原點 | 在嘗試清除或掃描之前每天都會建立系統還原點 | 已停用|
|掃描 | 開啟從掃描歷程記錄資料夾中移除專案 | 指定在掃描歷程記錄中應該保留的專案數天數 | 30 天 |
|根 | 關閉常式修復 | 您可以指定 Microsoft Defender 防毒程式是否會自動 remediates 威脅，或者是否應要求端點使用者執行的動作。 | 停用 (威脅會自動修正)  |
|隔離 | 設定從隔離資料夾中移除專案 | 指定專案應該保留在隔離之前多少天之後才能被移除 | 90 天 |
|威脅 | 指定偵測到預設動作時不應該採取的威脅警示層級 | Microsoft Defender 防病毒偵測到的每個威脅都會被指派威脅層級 (低、中、高或嚴重) 。 您可以使用此設定來定義每個威脅層級的所有威脅應如何補救 (隔離、移除或忽略)  | 不適用 |
|威脅 | 指定當偵測到預設動作時不應該採取的威脅 | 指定應該修正 (使用威脅識別碼的特定威脅) 。 您可以指定是否應該隔離、移除或忽略特定威脅。 | 不適用 |

> [!IMPORTANT]
> Microsoft Defender 防毒軟體會根據許多因素偵測和 remediates 檔案。 在某些情況下，完成修復需要重新開機。 即使後來判斷出的偵測是誤報，也必須完成重新開機，以確保已完成所有其他的修復步驟。
>
> 如果您是根據誤報將檔案隔離的 Microsoft Defender 防病毒，您可以在裝置重新開機後，從隔離區還原檔案。 請參閱 [在 Microsoft Defender 防毒軟體中還原隔離的](restore-quarantined-files-microsoft-defender-antivirus.md)檔案。
> 
> 為了避免未來發生此問題，您可以從掃描中排除檔案。 請參閱 [設定及驗證 Microsoft Defender 防病毒掃描的排除](configure-exclusions-microsoft-defender-antivirus.md)專案。

另請參閱 [設定修正-必要的定時完整 Microsoft Defender 防病毒掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) ，以取得更多修正相關設定。

## <a name="see-also"></a>另請參閱

- [設定 Microsoft Defender 防病毒掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [設定排定的 Microsoft Defender 防病毒掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [設定及執行隨選 Microsoft Defender 防毒程式掃描](run-scan-microsoft-defender-antivirus.md)
- [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md)
- [設定使用者的 Microsoft Defender 防毒程式互動](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [自訂、啟動和審閱 Microsoft Defender 防病毒掃描和修正的結果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)