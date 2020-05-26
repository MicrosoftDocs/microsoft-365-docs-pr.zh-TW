---
title: 核心 eDiscovery 案例中的限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明 Microsoft 365 核心 eDiscovery 案例中的限制。
ms.openlocfilehash: 00df8cff683701ce5ee38dca12b6f7af5b31c8b0
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351894"
---
# <a name="limits-in-core-ediscovery"></a>核心 eDiscovery 的限制

下表列出核心 ediscovery 案例相關聯之核心 eDiscovery 案例和保留專案的限制。 如需核心 eDiscovery 的詳細資訊，請參閱[核心 Ediscovery 一覽](ediscovery-cases.md)。
    
  |**限制的描述**|**限制**|
  |:-----|:-----|
  |組織的案例數目上限  <br/> |無限制  <br/> |
  |組織的案例保留數目上限  <br/> |10,000  <br/> |
  |單一案例保留中的信箱數目上限  <br/> |1,000  <br/> |
  |單一案例保留中的商務網站 SharePoint 和 OneDrive 數目上限  <br/> |100  <br/> |
  |顯示在核心 eDiscovery 首頁上的案例數目上限，以及在案例中的 [保留]、[搜尋] 和 [匯出] 索引標籤上顯示的專案數上限。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup>若要查看超過1000案例、保留、搜尋或匯出的清單，您可以使用對應的 Office 365 安全性 & 合規性 PowerShell Cmdlet：<br/> [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
