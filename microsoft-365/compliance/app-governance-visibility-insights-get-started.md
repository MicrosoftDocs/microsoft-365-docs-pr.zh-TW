---
title: 「可見度與深入解析」快速入門
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
description: 「可見度與深入解析」快速入門。
ms.openlocfilehash: 93be3557c32345e81c7126b669ead8edf8ebac21
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430477"
---
# <a name="get-started-with-visibility-and-insights"></a>「可見度與深入解析」快速入門

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

快速入門的第一個位置是位於 [https://aka.ms/appgovernance](https://aka.ms/appgovernance) 的應用程式控管儀表板。 請注意，您的登入帳戶必須具有其中一個[應用程式控管系統管理員角色](app-governance-get-started.md#administrator-roles)，才能檢視任何應用程式控管資料。

![Microsoft 365 合規性中心的應用程式控管概觀頁面](..\media\manage-app-protection-governance\mapg-cc-overview.png)

您也可以從 **[Microsoft 365 系統管理中心] > [Microsoft 365 合規性中心] > [應用程式控管] > [概觀] 頁面** 存取應用程式控管儀表板。

## <a name="whats-available-on-the-dashboard"></a>儀表板提供的資訊

儀表板包含租用戶中 Microsoft 365 應用程式生態系統的元件摘要：

- **租用戶摘要**：重要應用程式與警示類別的計數。
- **偵測和原則警示**：租用戶中最新的作用中警示
- **資料和資源存取**：彙總應用程式 API 存取和租用戶中熱門資源的整體使用量。 將滑鼠移到 Graph 的每月資料行上，以查看對應的值。
- **改善您的應用程式防護和控管**：建議的動作如建立應用程式使用狀況或權限原則。
- **根據類別排序的熱門應用程式**：根據這些類別排序的熱門應用程式：
  
  - **所有類別**：排序所有可用的類別。
  - **高權限**：高權限是內部根據平台機器學習和訊號所判斷的類別。
  - **權限過高**：當應用程式控管收到遙測，指出在過去 90 天內授予應用程序的權限未被使用，表示該應用程式被授予的權限過高。 應用程式控管必須至少執行 90 天，以判斷是否有任何應用程序權限過高。  
  - **未經驗證**：未獲得[發行者認證](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview)的應用程式被視為未經驗證。
  - **僅應用程式**：[應用程式權限](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types)由無需登入使用者即可執行的應用程式使用。 具有跨租用戶存取資料權限的應用程式可能具有更高的風險。
  - **新應用程式**：過去 7 天內註冊的新 Microsoft 365 應用程式。  

## <a name="next-step"></a>下一個步驟

[取得特定應用程式的詳細深入解析](app-governance-visibility-insights-view-apps.md)。
