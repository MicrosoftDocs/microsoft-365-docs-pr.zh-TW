---
title: 針對 MSCommerce PowerShell 模組使用 AllowSelfServicePurchase
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: 瞭解如何使用 AllowSelfServicePurchase PowerShell Cmdlet 來開啟或關閉自助購買服務。
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 07/16/2021
ms.openlocfilehash: 77cb1c753db22929ea2c3d14226a3927e6406b89
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461360"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="0a951-103">針對 MSCommerce PowerShell 模組使用 AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="0a951-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="0a951-104">**MSCommerce** PowerShell 模組現在可用於 [PowerShell 圖庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)。</span><span class="sxs-lookup"><span data-stu-id="0a951-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="0a951-105">此模組包含 **AllowSelfServicePurchase** 的 **PolicyID** 參數值，可讓您控制組織中的使用者是否可以進行自助購買。</span><span class="sxs-lookup"><span data-stu-id="0a951-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="0a951-106">您可以使用 **MSCommerce** PowerShell 模組來：</span><span class="sxs-lookup"><span data-stu-id="0a951-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="0a951-107">查看 **AllowSelfServicePurchase** 參數值的預設狀態，不論它是啟用還是停用</span><span class="sxs-lookup"><span data-stu-id="0a951-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="0a951-108">查看適用產品的清單，以及是否啟用或停用自助購買功能</span><span class="sxs-lookup"><span data-stu-id="0a951-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="0a951-109">查看或修改特定產品的目前設定，以啟用或停用</span><span class="sxs-lookup"><span data-stu-id="0a951-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="0a951-110">需求</span><span class="sxs-lookup"><span data-stu-id="0a951-110">Requirements</span></span>

