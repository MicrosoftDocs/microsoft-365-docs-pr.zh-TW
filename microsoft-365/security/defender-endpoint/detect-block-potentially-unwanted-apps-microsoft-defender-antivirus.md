---
title: 使用 Microsoft Defender 防毒軟體封鎖可能有害的應用程式
description: 啟用可能有害的應用程式 (PUA) 防病毒功能，以封鎖廣告軟體等不需要的軟體。
keywords: pua、啟用、不想要的軟體、有害的應用程式、廣告軟體、瀏覽器工具列、偵測、封鎖、Microsoft Defender 防毒程式
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8350db473580fd4d1728c3473742da5b63196c52
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893574"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>偵測並封鎖可能有害的應用程式

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

可能有害的應用程式 (PUA) 是一種軟體類別，可導致您的機器執行緩慢、顯示未預期的廣告或最壞的軟體安裝可能是意外或不需要的其他軟體。 PUA 不會被視為病毒、惡意程式碼或其他類型的威脅，但它可能會對對端點效能或使用造成不良影響的端點執行動作。 除了某些不良行為， *PUA* 字詞也可以參考具有不良信譽的應用程式，因為它是由 Microsoft Defender for Endpoint 所評估。

以下為一些範例：

- 顯示廣告或促銷的 **廣告軟體**，包含將廣告插入網頁的軟體。
- **搭售軟體** ，以安裝不是由相同實體進行數位簽署的其他軟體。 此外，也就是提供安裝其他符合 PUA 之軟體的軟體。
- **規避軟體** ，會積極企圖規避安全性產品的偵測，包括在安全性產品存在時，行為會不同的軟體。

> [!TIP]
> 如需更多範例，以及我們用於標示應用程式以特別注意安全性功能的準則，請參閱 [Microsoft 如何識別惡意程式碼和潛在的有害應用程式](/windows/security/threat-protection/intelligence/criteria)。

可能有害的應用程式可能會增加網路受到實際惡意程式碼感染的風險，使惡意程式碼感染難於識別，或浪費 IT 資源以加以清除。 Windows 10、Windows Server 2019 及 Windows Server 2016 都支援 PUA 保護。 在 Windows 10 (版本2004和更新版本) 中，Microsoft Defender 防毒程式預設會封鎖視為企業 (E5) 裝置的 PUA 的應用程式。

## <a name="microsoft-edge"></a>Microsoft Edge

[新的 Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)會以 Chromium 為基礎，封鎖可能有害的應用程式下載和相關聯的資源 URLs。 這項功能是透過 [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)所提供。

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>在以 Chromium 為基礎的 Microsoft Edge 中啟用 PUA 保護

雖然 Microsoft Edge 中可能有害的應用程式保護 (以 Chromium 為基礎的版本 80.0.361.50) 會預設為關閉，但是可以從瀏覽器中輕鬆地開啟此功能。

1. 在您的 Edge browser 中，選取省略號，然後選擇 [ **設定**]。

2. 選取 [ **隱私權]、[搜尋] 及 [服務**]。

3. 在 [ **安全性** ] 區段中，開啟 [ **封鎖可能有害的應用程式**]。

