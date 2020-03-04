---
title: '尋找和調查已傳遞 Office 365 中的惡意電子郵件、 修復，補救、 修復， '
keywords: TIMailData-內嵌圖案，安全性事件事件，ATP PowerShell 電子郵件的惡意程式碼、 危害使用者釣魚程式的電子郵件、 惡意程式碼的電子郵件、 讀取電子郵件標頭、 讀取標頭、 開啟電子郵件標頭
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威脅調查及回應功能來尋找並調查惡意電子郵件。
ms.openlocfilehash: 1cb7c418e9c4ae5f2223748d512e8718f81b010c
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409748"
---
# <a name="investigate-and-remediate-malicious-email-that-was-delivered-in-office-365"></a>調查並修復 Office 365 中已傳遞的惡意電子郵件

[Office 365 進階威脅防護](office-365-atp.md)可讓您調查放入風險，貴組織的人員的活動，並採取動作來保護您的組織。 例如，如果您是貴組織的安全性小組的一部分，您可以尋找和調查可疑的電子郵件已傳遞。 您可以使用[威脅總管 （或即時偵測的資訊）](threat-explorer.md)。
  
## <a name="before-you-begin"></a>開始之前...

請確定符合下列需求：
  
- 您的組織有[Office 365 進階威脅防護](office-365-atp.md)，並[將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)。
    
- [Office 365 稽核記錄](../../compliance/turn-audit-log-search-on-or-off.md)已為您的組織。 
    
- 貴組織的原則定義的反垃圾郵件、 反惡意程式碼、 反網路釣魚，依此類推。 請參閱[針對 Office 365 中的威脅保護](protect-against-threats.md)。
    
- 您是 Office 365 全域管理員，或具有安全性系統管理員或 「 搜尋及清除角色指派安全性&amp;合規性中心。 請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 某些動作，您也必須具備新預覽角色指派。 

#### <a name="preview-role-permissions"></a>預覽角色權限

若要執行某些動作，例如檢視郵件標頭或下載電子郵件訊息內容，您必須呼叫*預覽*新增至另一個適當的 Office 365 角色群組的新角色。 下表釐清所需的角色和權限。

|活動  |角色群組 |所需的預覽角色？  |
|---------|---------|---------|
|使用分析威脅威脅總管 （和即時偵測的資訊）     |Office 365 全域管理員 <br> 安全性系統管理員 <br> 安全性讀取者     | 否   |
|使用檢視的電子郵件，以及預覽標頭和下載隔離區的電子郵件威脅總管 （和即時偵測的資訊）    |Office 365 全域管理員 <br> 安全性系統管理員 <br>安全性讀取者   |       否  |
|使用威脅總管檢視標頭，並下載傳遞至信箱的電子郵件     |Office 365 全域管理員 <br>安全性系統管理員 <br> 安全性讀取者 <br> 預覽   |   是      |

> [!NOTE]
> *預覽*是角色並不是角色群組。「 預覽 」 角色必須新增至現有的角色群組，以 Office 365。 Office 365 全域系統管理員角色指派的 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))，並安全性管理員和安全性讀取者 」 角色指派 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))。 若要深入了解角色和權限，請參閱[Office 365 安全性 & 合規性中心的權限](permissions-in-the-security-and-compliance-center.md)。

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>尋找並刪除可疑的電子郵件的郵件傳遞

威脅總管是功能強大的報表，可以有多個用途，例如尋找及刪除的郵件，用來識別惡意電子郵件寄件者的 IP 位址或開始進一步調查的事件。 下列程序著重於使用 Explorer 來尋找並從收件者的信箱刪除惡意電子郵件。

