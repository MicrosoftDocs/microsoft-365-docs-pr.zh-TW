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
ms.openlocfilehash: 8db74c04335e0846666991d74980648cedb4d9d7
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547127"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>如何設定 Exchange Server 內部部署以使用混合式新式驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

混合式新式驗證 (HMA) 是一種提供更安全的使用者驗證和授權方法，可供 Exchange server 內部部署混合式部署使用。

## <a name="fyi"></a>僅供參考

開始之前，我會致電：

- 混合式新式驗證 \> HMA

- Exchange 內部部署 \> nm-exch-um-2nd

- Exchange Online \> EXO

此外， *如果本文中的圖形具有 ' 變暗」或「暗灰色」的物件，表示以灰色顯示的元素不會包含在 HMA 特定* 的設定中。

## <a name="enabling-hybrid-modern-authentication"></a>啟用混合式新式驗證

開啟 HMA 的方式：

1. 在您開始之前，請確定您已符合必要條件。

1. 由於商務用 Skype 和 Exchange 皆是許多 **必要條件** ，所以 [混合新式驗證概述和必要條件搭配內部部署商務用 Skype 和 Exchange 伺服器使用它](hybrid-modern-auth-overview.md)。 在您開始進行本文中的任何步驟之前，請先執行此動作。

1. 將內部部署 web 服務 URLs 新增為 **服務主體名稱 (** Azure AD 中的 spn) 。

1. 確保所有虛擬目錄都已啟用 HMA

1. 檢查 EvoSTS 驗證服務器物件

1. 啟用 NM-EXCH-UM-2ND 中的 HMA。

 **記事** 您的 Office 版本是否支援 MA？ 請參閱 [如何在 office 2013 和 office 2016 用戶端應用程式中運作新式驗證](modern-auth-for-office-2013-and-2016.md)。

## <a name="make-sure-you-meet-all-the-prerequisites"></a>請確認您符合所有必要條件

由於商務用 Skype 和 Exchange 一般都有許多必要條件，所以請參閱 [混合式新式驗證概述和使用內部部署商務用 skype 和 Exchange 伺服器的必要條件](hybrid-modern-auth-overview.md)。 在您開始進行本文中的任何步驟之前，請  *先*  執行此動作。

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>在 Azure AD 中將內部部署 web 服務 URLs 當做 Spn 新增

執行將您的內部部署 web 服務 URLs 指派為 Azure AD Spn 的命令。 在驗證和授權期間，用戶端機器和裝置會使用 Spn。 所有可能用來從內部部署至 Azure Active Directory (Azure AD) 的 URLs，都必須在 Azure AD 中註冊， (這包括內部及外部命名空間) 。

首先，請收集您需要在 AAD 中新增的所有 URLs。 在內部部署執行下列命令：

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

確定用戶端可以連線的 URLs 已列為 AAD 中的 HTTPS 服務主體名稱。

1. 首先，使用 [這些指示](connect-to-microsoft-365-powershell.md)連接至 AAD。

   **記事** 您必須使用此頁面上的 _Connect-MsolService_ 選項，才能使用下列命令。

2. 針對您的 Exchange 相關 URLs，請輸入下列命令：

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   記下 (和螢幕擷取畫面，以供稍後比較) 此命令的輸出應包含 HTTPs://  *autodiscover.yourdomain.com*  和 Https://  *mail.yourdomain.com* URL，但通常是由以 00000002-0000-0Ff1-ce00-000000000000/開頭的 spn 所組成。 如果從您的內部部署 HTTPs://URLs，將需要將這些特定記錄新增至此清單。

3. 如果您沒有看到您的內部及外部 MAPI/HTTP、EWS、ActiveSync、OAB 及自動探索記錄，您必須使用下列命令來新增， (範例 URLs 是 ' `mail.corp.contoso.com` ' 和 ' ' `owa.contoso.com` ，但是您會 **以您自己的 URLs 取代範例 ) ** ：

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 再次執行步驟2上的 New-msolserviceprincipal 命令，然後查看輸出，以確認新增的記錄已新增。 將清單/螢幕擷取畫面與新的 Spn 清單進行比較 (您也可以將記錄新增至新清單) 。 如果您成功，您會在清單中看到兩個新的 URLs。 接下來的範例，Spn 清單現在會包含特定的 URLs  `https://mail.corp.contoso.com`  和  `https://owa.contoso.com` 。

## <a name="verify-virtual-directories-are-properly-configured"></a>確認已正確設定虛擬目錄

現在，請執行下列命令，確認已在 Exchange 上針對所有可用的虛擬目錄，確認是否已在 Exchange 上正確啟用 OAuth：

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

如果任何伺服器及任何四個虛擬目錄中的 OAuth 都缺失，您必須使用相關命令新增它，然後再繼續 ([設定 MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory)、 [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory)、 [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)及 [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)) 。

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>確認 EvoSTS 驗證服務器物件存在

回到此最後一個命令的內部部署 Exchange 管理命令介面。 現在，您可以驗證您的內部部署是否具有 evoSTS 驗證提供者的專案：

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

您的輸出應顯示名稱為 EvoSts 的 Set-authserver，且 [Enabled] 狀態應該為 True。 如果您未看到此內容，您應該下載並執行最新版本的混合式設定向導。

 **重要事項** 如果您正在環境中執行 Exchange 2010，將不會建立 EvoSTS 驗證提供者。

## <a name="enable-hma"></a>啟用 HMA

在 Exchange 管理命令介面內部部署中執行下列命令：

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>驗證

一旦您啟用 HMA，用戶端的下一個登入將會使用新的驗證流程。 請注意，只要開啟 HMA，就不會觸發任何用戶端的重新驗證。 用戶端會根據驗證權杖和/或憑證的存留時間，重新進行驗證。

您也應該同時按住 CTRL 鍵，以滑鼠右鍵按一下 Outlook 用戶端的圖示 (也在 Windows 通知盤) 中，然後按一下 [線上狀態]。 根據 ' Authn ' 類型的 ' 載體 ' 尋找用戶端的 SMTP 位址 \* ，它代表 OAuth 中使用的持有者權杖。

 **記事** 需要使用 HMA 設定商務用 Skype？ 您將需要兩個文章：一個會列出 [支援的拓撲](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)，另一個說明 [如何進行](configure-skype-for-business-for-hybrid-modern-authentication.md)設定。

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>對 Outlook for iOS 和 Android 使用混合新式驗證

如果您是使用 TCP 443 上 Exchange server 的內部部署客戶，請將下列 IP 範圍列入白名單：

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>相關主題

[從 Office 365 專屬/ITAR 轉換為 vNext 的新式驗證設定需求](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