> [!TIP]
> 如果您正在執行 Microsoft Edge (以 Chromium 為基礎的) ，您可以在其中一個 [Microsoft Defender SmartScreen 示範頁面](https://demo.smartscreen.msft.net/)上進行測試，以安全地探索 PUA 保護的 URL 封鎖功能。

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a>使用 Microsoft Defender SmartScreen 封鎖 URLs

在開啟 PUA 保護的 Chromium 型 Edge 中，Microsoft Defender SmartScreen 會從 PUA 關聯的 URLs 中保護您。

安全性管理員可以 [設定](/DeployEdge/configure-microsoft-edge) microsoft Edge 和 Microsoft Defender SmartScreen 如何共同運作，以保護使用者群組免受 PUA 關聯的 URLs。 有幾個 [群組原則設定](/DeployEdge/microsoft-edge-policies#smartscreen-settings) 會明確用於 Microsoft Defender SmartScreen，包括 [一個用於封鎖 PUA 的](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)群組原則設定。 此外，系統管理員可以使用「群組原則」設定將 microsoft defender SmartScreen 開啟或關閉，以整體 [設定 Microsoft defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) 。

雖然 Microsoft Defender for Endpoint 會根據 Microsoft 所管理的資料集，自行 blocklist，您可以根據您自己的威脅智慧自訂此清單。 如果您在 Microsoft Defender for Endpoint 入口網站中 [建立及管理指示器](manage-indicators.md) ，microsoft defender SmartScreen 會尊重新設定。

## <a name="microsoft-defender-antivirus"></a>Microsoft Defender 防病毒

Microsoft Defender 防毒軟體中可能有害的 application (PUA) protection 功能可偵測並封鎖您網路中端點的 PUAs。

> [!NOTE]
> 這項功能可在 Windows 10、Windows Server 2019 及 Windows Server 2016 中取得。

Microsoft Defender 防病毒封鎖偵測到 PUA 檔案，以及任何嘗試下載、移動、執行或安裝這些檔案。 封鎖的 PUA 檔案會移至隔離區。 在端點上偵測到 PUA 檔案時， [除非已停用通知，否則](configure-notifications-microsoft-defender-antivirus.md) Microsoft Defender 防病毒會傳送通知給使用者 (，) 與其他威脅偵測的格式相同。 通知會 `PUA:` 以指示其內容的開頭。

通知會出現在 [Windows 安全性應用程式內的一般隔離清單](microsoft-defender-security-center-antivirus.md)中。

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>設定 Microsoft Defender 防毒軟體中的 PUA 保護

您可以使用 [Microsoft Intune](/mem/intune/protect/device-protect)、 [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection)、 [群組原則](/azure/active-directory-domain-services/manage-group-policy)或透過 [PowerShell Cmdlet](/powershell/module/defender/?preserve-view=true&view=win10-ps)來啟用 PUA 保護。

您也可以在稽核模式中使用 PUA 保護，以偵測可能有害的應用程式，而不加以封鎖。 在 Windows 事件記錄檔中捕獲偵測。

> [!TIP]
> 在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) 流覽 Microsoft Defender for Endpoint 示範網站，以確認該功能是否正常運作，並將其顯示在 [動作] 中。

如果貴公司正在進行內部軟體安全性符合性檢查，且您想要避免任何誤報，請 PUA protection 模式中的 [保護] 功能非常有用。

#### <a name="use-intune-to-configure-pua-protection"></a>使用 Intune 設定 PUA 保護

如需詳細資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure) 及 [Intune 中 Windows 10 的 Microsoft Defender 防病毒裝置限制設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 。

#### <a name="use-configuration-manager-to-configure-pua-protection"></a>使用 Configuration Manager 來設定 PUA 保護

PUA 目前的分支) 中的 Microsoft 端點管理員 (預設會啟用 [保護]。

請參閱 [如何建立及部署反惡意程式碼原則：排程的掃描設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) ，以取得設定 Microsoft 端點管理員 (目前分支) 的詳細資料。

如需 System Center 2012 Configuration Manager，請參閱 [如何在 Configuration manager 中為 Endpoint Protection 部署可能不需要的應用程式保護原則](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。

> [!NOTE]
> PUA 由 Microsoft Defender 防病毒封鎖的事件會在 Windows 事件檢視器中報告，而不會在 Microsoft 端點 Configuration Manager 中報告。

#### <a name="use-group-policy-to-configure-pua-protection"></a>使用群組原則來設定 PUA 保護

1. 下載及安裝 [Windows 10 十月 2020 Update (20H2) 的系統管理範本 ( admx) ](https://www.microsoft.com/download/details.aspx?id=102157)

2. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。

3. 選取您要設定的群組原則物件，然後選擇 [ **編輯**]。

4. 在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後選取 [**系統****管理範本**]。

5. 將樹狀目錄展開為  >  **microsoft Defender 防毒軟體** 的 Windows 元件。

6. 按兩下 [ **設定可能有害之應用程式的偵測**]。

7. 選取 [ **啟用** ] 以啟用 PUA 保護。

8. 在 [ **選項**] 中，選取 [ **封鎖** ] 以封鎖可能不需要的應用程式，或選取 [ **核查模式]** 以測試設定在您的環境中的運作 選取 [確定]。

9. 像往常一樣部署您的群組原則物件。

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>使用 PowerShell Cmdlet 來設定 PUA 保護

##### <a name="to-enable-pua-protection"></a>啟用 PUA 保護

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

設定此 Cmdlet 的值， `Enabled` 開啟功能（如果已停用）。

##### <a name="to-set-pua-protection-to-audit-mode"></a>將 PUA 防護設定為稽核模式

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

設定 `AuditMode` 偵測 PUAs 但不加以封鎖。

##### <a name="to-disable-pua-protection"></a>停用 PUA 保護

建議您保持 PUA 保護開啟狀態。 不過，您可以使用下列 Cmdlet 來關閉它：

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

設定此 Cmdlet 的值， `Disabled` 關閉功能（如果已啟用）。

如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/index) 。

## <a name="view-pua-events"></a>View PUA 事件

PUA 事件會在 Windows 事件檢視器中報告，但不會在 Microsoft 端點管理員或 Intune 中報告。 您也可以使用 `Get-MpThreat` Cmdlet 來查看 Microsoft Defender 防病毒處理的威脅。 以下為範例：

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

您可以開啟電子郵件通知，以接收 PUA 偵測的郵件。

如需查看 Microsoft Defender 防病毒事件的詳細資訊，請參閱 [事件 IDs 疑難排解](troubleshoot-microsoft-defender-antivirus.md) 。 PUA 事件會記錄在事件識別碼 **1160** 底下。

如果您是使用 Microsoft Defender for Endpoint，您可以使用高級搜尋查詢來查看 PUA 事件。 以下是範例查詢：

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

## <a name="excluding-files"></a>排除檔案

有時，PUA 保護會錯誤地封鎖檔案，或需要 PUA 的功能才能完成任務。 在這些情況下，您可以將檔案新增至排除清單。

如需詳細資訊，請參閱 [根據副檔名和資料夾位置設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

## <a name="see-also"></a>另請參閱

- [新一代保護](microsoft-defender-antivirus-in-windows-10.md)
- [設定行為、啟發學習法和即時保護](configure-protection-features-microsoft-defender-antivirus.md)