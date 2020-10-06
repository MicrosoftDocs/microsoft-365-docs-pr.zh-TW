---
title: 混合新式驗證概述和必要條件，以搭配內部部署商務用 Skype 和 Exchange 伺服器使用
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 08/25/2020
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
description: 在本文中，您將深入瞭解混合式新式驗證和使用內部部署商務用 Skype 和 Exchange 伺服器的必要條件。
ms.openlocfilehash: 82cd4203e2e9dc53c6add542c5f0ba90530b6548
ms.sourcegitcommit: d648356b27842e779921859480b1b405a1804c7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361924"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>混合新式驗證概述和使用內部部署商務用 Skype 和 Exchange 伺服器的必要條件

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

_新式驗證_ 是一種身分識別管理的方法，可提供更安全的使用者驗證和授權。 它適用于 Office 365 的商務用 Skype server 內部部署和 Exchange server 內部部署，以及分割網域商務用 Skype 混合式部署。 本文連結至有關必要條件、設定/停用新式驗證及部分相關用戶端 (ex 的相關檔。 Outlook 和 Skype 用戶端) 資訊。

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
- **條件式存取原則**：行動應用程式管理 (MAM) 和 Azure Active Directory (azure AD) 條件式存取

使用新式驗證來管理使用者身分識別，可讓系統管理員在保護資源時使用許多不同的工具，並提供更安全的身分識別管理方法，以進行內部部署 (Exchange 和商務用 Skype) 、Exchange 混合式和商務用 Skype 混合式/分割網域案例。

請注意，由於商務用 Skype 與 Exchange 緊密合作，所以商務用 Skype 用戶端使用者的登入行為將會受到 Exchange 新式驗證狀態的影響。 如果您有商務用 skype _分割網域混合式_ 架構，且您的商務用 skype Online 和商務用 skype 內部部署，也會套用這項功能，且使用者同時位於這兩個位置。

如需 Office 365 新式驗證的詳細資訊，請參閱 [office 365 用戶端應用程式支援-新式驗證](microsoft-365-client-support-modern-authentication.md)。

