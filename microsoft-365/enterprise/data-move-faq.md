---
title: 資料移動一般常見問題集
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: 尋找常見問題解答 (FAQs) 將核心資料移至新的 Office 365 datacenter geo。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e66c9f29b47c3f1bc8d6e89ebf2f077eee9f4adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919125"
---
# <a name="data-move-general-faq"></a>資料移動一般常見問題集

以下是有關如何將核心客戶資料移至新的資料中心地理位置的一般問題的解答。
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>哪些客戶適合要求移動？
  
選取符合新資料中心地理位置之國家/地區的現有 Microsoft 365 商業客戶將可以要求移動。 此程式僅適用于具有合格國家/地區代碼的承租人指派給 Microsoft 365 租使用者，以便將適用工作負載的核心客戶資料移轉至對應的 Microsoft 365 資料中心地理位置。 請參閱 how [to 要求資料移動](request-your-data-move.md) 頁面以確認國家資格。   

## <a name="how-do-we-define-core-customer-data"></a>如何定義核心客戶資料？
 
核心客戶資料是指在 [Microsoft Online Services 條款](https://aka.ms/ost)中所定義之客戶資料的子集的字詞： 
- Exchange Online 信箱內容 (電子郵件內文、行事曆專案和電子郵件附件的內容) 
- SharePoint 線上網站內容和儲存在該網站中的檔案
- 上傳至商務 OneDrive 的檔案 

## <a name="what-is-in-scope-for-teams-migration"></a>團隊遷移的範圍為何？

除了 Exchange Online、SharePoint 線上和商務 OneDrive;Microsoft 會將小組資料移轉至本機資料中心。 
- 小組會聊天訊息，包括私人郵件和通道訊息。 
- 在聊天中使用的小組圖像。 

小組檔案會儲存在 SharePoint 線上中，小組聊天檔會儲存在商務 OneDrive 中。 語音信箱、行事曆和連絡人會儲存在 Exchange Online 中。 在許多情況下，Exchange Online、SharePoint 線上和商務 OneDrive 已由本地資料中心地理位置的客戶使用，而且也是適用于合格客戶國家/地區的 Microsoft 365 遷移計畫的一部分。

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>在我的遷移完成時，我的租使用者核心客戶資料已存放在我的新地理位置中？

由於 Exchange Online 與 SharePoint 線上/OneDrive 間的共用相依性，在遷移這兩項服務之前，無法將任何遷移視為已完成。 Exchange Online 和 SharePoint 線上/OneDrive，通常會以不同的時間進行遷移，並彼此獨立地進行遷移。 客戶租使用者系統管理員會在每次服務遷移完成時于訊息中心接收確認，而且可以隨時查看系統管理中心的資料位置卡，以確認每個服務的 rest 位置的核心客戶資料。

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>如何在移動期間保證客戶資料是安全的，而且不會發生停機時間？
  
資料移動是後端服務作業，對使用者的影響最小。 在 [資料移動期間和之後，](during-and-after-your-data-move.md)會列出受影響的功能。 我們遵循 [Microsoft Online Services 服務等級協定 (SLA) ](https://go.microsoft.com/fwlink/p/?LinkId=523897) 以取得可用性，讓客戶無需準備或在移動期間進行監視。 
  
所有 Microsoft 365 服務都會在資料中心內執行相同的版本，因此您可以保證一致的功能。 整個程式都完全支援您的服務。
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>不同的服務位於不同的 geos 會有什麼影響？

有些 Microsoft 365 服務可能位於不同的 geos 中，供一些現有的客戶及在移動程式中間的客戶。 我們的服務彼此獨立執行，且在這種情況下不會影響使用者的體驗。 不過，針對資料派駐服務的目的，在 Exchange Online 和 SharePoint 商務線上/OneDrive 皆遷移至相同的資料中心地理位置之前，無法將租使用者遷移視為完整。

 ## <a name="where-is-my-core-customer-data-located"></a>我的核心客戶資料位於何處？

客戶租使用者系統管理員可以隨時查看系統管理中心的資料位置卡，以確認每個服務（特別是針對其租使用者）的核心客戶資料。  我們也會將 [Microsoft 365 互動式資料中心 ](https://office.com/datamaps) 的資料中心 geos、資料中心和365位置的位置發佈，作為新承租人的目前預設核心客戶資料的參考。 您可以透過 Microsoft 365 系統管理中心中組織設定檔底下的 [資料位置] 區段，確認您的客戶資料在 rest 上的位置。  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>何時可以要求移動？
  
請參閱 [如何要求資料移動](request-your-data-move.md) 頁面以取得資料中心地理位置支援的時段。
  
## <a name="how-can-i-request-to-be-moved"></a>我可以要求移動的要求為何？
  
合格的客戶將會在其 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)看到一頁。 請參閱 how [to 要求資料移動](request-your-data-move.md) 以取得如何要求移動的指示。 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>在要求移動之後，是否可以變更我的選取專案？
  
在您提交要求之後，我們無法將您的程式移除。
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>如果我不要求在期限之前移動，會發生什麼事？
  
在開啟的登記週期過後，我們無法接受進行遷移的要求。

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>如果我想要移動資料以取得更好的網路效能，該怎麼辦？
  
與 Microsoft 365 資料中心的實體接近，不會保證更好的網路效能。 有許多因素和元件會影響使用者與 Microsoft 365 服務之間的網路效能。 如需此和效能調整的詳細資訊，請參閱 [Microsoft 365 的網路規劃和效能調整](network-planning-and-performance.md)。
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>所有服務是否會將其資料在同一天內移動？
 
每個服務都會獨立移動，而且可能會在不同的時間移動其資料。
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>我是否可以選擇何時移動資料？
 
客戶無法選取特定日期、不能延遲其移動，而且無法共用移動的特定日期或時間範圍。
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>您可以在移動資料的時候進行共用嗎？
  
資料移動是後端作業，對使用者的影響最小。 複雜性、精確度及規模，我們需要在全域運作及自動環境中執行資料移動，禁止當您的租使用者或任何其他單一租使用者完成資料移動時，無法進行共用。 當客戶的資料移動完成時，客戶會在訊息中心接收一次確認。 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>如果使用者在資料移動時存取服務，會發生什麼事？

在 [資料移動期間和之後](during-and-after-your-data-move.md) ，請參閱資料移動的完整清單可能會限制，以供每個服務的資料移動部分使用。 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>如何知道移動已完成？
  
觀賞 Microsoft 365 訊息中心，以確認每個服務資料的移動是否已完成。 當每個服務的資料移動時，我們會發佈一個完成通知，讓您可以取得三個完成通知：一個適用于 Exchange Online、SharePoint 線上和商務用 Skype Online。 您也可以透過 Microsoft 365 系統管理中心中組織設定檔底下的 [資料位置] 區段，確認 rest 上的客戶資料的位置。  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>我是在其中一個新的資料中心 geos 中的 Microsoft 365 客戶，但是當我註冊時，我選取不同的國家/地區。 我可以如何移至新的資料中心地理位置？

您不可能變更與租使用者相關聯的註冊國家/地區。 相反地，您必須使用新的訂閱建立新的 Microsoft 365 租使用者，並將使用者和資料手動移至新的租使用者。
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>在 Exchange Online 移動期間，如果我們正在將電子郵件資料移轉至 Microsoft 365，會發生什麼情況？

這是一種非常常見的案例，而且受到完全支援。  資料中心 geos 之間的雲端遷移不會干擾任何內部部署至雲端信箱遷移。
  
 ## <a name="can-i-pilot-some-users"></a>我可以試驗部分使用者嗎？
  
您可以建立個別的試用租使用者來測試連線能力，但試用租使用者無法以任何方式結合現有的租使用者。

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>我不想要等候 Microsoft 移動我的資料。 我是否可以只建立新租使用者並自行移動？
  
是的，不過處理常式不會像 Microsoft 執行資料移動一樣順利。
  
如果您在新的資料中心地理位置之後建立新租使用者，則新的租使用者將會主控于新的 geo 中。 這個新租使用者完全不同于您先前的承租人，您會負責移動所有使用者信箱、網站內容、功能變數名稱及其他任何資料。 請注意，您無法將租使用者名稱從一個承租人移至另一個承租人。 建議您等候 Microsoft 所提供的移動程式，因為我們會為您移動使用者的所有設定、資料和訂閱。
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>我的客戶資料已經移至新的資料中心地理位置。 我可以再移回來嗎？
 
否，這是不可能的。 移至新 geo 資料中心的客戶無法移回。 身為任何地理位置的客戶，您會體驗到相同品質的服務、效能及安全性控制。 [Microsoft 365 多地理](https://aka.ms/multi-geo) 位置可供部分客戶做為附加元件，並可讓單一租使用者建立多個衛星 geos，並將使用者資料移至具有資料派駐承諾的 geos。
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>位於新資料中心的 Microsoft 365 租使用者是否可供全國以外的使用者使用？
  
是。 Microsoft 會在世界各地的35國家/地區內，以超過130個位置的 Internet 服務提供者（ (Isp) 中的對2700等合約來維護具有相關合約的大型全域網路。 使用者將能夠從網際網路上的任何地方存取資料中心。

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>我的承租人已設定 [多地理位置附加](https://aka.ms/multi-geo)元件。 我是否可以在 Microsoft 365 移動程式中註冊我的租使用者，以變更我的預設地理位置，並將不在附屬區域中的任何使用者移至新的預設地理位置？

是的，您的承租人可供註冊，但由於已設定多地理位置之客戶的承租人層級移動不完全支援，因此會有重要考慮。

SharePoint 線上和 OneDrive 商務用，無法透過此程式在租使用者層級遷移至新的資料中心地理位置。 客戶管理員可以設定商務用 OneDrive，將其移至任何使用多地理位置的可用區域，但在已為租使用者設定多地理位置之後，便無法變更租使用者的預設位置。

針對加入宣告遷移的客戶，我們會將您目前的預設地理位置的所有 Exchange Online 信箱移至新的本機資料中心地理位置，並更新預設的 Exchange Online 區域。 我們不會移動在多地理位置衛星區域中設定的任何 EXO 信箱，繼續依照預定的方式，繼續遵循衛星區域資料派駐服務。 

## <a name="related-topics"></a>相關主題

[將核心資料移至新的 Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md)

[如何要求資料移動](request-your-data-move.md)

[Microsoft 365 多地理位置](https://aka.ms/multi-geo)

[Microsoft 365 互動式 datacenter 地圖](https://office.com/datamaps)

[Microsoft 365 支援](../admin/contact-support-for-business-products.md)

[Microsoft Dynamics CRM Online 的新 datacenter geos](/power-platform/admin/new-datacenter-regions)
  
[依地區的 Azure 服務](https://azure.microsoft.com/regions/)