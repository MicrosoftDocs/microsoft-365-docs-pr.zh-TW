---
title: 刪除貴組織中的使用者
f1.keywords:
- NOCSH
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
- SPO_Content
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: 瞭解如何刪除使用者帳戶，以及如何處理使用者的電子郵件和 OneDrive 內容，以及是否要保留產品授權。
ms.openlocfilehash: 81dc71c6734340146e1dd13bcd59696eed5be202
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394348"
---
# <a name="delete-a-user-from-your-organization"></a>刪除貴組織中的使用者
  
**想知道如何刪除您 *自己* 在工作或學校使用的 Microsoft 365 使用者帳戶？請聯繫您工作或學校的技術支援人員，為您執行這些步驟。**

## <a name="before-you-begin"></a>在您開始之前

- 只有 Microsoft 365 具有公司或學校之[全域管理員](about-admin-roles.md)或使用者管理許可權的人員才能刪除使用者帳戶。
- 在永久刪除使用者資料之前，您有 30 天的期限可以[還原](restore-user.md)帳戶。
- 如果您想要保留使用者的 OneDrive 資料，請將其移到不同的位置。 您甚至可以在刪除帳戶後的30天內移動資料。 請參閱[存取及備份離職使用者的資料](get-access-to-and-back-up-a-former-user-s-data.md)。 您不需要移動他們的 SharePoint 檔案；您仍然可以存取這些檔案。
- 如果您想要保留使用者的電子郵件，請在刪除帳戶 **之前** ，將電子郵件移到不同的位置。如果您已刪除帳戶：如果尚未經過 30 天，則您可以還原帳戶、移動電子郵件資料，然後再刪除帳戶。請參閱 [存取及備份離職使用者的資料](get-access-to-and-back-up-a-former-user-s-data.md) (機器翻譯)。
- 如果您的 Enterprise 訂閱如 Office 365 企業版 E3，您可以將已刪除之使用者帳戶的信箱資料，將其變成非使用中的 *信箱*。 To learn more, see [Manage inactive mailboxes in Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>全域管理員：刪除使用者、停止支付其授權，並選擇要如何處理他們的電子郵件和 OneDrive 內容。

如果您是全域系統管理員，當您刪除使用者時，您也可以讓其他使用者存取他們的電子郵件，並選擇要如何處理其 OneDrive 內容。

### <a name="things-to-consider"></a>考慮事項

開始之前，請先考慮您想要如何處理使用者的電子郵件和 OneDrive 內容，以及您是否要保留授權或停止付款。
  
|項目 | 描述 |
|:-----|:-----|
|產品授權  <br/> |您可以從使用者移除授權，並將其從您的訂閱中移除，以停止支付該授權。 如果您選取此選項，則會自動從您的訂閱中移除授權。  <br/><br/> 如果您是透過合作夥伴或大量授權購買，**您就無法移除授權**。 如果您是支付年度計畫，或是您正在計費週期的中央，您將無法在您的承諾完成之前，從訂閱中移除授權。  <br/> |
|OneDrive 內容  <br/> |如果使用者將其檔案儲存為 OneDrive，您可以授予另一個使用者存取這些檔案的許可權。  <br/><br/> 您必須將想要保留的檔案移至 OneDrive 檔設定的保留期間內。 **根據預設，保留期間是30天。** 如果您在刪除使用者之後未移動保留期間內的檔案，則會永久刪除 OneDrive 內容。 若要增加您為已刪除的帳戶 OneDrive 的檔案保留天數，請參閱[設定已刪除使用者的 OneDrive 保留](/onedrive/set-retention)。  <br/><br/> **重要！** 如果刪除的使用者使用個人電腦從 SharePoint 和 OneDrive 下載檔案，您就無法在其電腦上擦除儲存的檔案。 他們將繼續存取所有從 OneDrive 同步處理的檔案。           |
|電子郵件  <br/> | 授與另一個使用者對已刪除使用者之電子郵件的存取權，會將刪除的使用者信箱轉換成共用信箱。 然後新的信箱擁有者可以存取信箱，並監視新的電子郵件。 您也會有下列選項：  <br/>  <br/>變更顯示名稱-建議您變更顯示名稱，以便在作用中 **使用者** 清單中識別共用信箱。  <br/>  開啟自動回復-我們已經為您撰寫了禮貌的自動回復。 您可以將不同的自動回復傳送給組織內的人員，以及組織外的人員。  <br/> <br/> 清除別名-別名是使用者的其他電子郵件地址。 有些組織並未使用它們，否則您不需要在這裡做任何其他事情。 如果使用者確實有別名，我們建議您將其移除，這樣您就可以重複使用這些電子郵件地址。 否則，您無法重複使用這些電子郵件地址，直到已刪除信箱的保留期間已經過去為止。 根據預設，已刪除的信箱可復原30天。 如需詳細資訊，請參閱[刪除或還原 Exchange Online 中的使用者信箱](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)。 <br/> |
|Active Directory  <br/> |如果您的公司使用與 Azure AD 同步處理的 **Active Directory** ，您必須從 Active Directory 中刪除使用者帳戶。 您無法透過 Office 365 執行這個動作。 如需相關指示，請參閱 [刪除使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。  <br/> |

### <a name="get-started"></a>入門

由於引導體驗逐步逐步完成刪除使用者的步驟，以下是如何開始的方式。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

::: moniker-end

::: moniker range="o365-germany"

 1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

::: moniker-end

2. 選取您要刪除的使用者，然後選取 [ **刪除使用者**]。

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>使用者管理：從 Office 365 中刪除一或多個使用者

> [!IMPORTANT]
> 如果您已將使用者的帳戶 [轉換成共用信箱](../email/convert-user-mailbox-to-shared-mailbox.md) ，或已設定該帳戶的電子郵件轉寄功能，請勿刪除使用者帳戶。 這些函數仍然需要該帳戶。 共用信箱不需要授權。 如果您已將帳戶轉換成共用信箱，您可以 [停止支付授權](#stop-paying-for-the-license)。 如果您已設定帳戶的電子郵件轉寄功能，您就無法移除授權。 這樣做會停止電子郵件轉發並停用信箱。
  
::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。  

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

::: moniker-end

2. 選取您要刪除的使用者名稱，然後選取三個點 () 其他動作]，然後選擇 [  **刪除使用者**]。

   雖然您已刪除使用者的帳戶，但 **仍在支付授權**。 請參閱下一個步驟，以停止支付授權。  或者，您可以將授權指派給其他使用者。 它不會自動指派給某人。

### <a name="stop-paying-for-the-license"></a>停止支付授權費用

減少授權數量是一項獨立的步驟，只能由全域系統管理員或計費系統管理員來執行。
  
::: moniker range="o365-worldwide"

1. 在系統管理中心，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[您的產品]</a> 頁面。
::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[您的產品]</a> 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[您的產品]</a> 頁面。
::: moniker-end

2. 在 [ **產品** ] 索引標籤上，選取您要移除授權的訂閱。

3. 在訂閱詳細資料頁面上，選取 **[移除授權]**。

4. 在 [ **移除授權** ] 窗格中的 [ **新數量**] 底下的 [ **授權總數** ] 方塊中，輸入此訂閱所需的授權總數。 例如，如果您有100授權，而且想要移除五個，請輸入95。

5. 選取 [儲存]。

稍後當您執行步驟以將其他人員新增至您的公司時，系統會提示您同時購買授權，只需一個步驟即可！

## <a name="delete-many-users-at-the-same-time"></a>同時刪除多個使用者

請參閱 [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell Cmdlet。

## <a name="fix-issues-with-deleting-a-user"></a>修正刪除使用者的問題

以下是使用者刪除使用者時遇到的最常見問題：
  
- **您會收到錯誤訊息，指出無法刪除使用者行。請稍後再試一次。」** 請仔細檢查帳戶是否已設定電子郵件轉寄功能，或是否已轉換成共用信箱。 這兩種情況都會導致該錯誤。 若帳戶有電子郵件轉寄或已轉換成共用信箱，請勿刪除帳戶。

- **您沒有適當的權限可刪除使用者** 。 只有[Microsoft 365 全域系統管理員或使用者管理管理員](about-admin-roles.md)可以刪除使用者的人員。 這通常需要您的學校或公司提供技術支援。

- **您刪除了某個使用者，但對方的名稱仍在您的全域通訊錄中出現** 。 如果公司使用 Active Directory，就會發生這個問題。 您必須刪除 Active Directory 中的使用者帳戶。 如需相關指示，請參閱 [刪除使用者帳戶。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**您想要從您的電腦刪除 Microsoft 365 嗎？移至 [[取消您的訂閱](../../commerce/subscriptions/cancel-your-subscription.md)]。**

## <a name="related-content"></a>相關內容

[還原使用者](restore-user.md) (文章) \
[永久刪除信箱](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (篇) \
[從 Office 365 (文章移除離職員工](remove-former-employee.md)) \
[將新員工新增至 Office 365](add-new-employee.md) (文章) \
[刪除使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))：如果您的公司使用與 Azure AD 同步處理的 **Active Directory** ，請使用這些指示。 您無法透過 Office 365 執行這個動作。  (篇文章) 