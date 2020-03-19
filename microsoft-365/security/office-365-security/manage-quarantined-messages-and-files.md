---
title: 在 Office 365 中以系統管理員身分管理被隔離的郵件和檔案
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: 系統管理員可以針對所有使用者，查看、發行和刪除所有類型的隔離郵件。 只有系統管理員可以管理被隔離為惡意程式碼、高可信度網路釣魚或郵件流程規則（傳輸規則）結果的郵件。
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857070"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>在 Office 365 中以系統管理員身分管理被隔離的郵件和檔案

在沒有 Exchange Online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中，隔離區會在 Office 365 組織中包含可能有害或有害的郵件。 如需詳細資訊，請參閱[Office 365 中的隔離](quarantine-email-messages.md)。

系統管理員可以針對所有使用者，查看、發行和刪除所有類型的隔離郵件。 只有系統管理員可以管理被隔離為惡意程式碼、高可信度網路釣魚或郵件流程規則（也稱為傳輸規則）結果的郵件。 系統管理員也可以將誤報報告給 Microsoft。

使用 Office 365 高級威脅防護（ATP）的組織中的系統管理員，也可以在 SharePoint Online、商務 OneDrive 商務和 Microsoft 小組中，查看、下載和刪除隔離的檔案。

您可以在安全性 & 規範中心或 PowerShell （Office 365 客戶的 Exchange Online PowerShell）中查看及管理隔離的郵件;Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要開啟 Office 365 安全性 & 規範中心，請移<https://protection.office.com>至。 若要直接開啟 [隔離] 頁面， <https://protection.office.com/quarantine>請移至。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連接至 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派許可權，才可以系統管理員身分管理隔離。許可權是由安全性 & 合規性中心內的**隔離**角色所控制。 根據預設，此角色會指派給安全性 & 合規性中心內的**組織管理**（全域管理員）、**隔離系統管理員**和**安全性管理員**角色群組。 如需詳細資訊，請參閱[Office 365 Security & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

- 隔離的郵件會在自動刪除之前保留在預設時間段內：

  - 反垃圾郵件原則（垃圾郵件、網路釣魚和大量電子郵件）隔離的郵件：30天。 這是預設值和最大值。 若要設定此值，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

  - 郵件流程規則隔離的郵件（規則動作會將**郵件傳遞至主控隔離區**）：30天。 您無法變更此值。

  - 包含惡意程式碼的郵件：15天。

  當郵件從隔離區到期時，您無法復原。

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>使用安全性 & 合規性中心管理隔離的電子郵件

### <a name="view-quarantined-email"></a>查看隔離的電子郵件

1. 在 [安全性與合規性中心] 中，移至「**威脅管理** \> 」**檢查** \> **隔離**。

2. 確認 [被**隔離的視圖**] 設定為預設值**電子郵件**。

3. 您可以按一下可用的欄標題，排序結果。 按一下 [**修改欄**] 以顯示最多7欄。 預設值會以星號（<sup>\*</sup>）標示：

   - **收到**<sup>\*</sup>

   - **發送**<sup>\*</sup>

   - **主題**<sup>\*</sup>

   - **隔離原因**<sup>\*</sup>

   - **釋放？**<sup>\*</sup>

   - **原則類型**<sup>\*</sup>

   - **到期**<sup>\*</sup>

   - **收件者**

   - **郵件識別碼**

   - **原則名稱**

   - **大小**

   - **Direction**

   當您完成時，按一下 [**儲存**]，或按一下 [**設為預設**]。

4. 若要篩選結果，請按一下 [**篩選**]。 可用的篩選包括：

   - **到期時間**：篩選郵件會從隔離區到期：

     - **今天**

     - **今後2天**

     - **未來7天**

     - **自訂**：輸入**開始日期**和**結束日期**。

   - **接收時間**：輸入**開始日期**和**結束日期**。

   - **隔離原因**：

     - **原則**：郵件符合郵件流程規則（也稱為傳輸規則）的條件。

     - **大量郵件**

     - **釣魚**

     - **惡意程式碼**

     - **垃圾郵件**

     - **高信賴網路釣魚**

   - **電子郵件收件**者：所有使用者或僅傳送給您的郵件。 使用者只能管理傳送給他們的隔離郵件。

   若要清除篩選，請按一下 [**清除**]。 若要隱藏 [篩選] 浮出控制項，請再次按一下 [**篩選**]。

5. 使用**排序結果**（預設為**郵件識別碼**按鈕）和對應值以尋找特定郵件。 不支援萬用字元。 您可以依下列值進行搜尋：

   - **郵件識別碼**：郵件的全域唯一識別碼。

        例如，您使用[郵件追蹤](message-trace-scc.md)尋找傳送給組織中使用者的郵件，而您判斷郵件已被隔離而非傳遞。 請務必包含完整的郵件識別碼值，其中可能包含角括弧（\<\>）。 例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。

   - **寄件者電子郵件地址**：單一寄件者的電子郵件地址。

   - **收件者電子郵件地址**：單一收件者的電子郵件地址。

   - 主旨 **：使用**整個郵件主題。 搜尋不區分大小寫。

   輸入搜尋準則之後，請按一下![[重新整理按鈕](../media/scc-quarantine-refresh.png) **重新**整理] 以篩選結果。

