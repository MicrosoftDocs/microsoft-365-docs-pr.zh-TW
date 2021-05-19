---
title: 設定 SPF 以協助防止詐騙
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何更新網域名稱服務 (DNS) 記錄，以在 Office 365 內的自訂網域中使用寄件者原則架構 (SPF)。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 828d76b95a1e3f8d1a1851121d28603a1922f486
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538984"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>設定 SPF 以協助防止詐騙

- [先決條件](#prerequisites)
- [建立或更新您的 SPF TXT 記錄](#create-or-update-your-spf-txt-record)
- [如何處理子網域？](#how-to-handle-subdomains)
- [SPF 疑難排解](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

本文說明如何更新網域名稱服務 (DNS) 記錄，以便可以在 Office 365 中和您的自訂網域一起使用寄件者原則架構 (SPF) 電子郵件驗證。

SPF 協助 *驗證* 自您的自訂網域 (來自該網域所指出) 傳送的外寄電子郵件。 這是設定 SPF、[DKIM](use-dkim-to-validate-outbound-email.md) 和 [DMARC](use-dmarc-to-validate-email.md) 的完整建議電子郵件驗證方法的第一步。

- [先決條件](#prerequisites)
- [建立或更新您的 SPF TXT 記錄](#create-or-update-your-spf-txt-record)
  - [如何處理子網域？](#how-to-handle-subdomains)
- [SPF 電子郵件驗證實際上做什麼？](#what-does-spf-email-authentication-actually-do)
  - [疑難排解 SPF](#troubleshooting-spf)
- [關於 SPF 的詳細資訊](#more-information-about-spf)

## <a name="prerequisites"></a>必要條件

> [!IMPORTANT]
> 如果您是 **小型企業**，或是不熟悉 IP 位址或 DNS 設定，請致電您的網際網路網域註冊機構 (例如， GoDaddy、Bluehost、web.com) 並請求有關 *SPF 的 DNS 設定* (以及任何其他電子郵件驗證方法) 的協助。 <p> **如果您不使用自訂 URL** (且 Office 365 使用的 URL 結束於 **onmicrosoft.com**)，則 SPF 會在 Office 365 服務中為您設定好。

讓我們開始吧。

Office 365 的 SPF TXT 記錄將在外部 DNS 中針對任何自訂網域或子網域進行。 您需要一些資訊來製作記錄。 收集這項資訊：

- 自訂網域的 SPF TXT 記錄 (如果有)。 如需相關指示，請參閱[收集建立 Office 365 DNS 記錄所需的資訊](../../admin/get-help-with-domains/information-for-dns-records.md)。

- 前往訊息伺服器並尋找外部 IP 位址 (需要來自所有內部部署訊息伺服器)。 例如，**131.107.2.200**。

- 要使用的網域名稱，針對您需要包含在 SPF TXT 記錄中的所有協力廠商網域。某些大量郵件提供者已設定要用於他們的客戶的子網域。例如，公司 MailChimp 已設定 **servers.mcsv.net**。

- 確定您想要對 SPF TXT 記錄使用何種強制執行規則。 建議使用 **-al** l規則。 如需其他語法選項的詳細資訊，請參閱 [Office 365 的 SPF TXT 記錄語法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。

> [!IMPORTANT]
> 如要使用自訂網域，Office 365 要求您將寄件者原則架構 (SPF) TXT 記錄新增至您的 DNS 記錄以協助防止詐騙。

## <a name="create-or-update-your-spf-txt-record"></a>建立或更新您的 SPF TXT 記錄

1. 請確定您熟悉下表中的 SPF 語法。

   ****

   |元素|如果您正在使用...|對客戶通用？|新增此...|
   |---|---|---|---|
   |1|任何電子郵件系統 (必要項)|通用。以此值開頭的所有 SPF TXT 記錄|`v=spf1`|
   |2|Exchange Online|通用|`include:spf.protection.outlook.com`|
   |3|僅限 Exchange Online 專用|不通用|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4|僅限 Office 365 德國、Microsoft Cloud 德國|不通用|`include:spf.protection.outlook.de`|
   |5|協力廠商電子郵件系統|不通用|`include:<domain_name>` <p> \<domain_name\> 是協力廠商電子郵件系統的網域。|
   |6|內部部署電子郵件系統。例如，Exchange Online Protection 加上另一個電子郵件系統|不通用|對每個額外郵件系統使用其中一個︰ <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> 和 \<domain_name\> 是其他郵件系統的 IP 位址和網域，可代表您的網域傳送電子郵件。|
   |7|任何電子郵件系統 (必要項)|通用。以此值結束的所有 SPF TXT 記錄|`<enforcement rule>` <p> 這可以是數個值其中之一。 我們建議的值是 `-all`。|
   |

2. 如果您還未這樣做，請使用表格中的語法以形成 SPF TXT 記錄。

   例如，如果您已完全託管於 Office 365，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包括 1、2 和 7 的資料列，並且看起來像這樣：

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   **以上範例是最通用的 SPF TXT 記錄。** 這筆記錄可供絕大部分人使用，無論您的 Microsoft 資料中心是設於美國、歐洲 (包括德國) 或其他地方。

   不過，如果您已購買 Office 365 Germany (為 Microsoft Cloud Germany 的一部分)，您應該使用第 4 行所包括的陳述式，而不是第 2 行。 例如，如果您已經完全託管於 Office 365 Germany，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包括 1、4 和 7 的資料列，並且看起來像這樣：

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   如果您已部署 Office 365，並已為您的自訂網域設定 SPF TXT 記錄，且正在移轉至 Office 365 Germany，您將需要更新 SPF TXT 記錄。 若要這麼做，請將 `include:spf.protection.outlook.com` 變更為 `include:spf.protection.outlook.de`。

3. 一旦您已形成 SPF TXT 記錄，您需要在 DNS 中更新記錄。 **您的網域只能有一個 SPF TXT 記錄。** 如果存在 SPF TXT 記錄，而不是新增新的記錄，您必須更新現有的記錄。 移至 [建立 Office 365 的 DNS 記錄](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)，然後選取您的 DNS 主機的連結。

4. 測試您的 SPF TXT 記錄。

## <a name="how-to-handle-subdomains"></a>如何處理子網域？

這很重要，請注意，*你必須為每個子網域建立個別記錄，因為子網域無法繼承頂層網域的 SPF 記錄*。

每個網域和子網域都需要萬用字元 SPF 記錄 (`*.`)，以免攻擊者傳送聲稱為來自不存在之子網域的電子郵件。 例如：

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>疑難排解 SPF

無法使用您的 SPF TXT 記錄嗎？請參閱[疑難排解：Office 365 中 SPF 的最佳作法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。

## <a name="what-does-spf-email-authentication-actually-do"></a>SPF 電子郵件驗證實際上做什麼？

SPF 會識別允許哪些郵件伺服器可以代表您傳送郵件。基本上，SPF 以及 DKIM、DMARC 和其他 Office 365 所支援的技術可以協助防止詐騙和網路釣魚。SPF 會新增為 TXT 記錄，而 DNS 用此記錄來識別哪些郵件伺服器可以代表您的自訂網域傳送郵件。收件者郵件系統參考 SPF TXT 記錄，以判斷您自訂網域的郵件是否來自授權的郵件伺服器。

例如，假設您的自訂網域 contoso.com 是使用 Office 365。您新增了 SPF TXT 記錄，而該記錄將 Office 365 訊息伺服器列為您的網域的合法郵件伺服器。當接收郵件伺服器是從 joe@contoso.com 取得訊息時，伺服器就會查閱 contoso.com 的 SPF TXT 記錄，並且找出訊息是否有效。如果接收伺服器發現訊息來自 SPF 記錄中所列的 Office 365 訊息伺服器以外的伺服器，接收郵件伺服器可以選擇將訊息當作垃圾郵件拒絕。

此外，如果您的自訂網域沒有 SPF TXT 記錄，某些接收伺服器可能會拒絕徹底訊息。這是因為接收伺服器無法驗證訊息是來自授權的訊息伺服器。

如果您已經設定 Office 365 的郵件，然後您已經在 DNS 中包含 Microsoft 的訊息伺服器作為 SPF TXT 記錄。不過，在某些情況下，您可能需要在 DNS 中更新您的 SPF TXT 記錄。例如：

- 以往，如果您是使用 SharePoint Online，您需要新增不同的 SPF TXT 記錄至您的自訂網域。你不再需要這樣做。此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。如果您達到 10 次查閱限制，且收到錯誤，表示「超出查閱限制」和「太多躍點」，請更新您的 SPF TXT 記錄。

- 如果您有 Office 365 與 Exchange 內部部署的混合式環境。

- 您想要設定 DKIM 和 DMARC (建議選項)。

## <a name="more-information-about-spf"></a>關於 SPF 的詳細資訊

如需進階範例、有關支援的 SPF 語法、詐騙、疑難排解，以及 Office 365 如何支援 SPF 的更詳細討論，請參閱 [SPF 如何運作以防止 Office 365 中的詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。

## <a name="next-steps-dkim-and-dmarc"></a>下一個步驟：DKIM 和 DMARC

 SPF 旨在協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。 為了防範這些騙術，設定 SPF 之後，應該為 Office 365 設定 DKIM 和 DMARC。

[DKIM](use-dkim-to-validate-outbound-email.md) 電子郵件驗證的目標是證明郵件的內容沒有被篡改。

[DMARC](use-dmarc-to-validate-email.md) 電子郵件驗證的目標是確保 SPF 和 DKIM 資訊與寄件者地址相符。

 如需進階範例和有關支援的 SPF 語法的更詳細討論，請參閱 [SPF 如何在 Office 365 中運作以防止詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。

*如果您有關於這個文件的意見反應，請在「意見反應」下選取「此頁面」。*
