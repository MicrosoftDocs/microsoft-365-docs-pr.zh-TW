---
title: 從 Google Workspace 移動商務電子郵件和日曆
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將電子郵件、連絡人和日曆從 Google Workspace 遷移到商務用 Microsoft 365。
ms.openlocfilehash: cb751b1d2f18b226021bb6f218b62f3ae426f6a4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928243"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>從 Google Workspace 移動商務電子郵件和日曆

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

您可以使用系統管理員管理方式從 Google Workspace 移往 Exchange Online。 您可以一次或階段地所有來電郵件。 下列步驟將說明一次如何遷移電子郵件資料。 詳細資訊請參閱執行 [G Suite 移移](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)。

移移程式需要數個步驟，而且可能需要數小時到數天的時間，視您移移的資料量決定。

## <a name="try-it"></a>試試看吧！

### <a name="create-a-google-service-account"></a>建立 Google 服務帳戶

1. 使用 Chrome 瀏覽器，在[admin.google.com。](https://admin.google.com) 
1. 在新的分頁或視窗中，流覽至服務 [帳戶](https://console.developers.google.com/iam-admin/serviceaccounts) 頁面。 
1. 選取 **建立專案**，命名專案 **，然後選擇建立**。 
1. 選取 **建立服務帳戶**，輸入名稱 **，選擇建立** ，然後 **完成**。 
1. 開啟動作 **功能表** ，選取 **編輯**，然後記下唯一識別碼。 此程式稍後會需要此識別碼。 
1. 開啟顯示 **全網委派** 區段。 
1. 選取 **啟用 G Suite 網域委派**，輸入同意畫面的產品名稱，**然後選擇儲存。** 

    > [!NOTE]
> 移移程式不會使用產品名稱，但需要產品名稱才能儲存在對話方塊中。     

1. 再次開啟 **動作功能表** ，然後選取建立 **鍵**。 
1. 選擇 **JSON，****然後建立**。 

     私密金鑰會儲存到您裝置上的下載資料夾。
 
1. 選取 **[關閉]**。 

### <a name="enable-api-usage-for-the-project"></a>啟用專案的 API 使用方式

1. 流覽至 [API 頁面](https://console.developers.google.com/apis/library)。 
1. 在搜尋行中，輸入 **Gmail API。**
1. 選取它，**然後選擇啟用。**
1. 針對 Google 日曆 API 和連絡人 API 重複此程式。 

### <a name="grant-access-to-the-service-account"></a>授予服務帳戶的存取權

1. 返回 Google Workspace 系統管理主控台。 
1. 選取 **安全性**，向下卷卷並開啟 **API 控制項**。 
1. 向下卷選並選取 **管理網域委派**。
1. 選取 **新增** ，然後輸入您先前記下的用戶端識別碼。
1. 然後輸入 Google API 的 OAuth 範圍。 這些步驟可在步驟 5 [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) 提供，並且有：

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. 選擇 **授權**。 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>為要寄到 Microsoft 365 的郵件建立子域

1. 返回 **Google Workspace 系統管理** 主控台。
1. 選取 **網域****、管理網域**，**然後新增網域別名**。 
1. 輸入網域別名，例如 `m365.contoso.com` .
1. 然後選取 **繼續並驗證網域擁有權**。 

    網域驗證通常只需要幾分鐘的時間，但最多可能需要 48 小時。

1. 請前往 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
1. 在 **Microsoft 365** 系統管理中心的左側 NAV中，選取顯示全部、設定、網域，然後新增 **網域。**  
1. 輸入您先前建立過的子域，然後選取使用 **這個網域**。 
1. 若要連接網域，請 **選取繼續**。 
1. 向下卷起並記下 MX 記錄、CNAME 記錄及 TXT 記錄。 
1. 返回 **Google 管理主控台**。
1. 選取 **網域**、**選取管理網域****、驗證** 詳細資料，然後 **管理網域**。 
1. 在左側流覽中，選擇 **DNS** 並向下卷到 **自訂資源記錄**。 
1. 開啟記錄類型下拉式選項，然後選取 **MX，** 輸入或複製並貼上您先前提到的 MX 記錄資訊，然後選擇新增。  
1. 對 CNAME 記錄和 TXT 記錄重複此程式。 

    這些變更可能需要一些時間，變更生效。  

1. 返回 Microsoft **365 系統** 管理中心您離開的地方，然後 **選取繼續**。 

您的網域現在已設定好。  

### <a name="create-email-aliases-in-microsoft-365"></a>在 Microsoft 365 中建立電子郵件別名

在開始移轉之前，您必須使用新的子域為使用者建立電子郵件別名。 

1. 若要開始下一個步驟，請在Microsoft 365 系統管理中心的新增網域精靈中，選取前往 **使用中使用者。** 
1. 選取使用者，然後管理 **使用者名稱和電子郵件**。 
1. 從網 **域下** 拉清單，選取您先前建立過的子域。 
1. 輸入使用者名稱、 **選取新增**、 **儲存變更**，然後關閉視窗。 

    為每個使用者重複此程式。 

### <a name="start-the-migration-process"></a>開始移移程式

完成後，就可以開始進行遷移了。 

1. 在 **Microsoft 365** 系統管理中心的左側流覽中，向下卷到系統 **管理中心**，然後選取 **Exchange。** 
1. 在 **收件者下****，選擇** 移移 **、選取新增**、移移至 Exchange **Online、** 選擇 **G Suite** 移移，然後選擇下 **一步**。 
1. 建立包含您想要遷移之信箱清單的 CSV 檔案。 請確認檔案採用此格式： 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      詳情[請參閱aka.ms/GoogleWorkspaceMigration。](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac) 

1. 選取 **選擇檔案**，流覽至 CSV 檔案，選擇該檔案， **選取開啟**，然後選取下 **一個**。 
1. 確認您想要用於測試的系統管理員電子郵件地址。 
1. 選取 **選擇檔案**，流覽至您先前所建立之 JSON (通常位於您電腦的下載) ，選擇該檔案，選取開啟，然後選取下一 **步**。 
1. 在新的移移批次名稱 **欄位中輸入名稱**。
1. 輸入您于目標傳遞網域欄位中所建立的子域 **，選取下** 一個，然後選取 **新**。 
1. 儲存資訊之後， **請選取確定**。 

    現在，您可以查看移移狀態。 

1. 經過一段時間之後，根據您移轉的使用者數量，選取重新 **更新。** 
1. 一旦狀態變更為已 **同步處理，請** 選取 **完成此** 移移批次，然後 **選取是**。 
1. 完成程式後，您的狀態就會變更為 **完成**。 
1. 您可以視需要選取查看 **詳細資料** ，以進一步瞭解移移。 
1. 選取 **[關閉]**。 
1. 開啟 Outlook 以驗證來自 Google Workspace 的所有電子郵件已成功移移。
您也可以對日曆專案和連絡人重複此操作。