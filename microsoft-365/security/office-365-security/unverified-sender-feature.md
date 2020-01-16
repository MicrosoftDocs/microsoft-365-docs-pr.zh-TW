---
title: 未驗證的寄件者
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
ms.collection:
- M365-security-compliance
description: 若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。
ms.openlocfilehash: 65b9d1dd3eb1a764867103710448255be96cd183
ms.sourcegitcommit: c9332016f61b26f63c9145c9169ea5330e91a243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2020
ms.locfileid: "41173509"
---
# <a name="unverified-sender"></a>未驗證的寄件者

> [!NOTE]
> 這些更新會循環現在，並可能無法使用尚未對所有使用者。 企業 outlook.com 使用者支援這項功能。 它不是目前適用於消費者 outlook.com。

若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。

> [!IMPORTANT]
> 當郵件標示為網路釣魚詐騙、 Outlook.com 和 Outlook 網頁顯示一則警告] 頁面頂端，但仍然可以開啟任何郵件中的連結。

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>如何識別我的收件匣中的可疑的郵件？

Outlook.com 和網頁型 Outlook 顯示指標，當郵件的寄件者也無法識別或其身分識別為不同於從地址中看到的內容。

## <a name="you-see-a--in-the-sender-image"></a>您會看到 '？ ' 中的寄件者影像

當 Outlook.com 和網頁型 Outlook 無法驗證使用電子郵件驗證技術的寄件者的身分識別時，他們會顯示 '？ ' 中的寄件者相片。

![郵件未通過驗證](../media/message-did-not-pass-verification.jpg)

若要驗證失敗不是每個訊息是惡意。 不過，您應該謹慎互動與未驗證如果您不能辨識寄件者的郵件。 或者，如果您辨識通常沒有寄件者 '？ ' 寄件者的影像，但您突然開始看到它，可能會登寄件者詐騙。

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>如何管理哪些郵件接收未驗證的寄件者處理方式 

如果您是 Office 365 客戶可以管理此功能透過 Office 365 安全性 & 合規性中心。

- 安全性 & 合規性中心，全域或安全性系統管理員可以關閉透過反 Phish 原則] 底下的反詐騙保護功能，開啟或關閉。 此外，您可以使用**Set AntiPhishPolicy**指令程式在 Exchange Online PowerShell。 如需詳細資訊，請參閱[在 Office 365 中的反網路釣魚保護](anti-phishing-protection.md)及 [設定 AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy)。

    ![編輯的圖形介面中的未驗證寄件者。](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- 如果系統管理員已識別為誤判，而寄件者應該不會收到未驗證的寄件者處理方式，其中一個下列動作可以採取新增至詐騙智慧詐騙的寄件者允許清單：

  - 加入網域組經由詐騙智慧深入解析。 如需詳細資訊，請參閱[逐步解說： 詐騙智慧深入了解](walkthrough-spoof-intelligence-insight.md)。

  - 加入網域組經由**Set-phishfilterpolicy** cmdlet 在 Exchange Online PowerShell。 如需詳細資訊，請參閱[Set-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy)和[設定 Office 365 ATP 防網路釣魚和防網路釣魚原則](set-up-anti-phishing-policies.md)。

此外，我們不適用未驗證的寄件者處理方式，如果郵件已傳遞至收件匣透過郵件流程規則 （也稱為傳輸規則），安全網域清單 （反垃圾郵件原則）] 或 [安全的寄件者清單。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a>查看準則沒有 Outlook.com 和網頁型 Outlook 使用新增 '？ ' 和 '透過' 屬性？

為 '？ ' 中的寄件者影像： Outlook.com 需要郵件通過 SPF 或 DKIM 驗證，並將會收到任一 dmarc 複雜，或從 Office 365 詐騙情報傳遞複合驗證。 如需詳細資訊，請參閱[Set up SPF in Office 365，以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)。

針對透過標記： Outlook.com 中自地址的網域不同網域的 DKIM 簽章或 SMTP MAIL FROM 中時，顯示在兩個欄位 （偏好的 DKIM 簽章） 的其中一個網域。

### <a name="how-do-i-remove-the-"></a>如何移除 '？ '

為 '？ ' 中的寄件者影像： 為寄件者，您應該驗證與 SPF 或 DKIM 郵件。

針對透過標記： 為寄件者，您應該確定是在 DKIM 簽章的網域或 SMTP 郵件從相同，或是的在 [從地址的網域子網域。

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a>Outlook.com 和 Outlook 網頁顯示執行此動作不會通過驗證每個郵件嗎？

不是一定。 Outlook.com 和網頁型 Outlook 可能已驗證寄件者的郵件內的其他屬性。

## <a name="related-topics"></a>相關主題

[協助保護您的 Outlook.com 電子郵件帳戶](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[處理網路釣魚或 Outlook.com 中詐騙](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[篩選垃圾電子郵件和網頁型 Outlook 中的垃圾郵件](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
