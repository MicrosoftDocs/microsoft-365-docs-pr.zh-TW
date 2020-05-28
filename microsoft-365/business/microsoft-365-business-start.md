---
title: 開始使用 Microsoft 365 for business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 深入瞭解 Microsoft 365 for business，如何加以設定，以及如何準備使用者的裝置和電腦，以確保 Microsoft 365 for business 所保護。
ms.openlocfilehash: a09b7c676f0e095d2a9db16daa56e19fb7a3baae
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401999"
---
# <a name="get-started-with-microsoft-365-for-business"></a>開始使用 Microsoft 365 for business

## <a name="what-is-microsoft-365-for-business"></a>何謂商務用 Microsoft 365

Microsoft 365 for business 是一組完整的商務生產力和共同作業工具，例如 Outlook、Word、Excel 和其他 Office 產品，其永遠都是最新的。 您可以使用易於管理的企業級安全性，保護所有 iOS、Android 和 Windows 10 裝置上的工作檔案。

觀賞這段影片，快速流覽 Microsoft 365 for business。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
適用于企業的 Microsoft 365 是針對最多300授權的目的。 如果您需要更多授權，請參閱 [Microsoft 365 企業版](https://go.microsoft.com/fwlink/p/?linkid=860986)文件，以取得詳細資訊。 
  
## <a name="get-microsoft-365-for-business"></a>取得 Microsoft 365 for business

- 如果您有合作夥伴，他們會獲得 Microsoft 365 for business：[從 Microsoft 合作夥伴中心取得 microsoft 365 for business](get-microsoft-365-business.md)。
    
- 如果您沒有合作夥伴，且想要取得 Microsoft 365 for business，您可以在[這裡購買](https://www.microsoft.com/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-for-business"></a>設定商務用 Microsoft 365

 **Microsoft 365 for business 套件設定概述**
  
下圖說明管理員如何設定 Microsoft 365 for business。 同時也說明為 Microsoft 365 for business 準備 Windows 電腦的步驟。 您也可以使用[Windows AutoPilot](add-autopilot-devices-and-profile.md)在 Microsoft 365 系統管理中心新增裝置。 您可以使用 AutoPilot 來設定和預先設定新的裝置，使其在使用者登入其 Microsoft 365 for business 認證時立即可供生產力使用。
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

觀賞這段影片，瞭解適用于企業的 Microsoft 365 設定。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1：設定 Microsoft 365 for business （系統管理員）

使用您的全域系統管理員認證登入[Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home)，然後完成下列步驟以設定 Microsoft 365 for business。 
  
1. [使用 Microsoft 365 for business 保護裝置上資料的必要條件](pre-requisites-for-data-protection.md)
    
    請先閱讀必要條件，以確保您的裝置可供商務用 Microsoft 365。
    
2. [使用設定向導設定 Microsoft 365 for business](set-up.md)
    
    如果您**永久從本機 Active Directory 移至雲端**，您可以移至 Microsoft 365 系統管理中心，並使用設定向導手動新增您的使用者，也可以使用 Azure AD Connect 進行一次同步處理。 方法有兩種： 
    
    - 如果您也有 Exchange 2010、Exchange 2013 或 Exchange 2016 伺服器，您可以[使用最小混合式，快速將 Exchange 信箱遷移至 Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)。 最基本的混合步驟包括將使用者同步處理至 Azure AD，以及從內部部署至雲端的電子郵件遷移。 電子郵件遷移完成之後，當您使用此方法時，目錄同步處理會自動關閉。
    
    - 使用目錄同步處理嚮導，將您的使用者同步處理至雲端。 依照[設定 Microsoft 365 的目錄同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)處理中的步驟完成此程式。 將使用者同步處理至雲端後，您必須[關閉 Office 365 的目錄同步](https://docs.microsoft.com/office365/enterprise/turn-off-directory-synchronization)作業。
    
    您也必須將以這種方式新增的每個使用者，授與 Microsoft 365 for business 的授權。 您可以在[安裝精靈](set-up.md)中執行這項作業，也可以[將授權指派給 Microsoft 365 for business 中的使用者](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)。
    
### <a name="2-prepare-mobile-devices"></a>2：準備行動裝置

請遵循為[商務用 microsoft 365 的行動裝置中設定行動裝置](set-up-mobile-devices.md)，以在裝置上安裝 Office 應用程式，並確認其受 Microsoft 365 for business 所保護。 
  
### <a name="3-prepare-pcs"></a>3：準備電腦

系統管理員可以使用[Windows AutoPilot](add-autopilot-devices-and-profile.md)，預先選取新 Windows 10 電腦的設定。 使用者可遵循本主題中的步驟，設定其現有或新的 Windows 10 裝置：[設定適用于商務用 Microsoft 365 的 Windows 電腦](set-up-windows-devices.md)。 在現有裝置中，使用者可以**選擇性地**[將檔案移至商務 OneDrive](move-files-to-onedrive.md)。 他們也可以使用協力廠商工具，將與 Windows 設定檔相關聯的檔案移至 OneDrive。
  
如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 for business 來保護您的 Windows 10 裝置，同時仍保持存取需要本機驗證的內部部署資源。 請遵循下列步驟，以[將已加入網域的 Windows 10 裝置管理，以供商務用 Microsoft 365](manage-windows-devices.md)進行設定。 這個方法是可取的，且此狀態的裝置稱為**混合式 AZURE AD join 裝置**。 
  
如果您保留包含某些內部部署資源（如檔案共用和印表機）的本機 Active Directory，您可以遵循下列步驟，將您的**azure 已加入 azure 裝置**存取這些資源：[從 Microsoft 365 for Business 中的 Azure 已加入 Azure 裝置存取內部部署資源](access-resources.md)。
  
  
## <a name="contact-support"></a>連絡客戶支援

 **如果您需要連絡客戶支援：**
  
- 請與您的合作夥伴連絡。
    
- 做為 Microsoft 365 for business admin，您可以存取我們的客戶支援小組： **[請洽詢商務產品的支援人員-系統管理](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)說明**
    
## <a name="see-also"></a>另請參閱

[商務用 Microsoft 365 檔和資源](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[管理 microsoft 365 for](manage.md)business[遷移至 microsoft 365 for business](migrate-to-microsoft-365-business.md)

[商務用 Microsoft 365 訓練影片](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