1. **瀏覽至威脅總管**： 移至[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。 這會帶您前往安全性&amp;合規性中心。

2. 在左的導覽快速-啟動中，選擇 [**威脅管理** \> **總管**。

    ![總管] 中的傳遞巨集指令與傳遞位置欄位。](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. **威脅總管中的檢視**： 在 [**檢視**] 功能表中，選擇 [**所有電子郵件**。

    ![威脅總管檢視] 功能表中，與電子郵件-惡意程式碼、 釣魚程式、 送出資料及所有的電子郵件選項，也內容-惡意程式碼。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    *惡意程式碼*檢視目前預設值，並會擷取電子郵件在偵測到惡意程式碼威脅。 釣魚程式相同的方式運作的*釣魚程式*檢視。

    不過，*所有電子郵件*] 檢視會列出每個組織中，所收到的郵件是否或未偵測到的威脅。 您可以想像，這會是大量資料，這就是為什麼這個檢視會顯示套用要求篩選器的預留位置。 （此檢視是僅供 ATP P2 客戶）。

    *提交*] 檢視會顯示所有的郵件提交系統管理員或使用者回報給 Microsoft。

4. **搜尋和威脅總管中的篩選**： 篩選顯示在頁面頂端的可協助系統管理員在其調查中的 [搜尋] 列中。 請注意，多個篩選可以套用在相同的時間，並新增至篩選器來縮小搜尋多個以逗號分隔值。 請記得：
    - 篩選器完全符合在大部分的篩選條件。
    - 主旨篩選會使用包含查詢。
    - URL 篩選器的運作或者沒有通訊協定 (ex。 https)。
    - URL 網域上、 URL 路徑及 URL 的網域和路徑篩選不需要一種通訊協定來篩選。
    - 每次變更篩選值，以取得相關的結果，您必須按一下 [重新整理] 圖示。

5. **進階篩選**： 使用這些篩選器，您可以建立複雜的查詢，並篩選您的資料集。 按一下 [*進階篩選*] 開啟彈出式選項。

   進階篩選是另一項絕佳搜尋功能。 布林值**不可**篩選具有已引進*收件者*、*寄件者*和*寄件者網域*以允許系統管理員来調查藉由排除值。 此選項會出現在*不包含*的 selection 參數。 **不**會讓系統管理員排除警示的信箱，預設回覆信箱從其調查，也很適合其中系統管理員搜尋特定主題的情況下 (主旨 ="注意 」) 其中收件者可以設定成 [*無 defaultMail@contoso.com*。 這是實際值搜尋。

   ![收件者-'不包含' 進階篩選器。](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *篩選由小時*可協助貴組織的安全性小組快速向下切入。 最短的允許的時間期間是 30 分鐘。 如果您可以縮小時間範圍可疑採取動作 （例如它發生 3 小時前），這會限制內容，並協助找出問題。

  ![篩選時數] 選項來縮小的量資料安全性小組必須處理程序，以及其最短的持續時間是 30 分鐘。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **威脅總管] 中的欄位**： 威脅總管公開*傳遞巨集指令*、*傳遞位置*、*特殊巨集指令*、*方向*、*會覆寫*，以及*URL 威脅*等更多的安全性相關的郵件資訊。 它也可讓貴組織的安全性小組，以調查以較高的確實方式。 

    *傳遞動作*是因為現有的原則或偵測電子郵件所採取的動作。 以下是電子郵件可能採取的動作：
    - **已傳遞**– 電子郵件已傳遞至收件匣或資料夾的使用者和該使用者可以直接存取。
    - **Junked** （已傳遞至垃圾郵件） – 電子郵件已傳送至任一使用者的垃圾郵件] 資料夾，或刪除的資料夾，且使用者在其 [垃圾郵件或刪除的郵件] 資料夾中具有存取電子郵件訊息。
    - **封鎖**– 任何電子郵件遭到隔離的郵件，會失敗，或者已卸除。 （這是完全無法存取的使用者）。
    - **取代**– 惡意附件由 state 附件的.txt 檔案所取代其中任何電子郵件已惡意

    **傳遞位置**： 傳遞位置篩選器是可用以協助系統管理員了解其中可疑惡意郵件結束延展及在其上所採取的行動。 產生的資料可以匯出至試算表。 可能的傳遞位置如下：
    - **收件匣或資料夾**– 電子郵件是在收件匣] 或 [特定的資料夾，根據您的電子郵件規則。
    - **在內部或外部**– 信箱定域機組中不存在，但內部。
    - **垃圾郵件資料夾**– 電子郵件是在使用者的垃圾郵件] 資料夾。
    - **刪除的項目] 資料夾**– 電子郵件是在使用者的已刪除項目] 資料夾中。
    - **隔離**-隔離區，而不是在使用者信箱的電子郵件。
    - **失敗**– 電子郵件無法連到信箱。
    - **丟棄**– 電子郵件的某處遺失，在 [郵件流程。

    **Directionality**： 此選項可讓您的安全性作業小組，以篩選 '' 的郵件來自，或方向將要。 Directionality 值是*輸入*、*輸出*中，與*組織內部*（對應至郵件進入從您組織外部、 傳送超出您的組織，或傳送在內部到您組織中，分別）。 這項資訊可以幫助瓶頸詐騙及模擬，安全性作業小組，因為方向不相符的值 （例如。 *輸入*)，以及 （哪一個*出現*的內部網域） 將會明顯的寄件者網域 ！ Directionality 值不同，且可以與不同，郵件追蹤。 結果可以匯出至試算表。

    **會覆寫**： 此篩選採用資訊會出現在郵件的詳細資料] 索引標籤上，使用它來公開其中組織，或使用者原則，允許與封鎖的郵件都已*覆寫*。 關於此篩選器的重點是它可以協助貴組織的安全性小組，請參閱多少可疑的電子郵件已傳遞因為組態。 這可以讓它們修改機會允許與封鎖視。 此篩選器的此結果集可以匯出至試算表。

