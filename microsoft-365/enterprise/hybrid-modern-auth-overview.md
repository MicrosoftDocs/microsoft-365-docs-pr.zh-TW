---
title: 混合新式驗證概述和必要條件，以搭配內部部署商務用 Skype 和 Exchange 伺服器使用
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 10/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: ef753b32-7251-4c9e-b442-1a5aec14e58d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 在本文中，您將深入瞭解混合式新式驗證，以及使用內部部署商務用 Skype 和 Exchange 伺服器的必要條件。
ms.openlocfilehash: 33bcf9bde2cda0388160337d3ffe6b81ab94eb12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907525"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>混合新式驗證概述和使用內部部署商務用 Skype 和 Exchange 伺服器的必要條件

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

_新式驗證_ 是一種身分識別管理的方法，可提供更安全的使用者驗證和授權。 可用於 Office 365 的混合部署商務用 Skype 伺服器內部部署，以及 Exchange 伺服器內部部署，以及分割網域商務用 Skype 混合式部署。 本文連結至有關必要條件、設定/停用新式驗證及部分相關用戶端 (ex 的相關檔。 ) 資訊 Outlook 和 Skype 用戶端。

- [何謂新式驗證？](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [使用新式驗證時會有什麼變更？](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [檢查您的內部部署環境的新式驗證狀態](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [您是否符合新式驗證必要條件？](#do-you-meet-modern-authentication-prerequisites)
- [開始之前，我還需要知道什麼？](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>何謂新式驗證？
<a name="BKMK_WhatisModAuth"> </a>

新式驗證是一項涵蓋在用戶端 (（例如，您的膝上型電腦或電話) 和伺服器）之間的驗證和授權方法的傘條款，以及一些依賴您可能已經熟悉之存取原則的安全性措施。 包括：

- **驗證方法**：多重要素驗證 (MFA) ;智慧卡驗證;以用戶端憑證為基礎的驗證
- **授權方法**： Microsoft 在開啟授權 (OAuth 的實施) 
- **條件式存取原則**：行動應用程式管理 (MAM) 和 Azure Active Directory (Azure AD) 條件式存取

以新式驗證來管理使用者身分識別，可讓系統管理員在保護資源時使用許多不同的工具，並提供更安全的身分識別管理方法給內部部署 (Exchange 及商務用 Skype) 、Exchange 混合式及商務用 Skype 混合式/分割網域案例。

請注意，因為商務用 Skype 與 Exchange 密切合作，所以商務用 Skype 用戶端使用者的登入行為會受到 Exchange 新式驗證狀態的影響。 如果您有商務用 Skype _分割網域的_ 混合架構，而且您有商務用 Skype 線上和商務用 Skype 內部部署，且同時位於這兩個位置的使用者，這也會適用。

如需 Office 365 中新式驗證的詳細資訊，請參閱[Office 365 用戶端應用程式支援-多重要素驗證](microsoft-365-client-support-multi-factor-authentication.md)。

> [!IMPORTANT]
> 到2017年8月為止，所有包含商務用 Skype 線上和 Exchange 線上的新 Office 365 租使用者預設都會啟用新式驗證。 預先存在的承租人不會變更其預設的 MA 狀態，但是所有的新承租人都會自動支援您所看到的一組擴充的身分識別功能。 若要檢查您的 MA 狀態，請參閱 [查看內部部署環境的新式驗證狀態](hybrid-modern-auth-overview.md#BKMK_CheckStatus) 一節。

## <a name="what-changes-when-i-use-modern-authentication"></a>使用新式驗證時會有什麼變更？
<a name="BKMK_WhatChanges"> </a>

搭配內部部署商務用 Skype 或 Exchange 伺服器使用新式驗證時，您仍然會 *驗證* 使用者內部部署，但 *授權* 其存取資源的情景， (如檔案或電子郵件) 變更。 這就是由於新式驗證有關用戶端和伺服器通訊的原因，在 (evoSTS 中設定 MA 結果所採取的步驟，是由 Azure AD) 設定為驗證服務器以商務用 Skype 和 Exchange 伺服器內部部署所使用的安全性權杖服務。

對 evoSTS 所做的變更可讓您的內部部署伺服器利用 OAuth (權杖發行) 來授權您的用戶端，也可讓您的內部部署使用雲端 (中常見的安全性方法，例如多重要素驗證) 。 此外，evoSTS 會發出標記，允許使用者要求存取資源，而不提供密碼做為要求的一部分。 不管您的使用者是在線上或內部部署) 的 (所在的位置，不論哪一個位置主控必要的資源，EvoSTS 將成為在設定新式驗證之後，授權使用者和用戶端的核心。

例如，如果商務用 Skype 用戶端需要存取 Exchange 伺服器以代表使用者取得行事曆資訊，它會使用 Active Directory 驗證程式庫 (ADAL) 來執行這項作業。 ADAL 是一個程式碼庫，其設計目的是讓您的目錄中的安全資源可供使用 OAuth 安全性權杖的用戶端應用程式使用。 ADAL 可與 OAuth 搭配驗證宣告和 exchange token (，而不是密碼) ，以授與使用者對資源的存取權。 過去，在交易中（如下列所示）中的授權機構（即知道如何驗證使用者宣告及發出必要標記的伺服器），可能是內部部署的安全性權杖服務，甚至是 Active Directory Federation Services。 不過，新式驗證使用 Azure AD 來集中該授權。

這也表示即使您的 Exchange 伺服器和商務用 Skype 環境可能完全在內部部署中，授權伺服器也是線上的，而您的內部部署環境必須能夠建立及維護雲端 (的 Office 365 訂閱連線，以及您的訂閱用來做為其目錄) 的 Azure AD 實例。

什麼不會變更？ 不論您是在分割網域混合，還是使用商務用 Skype 和 Exchange 伺服器內部部署，所有使用者都必須先驗證 *內部部署*。 在新式驗證的混合式實施中， _Lyncdiscovery_ 和 _自動_ 探索都指向您的內部部署伺服器。

> [!IMPORTANT]
> 如果您需要知道 MA 所支援的特定商務用 Skype 拓撲，已[在這裡記錄](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)。

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>檢查您的內部部署環境的新式驗證狀態
<a name="BKMK_CheckStatus"> </a>

因為新式驗證變更了服務利用 OAuth/S2S 時所使用的授權伺服器，所以您需要知道內部部署商務用 Skype 和 Exchange 環境是否已啟用或停用新式驗證。 您可以執行下列 PowerShell 命令，檢查 Exchange 伺服器上的狀態：

```powershell
Get-OrganizationConfig | ft OAuth*
```

如果 _OAuth2ClientProfileEnabled_ 屬性的值為 **False**，則會停用新式驗證。

如需 Get-OrganizationConfig Cmdlet 的詳細資訊，請參閱 [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig)。

您可以執行下列 PowerShell 命令，檢查您的商務用 Skype 伺服器：

```powershell
Get-CSOAuthConfiguration
```

如果命令傳回空的 _OAuthServers_ 屬性，或是不 **允許** _ClientADALAuthOverride_ 屬性的值，則會停用新式驗證。

如需 Get-CsOAuthConfiguration Cmdlet 的詳細資訊，請參閱 [Get-CsOAuthConfiguration](/powershell/module/skype/get-csoauthconfiguration)。

## <a name="do-you-meet-modern-authentication-prerequisites"></a>您是否符合新式驗證必要條件？

繼續進行之前，請先確認並檢查清單中的這些專案：

- **特定商務用 Skype**
  - 所有伺服器都必須有2017累積更新 (CU5) 商務用 Skype Server 2015 或更新版本
    - **例外** 狀況分支裝置 (SBA) 可以在目前的版本 (根據 Lync 2013) 
  - 您的 SIP 網域已新增為 Office 365 中的同盟網域
  - 所有 SFB 前端都必須有輸出至網際網路的連線，才能 Office 365 驗證 URLs (tcp 443) 和知名憑證根 crl (tcp 80) 列在[Microsoft 365 Office 和 IP 位址範圍](urls-and-ip-address-ranges.md)的「Office 365 通用和 URLs」區段的列56和125中。

- **混合 Office 365 環境中的商務用 Skype 內部部署**
  - 包含所有執行商務用 Skype Server 2019 之伺服器的商務用 Skype Server 2019 部署。
  - 包含所有執行商務用 Skype Server 2015 之伺服器的商務用 Skype Server 2015 部署。
  - 最多兩個不同伺服器版本的部署，如下所示：
    - 商務用 Skype Server 2015
    - 商務用 Skype Server 2019
  - 所有的商務用 Skype 伺服器都必須已安裝最新的累計更新，請參閱[商務用 Skype Server 更新](/skypeforbusiness/sfb-server-updates)，以尋找並管理所有可用的更新。
  - 混合式環境中沒有 Lync Server 2010 或2013。

>[!NOTE]
>如果您的商務用 Skype 前端伺服器使用 proxy 伺服器進行網際網路存取，則必須在每個前端使用 web.config 檔案的 [設定] 區段中輸入 proxy 伺服器的 IP 及埠號碼。

- C:\Program Files \ 商務用 Skype Server 2015 \ Web Components\Web ticket\int\web.config
- C:\Program Files \ 商務用 Skype Server 2015 \ Web Components\Web ticket\ext\web.config

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <proxy
        proxyaddress="https://192.168.100.60:8080"
        bypassonlocal="true" />
    </defaultProxy>
  </system.net>
</configuration>
```

> [!IMPORTANT]
> 請務必訂閱 rss 摘要，以取得[Office 365 URLs 及 IP 位址範圍](urls-and-ip-address-ranges.md)，以最新的必要 URLs 清單保持最新。

- **特定 Exchange Server**
  - 您使用的是 Exchange server 2013 CU19，且 Exchange 伺服器 2016 CU8 和更新，或是 Exchange Server 2019 CU1 和向上。
  - 環境中沒有 Exchange 伺服器2010。
  - 未設定 SSL 卸載。 支援 SSL 終止和重新加密。
  - 在您的環境使用 proxy 伺服器基礎結構以允許伺服器連線至網際網路時，請確定所有 Exchange 伺服器都具有[InternetWebProxy](/powershell/module/exchange/set-exchangeserver)屬性定義的 proxy 伺服器。

- **混合 Office 365 環境中的 Exchange Server 內部部署**

  - 如果您使用 Exchange Server 2013，至少有一部伺服器必須安裝信箱和用戶端存取伺服器角色。 雖然您可以在不同的伺服器上安裝信箱和用戶端存取角色，我們強烈建議您在同一部伺服器上安裝這兩種角色，以提供額外的可靠性並改善效能。
  - 如果您使用 Exchange server 2016 或更新版本，至少有一部伺服器必須已安裝信箱伺服器角色。
  - 混合式環境中沒有 Exchange 伺服器2007或2010。
  - 所有的 Exchange 伺服器都必須已安裝最新的累計更新，請參閱[Upgrade Exchange to all 累計更新](/exchange/plan-and-deploy/install-cumulative-updates)，以尋找並管理所有可用的更新。

- **Exchange 用戶端和通訊協定需求**

    新式驗證的可用性是由用戶端、通訊協定和設定的組合所決定。 如果用戶端、通訊協定及（或）設定不支援新式驗證，則用戶端將繼續利用舊版驗證。
  
    在環境中啟用新式驗證時，下列用戶端和通訊協定支援使用內部部署 Exchange 新式驗證：

  |**用戶端**|**主要通訊協定**|**附註**|
  |:-----|:-----|:-----|
  |Outlook 2013 和更新版本  <br/> |MAPI over HTTP  <br/> |必須在 Exchange 內啟用 MAPI over HTTP，才能利用這些用戶端的新式驗證 (通常是針對 Exchange 2013 Service Pack 1 和更新版本中的新安裝啟用或設為 True) ;如需詳細資訊[，請參閱新式驗證如何運作 Office 2013 和 Office 2016 用戶端應用程式](modern-auth-for-office-2013-and-2016.md)。  <br/> 確定您執行的是最小必要組建 Outlook;請參閱[使用 Windows Installer (MSI) 之 Outlook 版本的最新更新](/officeupdates/outlook-updates-msi)。  <br/> |
  |Mac 版 Outlook 2016 和更新版本  <br/> |Exchange Web 服務  <br/> |  <br/> |
  |iOS 和 Android 版 Outlook  <br/> | Microsoft sync 技術 <br/> |如需詳細資訊，請參閱[使用混合式新式驗證與適用于 iOS 和 Android 的 Outlook](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) 。  <br/> |
  |Exchange ActiveSync 用戶端 (例如，iOS11 Mail)   <br/> |Exchange ActiveSync  <br/> |針對支援新式驗證的 Exchange ActiveSync 用戶端，您必須重新建立設定檔，才能從基本驗證切換為新式驗證。  <br/> |

    未列出的用戶端和（或）通訊協定 (例如，POP3) 不支援搭配內部部署 Exchange 的新式驗證，繼續利用舊版驗證機制，即使已在環境中啟用新式驗證之後。

- **一般必要條件**
  - 資源樹系案例會需要與帳戶樹系進行雙向信任，以確保混合式新式驗證要求期間執行適當的 SID 查閱。 
  - 如果您使用 AD FS，則同盟應具備 Windows 2012 R2 AD FS 3.0 和更新版本。
  - 您的身分識別設定是 Azure AD 連線所支援的任何類型，例如密碼雜湊同步處理、傳遞驗證，以及 Office 365 所支援的內部部署 STS。
  - 您已設定 Azure AD 連線，且可在使用者複寫及同步處理時運作。
  - 您已驗證使用內部部署與 Office 365 環境之間的 Exchange 傳統混合拓撲模式設定混合。 Exchange 混合式的官方支援陳述說，您必須是目前的 cu 或目前的 cu-1。
    > [!NOTE]
    > [混合式代理程式](/exchange/hybrid-deployment/hybrid-agent)不支援混合式新式驗證。

  - 請確定內部部署測試使用者以及位於 Office 365 的混合式測試使用者可以登入商務用 Skype 桌面用戶端 (如果想要使用新式驗證搭配 Skype) 和 Microsoft Outlook (（如果您想要搭配 Exchange) 使用新式驗證）。

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>開始之前，我還需要知道什麼？
<a name="BKMK_Whatelse"> </a>

- 內部部署伺服器的所有案例都包括設定新式驗證內部部署 (事實上，針對商務用 Skype，有支援的拓撲清單) 因此，負責驗證和授權的伺服器是在 Microsoft 雲端 (Azure AD Security Token Service 中，稱為「evoSTS ' ) ，並更新 URLs 或商務用 Skype 的內部部署安裝所使用的命名空間的 Azure ad。 因此，內部部署伺服器會採用 Microsoft Cloud 相依性。 採取此動作可能會看作是「混合驗證」。
- 本文與其他專案連結，可協助您選擇支援的新式驗證拓撲 (只適用于商務用 Skype) 和說明如何針對 Exchange 內部部署和商務用 Skype 內部部署執行新式驗證的步驟。 如果您想要在您的伺服器環境中使用新式驗證，請在瀏覽器中，將此頁面最愛。

## <a name="related-topics"></a>相關主題
<a name="BKMK_URLListforMA"> </a>

- [如何設定 Exchange Server 內部部署以使用新式驗證](configure-exchange-server-for-hybrid-modern-authentication.md)
- [新式驗證支援的商務用 Skype 拓撲](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
- [如何設定商務用 Skype 內部部署以使用新式驗證](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [從商務用 Skype 與 Exchange 移除或停用混合式新式驗證](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)