---
title: 如何設定 Exchange Server 內部部署以使用混合式新式驗證
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 瞭解如何設定 Exchange Server 內部部署以使用混合式新式驗證 (HMA) ，為您提供更安全的使用者驗證和授權。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cb6d25a346ac48c9875a26f385cb733f1ff051f
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259448"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>如何設定 Exchange Server 內部部署以使用混合式新式驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

混合式新式驗證 (HMA) 是一種可提供更安全的使用者驗證和授權的身分識別管理方法，可用於 Exchange 伺服器內部部署混合式部署。

## <a name="fyi"></a>僅供參考

開始之前，我會致電：

- 混合式新式驗證 \> HMA

- Exchange 內部部署 \> nm-exch-um-2nd

- Exchange Online \>外

此外， *如果本文中的圖形具有 ' 變暗」或「暗灰色」的物件，表示以灰色顯示的元素不會包含在 HMA 特定* 的設定中。

## <a name="enabling-hybrid-modern-authentication"></a>啟用混合式新式驗證

開啟 HMA 表示：

1. 在您開始之前，請確定您已符合必要條件。

1. 由於許多 **必要條件** 都是商務用 Skype 和 Exchange、[混合新式驗證概述和必要條件搭配內部部署商務用 Skype 和 Exchange 伺服器共同使用](hybrid-modern-auth-overview.md)。 在您開始進行本文中的任何步驟之前，請先執行此動作。

1. 將內部部署 web 服務 URLs 新增為 **服務主體名稱 (** Azure AD 中的 spn) 。 在 NM-EXCH-UM-2ND 與 **多個承租人** 混合的情況下，這些內部部署 web 服務 URLs 必須新增為與 nm-exch-um-2nd 混合的所有承租人 Azure AD 中的 spn。

1. 確保所有虛擬目錄都已啟用 HMA

1. 檢查 EvoSTS 驗證服務器物件

1. 啟用 NM-EXCH-UM-2ND 中的 HMA。

> [!NOTE]
> 您的 Office 版本是否支援 MA？ 請參閱[新式驗證如何運作 Office 2013 和 Office 2016 用戶端應用程式](modern-auth-for-office-2013-and-2016.md)。


## <a name="make-sure-you-meet-all-the-prerequisites"></a>請確認您符合所有必要條件

由於許多必要條件對商務用 Skype 和 Exchange 都很常見，因此請參閱[混合式新式驗證概述和使用內部部署商務用 Skype 和 Exchange 伺服器的必要條件](hybrid-modern-auth-overview.md)。 在您開始進行本文中的任何步驟之前，請  *先*  執行此動作。

> [!NOTE]
> Outlook Web App 和 Exchange 控制台無法搭配混合式新式驗證使用。

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>在 Azure AD 中將內部部署 web 服務 URLs 當做 Spn 新增

執行將您的內部部署 web 服務 URLs 指派為 Azure AD Spn 的命令。 在驗證和授權期間，用戶端機器和裝置會使用 Spn。 所有可能用來從內部部署至 Azure Active Directory (azure ad) 的 URLs 都必須在 azure ad 中註冊， (這包括內部及外部命名空間) 。

首先，請收集您需要在 AAD 中新增的所有 URLs。 在內部部署執行下列命令：

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

確定用戶端可以連線的 URLs 已列為 AAD 中的 HTTPS 服務主體名稱。 在 NM-EXCH-UM-2ND 與 **多個承租人** 混合的情況下，這些 HTTPS spn 應新增在與 nm-exch-um-2nd 混合之所有承租人的 AAD 中。

1. 首先，使用 [這些指示](connect-to-microsoft-365-powershell.md)連接至 AAD。

    > [!NOTE]
    > 您必須使用此頁面上的 _Connect-MsolService_ 選項，才能使用下列命令。

2. 若為 Exchange 相關 URLs，請輸入下列命令：

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   記下 (和螢幕擷取畫面，以供稍後比較) 此命令的輸出應包含 HTTPs://  *autodiscover.yourdomain.com*  和 Https://  *mail.yourdomain.com* URL，但通常是由以 00000002-0000-0Ff1-ce00-000000000000/開頭的 spn 所組成。 如果從您的內部部署 HTTPs://URLs，我們需要將這些特定記錄新增至此清單。

