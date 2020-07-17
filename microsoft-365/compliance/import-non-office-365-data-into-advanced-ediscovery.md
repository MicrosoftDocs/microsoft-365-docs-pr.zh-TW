---
title: 匯入非 Microsoft 365 內容以進行高級 eDiscovery 分析
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
description: 操作方法：將未儲存在 Microsoft 365 中的內容匯入 Azure blob，以便使用 AeD 來進行分析
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fbb21f6bc3fdfd2a5251a9ec773a22351db5749e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817592"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>匯入非 Microsoft 365 內容以取得 Advanced eDiscovery （傳統）分析

並非所有您需要使用高級 eDiscovery 進行分析的檔，都將會在 Microsoft 365 中活。 使用高級 eDiscovery 的非 Microsoft 365 內容匯入功能，您可以將不在 Microsoft 365 中的檔（PST 檔除外）上傳至連結的情況下，Azure 儲存區 blob 和使用高級 eDiscovery 進行分析。 此程式顯示如何將您的非 Microsoft 365 檔放入高級 eDiscovery 以進行分析。
  
> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
> [!NOTE]
> 您可以購買非 Microsoft 365 內容的高級 eDiscovery 資料儲存區訂閱。 這只適用于使用高級 eDiscovery 進行分析的內容。 遵循[為商務用 Microsoft 365 購買或編輯附加](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on)元件中的步驟，並購買「Advanced eDiscovery 儲存」附加元件。 
  
## <a name="requirements-to-upload-non-office-365-content"></a>上傳非 Office 365 內容的需求

使用此程式所述的「上傳非 Office 365」功能，需要具備下列專案：
  
- Office 365 E3 含高級合規性增益集或 E5 訂閱
    
- 所有非 Office 365 內容的保管人，都必須具備具有高級合規性附加元件或 E5 授權的 E3。
    
- 現有的 eDiscovery 案例
    
- 所有檔案，可將收集到的資料夾中，每個保管人都有一個資料夾，而且資料夾的名稱為*alias@domainname*的此格式。 *Alias@domainname*必須是使用者 Office 365 別名和網域。 您可以將所有*alias@domainname*資料夾收集至根資料夾。 根資料夾只能包含*alias@domainname*資料夾，根資料夾中一定沒有鬆散檔案 
    
- 既可以是 eDiscovery 管理員，也可以是 eDiscovery 管理員的帳戶
    
- 在具有非 Office 365 內容資料夾結構存取權的電腦上安裝[Microsoft Azure Storage Tool 工具](https://aka.ms/downloadazcopy)。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>將非 Office 365 內容上傳至高級電子檔探索


1. 以 eDiscovery 管理員或 eDiscovery 管理員的身分開啟**ediscovery**，然後開啟非 Office 365 資料將上傳至的情況。 如果您需要建立案例，請參閱[在安全性與 &amp; 合規性中心管理 eDiscovery 案例](ediscovery-cases.md)
    
2. 按一下 [**切換至高級 eDiscovery** ]
    
3. 在 [**來源類型**] 下，選取 [**非 Office 365 資料**]。
    
4. 按一下 [**新增容器**]。 命名容器並新增描述。
    
5. 從容器清單中選取新加入的容器，然後複製容器詳細資料窗格中顯示的 URL，然後關閉窗格
    
6. 以系統管理員身分開啟命令提示字元，並將目錄變更為已安裝 AzCopy 的資料夾。
    
7. 構造 AzCopy 命令列，將檔案上傳如下：
    
    AzCopy/Source：「*本機電腦上根資料夾的完整路徑，* "/Dest："*容器 URL，但未包含？*  "/DestSAS："*來自「？」的容器 url 的其餘部分。至結束*"/S。 
    
    例如，使用這些值： 
    
  - 根資料夾-C:\Collected 資料 
    
  - 容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp ; sr = c &amp; Si = NonOfficeData15% 7C0 &amp; sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3d
    
    AzCopy 命令列語法如下：
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    如需 Azcopy 語法的詳細資訊，請參閱[使用 Windows 上的 AzCopy 傳輸資料](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。 
    
    > [!IMPORTANT]
    > 每位使用者都必須有一個根資料夾，而且資料夾名稱必須是*alias@domainname*格式。 
  
8. 完成上傳資料夾後，請切換回「高級電子檔探索」。 您上傳的資料夾內容現在可以在高級 eDiscovery 中處理。 選取容器，然後按一下 [處理] 按鈕。 如需有關高級 eDiscovery 處理的詳細資訊，請參閱，[在高級 ediscovery 中執行 Process module 和 load data](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > 在高級 eDiscovery 中成功處理容器後，您就無法再將新內容新增至 Azure 中的 SAS 儲存體。 如果您收集其他內容，而且想要將其新增至案例以進行高級 eDiscovery 分析，您必須建立新的**非 Office 365 資料**容器，並重複此程式。 
  
    > [!NOTE]
    > 如果容器*由於資料夾命名問題而無法順利處理*，而您又修正問題，則您仍然需要使用本文中的程式建立新的容器，並重新連線並上傳。
