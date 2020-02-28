---
title: 指派權限的資料調查 （預覽）
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明如何設定權限才能使用 Microsoft 365 中的資料調查工具。
ms.openlocfilehash: 855d288c373bd2525afa3b8b7a3bbd894c4683a2
ms.sourcegitcommit: 7930fb8327bbd3594fde52f2dbf91e0f5d92f684
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "42328136"
---
# <a name="assign-permissions-for-data-investigations-preview"></a>指派權限的資料調查 （預覽）

若要存取 Office 365 或 Microsoft 365 規範中心的資料進行調查，您必須是資料調查角色群組的成員。 若要將成員新增至角色群組，您必須是 「 組織管理角色群組的成員，或指派安全性 & 合規性中心中的角色管理角色。 使用者會變成資料調查角色群組的成員之後，他們可以建立、 存取及進行調查的成員資料調查。

若要指派資料調查權限：

1. 移至 [[https://protection.office.com](https://protection.office.com)並使用您組織中系統管理員帳戶認證登入。

2. 在 [安全性 & 合規性中心，按一下 [**權限**。

3. 按一下 [**資料調查**角色群組，並再旁彈出式頁面上的**成員**，按一下 [**編輯**。

4. 按一下 [**選取成員**]，然後按一下 [**新增]**。 選取您要新增為資料現場的使用者，然後按一下 [**新增]**。

5. 您已新增所有使用者之後，按一下 [**完成**]，然後按一下 [**儲存**] 以儲存角色群組所做的變更。

> [!NOTE]
> 資料調查管理角色指派給 「 資料調查 」 角色群組提供存取 Office 365 或 Microsoft 365 合規性中心中的資料調查工具的必要權限。 根據預設，此角色不指派至 [組織管理角色群組中，這表示您組織中的全域系統管理員可能無法存取資料調查工具預設。 若要修正此問題，您可以將全域系統管理員新增至資料調查角色群組，或將資料調查管理角色新增至 「 組織管理 」 角色群組。 第三個選項就是建立自訂角色群組和指派資料調查管理角色 （和其他角色），然後新增適當的成員。 如需有關角色群組和角色的詳細資訊，請參閱[Office 365 安全性 & 合規性中心的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。
