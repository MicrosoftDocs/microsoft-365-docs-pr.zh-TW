---
title: Office 365 中的系統管理員報送、O365 報送、Office 365 垃圾郵件問題、O365 false 負數、在 office 365 中提交網路釣魚功能、提交電子郵件的掃描、可疑的電子郵件在 Office 365、掃描郵件、Microsoft 掃描網路釣魚詐騙、郵件、提交電子郵件，送出電子郵件，dodgy 電子郵件，不良演員郵件，可疑，不受信任的郵件，報告網路釣魚電子郵件至 microsoft，向 microsoft 報告網路，向 microsoft 報告欺詐電子郵件，並將惡意電子郵件報告給 microsoft，垃圾郵件收件匣 office 365 中的電子郵件，在電子郵件 office 365 中的病毒
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
ms.collection:
- M365-security-compliance
description: 瞭解如何將可疑的電子郵件、可疑的網路釣魚郵件、垃圾郵件和其他可能有害的郵件、URLs 和檔案從您的 Office 365 租使用者提交至 Microsoft 進行掃描。
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033611"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft

如果您是 Office 365 組織中具有 Exchange Online 信箱的系統管理員，您可以使用 Office 365 安全性 & 合規性中心內的提交入口網站，將電子郵件訊息、URLs 和附件提交給 Microsoft 以進行掃描。

當您提交電子郵件時，您會收到任何可能允許內送電子郵件進入租使用者的原則，以及對郵件中的任何 URLs 和附件進行檢查的相關資訊。 可能允許郵件的原則包括個別使用者的安全寄件者清單，以及租使用者層級原則，例如 Exchange 郵件流程規則（也稱為傳輸規則）。

如需其他方式，將電子郵件訊息、URLs 和附件提交給 Microsoft，請參閱 

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您可以在<https://protection.office.com/>中開啟安全性 & 規範中心。 若要直接移至**提交**頁面，請<https://protection.office.com/reportsubmission>使用。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連線到獨立的 Exchange Online Protection PowerShell，請參閱[connect To Exchange Online protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 若要新增、修改和刪除反垃圾郵件原則，您必須是「**組織管理**」、「**安全性管理員**」或「**安全性讀者**」角色群組的成員。 如需安全性 & 規範中心中角色群組的詳細資訊，請參閱[Office 365 安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)。

- 如需使用者如何將郵件和檔案提交給 Microsoft 的詳細資訊，請參閱[將報告訊息和檔案傳送給 microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>如何將可疑內容引導至 Microsoft 以進行 Office 365 掃描

若要將內容提交至 Microsoft，請按一下 [提交] 頁面左上方的 [**新增提交**] 按鈕。 頁面右邊的浮出控制項顯示可供您提交電子郵件、URL 或檔案的選項。

### <a name="submit-a-questionable-email-to-microsoft"></a>將可疑的電子郵件提交給 Microsoft

![電子郵件提交範例](../../media/submission-flyout-email.PNG)

1. 若要提交電子郵件，請選取 [**電子郵件**] 並指定電子郵件**網路訊息識別碼**或上傳電子郵件檔案。

2. 指定您想要執行原則檢查的收件者。 原則檢查會決定是否因使用者或租使用者層級原則而略過掃描的電子郵件。

3. 指定是否應該封鎖電子郵件。 如果電子郵件應該已封鎖，請指定是否應該封鎖為垃圾郵件、網路釣魚或惡意程式碼。 如果您不確定可能是哪種類型，請使用您的最佳判斷。

   - 如果篩選因提交原則而略過，您將會看到該原則的相關資訊。

   - 如果篩選器因一或多個原則而略過，掃描將會在數分鐘內完成。 您可以按一下 [狀態] 連結，以查看有關提交的其他資訊。 這包括原則檢查的結果和重新掃描判定。 請注意，這不會再透過 Office 365 ATP 完整篩選棧執行電子郵件，但會根據郵件、URL 或檔案的某些屬性執行部分重新掃描。

4. 按一下 [**提交**] 按鈕。

### <a name="send-a-suspect-url-to-microsoft"></a>將可疑 URL 傳送給 Microsoft

![電子郵件提交範例](../../media/submission-url-flyout.png)

1. 若要提交 URL，請選取浮出控制項的**url** 。 輸入完整 URL，包含通訊協定（**HTTPs://**）。

   如果您選取 [**應該已經過篩選**]，請指定 URL 是否為網路釣魚或惡意程式碼。

2. 按一下 [**提交**] 按鈕。

### <a name="submit-a-suspected-file-to-microsoft"></a>將可疑檔提交至 Microsoft

![電子郵件提交範例](../../media/submission-file-flyout.PNG)

1. 若**要從飛出檔中**提交檔案選取檔案，並上傳想要掃描的檔。

2. 按一下 [**提交**] 按鈕。
