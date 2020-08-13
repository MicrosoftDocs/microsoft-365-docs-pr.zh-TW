---
title: 搜尋並刪除郵件 - 管理中心說明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 系統管理員可以使用 Search-Mailbox Cmdlet 來搜尋使用者信箱，然後刪除信箱中的郵件。
ms.openlocfilehash: b3505026034fabcc6d509e7a187fafc5691ef9e7
ms.sourcegitcommit: ca06ee52dec472d3827983d67b049847ec2fdfc1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2020
ms.locfileid: "41256651"
---
# <a name="search-for-and-delete-messages---admin-help"></a>搜尋並刪除郵件 - 管理中心說明
  
系統管理員可以使用**Search-Mailbox** Cmdlet 來搜尋使用者信箱，然後刪除信箱中的郵件。 
  
若要在一個步驟中搜尋並刪除郵件，請使用_DeleteContent_參數執行**Search-Mailbox** Cmdlet。 不過，當您執行此動作時，您無法預覽搜尋結果或產生搜尋會傳回的訊息記錄，而且您可能會無意中刪除您不想要的郵件。 若要在刪除之前預覽搜尋中找到的郵件記錄，請使用_LogOnly_參數執行**Search-Mailbox** Cmdlet。 
  
另外，您也可以使用_TargetMailbox_和_TargetFolder_參數，將郵件複製到另一個信箱。 這樣一來，您就可以保留已刪除郵件的複本，以備您需要重新存取。 
  
## <a name="before-you-begin"></a>開始之前

- 預估完成時間：10 分鐘。 實際時間可能會根據信箱和搜尋查詢的大小而有所不同。
    
- 您無法使用 Exchange 系統管理中心 (EAC) 來執行這些程式。 您必須使用命令介面。
    
- 您必須被指派下列兩個管理角色，才能在使用者的信箱中搜尋並刪除郵件：
    
  - **信箱搜尋**-此角色可讓您在組織中的多個信箱間搜尋郵件。 根據預設，系統管理員不會被指派這個角色。 若要指派此角色給您，讓您能夠搜尋信箱，請將自己新增為「探索管理」角色群組的成員。 請參閱[將使用者新增至探索管理角色群組](https://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。
    
  - **信箱匯入匯出**-此角色可讓您刪除使用者信箱中的郵件。 根據預設，此角色不會指派給任何角色群組。 若要刪除使用者信箱中的郵件，您可以將信箱匯入匯出角色新增至組織管理角色群組。 如需詳細資訊，請參閱[Manage Role Groups](https://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)中的「新增角色至角色群組」一節。 
    
- 如果您想要從中刪除郵件的信箱已啟用單一專案復原，則必須先停用該功能。 如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](https://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。
    
- [！附注] 如果您想要刪除其郵件的信箱處於暫止狀態，建議您先檢查您的記錄管理或法律部門，再移除保留，然後刪除信箱內容。 取得核准後，請依照主題中所列的步驟[清除 [可復原的專案] 資料夾](https://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)。
    
- 您最多可使用**Search-Mailbox** Cmdlet 搜尋10000個信箱。 如果您是 Exchange Online 組織，且擁有超過10000個信箱，您可以使用相容性搜尋功能 (或對應的**New-ComplianceSearch** Cmdlet) 來搜尋不限數量的信箱。 然後，您可以使用**New-ComplianceSearchAction** Cmdlet 刪除符合性搜尋所傳回的郵件。 如需詳細資訊，請參閱[搜尋並刪除 Office 365 組織中的電子郵件訊息](https://go.microsoft.com/fwlink/p/?LinkId=786856)。
    
- 如果您使用*SearchQuery*) 參數包含搜尋查詢 (， **Search-Mailbox**指令程式會在搜尋結果中傳回最多10000個專案。 因此，如果您包含搜尋查詢，您可能需要多次執行**Search-Mailbox**命令，以刪除10000以上的專案。 
    
- 當您執行**Search-Mailbox** Cmdlet 時，也會搜尋使用者的封存信箱。 同樣地，當您使用**Search-Mailbox** Cmdlet 搭配_DeleteContent_參數時，將會刪除主要封存信箱中的專案。 若要避免這種情況，您可以加入*DoNotIncludeArchive*參數。
    
## <a name="search-messages-and-log-the-search-results"></a>搜尋郵件並記錄搜尋結果

本範例會搜尋四月 Stewart 的信箱中的郵件，其中包含主旨欄位中的「銀行對帳單」一詞的郵件，並將搜尋結果記錄在系統管理員信箱的 SearchAndDeleteLog 資料夾中。 郵件不會複製到或從目標信箱中刪除。
  
```powershell
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

這個範例會在組織中的所有信箱中搜尋包含檔案名中包含 "特洛伊木馬" 字樣的郵件，並將記錄郵件傳送至管理員的信箱。
  
```powershell
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](https://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。
  
 
## <a name="search-and-delete-messages"></a>搜尋和刪除郵件

這個範例會搜尋四月 Stewart 的信箱，尋找包含 [主旨] 欄位中的「銀行對帳單」一詞的郵件，並從來源信箱刪除郵件，但不將搜尋結果複製到另一個資料夾。 如先前所述，您必須獲指派「信箱匯入匯出」管理角色，才能刪除使用者信箱中的郵件。
  
> [!IMPORTANT]
> 當您使用**Search-Mailbox** Cmdlet 搭配_DeleteContent_參數時，會永久刪除來源信箱中的郵件。 在您永久刪除郵件之前，建議您先使用_LogOnly_參數，在刪除之前，先產生搜尋中所發現郵件的記錄，然後再將郵件複製到另一個信箱，然後再將郵件從來源信箱中刪除。 
  
```powershell
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

本範例會搜尋四月 Stewart 的信箱，尋找包含 [主旨] 欄位中的「銀行對帳單」一詞的郵件，將搜尋結果複製到信箱 BackupMailbox 中的資料夾 AprilStewart-DeletedMessages，並刪除四月的信箱中的郵件。
  
```powershell
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

這個範例會搜尋組織中的所有信箱中的郵件，其中包含主旨行「下載這個檔案」，然後永久刪除這些郵件。 
  
```powershell
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](https://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。

## <a name="using-the--loglevel-full-parameter"></a>使用-LogLevel Full 參數

在先前的某些範例中，會使用具有值的_LogLevel_參數， `Full` 記錄**Search-Mailbox** Cmdlet 所傳回之結果的詳細資訊。 當您包含此參數時，會建立電子郵件訊息，並將其傳送至_TargetMailbox_參數所指定的信箱。 記錄檔 (，它是名為 Search Results.csv) 的 CSV 格式化檔案，會附加到這封電子郵件，而且會位於_TargetFolder_參數所指定的資料夾中。 當您執行**Search-Mailbox** Cmdlet 時，記錄檔會針對搜尋結果中包含的每一封郵件包含一列。 
