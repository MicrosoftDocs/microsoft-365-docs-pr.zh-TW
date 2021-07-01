---
title: 取得基本行動裝置及安全性受管理裝置的詳細資料
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用 Windows PowerShell 以取得組織中基本行動及安全性裝置的詳細資料。
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228168"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>取得基本行動裝置及安全性受管理裝置的詳細資料

本文說明如何使用 Windows PowerShell，以取得您為基本行動性和安全性設定之組織中裝置的詳細資料。

以下是您可以使用的裝置詳細資料明細。

|**Detail**|**在 PowerShell 中要尋找的專案**|
|:----------------|:------------------------------------------------------------------------------|
|裝置已註冊基本行動性和安全性。 如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)|IsManaged 參數的值 **   為：<br/>**True**= 裝置已註冊。<br/>**False**= 裝置未註冊。 |
|裝置符合您的裝置安全性原則。 如需詳細資訊，請參閱 [建立裝置安全性原則](create-device-security-policies.md)|IsCompliant 參數的值 **   為：<br/>**True**  = 裝置符合原則。<br/>**False**  = device 與原則不符。|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本行動性及安全性 PowerShell 參數":::

> [!NOTE]
> 本文中的命令和腳本也會傳回 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)所管理之任何裝置的詳細資料。

## <a name="before-you-begin"></a>開始之前

您必須設定一些事項，才能執行本文所述的命令和腳本。

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>步驟1：下載並安裝 Windows PowerShell 的 Azure Active Directory 模組

如需這些步驟的詳細資訊，請參閱 [連線 to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell)。

1. 移至 [IT 專業人員的 Microsoft Online services Sign-In Assistant] RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)   ，然後選取 [ **下載 microsoft online services**] 登入小幫手。

2. 以下列步驟安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：

    1. 開啟管理員層級的 PowerShell 命令提示字元。

    2. 執行 `Install-Module MSOnline` 命令。

    3. 如果系統提示您安裝 NuGet 提供者，請輸入 Y，然後按 ENTER 鍵。

    4. 如果系統提示您從 PSGallery 安裝模組，請輸入 Y，然後按 ENTER 鍵。

    5. 安裝完成後，請關閉 PowerShell 命令視窗。

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>步驟2：連線 Microsoft 365 訂閱

1. 在 Windows PowerShell 的 Windows Azure Active Directory 模組中，執行下列命令。

   ```powershell
   $UserCredential = Get-Credential
   ```

2. 在 [Windows PowerShell 認證要求] 對話方塊中，輸入 Microsoft 365 全域管理員帳戶的使用者名稱和密碼，然後選取 **[確定]**。

3. 執行下列指令：

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>步驟3：請確定您可以執行 PowerShell 腳本

> [!NOTE]
> 如果您已設定為執行 PowerShell 腳本，可以略過此步驟。

若要執行 Get-MsolUserDeviceComplianceStatus.ps1 腳本，您必須啟用執行 PowerShell 腳本。

1. 從您的 Windows 桌面，選取 [ **開始**]，然後輸入 Windows PowerShell。 以滑鼠右鍵按一下 [Windows PowerShell]，然後選取 [以 **系統管理員身分執行**]。

2. 執行下列指令：

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. 出現提示時，請輸入 Y，然後按 Enter 鍵。

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>執行 Get-MsolDevice Cmdlet 以顯示組織中所有裝置的詳細資料

1. 開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

2. 執行下列指令：

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

如需更多範例，請參閱  [MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)。

## <a name="run-a-script-to-get-device-details"></a>執行腳本以取得裝置詳細資料

首先，將腳本儲存至您的電腦。

1. 在記事本中複製並貼上下列文字。

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. 使用副檔名 .ps1 將其儲存為 Windows PowerShell 腳本檔案;例如，Get-MsolUserDeviceComplianceStatus.ps1。

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>執行腳本以取得單一使用者帳戶的裝置資訊

1. 開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

2. 移至您用來儲存腳本的資料夾。 例如，如果您將其儲存至 C:\PS-Scripts，請執行下列命令。

   ```powershell
   cd C:\PS-Scripts
   ```

3. 執行下列命令，識別您想要取得設備詳細資料的使用者。 此範例會取得 bar@example.com 的詳細資料。

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. 執行下列命令以啟動腳本。

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

此資訊會以 CSV 檔案形式匯出至您的 Windows 桌面。 您可以使用其他參數來指定 CSV 的檔案名和路徑。

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>執行腳本以取得使用者群組的裝置資訊

1. 開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

2. 移至您用來儲存腳本的資料夾。 例如，如果您將其儲存至 C:\PS-Scripts，請執行下列命令。

   ```powershell
   cd C:\PS-Scripts
   ```

3. 執行下列命令，識別您要取得設備詳細資料的群組。 此範例會取得 FinanceStaff 群組中使用者的詳細資料。

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. 執行下列命令以啟動腳本。

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

此資訊會以 CSV 檔案形式匯出至您的 Windows 桌面。 您可以使用其他參數來指定 CSV 的檔案名和路徑。

## <a name="related-topics"></a>相關主題

[已停用 Microsoft 連線](/collaborate/connect-redirect)

[基本行動與安全性概觀](overview.md)

[MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
