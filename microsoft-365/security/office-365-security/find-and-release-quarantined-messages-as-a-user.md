---
title: 以使用者身分找到並釋放被隔離的郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 使用者可以了解如何在 Exchange Online Protection (EOP) 中查看和管理收到的隔離郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c0f95561977c453d7040d84ba0c779c3d33e07f0
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029822"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>在 EOP 尋找及釋出隔離的郵件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，隔離區會保存可能有害或垃圾郵件。 如需詳細資訊，請參閱 [EOP 中的隔離區](quarantine-email-messages.md)。

作為隔離郵件的收件者，下表說明您能夠以非系統管理員使用者對郵件執行的動作：

<br>

****

|隔離原因|檢視|發行|刪除|
|---|:---:|:---:|:---:|
|大量|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|垃圾郵件|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|網路釣魚 (不是高信賴度網路釣魚)|![核取記號](../../media/checkmark.png)||![核取記號](../../media/checkmark.png)|
|

您可以在 Microsoft 365 Defender 入口網站或 (如果系統管理員已設定) 在[終端使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)中檢視及管理隔離郵件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要開啟 Microsoft 365 Defender 入口網站，請前往 <https://security.microsoft.com>。 若要直接開啟 [隔離區] 頁面，請移至 <https://security.microsoft.com/quarantine>。

- 系統管理員可以在反垃圾郵件原則中，設定郵件要先保留在隔離區中多久，然後才永久刪除。 已在隔離區中到期的郵件將無法還原。 如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

