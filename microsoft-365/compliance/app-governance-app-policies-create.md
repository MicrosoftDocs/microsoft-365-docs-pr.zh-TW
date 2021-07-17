---
title: 建立應用程式原則
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 建立應用程式原則。
ms.openlocfilehash: 66d8dda7c9cd768d6971e2b58dca4c9c5437e5bb
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438057"
---
# <a name="create-app-policies"></a>建立應用程式原則

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

除了偵測異常應用程式行為並產生警示的內建功能集外，Microsoft 應用程式控管中的應用程式原則也是一種您可以：

- 指定應用程式控管可警示您應用程式行為的條件，以進行自動或手動補救。
- 為貴組織實作應用程式合規性原則。

您可以從提供的範本建立可自訂的應用程式原則，也可以建立自己的自訂應用程式原則。

若要建立新的應用程式原則，請前往 **[Microsoft 365 合規性中心] > [應用程式控管] > [概觀頁面] > [原則]**：

- 若要使用針對應用程式使用量設計的範本，來建立新的應用程式原則，請選取 **[建立原則]** 下的 **[建立應用程式使用量原則]**。
- 若要使用針對應用程式權限設計的範本，來建立新的應用程式原則，請選取 **[建立原則]** 下的 **[建立權限原則]**。
- 若要為應用程式認證或自訂原則建立新的應用程式，請選取 **[新建]**。

## <a name="app-policy-templates"></a>應用程式原則範本

若要根據應用程式原則範本建立新的應用程式原則，請在 **[選擇應用程式原則範本頁面]** 上，選取應用程式範本的類別、選取範本的名稱，然後選取 **[下一步]**。

應用程式控管有三種應用程式原則範本類別。

### <a name="app-users-and-data-access"></a>應用程式使用者與資料存取

應用程式控管包含這些範本，以產生應用程式使用量的警示。

| 範本名稱 | 描述 |
|:-------|:-----|
| 具有大量資料存取權限的新應用程式 | 醒目提示任何存取大量資料的最近註冊之應用程式，以確保這些資料模式是預期的。 <br><br> 根據預設，此原則會標出過去 7 天內註冊且在這一期間具有超過 1 GB 資料存取的所有應用程式。 此原則可以自訂更多條件和動作。 |
|||

### <a name="app-permissions"></a>應用程式權限

應用程式控管包含這些範本，以產生應用程式權限的警示。

| 範本名稱 | 描述 |
|:-------|:-----|
| 權限過高的應用程式 | 醒目提示任何被授與高於其實際使用的權限的應用程式，以識別潛在的降低權限的機會。 <br><br> 根據預設，如果 90 天內未使用，此原則會標出標示為權限過高的所有應用程式。 此時間間隔篩選可以自訂更多條件和動作。 |
| 具有高權限的新應用程式 | 醒目提示所有具有高權限的新應用程式，以識別可能需要進一步調查的潛在高磁碟使用量應用程式。 <br><br> 根據預設，此原則會標幟在過去 7 天內註冊並具有高範圍權限的所有應用程式。 |
|||

### <a name="app-certification"></a>應用程式認證

應用程式控管包含這些範本，以產生應用程式認證的警示。

| 範本名稱 | 描述 |
|:-------|:-----|
| 新的未認證應用程式 | 醒目提示尚未經過應用程式認證程序的新應用程式，以確保在租用戶中預期它的存在。 <br><br> 根據預設，此原則會標幟在過去 7 天內註冊並尚未認證的所有應用程式。 |
|||

## <a name="custom-app-policies"></a>自訂應用程式原則

當您需要執行尚未由其中一個內建範本完成的工作時，請使用自訂應用程式原則。

若要建立新自訂應用程式原則，請先選取 **[原則]** 頁面中的 **[建立新的]**。 在 **[選擇應用程式原則範本頁面]** 上，選取 **[自訂]** 類別、**[自訂原則]** 範本，然後選取 **[下一步]**。

在 **[名稱與訂閱]** 頁面上，設定下列項目：

- 原則名稱

- 原則描述

- 選取設定此原則所產生警示嚴重性之原則嚴重性。

  - 高
  - 中
  - 低

在 **[選擇原則設定和條件]** 頁面上，針對 **[選擇此原則適用的應用程式]**，選取：

- 所有應用程式
- 選擇特定應用程式

  窗格可讓您選取一或多個應用程式。
  選取 **[新增]**。

