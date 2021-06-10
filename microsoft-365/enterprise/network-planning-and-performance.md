---
title: Microsoft 365 的網路規劃和效能調整
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/19/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_Enterprise
f1.keywords:
- CSH
search.appverid:
- MET150
ms.assetid: e5f1228c-da3c-4654-bf16-d163daee8848
ms.custom:
- seo-marvel-apr2020
- Adm_O365
description: 本文將協助您規劃 Microsoft 365 的網路頻寬需求，並精細調整和疑難排解效能。
ms.openlocfilehash: bf05e4128f8ba5ddecce76cb00dc945f43c9c59a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923597"
---
# <a name="network-planning-and-performance-tuning-for-microsoft-365"></a>Microsoft 365 的網路規劃和效能調整
在您第一次部署或遷移至 Microsoft 365 之前，您可以使用下列主題中的資訊來估計所需的頻寬，然後測試並確認您有足夠的頻寬可部署或遷移至 Microsoft 365。 如需概述，請參閱：[網路和遷移規劃 Microsoft 365](network-and-migration-planning.md)。
  
|||||
|:-----|:-----|:-----|:-----|
|**網路規劃** <br/> ![網路](../media/5e9dcd06-601b-4b28-88dc-f524e7548794.png)           <br/> |想要加快連線速度和頁面的載入速度嗎？  <br/> [在 Microsoft 365 中讀取取得最佳的連線能力與效能](https://aka.ms/o365perfprinciples)。<br/>閱讀[Microsoft 365 網路連線概述](microsoft-365-networking-overview.md)，以瞭解概念。<br/> |**測量您的網路** <br/> ![計算器](../media/d690a132-4884-40eb-a918-526bb3dff3cc.png)           <br/> |使用 Microsoft 365 的[基準和效能歷史](performance-tuning-using-baselines-and-history.md)和[效能疑難排解計畫](performance-troubleshooting-plan.md)讀取 Microsoft 365 效能調整。  <br/> 使用這些工具來[評估您現有的網路](network-and-migration-planning.md#calculators)。  <br/> |
|**最佳作法** <br/> ![最佳作法](../media/2a659a5c-1007-47d3-a6c6-a19e018ab29b.png)           <br/> |[網路規劃的最佳作法，以及改善 Microsoft 365 的遷移效能](network-and-migration-planning.md#BestPractices)。 想立即開始協助您的使用者嗎？ 參閱[在網路緩慢的情況下使用 Office 365 的最佳作法](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。  <br/> [Microsoft 365 網路連線原則](./microsoft-365-network-connectivity-principles.md)可協助您瞭解如何安全地優化 Microsoft 365 網路連線的最近指導方針。  <br/> |**參照** <br/> ![書籍或期刊](../media/56dff3c1-f605-48d8-811f-7d13ce639ecd.png)           <br/> |想要如 IP 位址和連接埠清單的詳細資料嗎？ 請參閱[網路規劃參考的 Microsoft 365](network-and-migration-planning.md#NetReference)。  <br/> |
|![請參閱適用於企業架構的 Microsoft 雲端網路海報](../media/3094be9f-2407-4fa5-896d-aa66ef7b9bb9.png)           <br/> |如需針對 Microsoft 365 和其他 Microsoft 雲端平臺及服務優化網路的步驟，請參閱[Microsoft 雲端網路，以取得 Enterprise 架構師](../solutions/cloud-architecture-models.md)海報。  <br/> |
   
## <a name="performance-tuning-and-troubleshooting-resources-for-microsoft-365"></a>Microsoft 365 的效能調整和疑難排解資源
<a name="apptuning"> </a>

部署 Microsoft 365 後，您就可以使用本節中的主題來優化效能。 若遇到效能降低情形，您也可以使用這些主題來疑難排解問題。
  
 **[調整 Office 365 效能](tune-microsoft-365-performance.md)**：如需有關搭配 Office 365 使用網路位址轉譯的資訊，請參閱 [Office 365 的 NAT 支援](nat-support-with-microsoft-365.md) (部分機器翻譯)。 此外，請參閱[優化及疑難排解 Office 365 網路連線的十大秘訣](/archive/blogs/onthewire/top-10-tips-for-optimising-troubleshooting-your-office-365-network-connectivity)。 
  
 **[調整 Exchange Online 的效能](tune-exchange-online-performance.md)**：使用這些文章的資訊，微調 Exchange Online 的效能。 
  
 **[調整商務用 Skype Online 的效能](tune-skype-for-business-online-performance.md)**：使用這些文章的資訊，微調商務用 Skype Online 的效能。 
  
 **[調整 SharePoint Online 的效能](tune-sharepoint-online-performance.md)**：使用這些文章的資訊，微調 SharePoint Online 的效能。 
  
 **[調整 Project Online 的效能](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)**：使用這些文章的資訊，微調 Project Online 的效能。