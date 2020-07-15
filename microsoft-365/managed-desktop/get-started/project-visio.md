---
title: 在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio
description: Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio 的資訊
keywords: Microsoft 受管理的桌面、microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126824"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio

Microsoft Project 和 Microsoft Visio 需要在 Microsoft 受管理的桌面裝置上安裝特定步驟。 本主題說明這些應用程式的必要條件和安裝程式。

## <a name="prerequisites"></a>必要條件

系統管理員應確認其符合下列必要條件：
- **授權數量**-您的使用者必須能夠使用正確的 microsoft Project 和 microsoft Visio 授權金額。 Microsoft 受管理的桌面目前只支援這些應用程式的64位版本。 
- **授權名稱**-這些應用程式的適當授權名稱是：
    - **Microsoft project** -Project Online 專業版或 Project online Premium
    - **Microsoft visio** -Visio Online 方案2
- **公司入口網站**-您的租使用者必須具備公司入口網站，您的使用者才可安裝這些應用程式。 如果未在租使用者中部署公司入口網站，請參閱[公司入口網站](company-portal.md)。

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>部署 Microsoft 受管理桌面裝置的 Project 和 Visio
Microsoft 受管理的桌面會將 Microsoft Project 和 Microsoft Visio 新增為 Microsoft Intune 中的兩個 Win32 應用程式。 我們也會在 Azure Active Directory 中建立兩個群組，將會指派給對應的應用程式，其具有「可用」的目的。 

**部署 Project 和 Visio**將使用者新增至適當的群組，該應用程式將會出現在公司入口網站中。 可能需要幾分鐘的時間進行同步處理，但是您的使用者可以從公司入口網站安裝應用程式。 

Azure AD 群組名稱 | 要指派哪些使用者？   
 --- | ---
現代辦公 Project_Install | 需要專案的使用者
現代辦公 Visio_Install | 需要 Visio 的使用者

## <a name="communicate-changes"></a>交流變更
讓使用者瞭解如何安裝 Project 和 Visio 很重要。 這包括： 
- 在這些應用程式可供使用時通知使用者。 
- 如何從公司入口網站安裝這些應用程式的指示。
