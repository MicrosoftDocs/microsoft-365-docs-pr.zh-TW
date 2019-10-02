---
title: 建立並追蹤透過 ServiceNow 票證
description: Microsoft 365 安全性中心正在增強原本建立並追蹤票證中 ServiceNow 的能力。 這可讓安全性管理員安全分數建議直接傳送到 ServiceNow 並建立票證。
keywords: 安全性，Microsoft 365，M365，安全分數，安全性中心、 ServiceNow、 票證，工作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350326"
---
# <a name="manage-tickets-through-servicenow"></a>管理透過 ServiceNow 票證

Microsoft 365 安全性中心正在增強原本建立並追蹤票證中 ServiceNow 的能力。 這可讓[Microsoft 安全分數](microsoft-secure-score.md)改進巨集指令直接傳送到 ServiceNow 並建立票證安全性系統管理員。 您可以建立兩個事件管理和變更管理票證。

## <a name="prerequisites"></a>必要條件

可以在 Microsoft 365 安全性中心及以 ServiceNow 執行個體的存取：  

* Kingston 或更高版本
* 具有系統管理員 HI 認證
* 在您的目標廠商執行個體上有系統管理員權限

ServiceNow 建議使用者保留超出] 方塊中的設定 （預設值） ServiceNow 執行個體。  具有自訂項目可能會造成錯誤中完成安裝檢查清單並與 Microsoft 365 安全性中心整合。

## <a name="data-exchange"></a>資料交換

當您在 Microsoft 365 安全性中心連線至 ServiceNow 時，Microsoft 將會收到下列額外的資料：

* ServiceNow 執行個體名稱
* ServiceNow 用戶端識別碼
* ServiceNow 用戶端密碼
* ServiceNow 存取 & 重新整理權杖

當您建立 ServiceNow 票證從 Microsoft 365 安全性中心下列資料傳送至 ServiceNow:

* 初始化票證架設的使用者識別碼
* 任務名稱
* 工作描述
* 優先順序
* 到期日
* 建議來源 （使用者建議或 Microsoft 建議）
* 建議類別 （裝置、 資料、 應用程式、 身分識別、 基礎結構）

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>連線至 ServiceNow 的 Microsoft 365 安全中心

瀏覽至 Microsoft 365 安全性中心首頁上，您會在其中看到詢問是否您使用 ServiceNow 卡片。

![您使用 ServiceNow 嗎](../images/do-you-use-servicenow-250.png)

從這裡您將會傳送至設定] 頁面上，您會依照授權的 Microsoft 365 連接器應用程式的指示 ServiceNow。

當授權 Microsoft 365 安全性中心與 ServiceNow 之間的連線，請確定您使用整合使用者登入和密碼剛才在安裝步驟並不是您個人的認證。

之後的下列指示和授權的連線，您可以檢視連線狀態，這兩個 Microsoft 365 安全性中心連線] 頁面上和在 ServiceNow Microsoft 365 面臨連接器 App 體驗。 現在您所有設為啟動建立工作 ！

## <a name="create-a-task-and-share-it-to-servicenow"></a>建立工作和分享 ServiceNow

一旦設定整合時，您可以建立 ServiceNow 工作根據 Microsoft 安全分數改進的特定動作。 移至任何改進巨集指令中安全分數的 Microsoft 365 安全性中心入口網站中，並選取 「 共用 」 圖示。 其中一個下拉式清單選項是 ServiceNow。

![ServiceNow 共用安全分數](../images/servicenow-share.png)

您可以在其中設定優先順序及編輯名稱、 描述、 或到期日，然後就會產生一項工作。 一旦所有必要的欄位已填入，您可以傳送工作給 ServiceNow。

工作會顯示在 ServiceNow 做為 Microsoft 365 安全性和組態變更要求。

## <a name="track-tickets"></a>追蹤票證

一旦 ServiceNow 變更 」 管理模型，並已建立附隨管理票證，則會顯示在 Microsoft 365 安全性中心首頁的卡片上。 從這些卡] 底下，您可以建立票證、 檢視所有票證，或管理 ServiceNow 組態。

![ServiceNow 變更管理票證](../images/change-management-375.png)  ![ServiceNow 附隨管理票證](../images/incident-management-375.png)

若要重新佈建或管理 Microsoft 365 安全性中心您 ServiceNow 整合，請選取**管理 ServiceNow 設定**上的卡片。 從該處可以移除目前的 ServiceNow 連線和自訂票證狀態名稱。

ServiceNow 票證可見 Microsoft 365 安全中心內與您的工作會 live 就地其中他們可追蹤並處理時，以及其他安全性儀表板的項目。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>我在安裝檢查清單 （OAuth 建立） 的第一個步驟中收到錯誤

**錯誤訊息**： 讀取作業對 'oauth_entity' 從範圍 'x_mioms_m365ticket' 已拒絕因為該資料表的跨範圍存取原則

我們 app 假設 ServiceNow 執行個體上的任何系統管理員可以建立及讀取 OAuth 實體。 由於 ServiceNow，這會限制可以建立/讀取 OAuth 實體執行個體上的自訂，可能會發生這個錯誤。 ServiceNow 建議使用者保留超出方塊的功能 （預設值）。

設定 「 應用程式登錄 」 資料表設定為預設值：

* 標籤 = 應用程式 Registeries
* 名稱 = oauth_entity
* 從存取 = 應用程式的所有範圍
* 可以讀取 = 選取核取方塊

**ServiceNow 建議使用者保留超出方塊的功能 （預設值）。**

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>如何驗證 OAuth 實體建立 Microsoft 365 安全性 & 規範連接器？

前往 [ServiceNow 中的 [應用程式登錄表格 (功能表 > 系統 OAuth > Application Registry)，並找出您 （您指派的名稱） 所建立的 OAuth 實體。

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a>如何驗證 Microsoft 365 安全性 & 規範連接器安裝檢查清單的兩個步驟中建立之整合使用者？

前往 ServiceNow 中的使用者表格 (功能表 > 使用者管理 > 使用者)，並找出整合使用者建立由您 （您指派的名稱）。

當授權 Microsoft 365 安全性中心與 ServiceNow 之間的連線，請確定您使用整合使用者登入和密碼剛才在安裝步驟並不是您個人的認證。

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a>我已完成安裝和設定步驟，但我無法看到 ServiceNow 卡在首頁上，而且無法看到 Microsoft 安全分數的共用圖示

檢查 [佈建] 頁面上的狀態移至https://security.microsoft.com/ticketProvisioning。 選取 [**儲存**]，並回到 [首頁] 頁面上。 卡應該會出現。
