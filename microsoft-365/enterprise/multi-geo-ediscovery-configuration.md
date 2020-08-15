---
title: 設定 Microsoft 365 多地理位置電子文件探索
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: 瞭解如何使用 Region 參數，設定電子檔探索，以用於 Microsoft 365 多地理位置的衛星位置。
ms.openlocfilehash: 83141f824c76ca5531e1b390b91adcdb4f3874de
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688421"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="ddb35-103">Microsoft 365 多地理位置電子文件探索設定</span><span class="sxs-lookup"><span data-stu-id="ddb35-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="ddb35-p101">依預設，電子文件探索管理員或多地理位置租用戶的系統管理員僅能在該租用戶的中央位置中進行電子文件探索。若要支援對衛星位置進行電子文件探索的能力，則可透過 PowerShell 取得名為「地區」的新合規性安全性篩選參數。</span><span class="sxs-lookup"><span data-stu-id="ddb35-p101">By default, an eDiscovery Manager or Administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant. To support the ability to conduct eDiscovery for satellite locations, a new Compliance Security Filter parameter called "Region" is available via PowerShell.</span></span>

<span data-ttu-id="ddb35-106">Microsoft 365 全域系統管理員必須指派電子文件探索管理員權限，以允許其他人執行電子文件探索，並在其適用的合規性安全性篩選中指派「地區」參數，以將進行電子文件探索的區域指定為衛星位置，否則將不會為該衛星位置執行任何電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="ddb35-106">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="ddb35-p102">當為特定衛星位置設定電子文件探索管理員或系統管理員角色時，電子文件探索管理員或系統管理員只能對位於該衛星位置中的 SharePoint 網站和 OneDrive 網站執行 eDiscovery 搜尋動作。如果電子文件探索管理員或系統管理員嘗試搜尋指定的衛星位置外的 SharePoint 或 OneDrive 網站，則不會傳回任何結果。此外，當某衛星位置的電子文件探索管理員或系統管理員區域觸發匯出時，系統會將資料匯出至該區域的 Azure 執行個體。這可透過禁止匯出控制框線外的內容來協助組織保持合規。</span><span class="sxs-lookup"><span data-stu-id="ddb35-p102">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location. If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned. Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region. This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="ddb35-111">如果此對跨多個 SharePoint 衛星位置的電子文件探索管理員是必要的，將必須為指定 OneDrive 或 SharePoint 網站所在位置之替代衛星位置的電子文件探索管理員建立另一個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ddb35-111">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="ddb35-112">若要為某地區設定合規性安全性篩選：</span><span class="sxs-lookup"><span data-stu-id="ddb35-112">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="ddb35-113">連線至 Microsoft 365 安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddb35-113">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)

2. <span data-ttu-id="ddb35-114">請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ddb35-114">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="ddb35-115">例如：</span><span class="sxs-lookup"><span data-stu-id="ddb35-115">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="ddb35-116">請參閱 [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesecurityfilter) 一文以了解額外的參數和語法。</span><span class="sxs-lookup"><span data-stu-id="ddb35-116">See the [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>
