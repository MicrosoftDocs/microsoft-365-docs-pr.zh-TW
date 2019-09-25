---
title: 批量导入外部联系人到联机交换
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
description: 了解管理员如何使用 Exchange 在线 PowerShell 和 CSV 文件将外部联系人批量导入到全局地址列表。
ms.openlocfilehash: 08fe7666f03c7fe60555133292be9e27a9ffa413
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076650"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>批量导入外部联系人到联机交换

**本文是为管理员。您是否正在尝试将联系人导入您自己的邮箱？请参阅[将联系人导入 Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
您的公司是否有许多现有业务联系人，您希望在 Exchange Online 中的共享通讯簿（也称为全局地址列表）中包括这些联系人？ 是否要将外部联系人添加为通讯组成员，就像可以与公司内部的用户一样？ 如果是这样，您可以使用 Exchange 在线电源外壳和 CSV（通信分离值）文件将外部联系人批量导入 Exchange Online。 这是一个三步过程：
  
[第 1 步：创建包含外部联系人信息的 CSV 文件](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[步骤 2：使用 PowerShell 创建外部联系人](#step-2-create-the-external-contacts-with-powershell) 

[步骤 3：向外部联系人的属性添加信息](#step-3-add-information-to-the-properties-of-the-external-contacts)

完成导入联系人的这些步骤后，可以执行以下其他任务：
  
- [添加更多外部联系人](#add-more-external-contacts)
  
- [从共享通讯簿中隐藏外部联系人](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>第 1 步：创建包含外部联系人信息的 CSV 文件

第一步是创建一个 CSV 文件，该文件包含有关要导入到联机 Exchange 的每个外部联系人的信息。 
  
1. 将以下文本复制到 NotePad 中的文本文件，并使用 .csv 的文件名后缀将其作为 CSV 文件保存到桌面;例如，外部联系人.csv。
    
    > [!TIP]
    > 如果您的语言包含特殊字符（如**瑞典语**中的 ***、*** 和 ***），** 则在 NotePad 中保存文件时，请保存带有 UTF-8 或其他 Unicode 编码的 CSV 文件。 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    CSV 文件的第一行或标题行列出了联系人在导入联机交换时可以使用的属性。 每个属性名称用逗号分隔。 标题行下的每一行表示导入单个外部联系人的属性值。 
    
    > [!NOTE]
    > 此文本包括示例数据，您可以删除这些数据。 但不要删除或更改第一行（标题）。 它包含外部联系人的所有属性。 
  
2. 在 Microsoft Excel 中打开 CSV 文件以编辑 CSV 文件，因为使用 Excel 编辑 CSV 文件要容易得多。
    
3. 为要导入到联机交换的每个联系人创建一行。 填充尽可能多的单元格。 此信息将显示在每个联系人的共享通讯簿中。 
    
    > [!IMPORTANT]
    >  创建外部联系人需要以下属性（头行的前四个项），并且必须在 CSV 文件中填充：**外部电子邮件地址、****姓名、****名字、****姓氏**。 在步骤 2 中运行的 PowerShell 命令将使用这些属性的值创建联系人。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>步骤 2：使用 PowerShell 创建外部联系人

下一步是使用您在步骤 1 和 PowerShell 中创建的 CSV 文件将 CSV 文件中列出的外部联系人批量导入联机交换。 
  
1.  将 PowerShell 连接到您的 Exchange 在线组织。 有关分步说明，请参阅[连接到交换在线 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。 连接到 Exchange 在线 PowerShell 时，请确保使用 Office 365 全局管理员帐户的用户名和密码。 
    
2. 将 PowerShell 连接到联机交换后，转到步骤 1 中保存 CSV 文件的桌面文件夹;如果将 PowerShell 连接到"联机交换"，则转到在步骤 1 中保存 CSV 文件的桌面文件夹。例如`C:\Users\Administrator\desktop`.
    
3. 运行以下命令以创建外部联系人：

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    创建新联系人可能需要一段时间，具体取决于要导入的联系人数。 命令运行完毕后，PowerShell 将显示已创建的新联系人的列表。 
    
4. 要查看新的外部联系人，请转到 Exchange 管理中心 （EAC），**然后单击"收件人**\>**联系人"。** 
    
    > [!TIP]
    > 有关连接到 EAC 的说明，请参阅[Exchange 在线交换管理中心。](https://go.microsoft.com/fwlink/p/?LinkId=328197) 
  
5. 如有必要，**单击"刷新**![刷新"](media/O365-MDM-Policy-RefreshIcon.gif)图标以更新列表并查看导入的外部联系人。 
    
    导入的联系人将显示在 Web 上的 Outlook 和 Outlook 中的共享通讯簿中。
    
    > [!NOTE]
    > 您还可以通过**访问"用户**\>**联系人"** 来查看 Microsoft 365 管理中心中的联系人。 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>步骤 3：向外部联系人的属性添加信息

在步骤 2 中运行命令后，将创建外部联系人，但它们不包含任何联系人或组织信息，这些信息来自 CSV 文件中的大多数单元格。 这是因为当您创建新的外部联系人时，仅填充所需的属性。 如果您没有在 CSV 文件中填充所有信息，请不要担心。 如果它不存在，它不会添加。
  
1.  将 PowerShell 连接到您的 Exchange 在线组织。 有关分步说明，请参阅[连接到交换在线 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. 转到在步骤 1 中保存 CSV 文件的桌面文件夹;例如`C:\Users\Administrator\desktop`.
    
3. 运行以下两个命令，将 CSV 文件中的其他属性添加到您在步骤 2 中创建的外部联系人。
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _管理器_参数可能有问题。 如果 CSV 文件中的单元格为空，您将收到错误，并且不会将任何属性信息添加到联系人中。 如果不需要指定管理器，则只需从以前的 PowerShell 命令` -Manager $_.Manager `中删除。 
  
    同样，更新联系人可能需要一段时间，具体取决于您在步骤 1 中导入的多少。 
    
4. 要验证属性是否已添加到联系人中，请： 
    
1. In the EAC, go to **Recipients** \> **Contacts**.
    
2. 单击联系人，**然后单击"编辑"**![图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)以显示联系人的属性。 
    
這就對了！ 用户可以在 Web 上的通讯簿 Outlook 和 Outlook 中查看联系人和其他信息。
  
## <a name="add-more-external-contacts"></a>添加更多外部联系人

您可以重复步骤 1 到步骤 3，在 Exchange 联机添加新的外部联系人。 您或您公司中的用户可以在 CSV 文件中为新联系人添加新行。 然后，可以从步骤 2 和步骤 3 运行 PowerShell 命令，以创建新联系人并添加信息。
  
> [!NOTE]
> 当您运行该命令以创建新联系人时，您可能会收到一个错误，指出以前创建的联系人已存在。 但将创建添加到 CSV 文件的任何新联系人。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>从共享通讯簿>隐藏外部联系人

某些公司可能只使用外部联系人，以便可以添加为通讯组成员。 在这种情况下，他们可能希望从共享通讯簿中隐藏外部联系人。 方法如下：
  
1.  将 PowerShell 连接到您的 Exchange 在线组织。 有关分步说明，请参阅[连接到交换在线 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. 要隐藏单个外部联系人，请运行以下命令。
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    例如，要从共享通讯簿中隐藏 Pilar Pinilla，应运行以下命令：

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. 要从共享通讯簿中隐藏所有外部联系人，可以运行以下命令：

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

隐藏联系人后，外部联系人不会显示在共享通讯簿中，但您仍然可以将它们添加为通讯组的成员。
