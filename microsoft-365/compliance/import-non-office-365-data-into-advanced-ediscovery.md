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
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636950"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>匯入非 Microsoft 365 內容以取得 Advanced eDiscovery (傳統) 分析

並非所有您需要使用高級 eDiscovery 進行分析的檔，都將會在 Microsoft 365 中活。 使用高級 eDiscovery 的非 Microsoft 365 內容匯入功能，您可以將不在 Microsoft (365 中的檔上傳) 至連結的情況下，Azure storage blob 和使用 Advanced eDiscovery 進行分析的情況下，則不會使用 PST 檔案。 此程式顯示如何將您的非 Microsoft 365 檔放入高級 eDiscovery 以進行分析。
  
> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
> [!NOTE]
> 您可以購買非 Microsoft 365 內容的高級 eDiscovery 資料儲存區訂閱。 這只適用于使用高級 eDiscovery 進行分析的內容。 遵循 [為商務用 Microsoft 365 購買或編輯附加](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) 元件中的步驟，並購買「Advanced eDiscovery 儲存」附加元件。 
  
## <a name="requirements-to-upload-non-office-365-content"></a>上傳非 Office 365 內容的需求

使用此程式所述的「上傳非 Office 365」功能，需要具備下列專案：
  
- 具有高級合規性附加元件或 E5 訂閱的 Office 365 E3。
    
- 所有非 Office 365 內容的保管人，都必須具備具有高級合規性附加元件或 E5 授權的 E3。
    
- 現有的 eDiscovery 案例。
    
- 所有檔案，可將收集到的資料夾中，每個保管人都有一個資料夾，而且資料夾的名稱為  *alias@domainname*  的此格式。 *Alias@domainname*必須是使用者 Office 365 別名和網域。 您可以將所有  *alias@domainname*  資料夾收集至根資料夾。 根資料夾只能包含  *alias@domainname*  資料夾，根資料夾中一定沒有鬆散檔案。
    
- 電子檔探索管理員或 eDiscovery 管理員的帳戶。
    
- 在具有非 Office 365 內容資料夾結構存取權的電腦上安裝[Microsoft Azure Storage Tool 工具](https://aka.ms/downloadazcopy)。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>將非 Office 365 內容上傳至高級電子檔探索


1. 以 eDiscovery 管理員或 eDiscovery 管理員的身分開啟 **ediscovery**，然後開啟非 Office 365 資料將上傳至的情況。 如果您需要建立案例，請參閱在 [安全性與 &amp; 合規性中心管理 eDiscovery 案例](ediscovery-cases.md)。
    
2. 按一下 [ **切換至高級 eDiscovery**]。

3. 從功能表中選取 [ **複查集** ]。

4. 選取現有的複查集，或選擇 [ **新增複查集**]。

5. 選取 [ **管理審閱集**]。

6. 在 [非 Office 365 數據卡] 中，選取 [ **View 上傳**]。

7. 選擇 [ **上傳** 檔案] 以啟動 [檔案上傳] 嚮導。

8. 第一個索引標籤為 **1。準備步驟**。 選取 **[下一步：上傳檔案]**。

9. 在 **2。上傳** 檔案] 索引標籤若尚未這麼做，則會提示您下載 AzCopy.exe （如果尚未這麼做），然後提供檔案位置的路徑。 例如， `C:\Upload`  將會提供執行 AzCopy.exe 的命令。 使用 `C:\Upload` ，您將會看到：

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. 開啟 [命令提示字元] 視窗，並執行 AzCopy.exe 命令，將資料匯入 Azure。 一旦載入所有資料，請選取 **[下一步：處理檔案]**。

11. 下一個 tab 鍵是 **3。處理** 檔案，您會看到擁有相關資料的保管人，也會顯示要匯入資料的進度。
        
    如需 Azcopy 語法的詳細資訊，請參閱 [使用 Windows 上的 AzCopy 傳輸資料](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。 
    
    如需有關高級 eDiscovery 處理的詳細資訊，請參閱在 [Advanced ediscovery (傳統) 中執行進程模組和載入資料 ](run-the-process-module-and-load-data-in-advanced-ediscovery.md)。 
    
    > [!IMPORTANT]
    > 每位使用者都必須有一個根資料夾，而且資料夾名稱必須是 <b>alias@domainname</b>  格式。 
   
    > [!IMPORTANT]
    > 在高級 eDiscovery 中成功處理容器後，您就無法再將新內容新增至 Azure 中的 SAS 儲存體。 如果您收集其他內容，而且想要將其新增至案例以進行高級 eDiscovery 分析，您必須建立新的 **非 Office 365 資料** 容器，並重複此程式。 
  
    > [!NOTE]
    > 如果容器  *由於資料夾命名問題而無法順利處理*  ，而您又修正問題，則您仍然需要使用本文中的程式建立新的容器，並重新連線並上傳。
