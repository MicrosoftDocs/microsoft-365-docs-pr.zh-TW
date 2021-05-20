---
title: 調查 Microsoft 365 Defender 中的使用者
description: 調查使用者 Microsoft 365 安全性中心的事件。
keywords: security，malware，Microsoft 365，M365，security center，monitor，report，identity，data，裝置，應用程式，事件，分析，回應
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
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572798"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>調查 Microsoft 365 Defender 中的使用者

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**

- Microsoft 365 Defender

您的一部分事件調查可以包含使用者帳戶。 從事件的 [ **使用者** ] 索引標籤開始， **& 警示 >** *事件* **> 使用者**。 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的使用者頁面範例":::

若要快速摘要瞭解事件的使用者帳戶，請選取使用者帳戶名稱旁邊的核取記號。 以下為範例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 security center 中事件之使用者帳戶摘要窗格的範例":::

> [!NOTE]
> [使用者] 頁面會顯示 Azure Active Directory (Azure AD) 組織和群組，協助您瞭解與使用者相關聯的群組和許可權。

在此 [飛出] 頁面中，您可以查看使用者威脅資訊，包括任何目前的事件、作用中的警示、風險層級，以及使用者曝光、帳戶、裝置等等。

此外，您可以直接在 Microsoft 365 的安全性中心採取行動，以處理已遭破壞的使用者，確認使用者已遭到破壞或要求他們重新登入。

您可以從這裡選取 [ **移至使用者] 頁面** ，以查看使用者帳戶的詳細資料。 以下為範例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 security center 中事件的使用者帳戶頁面範例":::

您也可以在 [ **使用者** ] 頁面上選取清單中的使用者帳戶名稱，以查看此頁面。

Microsoft 365 的安全性中心使用者頁面會結合 microsoft defender for Endpoint、microsoft defender 身分識別及 Microsoft Cloud App Security (的資訊，視您擁有) 的授權而定。 

此頁面顯示使用者帳戶安全風險的特定資訊。 這包括協助評估風險及最近的事件，以及對使用者整體風險所帶來的警示。

您可以從這個頁面執行下列其他動作： 

- 將使用者帳戶標示為已遭破壞
- 需要使用者重新登入
- 暫停使用者帳戶
- 請參閱 Azure Active Directory (Azure AD) 使用者帳戶設定
- 查看使用者帳戶所擁有的檔案
- 查看與此使用者共用的檔案。 

以下為範例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 security center 中的事件之使用者帳戶的動作範例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>後續步驟

視需要進行處理內事件，繼續進行 [調查](investigate-incidents.md)。

## <a name="see-also"></a>請參閱

- [事件概觀](incidents-overview.md)
- [設定事件優先順序](incident-queue.md)
- [管理事件](manage-incidents.md)