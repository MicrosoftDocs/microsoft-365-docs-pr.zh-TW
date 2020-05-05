---
title: 在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio
description: Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio 的資訊
keywords: Microsoft 受管理的桌面、microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 450dbcb08cd0636dae575ecd2d5e9abadc5ceb25
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022093"
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
在您提交支援要求之後，Microsoft 受管理的桌面會透過 Microsoft Intune 建立三個 Azure AD 群組和三個應用程式部署，以將應用程式部署至您的租使用者。  

**部署 Project 和 Visio**
1. 檔案**a 支援要求**IT 系統管理員必須將支援要求歸檔，以讓這些應用程式可供使用者使用。 如需聯繫 Microsoft 受管理的電腦的詳細資訊，請參閱[Microsoft Managed desktop 的系統管理支援](../working-with-managed-desktop/admin-support.md)。
2. **將使用者指派給新的 AZURE AD 群組**Microsoft 受管理的桌面會在您的租使用者和3對應的應用程式部署中建立3個 Azure AD 群組。 IT 系統管理員必須將使用者指派給適當的群組。

>[!NOTE]
>僅將使用者指派給這些 Azure AD 群組中的其中一個。 

Azure AD 群組名稱 | 要指派哪些使用者？   
 --- | ---
現代辦公 Project_Install | 需要專案的使用者
現代辦公 Visio_Install | 需要 Visio 的使用者

一旦指派給這些群組，便可在公司入口網站中取得應用程式。 可能需要幾分鐘的時間進行同步處理，但是您的使用者可以從公司入口網站安裝應用程式。 

## <a name="communicate-changes"></a>交流變更
讓使用者瞭解如何安裝 Project 和 Visio 很重要。 這包括： 
- 在這些應用程式可供使用時通知使用者。 
- 如何從公司入口網站安裝這些應用程式的指示。

>[!NOTE]
>使用者在從公司入口網站安裝 Microsoft Project 或 Microsoft Visio 之前，必須先關閉所有 Office 應用程式。 
