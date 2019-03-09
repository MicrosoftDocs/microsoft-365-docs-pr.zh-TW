---
title: Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio
description: Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio 的資訊
keywords: Microsoft 受管理的電腦，Microsoft 365、 Microsoft Project，Microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 004b6399bb7039c1e30fbc6a7b775b8c7f19d497
ms.sourcegitcommit: 41b3dd9e38f56d0d4683ae6dc8e0e053ff57a3e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2019
ms.locfileid: "30516328"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio

Microsoft Project 和 Microsoft Visio 需要安裝 Microsoft 受管理的電腦裝置上的特定步驟。 本主題記載的先決條件和安裝程序，為這些應用程式。

## <a name="prerequisites"></a>必要條件

系統管理員應該驗證其符合下列必要條件：
- 必須可供您的使用者**授權數量**正確的 Microsoft Project 和 Microsoft Visio 的授權數量。 Microsoft 受管理的電腦時，目前僅支援 64 位元版本的這些應用程式。 
- **授權名稱**這些應用程式的適當授權名稱如下：
    - **Microsoft Project** -Project Online 專業版或 Project Online 進階版
    - **Microsoft Visio** Visio Online 方案 2
- **公司入口網站**的公司入口網站必須能夠使用租用戶中為您的使用者安裝這些應用程式。 如果公司入口網站不部署在您的租用戶，請參閱 <<c0>的公司入口網站。

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>部署 Project 和 Visio 版 Microsoft 受管理的電腦裝置
您提交支援要求之後，Microsoft 受管理的電腦會建立三個 Azure AD 群組和三個應用程式部署透過 Microsoft Intune 部署至您的租用戶的應用程式。  

**部署 Project 及 Visio**
1. **支援要求的檔案**IT 系統管理員必須支援服務歸檔，讓這些應用程式可以使用自己的使用者。 連絡 Microsoft 受管理電腦的詳細資訊，請參閱[支援 Microsoft 受管理電腦的系統管理員](../working-with-managed-desktop/admin-support.md)。
2. **將使用者指派給新的 Azure AD 群組**Microsoft 受管理的電腦會建立租用戶中的 3 Azure AD 群組及 3 對應的應用程式部署。 IT 系統管理員必須將使用者指派給適當的群組。

>[!NOTE]
>將使用者指派給其中一個 Azure AD 群組。 

Azure AD 群組名稱 | 若要指派哪個使用者？   
 --- | ---
Microsoft Office Project 的安裝 | 使用者需要只有專案
Microsoft Office Visio-安裝 | 需要僅 Visio 的使用者
Microsoft Office Project 和 Visio 安裝 | 需要 Project 及 Visio 的使用者

一旦指派給這些群組，應用程式則可在公司入口網站。 可能需要數分鐘才能同步處理，但然後使用者可以從公司入口網站安裝應用程式。 

## <a name="communicate-changes"></a>傳達變更
請務必讓 IT 系統管理員可讓他們知道如何安裝 Project 及 Visio 的使用者。 其中包括： 
- 提供給他們這些應用程式時，請通知使用者。 
- 關於如何從公司入口網站安裝這些應用程式的指示。

>[!NOTE]
>使用者必須關閉所有 Office 應用程式，再從公司入口網站安裝 Mircosoft 專案或 Microsoft Visio。 