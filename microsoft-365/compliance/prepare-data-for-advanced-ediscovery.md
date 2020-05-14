---
title: 準備進階電子文件探索的資料
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
description: '瞭解如何使用安全性 &amp; 與合規性中心，準備要使用高級 eDiscovery 進行分析的資料。 '
ms.openlocfilehash: 31bf002c275b228de12b7ff9e39fabf7c72be74d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214281"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a>準備資料以供高級 eDiscovery （經典）

本主題說明如何在高級 eDiscovery （經典）中，將內容搜尋的結果載入至案例。 
  
> [!IMPORTANT]
> 隨著我們繼續投資於更新版本的進階電子文件探索，我們即將宣布停用進階文件探索 (也稱為*進階電子文件探索 (傳統版)* 或*進階文件探索 1.0 版*)。 如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。 進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。 若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a>步驟1：準備用於高級電子檔探索的資料

若要使用 Advanced eDiscovery 來分析資料，您可以使用 Microsoft 365 安全性與合規性中心中所執行的內容搜尋結果 &amp; （列于 microsoft 365 安全性與合規性中心的 [**內容搜尋**] 頁面上 &amp; ），或與 eDiscovery 案例相關聯的搜尋（列在 [安全性與規範中心] 中的 [ **ediscovery** ] 頁面上 &amp; ）。 
  
如需在高級 eDiscovery 中準備搜尋結果以進行分析的詳細步驟，請參閱[準備高級 ediscovery 的搜尋結果](prepare-search-results-for-advanced-ediscovery.md)。
  
> [!NOTE]
> 如果您有超出 Microsoft 365 的資料，且想要將資料匯入至 Microsoft 365，以便在高級 eDiscovery 中準備及分析它，請參閱將 PST 檔案匯[入至 Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)並封存[協力廠商資料](https://www.microsoft.com/?ref=go)的總覽。 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>步驟2：在高級 eDiscovery 中將搜尋結果資料載入到案例中

在安全性與規範中心中準備好搜尋結果 &amp; 以進行分析之後，下一步是在高級 eDiscovery 中的案例中載入搜尋結果。 如需詳細資訊，請參閱[執行 Process module](run-the-process-module-in-advanced-ediscovery.md)。
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您的公司或學校帳戶登入。
    
3. 在安全性與合規性中心，按一下 [搜尋和調查]**** \> [電子文件探索]****，來顯示貴組織中的案例清單。 
    
4. 在 [高級 eDiscovery] 中，按一下您想要在其中載入資料之案例旁邊的 [**開啟**]。 
    
5. 在案例的 [首頁]**** 頁面上，按一下 [進階電子文件探索]****。 
    
    ![按一下 [切換至高級 eDiscovery]，以在 [高級 eDiscovery] 中開啟案例。](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    隨即會顯示 [連線**至高級 eDiscovery** ] 進度列。 當您連線至「高級 eDiscovery」時，容器清單會顯示在案例的 [設定] 頁面上。 
    
    ![案例會顯示在高級 eDiscovery](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     這些容器代表您在步驟1的高級 eDiscovery 中準備分析的搜尋結果。 請注意，在安全性與合規性中心的案例中，容器的名稱與內容搜尋的名稱相同 &amp; 。 清單中的容器是您準備的容器。 如果不同的使用者已為高級 eDiscovery 準備好搜尋結果，對應的容器將不會包含在清單中。 
    
6. 若要在高級 eDiscovery 的案例中從容器中載入搜尋結果資料，請選取容器，然後按一下 [**處理**]。
    
在將安全性與 &amp; 合規性中心的搜尋結果新增至高級 ediscovery 的案例之後，下一步是使用高級 ediscovery 中的工具來分析和挑選與案例相關的資料。 
  
## <a name="see-also"></a>請參閱

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[設定使用者和案例](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[分析案例資料](analyze-case-data-with-advanced-ediscovery.md)
  
[管理相關性設定](manage-relevance-setup-in-advanced-ediscovery.md)
  
[使用相關性模組](use-relevance-in-advanced-ediscovery.md)
  
[匯出案例資料](export-case-data-in-advanced-ediscovery.md)

