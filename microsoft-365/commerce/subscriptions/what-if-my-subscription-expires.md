---
title: 當訂閱結束時，我的資料與存取權會發生什麼情況？
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: 了解當商務用 Microsoft 365 訂閱到期、停用或取消時，您的資料會發生什麼情況。
ms.openlocfilehash: ee83e237d17dc2de60b08b8d4dbdc46c98fc8251
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615396"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>若要深入了解，請參閱當商務用 Microsoft 365 訂閱結束時，我的資料與存取權會發生什麼情況？

如果您的訂閱結束 (無論是因為到期或是因為您決定取消)，您在訂閱之前對於多種狀態的 Microsoft 365 服務、應用程式和客戶資料的存取權將會完全關閉或「*刪除*」。 如果您知道這個進度，您就更能針對讓您的訂閱回到作用中狀態做好準備，以免為時已晚，或者，如果您要離開 Microsoft 365，請在最終刪除之前備份您的資料。

在您連絡 [Microsoft 365 客戶支援](../../admin/contact-support-for-business-products.md)之前，請仔細閱讀這個重要資訊。
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>訂閱到期時，資料會發生什麼情況？

- 如果您的訂閱到期，它會經歷下列階段：已到期/已停用/已刪除。 「已到期」階段會在訂閱到達結束日期之後立即開始。
- 如果您關閉年度訂閱的週期性計費，它會經歷與已到期的訂閱相同的階段。 第一個階段是從年度訂閱的週年日開始，而不是從您關閉訂閱的週期性計費設定的日期開始。
- 如果您取消每月訂閱，它會立即停用 (取消的日期)。 這表示您的使用者會立即失去 Microsoft 365 資產的存取權，且未來 90 天內只有系統管理員可以存取資料。

下表說明付費的商務用 Microsoft 365 訂閱到期時，會是怎樣的情形。

| 作用中 | 已到期 <br/>(30 天\*) | 已停用 <br/>(90 天\*) | 已刪除 |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *所有人都可以存取資料*                                               | *所有人都可以存取資料*                                                     | *只有系統管理員可以存取資料*                                             | **資料已刪除<br/>Azure Active Directory 已移除，如果沒有其他服務在使用** |
| 使用者可以正常存取 Microsoft 365、檔案和應用程式   | 使用者可以正常存取 Microsoft 365、檔案和應用程式              | 使用者無法存取 Microsoft 365、檔案和應用程式                        | 使用者無法存取 Microsoft 365、檔案和應用程式                                     |
| 系統管理員可以正常存取 Microsoft 365、資料和 Office 應用程式 | 系統管理員可以存取系統管理中心                                           | 系統管理員可以存取系統管理中心，但是無法指派授權給使用者       | 系統管理員可以存取系統管理中心以購買和管理其他訂閱             |
|                                                                        | 全域或計費系統管理員可以在系統管理中心重新啟動訂閱 | 全域或計費系統管理員可以在系統管理中心重新啟動訂閱 |                                                                                           |

*針對大部分國家/地區和區域的供應項目。
  
