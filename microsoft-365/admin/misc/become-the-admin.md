---
title: 執行內部系統管理員接管
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
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
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 瞭解如何驗證您的電子郵件和網域擁有權，以接管由自助使用者登錄 Microsoft 365 所建立的非管理租使用者。
ms.openlocfilehash: aa44023ffdc2b59e4db024706323c5b872566260
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635983"
---
# <a name="perform-an-internal-admin-takeover"></a>執行內部系統管理員接管

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。 

如果您是系統管理員，而且想要接管自助使用者註冊所建立的非管理租使用者，您可以使用內部系統管理員接管。

> [!NOTE]
> 使用 Azure AD 的任何雲端服務註冊的自助服務，會將使用者新增至未受管理或「陰影」 Azure AD 目錄，並建立未受管理的租使用者。 未受管理的租使用者是沒有全域管理員的目錄。 若要判斷承租人是否受管理或未受管理，請參閱 [決定租使用者類型](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="step-1-verify-your-email-address"></a>步驟1：確認您的電子郵件地址

> [!NOTE]
> 如果您的承租人中已啟用自助，使用者可以自行訂閱免費服務，例如 Power BI。 這些步驟假設自助使用者訂閱已建立您想要當作系統管理員接管的非管理租使用者。在第一個步驟中，您會在未受管理的承租人中建立使用者內容，使用 Power BI 來說明管理接管路徑。

1. 若要註冊 Power BI，請移至 [Power BI 網站](https://powerbi.com)，然後選取 [與 Power BI Pro 方塊共用] 方塊中的 [**開始免費**  >  **開始免費試用版** (]) 。 

2. 使用組織的功能變數名稱 (，如) ，註冊使用您組織的功能變數名稱的使用者帳戶 `powerbiadmin@contoso.com` 。 若您的帳戶已在使用中，請使用您目前的密碼登入。

3. 請檢查您的電子郵件是否有 **驗證碼** ，並輸入驗證電子郵件地址的程式碼。
    
## <a name="step-2-create-a-new-account"></a>步驟2：建立新帳戶

1. 當您輸入驗證碼時，您會進入可讓您建立新帳戶的頁面。 
    
2. 在 [使用者名稱] 和 [密碼] 欄位中填入您要使用的帳戶，然後選取 [ **啟動**]。 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>步驟3：確認網域擁有權並成為系統管理員

1. 隨即會開啟 [ **管理員** ] 嚮導。 如果該嚮導未啟動，請尋找 [系統 **管理** ] 磚，然後選取它。 

2. 選取 **[是，我要成為系統管理員]**。

3. 將 TXT 記錄新增至您的網域註冊機構，以確認您擁有要接管的網域。 嚮導將會提供您要新增的 TXT 記錄，並提供您註冊機構網站的連結，並提供逐步指示的連結。
    
4. 將 TXT 記錄新增至註冊網站後，請回到嚮導並選取 [確定] **，我已新增記錄**。
    
> [!NOTE]
> 接管陰影租使用者不會影響任何現有的資訊或服務。 不過，如果網域中的任何使用者已註冊需要授權的服務，系統就會要求您購買其授權，作為接管系統管理員角色的一部分。 您可以在系統管理員設定程式完成後，購買或移除授權。
  
## <a name="related-content"></a>相關內容

YouTube：[針對 Power BI 和 Microsoft 365 (影片進行 IT 系統管理員接管的3個步驟](https://www.youtube.com/watch?v=xt5EsrQBZZk)) \
[AZURE AD 中的系統管理接管](/azure/active-directory/users-groups-roles/domains-admin-takeover) (文章) \
[在您的組織中使用「自助註冊](self-service-sign-up.md) 」 (文章) \
[瞭解 Power BI 服務系統管理員角色](/power-bi/service-admin-role) (文章) 