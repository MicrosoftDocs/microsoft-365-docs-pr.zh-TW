---
title: Office 365 電子郵件的反垃圾郵件保護
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 6/29/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: 了解反垃圾郵件設定和篩選器，可協助您防止 Exchange Online 和 Office 365 中的垃圾郵件。 在 Office 365 收到太多垃圾郵件？ 您可以自訂您的垃圾郵件篩選和反垃圾郵件原則設定。
ms.openlocfilehash: b7ffb29d09a357cc0a2e407d1a66f29273fc950f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599860"
---
# <a name="office-365-email-anti-spam-protection"></a>Office 365 電子郵件的反垃圾郵件保護

您擔心 Office 365 中太多垃圾郵件？ 我們已內建多個垃圾郵件篩選您的 Office 365 或 Exchange Online Protection (EOP) 服務，所以您的電子郵件受到保護，您會收到第一個訊息的那一刻。 以協助防止 Office 365 中的垃圾郵件，您可能想要變更的保護設定，即可處理您的組織中的特定問題 — 說出您正在接收來自特定寄件者，大量的垃圾郵件，例如 — 或至只可調整您的設定，讓它們量身訂做以滿足組織的需求。 若要這麼做，您可以變更 Office 365 安全性中的反垃圾郵件設定&amp;合規性中心。

本文適用於 Office 365 系統管理員。 如果您不是系統管理員，但您是 Office 365 的使用者，而且您想要了解如何處理您收到的垃圾郵件，這不是您要尋找的文章。 相反地，如果您使用的電腦版 Outlook 或 Outlook for Mac，啟動與[垃圾郵件篩選器概觀](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。 如果您使用網頁型 Outlook，以[了解垃圾郵件和網路釣魚](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)開始。

## <a name="these-options-help-you-prevent-spam-in-office-365"></a>這些選項，協助您防止 Office 365 中的垃圾郵件

 **連線篩選**： 當您使用連線篩選時，Office 365 會檢查前允許的郵件若要透過取得寄件者信譽。 您可以建立允許清單] 或 [安全寄件者] 清單中，若要確保您收到來自特定 IP 位址或 IP 位址範圍傳送給您每封郵件。 您也可以建立要封鎖郵件，稱為封鎖清單的 IP 位址清單。 如需詳細資訊，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。 如果您擔心 Office 365 中的垃圾郵件，使用的連線，協助防範垃圾郵件篩選。

對於有 Office 365 企業版 E5 或購買進階威脅防護 (ATP) 授權的客戶，連線篩選由詐騙智慧用於建立允許和封鎖的寄件者詐騙您的網域清單。 如需詳細資訊，請參閱[了解詐騙情報更多](learn-about-spoof-intelligence.md)。

 **垃圾郵件篩選**： Office 365 會檢查郵件特性與垃圾郵件一致使用垃圾郵件篩選。 您可以變更哪些動作，以對郵件識別為垃圾郵件，並選擇是否要篩選以特定語言撰寫或從特定國家或地區傳送的郵件。 您也可以開啟進階垃圾郵件篩選選項，如果您想要追求垃圾郵件篩選積極方法。 此外，您可以設定使用者垃圾郵件通知改為通知使用者有關適用於他們的郵件已傳送至隔離區時。 （將郵件傳送至隔離區是下列其中一個可設定的動作）。從這些通知，使用者可以釋放誤判，並向 Microsoft 報告進行分析。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。 為了協助防止 Office 365 中的垃圾郵件，請使用垃圾郵件篩選，如果您擔心 Office 365 中太多垃圾郵件，請使用連線篩選，協助防範垃圾郵件。

> [!NOTE]
> 為 EOP 獨立版客戶： 根據預設，EOP 垃圾郵件篩選垃圾郵件偵測到郵件傳送至每個收件者的垃圾郵件] 資料夾。 不過，為了確保 [**移至垃圾郵件] 資料夾的郵件**] 動作將會使用內部部署信箱，您必須設定兩個 Exchange 郵件流程規則 （也稱為傳輸規則） 上您的內部部署伺服器，以偵測 EOP 所新增的垃圾郵件標頭。 如需詳細資料，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>如果您在 Office 365 收到太多垃圾郵件的額外資訊

下列視訊提供設定垃圾郵件篩選 EOP 中的概觀。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]

如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)主題。

## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>請檢查您要防止 Office 365 中的垃圾郵件的外寄郵件

 **輸出篩選**： Office 365 也會檢查以確定您的使用者不會傳送垃圾郵件。 比方說，導致其傳送垃圾郵件，因此我們建立呼叫*輸出篩選*防範惡意程式碼可能會取得感染使用者的電腦。 您不能關閉輸出篩選，但是您可以設定[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)中所述的設定。 如果您擔心太多垃圾郵件，Office 365 中，使用輸出篩選，幫助避免 Exchange Online 中的垃圾郵件。

## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>獨門密技： 若要防止 Office 365 中的垃圾郵件的更多方法

 **郵件流程規則**： 如果您想要超越內建的垃圾郵件篩選，並建立自訂規則，取決於您的業務原則，_[郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)_（也稱為_傳輸規則_） 是可協助您防止 Office 365 中的垃圾郵件的其他篩選器。 例如，您可以使用郵件流程規則中[使用郵件流程規則來設定垃圾郵件信賴等級 (SCL) 郵件中的](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)所述設定垃圾郵件信賴等級 (SCL) 值符合特定條件的郵件。

 **電子郵件驗證**： 使用網域名稱系統 (DNS) 將可驗證資訊新增至相關的電子郵件訊息的寄件者的電子郵件訊息的技術稱為電子郵件驗證。 更進階的 Office 365 系統管理員可以讓利用這些電子郵件的驗證方法：

- **寄件者原則架構 (SPF)**: SPF 驗證電子郵件訊息的原始來驗證指稱的擁有者為傳送網域的寄件者的 IP 位址。 如需 SPF 的快速簡介並快速設定，請參閱[在 Office 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 如需更深入了解 Office 365 如何使用 SPF 或是進行疑難排解或非標準的部署 (例如混合式部署)，請先參閱 [Office 365 如何使用寄件者原則架構 (SPF) 防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。

- **DomainKeys Identified Mail (DKIM)**: DKIM 可讓您將數位簽章附加至您傳送電子郵件訊息標頭中的電子郵件訊息。 接收來自您網域之電子郵件的電子郵件系統，可以使用此數位簽章來判斷所接收的內送電子郵件是否合法。 DKIM 與 Office 365 的相關資訊，請參閱[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)。

- **網域型郵件驗證、 報告和符合性聲明 (DMARC)**: DMARC 可協助接收郵件系統決定如何處理未通過 SPF 或 DKIM 檢查，並提供您電子郵件協力廠商的信任的另一個層級的郵件。 如需設定 DMARC 的相關資訊，請參閱[在 Office 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)。

如果您擔心垃圾郵件、 網路釣魚和詐騙 Office 365 中，SPF，DKIM、 DMARC 一起使用，協助防範垃圾郵件和不想要詐騙。

 **使用者受管理的設定**： 如果您正在尋找一般使用者可以如何管理自己的垃圾郵件設定的相關資訊，請參閱[垃圾郵件篩選器概觀](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)（適用於 Microsoft Outlook 使用者） 或[解垃圾郵件和網路釣魚](https://support.microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)（適用於 Outlook web 使用者)。 如果您正在使用 EOP 來保護在內部部署信箱，請務必使用目錄同步處理，以確保這些設定會同步至服務。 若需設定目錄同步作業的詳細資訊，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md) 中的「使用目錄同步作業來管理郵件使用者」。

## <a name="for-more-information"></a>相關資訊

[部落格： 為何沒有垃圾郵件和網路釣魚取得透過 Office 365？](https://blogs.msdn.microsoft.com/tzink/2014/09/12/why-does-spam-and-phishing-get-through-office-365-and-what-can-be-done-about-it/)

[反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)

[使用安全清單或其他技術防止誤判電子郵件標示為垃圾郵件](prevent-email-from-being-marked-as-spam.md)

[如何設定 Office 365 垃圾郵件篩選，以協助封鎖垃圾郵件](reduce-spam-email.md)

[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)

[反垃圾郵件訊息標頭](anti-spam-message-headers.md)

[非法回應郵件與 EOP](backscatter-messages-and-eop.md)

## <a name="more-resources"></a>其他資源

[從 Office 365 社群論壇獲得協助](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)

[管理員：登入及建立服務要求](https://portal.office.com/AdminPortal/Home?ref=support)

[AContact 產品的技術支援商務版-系統管理說明](https://docs.microsoft.com/Office365/Admin/contact-support-for-business-products)
