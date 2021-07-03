---
title: 如何設定商務用 Skype 內部部署以使用混合式新式驗證
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 瞭解如何設定商務用 Skype 內部部署以使用混合式新式驗證 (HMA) ，為您提供更安全的使用者驗證和授權。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9695815d0a085931b10f7f64b9fca2e997af9077
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286054"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>如何設定商務用 Skype 內部部署以使用混合式新式驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

新式驗證是一種可提供更安全的使用者驗證和授權的身分識別管理方法，可用於商務用 Skype server 內部部署和 Exchange 伺服器內部部署和分割網域商務用 Skype 混合式。

 **重要事項** 您想要深入瞭解新式驗證 (MA) ，以及您想要在公司或組織中使用的原因為何？ 請查看 [這份檔](hybrid-modern-auth-overview.md) 中的概要。 如果您需要瞭解 MA 所支援的商務用 Skype 拓撲，請參閱此處所述！

 **開始之前**，我使用下列術語：

- 新式驗證 (MA) 

- 混合式新式驗證 (HMA) 

- Exchange 內部部署 (nm-exch-um-2nd) 

- Exchange Online (EXO) 

- 商務用 Skype 內部部署 (SFB) 

- 商務用 Skype線上 (SFBO) 

此外，如果本文中的圖形具有變暗或變暗的物件，表示以灰色顯示的元素 **不** 會包含在 MA 特有的設定中。

## <a name="read-the-summary"></a>閱讀摘要

這項摘要會將程式分解成可能在執行期間遺失的步驟，而且很適合整個檢查清單以追蹤您在程式中的何處。

1. 首先，請確定您符合所有必要條件。

1. 由於許多 **必要條件** 對商務用 Skype 和 Exchange 都很常見，[請參閱預先要求之檢查清單的概述文章](hybrid-modern-auth-overview.md)。 在您開始進行本文中的任何步驟之前，請  *先*  執行此動作。

1. 收集檔案中所需的 HMA 特定資訊，或 OneNote。

1. 開啟 EXO (的新式驗證（如果尚未開啟) ）。

1. 開啟 SFBO (的新式驗證（如果尚未開啟) ）。

1. 針對內部部署 Exchange 開啟混合式新式驗證。

1. 針對內部部署商務用 Skype 開啟混合式新式驗證。

這些步驟會開啟 SFB、SFBO、NM-EXCH-UM-2ND 和 EXO 的 MA，也就是，所有可參與 HMA 設定的 SFB 及 SFBO (包括 NM-EXCH-UM-2ND/EXO) 上的相依性。 換句話說，如果您的使用者在混合式 (EXO + SFBO、EXO + SFB、NM-EXCH-UM-2ND + SFBO 或 NM-EXCH-UM-2ND + SFB) 中建立信箱，您的最終產品將如下所示：

