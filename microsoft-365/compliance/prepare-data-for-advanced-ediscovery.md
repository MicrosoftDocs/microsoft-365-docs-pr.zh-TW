---
title: 为 Office 365 高级电子数据展示准备数据
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: '了解如何使用 Microsoft 365 安全&amp;合规性中心准备 Office 365 数据，以便使用 Office 365 高级电子数据展示进行分析。 '
ms.openlocfilehash: be778acb3356071e9575ed708623a0b94e2b3c7a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077552"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a>为 Office 365 高级电子数据展示准备数据

本主题介绍如何将内容搜索的结果加载到高级电子数据展示中的案例中。 
  
> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a>第 1 步：为高级电子数据展示准备 Office 365 数据

要使用高级电子数据展示分析数据，可以使用在 Microsoft 365 安全&amp;合规性中心（在 Microsoft 365 安全&amp;合规性中心**的内容搜索**页面上列出）中运行的内容搜索的结果，或与电子数据展示案例关联的搜索（在安全&amp;合规中心**的第一个电子数据展示**页面上列出）。 
  
有关在高级电子数据展示中准备用于分析的搜索结果的详细步骤，请参阅[为 Office 365 高级电子数据展示准备搜索结果。](prepare-search-results-for-advanced-ediscovery.md)
  
> [!NOTE]
> 如果您有 Office 365 以外的数据，并且希望将其导入 Office 365，以便在高级电子数据展示中准备和分析数据，请参阅将[PST 文件导入 Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)和[在 Office 365 中存档第三方数据的](https://go.microsoft.com/fwlink/p/?linkid=716918)概述。 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>步骤 2：将搜索结果数据加载到高级电子数据展示中的案例

在安全&amp;合规性中心准备搜索结果进行分析后，下一步是将搜索结果加载到高级电子数据展示中的案例中。 有关详细信息，请参阅[运行流程模块](run-the-process-module-in-advanced-ediscovery.md)。
  
1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在安全性與合規性中心，按一下 [搜尋和調查]**** \> [電子文件探索]****，來顯示貴組織中的案例清單。 
    
4. 单击要在高级电子数据展示中加载数据的情况**旁边的"打开"。** 
    
5. 在案例的 [首頁]**** 頁面上，按一下 [進階電子文件探索]****。 
    
    ![单击"切换到高级电子数据展示"以在高级电子数据展示中打开案例](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    将显示"**连接到高级电子数据展示**进度栏"。 当您连接到高级电子数据展示时，案例的设置页上将显示一个容器列表。 
    
    ![案例显示在高级电子数据展示中](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     这些容器表示您在步骤 1 中的高级电子数据展示中为分析准备的搜索结果。 请注意，容器的名称与安全&amp;合规性中心中的内容搜索具有相同的名称。 列表中的容器是您准备的容器。 如果其他用户为高级电子数据展示准备了搜索结果，则相应的容器将不会包含在列表中。 
    
6. 要将搜索结果数据从 容器加载到高级电子数据展示中的案例中，请选择一个容器，然后单击"**处理"。**
    
将安全&amp;合规性中心的搜索结果添加到高级电子数据展示中的案例后，下一步是使用高级电子数据展示中的工具分析和剔除与案例相关的数据。 
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[设置用户和案例](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[分析案例資料](analyze-case-data-with-advanced-ediscovery.md)
  
[管理相关性设置](manage-relevance-setup-in-advanced-ediscovery.md)
  
[使用相關性模組](use-relevance-in-advanced-ediscovery.md)
  
[匯出案例資料](export-case-data-in-advanced-ediscovery.md)