選取 **[下一步]**。

在 **[選擇原則設定和條件]** 頁面上，選取 **[設定原則的新條件]**，然後選取 **[下一步]**。

**[建立規則]** 窗格可讓您選取新規則的條件。 選取 **[新增條件]**，然後從條件清單中選取，然後指定條件的值。 您可以新增多個條件。

以下是自訂應用程式原則的可用條件。

|條件 | 已接受條件值 | 詳細資訊 |
|:-------|:-----|:-------|
| 應用程式註冊年齡 | 在過去 X 天內 |  |
| 應用程式認證 | 基本合規性、MCAS 合規性或 N/A | [Microsoft 365 認證](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| 發行者驗證 | 是或否 | [發行者驗證](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| 應用程式權限 | 從清單中選取一或多個 API 權限。 | [Microsoft Graph 權限參考資料](https://docs.microsoft.com/graph/permissions-reference) |
| 委派的權限 | 從清單中選取一或多個 API 權限。 | [Microsoft Graph 權限參考資料](https://docs.microsoft.com/graph/permissions-reference) |
| 高權限 | 是或否 | 這是根據 MCAS 使用之相同邏輯的內部職銜。 |
| 權限過高的應用程式 | 是或否 | 授與比這些應用程式使用權限更多的應用程式。 |
| 應用程式資料存取 | 每小時資料存取大於 X GB |  |
| 應用程式資料存取趨勢 | 過去 7 天的資料使用量增加 X% |  |
| 應用程式 API 存取 | 每小時 API 呼叫大於 X |  |
| 應用程式 API 存取趨勢 | 過去 7 天的 API 呼叫增加 X%     |  |
| 使用者已同意 | (大於或小於) X 已同意的使用者 |  |
| 已同意的優先使用者 | 是或否 | 具有[優先帳戶](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)的使用者。 |
| 應用程式同意者 | 從清單中選取使用者 |  |
| 同意使用者的角色 | 選取一或多個：Teams 系統管理員、目錄讀取者、安全性讀取者、合規性系統管理員、安全性系統管理員、服務台系統管理員、SharePoint 系統管理員、Exchange 系統管理員、全域讀取者、全域系統管理員、合規性資料系統管理員、使用者系統管理員、服務支援系統管理員 | 已允許多個選取項目。 <br><br> 此清單中應提供具有受指派成員的任何 Azure AD 角色。 |
| 已存取的工作負載 | OneDrive 和/或 SharePoint 和/或 Exchange | 已允許多個選取項目。 |
| 錯誤率 | 過去 7 天的錯誤率大於 X%，其中 X 是系統管理員定義的值 |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

必須符合所有指定的條件，才能套用此應用程式原則。

當您完成指定條件時，請選取 **[儲存]**，然後選取 **[下一步]**。

在 **[定義原則動作]** 頁面上，如果您希望應用程式控管在根據此原則產生警示時停用應用程式，請選取 **[停用應用程式]**，然後選取 **[下一步]**。

在 **[定義原則狀態]** 頁面，選取其中一個選項：

- **[稽核模式]**：會評估原則，但不會發生已設定的動作。 稽核模式原則會顯示在清單中的 **[稽核]** 狀態。
- **[作用中]**：會評估原則，並會發生已設定的動作。
- **[非作用中]**：不會評估原則，且不會發生已設定的動作。

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a>測試並監視您的新應用程式原則

現在您的應用程式原則已建立，您應該在 **[原則]** 頁面上監視它，以確保它在測試期間登錄預期的作用中警示數目和警示總數。 

![在 Microsoft 365 合規性中心中，具有醒目提示原則的 MAPG 原則摘要頁面。](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

如果警示數目是意外的低值，請編輯應用程式原則的設定，確保您在設定其狀態之前已正確設定。

以下是建立新原則、進行測試，然後讓新原則成為作用中之程序範例：

1. 建立新原則，將嚴重性、應用程式、條件和動作設定為初始值，且狀態設定為 **[稽核模式]**。
2. 檢查預期的行為，例如已產生的警示。
3. 如果不是預期的行為，請根據需要編輯原則應用程式、條件和動作設定，並返回步驟 2。
4. 如果這是預期的行為，請編輯該原則，並將其狀態變更為 **[作用中]**。

![建立應用程式原則工作流程](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a>下一個步驟

[管理您的應用程式原則。](app-governance-app-policies-manage.md)
