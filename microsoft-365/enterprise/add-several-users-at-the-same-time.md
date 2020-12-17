---
title: 同時將多個使用者新增至 Microsoft 365-系統管理說明
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
ms.assetid: 1f5767ed-e717-4f24-969c-6ea9d412ca88
description: '瞭解如何從試算表或其他 CSV 格式的檔案中的清單，將多個使用者新增至 Microsoft 365 for business。 在說明如何將帳戶新增至 Microsoft 365 的 YouTube 觀看影片。 在此程式結束時，具有帳戶的每位使用者都會有 Microsoft 365 信箱。 '
ms.openlocfilehash: 71e1d1f9261fc58e9f49fac5050e07fd7b8839e3
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698264"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="a6a18-105">同時將多個使用者新增至 Microsoft 365-系統管理說明</span><span class="sxs-lookup"><span data-stu-id="a6a18-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="a6a18-p102">小組中的每位人員必須先使用使用者帳戶，才能登入並存取 Microsoft 365 服務，例如電子郵件和 Office。如果您有許多人員，您可以從 Excel 試算表或以 CSV 格式儲存的其他檔案，一次新增他們的帳戶。 [不確定 CSV 格式是什麼？](add-several-users-at-the-same-time.md#__toc316652088)</span><span class="sxs-lookup"><span data-stu-id="a6a18-p102">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office. If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format. [Not sure what CSV format is?](add-several-users-at-the-same-time.md#__toc316652088)</span></span>
  
> [!NOTE] 
> <span data-ttu-id="a6a18-109">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心]** 開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="a6a18-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a6a18-110">在 Microsoft 365 系統管理中心新增多個使用者</span><span class="sxs-lookup"><span data-stu-id="a6a18-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a6a18-111">請使用工作或學校帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a6a18-111">Sign in to Microsoft 365 with your work or school account.</span></span> 
    
2. <span data-ttu-id="a6a18-112">在系統管理中心，選擇 **[使用者]**\> > **[作用中使用者]**。</span><span class="sxs-lookup"><span data-stu-id="a6a18-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="a6a18-113">選取 [ **新增多個使用者**]。</span><span class="sxs-lookup"><span data-stu-id="a6a18-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="a6a18-114">在 **[匯入多個使用者]** 面板中，您可以選擇下載包含或不含範例資料的範例 CSV 檔。</span><span class="sxs-lookup"><span data-stu-id="a6a18-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span> 
    
    <span data-ttu-id="a6a18-115">您的試算表必須包含與範例一 (使用者名稱、名字等 **完全相同的欄標題** ，如此) 。</span><span class="sxs-lookup"><span data-stu-id="a6a18-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="a6a18-116">如果您使用範本，請在文字編輯工具（例如 [記事本]）中開啟它，並考慮只保留第1列的資料，並且只在第2列及下列的資料中輸入資料。</span><span class="sxs-lookup"><span data-stu-id="a6a18-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span> 
    
    <span data-ttu-id="a6a18-117">您的試算表也必須包含使用者名稱 (例如 bob@contoso.com) 與每個使用者的顯示名稱 (例如「柯百勝」) 這兩個值。</span><span class="sxs-lookup"><span data-stu-id="a6a18-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span> 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="a6a18-118">在方塊中輸入檔案路徑，或選擇 **[瀏覽]** 以瀏覽至 CSV 檔案的位置，然後選擇 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="a6a18-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="a6a18-p104">如果檔案有任何問題，問題會顯示在面板中。您也可以下載記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a6a18-p104">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>
    
5. <span data-ttu-id="a6a18-121">在 **[設定使用者選項]** 對話方塊中，您可以設定登入狀態，並選擇要指派給所有使用者的產品授權。</span><span class="sxs-lookup"><span data-stu-id="a6a18-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span> 
    
