---
title: Microsoft 受管理的桌面應用程式需求
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5889a4e80f44349b4f149ee4f2a631f12b32251e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637849"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft 受管理的桌面應用程式需求

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
為了保證 Microsoft 受管理桌面裝置的效能、可靠性及可維護性，客戶的商務線應用程式不一定會嚴重影響使用者的經驗，也不一定會影響安全性的目的。 因此，您想要部署至 Microsoft 受管理桌面裝置的商務線應用程式，必須符合本主題中的需求。

## <a name="application-condition"></a>應用程式條件

重要的是應用程式不會對 Microsoft 管理的桌面環境造成不良影響。 以下是應用程式必須符合才能部署應用程式的需求。 針對任何特定的應用程式或驅動程式，Microsoft 可能會停征任何在此提供的需求。 Microsoft 可能決定移除任何對 Microsoft 受管理的桌面裝置效能和可靠性產生負面影響的應用程式或驅動程式。

## <a name="centrally-managed-apps"></a>集中管理的應用程式

所有安裝在 Microsoft 受管理裝置上的應用程式和驅動程式都必須透過 Microsoft Intune、Microsoft Store 或 Microsoft Store for Business 進行部署;若有可用，也會透過 Windows Update 服務部署驅動程式。 

## <a name="prohibited-app-classes"></a>禁止的應用程式類別

Microsoft 受管理的桌面裝置上不允許某些應用程式類型：
- 協力廠商的反病毒、安全性或核查軟體
- Microsoft 365 Apps for enterprise 之前的 Microsoft Office 版本
- 安裝或捆綁其他協力廠商軟體的應用程式

## <a name="restricted-app-behaviors"></a>限制的應用程式行為

某些應用程式行為會對使用者經驗造成負面影響，也可能對 Microsoft 受管理的桌面裝置帶來安全性風險。 不允許在未從 Microsoft 管理的桌面環境中執行具有下列行為的應用程式。

使用者體驗：
- 安裝背景服務
- 將自身新增至 Windows 啟動路徑
- 取決於驅動程式的應用程式
- 協力廠商網頁瀏覽器

安全性：
- 提升使用者的許可權
- 做為應用程式存放區，或具有內建的延伸管理員
- 有已知的安全弱點
- 加密或限制存取使用者資料
- 未簽署或使用不會總成根信任的憑證進行簽署


## <a name="driver-deployment"></a>驅動程式部署

Microsoft 受管理的桌面只支援透過 Windows Update 或已安裝的 [收件匣] 與 Microsoft Managed 裝置提供的裝置驅動程式。 

若應用程式需要特定的驅動程式來執行它，就會被視為限制的應用程式，並在部署至 Microsoft Managed Desktop 之前需要例外狀況。 

