---
title: Exchange Online Protection 概觀
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) 是雲端式的電子郵件篩選服務，它能協助組織抵禦垃圾郵件和惡意軟體，同時也包括預防組織發生訊息原則違規的功能。
ms.openlocfilehash: 2083b71655b1d5bbf30adbb7bfff3229cfb07525
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970489"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概觀

Microsoft Exchange Online Protection (EOP) 是雲端式的電子郵件篩選服務，它能協助組織抵禦垃圾郵件和惡意軟體，同時也包括預防組織發生訊息原則違規的功能。EOP 能簡化訊息環境的管理，減輕維護內部部署硬體和軟體所衍生的繁重負擔。

下列清單說明您可以使用 EOP 來保護郵件的方法：

- **在獨立案例中**：EOP 會為您的內部部署、Exchange 組織，或任何其他內部部署 SMTP 電子郵件解決方案，提供雲端式電子郵件保護。

- **作為 Exchange Online 的一部分**：EOP 是 Exchange Online 和 Office 365 中雲端託管信箱的內建保護。 請參閱[防禦威脅](protect-against-threats.md)，協助您設定 Exchange Online 的功能。

- **在混合式部署中**：EOP 可以設定為保護您的郵件環境，並在您混合使用內部部署及雲端信箱時控制郵件路由傳送。

> [!NOTE]
> 這些 Exchange Online Protection 文章適用於混合式和內部部署環境。

## <a name="how-eop-works"></a>EOP 的運作方式

若要了解 EOP 的運作方式，查看它如何處理傳入電子郵件很有幫助：

![電子郵件流程圖。](../media/GitHubBugs/emailprocessingineop1.png)

傳入郵件最初會通過連線篩選，此篩選會檢查寄件者的信譽，並檢查郵件是否有惡意程式碼。 大部分垃圾郵件都會在此時遭到阻止並由 EOP 刪除。 郵件會繼續通過原則篩選，在此篩選中，會以從範本建立或強制執行的自訂郵件流程規則 (又稱為傳輸規則) 評估郵件。 例如，您可能有一個規則，會在特定寄件者的郵件送達時，傳送通知給管理員。 (如果您有這項功能，資料遺失防護檢查會在此時執行；請參閱 [Exchange Online Protection 服務描述](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。) 接著，郵件會通過內容篩選，在此篩選中，會檢查內容是否有垃圾郵件常見的術語或內容。 經內容篩選認定為垃圾郵件的郵件，可以傳送至使用者的 [垃圾郵件] 資料夾，或者根據您在其他選項 (包括收件匣或自訂資料夾) 中的設定傳送至隔離區。 郵件順利通過這些保護層後，即會傳遞給收件者。

### <a name="eop-datacenters"></a>EOP 資料中心

EOP 會在用於提供最佳可用性的全球資料中心網路上執行。例如，如果資料中心變成無法使用，則會將電子郵件自動路由傳送至其他資料中心，而不會中斷服務。每一個資料中心的伺服器都會代表您接受郵件，在您的組織與網際網路之間提供隔離層，進而減少伺服器上的負載。透過這個高可用性的網路，Microsoft 可以確保電子郵件及時送達您的組織。

EOP 會在資料中心之間執行負載平衡，但只在一個區域內。如果您佈建在一個區域中，則會以該區域的郵件路由來處理您的所有郵件。下列清單顯示 EOP 資料中心的地區郵件路由運作方式：

- 在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。

- 在亞太地區 (APAC)，所有 Exchange Online 信箱都位於 APAC 資料中心，且郵件目前透過 APAC 資料中心傳送供 EOP 篩選。

- 在美洲，所有的 Exchange Online 信箱都位於美國資料中心，除了南美洲是使用位於巴西和智利資料中心，以及加拿大使用位於加拿大資料中心。 所有電子郵件訊息（包括南美洲和加拿大客戶的訊息）都透過本地資料中心路由，以進行 EOP 篩選；隔離的電子郵件會儲存在租用者所在的資料中心。

- 至於政府社群雲端 (GCC)，所有 Exchange Online 信箱都位於美國資料中心，且所有郵件都透過美國資料中心傳送供 EOP 篩選。

## <a name="eop-plans-and-features"></a>EOP 方案和功能

以下是可用的 EOP 訂閱方案：

- **獨立 EOP**：您可以註冊 EOP 以保護內部部署的電子郵件組織。

- **Exchange Online 中的 EOP 功能**：任何包括 Exchange Online (獨立版或 Office 365 一部分) 的訂閱，都會使用 EOP 來保護您的 Exchange Online 信箱。

- **Exchange Enterprise CAL (含服務) **：如果您有內部部署的 Exchange 組織，且您已購買額外的 Exchange Enterprise CAL (含服務) 授權，EOP 會包含在服務中。

如需所有 EOP 訂閱方案之需求、重要限制和功能可用性的相關資訊，請參閱 [Exchange Online Protection 服務描述](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

## <a name="setting-up-eop"></a>設定 EOP

設定 EOP 可以很簡單，對於具有一些符合性規則的小型組織來說，更是如此。不過，如果您的組織是具有多個網域、自訂符合性規則或混合郵件流程的大型組織，則在進行設定時可能需要更加詳盡的規劃及更多的時間。

如果已購買 EOP，請參閱[設定 EOP 服務](set-up-your-eop-service.md)，以確保完成所有必要的 EOP 設定步驟，來保護郵件環境。

## <a name="for-more-information"></a>如需詳細資訊

[EOP 功能](eop-features.md)

[EOP 一般常見問題集](eop-general-faq.md)

[EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.md)

[委派管理常見問題集](delegated-administration-faq.md)

[將網域與設定從某個 EOP 組織移到另一個 EOP 組織](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
