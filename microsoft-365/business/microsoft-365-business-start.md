---
title: 開始使用商務 Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 深入瞭解商務的 Microsoft 365，如何加以設定，以及如何準備使用者的裝置和電腦，以確保它們受到商務 Microsoft 365 保護。
ms.openlocfilehash: ddf6f8d12587c6fb562a599a41c190ffef32c147
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293700"
---
# <a name="get-started-with-microsoft-365-for-business"></a>開始使用商務 Microsoft 365

## <a name="what-is-microsoft-365-for-business"></a>什麼是商務 Microsoft 365

商務用 Microsoft 365 是一組完整的商業生產力和共同作業工具，例如 Outlook、Word、Excel 和其他 Office 產品，永遠都是最新的。 您可以使用易於管理的企業級安全性，保護所有 iOS、Android 和 Windows 10 裝置上的工作檔案。

觀賞這段影片，快速流覽 Microsoft 365 商務。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
商務用 Microsoft 365 適用于300授權。 如果您需要更多授權，請參閱 [Microsoft 365 企業版](../enterprise/index.yml)文件，以取得詳細資訊。 
  
## <a name="get-microsoft-365-for-business"></a>取得商務 Microsoft 365

- 如果您有合作夥伴，他們會收到商務用 Microsoft 365：[從 Microsoft partner Center 取得商務 Microsoft 365](get-microsoft-365-business.md)。
    
- 如果您沒有合作夥伴，且想要取得商務 Microsoft 365，您可以在[這裡購買](https://www.microsoft.com/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-for-business"></a>設定商務用 Microsoft 365

 **商務套件設定 Microsoft 365 的概覽**
  
下圖說明管理員如何設定 Microsoft 365 的商務。 同時也說明為商務 Microsoft 365 準備 Windows 電腦的步驟。 您也可以使用[Windows AutoPilot](add-autopilot-devices-and-profile.md)，在 Microsoft 365 系統管理中心新增裝置。 您可以使用 AutoPilot 來設定和預先設定新的裝置，使其在使用者登入商務認證的 Microsoft 365 時立即可供生產力使用。
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

觀賞這段影片，瞭解商務安裝的 Microsoft 365。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](../business-video/index.yml)。

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1：設定商務 Microsoft 365 (Admin) 

使用您的全域系統管理員認證登入[Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home)，然後完成下列步驟以設定商務 Microsoft 365。 
  
1. [使用 Microsoft 365 商務裝置保護裝置資料的先決條件](pre-requisites-for-data-protection.md)
    
    請先閱讀必要條件，以確保您的裝置準備好用於 Microsoft 365 商務用。
    
2. [使用設定向導設定商務 Microsoft 365](set-up.md)
    
    如果您要 **永久地從本機 Active Directory 移至雲端**，您可以移至 Microsoft 365 系統管理中心，並使用安裝精靈手動新增您的使用者，也可以使用 Azure AD 連線進行一次同步處理。 執行這項作業的方法有兩種： 
    
    - 如果您也有 Exchange 2010、Exchange 2013 或 Exchange 2016 伺服器，您可以[使用最低混合式將 Exchange 信箱快速遷移至 Microsoft 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)。 最基本的混合步驟包括將使用者同步處理至 Azure AD，以及從內部部署至雲端的電子郵件遷移。 電子郵件遷移完成之後，當您使用此方法時，目錄同步處理會自動關閉。
    
    - 使用目錄同步處理嚮導，將您的使用者同步處理至雲端。 遵循[設定 Microsoft 365 的目錄同步](../enterprise/set-up-directory-synchronization.md)處理中的步驟，以完成此程式。 將使用者同步到雲端之後，您必須[關閉 Microsoft 365 的目錄同步](../enterprise/turn-off-directory-synchronization.md)處理。
    
    您也必須將以這種方式新增的每個使用者授與 Microsoft 365 為商務用的授權。 您可以在 [安裝精靈](set-up.md) 中執行這項作業，也可以 [將授權指派給使用者](../admin/manage/assign-licenses-to-users.md)。
    
### <a name="2-prepare-mobile-devices"></a>2：準備行動裝置

遵循為[商務使用者設定行動裝置 Microsoft 365](set-up-mobile-devices.md)中的步驟，在裝置上安裝 Office 應用程式，並確定其受到 Microsoft 365 企業版的保護。 
  
### <a name="3-prepare-pcs"></a>3：準備電腦

系統管理員可以使用[Windows AutoPilot](add-autopilot-devices-and-profile.md)，預先選取新 Windows 10 電腦的設定。 使用者可以遵循本主題中的步驟，設定其現有或新的 Windows 10 裝置：[為商務使用者設定 Windows 的 Microsoft 365 電腦](set-up-windows-devices.md)。 在現有裝置中，使用者可以 **選擇性地**[將檔案移至商務用 OneDrive](move-files-to-onedrive.md)。 他們也可以使用協力廠商工具，將與 Windows 設定檔相關聯的檔案移至 OneDrive。
  
如果您的組織使用 Windows 的伺服器 Active Directory 內部部署，您可以設定商務 Microsoft 365 以保護 Windows 10 裝置，同時仍維持對需要本機驗證的內部部署資源的存取。 請遵循[啟用加入網域的 Windows 10 裝置以供商務 Microsoft 365 進行管理](manage-windows-devices.md)，以加以設定的步驟。 這個方法是可取的，且此狀態的裝置稱為 **混合式 AZURE AD join 裝置**。 
  
如果您保留的本機 Active Directory 包含某些內部部署資源 (例如檔案共用和印表機) ，您可以執行下列步驟，讓 **Azure 已加入 azure 的裝置** 存取這些資源：[從 Microsoft 365 for business 的 Azure 已加入 Azure 裝置存取內部部署資源](access-resources.md)。
  
  
## <a name="contact-support"></a>連絡客戶支援

 **如果您需要連絡客戶支援：**
  
- 請與您的合作夥伴連絡。
    
- 作為商務系統管理員的 Microsoft 365，您可以存取我們的客戶支援小組： **[請洽詢商務產品的支援人員-系統管理](../business-video/get-help-support.md)說明**
    
## <a name="related-content"></a>相關內容

[商務檔和資源的 Microsoft 365](./index.yml)
  
[管理商務用 Microsoft 365](manage.md)[遷移至商務 Microsoft 365](migrate-to-microsoft-365-business.md)

[商務用 Microsoft 365 訓練影片](../business-video/index.yml)