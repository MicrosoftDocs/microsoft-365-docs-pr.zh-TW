---
title: 系統管理報送
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用 Microsoft 365 Defender 入口網站中的提交入口網站，將可疑的電子郵件、可疑網路釣魚郵件、垃圾郵件和其他可能有害的郵件、URLs 和電子郵件附件傳送給 Microsoft 以重新掃描。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e2fc859ea7df5e85ef65d1ad6f2a09f8806dd58
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893749"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)


在 Microsoft 365 具有 Exchange Online 信箱的組織中，系統管理員可以使用 Microsoft 365 Defender 入口網站中的提交入口網站，將電子郵件訊息、URLs 及附件提交給 Microsoft 以進行掃描。

當您提交電子郵件訊息時，您會收到：

- **電子郵件驗證檢查**：傳送電子郵件時的驗證是否已通過或失敗的詳細資料。
- **原則點擊**：有關任何可能允許或封鎖內送電子郵件進入您租使用者之原則的資訊，請覆寫我們的服務篩選 verdicts。
- 「**負載信譽/引爆**：檢查郵件中的任何 URLs 和附件。
- **評分分析**：檢查是否有惡意的「人工 graders 完成」。

> [!IMPORTANT]
> 在所有承租人中都不會進行負載信譽/引爆和評分分析。 當資料不應該保留租使用者界限以符合合規性目的時，就會封鎖資訊，避免進入組織外部。

如需其他方式將電子郵件訊息、URLs 和附件提交給 Microsoft，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您可以在中開啟 Microsoft 365 的 Defender 入口網站 <https://security.microsoft.com/> 。 若要直接移至 [ **提交** ] 頁面，請使用 <https://security.microsoft.com/reportsubmission> 。

- 若要將郵件和檔案提交給 Microsoft，您必須是下列其中一個角色群組的成員：
  - [Microsoft 365 Defender 入口網站](permissions-microsoft-365-security-center.md)中的 **組織管理** 或 **安全性讀者**。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理**。

    請注意，此角色群組的成員資格是 [查看使用者送至自訂信箱的使用者](#view-user-submissions-to-microsoft) ，如本文稍後所述。

- 如需使用者如何提交郵件和檔案給 Microsoft 的詳細資訊，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。

## <a name="report-suspicious-content-to-microsoft"></a>向 Microsoft 報告可疑內容

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **提交**]。

2. 在 [ **提交** ] 頁面上，確認已選取 [已 **提交的分析** ] 索引標籤，然後按一下 [ ![ Ad 圖示 ](../../media/m365-cc-sc-create-icon.png) **提交至 Microsoft 進行分析**]。

3. 使用送出 **至 Microsoft 來審閱** 浮出的浮出的浮出方式，如下列各節所述提交郵件、URL 或電子郵件附件。

### <a name="submit-a-questionable-email-to-microsoft"></a>將可疑的電子郵件提交給 Microsoft

1. 在 [ **選取提交類型** ] 方塊中，確認下拉式清單中已選取 [ **電子郵件** ]。

2. 在 [ **新增網路消息識別碼] 或 [上傳電子郵件** 檔案] 區段中，使用下列其中一個選項：
   - **新增電子郵件網路郵件識別碼**：此為 GUID 值，可在郵件中的 **X-MS-Exchange-Organization-網路 Message-Id** 標頭中，或在 Office365 中的 **X-** ----------------------------
   - **Upload 電子郵件檔 ( .msg 或 .eml)**：按一下 **[流覽檔案]**。 在開啟的對話方塊中，尋找並選取 .eml 或 .msg 檔案，然後按一下 [ **開啟**]。

   > [!NOTE]
   > 將郵件送出多久30天，已暫時為 Office 365 客戶的 Defender 停用。 系統管理員只可以回復7天。

3. 在 [ **選擇有問題的收件者** ] 方塊中，指定您想要執行原則檢查的收件者。 原則檢查會決定是否因使用者或組織原則而略過掃描的電子郵件。

