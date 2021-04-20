---
title: Windows Server 上的 Microsoft Defender 防毒軟體
description: 瞭解如何在 Windows Server 2016 和 Windows Server 2019 上啟用和設定 Microsoft Defender 防毒軟體。
keywords: windows defender、伺服器、scep、system center endpoint protection、伺服器2016、目前分支、伺服器2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50e6f9b16dbc633e75e86acdc54ac43580107ae3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893374"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上的 Microsoft Defender 防毒軟體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以在下列 Windows Server 版本上使用 Microsoft Defender 防毒程式：
- Windows Server 2019
- Windows Server，版本1803或更新版本
- Windows Server 2016。 

在某些情況下，Microsoft Defender 防毒程式稱為 *Endpoint Protection*;不過，保護引擎是相同的。 雖然 [windows 10 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)程式的功能、設定和管理基本相同，但在 windows Server 上有一些重要差異：

- 在 Windows Server 中，會根據您定義的伺服器角色套用 [自動排除](configure-server-exclusions-microsoft-defender-antivirus.md) 。
- 在 Windows Server 中，當您執行其他防病毒產品時，Microsoft Defender 防毒程式不會自動停用自身。

## <a name="the-process-at-a-glance"></a>程序概覽

在伺服器平臺上安裝及執行 Microsoft Defender 防毒程式的套裝程式含數個步驟：

