---
title: 使用 PowerShell 查看 Microsoft 365 授權和服務
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: 說明如何使用 PowerShell 來查看您的 Microsoft 365 組織中提供的授權方案、服務和授權的相關資訊。
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688496"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>使用 PowerShell 查看 Microsoft 365 授權和服務

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

每個 Microsoft 365 訂閱都包含下列元素：

- **授權方案** 這些也稱為「授權方案」或「Microsoft 365 方案」。 授權計畫定義使用者可以使用的 Microsoft 365 服務。 您的 Microsoft 365 訂閱可能包含多個授權計畫。 授權方案範例是 Microsoft 365 E3。
    
- **服務** 這些也稱為服務方案。 服務是每個授權計畫中可用的 Microsoft 365 產品、功能及功能，例如，Exchange Online 和 Microsoft 365 應用程式的 enterprise (先前命名為 Office 365 ProPlus) 。 使用者可以將多個授權指派給他們，以不同授權方案授與不同服務的存取權。
    
- **授權** 每個授權方案都包含您購買的授權數目。 您可以將授權指派給使用者，讓他們可以使用授權方案所定義的 Microsoft 365 服務。 每個使用者帳戶至少需要一個授權方案的授權，這樣他們才能登入 Microsoft 365 並使用服務。
    
您可以使用 Microsoft 365 的 PowerShell，以查看您的 Microsoft 365 組織中可用授權方案、授權及服務的詳細資料。 如需有關不同 Office 365 訂閱中可用之產品、功能和服務的詳細資訊，請參閱 [Office 365 方案選項](https://go.microsoft.com/fwlink/p/?LinkId=691147)。


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
若要查看您目前授權計畫的摘要資訊，以及每個計畫可用的授權，請執行下列命令：
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

結果包含：
  
- **SkuPartNumber：** 顯示您的組織可用的授權方案。 例如，「 `ENTERPRISEPACK` Office 365 企業版 E3」的授權方案名稱。
    
- **已啟用：** 您為特定授權方案購買的授權數目。
    
- **ConsumedUnits：** 您已從特定授權方案中指派給使用者的授權數目。
    
若要查看所有授權方案中可用之 Microsoft 365 服務的詳細資訊，請先顯示您的授權方案清單。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下來，將授權計畫資訊儲存在變數中。

```powershell
$licenses = Get-AzureADSubscribedSku
```

接下來，顯示特定授權方案中的服務。

```powershell
$licenses[<index>].ServicePlans
```

\<index> 是整數，它會指定授權方案的列數，從命令的顯示 `Get-AzureADSubscribedSku | Select SkuPartNumber` 減1。

例如，如果命令的顯示如下 `Get-AzureADSubscribedSku | Select SkuPartNumber` ：

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

顯示 ENTERPRISEPREMIUM 授權方案之服務的命令如下：

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM 是第三列。 因此，索引值為 (3-1) 或2。

如需授權方案的完整清單 (也稱為產品名稱) 、其包含的服務方案及其對應的易記名稱，請參閱 [產品名稱和服務方案識別碼取得授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

>[!Note]
>PowerShell 指令碼可供使用，會自動執行本主題中所述的程序。 具體說來，此腳本可讓您查看及停用 Microsoft 365 組織中的服務，包括 Sway。 如需詳細資訊，請參閱 [使用 PowerShell 停用 Sway 的存取權](disable-access-to-sway-with-microsoft-365-powershell.md)。
>
    
若要查看您目前授權計畫的摘要資訊，以及每個計畫可用的授權，請執行下列命令：
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。
>

結果包含下列資訊：
  
- **AccountSkuId：** 使用語法顯示組織可用的授權方案 `<CompanyName>:<LicensingPlan>` 。  _\<CompanyName>_ 是您在 Microsoft 365 中註冊時所提供的值，且對您的組織而言是唯一的。 _\<LicensingPlan>_ 所有人的值都相同。 例如，在值 `litwareinc:ENTERPRISEPACK` 、公司名稱以及  `litwareinc` 授權方案名稱  `ENTERPRISEPACK` ，也就是 Office 365 企業版 E3 的系統名稱。
    
- **ActiveUnits：** 您為特定授權方案購買的授權數目。
    
- **WarningUnits：** 授權方案中尚未更新，且30天寬限期後會到期的授權數目。
    
- **ConsumedUnits：** 您已從特定授權方案中指派給使用者的授權數目。
    
若要查看所有授權方案中可用之 Microsoft 365 服務的詳細資料，請執行下列命令：
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

下表顯示 Microsoft 365 服務方案及其最常見服務的易記名稱。 您的服務方案清單可能不同。 
  
|**服務計劃**|**描述**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure 版權管理 (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |*先前命名為 Office 365 ProPlus*的 Microsoft 365 應用程式 enterprise ()   <br/> |
| `MCOSTANDARD` <br/> |商務用 Skype Online  <br/> |
| `SHAREPOINTWAC` <br/> |辦公室  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online Plan 2  <br/> |
   
如需授權方案的完整清單 (也稱為產品名稱) 、其包含的服務方案及其對應的易記名稱，請參閱 [產品名稱和服務方案識別碼取得授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

若要查看特定授權方案中可用之 Microsoft 365 服務的詳細資料，請使用下列語法。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

此範例會顯示 litwareinc:ENTERPRISEPACK (Office 365 企業版 E3) 授權方案中可用的服務。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
