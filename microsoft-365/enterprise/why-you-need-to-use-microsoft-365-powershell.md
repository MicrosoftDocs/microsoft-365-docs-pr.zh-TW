---
title: 為什麼您需要使用適用於 Microsoft 365 的 PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 摘要：瞭解為何您必須使用 PowerShell 來管理 Microsoft 365，在某些情況下更有效率，在其他情況下也是必要的。
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688276"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>為什麼您需要使用適用於 Microsoft 365 的 PowerShell

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

使用 Microsoft 365 系統管理中心，您不僅可以管理您的 Microsoft 365 使用者帳戶和授權，還可以管理 Microsoft 365 服務，例如 Exchange Online、小組和 SharePoint 線上。 不過，您也可以使用 PowerShell 命令管理這些元素，充分運用命令列及指令碼語言環境，以取得速度、自動化和其他功能。
  
在本文中，我們將顯示您可以使用 PowerShell 來管理 Microsoft 365 的方式：
  
- 顯示您使用 Microsoft 365 系統管理中心看不到的其他資訊
    
- 設定 PowerShell 的功能和設定
    
- 執行大量作業
    
- 篩選資料
    
- 列印或儲存資料
    
- 跨服務管理
    
開始之前，請先瞭解 Microsoft 365 的 PowerShell 是一組 Windows PowerShell 模組，也就是 Windows 服務和平臺的命令列環境。 此環境會建立命令介面語言，可使用其他模組擴充，並提供執行簡易或複雜命令或腳本的方式。 例如，在您安裝 Microsoft 365 模組的 PowerShell 並聯機至您的 Microsoft 365 訂閱後，您可以執行此命令來列出 Microsoft Exchange Online 的所有使用者信箱：
  
```powershell
Get-Mailbox
```

您也可以使用 Microsoft 365 系統管理中心輕鬆完成信箱清單，但是計算所有 web 應用程式之所有網站的所有清單中的專案數，無法輕易完成。
  
請注意，Microsoft 365 的 PowerShell 設計為增強和增強您管理 Microsoft 365 的能力，而不是取代 Microsoft 365 系統管理中心。 身為系統管理員，您必須至少使用 Microsoft 365 的 PowerShell，因為某些設定程式只能使用 Microsoft 365 命令的 PowerShell 進行。 在這些情況下，您必須了解如何：
  
- 安裝 Microsoft 365 模組的 PowerShell (每個系統管理員電腦) 都只會執行一次。
    
- 連線至您的 Microsoft 365 訂閱 (每個 PowerShell 會話) 都會執行一次。
    
- 收集為 Microsoft 365 命令執行必要 PowerShell 所需的資訊。
    
- 成功執行 Microsoft 365 命令的 PowerShell。
    
了解這些基本技術之後，您不需要使用 **Get-mailbox** 命令列出信箱使用者，也不需要了解如何建立新命令 (例如前一個命令來計算所有 Web 應用程式之所有網站的所有清單中的所有項目)。 Microsoft 和系統管理員群組可以視需要協助您。
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a>Microsoft 365 PowerShell 會顯示您無法使用 Microsoft 365 系統管理中心所看到的其他資訊

Microsoft 365 系統管理中心會顯示許多有用的資訊，但這不意味著它會顯示 Microsoft 365 儲存在使用者、授權、信箱和網站上的所有可能資訊。 以下是 Microsoft 365 系統管理中心中 **使用者和群組** 的範例：
  
![Microsoft 365 系統管理中心中使用者和群組的顯示範例。](../media/o365-powershell-users-and-groups.png)
  
在許多用途中，這會顯示您需要知道的資訊。 不過，您有時需要更多的資訊。 例如，Microsoft 365 授權 (和 Microsoft 365 功能可供使用者) 因使用者的地理位置而異。 您可延伸到美國使用者的原則和功能，與您可延伸到印度或比利時使用者的原則和功能可能不大一樣。 您可以使用 Microsoft 365 系統管理中心，使用下列步驟來判斷使用者的地理位置：
  
1. 連按兩下使用者的 **[顯示名稱]** 。
    
2. 在使用者內容顯示窗格中，按一下 **[詳細資料]** 。
    
3. 在詳細資料顯示中，按一下 **[其他詳細資料]** 。
    