1. [啟用介面](#enable-the-user-interface-on-windows-server)。
2. [安裝 Microsoft Defender 防毒軟體](#install-microsoft-defender-antivirus-on-windows-server)。
3. [驗證 Microsoft Defender 防病毒是否正在](#verify-microsoft-defender-antivirus-is-running)執行中。
4. [更新您的反惡意程式碼安全性情報](#update-antimalware-security-intelligence)。
5.  (視需要) [提交範例](#submit-samples)。
6.  (視需要) [設定自動排除](#configure-automatic-exclusions)。
7. 只有在必要時) [將 Microsoft Defender 防毒軟體設定為被動模式](#need-to-set-microsoft-defender-antivirus-to-passive-mode)，才 (。

## <a name="enable-the-user-interface-on-windows-server"></a>在 Windows Server 上啟用使用者介面

根據預設，Windows Server 上已安裝 Microsoft Defender 防毒軟體，且運作正常。 預設會在某些 SKUs 上安裝使用者介面 (GUI) ，但不是必要的，因為您可以使用 PowerShell 或其他方法來管理 Microsoft Defender 防病毒。 如果您的伺服器上未安裝 GUI，您可以使用 [ **新增角色及功能** ] 嚮導或使用 PowerShell Cmdlet 來新增 GUI。

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>使用 [新增角色及功能] 嚮導開啟 GUI

1. 請參閱 [使用 [新增角色及功能] 嚮導安裝角色、角色服務和功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)，然後使用 [ **新增角色及功能] 嚮導**。

2. 當您到達嚮導的 [ **功能** ] 步驟時，請在 [ **windows defender 功能**] 底下，選取 [ **windows defender 的 GUI** ] 選項。

   在 Windows Server 2016 中，[ **新增角色及功能] 嚮導** 看起來像這樣：

   ![新增角色和功能嚮導顯示 Windows Defender 的 GUI 選項](images/server-add-gui.png)

   在 Windows Server 2019 中，[ **新增角色及功能] 嚮導** 是類似的。

### <a name="turn-on-the-gui-using-powershell"></a>使用 PowerShell 開啟 GUI

下列 PowerShell Cmdlet 會啟用介面： 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>在 Windows Server 上安裝 Microsoft Defender 防毒程式

您可以使用 [ **新增角色及功能] 嚮導** 或 PowerShell 來安裝 Microsoft Defender 防毒軟體。

### <a name="use-the-add-roles-and-features-wizard"></a>使用 [新增角色及功能] 嚮導

1. 請參閱 [本文](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)，並使用 [ **新增角色及功能] 嚮導**。

2. 當您到達嚮導的 [ **功能** ] 步驟時，請選取 [Microsoft Defender 防病毒] 選項。 同時選取 [ **Windows Defender 的 GUI** ] 選項。

### <a name="use-powershell"></a>使用 PowerShell

若要使用 PowerShell 來安裝 Microsoft Defender 防毒軟體，請執行下列 Cmdlet：

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Microsoft defender AV 事件中包含的反惡意軟體引擎的事件訊息可以在 [Microsoft defender AV 事件](troubleshoot-microsoft-defender-antivirus.md)中找到。


## <a name="verify-microsoft-defender-antivirus-is-running"></a>驗證 Microsoft Defender 防病毒是否正在執行中

若要確認您的伺服器上正在執行 Microsoft Defender 防毒程式，請執行下列 PowerShell Cmdlet：

```PowerShell
Get-Service -Name windefend
```

若要確認已開啟防火牆保護，請執行下列 PowerShell Cmdlet：

```PowerShell 
Get-Service -Name mpssvc
```

除了 PowerShell 之外，您還可以使用命令提示字元來驗證 Microsoft Defender 防病毒是否正在執行中。 若要這麼做，請從命令提示字元執行下列命令： 

```console
sc query Windefend
```

命令會傳回 `sc query` Microsoft Defender 防病毒服務的相關資訊。 當 Microsoft Defender 防病毒執行時，會 `STATE` 顯示此值 `RUNNING` 。

## <a name="update-antimalware-security-intelligence"></a>更新反惡意程式碼安全性情報 

若要取得更新的反惡意程式碼安全性情報，您必須執行 Windows Update 服務。 如果您使用更新管理服務（如 Windows Server Update Services (WSUS) ），請確定已針對您管理的電腦核准 Microsoft Defender 防病毒安全性情報的更新。

依預設，Windows Update 不會在 Windows Server 2019 或 Windows Server 2016 上自動下載並安裝更新。 您可以使用下列其中一種方法來變更此設定：


|方法	  |描述  |
|---------|---------|
|控制台中的 **Windows 更新**     |- **自動安裝更新** ，會自動安裝所有更新，包括 Windows Defender 安全性情報更新。 <br/>- **下載更新，但讓我選擇是否安裝這些更新** ，可讓 Windows Defender 自動下載並安裝安全性智慧更新，但不會自動安裝其他更新。       |
|**群組原則**     | 您可以使用 [群組原則] 中的可用設定來設定及管理 Windows 更新，其路徑如下：系統 **管理 \Windows 元件 \Windows Update\Configure 自動更新**         |
|**AUOptions** 登錄機碼     |下列兩個值允許 Windows Update 自動下載並安裝安全性情報更新： <br/>- **4**  - **自動安裝更新**。 這個值會導致自動安裝所有更新，包括 Windows Defender 安全性情報更新。 <br/>- **3**  - **下載更新，但讓我選擇是否要安裝這些更新**。  這個值可讓 Windows Defender 自動下載並安裝安全性智慧更新，但不會自動安裝其他更新。         |

為了確保維護惡意程式碼保護，建議您啟用下列服務：

- Windows 錯誤報告服務

- Windows Update 服務

下表列出 Microsoft Defender 防病毒和相依服務的服務。

|服務名稱|檔案位置|描述|
|--------|---------|--------|
|Windows Defender 服務 (WinDefend) |`C:\Program Files\Windows Defender\MsMpEng.exe`|這是主要的 Microsoft Defender 防病毒服務，必須在任何時間執行。|
|Windows 錯誤報告服務 (Wersvc) |`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|此服務會將錯誤報表傳送回 Microsoft。|
|Windows Defender 防火牆 (MpsSvc) |`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|建議您保留啟用 Windows Defender 防火牆服務。|
|Windows Update (Wuauserv) |`C:\WINDOWS\system32\svchost.exe -k netsvcs`|需要有 Windows Update 才能取得安全性情報更新和反惡意程式碼引擎更新|

## <a name="submit-samples"></a>提交範例

範例提交可讓 Microsoft 收集可能惡意軟體的範例。 為了協助提供持續且最新的保護，Microsoft 研究員使用這些範例來分析可疑活動，並產生更新的反惡意軟體安全性情報。 我們會收集程式的可執行檔，例如 .exe 檔案和 .dll 檔案。 我們不會收集包含個人資料的檔案，像是 Microsoft Word 檔和 PDF 檔案。

### <a name="submit-a-file"></a>提交檔案

1. 查看 [提交指南](/windows/security/threat-protection/intelligence/submission-guide)。

2. 請造訪 [範例提交入口網站](https://www.microsoft.com/wdsi/filesubmission)，並提交您的檔案。


### <a name="enable-automatic-sample-submission"></a>啟用自動範例提交

若要啟用自動範例提交，請以系統管理員身分啟動 Windows PowerShell 主控台，然後根據下列其中一個設定來設定 **SubmitSamplesConsent** 值資料：

|設定  |描述  |
|---------|---------|
|**0**  - **Always prompt**     |Microsoft Defender 防病毒服務會提示您確認是否提交所有必要的檔案。 這是 Microsoft Defender 防毒軟體的預設設定，但是不建議在未使用 GUI 的 Windows Server 2016 或2019上進行安裝。         |
|**1**   - **自動傳送安全的範例**     |Microsoft Defender 防病毒服務會傳送所有標示為「安全」的檔案，並提示您輸入檔案的其餘部分。         |
|**2**  - **從不傳送**      |Microsoft Defender 防病毒服務不會提示，也不會傳送任何檔案。         |
|**3**  - **自動傳送所有範例**     |Microsoft Defender 防病毒服務會不經提示確認即傳送所有檔案。         |

## <a name="configure-automatic-exclusions"></a>設定自動排除

為了協助確保安全性和效能，會根據您在 Windows Server 2016 或2019上使用 Microsoft Defender 防毒程式時所安裝的角色和功能，自動新增某些排除。

請參閱 [在 Windows Server 上設定 Microsoft Defender 防毒軟體中的排除](configure-server-exclusions-microsoft-defender-antivirus.md)專案。 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>需要將 Microsoft Defender 防毒程式設為被動模式？

如果您使用非 Microsoft 防病毒產品作為主要防病毒方案，請將 Microsoft Defender 防病毒產品設定為被動模式。  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>使用登錄機碼將 Microsoft Defender 防毒程式設定為被動模式

如果您使用的是 Windows Server，版本1803或 Windows Server 2019，您可以設定下列登錄機碼，將 Microsoft Defender 防毒軟體設定為被動式模式：
- 路徑： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名稱：`ForceDefenderPassiveMode`
- 類型： `REG_DWORD`
- 值：`1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>使用移除角色和功能嚮導停用 Microsoft Defender 防毒程式

1. 請參閱 [安裝或卸載角色、角色服務或功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)，並使用 **移除角色和功能嚮導**。 

2. 當您到達嚮導的 [ **功能** ] 步驟時，請清除 [ **Windows Defender 功能** ] 選項。 

    [！提示] 如果您在 [ **Windows Defender 功能**] 區段下清除 [ **windows defender** ]，系統會提示您移除 **windows defender** 的 [介面] 選項 GUI。 
    
    在沒有使用者介面的情況下，Microsoft Defender 防病毒仍會正常執行，但是如果您停用核心 **Windows Defender** 功能，則無法啟用使用者介面。

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>使用 PowerShell 關閉 Microsoft Defender 防病毒使用者介面

若要關閉 Microsoft Defender 防病毒 GUI，請使用下列 PowerShell Cmdlet：

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>您使用的是 Windows Server 2016 嗎？

如果您使用的是 Windows Server 2016，且是 Microsoft 未提供或開發的協力廠商反惡意軟體/防病毒產品，您必須停用/卸載 Microsoft Defender 防毒軟體。 

> [!NOTE]
> 您無法卸載 Windows 安全性 app，但是您可以使用這些指示來停用此介面。

下列 PowerShell Cmdlet 會在 Windows Server 2016 上卸載 Microsoft Defender 防毒程式：

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a>另請參閱

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 防毒程式相容性](microsoft-defender-antivirus-compatibility.md)
