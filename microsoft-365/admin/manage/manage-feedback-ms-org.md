---
title: 管理貴組織的 Microsoft 意見反應
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 管理您的使用者可以傳送給 Microsoft 有關 Microsoft 產品的意見反應。
ms.openlocfilehash: 70ea1d5c176dd603f6a5addb09356909f13f9ace
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840667"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>管理貴組織的 Microsoft 意見反應

在 Microsoft 365 組織的系統管理員中，現在有數個原則可協助您在使用 Microsoft 365 應用程式時，管理意見反應收集和使用者的客戶參與經驗。 您可以在組織中建立及使用每個原則的現有 Azure Active directory 群組。 透過這些原則，您可以控制組織中的不同部門如何傳送意見反應給 Microsoft。 Microsoft 會審查所有客戶提交的意見反應，並使用這種意見反應來改進產品。 開啟回應資訊 **時，可讓您** 查看使用者對所使用之 Microsoft 產品的評價。 我們從您的使用者收集的意見反應很快就會出現在 Microsoft 365 系統管理中心。

若要深入瞭解意見類型及 Microsoft 如何使用使用者意見反應，請參閱 [瞭解 microsoft 對您組織的意見](../misc/feedback-user-control.md)。

下表代表哪些應用程式和服務目前已連接至下一個意見反應原則表格中所示的意見反應原則。 如需螢幕擷取畫面範例，請參閱下表。

|**應用程式 & 服務**|**產品內意見反應** <br> |**產品內調查** <br> |**元資料集合** <br> |**客戶接洽** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|是|是|是|是|
|**Excel**|是|是|是|是|
|**Office.com**|即將推出|即將推出|即將推出|即將推出|
|**OneNote**|是|是|是|是|
|**OneDrive**|[有些設定目前是由其他控制項所管理。](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|即將推出|即將推出|即將推出|即將推出|
|**PowerPoint**|是|是|是|是|
|**Project**|即將推出|即將推出|即將推出|即將推出|
|**發行者**|是|是|是|是|
|**SharePoint**|[有些設定目前是由其他控制項所管理。](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[有些設定目前是由其他控制項所管理。](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|是|是|是|是|
|**Visio**|是|是|是|是|
|**Yammer**|是|是|是|是|

[請參閱這裡的部分產品調查和意見反應範例。](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**元資料集合**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="螢幕擷取畫面：顯示中繼資料的回饋頁面範例":::

**客戶接洽**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="螢幕擷取畫面：產品中客戶調查問題範例":::

## <a name="before-you-begin"></a>開始之前

您的裝置必須最低組建編號，才可使用這些原則。 如需詳細資訊，請參閱下表。

|**建立#**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|產品內意見反應|至少16.0.13328|至少2.42|至少16.0.13328|至少16.42|公開提供|
|產品內調查|至少16.0.13328|至少2.42|至少16.0.13426|至少16.42|擱置的首展|
|元資料集合|至少16.0.13328|至少2.42|至少16.0.13328|至少16.42|公開提供|
|客戶接洽|至少16.0.13328|至少2.42|至少16.0.13426|至少16.42|擱置的首展|

## <a name="specific-policies-you-can-configure"></a>您可以設定的特定原則

### <a name="feedback-policies"></a>意見反應原則

|**原則名稱**|**預設狀態**|**控制摘要**|
|:-----|:-----|:-----|
|允許使用者向 Microsoft 提交意見反應|開啟|控制各個應用程式的意見反應進入點|
|允許使用者接收和回應 Microsoft 的產品內調查|開啟|控制產品中的調查提示|
|允許使用者在向 Microsoft 提交意見反應時包含螢幕截圖和附件|關閉|決定使用者可以決定以意見反應/調查提交的中繼資料|
|允許 Microsoft 追蹤使用者提交的意見反應|關閉|決定使用者是否可以與意見反應/調查共用連絡人資訊|
|允許使用者在意見提交給 Microsoft 時包含記錄檔和內容樣本|關閉|決定使用者可以決定使用意見反應/調查提交的中繼資料|

## <a name="configure-policies"></a>設定原則

1. 移至 [https://config.office.com](https://config.office.com) 並以具有全域系統管理員許可權的使用者身分登入。
1. 選取 [ **自訂** ]，然後按 **原則管理**。
1. 選取 [建立 **]**。
1. 輸入 **名稱** 和 **描述**。
1. 選擇您要設定的 Azure Active directory 群組。
1. 搜尋 **意見** 反應與 **調查**。
1. 針對所列的每個原則，設定所需的值。

如需詳細資訊，請參閱[Office cloud policy service 的概述](/deployoffice/overview-office-cloud-policy-service)。

如果您使用群組原則，也可以使用這些原則設定。 若要使用這些原則設定，請在5146.1000 年3月 22 2021 日發行 [ (ADMX/ADML) ](https://www.microsoft.com/download/details.aspx?id=49030)，至少下載版本為的系統管理範本檔案。

您可以在 [使用者設定-> 原則-> 系統管理範本-系統管理範本-> Microsoft Office 2016-> 信任中心] 中找到這些原則設定。

> [!NOTE]
> 用戶端應用程式需要數小時才能進行更新。
