---
title: 將 Microsoft Defender AV 保護更新套用至日期結束端點
description: 定義何時及如何針對尚未更新的端點套用更新。
keywords: 更新、保護、過期、過期、舊、追趕
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275057"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>管理 Microsoft Defender 防毒軟體更新和掃描已過時的端點

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防毒軟體可讓您定義端點可以避免更新的時間長短，或在需要更新及掃描自身之前所能錯過的掃描數目。 這在裝置通常不會連接到公司或外部網路或每日未使用的裝置的環境中特別有用。

例如，使用特定電腦的員工會在中斷三天，而不會在該時間登入其電腦。

當使用者回到工作並登入其電腦時，Microsoft Defender 防毒軟體會立即檢查並下載最新的保護更新，並執行掃描。

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>針對尚未更新的端點，設定追趕防護更新

如果 Microsoft Defender 防毒軟體在指定的期間內沒有下載保護更新，您可以將其設定為在下次登入時自動檢查和下載最新的更新。 如果您已 [在啟動時以全域方式停用自動更新下載](manage-event-based-updates-microsoft-defender-antivirus.md)，這會很有用。

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>使用 Configuration Manager 來設定追趕保護更新

1.  在您的 Microsoft 端點管理員主控台上，開啟您想要變更的反惡意軟體原則 (按一下左側功能窗格中的 **[****資產和符合性**]，然後展開樹狀目錄  >  **Endpoint Protection**  >  **反惡意軟體原則**) 

2.  移至 [ **安全性情報更新** ] 區段，然後設定下列設定：

    1. **如果用戶端電腦離線時，有兩個以上的連續排程更新** 為 **[是]**，則設定強制安全性智慧更新。
    2. **如果是使用 Configuration manager 做為安全性智慧更新的來源**，請指定設定管理員所傳遞的保護更新應視為過期的時間。 這會根據定義的 [回退來源順序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)，使下一個更新位置成為使用。

3. 按一下 ****[確定]。

4.  [照常部署更新的原則](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>使用群組原則來啟用及設定追趕更新功能

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

3. 按一下 [ **原則** 然後是系統 **管理範本**]。

4. 展開樹狀目錄， **Windows 元件 > Microsoft Defender 防毒軟體 > 簽名更新**。

5. 按兩下 [ **定義需要彌補安全性的智慧更新之前的天數** ] 設定，並將此選項設定為 [ **啟用**]。 輸入您想要 Microsoft Defender AV 檢查的天數，並下載最新的保護更新。

6. 按一下 ****[確定]。

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>使用 PowerShell Cmdlet 來設定追趕防護更新

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>使用 Windows 管理指令 (WMI) 設定追趕防護更新

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
SignatureUpdateCatchupInterval
```

如需詳細資訊及允許的參數，請參閱下列各項：
- [Windows DefenderWMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>設定將保護報告為過期前的天數

您也可以指定會將 Microsoft Defender 防毒軟體保護視為舊或過期的天數。 在指定天數後，用戶端會將其本身報告為過期，並對電腦使用者顯示錯誤。 這可能也會導致 Microsoft Defender 防毒軟體嘗試根據定義的[回退來源順序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)) 從其他來源 (下載更新，例如，將 WSUS 或 Microsoft update 設定為第一個來源後，使用 MMPC 做為次要來源。

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>使用群組原則指定保護視為過期前的天數

1.  在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

3.  在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

4.  按一下 [ **原則** 然後是系統 **管理範本**]。

5.  展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 >** 簽章更新，並設定下列設定：

    1.  按兩下 **[定義間諜軟體定義視為過時的天數** ]，並將選項設定為 [ **啟用**]。 輸入您想要 Microsoft Defender AV 將間諜軟體安全性情報視為過期的天數。

    2. 按一下 ****[確定]。

    3.  按兩下 **[定義病毒定義視為過時的天數** ]，並將選項設定為 [ **啟用**]。 輸入您想要讓 Microsoft Defender AV 將病毒安全性情報視為過期的天數。

    4. 按一下 ****[確定]。


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>針對尚未掃描的端點，設定追趕掃描

您可以在 Microsoft Defender 防毒軟體會強制進行掃描之前，設定可錯過的連續排程掃描數目。

啟用此功能的程式為：

1. 設定至少一個排程掃描 (請參閱 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主題) 。
2. 啟用 [追趕掃描] 功能。
3. 定義在進行追趕掃描之前可略過的掃描數目。

這項功能可同時啟用完整和快速掃描。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>使用群組原則來啟用及設定追趕掃描功能

1.  確定您已設定至少一個排程掃描。

2.  在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

3.  在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

4.  按一下 [ **原則** 然後是系統 **管理範本**]。

5.  展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 掃描** 及設定下列設定：

    1.  如果您已設定排程快速掃描，請按兩下 [ **開啟追趕快速掃描** ] 設定，並將選項設定為 [ **啟用**]。 
    2. 如果您已設定排程完整掃描，請按兩下 [ **開啟追趕完整掃描** ] 設定，並將選項設定為 [ **啟用**]。 按一下 ****[確定]。
    3. 按兩下 [ **定義強制進行追趕掃描的天數之後的天數** ] 設定，並將選項設定為 [ **啟用**]。 
    4. 輸入當使用者下一次登入電腦時，系統會自動執行掃描之前，可錯過的掃描數目。 所執行的掃描類型是由 **指定用於排程掃描的掃描類型** 所決定 (請參閱 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主題) 。 按一下 ****[確定]。

> [!NOTE]
> 群組原則設定標題是指天數。 不過，此設定會套用至執行追趕掃描之前 (天數) 中的掃描數目。

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>使用 PowerShell Cmdlet 來設定追趕掃描

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet to manage Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>使用 Windows 管理指令 (WMI) 設定追趕掃描

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

如需詳細資訊及允許的參數，請參閱下列各項：
- [Windows DefenderWMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>使用 Configuration Manager 來設定追趕掃描

1.  在您的 Microsoft 端點管理員主控台上，開啟您想要變更的反惡意軟體原則 (按一下左側功能窗格中的 **[****資產和符合性**]，然後展開樹狀目錄  >  **Endpoint Protection**  >  **反惡意軟體原則**) 

2.  移至 [ **排程掃描** ] 區段，並在 **用戶端電腦離線時，強制掃描選取的掃描類型** ... 為 **[是]**。 

3. 按一下 ****[確定]。

4.  [照常部署更新的原則](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

## <a name="related-articles"></a>相關文章

- [部署 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理應下載及套用防護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [管理事件型強制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
- [管理行動裝置和虛擬機器 (VM) 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)