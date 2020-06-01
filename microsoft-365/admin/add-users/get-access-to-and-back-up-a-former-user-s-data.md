---
title: 存取及備份離職使用者的資料
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: 瞭解如何在人員離開組織時保留員工的檔案和電子郵件。
ms.openlocfilehash: 13cc1117c52a45f4ec1389d2e8b9f0189f4730e1
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431710"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a>存取及備份離職使用者的資料


當員工離開您的組織時，您可能會想要存取其資料（檔和電子郵件），並對其進行備份，或是將它備份或提供給新員工。
  
    
## <a name="access-a-former-users-onedrive-documents"></a>存取先前使用者的 OneDrive 檔

如果您移除使用者的授權，但沒有刪除帳戶，您可以讓自己存取使用者 OneDrive 中的內容。 如果您刪除使用者帳戶，則預設會有30天的時間來存取先前使用者的 OneDrive 資料。 [瞭解如何為已刪除的使用者設定 OneDrive 保留](/onedrive/set-retention)。 如果您在這段時間內沒有[還原使用者帳戶](/office365/admin/add-users/restore-user)，其 OneDrive 內容就會被刪除。 

若要保留先前使用者的 OneDrive 檔案，請先讓您自行存取 OneDrive，然後移動您想要保留的檔案。 

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。  
    
2. 選取使用者。

3. 在右窗格中，選取 [ **OneDrive**]。 在 [**存取**檔案] 底下，選取 [**建立檔的連結**]。

4. 選取連結以開啟檔案位置。 將檔案下載至您的電腦，或選取 [**移至**] 或 [**複製至**] 以移動或複製至您自己的 OneDrive 或共用文件庫。 

> [!NOTE]
> 您一次最多可以移動或複製 500 MB 的檔案和資料夾。<br/>
> 當您移動或複製具有版本記錄的檔時，只會移動最新的版本。  

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。  

2. 選取使用者。

3. 在右窗格中，展開 [ **OneDrive 設定**]，然後按一下 [**存取**] 旁的 [**存取**檔案]。

4. 選取連結以開啟檔案位置。 將檔案下載至您的電腦，或選取 [**移至**] 或 [**複製至**] 以移動或複製至您自己的 OneDrive 或共用文件庫。 

> [!NOTE]
> 您一次最多可以移動或複製 500 MB 的檔案和資料夾。<br/>
> 當您移動或複製具有版本記錄的檔時，只會移動最新的版本。  

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。 

2. 選取使用者。

3. 在右窗格中，展開 [ **OneDrive 設定**]，然後按一下 [**存取**] 旁的 [**存取**檔案]。

4. 選取連結以開啟檔案位置。 將檔案下載至您的電腦，或選取 [**移至**] 或 [**複製至**] 以移動或複製至您自己的 OneDrive 或共用文件庫。  

> [!NOTE]
> 您一次最多可以移動或複製 500 MB 的檔案和資料夾。<br/>
> 當您移動或複製具有版本記錄的檔時，只會移動最新的版本。  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a>撤銷使用者 OneDrive 的系統管理員存取權

如同全域系統管理員，您可以在使用者的 OneDrive 中存取內容，但您可能想要在不再需要時移除存取權。 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">以全域</a>系統管理員身分登入系統管理員或 SharePoint 管理員。 

    如果您收到的訊息您沒有存取系統管理中心的許可權，則您的組織不具備系統管理員許可權。

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">以全域</a>系統管理員身分登入系統管理員或 SharePoint 管理員。

    如果您收到的訊息您沒有存取系統管理中心的許可權，則您的組織不具備系統管理員許可權。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">以全域</a>系統管理員身分登入系統管理員或 SharePoint 管理員。

    如果您收到的訊息您沒有存取系統管理中心的許可權，則您的組織不具備系統管理員許可權。

::: moniker-end

2. 在左窗格中，選取 [系統**管理中心**] \> **SharePoint**。 (您可能需要選取 [全部顯示]**** 才能查看系統管理中心的清單。)

3. 如果出現 [傳統 SharePoint 系統管理中心]，請選取 [立即在頁面頂端開啟]，以開啟 SharePoint**系統**管理中心。

4. 在左窗格中，選取 [**其他功能**]。

5. 在 [**使用者設定檔**] 下，選取 [**開啟**]。

6. 在 [**人員**] 底下，選取 [**管理使用者設定檔**]。

7. 輸入使用者的名稱，然後選取 [**尋找**]。

8. 以滑鼠右鍵按一下使用者，然後選擇 [**管理網站集合擁有**者]。

9. 移除不再需要存取使用者資料的人員，然後選取 **[確定]**。

    
## <a name="access-the-outlook-data-of-a-former-user"></a>存取先前使用者的 Outlook 資料

若要儲存先前員工的電子郵件、行事曆、工作和連絡人，請將資訊匯出至 Outlook 資料檔案（.pst）。
  
1. [將離職員工的電子郵件新增](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)至您的 Outlook （如果您[重設使用者的密碼](reset-passwords.md)，您可以將它設定為您知道的內容）。
    
