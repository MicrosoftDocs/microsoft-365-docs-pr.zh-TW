---
title: 自行註冊現有裝置
description: 登錄重複使用的裝置已經可能有自己，讓他們可以由 Microsoft 受管理的電腦
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1d9b390cc28002b4561d61fa1d6cc411f3b135f1
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112707"
---
# <a name="register-existing-devices-yourself"></a>自行註冊現有裝置

>[!NOTE]
>本主題說明您可以重新使用的裝置您已經有，而且他們註冊 Microsoft 受管理電腦中的步驟。 如果您正在使用全新的裝置，請改為按照中[自行註冊 Microsoft 受管理電腦中的新裝置](register-devices-self.md)的步驟。

中[註冊裝置的協力廠商的步驟](register-devices-partner.md)會說明協力廠商的程序。

Microsoft 受管理的電腦可搭配全新的裝置運作，或您可重複使用您可能已經擁有的裝置 (這需要您重新製作其映像)。 您可以使用 Azure 入口網站上的 Microsoft 受管理的電腦來註冊裝置。

## <a name="prepare-to-register-existing-devices"></a>準備註冊現有裝置


若要登錄現有的裝置，請遵循下列步驟：

1. [取得每個裝置的硬體雜湊。](#obtain-the-hardware-hash)
2. [合併雜湊資料](#merge-hash-data)
3. [在 Microsoft 受管理的電腦中註冊裝置](#register-devices)。
4. [再次確認映像是否正確。](#check-the-image)
5. [交付裝置](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>取得硬體雜湊

Microsoft 受管理的電腦會藉由參照其硬體雜湊來唯一識別每個裝置。 您可以從您已經在使用的裝置取得這項資訊的四個選項：

- 請向您的 OEM 提供者索取 AutoPilot 註冊檔案，其中會包含硬體雜湊。
- 在[Configuration Manager](#configuration-manager)中建立自訂報告。
- 可以執行 Windows PowerShell 指令碼-由上每個裝置--使用[Active Directory](#active-directory-powershell-script-method) ] 或 [[手動](#manual-powershell-script-method)並收集檔案中的結果。
- 啟動每個裝置 (但不要完成 Windows 設定體驗)，然後[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。

#### <a name="configuration-manager"></a>Configuration Manager

您可以使用 Microsoft 端點 Configuration Manager 從現有的裝置，您想要註冊 Microsoft 受管理電腦收集硬體雜湊。

> [!IMPORTANT]
> 您想要取得這項資訊的任何裝置必須執行 Windows 10 版本 1703年或更新版本。 您也需要為連接至 Configuration Manager （最新分支） 站台的 Configuration Manager 用戶端裝置。 您也需要報告點網站系統角色設定您環境中使用 SQL Server Reporting Services 啟用。 

如果您已符合所有這些必要條件，就可以依照下列步驟收集的資訊：

1. 在 Configuration Manager 主控台中，選取 [**監視**]。 
2. 在監視工作區中，依序展開 [**報告**]，然後選取**報告**。 
3. 在 [**首頁**] 索引標籤上 [**建立**] 區段中，選取**建立報表**，以開啟 [建立報表] 精靈。 
4. 在 [**資訊**] 頁面上，設定這些設定： 
    - **名稱：** 指定報表的名稱。 
    - **描述：** 指定報表的描述。 
    - **伺服器：** 會顯示在其上您要建立此報表的報表伺服器名稱。 
    - **路徑：** 選取 [**瀏覽]** 以指定您要儲存的報告的資料夾]。 
5.  Select **Next**.  
6. 在 [**摘要**] 頁面上檢閱設定。 選取 [變更設定，或選取 [**下一步**建立報表設定管理員] 中的**上一步**]。 
7. 在 [**完成**] 頁面上選取 [**關閉**] 結束精靈]，並開啟**報表產生器**輸入報表的設定值。 輸入您的使用者帳戶和密碼，如果出現提示，，然後選取 [ **[確定]。** 如果報表產生器未安裝在裝置上，系統會提示您安裝它。 選取 [**執行，以安裝報表產生器**，這必要修改和建立報告。 


**在 「 Microsoft 報表產生器中**，提供報表的 SQL 陳述式，請遵循下列步驟：

1. 在左窗格中，選取**資料集**，並用滑鼠右鍵按一下要**新增的資料集**。
2. 移至 [**查詢**] 索引標籤，然後為*DataSet0*輸入名稱。 
3. 選取 [**我的報表中內嵌使用資料集**;報表產生器開啟。
4. 在 [**報表產生器中**，選取 [**資料來源：**。 選取預設資料來源，應該啟動與 「 AutoGen 」。 
5. 選擇 [**查詢類型為文字**，，然後輸入此查詢：




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. 瀏覽至 [**欄位**] 索引標籤中，應該已經填入 wehre 值的**欄位名稱**] 和 [**來源] 欄位**。 如果不是，然後選取 [**新增**]，然後選取 [**查詢] 欄位**。 輸入的**欄位名稱**和**欄位來源**。
6. 重複針對每一個這些值： 
    - 製造商 
    - Model 
    - Serial_Number 
    - HardwareHash
7. 選取 [確定]****。

**接下來，定義報告顯示，並建立報告**遵循下列步驟：

1. 選取**表格或矩陣**;會開啟新的精靈。
2. 在 **[選擇資料集**，選取 [**選擇現有的資料集，在這份報告或共用資料集**。  
3. 選取**DataSet0** （預設值），然後再選取 [**下一步**。
4. 將**製造商**、**模型**和**序號**拖曳至 [**列群組**] 方塊。 將**HardwareHash**拖曳至 [**值**] 方塊，然後選取 [**下一步**。
5. 清除核取方塊，**顯示小計和總計**] 及 [**展開/折疊群組**。  Select **Next**. 
6. Select **Finish**.
7. 選取 [若要執行您的報表的 [**執行**]。 確認報告提供您所預期的資訊。 如有必要，選取 [**設計**回到修改報表的 [設計] 檢視。
8. 選取 [將報告儲存至 report server 的 [**儲存**]。 您可以監視工作區中的 [報告] 節點中執行新的報表。 

**最後，將報告匯出並使用它來註冊裝置**遵循下列步驟。 （您應只需要遵循步驟 1 和 2 的這一節，如果您在先前步驟後立即瀏覽。）：

1. 在 Configuration Manager 主控台中，選取 [**監視**]。
2. 在 [**監視**]，依序展開 [**報告**]，然後再選取 [**報告**。
3. 尋找您稍早建立的報告使用的名稱。
4. 這份報告，以滑鼠右鍵按一下，並選取 [**執行**]。
5. 在 [開啟] 對話方塊中，選取 [**匯出**，然後選取 [**另存為 CSV**。
6. 此版本的報表從 Configuration Manager 進行通訊的所有 Windows 10 裝置擷取雜湊。 您將需要篩選至您要註冊 Microsoft 受管理電腦只要那些裝置的結果。


> [!IMPORTANT]
> 在 Configuration Manager 中的查詢不允許匯出的資料行名稱; 中的空格這就是為什麼步驟有您輸入 「 Serial_Number 」 和 「 HardwareHash。 」 有匯出的 CSV 檔案之後，您必須編輯讀取*序號*和*硬體雜湊*後，再繼續裝置註冊如下所示的報告標頭。

現在您可以繼續[註冊裝置使用 Azure 入口網站](#register-devices-by-using-the-azure-portal)。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell 指令碼方法

在 Active Directory 環境中，您可以使用`Get-MMDRegistrationInfo`PowerShell cmdlet，以使用 WinRM 從遠端收集從 Active Directory 群組中的裝置的資訊。 您也可以使用`Get-AD Computer`指令程式，以及如何取得篩選結果的特定硬體模型包含目錄的應用程式的名稱。 若要這麼做，請先確認下列必要條件，然後再繼續進行步驟：

- WinRM 已啟用。
- 您要註冊的裝置會在網路上作用中 （也就是說，它們是不中斷連線或關閉）。
- 請確定您已有執行遠端裝置上的權限的網域認證參數。
- 請確定 Windows 防火牆允許存取 WMI。 若要這麼做，請遵循下列步驟：
    1. 開啟 [控制台] 中的 [ **Windows Defender 防火牆**，然後選取 [**允許應用程式或功能通過 Windows Defender 防火牆**。
    2. 在清單中尋找**Windows Management Instrumentation (WMI)** 啟用這兩個**私密與公開金鑰**，，然後選取 **[確定]**。

1.  以系統管理權限開啟 PowerShell 提示字元。
2.  執行*其中一個*這些指令碼：
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. 存取任何目錄其中可能會有的裝置的項目。 移除*所有*目錄，包括 Windows Server Active Directory 網域服務和 Azure Active Directory 中的每個裝置的項目。 請注意此移除可能需要幾個小時才能完全處理程序。
4. 存取管理服務其中可能會有的裝置的項目。 移除*所有*的管理服務，包括 Microsoft 端點組態管理員、 Microsoft Intune 和 Windows Autopilot 為每個裝置的項目。 請注意此移除可能需要幾個小時才能完全處理程序。

現在您可以繼續[註冊裝置](#register-devices)。

#### <a name="manual-powershell-script-method"></a>手動 PowerShell 指令碼方法

1.  以系統管理權限開啟 PowerShell 提示字元。
2.  執行 `Install-Script -Name Get-MMDRegistrationInfo`
3.  執行 `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [合併的雜湊資料。](#merge-hash-data)

#### <a name="flash-drive-method"></a>快閃磁碟機方法

1. 在您要註冊的裝置以外的裝置上，插入 USB 磁碟機。
2. 以系統管理權限開啟 PowerShell 提示字元。
3. 執行 `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. 開啟您要註冊的裝置，但*請勿開始設定體驗*。 如果您不小心開始設定體驗，則必須重設裝置或重新製作其映像。
5. 插入 USB 磁碟機，然後按 SHIFT + F10。
6. 以系統管理權限開啟 PowerShell 提示字元，然後執行 `cd <pathToUsb>`。
7. 執行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 執行 `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. 移除 USB 磁碟機，然後執行 `shutdown -s -t 0` 以關閉裝置
10. [合併的雜湊資料。](#merge-hash-data)

>[!IMPORTANT]
>在您完成註冊前，請勿開啟您所註冊的裝置。 



### <a name="merge-hash-data"></a>合併雜湊資料

如果您手動 PowerShell 或快閃磁碟機方法所收集硬體雜湊資料，您現在需要在結合成單一檔案，以完成註冊的 CSV 檔案中有資料。 以下是讓註冊變輕鬆的範例 PowerShell 指令碼：

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

合併到一個 CSV 檔案的雜湊資料，您現在可以繼續[註冊裝置](#register-devices)。

### <a name="register-devices"></a>註冊裝置

CSV 檔案必須採用可供註冊的特定格式。 如果您在先前步驟中自行收集了資料，檔案應該已經是正確的格式。如果您是向供應商取得檔案，則可能需要調整格式。

>[!NOTE]
>為了方便起見，您可以下載這個 CSV 檔案的[範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。

您的檔案必須包含**完全相同的欄標題**作為範例一 (製造商、型號等)，但您自己的資料適用於其他列。 如果您使用範本，請在記事本這類的文字編輯工具中開啟範本，然後不妨將列 1 的所有資料維持原狀，只在列 2 以下輸入資料。 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>如果您忘記變更任何範例資料，註冊將會失敗。

#### <a name="register-devices-by-using-the-azure-portal"></a>使用 Azure 入口網站來註冊裝置

從 Microsoft 受管理的電腦的 [Azure 入口網站](https://aka.ms/mmdportal)，選取左側導覽窗格中的 [裝置]****。 選取 [+ 註冊裝置]****；飛入視窗隨即開啟：

[![在選取 [註冊裝置] 之後飛入，並列出裝置與已指派使用者、序號、狀態、上次查看日期和年限等欄](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (事實並非如此。我們可以移除此注意事項 - 但現在暫且擱置，留待我們有機會討論。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


請遵循下列步驟：

1. 在 [檔案上傳]**** 中，提供您先前建立的 CSV 檔案路徑。
2. 或者，您可以新增 [訂單識別碼]**** 或 [購買識別碼]****，以便自行追蹤。 這些值沒有格式需求。
3. 選取 [註冊裝置]****。 系統會將裝置新增至 [裝置] 刀鋒視窗**** 上標示為 [註冊擱置]**** 的裝置清單。 註冊通常需要不到 10 分鐘的時間，而註冊成功時，裝置將會顯示為 [使用者就緒]****，標示其已準備就緒並等待終端使用者開始使用。


您可以在主要 [Microsoft 受管理的電腦 - 裝置]**** 頁面上監視裝置註冊的進度。 其回報的可能狀態包括：

| 狀態 | 描述 |
|---------------|-------------|
| 註冊擱置 | 尚未完成註冊。 稍後再回頭檢查。 |
| 註冊失敗 | 無法完成註冊。 如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](#troubleshooting-device-registration)。 |
| 使用者就緒 | 註冊成功，且裝置現在已準備好交付給使用者。 Microsoft 受管理的電腦將會逐步引導使用者完成首次設定，因此您不需要再做任何進一步的準備。 |
| 作用中 | 裝置已交付給終端使用者並已向您的租用戶註冊。 這也表示使用者經常使用該裝置。 |
| 非作用中 | 裝置已交付給終端使用者並已向您的租用戶註冊。 不過，使用者最近尚未使用裝置 (在過去 7 天內)。  | 

#### <a name="troubleshooting-device-registration"></a>針對裝置註冊進行疑難排解

| 錯誤訊息 | 詳細資料 |
|---------------|-------------|
| 找不到裝置 | 我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。 請與您的裝置供應商確認這些值。 |
| 硬體雜湊無效 | 您為這個裝置提供的硬體雜湊格式不正確。 再次確認硬體雜湊，然後重新提交。 |
| 裝置已經註冊 | 此裝置已經註冊到您的組織。 無需採取任何動作。 |
| 其他組織所宣告的裝置 | 此裝置已經由其他組織所宣告。 請洽詢您的裝置供應商。 |
| 未預期的錯誤 | 無法自動處理您的要求。 連絡客戶支援並提供要求識別碼：<requestId> |

### <a name="check-the-image"></a>檢查映像

如果您的裝置來自 Microsoft 受管理的電腦合作夥伴供應商，映射應是正確的。

如果您想要的話，也歡迎您自行套用映像。 若要開始使用，請連絡您的 Microsoft 代表，他們會將映像的位置及其套用步驟提供給您。

### <a name="deliver-the-device"></a>交付裝置

> [!IMPORTANT]
> 將裝置交給使用者之前，請確認您已取得並套用[適合該使用者的授權](../get-ready/prerequisites.md)。

如果已套用所有授權，您可以[讓使用者準備好使用裝置](get-started-devices.md)，然後使用者即可啟動裝置並繼續進行 Windows 設定體驗。