4. 在 [ **選取要提交給 Microsoft 的原因** ] 區段中，選取下列其中一個選項：
   - **不應該封鎖 (誤報)**
   - **應該已封鎖**：在 [ **電子郵件應該已分類成** ] 區段中，選取下列其中一個值 (如果您不確定，請使用您的最佳 judgement) ：
     - **網路釣魚**
     - **垃圾郵件**
     - **惡意程式碼**

5. 完成作業後，請按一下 [ **提交** ] 按鈕。

   ![新的 URL 提交範例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>將可疑 URL 傳送給 Microsoft

1. 在 [ **選取提交類型** ] 方塊中，從下拉式清單中選取 [ **URL** ]。

2. 在出現的 [ **url** ] 方塊中，輸入完整的 URL (例如， `https://www.fabrikam.com/marketing.html`) 。

3. 在 [ **選取要提交給 Microsoft 的原因** ] 區段中，選取下列其中一個選項：
   - **不應該封鎖 (誤報)**
   - **應該已封鎖**：在 **此 URL 中，應該已分類為** 所出現的區段，請選取 [ **網路釣魚** 或 **惡意** 代碼]。

4. 完成作業後，請按一下 [ **提交** ] 按鈕。

   ![新的電子郵件提交範例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>將可疑的電子郵件附件提交給 Microsoft

1. 在 [ **選取提交類型** ] 方塊中， **從下拉式清單中選取** [檔案]。

2. 在出現的 [ **檔** ] 區段中，按一下 **[流覽檔案]**。 在開啟的對話方塊中，尋找並選取檔，然後按一下 [ **開啟**]。

3. 在 [ **選取要提交給 Microsoft 的原因** ] 區段中，選取下列其中一個選項：
   - **不應該封鎖 (誤報)**
   - **應該已封鎖**：在 **此 URL 中，應該已分類為** 所出現的區段， **惡意** 代碼是唯一的選擇，而且會自動加以選取。

4. 完成作業後，請按一下 [ **提交** ] 按鈕。

   ![新附件提交範例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions-to-microsoft"></a>查看對 Microsoft 的系統管理員報送

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **提交**]。

2. 在 [ **提交** ] 頁面上，確認已選取 [已 **提交進行分析** ] 索引標籤。

   - 您可以按一下可用的欄標題，排序專案。 按一下 [ **自訂欄** ] 以顯示最多7欄。 預設值會標上星號 (<sup>\*</sup>)：
     - **提交名稱**<sup>\*</sup>
     - **發送**<su>\*</sup>
     - **提交日期**<sup>\*</sup>
     - **提交類型**<sup>\*</sup>
     - **提交原因**<sup>\*</sup>
     - **重新掃描狀態**<sup>\*</sup>
     - **重新掃描結果**<sup>\*</sup>
     - **篩選判定**
     - **傳遞/封鎖原因**
     - **提交識別碼**
     - **網路消息識別碼/物件識別碼**
     - **方向**
     - **寄件者 IP**
     - **大量相容層級 (BCL)**
     - **目的地**
     - **原則動作**
     - **提交者**

     當您完成時 **，按一下 [** 套用]。

   - 若要篩選項目，請按一下 [ **篩選**]。 可用的篩選條件如下：
     - **提交日期**： **開始日期** 和 **結束日期**。
     - **提交類型**： **電子郵件**、 **URL** 或 **檔案**。
     - **提交識別碼**：指派給每個提交的 GUID 值。
     - **網路消息識別碼**
     - **Sender**

     當您完成時 **，按一下 [** 套用]。

     ![管理員報送的新篩選選項](../../media/admin-submission-email-filter-options.png)

   - 若要群組專案，請按一下 [ **群組** ]，然後從下拉式清單中選取下列其中一個值：
     - **無**
     - **類型**
     - **原因**
     - **狀態**
     - **重新掃描結果**

   - 若要匯出專案，請按一下 [ **匯出**]。 在出現的對話方塊中，儲存 .csv 檔。

### <a name="admin-submission-rescan-details"></a>系統管理員提交重新掃描詳細資料

在系統管理提交中送出的郵件會重新掃描，並顯示在提交詳細資料浮出控制項中的結果：

- 寄件者在傳遞電子郵件時，電子郵件驗證是否失敗。
- 任何有關可能會影響或覆寫郵件決策的原則點擊的資訊。
- 目前的引爆結果，查看郵件中所含的 URL 或檔案是否惡意。
- Graders 的意見反應。

如果發現覆寫，則應該會在幾分鐘內完成重新掃描。 如果電子郵件驗證或傳遞中沒有問題，則不會受到覆寫的影響，來自 graders 的意見反應可能需要一天。

## <a name="view-user-submissions-to-microsoft"></a>查看 Microsoft 的使用者報送

如果您已部署 [報表訊息增益集](enable-the-report-message-add-in.md)、[報告網路釣魚增益集](enable-the-report-phish-add-in.md)或人員在 [網頁上使用 Outlook 內建的報表](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)，您可以在 [**使用者報告的郵件**] 索引標籤上看到要報告的使用者。

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **提交**]。

2. 在 [ **提交** ] 頁面上，選取 [ **使用者報告的郵件** ] 索引標籤。

   - 您可以按一下可用的欄標題，排序專案。 按一下 [ **自訂欄** ] 以顯示最多7欄。 預設值會標上星號 (<sup>\*</sup>)：

     - **電子郵件主題**<sup>\*</sup>
     - **報告者**<su>\*</sup>
     - **報告日期**<sup>\*</sup>
     - **寄件者**<sup>\*</sup>
     - **報告原因**<sup>\*</sup>
     - **重新掃描結果**<sup>\*</sup>
     - **訊息報告識別碼**
     - **網路消息識別碼**
     - **寄件者 IP**
     - **網路釣魚模擬模擬**

     當您完成時 **，按一下 [** 套用]。

   - 若要篩選項目，請按一下 [ **篩選**]。 可用的篩選條件如下：
     - **報告日期**： **開始日期** 和 **結束日期**。
     - **報告者**
     - **電子郵件主旨**
     - **訊息報告識別碼**
     - **網路消息識別碼**
     - **Sender**
     - 已 **報告原因**：**非垃圾郵件**、**網路釣魚** 或 **垃圾郵件**。
     - **網路釣魚模擬**： **是** 或 **否**

     當您完成時 **，按一下 [** 套用]。

    ![使用者提交的新篩選選項](../../media/user-submissions-filter-options.png)

   - 若要群組專案，請按一下 [ **群組** ]，然後從下拉式清單中選取下列其中一個值：
     - **無**
     - **原因**
     - **Sender**
     - **報告者**
     - **重新掃描結果**
     - **網路釣魚模擬模擬**

   - 若要匯出專案，請按一下 [ **匯出**]。 在出現的對話方塊中，儲存 .csv 檔。

> [!NOTE]
> 如果組織已設定為將使用者報告的郵件傳送至自訂信箱，則不會傳送報告的郵件進行重新掃描，而且 **使用者報告的訊息** 中的結果將永遠為空。

### <a name="undo-user-submissions"></a>撤銷使用者報送

一旦使用者將可疑的電子郵件提交至自訂信箱，使用者和系統管理員就沒有任何可復原提交的選項。 如果使用者想要復原電子郵件，將可在 [刪除的郵件] 或 [垃圾郵件] 資料夾中復原。

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>從自訂信箱將郵件提交給 Microsoft

如果您已將自訂信箱設定為在未傳送郵件給 Microsoft 的情況下截獲使用者報告的郵件，您可以尋找特定郵件並將其傳送給 Microsoft 進行分析。 這會有效地將使用者提交權移至系統管理員提交。

在 [ **使用者報告的郵件** ] 索引標籤上，選取清單中的訊息，按一下 [ **提交給 Microsoft 進行分析**]，然後從下拉式清單中選取下列其中一個值：

- **報告清理**
- **報告網路釣魚**
- **報告惡意程式碼**
- **報告垃圾郵件**
- **觸發調查**

![動作按鈕上的新選項](../../media/user-submission-custom-mailbox-action-button.png)
