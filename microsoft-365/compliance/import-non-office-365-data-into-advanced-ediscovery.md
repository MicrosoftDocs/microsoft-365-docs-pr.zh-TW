---
title: 匯入非 Office 365 進階電子文件探索分析內容
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: 如何步驟以匯入內容，不會儲存在 O365 到 Azure blob，讓它可以與 AeD 分析
ms.openlocfilehash: 529eb21117ed2cdfbb7f02caf058dbc6863d2d9b
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557893"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-classic-analysis"></a>匯入非 Office 365 進階電子文件 （傳統） 分析內容

並非所有文件，您可能需要與 Office 365 進階電子文件探索分析會存在於 Office 365 中。 使用非 Office 365 內容匯入您可以上傳文件，不到案例的連結、 Azure 儲存體 blob live （除了 PST 檔案） 的 Office 365 中並分析其與進階電子文件的進階電子文件中的功能。 此程序將示範如何將非 Office 365 文件移入進階電子文件探索進行分析。
  
> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
> [!NOTE]
> 您可以購買 Office 365 進階電子文件探索資料儲存空間] 附加元件訂閱的非 Office 365 內容。 這是專門供進行分析使用進階電子文件的內容。 請遵循[購買或編輯和商務用 Office 365 的附加元件形式](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)中的步驟及購買 Office 365 進階電子文件探索儲存附加元件。 
  
## <a name="before-you-begin"></a>開始之前

使用此程序所述的上傳非 Office 365 功能需要您：
  
- 使用進階合規性的附加元件或 E5 訂閱 Office 365 E3
    
- 將上傳其非 Office 365 內容的所有 custodians 都必須 E3 與進階合規性的附加元件或 E5 授權
    
- 現有的 eDiscovery 案例
    
- 上傳的所有檔案所都收集到資料夾，其中沒有 custodian 每一個資料夾，而且此格式*alias@domainname*中已有該資料夾的名稱。 *Alias@domainname*必須是 Office 365 的使用者別名及網域。 您可以收集所有*alias@domainname*資料夾到根資料夾。 根資料夾只能包含*alias@domainname*資料夾、 根資料夾中必須有任何鬆散檔案 
    
- EDiscovery 管理員 」 或 「 eDiscovery 系統管理員帳戶
    
- 具有非 Office 365 內容的資料夾結構的存取權的電腦上安裝[Microsoft Azure 儲存體工具](https://aka.ms/downloadazcopy)。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>非 Office 365 內容上傳至進階電子文件


1. EDiscovery 管理員或 eDiscovery 系統管理員，以開啟 [ **eDiscovery**]，並開啟非 Office 365 資料就會上傳到的案例。 如果您需要建立案例，請參閱[管理 Office 365 安全性中的 eDiscovery 案例&amp;合規性中心](ediscovery-cases.md)
    
2. 按一下 [**切換至進階電子文件**
    
3. **來源類型**] 下選取 [**非 Office 365 資料**]。
    
4. 按一下 [**新增] 容器**。 名稱容器，並且新增描述。
    
5. 從其在容器清單中選取新加入的容器，然後複製出現在 [容器] 詳細資料窗格中，然後關閉 [] 窗格中的 URL
    
6. 開啟命令提示字元以系統管理員身分，將目錄變更必須 AzCopy 安裝資料夾...
    
7. 建構 AzCopy 命令列上傳的檔案，如下所示：
    
    AzCopy /Source: 「*在本機電腦上的根資料夾的完整路徑*」 /Dest: 「*容器 URL，但不是包括？*  「 /DestSAS: 「*其餘部分來自容器 url？結尾*"/ S 
    
    例如，使用這些值： 
    
  - 根資料夾-C:\Collected 資料 
    
  - 容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15 %7 C 0&amp;簽章 = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA %3d
    
    AzCopy 命令列語法為：
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    如需有關 Azcopy 語法，請參閱[傳輸與 windows AzCopy 的資料](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。 
    
    > [!IMPORTANT]
    > 必須有一個每位使用者根資料夾和資料夾名稱必須是*alias@domainname*格式。 
  
8. 一旦資料夾完成上傳，切換回進階電子文件。 在您上傳的資料夾中的內容已準備好在進階電子文件中處理。 選取的容器，然後按一下 [處理序] 按鈕。 如需詳細資訊，在 [進階電子文件上處理，請[執行處理序模組及載入 Office 365 進階電子文件探索中的資料](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > 一旦成功處理進階電子文件的容器，您將不再能夠將新的內容新增至 Azure 中的 SAS 儲存。 如果您收集其他內容，而且您想要將其新增至進階電子文件探索分析案例，您必須建立新的**非 Office 365 資料**容器，並重複此程序。 
  
    > [!NOTE]
    > 如果容器*不會處理成功由於資料夾命名問題*，而且您然後修正問題，您仍然必須建立新的容器，並重新連線並上傳一次使用本文中的程序。