找到特定隔離郵件之後，請選取該郵件以查看其詳細資料，並對其採取動作（例如，view、release、下載中心或 delete the message）。

#### <a name="export-message-results"></a>匯出郵件結果

1. 選取您想要的訊息，然後按一下 [**匯出結果**]。

2. 在確認訊息中按一下 **[是]** ，警告您保持瀏覽器視窗的開啟狀態。

3. 當您匯出準備好時，您可以命名並選擇 .csv 檔案的下載位置。

#### <a name="view-quarantined-message-details"></a>查看隔離的郵件詳細資料

當您在清單中選取一封電子郵件時，[**詳細資料**] 彈出窗格中會顯示下列郵件詳細資料：

- **郵件識別碼**：郵件的全域唯一識別碼。

- **寄件者位址**

- **已接收**：收到郵件的日期/時間。

- **Subject**

- **隔離原因**：顯示郵件是否已被識別為**垃圾**郵件、**大量**、**網路釣魚詐騙**、符合郵件流程規則（**傳輸規則**），或被識別為包含**惡意**代碼。

- 收件**者：如果**郵件包含多個收件者，則需要按一下 [**預覽郵件**] 或 [ **View message header** ]，以查看完整的收件者清單。

- **Expires**：從隔離區中自動和永久刪除郵件的日期/時間。

- **已釋出給**：該封郵件曾釋出至的所有電子郵件地址 (如果有的話)。

- 尚未**發行至**：郵件尚未發行的所有電子郵件地址（如果有的話）。

### <a name="take-action-on-quarantined-email"></a>對隔離的電子郵件採取動作

選取郵件後，您可以在 [**詳細資料**] 彈出窗格中，針對郵件執行的動作有好幾個選項：

- **Release message**：在出現的飛入窗格中，選擇下列選項：

  - **將郵件報告給 Microsoft 進行分析**：預設會選取此選項，並將錯誤隔離的郵件以誤報形式報告給 microsoft。 如果郵件被隔離為垃圾郵件、大量、網路釣魚或包含惡意程式碼，則也會向 Microsoft 垃圾郵件分析小組報告該郵件。 視其分析而定，可能會調整全服務垃圾郵件篩選規則，以允許郵件通過。

  - 選擇下列其中一個選項：

    - **放開郵件給所有收件者**

    - **將郵件發佈給特定的收件者**

    - **放開其他人員的訊息**

  當您完成時，按一下 [**放開郵件**]。

  關於釋放郵件的附注：

  - 您無法將郵件多次發佈到相同的收件者。

  - 只有尚未收到郵件的收件者會出現在可能的收件者清單中。

- **View message header**：選擇此連結以查看郵件頭文字。 若要深入分析標頭欄位及值，請將郵件頭文字複製到您的剪貼簿，然後選擇 [ **Microsoft Message Header analyzer** ] 移至遠端連線分析程式（按一下滑鼠右鍵，然後選擇 [在新索引標籤**中開啟]** ，如果您不想讓 Office 365 完成這項工作）。 將郵件頭貼到 [郵件頭分析器] 區段的頁面上，然後選擇 [**分析標頭**：]

- **預覽郵件**：在出現的飛入窗格中，選擇下列其中一個選項：

  - **來源視圖**：顯示已停用所有連結的郵件內文的 HTML 版本。
  
  - **文字視圖**：以純文字顯示郵件內文。

- **從隔離區移除**：在出現的警告中，按一下 [**是]** 之後，就會立即刪除郵件，而不會傳送至原始收件者。

- **下載郵件**：在出現的快顯視窗中，選取 [**我瞭解下載此郵件的風險**]，以以 .eml 格式儲存郵件的本機複本。

- **Submit message**：在出現的飛入窗格中，選擇下列選項：

  - **物件類型**：**電子郵件**（預設值）、 **URL**或**附件**。

  - **提交格式**：**網路消息識別碼**（預設值，具有 [**網路消息識別碼**] 方塊中的對應值 **）或檔案**（流覽至 [本地 .eml] 或 [.msg] 檔案）。 請注意，如果您**選取 [檔案]，然後**選取 [**網路消息識別碼**]，初始值便會消失。

  - 收件**者：輸入**郵件的原始收件者，或按一下 [全**選**] 識別所有收件者。 您也可以按一下 [**全選**]，然後選擇性地移除個別收件者。

  - **提交原因**：**應該未封鎖**（預設）或**應該封鎖**。

  當您完成時，按一下 [**提交**]。

如果您未放開或移除郵件，當預設的隔離保留期間到期時，它會被刪除。

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>對多個隔離的電子郵件採取動作

