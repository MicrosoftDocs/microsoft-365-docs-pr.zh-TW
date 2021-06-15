---
title: Microsoft Defender 防毒軟體虛擬桌面基礎結構部署指南
description: 瞭解如何在虛擬桌面環境中部署 Microsoft Defender 防毒軟體，以取得保護與效能之間的最佳平衡。
keywords: vdi，hyper-v，vm，虛擬機器，windows defender，防毒程式，av，虛擬桌面機，rds，遠端桌面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/11/2021
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 83e37b6d59d7356b53e5024204e39473764cea72
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924912"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>虛擬桌面基礎結構 (VDI) 環境中 Microsoft Defender 防毒軟體的部署指南

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

除了標準的內部部署或硬體設定之外，您也可以使用遠端桌面 (RDS) 或虛擬桌面基礎結構 (VDI) 環境中的 Microsoft Defender 防毒軟體。

如需 Microsoft 遠端桌面服務和 VDI 支援的詳細資訊，請參閱[Windows 虛擬機器檔](/azure/virtual-desktop)。

如需 azure 虛擬機器，請參閱[在 azure Defender 中安裝 Endpoint Protection](/azure/security-center/security-center-install-endpoint-protection)。

透過輕鬆將更新部署至 VDIs 中執行的 Vm 的功能，我們已縮短此指南，以著重于您可以快速輕鬆地在電腦上更新的方式。 您不再需要定期建立及密封黃金影像，因為更新會擴充至主伺服器上的元件位，然後在開啟時直接下載至 VM。

本指南說明如何設定您的 Vm 以取得最佳保護和效能，包括如何進行下列作業：

