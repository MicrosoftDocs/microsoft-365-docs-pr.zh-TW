---
title: 進階電子文件探索的快速設定
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: 了解如何從安全性與合規性中心存取進階電子文件探索，以及檢閱使用進階電子文件探索的一般工作流程。
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936256"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a>快速設定進階電子文件探索 (傳統版)

> [!IMPORTANT]
> 隨著我們繼續投資於更新版本的進階電子文件探索，我們即將宣布停用進階文件探索 (也稱為*進階電子文件探索 (傳統版)* 或*進階文件探索 1.0 版*)。 如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。 進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。 若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。 

此設定小節將為 Microsoft 365 安全性與合規性中心的電子文件探索管理員說明如何開始使用「進階電子文件探索」。 本文假設使用者具備這兩者的工作知識。
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>存取進階電子文件探索中的案例

You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md). 
  
若要移至進階電子文件探索中的案例： 
  
1. [前往安全性與合規性中心](go-to-the-securitycompliance-center.md)。 
    
2. 在安全性與合規性中心，按一下 [搜尋和調查]**** \> [電子文件探索]****，來顯示貴組織中的案例清單。 
    
3. 在 [電子文件探索]**** 頁面上，按一下進階電子文件探索中您要移至的案例旁邊的 [開啟]****。
    
4. 在案例的 [首頁]**** 頁面上，按一下 [切換至進階電子文件探索]****。
    
    The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery. 
    
## <a name="workflow"></a>工作流程

下圖說明常見的工作流程，用於管理和使用安全性與合規性中心以及進階電子文件探索中的電子文件探索案例。
  
![圖表會顯示設定中四個階段的進階電子文件探索工作流程，包括設定使用者和案例、識別案例資料、匯出及處理，接著是分析並匯出至本機電腦的階段。](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.
  
## <a name="analyze"></a>分析

[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results. 
  
## <a name="relevance-setup-and-relevance"></a>相關性設定和相關性

[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions. 
  
## <a name="export"></a>匯出

[匯出案例資料](export-case-data-in-advanced-ediscovery.md) 可讓您匯出進階電子文件探索內容和結果，進行外部檢閱。 
  
## <a name="report"></a>報告

[執行報告](run-reports-in-advanced-ediscovery.md) 可讓您產生選取的報告，其與進階電子文件探索處理相關。 
  
## <a name="see-also"></a>請參閱

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[設定使用者和案例](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[準備安裝](prepare-data-for-advanced-ediscovery.md)