|威脅總管] 中覆寫  | 及其所代表的意義  |
|---------|---------|
|允許組織原則     |   郵件已允許入信箱，因為組織原則所導入。       |
|封鎖的組織原則      |  依照指示組織原則所傳遞到信箱已封鎖郵件。    |
|Org 原則所封鎖的副檔名     | 在傳遞至信箱已封鎖檔案類型為導向的組織原則。        |
|允許使用者原則     | 郵件已允許入信箱，因為使用者原則所導入。        |
|封鎖的使用者原則     | 依照指示使用者原則所傳遞到信箱已封鎖郵件。        |

**URL 威脅**： URL 威脅欄位已包含在電子郵件給指出 URL 所呈現的威脅的 [*詳細資料*] 索引標籤上。 URL 所呈現的威脅可以包含*惡意程式碼*、*釣魚程式*或*垃圾郵件*，並*沒有威脅*與 URL 會像是*無*威脅] 區段中。

7. **電子郵件 [時間表] 檢視**： 安全性作業小組可能需要太深-探討調查的電子郵件詳細資料來進一步。 電子郵件時間表可讓系統管理員來檢視在傳遞至後續傳遞電子郵件採取的動作。 若要檢視的電子郵件時間表，按一下主旨的電子郵件訊息，，，然後按一下 [電子郵件時間表。 （它出現在像摘要] 或 [詳細資料] 面板上的其他標題之間）。這些結果可以匯出至試算表。

    顯示所有傳遞和電子郵件的後續傳遞事件的資料表會開啟電子郵件時間表。 如果沒有電子郵件上的沒有進一步動作，您應該會看到原始傳遞表示結果，例如*封鎖*，與 verdict 像*釣魚程式*的單一事件。 系統管理員可以匯出整個電子郵件時間表，包括所有的詳細資料] 索引標籤和電子郵件 （例如，主旨、 寄件者、 收件者、 網路和訊息識別碼）。 電子郵件時間表剪下向下上隨機化因為較少的時間所花費的嘗試了解事件發生於由於電子郵件抵達檢查不同的位置。 當多個事件會發生，在或接近，同時在一封電子郵件時，這些事件顯示在 [時間表] 檢視。

