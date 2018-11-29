---
title: 開始使用 Microsoft 365 商務版
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 了解如何設定 Microsoft 365 Business。
ms.openlocfilehash: ee15ffa98de032d7936d950124cdf772335949bd
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866521"
---
# <a name="get-started-with-microsoft-365-business"></a>開始使用 Microsoft 365 商務版

## <a name="what-is-microsoft-365-business"></a>什麼是 Microsoft 365 商務版

Microsoft 365 商務版是一組完整的企業生產力和共同作業工具，例如 Outlook、Word、Excel 和其他隨時保持最新狀態的 Office 產品。您可以使用易於管理的企業級安全性功能，保護所有 iOS、Android 和 Windows 10 裝置上的工作檔案。
  
如果您需要更多授權最多 300 授權，只用 Microsoft 365 Business，請參閱[Microsoft 365 企業版](https://go.microsoft.com/fwlink/p/?linkid=860986)文件的詳細資訊。 
  
## <a name="get-microsoft-365-business"></a>取得 Microsoft 365 商務版

- 如果您有合作夥伴，他們將獲得 Microsoft 365 商務版：[從 Microsoft 合作夥伴中心取得 Microsoft 365 商務版](get-microsoft-365-business.md)。
    
- 如果您不具有合作夥伴並想要取得 Microsoft 365 Business，您還可以[購買這裡](https://www.microsoft.com/en-us/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-business"></a>設定 Microsoft 365 商務版

 **設定 Microsoft 365 Business Suite 的概觀**
  
下圖說明系統管理員如何設定 Microsoft 365 Business。同時也會說明 Microsoft 365 企業版準備 Windows pc 後的步驟。您也可以在[Windows 自動駕駛儀上](add-autopilot-devices-and-profile.md)與 Microsoft 365 商務系統管理中心新增至新的裝置。您可以使用自動駕駛儀上設定及前設定新的裝置、 取得其準備好用於提高工作效率一旦使用者會使用其 Microsoft 365 商務認證。
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1： 設定 Microsoft 365 商務 (Admin)

使用您的全域系統管理員認證登入 [Microsoft 365 商務版系統管理中心](https://portal.office.com/adminportal/home)，然後完成下列步驟以設定 Microsoft 365 商務版。 
  
1. [使用 Microsoft 365 商務版保護裝置資料的先決條件](pre-requisites-for-data-protection.md)
    
    請先閱讀先決條件，確保您的裝置完成 Microsoft 365 商務版的設定。
    
2. [使用設定精靈來設定 Microsoft 365 商務版](set-up.md)
    
    如果您要**永久移至雲端的本機 Active Directory 中**，您可以新增您的使用者手動在 Microsoft 365 商務系統管理中心中使用 [安裝精靈] 或您可以使用 Azure AD Connect 一次性同步。有兩種方式可以執行這項作業： 
    
  - 如果您也有 Exchange 2010、 Exchange 2013 或 Exchange 2016 伺服器，您還可以[使用最少混合快速移轉至 Office 365 的 Exchange 信箱](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef)。最少的混合式步驟包括至 Azure AD 的使用者進行單次同步以及電子郵件從內部部署移轉至雲端。完成移轉電子郵件之後，請使用此方法時目錄同步作業會自動關閉。
    
  - 使用 Office 365 目錄同步精靈將使用者同步到雲端。請按照[為 Office 365 設定目錄同步處理](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)中的步驟來完成此程序。您將使用者同步到雲端之後，必須[關閉目錄同步處理](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)。
    
    您也必須提供每位使用者已新增至 Microsoft 365 商務如此一來授權。在[安裝精靈](set-up.md)] 或[指派給 Office 365 中的商務使用者的授權](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)您可以這麼做。
    
### <a name="2-prepare-mobile-devices"></a>2： 準備行動裝置

遵循裝置與確定並受到 Microsoft 365 業務上安裝 Office 應用程式[設定為 Microsoft 365 商務使用者的行動裝置](set-up-mobile-devices.md)中的步驟。 
  
### <a name="3-prepare-pcs"></a>3： 準備 Pc

系統管理員可以使用[Windows 自動駕駛儀上](add-autopilot-devices-and-profile.md)，預先選取新的裝置 Windows 10 pc 後的設定。使用者可以將其現有或新的 Windows 10 裝置設定遵循此主題中的步驟：[設定 Microsoft 365 商務使用者的 Windows Pc](set-up-windows-devices.md)。現有裝置的使用者可以也 **（選用）**[移至 OneDrive for Business 的檔案](move-files-to-onedrive.md)。他們也可以使用協力廠商工具以移動至 OneDrive Windows 設定檔相關聯的檔案。
  
如果貴組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務來保護您的 Windows 10 裝置，同時仍維持需要本機驗證的內部部署資源的存取權。請遵循[讓 Microsoft 365 商務一併管理已加入網域的 Windows 10 裝置](manage-windows-devices.md)來設定此步驟。這是慣用的方法和**混合式 Azure AD 加入裝置**稱為裝置在此狀態。 
  
如果您保留本機 Active Directory 包含一些內部資源 （例如檔案共用及印表機），您可以指定給**Azure AD 加入裝置**存取這些資源遵循以下步驟：[存取內部部署中的資源在 Microsoft 365 商務 azure AD 加入裝置](access-resources.md)。
  
設定 Windows 10 Pc 之後，您還可以裝置[自動安裝 Office](auto-install-or-uninstall-office.md) 。 
  
## <a name="contact-support"></a>連絡客戶支援

 **如果您需要連絡客戶支援：**
  
- 請與您的合作夥伴連絡。
    
- 必須為 Microsoft 365 商務系統管理存取 「 客戶支援小組**[商務產品-Admin 說明連絡人支援](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    

