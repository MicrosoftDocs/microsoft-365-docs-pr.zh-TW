---
title: 在 Office 365 中執行內部系統接管
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 了解如何確認接管未受管理的租用戶，Office 365 中您電子郵件和網域擁有權
ms.openlocfilehash: e3c89e122264808e2a8631c07269ea263c87fdaa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240359"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a>在 Office 365 中執行內部系統接管

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 

如果您是系統管理員，而且想要接管建立自助服務的使用者註冊受管理的租用戶，您可以將這運用內部系統接管。

> [!NOTE]
> 自助註冊使用 Azure AD 任何雲端服務會新增到未受管理的使用者或 「 陰影 「 Azure AD 目錄，並建立受管理的租用戶。 未受管理的租用戶是全域系統管理員沒有目錄。 若要判斷是否租用戶受管理或未受管理，請參閱[決定租用戶類型](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="step-1-verify-your-email-address"></a>步驟 1： 確認您的電子郵件地址

> [!NOTE]
> 如果您的租用戶中啟用自助，則使用者可以訂閱免費上的服務，例如 Power BI，自己。 這些步驟假設自助服務使用者的訂閱已建立未受管理的租用戶，您想要接管，成為管理員]。在第一個步驟中您可以建立未受管理的租用戶，以說明系統接管路徑使用 Power BI 中的使用者內容。

1. 若要註冊 Power BI，移至[Power BI 網站](https://powerbi.com)，然後選取 [**開始免費** > （在 [共用對象] 方塊中 Power BI 專業人員） 的 [**開始免費試用版**。 

2. 註冊的使用者使用之帳戶的組織的網域名稱 (例如`powerbiadmin@contoso.com`)。 如果您的帳戶已在使用中，使用登入您目前的密碼。

3. 請檢查您的電子郵件**驗證碼**，並輸入程式碼來驗證您的電子郵件地址。
    
## <a name="step-2-create-a-new-account"></a>步驟 2： 建立新的帳戶

1. 當您輸入驗證碼時，您將帶您可以在其中建立新的帳戶] 頁面上。 
    
2. 填入您要使用的帳戶使用者名稱和密碼欄位，然後選取 [**啟動**]。 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>步驟 3： 確認網域擁有權並成為系統管理員

1. **成為系統管理員**精靈會隨即開啟。 如果精靈並未自動啟動，尋找 [**管理**] 磚並選取它。 

2. 選取 [**是，我想成為系統管理員**。

3. 確認您擁有您想要接管將 TXT 記錄新增至您的網域註冊機構的網域。 精靈會提供 TXT 記錄新增，以及提供您的註冊機構網站以及逐步指示連結。
    
4. 一旦您已經註冊機構網站新增 TXT 記錄，請回到精靈，然後選取 [**好的我已新增記錄**。
    
> [!NOTE]
> 接管陰影租用戶將不會影響任何現有的資訊或服務。 不過，如果網域中的任何使用者已經註冊需要授權的服務，系統會要求您為其作為接管系統管理員角色的一部分購買授權。 您可以新增或移除授權，一旦完成管理安裝程序。 
  
## <a name="related-articles"></a>相關文章

Youtube：[接管 Power BI 和 Office 365 IT 系統管理員的 3 個步驟](https://www.youtube.com/watch?v=xt5EsrQBZZk) (英文)

[在 Azure AD 中的系統管理員接管](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[取得 Office 365 網域的說明](../get-help-with-domains/get-help-with-domains.md)

[組織中使用自助登](self-service-sign-up.md)
  
[了解 Power BI 服務系統管理員角色](https://docs.microsoft.com/power-bi/service-admin-role)