![混合式 6 Skype 的商務 HMA 拓撲在所有四個可能的位置上都有 MA。](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

如您所見，有四個不同的地方可開啟 MA！ 為了獲得最佳的使用者體驗，建議您在上述四個位置中開啟 MA。 [！注意] 如果您無法在這些位置中開啟 MA，請調整步驟，讓您只在環境所需的位置開啟 MA。

如需支援的拓撲，請參閱[適用于商務用 Skype](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)的支援主題。

 **重要事項** 請仔細檢查您是否已符合所有必要條件，再開始之前。 您會發現 [混合式新式驗證概述和必要條件](hybrid-modern-auth-overview.md)中的資訊。

## <a name="collect-all-hma-specific-info-youll-need"></a>收集您需要的所有 HMA 特有資訊

當您已仔細檢查您是否符合使用新式驗證的 [必要條件](hybrid-modern-auth-overview.md) 時 (請參閱上述) 的附注，您應該建立檔案，以保留在前面步驟中設定 HMA 所需的資訊。 本文使用的範例：

- **SIP/SMTP 網域**

  - 前。 contoso.com (與 Office 365 同盟) 

- **租使用者識別碼**

  - contoso.onmicrosoft.com) 登入代表 Office 365 租使用者 (的 GUID。

- **SFB 2015 CU5 Web 服務 URLs**

您將需要部署的所有 SfB 2015 集區的內部及外部 web 服務 URLs。 若要取得這些，請從商務用 Skype 管理命令介面執行下列命令：

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- 前。 內部： https://lyncwebint01.contoso.com

- 前。 外部： https://lyncwebext01.contoso.com

如果您是使用 Standard Edition 伺服器，則內部 URL 會是空白的。 在此情況下，請使用內部 URL 的集區 fqdn。

## <a name="turn-on-modern-authentication-for-exo"></a>開啟 EXO 的新式驗證

遵循下列指示： [Exchange Online：如何針對新式驗證啟用租使用者。](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)

## <a name="turn-on-modern-authentication-for-sfbo"></a>開啟 SFBO 的新式驗證

請遵循下列指示：[商務用 Skype 線上：針對新式驗證啟用租使用者](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>在內部部署 Exchange 開啟混合式新式驗證

遵循下列指示：[如何設定 Exchange Server 內部部署以使用混合式新式驗證](configure-exchange-server-for-hybrid-modern-authentication.md)。

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>在內部部署商務用 Skype 開啟混合式新式驗證

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>在 Azure Active Directory 中將內部部署 web 服務 URLs 當做 Spn 新增

現在，您必須執行命令，以新增) 為 SFBO 中的服務主體 (所收集的 URLs。

 **記事** 服務主體名稱 (Spn) 識別 web 服務，並將它們與安全性主體 (例如帳戶名稱或群組) 等相關聯，這樣服務才能代表授權的使用者進行動作。 對伺服器進行驗證的用戶端會使用包含在 Spn 中的資訊。

1. 首先，使用[這些指示](/powershell/azure/active-directory/overview)，連接至 Azure Active Directory (Azure AD) 。

2. 在內部部署中執行此命令，以取得 SFB web 服務 URLs 的清單。

   請注意，AppPrincipalId 會以開頭 `00000004` 。 這對應于線上商務用 Skype。

   請記下 (和螢幕擷取畫面，以) 此命令的輸出，它會包含 SE 和 WS URL，但通常是由開頭的 spn 所組成 `00000004-0000-0ff1-ce00-000000000000/` 。

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. 例如，如果內部 **或** 外部 SFB URLs 來自內部部署 (例如，則 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) 需要將這些特定記錄新增至此清單。

    請務必使用 Add 命令中的實際 URLs 取代下列  *範例 URLs* ！

```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. 再次執行步驟2上的 **new-msolserviceprincipal** 命令，然後查看輸出，以確認新增的記錄已新增。 將清單或螢幕擷取畫面與新的 Spn 清單進行比較。 您也可以將新的記錄清單螢幕擷取畫面。 如果您成功，您會在清單中看到兩個新的 URLs。 接下來的範例，Spn 清單現在會包含特定的 URLs https://lyncwebint01.contoso.com 和 https://lyncwebext01.contoso.com/ 。

### <a name="create-the-evosts-auth-server-object"></a>建立 EvoSTS 驗證服務器物件

在商務用 Skype 管理命令介面中執行下列命令。

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>啟用混合式新式驗證

這是實際開啟 MA 的步驟。 您可以事先執行上述所有步驟，而不需變更用戶端驗證流程。 當您準備好變更驗證流程時，請在商務用 Skype 管理命令介面中執行此命令。

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>驗證

一旦您啟用 HMA，用戶端的下一個登入將會使用新的驗證流程。 請注意，只要開啟 HMA，就不會對任何用戶端觸發重新驗證。 用戶端會根據驗證權杖和/或憑證的存留時間來驗證。

若要測試 HMA 在您啟用後是否正常運作，請登出 test SFB Windows 用戶端，並確定按一下「刪除我的認證」。 重新登入。 用戶端現在應該使用新式驗證流程，而且您的登入現在會包含「工作或學校」帳戶的 **Office 365** 提示，在用戶端聯繫伺服器並登入之前看到。

您也應該檢查「設定資訊」，以取得「OAuth 授權」商務用 Skype 用戶端的「設定資訊」。 若要在用戶端電腦上執行這項作業，請在您以滑鼠右鍵按一下 Windows 通知列中的商務用 Skype 圖示時，按住 CTRL 鍵。 按一下出現的功能表中的 [設定 **資訊** ]。 在桌面上會出現的「商務用 Skype 設定資訊」視窗中，尋找下列專案：

![使用新式驗證的商務用 Skype 用戶端的設定資訊會顯示的 Lync 和 EWS OAUTH 授權 URL https://login.windows.net/common/oauth2/authorize 。](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)

您也應該同時按住 CTRL 鍵，以滑鼠右鍵按一下 Outlook 用戶端 (圖示，也就是在 [Windows 通知] 工作列) ，然後按一下 [線上狀態]。 根據「載體」的 AuthN 類型 \* （代表 OAuth 中使用的持有者權杖），尋找用戶端的 SMTP 位址。

## <a name="related-articles"></a>相關文章

[連結回新式驗證概述](hybrid-modern-auth-overview.md)。

您需要瞭解如何對您的商務用 Skype 用戶端使用新式驗證 (ADAL) 嗎？ 我們已 [在這裡](./hybrid-modern-auth-overview.md)獲得步驟。