4. 向下捲動，直到您看到 **[國家或地區]** 標題為止。
    
     ![Microsoft 365 系統管理中心中使用者之地區資訊的範例。](../media/o365-powershell-usage-location.png)
  
5. 在一張紙上寫下使用者的顯示名稱和位置，或複製並貼到 [記事本]。 
    
您必須為每位使用者重複此程序。 對於許多使用者，這可能是冗長乏味的工作。 使用 Microsoft 365 的 PowerShell，您可以使用下列命令，為所有使用者顯示此資訊：
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。
>

以下是顯示範例：
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

> [!TIP]
>  此 PowerShell 命令的轉譯如下： ( **AzureADUser** ) 中取得目前 Microsoft 365 訂閱中的所有使用者，但只顯示每位使用者的名稱和位置 ( **選取 DisplayName，UsageLocation** ) 。
  
因為 Microsoft 365 PowerShell 支援命令介面語言，所以您可以進一步操縱 **AzureADUser** 命令中取得的資訊。 例如，您可能想要依其位置排序使用者、將所有巴西使用者組合在一起，將美國所有使用者組合在一起，等等。命令如下：
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

以下是顯示範例：
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

> [!TIP]
>  此 PowerShell 命令的轉譯為：取得目前 Microsoft 365 訂閱中的所有使用者，但是只會顯示每位使用者的名稱和位置，並依其位置排序，然後再以其名稱 ( **sort UsageLocation，DisplayName** ) 。
  
您也可以使用其他篩選。例如，如果您只想看到巴西使用者的資訊，請使用這個命令：
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

以下是顯示範例：
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，其位置是巴西 ( **其中 {$ \_ 。UsageLocation-eq "BR"}** ) ，然後顯示每位使用者的名稱和位置。
  
 **與較大型網域相關的備註**
  
如果您有超大型的網域 (擁有數萬名的使用者)，嘗試我們在本文中所示範的部分範例可能會走向「節流」。 這表示根據如運算能力和可用網路頻寬等項目，您可能一次做太多事情。 因此，較大的組織可能會想要將某些 Microsoft 365 命令的 PowerShell 分割成兩個命令。 例如，此命令會傳回所有使用者帳戶，並顯示每位使用者的名稱和位置：
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

該命令非常適合較小型的網域。然而，在大型組織中，您可能需要將它分割成兩個命令：一個命令用來將使用者帳戶資訊儲存至變數中，而另一個命令用來顯示所需的資訊。範例如下：
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

這組 PowerShell 命令的轉譯如下：
- 取得目前 Microsoft 365 訂閱中的所有使用者，並將資訊儲存在名為 $x 的變數中 ( **$x = AzureADUser** ) 。
- 顯示變數 $x 的內容，但只會包括每位使用者的名稱和位置 ( **$x | Select DisplayName, UsageLocation** )。
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 具有您只能使用 Microsoft 365 PowerShell 所設定的功能

Microsoft 365 系統管理中心主要是用來存取大多數使用者適用的最常見或有意義的管理工作。 換句話說，已設計 Microsoft 365 系統管理中心，讓一般管理員可以使用工具來執行最常見的管理工作。 根據此定義，這表示有一些工作無法使用 Microsoft 365 系統管理中心完成。
  
例如，商務用 Skype Online 系統管理中心提供一些選項來建立自訂會議邀請：
  
![在商務用 Skype Online 系統管理中心內，自訂會議邀請顯示方式的範例。](../media/o365-powershell-meeting-invitation.png)
  
使用這些設定，您可以新增會議邀請的一些個人化和專門技術。不過，這不只是建立自訂會議邀請，還會進行其他會議組態設定。例如，會議預設允許：
  
- 匿名使用者自動進入每個會議。
    
- 出席者記錄會議。
    
- 您組織的所有使用者在加入會議時都會指定為主持人。
    
這些設定無法從 商務用 Skype Online 系統管理中心取得。 不過，您可以從 PowerShell 對 Microsoft 365 進行控制。 以下是停用這三項設定的命令：
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> 這個命令需要您安裝 [商務用 Skype Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)。 
  
