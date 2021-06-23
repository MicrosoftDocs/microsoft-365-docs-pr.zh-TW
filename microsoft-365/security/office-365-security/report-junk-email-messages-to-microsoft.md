---
title: 將垃圾郵件、非垃圾郵件和網路釣魚郵件報告給 Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解不同的方式，向 Microsoft 報告好的和壞的訊息和檔案，以進行分析。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082813"
---
# <a name="report-messages-and-files-to-microsoft"></a>回報訊息和檔案至 Microsoft。

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，使用者與系統管理員都有數種不同的方法，可向 Microsoft 報告電子郵件和檔案。

<br>

****

|方法	|描述|
|---|---|
|[使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft](admin-submission.md)|在具有 Exchange Online 信箱的組織中，系統管理員的建議報告方法 (無法在獨立 EOP) 中使用。|
|[啟用報告訊息或報告網路釣魚增益集](enable-the-report-message-add-in.md)|使用 Outlook 和 Outlook 網頁版 (先前稱為 Outlook Web App) 。 <p> 視您的訂閱而定，使用者使用增益集來報告的郵件可用於系統 [管理提交入口網站](admin-submission.md)、 [自動調查和回應 (AIR) 結果](air-view-investigation-results.md)、 [使用者報告的訊息報告](view-email-security-reports.md#user-reported-messages-report)及 [Explorer](threat-explorer-views.md#email--submissions)。 <p> 您可以設定報告的郵件以複製或重新導向至您指定的信箱。 如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。
|[在 Outlook 中報告誤判和漏報](report-false-positives-and-false-negatives.md)|提交誤報 (已封鎖或傳送至 [垃圾郵件] 資料夾) 的良好電子郵件，以及已傳遞至收件匣) 的電子郵件釣魚 (有害電子郵件或網路釣魚程式，使用報告郵件功能 Exchange Online Protection (EOP) 。|
|[手動將郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|手動將附加的郵件傳送到垃圾郵件、非垃圾郵件和網路釣魚的特定 Microsoft 電子郵件地址。|
|[使用郵件流程規則來查看使用者報告給 Microsoft 的內容](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|瞭解如何建立郵件流程規則 (也稱為傳輸規則) ，當使用者將郵件報告給 Microsoft 進行分析時，會通知您。|
|[將惡意程式碼和非惡意程式碼提交給 Microsoft 進行分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|使用 Microsoft 安全情報網站提交附件及其他檔案。|
|

如果已隔離垃圾郵件或網路釣魚郵件，而非傳遞郵件，則使用者可以在 Microsoft 365 Defender 入口網站中，從隔離區將郵件報告給 Microsoft。 如需詳細資訊，請參閱[在 Microsoft 365 中尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。

> [!NOTE]
> 送出至 Microsoft 的資料是在北美資料中心的 Office 365 法規遵從性界限內。 工程小組的分析人員會檢查資料，以協助改善篩選的效能。
