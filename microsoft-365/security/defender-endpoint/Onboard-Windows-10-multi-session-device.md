---
title: 在 Windows 虛擬桌面中上將 Windows 10 多工作階段裝置上線
description: 如需有關在 Windows 虛擬桌面上架 Windows 10 多會話裝置的資訊，請參閱本文中的更多內容。
keywords: Windows虛擬桌面、WVD、microsoft defender、端點、板載
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9114a825ad011f0b2a17cea4929ab2a09bfa2172
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339475"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>在 Windows 虛擬桌面中上將 Windows 10 多工作階段裝置上線 
6分鐘可供讀取 

適用於： 
- 在 Windows 虛擬機器上執行的 Windows 10 多個會話 (WVD)  

Microsoft Defender for Endpoint 支援監控 VDI 和 Windows 虛擬桌面會話。 根據組織的需求，您可能需要執行 VDI 或 Windows 虛擬機器會話，以協助員工從未受管理的裝置、遠端位置或類似案例中存取公司資料和應用程式。 使用 Microsoft Defender for Endpoint，您可以監視這些虛擬機器，以進行反常的活動。

 ## <a name="before-you-begin"></a>事前準備
熟悉 [非持久性 VDI 的考慮](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。 雖然[Windows 虛擬桌面](/azure/virtual-desktop/overview)不提供非持續性選項，但是它提供使用黃金 Windows 影像的方式，可用來布建新的主機和重新部署電腦。 這會增加環境中的變化程度，進而影響在 Microsoft Defender for Endpoint 入口網站中建立及維護的專案，可能會降低安全性分析分析員的知名度。

> [!NOTE]
> 取決於您選擇的上架方法，裝置可以出現在端點入口網站的 Microsoft Defender 中，做為下列其中一種： 
> - 每個虛擬機器的單一專案 
> - 每個虛擬機器的多個專案 

Microsoft 建議將 Windows 虛擬機器上架成每個虛擬桌面的單一專案。 這可確保 Microsoft Defender 端點入口網站中的調查經驗是以電腦名稱稱為基礎的一個裝置的內容。 經常刪除及重新部署 WVD 主機的組織，應強烈考慮使用此方法，因為這會防止在 Microsoft Defender for Endpoint 入口網站中建立相同機器的多個物件。 這可能會在調查事件時造成混淆。 在測試或非易失環境中，您可以選擇不同的方式。 

Microsoft 建議將 Microsoft Defender for Endpoint 上架腳本新增至 WVD 黃金影像。 如此一來，您就可以確定此上架腳本會在第一次啟動時立即執行。 它會在從 WVD 黃金影像布建的所有 WVD 電腦上第一次啟動時做為啟動腳本執行。 不過，如果您使用其中一個圖庫圖像但未修改，請將腳本放入共用位置，然後從本機或網域群組原則呼叫它。 

> [!NOTE]
> WVD 黃金影像上的 VDI 上架啟動腳本的位置和設定會將其設定為啟動腳本，當 WVD 啟動時執行。 建議您不要以實際 WVD 黃金影像為架。 另一個考慮是用來執行腳本的方法。 它應盡可能在啟動/布建程式中執行，以減少可供接收會話和裝置上架至服務的機器之間的時間。 下列案例 1 & 2 會將此納入考慮。

### <a name="scenarios"></a>案例
有幾種方式可以將 WVD 主機電腦架上架：

- 在啟動期間) 從共用位置 (或從共用位置執行腳本。
- 使用管理工具來執行腳本。

#### <a name="scenario-1-using-local-group-policy"></a>*案例1：使用本機組策略*
此案例需要將腳本放在黃金映射中，並使用本機組策略在啟動程式的初期執行。

使用上 [架非持久性虛擬桌面基礎結構 (VDI) 裝置](configure-endpoints-vdi.md#onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices)上的指示。

遵循每個裝置的單一專案指示。

#### <a name="scenario-2-using-domain-group-policy"></a>*案例2：使用網域群組原則*
此案例使用以網域為基礎的群組原則來執行集中放置的腳本。 您也可以將腳本放在黃金影像中，並以相同的方式執行。

**從 Windows Defender 安全中心下載 WindowsDefenderATPOnboardingPackage.zip 檔案**

1. 開啟 VDI 設定套件 .zip 檔案 (WindowsDefenderATPOnboardingPackage.zip)   

    1. 在 [Microsoft Defender 資訊安全中心] 導覽窗格中，選取 [**設定** 上  >  **架**]。 
    1. 選取 [Windows 10] 做為作業系統。 
    1. 在 [ **部署方法** ] 欄位中，選取非持續端點的 VDI 上架腳本。 
    1. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。 

2. 將 .zip 檔案的內容解壓至共用的唯讀位置，可供裝置存取。 您應該會有一個稱為 **OptionalParamsPolicy** 的資料夾，以及檔案 **WindowsDefenderATPOnboardingScript** 和 **Onboard-NonPersistentMachine.ps1**。

**在虛擬機器啟動時使用群組原則管理主控台執行腳本**

1. 開啟「群組原則管理主控台 (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [群組原則管理編輯器] 中，移至 [ **電腦** 設定 \> **偏好** 設定] [控制台 \> **設定**]。 

3. 以滑鼠右鍵按一下 [**排程任務**]，按一下 [**新增**]，然後按一下 [**立即** 工作 (至少 Windows 7) 。 

4. 在開啟的任務視窗中，移至 [ **一般** ] 索引標籤。在 [ **安全性選項** ] 底下，按一下 [ **變更使用者或群組** ，然後輸入系統]。 按一下 [ **檢查名稱** ]，然後按一下 [確定]。 NT AUTHORITY\SYSTEM 會顯示為執行工作時所用的使用者帳戶。 

5. 選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。 

6. 移至 [ **動作** ] 索引標籤，然後按一下 [ **新增**]。 確定 [動作] 欄位中已選取 [ **啟動程式** ]。 輸入下列專案： 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   然後選取 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。

#### <a name="scenario-3-onboarding-using-management-tools"></a>*案例3：使用管理工具上架*

如果您打算使用管理工具來管理機器，您可以使用 Microsoft Endpoint Configuration Manager 板載裝置。

如需詳細資訊，請參閱[使用 Configuration Manager 的板載 Windows 10 裝置](configure-endpoints-sccm.md)。

> [!WARNING]
> 如果您打算使用[攻擊面減少規則](attack-surface-reduction.md)，請注意，不應該使用規則「[封鎖從 PSExec 和 WMI 命令](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)產生的程式建立」，因為該規則與透過 Microsoft Endpoint Configuration Manager 的管理不相容。 規則會封鎖 Configuration Manager 用戶端用來正確運作的 WMI 命令。 

> [!TIP]
> 在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。 如需詳細資訊，請參閱 [在新架的 Microsoft Defender For Endpoint 裝置上執行偵測測試](run-detection-test.md)。 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>在建立黃金影像時標記您的電腦 

在您的上架中，您可能會想要考慮設定機器標記，以在 Microsoft 的「安全性中心」中更輕鬆地讓 WVD 電腦與眾不同。 如需詳細資訊，請參閱設定登錄機 [碼值以新增裝置標記](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)。 

#### <a name="other-recommended-configuration-settings"></a>其他建議的設定 

當您建立黃金影像時，您可能也想要設定初始保護設定。 如需詳細資訊，請參閱 [其他建議的配置設定](configure-endpoints-gp.md#other-recommended-configuration-settings)。 

此外，如果您使用的是 FSlogix 的使用者設定檔，建議您從永遠開啟的保護中排除下列檔： 

**排除檔案：** 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

**排除處理常式：**

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a>授權需求 

授權時請注意：使用 Windows 10 企業版多個會話時，您可以選擇以每位使用者的端點 (所有使用者授權的所有使用者) 、Windows Enterprise E5、Microsoft 365 安全性或 Microsoft 365 E5，或讓 VM 透過 Azure Defender 授權。
Microsoft Defender for endpoint 的授權需求可在下列位置找到： [授權要求](minimum-requirements.md#licensing-requirements)。

#### <a name="related-links"></a>相關連結

[使用 PowerShell 新增 Microsoft Defender 的排除專案](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
