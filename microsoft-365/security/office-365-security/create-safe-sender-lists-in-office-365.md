---
title: 在 Office 365 中建立安全的寄件者清單
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 4/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 如果您想要是確定您接收來自特定寄件者的郵件，因為您信任它們與他們的郵件，您可以調整您允許在 Exchange 系統管理中心中的垃圾郵件篩選原則中的清單。
ms.openlocfilehash: b01abc327dd19a2d3098d3c49deed1edb1c07b68
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077939"
---
# <a name="create-safe-sender-lists-in-office-365"></a>在 Office 365 中建立安全的寄件者清單

如果您想要確保使用者接收電子郵件從特定寄件者或寄件者因為信任它們與他們的郵件，，有多種方法可用，您可以選擇。 這些選項包含 Exchange 傳輸規則 (Etr)，Outlook 安全寄件者，IP 允許清單，反垃圾郵件寄件者/網域允許清單。

> [!IMPORTANT]
> 雖然組織允許清單可以用來解決誤判，這應被視為暫時性的解決方法並盡可能避免。 使用管理誤判允許不建議清單，因為它可以不小心開啟您的組織最多詐騙、 模擬，以及其他攻擊。 如果您將會使用一份允許清單達到此目的，您必須是並且隨時警覺及保持文章[提交垃圾郵件、 非垃圾郵件和網路釣魚郵件給 Microsoft 進行分析](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)，在準備。

若要設定安全的寄件者清單的建議的方法是使用 Exchange 傳輸規則 (Etr)，因為這樣可以呈現最大的彈性來確認取得允許正確的郵件。 *反垃圾郵件原則電子郵件地址*和*網域為基礎允許清單*不是與*IP 位址型清單*一樣安全因為網域可以輕易地假冒。 但反垃圾郵件原則以 IP 允許清單也會呈現風險，如它們會允許透過該 IP 寄送給略過垃圾郵件篩選的任何網域。 請小心，並監視仔細所做的*任何*例外狀況。

> [!IMPORTANT]
> 如需如何建立**封鎖的寄件者清單**的資訊[在這裡](create-block-sender-lists-in-office-365.md)。

## <a name="options-from-most-to-least-recommended"></a>大部分從 [選項]，以至少建議

因為它們略過多的安全性措施，應該一律會限制您允許清單。 您必須再重新檢查所有允許清單作為您標準維護的一部分，因此您不知道誰允許略過。 請儘可能使用嚴格 Etr 建議。

- Exchange 傳輸規則 （Etr 也稱為的郵件流程規則）
- Outlook 安全寄件者
- 反垃圾郵件原則： IP 允許清單
- 反垃圾郵件原則： 寄件者/網域允許清單

## <a name="using-exchange-transport-rules-etrs-to-allow-specific-senders-recommended"></a>使用 Exchange 傳輸規則 (Etr)，以允許特定寄件者 （建議使用）

若要確保只有合法郵件被允許進入您的組織條件應該是下列其中一項：

