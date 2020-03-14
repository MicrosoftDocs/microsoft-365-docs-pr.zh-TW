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
description: 瞭解可協助您防止 Exchange Online 和 Office 365 中垃圾郵件的反垃圾郵件設定和篩選器。 在 Office 365 中取得太多垃圾郵件？ 您可以自訂垃圾郵件篩選器和反垃圾郵件原則設定。
ms.openlocfilehash: b7ffb29d09a357cc0a2e407d1a66f29273fc950f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633831"
---
# <a name="office-365-email-anti-spam-protection"></a>Office 365 電子郵件的反垃圾郵件保護

您是否擔心 Office 365 中有太多垃圾郵件？ 我們已在您的 Office 365 或 Exchange Online Protection （EOP）服務中建立多個垃圾郵件篩選器，因此您的電子郵件會從您接收到第一封郵件的時刻開始保護。 為了協助防止 Office 365 中的垃圾郵件，您可能想變更保護設定，以處理組織中的特定問題，例如，您收到大量來自特定寄件者的垃圾郵件，或是只是微調您的設定，以便專為符合您組織的需求而量身定制。 若要這麼做，您可以在 Office 365 安全性&amp;與合規性中心變更反垃圾郵件設定。

本文適用于 Office 365 系統管理員。 如果您不是系統管理員，但您是 Office 365 使用者，而您想要瞭解如何處理您收到的垃圾郵件，這不是您要尋找的文章。 相反地，如果您使用 Outlook 的 PC 或 Outlook for Mac，請從 [[垃圾郵件篩選](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)] 開始。 如果您使用 Outlook 網頁版，請從[瞭解垃圾郵件和網路釣魚](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)開始。

## <a name="these-options-help-you-prevent-spam-in-office-365"></a>這些選項可協助您防止 Office 365 中的垃圾郵件

 連線**篩選**：當您使用連線篩選時，Office 365 會檢查寄件者的信譽，再允許郵件透過。 您可以建立允許清單或安全寄件者清單，以確保您收到從特定 IP 位址或 IP 位址範圍傳送給您的每封郵件。 您也可以建立用來封鎖郵件的 IP 位址清單，稱為封鎖清單。 如需詳細資訊，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。 如果您擔心 Office 365 中的垃圾郵件，請使用連線篩選協助防止垃圾郵件。

針對具有 Office 365 企業版 E5 或已購買高級威脅防護（ATP）授權的客戶，哄騙智慧會使用連線篩選，來建立允許和封鎖的寄件者清單，以欺騙您的網域。 如需詳細資訊，請參閱[深入瞭解欺騙智慧](learn-about-spoof-intelligence.md)。

 **垃圾郵件篩選**：使用垃圾郵件篩選功能，Office 365 會檢查郵件特性與垃圾郵件的一致性。 您可以在識別為垃圾郵件的郵件上變更採取的動作，並選擇是否要篩選以特定語言撰寫的郵件，或是從特定國家或地區傳送的郵件。 您也可以開啟高級垃圾郵件篩選選項，如果您想要採用嚴格的垃圾郵件篩選方法。 此外，您可以設定使用者垃圾郵件通知，以告知使用者何時將其傳送至隔離區。 （傳送郵件至隔離區是其中一個可設定的動作。）在這些通知中，使用者可以發行誤報，並向 Microsoft 報告以進行分析。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。 為了協助防止 Office 365 中的垃圾郵件，請使用垃圾郵件篩選（如果您擔心 Office 365 中有太多垃圾郵件），請使用連線篩選協助防止垃圾郵件。

> [!NOTE]
> 針對 EOP 單機客戶：依預設，EOP 垃圾郵件篩選器會將偵測到的垃圾郵件傳送給每個收件者的 [垃圾郵件] 資料夾。 不過，為了確保 [**將郵件移至垃圾郵件資料夾**] 動作可用於內部部署信箱，您必須在內部部署伺服器上設定兩個 Exchange 郵件流程規則（也稱為傳輸規則），以偵測 EOP 新增的垃圾郵件頭。 如需詳細資料，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>如果您在 Office 365 收到太多垃圾郵件，則會有額外資訊

下列影片概要說明如何在 EOP 中設定垃圾郵件篩選。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]

如需詳細資訊，請參閱[設定垃圾郵件篩選原則](configure-your-spam-filter-policies.md)主題。

## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>檢查您的外寄郵件，以防止 Office 365 中的垃圾郵件

 **輸出篩選**： Office 365 也會進行檢查，確定您的使用者不會傳送垃圾郵件。 例如，使用者的電腦可能會受到惡意程式碼的感染，使其無法傳送垃圾郵件，因此我們會針對所謂的*輸出篩選*建立保護。 您無法關閉輸出篩選，但您可以設定設定[輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)中所述的設定。 如果您擔心 Office 365 中有太多垃圾郵件，請使用輸出篩選，以協助防止 Exchange Online 中的垃圾郵件。

## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>除了基本知識之外，還有其他方式可防止 Office 365 中的垃圾郵件

 **郵件流程規則**：如果您想要超越內建的垃圾郵件篩選功能，並根據您的商務原則建立自訂規則，_[郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)_（也稱為_傳輸規則_）是另一個篩選，可協助您防止 Office 365 中的垃圾郵件。 例如，您可以使用郵件流程規則，設定符合特定條件的郵件的垃圾郵件信賴等級（SCL）值，如[使用郵件流程規則設定郵件中的垃圾郵件信賴等級（scl）](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)所述。

 **電子郵件驗證**：使用網域名稱系統（DNS）將可驗證資訊新增至有關電子郵件寄件者的電子郵件的技術，稱為電子郵件驗證。 更高級的 Office 365 系統管理員可以使用這些電子郵件驗證方法：

- **寄件者原則架構（SPF）**： SPF 會驗證寄件者的 IP 位址，以驗證傳送網域的寄件者的 IP 位址，以驗證電子郵件的來源。 如需 SPF 的快速簡介並快速設定，請參閱[在 Office 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 如需更深入了解 Office 365 如何使用 SPF 或是進行疑難排解或非標準的部署 (例如混合式部署)，請先參閱 [Office 365 如何使用寄件者原則架構 (SPF) 防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。

- **DomainKeys 識別的郵件（DKIM）**： DKIM 可讓您在所傳送電子郵件的郵件頭中，將數位簽章附加到電子郵件。 接收來自您網域之電子郵件的電子郵件系統，可以使用此數位簽章來判斷所接收的內送電子郵件是否合法。 如需 DKIM 和 Office 365 的詳細資訊，請參閱[使用 DKIM 驗證從您的自訂網域傳送的外寄電子郵件（Office 365](use-dkim-to-validate-outbound-email.md)）。

- 以**網域為基礎的郵件驗證、報告和符合性（DMARC）**： DMARC 可協助接收郵件系統判斷如何處理失敗的 SPF 或 DKIM 檢查的郵件，並為您的電子郵件合作夥伴提供另一個信任層級。 如需設定 DMARC 的相關資訊，請參閱[在 Office 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)。

如果您擔心 Office 365 中的垃圾郵件、網路釣魚和詐騙，請使用 SPF、DKIM 及 DMARC，以協助防止垃圾郵件和不需要的欺騙。

 **使用者管理設定**：如果您要尋找使用者如何管理自己的垃圾郵件設定的相關資訊，請參閱[垃圾郵件篩選器](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)（適用于 Microsoft Outlook 使用者）或[深入瞭解垃圾郵件和網路釣魚](https://support.microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)（適用于網頁使用者的 Outlook）。 如果您是使用 EOP 來保護內部部署信箱，請務必使用目錄同步處理，以確保這些設定已同步處理至服務。 若需設定目錄同步作業的詳細資訊，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md) 中的「使用目錄同步作業來管理郵件使用者」。

## <a name="for-more-information"></a>如需詳細資訊

[博客：垃圾郵件和網路釣魚如何透過 Office 365？](https://blogs.msdn.microsoft.com/tzink/2014/09/12/why-does-spam-and-phishing-get-through-office-365-and-what-can-be-done-about-it/)

[反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)

[使用安全清單或其他技術防止誤判電子郵件標示為垃圾郵件](prevent-email-from-being-marked-as-spam.md)

[如何設定 Office 365 垃圾郵件篩選，以協助封鎖垃圾郵件](reduce-spam-email.md)

[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)

[反垃圾郵件訊息標頭](anti-spam-message-headers.md)

[非法回應郵件與 EOP](backscatter-messages-and-eop.md)

## <a name="more-resources"></a>其他資源

[從 Office 365 社群論壇獲得協助](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)

[管理員：登入及建立服務要求](https://portal.office.com/AdminPortal/Home?ref=support)

[商務產品的 AContact 支援-系統管理說明](https://docs.microsoft.com/Office365/Admin/contact-support-for-business-products)
