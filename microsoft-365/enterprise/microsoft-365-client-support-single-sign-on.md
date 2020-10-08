---
title: Microsoft 365 用戶端應用程式支援-單一 Sign-On
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 在本文中，瞭解哪些平臺、用戶端和 Powershell 模組支援 Microsoft 365 的單一登入。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d0a45c30ffe736cf67e811bce6eb029d6fb50674
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384799"
---
# <a name="microsoft-365-client-app-support--single-sign-on"></a>Microsoft 365 用戶端應用程式支援-單一 Sign-On

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

單一登入 (SSO) 會在使用者登入 Azure Active Directory (Azure AD) 中的應用程式時，新增安全性和便利性。 使用單一登入時，使用者可以使用一個帳戶登入一次，以存取內部部署 Active Directory 網域服務 (AD DS) 加入網域的裝置、軟體為服務 (SaaS) 應用程式和 web 應用程式。

深入瞭解 [單一登入](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。

## <a name="supported-platforms"></a>支援的平台

 - Windows 10 桌上出版<sup>2</sup>
 - Windows 10 現代應用程式
 - 網頁瀏覽器
 - Android<sup>3</sup>
 - iOS<sup>1</sup>
 - macOS<sup>4</sup>

如需 Microsoft 365 平臺支援的詳細資訊，請參閱 [microsoft 365 的系統需求](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)。

## <a name="supported-clients"></a>支援的用戶端

下列用戶端的最新版本支援單一登入：

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Access 圖示](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![公司入口網站圖示](../media/o365-microsoft-64x64.png) <br> [公司 <br> 入口網站<sup>3、4</sup>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Delve 圖示](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Edge 圖示](../media/o365-edge-64x64.png) <br> [Edge<sup>1</sup>](https://www.microsoft.com/windows/microsoft-edge) | ![Excel 圖示](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) 
| ![Kaizala 圖示](../media/o365-kaizala-64x64.png) <br> [Kaizala<sup>1</sup>](https://products.office.com/en/business/microsoft-kaizala) | ![Office.com 圖示](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![鏡頭圖示](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![商務用 OneDrive 圖示](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) | ![OneNote 圖示](../media/o365-OneNote-64x64.png) <br> [OneNote<sup>2</sup>](https://products.office.com/onenote) 
| ![Outlook 圖示](../media/o365-outlook-64x64.png) <br> [Outlook<sup>4</sup>](https://products.office.com/outlook) | ![Planner 圖示](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![電源自動圖示](../media/o365-flow-64x64.png) <br> [<br>自動功耗](https://flow.microsoft.com) | ![PowerBI 圖示](../media/o365-powerbi-64x64.png) <br> [Power BI<sup>2</sup>](https://powerbi.microsoft.com)| ![PowerPoint 圖示](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Project 圖示](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Publisher 圖示](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint 圖示](../media/o365-sharepoint-64x64.png) <br> [Sharepoint](https://products.office.com/sharepoint) | ![粘滯音符圖示](../media/o365-stickynotes-64x64.png) <br> [粘滯音符](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw)  | ![Sway 圖示](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) 
| ![Teams 圖示](../media/o365-teams-64x64.png) <br> [團隊<sup>2、4</sup>](https://products.office.com/microsoft-teams/group-chat-software) | ![待辦事項圖示](../media/o365-todo-64x64.png) <br> [To Do](https://todo.microsoft.com) | ![Visio 圖示](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Whiteboard 圖示](../media/o365-whiteboard-64x64.png) <br> [白板<sup>3</sup>](https://whiteboard.microsoft.com/) | ![Word 圖示](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) 
| ![Yammer 圖示](../media/o365-yammer-64x64.png) <br> [Yammer<sup>2</sup>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a>支援的 PowerShell 模組

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure 圖示](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Exchange 圖示](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![SharePoint 圖示](../media/o365-sharepoint-64x64.png) <br> [線上 SharePoint <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> 對 iOS 提供的 Edge 和 Kaizala 支援。 <br>
> <sup>2</sup> 對 Windows 10 Desktop 上的 OneNote、PowerBI、小組和 Yammer 的支援即將推出。 <br>
> 在 Android 上，您很快就<sup>會支援使用</sup>白板。 <br>
> <sup>4</sup> MacOS 于 Outlook、小組和公司入口網站上提供支援。 <br>

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)
