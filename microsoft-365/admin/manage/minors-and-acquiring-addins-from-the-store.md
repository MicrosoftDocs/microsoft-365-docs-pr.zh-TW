---
title: 對存放區中的增益集進行未成年人和取得
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 深入瞭解一般資料保護法規 (GDPR) 管理未成年人之個人資料的規章。
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580915"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>對存放區中的增益集進行未成年人和取得

一般資料保護法規 (GDPR) 是一種已生效的歐盟法規（可能會是25，2018）。 它可讓使用者具備及保護其資料的權力。 其中一個 GDPR 的其中一個方面是，所有未成年人都無法將其個人資料傳送給他們的父系或監護人未獲核准的協力廠商。 定義為次要的特定年齡取決於個人所在的地區。
  
法律規定具有「父母同意」規定的地區包括美國、韓國、英國和歐盟。 針對這些地區，將會封鎖 (透過 Azure Active Directory) 取得任何新的 Office 增益集，並執行先前取得之增益集的次要功能。 對於沒有法令規定的國家，將不會有下載限制。
  
根據 Azure Active Directory 中所指定的資料，將使用者判斷為次要。 組織管理員負責宣告法律年齡群組和該使用者的「父母同意」。
  
如果上層/監護人 consents 使用特定增益集，則組織系統管理員可以使用集中式部署，將該增益集部署至所有已同意的未成年人。
  
若要 GDPR 相容性，您必須確定在學校/組織中部署下列 Office 組建中的其中一項。
 
 **Word、Excel、PowerPoint 及專案**： 

|**平台** <br/> |**組建號碼** <br/> |
|:-----|:-----|
|Microsoft 365 應用程式 enterprise (目前通道)   <br/> |9001.2138   <br/> |
|適用于企業的 Microsoft 365 應用程式 (半年 Enterprise 通道)   <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Office 網頁版  <br/> |不適用  <br/> |
   
 **Outlook**： 
  
|**平台** <br/> |**組建號碼** <br/> |
|:-----|:-----|
|Outlook 2016 for Windows (MSI)   <br/> |建立無待定  <br/> |
|適用于 Windows (C2R 的 Outlook 2016)   <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|iOS 的 Outlook mobile  <br/> |2.75.0  <br/> |
|適用于 Android 的 Outlook mobile  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |不適用  <br/> |

 **Office 2013 需求**
  
如果啟用 Active Directory 驗證程式庫 (ADAL) ，則 Windows 的 Word、Excel 及 PowerPoint 2013 會支援相同的各處檢查。 規範有兩個選項，如接下來所述。
  
- **啟用 ADAL**。 本文說明如何啟用 ADAL for Office 2013：搭配 [使用 Microsoft 365 新式驗證與 office 用戶端](../../enterprise/modern-auth-for-office-2013-and-2016.md)。<br/>您也需要將登錄機碼設定為啟用 ADAL，如在 [Windows 裝置上啟用 Office 2013 新式驗證](../security-and-compliance/enable-modern-authentication.md)中所述。<br/>此外，您必須安裝下列 Office 2013 的四月更新：
    
  - [Office 2013 的安全性更新說明：4月10日（2018）](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018年4月3日，Office 2013 的更新 (KB4018333) ](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **不要啟用 ADAL**。 如果您無法在 Office 2013 中啟用 ADAL，我們建議使用「群組原則」來關閉 Office 用戶端的存放區。 有關如何關閉 Office 相關應用程式設定的資訊位於 [這裡](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))。

## <a name="related-articles"></a>相關文章

[在系統管理中心部署增益集](./manage-deployment-of-add-ins.md)

[在系統管理中心管理增益集](./manage-addins-in-the-admin-center.md)