<span data-ttu-id="0a951-111">若要使用 **MSCommerce** PowerShell 模組，您需要：</span><span class="sxs-lookup"><span data-stu-id="0a951-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="0a951-112">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="0a951-112">A Windows 10 device</span></span>
- <span data-ttu-id="0a951-113">PowerShell 5 或下列。</span><span class="sxs-lookup"><span data-stu-id="0a951-113">PowerShell 5 or below.</span></span> <span data-ttu-id="0a951-114">目前，此模組不支援 PowerShell 的 a.x/7. x。</span><span class="sxs-lookup"><span data-stu-id="0a951-114">Currently, PowerShell 6.x/7.x isn't supported with this module.</span></span>
- <span data-ttu-id="0a951-115">裝置的系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="0a951-115">Administrator permission for the device</span></span>
- <span data-ttu-id="0a951-116">您租使用者的全域或計費系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="0a951-116">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="0a951-117">安裝 MSCommerce PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="0a951-117">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="0a951-118">您 Windows 10 裝置上安裝 **MSCommerce** PowerShell 模組一次，然後將其匯入您所開始的每一個 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="0a951-118">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="0a951-119">從 [PowerShell 庫](https://aka.ms/allowselfservicepurchase-powershell-gallery)下載 **MSCommerce** PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="0a951-119">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="0a951-120">若要使用 **PowerShellGet** 安裝 **MSCommerce** PowerShell 模組，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0a951-120">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="0a951-121">將 MSCommerce 匯入至 PowerShell 會話</span><span class="sxs-lookup"><span data-stu-id="0a951-121">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="0a951-122">在 Windows 10 裝置上安裝模組之後，您可以將它匯入開始的每個 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="0a951-122">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="0a951-123">若要將其匯入 PowerShell 會話，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0a951-123">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="0a951-124">使用您的認證連線 MSCommerce</span><span class="sxs-lookup"><span data-stu-id="0a951-124">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="0a951-125">若要使用您的認證連接至 PowerShell 模組，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="0a951-125">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="0a951-126">此命令會將目前的 PowerShell 會話連接至 Azure Active Directory 租使用者。</span><span class="sxs-lookup"><span data-stu-id="0a951-126">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="0a951-127">命令會提示您輸入您要連線的承租人的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="0a951-127">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="0a951-128">如果為您的認證啟用多重要素驗證，您可以使用 [互動式] 選項來登入。</span><span class="sxs-lookup"><span data-stu-id="0a951-128">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="0a951-129">查看 AllowSelfServicePurchase 的詳細資料</span><span class="sxs-lookup"><span data-stu-id="0a951-129">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="0a951-130">若要根據您的組織，查看 **AllowSelfServicePurchase** 參數值的描述及預設狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0a951-130">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="0a951-131">查看自助購買產品及其狀態的清單</span><span class="sxs-lookup"><span data-stu-id="0a951-131">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="0a951-132">若要查看所有可用自助購買產品的清單，以及每個產品的狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0a951-132">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="0a951-133">下表列出可用的產品及其 **ProductId**。</span><span class="sxs-lookup"><span data-stu-id="0a951-133">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="0a951-134">產品</span><span class="sxs-lookup"><span data-stu-id="0a951-134">Product</span></span> | <span data-ttu-id="0a951-135">ProductId</span><span class="sxs-lookup"><span data-stu-id="0a951-135">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="0a951-136">每位使用者 Power Apps</span><span class="sxs-lookup"><span data-stu-id="0a951-136">Power Apps per user</span></span> | <span data-ttu-id="0a951-137">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="0a951-137">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="0a951-138">每位使用者 Power Automate</span><span class="sxs-lookup"><span data-stu-id="0a951-138">Power Automate per user</span></span> | <span data-ttu-id="0a951-139">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="0a951-139">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="0a951-140">Power AutomateRPA</span><span class="sxs-lookup"><span data-stu-id="0a951-140">Power Automate RPA</span></span> | <span data-ttu-id="0a951-141">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="0a951-141">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="0a951-142">Power BI Premium (獨立) </span><span class="sxs-lookup"><span data-stu-id="0a951-142">Power BI Premium (standalone)</span></span> | <span data-ttu-id="0a951-143">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="0a951-143">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="0a951-144">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="0a951-144">Power BI Pro</span></span> | <span data-ttu-id="0a951-145">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="0a951-145">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="0a951-146">Project 方案 1</span><span class="sxs-lookup"><span data-stu-id="0a951-146">Project Plan 1</span></span> | <span data-ttu-id="0a951-147">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="0a951-147">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="0a951-148">Project 方案 3</span><span class="sxs-lookup"><span data-stu-id="0a951-148">Project Plan 3</span></span> | <span data-ttu-id="0a951-149">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="0a951-149">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="0a951-150">Visio 方案 1</span><span class="sxs-lookup"><span data-stu-id="0a951-150">Visio Plan 1</span></span> | <span data-ttu-id="0a951-151">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="0a951-151">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="0a951-152">Visio 方案 2</span><span class="sxs-lookup"><span data-stu-id="0a951-152">Visio Plan 2</span></span> | <span data-ttu-id="0a951-153">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="0a951-153">CFQ7TTC0KXN8</span></span> |
| <span data-ttu-id="0a951-154">Windows 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0a951-154">Windows 365 Enterprise</span></span> | <span data-ttu-id="0a951-155">CFQ7TTC0HHS9</span><span class="sxs-lookup"><span data-stu-id="0a951-155">CFQ7TTC0HHS9</span></span> |
| <span data-ttu-id="0a951-156">Windows 365 商務</span><span class="sxs-lookup"><span data-stu-id="0a951-156">Windows 365 Business</span></span> | <span data-ttu-id="0a951-157">CFQ7TTC0J203</span><span class="sxs-lookup"><span data-stu-id="0a951-157">CFQ7TTC0J203</span></span> |
| <span data-ttu-id="0a951-158">Windows 365 商務，具有 Windows 的混合式權益</span><span class="sxs-lookup"><span data-stu-id="0a951-158">Windows 365 Business with Windows Hybrid Benefit</span></span> | <span data-ttu-id="0a951-159">CFQ7TTC0HX99</span><span class="sxs-lookup"><span data-stu-id="0a951-159">CFQ7TTC0HX99</span></span> |
## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="0a951-160">查看或設定 AllowSelfServicePurchase 的狀態</span><span class="sxs-lookup"><span data-stu-id="0a951-160">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="0a951-161">在您查看可供自助購買之產品的清單後，您可以查看或修改特定產品的設定。</span><span class="sxs-lookup"><span data-stu-id="0a951-161">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="0a951-162">若要取得特定產品的原則設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0a951-162">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="0a951-163">若要啟用特定產品的原則設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0a951-163">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="0a951-164">若要停用特定產品的原則設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0a951-164">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="0a951-165">停用 AllowSelfServicePurchase 的範例腳本</span><span class="sxs-lookup"><span data-stu-id="0a951-165">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="0a951-166">下列範例會逐步引導您如何匯入 **MSCommerce** 模組、以您的帳戶登入、取得 Power Automate 的 **ProductId** ，然後停用該產品的 **AllowSelfServicePurchase** 。</span><span class="sxs-lookup"><span data-stu-id="0a951-166">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="0a951-167">疑難排解</span><span class="sxs-lookup"><span data-stu-id="0a951-167">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="0a951-168">問題</span><span class="sxs-lookup"><span data-stu-id="0a951-168">Problem</span></span>

<span data-ttu-id="0a951-169">您會看到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0a951-169">You see the following error message:</span></span>

> <span data-ttu-id="0a951-170">HandleError：無法使用 PolicyId ' AllowSelfServicePurchase ' 取得原則，ErrorMessage-基礎 connection 已關閉：傳送時發生意外的錯誤。</span><span class="sxs-lookup"><span data-stu-id="0a951-170">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="0a951-171">這可能是因為舊版本的傳輸層安全性 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="0a951-171">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="0a951-172">若要連接此服務，您需要使用 TLS 1.2 或更新版本</span><span class="sxs-lookup"><span data-stu-id="0a951-172">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="0a951-173">解決方案</span><span class="sxs-lookup"><span data-stu-id="0a951-173">Solution</span></span>

<span data-ttu-id="0a951-174">升級到 TLS 1.2： (/mem/configmgr/core/plan-design/security/enable-tls-1-2) </span><span class="sxs-lookup"><span data-stu-id="0a951-174">Upgrade to TLS 1.2: (/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a><span data-ttu-id="0a951-175">相關內容</span><span class="sxs-lookup"><span data-stu-id="0a951-175">Related content</span></span>

<span data-ttu-id="0a951-176">[ (系統管理)  (文章中管理自助購買 ](manage-self-service-purchases-admins.md)) </span><span class="sxs-lookup"><span data-stu-id="0a951-176">[Manage self-service purchases (Admin)](manage-self-service-purchases-admins.md) (article)</span></span>

<span data-ttu-id="0a951-177">[自助購買常見問題](self-service-purchase-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="0a951-177">[Self-service purchase FAQ](self-service-purchase-faq.yml) (article)</span></span>
