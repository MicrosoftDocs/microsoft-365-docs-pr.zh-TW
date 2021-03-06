---
title: 自行註冊現有裝置
description: 登錄您可能已經使用的裝置，以便透過 Microsoft 受管理的電腦來管理它們。
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: ed254234109bc5ff9865ff49ed3fa0fff8770ab0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286906"
---
# <a name="register-existing-devices-yourself"></a>自行註冊現有裝置

>[!NOTE]
>本主題說明在 Microsoft 受管理的電腦中重複使用已有裝置及註冊裝置的步驟。 如果您使用全新的裝置，請改為在[Microsoft 受管理的電腦自行註冊新裝置](register-devices-self.md)中的步驟。

合作夥伴的程式會記錄在協力廠商，以 [供協力廠商註冊裝置](register-devices-partner.md)。

Microsoft 受管理的電腦可以與全新裝置搭配使用，也可以重複使用已有的裝置 (這會要求您重新) 。 您可以在 Microsoft 端點管理員入口網站中使用 Microsoft 受管理的電腦來註冊裝置。

## <a name="prepare-to-register-existing-devices"></a>準備註冊現有的裝置


若要註冊現有的裝置，請遵循下列步驟：

1. [取得每個裝置的硬體雜湊。](#obtain-the-hardware-hash)
2. [合併雜湊資料](#merge-hash-data)
3. [在 Microsoft 受管理的電腦中註冊裝置](#register-devices-by-using-the-admin-portal)。
4. [再次確認映像是否正確。](#check-the-image)
5. [交付裝置](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>取得硬體雜湊

Microsoft 受管理的電腦會藉由參照其硬體雜湊來唯一識別每個裝置。 您有四個選項可從您已在使用的裝置取得此資訊：

- 請向您的 OEM 提供者索取 AutoPilot 註冊檔案，其中會包含硬體雜湊。
- 在[Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)中收集資訊。
- 在每個裝置上使用[Active Directory](#active-directory-powershell-script-method)或[手動](#manual-powershell-script-method)執行 Windows PowerShell 腳本--並收集檔案中的結果。
- 啟動每個裝置 (但不要完成 Windows 設定體驗)，然後[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

您可以使用 Microsoft Endpoint Configuration Manager，從您要使用 Microsoft 受管理的電腦註冊的現有裝置收集硬體雜湊。

> [!IMPORTANT]
> 您要取得此資訊的任何裝置都必須執行 Windows 10 版本1703或更新版本。 

如果您已符合所有這些必要條件，您可以遵循下列步驟來收集資訊：

1. 在 Configuration Manager 主控台中，選取 [ **監視**]。 
2. 在 [監視] 工作區中，展開 [ **報告** ] 節點、[ **報告**]，然後選取 [ **硬體-一般** ] 節點。 
3. 執行報告、 **Windows Autopilot 裝置資訊**，以及查看結果。
4. 在報表檢視器中，選取 [ **匯出** ] 圖示，然後選擇 **CSV (逗點分隔)** ] 選項。
5. 儲存檔案之後，您必須將結果篩選為您計畫要向其註冊的那些裝置 Microsoft 受管理的電腦，並將資料上傳至 Microsoft 受管理的電腦。 開啟 Microsoft 端點管理員並流覽至 [**裝置**] 功能表，然後尋找 [Microsoft 受管理的電腦] 區段，然後選取 [**裝置**]。 選取 [ **+ 註冊裝置**]，這會開啟飛入以註冊新裝置。


如需詳細資訊，請參閱 [使用系統管理入口網站的註冊裝置](#register-devices-by-using-the-admin-portal) 。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell script 方法

在 Active Directory 環境中，您可以使用 `Get-WindowsAutoPilotInfo` PowerShell Cmdlet，以遠端從 Active Directory 群組中的裝置，使用 WinRM 來收集資訊。 您也可以使用 `Get-AD Computer` Cmdlet，取得目錄中所含特定硬體模型名稱的篩選結果。 繼續之前，請先確認這些必要條件，然後繼續執行下列步驟：

- 已啟用 WinRM。
- 您想要註冊的裝置會在網路 (上使用，也就是說，它們並未中斷連線或關閉) 。
- 請確定您擁有的網域認證參數具有在裝置上遠端執行的許可權。
- 請確定 Windows 防火牆允許存取 WMI。 若要這麼做，請遵循下列步驟：

    1. 開啟 **Windows Defender 防火牆**[控制台]，然後選取 [**允許應用程式或功能透過 Windows Defender 防火牆**]。

    2. 在清單中找出 **Windows 的管理工具 (WMI)** 中，啟用 [**私人] 和 [公用**]，然後選取 **[確定]**。

1. 以系統管理權限開啟 PowerShell 提示字元。

2. 請執行下列其中 *一個* 腳本：

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. 存取任何可能具有裝置專案的目錄。 從 *所有* 目錄移除每個裝置的專案，包括 Windows Server Active Directory 網域服務和 Azure Active Directory。 請注意，移除動作可能需要數小時才能完成處理。

4. 存取管理服務，其中可能有裝置的專案。 從 *所有* 管理服務中移除每個裝置的專案，包括 Microsoft Endpoint Configuration Manager、Microsoft Intune 及 Windows Autopilot。 請注意，移除動作可能需要數小時才能完成處理。

現在您可以繼續 [註冊裝置](#register-devices-by-using-the-admin-portal)。

#### <a name="manual-powershell-script-method"></a>手動 PowerShell script 方法

1. 以系統管理權限開啟 PowerShell 提示字元。
2. 執行 `Install-Script -Name Get-WindowsAutoPilotInfo`
3. 執行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [合併雜湊資料。](#merge-hash-data)

#### <a name="flash-drive-method"></a>快閃磁碟機方法

1. 在您要註冊的裝置以外的裝置上，插入 USB 磁碟機。
2. 以系統管理權限開啟 PowerShell 提示字元。
3. 執行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. 開啟您要註冊的裝置，但 *請勿開始設定體驗*。 如果您不小心開始設定體驗，則必須重設裝置或重新製作其映像。
5. 插入 USB 磁碟機，然後按 SHIFT + F10。
6. 以系統管理權限開啟 PowerShell 提示字元，然後執行 `cd <pathToUsb>`。
7. 執行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 執行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. 移除 USB 磁碟機，然後執行 `shutdown -s -t 0` 以關閉裝置
10. [合併雜湊資料。](#merge-hash-data)

> [!IMPORTANT]
> 在您完成註冊前，請勿開啟您所註冊的裝置。 

### <a name="merge-hash-data"></a>合併雜湊資料

如果您是由手動 PowerShell 或快閃記憶體磁片磁碟機方法收集硬體雜湊資料，您現在必須將 CSV 檔案中的資料組合成單一檔案，才能完成註冊。 以下是可讓您輕鬆使用 PowerShell 腳本的範例：

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

將雜湊資料合併到一個 CSV 檔案中，您現在可以繼續 [註冊裝置](#register-devices-by-using-the-admin-portal)。

## <a name="register-devices-by-using-the-admin-portal"></a>使用管理入口網站註冊裝置

在 [Microsoft 端點管理員](https://endpoint.microsoft.com/)中，選取左導覽窗格中的 [**裝置**]。 尋找功能表的 [Microsoft 受管理的電腦] 區段，然後選取 [**裝置**]。 在 [Microsoft 受管理的電腦裝置] 工作區中，選取 [ **+ 註冊裝置**]，該裝置會開啟飛入以註冊新裝置。

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

請遵循下列步驟：

1. 在 [檔案上傳] 中，提供您先前建立的 CSV 檔案路徑。
2. 在下拉式功能表中選取 [裝置設定檔](../service-description/profiles.md) 。
3. 選取 [註冊裝置]。 系統會將裝置新增至 [裝置] 刀鋒視窗上標示為 [註冊擱置]的裝置清單。 登錄所需的時間通常不會超過10分鐘，當成功時，裝置會顯示為已就緒，可供 **使用者** 使用，且等候使用者開始使用。

> [!NOTE]
> 如果您手動變更裝置的 Azure Active Directory (AAD) 群組成員資格，它會自動重新指派給其裝置設定檔的群組，並將其從任何衝突的群組中移除。

您可以在主頁面上監視裝置註冊的進度。 其回報的可能狀態包括：

| 狀態 | 描述 |
|---------------|-------------|
| 註冊擱置 | 尚未完成註冊。 稍後再回頭檢查。 |
| 註冊失敗 | 無法完成註冊。 如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](#troubleshooting-device-registration)。 |
| 使用者就緒 | 註冊成功，裝置現在可以傳遞給使用者。 Microsoft 受管理的電腦會透過初次設定來引導他們，所以您不需要做進一步的準備。 |
| 作用中 | 裝置已傳遞給使用者，且已向您的承租人註冊。 這也表示使用者經常使用該裝置。 |
| 非作用中 | 裝置已傳遞給使用者，且已向您的承租人註冊。 不過，使用者最近尚未使用裝置 (在過去 7 天內)。  | 

### <a name="troubleshooting-device-registration"></a>針對裝置註冊進行疑難排解

| 錯誤訊息 | 詳細資料 |
|---------------|-------------|
| 找不到裝置 | 我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。 請與您的裝置供應商確認這些值。 |
| 硬體雜湊無效 | 您為這個裝置提供的硬體雜湊格式不正確。 再次確認硬體雜湊，然後重新提交。 |
| 裝置已經註冊 | 此裝置已經註冊到您的組織。 無需採取任何動作。 |
| 其他組織所宣告的裝置 | 此裝置已經由其他組織所宣告。 請洽詢您的裝置供應商。 |
| 未預期的錯誤 | 無法自動處理您的要求。 連絡客戶支援並提供要求識別碼：<requestId> |

## <a name="check-the-image"></a>檢查映像

如果您的裝置來自 Microsoft 受管理的電腦合作夥伴供應商，映射應是正確的。

如果您想要的話，也歡迎您自行套用映像。 若要開始使用，請連絡您的 Microsoft 代表，他們會將映像的位置及其套用步驟提供給您。

## <a name="deliver-the-device"></a>交付裝置

> [!IMPORTANT]
> 將裝置交給使用者之前，請確認您已取得並套用[適合該使用者的授權](../get-ready/prerequisites.md)。

如果已套用所有授權，您可以[讓使用者準備好使用裝置](get-started-devices.md)，然後使用者即可啟動裝置並繼續進行 Windows 設定體驗。
