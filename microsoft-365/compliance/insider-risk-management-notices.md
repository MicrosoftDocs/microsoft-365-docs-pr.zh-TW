---
title: 測試人員風險管理通知範本 （預覽）
description: 了解測試人員風險管理 Microsoft 365 中的通知範本
keywords: Microsoft 365，測試人員風險管理、 風險管理、 合規性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: fafbd1eab21b67680bd91140c6a1d99df608513c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259813"
---
# <a name="insider-risk-management-notice-templates-preview"></a>測試人員風險管理通知範本 （預覽）

測試人員風險管理看到範本，可讓您將電子郵件傳送給員工，當使用者活動所產生的原則相符項目和警示。 在大多數情況下，產生警示的員工動作是錯誤或沒有不良意圖不慎活動的結果。 通知做為簡單的提醒給員工更仔細或重新整理程式訓練或公司的政策資源提供的連結或資訊。 通知可以是您的內部規範訓練程式很重要的一部分，且可協助您建立含有週期性風險活動的員工所記錄的稽核記錄。

如果您想要傳送給使用者的電子郵件提醒通知的原則相符項目是此問題： 解析程序的一部分，請建立通知範本。 只能以經過檢閱特定警示相關聯的員工電子郵件地址傳送通知。 當選取要套用至原則相符項目通知範本，您可以選擇接受範本中定義的欄位值或視需要覆寫欄位。

## <a name="notice-templates-dashboard"></a>請注意範本儀表板

**通知範本儀表板**會顯示設定的通知範本的清單，並可讓您建立新的通知範本。 反向順序列出的通知範本與要先列出最新的通知範本。

![測試人員風險管理通知範本儀表板](media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>傳送通知的 HTML

如果您想要建立多個簡單文字型電子郵件通知，您可以使用 HTML 在郵件內文] 欄位中的通知範本來建立更詳細的訊息。 下列範例會將郵件內文格式提供基本的 HTML 電子郵件通知範本：

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> 測試人員風險管理中的 HTML href 屬性實作注意到目前支援 URL 參照僅單引號記號而不是雙引號的範本。

## <a name="create-a-new-notice-template"></a>建立新的通知範本

若要建立新的測試人員風險管理會注意到範本，您將在 Microsoft 365 合規性中心**測試人員風險管理**解決方案中使用 [通知] 精靈。

完成下列步驟來建立新的測試人員風險管理通知範本：

1. 在[Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至**測試人員風險管理**並選取 [**通知範本**] 索引標籤。
2. 選取 [**建立通知範本**，以開啟 [通知] 精靈。
3. 在 [**建立新的通知範本**] 頁面上，完成下列欄位：
    - **範本名稱**： 輸入通知的易記名稱。 從案例傳送通知時，這個名稱會出現在通知通知儀表板上和在通知的選取範圍] 清單中的清單。
    - **從傳送**： 輸入通知寄件者電子郵件地址。 這個地址將會出現在**從：** 欄位中所有通知傳送給員工，除非變更時將通知傳送從案例。
    - **[副本] 及 [密件副本**欄位： 選用的使用者或群組原則相符項目，從您訂閱的 Active Directory 中所選取的通知。
    - **主旨**： 郵件的主旨行中顯示的資訊支援文字字元。
    - **郵件內文**： 會出現在郵件本文的資訊支援文字或 HTML 值。
4. 選取 [**建立**]，以建立和儲存的通知範本或選取 [**取消**] 以關閉而不儲存的通知範本。

## <a name="update-a-notice-template"></a>更新通知範本

若要更新現有的測試人員風險管理注意到範本中，完成下列步驟：

1. 在[Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至**測試人員風險管理**並選取 [**通知範本**] 索引標籤。
2. 在通知儀表板中，選取您想要管理的通知範本。
3. 在通知詳細資料] 頁面上，選取 [**編輯**]
4. 在 [**編輯**] 頁面上，您可以編輯下列欄位：
    - **範本名稱**： 輸入新的易記名稱的注意事項。 從案例傳送通知時，這個名稱會出現在通知通知儀表板上和在通知的選取範圍] 清單中的清單。
    - **從傳送**： 更新通知的寄件者電子郵件地址。 這個地址將會出現在**從：** 欄位中所有通知傳送給員工，除非變更時將通知傳送從案例。
    - **[副本] 及 [密件副本**欄位： 更新選用的使用者或群組原則相符項目，從您訂閱的 Active Directory 中所選取的通知。
    - **主旨**： 郵件的主旨行中顯示的最新更新資訊支援文字字元。
    - **郵件內文**： 更新資訊，會出現在郵件本文中，支援文字或 HTML 值。
5. 選取 [**儲存**] 以更新，並儲存通知或選取 [**取消**] 以關閉而不儲存的通知範本。

## <a name="delete-a-notice-template"></a>刪除通知範本

若要刪除現有的測試人員風險管理注意到範本中，完成下列步驟：

1. 在[Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至**測試人員風險管理**並選取 [**通知範本**] 索引標籤。
2. 在通知儀表板中，選取您想要刪除的通知範本。
3. 選取 [在工具列上的 [**刪除**] 圖示。
4. 若要刪除的通知範本，請選取 [刪除] 對話方塊中的 **[是]** 。 若要取消刪除，請選取 [**取消**。