2. 在 Outlook 中，**選取 [** 檔案]。
    
    ![這是功能區在 Outlook 2016 中的外觀。](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. 選取 [**開啟 &amp; 匯出**匯 \> **入/匯出**]。
    
    ![Backstage 檢視中的匯入/匯出命令](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. 選取 [**匯出至**檔案]，然後選取 **[下一步]**。
    
    ![匯出至 [匯入及匯出] 嚮導中的 [檔案] 選項](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. 選取 [ **Outlook 資料檔案（.pst）**]，然後選取 **[下一步]**。
    
6. 選取您要匯出的帳戶，方法是選取其名稱或電子郵件地址，例如信箱-Anne Weiler 或 anne@contoso.com。 如果您想要匯出帳戶中的所有內容，包括郵件、行事曆、連絡人、工作和附注，請確定已選取 [**包含子資料夾**] 核取方塊。 
    
    > [!NOTE]
    > 您一次可以匯出一個帳戶。 如果您想要匯出多個帳戶，請在匯出一個帳戶後，重複這些步驟。 
  
    ![選取上方資料夾並包含檢查子資料夾的 [匯出 Outlook 資料檔案] 對話方塊](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. 選取 [下一步]****。
    
8. 選取 **[流覽]** 以選取要儲存 Outlook 資料檔案（.pst）的位置。 輸入檔案名 *，然後*選取 **[確定]** 繼續。 
    
    > [!NOTE]
    > 如果您以前已使用 export，就會出現上一個資料夾位置和檔案名。 請輸入*其他*的檔案名，然後選取 **[確定]**。 
  
9. 若要匯出至現有的 Outlook 資料檔（.pst），請在 [**選項**] 下，指定匯出檔案中已存在的專案時要執行的動作。
    
10. Select **Finish**.
    
Outlook 會立即開始匯出，除非已建立新的 Outlook 資料檔（.pst）或使用密碼保護的檔案。
  
   - 如果您正在建立 Outlook 資料檔案（.pst），選用密碼可協助保護檔案。 當 [**建立 Outlook 資料檔案**] 對話方塊出現時，在 [**密碼**] 和 [**確認密碼**] 方塊中輸入*密碼*，然後選取 **[確定]**。 在 [ **Outlook 資料檔案密碼**] 對話方塊中，輸入*密碼*，然後選取 **[確定]**。
    
  - 如果您要匯出的現有 Outlook 資料檔案（.pst）是受密碼保護，請在 [ **Outlook 資料檔案密碼**] 對話方塊中，輸入*密碼*，然後選取 **[確定]**。
    
請參閱如何[將電子郵件、連絡人及行事曆匯出或備份至 outlook 2010 中的 outlook .pst](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)檔案。 
  
  
  > [!NOTE]
  > 根據預設，您的電子郵件在12個月內可供離線使用。 如有需要，請參閱 how to[增加可離線使用的資料](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)。
 
## <a name="give-another-user-access-to-a-former-users-email"></a>讓另一位使用者能夠存取先前使用者的電子郵件 

若要將離職員工的電子郵件、行事曆、工作和連絡人的存取權授與另一個員工，請將此資訊匯入另一個員工的 Outlook 收件匣。

> [!NOTE]
> 您也可以[將先前使用者的信箱轉換成共用信箱，或將](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox)[離職員工的電子郵件轉寄給另一個員工](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)。

  
1. 在 Outlook 中，移**至 [** 檔案] [ \> **開啟 &amp; 匯出**] [匯 \> **入/匯出**]。
    
    這會啟動 [匯入及匯出] 嚮導。
    
2. 選取 [**從其他程式或**檔案匯入]，然後選取 **[下一步]**。
    
    ![匯入及匯出嚮導](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. 選取 [ **Outlook 資料檔案（.pst）**]，然後選取 **[下一步]**。
    
4. 流覽至您要匯入的 .pst 檔案。
    
5. 在 [**選項**] 底下，選擇您要處理重複專案的方式
    
6. 選取 [下一步]****。
    
7. 如果已指派密碼給 Outlook 資料檔案（.pst），請輸入密碼，然後選取 **[確定]**。
    
8. 設定匯入專案的選項。 通常不需要變更預設設定。
    
9. Select **Finish**.

> [!NOTE]
> 存取現有使用者的 OneDrive 和電子郵件資料時，這些步驟會保持不變。
    
> [!TIP]
> 如果您只想匯入或還原 Outlook 資料檔（.pst）中的幾個專案，您可以開啟 Outlook 資料檔案。 然後，在功能窗格中，將 [Outlook 資料檔案資料夾] 中的專案拖曳到現有的 Outlook 資料夾中。 
  
  
## <a name="related-articles"></a>相關文章
[從 Office 365 中移除前任員工](remove-former-employee.md)

[在 OneDrive 帳戶上新增及移除系統管理員](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[還原已刪除的 OneDrive](/onedrive/restore-deleted-onedrive)
  
[OneDrive 保留與刪除](/onedrive/retention-and-deletion)
  