> [!IMPORTANT]
> 到2017年8月為止，所有包含商務用 Skype online 和 Exchange online 的新 Office 365 租使用者預設都會啟用新式驗證。 預先存在的承租人不會變更其預設的 MA 狀態，但是所有的新承租人都會自動支援您所看到的一組擴充的身分識別功能。 若要檢查您的 MA 狀態，請參閱 [查看內部部署環境的新式驗證狀態](hybrid-modern-auth-overview.md#BKMK_CheckStatus) 一節。

## <a name="what-changes-when-i-use-modern-authentication"></a>使用新式驗證時會有什麼變更？
<a name="BKMK_WhatChanges"> </a>

搭配內部部署商務用 Skype server 或 Exchange server 使用新式驗證時，您仍然會 *驗證* 使用者的內部部署，但在 (像是檔案或電子郵件) 變更的情況下，對資源進行 *授權* 存取的情景也是如此。 這就是由於新式驗證有關用戶端和伺服器通訊的原因，在 (evoSTS 中設定 MA 結果時所採取的步驟，是由 Azure AD) 設定為適用于商務用 Skype 和 Exchange server 內部部署之驗證服務器的安全性 Token 服務。

對 evoSTS 所做的變更可讓您的內部部署伺服器利用 OAuth (權杖發行) 來授權您的用戶端，也可讓您的內部部署使用雲端 (中常見的安全性方法，例如多重要素驗證) 。 此外，evoSTS 會發出標記，允許使用者要求存取資源，而不提供密碼做為要求的一部分。 不管您的使用者是在線上或內部部署) 的 (所在的位置，不論哪一個位置主控必要的資源，EvoSTS 將成為在設定新式驗證之後，授權使用者和用戶端的核心。

例如，如果商務用 Skype 用戶端需要存取 Exchange 伺服器以代表使用者取得行事曆資訊，它會使用 Active Directory 驗證程式庫 (ADAL) 來執行此作業。 ADAL 是一個程式碼庫，其設計目的是讓您的目錄中的安全資源可供使用 OAuth 安全性權杖的用戶端應用程式使用。 ADAL 可與 OAuth 搭配驗證宣告和 exchange token (，而不是密碼) ，以授與使用者對資源的存取權。 過去，在交易中（如下列所示）中的授權機構（即知道如何驗證使用者宣告及發出必要標記的伺服器），可能是內部部署的安全性權杖服務，甚至是 Active Directory Federation Services。 不過，新式驗證使用 Azure AD 來集中該授權。

這也表示，即使您的 Exchange 伺服器和商務用 Skype 環境可能完全在內部部署中，授權伺服器也是線上的，而您的內部部署環境必須能夠建立及維護雲端 (中的 Office 365 訂閱連線，以及您的訂閱用來做為其目錄) 的 Azure AD 實例。

什麼不會變更？ 不論您是在分割網域混合式，還是使用商務用 Skype 和 Exchange server 內部部署，所有使用者都必須先驗證 *內部部署*。 在新式驗證的混合式實施中， _Lyncdiscovery_ 和 _自動_ 探索都指向您的內部部署伺服器。

> [!IMPORTANT]
> 如果您需要知道麻塞諸塞州支援的特定商務用 Skype 拓撲，已 [在這裡記錄](https://technet.microsoft.com/library/mt803262.aspx)。

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>檢查您的內部部署環境的新式驗證狀態
<a name="BKMK_CheckStatus"> </a>

因為新式驗證變更了服務利用 OAuth/S2S 時所使用的授權伺服器，所以您需要知道您的內部部署商務用 Skype 和 Exchange 環境中，是否啟用或停用新式驗證。 您可以執行下列 PowerShell 命令，檢查 Exchange 伺服器的狀態：

```powershell
Get-OrganizationConfig | ft OAuth*
```

如果 _OAuth2ClientProfileEnabled_ 屬性的值為 **False**，則會停用新式驗證。

如需 Get-OrganizationConfig Cmdlet 的詳細資訊，請參閱 [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)。

您可以執行下列 PowerShell 命令，檢查您的商務用 Skype 伺服器：

```powershell
Get-CSOAuthConfiguration
```

如果命令傳回空的_OAuthServers_屬性，或是不**允許** _ClientADALAuthOverride_屬性的值，則會停用新式驗證。

如需 Get-CsOAuthConfiguration Cmdlet 的詳細資訊，請參閱 [Get-CsOAuthConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csoauthconfiguration)。

## <a name="do-you-meet-modern-authentication-prerequisites"></a>您是否符合新式驗證必要條件？

繼續進行之前，請先確認並檢查清單中的這些專案：

- **特定商務用 Skype**
  - 在商務用 Skype Server 2015 或更新版本中，所有伺服器都必須有2017累積更新 (CU5) 
    - **例外** 狀況分支裝置 (SBA) 可以在目前的版本 (根據 Lync 2013) 
  - 您的 SIP 網域已新增為 Office 365 的同盟網域
  - 所有 SFB 前端都必須有輸出至網際網路的連線，到 Office 365 驗證 URLs (TCP 443) 和知名憑證根 Crl (TCP 80) 列于 [Office 125 URLs 和 IP 位址範圍](urls-and-ip-address-ranges.md)的「Microsoft 365 通用和 Office」區段的列56和365中。

- **混合式 Office 365 環境中的商務用 Skype 內部部署**
  - 商務用 Skype Server 2019 部署，包含所有執行商務用 Skype Server 2019 的伺服器。
  - 商務用 Skype Server 2015 部署，包含所有執行商務用 Skype Server 2015 的伺服器。
  - 最多兩個不同伺服器版本的部署，如下所示：
    - 商務用 Skype Server 2015
    - 商務用 Skype Server 2019
  - 所有商務用 Skype 伺服器都必須已安裝最新的累計更新，請參閱 [商務用 Skype Server 更新](https://docs.microsoft.com/skypeforbusiness/sfb-server-updates) ，以尋找並管理所有可用的更新。
  - 混合式環境中沒有 Lync Server 2010 或2013。

>[!NOTE]
>若您的商務用 Skype 前端伺服器使用 proxy 伺服器進行網際網路存取，則必須在每個前端的 web.config 檔的 [設定] 區段中輸入 proxy 伺服器的 IP 和埠號碼。

- C:\Program Files\Skype for Business Server 2015 \ Web Components\Web ticket\int\web.config
- C:\Program Files\Skype for Business Server 2015 \ Web Components\Web ticket\ext\web.config

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
> 請務必訂閱 Office 365 URLs 的 RSS 摘要 [，以及 IP 位址範圍](urls-and-ip-address-ranges.md) ，以掌握最新的必要 URLs 清單。

- **Exchange Server 專用**
  - 您使用的是 Exchange server 2013 CU19、Exchange server 2016 CU8 及更新，或 Exchange Server 2019 CU1 和向上。
  - 環境中沒有 Exchange server 2010。
  - 未設定 SSL 卸載。 支援 SSL 終止和重新加密。
  - 在您的環境使用 proxy 伺服器基礎結構以允許伺服器連線至網際網路時，請確定所有 Exchange 伺服器的 [InternetWebProxy](https://technet.microsoft.com/library/bb123716%28v=exchg.160%29.aspx) 屬性中定義了 proxy 伺服器。

- **混合式 Office 365 環境中的 Exchange Server 內部部署**

  - 如果您使用的是 Exchange Server 2013，至少有一部伺服器必須已安裝信箱和用戶端存取伺服器角色。 雖然您可以在不同的伺服器上安裝信箱和用戶端存取角色，我們強烈建議您在同一部伺服器上安裝這兩種角色，以提供額外的可靠性並改善效能。
  - 如果您使用的是 Exchange server 2016 或更新版本，至少有一部伺服器必須已安裝信箱伺服器角色。
  - 混合式環境中沒有 Exchange server 2007 或2010。
  - 所有 Exchange 伺服器都必須已安裝最新的累計更新，請參閱 [升級 Exchange 至最新的累計更新](https://docs.microsoft.com/exchange/plan-and-deploy/install-cumulative-updates) ，以尋找並管理所有可用的更新。

- **Exchange 用戶端和通訊協定需求**

    新式驗證的可用性是由用戶端、通訊協定和設定的組合所決定。 如果用戶端、通訊協定及（或）設定不支援新式驗證，則用戶端將繼續利用舊版驗證。
  
    在環境中啟用新式驗證時，下列用戶端和通訊協定支援搭配內部部署 Exchange 的新式驗證：

  |**用戶端**|**主要通訊協定**|**附註**|
  |:-----|:-----|:-----|
  |Outlook 2013 和更新版本  <br/> |MAPI over HTTP  <br/> |必須在 Exchange 內啟用 MAPI over HTTP，以利用這些用戶端的新式驗證 (通常會啟用或為 Exchange 2013 Service Pack 1 和更新版本的新安裝啟用或設為 True) ;如需詳細資訊，請參閱 [office 2013 和 office 2016 用戶端應用程式的新式驗證的運作方式](modern-auth-for-office-2013-and-2016.md)。  <br/> 確定您執行的是最小必要組建的 Outlook;請查看 [使用 Windows Installer (MSI) 的 Outlook 版本最新更新 ](https://docs.microsoft.com/officeupdates/outlook-updates-msi)。  <br/> |
  |適用于 Mac 的 Outlook 2016 和更新版本  <br/> |Exchange Web 服務  <br/> |  <br/> |
  |iOS 和 Android 版 Outlook  <br/> | Microsoft sync 技術 <br/> |如需詳細資訊，請參閱 [使用 Outlook 適用于 Outlook 的混合新式驗證 iOS 和 Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) 。  <br/> |
  |Exchange ActiveSync 用戶端 (例如，iOS11 Mail)   <br/> |Exchange ActiveSync  <br/> |針對支援新式驗證的 Exchange ActiveSync 用戶端，您必須重新建立設定檔，才能從基本驗證切換至新式驗證。  <br/> |

    未列出的用戶端和（或）通訊協定 (例如，POP3) 不支援搭配內部部署 Exchange 的新式驗證，而且繼續利用舊版驗證機制，即使在環境中啟用新式驗證之後也是一樣。

- **一般必要條件**
  - 如果您使用 AD FS，則同盟必須具有 Windows 2012 R2 AD FS 3.0 和更新版本。
  - 您的身分識別設定是 Azure AD Connect 支援的任何類型，例如密碼雜湊同步處理、傳遞驗證，以及 Office 365 支援的內部部署 STS。
  - 您已設定 Azure AD Connect，以供使用者複寫及同步處理。
  - 您已驗證混合模式是在您的內部部署與 Office 365 環境之間使用 Exchange 傳統混合式拓撲模式設定。 Exchange 混合式的官方支援陳述說，您必須是目前的 CU 或目前的 CU-1。
    > [!NOTE]
    > [混合式代理程式](https://docs.microsoft.com/exchange/hybrid-deployment/hybrid-agent)不支援混合式新式驗證。

  - 如果您想要使用現代驗證與 Exchange) ，請確定內部部署測試使用者和 Office 365 中的混合測試使用者都可以登入商務用 Skype 桌面用戶端 (。如果您想要搭配 Exchange 使用新式驗證， () 則可以登入商務用 Skype 桌面用戶端。

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>開始之前，我還需要知道什麼？
<a name="BKMK_Whatelse"> </a>

- 內部部署伺服器的所有案例都包括設定新式驗證內部部署 (事實上，若為商務用 Skype，會列出支援的拓撲) ，因此負責驗證和授權的伺服器是在 Microsoft 雲端 (Azure AD 的安全性權杖服務（稱為「evoSTS ' ) ）和更新 Azure AD，以供您的內部部署安裝用 Skype 或 Exchange 使用的 URLs 或命名空間。 因此，內部部署伺服器會採用 Microsoft Cloud 相依性。 採取此動作可能會看作是「混合驗證」。
- 本文與其他專案連結，可協助您選擇支援的新式驗證拓撲 (只適用于商務用 Skype) ，以及如何對 Exchange 內部部署和商務用 Skype 內部部署啟用新式驗證的步驟。 如果您想要在您的伺服器環境中使用新式驗證，請在瀏覽器中，將此頁面最愛。

## <a name="related-topics"></a>相關主題
<a name="BKMK_URLListforMA"> </a>

- [如何設定 Exchange Server 內部部署以使用新式驗證](configure-exchange-server-for-hybrid-modern-authentication.md)
- [新式驗證支援的商務用 Skype 拓撲](https://technet.microsoft.com/library/mt803262.aspx)
- [如何設定商務用 Skype 內部部署以使用新式驗證](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [從商務用 Skype 與 Exchange 移除或停用混合式新式驗證](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)
