---
title: 管理保留通知
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用 Advanced eDiscovery 中的通訊工作流程來追蹤法律封存通知的狀態，並視需要更新及重發。
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280111"
---
# <a name="manage-hold-notifications"></a>管理保留通知

在您開始合法保留通知工作流程之後，您可以使用 Advanced eDiscovery 中的通訊工作流程來追蹤通訊的狀態。 [通訊] 索引標籤包含 Advanced eDiscovery 案例內所有通知的清單。 您可以查看詳細資料，例如已獲指派或已確認通知的保管人數目。

## <a name="monitor-acknowledgments"></a>監視回執

從 [ **通訊** ] 索引標籤中選取通訊之後，您可以查看已確認保留通知的保管人清單。 

1. 在 [規範中心] 中，移至 [ **eDiscovery > Advanced eDiscovery**]。

2. 選取案例，然後按一下 [ **通訊** ] 索引標籤。

3. 選取 [通訊] 以顯示「 **保管人」通訊** 彈出頁面。

與所選通訊相關聯的保管人清單會顯示在 [通訊快顯視窗] 頁面上。 此頁面也會顯示深入資訊，以及已接收的確認數目及未完成的確認數量。 此頁面也會顯示哪些保管人已傳送他們收到保留通知的確認。

## <a name="re-send-a-hold-notice"></a>重新傳送保留通知

有時，保管人會在日常工作中不再追蹤電子郵件訊息。 或者，如果是長期執行的訴訟案例，系統管理員可能會聯繫您或其他人，並要求您重新傳送通知。 當您管理法律封存通知的通訊工作流程時，您可能需要重新傳送通知，使其回到「使用者信箱的最上層」。

若要將保留通知重新傳送給管理員：

1. 在 Advanced eDiscovery 中，選取案例，然後按一下 [**通訊**] 索引標籤。

2. 選取 [通訊] 以顯示「 **保管人」通訊** 彈出頁面。

3. 按一下 [ **更多 > 重新傳送保留通知**]。

4. 在 [ **重新傳送保留通知** ] 飛入頁面上，選取您要重新傳送通知的保管人，並輸入選用的原因。

5. 按一下 [ **重新傳送** ]，將通知傳送給選取的保管人。

如果管理員尚未認可保留通知，便會重新開機提醒和上報工作流程。 如果保管人已確認保留通知，則保管人會收到原始保留通知的複本。

> [!NOTE]
> 您只能將合法保留通知重新傳送給指派給通訊的保管人。 

## <a name="update-preservation-requirements"></a>更新保留需求
  
隨著案例的進展，您可能需要保管人保留其他或較少的資料，而不是先前所指示的資料。 在 eDiscovery 字詞中，您必須使用更新的內容重新發佈保留通知。

若要更新初始保留通知的內容，請執行下列動作：

1. 在 Advanced eDiscovery 中，選取案例，然後按一下 [**通訊**] 索引標籤。

2. 選取您要更新的保留通知，然後按一下 [**管理員通訊**] 快顯視窗頁面上的 [**編輯**]。

3. 在 [ **編輯通訊** 嚮導] 的左窗格中，按一下 [ **定義入口網站內容** ]，然後更新通知的內容。

4. 按一下 **[儲存]**。

重新發佈通知會傳送給所有指派給合法保留通知的保管人。 此外，如果已啟用提醒或上報通知，則會重新開機這些通知類型的工作流程。

## <a name="update-legal-hold-notifications-and-settings"></a>更新法律封存通知和設定

當您更新發佈、發行、重新簽發、提醒或上報通知的內容或設定時，這些變更將會套用到所有未來由工作流程所產生的通訊。

## <a name="more-information"></a>其他資訊

- [將監管人新增至案例](add-custodians-to-case.md)

- [建立法律封存通知](create-hold-notification.md)

- [確認保留通知](acknowledge-hold-notification.md)
