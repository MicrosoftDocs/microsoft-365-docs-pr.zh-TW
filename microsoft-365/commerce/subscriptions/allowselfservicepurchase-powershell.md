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
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="eab0f-103">針對 MSCommerce PowerShell 模組使用 AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="eab0f-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="eab0f-104">**MSCommerce** PowerShell 模組現在可用於[PowerShell 圖庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)。</span><span class="sxs-lookup"><span data-stu-id="eab0f-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="eab0f-105">此模組包含**AllowSelfServicePurchase**的**PolicyID**參數值，可讓您控制組織中的使用者是否可以進行自助購買。</span><span class="sxs-lookup"><span data-stu-id="eab0f-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="eab0f-106">您可以使用**MSCommerce** PowerShell 模組來：</span><span class="sxs-lookup"><span data-stu-id="eab0f-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="eab0f-107">查看**AllowSelfServicePurchase**參數值的預設狀態，不論它是啟用還是停用</span><span class="sxs-lookup"><span data-stu-id="eab0f-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="eab0f-108">查看適用產品的清單，以及是否啟用或停用自助購買功能</span><span class="sxs-lookup"><span data-stu-id="eab0f-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="eab0f-109">查看或修改特定產品的目前設定，以啟用或停用</span><span class="sxs-lookup"><span data-stu-id="eab0f-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="eab0f-110">需求</span><span class="sxs-lookup"><span data-stu-id="eab0f-110">Requirements</span></span>

<span data-ttu-id="eab0f-111">若要使用**MSCommerce** PowerShell 模組，您需要：</span><span class="sxs-lookup"><span data-stu-id="eab0f-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="eab0f-112">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="eab0f-112">A Windows 10 device</span></span>
- <span data-ttu-id="eab0f-113">裝置的系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="eab0f-113">Administrator permission for the device</span></span>
- <span data-ttu-id="eab0f-114">您租使用者的全域或計費系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="eab0f-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="eab0f-115">安裝 MSCommerce PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="eab0f-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="eab0f-116">您可以在 Windows 10 裝置上安裝**MSCommerce** PowerShell 模組一次，然後將其匯入您所開始的每個 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="eab0f-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="eab0f-117">從[PowerShell 庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)下載**MSCommerce** PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="eab0f-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="eab0f-118">若要使用**PowerShellGet**安裝**MSCommerce** PowerShell 模組，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eab0f-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="eab0f-119">將 MSCommerce 匯入至 PowerShell 會話</span><span class="sxs-lookup"><span data-stu-id="eab0f-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="eab0f-120">在 Windows 10 裝置上安裝模組之後，您可以將它匯入至每個開始的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="eab0f-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="eab0f-121">若要將其匯入 PowerShell 會話，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eab0f-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="eab0f-122">使用您的認證連接至 MSCommerce</span><span class="sxs-lookup"><span data-stu-id="eab0f-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="eab0f-123">若要使用您的認證連接至 PowerShell 模組，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="eab0f-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="eab0f-124">此命令會將目前的 PowerShell 會話連接至 Azure Active Directory 租使用者。</span><span class="sxs-lookup"><span data-stu-id="eab0f-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="eab0f-125">命令會提示您輸入您要連線的承租人的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="eab0f-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="eab0f-126">如果為您的認證啟用多重要素驗證，您可以使用 [互動式] 選項來登入。</span><span class="sxs-lookup"><span data-stu-id="eab0f-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="eab0f-127">查看 AllowSelfServicePurchase 的詳細資料</span><span class="sxs-lookup"><span data-stu-id="eab0f-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="eab0f-128">若要根據您的組織，查看**AllowSelfServicePurchase**參數值的描述及預設狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eab0f-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="eab0f-129">查看自助購買產品及其狀態的清單</span><span class="sxs-lookup"><span data-stu-id="eab0f-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="eab0f-130">若要查看所有可用自助購買產品的清單，以及每個產品的狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eab0f-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="eab0f-131">下表列出可用的產品及其**ProductId**。</span><span class="sxs-lookup"><span data-stu-id="eab0f-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="eab0f-132">產品</span><span class="sxs-lookup"><span data-stu-id="eab0f-132">Product</span></span> | <span data-ttu-id="eab0f-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="eab0f-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="eab0f-134">每位使用者的電源應用程式</span><span class="sxs-lookup"><span data-stu-id="eab0f-134">Power Apps per user</span></span> | <span data-ttu-id="eab0f-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="eab0f-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="eab0f-136">每位使用者的電源自動化</span><span class="sxs-lookup"><span data-stu-id="eab0f-136">Power Automate per user</span></span> | <span data-ttu-id="eab0f-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="eab0f-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="eab0f-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="eab0f-138">Power BI Pro</span></span> | <span data-ttu-id="eab0f-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="eab0f-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="eab0f-140">查看或設定 AllowSelfServicePurchase 的狀態</span><span class="sxs-lookup"><span data-stu-id="eab0f-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="eab0f-141">在您查看可供自助購買之產品的清單後，您可以查看或修改特定產品的設定。</span><span class="sxs-lookup"><span data-stu-id="eab0f-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="eab0f-142">若要取得特定產品的原則設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eab0f-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="eab0f-143">若要啟用特定產品的原則設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eab0f-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="eab0f-144">若要停用特定產品的原則設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eab0f-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="eab0f-145">停用 AllowSelfServicePurchase 的範例腳本</span><span class="sxs-lookup"><span data-stu-id="eab0f-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="eab0f-146">下列範例會逐步引導您如何匯入 MSCommerce 模組、以您的帳戶登入、取得自動**MSCommerce**的**ProductId** ，然後針對該產品停用**AllowSelfServicePurchase** 。</span><span class="sxs-lookup"><span data-stu-id="eab0f-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="eab0f-147">疑難排解</span><span class="sxs-lookup"><span data-stu-id="eab0f-147">Troubleshooting</span></span>

<span data-ttu-id="eab0f-148">**問題**</span><span class="sxs-lookup"><span data-stu-id="eab0f-148">**Problem**</span></span>

<span data-ttu-id="eab0f-149">您會看到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="eab0f-149">You see the following error message:</span></span>

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

<span data-ttu-id="eab0f-150">這可能是因為舊版本的傳輸層安全性（TLS）。</span><span class="sxs-lookup"><span data-stu-id="eab0f-150">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="eab0f-151">若要連接此服務，您需要使用 TLS 1.2 或更新版本</span><span class="sxs-lookup"><span data-stu-id="eab0f-151">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="eab0f-152">**解決方案**</span><span class="sxs-lookup"><span data-stu-id="eab0f-152">**Solution**</span></span>

<span data-ttu-id="eab0f-153">升級到 TLS 1.2：[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="eab0f-153">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
