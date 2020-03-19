---
title: 將垃圾郵件、非垃圾郵件與網路釣魚詐騙郵件提交給 Microsoft 進行分析
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: '您和您的使用者可以將假的否定和誤報垃圾郵件提交給 Microsoft 進行分析。 '
ms.openlocfilehash: 7b53f74be78bc1203189815c6a7adf3337decd21
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856866"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a>將垃圾郵件、非垃圾郵件與網路釣魚詐騙郵件提交給 Microsoft 進行分析

當您組織中的使用者收到其收件匣中的垃圾郵件（垃圾郵件）或網路釣魚詐騙郵件時，或是因為郵件標示為垃圾郵件而未收到合法的電子郵件時，可能會令人感到麻煩。 我們不斷微調垃圾郵件篩選器，使其更準確。 您和您的使用者可以將虛假的反垃圾郵件訊息提交給 Microsoft 進行分析，以協助此程式。 "False 負值" 是垃圾郵件，應為垃圾郵件，但不會被識別為垃圾郵件。 "誤報" 是一種合法的電子郵件訊息，錯誤地辨識為垃圾郵件。

> [!NOTE]
> 由於我們收到大量送出的報送，我們可能無法回答所有要求進行分析。

系統管理員可以將電子郵件、url 和附件傳送給 Microsoft 以供審閱。 請參閱[Office 365 ATP 中的系統管理員報送](admin-submission.md)。

## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a>提交透過垃圾郵件篩選器傳遞的垃圾郵件或網路釣魚郵件

如果您收到的郵件是透過垃圾郵件篩選器傳遞，而且應歸類為垃圾郵件篩選器或網路釣魚詐騙，您可以視需要將 "假否定" 郵件提交至 Microsoft 垃圾郵件分析和 Microsoft 網路釣魚分析小組。 分析員會檢查郵件，並將其新增至全服務篩選準則（如果符合分類準則）。

如需適用于整個組織的垃圾郵件設定，請參閱[使用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件，以避免誤報負面問題](reduce-spam-email.md)。 本文包含協助避免誤報的秘訣。

您可以透過下列方式提交垃圾郵件：

- 針對網頁使用者的 Outlook 和 Outlook，請使用 Microsoft Outlook 的報告訊息增益集。 如需如何安裝及使用此工具的詳細資訊，請參閱[Enable The Report Message 增益集](enable-the-report-message-add-in.md)。

- 您也可以使用電子郵件將郵件提交至 Microsoft，以歸類為垃圾郵件或網路釣魚詐騙，如下列程式所述。

### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a>使用電子郵件將垃圾郵件（垃圾郵件）或網路釣魚詐騙郵件提交給 Microsoft

若要將垃圾郵件或網路釣魚詐騙郵件提交給 Microsoft：

1. 建立空白的電子郵件訊息。

2. 將郵寄地址視為審閱郵件的 Microsoft 小組，如下所示：

   - 若為垃圾郵件： junk@office365.microsoft.com

   - 對於網路釣魚詐騙郵件： phish@office365.microsoft.com

3. 將垃圾郵件或網路釣魚詐騙郵件複製並貼到新郵件中以附件形式傳送。

   > [!NOTE]
   > •您可以在新郵件中附加多封郵件。 請確定所有郵件都是相同類型：網路釣魚詐騙郵件或垃圾郵件。 <br/><br/>•將新郵件的本文保留空白。 <br/><br/>•使用 .msg （預設 Outlook 格式）或 .eml （預設 Outlook 網頁格式）格式的附加郵件。

4. 按一下 **[傳送]**。

## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a>提交已標記為垃圾郵件的郵件，但應該允許透過

如果郵件被錯誤地識別為垃圾郵件，您可以將 "誤報" 郵件提交給 Microsoft 垃圾郵件分析小組。 分析員會評估和分析郵件。 我們可以根據分析的結果調整全服務的垃圾郵件內容篩選規則，以便允許郵件通行。
  
管理員可以查看更多垃圾郵件設定資訊，以套用至整個組織。 請參閱操作[方法：協助確保郵件不會標示為垃圾](prevent-email-from-being-marked-as-spam.md)郵件。 如果您有系統管理員層級的控制，而您想要避免誤報，則此資訊非常有用。
  
您可以透過下列方式提交非垃圾郵件：

