---
title: 核心 eDiscovery 案例中的限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明核心 eDiscovery 案例中 Microsoft 365 的限制。
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311421"
---
# <a name="limits-in-core-ediscovery"></a>核心 eDiscovery 的限制

下表列出核心 ediscovery 案例相關聯之核心 eDiscovery 案例和保留專案的限制。 如需核心 eDiscovery 的詳細資訊，請參閱 [核心 Ediscovery 一覽](./get-started-core-ediscovery.md)。
    
  | 限制的描述 | 限制 |
  |:-----|:-----|
  |組織的案例數目上限。  <br/> |無限制  <br/> |
  |組織的案例保留數目上限。  <br/> |10,000  <br/> |
  |單一案例保留中的信箱數目上限。 此限制包括使用者信箱的組合總數，以及與 Microsoft 365 群組、Microsoft Teams 及 Yammer 群組相關聯的信箱。  <br/> |1,000  <br/> |
  |單一案例保留中的網站數目上限。 此限制包括與 Microsoft 365 群組、Microsoft Teams 及 Yammer 群組相關聯的商務用 OneDrive 網站、SharePoint 網站和網站的綜合總數。  <br/> |100  <br/> |
  |顯示在核心 eDiscovery 首頁上的案例數目上限，以及在案例中的 [保留]、[搜尋] 和 [匯出] 索引標籤上顯示的專案數上限。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup>若要查看超過1000案例、保留、搜尋或匯出的清單，您可以使用對應的 Office 365 安全性 & 相容性 PowerShell Cmdlet：
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

如需與核心 eDiscovery 案例相關聯之搜尋和匯出相關限制的相關資訊，請參閱 [內容搜尋和核心 ediscovery 的限制](limits-for-content-search.md)。