---
title: Microsoft 受管理電腦中的應用程式
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a24212cf69df50d00a32f17e8daf1939657dd602
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632848"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中的應用程式

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>應用程式一般

Microsoft 包含特定的主要應用程式，以及參與 Microsoft Managed Desktop 所需的 Microsoft 365 E3 或 E5 授權。 不過，即使我們提供這些應用程式，仍有一些責任和動作可完成。

您也可以使用 Microsoft Intune 的部署管線，透過公司入口網站或必要的背景安裝，將其他非 Microsoft 應用程式部署至使用者，以進行自助服務。 如果您有專業技術，您可以自行遷移所需的應用程式。或者，Microsoft 諮詢服務（MCS）或非 Microsoft 廠商很樂意協助您進行打包和遷移專案。 如需使用 MCS 的詳細資訊，請參閱使用[Microsoft 諮詢服務](apps-MCS.md)。


## <a name="apps-provided-by-microsoft"></a>Microsoft 提供的應用程式

隨附于 Microsoft 受管理的桌面授權中的 Microsoft 365 應用程式中的64位版本的應用程式，適用于企業標準套件（Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype 和 OneNote）。預設*不*會包含 Microsoft Project 和 Visio 的 Click-to-Run 版本，但您可以要求新增這些版本。 如需這些應用程式的詳細資訊，請參閱[Install Microsoft Project or Microsoft Visio On Microsoft Managed Desktop 裝置](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft 對於我們提供的應用程式的支援。

Microsoft 將為適用于企業應用程式的包含 Microsoft 365 應用程式，提供完整服務，以進行部署、更新和支援。 預設*不*會包含 microsoft Project 和 Visio 的 Click-to-Run 版本，但 Microsoft 受管理的桌面會提供部署群組，讓您的 IT 系統管理員可以管理授權，並適當地為您的組織部署這些應用程式。 Microsoft 將透過 Microsoft 受管理的桌面支援通道來支援這些應用程式的使用者。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>您必須執行哪些動作才能支援我們提供的應用程式

您仍需要使用這些應用程式進行的某些工作：

- **指派授權**-您負責針對適用于 Enterprise 的 Microsoft 365 應用程式取得或指派適當的授權給使用者。
- **將使用者新增至安全性群組**-如果您使用的是 Microsoft Project 或 Visio，您的 IT 系統管理員必須將這些使用者新增至適當的部署群組。 IT 系統管理員也負責在使用者離開公司時，從這些使用者回收授權。
- **部署 microsoft 365 附加**元件-如果您需要任何適用于企業應用程式的 Microsoft 365 應用程式的任何附加元件，請將它們集中部署，如其他任何 Windows 32 應用程式。 

## <a name="apps-you-provide"></a>您提供的應用程式

當然，您可能需要許多其他應用程式供商務運作使用。 使用 Microsoft Intune 的部署管線，只可將這些裝置部署至 Microsoft 受管理的桌面裝置。 若應用程式需要，您可以將其封裝（可能是非 Microsoft 轉銷商或 Microsoft 諮詢服務（MCS）），或如果您有這種方式，您可以自行打包。 然後，您可以將這些套件新增至 Microsoft 受管理的桌面入口網站，並將它們指派給 Azure Active Directory 群組，以觸發部署。 

如果您目前使用 Microsoft 端點設定管理員部署應用程式，則 Microsoft 受管理的桌面可以提供查詢來評估您的應用程式，並探索哪些專案準備好可遷移至 Microsoft Intune，以及哪些可能需要進行調整。


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>準備您自己的應用程式以包含在 Microsoft 受管理的桌面
查看您的應用程式，檢查：

- 沒有任何應用程式被禁止或具有限制的行為，如[Microsoft Managed Desktop app 需求](https://aka.ms/app-req)所述。
- 應用程式必須準備好由 Microsoft Intune 進行管理。 如需相關資訊，請參閱[Windows 10 app deployment Using Microsoft intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)及[新增應用程式至 Microsoft intune](https://docs.microsoft.com/intune/apps-add)。
- 其他預先打包需求，例如提供授權金鑰、授權條款的合約，以及預先設定的伺服器連線。

### <a name="decide-how-to-package-apps"></a>決定如何封裝應用程式

有些獨立的軟體廠商可能需要先封裝應用程式，才能進行集中部署。 「打包」表示應用程式的安裝程式是以授權金鑰、遠端伺服器位置或桌面快捷方式等設定來設定，以便在後臺安裝應用程式。

有三個可讓您的應用程式封裝的選項： 


- 您可以自行封裝應用程式
- 您可以與非 Microsoft 廠商搭配使用
- 您可以接洽 MCS 以封裝應用程式。 請與您的 Microsoft 客戶代表合作。 如需詳細資訊，請參閱使用[Microsoft 諮詢服務](apps-MCS.md)。







## <a name="deploying-apps"></a>部署應用程式

任何您用來取得應用程式打包方式的方法完成之後，您就可以遵循將[應用程式部署至 Microsoft 受管理的桌面裝置](../get-started/deploy-apps.md)中的步驟進行。