- 使用在傳送網域的寄件者驗證狀態。 這是藉由檢查以確定它包含的 Authentication-results 標頭 」 dmarc = 傳遞 」 或 「 dmarc = bestguesspass 」。 這可確保在傳送網域已經通過驗證，並不正在詐騙郵件。 按一下 [更多在[SPF](https://docs.microsoft.com/en-us/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)， [DKIM](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dmarc-to-validate-email)電子郵件驗證。

- 或者，如果在傳送網域沒有驗證，請使用傳送網域*加上*傳送的 IP （或 IP 範圍）。 請確定您已*儘可能限制*的目標在於您執行這項操作以安全。 IP 範圍大於/24*不*建議使用。 避免新增屬於消費者服務或共用的基礎結構的 IP 位址範圍。

> [!IMPORTANT]
> 如果您允許 NATted IP 地址，您應該了解才能知道您允許的範圍相關的 NAT 集區中的機器。 請注意，IP 位址可能會變更，且 NAT 參與者可能太。 您必須重新檢查所有的 [允許] 清單，包括 IP 可讓您標準維護的一部分。

- *（選用）*，新增郵件來自組織外部的條件 （這是隱含的但很好將它新增為帳戶可能未正確設定的內部部署伺服器所要的條件）。

- *或者*，如果您可以識別唯一的任何關鍵字或電子郵件主旨或內文中的片語做為其他條件使用此資訊來進一步限制郵件流程規則所允許的電子郵件訊息。

規則動作必須遵循這個模式：

1. 將垃圾郵件信賴等級 (SCL) 設定為-1 （略過垃圾郵件篩選）。

2. 新增至說規則沒有 X 標頭。 在下列範例中，您可以新增一個簡單的標頭 」 X ETR： 略過垃圾郵件篩選已驗證寄件者`contoso.com`"。 如果您有此規則中的多個網域，您可以變更成適當的標題文字。**當郵件會略過篩選 ETR，因為它加上戳記 sfv: skn X Forefront-反垃圾郵件報告標頭中**（**如果它是在 IP 允許清單中，也加上戳記 IPV:CAL**）。 這將會協助您疑難排解。

![GUI 的略過垃圾郵件篩選。](../media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> 不需設定郵件流程規則與*寄件者網域*做為略過垃圾郵件篩選條件。 此方法會大幅增加的風險濫發垃圾郵件者可以詐騙傳送的網域 （或模擬的完整電子郵件地址） 略過所有垃圾郵件篩選，寄件者驗證檢查，郵件會送達人員的收件匣中。

![如何將 SCL 設定為一個減號。](../media/2-AllowList-SetsSCLMinus1.png)

請勿將新增您自己的網域或受歡迎的網域 (例如： `microsoft.com`) 做為條件的郵件流程規則。 這會被視為高風險，因為它會建立不佳動作項目到所傳送的郵件，否則會篩選出的機會。

[請按一下 [建立 ETR，也稱為郵件流程規則的步驟](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)。

## <a name="use-outlook-safe-senders-end-user-managed"></a>使用 Outlook 安全寄件者 （受管理的使用者）

而不是全域授權位址、 網域或 IP 位址，使用者也可以允許傳送到 Outlook 安全寄件者的地址。 [Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46)和[Outlook 用戶端](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)之間的不同設定此案例的步驟。 **當郵件已成功授權由於安全寄件者時您會看到 SFV:SFE X-Forefront-反垃圾郵件的報告**指出，垃圾郵件/詐騙/釣魚程式篩選會略過。

## <a name="use-anti-spam-policy-ip-allow-lists"></a>使用反垃圾郵件原則 IP 允許清單

當您不可以使用 Etr 來驗證寄件者驗證時，或繫結的網域和 IP 一起全域允許特定寄件者時下, 一個最佳選項是將寄件者新增至*反垃圾郵件原則 IP 允許清單*。 [詳細的步驟，請參閱設定連線篩選器原則的文件](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy)。 請務必保持在最小值的允許 IP 位址清單，並避免使用 IP 位址範圍。 避免新增屬於消費者服務或共用的基礎結構，以及也*請確定*您定期檢閱允許的 IP 位址清單，並移除不再需要的 IP 位址範圍。

> [!CAUTION]
> 設定反垃圾郵件原則來允許架構上唯一的寄件者 IP 位址會導致略過垃圾郵件篩選針對來自該 IP 位址，允許規則中的所有郵件。 這會建立傳送您的郵件，否則會篩選出不佳執行者高風險。此方法也會略過的所有垃圾郵件篩選，寄件者驗證檢查及郵件落在使用者的收件匣，增加的風險。

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>使用反垃圾郵件原則寄件者/網域允許清單

最不適合的選項是授權的寄件者/網域。 此選項應避免使用，*盡可能*完全會略過釣魚程式垃圾郵件/詐騙保護並不會評估寄件者驗證。 此方法會增加壞動作項目從接收郵件的風險，並最佳建議暫時，並只在測試時。 詳細的步驟可以[設定您的垃圾郵件篩選原則](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)的文件中找到。

這些清單的最大限制為大約 1000年項目。

> [!CAUTION]
> 設定反垃圾郵件原則來*允許寄件者/允許網域*將會產生略過垃圾郵件篩選的） 郵件從寄件者的允許清單中或從允許的網域 b） 任何寄件者的郵件。 此方法會大幅增加的風險濫發垃圾郵件者可以詐騙傳送的網域 （或模擬的完整電子郵件地址） 這會略過所有垃圾郵件篩選，寄件者驗證檢查，然後會直接將人員的收件匣] 傳送郵件。
> 
> 請勿加上您自己的網域或受歡迎的網域 (例如： `microsoft.com`) 做為條件的郵件流程規則。 此方法會被視為高風險，因為它會建立傳送郵件，不佳執行者的機會否則進行篩選出、 增加的風險。

> [!IMPORTANT]
> 如需如何建立**封鎖的寄件者清單**的資訊[在這裡](create-block-sender-lists-in-office-365.md)。
