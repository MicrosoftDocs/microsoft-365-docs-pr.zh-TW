---
title: Microsoft Defender for Endpoint 裝置控制可移動儲存體存取控制
description: 關於 Microsoft Defender for Endpoint 的逐步說明
keywords: 可移動儲存媒體
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cb23987600a5f87a99449510f7651c4fdcd45f66
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028400"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint 裝置控制可移動儲存體存取控制

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint 裝置控制可移動儲存體存取控制可讓您執行下列工作：
- 審核，允許或防止讀取、寫入或執行可移動儲存的讀取、寫入或執行存取（含或不含）

|特權 |權限  |
|---------|---------|
|Access    |  讀取、寫入、執行       |
|動作模式    |    Audit、Allow、防止     |
|CSP 支援   |   是      |
|GPO 支援    |   是      |
|以使用者為基礎的支援     |   是      |
|以機器為基礎的支援    |    是     |

## <a name="prepare-your-endpoints"></a>準備您的端點

在具有反惡意軟體用戶端版本 **4.18.2103.3 或更新** 版本的 Windows 10 裝置上，部署可移動儲存體存取控制。

- **4.18.2104 或更新版本**：新增 SerialNumberId、VID_PID、以 filepath 為基礎的 GPO 支援、ComputerSid

- **4.18.2105 或更新版本**：針對 HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId 新增萬用字元支援、特定電腦上的特定使用者組合、可移動 SSD (SANDISK 至尊 SSD) /USB 連接的 SCSI (UAS) 支援

:::image type="content" source="images/powershell.png" alt-text="PowerShell 介面":::

> [!NOTE]
> Windows 安全性元件都不需要使用中，您可以執行可移動儲存體存取控制，而不限 Windows 安全性狀態。

## <a name="policy-properties"></a>原則屬性

您可以使用下列屬性建立「可移動儲存」群組：

**屬性名稱：群組識別碼**

1. 描述： [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)、唯一識別碼、代表群組，並將用於原則中。

**屬性名稱： DescriptorIdList**

1. 描述：列出您要用來在群組中涵蓋的裝置屬性。
列出您要用來在群組中涵蓋的裝置屬性。
如需每個裝置屬性的詳細資訊，請參閱上述 **裝置** 內容一節。

1. 選項：

    - 主要識別碼
        - RemovableMediaDevices
        - CdRomDevices
    - DeviceId
    - HardwareId
    - InstancePathId： InstancePathId 是唯一識別系統中裝置的字串，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8 .07 \ 8735B611&0。 例如， (**&0**) 代表可用的槽，而且可能會從裝置變更為裝置。 為了獲得最佳結果，請在結尾使用萬用字元。 例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8。 07 \ 8735B611 *
    - FriendlyNameId
    - SerialNumberId
    - Vid
    - Pid
    - VID_PID
        - 0751_55E0：符合此確切的 VID/PID 對
        - _55E0：搭配任何具有 PID = 55E0 的媒體
        - 0751_：搭配任何具有 VID = 0751 的媒體
        
**屬性名稱： MatchType** 

1. 描述：當 DescriptorIDList 中使用多個裝置屬性時，MatchType 會定義關聯性。

1. 選項：

    - MatchAll： DescriptorIdList 下的任何屬性都是 **和** 關聯;例如，如果系統管理員將 DeviceID 和 InstancePathID，用於每個連線的 USB，系統會檢查 USB 是否同時滿足這兩個值。
    - MatchAny： [DescriptorIdList] 底下的屬性將是 **Or** relationship;例如，如果系統管理員為 DeviceID 和 InstancePathID，則對於每個連線的 USB，只要 USB 具有相同的 **DeviceID** 或 **InstanceID** 值，系統就會執行強制執行。

以下是存取控制原則屬性：

**屬性名稱： PolicyRuleId**

1. 描述： [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)、唯一識別碼、代表原則，並將用於報告和疑難排解。

**屬性名稱： IncludedIdList**

2. 描述：將套用原則的群組 (s) 。 如果新增多個群組，則會將原則套用至所有群組中的任何介質。

3. 選項：此實例必須使用群組識別碼/GUID。

下列範例顯示 GroupID 的使用方式：

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

**屬性名稱： ExcludedIDList**

描述：不會將原則套用至的群組 (s) 。

選項：此實例必須使用群組識別碼/GUID。

**屬性名稱：專案識別碼**

1. 描述：一個 PolicyRule 可以有多個專案;每個具有唯一 GUID 的專案都會告訴裝置控制一種限制。

**屬性名稱： Type**

1. 描述：針對 IncludedIDList 中的可移動儲存群組定義動作。
    - 強制執行：允許或拒絕
    - Audit： AuditAllowed 或 AuditDenied 

2. 選項：

    - 允許
    - 拒絕
    - AuditAllowed：定義允許存取時的通知和事件
    - AuditDenied：在存取遭到拒絕時定義通知和事件;必須一起使用 **Deny** 專案。

