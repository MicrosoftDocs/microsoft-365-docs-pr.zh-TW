---
title: Exchange Online Protection （EOP）概述
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: 瞭解 Exchange Online Protection （EOP）如何在獨立和混合環境中協助保護您的內部部署電子郵件組織。
ms.openlocfilehash: a3f71ea5366224465cdaf3922c6c467fcb49f3cc
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616983"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概觀

Exchange Online Protection （EOP）是雲端架構篩選服務，可協助您的組織抵禦垃圾郵件和惡意程式碼。 EOP 包含 Exchange Online 信箱的所有 Microsoft 365 組織。

不過，下列內部部署案例也提供 EOP：

- **在獨立案例中**：EOP 會為您的內部部署、Exchange 組織，或任何其他內部部署 SMTP 電子郵件解決方案，提供雲端式電子郵件保護。

- **在混合式部署中**：當您混合使用內部部署和雲端信箱時，可以設定 EOP 來保護您的電子郵件環境，並控制郵件路由傳送。

在這些案例中，EOP 可以簡化電子郵件環境的管理，並減輕維護內部部署硬體和軟體帶來的許多負擔。

本主題的其餘部分將說明 EOP 在獨立和混合環境中的運作方式。

## <a name="how-eop-works"></a>EOP 的運作方式

若要了解 EOP 的運作方式，查看它如何處理傳入電子郵件很有幫助：

![電子郵件處理圖表](../../media/emailprocessingineop1.png)

- 傳入郵件最初會通過連線篩選，此篩選會檢查寄件者的信譽，並檢查郵件是否有惡意程式碼。 大部分垃圾郵件都會在此時遭到阻止並由 EOP 刪除。 如需詳細資訊，請參閱[設定連線篩選](configure-the-connection-filter-policy.md)。

- 郵件會繼續通過原則篩選，在此篩選中，會以從範本建立或強制執行的自訂郵件流程規則 (又稱為傳輸規則) 評估郵件。 例如，您可能有一個規則，會在特定寄件者的郵件送達時，傳送通知給管理員。 資料遺失防護（DLP）檢查也會在此點發生（Exchange Enterprise CAL with Services）。

- 接下來，郵件會透過反垃圾郵件篩選（也稱為「內容篩選」）傳遞。 決定是垃圾郵件的郵件，可以傳送至使用者的 [垃圾郵件] 資料夾或隔離區，以及其他選項。 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

- 郵件順利通過這些保護層後，即會傳遞給收件者。

如需詳細資訊，請參閱[電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。

### <a name="eop-datacenters"></a>EOP 資料中心

EOP 會在用於提供最佳可用性的全球資料中心網路上執行。 例如，如果資料中心變成無法使用，則會將電子郵件自動路由傳送至其他資料中心，而不會中斷服務。 每個資料中心的伺服器都會以您的名義接收郵件，提供組織和網際網路之間的分隔區，從而減少伺服器的負載。 透過這個高可用性的網路，Microsoft 可以確保電子郵件及時送達您的組織。

EOP 會在資料中心之間執行負載平衡，但只在一個區域內。如果您佈建在一個區域中，則會以該區域的郵件路由來處理您的所有郵件。下列清單顯示 EOP 資料中心的地區郵件路由運作方式：

- 在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。

- 在亞太地區 (APAC)，所有 Exchange Online 信箱都位於 APAC 資料中心，且郵件目前透過 APAC 資料中心傳送供 EOP 篩選。

- 在美洲，所有的 Exchange Online 信箱都位於美國資料中心，除了南美洲是使用位於巴西和智利資料中心，以及加拿大使用位於加拿大資料中心。 所有電子郵件訊息（包括南美洲和加拿大客戶的訊息）都透過本地資料中心路由，以進行 EOP 篩選；隔離的電子郵件會儲存在租用者所在的資料中心。

- 至於政府社群雲端 (GCC)，所有 Exchange Online 信箱都位於美國資料中心，且所有郵件都透過美國資料中心傳送供 EOP 篩選。

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP 內部部署電子郵件組織的計畫及功能

以下是可用的 EOP 訂閱方案：

- **獨立 EOP**：您可以註冊 EOP 以保護內部部署的電子郵件組織。

- **Exchange online 中的 EOP 功能**：包含 Exchange online 的任何訂閱（獨立或 Microsoft 365 的一部分）都會使用 EOP 來保護您的 Exchange Online 信箱。

- **Exchange Enterprise CAL (含服務) **：如果您有內部部署的 Exchange 組織，且您已購買額外的 Exchange Enterprise CAL (含服務) 授權，EOP 會包含在服務中。

如需所有 EOP 訂閱方案之需求、重要限制和功能可用性的相關資訊，請參閱 [Exchange Online Protection 服務描述](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>設定內部部署電子郵件組織的 EOP

設定 EOP 可以很簡單，對於具有一些符合性規則的小型組織來說，更是如此。不過，如果您的組織是具有多個網域、自訂符合性規則或混合郵件流程的大型組織，則在進行設定時可能需要更加詳盡的規劃及更多的時間。

如果已購買 EOP，請參閱[設定 EOP 服務](set-up-your-eop-service.md)，以確保完成所有必要的 EOP 設定步驟，來保護郵件環境。

## <a name="eop-help-for-admins"></a>EOP 系統管理員的協助

適用於 EOP 系統管理員的幫助內容由下列頂層類別組成：

- [Exchange Online Protection 概觀](exchange-online-protection-overview.md)：介紹 EOP 的運作方式，並提供其他資訊連結。

- [EOP 功能](eop-features.md)：提供一份 EOP 中可用的功能清單。

- [設定 EOP 服務](set-up-your-eop-service.md)：提供 EOP 服務的設定步驟，以及其他資訊的連結。

- [從 Google Postini、Barracuda Spam and Virus Firewall 或 Cisco IronPort 切換到 EOP](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)：說明從其他電子郵件保護產品切換到 EOP 的程序。

- [管理獨立 EOP 中的](manage-recipients-in-eop.md)收件者：說明如何管理 EOP 中的郵件使用者和群組。

- [EOP 中的郵件流程](mail-flow-in-eop.md)：說明如何使用連接器來設定自訂郵件流程案例、如何管理與服務相關的網域，以及如何啟用目錄架構邊緣封鎖 (DBEB) 功能。

- [設定 EOP 的最佳作法](best-practices-for-configuring-eop.md)：說明在您設定和佈建服務之後的建議組態設定和考量。

- [獨立 EOP 中的審計報告](auditing-reports-in-eop.md)：說明如何使用審核報告追蹤對服務的設定變更。

- [EOP 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)：說明垃圾郵件篩選和惡意程式碼篩選，並示範如何自訂以符合組織的需求。 此外，還說明系統管理員和使用者可以對隔離郵件執行的工作。

- [Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md)：說明可用的報告和疑難排解工具。

- [Exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)：說明如何存取和流覽 Exchange 系統管理中心（EAC）管理介面，以便管理 EOP 服務。

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)：提供遠端 PowerShell 的相關資訊，讓您可以從命令列管理 EOP 服務。

- [EOP 幫助和支援](help-and-support-for-eop.md) 提供有關取得幫助和技術支援的資訊。
