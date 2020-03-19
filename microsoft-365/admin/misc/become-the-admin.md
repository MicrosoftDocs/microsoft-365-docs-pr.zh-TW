---
title: 在 Office 365 中執行內部系統管理員接管
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
description: 瞭解如何驗證您的電子郵件和網域擁有權，以在 Office 365 中接管未受管理的租使用者
ms.openlocfilehash: 0f7932b9ba727db62f81ac15b99a5f5ca276f09f
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857400"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a>在 Office 365 中執行內部系統管理員接管

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 

如果您是系統管理員，而且想要接管自助使用者註冊所建立的非管理租使用者，您可以使用內部系統管理員接管。

> [!NOTE]
> 使用 Azure AD 的任何雲端服務註冊的自助服務，會將使用者新增至未受管理或「陰影」 Azure AD 目錄，並建立未受管理的租使用者。 未受管理的租使用者是沒有全域管理員的目錄。 若要判斷承租人是否受管理或未受管理，請參閱[決定租使用者類型](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="step-1-verify-your-email-address"></a>步驟1：確認您的電子郵件地址

> [!NOTE]
> 如果您的承租人中已啟用自助功能，使用者可以自行訂閱免費服務，例如 Power BI。 這些步驟假設自助使用者訂閱已建立您想要當作系統管理員接管的非管理租使用者。在第一個步驟中，您會在未受管理的租使用者中建立使用者內容，使用 Power BI 來說明管理接管路徑。

1. 若要註冊 power bi，請移至[power bi site](https://powerbi.com) ，然後選取 **[開始免費** > **開始免費試用版**（在與 Power BI Pro] 方塊中的 [共用]）。 

2. 使用您組織的功能變數名稱（例如`powerbiadmin@contoso.com`）註冊使用者帳戶。 若您的帳戶已在使用中，請使用您目前的密碼登入。

3. 請檢查您的電子郵件是否有**驗證碼**，並輸入驗證電子郵件地址的程式碼。
    
## <a name="step-2-create-a-new-account"></a>步驟2：建立新帳戶

1. 當您輸入驗證碼時，您會進入可讓您建立新帳戶的頁面。 
    
2. 在 [使用者名稱] 和 [密碼] 欄位中填入您要使用的帳戶，然後選取 [**啟動**]。 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>步驟3：確認網域擁有權並成為系統管理員

1. 隨即會開啟 [**管理員**] 嚮導。 如果該嚮導未啟動，請尋找 [系統**管理**] 磚，然後選取它。 

2. 選取 **[是，我要成為系統管理員]**。

3. 將 TXT 記錄新增至您的網域註冊機構，以確認您擁有要接管的網域。 嚮導將會提供您要新增的 TXT 記錄，並提供您註冊機構網站的連結，並提供逐步指示的連結。
    
4. 將 TXT 記錄新增至註冊網站後，請回到嚮導並選取 [確定] **，我已新增記錄**。
    
> [!NOTE]
> 接管陰影租使用者不會影響任何現有的資訊或服務。 不過，如果網域中的任何使用者已註冊需要授權的服務，系統就會要求您購買其授權，作為接管系統管理員角色的一部分。 您可以在系統管理員設定程式完成之後，新增或移除授權。 
  
## <a name="related-articles"></a>相關文章

Youtube：[接管 Power BI 和 Office 365 IT 系統管理員的 3 個步驟](https://www.youtube.com/watch?v=xt5EsrQBZZk) (英文)

[Azure AD 中的系統管理接管](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[取得 Office 365 網域的說明](../get-help-with-domains/get-help-with-domains.yml)

[在您的組織中使用自助註冊](self-service-sign-up.md)
  
[瞭解 Power BI 服務系統管理員角色](https://docs.microsoft.com/power-bi/service-admin-role)

