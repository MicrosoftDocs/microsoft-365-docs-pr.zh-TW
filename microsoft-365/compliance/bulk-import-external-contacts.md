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
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="193e4-103">將外部連絡人大量匯入到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="193e4-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="193e4-104">**本文適用于系統管理員。您嘗試將連絡人匯入您自己的信箱嗎？請參閱 [將連絡人匯入 Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="193e4-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="193e4-105">您的公司是否有許多您想要包含在共用通訊錄中的現有商務連絡人 (也稱為全域通訊清單) 在 Exchange Online 中？</span><span class="sxs-lookup"><span data-stu-id="193e4-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="193e4-106">您是否要將外部連絡人新增為通訊群組的成員，就像您可以搭配公司內的使用者一樣？</span><span class="sxs-lookup"><span data-stu-id="193e4-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="193e4-107">如果是的話，您可以使用 Exchange Online PowerShell 和 CSV (逗號分隔值) 檔案，以將外部連絡人大量匯入 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="193e4-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="193e4-108">這是三個步驟的處理常式：</span><span class="sxs-lookup"><span data-stu-id="193e4-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="193e4-109">步驟1：建立包含外部連絡人相關資訊的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="193e4-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="193e4-110">步驟2：使用 PowerShell 建立外部連絡人</span><span class="sxs-lookup"><span data-stu-id="193e4-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="193e4-111">步驟3：將資訊新增至外部連絡人的屬性</span><span class="sxs-lookup"><span data-stu-id="193e4-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="193e4-112">在您完成這些步驟以匯入連絡人之後，您可以執行下列額外的工作：</span><span class="sxs-lookup"><span data-stu-id="193e4-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="193e4-113">新增更多外部連絡人</span><span class="sxs-lookup"><span data-stu-id="193e4-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="193e4-114">隱藏共用通訊錄中的外部連絡人</span><span class="sxs-lookup"><span data-stu-id="193e4-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="193e4-115">步驟1：建立包含外部連絡人相關資訊的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="193e4-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="193e4-116">第一步是建立 CSV 檔案，其中包含您要匯入 Exchange Online 之每個外部連絡人的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="193e4-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="193e4-117">將下列文字複製到記事本中的文字檔，並使用檔案名尾碼 .csv，將其儲存在您的桌面機為 CSV 檔案。例如，ExternalContacts.csv。</span><span class="sxs-lookup"><span data-stu-id="193e4-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="193e4-118">如果您的語言包含特殊字元 (例如 **å**、 **ä** 和 **ö** in 瑞典文中) 使用 UTF-8 或其他 Unicode 編碼方式儲存 CSV 檔案，當您在 [記事本] 中儲存檔案時。</span><span class="sxs-lookup"><span data-stu-id="193e4-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="193e4-119">CSV 檔案的第一列（或標題列）會列出當您匯入 Exchange Online 時可使用的連絡人的屬性。</span><span class="sxs-lookup"><span data-stu-id="193e4-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="193e4-120">每個屬性名稱都會以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="193e4-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="193e4-121">標頭列底下的每一列都代表用來匯入單一外部連絡人的屬性值。</span><span class="sxs-lookup"><span data-stu-id="193e4-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="193e4-122">此文字包含您可以刪除的範例資料。</span><span class="sxs-lookup"><span data-stu-id="193e4-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="193e4-123">不過，請勿刪除或變更第一個 (頁首) 列。</span><span class="sxs-lookup"><span data-stu-id="193e4-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="193e4-124">包含外部連絡人的所有屬性。</span><span class="sxs-lookup"><span data-stu-id="193e4-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="193e4-125">在 Microsoft Excel 中開啟 CSV 檔案，以編輯 CSV 檔案，因為使用 Excel 編輯 CSV 檔案的方式很簡單。</span><span class="sxs-lookup"><span data-stu-id="193e4-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="193e4-126">針對您要匯入 Exchange Online 的每個連絡人建立一列。</span><span class="sxs-lookup"><span data-stu-id="193e4-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="193e4-127">盡可能填入盡可能多的儲存格。</span><span class="sxs-lookup"><span data-stu-id="193e4-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="193e4-128">這項資訊會顯示在每個連絡人的共用通訊錄中。</span><span class="sxs-lookup"><span data-stu-id="193e4-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="193e4-129">下列屬性 (是建立外部連絡人時需要) 標頭列中的前四個專案，必須在 CSV 檔案中填入： **ExternalEmailAddress**、 **Name**、 **FirstName**、 **LastName**。</span><span class="sxs-lookup"><span data-stu-id="193e4-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="193e4-130">您在步驟2中執行的 PowerShell 命令會使用這些屬性的值來建立連絡人。</span><span class="sxs-lookup"><span data-stu-id="193e4-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="193e4-131">步驟2：使用 PowerShell 建立外部連絡人</span><span class="sxs-lookup"><span data-stu-id="193e4-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="193e4-132">下一步是使用您在步驟1中建立的 CSV 檔案 PowerShell，將 CSV 檔案中列出的外部連絡人大量匯入 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="193e4-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="193e4-133">將 PowerShell 連接至您的 Exchange Online 組織。</span><span class="sxs-lookup"><span data-stu-id="193e4-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="193e4-134">如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="193e4-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="193e4-135">當您連線至 Exchange Online PowerShell 時，請務必使用全域系統管理員帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="193e4-135">Be sure to use the user name and password for your global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="193e4-136">在您將 PowerShell 連接至 Exchange Online 之後，請移至您在步驟1中儲存 CSV 檔案的桌面資料夾;例如 `C:\Users\Administrator\desktop` 。</span><span class="sxs-lookup"><span data-stu-id="193e4-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="193e4-137">執行下列命令來建立外部連絡人：</span><span class="sxs-lookup"><span data-stu-id="193e4-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="193e4-138">視您要匯入的數目而定，可能需要一段時間來建立新的連絡人。</span><span class="sxs-lookup"><span data-stu-id="193e4-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="193e4-139">當命令執行完畢時，PowerShell 會顯示已建立之新連絡人的清單。</span><span class="sxs-lookup"><span data-stu-id="193e4-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="193e4-140">若要查看新的外部連絡人，請移至 Exchange 系統管理中心 (EAC) ， **然後按一下 [** 收件者 \> **連絡人**]。</span><span class="sxs-lookup"><span data-stu-id="193e4-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="193e4-141">如需連接到 EAC 的指示，請參閱 exchange [Online 中的 exchange 系統管理中心](/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="193e4-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span> 
  
