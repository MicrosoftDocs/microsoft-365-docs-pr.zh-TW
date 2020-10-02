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
ms.openlocfilehash: e53facc12ed8ad2b702d2d0514aebe0068c097b7
ms.sourcegitcommit: 61ef32f802a1fb6d1e3a3aa005764ead32a7951e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48318169"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="a1792-103">設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="a1792-103">Set up SPF to help prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

 <span data-ttu-id="a1792-p101">**摘要：** 本文說明如何更新網域名稱服務 (DNS) 記錄，使您可以在 Office 365 內的自訂網域中使用寄件者原則架構 (SPF)。使用 SPF 協助驗證自您自訂網域傳送的輸出電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a1792-p101">**Summary:** This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF) with your custom domain in Office 365. Using SPF helps to validate outbound email sent from your custom domain.</span></span>

<span data-ttu-id="a1792-p102">如要使用自訂網域，Office 365 要求您將寄件者原則架構 (SPF) TXT 記錄新增至您的 DNS 記錄以協助防止詐騙。SPF 會識別哪些郵件伺服器可以代表您傳送郵件。基本上，SPF 以及 DKIM、DMARC 和其他 Office 365 所支援的技術可以協助防止詐騙和網路釣魚。SPF 會新增為 TXT 記錄，DNS 用來識別哪些郵件伺服器可以代表您的自訂網域傳送郵件。收件者郵件系統參考 SPF TXT 記錄，以判斷您自訂網域的郵件是否來自授權的郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="a1792-p102">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing. SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="a1792-p103">例如，假設您的自訂網域 contoso.com 是使用 Office 365。您新增了 SPF TXT 記錄，而該記錄將 Office 365 訊息伺服器列為您的網域的合法郵件伺服器。當接收郵件伺服器是從 joe@contoso.com 取得訊息時，伺服器就會查閱 contoso.com 的 SPF TXT 記錄，並且找出訊息是否有效。如果接收伺服器發現訊息來自 SPF 記錄中所列的 Office 365 訊息伺服器以外的伺服器，接收郵件伺服器可以選擇將訊息當作垃圾郵件拒絕。</span><span class="sxs-lookup"><span data-stu-id="a1792-p103">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="a1792-p104">此外，如果您的自訂網域沒有 SPF TXT 記錄，某些接收伺服器可能會拒絕徹底訊息。這是因為接收伺服器無法驗證訊息是來自授權的訊息伺服器。</span><span class="sxs-lookup"><span data-stu-id="a1792-p104">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="a1792-p105">如果您已經設定 Office 365 的郵件，然後您已經在 DNS 中包含 Microsoft 的訊息伺服器作為 SPF TXT 記錄。不過，在某些情況下，您可能需要在 DNS 中更新您的 SPF TXT 記錄。例如：</span><span class="sxs-lookup"><span data-stu-id="a1792-p105">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="a1792-p106">以往，如果您是使用 SharePoint Online，您需要新增不同的 SPF TXT 記錄至您的自訂網域。你不再需要這樣做。此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。如果您達到 10 次查閱限制，且收到錯誤，表示「超出查閱限制」和「太多躍點」，請更新您的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="a1792-p106">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="a1792-124">如果您有 Office 365 與 Exchange 內部部署的混合式環境。</span><span class="sxs-lookup"><span data-stu-id="a1792-124">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="a1792-125">您想要設定 DKIM 和 DMARC (建議選項)。</span><span class="sxs-lookup"><span data-stu-id="a1792-125">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="updating-your-spf-txt-record-for-office-365"></a><span data-ttu-id="a1792-126">更新 Office 365 的 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="a1792-126">Updating your SPF TXT record for Office 365</span></span>

