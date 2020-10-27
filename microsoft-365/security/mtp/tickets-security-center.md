---
title: 在 Microsoft 365 的安全性中心建立及追蹤 ServiceNow 入場券
description: 瞭解如何在 Microsoft 365 安全中心的 ServiceNow 中建立及追蹤票證。
keywords: 安全性，Microsoft 365，M365，安全分數，安全性中心，ServiceNow，票證，任務
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 8992efdd79295b6b56b8f033bd97b10f59a7a4d5
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769672"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>在 Microsoft 365 的安全性中心建立及追蹤 ServiceNow 入場券

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
>**ServiceNow 連接器的預覽期間結束**<br>
>2020年11月之後，這項功能將無法再使用。 感謝您的意見反應，並在我們決定接下來的步驟時繼續支援。

[Microsoft 365 的安全性中心](overview-security-center.md)已增強，可在 ServiceNow 中以本機方式建立及追蹤票證。 [深入瞭解 ServiceNow](https://www.servicenow.com/)

在 [安全性中心] 中，安全性管理員可以直接傳送 [Microsoft Secure 得分](microsoft-secure-score.md) 改進動作來 ServiceNow 和建立票證。 您可以建立事件管理和變更管理票證。 在「安全性中心」首頁及 ServiceNow 中追蹤入場券。

- [**深入瞭解必要條件、資料交換及疑難排解**](tickets.md)
- **在「規範中心」中管理 ServiceNow 入場券** (無法使用) 

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>將 Microsoft 365 的安全性中心連線至 ServiceNow

流覽至 Microsoft 365 的「安全性中心」首頁，以查看 ServiceNow 連接卡。

![您使用 ServiceNow](../../media/do-you-use-servicenow-250.png)

選取 [連線至 ServiceNow] 以移至 [ServiceNow 設定] 頁面。 依照指示授權 Microsoft 365 連接器應用程式。

> [!NOTE]
> 在您授權 Microsoft 365 security center 和 ServiceNow 之間的連線之前，請確定您使用您在安裝步驟中建立的整合使用者登入和密碼。 請勿使用您的個人認證。

在您遵循指示並授權連線之後，請在 Microsoft 365 的「安全性中心」連線頁面和 ServiceNow Microsoft 365 票證發放連接器應用程式體驗中查看線上狀態。 現在，您已經設定為開始建立工作！

### <a name="troubleshooting"></a>疑難排解

瞭解您可能會出現在連線過程中的常見錯誤，以及如何在 [疑難排解區段](tickets.md#troubleshooting)中加以緩解。

## <a name="create-a-task-and-share-it-to-servicenow"></a>建立任務並將其共用至 ServiceNow

整合設定後，根據特定的 [Microsoft 安全分數](microsoft-secure-score.md) 改進動作建立 ServiceNow 工作。 移至 Microsoft 365 security center 中的任何安全得分改進動作，然後選取 [ **共用** ]。 其中一個 dropdown 選項是 ServiceNow。

工作會產生，您可以在其中設定優先順序及編輯名稱、描述或到期日。 填寫所有必要欄位後，將工作傳送至 ServiceNow。

這項工作會顯示在 ServiceNow 成為 Microsoft 365 安全性和設定變更要求。

## <a name="track-tickets"></a>追蹤票據

一旦 ServiceNow 變更管理和事件管理票證已建立，它們就會顯示在 Microsoft 365 安全中心首頁的卡片上。 您可以從這些卡片建立票證、查看所有票證或管理 ServiceNow 設定。

![ServiceNow 變更管理票證](../../media/change-management-375.png)  ![ServiceNow 事件管理票證](../../media/incident-management-375.png)

若要在 Microsoft 365 的安全性中心重新布建或管理您的 ServiceNow 整合，請選取 [管理任何卡片上 **ServiceNow** 設定]。 從那裡移除目前的 ServiceNow 連線，並自訂票證狀態名稱。

使用 Microsoft 365 security center 中顯示的 ServiceNow 入場券，您的工作可以在一個位置進行追蹤，並依據其他安全性儀表板專案進行處理。

## <a name="resources"></a>資源

- [深入瞭解必要條件、資料交換及疑難排解](tickets.md)
- [Microsoft 安全分數](microsoft-secure-score.md)