5. <span data-ttu-id="193e4-142">如有必要， **請按一下 [** 重新整理] 以更新清單，並查看已匯入的外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="193e4-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="193e4-143">匯入的連絡人會出現在 Outlook 和 Outlook 網頁版的共用通訊錄中。</span><span class="sxs-lookup"><span data-stu-id="193e4-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="193e4-144">您也可以移至 [ **使用者**] [連絡人]，以查看 Microsoft 365 系統管理中心中的連絡人 \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="193e4-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="193e4-145">步驟3：將資訊新增至外部連絡人的屬性</span><span class="sxs-lookup"><span data-stu-id="193e4-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="193e4-146">在步驟2中執行此命令之後，會建立外部連絡人，但不會包含任何連絡人或組織資訊，也就是 CSV 檔案中大部分儲存格的資訊。</span><span class="sxs-lookup"><span data-stu-id="193e4-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="193e4-147">這是因為當您建立新的外部連絡人時，只會填入必要的屬性。</span><span class="sxs-lookup"><span data-stu-id="193e4-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="193e4-148">如果您沒有所有在 CSV 檔案中填入的資訊，請不要擔心。</span><span class="sxs-lookup"><span data-stu-id="193e4-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="193e4-149">如果不存在，則不會新增它。</span><span class="sxs-lookup"><span data-stu-id="193e4-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="193e4-150">將 PowerShell 連接至您的 Exchange Online 組織。</span><span class="sxs-lookup"><span data-stu-id="193e4-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="193e4-151">如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="193e4-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="193e4-152">移至您在步驟1中儲存 CSV 檔的 [桌面] 資料夾。例如， `C:\Users\Administrator\desktop` 。</span><span class="sxs-lookup"><span data-stu-id="193e4-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="193e4-153">執行下列兩個命令，以將其他屬性從 CSV 檔案新增至您在步驟2中建立的外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="193e4-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="193e4-154">_Manager_ 參數可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="193e4-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="193e4-155">如果在 CSV 檔案中儲存格是空白的，您會收到錯誤，而且不會將任何屬性資訊新增至連絡人。</span><span class="sxs-lookup"><span data-stu-id="193e4-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="193e4-156">如果您不需要指定管理員，請只  ` -Manager $_.Manager ` 從先前的 PowerShell 命令中刪除。</span><span class="sxs-lookup"><span data-stu-id="193e4-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="193e4-157">再說一次，可能需要一段時間來更新連絡人，視您在步驟1中匯入的數目而定。</span><span class="sxs-lookup"><span data-stu-id="193e4-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="193e4-158">若要確認已將屬性新增至連絡人：</span><span class="sxs-lookup"><span data-stu-id="193e4-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="193e4-159">In the EAC, go to **Recipients** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="193e4-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="193e4-160">按一下連絡人，然後按一下 [ **編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 以顯示連絡人的屬性。</span><span class="sxs-lookup"><span data-stu-id="193e4-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="193e4-161">這就對了！</span><span class="sxs-lookup"><span data-stu-id="193e4-161">That's it!</span></span> <span data-ttu-id="193e4-162">使用者可以在通訊錄 Outlook 和 Outlook 網頁版上看到連絡人及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="193e4-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="193e4-163">新增更多外部連絡人</span><span class="sxs-lookup"><span data-stu-id="193e4-163">Add more external contacts</span></span>

<span data-ttu-id="193e4-164">您可以重複步驟1到步驟3，在 Exchange Online 中新增新的外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="193e4-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="193e4-165">您或您公司中的使用者只可以在新的連絡人的 CSV 檔案中新增一列。</span><span class="sxs-lookup"><span data-stu-id="193e4-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="193e4-166">然後，您可以執行步驟2和步驟3中的 PowerShell 命令，以建立新連絡人的資訊並新增資訊。</span><span class="sxs-lookup"><span data-stu-id="193e4-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="193e4-167">當您執行命令以建立新的連絡人時，可能會收到錯誤訊息，指出先前建立的連絡人已存在。</span><span class="sxs-lookup"><span data-stu-id="193e4-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="193e4-168">但已建立任何新增至 CSV 檔案的新連絡人。</span><span class="sxs-lookup"><span data-stu-id="193e4-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="193e4-169">隱藏共用通訊錄中的外部連絡人></span><span class="sxs-lookup"><span data-stu-id="193e4-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="193e4-170">有些公司可能只會使用外部連絡人，因此可以新增為通訊群組的成員。</span><span class="sxs-lookup"><span data-stu-id="193e4-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="193e4-171">在此案例中，他們可能會想要隱藏共用通訊錄中的外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="193e4-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="193e4-172">方法如下：</span><span class="sxs-lookup"><span data-stu-id="193e4-172">Here's how:</span></span>
  
1.  <span data-ttu-id="193e4-173">將 PowerShell 連接至您的 Exchange Online 組織。</span><span class="sxs-lookup"><span data-stu-id="193e4-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="193e4-174">如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="193e4-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="193e4-175">若要隱藏單一外部連絡人，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="193e4-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="193e4-176">例如，若要隱藏共用通訊錄中的 Pilar Pinilla，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="193e4-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="193e4-177">若要隱藏共用通訊錄中的所有外部連絡人，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="193e4-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="193e4-178">在您隱藏這些連絡人之後，就不會顯示在共用通訊錄中的外部連絡人，但您仍然可以將它們新增為通訊群組的成員。</span><span class="sxs-lookup"><span data-stu-id="193e4-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>