當同一個媒體有衝突類型時，系統會將原則中的第一個類型。 衝突類型的範例為 **Allow** 和 **Deny**。

**屬性名稱： Sid**

描述：定義是否對特定使用者或使用者群組套用此原則;一個專案最多可以有一個 Sid，而沒有任何 Sid 的專案則表示在機器上套用原則。

**屬性名稱： ComputerSid**

描述：定義是否要將此原則套用到特定機器或機器群組上;一個專案最多可以有一個 ComputerSid，而且沒有任何 ComputerSid 的專案則表示在機器上套用原則。 如果您想要將專案套用至特定使用者和特定的機器，請將 Sid 和 ComputerSid 新增至相同的專案。

**屬性名稱：選項**

描述：定義是否要顯示通知。

   :::image type="content" source="images/device-status.png" alt-text="可看到裝置狀態的畫面":::

選項：0-4。 選取 [類型允許] 或 [拒絕] 時：

   - 0：無
   - 4：停用此專案的 **AuditAllowed** 和 **AuditDenied** 。 即使發生 **封鎖** ，且已設定 **AuditDenied** ，系統就不會顯示通知。

   選取 [類型 **AuditAllowed** ] 或 [ **AuditDenied** ] 時：

   - 0：無
   - 1：顯示通知
   - 2： send 事件
   - 3：顯示通知及傳送事件

**屬性名稱： AccessMask**

描述：定義存取。

選項1-7：
  - 1：讀取
  - 2：寫入
  - 3：讀取和寫入
  - 4：執行
  - 5：讀取和執行
  - 6：寫入和執行
  - 7：讀取和寫入和執行

## <a name="common-removable-storage-access-control-scenarios"></a>常見的可移動儲存體存取控制案例

為了協助您熟悉 Microsoft Defender for Endpoint 可移動儲存體存取控制，我們為您提供下列一些常見案例。

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>案例1：防止寫入和執行所有但允許特定核准 USBs 的存取

