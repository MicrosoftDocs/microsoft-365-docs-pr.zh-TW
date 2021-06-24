---
title: 手動將郵件提交給 Microsoft 進行分析
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 系統管理員和使用者可以瞭解如何使用電子郵件傳送郵件， (郵件會標示為壞或錯誤的郵件，以供 Microsoft 進行分析) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0d48c3c6f6d082085390d6e246a088b6d3f6bf0
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105545"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>手動將郵件提交給 Microsoft 進行分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 如果您是組織中 Exchange Online 信箱的系統管理員，建議您使用 Microsoft 365 Defender 入口網站中的 [**提交**] 頁面。 如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。

當您組織中的使用者收到垃圾郵件 (其收件匣中的垃圾郵件) 或網路釣魚郵件，或是因為郵件標記為垃圾郵件而未收到合法的電子郵件時，可能會令人感到沮喪。 我們不斷微調垃圾郵件篩選器，使其更準確。

您和您的使用者可以提交誤報 (良好的電子郵件標示為壞) ，誤報 (錯誤郵件) ，並將網路釣魚郵件傳送至 Microsoft 進行分析，以協助此處理程式。

> [!NOTE]
> 由於我們收到大量送出的報送，我們可能無法回答所有要求進行分析。

## <a name="submit-false-negatives-to-microsoft"></a>將漏報提交給 Microsoft

> [!TIP]
> 在 Outlook 和 Outlook 網頁版中 (之前稱為 Outlook Web App) 的使用者，您可以使用報告郵件增益集或報告網路釣魚增益集，而不是使用下列程式來報告 false 的否定。 如需如何安裝及使用這些工具的相關資訊，請參閱 [enable The Report Message 增益集](enable-the-report-message-add-in.md) 及 [啟用報告網路釣魚增益集](enable-the-report-phish-add-in.md)。

如果您收到的郵件透過應識別為垃圾郵件篩選的垃圾郵件篩選，您可以視需要將郵件提交至 Microsoft 垃圾郵件分析和 Microsoft 網路釣魚分析小組。 分析員會檢查郵件，並將其新增至全服務篩選準則（如果符合分類準則）。

1. 使用下列其中一個收件者建立新的空白電子郵件訊息：

   - **垃圾郵件**： `junk@office365.microsoft.com`
   - **網路釣魚**： `phish@office365.microsoft.com`

2. 將垃圾郵件或網路釣魚郵件拖放到新郵件中。 這會將垃圾郵件或網路釣魚郵件儲存為新郵件中的附件。 請勿複製及貼上郵件的內容，或轉寄郵件 (我們需要原始郵件，才能檢查郵件頭) 。

   > [!NOTE]
   >
   > - 您可以在新郵件中附加多封郵件。 請確定所有郵件都是相同類型：網路釣魚郵件或垃圾郵件。
   > - 將新郵件的內文保留空白。
   > - 請使用 .msg (預設 Outlook format) 或 .eml (預設 Outlook，其格式為) 所附加郵件的格式。

3. 當您完成時，按一下 [ **傳送**]。

> [!TIP]
> 系統管理員可以使用數種不同的方式封鎖正 misidentified 為垃圾郵件的特定郵件。 如需詳細資訊，請參閱 [在 EOP 中建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)。

## <a name="submit-false-positives-to-microsoft"></a>將誤報提交給 Microsoft

> [!TIP]
> Outlook 和 Outlook 網頁版中的使用者可以使用報表訊息增益集或報告網路釣魚增益集，而不是使用下列程式來報告誤報。 如需如何安裝及使用這些工具的相關資訊，請參閱 [enable The Report Message 增益集](enable-the-report-message-add-in.md) 及 [啟用報告網路釣魚增益集](enable-the-report-phish-add-in.md)。

如果郵件被錯誤地辨識為垃圾郵件，您可以將郵件提交給 Microsoft 垃圾郵件分析小組。 分析員會評估郵件，並根據分析的結果 () 可調整整個服務篩選器以允許郵件通過。

1. 以收件者的身分建立新的空白電子郵件訊息 `not_junk@office365.microsoft.com` 。

2. 將 misidentified 郵件拖曳並放入新的郵件。 這會將 misidentified 郵件儲存為新郵件中的附件。 請勿複製及貼上郵件的內容，或轉寄郵件 (我們需要原始郵件，才能檢查郵件頭) 。

   > [!NOTE]
   >
   > - 您可以在新郵件中附加多封郵件。 請確定所有郵件都是相同類型：網路釣魚郵件或垃圾郵件。
   > - 將新郵件的內文保留空白。
   > - 請使用 .msg (預設 Outlook format) 或 .eml (預設 Outlook，其格式為) 所附加郵件的格式。

3. 當您完成時，按一下 [ **傳送**]。

> [!TIP]
> 系統管理員有幾種不同的方式可讓特定郵件略過垃圾郵件篩選。 如需詳細資訊，請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>送出至 Microsoft 儲存的資料位於何處？

資料位於北美資料中心的 Office 365 規範界限內。 工程小組的分析人員會檢查資料，以協助改善篩選的效能。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>建立郵件流程規則，以接收報告給 Microsoft 的郵件副本

如需相關指示，請參閱 [使用郵件流程規則來查看向 Microsoft 報告的使用者](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)。