- 如果您在設定內容篩選器時使用 [**將郵件移至垃圾郵件資料夾**] 動作（這是預設動作），使用者可以在其 Outlook 或 outlook 網頁版（先前稱為 Outlook web App）的 [垃圾郵件] 資料夾中，放開誤報郵件。

  - Outlook 使用者可以使用 [**非垃圾**郵件] 按滑鼠右鍵按一下功能表選項，來釋放 false 的肯定郵件。 不過，他們必須透過電子郵件將郵件提交給 Microsoft，如本文中的程式所示。

  - Web 使用者上的 Outlook 可發放誤報郵件，並將其提交給 Microsoft 進行分析，以使用「**標記為非垃圾**郵件」動作。 如需如何執行此動作的詳細資訊，請參閱[在 Outlook 網頁版中報告垃圾郵件和網路釣魚詐騙](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。

- 當您設定內容篩選器時，如果您使用 [**隔離郵件**] 動作，而非 [**將郵件移至垃圾郵件資料夾**] 動作，請執行下列動作：

  - 系統管理員可以釋放被當成垃圾郵件隔離的郵件，並從 Exchange 系統管理中心將這些郵件回報為誤判。 如需詳細資訊，請參閱[在 Office 365 中以系統管理員身分管理隔離的郵件和](manage-quarantined-messages-and-files.md)檔案。

  - 使用者可以放開自己的垃圾隔離郵件，並透過下列頻道將其報告為誤報：

  - Exchange 系統管理中心 (EAC) 使用者介面。 如需詳細資訊，請參閱 [Find and Release Quarantined Messages (End Users)](find-and-release-quarantined-messages-as-a-user.md)。

  - 使用者垃圾郵件通知訊息 (如果您的系統管理員已加以啟用)。

- 您也可以使用電子郵件將不應歸類為垃圾郵件的郵件提交給 Microsoft。 當您執行此動作時，請確定您使用下列程式中的步驟。

### <a name="use-email-to-submit-false-positive-messages"></a>使用電子郵件來提交誤判的郵件

使用 [[使用電子郵件將垃圾郵件提交給 Microsoft] 或 [網路釣魚詐騙郵件](#use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft)] 區段中所述的相同程式，但會將郵件傳送至 not_junk@office365.microsoft.com。

## <a name="spam-evaluation-and-rules-deployment"></a>垃圾郵件評估和規則部署

垃圾郵件分析小組會檢查您提交的郵件，並調整垃圾郵件篩選器以避免今後的垃圾郵件。 因此，Office 365 垃圾郵件篩選器會 areconstantly 精緻。 任何提交的項目都是在整個網路層級接受評估。 誤報會檢查並評估提交可能的規則，以允許今後透過垃圾郵件篩選器的郵件。 因此，通知服務的誤報和否定的否定（未篩選的垃圾郵件），對您和使用全域網路的所有客戶都很有利。 垃圾郵件小組會在每封提交的郵件中檢查各項指標，例如：

- 寄件者地址

- 傳送方 IP 位址

- 關鍵字

- 詞組

- 傳輸頻率

- 其他趨勢和模式

審閱此資訊之後，垃圾郵件小組可能會變更服務的垃圾郵件篩選層。 如需垃圾郵件小組的詳細資訊，您可以收看下列英文版影片：

[Microsoft Exchange 垃圾郵件小組影片](https://youtu.be/-TpX_-GMC7o?hd=1)

垃圾郵件評估是一種持續執行的程式，不論原始語言或字元集為何都會套用。 因為垃圾郵件可能會含糊含糊或甚至缺乏主旨或郵件內文中的文字，所以垃圾郵件小組會依靠其他郵件特性來執行篩選。 這表示，當垃圾郵件小組將提供的郵件標示為垃圾郵件，並且對規則基礎進行必要變更之後，該郵件將來便會遭到封鎖，除非其特性又被修改到足可避開我們的篩選器。 我們會不斷地部署新的垃圾郵件規則。 個別報送之規則的時間範圍視報送的數量和品質而有所不同。 因為新的垃圾郵件規則是針對所有客戶進行全域設定，所以並非個別的垃圾郵件提交會產生新的垃圾郵件規則。

## <a name="for-more-information"></a>相關資訊

[反垃圾郵件和反惡意程式碼防護](anti-spam-and-anti-malware-protection.md)
  
[如何協助確保郵件不會標示為垃圾郵件](prevent-email-from-being-marked-as-spam.md)
  
[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常](reduce-spam-email.md)
  

[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件，以避免誤判問題](reduce-spam-email.md)
