---
title: 將 ServiceNow 票證整合至 Microsoft 365 的安全性中心和合規性中心
description: 瞭解如何從 Microsoft 365 的安全性中心和合規性中心開始，在 ServiceNow 中建立及追蹤入場券。
keywords: 安全性，Microsoft 365，M365，合規性中心，安全性中心，ServiceNow，票證，任務，雪，connection
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: ca13234a93ffcc226be45d337880692a3a39c28b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196116"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>將 ServiceNow 票證整合至 Microsoft 365 的安全性中心和合規性中心

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


[!include[Prerelease information](../includes/prerelease.md)]

ServiceNow 是一個流行的雲端計算平臺，可協助公司管理企業作業的數位工作流程。 其 Now 平臺具有 IT 工作流程、員工工作流程和客戶工作流程。 [深入瞭解 ServiceNow](https://www.servicenow.com/)

Microsoft 已與 ServiceNow 合作，讓 IT 系統管理員可輕鬆管理這兩個平臺的票證和工作。 [Microsoft 365 的安全性中心](overview-security-center.md) 和 [microsoft 365 規範中心](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 已增強，可在 ServiceNow 中以本機方式建立及追蹤票證。

- [**管理安全性中心的 ServiceNow 票證**](tickets-security-center.md)
- **在規範中心管理 ServiceNow 入場券** (即將推出) 

## <a name="prerequisites"></a>必要條件

可以存取 Microsoft 365 的「安全中心」或「合規性中心」和 ServiceNow 實例，其中包括：  

* Kingston 或更高版本
* 具有系統管理員高認證
* 具有目標廠商實例的系統管理員許可權

ServiceNow 建議使用者將預設設定保留在 ServiceNow 實例中。 在完成安裝檢查清單並與 Microsoft 365 安全性中心整合時，讓自訂動作可能會造成錯誤。

## <a name="data-exchange"></a>資料交換

當您將 Microsoft 365 的安全性中心或規範中心連線至 ServiceNow 時，Microsoft 會收到下列額外的資料：

* ServiceNow 實例名稱
* ServiceNow 用戶端識別碼
* ServiceNow 用戶端密碼
* ServiceNow 存取 & 重新整理權杖

當您從 Microsoft 365 的「安全中心」或「合規性中心」建立 ServiceNow 票證時，會將下列資料傳送至 ServiceNow：

* 啟動票證建立的使用者識別碼
* 任務名稱
* 任務描述
* 優先順序
* 到期日
* 建議來源 (使用者建議或 Microsoft 建議) 
* 建議類別 (裝置、資料、應用程式、身分識別、基礎結構) 

## <a name="connect-to-servicenow"></a>連接至 ServiceNow

移至 [[建立並追蹤 Microsoft 365 的安全性中心的 ServiceNow 入場券](tickets-security-center.md) ]，以瞭解如何連線至 ServiceNow。 即將推出從 Microsoft 365 規範中心連線。

## <a name="troubleshooting"></a>疑難排解

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>您會在安裝檢查清單的第一個步驟中收到錯誤 (OAuth 建立) 

**錯誤訊息**：從範圍 ' x_mioms_m365ticket ' 對「oauth_entity ' 進行的讀取作業已被拒絕，因為資料表的跨範圍存取原則

應用程式假設 ServiceNow 實例上的任何系統管理員都可以建立和讀取 OAuth 實體。 此錯誤可能是由您的 ServiceNow 實例中的自訂，用以限制誰可以建立或讀取 OAuth 實體。

**ServiceNow 建議使用者保留預設功能。**

將 "應用程式註冊表" 資料表設定設為預設值：

* 標籤 = 應用程式 Registeries
* Name = oauth_entity
* 從 = 所有應用程式範圍存取
* 可讀取 = 核取方塊選取

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>如何驗證為 Microsoft 365 Security & 合規性連接器所建立的 OAuth 實體

移至應用程式註冊表表 (**功能表 > 系統 OAuth > 應用程式** 登錄) ServiceNow。 使用您所指派的名稱，尋找您所建立的 OAuth 實體。

### <a name="signing-in-as-the-integration-user"></a>以整合使用者的身分登入

在您授權 Microsoft 365 security center 和 ServiceNow 之間的連線之前，請確定您使用您在安裝步驟中建立的整合使用者登入和密碼。 請勿使用您的個人認證。

1. 前往 ServiceNow 中的 [授權] 頁面。
2. 如果您是以您的個人認證登入，請選取右上角的 [ **不** ] 連結。
3. 以您先前從安裝檢查清單建立的整合使用者身分，登入 ServiceNow。  
4. 在 [ServiceNow] 頁面中選取 [ **允許** ]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。
5. 繼續執行設定步驟。

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>如何驗證使用 Microsoft 365 Security & 合規性連接器安裝檢查清單所建立的整合使用者

移至 [使用者] 表格 ** (功能表中 > 使用者管理 > 使用者**) 在 ServiceNow 中，並尋找您所指定的整合使用者名稱。

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>您的公司啟用單一登入，可防止您透過 Microsoft 365 安全中心連線到 ServiceNow。

如果貴公司已啟用單一登入，但收到錯誤或登入失敗，請遵循這兩種方案之一。

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a>以 integration 使用者的身分登入 ServiceNow

1. 向後流覽至 ServiceNow 中的 [授權] 頁面。
2. 選取右上角的 [ **不** ] 連結。
3. 以您先前從安裝檢查清單建立的整合使用者身分，登入 ServiceNow。  
4. 在 [ServiceNow] 頁面中選取 [ **允許** ]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。
5. 繼續執行設定步驟。

#### <a name="create-a-security-admin-user"></a>建立安全性系統管理員使用者

1. 在 Azure Active Directory 中建立具有安全性系統管理員許可權的使用者。 使用者必須具有與您從安裝檢查清單中所建立的整合使用者相同的名稱和電子郵件地址。 登入和連線完成後，您就可以移除安全性系統管理員角色。
2. 請以此使用者身分登入 Microsoft 365 安全中心，然後執行安裝步驟。

### <a name="ip-filtering"></a>IP 篩選

如果您已啟用 IP 篩選，您可能需要明確允許 IP 位址。 如需如何在 ServiceNow 中允許 IP 範圍的資訊，請參閱 [IP 位址存取控制](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) 。 請參閱 [AZURE Ip 範圍和服務標籤-公用雲端](https://www.microsoft.com/en-us/download/details.aspx?id=56519) 以取得允許的 IP 位址清單。

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>安裝已完成，但看不到票證，而且無法共用

如果已完成安裝和設定步驟，但是您沒有在首頁上看到 ServiceNow 卡片，而且無法從 Microsoft 安全分數 ServiceNow 共用，請檢查 [布建] 頁面的狀態 https://security.microsoft.com/ticketProvisioning 。 選取 [ **授權** ]，然後回到首頁。 應該會出現卡。

## <a name="resources"></a>資源

- [管理安全性中心的 ServiceNow 票證](tickets-security-center.md)