> [!TIP]
>  此 PowerShell 命令的轉譯：針對新的商務用 Skype Online 會議設定 ( **Set-CsMeetingConfiguration** ) 、停用讓匿名使用者能夠自動進入會議 (- **AdmitAnonymousUsersByDefault $False** ) 、停用出席者記錄 **會議 ( AllowConferenceRecording $False ) ** ，但不要將組織中的所有使用者指定為簡報者 ( **-DesignateAsPresenter "None"** ) 。
  
如果您改變主意想要還原這些預設設定 (全部都已啟用)，請執行這個命令：
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

這只是其中一個範例。 還有其他一些原因，您在系統管理員的情況下，您必須熟悉 Microsoft 365 命令的執行 PowerShell。
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a>Microsoft 365 的 PowerShell 非常適合執行大量作業

從過去的角度來看，當您執行單一作業時，像是 Microsoft 365 系統管理中心的視覺介面最有價值。 例如，如果您需要停用一個使用者帳戶，您可以使用 Microsoft 365 系統管理中心，快速找出並清除核取方塊。 這可以比在 PowerShell 中執行類似的作業更簡單。
  
不過，如果您必須在大量的其他專案中變更許多專案或某些選取的專案，Microsoft 365 系統管理中心可能無法充分利用您的時間。 例如，如果您必須變更數千個電話號碼的前置詞，或者您需要移除所有 SharePoint 線上網站上的特定使用者（Ken Myer），您會如何在 Microsoft 365 系統管理中心中執行此動作？
  
對於後面的範例，您有數百個 SharePoint Online 網站，而且甚至不知道 Ken Meyer 所屬的網站。 這表示您必須從 Microsoft 365 系統管理中心開始，然後針對每個網站執行此程式：
  
1. 按一下網站的 **URL** 。
    
2. 在 [網站集合內容] 方塊中，按一下 [網站位址] 連結以開啟網站。
    
3. 在網站上，按一下 [共用]。
    
4. 在 [共用] 對話方塊中，按一下連結，以顯示所有具有網站權限的使用者：
    
     ![在 SharePoint Online 系統管理中心內，檢視 SharePoint Online 網站成員的範例。](../media/o365-powershell-view-permissions.png)
  
5. 在 [共用對象] 對話方塊中，按一下 [進階]。
    
6. 捲動使用者清單，並尋找和選取 Ken Myer (假設他具有網站權限)，然後按一下 [移除使用者權限]。
    
因為有數百個網站，所以這可能需要很長的時間。
  
