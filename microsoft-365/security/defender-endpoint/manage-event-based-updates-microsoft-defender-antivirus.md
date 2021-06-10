---
title: 在特定事件之後套用 Microsoft Defender 防毒軟體更新
description: 管理在啟動或接收雲端傳送偵測報告之後，Microsoft Defender 防毒軟體套用安全性智慧更新的方式。
keywords: 更新、保護、強制更新、事件、啟動、檢查最近的通知
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 624e32bfebfce02021f1dcb1dbdde9446472239a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274697"
---
# <a name="manage-event-based-forced-updates"></a>管理事件型強制更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防毒軟體可讓您判斷是否 (應該在特定事件（例如啟動時）或從具備雲端功能的保護服務接收特定報告之後，) 發生更新。

## <a name="check-for-protection-updates-before-running-a-scan"></a>在執行掃描之前檢查保護更新

您可以使用 Microsoft Endpoint Configuration Manager、群組原則、PowerShell Cmdlet 及 WMI，強制 Microsoft Defender 防毒軟體在執行排程掃描之前先檢查及下載保護更新。

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>使用 Configuration Manager 檢查保護更新，然後再執行掃描

1. 在您的 Microsoft 端點管理員主控台上，開啟您想要變更的反惡意軟體原則 (按一下左側功能窗格中的 **[****資產和符合性**]，然後展開樹狀目錄  >  **Endpoint Protection**  >  **反惡意軟體原則**) 

2. 請移至 [**排程的掃描**] 區段，並在 **[是]****執行掃描之前，設定檢查是否有最新的安全性情報更新**。

3. 按一下 ****[確定]。

4. [照常部署更新的原則](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>使用群組原則檢查保護更新，然後再執行掃描

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。

3. 按一下 [ **原則** 然後是系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows**  >  **Microsoft Defender 防毒軟體**  >  **掃描** 的元件。

5. **在執行排程掃描之前，按兩下 [檢查最新的病毒和間諜軟體定義**]，然後將選項設定為 [**啟用**]。

6. 按一下 ****[確定]。

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>在執行掃描之前，使用 PowerShell Cmdlet 檢查保護更新

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/index)。

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>在執行掃描之前，使用 Windows 管理指令 (WMI) 檢查保護更新

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
CheckForSignaturesBeforeRunningScan
```

如需詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="check-for-protection-updates-on-startup"></a>在啟動時檢查保護更新

您可以使用群組原則，強制 Microsoft Defender 防毒軟體在機器啟動時，檢查及下載保護更新。

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。

3. 按一下 [ **原則** 然後是系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**。

5. 按兩下 **[在啟動時檢查最近的病毒和間諜軟體定義** ]，並將選項設定為 [ **啟用**]。 

6. 按一下 ****[確定]。

您也可以使用「群組原則」、「PowerShell」或「WMI」，設定 Microsoft Defender 防毒軟體在啟動時檢查是否有更新，甚至是不執行。

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Microsoft Defender 防毒軟體不存在時，使用群組原則下載更新

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 使用 **群組原則管理編輯器**，移至 [ **電腦** 設定]。

3. 按一下 [ **原則** 然後是系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**。

5. 按兩下 [ **啟動時啟動安全性智慧更新** ]，並將選項設定為 [ **啟用**]。

6. 按一下 ****[確定]。

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>在未出現 Microsoft Defender 防毒軟體時使用 PowerShell Cmdlet 下載更新

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

如需詳細資訊，請參閱[use PowerShell Cmdlet to manage Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/index) ，以取得如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊。

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>當 Microsoft Defender 防毒軟體不存在時，使用 Windows 管理指令 (WMI) 下載更新

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

如需詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>根據雲端提供的保護，允許特定變更的保護

Microsoft Defender AV 可根據雲端提供的保護，對其保護進行變更。 這類變更可能會發生在一般或排程的保護更新之外。

如果您已啟用雲端提供的保護，Microsoft Defender AV 會將可疑的檔案傳送至 Windows Defender 雲端。 如果雲端服務報告該檔案為惡意檔，且在最近的保護更新中偵測到該檔案，您可以使用群組原則來設定 Microsoft Defender AV，以自動接收該防護更新。 您也可以套用其他重要的保護更新。

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>使用群組原則，根據雲端提供的保護自動下載最近的更新

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。

3. 按一下 [ **原則** 然後是系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**。

5. 按兩下 [ **允許即時安全性智慧更新根據 MICROSOFT 地圖報告** ]，並將選項設定為 [ **啟用**]。 然後按一下 **[確定]**。

6. **允許通知以停用 MICROSOFT MAPS 的定義型報告** ，並將選項設定為 [ **啟用**]。 然後按一下 **[確定]**。
    
> [!NOTE]
> **允許通知若停用以定義為基礎的報表** ，可讓 Microsoft MAPS 停用這些已知導致誤報的定義。 您必須將電腦設定為加入 Microsoft MAPS，此功能才能運作。

## <a name="see-also"></a>另請參閱

- [部署 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理應下載及套用防護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [管理行動裝置和虛擬機器 (VM) 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)