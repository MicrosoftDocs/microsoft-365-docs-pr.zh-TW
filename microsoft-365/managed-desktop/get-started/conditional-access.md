---
title: 調整條件式存取
description: 如何排除某些 Microsoft 帳戶
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8844c50f5faba609b3f5f53adc5ab45ba1dbaa74
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529680"
---
# <a name="adjust-conditional-access"></a>調整條件式存取

如果您在組織中使用[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則，則必須將其設定為排除某些帳戶，Microsoft 受管理的桌上型電腦才能正常運作。

如果要執行這項操作，請依照下列步驟執行：

1. 請參閱 how [to：在 Azure Active Directory 中規劃條件式存取部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps)的「回滾步驟」一節。
2. 請遵循這裡所述的步驟，排除所有原則的*現代 Workplace Service 帳戶*群組。


如果您有設定條件式存取的任何困難，請與系統管理員[支援](../working-with-managed-desktop/admin-support.md)人員聯繫。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>開始使用 Microsoft 受管理電腦的步驟

1. [在系統管理入口網站中新增和驗證系統管理員連絡人](add-admin-contacts.md)
2. 調整條件式存取（本主題）
3. [指派授權](assign-licenses.md)
4. [部署 Intune 公司入口網站](company-portal.md)
5. [啟用企業狀態漫遊](enterprise-state-roaming.md)
6. [設定裝置](set-up-devices.md)
7. [讓您的使用者準備好使用裝置](get-started-devices.md)
8. [部署應用程式](deploy-apps.md)
