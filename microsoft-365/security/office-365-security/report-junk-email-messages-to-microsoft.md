---
title: 將垃圾郵件、非垃圾郵件和網路釣魚郵件報告給 Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解不同的方式，向 Microsoft 報告好的和壞的訊息和檔案，以進行分析。
ms.openlocfilehash: cff9d1b3524200fba9d7ba1775e0b9851027158d
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315860"
---
# <a name="report-messages-and-files-to-microsoft"></a>回報訊息和檔案至 Microsoft。

在使用 Exchange Online 中的信箱或獨立 Exchange Online (Protection 中的 Microsoft 365 組織中，使用者與系統管理員都有數種不同的方法，可將電子郵件和檔案報告給 Microsoft，) EOP 不需要 Exchange Online 信箱的組織。

****

|方法	|描述|
|---|---|
|[使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft](admin-submission.md)|在具有 Exchange Online 信箱的組織中，系統管理員建議的報表方法 (無法在獨立 EOP) 中使用。|
|[啟用報告訊息增益集](enable-the-report-message-add-in.md)|可搭配 Outlook、outlook for Mac 和 outlook 網頁版上的 outlook (以前稱為 Outlook Web App) ，也是建議的增益集。 <br/><br/> 視您的訂閱而定，使用者使用增益集來報告的郵件可用於系統 [管理提交入口網站](admin-submission.md)、 [自動調查和回應 (AIR) 結果](air-view-investigation-results.md)、 [使用者報告的郵件報告](view-email-security-reports.md#user-reported-messages-report)及 [威脅瀏覽器](threat-explorer-views.md#email--submissions)。 <br/><br/> 您可以設定報告的郵件以複製或重新導向至您指定的信箱。 如需詳細資訊，請參閱 [在 EOP 中指定使用者送出垃圾郵件和網路釣魚郵件的信箱](user-submission.md)。|
|[安裝和使用 Microsoft Outlook 的垃圾郵件回報增益集](junk-email-reporting-add-in-for-microsoft-outlook.md)|只能在 Outlook 中運作。|
|[在 web 上的 Outlook 中報告垃圾郵件和網路釣魚電子郵件](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|在適用于 Exchange Online 信箱的組織網頁上，使用 Outlook 網頁版內建的功能 (無法在獨立 EOP) 中使用。 <br/><br/> 使用者報告可在系統 [管理員提交入口網站](admin-submission.md)中使用的訊息。 <br/><br/> 您可以設定報告的郵件以複製或重新導向至您指定的信箱。 如需詳細資訊，請參閱 [在 Exchange online 中指定使用者送出垃圾郵件和網路釣魚郵件的信箱](user-submission.md)。|
|[在 Outlook 中報告 iOS 和 Android 的垃圾郵件和網路釣魚電子郵件](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|使用 Outlook 中的內建功能 iOS 適用于 Exchange Online 信箱的組織 (無法在獨立 EOP) 中使用。 <br/><br/> 使用者報告可在系統 [管理員提交入口網站](admin-submission.md)中使用的訊息。 <br/><br/> 您可以設定報告的郵件以複製或重新導向至您指定的信箱。 如需詳細資訊，請參閱 [在 Exchange online 中指定使用者送出垃圾郵件和網路釣魚郵件的信箱](user-submission.md)。|
|[手動將郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|手動將附加的郵件傳送到垃圾郵件、非垃圾郵件和網路釣魚的特定 Microsoft 電子郵件地址。|
|[使用郵件流程規則來查看您的使用者回報給 Microsoft 哪些內容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|瞭解如何建立郵件流程規則 (也稱為傳輸規則) ，當使用者將郵件報告給 Microsoft 進行分析時，會通知您。
|||
|[將惡意程式碼和非惡意程式碼提交給 Microsoft 進行分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|使用 Microsoft 安全性情報網站送出附件及其他檔案。|
|

如果已隔離垃圾郵件或網路釣魚郵件，而不是傳遞郵件，則使用者可以從 Security & 合規性中心的隔離入口網站，將郵件報告給 Microsoft。 如需詳細資訊，請參閱 [在 Microsoft 365 中尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。
