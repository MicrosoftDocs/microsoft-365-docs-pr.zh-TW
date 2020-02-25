---
title: 在 Office 365 中設定標準或已設定目標發行選項
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 了解如何在 Microsoft 365 系統管理中心中設定新的產品與功能更新發行選項。
ms.openlocfilehash: 2d4940003c791e50926eff46aaf6a299e60fb9aa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251613"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a>在 Office 365 中設定標準或已設定目標發行選項

有了 Office 365，您就可以在新的產品更新及功能推出時收到這些更新，而不必每幾年進行所費不貲的更新。您可以管理組織收到這些更新的方式。例如，您可以註冊以在早期取得發行的更新，讓您的組織率先收到更新。您可以指定僅特定人員收到這些更新。或者，您可以維持預設的發行排程，於稍後收到更新。本文說明不同的發行選項，以及您可以如何將它運用於您的組織。
  
> [!IMPORTANT]
> 本文中所描述的 Office 365 更新適用於 Office 365、SharePoint Online 和 Exchange Online。這些不適用於商務用 Skype 及相關服務。這些發行選項是有特定對象，並且是發佈 Office 365 變更的最佳方式，但無法保證永遠適用所有更新。 
  
## <a name="how-it-works---release-validation"></a>發行驗證如何運作

第一次測試及驗證由功能小組進行，然後由整個 Office 365 功能小組進行，後面接著所有 Microsoft 的任何新的版本。 內部測試和驗證之後, 的下一個步驟是**已設定目標發行**（先前稱為初次發行計劃） 選擇加入的客戶。 在每個發行週期，Microsoft 都會收集意見反應，並透過監視關鍵使用計量，進一步驗證品質。 這樣一系列的漸進式驗證，都是為了確保全球發行能夠盡可能完善。 下圖是發行的圖片說明： 
  
![驗證週期版 Office 365](../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
針對重大更新，Office 客戶一開始會由[Microsoft 365 藍圖](https://products.office.com/business/office-365-roadmap)獲得通知。 當更新變得更接近推出，它會傳達透過[Office 365 訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)。

> [!NOTE]
> 您必須透過[系統管理中心](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)存取您的訊息中心 Office 365 或 Azure AD 帳戶。 Office 365 家用版方案的使用者沒有系統管理中心。


## <a name="standard-release"></a>標準發行

這是預設選項： 您和您的使用者收到最新的更新時正在廣泛發行給所有客戶。
  
很好的作法是將大部分使用者在**標準發行**和 IT 專業人員和電源中的使用者來評估新功能，並準備小組**已設定目標發行**至支援商務使用者和主管。 
  
> [!NOTE]
> 如果您從已設定目標發行切換回標準發行，您的使用者可能無法存取尚未到達標準發行的功能。 
  
## <a name="targeted-release"></a>已設定目標發行

使用此選項時，您和您的使用者將成為第一批使用最新更新的人員，並可率先提供意見反應來協助改進產品。您可以選擇讓個人或整個組織率先收到更新。
  
> [!IMPORTANT]
> 較大或較複雜的更新可能需要比其他更新更長的時間，以免對使用者造成負面影養。我們無法保持發行的確切時間表。 
  
### <a name="targeted-release-for-entire-organization"></a>適用於整個組織的已設定目標發行

如果您[在系統管理中心的 [版本] 選項設定](#set-up-the-release-option-in-the-admin-center)此選項，您所有的使用者會收到已設定目標發行 」 體驗。 針對超過 300 個使用者的組織，建議您針對此選項使用測試訂閱。 如需測試訂閱資訊，請連絡您的 Microsoft 連絡人。 
  
### <a name="targeted-release-for-selected-users"></a>適用於已選取使用者的已設定目標發行

如果您[在系統管理中心的 [版本] 選項設定](#set-up-the-release-option-in-the-admin-center)此選項，您可以定義特定使用者，通常是電源，以接收搶先特色與功能。 
  
## <a name="benefits-of-targeted-release"></a>已設定目標發行的優點

已設定目標發行可讓系統管理員、變更管理員，或者任何負責 Office 365 更新的人員為即將到來的變更做好準備，方法是：
  
- 在新的更新發行給組織中的所有使用者之前，對更新進行測試與驗證。
    
- 在更新全球發行之前準備使用者通知與文件。
    
- 針對即將到來的變更準備內部技術支援中心。
    
- 瀏覽合規性與安全性審查。
    
- 使用功能控制項 (如果適用的話) 來控制發行給使用者的更新。
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>在系統管理中心中設定發行選項

您可以依照下列步驟，變更您的組織收到 Office 365 更新的方式。您必須是 Office 365 中的全域系統管理員才能加入。
  
> [!IMPORTANT]
> 以下變更可能需要 24 小時的時間，才能在 Office 365 中生效。如果您在啟用已設定目標發行後選擇退出，使用者可能會無法存取尚未到達排定發行的功能。 
  
1. 在系統管理中心，移至 [**設定** > **設定**，並在 [**組織設定檔**] 索引標籤上，選擇 [**發行喜好設定**。

5. 若要停用已設定目標的發行，請選取 [**標準發行**，然後選取 [**儲存變更**。 
    
6. 若要啟用已設定目標的發行您的組織中的所有使用者，請選取 [**已設定目標發行的所有人**，然後選取 [**儲存變更**。 
    
7. 若要啟用已設定目標的發行的部分人員在組織中，選取**所選使用者的已設定目標發行**，然後選取 [**儲存變更**。 
    
8. 若要新增一位使用者在時間，或將它們新增大量**上傳的使用者**，選擇 [**選取使用者**。
    
9. 當您新增完使用者後，請選取 [**儲存變更**。



## <a name="get-the-targeted-release-version-of-office"></a>取得 Office 已設定目標發行版本

若要安裝 Office 已設定目標發行組建，[請遵循以下步驟](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead)。完成後您就能夠提早使用 Windows 傳統型 Office 2016 新功能。
  
## <a name="learn-more"></a>深入了解

探索如何取得有關即將來臨的 Office 365 更新和發行的通知您[Office 365 訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)中的 [[管理的郵件](https://docs.microsoft.com/office365/admin/manage/message-center)。
