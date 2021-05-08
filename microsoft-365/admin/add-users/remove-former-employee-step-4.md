---
title: 步驟 4-授予另一個員工 OneDrive 和 Outlook 資料的存取權
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 請遵循下列步驟，讓另一個員工存取離職員工的 OneDrive 和 Outlook 資料。
ms.openlocfilehash: 451f8f7f50098c280e3925ef4efe5ad491ac54fa
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244162"
---
# <a name="step-4---give-another-employee-access-to-onedrive-and-outlook-data"></a>步驟 4-授予另一個員工 OneDrive 和 Outlook 資料的存取權

當員工離開您的組織時，您會想要存取其 OneDrive 和 Outlook 資料，進行備份，然後選擇是否要將其授與其他員工。
  
## <a name="access-a-former-users-onedrive-documents"></a>存取先前使用者的 OneDrive 檔

如果您移除使用者的授權，但沒有刪除帳戶，您可以讓自己存取使用者 OneDrive 中的內容。 如果您刪除使用者帳戶，則預設會有30天的時間來存取先前使用者的 OneDrive 資料。 [瞭解如何為已刪除的使用者設定 OneDrive 保留](/onedrive/set-retention)。 如果您在這段時間內沒有[還原使用者帳戶](/office365/admin/add-users/restore-user)，其 OneDrive 內容就會被刪除。

若要保留先前使用者的 OneDrive 檔案，請先讓您自行存取 OneDrive，然後移動您想要保留的檔案。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。  

2. 選取使用者。

3. 在右窗格中，選取 [ **OneDrive**]。 在 [ **存取** 檔案] 底下，選取 [ **建立檔的連結**]。

4. 選取連結以開啟檔案位置。 將檔案下載至您的電腦，或選取 [**移至**] 或 [**複製至**] 以移動或複製至您自己的 OneDrive 或共用文件庫。

> [!NOTE]
> 您一次最多可以移動或複製 500 MB 的檔案和資料夾。<br/>
> 當您移動或複製具有版本記錄的檔時，只會移動最新的版本。  

### <a name="revoke-admin-access-to-a-users-onedrive"></a>撤銷使用者 OneDrive 的系統管理員存取權

您可以讓自己存取使用者 OneDrive 中的內容，但您可能想要在不再需要時移除存取權。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">以全域</a>系統管理員身分登入系統管理員或 SharePoint 管理員。

    如果您收到的訊息您沒有存取系統管理中心的許可權，則您的組織不具備系統管理員許可權。

2. 在左窗格中，選取 [系統 **管理中心**] \> **SharePoint**。 (您可能需要選取 [全部顯示] 才能查看系統管理中心的清單。)

3. 如果出現 [傳統 SharePoint 系統管理中心]，請選取 [立即在頁面頂端開啟]，以開啟 SharePoint **系統** 管理中心。

4. 在左窗格中，選取 [ **其他功能**]。

5. 在 [ **使用者設定檔**] 下，選取 [ **開啟**]。

6. 在 [ **人員**] 底下，選取 [ **管理使用者設定檔**]。

7. 輸入使用者的名稱，然後選取 [ **尋找**]。

8. 以滑鼠右鍵按一下使用者，然後選擇 [ **管理網站集合擁有** 者]。

9. 移除不再需要存取使用者資料的人員，然後選取 **[確定]**。

## <a name="access-the-outlook-data-of-a-former-user"></a>存取先前使用者的 Outlook 資料

若要儲存先前員工的電子郵件、行事曆、工作和連絡人，請將資訊匯出至 Outlook 資料檔案 ( .pst) 。
  
1. [將離職員工的電子郵件新增](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b)至您的 Outlook (如果您[重設使用者的密碼](reset-passwords.md)，您可以將它設定為您知道的內容。 ) 

