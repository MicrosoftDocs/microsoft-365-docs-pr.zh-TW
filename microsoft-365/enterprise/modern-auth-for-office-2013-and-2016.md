---
title: Office 2013 和 Office 2016 用戶端應用程式的新式驗證方式
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: 瞭解 Office 2013 和2016用戶端應用程式的 Microsoft 365 新式驗證功能的運作方式。
ms.openlocfilehash: 3e402f5786a72f3703ab4a1a77df688176f7de61
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921663"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>新式驗證如何運作 Office 2013、Office 2016 和 Office 2019 用戶端應用程式

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

請閱讀本文，以瞭解 Office 2013、Office 2016 和 Office 2019 用戶端應用程式如何根據 Exchange Online、SharePoint Online 和商務用 Skype Online 的 Microsoft 365 承租人上的驗證設定，使用新式驗證功能。

> [!NOTE]
> 舊版用戶端應用程式（例如 Office 2010 和 Office for Mac 2011）不支援新式驗證，而且只能搭配基本驗證使用。

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Microsoft 365 服務的新式驗證可用性

針對 Microsoft 365 服務，新式驗證的預設狀態為：
  
- 預設 **會開啟 Exchange** Online。 請參閱 [啟用或停用 Exchange Online 中的新式驗證](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) ，以關閉或開啟。 
    
- 預設 **會為 SharePoint 線上開啟。** 
    
- **根據** 預設，啟用商務用 Skype Online。 請參閱 [啟用新式驗證的商務用 Skype Online ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)以關閉或開啟。

> [!NOTE]
> 針對在 2017 年 8 月 1 日 **之前** 建立的租用戶，將對 Exchange Online 和商務用 Skype Online 預設 **關閉** 新式驗證。
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Office 用戶端應用程式的登入行為

根據預設，Office 2013 用戶端應用程式支援舊版驗證。 「舊版」是表示它們支援 Microsoft 線上登入小幫手或基本驗證。 為了讓這些用戶端使用新式驗證功能，Windows 用戶端必須已設定登錄機碼。 如需相關指示，請參閱 [在 Windows 裝置上啟用 Office 2013 的新式驗證](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)。

若要針對已安裝 Microsoft Office 2013、且執行 Windows 的任何裝置啟用新式驗證 (比如膝上型電腦和平板電腦)，您必須先設定下列登錄機碼。您必須在每部要啟用新式驗證的裝置上設定機碼：
  
|**登錄機碼**|**Type**|**Value** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
閱讀 [如何使用現代驗證 (ADAL) 搭配商務](./hybrid-modern-auth-overview.md) 用 skype 來瞭解如何使用商務用 skype。 
  
Office 2016 和 Office 2019 用戶端預設會支援新式驗證，且不需要採取任何動作，用戶端即可使用這些新流程。 不過，需要明確的動作才能使用舊版驗證。
  