> [!NOTE]
> **什麼是「客戶資料」？** 客戶資料如同 [Microsoft Online Service 條款](https://go.microsoft.com/fwlink/p/?LinkId=613649)中的定義，指的是所有資料，包括所有文字、聲音或影像檔，由 Microsoft 或代表其提供，或客戶透過使用 Microsoft 365 服務所使用的資料。 若要深入了解客戶資料的保護，請參閱[開始使用 Microsoft 服務信任入口網站](../../compliance/get-started-with-service-trust-portal.md)。

## <a name="what-happens-if-i-cancel-a-subscription"></a>如果我取消訂閱，會發生什麼情況？

如果您在訂閱期間結束日期之前取消訂閱，訂閱會略過「已到期」階段，直接進入「已停用」階段 (對於大部分國家/地區和區域的大部分訂閱是 90 天)。 建議您在取消之前[備份您的資料](back-up-data-before-switching-plans.md)，但是身為系統管理員，在訂閱處於「已停用」階段時，您仍然可以為貴組織存取和備份資料。 您所留下的任何客戶資料在 90 天後可能會遭到刪除，並且會在取消後的 180 天內全部刪除。
  
以下是取消訂閱後，您和您的使用者預期會面臨的狀況。
  
- **系統管理員存取**：系統管理員仍可登入及存取系統管理中心，並視需要購買其他訂閱。 如果您是全域或計費系統管理員，您有 90 天的時間可以[重新啟動訂閱](reactivate-your-subscription.md)，而且所有資料皆保持原封不動。

- **使用者存取**：您的使用者將無法使用服務 (像是商務用 OneDrive) 或是存取客戶資料 (例如小組網站上的電子郵件或文件)。 Word 和 Excel 等 Office 應用程式最後都會進入唯讀、精簡功能模式，並顯示[未授權產品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)。

若要了解如何立即取消訂閱，請參閱[取消您的訂閱](cancel-your-subscription.md)。
  
> [!IMPORTANT]
> 如果您想要在一般的「已停用」階段結束之前刪除您的訂閱資料，可以[關閉帳戶](../close-your-account.md)。
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>我的訂閱即將到期時，我有哪些選擇？

當訂閱為使用中時，您和使用者可以正常存取您的資料、電子郵件、商務用 OneDrive 和 Office 應用程式等服務。 如果您是系統管理員，當您的訂閱接近到期日時，您將會透過電子郵件和系統管理中心收到一系列通知。
  
在訂閱實際到達到期日之前，您可以選擇下列做法：
  
- **為訂閱啟用週期性計費。**

  - 如果 **週期性計費** 已開啟，您不需執行任何動作。 您的訂閱將會自動計費，而您將會根據目前的付款頻率，支付一年或一個月的費用。 如因任何原因關閉 **週期性計費**，您可以隨時 [開啟週期性計費](renew-your-subscription.md)。

  - 如果您是使用預付卡購買 Microsoft 365 Apps 商務版，可以為訂閱[開啟週期性計費](renew-your-subscription.md)。

  - 如果您是預付 1 年期的開放式大量授權客戶，請與您的合作夥伴聯繫，購買新的產品金鑰。 您會透過電子郵件收到指示，以在[大量授權服務中心](https://go.microsoft.com/fwlink/p/?LinkID=282016)啟用您的金鑰。 若要了解如何尋找新的合作夥伴或您過去合作過的合作夥伴，請參閱[尋找您的合作夥伴或經銷商](../../admin/manage/find-your-partner-or-reseller.md)。

  - 如果您有 Microsoft 365 Apps 商務版，請參閱[管理訂閱的週期性計費](renew-your-subscription.md)。

- **任由訂閱到期。**

  - 如果您是使用信用卡或發票付款，而且不想繼續訂閱，請[關閉週期性計費](renew-your-subscription.md)。 您的訂閱會在到期日結束，您可以忽略所有相關的電子郵件通知。

  - 如果您是與合作夥伴合作的 Open 大量授權客戶，不需採取任何動作，任由訂閱到期即可。

  - 如果您是 Microsoft 365 商務標準版客戶，並且採用預付方式，用產品金鑰啟動 Microsoft 365，則不需採取任何動作，任由訂閱到期即可。

- **在訂閱到期之前取消。** 如需詳細資訊，請參閱[取消您的訂閱](cancel-your-subscription.md)。

## <a name="what-happens-after-my-subscription-expires"></a>在訂閱到期之後，會發生什麼情況？

如果您讓訂閱到期，它會在最終刪除之前經歷多個狀態。 如果您是系統管理員，而且想延續訂閱服務的話，您將有時間可以重新啟動訂閱；如果您確定不想再訂閱，也還有時間可以進行資料備份。
  
以下是您在訂閱的每個狀態中所能預期的情況。
  
### <a name="state-expired"></a>狀態：已到期

 **預期狀況：** 在大多數國家/地區和區域中，大部分訂閱 (包括透過 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298) 購買的訂閱) 的「已到期」階段會持續 30 天。 若為大量授權的產品 (Microsoft Open 除外)，「已到期」階段會持續 90 天。

在此狀態下，使用者仍可正常存取 Microsoft 365 入口網站、Office 應用程式，以及電子郵件和 SharePoint Online 等服務。
  
身為系統管理員的您仍然可以存取系統管理中心。 別擔心，全域系統管理員或計費系統管理員可以[重新啟動訂閱](reactivate-your-subscription.md)，並且繼續使用 Microsoft 365。 如果您不要重新啟動，請[備份您的資料](back-up-data-before-switching-plans.md)。
  
### <a name="state-disabled"></a>狀態：已停用

 **預期狀況：** 如果您沒有在「已到期」階段期間重新啟動訂閱，它會進入「已停用」階段。對大部分國家/地區和區域的多數訂閱來說，「已停用」階段會持續 90 天。 若為大量授權產品，「已停用」階段會持續 30 天。

在此狀態中，您的存取權會明顯減少。 您的使用者無法登入，或存取電子郵件或 SharePoint Online 等服務。 Office 應用程式最後都會進入唯讀、精簡功能模式，並顯示[未授權產品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)。 您仍然可以登入系統管理中心，但是無法指派授權給使用者。 您的客戶資料 (包括小組網站上所有的使用者資料、電子郵件和檔案) 僅可供您和其他系統管理員使用。

如果您是全域或計費系統管理員，您可以[重新啟動訂閱](reactivate-your-subscription.md)，並繼續使用 Microsoft 365，而且客戶資料都將保持原封不動。 如果您選擇不重新啟動，請[備份您的資料](back-up-data-before-switching-plans.md)。

### <a name="state-deleted"></a>狀態：已刪除
  
 **預期狀況：** 如果您未在「已到期」或「已停用」階段內重新啟動訂閱，系統就會刪除訂閱。
  
系統管理員和使用者都不能再存取訂閱隨附的服務或 Office 應用程式。 從使用者資料到文件和電子郵件等等的所有客戶資料，都會永久遭到刪除且無法復原。
  
此時您無法重新啟動訂閱。 但是如果您是全域或計費系統管理員，您還是可以存取系統管理中心以管理其他訂閱，或購買您的企業所需的新訂閱。
  
> [!NOTE]
> - 新增與已刪除訂閱相同類型的新訂閱，並不會還原與已刪除訂閱相關聯的資料。
> - 如果 CSP 授權已暫停，則不會有 30 天的「已到期」階段，服務會立即停用。 如果租用戶未新增授權以重新啟動，則資料將會在 90 天之後刪除。

### <a name="what-happens-when-my-trial-ends"></a>試用版結束時，會發生什麼情況？

試用版結束時，您就無法繼續免費使用 Microsoft 365。 此時，您有幾個選項：

- **購買 Microsoft 365。** 試用版到期時，訂閱會進入「已到期」階段，再給您 30 天的時間 (大部分國家/地區和區域的多數試用版) 購買 Microsoft 365。 若要了解將試用版轉換成付費訂閱的方式，請參閱[從免費試用版購買訂閱](../try-or-buy-microsoft-365.md#buy-a-subscription-from-your-free-trial)。

- **延長試用期。** 需要更多時間來評估 Microsoft 365 嗎？ 在某些情況下，您可以[延長試用期](../extend-your-trial.md)。

- **取消試用或讓它到期。** 如果您決定不購買 Microsoft 365，您可以讓試用版到期或[取消](cancel-your-subscription.md)。 備份您想要保留的任何資料。 30 天「已到期」階段之後，您的試用帳戶資訊和資料就會永久清除。

> [!NOTE]
> [Microsoft 原則免責聲明和異動通知](https://go.microsoft.com/fwlink/p/?LinkId=613651)可能隨時更改這個頁面上的資訊。 請定期回到本網站檢閱有無任何資訊變更。

## <a name="related-content"></a>相關內容

[取消您的訂閱](./cancel-your-subscription.md) (文章)\
[續約商務用 Microsoft 365](./renew-your-subscription.md) (文章)\
[重新啟動您的訂閱](./reactivate-your-subscription.md) (文章)