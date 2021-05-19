---
title: 以系統管理員身分管理被隔離的郵件與檔案
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何針對 Exchange Online Protection (EOP) 中的所有使用者，查看及管理隔離的郵件。 使用 Microsoft Defender for Office 365 的組織中的系統管理員也可以管理 SharePoint Online、商務用 OneDrive 和 Microsoft Teams 中的隔離檔案。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 508866fd66e4cbd00f559446d4ce52a4be063c94
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539104"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>在 EOP 中管理隔離的郵件與檔案

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，隔離區會保存可能有害或垃圾郵件。 如需詳細資訊，請參閱 [在 EOP 中隔離的電子郵件訊息](quarantine-email-messages.md)。

系統管理員可以針對所有使用者，查看、發行和刪除所有類型的隔離郵件。 只有系統管理員可以管理被隔離為惡意程式碼、高可信度網路釣魚的郵件，或郵件流程規則的結果 (也稱為傳輸規則) 。 系統管理員也可以將誤報報告給 Microsoft。

使用 Microsoft Defender for Office 365 的組織中的系統管理員也可以在 SharePoint Online、商務用 OneDrive 和 Microsoft Teams 中，查看、下載和刪除隔離的檔案。

您可以在 [安全性 & 合規性中心] 或 [PowerShell (Exchange Online PowerShell 中查看及管理已隔離的郵件，Microsoft 365 組織中 Exchange Online 的信箱;組織的獨立 EOP PowerShell，不 Exchange Online 信箱) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要開啟安全性與合規性中心，請移至 <https://protection.office.com>。 若要直接開啟 [隔離區] 頁面，請移至 <https://protection.office.com/quarantine>。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要對所有使用者執行隔離郵件的動作，您必須是「**組織管理**」、「**安全性管理員**」或「**隔離系統管理員**」 <sup>\*</sup> 角色群組的成員。
  - 若要對所有使用者的隔離郵件進行唯讀存取，您必須是 **全域讀取** 者或 **安全性讀者** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。
  - <sup>\*</sup>**隔離系統管理員** 角色群組的成員也必須是 [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的「**衛生」管理** 角色群組的成員，才能在 Exchange Online PowerShell 中執行隔離程式。

- 隔離的郵件會在自動刪除之前保留在預設時間段內：
  - 30天的反垃圾郵件原則隔離的郵件 (垃圾郵件、網路釣魚和大量電子郵件) 。 這是預設值和最大值。 若要設定 (較低) 此值，請參閱 [設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。
  - 包含惡意程式碼的郵件為15天。
  - 針對 Office 365 的 SharePoint、OneDrive 及 Microsoft Teams 中的安全附件隔離的檔案的15天。

  當郵件從隔離區到期時，您無法復原。

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>使用安全性 & 合規性中心管理隔離的電子郵件

### <a name="view-quarantined-email"></a>查看隔離的電子郵件

1. 在 [安全性 & 規範中心] 中，移至「 **威脅管理**」 \> **檢查** \> **隔離**。

2. 驗證 **[檢視隔離的項目]** 設為 **[電子郵件]** 的預設值。

3. 您可以按一下可用資料行標題來排序結果。 按一下 [修改資料行] 可顯示最多七個資料行。 預設值會標上星號 (<sup>\*</sup>)：

   - **收到日期**<sup>\*</sup>
   - **寄件者**<sup>\*</sup>
   - **主旨**<sup>\*</sup>
   - **隔離原因**<sup>\*</sup>
   - **已釋出？**<sup>\*</sup>
   - **原則類型**<sup>\*</sup>
   - **到期**
   - **收件者**
   - **郵件識別碼**
   - **原則名稱**
   - **大小**
   - **方向**

   完成時，請按一下 [儲存]，或按一下 [設為預設值]。

4. 若要篩選結果，請按一下 [篩選]。 可用的篩選條件如下：

   - **到期時間**：依郵件將於隔離區中到期的時間進行篩選：
     - **今天**
     - **未來 2 天**
     - **未來 7 天**
     - **自訂**：輸入 [開始日期] 和 [結束日期]。

   - **收到時間**：輸入 [開始日期] 和 [結束日期]。

   - **隔離原因**：
     - **原則**：郵件符合郵件流程規則的條件 (也稱為傳輸規則) 。
     - **大量郵件**
     - **網路釣魚**：垃圾郵件篩選判定為 **網路釣魚電子郵件** 或反網路釣魚防護隔離郵件 ([欺騙設定](set-up-anti-phishing-policies.md#spoof-settings) 或 [模仿保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)) 。
     - **惡意程式碼**
     - **垃圾郵件**
     - **高信賴網路釣魚**

   - **原則類型**：依原則類型篩選郵件：
     - **反惡意程式碼原則**
     - **安全附件原則**
     - **反網路釣魚原則**
     - **託管的內容篩選原則** (反網路釣魚原則)
     - **傳輸規則**

   - **電子郵件收件** 者：所有使用者或僅傳送給您的郵件。 使用者只能管理傳送給他們的隔離郵件。

   若要清除篩選，按一下 [清除]。 若要隱藏 [篩選] 飛出視窗，再按一下 [篩選]。

5. 使用 [結果排序依據] (預設為 [郵件識別碼] 按鈕) 和對應值來尋找特定郵件。 不支援萬用字元。 您可以依下列值進行搜尋：

   - **郵件識別碼**：郵件的全域唯一識別碼。

     例如，您使用 [郵件追蹤](message-trace-scc.md) 尋找傳送給組織中使用者的郵件，而您判斷郵件已被隔離而非傳遞。 請務必包含完整的郵件識別碼值，其中可能包含角括弧 (\<\>) 。 例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。

   - **寄件者電子郵件地址**：單一寄件者的電子郵件地址。

   - **原則名稱**：使用郵件的整個原則名稱。 搜尋時不會區分大小寫。

   - **收件者電子郵件地址**：單一收件者的電子郵件地址。

   - **主旨**：使用郵件的完整主旨。 搜尋時不會區分大小寫。

   - **原則名稱**：負責隔離郵件的原則名稱。

   輸入搜尋準則後，請按一下![重新整理按鈕](../../media/scc-quarantine-refresh.png) [重新整理] 來篩選結果。

當您找到特定隔離郵件後，選取該郵件即可檢視其詳細資料，並對其採取動作 (例如檢視、釋出、下載或刪除郵件)。

#### <a name="view-quarantined-message-details"></a>檢視隔離郵件詳細資料

當您選取清單中的電子郵件訊息時，[詳細資料] 飛出窗格中會出現下列郵件詳細資料：

- **郵件識別碼**：郵件的全域唯一識別碼。

- **寄件者位址**

- **收到日期**：收到郵件的日期/時間。

- **主旨**

- **隔離原因**：顯示郵件是否已識別為 **垃圾** 郵件、 **大量**、 **網路釣魚詐騙**、符合郵件流程規則 (**傳輸規則**) 或已識別為包含 **惡意** 代碼。

- **收件者計數**

- **收件者**：如果郵件包含多個收件者，則必須按一下 [預覽郵件] 或 [檢視郵件標頭] 以查看完整的收件者清單。

- **到期**：郵件會自動從隔離區永久刪除的日期/時間。

- **已釋出給**：該封郵件曾釋出至的所有電子郵件地址 (如果有的話)。

- **尚未釋出給**：該封郵件尚未釋出至的所有電子郵件地址 (如果有的話)。

### <a name="take-action-on-quarantined-email"></a>對隔離的電子郵件採取動作

選取郵件後，您可以在 [ **詳細資料** ] 彈出窗格中，針對郵件執行的動作有好幾個選項：

- **Release message**：在出現的飛入窗格中，選擇下列選項：

  - **將郵件報告給 Microsoft 進行分析**：預設會選取此選項，並將錯誤隔離的郵件以誤報形式報告給 microsoft。 如果郵件被隔離為垃圾郵件、大量、網路釣魚或包含惡意程式碼，則也會向 Microsoft 垃圾郵件分析小組報告該郵件。 視其分析而定，可能會調整全服務垃圾郵件篩選規則，以允許郵件通過。

  - 選擇下列其中一個選項：
    - **放開郵件給所有收件者**
    - **將郵件發佈給特定的收件者**
    - **為其他人發行訊息**：請注意，不支援將惡意程式碼封發行給原始收件者以外的人員。

  完成時，請按一下 [釋出郵件]。

  關於釋放郵件的附注：

  - 您無法將郵件多次發佈到相同的收件者。
  - 只有尚未收到郵件的收件者會出現在可能的收件者清單中。

- **檢視郵件標頭**：選擇此連結來查看郵件標頭文字。 若要深入分析標頭欄位和值，請將郵件標頭文字複製到您的剪貼簿，然後選擇 [Microsoft 郵件標頭分析器] 來移至遠端連線分析程式 (如果您想在不離開 Microsoft 365 的情況下完成這項工作，請按一下滑鼠右鍵並選擇 [在新索引標籤中開啟])。 將郵件標頭貼至 [郵件標頭分析器] 區段的頁面上，並選擇 [分析標頭]：

- **預覽郵件**：在出現的飛出窗格中，選擇下列其中一個選項：
  - **原始碼檢視**：顯示已停用所有連結的郵件內文 HTML 版本。
  - **文字檢視**：以純文字顯示郵件內文。

- **從隔離區移除**：在出現的警告中，按一下 [ **是]** 之後，就會立即刪除郵件，而不會傳送至原始收件者。

- **下載郵件**：在出現的飛出窗格中，選取 [我了解下載此郵件的風險] 以使用 .eml 格式儲存郵件的本機複本。

- **封鎖寄件者**：將寄件者新增到您信箱上的封鎖寄件者清單。 如需詳細資訊，請參閱[封鎖郵件寄件者](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

- **Submit message**：在出現的飛入窗格中，選擇下列選項：

  - **物件類型**： **電子郵件** (預設) 、 **URL** 或 **附件**。

  - **提交格式**： **網路郵件識別碼** (預設值，並在 [ **網路消息識別碼** ] 方塊中顯示對應的值) 或 **檔案 (流覽** 至本地 .eml 或 .msg 檔案) 。 請注意，如果您 **選取 [檔案]，然後** 選取 [ **網路消息識別碼**]，初始值便會消失。

  - 收件 **者：輸入** 郵件的原始收件者，或按一下 [全 **選**] 識別所有收件者。 您也可以按一下 [ **全選** ]，然後選擇性地移除個別收件者。

  - **提交原因**： **應該不會封鎖** (預設) 或 **應該封鎖**。

  當您完成時，按一下 [ **提交**]。

如果您未釋出或移除郵件，則郵件會在預設的隔離保留期間到期後遭到刪除。

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>對多個隔離的電子郵件採取動作

當您選取清單中的多個隔離郵件 (最多 100 個) 時，隨即會出現 [大量動作] 飛出窗格供您採取下列動作：

- **釋出郵件**：這些選項與您釋出單一郵件時的選項相同，差別只在您無法選取 [將郵件釋出給特定收件者]；您只能選取 [將郵件釋出給所有收件者] 或 [將郵件釋出給其他人]。

  > [!NOTE]
  > 請考慮下列案例： john@gmail.com 會將郵件傳送至 faith@contoso.com 和 john@subsidiary.contoso.com。 Gmail 會將此郵件 bifurcates 成兩個副本，以在 Microsoft 中路由傳送至隔離區。 系統管理員會將這兩封郵件都發行至 admin@contoso.com。 傳遞到達系統管理員信箱的第一個已發佈郵件。 第二個發行的郵件會被識別為重複傳遞，而且會略過。 如果郵件有相同的郵件識別碼和接收時間，便會將它識別為重複郵件。

- **刪除郵件**：在出現的警告中，按一下 [ **是]** 之後，就會立即刪除郵件，而不會傳送至原始收件者。

完成時，請按一下 [關閉]。

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>僅適用于 Office 365 的 Microsoft Defender：使用安全性 & 相容性中心管理隔離的檔案

> [!NOTE]
> 本節中隔離檔的程式僅適用于 Office 365 方案1和計畫2訂閱者的 Microsoft Defender。

在具有 Office 365 的 Defender 的組織中，系統管理員可以管理 SharePoint Online、商務用 OneDrive 和 Microsoft Teams 中的隔離檔案。 若要啟用這些檔案的保護，請參閱[開啟安全附件以取得 SharePoint、OneDrive 及 Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)。

### <a name="view-quarantined-files"></a>查看隔離的檔案

1. 在 [安全性 & 規範中心] 中，移至「 **威脅管理**」 \> **檢查** \> **隔離**。

2. 變更 **隔離****至值檔的** 視圖。 您可以按一下可用的欄標題，依序排序欄位。

3. 您可以按一下可用資料行標題來排序結果。 按一下 [修改資料行] 可顯示最多七個資料行。 預設的欄會以星號 () 標示 <sup>\*</sup> ：

   - **使用者**<sup>\*</sup>
   - **位置**<sup>\*</sup>
   - **檔案名**<sup>\*</sup>
   - **檔案 URL**<sup>\*</sup>
   - **檔案大小**<sup>\*</sup>
   - **到期**<sup>\*</sup>
   - **已釋出？**<sup>\*</sup>
   - **偵測到**
   - **修改時間**

4. 若要篩選結果，請按一下 [篩選]。 可用的篩選條件如下：

   - **到期時間**：依郵件將於隔離區中到期的時間進行篩選：
     - **今天**
     - **未來 2 天**
     - **未來 7 天**
     - 自訂的日期/時間範圍。
   - **接收時間**
   - **隔離原因**：唯一可用的值為 **惡意** 代碼。
   - **原則類型**

找到特定隔離的檔案之後，請選取檔案以查看其詳細資料，並對其採取動作 (例如，view、release、下載中心或 delete message) 。

#### <a name="view-quarantined-file-details"></a>查看隔離檔詳細資料

當您選取清單中的檔案時，[ **詳細資料** ] 彈出窗格中會顯示下列檔案詳細資料：

- **檔案名稱**
- 檔案 **url**：定義檔案位置的 url (例如，在 SharePoint 線上) 中。
- **在上偵測到惡意內容** 隔離檔的日期/時間。
- **Expires**：將從隔離區中刪除檔案的日期。
- 偵測： Office 365 或 Microsoft 的反惡意程式碼 **引擎的 Defender**。
- **已釋出？**
- **惡意軟體名稱**
- **檔識別碼**：檔的唯一識別碼。
- **檔案大小**： KB (kb) 。
- **組織** 您組織的唯一識別碼。
- **上次修改日期**
- **修改者**：上次修改檔案的使用者。
- **安全雜湊演算法 256-位 (SHA-256) 值**：您可以使用此雜湊值，在其他信譽存放區或您環境中的其他位置識別檔案。

### <a name="take-action-on-quarantined-files"></a>對隔離的檔案採取動作

當您選取清單中的檔案時，您可以對 [ **詳細資料** ] 彈出窗格中的檔案採取下列動作：

- **版本** 檔案：選取 [ (預設值]) 或取消選取 [ **Microsoft for Analysis] 的報表** 檔案，然後按一下 [ **釋放檔**]。
- **下載檔案**
- **從隔離區移除檔案**

如果您未放開或移除檔案，則會在預設的隔離保留期間到期時刪除這些檔案。

#### <a name="actions-on-multiple-quarantined-files"></a>對多個隔離檔的動作

當您在清單中選取多個隔離的檔案 (直到 100) 時，會出現 [ **大量動作** ] 彈出窗格，您可以在其中採取下列動作：

- **發行檔**
- **刪除** 檔案：在出現的警告中，按一下 [ **是]** 後，就會立即刪除檔案。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>使用 Exchange Online PowerShell 或獨立 EOP PowerShell 來查看及管理隔離的郵件和檔案

您用來在隔離區中查看及管理郵件和檔案的 Cmdlet 如下：

- [Delete-Get-quarantinemessage](/powershell/module/exchange/delete-quarantinemessage)

- [Export-Get-quarantinemessage](/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)

- [預覽-get-quarantinemessage](/powershell/module/exchange/preview-quarantinemessage)：請注意，此 Cmdlet 只適用于郵件，而不是從 SharePoint、OneDrive 和 Microsoft Teams 的安全附件隔離檔案。

- [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
