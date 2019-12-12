---
title: 自行註冊現有裝置
description: 登錄重複使用的裝置已經可能有自己，讓他們可以由 Microsoft 受管理的電腦
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 8d2bc20a1d429510dfcd651c6b15dc1a2a89de9d
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962600"
---
# <a name="register-existing-devices-yourself"></a>自行註冊現有裝置

>[!NOTE]
>本主題說明您可以重新使用的裝置您已經有，而且他們註冊 Microsoft 受管理電腦中的步驟。 如果您正在使用全新的裝置，請改為按照中[自行註冊 Microsoft 受管理電腦中的新裝置](register-devices-self.md)的步驟。

中[註冊裝置的協力廠商的步驟](register-devices-partner.md)會說明協力廠商的程序。

Microsoft 受管理的電腦可搭配全新的裝置，或者您可以重新使用您可能已有的裝置 （這會需要，您重新影像它們）。 您可以註冊裝置，在 Azure 入口網站上使用 Microsoft 受管理的電腦。

## <a name="prepare-to-register-existing-devices"></a>準備註冊現有裝置


若要登錄現有的裝置，請遵循下列步驟：

1. [取得硬體的每個裝置的雜湊。](#obtain-the-hardware-hash)
2. [合併的雜湊資料](#merge-hash-data)
3. [註冊 Microsoft 受管理電腦中的裝置](#register-devices)。
4. [請仔細檢查圖像正確。](#check-the-image)
5. [傳遞裝置](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>取得硬體雜湊

Microsoft 受管理的電腦會藉由參照其硬體雜湊唯一識別每個裝置。 您可以從您已經在使用的裝置取得這項資訊的四個選項：

- AutoPilot 登錄檔，其中會包含硬體雜湊會要求您 OEM 供應商。
- 在[Configuration Manager](#configuration-manager)中建立自訂報告。
- 可以執行 Windows PowerShell 指令碼-由上每個裝置--使用[Active Directory](#active-directory-powershell-script-method) ] 或 [[手動](#manual-powershell-script-method)並收集檔案中的結果。
- 啟動每個裝置--，但未完成 Windows 安裝程式體驗-並[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。

#### <a name="configuration-manager"></a>Configuration Manager

您可以使用 System Center Configuration Manager 從現有的裝置，您想要註冊 Microsoft 受管理電腦收集硬體雜湊。

> [!IMPORTANT]
> 您想要取得這項資訊的任何裝置必須執行 Windows 10 版本 1703年或更新版本。 您也需要為連接至系統管理中心目前分支站台的 Configuration Manager 用戶端裝置。 您也需要報告點網站系統角色設定您環境中使用 SQL Server Reporting Services 啟用。 

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

1.  以系統管理權限開啟 PowerShell 命令提示字元。
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
4. 存取管理服務其中可能會有的裝置的項目。 移除*所有*的管理服務，包括 System Center 設定管理員、 Microsoft Intune 和 Windows Autopilot 為每個裝置的項目。 請注意此移除可能需要幾個小時才能完全處理程序。

現在您可以繼續[註冊裝置](#register-devices)。

#### <a name="manual-powershell-script-method"></a>手動 PowerShell 指令碼方法

1.  以系統管理權限開啟 PowerShell 命令提示字元。
2.  執行`Install-Script -Name Get-MMDRegistrationInfo`
3.  執行`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [合併的雜湊資料。](#merge-hash-data)

#### <a name="flash-drive-method"></a>快閃磁碟機方法

1. 在裝置上您註冊以外，插入 USB 磁碟機。
2. 以系統管理權限開啟 PowerShell 命令提示字元。
3. 執行`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. 開啟您要註冊，裝置，但*不是會啟動安裝程式的經驗*。 如果您不小心開始的安裝體驗，您必須重設或重新裝置。
5. 插入的 USB 磁碟機，並按下 SHIFT + f10 時會顯示功能表。
6. 以系統管理權限，開啟 PowerShell 命令提示字元，然後執行`cd <pathToUsb>`。
7. 執行`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 執行`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. 移除的 USB 磁碟機，然後關閉該裝置，藉由執行`shutdown -s -t 0`
10. [合併的雜湊資料。](#merge-hash-data)

>[!IMPORTANT]
>請勿電源您註冊一次直到您已經完成註冊為其在裝置上。 



### <a name="merge-hash-data"></a>合併雜湊資料

如果您手動 PowerShell 或快閃磁碟機方法所收集硬體雜湊資料，您現在需要在結合成單一檔案，以完成註冊的 CSV 檔案中有資料。 以下是範例 PowerShell 指令碼，以將此位址設簡單：

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

合併到一個 CSV 檔案的雜湊資料，您現在可以繼續[註冊裝置](#register-devices)。

### <a name="register-devices"></a>註冊裝置

CSV 檔案必須註冊以特定格式。 如果您收集的資料自行在先前步驟中，檔案應該已可以正確的格式;如果您從供應商取得的檔案，您可能需要調整格式。

>[!NOTE]
>以方便您使用，您可以下載這個 CSV 檔案的[範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。

您的檔案必須包含**完全相同的欄名**為其中一個範例 （製造商、 型號、 等），但您自己的資料列的資料。 如果您使用的範本，在編輯 [記事本] 之類的文字中開啟，並且考慮離開的所有資料列 1 單獨中的，只輸入資料，資料列 2 中下, 面。 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>如果您忘記變更其中一個範例資料，將會失敗註冊。

#### <a name="register-devices-by-using-the-azure-portal"></a>使用 Azure 入口網站來註冊裝置

從 Microsoft 受管理電腦的 [ [Azure 入口網站](https://aka.ms/mmdportal)中，選取 [在左側的導覽窗格中的**裝置**。 選取 [ **+ 註冊裝置**;飛出視窗中開啟：

[![飛出視窗中選取註冊裝置，列出裝置資料行的指定的使用者、 序號、 狀態、 最後一筆看日期，以及保留天數之後](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (可惜這不是，則為 true。我們可以移除此附註-但現在離開它，直到我們有機會關於該聊天室。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


請遵循下列步驟：

1. 在 [**檔案上傳**，提供您先前建立的 CSV 檔案的路徑。
2. （選用） 您可以新增**順序識別碼**或**購買識別碼**自己追蹤的目的。 沒有這些值的格式需求。
3. 選取 [**註冊的裝置**]。 系統會將裝置新增至您的**裝置] 刀鋒視窗中**，標示為 [**擱置中註冊**裝置的清單。 註冊通常採用小於 10 分鐘，並成功時裝置將會顯示為**使用者準備**這很好，等待使用者開始使用。


您可以監視進度的主要**Microsoft 受管理電腦的 [裝置**] 頁面上的裝置註冊。 報告那里可能的狀態包括：

| 狀態 | 描述 |
|---------------|-------------|
| 註冊暫止 | 註冊未尚未完成。 請稍後再回來。 |
| 註冊失敗 | 無法完成註冊。 如需詳細資訊，請參閱[疑難排解裝置註冊](#troubleshooting-device-registration)。 |
| 準備使用者 | 註冊成功，而且裝置已準備好要傳遞給使用者。 Microsoft 受管理的電腦會逐步引導其第一次 」 設定，因此不需要為您進行任何進一步的準備工作。 |
| 作用中 | 裝置已經傳送給使用者，他們必須註冊您的租用戶。 這也表示他們定期使用裝置。 |
| 非使用中 | 裝置已經傳送給使用者，他們必須註冊您的租用戶。 不過，他們有不適用於裝置最近 （過去 7 天）。  | 

#### <a name="troubleshooting-device-registration"></a>疑難排解裝置註冊

| 錯誤訊息 | 詳細資料 |
|---------------|-------------|
| 找不到裝置 | 我們無法註冊此裝置，因為我們找不到相符項目提供的製造商、 模型，或序號。 與您的裝置供應商確認這些值。 |
| 不正確的硬體雜湊 | 您提供此裝置的硬體雜湊格式不正確。 請仔細檢查硬體雜湊，然後重新提交。 |
| 已註冊的裝置 | 此裝置已登錄至您的組織。 不再需要的動作。 |
| 另一個組織所宣告的裝置 | 此裝置已經被另一個組織所宣告。 請與您的裝置供應商。 |
| 未預期的錯誤 | 無法自動處理您的要求。 連絡支援人員，並提供 「 要求識別碼：<requestId> |

### <a name="check-the-image"></a>檢查映像

如果您的裝置有來自 Microsoft 受管理電腦的協力廠商供應商，應正確映像。

如果您想要的話，則您也歡迎使用自行套用映像。 若要開始，請連絡您正在使用的 Microsoft 代表和他們將會提供您的位置與步驟套用映像。

### <a name="deliver-the-device"></a>傳遞裝置

> [!IMPORTANT]
> 您交給裝置使用者之前，請確定您已經取得並套用該使用者的[適當授權](../get-ready/prerequisites.md)。

如果套用所有授權，您可以[讓使用者可使用的裝置](get-started-devices.md)，，然後使用者可以啟動裝置，並且繼續透過 Windows 安裝程式體驗。









