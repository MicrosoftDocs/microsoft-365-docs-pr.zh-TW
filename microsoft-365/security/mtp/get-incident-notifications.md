---
title: 在 Microsoft 365 Defender 中取得事件通知
description: 瞭解如何在 Microsoft 365 Defender 中建立規則以取得事件的電子郵件通知
keywords: 事件、電子郵件、電子郵件通知、設定、使用者、信箱、電子郵件、事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
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
ms.openlocfilehash: 9db025818fdd5eb2635a9a676e4a10e20f3036b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930975"
---
# <a name="get-incident-notifications-by-email"></a>以電子郵件取得事件通知

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

您可以設定 Microsoft 365 Defender，每當有新事件或現有事件的更新時，都會以電子郵件通知您。 

您可以選擇根據事件嚴重性或裝置群組來取得通知。 您也可以選擇只在每個事件的第一次更新時收到通知。

您可以在電子郵件通知中新增或移除收件者。 新增的收件者在新增事件後會收到事件通知。 

電子郵件通知包含事件的重要詳細資料，例如事件名稱、嚴重性和類別等等。 您也可以直接前往事件，以便立即開始調查。 有關調查事件的更多資訊，請參閱 [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)中的調查事件。

>[!NOTE]
>您需要有管理安全性設定的許可權，才能設定電子郵件通知設定。 如果您選擇使用基本版權管理，具有安全性系統管理員或全域系統管理員角色的使用者可以設定電子郵件通知。 <br> <br>
同樣地，如果貴組織是使用角色型存取控制 (RBAC) ，則只能根據您允許管理的裝置群組來建立、編輯、刪除及接收通知。

## <a name="create-rules-for-incident-notifications"></a>建立事件通知規則

若要設定事件的第一封電子郵件通知，請建立新規則並自訂電子郵件通知設定。

1. 在功能窗格中，選取 **設定**  >  **事件電子郵件通知**。
2. 選取 **新增專案**。
3. 在名稱中為規則 **命名，** 並提供 **描述**。

    ![事件電子郵件通知的建立規則視窗](../../media/incidentemailnotif1.png) 
4. 選取 **下一** 步以前往 **通知設定**。 您可以在此處指定：
    - **警示嚴重性** - 選擇會觸發事件通知的警示嚴重性。 例如，如果您只想通知高嚴重性事件，請選取 [高。
    - **裝置群組範圍** - 此下拉式清單會顯示使用者可以存取的所有裝置群組。 選取要建立事件通知規則的裝置群組。
    - **只會在每個事件第** 一次出現時通知 - 選取此選項只會在符合您其他選項的第一個通知上傳送電子郵件通知。 之後與事件相關的更新或警示不會觸發通知。
    - **包含組織名稱** - 指出客戶名稱是否顯示在電子郵件通知上。
    - **包含租使用者專用入口網站連結** -新增包含租使用者識別碼的連結，以允許存取特定租使用者。
    
    ![事件電子郵件的 Notif 設定視窗](../../media/incidentemailnotif2.png)
5. 選取 **下一** 步以前往收 **件者** 區段。 您可以在此處指定將接收事件電子郵件通知的電子郵件地址。 輸入 **每個電子郵件地址之後** ，選取新增收件者。

    ![事件電子郵件的新增收件者視窗](../../media/incidentemailnotif3.png) 

6. 最後，選取 **下一** 步以前往檢查 **規則** ，以便查看所有與新規則相關聯的設定。 收件者會開始根據設定，透過電子郵件接收事件通知。

## <a name="see-also"></a>另請參閱
- [Microsoft 365 Defender 中的事件概觀](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [在 Microsoft 365 Defender 中排列事件的優先順序](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [調查 Microsoft 365 Defender 中的事件](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

