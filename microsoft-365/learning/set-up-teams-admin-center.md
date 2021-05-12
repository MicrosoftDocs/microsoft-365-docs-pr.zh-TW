---
title: '在團隊系統管理中心設定 Microsoft Viva 教學 (預覽) '
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 瞭解如何在團隊系統管理中心中設定 Microsoft Viva 教學 (預覽) 。
ms.openlocfilehash: 40e659796b22097f42515c0cbb704bdaa4ccc972
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333515"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>在團隊系統管理中心設定 Microsoft Viva 教學 (預覽) 

> [!NOTE]
> 本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。 

小組管理員會安裝 Viva 教學 (預覽) 並透過團隊系統管理中心套用許可權原則。

## <a name="manage-settings-for-viva-learning-preview"></a>管理 Viva 學習 (預覽的設定) 

您必須是小組系統管理員的管理員，才可執行這些工作。

若要讓 Viva 學習 (預覽) 供組織中的使用者使用，請遵循下列步驟：

1. 在團隊系統管理中心的左側導覽中，移至 [**小組應用** 程式  >  **管理應用程式**]。

   ![小組系統管理中心中的左側導覽，顯示「小組應用程式和管理應用程式」區段。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. 在 [ **管理應用程式** ] 頁面上的搜尋方塊中，輸入 *Viva 教學*，然後選取 [ **Viva 教學 (預覽])**。

   ![[管理應用程式] 頁面中顯示搜尋方塊的小組系統管理中心。](../media/learning/learning-app-teams-manage-apps-page.png)

3. 在「 **Viva 教學 (預覽)** 」頁面上：

   1. 在 [ **狀態**] 下，選取 [ **允許** ]，以開啟 Viva 教學 (預覽) 。

   2. 在 [ **設定** ] 索引標籤的 [ **應用程式設定**] 底下，移至 Microsoft 365 系統管理中心以 [設定教學內容來源](content-sources-365-admin-center.md)。

   ![小組系統管理中心的學習頁面，顯示 [狀態與應用程式設定] 區段。](../media/learning/learning-app-teams-learning-page.png)

4. 在 [ **管理應用程式** 設定] 之後，移至 [ **許可權原則** 及 **設定原則** ]，將許可權授與可存取 Viva 教學 (預覽) 做為組織參與預覽的一部分的員工。

> [!NOTE]
>  如果您的組織是4.0 在「小組 TAP100 計畫」的一部分，您可能需要在環3.0 中啟用核准的使用者，才能存取 Viva 教學 (預覽) 。 <br><br>做為預覽的一部分，Viva 教學 (預覽) 會在環3.0 中發行。 如果您的組織是在環4.0，您將不會在 [ **管理應用程式** ] 頁面上看到 Viva 學習 (預覽) 。 若要測試應用程式，您需要建立自訂應用程式許可權原則，將其設定為 **允許所有的應用程式**，並將其指派給環3.0 核准的使用者。 <br><br>   ![AppsPermission-Plcy] 頁面顯示 [允許所有已選取的應用程式]。](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>下一步

[在 Microsoft 365 系統管理中心中設定 Viva 學習 (預覽) 的教學內容來源](content-sources-365-admin-center.md)