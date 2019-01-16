---
title: 驗證 Windows 10 PC 上的 App 保護設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何驗證 Windows 10 裝置中的 Microsoft 365 商務應用程式保護設定。
ms.openlocfilehash: f00dd380103ad9498d77b0e8814bace3de168df4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866526"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>驗證 Windows 10 PC 上的 App 保護設定

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>確認使用者無法在公司裝置上將公司資料複製到個人檔案

之後您[設定應用程式保護原則](protection-settings-for-windows-10-devices.md)，它可能需要幾個小時才會影響使用者的裝置原則。如果**您開啟**防止使用者將複製的個人檔案的公司資料與強制其儲存至 OneDrive for Business 的工時檔案**設定擁有裝置的公司，** 您可以檢查此使用者的裝置後他們已連線至 Azure AD並已登入。 
  
 **驗證連線設定**
  
1. 使用 Microsoft 365 商務認證登入並連線至 Azure AD 如所述[設定 Microsoft 365 商務使用者的 Windows 裝置](set-up-windows-devices.md)之後，移至 [ **Windows 設定** \> **帳戶** \> **存取工作或學校**.選擇 [**連接至\<租用戶名稱\>Azure AD**，然後選擇 [**資訊**。
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. 在**受管理的**\<租用戶名稱\>頁面您可以看到包含類似如下圖所示的其中一個**管理伺服器位址****連線資訊**。 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **確認您無法將公司資料貼到未受管理的 App**
  
1. 開啟由 Microsoft 365 商務版 安裝的 Outlook 2016。
    
2. 開啟一封電子郵件，並從中複製部分內容。
    
    開啟記事本，嘗試將內容貼上。
    
    您會收到一則錯誤，其中指出 App 無法存取內容。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    不過，您可以將同樣的內容貼入 Word 2016。
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>確認使用者無法在個人裝置上將公司資料複製到個人檔案

 **驗證連線設定**
  
1. 在 Windows 10 個人在裝置上出您要以登入本機使用者移至 [ **Windows 設定**並按一下或點選**帳戶** \> **存取工作或學校**。
    
2. **存取工作或學校**] 下選擇 [**連接**]。
    
3. 輸入到您 Microsoft 365 商務認證**設定工作或學校帳戶] 對話方塊** \> **登入**。
    
4. 在 [**存取工作或學校**] 頁面上選擇 [**工作或學校帳戶**，然後選擇 [**資訊**。
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. 在 [**存取工作或學校**頁面您可以看到**連線資訊**包括顯示於下圖、 種方式在**管理伺服器位址**並包含單字*wip*和*mam*內。 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **確認您無法將公司資料貼到未受管理的 App**
  
1. 開啟 Outlook 2016，若有需要的話請新增您的 Microsoft 365 商務版 帳戶，並以您的 Microsoft 365 商務版 認證登入。
    
2. 開啟一封電子郵件，並從中複製部分內容。
    
    開啟記事本，嘗試將內容貼上。
    
    您會收到一則錯誤，其中指出 App 無法存取內容。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    不過，您可以將同樣的內容貼入 Word 2016。
    

