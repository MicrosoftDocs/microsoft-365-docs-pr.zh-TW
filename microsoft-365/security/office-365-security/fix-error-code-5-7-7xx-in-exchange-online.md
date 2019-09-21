---
title: 修正電子郵件傳送問題的錯誤的程式碼 5.7.7xx in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/11/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 了解如何在 Exchange Online （封鎖而無法傳送郵件的承租人） 中修正錯誤的程式碼 5.7.7xx 的電子郵件問題。
ms.openlocfilehash: d55bc1f8a051a7f9932528a75aac8f1efa18911c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076876"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>修正電子郵件傳送問題的錯誤的程式碼 5.7.7xx in Exchange Online

這個主題會說明若您在未傳遞回報 （也稱為 NDR、 退回的郵件、 傳遞狀態通知或 DSN） 的狀態碼 550 5.7.7xx 您可以執行的動作。 當您的租用戶限制在一或多種方式傳送電子郵件時，您會看到此自動化的通知。 這些錯誤碼通常會為 705 或 750 變成。

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705： 租用戶已超出臨界值限制： 您需要知道

內部寄件者無法看到此 NDR，每當您嘗試傳送郵件，如果您的租用戶遭到盜用了。 這通常 occus 時從您的租用戶的流量大部分為可疑已偵測到和已經產生的郵件傳送的租用戶的能力。 這也可能是如果您的使用者從 Office 365 傳送大量的大宗郵件。 服務描述中所述，Exchange Online 客戶若需要傳送合法的大量商業電子郵件 （例如客戶電子報） 應使用專門提供這些服務的協力廠商提供者。

一旦您的使用者共同租用戶，傳送透過服務的可疑郵件數量，所有使用者就都無法傳送的任何郵件，直到問題解決為止。 使用者會收到未傳遞回報 (NDR) 表示：

- 550 5.7.705 存取被拒，租用戶已超出臨界值

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750： 未註冊的網域的電子郵件限制： 您需要知道

Office 365 允許轉送某些郵件透過 Exchange Online Protection (EOP) 的租用戶。 當使用者擁有 Office 365 信箱和外部的人員傳送他們電子郵件，但使其回到使用者的外部信箱設定電子郵件轉寄功能，就是一個支援的範例。 這是最常見的學生，想要利用其個人電子郵件介面，但仍取得電子郵件與學校相關的教育版環境中。 另一個例子是客戶在混合式案例，並有傳送超出 EOP 的電子郵件的內部部署伺服器時。

### <a name="problems-with-unregistered-domains"></a>問題未註冊的網域

問題時，內部部署伺服器取得危害和最終轉送大量超出 EOP 垃圾郵件。 在大多數情況下，右連接器已設定，但未註冊，也就是取消提供這項，網域從要傳送電子郵件。 Office 365，並讓合理的郵件來自未註冊的網域，但應在您計劃傳送出的每個網域的系統管理中心中設定公認的網域。

一旦危害，租用戶就禁止傳送未註冊的網域的輸出郵件。 使用者會收到未傳遞回報 (NDR) 表示：

- 550 5.7.750 服務無法使用。 封鎖來自未註冊的網域傳送的用戶端

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a>如何才能重新傳送解除封鎖租用戶

有幾個事項如果您的租用戶取得阻止傳送電子郵件：

1. 請確定您網域的所有註冊 Microsoft 365 系統管理中心。 詳細資訊，請參閱[以下](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

2. 尋找不尋常的連接器。 惡意動作項目通常會傳送垃圾郵件您 Office 365 租用戶中建立新的輸入的連接器。 檢查您的連接器的詳細資訊可以找到[以下](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)。 

3. 鎖定您的內部部署伺服器，並確定他們沒有遭到盜用。

> [!TIP]
> 有許多因素所涉及在這裡，尤其是協力廠商的伺服器。 無論如何，您將需要能夠確認是合法的所有郵件離開您的伺服器。

4. 完成時，您必須連絡 Microsoft 支援服務，並要求以取得您的租用戶解除封鎖再次傳送來自未註冊的網域。  提供錯誤碼很有幫助，但您想要證明您的環境受到保護，且不會在一次傳送垃圾郵件。 在開啟支援案例的詳細資訊可以找到[以下](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。
  
## <a name="for-more-information"></a>如需詳細資訊

[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md)

[Office 365 中的電子郵件未傳遞回報](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[設定信箱的電子郵件轉寄功能](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[如何將多功能裝置或應用程式設定為使用 Office 365 傳送電子郵件](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[管理公認的網域在 Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