8. **預覽 / 下載**： 威脅總管提供安全性作業小組他們需要調查可疑的電子郵件的詳細資料。 您的安全性作業小組可以：

    - [請檢查傳遞動作及位置](#check-the-delivery-action-and-location)。

    - [檢視您的電子郵件的時間表](#view-the-timeline-of-your-email)。

    ##### <a name="check-the-delivery-action-and-location"></a>請檢查傳遞動作及位置

    在 [[威脅總管 （和即時偵測的資訊）](threat-explorer.md)，您現在可以**傳遞巨集指令**並**傳遞位置**而不是前者**傳遞狀態**] 欄中的資料行。 這會導致更完整的地方您的電子郵件訊息園地圖片。 組件的這項變更的目標是要讓調查安全性作業小組，更容易，但最終結果知道一眼問題電子郵件的位置。

    傳遞狀態現在劃分為兩個資料行：

    - **傳遞動作**-這封電子郵件的狀態為何？

    - **傳遞位置**-其中這封電子郵件路由傳送結果？

    傳遞動作是因為現有的原則或偵測電子郵件所採取的動作。 以下是電子郵件可能採取的動作：

    - **已傳遞**– 電子郵件已傳遞至收件匣或資料夾的使用者和該使用者可以直接存取。

    - **Junked** – 電子郵件已傳送至任一使用者的垃圾郵件] 資料夾，或刪除資料夾，且使用者在其 [垃圾郵件或刪除的郵件] 資料夾中具有存取電子郵件訊息。

    - **封鎖**– 任何電子郵件遭到隔離的郵件，會失敗，或者已卸除。 （這是完全無法存取的使用者）。

    - **取代**– 惡意附件由 state 附件的.txt 檔案所取代其中任何電子郵件程式惡意。
 
    傳遞位置顯示原則和執行傳遞後偵測的結果。 其連結到「傳遞動作」。 已新增此欄位，以深入了解找到問題電子郵件時所採取的動作。 以下是傳遞位置可能的值：

    - **收件匣或資料夾**– 電子郵件是在收件匣或資料夾中 （根據您的電子郵件的規則）。

    - **在內部或外部**– 信箱不存在於雲端上，但內部。

    - **垃圾郵件資料夾**– 電子郵件是在使用者的垃圾郵件資料夾。

    - **刪除的項目] 資料夾**– 電子郵件是在使用者的已刪除項目] 資料夾中。

    - **隔離**-隔離區，而不是在使用者信箱的電子郵件。

    - **失敗**– 電子郵件無法連到信箱。

    - **丟棄**– 電子郵件會取得某處遺失，在 [郵件流程。

     ##### <a name="view-the-timeline-of-your-email"></a>檢視您的電子郵件的時間表
  
     **電子郵件時間表**] 是能方便狩獵安全性作業小組的威脅總管中的欄位。 當多個事件會發生在或接近同一時間上一封電子郵件時，這些事件顯示在 [時間表] 檢視。 [**特殊動作**] 欄中擷取某些電子郵件發生後傳遞的事件。 合併的電子郵件訊息從時間表資訊拍攝後續傳遞任何特殊動作讓系統管理員深入資訊原則和威脅處理 （例如其中已路由傳送郵件，以及在某些情況下，最終評估已）。

<!-- Reference material

1. **Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 

2. In the left navigation quick-launch, choose **Threat management** \> **Explorer**.

3. Click on the subject of an email message, and then click **Email timeline**. (It appears among other headings on the panel like **Summary** or **Details**.)

    Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail. In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**. The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).

    The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived. When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view. 
    
    Some events that happen post-delivery to your mail are captured in the **Special actions** column. Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was. 

4. In the **View** menu, choose **All email**.

    ![Use the View menu to choose between Email and Content reports](../../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.

    ![Threat Explorer showing data for all email](../../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.

    ![Clicking "Delivered to junk" removes that data from view](../../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.

    ![Below the chart, view a list of email messages that were detected](../../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.

    ![You can view additional information about an item](../../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This deletes the selected messages from the recipients' mailboxes.

    ![When you select one or more email messages, you can choose from several available actions](../../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## Dealing with suspicious email messages

Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets. To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md). However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware). Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization. As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes. To do that, you can use [Threat Explorer](threat-explorer.md).

## Finding re-routed email messages after actions are taken

Threat Explorer provides your security operations team with the details they need to investigate suspicious email. Your security operations team can:

- [View the email headers and download the email body](#view-the-email-headers-and-download-the-email-body) 

- [Check the delivery action and location](#check-the-delivery-action-and-location)

- [View the timeline of your email](#view-the-timeline-of-your-email)

### View the email headers and download the email body

The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer. Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned. See [Preview role permissions](#preview-role-permissions).

To access your message header and email download options, follow these steps: 

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 
    
2. In the left navigation, choose **Threat management** \> **Explorer**.

3. Click on a subject in the Threat Explorer table. 

    This opens the flyout, where both header preview and email download links are positioned.

    ![Threat Explorer flyout with download and preview links on the page.](../../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed. In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.
-->

## <a name="related-topics"></a>相關主題

[Office 365 進階威脅防護](office-365-ti.md)
  
[防範 Office 365 中的威脅](protect-against-threats.md)
  
[檢視 Office 365 進階威脅防護的報告](view-reports-for-atp.md)
