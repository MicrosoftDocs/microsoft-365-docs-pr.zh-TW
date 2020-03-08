---
title: 為 Microsoft 365 商務版使用者設定 Windows 裝置
f1.keywords:
- CSH
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 了解如何設定 Windows 裝置執行 Windows 10 專業版 Microsoft 365 商務版使用者，啟用集中式的管理和安全性控制。
ms.openlocfilehash: 6ecc45f825a783d9d47c4b069a6021143d96597c
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561153"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a>為 Microsoft 365 商務版使用者設定 Windows 裝置

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-users"></a>設定為 Microsoft 365 商務版使用者的 Windows 裝置的必要條件

請先確認所有 Windows 裝置皆執行 Windows 10 專業版的版本 1703 (Creators Update)，才能為 Microsoft 365 商務版使用者設定 Windows 裝置。Windows 10 專業版是部署 Windows 10 商務版的先決條件，它是一套加強 Windows 10 專業版的雲端服務和裝置管理功能，而且可支援 Microsoft 365 商務版的集中管理和安全性控制。
  
如果您有執行 Windows 7 專業版、Windows 8 專業版或 Windows 8.1 專業版的 Windows 裝置，您的 Microsoft 365 商務版訂閱即符合 Windows 10 升級的資格。
  
如需有關如何將 Windows 裝置升級到 Windows 10 專業版 Creators Update 的資訊，請按照本主題中的步驟進行：[將 Windows 裝置升級到 Windows 專業版 Creators Update](upgrade-to-windows-pro-creators-update.md)。
  
請參閱[驗證裝置已連線到 Azure AD](#verify-the-device-is-connected-to-azure-ad)若要確認您已升級或確認升級正常運作。

觀看有關 Windows 連線至 Microsoft 365 簡短影片。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>將 Windows 10 裝置加入到貴組織的 Azure AD

組織中的所有 Windows 裝置可以都已升級至 Windows 10 專業版 Creators Update，或已在執行 Windows 10 專業版 Creators Update 時, 您可以將這些裝置加入貴組織的 Azure Active Directory。 一旦加入裝置後，他們將會自動升級到 Windows 10 商務版，這是 Microsoft 365 商務版訂閱的一部分。
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>適用於全新或新升級的 Windows 10 專業版裝置

針對執行 Windows 10 專業版 Creators Update 的全新裝置，或針對已升級到 Windows 10 專業版 Creators Update 但未完成 Windows 10 裝置設定的裝置，請按照這些步驟進行。
  
1. 移到 Windows 10 裝置設定，直到到達**您要如何設定？** ] 頁面。 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. 在這裡，選擇 [**為組織設定**，然後輸入您的使用者名稱和密碼，Microsoft 365 商務版。 
    
3. 完成 Windows 10 裝置設定。
    
   完成後，使用者將連線到貴組織的 Azure AD。請參閱[驗證裝置已連線到 Azure AD](#verify-the-device-is-connected-to-azure-ad) 以確認。 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>適用於已設定且執行 Windows 10 專業版的裝置

 **將使用者連線到 Azure AD：**
  
1. In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. 在 [**設定**] 中，移至 [**帳戶**。
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. 在**您的資訊]** 頁面上，按一下 [**存取公司或學校** \> **連線**。
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. 在 [**設定公司或學校帳戶**] 對話方塊中，[**其他動作**] 底下選擇 [**加入至 Azure Active Directory 此裝置**。
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. 在 [**讓我們協助您登入**] 頁面上，輸入您的公司或學校帳戶\>**下一步**。
  
   在 [**輸入密碼**] 頁面上，輸入您的密碼\>**登入**。
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. 在**確定這是您的組織**] 頁面上，確認資訊正確，然後按一下 [**加入**。
  
   在**一切就緒 ！** ] 頁面上，按一下 [**完成**]。
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
如果您將檔案上傳至商務用 OneDrive，請將檔案同步回原處。 如果您使用協力廠商工具移轉個人資料和檔案時，也將這些內容同步到新的設定檔。
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>驗證裝置已連線到 Azure AD

若要確認您的同步處理狀態，在 [**設定**] [**存取公司或學校資源**] 頁面上按一下 [在**連線至**_\<組織名稱\>_ 區域中展示 [**資訊**] 以及 [**中斷連線**] 按鈕。 按一下 [**資訊**]，以取得您同步處理狀態。 
  
在 [同步處理狀態] 頁面上，按一下 [同步處理] 將最新的行動裝置管理原則下載到 PC 上。
  
若要開始使用 Microsoft 365 商務版帳戶，請移至 Windows [**開始**] 按鈕，以滑鼠右鍵按一下您目前的帳戶圖片]，然後**切換帳戶**。 使用您的組織電子郵件和密碼登入。
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>驗證裝置已升級到 Windows 10 商務版

驗證 Azure AD 加入的 Windows 10 裝置已升級到 Windows 10 商務版，做為 Microsoft 365 商務版訂閱的一部分。
  
1. 移至 [**設定** \> **系統** \> **有關**。
    
2. 確認**版本**] 顯示**Windows 10 商務版**。
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>後續步驟

若要設定行動裝置，請參閱[為 Microsoft 365 商務版使用者設定行動裝置](set-up-mobile-devices.md)。若要設定裝置保護或 App 保護原則，請參閱[管理 Microsoft 365 商務版](manage.md)。
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business"></a>如需設定和使用 Microsoft 365 商務版

[Microsoft 365 商務版訓練影片](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
