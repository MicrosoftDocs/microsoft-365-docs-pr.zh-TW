---
title: 在郵件流程儀表板中佇列洞察力
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 系統管理員可以瞭解如何使用 Security & 合規性中心內郵件流程儀表板中的 [佇列] 小工具，以透過輸出連接器監視其內部部署或夥伴組織的失敗郵件流程。
ms.openlocfilehash: 3291a21828215d0a2a99c2226147bb1b748b8469
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199286"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>在安全性 & 規範中心內佇列的洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


當郵件無法使用連接器從您的組織傳送至您的內部部署或夥伴電子郵件伺服器時，郵件會在 Microsoft 365 中佇列。 導致此狀況的常見範例如下：

- 連接器設定不正確。
- 您的內部部署環境中已有網路或防火牆變更。

Microsoft 365 會繼續重新嘗試傳遞24小時。 24小時後，郵件會到期，並且會傳回未傳遞回報中的寄件者 (也稱為 NDRs 或退回的郵件) 。

如果佇列中的電子郵件磁片區超過預先定義的臨界值 (預設值為200郵件) 中，則可在下列位置取得此資訊：

- 在[安全性 & 合規性中心](https://protection.office.com)的[郵件流程儀表板](mail-flow-insights-v2.md)中，**佇列**的洞察力。 如需詳細資訊，請參閱本主題中的 [郵件流程儀表板區段中的佇列洞察力](#queues-insight-in-the-mail-flow-dashboard) 。
  
- 警示會 **顯示在 [** [安全性 & 規範中心](https://protection.office.com) ] 中的 [提醒] 儀表板 (**警示** \> **儀表板** ] 或 [ <https://protection.office.com/alertsdashboard>) ]。

  ![安全性 & 規範中心內的警示儀表板中的最近警示](../../media/mfi-queued-messages-alert.png)

- 系統管理員會根據名為 **Messages**的預設警示原則設定，收到電子郵件通知。 若要設定此警示的通知設定，請參閱下一節。

  如需警示原則的詳細資訊，請參閱 [安全性 & 合規性中心中的警示原則](../../compliance/alert-policies.md)。

## <a name="customize-queue-alerts"></a>自訂佇列警示

1. 在 [ [安全性 & 規範中心](https://protection.office.com)] 中，移至 [ **警示** \> **警示原則** ] 或 [開啟] <https://protection.office.com/alertpolicies> 。

2. 在 [ **警示原則** ] 頁面上，尋找並選取名為 Messages 的原則已 **延遲**。

3. 在 **郵件中已延遲** 開啟的浮出的浮出狀態，您可以開啟或關閉提醒並設定通知設定。

   ![郵件已延遲警示原則詳細資訊安全 & 規範中心](../../media/mfi-queued-messages-alert-policy.png)

   - **狀態**：您可以開啟或關閉提醒。

   - **電子郵件** 收件者和 **每日通知限制**：按一下 [ **編輯** ] 以設定下列設定：

4. 若要設定通知設定，請按一下 [ **編輯**]。 在出現的 [ **編輯原則** ] 飛入中，設定下列設定：

   - **傳送電子郵件通知**：預設值為 on。
   - **電子郵件**收件者：預設值為 **TenantAdmins**。
   - **每日通知限制**：預設值為 **無限制**。
   - **臨界**值：預設值為200。

   ![郵件中的通知設定已延遲警示原則詳細資訊安全 & 規範中心](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. 完成後，按一下 [ **儲存** 並 **關閉**]。

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>在郵件流程儀表板中佇列洞察力

即使已排入佇列的郵件磁片區未超出臨界值並產生警示，您仍然可以使用[郵件流程儀表板](mail-flow-insights-v2.md)中的**佇列**洞察力，以查看佇列中超過一小時的郵件，並在佇列郵件數目變得太大之前採取動作。

![安全性 & 規範中心內的郵件流程儀表板中的佇列小工具](../../media/mfi-queues-widget.png)

如果您按一下小工具上的郵件數目，則會出現佇列彈出的 **郵件** ，並顯示下列資訊：

- **佇列中郵件的數目**
- **連接器名稱**：按一下連接器名稱可管理 Exchange 系統管理中心中的連接器 (EAC) 。
- **佇列開始時間**
- **已超過最舊的郵件**
- **目的地伺服器**
- **最後一個 IP 位址**
- **上一個錯誤**
- **如何修正**：共有問題和解決方案可供使用。 如果 [ **立即修復它** ] 連結可用，請按一下它以修正此問題。 否則，請按一下任何可用的連結，以取得有關錯誤及可能解決方案的詳細資訊。

![按一下郵件流程儀表板中佇列洞察力之後的詳細資料](../../media/mfi-queues-details.png)

在**郵件**的詳細資料中，按一下 [**查看佇列**] 後，就會顯示相同的飛入通知。

![郵件已延遲安全性 & 規範中心的警示詳細資料](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>請參閱

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。
