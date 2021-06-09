---
title: 在 Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio
description: Microsoft 受管理的電腦裝置上的 Microsoft Project 或 Microsoft Visio 安裝資訊
keywords: Microsoft 受管理的電腦、Microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950529"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>在 Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio

Microsoft Project 和 Microsoft Visio 需要在 Microsoft 受管理的電腦裝置上安裝特定步驟。 本主題說明這些應用程式的必要條件和安裝程式。

## <a name="prerequisites"></a>必要條件

系統管理員應確認其符合下列必要條件：
- **授權數量**-您的使用者必須能使用正確的 Microsoft Project 數量和 Microsoft Visio 授權。 Microsoft 受管理的電腦目前只支援這些應用程式的64位版本。 
- **授權名稱** -這些應用程式的適當授權名稱是：
    - **Microsoft Project** Project Online 專業版或 Project Online 進階版
    - **Microsoft Visio** Visio 線上方案2
- **公司入口網站**-您的承租人必須可使用公司入口網站，以供您的使用者安裝這些應用程式。 如果公司入口網站未部署在您的租使用者中，請參閱[公司入口網站](company-portal.md)。

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>部署 Microsoft 受管理的電腦裝置的 Project 和 Visio
Microsoft 受管理的電腦會將 Microsoft Project 和 Microsoft Visio 新增為 Microsoft Intune 中的兩個 Win32 應用程式。 我們也會在 Azure Active Directory 中建立兩個群組，將會指派給具有「可用」之對應應用程式的。 

**若要部署 Project 和 Visio** 將使用者新增至適當的群組，該應用程式就會出現公司入口網站中。 可能需要幾分鐘的時間進行同步處理，但是您的使用者可以從公司入口網站安裝應用程式。 

Azure AD 群組名稱 | 要指派哪些使用者？   
 --- | ---
新式工作區-Office Project_Install | 需要 Project 的使用者
新式工作區-Office Visio_Install | 需要 Visio 的使用者

## <a name="communicate-changes"></a>交流變更
請務必讓 IT 系統管理員知道如何安裝 Project 和 Visio。 這包括： 
- 在這些應用程式可供使用時通知使用者。 
- 如何從公司入口網站安裝這些應用程式的指示。
