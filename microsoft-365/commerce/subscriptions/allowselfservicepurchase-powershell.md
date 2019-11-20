---
title: AllowSelfServicePurchase 用於 MSCommerce PowerShell 模組
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
ms.openlocfilehash: cb035294ff7f6007e73464f88fc69376fc5b8cc1
ms.sourcegitcommit: b535fe233234fd25146cfe15478e20d954f71e03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2019
ms.locfileid: "38748244"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="0dfa0-103">AllowSelfServicePurchase 用於 MSCommerce PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="0dfa0-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="0dfa0-104">現在使用[PowerShell 資源庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)上**MSCommerce** PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="0dfa0-105">模組包含**AllowSelfServicePurchase** ，可讓您控制您組織中的使用者是否可以讓自助購買**PolicyID**參數值。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="0dfa0-106">您可以使用**MSCommerce** PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="0dfa0-107">檢視**AllowSelfServicePurchase**參數值的預設狀態 — 是否已啟用或停用</span><span class="sxs-lookup"><span data-stu-id="0dfa0-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="0dfa0-108">檢視清單中的適用產品與是否啟用或停用自助購買</span><span class="sxs-lookup"><span data-stu-id="0dfa0-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="0dfa0-109">檢視或修改特定產品的啟用或停用它目前的設定</span><span class="sxs-lookup"><span data-stu-id="0dfa0-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="0dfa0-110">需求</span><span class="sxs-lookup"><span data-stu-id="0dfa0-110">Requirements</span></span>

<span data-ttu-id="0dfa0-111">若要使用**MSCommerce** PowerShell 模組，您需要：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="0dfa0-112">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="0dfa0-112">A Windows 10 device</span></span>
- <span data-ttu-id="0dfa0-113">裝置的系統管理員權限</span><span class="sxs-lookup"><span data-stu-id="0dfa0-113">Administrator permission for the device</span></span>
- <span data-ttu-id="0dfa0-114">您的租用戶的全域或計費系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="0dfa0-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="0dfa0-115">安裝 MSCommerce PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="0dfa0-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="0dfa0-116">您一次安裝在 Windows 10 裝置上的 [ **MSCommerce** PowerShell 模組，並再將其匯入您啟動每個 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="0dfa0-117">從[PowerShell 資源庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)下載**MSCommerce** PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="0dfa0-118">若要使用**PowerShellGet**安裝**MSCommerce** PowerShell 模組，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="0dfa0-119">MSCommerce 匯入 PowerShell 工作階段</span><span class="sxs-lookup"><span data-stu-id="0dfa0-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="0dfa0-120">在 Windows 10 裝置上安裝模組之後，再匯入您啟動每個 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="0dfa0-121">若要將其匯入 PowerShell 工作階段，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="0dfa0-122">使用您的認證連線至 MSCommerce</span><span class="sxs-lookup"><span data-stu-id="0dfa0-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="0dfa0-123">若要連接至您的認證之 PowerShell 模組，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="0dfa0-124">此命令會連線到 Azure Active Directory 租用戶目前 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="0dfa0-125">此命令會提示您輸入使用者名稱和密碼，您想要連線至租用戶。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="0dfa0-126">如果您的認證啟用多重要素驗證，則您可以使用 [互動] 選項登入]。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="0dfa0-127">AllowSelfServicePurchase 檢視詳細資料</span><span class="sxs-lookup"><span data-stu-id="0dfa0-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="0dfa0-128">若要檢視的描述**AllowSelfServicePurchase**參數值和預設狀態，根據您的組織，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="0dfa0-129">檢視清單中的自助購買產品以及其狀態</span><span class="sxs-lookup"><span data-stu-id="0dfa0-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="0dfa0-130">若要檢視所有可用的自助購買產品和每個狀態的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="0dfa0-131">下表列出可用的產品和其**ProductId**。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="0dfa0-132">產品</span><span class="sxs-lookup"><span data-stu-id="0dfa0-132">Product</span></span> | <span data-ttu-id="0dfa0-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="0dfa0-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="0dfa0-134">每位使用者的電源應用程式</span><span class="sxs-lookup"><span data-stu-id="0dfa0-134">Power Apps per user</span></span> | <span data-ttu-id="0dfa0-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="0dfa0-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="0dfa0-136">每位使用者的電源自動化</span><span class="sxs-lookup"><span data-stu-id="0dfa0-136">Power Automate per user</span></span> | <span data-ttu-id="0dfa0-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="0dfa0-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="0dfa0-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="0dfa0-138">Power BI Pro</span></span> | <span data-ttu-id="0dfa0-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="0dfa0-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="0dfa0-140">檢視或設定 AllowSelfServicePurchase 狀態</span><span class="sxs-lookup"><span data-stu-id="0dfa0-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="0dfa0-141">檢視可供自助購買的產品清單之後，您可以檢視或修改某項特定產品的設定。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="0dfa0-142">若要取得特定產品的原則設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="0dfa0-143">若要啟用特定產品的原則設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="0dfa0-144">若要停用某項特定產品的原則設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="0dfa0-145">若要停用 AllowSelfServicePurchase 的範例指令碼</span><span class="sxs-lookup"><span data-stu-id="0dfa0-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="0dfa0-146">下列範例會引導您逐步完成如何匯入**MSCommerce**模組，使用您的帳戶登入，取得**ProductId** Power 自動化，，然後停用**AllowSelfServicePurchase**該產品。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="0dfa0-147">疑難排解</span><span class="sxs-lookup"><span data-stu-id="0dfa0-147">Troubleshooting</span></span>

<span data-ttu-id="0dfa0-148">**問題**</span><span class="sxs-lookup"><span data-stu-id="0dfa0-148">**Problem**</span></span>

<span data-ttu-id="0dfa0-149">您會看到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0dfa0-149">You see the following error message:</span></span>

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

<span data-ttu-id="0dfa0-150">這可能是由於較舊版本的傳輸層安全性 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="0dfa0-150">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="0dfa0-151">若要連接這項服務必須使用 TLS 1.2 版或更新版本</span><span class="sxs-lookup"><span data-stu-id="0dfa0-151">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="0dfa0-152">**解決方案**</span><span class="sxs-lookup"><span data-stu-id="0dfa0-152">**Solution**</span></span>

<span data-ttu-id="0dfa0-153">升級為 TLS 1.2:[https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="0dfa0-153">Upgrade to TLS 1.2: [https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->