- 系統管理員也可以在反垃圾郵件原則中[啟用使用者垃圾郵件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。 使用者可以直接從這些通知釋出垃圾郵件隔離郵件。 使用者可以直接從這些通知檢閱垃圾郵件隔離郵件 (非高信賴度網路釣魚郵件)。 如需詳細資訊，請參閱 [EOP 中的使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。

- 經郵件流程規則 (又稱為傳輸規則) 認為是高信賴度網路釣魚或惡意程式碼而遭到隔離的郵件，只有系統管理員能看到，使用者看不到。 如需詳細資訊，請參閱[在 EOP 中管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。

- 您只能釋出郵件並將其報告為誤判 (非垃圾郵件) 一次。

## <a name="view-your-quarantined-messages"></a>檢視隔離的郵件

1. 在 Microsoft 365 Defender 入口網站中，前往 **[電子郵件與共同作業]** \> **[檢閱]** \> **[隔離]**。

2. 您可以按一下可用資料行標題來排序結果。 按一下 [修改資料行] 可顯示最多七個資料行。 預設值會標上星號 (<sup>\*</sup>)：

   - **收到日期**<sup>\*</sup>
   - **寄件者**<sup>\*</sup>
   - **主旨**<sup>\*</sup>
   - **隔離原因**<sup>\*</sup>
   - **已釋出？**<sup>\*</sup>
   - **原則類型**<sup>\*</sup>
   - **到期**<sup>\*</sup>
   - **收件者**
   - **郵件識別碼**
   - **原則名稱**
   - **大小**
   - **方向**

   完成時，請按一下 [儲存]，或按一下 [設為預設值]。

3. 若要篩選結果，請按一下 [篩選]。 可用的篩選條件如下：

   - **到期時間**：依郵件將於隔離區中到期的時間進行篩選：
     - **今天**
     - **未來 2 天**
     - **未來 7 天**
     - **自訂**：輸入 [開始日期] 和 [結束日期]。

   - **收到時間**：輸入 [開始日期] 和 [結束日期]。

   - **隔離原因**：
     - **大量郵件**
     - **垃圾郵件**
     - **網路釣魚**

   - **原則類型**：依原則類型篩選郵件：
     - **反惡意程式碼原則**
     - **安全附件原則** (適用於 Office 365 的 Defender)
     - **反網路釣魚原則**
     - **託管的內容篩選原則** (反網路釣魚原則)
     - **傳輸規則**

     <sup>\*</sup>

   若要清除篩選，按一下 [清除]。 若要隱藏 [篩選] 飛出視窗，再按一下 [篩選]。

4. 使用 [結果排序依據] (預設為 [郵件識別碼] 按鈕) 和對應值來尋找特定郵件。 不支援萬用字元。 您可以依下列值進行搜尋：

   - **郵件識別碼**：郵件的全域唯一識別碼。 如果您在清單中選取某個郵件，出現的 [詳細資料] 飛出窗格中就會出現 [郵件識別碼] 值。 系統管理員可以使用 [郵件追蹤][](message-trace-scc.md) 來尋找郵件及其對應的郵件識別碼值。
   - **寄件者電子郵件地址**：單一寄件者的電子郵件地址。
   - **原則名稱**：使用郵件的整個原則名稱。 搜尋時不會區分大小寫。
   - **收件者電子郵件地址**：單一收件者的電子郵件地址。
   - **主旨**：使用郵件的完整主旨。 搜尋時不會區分大小寫。

   輸入搜尋準則後，請按一下![重新整理按鈕](../../media/scc-quarantine-refresh.png) [重新整理] 來篩選結果。

當您找到特定隔離郵件後，選取該郵件即可檢視其詳細資料，並對其採取動作 (例如檢視、釋出、下載或刪除郵件)。

### <a name="export-message-results"></a>匯出郵件結果

1. 選取您感興趣的郵件，然後按一下 [匯出結果]。

2. 在提醒您讓瀏覽器視窗保持開啟的確認訊息中，按一下 [是]。

3. 匯出作業準備就緒時，便可為 .csv 檔案命名並選擇下載位置。

### <a name="view-quarantined-message-details"></a>檢視隔離郵件詳細資料

當您選取清單中的電子郵件訊息時，[詳細資料] 飛出窗格中會出現下列郵件詳細資料：

- **郵件識別碼**：郵件的全域唯一識別碼。
- **寄件者位址**
- **收到日期**：收到郵件的日期/時間。
- **主旨**
- **隔離原因**：顯示是否將郵件識別為 [垃圾郵件] 或 [大量] 或 [網路釣魚]。
- **收件者**：如果郵件包含多個收件者，則必須按一下 [預覽郵件] 或 [檢視郵件標頭] 以查看完整的收件者清單。
- **到期**：郵件會自動從隔離區永久刪除的日期/時間。
- **已釋出給**：該封郵件曾釋出至的所有電子郵件地址 (如果有的話)。
- **尚未釋出給**：該封郵件尚未釋出至的所有電子郵件地址 (如果有的話)。

### <a name="take-action-on-quarantined-email"></a>對隔離的電子郵件採取動作

選取郵件之後，便可以在 [詳細資料] 飛出窗格中選擇要如何處理郵件：

- **釋出郵件**：在出現的飛出窗格中，選擇是否要 [向 Microsoft 回報郵件以便分析]。 預設會選取此選項，並向 Microsoft 回報錯誤隔離的郵件屬於誤判。

  完成時，請按一下 [釋出郵件]。

- **檢視郵件標頭**：選擇此連結來查看郵件標頭文字。 若要深入分析標頭欄位和值，請將郵件標頭文字複製到您的剪貼簿，然後選擇 [Microsoft 郵件標頭分析器] 來移至遠端連線分析程式 (如果您想在不離開 Microsoft 365 的情況下完成這項工作，請按一下滑鼠右鍵並選擇 [在新索引標籤中開啟])。 將郵件標頭貼至 [郵件標頭分析器] 區段的頁面上，並選擇 [分析標頭]：

- **預覽郵件**：在出現的飛出窗格中，選擇下列其中一個選項：
  - **原始碼檢視**：顯示已停用所有連結的郵件內文 HTML 版本。
  - **文字檢視**：以純文字顯示郵件內文。

- **從隔離區中移除**：當您在出現的警告中按一下 [是] 之後，郵件就會立即遭到刪除。

- **封鎖寄件者**：將寄件者新增到您信箱上的封鎖寄件者清單。 如需詳細資訊，請參閱[封鎖郵件寄件者](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

將寄件者新增到您信箱上的封鎖寄件者清單。 如需詳細資訊，請參閱[封鎖郵件寄件者](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

完成時，請按一下 [關閉]。

如果您未釋出或移除郵件，則郵件會在預設的隔離保留期間到期後遭到刪除。

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>對多個隔離的電子郵件採取動作

當您選取清單中的多個隔離郵件 (最多 100 個) 時，隨即會出現 [大量動作] 飛出窗格供您採取下列動作：

- **釋出郵件**：這些選項與您釋出單一郵件時的選項相同，差別只在您無法選取 [將郵件釋出給特定收件者]；您只能選取 [將郵件釋出給所有收件者] 或 [將郵件釋出給其他人]。
- **刪除郵件**：在出現的警告中按一下 [是] 之後，郵件就會立即遭到刪除，而不會傳送給原始收件者。

完成時，請按一下 [關閉]。
