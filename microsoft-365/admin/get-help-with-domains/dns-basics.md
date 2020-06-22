---
title: DNS 基本知識
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: 了解網域及其相關聯的 DNS 記錄，協助您管理網域。
ms.openlocfilehash: 3a3a03c408d480b5d4678fde25c8830e063b1310
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780178"
---
# <a name="dns-basics"></a>DNS 基本知識

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
::: moniker range="o365-worldwide"

網域名稱 (例如 contoso.com) 是由網域註冊機構和資料庫的全球系統管理。 網域名稱系統 (DNS) 可提供人類看得懂的電腦主機名稱與網路設備所使用的 IP 位址之間的對應。 了解 DNS 和網域註冊機構的基本概念有助於管理網域。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

網域名稱 (例如 contoso.com) 是由網域註冊機構和資料庫的全球系統管理。 網域名稱系統 (DNS) 可提供人類看得懂的電腦主機名稱與網路設備所使用的 IP 位址之間的對應。 了解 DNS 和網域註冊機構的基本概念有助於管理 Office 365 中的網域。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

網域名稱 (例如 contoso.com) 是由網域註冊機構和資料庫的全球系統管理。 網域名稱系統 (DNS) 可提供人類看得懂的電腦主機名稱與網路設備所使用的 IP 位址之間的對應。 了解 DNS 和網域註冊機構的基本概念有助於系統管理員管理由 21Vianet 營運的 Office 365 網域。
  
::: moniker-end

## <a name="what-are-domain-names"></a>什麼是網域名稱？

網域名稱是用於 URL 與電子郵件地址，包含不同的層級。 例如，mail.contoso.com 是一個網域名稱，包含下列三個層級：
  
- **.com** 是頂層網域 
    
- **contoso** 是第二層網域 
    
- **mail** 是第三層網域 
    
為什麼要使用第三層網域？ 您可能會想要針對行銷或部落格使用不同的網域名稱。 例如，blog.contoso.com。 您通常會新增第二層網域 (例如 contoso.com) 以搭配 Office 365 使用，但也可以視需要使用第三層網域。
  
