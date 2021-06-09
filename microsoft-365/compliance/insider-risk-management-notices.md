---
title: 內部風險管理通知範本
description: 深入瞭解 Microsoft 365 中的內幕人員風險管理通知範本
keywords: Microsoft 365, 內部風險管理, 風險管理, 合規性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416477"
---
# <a name="insider-risk-management-notice-templates"></a>內部風險管理通知範本

內部使用者風險管理通知範本可讓您在活動產生原則相符及警示時，將電子郵件傳送給使用者。 在大多數情況下，產生警示的使用者動作是不具正確意圖的錯誤或無意活動的結果。 通知是一種簡單的提醒，讓使用者更小心，提供有關複習訓練或公司原則資源的資訊連結。 通知可能是您的內部規範訓練計畫的重要部分，可協助為具有定期風險活動的使用者建立記錄的審計追蹤。

如果您想要在問題解決程式中傳送使用者的電子郵件提醒通知與原則相符，請建立通知範本。 通知只能傳送至與所檢查的特定警示相關聯的使用者電子郵件地址。 選取要套用至原則相符的公告範本時，您可以選擇接受範本中所定義的欄位值，或是視需要覆寫這些欄位。

## <a name="notice-templates-dashboard"></a>注意範本儀表板

**通知儀表板** 會顯示已配置的通知範本清單，並可讓您建立新通知範本。 通知範本會以反向日期順序列出，最新的通知範本會先列出。

![有問必答風險管理通知範本儀表板](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>用於通知的 HTML

如果您想要建立超過簡單的文字式電子郵件訊息以進行通知，您可以在 [公告範本] 的 [郵件內文] 欄位中使用 HTML，建立更詳細的訊息。 下列範例會提供基本的 HTML 電子郵件通知範本的郵件內文格式：

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> 「內幕風險管理」通知範本中的 HTML href 屬性實現目前只支援單一單引號標記，而不支援 URL 參照的雙引號。

## <a name="create-a-new-notice-template"></a>建立新的通知範本

若要建立新的內會員風險管理通知範本，您可以使用「Microsoft 365 規範中心」的「**內幕風險管理**」方案中的「通知」嚮導。

完成下列步驟，以建立新的有問必答風險管理通知範本：

1. 在 [ [Microsoft 365 規範中心](https://compliance.microsoft.com)] 中，移至 [**內幕風險管理**]，然後選取 [**公告範本**] 索引標籤。
2. 選取 [ **建立公告範本** ] 以開啟 [通知嚮導]。
3. 在 [ **建立新的通知範本** ] 頁面上，完成下欄欄位：
    - **範本名稱**：輸入通知的易記名稱。 此名稱會出現在 [通知] 儀表板上的通知清單，以及從案例中傳送通知時的 [通知選擇] 清單中。
    - **傳送來源**：輸入通知的寄件者電子郵件地址。 除非在從案例傳送通知時進行變更，否則此位址會出現在所有通知傳送給使用者的 [ **寄件者：** ] 欄位中。
    - [副本]**和 [密件副本**] 欄位：在您訂閱的 Active Directory 中，選取要向其通報原則相符專案的選用使用者或群組。
    - 主旨 **：顯示** 在郵件主旨行中的資訊，支援文字字元。
    - **郵件** 內文：出現在郵件內文中的資訊，支援文字或 HTML 值。
4. 選取 [ **建立** ]，以建立及儲存公告範本，或選取 [ **取消** ] 關閉而不儲存公告範本。

## <a name="update-a-notice-template"></a>更新公告範本

若要更新現有的「內幕風險管理通知」範本，請完成下列步驟：

1. 在 [ [Microsoft 365 規範中心](https://compliance.microsoft.com)] 中，移至 [**內幕風險管理**]，然後選取 [**公告範本**] 索引標籤。
2. 在 [通知] 儀表板上，選取您要管理的公告範本。
3. 在 [通知詳細資料] 頁面上，選取 [**編輯**]
4. 在 [ **編輯** ] 頁面上，您可以編輯下欄欄位：
    - **範本名稱**：輸入通知的新易記名稱。 此名稱會出現在 [通知] 儀表板上的通知清單，以及從案例中傳送通知時的 [通知選擇] 清單中。
    - **傳送來源**：更新通知的寄件者電子郵件地址。 除非在從案例傳送通知時進行變更，否則此位址會出現在所有通知傳送給使用者的 [ **寄件者：** ] 欄位中。
    - [副本]**和 [密件副本**] 欄位：更新選用的使用者或群組，以獲得您訂閱之 Active Directory 中所選取的原則相符專案。
    - 主旨 **：會** 出現在郵件主旨行的更新資訊，支援文字字元。
    - **郵件** 內文：更新出現在郵件內文中的資訊，支援文字或 HTML 值。
5. 選取 [ **儲存** ] 以更新並儲存通知，或選取 [ **取消** ] 關閉而不儲存公告範本。

## <a name="delete-a-notice-template"></a>刪除公告範本

若要刪除現有的現有會員風險管理通知範本，請完成下列步驟：

1. 在 [ [Microsoft 365 規範中心](https://compliance.microsoft.com)] 中，移至 [**內幕風險管理**]，然後選取 [**公告範本**] 索引標籤。
2. 在 [通知] 儀表板上，選取您要刪除的公告範本。
3. 選取工具列上的 [ **刪除** ] 圖示。
4. 若要刪除公告範本，請在 [刪除] 對話方塊中選取 **[是]** 。 若要取消刪除，請選取 [ **取消**]。
