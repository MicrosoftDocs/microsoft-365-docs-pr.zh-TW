---
title: 使用 MMicrosoft Defender 防毒軟體封鎖潛在的垃圾應用程式
description: 啟用潛在的垃圾應用程式（PUA）防毒功能封鎖垃圾軟體，例如廣告軟體。
keywords: PUA，啟用，垃圾軟體，垃圾應用程式，廣告軟體，瀏覽器工具列，偵測，封鎖，Windows Defender 防毒軟體
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: mimilone, julih
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/02/2021
ms.openlocfilehash: d7f411c81e839d3929d4aa1a52fda29399c59dca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772374"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>偵測並封鎖潛在的垃圾應用程式

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

潛在的垃圾應用程式（PUA）是一類軟體，可能導致您的機器執行速度緩慢、顯示非預期的廣告、或者最壞的情況是安裝其他非預期或不想要的軟體。 PUA 並非病毒、惡意軟體或其他類型的威脅，但它可能在端點上執行會對端點效能或使用產生不良影響的動作。 由於某些不良行為，經由 Microsoft Defender 進階威脅防護進行評估，術語 *PUA* 也可以指聲譽不佳的應用程式。

範例如下：

- 用於顯示廣告或促銷的 **廣告軟體**，包括將廣告插入網頁的軟體。
- 用於安裝未由同一實體進行數位簽章的其他軟體的 **統合軟體**。 另外，用於安裝其他符合 PUA 要求的軟體的軟體。
- 積極嘗試逃避安全性產品偵測的 **逃避軟體**，包括在有安全性產品的情況下，行為會不同的軟體。

> [!TIP]
> 若需要更多範例以及關於我們用來標籤應用程式以從安全性功能中特別注意的準則的討論，請參閱 [Microsoft 如何識別惡意軟體和潛在的垃圾應用程式](/windows/security/threat-protection/intelligence/criteria)。

潛在的垃圾應用程式可能會增加網路被實際惡意軟體感染的風險、使惡意軟體感染難以識別，或者浪費 IT 資源來清理它們。 Windows 10、Windows Server 2019 和 Windows Server 2016　均支援 PUA 保護。 在 Windows 10 (2004 及更新版本) 的預設情況下，Microsoft Defender 防毒軟體會封鎖被視為企業 (E5) 裝置 PUA 的應用程式。

## <a name="microsoft-edge"></a>Microsoft Edge

