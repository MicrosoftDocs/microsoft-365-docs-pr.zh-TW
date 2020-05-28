---
title: 比較群組
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: 了解您可以使用的群組類型。
ms.openlocfilehash: b81bb09efedc503b49d2ed4aa10b1e7153116f14
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44388026"
---
# <a name="compare-groups"></a>比較群組

在 Microsoft 365 系統管理中心的 [群組]**** 區段中，您可以建立和管理以下類型的群組： 

- **Microsoft 365 群組**用來在公司內部和外部的使用者之間共同作業。
- **通訊群組**用來傳送通知給一群人。
- **安全性群組**用來授權存取資源，例如 SharePoint 網站。
- **擁有郵件功能的安全性群組**用來授權存取資源 (如 SharePoint)，以及將通知透過電子郵件傳送給這些使用者。
- 如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址)，就會使用**共用信箱**。

## <a name="microsoft-365-groups"></a>Microsoft 365 群組

Microsoft 365 群組用來在公司內部和外部的使用者之間共同作業。 透過每個 Microsoft 365 群組，成員可以取得交談、檔案和行事曆活動以及 Planner 的群組電子郵件與共用工作區。

只要[系統管理員啟用](manage-guest-access-in-groups.md)這項功能，您就可以將組織外部的人員新增至群組。 您也可以允許外部寄件者將電子郵件傳送到群組電子郵件地址。

Microsoft 365 群組可以[在 Azure Active Directory 中針對動態成員資格設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type) (部分機器翻譯)，以便根據使用者屬性 (例如部門、位置、職稱等) 自動新增或移除群組成員。

Microsoft 365 群組可透過行動裝置應用程式存取，例如 iOS 版 Outlook 和 Android 版 Outlook。

如果[系統管理員已啟用](allow-members-to-send-as-or-send-on-behalf-of-group.md)此功能，則群組成員可以以群組電子郵件地址的身分傳送或代表其傳送。

## <a name="distribution-groups"></a>通訊群組

[通訊群組](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)用來傳送通知給一群人。 如果系統管理員已啟用該功能，他們就能接收外部電子郵件。

如果您需要將資訊廣播給一群人，例如「大樓 A 的人員」或「Contoso 的每個人」，則最適合使用通訊群組。

## <a name="security-groups"></a>安全性群組

[安全性群組](../email/create-edit-or-delete-a-security-group.md)用來授權存取 Microsoft 365 資源，例如 SharePoint。 由於您只需要管理群組，而非將使用者個別新增至每個資源，它們能讓系統管理更容易。

安全性群組可以包含使用者或裝置。 為裝置建立可搭配行動裝置管理服務 (例如 Intune) 使用的安全性群組。

安全性群組可以[在 Azure Active Directory 中針對動態成員資格設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)，以便根據使用者屬性 (例如部門、位置、職稱等) 或裝置屬性 (例如作業系統版本) 自動新增或移除群組成員。

## <a name="mail-enabled-security-groups"></a>擁有郵件功能的安全性群組

擁有郵件功能的安全性群組運作方式與一般安全性群組相同，除了無法透過 Azure Active Directory 動態管理且不能包含裝置以外。

其中包括能夠將郵件傳送給群組的所有成員。

## <a name="shared-mailboxes"></a>共用信箱

如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址、接待處或其他可能由多人共用的功能)，就會使用[共用信箱](../email/create-a-shared-mailbox.md)。

如果系統管理員已啟用此功能，共用信箱就可以接收外部電子郵件。

擁有群組信箱權限的使用者可以以信箱電子郵件地址的身分傳送或代表其傳送 (如果系統管理員已授與使用者執行該動作的權限)。 這對於說明和支援信箱特別有用，因為使用者可以透過「Contoso 支援」或「大樓 A 接待處」傳送電子郵件。

目前無法將共用信箱移轉至 Microsoft 365 群組。 這是您需要的內容嗎？ 請告訴我們。 **[在這裡投票](https://go.microsoft.com/fwlink/?linkid=871518)**。

## <a name="related-articles"></a>相關文章

[深入了解 Microsoft 365 群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
