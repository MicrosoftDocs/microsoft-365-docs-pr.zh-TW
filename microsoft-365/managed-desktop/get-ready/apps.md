---
title: Microsoft 受管理電腦中的應用程式
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: db89e3b1f8b5b8073eab62e4b4d38087e1e73fa4
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/12/2019
ms.locfileid: "34913044"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中的應用程式

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>應用程式通常

Microsoft 包含特定索引鍵的應用程式，以及參與 Microsoft 受管理的電腦所需的 Microsoft 365 E3 或 E5 授權。 不過，即使我們將提供這些應用程式，您仍會有特定的職責和動作，以完成。

您也可以部署其他非 Microsoft 應用程式至您的使用者透過公司入口網站或所需的背景安裝的自助，所有使用 Microsoft Intune 部署管線。 如果您有您可以移轉您需要自行; 這些應用程式的專業知識如果沒有 Microsoft 諮詢服務 (MCS) 或非 Microsoft 廠商將樂於以協助您進行封裝和移轉的專案。 如需使用 MCS 的詳細資訊，請參閱[Working with Microsoft 諮詢服務](apps-MCS.md)。


## <a name="apps-provided-by-microsoft"></a>Microsoft 所提供的應用程式

隨附於 Microsoft 受管理電腦授權是 64 位元版本的 Office 365 專業增強版 Standard Suite （Word、 Excel、 PowerPoint、 Outlook、 Publisher、 Access、 Skype for Business 和 OneNote。) 中的應用程式按一下 [-隨選即用版本的 Microsoft Project 和 Visio 會根據預設，*不*包含，但您可以要求他們加入。 如需有關這些應用程式的詳細資訊，請參閱[安裝 Microsoft Project 或 Microsoft 受管理的電腦裝置上的 Microsoft Visio](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft 沒有為支援我們提供應用程式

Microsoft 會提供包含 Office 365 專業增強版應用程式的部署、 更新和支援的完整服務。 按一下 [-隨選即用版本的 Microsoft Project 和 Visio 會根據預設，*不*包含，但 Microsoft 受管理的電腦會提供讓 IT 系統管理員管理授權及部署這些應用程式適當的部署群組您組織。 Microsoft 將會支援透過 Microsoft 受管理的電腦支援頻道這些應用程式的使用者。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>您要做為支援我們提供應用程式

仍有某些您需要運用這些應用程式的事項：

- **將授權指派**-您負責取得並指派適當的授權給 Office 365 專業增強版的使用者。
- **新增使用者至安全性群組**-如果您使用 Microsoft Project 或 Visio，IT 系統管理員必須將新增至適當的部署群組的使用者。 IT 系統管理員也是負責收回這些使用者的授權，如果他們離開公司的。
- **部署 Office 365 Addons** -如果您需要的任何 Office 365 專業增強版的應用程式的任何 Addons，將其部署集中像任何其他 Windows 32 應用程式。 

## <a name="apps-you-provide"></a>您提供的應用程式

當然，您可能有其他您需要的企業營運的應用程式的數量。 這些可以可以只部署至 Microsoft 受管理的電腦裝置使用 Microsoft Intune 部署管線。 如果應用程式需要它可以讓他們封裝廠商 （這可能是在非 Microsoft 供應商或 Microsoft 諮詢服務 (MCS)），或如果您有方法，您可以封裝他們自己。 然後將這些套件新增至 Microsoft 受管理電腦入口網站，並將它們指派給 Azure Active Directory 群組，以觸發部署。 

如果您目前使用 System Center Configuration Manager 部署您的應用程式，Microsoft 受管理的電腦可以提供您評估您的應用程式，並探索哪些項目可供移轉至 Microsoft Intune 和哪些項目可能需要一些調整查詢.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>準備您自己的應用程式以使用 Microsoft 受管理電腦中的相對路徑
檢閱您的應用程式，檢查：

- 無應用程式禁止或有限制的行為， [Microsoft 受管理的電腦應用程式需求](https://aka.ms/app-req)所述。
- 應用程式必須準備好以透過 Microsoft Intune 進行管理。 如需有關此的詳細資訊，請參閱[Windows 10 應用程式部署使用 Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)和[新增應用程式連接至 Microsoft Intune](https://docs.microsoft.com/intune/apps-add)。
- 提供授權金鑰、 授權合約協議等預先設定的伺服器連線其他前封裝需求。

### <a name="decide-how-to-package-apps"></a>決定如何封裝應用程式

某些獨立軟體廠商可能會要求您的應用程式會封裝集中在部署之前。 「 封裝 」 表示應用程式的安裝程式會設定與授權金鑰，遠端伺服器的位置或桌面捷徑語言設定，以便應用程式可以安裝在背景中。

有三個選項来封裝您的應用程式： 


- 您可以自行封裝應用程式
- 您可以使用非 Microsoft 廠商
- 您可以邀請 MCS 與要封裝您的應用程式。 使用您的 Microsoft 帳戶代表配合。 如需詳細資訊，請參閱[Working with Microsoft 諮詢服務](apps-MCS.md)。







## <a name="deploying-apps"></a>部署應用程式

不論您用來取得封裝之後，已完成，應用程式的方法就可以依照[部署應用程式連接至 Microsoft 受管理的電腦裝置](../get-started/deploy-apps.md)中的步驟。


