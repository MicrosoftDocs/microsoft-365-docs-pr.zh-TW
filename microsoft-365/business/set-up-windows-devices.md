---
title: 設定 Microsoft 365 商務進階版使用者的 Windows 裝置
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 為 Microsoft 365 商務進階版使用者設定執行 Windows 10 專業版的 Windows 裝置，以啟用集中式管理及安全性控制。
ms.openlocfilehash: a911414b1a7abef259f4c5fffbdd48e07f9ebfdd
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393352"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>設定 Microsoft 365 商務進階版使用者的 Windows 裝置

## <a name="before-you-begin"></a>在您開始之前

在您可以設定 Microsoft 365 商務進階版使用者的 Windows 裝置之前，請確定所有 Windows 裝置都執行 Windows 10 專業版，版本 1703 (建立者更新) 。 Windows 10 專業版是部署 Windows 10 商務版的必要條件，也就是一組雲端服務和裝置管理功能，可補充 Windows 10 專業版和啟用 Microsoft 365 商務進階版的集中式管理及安全性控制。
  
如果您有執行 Windows 7 Pro、Windows 8 專業版或 Windows 8.1 專業版的 Windows 裝置，Microsoft 365 商務進階版訂閱可讓您進行 Windows 10 升級。
  
如需有關如何將 Windows 裝置升級到 Windows 10 專業版 Creators Update 的資訊，請按照本主題中的步驟進行：[將 Windows 裝置升級到 Windows 專業版 Creators Update](upgrade-to-windows-pro-creators-update.md)。
  
請參閱 Verify the device the the the the device the the [AZURE AD](#verify-the-device-is-connected-to-azure-ad) to verify the the the the the the the the the the

## <a name="watch-connect-your-pc-to-microsoft-365-business"></a>觀賞：連線您的電腦以 Microsoft 365 商務

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](../business-video/index.yml)。
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>將 Windows 10 裝置加入到貴組織的 Azure AD

當您組織中的所有 Windows 裝置都已升級為 Windows 10 專業版創意者更新，或已執行 Windows 10 專業版創意者更新時，您可以將這些裝置加入您組織的 Azure Active Directory。 裝置加入後，系統會自動升級為 Windows 10 商務版，也就是您 Microsoft 365 商務進階版訂閱的一部分。
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>適用於全新或新升級的 Windows 10 專業版裝置

針對執行 Windows 10 專業版 Creators Update 的全新裝置，或針對已升級到 Windows 10 專業版 Creators Update 但未完成 Windows 10 裝置設定的裝置，請按照這些步驟進行。
  
1. 流覽 Windows 10 裝置安裝程式，直到您看到 [**您要如何設定？** ] 頁面。 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. 在這裡，選擇 [**為組織設定**]，然後輸入 Microsoft 365 商務進階版的使用者名稱和密碼。 
    
3. 完成 Windows 10 裝置設定。
    
   完成後，使用者將連線到貴組織的 Azure AD。請參閱[驗證裝置已連線到 Azure AD](#verify-the-device-is-connected-to-azure-ad) 以確認。 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>適用於已設定且執行 Windows 10 專業版的裝置

 **將使用者連線到 Azure AD：**
  
1. In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. 在 **設定** 中，移至 [**帳戶**]。
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. 在 [**資訊**] 頁面上，按一下 [**存取工作或學校** \> **連線**]。
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. 在 [**設定工作或學校帳戶**] 對話方塊的 [**替代動作**] 下，選擇 [將 **此裝置加入至 Azure Active Directory**]。
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. 在 [ **讓您登入** ] 頁面上，輸入您 \> **下一個** 工作或學校帳戶。
  
   在 [ **輸入密碼** ] 頁面上，輸入您的密碼登 \> **入**。
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. 在 [ **確定這是您的組織** ] 頁面上，確認資訊正確無誤，然後選擇 [ **加入**]。
  
   已 **全部設定！** 頁面上，chosse **完成**。
  
   ![在 [確定這是您的組織] 畫面上，選擇 [加入]](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
如果您將檔案上傳至商務用 OneDrive，請將檔案同步回原處。 如果您使用協力廠商工具來遷移設定檔和檔案，也請將其同步處理至新的設定檔。
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>驗證裝置已連線到 Azure AD

若要確認您的同步處理狀態，請在 **設定** 的 [**存取工作或學校**] 頁面上，選取 [**連接到** _ \<organization name\> _ **]** 區域，以公開按鈕 **資訊** 並中斷連線。 選擇 [ **資訊** ] 以取得同步處理狀態。 
  
在 [ **同步處理狀態** ] 頁面上，選擇 [ **同步** 處理]，以取得最新的行動裝置管理原則至電腦。
  
若要開始使用 Microsoft 365 商務進階版帳戶，請移至 [Windows **開始**] 按鈕，以滑鼠右鍵按一下您目前的帳戶圖片，然後 **切換帳戶**。 使用您的組織電子郵件和密碼登入。
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>確認電腦已升級為 Windows 10 商務版

確認您的 Azure AD 加入的 Windows 10 裝置已升級為 Windows 10 商務版 Microsoft 365 商務進階版訂閱的一部分。
  
1. 移至 **設定** \> **系統** \> ****。
    
2. 確認該 **版本** 顯示 **Windows 10 商務版**。
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>後續步驟

若要設定行動裝置，請參閱為[Microsoft 365 商務進階版使用者設定行動裝置](set-up-mobile-devices.md)，以設定裝置保護或應用程式保護原則，請參閱[Manage Microsoft 365 for Business](manage.md)。
  
## <a name="related-content"></a>相關內容

[商務用 Microsoft 365 訓練影片](../business-video/index.yml) (連結頁面)
