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
ms.openlocfilehash: 216012791473776395d27821293e8fc565568c2c
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547947"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 多地理位置電子文件探索設定

依預設，電子文件探索管理員或多地理位置租用戶的系統管理員僅能在該租用戶的中央位置中進行電子文件探索。若要支援對衛星位置進行電子文件探索的能力，則可透過 PowerShell 取得名為「地區」的新合規性安全性篩選參數。

Microsoft 365 全域系統管理員必須指派電子文件探索管理員權限，以允許其他人執行電子文件探索，並在其適用的合規性安全性篩選中指派「地區」參數，以將進行電子文件探索的區域指定為衛星位置，否則將不會為該衛星位置執行任何電子文件探索。

當為特定衛星位置設定電子文件探索管理員或系統管理員角色時，電子文件探索管理員或系統管理員只能對位於該衛星位置中的 SharePoint 網站和 OneDrive 網站執行 eDiscovery 搜尋動作。如果電子文件探索管理員或系統管理員嘗試搜尋指定的衛星位置外的 SharePoint 或 OneDrive 網站，則不會傳回任何結果。此外，當某衛星位置的電子文件探索管理員或系統管理員區域觸發匯出時，系統會將資料匯出至該區域的 Azure 執行個體。這可透過禁止匯出控制框線外的內容來協助組織保持合規。

> [!NOTE]
> 如果此對跨多個 SharePoint 衛星位置的電子文件探索管理員是必要的，將必須為指定 OneDrive 或 SharePoint 網站所在位置之替代衛星位置的電子文件探索管理員建立另一個使用者帳戶。

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

若要為某地區設定合規性安全性篩選：

1. [連線至 Microsoft 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. 請使用下列語法：

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   例如：

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

請參閱 [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) 一文以了解額外的參數和語法。
