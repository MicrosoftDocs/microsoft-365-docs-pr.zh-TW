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
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924633"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="91563-103">使用 PowerShell 查看 Microsoft 365 授權和服務</span><span class="sxs-lookup"><span data-stu-id="91563-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="91563-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="91563-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="91563-105">每個 Microsoft 365 訂閱都包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="91563-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="91563-106">**授權方案** 這些也稱為「授權方案」或「Microsoft 365 方案」。</span><span class="sxs-lookup"><span data-stu-id="91563-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="91563-107">授權計畫定義使用者可以使用的 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="91563-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="91563-108">您的 Microsoft 365 訂閱可能包含多個授權計畫。</span><span class="sxs-lookup"><span data-stu-id="91563-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="91563-109">授權方案範例是 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="91563-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="91563-110">**服務** 這些也稱為服務方案。</span><span class="sxs-lookup"><span data-stu-id="91563-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="91563-111">服務是每個授權計畫中可用的 Microsoft 365 產品、功能及功能，例如，Exchange Online 和 Microsoft 365 應用程式的 enterprise (先前命名為 Office 365 ProPlus) 。</span><span class="sxs-lookup"><span data-stu-id="91563-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="91563-112">使用者可以將多個授權指派給他們，以不同授權方案授與不同服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="91563-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="91563-113">**授權** 每個授權方案都包含您購買的授權數目。</span><span class="sxs-lookup"><span data-stu-id="91563-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="91563-114">您可以將授權指派給使用者，讓他們可以使用授權方案所定義的 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="91563-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="91563-115">每個使用者帳戶至少需要一個授權方案的授權，這樣他們才能登入 Microsoft 365 並使用服務。</span><span class="sxs-lookup"><span data-stu-id="91563-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="91563-116">您可以使用 Microsoft 365 的 PowerShell，以查看您的 Microsoft 365 組織中可用授權方案、授權及服務的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91563-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="91563-117">如需有關不同 Office 365 訂閱中可用之產品、功能和服務的詳細資訊，請參閱 [Office 365 方案選項](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。</span><span class="sxs-lookup"><span data-stu-id="91563-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="91563-118">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="91563-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="91563-119">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="91563-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="91563-120">若要查看您目前授權計畫的摘要資訊，以及每個計畫可用的授權，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="91563-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="91563-121">結果包含：</span><span class="sxs-lookup"><span data-stu-id="91563-121">The results contain:</span></span>
  