6. <span data-ttu-id="a6a18-122">在 **[檢視結果]** 對話方塊中，您可以選擇將結果傳送給自己或其他使用者 (密碼會以純文字顯示)，並且可以看到已建立多少使用者，以及是否需要購買更多授權以指派給某些新使用者。</span><span class="sxs-lookup"><span data-stu-id="a6a18-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a6a18-123">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a6a18-123">Next steps</span></span>
<span data-ttu-id="a6a18-124"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a6a18-124"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="a6a18-125">現在，這些人具有帳戶，他們必須 [在電腦或 Mac 上下載並安裝或重新安裝 Microsoft 365 或 Office 2016](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)。</span><span class="sxs-lookup"><span data-stu-id="a6a18-125">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="a6a18-126">您的小組中的每位人員最多可以在5部 Pc 或 Mac 上安裝 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a6a18-126">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span> 
    
- <span data-ttu-id="a6a18-127">每位人員也可以[在行動裝置上安裝 Office 應用程式和電子郵件](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) (最多 5 部平板電腦和 5 支手機)，例如 iPhone、iPad 和 Android 電話及平板電腦。</span><span class="sxs-lookup"><span data-stu-id="a6a18-127">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="a6a18-128">這樣一來，他們就能隨時隨地編輯 Office 檔案。</span><span class="sxs-lookup"><span data-stu-id="a6a18-128">This way they can edit Office files from anywhere.</span></span> 
    
    <span data-ttu-id="a6a18-129">如需安裝步驟的端對端清單，請參閱 [設定 Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) 。</span><span class="sxs-lookup"><span data-stu-id="a6a18-129">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span> 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="a6a18-130">如何將使用者新增至 Microsoft 365 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a6a18-130">More information about how to add users to Microsoft 365</span></span>
<span data-ttu-id="a6a18-131"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a6a18-131"><a name="bk_preview"> </a></span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="a6a18-132">不確定 CSV 格式是什麼嗎？</span><span class="sxs-lookup"><span data-stu-id="a6a18-132">Not sure what CSV format is?</span></span>
<span data-ttu-id="a6a18-133"><a name="__toc316652088"> </a></span><span class="sxs-lookup"><span data-stu-id="a6a18-133"><a name="__toc316652088"> </a></span></span>