若要深入了解如何將網域用於每種類型的產品，請參閱 [Office 365 網域服務說明](https://go.microsoft.com/fwlink/?LinkId=402693)。
  
## <a name="understand-dns-record-types"></a>了解 DNS 記錄類型

儲存在網域 DNS 主機的 DNS 記錄用於指引網域的流量。 下表說明經常使用的 DNS 記錄，以及與 Office 365 搭配的方式。
  
|**NS (名稱伺服器) 記錄**|**可識別做為網域「授權名稱伺服器」的名稱伺服器。當您變更網域的名稱伺服器時，您會變更管理 DNS 記錄的位置，以及 DNS 系統尋找郵件伺服器等相關資訊的位置。Office 365 擁有自己的名稱伺服器，您也可以決定繼續使用已經為您網域設定的名稱伺服器。**|
|:-----|:-----|
|記錄 (位址記錄)  <br/> |建立網域名稱與特定 IP 位址之間的關聯。  <br/> |
|CNAME (別名或正式名稱) 記錄  <br/> |將網域重新導向至 DNS 系統中的另一個網域。 當名稱伺服器尋找某個網域，並發現該網域有 CNAME 記錄時，該伺服器會以 CNAME 取代第一個網域名稱，然後再尋找新名稱。  <br/> |
|MX (郵件交換程式) 記錄  <br/> |指向電子郵件應該傳送的目標位置。 它也具有優先順序欄位，讓您可按照優先順序，將郵件傳送到不同的伺服器。  <br/> |
|SPF (寄件者原則架構) 記錄  <br/> |TXT 記錄，有助於防止電子郵件詐騙和網路釣魚。  <br/> |
|SRV (服務) 記錄  <br/> |商務用 Skype Online 和 Exchange Online 會用來協調 Office 365 服務之間的資訊流程。 例如，必須具備 SRV 記錄才能查看 Outlook Web App 中的目前狀態，以及與其他公司中的人員使用商務用 Skype Online、Skype 或其他立即訊息工具。  <br/> |
|TTL (存留時間)  <br/> |在名稱伺服器開始尋找更新版本前，保留 DNS 記錄的時間長度。  <br/> |
   
## <a name="how-does-dns-work"></a>DNS 如何運作？

透過 Office 365 等雲端服務設定網域的程序包含為網域變更或新增 [DNS 記錄](dns-basics.md)的作業。 由於網際網路是使用 DNS (網域名稱系統) 和網域名稱來傳送或尋找電子郵件及網站等項目，所以這些變更有其必要性。 
  
設定網際網路使用 DNS (或稱網域名稱系統)，可讓我們以熟悉的名稱 (例如 contoso.com) 尋找特定的網際網路位置。在熟悉的名稱背後，這些網際網路位置實際上是以一串難以記憶、名為 IP (網際網路通訊協定) 位址的數字所標示而成。 IP 位址看起來像這樣：70.42.241.42。相較之下，使用網域名稱來識別電子郵件主機和網站等位置就容易多了。
  
簡而言之：DNS 記錄會告訴網際網路傳送電子郵件的位置 (例如 joe@contoso.com)，或尋找使用您的網域名稱的網站 (例如 www.contoso.com)。 當您將適當的資訊儲存到正確的網域 DNS 記錄中時，DNS 系統會正確路由所有內容，例如，您的電子郵件會傳送至 Office 365，而不是其他地方。
  
網域的 DNS 記錄在其他用途上也非常有用。 例如 Exchange 會檢查 DNS 記錄，讓 Outlook 自動設定連線至正確的 Exchange 伺服器。
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS 記錄可協助網際網路將電子郵件傳送到正確的地方

如前述，DNS 主要是在引導網際網路流量，將好記的網域名稱對應到那些難記的 IP 位址上。 稱為 MX 記錄的 DNS 記錄專門將電子郵件傳送到正確的主機。 
  
DNS 記錄如同網域相關資訊的資料庫。 該記錄及其值會儲存在區域檔案中，其中包含網域的每一筆記錄清單及其值。 網域註冊機構和其他 DNS 主機服務公司會在其網站上提供使用者介面，以便讓您編輯網域區域檔案中的記錄。 您可以在該介面更新網域的 MX 記錄，以將電子郵件傳送到 Office 365。
  
 *當您將電子郵件變更至 Office 365 時，透過在下一步更新您的網域 MX 記錄，所有傳送至該網域的電子郵件都會開始送往 Office 365。*  如果其他人使用您的網域傳送電子郵件，您必須為這些人個別設定 Office 365 信箱。 
  
聽起來很複雜嗎？ 確實，但我們會逐步引導您完成 Office 365 的網域設定。
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS 也會告訴網際網路到哪裡尋找網站

輸入網址 (例如 www.contoso.com) 時，網際網路會先檢查其中一個 DNS 伺服器，尋找用於 (在本案例中) contoso.com 的名稱伺服器 (NS) 記錄。 NS 記錄會告訴網際網路應在何處尋找具有所有該網域的其他 DNS 記錄值的區域檔案。 有許多彼此連線的 DNS 伺服器。 伺服器共同追蹤所有已註冊的網域名稱，這些網域名稱必須是唯一的，而且是網域區域檔案的所在位置。
  
::: moniker range="o365-worldwide"

假設 contoso.com 的 NS 記錄為「godaddy.com」。 現在，網際網路知道 GoDaddy.com 是尋找區域檔案的位置，區域檔案列出 contoso.com 的所有其他 DNS 記錄。 這些 DNS 記錄包含 MX 記錄，顯示傳送 contoso.com 電子郵件和其他記錄的位置。 如果 MX 記錄具有值「send email to Office 365」(但以技術詞彙描述)，表示所有傳送到 contoso.com 電子郵件地址 (例如 joe@contoso.com) 的電子郵件將傳送到該處。 然後，只要該位置有一個名為「joe」的信箱，便會傳遞電子郵件。

::: moniker-end

::: moniker range="o365-germany"

假設 contoso.com 的 NS 記錄為「godaddy.com」。 現在，網際網路知道 GoDaddy.com 是尋找區域檔案的位置，區域檔案列出 contoso.com 的所有其他 DNS 記錄。 這些 DNS 記錄包含 MX 記錄，顯示傳送 contoso.com 電子郵件和其他記錄的位置。 如果 MX 記錄具有值「send email to Office 365」(但以技術詞彙描述)，表示所有傳送到 contoso.com 電子郵件地址 (例如 joe@contoso.com) 的電子郵件將傳送到該處。 然後，只要該位置有一個名為「joe」的信箱，便會傳遞電子郵件。

::: moniker-end

::: moniker range="o365-21vianet"

假設 contoso.com 的 NS 記錄為「hichina.com」。 現在，網際網路知道 hichina.com 是尋找區域檔案的位置，區域檔案列出 contoso.com 的所有其他 DNS 記錄。 這些 DNS 記錄包含 MX 記錄，顯示傳送 contoso.com 電子郵件和其他記錄的位置。 如果 MX 記錄具有值「send email to Office 365」(但以技術詞彙描述)，表示所有傳送到 contoso.com 電子郵件地址 (例如 joe@contoso.com) 的電子郵件將傳送到該處。 然後，只要該位置有一個名為「joe」的信箱，便會傳遞電子郵件。

::: moniker-end

當您在網域設定步驟中設定網域時，系統會列出您必須輸入才能使用 Office 365 的實際值。 若要手動設定，請將值複製並貼到 DNS 主機上的正確 DNS 記錄 (MX 記錄、CNAME 記錄等)，這可能是網域註冊機構，但不一定。
  
::: moniker range="o365-worldwide"

為什麼區域檔案可能位於網域註冊機構以外的其他位置？ 您可能會在網域註冊機構 (例如 GoDaddy) 註冊您的網域名稱，但您的 DNS 記錄可能是由其他 DNS 主機服務公司或虛擬主機公司管理。 網域的 NS 記錄會儲存該資訊，讓所有 DNS 伺服器知道尋找的位置。

::: moniker-end

::: moniker range="o365-germany"

為什麼區域檔案可能位於網域註冊機構以外的其他位置？ 您可能會在網域註冊機構 (例如 GoDaddy) 註冊您的網域名稱，但您的 DNS 記錄可能是由其他 DNS 主機服務公司或虛擬主機公司管理。 網域的 NS 記錄會儲存該資訊，讓所有 DNS 伺服器知道尋找的位置。

::: moniker-end

::: moniker range="o365-21vianet"

為什麼區域檔案可能位於網域註冊機構以外的其他位置？ 您可能會在網域註冊機構 (例如 HiChina) 註冊您的網域名稱，但您的 DNS 記錄可能是由其他 DNS 主機服務公司或虛擬主機公司管理。 網域的 NS 記錄會儲存該資訊，讓所有 DNS 伺服器知道尋找的位置。

::: moniker-end

> [!NOTE]
> 如果您要在 Office 365 設定網域，讓 [Microsoft 為您設定及管理 DNS 記錄](../setup/domains-faq.md#how-does-office-365-manage-my-dns-records)，則在設定過程中，您得[將 DNS 管理變更為 Office 365](../setup/domains-faq.md#change-dns-management-to-office-365)。 
 

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-office-365"></a>為什麼要在 Office 365 中新增網域？


將自訂網域 (例如 fourthcoffee.com) 新增至 Office 365 可讓您使用更簡短、更熟悉的電子郵件地址和該服務的 userID。 註冊 Office 365 帳戶時，將會[提供一個網域供您使用](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)，但包括「onmicrosoft.com」。 如果計劃將 Office 365 用於電子郵件，許多人偏好新增組織或商務網域。 
  
> [!NOTE]
> 如果您只是要下載並使用 Microsoft App (例如 Outlook 或 Word)，則無需新增網域：[在您的 PC 或 Mac 上安裝 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。 
  
您可以在 Office 365 中將網域名稱用於電子郵件、公用網站及立即訊息位址。
  
- **電子郵件：** 您的網域名稱可讓您自訂電子郵件，因此您可以使用更簡短且易記的地址，而不是帳戶隨附的[初始 onmicrosoft.com 電子郵件地址](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。 因此電子郵件地址 (也是用於登入 Office 365 的公司帳戶) 可能是 joe@contoso.com，而不是 joe@contoso.onmicrosoft.com。 
    
- **網站：** 如果您的 Microsoft 365 訂閱包含 SharePoint Online 公用網站 (已不再提供購買)，您的公用網站會隨附像 contoso-public.sharepoint.com 這樣的初始位址。 如果您是為企業設定網站，您可以使用自訂網域名稱，將網站位址重新命名為類似 www.contoso.com 這樣的位址。 
    
- **立即訊息：** 您也可以將商務用 Skype Online 位址自訂為使用您的網域名稱，讓組織內部人員使用更簡短易記的位址 (例如 joe@contoso.com)，在商務用 Skype Online 上彼此聯繫。 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-office-365"></a>為什麼要在 Office 365 中新增網域？


將自訂網域 (例如 fourthcoffee.com) 新增至 Office 365 可讓您使用更簡短、更熟悉的電子郵件地址和該服務的 userID。 註冊 Office 365 帳戶時，將會[提供一個網域供您使用](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)，但包括「onmicrosoft.com」。 如果計劃將 Office 365 用於電子郵件，許多人偏好新增組織或商務網域。 
  
> [!NOTE]
> 如果您只是要下載並使用 Office 365 App (例如 Outlook 或 Word)，則無需新增網域：[在您的 PC 或 Mac 上安裝 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。 
  
您可以在 Office 365 中將網域名稱用於電子郵件、公用網站及立即訊息位址。
  
- **電子郵件：** 您的網域名稱可讓您自訂電子郵件，因此您可以使用更簡短且易記的地址，而不是帳戶隨附的[初始 onmicrosoft.com 電子郵件地址](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。 因此電子郵件地址 (也是用於登入 Office 365 的公司帳戶) 可能是 joe@contoso.com，而不是 joe@contoso.onmicrosoft.com。 
    
- **網站：** 如果您的訂閱包含 SharePoint Online 公用網站 (已不再提供購買)，您的公用網站會隨附像 contoso-public.sharepoint.com 這樣的初始位址。 如果您是為企業設定網站，您可以使用自訂網域名稱，將網站位址重新命名為類似 www.contoso.com 這樣的位址。 
    
- **立即訊息：** 您也可以將商務用 Skype Online 位址自訂為使用您的網域名稱，讓組織內部人員使用更簡短易記的位址 (例如 joe@contoso.com)，在商務用 Skype Online 上彼此聯繫。 
    
::: moniker-end

## <a name="the-dns-records-required-for-office-365"></a>Office 365 所需的 DNS 記錄

Office 365 需要具備數種 DNS 記錄才能搭配您的網域使用。 除了設定網域的 MX 記錄，讓電子郵件傳送到 Office 365 之外，還有其他記錄可以協助您處理任務，像是確認 Outlook 可以自動連線到正確的 Exchange 伺服器、設定立即訊息，以及協助防堵垃圾郵件等。
  
您可以[尋找值清單](information-for-dns-records.md)設定您的網域。 這些都包含在 Microsoft 365 系統管理中心。 
  
或者，如果您正在規劃部署，建議您檢閱 Office 365 所需的所有 DNS 記錄清單、DNS 記錄的作用與範例值。 請參閱 [Office 365 的外部網域名稱系統記錄](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)。
  
## <a name="how-can-i-learn-more"></a>如何深入了解？

請參閱下列其中一項： 
  
- 不確定網域的註冊位置？ [協助您找到網域註冊機構。](find-your-domain-registrar.md)
    
- 了解[為什麼您必須完成精靈中的步驟](../setup/add-domain.md)才能搭配 Office 365 使用您的網域。 
    

