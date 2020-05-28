---
title: 驗證 Windows 10 PC 上的 App 保護設定
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 在 Windows 10 裝置上驗證 Microsoft 365 商務高級應用程式保護設定，並確認使用者無法將公司資料複製到個人檔案或非受管理的應用程式。
ms.openlocfilehash: 589d2fc25cc1425a775523595881660cc03e152e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403383"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>驗證 Windows 10 PC 上的 App 保護設定

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>確認使用者無法在公司裝置上將公司資料複製到個人檔案

在您[設定 App 保護原則](protection-settings-for-windows-10-devices.md)後，這些原則可能需要幾個小時才會在使用者的裝置上生效。 如果您已**開啟**[**防止使用者將公司資料複製到個人檔案，並強制使用者將公司的工作檔案儲存到**公司所擁有的裝置 OneDrive] 設定，您可以在使用者的裝置連接至 Azure AD 並登入後，對其進行檢查。 
  
 **驗證連線設定**
  
1. 使用 microsoft 365 商務版認證登入並聯機至 Azure AD 後，如[設定 microsoft 365 商務版使用者的 Windows 裝置](set-up-windows-devices.md)中所述，請移至 [ **windows 設定** \> **帳戶**]， \> **存取工作或學校**。 選擇 [**連線到 \<tenant name\> Azure AD**]，然後選擇 [**資訊**]。
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. 在 [**管理者**] \<tenant name\> 頁面上，您可以看到包含**管理伺服器位址**的連線**資訊**，如下圖所示。 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **確認您無法將公司資料貼到非受管理的應用程式中**
  
1. 開啟由 Microsoft 365 商務版特優安裝的 Outlook 2016。
    
2. 開啟一封電子郵件，並從中複製部分內容。
    
    開啟記事本，嘗試將內容貼上。
    
    您會收到錯誤，指出應用程式無法存取內容。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    不過，您可以將同樣的內容貼入 Word 2016。
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>確認使用者無法在個人裝置上將公司資料複製到個人檔案

 **驗證連線設定**
  
1. 在您以本機使用者身分登入的 Windows 10 個人裝置上，移至 [ **Windows 設定**]，然後按一下或點擊 [**帳戶** \> **存取工作或學校**]。
    
2. 在 [**存取工作或學校**] 底下，選擇 **[連接]**。
    
3. 在 [**設定公司或學校帳戶] 對話方塊**的 [登入] 中輸入您的 Microsoft 365 商務版認證 \> ** **。
    
4. 在 [**存取公司或學校**] 頁面上，選擇 [**公司或學校帳戶**]，然後選擇 [**資訊**]。
    
    ![在 [工作或學校帳戶] 對話方塊中，按一下或點擊 [資訊]。](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. 在 [**存取公司或學校**] 頁面上，您可以看到包含**管理伺服器位址**的連線**資訊**，如下圖所示，並包含*wip*和*mam*中的文字。 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **確認您無法將公司資料貼到非受管理的應用程式中**
  
1. 開啟 Outlook 2016，並在必要時新增您的 Microsoft 365 商務版帳戶，並使用您的 Microsoft 365 商務版認證登入。
    
2. 開啟一封電子郵件，並從中複製部分內容。
    
    開啟記事本，嘗試將內容貼上。
    
    您會收到錯誤，指出應用程式無法存取內容。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    不過，您可以將同樣的內容貼入 Word 2016。
    

