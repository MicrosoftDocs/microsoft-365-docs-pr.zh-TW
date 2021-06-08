---
title: Microsoft Defender for Endpoint 裝置控制印表機保護
description: Microsoft Defender for Endpoint 裝置控制印表機保護會封鎖透過非公司的印表機或未經核准的 USB 印表機列印的人員。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809212"
---
# <a name="device-control-printer-protection"></a>裝置控制印表機保護 

Microsoft Defender for Endpoint 裝置控制印表機保護會封鎖透過非公司的印表機或未經核准的 USB 印表機列印的人員。

## <a name="licensing"></a>授權 

在您開始使用印表機保護之前，您應該先[確認您的 Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。 若要存取和使用印表機保護，您必須具備下列各項：

- 功能/原則部署的 Microsoft 365 E3 
- 報表的 Microsoft 365 E5 

## <a name="permission"></a>權限 

針對 Intune 中的原則部署，若要透過 OMA-URI 部署原則，帳戶必須具有建立、編輯、更新或刪除裝置設定檔的許可權。 您可以建立自訂角色，或使用具有下列許可權的任何內建角色：  

- 原則和設定檔管理員角色。 
- 或自訂角色已開啟裝置設定設定檔的「建立/編輯/更新/讀取/刪除/查看報告」許可權  
- 或全域系統管理員

若要查看裝置設定報告，該帳戶必須具有「查看報告」許可權。 您可以建立自訂角色，或使用具有下列許可權的內建角色：  

- 全域安全性系統管理員
- 安全性系統管理員
- 安全性讀取者 

## <a name="prepare-your-endpoints"></a>準備您的端點

請確定您規劃部署印表機保護的 Windows 10 裝置，以符合這些需求。

1. 加入有問必答計畫。

1. 已安裝下列 Windows 更新。 

    - Windows 1809：安裝 Windows 更新[KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) 
    - Windows 1909：安裝 Windows 更新[KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - 若為 Windows 2004 或更新版本 
    
1. 如果您計畫透過「群組原則」來部署原則，裝置必須 MDATP 加入;如果您計畫透過 MEM 部署原則，裝置必須已加入 Intune。

## <a name="deploy-device-control-printer-protection-policy"></a>部署裝置控制印表機保護原則

您可以透過群組原則或 Intune 部署原則。

| 職稱 | 描述 | CSP 支援 | GPO 支援 | 以使用者為基礎的支援 | 以機器為基礎的支援 |
|:--|:--|:--|:--|:--|:--|
|**啟用裝置控制列印限制**|透過非公司的印表機封鎖人員進行列印|是|是|是|是|
|**已核准的 USB 連線列印裝置清單**\*|允許特定的 USB 印表機|是|是|是|是|
|||||||

\*這個原則必須和 **啟用裝置控制列印限制** 一起使用
## <a name="deploy-policy-via-intune"></a>透過 Intune 部署原則 

對於 Intune，目前的裝置控制項印表機保護只支援 OMA URI。

**案例1：透過任何非公司的印表機封鎖人員列印** 

 - 透過機器套用原則： 

    - ./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl 

- 套用原則于使用者： 

    - ./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser 

CSP 支援的字串 `` <enabled/>`` ： 

:::image type="content" source="../../media/customeditrow.png" alt-text="自訂編輯列":::

**案例2：允許特定核准的 USB 印表機**

- 透過機器套用原則： 

    - ./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices 

- 套用原則于使用者： 

    - ./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser  

具有經核准的 USB 印表機透過 ' ApprovedUsbPrintDevices ' 屬性的 CSP 支援字串範例 `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` ： 

:::image type="content" source="../../media/editrow.png" alt-text="編輯列":::

## <a name="deploy-policy-via-group-policy"></a>透過群組原則部署原則 

如果裝置並未加入 Intune，您也可以透過 [群組原則] 來部署原則。 

**案例1：透過任何非公司的印表機封鎖人員列印** 

- 透過機器套用原則： 

    - 電腦設定 > 系統管理範本 > 印表機：啟用裝置控制列印限制 

- 套用原則于使用者： 

    - 使用者設定 > 系統管理範本 > 控制台 > 印表機：啟用裝置控制列印限制 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="啟用裝置列印限制":::
 

**案例2：允許特定核准的 USB 印表機**

- 透過機器套用原則： 

    - 電腦設定 > 系統管理範本 > 印表機：已核准的 USB 連線列印裝置清單 

- 套用原則于使用者：  

    - 使用者設定 > 系統管理範本 > 控制台 > 印表機：已核准的 USB 連線列印裝置清單 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="已核准的 usb 連線列印裝置清單":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>在 Microsoft Defender for Endpoint portal 中查看裝置控制印表機保護資料 

[Microsoft 365 的安全性中心](https://security.microsoft.com)會顯示以上裝置控制印表機保護原則所封鎖的列印。
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="高級搜尋":::
