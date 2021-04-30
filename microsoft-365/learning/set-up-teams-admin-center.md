---
title: '在 Teams 系統管理中心中設定 Microsoft Viva 教學 (預覽) '
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 瞭解如何設定 Microsoft Viva 教學 (預覽) Teams 系統管理中心。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: c1427ae9fceab38046b53b31540e08d726815bda
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100896"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>在 Teams 系統管理中心中設定 Microsoft Viva 教學 (預覽) 

> [!NOTE]
> 本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。 

Teams 系統管理員會) Teams 系統管理中心安裝 Viva 教學 (Preview 並套用許可權原則。

## <a name="manage-settings-for-viva-learning-preview"></a>管理 Viva 學習 (預覽的設定) 

您必須是 Teams 系統管理中心的管理員，才可執行這些工作。

若要讓 Viva 學習 (預覽) 供組織中的使用者使用，請遵循下列步驟：

1. 在 Teams 系統管理中心的左側導覽中，移至 **Teams 應用** 程式  >  **管理應用程式**。

   ![Teams 系統管理中心中的左側導覽，顯示 [Teams 應用程式和管理應用程式] 區段。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. 在 [ **管理應用程式** ] 頁面上的搜尋方塊中，輸入 *Viva 教學*，然後選取 [ **Viva 教學 (預覽])**。

   ![[管理應用程式] 頁面中顯示搜尋方塊的 Teams 系統管理中心。](../media/learning/learning-app-teams-manage-apps-page.png)

3. 在「 **Viva 教學 (預覽)** 」頁面上：

   1. 在 [ **狀態**] 下，選取 [ **允許** ]，以開啟 Viva 教學 (預覽) 。

   2. 在 [**設定**] 索引標籤的 [**應用程式設定**] 底下，移至 Microsoft 365 系統管理中心，[設定教學內容來源](content-sources-365-admin-center.md)。

   ![Teams 系統管理中心中的學習頁面，顯示 [狀態與應用程式設定] 區段。](../media/learning/learning-app-teams-learning-page.png)

4. 在 [ **管理應用程式** 設定] 之後，移至 [ **許可權原則** 及 **設定原則** ]，將許可權授與可存取 Viva 教學 (預覽) 做為組織參與預覽的一部分的員工。

> [!NOTE]
>  如果您的組織4.0 是 Teams TAP100 程式的一部分，您可能需要在環3.0 中啟用核准的使用者，才能存取 Viva 教學 (Preview) 。 <br><br>做為預覽的一部分，Viva 教學 (預覽) 會在環3.0 中發行。 如果您的組織是在環4.0，您將不會在 [ **管理應用程式** ] 頁面上看到 Viva 學習 (預覽) 。 若要測試應用程式，您需要建立自訂應用程式許可權原則，將其設定為 **允許所有的應用程式**，並將其指派給環3.0 核准的使用者。 <br><br>   ![AppsPermission-Plcy] 頁面顯示 [允許所有已選取的應用程式]。](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>下一步

[設定教學內容來源以取得 Viva 教學 (預覽) Microsoft 365 系統管理中心](content-sources-365-admin-center.md)