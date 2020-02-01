---
title: 疑難排解和支援資訊
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: 本主題說明使用者和系統管理員可用的疑難排解步驟，並提供如何連絡技術支援人員以取得協助的相關資訊。
ms.openlocfilehash: efb71aab852b76b2b898419444bfea4144728514
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598170"
---
# <a name="troubleshooting-and-support-information"></a>疑難排解和支援資訊

本主題說明使用者和系統管理員可用的疑難排解步驟，並提供如何連絡技術支援人員以取得協助的相關資訊。

## <a name="troubleshooting-for-users"></a>使用者疑難排解

有時候，您可能會遇到無法使用 Microsoft Outlook 新增垃圾郵件回報增益集之後。 以下是可能發生的問題，以及解決這些問題的秘訣。

- 按一下 **[回報垃圾郵件]** 沒有作用

- 選取電子郵件後，Outlook 停止回應

- 由於「無法傳遞」回覆，回報的垃圾郵件無法傳遞

若要修正這個問題，請執行下列步驟：

1. 關閉並重新啟動 Outlook。

2. 確認您能夠建立並傳送測試郵件。若要這麼做，您可以將測試郵件傳送至您負責的另一個電子郵件帳戶，然後驗證是否收到電子郵件。

如果問題仍然存在，請連絡您的系統管理員。

> [!TIP]
> 您也可以將垃圾郵件直接提交給 Microsoft，請使用 [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) 電子郵件地址，若要提交誤判郵件，請使用 [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com) 電子郵件地址。 如需詳細資訊，請參閱[將垃圾郵件、非垃圾郵件與網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。

## <a name="troubleshooting-for-administrators"></a>系統管理員疑難排解

身為管理員，您可能會與 Outlook 的垃圾郵件回報增益集使用的使用者遇到問題。 以下是解決您可能遇到的問題的一些秘訣。

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>問題： 出現錯誤訊息來要求使用者不斷連絡系統管理員

1. 將下列登錄機碼值設為 "Verbose"：

   - **在 32 位元作業系統上安裝的 32 位元 Outlook**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **在 64 位元作業系統上安裝的 32 位元 Outlook**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **64 位元 Outlook （一律安裝在 64 位元作業系統上）**：

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. 重新啟動 Outlook，並要求使用者將他們會看到錯誤訊息時回報。

3. 收集下列位置中的記錄資訊：

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. 連絡 Exchange Online Protection 技術支援人員，並提供這項記錄資訊。

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>問題： 使用者選擇不接收確認，當在提交電子郵件為垃圾郵件，但現在想要回復為此選項

1. 將下列登錄機碼值為"True": `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`。

2. 重新啟動 Outlook。

## <a name="support-information"></a>支援資訊

如果您需要安裝的說明，設定或解除安裝增益集，請連絡技術支援使用 Microsoft 365 系統管理中心中的 [支援] 頁面上的 [新的服務要求] 連結。 如其他選項，包括提交服務要求透過電話] 和 [自我支援選項，請參閱[說明和 EOP 的支援](help-and-support-for-eop.md)。

## <a name="for-more-information"></a>相關資訊

[啟用報告訊息增益集](enable-the-report-message-add-in.md)

[向 Microsoft 回報垃圾郵件](report-junk-email-messages-to-microsoft.md)
