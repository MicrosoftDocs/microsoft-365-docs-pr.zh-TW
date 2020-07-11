---
title: 自行註冊現有裝置
description: 登錄已重新使用的裝置，使其可由 Microsoft 受管理的電腦進行管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: abe9e63eb4fcd31993bd26822dc445ff0e48e369
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101482"
---
# <a name="register-existing-devices-yourself"></a>自行註冊現有裝置

>[!NOTE]
>本主題說明重新使用已有的裝置的步驟，並在 Microsoft 受管理的電腦中註冊這些裝置。 如果您正在使用全新的裝置，請依照直接在[Microsoft 管理的桌面中註冊新裝置](register-devices-self.md)中的步驟進行。

合作夥伴的程式會記錄在協力廠商，以[供協力廠商註冊裝置](register-devices-partner.md)。

Microsoft 受管理的電腦可搭配全新的裝置運作，或您可重複使用您可能已經擁有的裝置 (這需要您重新製作其映像)。 您可以使用 Microsoft Managed Desktop Admin 入口網站來註冊裝置。

## <a name="prepare-to-register-existing-devices"></a>準備註冊現有的裝置


若要註冊現有的裝置，請遵循下列步驟：

1. [取得每個裝置的硬體雜湊。](#obtain-the-hardware-hash)
2. [合併雜湊資料](#merge-hash-data)
3. [在 Microsoft 受管理的電腦中註冊裝置](#register-devices)。
4. [再次確認映像是否正確。](#check-the-image)
5. [交付裝置](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>取得硬體雜湊

Microsoft 受管理的電腦會藉由參照其硬體雜湊來唯一識別每個裝置。 您有四個選項可從您已在使用的裝置取得此資訊：

- 請向您的 OEM 提供者索取 AutoPilot 註冊檔案，其中會包含硬體雜湊。
- 在[Configuration Manager](#configuration-manager)中建立自訂報告。
- 在每個裝置上使用[Active Directory](#active-directory-powershell-script-method)或[手動](#manual-powershell-script-method)執行 Windows PowerShell script--並收集檔案中的結果。
- 啟動每個裝置 (但不要完成 Windows 設定體驗)，然後[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。

#### <a name="configuration-manager"></a>Configuration Manager

您可以使用 Microsoft 端點 Configuration Manager 來收集您要使用 Microsoft Managed Desktop 註冊的現有裝置的硬體雜湊。

> [!IMPORTANT]
> 您要取得此資訊的任何裝置都必須執行 Windows 10、版本1703或更新版本。 您也需要一個裝置，該裝置會連接到設定管理員 (目前的分支) 網站。 您也需要在啟用 SQL Server Reporting Services 的環境中設定報告點網站系統角色。 

如果您已符合所有這些必要條件，您可以遵循下列步驟來收集資訊：

1. 在 Configuration Manager 主控台中，選取 [**監視**]。 
2. 在 [監視] 工作區中，展開 [**報告**]，然後選取 [**報告**]。 
3. 在 [**首頁**] 索引標籤上，選取 [**建立**] 區段中的 [**建立報告**] 以開啟 [建立報表] 嚮導。 
4. 在 [**資訊**] 頁面上，設定下列設定： 
    - **名稱：** 指定報表的名稱。 
    - **描述：** 指定報表的描述。 
    - **伺服器：** 顯示您要建立此報告的報表伺服器名稱。 
    - **路徑：** 選取 **[流覽]** 以指定您要用來儲存報告的資料夾。 
5. 選取 [下一步]****。 
6. 在 [**摘要**] 頁面上，複查設定。 選取 [**上一**步] 以變更設定，或選取 **[下一步]** 以在 Configuration Manager 中建立報告。 
7. 在 [**完成**] 頁面上，選取 [關閉]，**結束**嚮導並開啟**報表**產生器以輸入報表設定。 出現提示時，請輸入您的使用者帳戶和密碼，然後選取 **[確定]。** 如果裝置上未安裝報表建立器，系統會提示您進行安裝。 選取 [執行]，以安裝修改及建立報表所需的**報表**產生器。 


**在 Microsoft Report Builder 中**，提供報表的 SQL 語句，然後遵循下列步驟：

1. 在左窗格中，選取 [**資料集**]，然後以滑鼠右鍵按一下以**新增資料集**。
2. 移至 [**查詢**] 索引標籤，然後輸入名稱為*DataSet0*。 
3. 選取 [**使用內嵌在我的報表中的資料集**];報表建立器隨即開啟。
4. 在**報表**建立器中，選取 [**資料來源：**]。 選取 [預設資料來源]，其開頭應為 "AutoGen"。 
5. 選擇 [**查詢類型] 做為 [文字**]，然後輸入下列查詢：




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




5. 流覽至 [**欄位**] 索引標籤， **Field Name** Wehre 功能變數名稱和**欄位來源**的值應該已經填滿。 如果不是，請選取 [**新增**]，然後選取 [**查詢欄位**]。 輸入功能變數名稱**和****欄位來源**。
6. 針對下列每個值重複： 
    - 製造商 
    - Model 
    - Serial_Number 
    - HardwareHash
7. 選取 **[確定]**。

**接下來，依照下列步驟定義報告顯示並建立報告**：

1. 選取**表格或矩陣**;隨即會開啟新的嚮導。
2. 在 **[選擇資料集**] 中，選取 **[選擇此報告中的現有資料集] 或 [共用資料集**]。  
3. 選取 [ **DataSet0** (預設) ]，然後選取 **[下一步]**。
4. 將**Manufacturer**、 **Model**和**序數**拖曳至 [**列群組**] 方塊中。 將**HardwareHash**拖曳至 [**值**] 方塊中，然後選取 **[下一步]**。
5. 清除 [**顯示小計和**總計] 的核取方塊，然後**展開/折疊群組**。 選取 [下一步]****。
6. Select **Finish**.
7. 選取 [**執行**] 執行您的報表。 驗證報告是否提供您預期的資訊。 如有必要，請選取 [**設計**] 以回到設計檢視，以修改報告。
8. 選取 [**儲存**]，將報告儲存至報表伺服器。 您可以在監控工作區的 [報表] 節點中執行新報告。 

**最後，請遵循下列步驟，匯出報表並使用它來註冊裝置**。  (如果您已在先前的步驟之後流覽過，您只需要遵循本節中的步驟1和2。 ) ：

1. 在 Configuration Manager 主控台中，選取 [**監視**]。
2. 在 [**監視**] 中，展開 [**報告**]，然後選取 [**報告**]。
3. 使用您先前建立的名稱尋找報表。
4. 以滑鼠右鍵按一下此報告，然後選取 [**執行**]。
5. 在開啟的對話方塊中，選取 [**匯出**]，然後選取 [**另存為 CSV**]。
6. 這個報告版本會從 Configuration Manager 通訊的所有 Windows 10 裝置提取雜湊。 您將需要篩選結果，只顯示您計畫要向 Microsoft Managed Desktop 註冊的裝置。


> [!IMPORTANT]
> Configuration Manager 中的查詢不允許匯出的欄名稱中包含空格;這就是步驟您可以輸入 "Serial_Number" 和 "HardwareHash" 的原因。 現在，您已匯出 CSV 檔案，您必須編輯報告標頭，以讀取如下所示的*序號*和*硬體雜湊*，然後再繼續進行裝置註冊。

現在您可以[使用管理入口網站繼續註冊裝置](#register-devices-by-using-the-admin-portal)。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell script 方法

在 Active Directory 環境中，您可以使用 `Get-MMDRegistrationInfo` PowerShell Cmdlet，以遠端從 Active Directory 群組中的裝置，使用 WinRM 來收集資訊。 您也可以使用 `Get-AD Computer` Cmdlet，取得目錄中所含特定硬體模型名稱的篩選結果。 若要這麼做，請先確認這些必要條件，然後繼續執行下列步驟：

- 已啟用 WinRM。
- 您想要註冊的裝置會在網路 (上使用，也就是說，它們並未中斷連線或關閉) 。
- 請確定您擁有的網域認證參數具有在裝置上遠端執行的許可權。
- 請確定 Windows 防火牆允許存取 WMI。 若要這麼做，請遵循下列步驟：
    1. 開啟 [ **Windows Defender 防火牆**] 控制台，然後選取 [**允許透過 Windows defender 防火牆的應用程式或功能**]。
    2. 找到**Windows Management Instrumentation (WMI) **在清單中，啟用 [**私人] 和 [公用**]，然後選取 **[確定]**。

1.  以系統管理權限開啟 PowerShell 提示字元。
2.  請執行下列其中*一個*腳本：
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. 存取任何可能具有裝置專案的目錄。 從*所有*目錄中移除每個裝置的專案，包括 Windows Server Active Directory 網域服務和 Azure Active directory。 請注意，此移除動作可能需要數小時才能完成處理。
4. 存取管理服務，其中可能有裝置的專案。 從*所有*管理服務（包括 Microsoft Endpoint Configuration Manager、Microsoft Intune 及 Windows Autopilot）中移除每個裝置的專案。 請注意，此移除動作可能需要數小時才能完成處理。

現在您可以繼續[註冊裝置](#register-devices)。

#### <a name="manual-powershell-script-method"></a>手動 PowerShell script 方法

1.  以系統管理權限開啟 PowerShell 提示字元。
2.  執行 `Install-Script -Name Get-MMDRegistrationInfo`
3.  執行 `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [合併雜湊資料。](#merge-hash-data)

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
10. [合併雜湊資料。](#merge-hash-data)

>[!IMPORTANT]
>在您完成註冊前，請勿開啟您所註冊的裝置。 



### <a name="merge-hash-data"></a>合併雜湊資料

如果您是由手動 PowerShell 或快閃記憶體磁片磁碟機方法收集硬體雜湊資料，您現在必須將 CSV 檔案中的資料組合成單一檔案，才能完成註冊。 以下是讓註冊變輕鬆的範例 PowerShell 指令碼：

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

將雜湊資料合併到一個 CSV 檔案中，您現在可以繼續[註冊裝置](#register-devices)。

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

#### <a name="register-devices-by-using-the-admin-portal"></a>使用管理入口網站註冊裝置

從 Microsoft Managed Desktop [Admin 入口網站](https://aka.ms/mmdportal)的左側流覽窗格中，選取 [**裝置**]。 選取 [+ 註冊裝置]****；飛入視窗隨即開啟：

[![在選取 [註冊裝置] 之後飛入，並列出裝置與已指派使用者、序號、狀態、上次查看日期和年限等欄](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


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









