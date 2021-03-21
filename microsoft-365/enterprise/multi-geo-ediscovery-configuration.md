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
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923717"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 多地理位置電子文件探索設定

「[高級 ediscovery」功能](../compliance/overview-ediscovery-20.md)可讓多地理位置 ediscovery 管理員搜尋所有的 geos，而不需要使用「地區」安全性篩選器。 資料會匯出至多地理位置承租人的中央位置 Azure 實例。 

若沒有任何高級電子檔探索能力，多地理位置租使用者的 eDiscovery 管理員或管理員將只能在該租使用者的中央位置執行 eDiscovery。 若要支援進行電子檔探索的功能，請透過 PowerShell 使用名為 "Region" 的新合規性安全性篩選參數。 此參數可供核心位置位於北美、歐洲或亞太地區的承租人使用。 建議使用高級 eDiscovery，以供核心位置不在北美、歐洲或亞太地區的承租人，以及需要跨衛星地理位置執行 eDiscovery 的使用者。 

Microsoft 365 全域系統管理員必須指派電子文件探索管理員權限，以允許其他人執行電子文件探索，並在其適用的合規性安全性篩選中指派「地區」參數，以將進行電子文件探索的區域指定為衛星位置，否則將不會為該衛星位置執行任何電子文件探索。

當為特定衛星位置設定電子文件探索管理員或系統管理員角色時，電子文件探索管理員或系統管理員只能對位於該衛星位置中的 SharePoint 網站和 OneDrive 網站執行 eDiscovery 搜尋動作。如果電子文件探索管理員或系統管理員嘗試搜尋指定的衛星位置外的 SharePoint 或 OneDrive 網站，則不會傳回任何結果。此外，當某衛星位置的電子文件探索管理員或系統管理員區域觸發匯出時，系統會將資料匯出至該區域的 Azure 執行個體。這可透過禁止匯出控制框線外的內容來協助組織保持合規。

> [!NOTE]
> 如果此對跨多個 SharePoint 衛星位置的電子文件探索管理員是必要的，將必須為指定 OneDrive 或 SharePoint 網站所在位置之替代衛星位置的電子文件探索管理員建立另一個使用者帳戶。

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

若要為某地區設定合規性安全性篩選：

1. [連線至 Microsoft 365 安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)

2. 請使用下列語法：

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   例如：

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

請參閱 [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) 一文以了解額外的參數和語法。