另一種方法是使用 Microsoft 365 的 PowerShell，並使用下列命令，從所有網站中移除 Ken Myer：
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> 這個命令需要您安裝 [SharePoint 線上 PowerShell 模組](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。 
  
> [!TIP]
>  此 PowerShell 命令的轉譯為：取得目前 Microsoft 365 訂閱中的所有 SharePoint 網站 ( **Get-SPOSite** ) 以及每個網站，從可以存取它的使用者清單中移除 Ken Meyer ( **ForEach {Remove-SPOUser 網站 $ \_ 。Url-LoginName "kenmyer@litwareinc.com"}** ) 。
  
因為我們會告訴 Microsoft 365 從每個網站中移除 Ken Meyer，包括其沒有存取權的網站，所以此命令的顯示將會顯示其目前沒有存取權之網站的錯誤。 我們可以在此命令上使用其他條件，只從登入清單中有 Key Meyer 的網站中移除 Key Meyer，但列出的錯誤不會傷害網站本身。 這個命令可能需要幾分鐘的時間來執行數百個網站，而不是透過 Microsoft 365 系統管理中心的工作時間。
  
以下是另一個大量作業範例。使用此命令將 Bonnie Kearney (新的 SharePoint 系統管理員) 新增至組織中的所有網站：
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  此 PowerShell 命令的轉譯為：取得目前 Microsoft 365 訂閱中的所有 SharePoint 網站，並針對每個網站，將其登入名稱新增至網站的 Members 群組，以允許 Bonnie Kearney 存取 ( **ForEach {Add-SPOUser-site $ \_ 。Url-LoginName "bkearney@litwareinc.com"-Group 「Members」}** ) 。
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>Microsoft 365 的 PowerShell 非常適合篩選資料

Microsoft 365 系統管理中心提供數種不同的方式來篩選您的資料，以快速輕鬆地找出目標的資訊子集。 例如，Exchange 可輕鬆篩選使用者信箱的任何內容。 例如，以下是住在布魯民頓市中所有使用者的信箱清單：
  
![在 Microsoft 365 系統管理中心中執行高級搜尋的範例，針對居住于 Bloomington 城市中之所有使用者的信箱清單。](../media/o365-powershell-advanced-search.png)
  
Exchange 系統管理中心也可讓您合併篩選準則。例如，您可以找到住在布魯民頓市並且在財務部門工作之所有人的信箱。 
  
不過，在 Exchange 系統管理中心內有一些限制。例如，您可能想要找到住在布魯民頓市或聖地牙哥市之人員的信箱，或不住在布魯民頓市之所有人員的信箱。 
  
使用 Microsoft 365 的 PowerShell，您可以使用此命令來取得居住在 Bloomington 或聖地牙哥市之所有人員的信箱清單：
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

以下是顯示範例：
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，這些使用者在聖地牙哥或 ( Bloomington 的城市中擁有信箱 **，其是 {$ \_ 。RecipientTypeDetails-eq "UserMailbox" 和 ($ \_ 。城市-eq "聖地牙哥"-或 $ \_ 。City-eq "Bloomington" ) }** ) ，然後顯示每個 ( **選取 DisplayName，城市** ) 的名稱和城市。
  
若要列出不住在布魯民頓市之人員的所有信箱，則命令如下：
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

以下是顯示範例：
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

> [!TIP]
>  此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的信箱未位於 Bloomington 的城市中的所有使用者 ( **其中 {$ \_ 。RecipientTypeDetails-eq "UserMailbox"-和 $ \_ 。City-ne "Bloomington"}** ) ，然後顯示每一個的名稱和城市。
  
您也可以在 PowerShell 篩選中使用萬用字元，以符合部分名稱。 例如，假設您正在尋找一個使用者帳戶，而且您只記得姓氏是 Anderson 或 Henderson，也可能是 Jorgenson。
  
您可以使用搜尋工具並執行三種不同的搜尋，以在 Microsoft 365 系統管理中心中追蹤該使用者：
  
- 一個用於  *Anderson* 
    
- 一個用於  *Henderson* 
    
- 一個用於  *Jorgenson* 
    
因為這些名稱中的三個都以 "兒子" 結尾，您可以告訴 PowerShell 顯示名稱以 "兒子" 結尾的所有使用者。 命令如下：
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，但是使用篩選器，該篩選只會列出姓氏結尾為 "兒子" ( **-filter "{LastName-like" \* 兒子 "}"** ) 的使用者。 \*代表任何一組字元，也就是使用者的姓氏的情況下的字母。
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>Microsoft 365 的 PowerShell 可讓您輕鬆地列印或儲存資料

Microsoft 365 系統管理中心可讓您查看資料清單。 以下是商務用 Skype Online 系統管理中心範例，其中顯示已啟用商務用 Skype Online 的使用者清單：
  
![商務用 Skype Online 系統管理中心，顯示商務用 Skype Online 已啟用的使用者清單的範例。](../media/o365-powershell-lync-users.png)
  
若要將該資訊儲存至檔案，您必須複製該資訊，並將它貼到文件或 Excel。 在任一情況下，複本可能都需要進行其他格式設定。 此外，Microsoft 365 系統管理中心不會提供直接列印所顯示清單的方式。
  
幸運的是，您可以使用 PowerShell，而不只顯示清單，但將它儲存到可輕鬆匯入 Excel 的檔案。 以下範例命令可將 商務用 Skype Online 使用者資料儲存為逗點分隔值 (CSV) 檔案，而這是可輕鬆地匯入為 Excel 工作表中的資料表的檔案：
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

以下是顯示範例：
  
![儲存成逗點分隔值 (CSV) 檔案的商務用 Skype Online 使用者資料表，匯入到 Excel 工作表中的範例。](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  此 PowerShell 命令的轉譯如下：在目前的 Microsoft 365 訂閱中取得所有商務用 Skype Online 使用者 ( **Get-CsOnlineUser** ) 、只取得使用者名稱、UPN 和位置 ( **選取 DisplayName，UserPrincipalName，UsageLocation** ) ，然後將該資訊儲存在名為 C：記錄檔的 CSV 檔案 \\ 中 \\SfBUsers.csv ( **匯出-CSV 路徑 "c： \\ logs \\SfBUsers.csv"-NoTypeInformation** ) 。
  
您也可以使用選項，將此清單儲存為 XML 檔案或 HTML 頁面。事實上，使用其他 PowerShell 命令，您可以直接將它儲存為 Excel 檔 (內含任何您想要的自訂格式)。 
  
您也可以傳送 PowerShell 命令的輸出，將清單直接顯示在 Windows 中的預設印表機。 範例命令如下：
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

以下是您將列印出的文件樣貌：
  
![列印的檔的範例是直接列于 Windows 的預設印表機的 PowerShell 命令輸出。](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  此 PowerShell 命令的轉譯如下：在目前的 Microsoft 365 訂閱中取得所有商務用 Skype Online 使用者、只取得使用者名稱、UPN 和位置，然後將該資訊傳送至預設 Windows printer ( **Out-Printer** ) 。
  
列印的檔具有與 PowerShell 命令視窗中的顯示相同的簡易格式設定，但是一旦您建立 PowerShell 命令以列出您需要的專案，您只需新增 **|Out-Printer** 至命令的結尾，以取得可供使用的硬拷貝。
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Microsoft 365 的 PowerShell 可讓您跨伺服器產品進行管理

組成 Microsoft 365 的不同元件是設計成共同運作。 例如，假設您將新使用者新增至 Microsoft 365，當您這樣做時，您會指定使用者的部門和電話號碼等資訊。 當您使用 Microsoft 365 服務（商務用 Skype Online、Exchange 或 SharePoint 線上）存取使用者的資訊時，該資訊將可供使用。
  
不過，這是對跨越產品系列的一般資訊而言。產品特定資訊 (例如，使用者的 Exchange 信箱相關資訊) 通常不會跨系列提供。例如，如果您想要知道是否已啟用使用者的信箱，則只能在 Exchange 系統管理中心內取得該資訊。 
  
假設您想要製作一份報告，顯示所有使用者的下列資訊：
  
- 使用者的顯示名稱
    
- 使用者是否已取得 Microsoft 365 的授權
    
- 使用者的 Exchange 信箱是否已啟用
    
- 是否已對使用者啟用商務用 Skype Online
    
您目前無法使用 Microsoft 365 管理中心來輕鬆產生這類報告。 相反地，您必須建立個別的檔來儲存資訊，例如 Excel 工作表，並從 Microsoft 365 系統管理中心取得所有的使用者名稱和授權資訊、取得來自 Exchange 系統管理中心的信箱資訊、從商務用 Skype Online 系統管理中心取得商務用 Skype Online 資訊，然後再進行 collate 及合併該資訊。
  
另一種方法是使用 PowerShell 腳本為您編譯該報告。
  
下列範例指令碼會比目前為止在本文中看過的命令還要複雜。 不過，它會顯示可能使用 PowerShell 來建立非常困難的資訊視圖。 以下指令碼可以編譯並顯示所需的清單：
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

以下是顯示範例：
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

此 PowerShell 腳本的轉譯如下：  

- 取得目前 Microsoft 365 訂閱中的所有使用者，並將資訊儲存在名為 $x 的變數中 ( **$x = AzureADUser** ) 。
- 開始迴圈，而迴圈會對名稱為 $x 之變數中的所有使用者執行 ( **foreach ($i in $x)** )。  
- 定義名稱為 $y 的變數，並在其中儲存使用者的信箱資訊 ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** )。
- 將新的屬性新增至名稱為 IsMailBoxEnabled 的使用者資訊，並將它設定為使用者信箱的 IsMailBoxEnabled 屬性值 ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** )。
- 定義名稱為 $y 的變數，並在其中儲存使用者的商務用 Skype Online 資訊 ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** )。
- 將新的屬性新增至名稱為 EnabledForSfB 的使用者資訊，並將它設定為使用者之商務用 Skype Online 資訊的 Enabled 屬性值 ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** )。
- 顯示使用者清單，但只包括其名稱、是否獲得授權，以及指出是否已啟用其信箱以及其是否已啟用商務用 Skype Online 的兩個新屬性 ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** )。
  
## <a name="see-also"></a>另請參閱

[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
  
[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[在 Microsoft 365 中使用 Windows PowerShell 建立報告](use-windows-powershell-to-create-reports-in-microsoft-365.md)

