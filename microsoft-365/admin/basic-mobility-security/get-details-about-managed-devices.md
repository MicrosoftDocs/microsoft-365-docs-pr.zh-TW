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
ms.openlocfilehash: 7cb2369c9a31210f26db12b0453e7a4228e1cccc
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782438"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>取得基本行動裝置及安全性受管理裝置的詳細資料

本文說明如何使用 Windows PowerShell，以取得您為基本行動性和安全性設定之組織中裝置的詳細資料。

以下是您可以使用的裝置詳細資料明細。

|**Detail**|**在 PowerShell 中要尋找的專案**|
|:----------------|:------------------------------------------------------------------------------|
|裝置已註冊基本行動性和安全性。 如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)|IsManaged 參數的值 **   為：<br/>**True**= 裝置已註冊。<br/>**False**= 裝置未註冊。 |
|裝置符合您的裝置安全性原則。 如需詳細資訊，請參閱 [建立裝置安全性原則](create-device-security-policies.md)|IsCompliant 參數的值 **   為：<br/>**True**  = 裝置符合原則。<br/>**False**  = device 與原則不符。|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本行動性及安全性 PowerShell 參數":::

>[!NOTE]
>本文中的命令和腳本也會傳回 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)所管理之任何裝置的詳細資料。

## <a name="before-you-begin"></a>開始之前

您必須設定一些事項，才能執行本文所述的命令和腳本。

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>步驟1：下載並安裝 Windows PowerShell 的 Azure Active Directory 模組

如需這些步驟的詳細資訊，請參閱 [連線 to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell)。

1. 移至 [IT 專業人員的 Microsoft Online services Sign-In Assistant] RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)   ，然後選取 [ **下載 microsoft online services**] 登入小幫手。

2. 以下列步驟安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：

    1. 開啟管理員層級的 PowerShell 命令提示字元。  

    2. 執行 Install-Module MSOnline 命令。

    3. 如果系統提示您安裝 NuGet 提供者，請輸入 Y，然後按 ENTER 鍵。

    4. 如果系統提示您從 PSGallery 安裝模組，請輸入 Y，然後按 ENTER 鍵。

    5. 安裝完成後，請關閉 PowerShell 命令視窗。

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>步驟2：連線 Microsoft 365 訂閱

1. 在 Windows PowerShell 的 Windows Azure Active Directory 模組中，執行下列命令。  

    $UserCredential = Get-Credential

2. 在 [Windows PowerShell 認證要求] 對話方塊中，輸入 Microsoft 365 全域管理員帳戶的使用者名稱和密碼，然後選取 **[確定]**。

3. 執行下列命令。

    Connect-MsolService-身分 $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>步驟3：請確定您可以執行 PowerShell 腳本

>[!NOTE]
>如果您已設定為執行 PowerShell 腳本，可以略過此步驟。

若要執行 Get-MsolUserDeviceComplianceStatus.ps1 腳本，您必須啟用執行 PowerShell 腳本。

1. 從您的 Windows 桌面，選取 [ **開始**]，然後輸入 Windows PowerShell。 以滑鼠右鍵按一下 [Windows PowerShell]，然後選取 [以 **系統管理員身分執行**]。

2. 執行下列命令。

    Set-ExecutionPolicy RemoteSigned

3. 出現提示時，請輸入 Y，然後按 Enter 鍵。

**執行 Get-MsolDevice Cmdlet 以顯示組織中所有裝置的詳細資料**

1. 開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。  

2. 執行下列命令。

    Get-MsolDevice-ReturnRegisteredOwners |Where-Object {$ _。RegisteredOwners-gt 0}

如需更多範例，請參閱  [MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)。

## <a name="run-a-script-to-get-device-details"></a>執行腳本以取得裝置詳細資料

首先，將腳本儲存至您的電腦。

1. 在記事本中複製並貼上下列文字。  

2.  param (

3.  [PSObject []] $users = @ () ，

4.  [切換] $export，

5.  [String] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date 格式 "yyMMdd_HHMMss" ) + ".csv"

6.  [字串] $exportPath = [環境]：： GetFolderPath ( "Desktop" ) 

7.  )