2. 在 Outlook 中，**選取 [** 檔案]。

    ![Outlook 2016 中的功能區看起來像這樣。](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. 選取 [**開啟 &amp; 匯出** \> **匯入/匯出**]。

    ![Backstage 檢視中的匯入/匯出命令](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. 選取 [ **匯出至** 檔案]，然後選取 **[下一步]**。

    ![匯出至 [匯入及匯出] 嚮導中的 [檔案] 選項](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. 選取 [ **Outlook 資料檔案 ( .pst)**]，然後選取 **[下一步]**。

6. 選取您要匯出的帳戶，方法是選取其名稱或電子郵件地址，例如信箱-Anne Weiler 或 anne@contoso.com。 如果您想要匯出帳戶中的所有內容，包括郵件、行事曆、連絡人、工作和附注，請確定已選取 [ **包含子資料夾** ] 核取方塊。

    > [!NOTE]
    > 您一次可以匯出一個帳戶。 如果您想要匯出多個帳戶，請在匯出一個帳戶後，重複這些步驟。
  
    ![選取上方資料夾並包含檢查子資料夾的 [匯出 Outlook 資料檔案] 對話方塊](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. 選取 **[下一步]**。

8. 選取 **[流覽]** ，以選取要將 Outlook 資料檔案儲存 ( .pst) 的位置。 輸入檔案名  *，然後* 選取 **[確定]** 繼續。

    > [!NOTE]
    > 如果您以前已使用 export，就會出現上一個資料夾位置和檔案名。 請輸入  *其他*  的檔案名，然後選取 **[確定]**。
  
9. 若要匯出至現有的 Outlook 資料檔案 ( .pst) 的 [**選項**] 底下，指定匯出檔案中已存在的專案時要執行的動作。

10. 選取 [完成 **]**。

Outlook 會立即開始匯出，除非已建立新的 Outlook 資料檔案 ( .pst) 或使用密碼保護檔案。
  
- 如果您正在建立 Outlook 資料檔案 ( .pst) 中，選用密碼可協助保護檔案。 出現 [**建立 Outlook 資料** 檔] 對話方塊時，在 [**密碼**] 和 [**確認密碼**] 方塊中輸入 *密碼*，然後選取 **[確定]**。 在 [ **Outlook 資料檔案密碼**] 對話方塊中，輸入 *密碼*，然後選取 **[確定]**。

- 如果您要匯出至現有的 Outlook 資料檔案 ( .pst) 受密碼保護，請在 [ **Outlook 資料檔案密碼**] 對話方塊中，輸入 *密碼*，然後選取 **[確定]**。

請參閱如何[將電子郵件、連絡人及行事曆匯出或備份至](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)Outlook 2010 的 Outlook .pst 檔案。

  > [!NOTE]
  > 根據預設，您的電子郵件在12個月內可供離線使用。 如有需要，請參閱 how to [增加可離線使用的資料](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)。

### <a name="give-another-user-access-to-a-former-users-email"></a>讓另一位使用者能夠存取先前使用者的電子郵件

若要將離職員工的電子郵件、行事曆、工作和連絡人的存取權授與另一個員工，請將此資訊匯入另一個員工的 Outlook 收件匣。

> [!NOTE]
> 您也可以[將先前使用者的信箱轉換成共用信箱，或將](/office365/admin/email/convert-user-mailbox-to-shared-mailbox)[離職員工的電子郵件轉寄給另一個員工](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)。

1. 在 Outlook 中，移 **至 [** 檔案] [ \> **開啟 &amp; 匯出**] \> **匯入/匯出**。

    這會啟動 [匯入及匯出] 嚮導。

2. 選取 [ **從其他程式或** 檔案匯入]，然後選取 **[下一步]**。

    ![匯入及匯出嚮導](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. 選取 [ **Outlook 資料檔案 ( .pst)**]，然後選取 **[下一步]**。

4. 流覽至您要匯入的 .pst 檔案。

5. 在 [ **選項**] 底下，選擇您要處理重複專案的方式

6. 選取 **[下一步]**。

7. 如果已指派密碼給 Outlook 資料檔案 ( .pst) ，請輸入密碼，然後選取 **[確定]**。

8. 設定匯入專案的選項。 通常不需要變更預設設定。

9. 選取 [完成 **]**。

> [!NOTE]
> 存取現有使用者的 OneDrive 和電子郵件資料時，這些步驟會保持不變。

> [!TIP]
> 如果您只想要匯入或還原 Outlook 資料檔案 ( .pst) 中的幾個專案，您可以開啟 Outlook 資料檔案。 然後，在功能窗格中，將專案從 Outlook 資料檔案資料夾拖曳至現有的 Outlook 資料夾。 

## <a name="related-articles"></a>相關文章

[在 OneDrive 帳戶上新增及移除系統管理員](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[還原已刪除的 OneDrive](/onedrive/restore-deleted-onedrive)
  
[OneDrive 保留與刪除](/onedrive/retention-and-deletion)