3. 如果您未在此清單中看到您的內部及外部 MAPI/HTTP、EWS、ActiveSync、OAB 及自動探索記錄，您必須使用下列命令新增這些記錄， (範例 URLs 是 ' `mail.corp.contoso.com` ' 和 ' ' `owa.contoso.com` ，但是您會 **以您自己的 URLs 取代範例)** ：

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 再次執行步驟2的 Get-MsolServicePrincipal 命令，然後查看輸出，以確認新增的記錄已新增。 將清單/螢幕擷取畫面與新的 Spn 清單進行比較。 您也可以取得記錄的新清單的螢幕擷取畫面。 如果您成功，您會在清單中看到兩個新的 URLs。 接下來的範例，Spn 清單現在會包含特定的 URLs  `https://mail.corp.contoso.com`  和  `https://owa.contoso.com` 。

## <a name="verify-virtual-directories-are-properly-configured"></a>確認已正確設定虛擬目錄

現在驗證 OAuth 已在所有虛擬目錄上 Exchange 中正確啟用 Outlook 可能會執行下列命令：

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

檢查輸出，確定每個 VDirs 都已啟用 **OAuth** ，它看起來像這樣 (，而要查看的關鍵事項是「OAuth ' ) ：

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

如果任何伺服器和任何四個虛擬目錄中的 OAuth 都缺失，您必須使用相關命令新增它，才能繼續 ([設定 MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory)、 [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory)、 [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)及 [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)) 。

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>確認 EvoSTS 驗證服務器物件存在

回到此最後一個命令的內部部署 Exchange 管理命令介面。 現在，您可以驗證您的內部部署是否具有 evoSTS 驗證提供者的專案：

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

您的輸出應顯示名稱為 EvoSts 的 Set-authserver，且 [Enabled] 狀態應該為 True。 如果您未看到此內容，您應該下載並執行最新版本的混合式設定向導。

> [!NOTE]
> 在 NM-EXCH-UM-2ND 與 **多個承租人** 混合的情況下，您的輸出應該會顯示每個承租人中每個租使用者名稱 EvoSts {GUID} 的 set-authserver，且所有 set-authserver 物件的「Enabled」狀態應該是 True。

 **重要事項** 如果您正在環境中執行 Exchange 2010，將不會建立 EvoSTS 驗證提供者。

## <a name="enable-hma"></a>啟用 HMA

在內部部署的 Exchange 管理命令介面中執行下列命令：

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

如果 nm-exch-um-2nd 版本為 Exchange 2016 (CU18 或更高版本) 或 Exchange 2019 (CU7 或更高的) ，且混合已設定 HCW 在2020年9月之後下載，請在 Exchange 管理命令介面（內部部署）上執行下列命令：

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> 在 NM-EXCH-UM-2ND 與 **多個承租人** 混合的情況下，nm-exch-um-2nd 中有多個 set-authserver 物件會與每個租使用者對應的網域一起存在。  **IsDefaultAuthorizationEndpoint** 旗標應設定為 true (使用 **IsDefaultAuthorizationEndpoint** 指令程式) 以上任何一個 set-authserver 物件。 即使其中一個 Set-authserver 物件的 **IsDefaultAuthorizationEndpoint** 旗標設定為 true，這個旗標也不能設定為 True，set-authserver 物件和 HMA 都會啟用。

## <a name="verify"></a>驗證

一旦您啟用 HMA，用戶端的下一個登入將會使用新的驗證流程。 請注意，只要開啟 HMA，就不會對任何用戶端觸發重新驗證。 用戶端會根據驗證權杖和/或憑證的存留時間來驗證。

您也應該同時按住 CTRL 鍵，以滑鼠右鍵按一下 Outlook 用戶端 (圖示，也就是在 [Windows 通知] 工作列) ，然後按一下 [線上狀態]。 根據 ' Authn ' 類型的 ' 載體 ' 尋找用戶端的 SMTP 位址 \* ，它代表 OAuth 中使用的持有者權杖。

> [!NOTE]
> 需要使用 HMA 設定商務用 Skype 嗎？ 您將需要兩個文章：一個會列出 [支援的拓撲](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)，另一個說明 [如何進行](configure-skype-for-business-for-hybrid-modern-authentication.md)設定。


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>對 Outlook for iOS 和 Android 使用混合新式驗證

如果您是使用 TCP 443 上的 Exchange 伺服器的內部部署客戶，請回避下列 IP 位址範圍的流量處理：

```
52.125.128.0/20
52.127.96.0/23
```

iOS 和 Android 的 Outlook 應用程式是設計為在行動裝置上使用 Microsoft 服務來體驗 Microsoft 365 或 Office 365 的最佳方式，以協助您尋找、規劃及設定每日生命和工作的優先順序。 如需詳細資訊，請參閱[針對 iOS 和 Android 使用 Outlook 的混合新式驗證](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019)。

## <a name="related-topics"></a>相關主題

[從 Office 365 專屬/ITAR 轉換至 vNext 的新式驗證設定需求](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
