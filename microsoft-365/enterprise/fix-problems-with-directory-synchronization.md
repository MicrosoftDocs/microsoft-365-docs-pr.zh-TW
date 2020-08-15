---
title: 修正 Microsoft 365 的目錄同步處理問題
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: 說明 Office 365 中目錄同步處理問題的常見原因，並提供一些協助疑難排解並解決問題的方法。
ms.openlocfilehash: 80b4a88e91230a8736f209ecd65c58b2882c25d6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688791"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a>修正 Microsoft 365 的目錄同步處理問題

您可以使用目錄同步處理繼續透過內部部署方式管理使用者和群組，以及同步處理雲端的新增、刪除和變更。 但是，安裝程式有些複雜，而且有時很難找出問題來源。 我們有資源可以協助您辨別潛在問題並加以修正。
  
## <a name="how-do-i-know-if-something-is-wrong"></a>要如何知道發生問題了？

發生問題時，Microsoft 365 系統管理中心中的 [DirSync 狀態] 磚會在第一時間表示有問題發生。
  
您也會收到 Microsoft 365 寄送的郵件通知 (會傳送到備用電子郵件與您的系統管理員電子郵件)，指出您的租用戶目前發生目錄同步處理錯誤。 如需詳細資料，請參閱[識別 Microsoft 365 中的目錄同步處理錯誤](identify-directory-synchronization-errors.md)。
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a>如何獲取 Azure Active Directory Connect 工具?

在 [Microsoft 365 系統管理中心](https://admin.microsoft.com)中，瀏覽至 **[使用者]** \> **[作用中使用者]**。 按一下 **[其他]** 功能表 (三個點) 並選取 **[目錄同步處理]**。 
  
請遵循[精靈中的指示](set-up-directory-synchronization.md)以下載 Aure AD Connect。 
  
如果您仍在使用 Azure Active Directory (Azure AD) 同步處理 (DirSync)，請參閱[如何疑難排解 Microsoft 365 中的 Azure Active Directory 同步處理工具安裝和設定精靈錯誤訊息](https://go.microsoft.com/fwlink/p/?LinkId=396717)，以取得安裝同步處理的系統需求、所需的權限及如何疑難排解常見錯誤的相關資訊。 
  
若要從 Azure AD 同步服務更新至 Azure AD Connect，請參閱 [[升級指示]](https://go.microsoft.com/fwlink/p/?LinkId=733240)。
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a>解決 Microsoft 365 中目錄同步處理問題的常見原因

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a>已同步處理的物件並未出現或在線上更新，或從服務收到同步處理錯誤報告。

- [身分識別同步及重複屬性復原](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a>我的系統管理中心出現警示，或收到最近未進行同步處理事件的自動發送電子郵件
- [針對 Azure AD Connect 的連線問題進行疑難排解](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [Azure AD Connect 帳戶和權限](https://go.microsoft.com/fwlink/p/?LinkId=820598)
- [Azure AD Connect 同步：如何管理 Azure AD 服務帳戶](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [Azure Active Directory 目錄同步處理停止，或者系統警告您超過一天未登錄同步處理](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a>密碼雜湊未同步處理，或我在系統管理中心看到最近未進行同步處理密碼雜湊的警示
- [使用 Azure AD Connect 同步處理來實作密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a>我看到超過物件配額的警示
- 我們有內建物件配額可協助保護服務。 如果您的目錄中有太多需要同步處理至 Microsoft 365 的物件，則必須 [連絡商務產品的客戶支援](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)以增加您的配額。

### <a name="i-need-to-know-which-attributes-are-synchronized"></a>我需要知道哪些屬性已同步處理
- 您可以在 [[這裡]](https://go.microsoft.com/fwlink/p/?LinkId=396719) 找到內部部署與雲端之間同步處理的所有屬性清單。

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a>我無法管理或移除已同步處理到雲端的物件
- 您是否準備好僅管理雲端中的物件？ 或者，是否有透過內部部署刪除但卡在雲端中的物件？ 請參閱此 [在同步處理期間進行疑難排解錯誤](https://go.microsoft.com/fwlink/p/?linkid=842044) 和 [支援文章](https://go.microsoft.com/fwlink/p/?LinkId=396720)以獲取解決這些問題的指南。

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a>我收到公司超出可同步處理之物件數目的錯誤訊息
- 如需此問題的詳細資訊，請參閱 [[這裡]](https://go.microsoft.com/fwlink/p/?LinkId=396721)。
   
## <a name="other-resources"></a>其他資源

- [修正使用者主要名稱重複問題的腳本](https://go.microsoft.com/fwlink/p/?LinkId=396725)
    
- [如何準備無法路由傳送的網域 (例如.local 網域) 以用於目錄同步處理](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [計算已同步處理物件之總數的腳本](https://go.microsoft.com/fwlink/p/?LinkId=396726)
    
- [疑難排解 AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [針對已啟用郵件功能的群組，使用 PowerShell 修正空的 DisplayName 屬性](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [使用 PowerShell 修正 UPN 重複的問題](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [使用 PowerShell 修正電子郵件地址重複的問題](https://go.microsoft.com/fwlink/p/?LinkId=396731)
    