<span data-ttu-id="a6a18-p107">CSV 檔案是以逗號區分值的檔案。您可以用任何文字編輯器或試算表程式 (例如 Excel) 來建立或編輯這樣的檔案。</span><span class="sxs-lookup"><span data-stu-id="a6a18-p107">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="a6a18-136">您可以從下載[這份樣本試算表](https://www.microsoft.com/download/details.aspx?id=45485)開始著手。</span><span class="sxs-lookup"><span data-stu-id="a6a18-136">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="a6a18-137">請注意，Microsoft 365 需要在第一列中欄標題，否則請勿將其取代為其他內容。</span><span class="sxs-lookup"><span data-stu-id="a6a18-137">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="a6a18-138">接著請以新名稱儲存檔案，然後指定 CSV 格式。</span><span class="sxs-lookup"><span data-stu-id="a6a18-138">Save the file with a new name, and specify CSV format.</span></span>
  
![說明如何在 Excel 中將檔案儲存為 CSV 格式的影像](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="a6a18-140">儲存檔案時，系統會提示您若儲存為 CSV 格式，將遺失部分活頁簿中的功能。</span><span class="sxs-lookup"><span data-stu-id="a6a18-140">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format.</span></span> <span data-ttu-id="a6a18-141">這沒有關係。</span><span class="sxs-lookup"><span data-stu-id="a6a18-141">This is okay.</span></span> <span data-ttu-id="a6a18-142">按一下 **[是]** 以繼續。</span><span class="sxs-lookup"><span data-stu-id="a6a18-142">Click **Yes** to continue.</span></span> 
  
![Excel 可能會向您顯示的提示圖片，Excel 會詢問您是否真的要將檔案儲存為 CSV 格式](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="a6a18-144">設定試算表格式的祕訣</span><span class="sxs-lookup"><span data-stu-id="a6a18-144">Tips for formatting your spreadsheet</span></span>
<span data-ttu-id="a6a18-145"><a name="__toc314595848"> </a></span><span class="sxs-lookup"><span data-stu-id="a6a18-145"><a name="__toc314595848"> </a></span></span>

- <span data-ttu-id="a6a18-146">**我需要使用和範例試算表中相同的欄標題嗎？**</span><span class="sxs-lookup"><span data-stu-id="a6a18-146">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="a6a18-147">是。</span><span class="sxs-lookup"><span data-stu-id="a6a18-147">Yes.</span></span> <span data-ttu-id="a6a18-148">樣本試算表的第一列是欄標題。</span><span class="sxs-lookup"><span data-stu-id="a6a18-148">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="a6a18-149">這些標題不能省略。</span><span class="sxs-lookup"><span data-stu-id="a6a18-149">These headings are required.</span></span> <span data-ttu-id="a6a18-150">針對您要新增至 Microsoft 365 的每一位使用者，在標題底下建立一列。</span><span class="sxs-lookup"><span data-stu-id="a6a18-150">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="a6a18-151">如果您新增、變更或刪除任何欄標題，Microsoft 365 可能無法從檔案中的資訊建立使用者。</span><span class="sxs-lookup"><span data-stu-id="a6a18-151">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span> 
    
- <span data-ttu-id="a6a18-152">**如果我沒有每位使用者所需的所有資訊，該怎麼辦？**</span><span class="sxs-lookup"><span data-stu-id="a6a18-152">**What if I don't have all the information required for each user?**</span></span> <span data-ttu-id="a6a18-153">使用者名稱和顯示名稱是必要資訊，缺少的話無法新增新使用者。</span><span class="sxs-lookup"><span data-stu-id="a6a18-153">The user name and display name are required, and you cannot add a new user without this information.</span></span> <span data-ttu-id="a6a18-154">若您缺少部分其他資訊 (例如傳真)，可使用空格加上逗號表示此欄位應保留空白。</span><span class="sxs-lookup"><span data-stu-id="a6a18-154">If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span> 
    
- <span data-ttu-id="a6a18-155">**試算表大小的上下限為何？**</span><span class="sxs-lookup"><span data-stu-id="a6a18-155">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="a6a18-156">試算表至少要有兩列。</span><span class="sxs-lookup"><span data-stu-id="a6a18-156">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="a6a18-157">一列是欄標題 (使用者資料欄標籤)，另一列是使用者。</span><span class="sxs-lookup"><span data-stu-id="a6a18-157">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="a6a18-158">列數不得超過 251 列。</span><span class="sxs-lookup"><span data-stu-id="a6a18-158">You cannot have more than 251 rows.</span></span> <span data-ttu-id="a6a18-159">如果您必須匯入超過 250 位使用者，可以建立多份試算表。</span><span class="sxs-lookup"><span data-stu-id="a6a18-159">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span> 
    
- <span data-ttu-id="a6a18-160">**我可以使用什麼語言？**</span><span class="sxs-lookup"><span data-stu-id="a6a18-160">**What languages can I use?**</span></span> <span data-ttu-id="a6a18-161">建立試算表時，您可以使用任何語言或字元輸入使用者資料欄標籤，但不得變更範例所顯示的標籤順序。</span><span class="sxs-lookup"><span data-stu-id="a6a18-161">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="a6a18-162">然後您可以使用任何語言或字元將項目輸入到欄位中，並將檔案儲存為 Unicode 或 UTF-8 格式。</span><span class="sxs-lookup"><span data-stu-id="a6a18-162">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span> 
    
- <span data-ttu-id="a6a18-163">**如果我要新增不同國家或地區的使用者該怎麼辦？**</span><span class="sxs-lookup"><span data-stu-id="a6a18-163">**What if I'm adding users from different countries or regions?**</span></span> <span data-ttu-id="a6a18-164">請為每一個地區分別建立一個試算表。</span><span class="sxs-lookup"><span data-stu-id="a6a18-164">Create a separate spreadsheet for each area.</span></span> <span data-ttu-id="a6a18-165">每一個試算表都要執行 [大量新增使用者精靈] 的所有步驟，讓您所用的檔案中，所有的使用者都具備單一位置。</span><span class="sxs-lookup"><span data-stu-id="a6a18-165">You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span> 
    
- <span data-ttu-id="a6a18-166">**是否有字元數的使用上限？**</span><span class="sxs-lookup"><span data-stu-id="a6a18-166">**Is there a limit to the number of characters I can use?**</span></span> <span data-ttu-id="a6a18-167">下表所列的是範例試算表中各使用者資料欄標籤及其字元數長度上限。</span><span class="sxs-lookup"><span data-stu-id="a6a18-167">The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span> 
    
|<span data-ttu-id="a6a18-168">**使用者資料欄標籤**</span><span class="sxs-lookup"><span data-stu-id="a6a18-168">**User data column label**</span></span>|<span data-ttu-id="a6a18-169">**最大字元長度**</span><span class="sxs-lookup"><span data-stu-id="a6a18-169">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a6a18-170">使用者 名稱 (必填)</span><span class="sxs-lookup"><span data-stu-id="a6a18-170">User Name (Required)</span></span>  <br/> |<span data-ttu-id="a6a18-171">79，其中包含 name@domain 格式的 at 符號 ( @ \<extension\> ) 。</span><span class="sxs-lookup"><span data-stu-id="a6a18-171">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="a6a18-172">使用者的別名不得超過50個字元，功能變數名稱不得超過48個字元。</span><span class="sxs-lookup"><span data-stu-id="a6a18-172">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="a6a18-173">名字</span><span class="sxs-lookup"><span data-stu-id="a6a18-173">First Name</span></span>  <br/> |<span data-ttu-id="a6a18-174">64</span><span class="sxs-lookup"><span data-stu-id="a6a18-174">64</span></span>  <br/> |
|<span data-ttu-id="a6a18-175">姓氏</span><span class="sxs-lookup"><span data-stu-id="a6a18-175">Last Name</span></span>  <br/> |<span data-ttu-id="a6a18-176">64</span><span class="sxs-lookup"><span data-stu-id="a6a18-176">64</span></span>  <br/> |
|<span data-ttu-id="a6a18-177">顯示 名稱 (必填)</span><span class="sxs-lookup"><span data-stu-id="a6a18-177">Display Name (required)</span></span>  <br/> |<span data-ttu-id="a6a18-178">256</span><span class="sxs-lookup"><span data-stu-id="a6a18-178">256</span></span>  <br/> |
|<span data-ttu-id="a6a18-179">職稱</span><span class="sxs-lookup"><span data-stu-id="a6a18-179">Job Title</span></span>  <br/> |<span data-ttu-id="a6a18-180">64</span><span class="sxs-lookup"><span data-stu-id="a6a18-180">64</span></span>  <br/> |
|<span data-ttu-id="a6a18-181">部門</span><span class="sxs-lookup"><span data-stu-id="a6a18-181">Department</span></span>  <br/> |<span data-ttu-id="a6a18-182">64</span><span class="sxs-lookup"><span data-stu-id="a6a18-182">64</span></span>  <br/> |
|<span data-ttu-id="a6a18-183">辦公室號碼</span><span class="sxs-lookup"><span data-stu-id="a6a18-183">Office Number</span></span>  <br/> |<span data-ttu-id="a6a18-184">128</span><span class="sxs-lookup"><span data-stu-id="a6a18-184">128</span></span>  <br/> |
|<span data-ttu-id="a6a18-185">辦公室電話</span><span class="sxs-lookup"><span data-stu-id="a6a18-185">Office Phone</span></span>  <br/> |<span data-ttu-id="a6a18-186">64</span><span class="sxs-lookup"><span data-stu-id="a6a18-186">64</span></span>  <br/> |
|<span data-ttu-id="a6a18-187">行動電話</span><span class="sxs-lookup"><span data-stu-id="a6a18-187">Mobile Phone</span></span>  <br/> |<span data-ttu-id="a6a18-188">64</span><span class="sxs-lookup"><span data-stu-id="a6a18-188">64</span></span>  <br/> |
|<span data-ttu-id="a6a18-189">傳真</span><span class="sxs-lookup"><span data-stu-id="a6a18-189">Fax</span></span>  <br/> |<span data-ttu-id="a6a18-190">64</span><span class="sxs-lookup"><span data-stu-id="a6a18-190">64</span></span>  <br/> |
|<span data-ttu-id="a6a18-191">地址</span><span class="sxs-lookup"><span data-stu-id="a6a18-191">Address</span></span>  <br/> |<span data-ttu-id="a6a18-192">1023</span><span class="sxs-lookup"><span data-stu-id="a6a18-192">1023</span></span>  <br/> |
|<span data-ttu-id="a6a18-193">城市</span><span class="sxs-lookup"><span data-stu-id="a6a18-193">City</span></span>  <br/> |<span data-ttu-id="a6a18-194">128</span><span class="sxs-lookup"><span data-stu-id="a6a18-194">128</span></span>  <br/> |
|<span data-ttu-id="a6a18-195">省/市</span><span class="sxs-lookup"><span data-stu-id="a6a18-195">State or Province</span></span>  <br/> |<span data-ttu-id="a6a18-196">128</span><span class="sxs-lookup"><span data-stu-id="a6a18-196">128</span></span>  <br/> |
|<span data-ttu-id="a6a18-197">郵遞區號</span><span class="sxs-lookup"><span data-stu-id="a6a18-197">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="a6a18-198">40</span><span class="sxs-lookup"><span data-stu-id="a6a18-198">40</span></span>  <br/> |
|<span data-ttu-id="a6a18-199">國家/地區</span><span class="sxs-lookup"><span data-stu-id="a6a18-199">Country or Region</span></span>  <br/> |<span data-ttu-id="a6a18-200">128</span><span class="sxs-lookup"><span data-stu-id="a6a18-200">128</span></span>  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="a6a18-201">將使用者新增至 Microsoft 365 時仍然有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="a6a18-201">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="a6a18-202">**請仔細檢查試算表的格式是否正確。**</span><span class="sxs-lookup"><span data-stu-id="a6a18-202">**Double-check that the spreadsheet is formatted correctly.**</span></span> <span data-ttu-id="a6a18-203">檢查欄標題，確認與樣本檔案中的標題相符。</span><span class="sxs-lookup"><span data-stu-id="a6a18-203">Check the column headings to make sure they match the headings in the sample file.</span></span> <span data-ttu-id="a6a18-204">務必遵循字元長度的規則，各欄位均以逗號隔開。</span><span class="sxs-lookup"><span data-stu-id="a6a18-204">Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span> 
    
- <span data-ttu-id="a6a18-205">**如果您在 Microsoft 365 中看不到新的使用者，請稍候幾分鐘。**</span><span class="sxs-lookup"><span data-stu-id="a6a18-205">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="a6a18-206">您可能需要一點時間，才能讓變更移至 Microsoft 365 中的所有服務。</span><span class="sxs-lookup"><span data-stu-id="a6a18-206">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 
    
## <a name="related-articles"></a><span data-ttu-id="a6a18-207">相關文章</span><span class="sxs-lookup"><span data-stu-id="a6a18-207">Related articles</span></span>

[<span data-ttu-id="a6a18-208">個別或大量將使用者新增至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a6a18-208">Add users individually or in bulk to Microsoft 365</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)




