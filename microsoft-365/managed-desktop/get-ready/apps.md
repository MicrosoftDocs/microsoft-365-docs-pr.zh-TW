---
title: Microsoft 受管理電腦中的應用程式
description: 說明如何處理應用程式，包括如何封裝、部署及支援應用程式。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028941"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中的應用程式

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>應用程式一般

Microsoft 包含特定的主要應用程式，以及參與 Microsoft 受管理的電腦所需的 Microsoft 365 E3 或 E5 授權。 不過，即使我們提供這些應用程式，仍有一些責任和動作可完成。

您也可以使用 Microsoft Intune 的部署管線，將其他非 Microsoft 應用程式部署給您的使用者，以供自助服務使用公司入口網站或必要的背景安裝。 

## <a name="apps-provided-by-microsoft"></a>Microsoft 提供的應用程式

隨附于您的 Microsoft 受管理的電腦授權是 Microsoft 365 Apps 企業版 Standard 套件中的64位版本的應用程式 (Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype 和 OneNote。預設 *不* 會包含 ) Click-to-Run 和 Microsoft Project 的 Visio 版本，但您可以要求加入這些版本。 如需這些應用程式的詳細資訊，請參閱[Install Microsoft Project or Microsoft Visio Microsoft 受管理的電腦裝置](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft 對於我們提供的應用程式的支援。

Microsoft 會提供完整服務，以供部署、更新及支援所包含的 Microsoft 365 Apps 企業版應用程式。 預設 *不* 會包含 Microsoft Project 和 Visio 的 Click-to-Run 版本，但是 Microsoft 受管理的電腦會提供部署群組，讓您的 IT 系統管理員可以管理授權，並適當地為您的組織部署這些應用程式。 Microsoft 會透過 Microsoft 受管理的電腦支援通道來支援這些應用程式的使用者。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>您必須執行哪些動作才能支援我們提供的應用程式

您仍需要使用這些應用程式進行的某些工作：

- **指派授權**-您負責為 Microsoft 365 Apps 企業版的使用者取得或指派適當的授權。
- **將使用者新增至安全性群組**-如果您使用 Microsoft Project 或 Visio，您的 IT 系統管理員必須將這些使用者新增至適當的部署群組。 IT 系統管理員也負責在使用者離開公司時，從這些使用者回收授權。
- **部署 Microsoft 365 附加** 元件-如果您需要任何 Microsoft 365 Apps 企業版應用程式的任何附加元件，請將它們集中部署，就像部署任何其他 Windows 32 應用程式一樣。 

## <a name="apps-you-provide"></a>您提供的應用程式

您可能需要其他應用程式，才能進行商務作業。 這些應用程式僅能使用 Microsoft Intune 的部署管線部署至 Microsoft 受管理的電腦裝置。 如需應用程式部署的詳細資訊，請依照將[應用程式部署至 Microsoft 受管理的電腦裝置](../get-started/deploy-apps.md)中的步驟進行。

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>準備您自己的應用程式以納入 Microsoft 受管理的電腦
查看您的應用程式，檢查：

- 沒有任何應用程式被禁止或具有限制的行為，如[Microsoft 受管理的電腦的應用程式需求](../service-description/mmd-app-requirements.md)所述。
- 應用程式必須準備好進行管理 Microsoft Intune。 如需本主題的詳細資訊，請參閱[使用 Microsoft Intune Windows 10 應用程式部署](/intune/apps-windows-10-app-deploy)，並[新增 Microsoft Intune 的應用程式](/intune/apps-add)。
- 其他預先打包需求，例如提供授權金鑰、授權條款的合約，以及預先設定的伺服器連線。

## <a name="steps-to-get-ready"></a>準備就緒的步驟

1. 審查[Microsoft 受管理的電腦的必要條件](prerequisites.md)。
2. 使用 [準備工作評估工具](readiness-assessment-tool.md)。
3. [來賓帳戶的先決條件](guest-accounts.md)
4. [Microsoft 受管理的電腦的網路設定](network.md)
5. [為 Microsoft 受管理的電腦準備認證和網路設定檔](certs-wifi-lan.md)
6. [為 Microsoft 受管理的電腦準備內部部署資源存取](authentication.md)
7. [Microsoft 受管理的電腦中的應用程式](apps.md) (本文) 
8. [為 Microsoft 受管理的電腦準備對應磁碟機](mapped-drives.md)
9. [為 Microsoft 受管理的電腦準備列印資源](printing.md)
