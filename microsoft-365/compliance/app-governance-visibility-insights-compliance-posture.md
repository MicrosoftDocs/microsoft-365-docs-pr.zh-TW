---
title: 判斷您的應用程式合規性狀況
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
description: 判斷您的應用程式合規性狀況。
ms.openlocfilehash: 152f68e8fe0e7d7340d2e048bc73684bc079386f
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438021"
---
# <a name="determine-your-app-compliance-posture"></a>判斷您的應用程式合規性狀況

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

Microsoft 應用程式控管可讓您從 [Microsoft 365 合規性中心](https://aka.ms/appgovernance) 的應用程式控管概觀頁面，快速評估協力廠商應用程式的合規性狀況，及其對於您 Microsoft 365 租用戶中的資料存取權。

![Microsoft 365 合規性中心的應用程式控管概觀頁面](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> 您的登入帳戶必須具有 [這些角色](app-governance-get-started.md#administrator-roles) 的其中一個，才能檢視任何應用程式控管資料。
>

從此頁面，您可以查看：

- 對於使用 Microsoft Graph API 的啟用 OAuth 應用程式：

  - 您的租用戶中有多少
  - 擁有過度授權的人員可能有多少
  - 具有高權限的人員有多少

  從這項資訊中，您可以利用過度授權和高度權限應用程式來判斷貴組織的風險層級。

- 針對警示：

  - 您的租用戶有多少個作用中警示？
  - 有多少警示是以應用程式控管偵測（**威脅警示**）為依據
  - 有多少警示是以您目前使用的應用程式原則（**原則警示**）為依據
  - 10 個最新警示

  從此資訊中，您可以判斷產生警示的速度有多快，以及偵測到和以原則為依據的警示相對數目。

- 資料與資源存取：

  - 於目前和前三個行事曆月份，租用戶中的應用程式透過圖形 API 存取的資料總計。 (目前僅包含郵件和檔案上傳和下載使用情況)
  - 目前和前三個行事曆月份的資料使用情況，按資源類型細分。 (目前僅包含郵件和檔案上傳和下載使用情況)

  從此資訊中，您可以判斷 Microsoft 365 租用戶的資料存取是否有異常高峰。
