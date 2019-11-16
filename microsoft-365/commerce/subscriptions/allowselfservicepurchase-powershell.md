---
title: 若要啟用或停用自助購買使用 AllowSelfServicePurchase
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 了解如何使用 AllowSelfServicePurchase PowerShell 指令程式來開啟或關閉自助購買。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9093e018ed24a9e9735f5b6b71084246967cb59d
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676263"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>AllowSelfServicePurchase 用於 MSCommerce PowerShell 模組

現在使用[PowerShell 資源庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)上**MSCommerce** PowerShell 模組。 模組包含**AllowSelfServicePurchase** ，可讓您控制您組織中的使用者是否可以讓自助購買**PolicyID**參數值。

您可以使用**MSCommerce** PowerShell 模組：

- 檢視**AllowSelfServicePurchase**參數值的預設狀態 — 是否已啟用或停用
- 檢視清單中的適用產品與是否啟用或停用自助購買
- 檢視或修改特定產品的啟用或停用它目前的設定

## <a name="requirements"></a>需求

若要使用**MSCommerce** PowerShell 模組，您需要：

- Windows 10 裝置
- 裝置的系統管理員權限
- 您的租用戶的全域或計費系統管理員角色

## <a name="install-the-mscommerce-powershell-module"></a>安裝 MSCommerce PowerShell 模組

您一次安裝在 Windows 10 裝置上的 [ **MSCommerce** PowerShell 模組，並再將其匯入您啟動每個 PowerShell 工作階段。 從[PowerShell 資源庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)下載**MSCommerce** PowerShell 模組。

若要使用**PowerShellGet**安裝**MSCommerce** PowerShell 模組，請執行下列命令：

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>MSCommerce 匯入 PowerShell 工作階段

在 Windows 10 裝置上安裝模組之後，再匯入您啟動每個 PowerShell 工作階段。 若要將其匯入 PowerShell 工作階段，執行下列命令：

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>使用您的認證連線至 MSCommerce

若要連接至您的認證之 PowerShell 模組，請執行下列命令。

```powershell
Connect-MSCommerce
```

此命令會連線到 Azure Active Directory 租用戶目前 PowerShell 工作階段。 此命令會提示您輸入使用者名稱和密碼，您想要連線至租用戶。 如果您的認證啟用多重要素驗證，則您可以使用 [互動] 選項登入]。

## <a name="view-details-for-allowselfservicepurchase"></a>AllowSelfServicePurchase 檢視詳細資料

若要檢視的描述**AllowSelfServicePurchase**參數值和預設狀態，根據您的組織，執行下列命令：

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>檢視清單中的自助購買產品以及其狀態

若要檢視所有可用的自助購買產品和每個狀態的清單，請執行下列命令：

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

下表列出可用的產品和其**ProductId**。

| 產品 | ProductId |
|-----------------------------|--------------|
| 每位使用者的電源應用程式 | CFQ7TTC0KP0P |
| 每位使用者的電源自動化 | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>檢視或設定 AllowSelfServicePurchase 狀態

檢視可供自助購買的產品清單之後，您可以檢視或修改某項特定產品的設定。

若要取得特定產品的原則設定，請執行下列命令：

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

若要啟用特定產品的原則設定，請執行下列命令：

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

若要停用某項特定產品的原則設定，請執行下列命令：

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>若要停用 AllowSelfServicePurchase 的範例指令碼

下列範例會引導您逐步完成如何匯入**MSCommerce**模組，使用您的帳戶登入，取得**ProductId** Power 自動化，，然後停用**AllowSelfServicePurchase**該產品。

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->