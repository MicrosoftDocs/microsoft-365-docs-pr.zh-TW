---
title: 設定標準或目標發行選項
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 瞭解如何在 Microsoft 365 系統管理中心中設定新產品及功能更新的發行選項。
ms.openlocfilehash: ba9c3a71807728e18b612f0b63aff80d04a46a90
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392524"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>設定標準或目標發行選項

> [!IMPORTANT]
> 本文所述的 Microsoft 365 更新適用于 Microsoft 365、SharePoint 線上及 Exchange Online。 這些版本選項的目標是針對 Microsoft 365 發佈變更的最佳方式，但在任何時間或所有更新皆無法保證。 不適用於 Microsoft 365 Apps、商務用 Skype、Microsoft Teams 和相關的服務。 如需 Microsoft 365 Apps 之版本選項的詳細資訊，請參閱[Microsoft 365 Apps 的更新通道](/deployoffice/overview-update-channels)。

透過 Microsoft 365，您會在新的產品更新和功能可供使用時立即收到，而不是每隔幾年執行昂貴的更新。 您可以管理組織收到這些更新的方式。 例如，您可以註冊以在早期取得發行的更新，讓您的組織率先收到更新。 您可以指定僅特定人員收到這些更新。 或者，您可以維持預設的發行排程，於稍後收到更新。 本文說明不同的發行選項，以及您可以如何將它們用於您的組織。

## <a name="how-it-works---release-validation"></a>發行驗證如何運作

任何新的版本都會先由功能小組進行測試及驗證，然後由整個 Microsoft 365 的功能小組進行測試，接著所有的 Microsoft。 在內部測試及驗證之後，下一步是 **目標發行** (（先前稱為「初次發行」) 客戶加入宣告）。 在每個發行週期，Microsoft 都會收集意見反應，並透過監視關鍵使用計量，進一步驗證品質。 這樣一系列的漸進式驗證，都是為了確保全球發行能夠盡可能完善。 下圖是發行的圖片說明： 
  
![Microsoft 365 的版本驗證振鈴](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
對於重要的更新，客戶最初會收到[Microsoft 365 藍圖](https://products.office.com/business/office-365-roadmap)。 當更新變得更接近時，它會透過您的[Microsoft 365 訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)進行傳遞。

> [!NOTE]
> 您需要 Microsoft 365 或 Azure AD 帳戶，才能透過系統[管理中心](/office365/admin/admin-overview/about-the-admin-center)存取您的郵件中心。 Microsoft 365 家用方案使用者沒有系統管理中心。


## <a name="standard-release"></a>標準發行

這是預設選項，當您和您的使用者廣泛發佈給所有客戶時，您就會收到最新的更新。
  
好的做法是讓大部分的使用者都是在 **標準發行** 中，也可以讓 IT 專業人員和超級使用者在 **目標版本** 中，評估新功能，並準備小組以支援商務使用者和主管人員。 
  
> [!NOTE]
> 如果您從已設定目標發行切換回標準發行，您的使用者可能無法存取尚未到達標準發行的功能。 
  
## <a name="targeted-release"></a>已設定目標發行

使用此選項時，您和您的使用者將成為第一批使用最新更新的人員，並可率先提供意見反應來協助改進產品。您可以選擇讓個人或整個組織率先收到更新。
  
> [!IMPORTANT]
> 較大或較複雜的更新可能需要比其他更新更長的時間，以免對使用者造成負面影養。我們無法保持發行的確切時間表。 
  
### <a name="targeted-release-for-entire-organization"></a>適用於整個組織的已設定目標發行

如果您為此選項 [設定系統管理中心的 [發行] 選項](#set-up-the-release-option-in-the-admin-center) ，所有的使用者都將取得目標的發行體驗。 針對超過 300 個使用者的組織，建議您針對此選項使用測試訂閱。 如需測試訂閱資訊，請連絡您的 Microsoft 連絡人。 
  
### <a name="targeted-release-for-selected-users"></a>適用於已選取使用者的已設定目標發行

如果您為此選項 [設定系統管理中心的 [發行] 選項](#set-up-the-release-option-in-the-admin-center) ，您可以定義特定使用者（通常為 [超級使用者]）以接收可及早存取功能。 
  
## <a name="benefits-of-targeted-release"></a>已設定目標發行的優點

目標版本可讓系統管理員、變更管理員或其他人負責 Microsoft 365 更新，以準備即將進行的變更，其方式如下：
  
- 在新的更新發行給組織中的所有使用者之前，對更新進行測試與驗證。
    
- 在更新全球發行之前準備使用者通知與文件。
    
- 針對即將到來的變更準備內部技術支援中心。
    
- 瀏覽合規性與安全性審查。
    
- 使用功能控制項 (如果適用的話) 來控制發行給使用者的更新。
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>設定系統管理中心的 [發行] 選項

您可以遵循下列步驟，變更組織接收 Microsoft 365 更新的方式。 您必須是全域系統管理員，才能 Microsoft 365 自願加入。
  
> [!IMPORTANT]
> 最多可能需要24小時的時間，變更才會在 Microsoft 365 中生效。 如果您在啟用已設定目標發行後選擇退出，使用者可能會無法存取尚未到達排定發行的功能。 
  
1. 在系統管理中心中，移至 [**設定**  >  **Org 設定**]，然後在 [**組織設定檔**] 索引標籤下，選擇 [**發行喜好** 設定]。

5. 若要停用目標版本，請選取 [ **標準版本**]，然後選取 [ **儲存變更**]。 
    
6. 若要為組織中的所有使用者啟用目標版本，請為 [所有人] 選取 [ **目標版本**]，然後選取 [ **儲存變更**]。 
    
7. 若要為組織中的某些人員啟用目標版本，請選取 [ **目標的版本] 選取的使用者**，然後選取 [ **儲存變更**]。 
    
8. 選擇 [**選取使用者**]，一次新增一個使用者，或 **Upload 使用者** 成批新增。
    
9. 當您新增使用者後，請選取 [ **儲存變更**]。
  
## <a name="next-steps"></a>後續步驟

探索如何在[Microsoft 365 訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)[管理郵件](/office365/admin/manage/message-center)，以取得即將推出 Microsoft 365 更新及發行的通知。

## <a name="related-content"></a>相關內容

[加入 Office 的內幕程式](https://insider.office.com/join/windows) (文章) 
