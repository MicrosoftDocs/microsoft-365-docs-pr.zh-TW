---
title: 針對 MSCommerce PowerShell 模組使用 AllowSelfServicePurchase
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 瞭解如何使用 AllowSelfServicePurchase PowerShell Cmdlet 來開啟或關閉自助購買服務。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ec5ebe814066916de5cafc176cdcd82bfd416a57
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403687"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>針對 MSCommerce PowerShell 模組使用 AllowSelfServicePurchase

**MSCommerce** PowerShell 模組現在可用於[PowerShell 圖庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)。 此模組包含**AllowSelfServicePurchase**的**PolicyID**參數值，可讓您控制組織中的使用者是否可以進行自助購買。

您可以使用**MSCommerce** PowerShell 模組來：

- 查看**AllowSelfServicePurchase**參數值的預設狀態，不論它是啟用還是停用
- 查看適用產品的清單，以及是否啟用或停用自助購買功能
- 查看或修改特定產品的目前設定，以啟用或停用

## <a name="requirements"></a>需求

若要使用**MSCommerce** PowerShell 模組，您需要：

- Windows 10 裝置
- 裝置的系統管理員許可權
- 您租使用者的全域或計費系統管理員角色

## <a name="install-the-mscommerce-powershell-module"></a>安裝 MSCommerce PowerShell 模組

您可以在 Windows 10 裝置上安裝**MSCommerce** PowerShell 模組一次，然後將其匯入您所開始的每個 PowerShell 會話。 從[PowerShell 庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)下載**MSCommerce** PowerShell 模組。

若要使用**PowerShellGet**安裝**MSCommerce** PowerShell 模組，請執行下列命令：

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>將 MSCommerce 匯入至 PowerShell 會話

在 Windows 10 裝置上安裝模組之後，您可以將它匯入至每個開始的 PowerShell 會話。 若要將其匯入 PowerShell 會話，請執行下列命令：

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>使用您的認證連接至 MSCommerce

若要使用您的認證連接至 PowerShell 模組，請執行下列命令。

```powershell
Connect-MSCommerce
```

此命令會將目前的 PowerShell 會話連接至 Azure Active Directory 租使用者。 命令會提示您輸入您要連線的承租人的使用者名稱和密碼。 如果為您的認證啟用多重要素驗證，您可以使用 [互動式] 選項來登入。

## <a name="view-details-for-allowselfservicepurchase"></a>查看 AllowSelfServicePurchase 的詳細資料

若要根據您的組織，查看**AllowSelfServicePurchase**參數值的描述及預設狀態，請執行下列命令：

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>查看自助購買產品及其狀態的清單

若要查看所有可用自助購買產品的清單，以及每個產品的狀態，請執行下列命令：

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

下表列出可用的產品及其**ProductId**。

| 產品 | ProductId |
|-----------------------------|--------------|
| 每位使用者的電源應用程式 | CFQ7TTC0KP0P |
| 每位使用者的電源自動化 | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>查看或設定 AllowSelfServicePurchase 的狀態

在您查看可供自助購買之產品的清單後，您可以查看或修改特定產品的設定。

若要取得特定產品的原則設定，請執行下列命令：

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

若要啟用特定產品的原則設定，請執行下列命令：

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

若要停用特定產品的原則設定，請執行下列命令：

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>停用 AllowSelfServicePurchase 的範例腳本

下列範例會逐步引導您如何匯入 MSCommerce 模組、以您的帳戶登入、取得自動**MSCommerce**的**ProductId** ，然後針對該產品停用**AllowSelfServicePurchase** 。

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>疑難排解

**問題**

您會看到下列錯誤訊息：

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

這可能是因為舊版本的傳輸層安全性（TLS）。 若要連接此服務，您需要使用 TLS 1.2 或更新版本

**解決方案**

升級到 TLS 1.2：[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