9.  [System.Collections.IDictionary] $script： schema = @ {

11.  DeviceId = ' '

12.  DeviceOSType = ' '

13.  DeviceOSVersion = ' '

14.  DeviceTrustLevel = ' '

15.  DisplayName = ' '

16.  IsCompliant = ' '

17.  IsManaged = ' '

18.  ApproximateLastLogonTimestamp = ' '

19.  DeviceObjectId = ' '

20.  RegisteredOwnerUpn = ' '

21.  RegisteredOwnerObjectId = ' '
    

22.  RegisteredOwnerDisplayName = ' '
    

23.  }
    

25.  函數 createResultObject
    

26.  {
    

28.  [PSObject] $resultObject = New-Object TypeName PSObject-Property $script：架構
    

30.  退回 $resultObject
    

31.  }
    

33.  如果 ($users。計數-eq 0) 
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject []] $result = foreach ($u $users) 
    

39.  {
    

41.  [PSObject] $devices = msoldevice-RegisteredOwnerUpn $u。 UserPrincipalName
    

42.  $devices) 中的 foreach ($d
    

43.  {
    

44.  [PSObject] $deviceResult = createResultObject
    

45.  $deviceResult DeviceId = $d DeviceId
    

46.  $deviceResult。 DeviceOSType = $d DeviceOSType
    

47.  $deviceResult。 DeviceOSVersion = $d DeviceOSVersion
    

48.  $deviceResult。 DeviceTrustLevel = $d DeviceTrustLevel
    

49.  $deviceResult。 DisplayName = $d。 DisplayName
    

50.  $deviceResult。 IsCompliant = $d IsCompliant
    

51.  $deviceResult。 IsManaged = $d IsManaged
    

52.  $deviceResult。 DeviceObjectId = $d ObjectId
    

53.  $deviceResult。 RegisteredOwnerUpn = $u UserPrincipalName
    

54.  $deviceResult。 RegisteredOwnerObjectId = $u ObjectId
    

55.  $deviceResult。 RegisteredOwnerDisplayName = $u DisplayName
    

56.  $deviceResult。 ApproximateLastLogonTimestamp = $d ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  如果 ($export) 
    

64.  {
    

65.  $result |Export-Csv-path ($exportPath + " \" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  使用副檔名 .ps1 將其儲存為 Windows PowerShell 腳本檔案;例如，Get-MsolUserDeviceComplianceStatus.ps1。   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>執行腳本以取得單一使用者帳戶的裝置資訊

1. 開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。
    
2. 移至您用來儲存腳本的資料夾。 例如，如果您將其儲存至 C:\PS-Scripts，請執行下列命令。
    
    cd C:\PS-Scripts

3. 執行下列命令，識別您想要取得設備詳細資料的使用者。 此範例會取得 bar@example.com 的詳細資料。
    
    $u = Get-MsolUser UserPrincipalName bar@example.com

4. 執行下列命令以啟動腳本。

    .\Get-MsolUserDeviceComplianceStatus.ps1-使用者 $u 匯出

此資訊會以 CSV 檔案形式匯出至您的 Windows 桌面。 您可以使用其他參數來指定 CSV 的檔案名和路徑。

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>執行腳本以取得使用者群組的裝置資訊

1. 開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。
    
2. 移至您用來儲存腳本的資料夾。 例如，如果您將其儲存至 C:\PS-Scripts，請執行下列命令。   

    cd C:\PS-Scripts

3. 執行下列命令，識別您要取得設備詳細資料的群組。 此範例會取得 FinanceStaff 群組中使用者的詳細資料。 

    $u = Get-MsolGroupMember-SearchString "FinanceStaff" |% {Get-MsolUser-ObjectId $ _。ObjectId}

4. 執行下列命令以啟動腳本。

    .\Get-MsolUserDeviceComplianceStatus.ps1-使用者 $u 匯出

此資訊會以 CSV 檔案形式匯出至您的 Windows 桌面。 您可以使用其他參數來指定 CSV 的檔案名和路徑。

## <a name="related-topics"></a>相關主題

[已停用 Microsoft 連線](/collaborate/connect-redirect)

[基本行動與安全性概觀](overview.md)

[MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)