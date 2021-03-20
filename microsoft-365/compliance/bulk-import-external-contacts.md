---
title: 將外部連絡人大量匯入到 Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 瞭解系統管理員如何使用 Exchange Online PowerShell 和 CSV 檔案，以將外部連絡人大容量匯入全域通訊清單。
ms.openlocfilehash: 178e3676f8dc5fb59cdad9cc46d7ecbd9dddb90e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918209"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>將外部連絡人大量匯入到 Exchange Online

**本文適用于系統管理員。您嘗試將連絡人匯入您自己的信箱嗎？請參閱 [將連絡人匯入 Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
您的公司是否有許多您想要包含在共用通訊錄中的現有商務連絡人 (也稱為全域通訊清單) 在 Exchange Online 中？ 您是否要將外部連絡人新增為通訊群組的成員，就像您可以搭配公司內的使用者一樣？ 如果是的話，您可以使用 Exchange Online PowerShell 和 CSV (逗號分隔值) 檔案，以將外部連絡人大量匯入 Exchange Online。 這是三個步驟的處理常式：
  
[步驟1：建立包含外部連絡人相關資訊的 CSV 檔案](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[步驟2：使用 PowerShell 建立外部連絡人](#step-2-create-the-external-contacts-with-powershell) 

[步驟3：將資訊新增至外部連絡人的屬性](#step-3-add-information-to-the-properties-of-the-external-contacts)

在您完成這些步驟以匯入連絡人之後，您可以執行下列額外的工作：
  
- [新增更多外部連絡人](#add-more-external-contacts)
  
- [隱藏共用通訊錄中的外部連絡人](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>步驟1：建立包含外部連絡人相關資訊的 CSV 檔案

第一步是建立 CSV 檔案，其中包含您要匯入 Exchange Online 之每個外部連絡人的相關資訊。 
  
1. 將下列文字複製到記事本中的文字檔，並使用檔案名尾碼 .csv，將其儲存在您的桌面機為 CSV 檔案。例如，ExternalContacts.csv。
    
    > [!TIP]
    > 如果您的語言包含特殊字元 (例如 **å**、 **ä** 和 **ö** in 瑞典文中) 使用 UTF-8 或其他 Unicode 編碼方式儲存 CSV 檔案，當您在 [記事本] 中儲存檔案時。 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    CSV 檔案的第一列（或標題列）會列出當您匯入 Exchange Online 時可使用的連絡人的屬性。 每個屬性名稱都會以逗號分隔。 標頭列底下的每一列都代表用來匯入單一外部連絡人的屬性值。 
    
    > [!NOTE]
    > 此文字包含您可以刪除的範例資料。 不過，請勿刪除或變更第一個 (頁首) 列。 包含外部連絡人的所有屬性。 
  
2. 在 Microsoft Excel 中開啟 CSV 檔案，以編輯 CSV 檔案，因為使用 Excel 編輯 CSV 檔案的方式很簡單。
    
3. 針對您要匯入 Exchange Online 的每個連絡人建立一列。 盡可能填入盡可能多的儲存格。 這項資訊會顯示在每個連絡人的共用通訊錄中。 
    
    > [!IMPORTANT]
    >  下列屬性 (是建立外部連絡人時需要) 標頭列中的前四個專案，必須在 CSV 檔案中填入： **ExternalEmailAddress**、 **Name**、 **FirstName**、 **LastName**。 您在步驟2中執行的 PowerShell 命令會使用這些屬性的值來建立連絡人。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>步驟2：使用 PowerShell 建立外部連絡人

下一步是使用您在步驟1中建立的 CSV 檔案 PowerShell，將 CSV 檔案中列出的外部連絡人大量匯入 Exchange Online。 
  
1.  將 PowerShell 連接至您的 Exchange Online 組織。 如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 當您連線至 Exchange Online PowerShell 時，請務必使用全域系統管理員帳戶的使用者名稱和密碼。 
    
2. 在您將 PowerShell 連接至 Exchange Online 之後，請移至您在步驟1中儲存 CSV 檔案的桌面資料夾;例如 `C:\Users\Administrator\desktop` 。
    
3. 執行下列命令來建立外部連絡人：

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    視您要匯入的數目而定，可能需要一段時間來建立新的連絡人。 當命令執行完畢時，PowerShell 會顯示已建立之新連絡人的清單。 
    
4. 若要查看新的外部連絡人，請移至 Exchange 系統管理中心 (EAC) ， **然後按一下 [** 收件者 \> **連絡人**]。 
    
    > [!TIP]
    > 如需連接到 EAC 的指示，請參閱 exchange [Online 中的 exchange 系統管理中心](/exchange/exchange-admin-center)。 
  
5. 如有必要， **請按一下 [** 重新整理] 以更新清單，並查看已匯入的外部連絡人。 
    
    匯入的連絡人會出現在 Outlook 和 Outlook 網頁版的共用通訊錄中。
    
    > [!NOTE]
    > 您也可以移至 [ **使用者**] [連絡人]，以查看 Microsoft 365 系統管理中心中的連絡人 \> ****。 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>步驟3：將資訊新增至外部連絡人的屬性

在步驟2中執行此命令之後，會建立外部連絡人，但不會包含任何連絡人或組織資訊，也就是 CSV 檔案中大部分儲存格的資訊。 這是因為當您建立新的外部連絡人時，只會填入必要的屬性。 如果您沒有所有在 CSV 檔案中填入的資訊，請不要擔心。 如果不存在，則不會新增它。
  
1.  將 PowerShell 連接至您的 Exchange Online 組織。 如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
    
2. 移至您在步驟1中儲存 CSV 檔的 [桌面] 資料夾。例如， `C:\Users\Administrator\desktop` 。
    
3. 執行下列兩個命令，以將其他屬性從 CSV 檔案新增至您在步驟2中建立的外部連絡人。
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _Manager_ 參數可能會發生問題。 如果在 CSV 檔案中儲存格是空白的，您會收到錯誤，而且不會將任何屬性資訊新增至連絡人。 如果您不需要指定管理員，請只  ` -Manager $_.Manager ` 從先前的 PowerShell 命令中刪除。 
  
    再說一次，可能需要一段時間來更新連絡人，視您在步驟1中匯入的數目而定。 
    
4. 若要確認已將屬性新增至連絡人： 
    
1. In the EAC, go to **Recipients** \> **Contacts**.
    
2. 按一下連絡人，然後按一下 [ **編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 以顯示連絡人的屬性。 
    
這就對了！ 使用者可以在通訊錄 Outlook 和 Outlook 網頁版上看到連絡人及其他資訊。
  
## <a name="add-more-external-contacts"></a>新增更多外部連絡人

您可以重複步驟1到步驟3，在 Exchange Online 中新增新的外部連絡人。 您或您公司中的使用者只可以在新的連絡人的 CSV 檔案中新增一列。 然後，您可以執行步驟2和步驟3中的 PowerShell 命令，以建立新連絡人的資訊並新增資訊。
  
> [!NOTE]
> 當您執行命令以建立新的連絡人時，可能會收到錯誤訊息，指出先前建立的連絡人已存在。 但已建立任何新增至 CSV 檔案的新連絡人。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>隱藏共用通訊錄中的外部連絡人>

有些公司可能只會使用外部連絡人，因此可以新增為通訊群組的成員。 在此案例中，他們可能會想要隱藏共用通訊錄中的外部連絡人。 方法如下：
  
1.  將 PowerShell 連接至您的 Exchange Online 組織。 如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
    
2. 若要隱藏單一外部連絡人，請執行下列命令。
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    例如，若要隱藏共用通訊錄中的 Pilar Pinilla，請執行下列命令：

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. 若要隱藏共用通訊錄中的所有外部連絡人，請執行下列命令：

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

在您隱藏這些連絡人之後，就不會顯示在共用通訊錄中的外部連絡人，但您仍然可以將它們新增為通訊群組的成員。