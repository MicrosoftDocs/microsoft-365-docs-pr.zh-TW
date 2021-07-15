---
title: 應用程式原則快速入門
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
description: 「了解應用程式原則」快速入門。
ms.openlocfilehash: 3f80048835388e740ba64ac36d1aa19594bf7a9d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420095"
---
# <a name="get-started-with-app-policies"></a>應用程式原則快速入門

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

Microsoft 應用程式控管的應用程式原則是您可以實作更主動或被動的條件以建立警示或自動補救，以滿足組織中應用程式合規性的特定需求的方式。

若要查看目前的應用程式原則清單，請前往 **[Microsoft 365 合規性中心] > [應用程式防護與控管] > [原則]**。

![Microsoft 365 合規性中心的 MAPG 原則摘要頁面。](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a>應用程式原則儀表板提供的資訊

您可以看見作用中、非作用中和測試原則的數量，以及每個原則的下列資訊：

- **原則名稱**
- **狀態**

  - **作用中**：所有原則評估與動作為作用中。
  - **非作用中**：所有原則評估與動作為停用。
  - **稽核模式**：原則評估處於稽核模式。 原則為作用中，但已停用該原則動作。

- **嚴重性**：由於此原則被評估為 True 而觸發的任何警報上設定的嚴重性層級，這是原則設定的一部分。
- **作用中的警示數目**：由原則產生，具有 **[進行中]** 或 **[新]** 狀態的警示。
- **警示總數**：此原則的作用中警示和已解決的警示。
- **上次警示日期**：因為此原則，上次產生警示的日期。
- **上次修改日期**：上次變更此原則的日期。

預設會以 **[上次修改日期]** 排序原則清單。 若要根據另一個屬性排序清單，請選取屬性名稱。

選取原則後，您會取得包含這些額外詳細資料的詳細原則窗格：

- **描述**：此原則用途的更詳細說明。
- **建立者**：建立此原則的帳戶使用者主體名稱 (UPN)。
- 此原則產生的作用中警示清單。

您可以選取詳細原則窗格中的 **[編輯]** 或 **[刪除]**，或在原則清單中選取該原則的垂直省略號，來編輯或刪除應用程式原則。

您也可以：

- 建立新的原則。 您可以先從應用程式使用原則或權限原則開始。
- 將原則清單匯出為逗號分隔值 (CSV) 檔案。 例如，您可以在 Microsoft Excel 中開啟 CVS 檔案，然後根據 **[嚴重性]**，然後是 **[警示總數]** 排序原則。
- 搜尋原則清單。

## <a name="next-step"></a>下一個步驟

[建立應用程式原則。](app-governance-app-policies-create.md)