- <span data-ttu-id="91563-122">**SkuPartNumber：** 顯示您的組織可用的授權方案。</span><span class="sxs-lookup"><span data-stu-id="91563-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="91563-123">例如，「 `ENTERPRISEPACK` Office 365 企業版 E3」的授權方案名稱。</span><span class="sxs-lookup"><span data-stu-id="91563-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="91563-124">**已啟用：** 您為特定授權方案購買的授權數目。</span><span class="sxs-lookup"><span data-stu-id="91563-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="91563-125">**ConsumedUnits：** 您已從特定授權方案中指派給使用者的授權數目。</span><span class="sxs-lookup"><span data-stu-id="91563-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="91563-126">若要查看所有授權方案中可用之 Microsoft 365 服務的詳細資訊，請先顯示您的授權方案清單。</span><span class="sxs-lookup"><span data-stu-id="91563-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="91563-127">接下來，將授權計畫資訊儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="91563-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="91563-128">接下來，顯示特定授權方案中的服務。</span><span class="sxs-lookup"><span data-stu-id="91563-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="91563-129">\<index> 是整數，它會指定授權方案的列數，從命令的顯示 `Get-AzureADSubscribedSku | Select SkuPartNumber` 減1。</span><span class="sxs-lookup"><span data-stu-id="91563-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="91563-130">例如，如果命令的顯示如下 `Get-AzureADSubscribedSku | Select SkuPartNumber` ：</span><span class="sxs-lookup"><span data-stu-id="91563-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="91563-131">顯示 ENTERPRISEPREMIUM 授權方案之服務的命令如下：</span><span class="sxs-lookup"><span data-stu-id="91563-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="91563-132">ENTERPRISEPREMIUM 是第三列。</span><span class="sxs-lookup"><span data-stu-id="91563-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="91563-133">因此，索引值為 (3-1) 或2。</span><span class="sxs-lookup"><span data-stu-id="91563-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="91563-134">如需授權方案的完整清單 (也稱為產品名稱) 、其包含的服務方案及其對應的易記名稱，請參閱 [產品名稱和服務方案識別碼取得授權](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="91563-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="91563-135">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="91563-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="91563-136">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="91563-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="91563-137">PowerShell 指令碼可供使用，會自動執行本主題中所述的程序。</span><span class="sxs-lookup"><span data-stu-id="91563-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="91563-138">具體說來，此腳本可讓您查看及停用 Microsoft 365 組織中的服務，包括 Sway。</span><span class="sxs-lookup"><span data-stu-id="91563-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="91563-139">如需詳細資訊，請參閱 [使用 PowerShell 停用 Sway 的存取權](disable-access-to-sway-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="91563-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="91563-140">若要查看您目前授權計畫的摘要資訊，以及每個計畫可用的授權，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="91563-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="91563-141">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="91563-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="91563-142">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="91563-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="91563-143">結果包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="91563-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="91563-144">**AccountSkuId：** 使用語法顯示組織可用的授權方案 `<CompanyName>:<LicensingPlan>` 。</span><span class="sxs-lookup"><span data-stu-id="91563-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="91563-145">_\<CompanyName>_ 是您在 Microsoft 365 中註冊時所提供的值，且對您的組織而言是唯一的。</span><span class="sxs-lookup"><span data-stu-id="91563-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="91563-146">_\<LicensingPlan>_ 所有人的值都相同。</span><span class="sxs-lookup"><span data-stu-id="91563-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="91563-147">例如，在值 `litwareinc:ENTERPRISEPACK` 、公司名稱以及  `litwareinc` 授權方案名稱  `ENTERPRISEPACK` ，也就是 Office 365 企業版 E3 的系統名稱。</span><span class="sxs-lookup"><span data-stu-id="91563-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="91563-148">**ActiveUnits：** 您為特定授權方案購買的授權數目。</span><span class="sxs-lookup"><span data-stu-id="91563-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="91563-149">**WarningUnits：** 授權方案中尚未更新，且30天寬限期後會到期的授權數目。</span><span class="sxs-lookup"><span data-stu-id="91563-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="91563-150">**ConsumedUnits：** 您已從特定授權方案中指派給使用者的授權數目。</span><span class="sxs-lookup"><span data-stu-id="91563-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="91563-151">若要查看所有授權方案中可用之 Microsoft 365 服務的詳細資料，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="91563-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="91563-152">下表顯示 Microsoft 365 服務方案及其最常見服務的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="91563-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="91563-153">您的服務方案清單可能不同。</span><span class="sxs-lookup"><span data-stu-id="91563-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="91563-154">**服務計劃**</span><span class="sxs-lookup"><span data-stu-id="91563-154">**Service plan**</span></span>|<span data-ttu-id="91563-155">**描述**</span><span class="sxs-lookup"><span data-stu-id="91563-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="91563-156">Sway</span><span class="sxs-lookup"><span data-stu-id="91563-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="91563-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91563-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="91563-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="91563-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="91563-159">Azure 版權管理 (RMS)</span><span class="sxs-lookup"><span data-stu-id="91563-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="91563-160">*先前命名為 Office 365 ProPlus* 的 Microsoft 365 應用程式 enterprise () </span><span class="sxs-lookup"><span data-stu-id="91563-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="91563-161">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="91563-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="91563-162">辦公室</span><span class="sxs-lookup"><span data-stu-id="91563-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="91563-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="91563-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="91563-164">Exchange Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="91563-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="91563-165">如需授權方案的完整清單 (也稱為產品名稱) 、其包含的服務方案及其對應的易記名稱，請參閱 [產品名稱和服務方案識別碼取得授權](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="91563-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="91563-166">若要查看特定授權方案中可用之 Microsoft 365 服務的詳細資料，請使用下列語法。</span><span class="sxs-lookup"><span data-stu-id="91563-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="91563-167">此範例會顯示 litwareinc:ENTERPRISEPACK (Office 365 企業版 E3) 授權方案中可用的服務。</span><span class="sxs-lookup"><span data-stu-id="91563-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="91563-168">另請參閱</span><span class="sxs-lookup"><span data-stu-id="91563-168">See also</span></span>

[<span data-ttu-id="91563-169">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="91563-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="91563-170">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91563-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="91563-171">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="91563-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)