基於 Chromium 的 [新 Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea) 可以封鎖潛在的垃圾應用程式下載和相關的資源 URL。 透過 [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 提供此功能。

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>在基於 Chromium 的 Microsoft Edge 中啟用 PUA 保護

儘管 Microsoft Edge (基於 Chromium ,版本 80.0.361.50) 中的潛在的垃圾應用程式保護預設為關閉狀態，但可以輕鬆地從瀏覽器中開啟它。

1. 在您的 Edge 瀏覽器中，選取省略符號，然後選擇 **[設定]**。

2. 選取 **隱私、搜尋和服務**。

3. 在 **[安全性]** 章節下，開啟 **[封鎖潛在的垃圾應用程式]**。

> [!TIP]
> 如果您在執行 Microsoft Edge (基於 Chromium)，透過在其中一個 [[Microsoft Defender SmartScreen 示範頁面]](https://demo.smartscreen.msft.net/) 進行測試，您可以安全地探索 PUA 保護的 URL 封鎖功能。

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>使用 Microsoft Defender SmartScreen 封鎖 URL

在啟用了 PUA 保護的基於Chromium 的 Edge 中，Microsoft Defender SmartScreen 可以保護您免受 PUA 關聯的 URL 的侵害。

安全性管理員可以 [設定](/DeployEdge/configure-microsoft-edge) Microsoft Edge 和 Microsoft Defender SmartScreen 如何共同工作，以保護使用者群組免受與PUA 相關的 URL 的侵害。 有幾種明確適用於 Microsoft Defender SmartScreen 的 [群組原則設定](/DeployEdge/microsoft-edge-policies#smartscreen-settings)，其中包括一種 [用於封鎖 PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled) 的原則設定。 此外，使用群組原則設定開啟或關閉 Microsoft Defender SmartScreen，管理員可以整體 [設定 Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)。

雖然 Microsoft Defender 進階威脅防護根據 Microsoft 管理的資料集有自己的封鎖清單，您可以根據自己的威脅情報來自訂這個清單。 如果您在 Microsoft Defender 進階威脅防護入口網站中 [建立和管理指標](manage-indicators.md)，則 Microsoft Defender SmartScreen 將遵守新設定。

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Microsoft Defender 防毒軟體和 PUA 保護

Microsoft Defender 防毒軟體中的潛在的垃圾應用程式 (PUA) 保護功能可以偵測並封鎖網路中端點上的 PUA。

> [!NOTE]
> Windows 10、Windows Server 2019 和 Windows Server 2016　均支援該功能。

Microsoft Defender 防毒軟體封鎖偵測到的 PUA 檔案以及任和下載、移動、執行或安裝它們的嘗試。 已封鎖的 PUA 檔案會被移至隔離。 當在端點上偵測到 PUA 檔案時，Microsoft Defender 防毒軟體會以與其他威脅偵測相同的格式，向使用者發送通知 ([除非已停用通知](configure-notifications-microsoft-defender-antivirus.md))。 通知以 `PUA:` 開頭以表示其內容。

通知將顯示在慣例的 [Windows 安全性應用程式隔離清單](microsoft-defender-security-center-antivirus.md)中。

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>在 Microsoft Defender 防毒軟體設定 PUA 保護

您可以使用 [Microsoft Intune](/mem/intune/protect/device-protect)、[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection)、[群組原則](/azure/active-directory-domain-services/manage-group-policy)，或者透過 [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps) 來啟用 PUA 保護。

您也可以在稽核模式使用 PUA 保護以偵測潛在的垃圾應用程式而不封鎖它們。 偵測會被 Windows 事件記錄擷取。

> [!TIP]
> 請造訪 Microsoft Defender 進階威脅防護的示範網站: [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep)，以確認該功能正常運行，並看它如何運作。

如果貴公司正在進行內部軟體安全性合規性檢查，並且希望避免任何誤報，稽核模式的 PUA 保護很實用。

### <a name="use-intune-to-configure-pua-protection"></a>使用 Intune 來設定 PUA 保護

請參閱 [《在 Microsoft Intune 中設定裝置限制設定》](/intune/device-restrictions-configure) 及 [《Windows 10 中 Intune 的 Microsoft Defender 防毒軟體裝置限制設定》](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 了解詳情。

### <a name="use-configuration-manager-to-configure-pua-protection"></a>使用 Configuration Manager 來設定 PUA 保護

Microsoft 端點管理員 (目前分支) 中會預設啟用 PUA 保護。

請參閱 [《如何建立和部署反惡意程式碼原則: 亦排程的掃描設定》](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 深入了解 Microsoft 端點管理員 (目前分支) 的設定。

針對 System Center 2012 Configuration Manager，請參閱 [如何在 Configuration Manager 中為端點保護部署潛在的垃圾應用程式保護原則](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。

> [!NOTE]
> Microsoft Defender 防毒軟體封鎖的 PUA 事件會在 Windows 事件檢視器中舉報，而不是在 Microsoft Endpoint Configuration Manager 中。

### <a name="use-group-policy-to-configure-pua-protection"></a>使用群組原則來設定 PUA 保護

1. 下載並安裝 [Windows 10 的系統管理範本 (.admx) 2020 年 10 月更新 (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. 在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

3. 選取您想設定的群組原則物件，然後選擇 **編制**。

4. 在 **[群組原則管理編輯器]** 中，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。

5. 展開 **Windows 元件** > **Microsoft Defender 防毒軟體** 的樹狀結構。

6. 按兩下以 **設定潛在的垃圾應用程式 (PUA) 的偵測**。

7. 選取 **[啟用]** 來啟用 PUA 保護。

8. 在 **[選項]**，選取 **[封鎖]** 來封鎖潛在的垃圾應用程式，或選取 **[稽核模式]** 來測試您環境中的設定如何運作。 選取 **[確定]**。

9. 如常部署您的群組原則物件。

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>使用 PowerShell Cmdlet 來設定 PUA 保護

#### <a name="to-enable-pua-protection"></a>啟用 PUA 保護

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

將此 Cmdlet 的值設定為 `Enabled`，會開啟已被停用的功能。

#### <a name="to-set-pua-protection-to-audit-mode"></a>將 PUSA 保護設定到稽核模式

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

設定 `AuditMode` 可以偵測 PUA 但不封鎖它們。

#### <a name="to-disable-pua-protection"></a>停用 PUA 保護

我們推薦持續開啟 PUA 保護。 不過，如果您可以使用下列 Cmdlet 來關閉它:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

將此 Cmdlet 的值設定為 `Disabled`，會關閉已被啟用的功能。

要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/index)。

## <a name="view-pua-events-using-powershell"></a>使用 PowerShell 檢視 PUA 事件

在 Windows 事件檢視器中舉報 PUA 事件，但在　Microsoft Endpoint Manager 或 Intune 中則不舉報。 您也可以使用 `Get-MpThreat` Cmdlet 來檢視 Microsoft Defender 防毒軟體已經處理的威脅。 以下為範例:

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

## <a name="get-email-notifications-about-pua-detections"></a>收取關於 PUA 偵測的電子郵件通知

您開業開啟電子郵件通知以接收關於 PUA 偵測的電子郵件。

關於檢視 Microsoft Defender 防毒軟體事件的詳細資料，請參閲 [《疑難排解事件識別碼》](troubleshoot-microsoft-defender-antivirus.md)。 PUA 事件記錄在事件識別碼 **1160** 下。

## <a name="view-pua-events-using-advanced-hunting"></a>使用進階搜捕檢視 PUA 事件

如果您使用 [Microsoft Defender 進階威脅防護](microsoft-defender-endpoint.md)，則可以使用進階搜捕查詢來檢視 PUA 事件。 以下為範例查詢:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName = tostring(x.ThreatName), WasExecutingWhileDetected = tostring(x.WasExecutingWhileDetected), WasRemediated = tostring(x.WasRemediated)
| where ThreatName startswith_cs 'PUA:'
```

深入了解進階搜捕，請參閲 [《使用進階搜捕主動搜捕威脅》](advanced-hunting-overview.md)。

## <a name="exclude-files-from-pua-protection"></a>排除來自 PUA 保護的檔案

有時一個檔案會不小心被 PUA 保護封鎖，或者需要 PUA 的功能來完成一個工作。 在這些情況下，檔案可以新增到排除項目清單。

如需詳細資訊，請參閱 [《設定及驗證基於檔案副檔名和資料夾位置的排除》](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

## <a name="see-also"></a>另請參閱

- [新一代保護](microsoft-defender-antivirus-in-windows-10.md)
- [設定行為、啟發學習法和即時保護](configure-protection-features-microsoft-defender-antivirus.md)