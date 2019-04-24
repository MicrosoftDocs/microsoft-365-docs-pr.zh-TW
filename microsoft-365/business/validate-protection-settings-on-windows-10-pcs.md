---
title: 驗證 Windows 10 PC 上的 App 保護設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何驗證 Windows 10 裝置中的 Microsoft 365 商務版應用程式保護設定。
ms.openlocfilehash: 4f1f0993dff0ef8d3f6858a3749e063c7b5579c7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279934"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>驗證 Windows 10 PC 上的 App 保護設定

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>確認使用者無法在公司裝置上將公司資料複製到個人檔案

在您[設定 App 保護原則](protection-settings-for-windows-10-devices.md)後，這些原則可能需要幾個小時才會在使用者的裝置上生效。 如果**您開啟**防止使用者複製到個人檔案的公司資料並強制他們將工作將檔案儲存到商務用 OneDrive**設定公司擁有裝置，** 您可以檢查此使用者的裝置之後他們已連線到 Azure AD並登入。 
  
 **驗證連線設定**
  
1. 使用 Microsoft 365 商務版認證登入後，當您連線到 Azure AD 中[設定 Windows 裝置，為 Microsoft 365 商務版使用者](set-up-windows-devices.md)所述，移至 [ **Windows 設定** \> **帳戶** \> **存取公司或學校資源**. 選擇 [**連線至\<租用戶名稱\>Azure AD**，然後選擇 [**資訊**。
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. 在**管理者**\<租用戶名稱\>] 頁面上，您可以查看**連線資訊**，其中包含的**管理伺服器位址**，例如下圖所示。 
    
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
  
1. Windows 10 個人裝置： 您以登入本機使用者，請移至**Windows 設定**並按一下或點選 [**帳戶** \> **存取公司或學校資源**。
    
2. **存取公司或學校資源**] 下選擇 [**連線**]。
    
3. 輸入您的 Microsoft 365 商務版認證到**設定公司或學校帳戶] 對話方塊** \> **登入**。
    
4. 在 [**存取公司或學校資源**] 頁面上，選擇 [**工作或學校帳戶**，然後選擇 [**資訊**。
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. 在 [**存取公司或學校資源**] 頁面中，您可以查看**連線資訊**，包含**管理伺服器位址**，例如下圖中，所示，並包含單字*wip*和*mam*內。 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **確認您無法將公司資料貼到未受管理的 App**
  
1. 開啟 Outlook 2016，若有需要的話請新增您的 Microsoft 365 商務版 帳戶，並以您的 Microsoft 365 商務版 認證登入。
    
2. 開啟一封電子郵件，並從中複製部分內容。
    
    開啟記事本，嘗試將內容貼上。
    
    您會收到一則錯誤，其中指出 App 無法存取內容。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    不過，您可以將同樣的內容貼入 Word 2016。
    

