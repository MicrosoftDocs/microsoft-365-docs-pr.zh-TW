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
ms.openlocfilehash: b00de649bf0517d3c5cda99f1c20579ad1dfeec5
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772267"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概觀

Microsoft Exchange Online Protection (EOP) 是雲端式的電子郵件篩選服務，它能協助組織抵禦垃圾郵件和惡意軟體，同時也包括預防組織發生訊息原則違規的功能。EOP 能簡化訊息環境的管理，減輕維護內部部署硬體和軟體所衍生的繁重負擔。

下列清單說明如何使用 EOP 來保護郵件：

- **在獨立案例中**： EOP 的內部部署 Exchange 組織，或任何其他內部部署 smtp 電子郵件解決方案，提供雲端式電子郵件保護。

- **Exchange Online 的一部分**： EOP 是雲端託管信箱在 Exchange Online 和 Office 365 內建的保護。 設定這些 Exchange Online 功能的說明，請參閱[防範威脅](protect-against-threats.md)。

- **在混合式部署**： EOP 可以設定為保護您的郵件環境，並控制郵件路由傳送您混合使用內部部署及雲端信箱時。

> [!NOTE]
> 下列 Exchange Online Protection 文章適用於混合式和內部部署環境。

## <a name="how-eop-works"></a>EOP 的運作方式

若要了解 EOP 的運作方式，查看它如何處理傳入電子郵件很有幫助：

![電子郵件程序圖。](../media/GitHubBugs/emailprocessingineop1.png)

傳入郵件最初會通過連線篩選，此篩選會檢查寄件者的信譽，並檢查郵件是否有惡意程式碼。 大部分垃圾郵件都會在此時遭到阻止並由 EOP 刪除。 郵件會繼續透過原則篩選，針對您建立或強制執行從範本的自訂郵件流程規則 （也稱為傳輸規則） 來評估郵件。 例如，您可能有一個規則，會在特定寄件者的郵件送達時，傳送通知給管理員(如果您具有該功能，此時也會進行資料遺失防護檢查；如需功能可用性的相關資訊，請參閱 Exchange Online Protection 服務說明。 )接著，郵件會通過內容篩選，在此篩選中，會檢查內容是否有垃圾郵件常見的術語或內容。 郵件判定為垃圾郵件內容篩選可傳送至使用者的垃圾郵件資料夾或隔離區，根據您設定其他選項 （包括收件匣或自訂的資料夾） 之間。 郵件順利通過這些保護層級的所有之後，它會傳遞至收件者。

### <a name="eop-datacenters"></a>EOP 資料中心

EOP 會在用於提供最佳可用性的全球資料中心網路上執行。例如，如果資料中心變成無法使用，則會將電子郵件自動路由傳送至其他資料中心，而不會中斷服務。每一個資料中心的伺服器都會代表您接受郵件，在您的組織與網際網路之間提供隔離層，進而減少伺服器上的負載。透過這個高可用性的網路，Microsoft 可以確保電子郵件及時送達您的組織。

EOP 會在資料中心之間執行負載平衡，但只在一個區域內。如果您佈建在一個區域中，則會以該區域的郵件路由來處理您的所有郵件。下列清單顯示 EOP 資料中心的地區郵件路由運作方式：

- 在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。

- 在亞太地區 (APAC)，所有的 Exchange Online 信箱都位於 APAC 資料中心，以及目前會透過 APAC 資料中心，供 EOP 篩選會路由傳送郵件。

- 美洲，所有 Exchange Online 信箱都位於美國資料中心，除了可用的巴西和智利資料中心的南美洲和加拿大可用的加拿大資料中心中。 透過 EOP 篩選; 本機資料中心會路由傳送所有電子郵件，包括南美洲和加拿大客戶的郵件隔離的電子郵件會儲存在租用戶所在的資料中心。

- 至於政府社群雲端 (GCC)，所有 Exchange Online 信箱都位於美國資料中心，且所有郵件都透過美國資料中心傳送供 EOP 篩選。

## <a name="eop-plans-and-features"></a>EOP 方案和功能

可用的 EOP 訂閱計劃包括：

- **獨立式 EOP**： 您註冊 EOP 來保護您的內部部署電子郵件組織中。

- **在 Exchange Online EOP 功能**： 任何包含 Exchange Online 的訂閱 (獨立或 Office 365 的一部分) 使用 EOP 來保護您的 Exchange Online 信箱。

- **Exchange Enterprise CAL with Services**： 如果您有內部部署 Exchange 組織您已購買其他 Exchange Enterprise CAL with Services 授權，EOP 會包含服務的一部分。

如需所有 EOP 訂閱方案之需求、重要限制和功能可用性的相關資訊，請參閱 [Exchange Online Protection 服務描述](https://go.microsoft.com/fwlink/p/?LinkId=320619)。

## <a name="setting-up-eop"></a>設定 EOP

設定 EOP 可以很簡單，對於具有一些符合性規則的小型組織來說，更是如此。不過，如果您的組織是具有多個網域、自訂符合性規則或混合郵件流程的大型組織，則在進行設定時可能需要更加詳盡的規劃及更多的時間。

如果已購買 EOP，請參閱[設定 EOP 服務](set-up-your-eop-service.md)，以確保完成所有必要的 EOP 設定步驟，來保護郵件環境。

## <a name="for-more-information"></a>相關資訊

[EOP 功能](eop-features.md)

[EOP 一般常見問題集](eop-general-faq.md)

[EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.md)

[委派管理常見問題集](delegated-administration-faq.md)

[將網域及設定從某個 EOP 組織移到另一個 EOP 組織](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
