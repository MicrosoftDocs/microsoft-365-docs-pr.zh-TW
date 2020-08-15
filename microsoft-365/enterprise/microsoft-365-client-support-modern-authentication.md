---
title: Microsoft 365 用戶端應用程式支援-新式驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 在本文中，瞭解哪些平臺、用戶端和 Powershell 模組支援 Microsoft 365 的新式驗證。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0357c357de2b8db355c539acda851fca7802d17
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688459"
---
# <a name="microsoft-365-client-app-support---modern-authentication"></a>Microsoft 365 用戶端應用程式支援-新式驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

新式驗證可讓 Active Directory 驗證程式庫 (ADAL) 型登入跨不同平臺的 Office 用戶端應用程式。 這可讓登入功能（例如 Multi-Factor 驗證） (MFA) 、智慧卡和憑證型驗證。

深入瞭解 [多重要素驗證](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) 和 [憑證型驗證](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started)。

## <a name="supported-platforms"></a>支援的平台

 - Windows 10 桌上出版
 - Windows 10 現代應用程式
 - 網頁瀏覽器<sup>1</sup>
 - Android<sup>2</sup>
 - iOS
 - macOS

如需 Microsoft 365 平臺支援的詳細資訊，請參閱 [microsoft 365 的系統需求](https://products.office.com/office-system-requirements)。

## <a name="supported-clients"></a>支援的用戶端

下列用戶端的最新版本支援新式驗證：

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Access 圖示](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Azure 圖示](../media/o365-azure-64x64.png) <br> [Azure <br> 入口網站 ](https://azure.microsoft.com/features/azure-portal/) | ![公司入口網站圖示](../media/o365-microsoft-64x64.png) <br> [公司 <br> 入口網站 ](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Delve 圖示](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Dynamics 365 圖示](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) 
| ![Edge 圖示](../media/o365-edge-64x64.png) <br> [銳利](https://www.microsoft.com/windows/microsoft-edge) | ![Excel 圖示](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![表單圖示](../media/o365-forms-64x64.png) <br> [表單](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) | ![Kaizala 圖示](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Office.com 圖示](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) 
| ![Office 365 系統管理員圖示](../media/o365-o365admin-64x64.png) <br> [Microsoft 365 系統 <br> 管理員](https://products.office.com/business/manage-office-365-admin-app) | ![鏡頭圖示](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![商務用 OneDrive 圖示](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) |  ![OneNote 圖示](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Outlook 圖示](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) 
| ![Planner 圖示](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![PowerApps 圖示](../media/o365-powerapps-64x64.png) <br> [PowerApps ](https://powerapps.microsoft.com) | ![電源自動圖示](../media/o365-flow-64x64.png) <br> [<br>自動功耗](https://flow.microsoft.com) | ![PowerBI 圖示](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com)| ![PowerPoint 圖示](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Project 圖示](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Publisher 圖示](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint 圖示](../media/o365-sharepoint-64x64.png) <br> [Sharepoint](https://products.office.com/sharepoint) | ![商務用 Skype 圖示](../media/o365-skypeforbusiness-64x64.png) <br> [商務用 <br> Skype<sup>1</sup>](https://www.skype.com/business/) | ![StaffHub 圖示](../media/o365-staffhub-64x64.png) <br> [StaffHub](https://products.office.com/microsoft-staffhub/staff-scheduling-software)
| ![粘滯音符圖示](../media/o365-stickynotes-64x64.png) <br> [粘滯音符](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Stream 圖示](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Sway 圖示](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Teams 圖示](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) | ![待辦事項圖示](../media/o365-todo-64x64.png) <br> [To Do](https://todo.microsoft.com) 
| ![Visio 圖示](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Whiteboard 圖示](../media/o365-whiteboard-64x64.png) <br> [白板<sup>1</sup>、<sup>2</sup>](https://whiteboard.microsoft.com/) | ![Word 圖示](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Yammer 圖示](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview) | ![Yammer 圖示](../media/o365-yammer-64x64.png) <br> [Yammer <br> 通告程式](https://products.office.com/yammer/yammer-overview) |  |

## <a name="supported-powershell-modules"></a>支援的 PowerShell 模組

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure 圖示](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Exchange 圖示](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) | ![SharePoint 圖示](../media/o365-sharepoint-64x64.png) <br> [線上 SharePoint <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> 很快就會支援白板和商務用 Skype on web app。 <br>
> <sup>2</sup> 對 Android 上的白板功能很快就可供使用。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)
