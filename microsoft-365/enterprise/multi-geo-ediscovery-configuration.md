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
description: 瞭解如何使用 Region 參數設定 eDiscovery，以用於 Microsoft 365 多地理位置的衛星位置。
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923717"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="86006-103">Microsoft 365 多地理位置電子文件探索設定</span><span class="sxs-lookup"><span data-stu-id="86006-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="86006-104">[Advanced eDiscovery 功能](../compliance/overview-ediscovery-20.md)可讓多地理位置 eDiscovery 管理員搜尋所有的 geos，而不需要使用「地區」安全性篩選器。</span><span class="sxs-lookup"><span data-stu-id="86006-104">[Advanced eDiscovery capabilities](../compliance/overview-ediscovery-20.md) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="86006-105">資料會匯出至多地理位置承租人的中央位置 Azure 實例。</span><span class="sxs-lookup"><span data-stu-id="86006-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="86006-106">若沒有任何高級電子檔探索能力，多地理位置租使用者的 eDiscovery 管理員或管理員將只能在該租使用者的中央位置執行 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="86006-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="86006-107">若要支援進行電子檔探索的功能，請透過 PowerShell 使用名為 "Region" 的新合規性安全性篩選參數。</span><span class="sxs-lookup"><span data-stu-id="86006-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="86006-108">此參數可供核心位置位於北美、歐洲或亞太地區的承租人使用。</span><span class="sxs-lookup"><span data-stu-id="86006-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="86006-109">建議針對其中央地點不在北美、歐洲或亞太地區的承租人，以及需要跨衛星地理位置執行 eDiscovery 的承租人。 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="86006-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="86006-110">Microsoft 365 全域系統管理員必須指派電子文件探索管理員權限，以允許其他人執行電子文件探索，並在其適用的合規性安全性篩選中指派「地區」參數，以將進行電子文件探索的區域指定為衛星位置，否則將不會為該衛星位置執行任何電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="86006-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="86006-p103">當為特定衛星位置設定電子文件探索管理員或系統管理員角色時，電子文件探索管理員或系統管理員只能對位於該衛星位置中的 SharePoint 網站和 OneDrive 網站執行 eDiscovery 搜尋動作。如果電子文件探索管理員或系統管理員嘗試搜尋指定的衛星位置外的 SharePoint 或 OneDrive 網站，則不會傳回任何結果。此外，當某衛星位置的電子文件探索管理員或系統管理員區域觸發匯出時，系統會將資料匯出至該區域的 Azure 執行個體。這可透過禁止匯出控制框線外的內容來協助組織保持合規。</span><span class="sxs-lookup"><span data-stu-id="86006-p103">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location. If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned. Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region. This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="86006-115">如果此對跨多個 SharePoint 衛星位置的電子文件探索管理員是必要的，將必須為指定 OneDrive 或 SharePoint 網站所在位置之替代衛星位置的電子文件探索管理員建立另一個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="86006-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="86006-116">若要為某地區設定合規性安全性篩選：</span><span class="sxs-lookup"><span data-stu-id="86006-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="86006-117">連線至 Microsoft 365 安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="86006-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="86006-118">請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="86006-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="86006-119">例如：</span><span class="sxs-lookup"><span data-stu-id="86006-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="86006-120">請參閱 [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) 一文以了解額外的參數和語法。</span><span class="sxs-lookup"><span data-stu-id="86006-120">See the [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>