---
title: 在 Microsoft 365 安全性中心調查使用者
description: 調查 Microsoft 365 security center 中的使用者
keywords: 安全性，惡意程式碼，Microsoft 365，M365，security center，monitor，report，identity，data，裝置，應用程式
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 68fc924ee14932ebdf92ef76306ba00e352b6030
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861251"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a>在 Microsoft 365 安全性中心調查使用者

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**

- Microsoft 365 Defender

您的一部分事件調查可以包含使用者帳戶。 從事件的 [ **使用者** ] 索引標籤開始， **& 警示 >** *事件* **> 使用者**。 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的使用者頁面範例":::

若要快速摘要瞭解事件的使用者帳戶，請選取使用者帳戶名稱旁邊的核取記號。 以下為範例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 安全中心內事件之使用者帳戶摘要窗格的範例":::

您可以從這裡選取 [ **移至使用者] 頁面** ，以查看使用者帳戶的詳細資料。 以下為範例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 安全中心內事件的使用者帳戶頁面範例":::

您也可以在 [ **使用者** ] 頁面上選取清單中的使用者帳戶名稱，以查看此頁面。

Microsoft 365 的「安全性中心」使用者頁面會結合 Microsoft Defender for Endpoint、Microsoft Defender 身分識別及 Microsoft Cloud App Security (的資訊，取決於您) 的授權。 

此頁面顯示使用者帳戶安全風險的特定資訊。 這包括協助評估風險及最近的事件，以及對使用者整體風險所帶來的警示。

您可以從這個頁面執行下列其他動作： 

- 將使用者帳戶標示為已遭破壞
- 需要使用者重新登入
- 暫停使用者帳戶
- 請參閱 Azure Active Directory (Azure AD) 使用者帳戶設定
- 查看使用者帳戶所擁有的檔案
- 查看與此使用者共用的檔案。 

以下為範例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 安全性中心內事件之使用者帳戶的動作範例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a>相關主題

- [事件概觀](incidents-overview.md)
- [設定事件優先順序](incident-queue.md)
- [管理事件](manage-incidents.md)