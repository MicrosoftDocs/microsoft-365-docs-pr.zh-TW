---
title: 在多地理位置環境中的使用者體驗
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: 了解 Microsoft 365 多地理位置環境中的 SharePoint、OneDrive 和 Exchange 使用者體驗。
ms.openlocfilehash: 4e752581f4ca692f9fecc5019f8e34543ebf7067
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362375"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>在多地理位置環境中的使用者體驗

以下是您的使用者在 OneDrive 多地理位置組態中會看到的內容：

## <a name="exchange-mailbox"></a>Exchange 信箱

使用者的 Exchange 信箱已佈建到慣用的資料位置，當 PDL 變更時將自動重新配置。 使用者可以正常使用 Outlook 與 Outlook 網頁版，在多地理環境中的使用者體驗沒有任何改變。

## <a name="hub-sites"></a>中樞網站

SharePoint 中樞網站改善了員工對內容的探索和參與，同時建立了完整且一致的專案、部門或區域的表示方式。 在多地理環境中，無論中樞網站的地理位置在哪裡，衛星位置中的網站都能輕鬆與中樞網站建立關聯。 無論網站的地理位置在哪裡，使用者都可以透過單一搜尋，在中樞搜尋並獲得結果。

## <a name="microsoft-365-app-launcher"></a>Microsoft 365 應用程式啟動器

應用程式啟動器具有多地理位置感知功能，可將每個磚定導向工作負載的相應地理位置。 SharePoint 和 OneDrive 磚會將使用者指向對應到使用者佈建之地理位置的位置。 這表示使用者在中央位置有OneDrive，他們的 SharePoint 磚會將他們導向中央位置的 SP 首頁，但他們的群組網站將會佈建到對應其 PDL 的位置。 

## <a name="office-applications"></a>Office 應用程式

Office 的應用程式（如 Word、Excel 及 PowerPoint）會在使用者登入時，自動偵測每位使用者的正確 OneDrive 地理位置。 使用者不需要輸入他們的 OneDrive 或 SharePoint 網站特定地理位置 URL。

## <a name="onedrive-sync-app"></a>OneDrive 同步處理應用程式

OneDrive 同步處理應用程式 (版本17.3.6943.0625 及更新版本，) 會自動偵測使用者正確的 OneDrive 地理位置。 Sync 應用程式支援包括同步處理群組型網站的能力，不論其地理位置為何。 請注意，多地理位置不支援 Groove 同步處理用戶端。 

## <a name="onedrive-location"></a>OneDrive 位置

使用者將在其慣用的資料位置中布建其 OneDrive。 如果使用者流覽至包含不正確地理位置的 OneDrive URL (如先前地理位置) 的書簽，則會自動重新導向適當地理位置的 OneDrive。

## <a name="onedrive-ios-and-android"></a>OneDrive iOS 和 Android 

OneDrive iOS 和 Android 的行動裝置應用程式會顯示您的 OneDrive 檔案及與您共用的檔案 (無論其地理位置為何)。透過 OneDrive 行動裝置應用程式的搜尋會顯示來自所有地理位置的相關結果。請下載這些應用程式的最新版本。

請參閱使用「[在 iOS 上的 OneDrive](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247)」和「[使用適用於 Android 的 OneDrive](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36)」以了解詳細資訊。

## <a name="onedrive-mobile-client"></a>OneDrive 行動用戶端 

OneDrive 行動用戶端具有多地理位置感知功能，可顯示所有地理位置的相關內容和結果。

## <a name="search"></a>Search

每個地理位置都有自己的搜尋索引和搜尋中心。 當使用者搜尋時，會將查詢傳送至所有地理位置，然後合併傳回的結果，然後排列傳回的結果，讓使用者取得統一的結果。 不論其專屬地理位置為何，使用者都能取得來自所有地理位置的結果。 如需詳細資訊，請參閱[設定搜尋 OneDrive 多地理位置](configure-search-for-multi-geo.md)。

支援以下搜尋用戶端：

-   OneDrive

-   Delve

-   SharePoint 首頁

-   搜尋中心

-   使用 SharePoint 搜尋 API 的自訂搜尋應用程式

## <a name="sharepoint-home"></a>SharePoint 首頁 

在 SharePoint 多地理位置您的 SharePoint home 是由使用者在其所在的 OneDrive 位置所決定的位置所主控。 例如，若使用者將 OneDrive 裝載在歐洲衛星位置，則他們的 SharePoint 首頁將從歐洲顯示。 SharePoint 首頁包含使用者的所有相關內容，無論內容的地理位置為何。 

**已追蹤網站、來自網站的新聞、最近使用的網站、最常瀏覽的網站，以及建議的網站**

只要使用者擁有這些元件的權限，都能看到這些內容，不管內容裝載的地理位置為何。 

**精選連結**

系統管理員可以根據每個地理位置，在 SharePoint 首頁中設定 [精選連結]。 這可讓系統管理員在每個區域的 SP 首頁中，提供適合該區域使用者的連結。 

## <a name="sharepoint-mobile-client"></a>SharePoint 行動用戶端 

SharePoint 行動用戶端具有多地理位置感知功能，可顯示所有地理位置的相關內容和結果。

## <a name="sharing"></a>共用

[人員選擇器] 可顯示所有地理位置的所有使用者。 這可讓使用者與相同地理位置的其他使用者共用，或與任何其他租用戶地理位置中的其他使用者共用。 不同地理位置的內容會顯示在使用者 OneDrive 中的 [**與我共用**] 視圖中，不論其所在地理位置為何，都可以使用單一 Sign-On 體驗存取。

## <a name="teams-experience"></a>小組體驗

Teams 是多地理位置服務。 無論使用者的地理位置為何，都會顯示 OneDrive 檔案及最近檢視過的檔案。 所有地理位置的使用者都可以使用 @ 提及功能。

## <a name="user-profiles"></a>使用者設定檔

系統會在使用者地理位置中管理使用者的設定檔資訊。選取使用者時，系統會將您導向至使用者的適當地理位置，您在其中可看到他們完整的設定檔詳細資料。

如果將 Delve 關閉，您會在 SharePoint 中看到傳統設定檔經驗，這並不具備地理位置意識。