按一下下列連結，以查看 Office 2013、Office 2016 和 Office 2019 用戶端驗證如何使用 Microsoft 365 服務，視是否已開啟新式驗證而定。
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [商務用 Skype Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

下表說明使用或不使用新式驗證連線至 Exchange Online 時，Office 2013、Office 2016 及 Office 2019 用戶端應用程式的驗證行為。
  
|Office 用戶端應用程式版本 * * * *|登錄機碼存在？ * * * *|上的新式驗證？ * * * *|針對租使用者開啟的新式驗證行為驗證行為 (預設) * * * * * * * * * * * * *|針對承租人的新式驗證關閉驗證行為 * * * * * * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |不 <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |是  <br/> |在 Outlook 2013、2016或2019上強制執行新式驗證。 <br/> [其他資訊](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|強制執行 Outlook 用戶端中的新式驗證。<br/> |
|Office 2019  <br/> |No 或 EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |基本驗證  <br/> |基本驗證  <br/> |
|Office 2016  <br/> |不 <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |是  <br/> |在2013、2016或2019上強制執行新式驗證。 <br/> [其他資訊](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|強制執行 Outlook 用戶端中的新式驗證。<br/> |
|Office 2016  <br/> |No 或 EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |基本驗證  <br/> |基本驗證  <br/> |
|Office 2013  <br/> |否  <br/> |否  <br/> |基本驗證  <br/> |基本驗證  <br/> |
|Office 2013  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連接，則使用基本驗證。 當租使用者未啟用時，伺服器會拒絕新式驗證。  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

下表說明 Office 2013、Office 2016 及 Office 2019 用戶端應用程式連線至 SharePoint 線上時，是否有新式驗證的驗證行為。
  
|Office 用戶端應用程式版本 * * * *|登錄機碼存在？ * * * *|上的新式驗證？ * * * *|針對租使用者開啟的新式驗證行為驗證行為 (預設) * * * * * * * * * * * * *|針對承租人的新式驗證關閉驗證行為 * * * * * * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No 或 EnableADAL = 1  <br/> |是  <br/> |僅限新式驗證。  <br/> |連接失敗。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |僅限新式驗證。  <br/> |連接失敗。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |僅限 Microsoft Online 登入助理。  <br/> |僅限 Microsoft Online 登入助理。  <br/> |
|Office 2016  <br/> |No 或 EnableADAL = 1  <br/> |是  <br/> |僅限新式驗證。  <br/> |連接失敗。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |僅限新式驗證。  <br/> |連接失敗。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |僅限 Microsoft Online 登入助理。  <br/> |僅限 Microsoft Online 登入助理。  <br/> |
|Office 2013  <br/> |否  <br/> |否  <br/> |僅限 Microsoft Online 登入助理。  <br/> |僅限 Microsoft Online 登入助理。  <br/> |
|Office 2013  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |僅限新式驗證。  <br/> |連接失敗。  <br/> |
   
### <a name="skype-for-business-online"></a>商務用 Skype Online
<a name="BK_SFBO"> </a>

下表說明使用或不含新式驗證連線至商務用 Skype Online 時，Office 2013、Office 2016 及 Office 2019 用戶端應用程式的驗證行為。
  
|Office 用戶端應用程式版本 * * * *|登錄機碼存在？ * * * *|上的新式驗證？ * * * *|針對租使用者開啟的新式驗證行為驗證行為 * * * * *|針對租使用者 (的新式驗證關閉驗證行為預設) * * * * * * * * * * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No 或 EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連線，則會使用 Microsoft 線上登入 Assistant。 當未啟用商務用 Skype Online 承租人時，伺服器會拒絕新式驗證。  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連線，則會使用 Microsoft 線上登入 Assistant。 當未啟用商務用 Skype Online 承租人時，伺服器會拒絕新式驗證。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連線，則會使用 Microsoft 線上登入 Assistant。 當未啟用商務用 Skype Online 承租人時，伺服器會拒絕新式驗證。  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連線，則會使用 Microsoft 線上登入 Assistant。 當未啟用商務用 Skype Online 承租人時，伺服器會拒絕新式驗證。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |僅限 Microsoft Online 登入助理。  <br/> |僅限 Microsoft Online 登入助理。  <br/> |
|Office 2016  <br/> |No 或 EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連線，則會使用 Microsoft 線上登入 Assistant。 當未啟用商務用 Skype Online 承租人時，伺服器會拒絕新式驗證。  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連線，則會使用 Microsoft 線上登入 Assistant。 當未啟用商務用 Skype Online 承租人時，伺服器會拒絕新式驗證。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連線，則會使用 Microsoft 線上登入 Assistant。 當未啟用商務用 Skype Online 承租人時，伺服器會拒絕新式驗證。  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連線，則會使用 Microsoft 線上登入 Assistant。 當未啟用商務用 Skype Online 承租人時，伺服器會拒絕新式驗證。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |僅限 Microsoft Online 登入助理。  <br/> |僅限 Microsoft Online 登入助理。  <br/> |
|Office 2013  <br/> |否  <br/> |否  <br/> |僅限 Microsoft Online 登入助理。  <br/> |僅限 Microsoft Online 登入助理。  <br/> |
|Office 2013  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |先嘗試新式驗證。 如果伺服器拒絕新式驗證連線，則會使用 Microsoft 線上登入 Assistant。 當未啟用商務用 Skype Online 承租人時，伺服器會拒絕新式驗證。  <br/> |僅限 Microsoft Online 登入助理。  <br/> |
   
## <a name="see-also"></a>另請參閱

[為 Windows 裝置上的 Office 2013 啟用新式驗證](../admin/security-and-compliance/enable-modern-authentication.md)

[Microsoft 365 的多重要素驗證](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[使用多重要素驗證登入 Microsoft 365](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)