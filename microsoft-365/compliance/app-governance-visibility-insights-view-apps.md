---
title: 檢視您的應用程式
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 檢視您的應用程式。
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420063"
---
# <a name="view-your-apps"></a>檢視您的應用程式

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

Microsoft 應用程式管理可讓您快速深入瞭解您租用戶中的 Microsoft 365 應用程式。 例如，您可以：

- 租用戶中啟用 OAuth 的應用程式清單，這些應用程式使用 Microsoft Graph API，以及相關的應用程式中繼資料和使用狀況資料。
- 選取清單中的應用程式，以包含更深入的深入解析和資訊的應用程式詳細資料。

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a>取得租用戶中所有應用程式的清單

如需租用戶中的應用程式摘要，請前往 **Microsoft 365 合規性中心 > 應用程式保護與控管 > 應用程式**。

![Microsoft 365 合規性中心的 MAPG 應用程式摘要頁面。](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> 您的登入帳戶必須具有 [這些角色](app-governance-get-started.md#administrator-roles) 的其中一個，才能檢視任何應用程式控管資料。
>

您將看到應用程式清單和這項資訊：

- 應用程式名稱
- 發行者
- 應用程式認證

  指出此應用程式是否與 Microsoft 技術相容、符合雲端應用程式安全性最佳做法，並受 Microsoft 支援。

- 上次修改日期

  顯示用戶端中已安裝應用程式控管的日期（如果該日期比上次修改應用程式的日期還要新）。

- 安裝日期
- 權限等級
- 使用者數目
- 資料存取

  此應用程式過去一天在租用戶中的資料上傳和下載總和以及前一天的變更。

應用程式控管會根據預設 **應用程式名稱** 排序此份應用程式清單。 若要根據其他應用程屬性排序此清單，請選取屬性名稱。

您也可以選取 **搜尋** 以根據名稱搜尋應用程式。

## <a name="getting-detailed-information-on-an-app"></a>取得應用程式的詳細資訊

如需您租用戶中的特定應用程式詳細資訊，請前往 **Microsoft 365 合規性中心 > 應用程式控管 > 應用程式頁面 > *應用程式名稱***。

![Microsoft 365 合規性中心的應用程式控管應用程式詳細資料窗格](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

應用程式詳細資料窗格提供這些定位字元的其他資訊：

| 索引標籤名稱 | 說明 |
|:-------|:-----|
| 詳細資料 | 查看應用程式上的其他資料，例如第一次同意的日期與應用程式識別碼。 若要查看在 Azure AD 中註冊的應用程式屬性，請選取 **在 Azure AD 中選取**。 |
| 使用情況 | 查看租用戶中由應用程式存取的資料、繪製資料使用量，以及顯示前 \<x> 名使用者與具有 [優先帳戶](/microsoft-365/admin/setup/priority-accounts) 的使用者。 |
| 使用者 | 查看正在使用應用程式的使用者清單、無論他們是否為優先帳戶，以及下載和上傳的資料量。 |
| 權限 | 請參閱由應用程式授予及使用的權限摘要，以及特定權限的清單。 請參閱 [Microsoft Graph 權限參考](/graph/permissions-reference) 以取得詳細資訊。 |
|||

針對已啟用的應用程式，還有一個 **停用應用程式** 控制項以停用所選應用程式的使用，以及一個 **啟用應用程式** 控制項以啟用遭停用的應用程式。 這些動作需要這些 [系統管理員角色](app-governance-get-started.md#administrator-roles)：

- 合規性系統管理員
- 全域系統管理員
- 安全性系統管理員
- 安全性操作員

## <a name="next-step"></a>後續步驟

[判斷您的整體應用程式合規性狀態](app-governance-visibility-insights-compliance-posture.md)。
