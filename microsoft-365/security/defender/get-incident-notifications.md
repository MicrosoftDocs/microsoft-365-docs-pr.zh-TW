---
title: 在 Microsoft 365 Defender 中取得事件通知
description: 瞭解如何建立規則，以在 Microsoft 365 Defender 中取得事件的電子郵件通知
keywords: 事件，電子郵件，電子郵件 notfications，設定，使用者，信箱，電子郵件，事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 72a1f8fe71efcfa7f4f73671611576a454b508e6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861310"
---
# <a name="get-incident-notifications-by-email"></a>透過電子郵件取得事件通知

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

您可以設定 Microsoft 365 Defender 以透過電子郵件通知您的員工有關新的事件或更新現有的事件。 您可以選擇根據下列專案取得通知：

- 事件嚴重性。
- 裝置群組。
- 僅限每個事件第一個更新。

電子郵件通知包含有關事件的重要詳細資料，例如事件名稱、嚴重性和類別，以及其他。 您也可以直接前往該事件，並立即開始進行調查。 如需詳細資訊，請參閱 [調查事件](investigate-incidents.md)。

您可以在電子郵件通知中新增或移除收件者。 新增的收件者會在新增事件後收到相關通知。 

>[!NOTE]
>您必須具有「管理安全性設定」許可權，才可設定電子郵件通知設定。 如果您已選擇使用基本版權管理，具有安全性管理員或全域系統管理員角色的使用者便可為您設定電子郵件通知。 <br> <br>
同樣地，如果您的組織使用角色型存取控制 (RBAC) ，您可以根據允許管理的裝置群組，只建立、編輯、刪除和接收通知。

## <a name="create-a-rule-for-email-notifications"></a>建立電子郵件通知的規則

請遵循下列步驟建立新的規則，並自訂電子郵件通知設定。

1. 在功能窗格中，選取 [ **設定 > Microsoft 365 Defender > 事件電子郵件通知**]。
2. 選取 [ **新增專案**]。
3. 在 [ **基礎** ] 頁面上，輸入規則名稱和描述，然後選取 **[下一步]**。
4. 在 [ **通知設定** ] 頁面上，設定：
    - **警示嚴重性** -選擇會觸發事件通知的警示嚴重性。 例如，如果您只想要知道高嚴重性的事件，請選取 [ **高**]。
    - **裝置群組範圍** -您可以指定所有的裝置群組，或從您租使用者中的裝置群組清單中進行選取。
    - **僅在每個事件第一次出現** 時，如果您只想要在第一個警示中符合其他選項，請選取 [僅限通知]。 稍後與該事件相關的更新或警示將不會傳送其他通知。
    - **在電子郵件中包含組織名稱** -如果您想要讓組織名稱出現在電子郵件通知中，請選取 [選取]。
    - **包含租使用者專用入口網站連結** -如果您想要在電子郵件通知中新增具有租使用者識別碼的連結，以便存取特定的 Microsoft 365 租使用者，請選取此連結。

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="事件電子郵件通知的通知設定":::

5. 選取 [下一步 **]**。 **在 [收** 件者] 頁面上，新增要接收事件通知的電子郵件地址。 在輸入每個新的電子郵件地址後，選取 **[新增]** 。 若要測試通知，並確認收件者在收件匣中收到這些通知，請選取 [ **傳送測試電子郵件**]。 
6. 選取 [下一步 **]**。 在 [ **檢查規則** ] 頁面上，複查規則的設定，然後選取 [ **建立規則**]。 收件者會開始透過電子郵件以設定為基礎來接收事件通知。

若要編輯現有規則，請從規則清單中進行選取。 在具有規則名稱的窗格上，選取 [ **編輯規則** ]，然後在 [ **基本** 設定]、[ **通知設定**] 及 [收件者 **] 頁面上** 進行變更。

若要編輯現有規則，請從規則清單中進行選取。 在具有規則名稱的窗格上，選取 [ **刪除**]。

## <a name="see-also"></a>另請參閱
- [事件概觀](incidents-overview.md)
- [設定事件優先順序](incident-queue.md)
- [調查事件](investigate-incidents.md)
