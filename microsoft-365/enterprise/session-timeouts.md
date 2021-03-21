---
title: Microsoft 365 的會話超時
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
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
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: 瞭解如何使用會話超時，以在 Microsoft 365 用戶端應用程式中平衡安全性和輕鬆存取。
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924913"
---
# <a name="session-timeouts-for-microsoft-365"></a>Microsoft 365 的會話超時

「會話週期」是 Microsoft 365 驗證的重要部分，也是平衡安全性的重要元件，以及使用者提示他們輸入認證的次數。

## <a name="session-times-for-microsoft-365-services"></a>Microsoft 365 服務的會話時間

當使用者在任何 Microsoft 365 web apps 或行動應用程式中進行驗證時，即會建立會話。 在會話期間內，使用者不需要重新驗證。 當使用者處於非使用中狀態、當使用者關閉瀏覽器或索引標籤，或其驗證權杖到期時（例如，當其密碼已重設時），會話便會到期。 Microsoft 365 服務具有不同的會話超時，以與每個服務的一般用途相對應。

下表列出 Microsoft 365 服務的會話存留時間：

| Microsoft 365 服務 | 會話超時 |
|:-----|:-----|
|Microsoft 365 系統管理中心  <br/> |系統會要求您每8小時為系統管理員提供認證。  <br/> |
|SharePoint Online  <br/> |只要使用者選擇 [ **讓我登入**]，就會有5天的非活動狀態。 如果使用者在24小時後又從先前登入的小時內重新存取 SharePoint，該超時值會重設為5天。  <br/> |
|Outlook Web App  <br/> |6小時。  <br/> 您可以使用 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) Cmdlet 中的 _ActivityBasedAuthenticationTimeoutInterval_ 參數變更此值。  <br/> |
|Azure Active Directory  <br/> 在已啟用新式驗證的 Windows 用戶端中，Office 和 Microsoft 365 應用程式所使用的 ()   <br/> | 新式驗證使用存取權杖和重新整理權杖，以使用 Azure Active Directory 授與使用者對 Microsoft 365 資源的存取權。 存取權杖是一種 JSON Web Token，可在驗證成功之後和有效1小時之後提供。 此外，也會提供較長壽命的刷新權杖。 當存取權杖到期時，Office 用戶端會使用有效的重新整理權杖來取得新的訪問權杖。 如果使用者的初始驗證仍然有效，則此 exchange 會成功。  <br/>  重新整理權杖的有效期為90天，而且連續使用，在廢除之前，其可能會有效。  <br/>  重新整理權杖可能會因下列的幾個事件而失效：  <br/>  自重新整理權杖後，使用者的密碼已變更。  <br/>  管理員可以套用條件式存取原則，以限制使用者嘗試存取之資源的存取權。  <br/> |
|針對 Android、iOS 和 Windows 10 SharePoint 和 OneDrive 行動應用程式  <br/> |存取權杖的預設週期為1小時。 更新權杖的預設最大非使用時間為90天。  <br/> [深入瞭解標記及如何設定權杖存留期](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> 若要撤銷重新整理權杖，您可以重設使用者的 Microsoft 365 密碼  <br/> |
|使用 Microsoft 365 Sign-In 的 Yammer  <br/> |瀏覽器的存留期。 若使用者關閉瀏覽器，並在新的瀏覽器中存取 Yammer，Yammer 將使用 Microsoft 365 重新驗證。 如果使用者使用可快取 cookie 的協力廠商瀏覽器，在重新開啟瀏覽器時，可能不需要重新驗證。  <br/> > [!NOTE]> 這只對使用 Microsoft 365 Sign-In for Yammer 的網路有效。           |