- [為安全性情報更新設定專用的 VDI 檔案共用](#set-up-a-dedicated-vdi-file-share)
- [隨機化排程掃描](#randomize-scheduled-scans)
- [使用快速掃描](#use-quick-scans)
- [防止通知](#prevent-notifications)
- [停用每次更新後所發生的掃描](#disable-scans-after-an-update)
- [掃描已離線一段時間的過時機器或機器](#scan-vms-that-have-been-offline)
- [套用排除專案](#exclusions)

您也可以[在虛擬桌面基礎結構上](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)下載白皮書 Microsoft Defender 防毒軟體，它會看看新的共用安全情報更新功能，也就是如何在您自己的 VDI 上測試防病毒效能的效能測試及指導方針。

> [!IMPORTANT]
> 雖然 VDI 可以主控于 Windows Server 2012 或 Windows Server 2016 上，但虛擬機器 (vm) 應該至少執行 Windows 10 1607，因為在舊版的 Windows 中已增加的保護技術和功能無法使用。<br/>在 Windows 10 內幕機預覽、組建 18323 (和更新) 版本中，Microsoft Defender AV 對虛擬機器的運作方式，具有效能及功能的增強功能。 如果您需要使用內部使用者預覽組建，我們會在此指南中識別。若未指定，則最佳保護和效能所需的最低版本為 Windows 10 1607。

## <a name="set-up-a-dedicated-vdi-file-share"></a>設定專用的 VDI 檔案共用

在 Windows 10 版本1903中，我們引進了共用安全性智慧功能，以將下載的安全性情報更新解除至主機機，進而儲存個別電腦上的 CPU、磁片和記憶體資源。 這項功能已經過回溯，現在可在 Windows 10 版本1703和更新版本中運作。 您可以使用群組原則或 PowerShell 來設定此功能。

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>使用群組原則來啟用共用的安全性智慧功能：

1. 在您的群組原則管理電腦上，開啟 [群組原則管理主控台]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**。

5. 按兩下 [ **定義 VDI 用戶端的安全性智慧位置**]，然後將此選項設定為 [ **啟用**]。 會自動顯示欄位。

6. 輸入 `\\<sharedlocation\>\wdav-update` 此值的說明 (，請參閱 [下載和解開](#download-and-unpackage-the-latest-updates)) 。

7. 按一下 ****[確定]。

8. 將 GPO 部署至您要測試的 Vm。

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>使用 PowerShell 啟用共用安全性智慧功能

使用下列 Cmdlet 來啟用該功能。 您通常需要將 PowerShell 型設定原則推入 Vm，就像往常一樣：

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

請參閱 [下載及解壓縮](#download-and-unpackage-the-latest-updates) 區段，以瞭解 \<shared location\> 將會有哪些專案。

## <a name="download-and-unpackage-the-latest-updates"></a>下載並解開最新的更新

現在，您可以開始下載及安裝新的更新。 我們為您建立了範例 PowerShell 腳本。 此腳本是下載新更新並為您的 Vm 做好準備的最簡單方式。 然後，您應該使用計畫的工作 (，將腳本設定為在管理電腦上的特定時間執行; 如果您很熟悉在 Azure、Intune 或 SCCM 中使用 PowerShell 腳本，也可以) 使用這些腳本。

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

您可以將排定的任務設定為一天執行一次，這樣每當下載並解壓縮套件時，Vm 都會收到新的更新。 我們建議您一天開始一次，但您應嘗試增加或減少頻率，以瞭解影響。 

安全性智慧套件通常每三至四個小時發佈一次。 設定頻率短于四小時的頻率不會被告知，因為這會增加管理電腦上沒有任何好處的網路開銷。

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>設定計劃任務以執行 PowerShell 腳本

1. 在管理電腦上，開啟 [開始] 功能表，然後輸入 [ **任務** 排程器]。 開啟它，然後選取 [ **建立任務 ...]。** 在側面面板上。

2. 輸入名稱作為 **安全性情報 unpacker**。 移至 [**觸發器**] 索引標籤。選取 [**新增 ...** ] > [**每日**]，然後選取 **[確定]**。

3. 移至 [**動作**] 索引標籤。選取 [**新增 ...** ] 在 [**程式/腳本**] 欄位中輸入 **PowerShell** 。 `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1`在 [**新增引數**] 欄位中輸入。 選取 **[確定]**。

4. 您可以視需要選擇設定其他設定。

5. 選取 **[確定]** 以儲存排程的任務。
 
您可以手動啟動更新，方法是以滑鼠右鍵按一下任務，然後按一下 [ **執行**]。

### <a name="download-and-unpackage-manually"></a>手動下載和解開

如果您想要手動執行所有動作，以下是複製腳本行為的方法：

1. 在稱為儲存情報更新的系統根目錄上建立新的資料夾 `wdav_update` ，例如，建立資料夾 `c:\wdav_update` 。

2. 使用 GUID 名稱在 *wdav_update* 底下建立子資料夾，例如 `{00000000-0000-0000-0000-000000000000}`

範例如下： `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > 在腳本中，我們會設定它，使 GUID 的最後12位數成為下載檔案的年、月、日和時間，以便每次建立新的資料夾。 您可以變更此方式，每次將檔案下載至相同的資料夾。

3. 從 GUID 資料夾下載安全性智慧套件 [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  。 該檔案應該是以檔案名命名 `mpam-fe.exe` 。

4. 開啟 cmd 命令提示字元視窗，並流覽至您建立的 GUID 資料夾。 例如，使用 **/x** 解壓縮命令解壓縮檔案 `mpam-fe.exe /X` 。

   > [!NOTE]
   > 每當使用解壓縮的更新套件建立新的 GUID 資料夾時，或在使用新的解壓縮套件更新現有的資料夾時，Vm 都會拾取更新的套件。

## <a name="randomize-scheduled-scans"></a>隨機化排程掃描

除了 [即時保護及掃描](configure-real-time-protection-microsoft-defender-antivirus.md)之外，還會執行排程掃描。

掃描本身的開始時間仍以排程的掃描原則為基礎， (**ScheduleDay**、 **ScheduleTime** 及 **ScheduleQuickScanTime**) 。 隨機會使 Microsoft Defender 防毒軟體從排定的掃描時間設定之4小時內的每一部電腦上開始掃描。

請參閱 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 以取得可用於排程掃描的其他配置選項。

## <a name="use-quick-scans"></a>使用快速掃描

您可以指定在排程掃描期間應執行的掃描類型。 快速掃描是一種慣用方式，其設計目的是要尋找惡意程式碼所在的所有位置，以供使用中的惡意程式碼。 下列程式說明如何使用「群組原則」設定快速掃描。

1. 在 [群組原則編輯器] 中，移至 [系統 **管理範本**]  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **掃描**]。

2. 選取 **[指定要用於排程掃描的掃描類型** ]，然後編輯原則設定。

3. 將原則設定為 [ **啟用**]，然後在 [ **選項**] 下，選取 [  **快速掃描**]。

4. 選取 **[確定]**。 

5. 如常部署您的群組原則物件。

## <a name="prevent-notifications"></a>防止通知

在某些情況下，Microsoft Defender 防毒軟體通知可能會傳送至或持續傳送至多個會話。 為了將此問題降至最低，您可以鎖定 Microsoft Defender 防毒軟體使用者介面。 下列程式說明如何使用群組原則來抑制通知。

1. 在 [群組原則編輯器] 中，移至 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **用戶端介面**。

2. 選取 [ **抑制所有通知** ]，然後編輯原則設定。 

3. 將原則設定為 [ **啟用**]，然後選取 **[確定]**。

4. 如常部署您的群組原則物件。

抑制通知，可防止在執行掃描時 Windows 10 的「動作中心」或進行修正動作時，Microsoft Defender 防毒軟體中顯示的通知。 不過，您的安全性作業小組會在[Microsoft 365 Defender 入口網站](microsoft-defender-security-center.md)中看到掃描的結果。

> [!TIP]
> 若要在 Windows 10 上開啟「行動中心」，請執行下列其中一個步驟：
> - 在工作列的右端，選取 [動作中心] 圖示。
> - 按 Windows 標誌鍵按鈕 + A。
> - 在觸控式螢幕裝置上，從畫面的右邊緣輕掃。

## <a name="disable-scans-after-an-update"></a>在更新後停用掃描

在更新後停用掃描會使掃描在接收到更新後發生。 您可以在建立基底影像時套用此設定（如果您同時執行快速掃描）。 如此一來，您就可以在建立基本影像) 時，防止新更新的 VM 重新執行掃描 (已掃描。

> [!IMPORTANT]
> 在更新後執行掃描會協助確保您的 Vm 受到最新安全性情報更新的保護。 停用此選項將會降低 Vm 的保護層級，只應該在第一次建立或部署基底影像時使用。

1. 在 [群組原則編輯器] 中，移至 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **安全性智慧更新**]。

2. 選取 [ **在安全性智慧更新後開啟掃描** ]，然後編輯原則設定。

3. 將原則設定為 [ **停用**]。

4. 選取 **[確定]**。

5. 如常部署您的群組原則物件。

這個原則可防止在更新之後立即執行掃描。

## <a name="scan-vms-that-have-been-offline"></a>掃描已離線的 Vm

1. 在 [群組原則編輯器] 中，移至 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **掃描**]。

2. 選取 [ **開啟追趕快速掃描** ]，然後編輯原則設定。

3. 將原則設定為 [ **啟用**]。

4. 選取 **[確定]**。

5. 像往常一樣部署您的群組原則物件。

如果 VM 已錯過兩個或多個連續排程掃描，此原則會強制進行掃描。

## <a name="enable-headless-ui-mode"></a>啟用無周邊 UI 模式

1. 在 [群組原則編輯器] 中，移至 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **用戶端介面**。

2. 選取 [ **啟用無周邊 UI 模式]** ，然後編輯原則。

3. 將原則設定為 [ **啟用**]。

4. 按一下 ****[確定]。

5. 像往常一樣部署您的群組原則物件。
 
這個原則會從您組織中的使用者隱藏整個 Microsoft Defender 防毒軟體使用者介面。

## <a name="exclusions"></a>排除項目

您可以新增、移除或自訂排除專案，以符合您的需求。

如需詳細資訊，請參閱[Configure Microsoft Defender 防毒軟體 Windows Server 上的排除](configure-exclusions-microsoft-defender-antivirus.md)專案。

## <a name="additional-resources"></a>其他資源

- [技術 Community 博客：針對非 persistent VDI 機器設定 Microsoft Defender 防毒軟體](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [在遠端桌面服務和 VDI 上 TechNet 論壇](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [SignatureDownloadCustomTask PowerShell 腳本](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)