---
title: 透過 ServiceNow 建立及追蹤入場券
description: Microsoft 365 security center 已增強，可在 ServiceNow 中以本機方式建立及追蹤票證。 安全性管理員可以直接傳送安全得分建議，以 ServiceNow 及建立票證。
keywords: 安全性，Microsoft 365，M365，安全分數，安全性中心，ServiceNow，票證，任務
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
ms.openlocfilehash: eb6af6b11d2d932f3bd2165aa3f597c14feb5ae8
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901019"
---
# <a name="manage-tickets-through-servicenow"></a>透過 ServiceNow 管理票證

ServiceNow 是一個流行的雲端計算平臺，可協助公司管理企業作業的數位工作流程。 其 Now 平臺具有 IT 工作流程、員工工作流程和客戶工作流程。 Microsoft 已與 ServiceNow 合作，讓 IT 系統管理員可輕鬆管理這兩個平臺的票證和工作。 [深入瞭解 ServiceNow](https://www.servicenow.com/)

Microsoft 365 的安全性中心現在已增強，可在 ServiceNow 中以本機方式建立及追蹤票證。 安全性管理員可以直接傳送[Microsoft Secure 得分](microsoft-secure-score.md)改進動作來 ServiceNow 和建立票證。 您可以建立事件管理和變更管理票證。 然後，您可以在 Microsoft 的「安全性中心」首頁中追蹤它們，然後 ServiceNow。

## <a name="prerequisites"></a>必要條件

可以存取 Microsoft 365 security center 和 ServiceNow 實例，其具有：  

* Kingston 或更高版本
* 具有系統管理員高認證
* 具有目標廠商實例的系統管理員許可權

ServiceNow 建議使用者將預設設定保留在 ServiceNow 實例中。 在完成安裝檢查清單並與 Microsoft 365 安全性中心整合時，讓自訂動作可能會造成錯誤。

## <a name="data-exchange"></a>資料交換

當您將 Microsoft 365 的安全性中心連線至 ServiceNow 時，Microsoft 會收到下列其他資料：

* ServiceNow 實例名稱
* ServiceNow 用戶端識別碼
* ServiceNow 用戶端密碼
* ServiceNow 存取 & 重新整理權杖

當您從 Microsoft 365 security center 建立 ServiceNow 票證時，下列資料會傳送至 ServiceNow：

* 啟動票證建立的使用者識別碼
* 任務名稱
* 任務描述
* 優先順序
* 到期日
* 建議來源（使用者建議或 Microsoft 建議）
* 建議類別（裝置、資料、應用程式、身分識別、基礎結構）

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>將 Microsoft 365 的安全性中心連線至 ServiceNow

流覽至 Microsoft 365 的「安全性中心」首頁，以查看 ServiceNow 連接卡。

![您使用 ServiceNow](../../media/do-you-use-servicenow-250.png)

選取 [連線至 ServiceNow] 以移至 [ServiceNow 設定] 頁面。 依照指示授權 Microsoft 365 連接器應用程式。

> [!NOTE]
> 在您授權 Microsoft 365 security center 和 ServiceNow 之間的連線之前，請確定您使用您在安裝步驟中建立的整合使用者登入和密碼。 請勿使用您的個人認證。

在您遵循指示和授權連線之後，請在 Microsoft 365 [安全性中心] 連線頁面和 ServiceNow Microsoft 365 票證發放連接器應用程式體驗中查看線上狀態。 現在，您已全部設定為開始建立任務！

## <a name="create-a-task-and-share-it-to-servicenow"></a>建立任務並將其共用至 ServiceNow

整合設定後，根據特定的 Microsoft 安全分數改進動作建立 ServiceNow 工作。 請移至 Microsoft 365 安全性中心入口網站中安全評分的任何改進動作，然後選取「共用」圖示。 其中一個 dropdown 選項是 ServiceNow。

![ServiceNow 在安全分數中共用](../../media/servicenow-share.png)

工作會產生，您可以在其中設定優先順序及編輯名稱、描述或到期日。 填寫所有必要欄位後，將工作傳送至 ServiceNow。

這項工作會顯示在 ServiceNow 成為 Microsoft 365 安全性和設定變更要求。

## <a name="track-tickets"></a>追蹤票據

一旦 ServiceNow 變更管理和事件管理票證已建立，便會顯示在 Microsoft 365 安全中心首頁的卡片上。 您可以從這些卡片建立票證、查看所有票證或管理 ServiceNow 設定。

![ServiceNow 變更管理票證](../../media/change-management-375.png)  ![ServiceNow 事件管理票證](../../media/incident-management-375.png)

若要在 Microsoft 365 的安全性中心重新布建或管理您的 ServiceNow 整合，請選取 [管理任何卡片上的**ServiceNow**設定]。 從那裡移除目前的 ServiceNow 連線，並自訂票證狀態名稱。

使用 Microsoft 365 security center 中顯示的 ServiceNow 入場券，您的工作可以在一個位置進行追蹤，並依據其他安全性儀表板專案進行處理。

## <a name="troubleshooting"></a>疑難排解

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>安裝檢查清單（OAuth 建立）的第一個步驟中收到錯誤

**錯誤訊息**：針對來自範圍 ' x_mioms_m365ticket ' 的「oauth_entity ' 的讀取作業已遭到拒絕，因為資料表的跨範圍存取原則

應用程式假設 ServiceNow 實例上的任何系統管理員都可以建立和讀取 OAuth 實體。 這項錯誤可能是由於您的 ServiceNow 實例的自訂專案所造成，其可限制誰可以建立/讀取 OAuth 實體。

**ServiceNow 建議使用者保留預設功能。**

將 "應用程式註冊表" 資料表設定設為預設值：

* 標籤 = 應用程式 Registeries
* Name = oauth_entity
* 從 = 所有應用程式範圍存取
* 可讀取 = 核取方塊選取

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>如何驗證為 Microsoft 365 Security & 合規性連接器所建立的 OAuth 實體

移至 ServiceNow 中的 [應用程式註冊表（**功能表 > 系統 OAuth > 應用程式**登錄）]，並使用您指派它的名稱，尋找您所建立的 OAuth 實體。

### <a name="logging-in-as-the-integration-user"></a>以 integration 使用者的身分登入

在您授權 Microsoft 365 security center 和 ServiceNow 之間的連線之前，請確定您使用您在安裝步驟中建立的整合使用者登入和密碼。 請勿使用您的個人認證。

1. 前往 ServiceNow 中的 [授權] 頁面。
2. 如果您是以您的個人認證登入，請選取右上角的 [**不**] 連結。
3. 以您先前從安裝檢查清單建立的整合使用者身分登入 ServiceNow。  
4. 在 [ServiceNow] 頁面中選取 [**允許**]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。
5. 繼續執行設定步驟。

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>如何驗證使用 Microsoft 365 Security & 合規性連接器安裝檢查清單所建立的整合使用者

移至 ServiceNow 中的 [使用者] 表格 **（[功能表 > 使用者管理 > 使用者**）]，並尋找您用來指定的整合使用者名稱。

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>您的公司啟用單一登入，可防止您透過 Microsoft 365 安全中心連線到 ServiceNow。

如果貴公司已啟用單一登入，但收到錯誤或登入失敗，請遵循這兩種方案之一。

#### <a name="log-into-servicenow-as-the-integration-user"></a>以 integration 使用者的身分登入 ServiceNow

1. 向後流覽至 ServiceNow 中的 [授權] 頁面。
2. 選取右上角的 [**不**] 連結。
3. 以您先前從安裝檢查清單建立的整合使用者身分登入 ServiceNow。  
4. 在 [ServiceNow] 頁面中選取 [**允許**]，詢問安全性 + 合規性連接器是否可以連線至您的 ServiceNow 帳戶。
5. 繼續執行設定步驟。

#### <a name="create-a-security-admin-user"></a>建立安全性系統管理員使用者

1. 在 Azure Active Directory 中建立具有安全性系統管理員許可權的使用者。 使用者必須具有與您從安裝檢查清單中所建立的整合使用者相同的名稱和電子郵件地址。 登入和連線完成後，您就可以移除安全性系統管理員角色。
2. 以此使用者的身分登入 Microsoft 365 安全中心，然後依照設定步驟進行。

### <a name="ip-filtering"></a>IP 篩選

如果您已啟用 IP 篩選，您可能需要明確允許 IP 位址。 如需如何在 ServiceNow 中允許 IP 範圍的資訊，請參閱[IP 位址存取控制](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html)。 請參閱[AZURE Ip 範圍和服務標籤-公用雲端](https://www.microsoft.com/en-us/download/details.aspx?id=56519)以取得允許的 IP 位址清單。

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>安裝已完成，但看不到票證，而且無法共用

如果已完成安裝和設定步驟，但是您沒有在首頁上看到 ServiceNow 卡片，而且無法從 Microsoft 安全分數 ServiceNow 共用，請檢查 [布建] 頁面的狀態https://security.microsoft.com/ticketProvisioning。 選取 [**授權**]，然後回到首頁。 應該會出現卡。

