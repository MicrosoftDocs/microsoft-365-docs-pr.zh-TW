---
title: 建立並追蹤透過 ServiceNow 票證
description: Microsoft 365 安全性中心正在增強原本建立並追蹤票證中 ServiceNow 的能力。 安全性系統管理員可以直接傳送 ServiceNow 安全分數建議，並建立票證。
keywords: 安全性，Microsoft 365，M365，安全分數，安全性中心、 ServiceNow、 票證，工作
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
ms.openlocfilehash: 240e153c43c7dc52d67d35eeca36def2f76b08e2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086920"
---
# <a name="manage-tickets-through-servicenow"></a>透過 ServiceNow 管理票證

Microsoft 365 安全性中心正在增強原本建立並追蹤票證中 ServiceNow 的能力。 安全性系統管理員可以直接傳送 ServiceNow [Microsoft 安全分數](microsoft-secure-score.md)改進巨集指令，並建立票證。 您可以建立兩個事件管理和變更管理票證。

## <a name="prerequisites"></a>必要條件

可以在 Microsoft 365 安全性中心及以 ServiceNow 執行個體的存取：  

* Kingston 或更高版本
* 具有系統管理員 HI 認證
* 在您的目標廠商執行個體上有系統管理員權限

ServiceNow 建議使用者保留預設設定，您 ServiceNow 執行個體中。 具有自訂項目可能會造成錯誤，完成安裝檢查清單並與 Microsoft 365 安全性中心整合時。

## <a name="data-exchange"></a>資料交換

當您在 Microsoft 365 安全性中心連線至 ServiceNow 時，Microsoft 會收到下列額外的資料：

* ServiceNow 執行個體名稱
* ServiceNow 用戶端識別碼
* ServiceNow 用戶端密碼
* ServiceNow 存取 & 重新整理權杖

當您從 Microsoft 365 安全性中心建立 ServiceNow 票證時，下列資料傳送至 ServiceNow:

* 初始化票證架設的使用者識別碼
* 任務名稱
* 工作描述
* 優先順序
* 到期日
* 建議來源 （使用者建議或 Microsoft 建議）
* 建議類別 （裝置、 資料、 應用程式、 身分識別、 基礎結構）

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>連線至 ServiceNow 的 Microsoft 365 安全中心

瀏覽至 Microsoft 365 安全性中心首頁上，若要查看 ServiceNow 連線卡片。

![您使用 ServiceNow 嗎](../../media/do-you-use-servicenow-250.png)

選取 「 連線至 ServiceNow 」 移至 [ServiceNow 安裝程式] 頁面上。 依照指示授權的 Microsoft 365 連接器應用程式。

> [!NOTE]
> 授權 Microsoft 365 安全性中心與 ServiceNow 之間的連線之前，請確定您使用的整合使用者登入與您在安裝步驟中建立的密碼。 請勿使用個人的認證。

您必須遵循指示和授權連線之後，檢視連線狀態，在這兩個 Microsoft 365 安全性中心連線] 頁面上和 ServiceNow Microsoft 365 面臨連接器應用程式的經驗。 現在您所有設為啟動建立工作 ！

## <a name="create-a-task-and-share-it-to-servicenow"></a>建立工作和分享 ServiceNow

一旦設定整合時，建立 ServiceNow 工作根據 Microsoft 安全分數改進的特定動作。 移至任何改進巨集指令中安全分數的 Microsoft 365 安全性中心入口網站中，並選取 「 共用 」 圖示。 其中一個下拉式清單選項是 ServiceNow。

![ServiceNow 共用安全分數](../../media/servicenow-share.png)

您可以在其中設定優先順序及編輯名稱、 描述、 或到期日，就會產生一項工作。 一旦所有必要的欄位中填滿，將工作傳送至 ServiceNow。

任務是顯示在 ServiceNow 做為 Microsoft 365 安全性和組態變更要求。

## <a name="track-tickets"></a>追蹤票證

一旦 ServiceNow 變更 」 管理模型，並已建立附隨管理票證，它們會顯示在 Microsoft 365 安全性中心首頁的卡片上。 從這些卡] 底下，您可以建立票證、 檢視所有票證，或管理 ServiceNow 組態。

