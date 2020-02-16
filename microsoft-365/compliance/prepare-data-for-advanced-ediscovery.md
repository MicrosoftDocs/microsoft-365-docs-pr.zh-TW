---
title: 準備資料以供 Office 365 進階電子文件探索
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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: '了解如何使用 Microsoft 365 安全性&amp;合規性中心，以準備與 Office 365 進階電子文件探索分析的 Office 365 的資料。 '
ms.openlocfilehash: 028cdb48e5ece2509d175a363c19beb6c2fafa19
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071030"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a>準備資料以供 Office 365 進階電子文件探索

本主題說明如何載入至進階電子文件中的案例中的內容搜尋的結果。 
  
> [!IMPORTANT]
> 隨著我們繼續投資於更新版本的進階電子文件探索，我們現在宣布停用 Office 365 進階文件探索 (也稱為*進階文件探索 1.0 版*)。 如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。 進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。 若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。  
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a>步驟 1： 準備 Office 365 資料以供進階電子文件

若要分析資料的進階電子文件，您可以使用您執行 Microsoft 365 安全性中的內容搜尋的結果&amp;合規性中心 (Microsoft 365 安全性中的 [**內容搜尋**] 頁面上列出&amp;合規性中心) 或 eDiscovery 案例相關聯的搜尋 (安全性 [ **eDiscovery** ] 頁面上列出&amp;合規性中心)。 
  
如需準備進階 eDiscovery 中分析的搜尋結果詳細步驟，請參閱[準備 Office 365 進階電子文件探索的搜尋結果](prepare-search-results-for-advanced-ediscovery.md)。
  
> [!NOTE]
> 如果您有 Office 365 外部資料，並且想要匯入 Office 365，以便您可以準備和分析的進階電子文件，請參閱[ Overview of 匯入 PST 檔案複製到 Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) and [Office 365 中的封存協力廠商資料](https://go.microsoft.com/fwlink/p/?linkid=716918)。 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>步驟 2： 負載搜尋結果中資料至進階電子文件中的案例

您準備好的搜尋結果中的安全性之後&amp;進行分析的合規性中心下, 一步是載入至進階電子文件中的案例的搜尋結果中。 如需詳細資訊，請參閱[執行處理序模組](run-the-process-module-in-advanced-ediscovery.md)。
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在安全性與合規性中心，按一下 [搜尋和調查]**** \> [電子文件探索]****，來顯示貴組織中的案例清單。 
    
4. 您想要將資料載入在進階電子文件中的案例旁邊，按一下 [**開啟**]。 
    
5. 在案例的 [首頁]**** 頁面上，按一下 [進階電子文件探索]****。 
    
    ![按一下切換以開啟 [進階電子文件中的 [大小寫的進階 ediscovery](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    **連線至進階電子文件**會顯示進度列。 當您已連線至進階電子文件時，在這種情況的 [設定] 頁面上會顯示容器的清單。 
    
    ![這種情況會顯示在進階電子文件](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     這些容器代表您準備好在步驟 1 中的進階 eDiscovery 中分析的搜尋結果。 附註容器的名稱中安全性的案例有同名的內容搜尋&amp;合規性中心。 在清單容器是您備妥。 如果不同的使用者準備進階電子文件中的搜尋結果，將不會在清單中包含對應的容器。 
    
6. 若要從容器中的搜尋結果資料載入至進階電子文件中的案例中，選取的容器，然後按一下 [**程序**。
    
從安全性搜尋結果之後&amp;合規性中心會新增至進階電子文件探索中的情況下一步是在進階電子文件中使用的工具來分析並 cull 與案件相關的資料。 
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[設定使用者和案例](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[分析案例資料](analyze-case-data-with-advanced-ediscovery.md)
  
[管理相關性設定](manage-relevance-setup-in-advanced-ediscovery.md)
  
[使用相關性模組](use-relevance-in-advanced-ediscovery.md)
  
[匯出案例資料](export-case-data-in-advanced-ediscovery.md)

