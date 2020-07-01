---
title: 設定 SPF 以協助防止詐騙
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何更新網域名稱服務 (DNS) 記錄，以在 Office 365 內的自訂網域中使用寄件者原則架構 (SPF)。
ms.openlocfilehash: 93356799967932813252e7db27e7ac796e46cbc6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936934"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>設定 SPF 以協助防止詐騙

 **Summary:** This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF) with your custom domain in Office 365. Using SPF helps to validate outbound email sent from your custom domain.

In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing. SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.

For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.

Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.

If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:

- Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".

- 如果您有 Office 365 與 Exchange 內部部署的混合式環境。

- 您想要設定 DKIM 和 DMARC (建議選項)。

## <a name="updating-your-spf-txt-record-for-office-365"></a>更新 Office 365 的 SPF TXT 記錄

Before you update the TXT record in DNS, you need to gather some information and determine the format of the record. This will help prevent you from generating DNS errors. For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

收集這項資訊：

- The current SPF TXT record for your custom domain. For instructions, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).

- External IP addresses of all on-premises messaging servers. For example, **131.107.2.200**.

- Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.

- Determine what enforcement rule you want to use for your SPF TXT record. We recommend **-all**. For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

### <a name="to-add-or-update-your-spf-txt-record"></a>若要新增或更新 SPF TXT 記錄

1. 請確定您熟悉下表中的 SPF 語法。

   ||**如果您正在使用...**|**對客戶通用？**|**新增此...**|
   |:-----|:-----|:-----|:-----|
   |1|任何電子郵件系統 (必要項)|Common. All SPF TXT records start with this value|v=spf1|
   |2|Exchange Online|通用|include:spf.protection.outlook.com|
   |3|僅限 Exchange Online 專用|不通用|ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com|
   |4|僅限 Office 365 德國、Microsoft Cloud 德國|不通用|include:spf.protection.outlook.de|
   |5|協力廠商電子郵件系統|不通用|包含：\<domain name\>  <br/> 其中網域名稱是協力廠商電子郵件系統的網域名稱。|
   |6|On-premises mail system. For example, Exchange Online Protection plus another mail system|不通用| 對每個額外郵件系統使用其中一個︰ <br> ip4：\<_IP address_\>  <br/>  ip6：\<_IP address_\>  <br/>  包含：\<_domain name_\>  <br/>  其中 \<_IP address_\> 的值是其他郵件系統的 IP 位址，\<_domain name_\> 是代表您的網域傳送郵件的其他郵件系統的網域名稱。|
   |7|任何電子郵件系統 (必要項)|Common. All SPF TXT records end with this value|\<_enforcement rule_\>  <br/> This can be one of several values. We recommend that you use **-all**.|

2. 如果您還未這樣做，請使用表格中的語法以形成 SPF TXT 記錄：

   例如，如果您已完全裝載於 Office 365，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包含 1、2 和 7 的資料列，並且看起來如下：

   `v=spf1 include:spf.protection.outlook.com -all`

   這是最通用的 SPF TXT 記錄。 這筆記錄可供絕大部分人使用，無論您的 Microsoft 資料中心是設於美國、歐洲 (包括德國) 或其他地方。

   不過，如果您已購買 Microsoft Office 365 Germany (為 Microsoft Cloud Germany 德國的一部分)，您應該使用第 4 行所包含的陳述式，而不是第 2 行。 例如，如果您已經完全裝載於 Office 365 Germany，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包含 1、4 和 7 的資料列，並且看起來如下：

   `v=spf1 include:spf.protection.outlook.de -all`

   如果您已部署 Office 365，並已為您的自訂網域設定 SPF TXT 記錄，且正在移轉至 Office 365 Germany，您將需要更新 SPF TXT 記錄。 若要這樣做，請將 **include:spf.protection.outlook.com** 變更至 **include:spf.protection.outlook.de**。

3. 一旦您已形成 SPF TXT 記錄，您需要在 DNS 中更新記錄。 您的網域只能有一個 SPF TXT 記錄。 如果存在 SPF TXT 記錄，請不要新增新的記錄，而是必須更新現有的記錄。 移至[建立 Office 365 的 DNS 記錄](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)，然後按一下您的 DNS 主機的連結。

4. 測試您的 SPF TXT 記錄。

## <a name="more-information-about-spf"></a>關於 SPF 的詳細資訊

如需進階範例、有關支援的 SPF 語法、詐騙、疑難排解，以及 Office 365 如何支援 SPF 的更詳細討論，請參閱 [SPF 如何運作以防止 Office 365 中的詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。

## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>後續步驟：為 Office 365 設定 SPF 之後

Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

 SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).