<span data-ttu-id="a1792-p107">在 DNS 中更新 TXT 記錄之前，您需要收集一些資訊，並判斷記錄的格式。這有助於防止產生 DNS 錯誤。如需進階範例和有關支援的 SPF 語法的更詳細討論，請參閱 [SPF 如何運作以防止 Office 365 中的詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="a1792-p107">Before you update the TXT record in DNS, you need to gather some information and determine the format of the record. This will help prevent you from generating DNS errors. For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="a1792-130">收集這項資訊：</span><span class="sxs-lookup"><span data-stu-id="a1792-130">Gather this information:</span></span>

- <span data-ttu-id="a1792-p108">您網域的目前 SPF TXT 記錄。如需相關指示，請參閱[收集建立 Office 365 DNS 記錄所需的資訊](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)。</span><span class="sxs-lookup"><span data-stu-id="a1792-p108">The current SPF TXT record for your custom domain. For instructions, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span>

- <span data-ttu-id="a1792-p109">所有內部部署訊息伺服器的外部 IP 位址。例如，**131.107.2.200**。</span><span class="sxs-lookup"><span data-stu-id="a1792-p109">External IP addresses of all on-premises messaging servers. For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="a1792-p110">要使用的網域名稱，針對您需要包含在 SPF TXT 記錄中的所有協力廠商網域。某些大量郵件提供者已設定要用於他們的客戶的子網域。例如，公司 MailChimp 已設定 **servers.mcsv.net**。</span><span class="sxs-lookup"><span data-stu-id="a1792-p110">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="a1792-p111">決定您想要對 SPF TXT 記錄使用何種強制執行規則。我們建議 **-all**。如需其他語法選項的詳細資訊，請參閱 [Office 365 的 SPF TXT 記錄語法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。</span><span class="sxs-lookup"><span data-stu-id="a1792-p111">Determine what enforcement rule you want to use for your SPF TXT record. We recommend **-all**. For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

### <a name="to-add-or-update-your-spf-txt-record"></a><span data-ttu-id="a1792-141">若要新增或更新 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="a1792-141">To add or update your SPF TXT record</span></span>

1. <span data-ttu-id="a1792-142">請確定您熟悉下表中的 SPF 語法。</span><span class="sxs-lookup"><span data-stu-id="a1792-142">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="a1792-143">元素</span><span class="sxs-lookup"><span data-stu-id="a1792-143">Element</span></span>|<span data-ttu-id="a1792-144">如果您正在使用...</span><span class="sxs-lookup"><span data-stu-id="a1792-144">If you're using...</span></span>|<span data-ttu-id="a1792-145">對客戶通用？</span><span class="sxs-lookup"><span data-stu-id="a1792-145">Common for customers?</span></span>|<span data-ttu-id="a1792-146">新增此...</span><span class="sxs-lookup"><span data-stu-id="a1792-146">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="a1792-147">1</span><span class="sxs-lookup"><span data-stu-id="a1792-147">1</span></span>|<span data-ttu-id="a1792-148">任何電子郵件系統 (必要項)</span><span class="sxs-lookup"><span data-stu-id="a1792-148">Any email system (required)</span></span>|<span data-ttu-id="a1792-p112">通用。以此值開頭的所有 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="a1792-p112">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="a1792-151">2</span><span class="sxs-lookup"><span data-stu-id="a1792-151">2</span></span>|<span data-ttu-id="a1792-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a1792-152">Exchange Online</span></span>|<span data-ttu-id="a1792-153">通用</span><span class="sxs-lookup"><span data-stu-id="a1792-153">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="a1792-154">3</span><span class="sxs-lookup"><span data-stu-id="a1792-154">3</span></span>|<span data-ttu-id="a1792-155">僅限 Exchange Online 專用</span><span class="sxs-lookup"><span data-stu-id="a1792-155">Exchange Online dedicated only</span></span>|<span data-ttu-id="a1792-156">不通用</span><span class="sxs-lookup"><span data-stu-id="a1792-156">Not common</span></span>|`ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com`|
   |<span data-ttu-id="a1792-157">4</span><span class="sxs-lookup"><span data-stu-id="a1792-157">4</span></span>|<span data-ttu-id="a1792-158">僅限 Office 365 德國、Microsoft Cloud 德國</span><span class="sxs-lookup"><span data-stu-id="a1792-158">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="a1792-159">不通用</span><span class="sxs-lookup"><span data-stu-id="a1792-159">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="a1792-160">5</span><span class="sxs-lookup"><span data-stu-id="a1792-160">5</span></span>|<span data-ttu-id="a1792-161">協力廠商電子郵件系統</span><span class="sxs-lookup"><span data-stu-id="a1792-161">Third-party email system</span></span>|<span data-ttu-id="a1792-162">不通用</span><span class="sxs-lookup"><span data-stu-id="a1792-162">Not common</span></span>|`include:<domain_name>`  <br/> <span data-ttu-id="a1792-163">其中\<domain_name\> 是協力廠商電子郵件系統的網域。</span><span class="sxs-lookup"><span data-stu-id="a1792-163">Where \<domain_name\> is the domain of the third party email system.</span></span>|
   |<span data-ttu-id="a1792-164">6</span><span class="sxs-lookup"><span data-stu-id="a1792-164">6</span></span>|<span data-ttu-id="a1792-p113">內部部署郵件系統例如，Exchange Online Protection 加上另一個郵件系統</span><span class="sxs-lookup"><span data-stu-id="a1792-p113">On-premises mail system. For example, Exchange Online Protection plus another mail system</span></span>|<span data-ttu-id="a1792-167">不通用</span><span class="sxs-lookup"><span data-stu-id="a1792-167">Not common</span></span>|<span data-ttu-id="a1792-168">對每個額外郵件系統使用其中一個︰</span><span class="sxs-lookup"><span data-stu-id="a1792-168">Use one of these for each additional mail system:</span></span> <br> `ip4:<IP_address>` <br/> `ip6:<IP_address>` <br/> `include:<domain_name>` <br/> <span data-ttu-id="a1792-169">其中 \<IP_address\> 和 \<domain_name\> 是另一個郵件系統的 IP 位址和網域，可代表您的網域傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="a1792-169">Where \<IP_address\> and \<domain_name\> are the IP address and domain of the other mail system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="a1792-170">7</span><span class="sxs-lookup"><span data-stu-id="a1792-170">7</span></span>|<span data-ttu-id="a1792-171">任何電子郵件系統 (必要項)</span><span class="sxs-lookup"><span data-stu-id="a1792-171">Any email system (required)</span></span>|<span data-ttu-id="a1792-p114">通用。以此值結束的所有 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="a1792-p114">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <br/> <span data-ttu-id="a1792-174">這可以是數個值其中之一。</span><span class="sxs-lookup"><span data-stu-id="a1792-174">This can be one of several values.</span></span> <span data-ttu-id="a1792-175">我們建議的值是「-all」。</span><span class="sxs-lookup"><span data-stu-id="a1792-175">We recommend the value \`\`-all\`.</span></span>|
   |

2. <span data-ttu-id="a1792-176">如果您還未這樣做，請使用表格中的語法以形成 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="a1792-176">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="a1792-177">例如，如果您已完全裝載於 Office 365，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包含 1、2 和 7 的資料列，並且看起來如下：</span><span class="sxs-lookup"><span data-stu-id="a1792-177">For example, if you are fully-hosted in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="a1792-178">這是最通用的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="a1792-178">This is the most common SPF TXT record.</span></span> <span data-ttu-id="a1792-179">這筆記錄可供絕大部分人使用，無論您的 Microsoft 資料中心是設於美國、歐洲 (包括德國) 或其他地方。</span><span class="sxs-lookup"><span data-stu-id="a1792-179">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="a1792-180">不過，如果您已購買 Microsoft Office 365 Germany (為 Microsoft Cloud Germany 德國的一部分)，您應該使用第 4 行所包含的陳述式，而不是第 2 行。</span><span class="sxs-lookup"><span data-stu-id="a1792-180">However, if you have purchased Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2.</span></span> <span data-ttu-id="a1792-181">例如，如果您已經完全裝載於 Office 365 Germany，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包含 1、4 和 7 的資料列，並且看起來如下：</span><span class="sxs-lookup"><span data-stu-id="a1792-181">For example, if you are fully-hosted in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="a1792-182">如果您已部署 Office 365，並已為您的自訂網域設定 SPF TXT 記錄，且正在移轉至 Office 365 Germany，您將需要更新 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="a1792-182">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="a1792-183">若要這麼做，請將 `include:spf.protection.outlook.com` 變更為 `include:spf.protection.outlook.de`。</span><span class="sxs-lookup"><span data-stu-id="a1792-183">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="a1792-184">一旦您已形成 SPF TXT 記錄，您需要在 DNS 中更新記錄。</span><span class="sxs-lookup"><span data-stu-id="a1792-184">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="a1792-185">您的網域只能有一個 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="a1792-185">You can only have one SPF TXT record for a domain.</span></span> <span data-ttu-id="a1792-186">如果存在 SPF TXT 記錄，請不要新增新的記錄，而是必須更新現有的記錄。</span><span class="sxs-lookup"><span data-stu-id="a1792-186">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="a1792-187">移至[建立 Office 365 的 DNS 記錄](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)，然後按一下您的 DNS 主機的連結。</span><span class="sxs-lookup"><span data-stu-id="a1792-187">Go to [Create DNS records for Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), and then click the link for your DNS host.</span></span>

4. <span data-ttu-id="a1792-188">測試您的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="a1792-188">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="a1792-189">如何處理子網域？</span><span class="sxs-lookup"><span data-stu-id="a1792-189">How to handle subdomains?</span></span>

<span data-ttu-id="a1792-190">請注意，你必須為每個子網域建立個別記錄，因為子網域無法獲取最上層網域的 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="a1792-190">It is important to note that you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top level domain.</span></span>

<span data-ttu-id="a1792-191">每個網域和子網域都需要額外的通配符 SPF 記錄（`*.`），以免攻擊者傳送聲稱為來自不存在之子網域的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a1792-191">An additional wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="a1792-192">例如：</span><span class="sxs-lookup"><span data-stu-id="a1792-192">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 –all"
```

## <a name="more-information-about-spf"></a><span data-ttu-id="a1792-193">關於 SPF 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a1792-193">More information about SPF</span></span>

<span data-ttu-id="a1792-194">如需進階範例、有關支援的 SPF 語法、詐騙、疑難排解，以及 Office 365 如何支援 SPF 的更詳細討論，請參閱 [SPF 如何運作以防止 Office 365 中的詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="a1792-194">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-after-you-set-up-spf-for-office-365"></a><span data-ttu-id="a1792-195">後續步驟：為 Office 365 設定 SPF 之後</span><span class="sxs-lookup"><span data-stu-id="a1792-195">Next steps: After you set up SPF for Office 365</span></span>

<span data-ttu-id="a1792-p121">無法使用您的 SPF TXT 記錄嗎?請參閱[疑難排解：Office 365 中 SPF 的最佳作法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="a1792-p121">Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

 <span data-ttu-id="a1792-p122">SPF 是設計來協助防止詐騙，但是有 SPF 無法防護的詐騙技術。為了防止這些項目，設定 SPF 之後，您也應該為 Office 365 設定 DKIM 和 DMARC。若要開始使用，請參閱 [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。接下來，請參閱[使用 DMARC 來驗證 Office 365 電子郵件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="a1792-p122">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
