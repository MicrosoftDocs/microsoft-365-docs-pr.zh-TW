---
title: 從 Google Workspace 遷移商務電子郵件和行事曆
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將電子郵件、連絡人及行事曆從 Google Workspace 遷移至商務用 Microsoft 365。
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913619"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>從 Google Workspace 遷移商務電子郵件和行事曆

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

您可以使用從 Google Workspace Exchange Online 的系統管理員的遷移。 您可以一次或分階段遷移郵件。 下列步驟顯示如何一次遷移電子郵件資料。 如需詳細資訊，請參閱 [執行 a G Suite 遷移](/exchange/mailbox-migration/perform-g-suite-migration)。

遷移程式需要數個步驟，而且可能需要數小時到數天內，視您要遷移的資料量而定。

## <a name="try-it"></a>試試看吧！

### <a name="create-a-google-service-account"></a>建立 Google 服務帳戶

1. 使用 Chrome 瀏覽器，在 [admin.google.com](https://admin.google.com)登入 Google Workspace 管理主控台。 
1. 在新的索引標籤或視窗中，流覽至 [ [服務帳戶](https://console.developers.google.com/iam-admin/serviceaccounts) ] 頁面。 
1. 選取 [ **建立專案**]，為專案命名，然後選擇 [ **建立**]。 
1. 選取 [**建立服務帳戶**]，輸入名稱，然後選擇 [建立]，然後選擇 [**建立** **]。** 
1. 開啟 [ **動作** ] 功能表，選取 [ **編輯**]，並記下唯一的識別碼。 您將在此程式中稍後需要這個識別碼。 
1. 開啟 [ **顯示全網域委派** ] 區段。 
1. 選取 [ **啟用 G Suite 全域的委派**]，輸入同意畫面的產品名稱，然後選擇 [ **儲存**]。 

    > [!NOTE]
> 遷移程式不會使用產品名稱，但需要在對話方塊中進行儲存。     

1. 再次開啟 [ **動作** ] 功能表，然後選取 [ **建立機碼**]。 
1. 選擇 [ **JSON**]，然後 **建立**。 

     私密金鑰會儲存至裝置上的下載資料夾。
 
1. 選取 **[關閉]**。 

### <a name="enable-api-usage-for-the-project"></a>啟用專案的 API 使用方式

1. 流覽至 [ [APIs] 頁面](https://console.developers.google.com/apis/library)。 
1. 在搜尋列中，輸入 **GMAIL API**。
1. 選取它，然後選擇 [ **啟用**]。
1. 針對 Google Calendar API 和 Contacts API 重複此程式。 

### <a name="grant-access-to-the-service-account"></a>授與服務帳戶的存取權

1. 回到 Google Workspace 管理主控台。 
1. 選取 [ **安全性**]，向下並向下並開啟 **API 控制項**。 
1. 向外按，然後選取 [ **管理全網域委派**]。
1. 選取 [ **新增** ]，然後輸入您在先前所做的用戶端識別碼。
1. 然後輸入 Google APIs 的 OAuth 範圍。 這些是在步驟5的 [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) 中提供，也就是：

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. 選擇 [ **授權**]。 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>建立要 Microsoft 365 郵件的子域

1. 回到 **Google Workspace 管理** 主控台。
1. 選取 [ **網域**]、[ **管理網域**]，然後 **新增網域別名**。 
1. 輸入類似的域別名 `m365.contoso.com` 。
1. 然後選取 [ **繼續]，然後確認網域擁有權**。 

    網域驗證通常只需要幾分鐘的時間，但可能需要長達48小時。

1. 移至[Microsoft 365 系統管理中心](https://admin.microsoft.com)。
1. 在 **Microsoft 365 系統管理中心** 的左側導覽中，選取 [**全部顯示**]、[**設定**]、[**網域**]，然後 **新增網域**。 
1. 輸入您先前建立的子域，然後選取 [ **使用此網域**]。 
1. 若要連接網域，請選取 [ **繼續**]。 
1. 向下滾動並記下 MX 記錄、CNAME 記錄和 TXT 記錄。 
1. 回到 Google 系統 **管理主控台**。
1. 選取 [ **網域**]，選取 [ **管理網域**]， **確認詳細資料** ，然後 **管理網域**。 
1. 在左側導覽中，選擇 [ **DNS** ]，然後向下滾動至 [ **自訂資源記錄**]。 
1. 開啟 [記錄類型] 下拉式清單，然後選取 [ **mx**]，輸入或複製並貼上您先前記下的 mx 記錄資訊，然後選擇 [ **新增**]。 
1. 重複 CNAME 記錄和 TXT 記錄的處理常式。 

    可能需要一些時間，這些變更才會生效。  

1. 回到您在 **Microsoft 365 系統管理中心** 中離開的位置，然後選取 [**繼續**]。 

您的網域現在已設定好。  

### <a name="create-email-aliases-in-microsoft-365"></a>在 Microsoft 365 中建立電子郵件別名

在遷移開始之前，您必須使用新的子域建立使用者的電子郵件別名。 

1. 若要開始下一個步驟，請在 Microsoft 365 系統管理中心的 [**新增網域**] 嚮導中，選取 [**移至** 作用中使用者]。 
1. 選取使用者，然後管理使用者 **名稱和電子郵件**。 
1. 從 [ **網域** ] 下拉式清單中，選取您先前建立的子域。 
1. 輸入使用者名稱，然後選取 [ **新增**]、[ **儲存變更**]，然後關閉視窗。 

    針對每個使用者重複此程式。 

### <a name="start-the-migration-process"></a>啟動遷移程式

完成後，您就可以遷移。 

1. 在 **Microsoft 365 系統管理中心** 的左側導覽中，向下滾動至 [系統管理中心 **]，然後** 選取 [ **Exchange**]。 
1. 在 [收件者]**底下，選擇**[**遷移**]，選取 [**新增**]，[**遷移至 Exchange Online**]，選擇 [ **G Suite 遷移** **]**，然後 
1. 使用您要遷移的信箱清單建立 CSV 檔案。 請確定檔案遵循下列格式： 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      如需詳細資訊，請參閱 [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)。 

1. 選取 **[選擇** 檔案]，流覽至 CSV 檔案，然後選取 [ **開啟**]，然後選取 **[下一步]**。 
1. 確認您要用來測試的系統管理員電子郵件地址。 
1. 選取 **[選擇** 檔案]，流覽至您先前建立的 JSON 檔案 (通常是在電腦上的 [下載] 資料夾中) 選取它，然後選取 [ **開啟**]，再按 **[下一步]**。 
1. 在 [ **新增遷移批次名稱] 欄位** 中輸入名稱。
1. 在 [ **目標傳遞網域** ] 欄位中，輸入您建立的子域，選取 **[下一步]**，然後選取 [ **新增**]。 
1. 儲存資訊後，請選取 **[確定]**。 

    您現在可以查看遷移的狀態。 

1. 經過一段時間之後，視您要遷移的使用者人數而定， **選取 [** 重新整理]。 
1. 一旦狀態變更為 [已 **同步** 處理]，請選取 [ **完成此遷移批次**]，然後選取 **[是]**。 
1. 完成此程式之後，您的狀態會變更為 [ **已完成**]。 
1. 如有需要，您可以選取 [ **查看詳細** 資訊] 以取得有關遷移的詳細資訊。 
1. 選取 **[關閉]**。 
1. 開啟 Outlook，確認已順利遷移 Google Workspace 中的所有電子郵件。
您也可以為行事曆專案和連絡人重複此專案。