當您在清單中選取多個隔離郵件（最多100）時，會出現 [**大量動作**] 飛入窗格，您可以在其中採取下列動作：

- **放開郵件**：這些選項與您發佈單一郵件時的選項相同，只是您不能選取 [將**郵件發佈給特定**的收件者]。您只能選取 [**發行訊息給所有**收件者] 或 [**向其他人發佈郵件**]。

- **刪除郵件**：在出現的警告中，按一下 [**是]** 之後，就會立即刪除郵件，而不會傳送至原始收件者。

完成後，按一下 [**關閉**]。

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>僅 ATP：使用安全性 & 合規性中心管理隔離的檔案

> [!NOTE]
> 本節中隔離檔的程式僅適用于 ATP 方案1和 Plan 2 訂閱者。

在具有 ATP 的組織中，系統管理員可以在 SharePoint Online、商務 OneDrive 商務和 Microsoft 小組中管理隔離的檔案。

### <a name="view-quarantined-files"></a>查看隔離的檔案

1. 在 [安全性與合規性中心] 中，移至「**威脅管理** \> 」**檢查** \> **隔離**。

2. 變更**隔離**為**預設值檔的**視圖。 您可以按一下可用的欄標題，依序排序欄位。

3. 您可以按一下可用的欄標題，排序結果。 按一下 [**修改欄**] 以顯示最多7欄。 預設欄會以星號（<sup>\*</sup>）標示：

   - **使用者**<sup>\*</sup>

   - **位置**<sup>\*</sup>

   - **檔案名**<sup>\*</sup>

   - **檔案 URL**<sup>\*</sup>

   - **檔案大小**<sup>\*</sup>

   - **到期**<sup>\*</sup>

   - **釋放？**<sup>\*</sup>

   - **偵測到**

   - **修改時間**

4. 若要篩選結果，請按一下 [**篩選**]。 可用的篩選包括：

   - **到期時間**：篩選郵件會從隔離區到期：

     - **今天**

     - **今後2天**

     - **未來7天**

     - 自訂的日期/時間範圍。

   - **接收時間**

   - **隔離原因**：唯一可用的值為**惡意**代碼。

找到特定隔離的檔案之後，請選取檔案以查看其詳細資料，並對其採取動作（例如，view、release、下載中心或 delete message）。

#### <a name="export-file-results"></a>匯出檔結果

1. 選取您想要的檔，然後按一下 [**匯出結果**]。

2. 在確認訊息中按一下 **[是]** ，警告您保持瀏覽器視窗的開啟狀態。

3. 當您匯出準備好時，您可以命名並選擇 .csv 檔案的下載位置。

#### <a name="view-quarantined-file-details"></a>查看隔離檔詳細資料

當您選取清單中的檔案時，[**詳細資料**] 彈出窗格中會顯示下列檔案詳細資料：

- **檔案名稱**

- 檔案**url**：定義檔案位置的 url （例如，在 SharePoint Online 中）。

- **在上偵測到惡意內容**隔離檔的日期/時間。

- **Expires**：將從隔離區中刪除檔案的日期。

- 偵測**者**： ATP （高級威脅防護）或 Microsoft 的反惡意程式碼引擎。

- **釋放？**

- **惡意軟體名稱**

- **檔識別碼**：檔的唯一識別碼。

- **檔案大小**：以 kb 為單位。

- **組織**您組織的唯一識別碼。

- **上次修改日期**

- **修改者**：上次修改檔案的使用者。

- **安全雜湊演算法 256-位（SHA-256）值**：您可以使用此雜湊值，在其他信譽存放區或您環境中的其他位置識別檔案。

### <a name="take-action-on-quarantined-files"></a>對隔離的檔案採取動作

當您選取清單中的檔案時，您可以對 [**詳細資料**] 彈出窗格中的檔案採取下列動作：

- **發行**檔案：選取（預設值）或取消選取 [ **Microsoft for analysis**]，然後按一下 [**發行**檔案]。

- **下載檔案**

- **從隔離區移除檔案**

如果您未放開或移除檔案，則會在預設的隔離保留期間到期時刪除這些檔案。

#### <a name="actions-on-multiple-quarantined-files"></a>對多個隔離檔的動作

當您在清單中選取多個隔離的檔案（最多100個）時，會出現 [**大量動作**] 飛入窗格，您可以在其中採取下列動作：

- **發行檔**

- **刪除**檔案：在出現的警告中，按一下 [**是]** 後，就會立即刪除檔案。

完成後，按一下 [**關閉**]。

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>使用 Exchange Online PowerShell 或獨立 Exchange Online Protection PowerShell 來查看及管理隔離的郵件和檔案

您用來在隔離區中查看及管理郵件和檔案的 Cmdlet 如下：

- [Delete-Get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Export-Get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [預覽-get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage)：請注意，此 Cmdlet 只適用于 SharePoint Online、商務 OneDrive 或小組的 ATP 中的電子郵件，而非惡意程式碼檔案。

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