1. 建立群組

    1. 群組1：任何「可移動儲存」和「CD/DVD」。 例如，可移動儲存區和 CD/DVD 的範例是： Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the the Group.xmlFile 的 [任何可移動儲存體和 cd dvd](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 。
    
    2. 群組2：根據裝置屬性核准的 USBs。 此使用案例的範例為：範例識別碼– Group **65fa649a-a111-4912-9294-fb6337a25038** In 樣本 [已核准的 USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔。

    > [!NOTE]
    > 您必須以 `&` 值取代 `&amp;` 。

2. 建立原則

    1. 原則1：封鎖寫入和執行存取，但允許核准的 USBs。 此使用案例的範例是： PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** In 範例 [案例1封鎖寫入和執行存取，但允許核准的 USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案。
    
    2. 原則2：對允許的 USBs 的「寫入」和「執行」存取權。 這種使用案例的範例是： PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** In 範例 [案例1的「審核寫入」和「執行核准 USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案的存取」。

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>案例2：審核寫入並執行全部，但封鎖特定的未核准 USBs

1. 建立群組

    1. 群組1：任何「可移動儲存」和「CD/DVD」。 此使用案例的範例是： Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample Group.xmlfile 中的 [任何可移動儲存體和 CD DVD](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)檔案。
    
    2. 群組2：根據裝置屬性（例如，在「未 [核准的 USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)檔案中的「廠商識別碼/產品識別碼」、「易記名稱–群組 **65fa649a-a111-4912-9294-fb6337a25038** 」）進行未核准的 USBs。 

    > [!NOTE]
    > 您必須以 `&` 值取代 `&amp;` 。

2. 建立原則

    1. 原則1：封鎖「寫入」和「執行」許可權，但會封鎖特定的未核准 USBs。 這種使用案例的範例是： PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** In 範例 [案例2的「審核寫入」和「執行」許可權，但會封鎖特定的未核准 USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案。
    
    2. 原則2：對其他人進行審核寫入和執行存取。 這種使用案例的範例是： PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** In 範例 [案例2的「審核寫入」和「執行」 others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案的存取。

## <a name="deploying-and-managing-policy-via-group-policy"></a>透過群組原則部署及管理原則

「可移動儲存體存取控制」功能可讓您透過群組原則將原則套用至使用者或裝置，或同時套用兩者。

### <a name="licensing"></a>授權

開始使用 [可移動儲存體] 存取控制之前，必須先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 若要存取和使用 [可移動儲存體] 存取控制，您必須具有 Microsoft 365 E3 或 Microsoft 365 E5。

### <a name="deploying-policy-via-group-policy"></a>透過群組原則部署原則

1. 將所有群組合並 `<Groups>` `</Groups>` 成一個 xml 檔案。 

    下圖說明案例1的範例 [：防止寫入和執行全部，但允許特定核准的 USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="顯示在裝置上允許特定核准 USBs 之設定設定的畫面":::
    
2. 將所有規則合併 `<PolicyRules>` `</PolicyRules>` 到一個 xml 檔案中。 

    如果您想要限制特定使用者，請使用 SID 屬性進入專案中。 若原則專案中沒有 SID，該專案將會套用到機器的所有使用者登入實例。
    
    下圖說明 SID 內容的使用方式，以及案例1的範例 [：防止寫入權及執行全部，但允許特定核准的 USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="顯示程式碼以指出 SID 屬性屬性用法的畫面":::

3. 在網路共用資料夾上儲存規則和群組 XML 檔案，並將網路共用資料夾路徑放入「群組原則」設定中：「**電腦設定-> 系統管理範本-> Windows 元件-> Microsoft Defender 防毒軟體-> 裝置控制項： ' 定義裝置控制項原則群組」和「定義裝置控制項原則規則**」。

    - 目的機器必須能夠存取網路共用以具備該原則。 不過，在閱讀原則之後，就不再需要網路共用連線，即使機器重新開機也是一樣。

    :::image type="content" source="images/device-control.png" alt-text="裝置控制項畫面":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>透過 Intune OMA-URI 部署及管理原則

「可移動儲存體存取控制」功能可讓您透過 OMA-URI 將原則套用至使用者或裝置，或同時套用兩者。

### <a name="licensing"></a>授權

開始使用 [可移動儲存體] 存取控制之前，必須先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 若要存取和使用 [可移動儲存體] 存取控制，您必須具有 Microsoft 365 E3 或 Microsoft 365 E5。

### <a name="permission"></a>權限

針對 Intune 中的原則部署，帳戶必須具有建立、編輯、更新或刪除裝置設定檔的許可權。 您可以建立自訂角色，或使用具有這些許可權的任何內建角色。

- 原則與設定檔管理員角色
- 已開啟裝置設定檔的「建立/編輯/更新/讀取/刪除/查看報告」許可權的自訂角色
- 全域系統管理員

### <a name="deploying-policy-via-oma-uri"></a>透過 OMA-URI 部署原則

**Microsoft 端點管理員系統管理中心 (https://endpoint.microsoft.com/) > 裝置-> 設定檔-> 建立設定檔-> 平臺： Windows 10 和更新版本 & 設定檔：自訂**

1. 針對每個群組建立 OMA URI 規則：
    - OMA-URI：

      /Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**% 7D/GroupData

      例如，對於範例中的 **任何「可移動儲存」和「CD/DVD」** 群組，連結必須是：

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData

    - 資料類型： String (XML 檔案) 
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="字串資料類型的 xml 檔":::

2. 針對每個原則，也建立 OMA URI：

    - OMA-URI：

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData

      例如，針對 **區塊寫入和執行存取，但允許** 範例中的核准 USBs 規則，該連結必須是： 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.

    - 資料類型： String (XML 檔案) 

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="字串資料類型之 XML 檔案的顯示":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>使用 Intune 使用者介面部署及管理原則

這項功能 (在 Microsoft 端點管理員系統管理中心 (https://endpoint.microsoft.com/) > 裝置 > 設定設定檔 > 建立設定檔 > 平臺： Windows 10 和更新版本 & 設定檔：尚未提供裝置控制項) 。 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>View Device Control 可移動儲存體 Microsoft Defender for Endpoint 中的存取控制資料

Microsoft 365 安全性入口網站顯示由裝置控制項可移動儲存體存取控制封鎖的可拆卸儲存體。 若要存取 Microsoft 365 的安全性，您必須具備下列訂閱：

- E5 報表的 Microsoft 365

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="描述「可移動儲存」之瓶頸的畫面":::

## <a name="frequently-asked-questions"></a>常見問題集
**USBs 最大數目的可拆卸儲存體媒體限制是多少？**

我們已驗證一個具有100000媒體的 USB 群組（大小高達 7 MB）。 原則可在 Intune 和 GPO 中運作，但不會出現效能問題。

**為何原則無法運作？**

最常見的原因是沒有必要的 [反惡意程式碼用戶端版本](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control?view=o365-worldwide#prepare-your-endpoints)。

另一個原因可能是 XML 檔的格式不正確，例如，未使用 XML 檔案中 "&" 字元的正確 markdown 格式，或文字編輯器可能會在導致 XML 分析無法運作的檔案開頭，新增一個位元組順序標記 (BOM) 0xEF 0xBB 0xBF。 一個簡單的解決方案是下載 [範例](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案 (選取 [ **Raw** ]，然後按一下 [ **另存** 新檔]) 然後更新。

如果有值而且原則是透過「群組原則」管理，請檢查用戶端裝置是否可以存取原則 XML 路徑。

**如何知道哪些機器在組織中使用的反惡意軟體用戶端版本已過時？**

您可以使用下列查詢來取得 Microsoft 365 安全性入口網站上的反惡意程式碼用戶端版本：
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```

