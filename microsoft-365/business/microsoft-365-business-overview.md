---
title: 開始使用 Microsoft 365 商務版
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 了解如何設定 Microsoft 365 商務版。
ms.openlocfilehash: 80c6590a682af5fadeceac7a75e409adac897f6f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276713"
---
# <a name="get-started-with-microsoft-365-business"></a>開始使用 Microsoft 365 商務版

## <a name="what-is-microsoft-365-business"></a>什麼是 Microsoft 365 商務版

Microsoft 365 商務版是一組完整的企業生產力和共同作業工具，例如 Outlook、Word、Excel 和其他隨時保持最新狀態的 Office 產品。您可以使用易於管理的企業級安全性功能，保護所有 iOS、Android 和 Windows 10 裝置上的工作檔案。
  
Microsoft 365 商務版是最多 300 個授權，如果您需要更多授權，請參閱[Microsoft 365 企業版](https://go.microsoft.com/fwlink/p/?linkid=860986)文件的詳細資訊。 
  
## <a name="get-microsoft-365-business"></a>取得 Microsoft 365 商務版

- 如果您有合作夥伴，他們將獲得 Microsoft 365 商務版：[從 Microsoft 合作夥伴中心取得 Microsoft 365 商務版](get-microsoft-365-business.md)。
    
- 如果您不有合作夥伴，並想要取得 Microsoft 365 商務版，您可以[在這裡購買](https://www.microsoft.com/en-us/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-business"></a>設定 Microsoft 365 商務版

 **設定 Microsoft 365 商務版套件的概觀**
  
下圖說明系統管理員如何設定 Microsoft 365 商務版。 此外，也描述準備 Windows 電腦以設定 Microsoft 365 商務版的步驟。 您也可以使用 [Windows AutoPilot](add-autopilot-devices-and-profile.md) 在 Microsoft 365 商務版系統管理中心新增裝置。 您可以使用 AutoPilot 來設定和預先設定新裝置，將裝置備妥，在使用者透過 Microsoft 365 商務版 認證登入後，就能立即用於工作生產。
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1： 設定 Microsoft 365 商務版 （系統）

使用您的全域系統管理員認證登入 [Microsoft 365 商務版系統管理中心](https://portal.office.com/adminportal/home)，然後完成下列步驟以設定 Microsoft 365 商務版。 
  
1. [使用 Microsoft 365 商務版保護裝置資料的先決條件](pre-requisites-for-data-protection.md)
    
    請先閱讀先決條件，確保您的裝置完成 Microsoft 365 商務版的設定。
    
2. [使用設定精靈來設定 Microsoft 365 商務版](set-up.md)
    
    如果您是**永久移至雲端的本機 Active directory**，您可以新增您的使用者手動在 Microsoft 365 商務版系統管理中心使用安裝精靈中，或您可以執行一次性同步作業的 Azure AD Connect。 方法有兩種： 
    
  - 如果您也有 Exchange 2010、 Exchange 2013 或 Exchange 2016 伺服器，您可以[使用基本混合式以快速移轉至 Office 365 的 Exchange 信箱](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef)。 基本混合式步驟包括將使用者同步到 Azure AD 的一次性作業，以及將電子郵件從內部部署移轉到雲端的作業。 當您使用此方法時，在電子郵件移轉作業完成之後，系統會自動關閉目錄同步處理功能。
    
  - 使用 Office 365 目錄同步精靈將使用者同步到雲端。請按照[為 Office 365 設定目錄同步處理](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)中的步驟來完成此程序。您將使用者同步到雲端之後，必須[關閉目錄同步處理](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)。
    
    您也必須向以這種方式新增的每個使用者，提供 Microsoft 365 商務版授權。 在[安裝精靈](set-up.md)中，或[指派給商務用 Office 365 中的使用者授權](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)，您可以這麼做。
    
### <a name="2-prepare-mobile-devices"></a>2： 準備行動裝置

遵循[設定為 Microsoft 365 商務版使用者的行動裝置](set-up-mobile-devices.md)上的裝置，並確定受到 Microsoft 365 商務版安裝 Office 應用程式中的步驟。 
  
### <a name="3-prepare-pcs"></a>3： 準備電腦

系統管理員可以使用[Windows AutoPilot](add-autopilot-devices-and-profile.md)來預先選取新裝置 Windows 10 電腦適用的設定。 使用者可以將他們現有或新的 Windows 10 裝置設定遵循此主題中的步驟：[設定 Microsoft 365 商務版使用者的 Windows 電腦](set-up-windows-devices.md)。 現有的裝置的使用者可以也**選擇性地**[將檔案移到商務用 OneDrive](move-files-to-onedrive.md)。 他們也可以使用協力廠商工具來移動至 OneDrive 的 Windows 設定檔相關聯的檔案。
  
如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版來保護 Windows 10 裝置，同時仍維持需要本機驗證的內部部署資源的存取權。 請遵循[啟用由 Microsoft 365 商務版來管理已加入網域的 Windows 10 裝置](manage-windows-devices.md)設定此案例中的步驟。 這是會使用慣用的方法，在此狀態的裝置稱為**混合式 Azure AD 加入裝置**。 
  
如果您保留本機 Active Directory，其中包含一些內部資源 （例如檔案共用和印表機），您可以授與您的**Azure AD 加入的裝置**存取這些資源遵循以下步驟：[存取內部部署資源Microsoft 365 商務版中的 azure AD 加入裝置](access-resources.md)。
  
您已設定 Windows 10 電腦之後，您可以對裝置的 [[自動安裝 Office](auto-install-or-uninstall-office.md) 。 
  
## <a name="contact-support"></a>連絡客戶支援

 **如果您需要連絡客戶支援：**
  
- 請與您的合作夥伴連絡。
    
- Microsoft 365 商務版系統管理員，您可以存取我們的客戶支援小組，**[商務版產品-系統管理說明連絡支援部門](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    