![ServiceNow 變更管理票證](../../media/change-management-375.png)  ![ServiceNow 附隨管理票證](../../media/incident-management-375.png)

若要重新佈建或管理 Microsoft 365 安全性中心您 ServiceNow 整合，請選取**管理 ServiceNow 設定**上的卡片。 從那裡，移除目前的 ServiceNow 連線和自訂票證狀態名稱。

ServiceNow 票證可見 Microsoft 365 安全中心內與您的任務 live 就地其中他們可追蹤並處理時，以及其他安全性儀表板的項目。

## <a name="troubleshooting"></a>疑難排解

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>安裝檢查清單 （OAuth 建立） 的第一個步驟中收到錯誤訊息

**錯誤訊息**： 讀取作業對 'oauth_entity' 從範圍 'x_mioms_m365ticket' 已拒絕因為該資料表的跨範圍存取原則

應用程式假設 ServiceNow 執行個體上的任何系統管理員可以建立及讀取 OAuth 實體。 由於 ServiceNow，這會限制可以建立/讀取 OAuth 實體執行個體上的自訂，可能會發生這個錯誤。

**ServiceNow 建議使用者保留預設功能。**

設定 「 應用程式登錄 」 資料表設定為預設值：

* 標籤 = 應用程式 Registeries
* 名稱 = oauth_entity
* 從存取 = 應用程式的所有範圍
* 可以讀取 = 選取核取方塊

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>如何驗證建立 Microsoft 365 安全性 & 規範連接器的 OAuth 實體

前往 [ServiceNow 中的 [應用程式登錄表格 (**功能表 > 系統 OAuth > Application Registry**)，並找出您建立的您將其指派的名稱與 OAuth 實體。

### <a name="logging-in-as-the-integration-user"></a>整合使用者身分登入

授權 Microsoft 365 安全性中心與 ServiceNow 之間的連線之前，請確定您使用的整合使用者登入與您在安裝步驟中建立的密碼。 請勿使用個人的認證。

1. 移 ServiceNow 中的 [授權] 頁面。
2. 如果您已登入您個人的認證，選取 [**不是您**連結中右上角。
3. 您先前建立的安裝檢查清單從整合使用者身分登入 ServiceNow。  
4. 在詢問安全性 + 規範連接器可以連線到您 ServiceNow 帳戶 ServiceNow] 頁面上，選取 [**允許**。
5. 繼續進行設定的步驟。

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>如何驗證整合使用者建立與 Microsoft 365 安全性 & 規範連接器的安裝檢查清單

前往 [Users Table **(功能表 > 使用者管理 > 使用者**) 中 ServiceNow] 和 [尋找整合使用者所建立，與您指派的名稱。

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>您的公司具有單一登入已啟用阻止您連線至 ServiceNow 透過 Microsoft 365 安全中心

如果貴公司已啟用單一登入，您會收到錯誤或登入未成功，請遵循下列其中一個兩個解決方案。

#### <a name="log-into-servicenow-as-the-integration-user"></a>整合使用者身分登入 ServiceNow

1. 瀏覽回 ServiceNow 中的 [授權] 頁面上。
2. 選取 [**不是您**連結中右上角。
3. 您先前建立的安裝檢查清單從整合使用者身分登入 ServiceNow。  
4. 在詢問安全性 + 規範連接器可以連線到您 ServiceNow 帳戶 ServiceNow] 頁面上，選取 [**允許**。
5. 繼續進行設定的步驟。

#### <a name="create-a-security-admin-user"></a>建立安全性系統管理使用者

1. 建立使用者具有安全性系統管理員權限在 Azure Active Directory 中。 使用者必須與您建立安裝檢查清單從整合使用者具有相同的名稱和電子郵件地址。 一旦登入和連線完成後，您可以移除安全性系統管理員角色。
2. 登入為此使用者在 Microsoft 365 安全性管理中心並遵循設定步驟。

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>安裝完成時，但看不到票證，而且無法共用

如果已完成的安裝和設定步驟，但您看不到 ServiceNow 卡在首頁上，而且無法共用 ServiceNow 要從 Microsoft 安全分數，檢查狀態的佈建頁面上的https://security.microsoft.com/ticketProvisioning。 選取 [**授權]，** 並返回 [首頁] 頁面。 卡應該會出現。

