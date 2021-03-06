---
title: 管理 Microsoft Defender for Endpoint 抑制規則
description: 您可能需要使用抑制規則，防止警示出現在入口網站中。 瞭解如何在 Microsoft Defender for Endpoint 中管理抑制規則。
keywords: 管理抑制、規則、規則名稱、範圍、動作、警示、開啟、關閉
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 74b89d86b770cb47a0855b45d457ea8ce5fb9802
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454754"
---
# <a name="manage-suppression-rules"></a>管理歸併規則

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


在某些情況下，您可能需要抑制出現在入口網站中的提醒。 您可以針對已知的特殊警示（如組織中的已知工具或處理常式），建立抑制規則。 如需如何抑制提醒的詳細資訊，請參閱 [抑制警示](manage-alerts.md)。

您可以查看所有抑制規則的清單，並在一個位置進行管理。 您也可以開啟或關閉警示抑制規則。


1. 在功能窗格中，選取 [**設定**  >  **端點**  >  **規則**  >  **警示抑制**]。 組織中使用者所建立的隱藏規則清單隨即顯示。

2. 按一下規則名稱旁邊的核取方塊，以選取規則。

3. 按一下 [ **開啟規則**]、[ **編輯規則**] 或 [  **刪除規則**]。 當您變更規則時，您可以選擇發行已經取消的警示，不論這些警示是否符合新的準則。 


## <a name="view-details-of-a-suppression-rule"></a>查看抑制規則的詳細資料

1. 在功能窗格中，選取 [**設定**  >  **端點**  >  **規則**  >  **警示抑制**]。 組織中使用者所建立的隱藏規則清單隨即顯示。

2. 按一下規則名稱。 會顯示規則的詳細資料。 您將會看到 [狀態]、[範圍]、[動作]、[建立者]、[建立者] 和 [建立規則] 日期等規則詳細資料。 您也可以查看相關聯的警示和規則條件。

## <a name="related-topics"></a>相關主題

- [管理警示](manage-alerts.md)
