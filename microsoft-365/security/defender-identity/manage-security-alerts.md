---
title: Microsoft defender 在 Microsoft 365 Defender 中的身分識別安全性警示
description: 瞭解如何在 Microsoft 365 defender 中管理及審閱 Microsoft defender 的身分識別所發出的安全性警示
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c48c9076d05cd352229477acc28b32185eef54f
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657773"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Microsoft 365 defender 中身分識別安全性警示的 defender

**適用於：**

- Microsoft 365 Defender
- 適用於身分識別的 Defender

本文說明如何在[Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center)中使用[Microsoft Defender 以取得身分識別](/defender-for-identity)安全性警示的基本概念。

用於身分識別警示的 Defender 會以專用的身分識別警示頁面格式，以本機方式整合到[Microsoft 365 的安全性中心](https://security.microsoft.com)。 這會標示旅程中的第一個步驟，將[完整的 Microsoft Defender 身分識別經驗引入 Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)。

新的身分識別提醒頁面可讓 Microsoft Defender 身分識別客戶獲得更佳的跨網域信號豐富和新的自動身分識別回應功能。 它可確保您保持安全，並協助改善安全性作業的效率。

透過[Microsoft 365 defender](/microsoft-365/security/defender/microsoft-365-defender)調查警示的其中一個好處，就是 Microsoft defender 的身分識別警示會進一步與從套件中的每個其他產品取得的資訊相關聯。 這些增強型警示會與來自[microsoft defender for Office 365](/microsoft-365/security/office-365-security)和[microsoft defender for Endpoint](/microsoft-365/security/defender-endpoint)的其他 Microsoft 365 defender 警示格式一致。 新的頁面可有效地避免流覽至另一個產品入口網站，以調查與 identity 相關聯的警示。

來自于某項身分識別的警示現在可以觸發[Microsoft 365 的 defender 自動化調查和回應 (AIR) ](/microsoft-365/security/defender/m365d-autoir)功能，包括自動修正警示，以及可對可疑活動產生影響的工具和程式的緩解。

>[!IMPORTANT]
>在與 Microsoft 365 defender 的收斂中，部分選項及詳細資料已從其在「身分識別入口網站」中的位置變更。 請閱讀下列詳細資料，以找出熟悉和新功能的位置。

## <a name="review-security-alerts"></a>檢查安全性警示

警示可從多個位置存取，包括「 **提醒** 」頁面、「 **事件** 」頁面、個別 **裝置** 的頁面，以及「 **高級搜尋** 」頁面。 在此範例中，我們會檢查 **提醒頁面**。  

在 [Microsoft 365 的安全性中心](https://security.microsoft.com/)，移至 [**事件 & 警示**]，然後移至 [**警示**]。

![移至 [事件及警示]，然後按 [警示]](../../media/defender-identity/incidents-alerts.png)

若要查看來自 Defender 身分識別的警示，請在右上方的選取 **篩選器** 上，然後在 [ **服務來源** ] 下選取 [ **Microsoft Defender 身分識別**]，然後選取 [ **套用：]**。

![篩選身分識別事件的 Defender](../../media/defender-identity/filter-defender-for-identity.png)

警示會顯示在下列欄中的資訊： **警示名稱**、 **標記**、 **嚴重性**、 **調查狀態**、 **狀態**、 **類別**、 **偵測來源**、 **受影響的資產**、 **第一個活動** 及 **最後一個活動**。

![身分識別事件的 Defender](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a>管理警示

如果您按一下其中一個提醒的 **警示名稱** ，就會移至包含提醒詳細資料的頁面。 在左窗格中，您將會看到 **發生** 狀況的摘要：

![警示中發生的情況](../../media/defender-identity/what-happened.png)

在 [ **發生的情形** ] 方塊中，會有警示的 **帳戶**、 **目的地主機** 和 **來源主機** 按鈕。 針對其他警示，您可能會看到 [按鈕]，以取得其他主機、帳戶、IP 位址、網域及安全性群組的詳細資料。 選取其中任何一項，以取得相關實體的詳細資料。

在右窗格上，您會看到 **警示的詳細資料**。 您可以在這裡看到更多詳細資料，並執行數項工作：

- 將此 **警示分類至此**，您可以將此警示指定為 **True 警示** 或 **虛假警示**

    ![分類警示](../../media/defender-identity/classify-alert.png)

- **警示狀態** -在 **集合分類** 中，您可以將警示分類為 **True** 或 **False**。 在 [ **指派給**] 中，您可以指派提醒給您自己或取消指派。

    ![警示狀態](../../media/defender-identity/alert-state.png)

- **警示詳細資料** -在 [ **警示詳細資料**] 下，您可以找到有關特定警示的詳細資訊，遵循有關警示類型的說明文件的連結，查看與此警示類型相關的任何自動調查，並查看與受影響裝置和使用者的任何自動調查。

    ![警示詳細資料](../../media/defender-identity/alert-details.png)

- **批註 & 史** -這裡您可以將批註新增至提醒，以及查看與提醒相關聯的所有動作的記錄。

    ![批註和記錄](../../media/defender-identity/comments-history.png)

- **管理警示** -如果您選取 [ **管理警示**]，您會移至一個窗格，讓您編輯：
  - **狀態** -您可以選擇 [ **新增**]、[ **已解決** ] 或 [ **正在進行中**]。
  - **分類** -您可以選擇 [ **True 警示** ] 或 [ **False 警示**]。
  - **批註** -您可以新增提醒的批註。

    如果您選取 [**管理提醒**] 旁邊的三個點，您可以 **諮詢威脅專家**、將警示 **匯出** 至 Excel 檔案，或 **連結至其他事件**。

    ![管理警示](../../media/defender-identity/manage-alert.png)

    >[!NOTE]
    >在 Excel 檔案中，您現在有兩個連結可供使用：**在 Microsoft Defender for Identity** 和 **view in Microsoft 365 Defender** 中查看。 每個連結將會帶您前往相關入口網站，並提供該警示的相關資訊。

## <a name="see-also"></a>請參閱

- [調查 Microsoft 365 Defender 中的警示](../defender/investigate-alerts.md)
