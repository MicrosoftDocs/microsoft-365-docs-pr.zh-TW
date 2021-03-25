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
ms.openlocfilehash: 1aff62792be86b9c77430777c23edc655fe3bb9b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203479"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="1ed8f-103">設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="1ed8f-103">Set up SPF to help prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1ed8f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="1ed8f-104">**Applies to**</span></span>
- [<span data-ttu-id="1ed8f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1ed8f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1ed8f-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="1ed8f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1ed8f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ed8f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1ed8f-108">本文說明如何更新網域名稱服務 (DNS) 記錄，以便可以在 Office 365 中結合使用寄件者原則架構 (SPF) 電子郵件驗證和自訂網域。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-108">This article describes how to update an Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="1ed8f-109">使用 SPF 協助驗證自您自訂網域傳送的輸出電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-109">Using SPF helps to validate outbound email sent from your custom domain.</span></span> <span data-ttu-id="1ed8f-110">這是設定其他推薦的電子郵件驗證方法 DMARC 和 DKIM (Office 365 還支援另外兩種電子郵件驗證方法) 的第一步。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-110">It's a first step in setting up other recommended email authentication methods DMARC and DKIM (two further email authentication methods supported in Office 365).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ed8f-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="1ed8f-111">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ed8f-112">如果您是 **小型企業**，或是不熟悉 IP 位址或 DNS 設定，請致電您的網際網路網域註冊機構 (例如，</span><span class="sxs-lookup"><span data-stu-id="1ed8f-112">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="1ed8f-113">GoDaddy、Bluehost、web.com) 請求有關 SPF 的 DNS 設定 (以及任何其他電子郵件驗證方法) 的協助。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-113">GoDaddy, Bluehost, web.com) to ask for help with DNS configuration of SPF (and any other email authentication method).</span></span> <span data-ttu-id="1ed8f-114">*另外*，如果您尚未購買或未使用自訂 URL (換言之，您和您的客戶瀏覽至 Office 365 的 URL 以 **onmicrosoft.com** 結尾)，已在 Office 365 服務中為您設定 SPF。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-114">*Also*, if you haven't bought, or don't use a custom URL (in other words the URL you and your customers browse to reach Office 365 ends in **onmicrosoft.com**), SPF has been set up for you in the Office 365 service.</span></span> <span data-ttu-id="1ed8f-115">在這種情況下，不需要採取進一步的步驟。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-115">No further steps are required in that case.</span></span> <span data-ttu-id="1ed8f-116">感謝閲讀。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-116">Thanks for reading.</span></span>

<span data-ttu-id="1ed8f-117">在外部 DNS 中為 Office 365 建立或更新 SPF TXT 記錄之前，需要收集一些建立該記錄所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-117">Before you create or update the SPF TXT record for Office 365 in external DNS, you need to gather some information needed to make the record.</span></span> <span data-ttu-id="1ed8f-118">如需進階範例和有關支援的 SPF 語法的更詳細討論，請參閱 [SPF 如何在 Office 365 中運作以防止詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-118">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="1ed8f-119">收集這項資訊：</span><span class="sxs-lookup"><span data-stu-id="1ed8f-119">Gather this information:</span></span>

- <span data-ttu-id="1ed8f-120">自訂網域的目前 SPF TXT 記錄 (如果存在)。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-120">The current SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="1ed8f-121">如需相關指示，請參閱[收集建立 Office 365 DNS 記錄所需的資訊](../../admin/get-help-with-domains/information-for-dns-records.md)。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-121">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="1ed8f-122">前往訊息伺服器並尋找外部 IP 位址 (需要來自所有內部部署訊息伺服器)。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-122">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="1ed8f-123">例如，**131.107.2.200**。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-123">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="1ed8f-p106">要使用的網域名稱，針對您需要包含在 SPF TXT 記錄中的所有協力廠商網域。某些大量郵件提供者已設定要用於他們的客戶的子網域。例如，公司 MailChimp 已設定 **servers.mcsv.net**。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-p106">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="1ed8f-127">確定您想要對 SPF TXT 記錄使用何種強制執行規則。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-127">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="1ed8f-128">建議使用 **-al** l規則。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-128">The **-all** rule is recommended.</span></span> <span data-ttu-id="1ed8f-129">如需其他語法選項的詳細資訊，請參閱 [Office 365 的 SPF TXT 記錄語法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-129">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ed8f-130">如要使用自訂網域，Office 365 要求您將寄件者原則架構 (SPF) TXT 記錄新增至您的 DNS 記錄以協助防止詐騙。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-130">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="1ed8f-131">建立或更新您的 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="1ed8f-131">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="1ed8f-132">請確定您熟悉下表中的 SPF 語法。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-132">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="1ed8f-133">元素</span><span class="sxs-lookup"><span data-stu-id="1ed8f-133">Element</span></span>|<span data-ttu-id="1ed8f-134">如果您正在使用...</span><span class="sxs-lookup"><span data-stu-id="1ed8f-134">If you're using...</span></span>|<span data-ttu-id="1ed8f-135">對客戶通用？</span><span class="sxs-lookup"><span data-stu-id="1ed8f-135">Common for customers?</span></span>|<span data-ttu-id="1ed8f-136">新增此...</span><span class="sxs-lookup"><span data-stu-id="1ed8f-136">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="1ed8f-137">1</span><span class="sxs-lookup"><span data-stu-id="1ed8f-137">1</span></span>|<span data-ttu-id="1ed8f-138">任何電子郵件系統 (必要項)</span><span class="sxs-lookup"><span data-stu-id="1ed8f-138">Any email system (required)</span></span>|<span data-ttu-id="1ed8f-p108">通用。以此值開頭的所有 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="1ed8f-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="1ed8f-141">2</span><span class="sxs-lookup"><span data-stu-id="1ed8f-141">2</span></span>|<span data-ttu-id="1ed8f-142">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1ed8f-142">Exchange Online</span></span>|<span data-ttu-id="1ed8f-143">通用</span><span class="sxs-lookup"><span data-stu-id="1ed8f-143">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="1ed8f-144">3</span><span class="sxs-lookup"><span data-stu-id="1ed8f-144">3</span></span>|<span data-ttu-id="1ed8f-145">僅限 Exchange Online 專用</span><span class="sxs-lookup"><span data-stu-id="1ed8f-145">Exchange Online dedicated only</span></span>|<span data-ttu-id="1ed8f-146">不通用</span><span class="sxs-lookup"><span data-stu-id="1ed8f-146">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="1ed8f-147">4</span><span class="sxs-lookup"><span data-stu-id="1ed8f-147">4</span></span>|<span data-ttu-id="1ed8f-148">僅限 Office 365 德國、Microsoft Cloud 德國</span><span class="sxs-lookup"><span data-stu-id="1ed8f-148">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="1ed8f-149">不通用</span><span class="sxs-lookup"><span data-stu-id="1ed8f-149">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="1ed8f-150">5</span><span class="sxs-lookup"><span data-stu-id="1ed8f-150">5</span></span>|<span data-ttu-id="1ed8f-151">協力廠商電子郵件系統</span><span class="sxs-lookup"><span data-stu-id="1ed8f-151">Third-party email system</span></span>|<span data-ttu-id="1ed8f-152">不通用</span><span class="sxs-lookup"><span data-stu-id="1ed8f-152">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="1ed8f-153">\<domain_name\> 是協力廠商電子郵件系統的網域。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-153">\<domain_name\> is the domain of the third party email system.</span></span>|
   |<span data-ttu-id="1ed8f-154">6</span><span class="sxs-lookup"><span data-stu-id="1ed8f-154">6</span></span>|<span data-ttu-id="1ed8f-p109">內部部署電子郵件系統。例如，Exchange Online Protection 加上另一個電子郵件系統</span><span class="sxs-lookup"><span data-stu-id="1ed8f-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="1ed8f-157">不通用</span><span class="sxs-lookup"><span data-stu-id="1ed8f-157">Not common</span></span>|<span data-ttu-id="1ed8f-158">對每個額外郵件系統使用其中一個︰</span><span class="sxs-lookup"><span data-stu-id="1ed8f-158">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="1ed8f-159">\<IP_address\> 和 \<domain_name\> 是其他郵件系統的 IP 位址和網域，可代表您的網域傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-159">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="1ed8f-160">7</span><span class="sxs-lookup"><span data-stu-id="1ed8f-160">7</span></span>|<span data-ttu-id="1ed8f-161">任何電子郵件系統 (必要項)</span><span class="sxs-lookup"><span data-stu-id="1ed8f-161">Any email system (required)</span></span>|<span data-ttu-id="1ed8f-p110">通用。以此值結束的所有 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="1ed8f-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="1ed8f-164">這可以是數個值其中之一。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-164">This can be one of several values.</span></span> <span data-ttu-id="1ed8f-165">我們建議的值是 `-all`。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-165">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="1ed8f-166">如果您還未這樣做，請使用表格中的語法以形成 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-166">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="1ed8f-167">例如，如果您已完全裝載於 Office 365，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包含 1、2 和 7 的資料列，並且看起來如下：</span><span class="sxs-lookup"><span data-stu-id="1ed8f-167">For example, if you are fully-hosted in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="1ed8f-168">這是最通用的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-168">This is the most common SPF TXT record.</span></span> <span data-ttu-id="1ed8f-169">這筆記錄可供絕大部分人使用，無論您的 Microsoft 資料中心是設於美國、歐洲 (包括德國) 或其他地方。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-169">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="1ed8f-170">不過，如果您已購買 Microsoft Office 365 Germany (為 Microsoft Cloud Germany 德國的一部分)，您應該使用第 4 行所包含的陳述式，而不是第 2 行。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-170">However, if you have purchased Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2.</span></span> <span data-ttu-id="1ed8f-171">例如，如果您已經完全裝載於 Office 365 Germany，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包含 1、4 和 7 的資料列，並且看起來如下：</span><span class="sxs-lookup"><span data-stu-id="1ed8f-171">For example, if you are fully-hosted in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="1ed8f-172">如果您已部署 Office 365，並已為您的自訂網域設定 SPF TXT 記錄，且正在移轉至 Office 365 Germany，您將需要更新 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-172">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="1ed8f-173">若要這麼做，請將 `include:spf.protection.outlook.com` 變更為 `include:spf.protection.outlook.de`。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-173">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="1ed8f-174">一旦您已形成 SPF TXT 記錄，您需要在 DNS 中更新記錄。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-174">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="1ed8f-175">您的網域只能有一個 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-175">You can only have one SPF TXT record for a domain.</span></span> <span data-ttu-id="1ed8f-176">如果存在 SPF TXT 記錄，請不要新增新的記錄，而是必須更新現有的記錄。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-176">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="1ed8f-177">移至[建立 Office 365 的 DNS 記錄](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)，然後按一下您的 DNS 主機的連結。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-177">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then click the link for your DNS host.</span></span>

4. <span data-ttu-id="1ed8f-178">測試您的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-178">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="1ed8f-179">如何處理子網域？</span><span class="sxs-lookup"><span data-stu-id="1ed8f-179">How to handle subdomains?</span></span>

<span data-ttu-id="1ed8f-180">請注意，*你必須為每個子網域建立個別記錄，因為子網域無法獲取最上層網域的 SPF 記錄*。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-180">It is important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top level domain*.</span></span>

<span data-ttu-id="1ed8f-181">每個網域和子網域都需要額外的通配符 SPF 記錄（`*.`），以免攻擊者傳送聲稱為來自不存在之子網域的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-181">An additional wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="1ed8f-182">例如：</span><span class="sxs-lookup"><span data-stu-id="1ed8f-182">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="1ed8f-183">疑難排解 SPF</span><span class="sxs-lookup"><span data-stu-id="1ed8f-183">Troubleshooting SPF</span></span>

<span data-ttu-id="1ed8f-184">無法使用您的 SPF TXT 記錄嗎?</span><span class="sxs-lookup"><span data-stu-id="1ed8f-184">Having trouble with your SPF TXT record?</span></span> <span data-ttu-id="1ed8f-185">請閲讀[疑難排解：Office 365 中 SPF 的最佳做法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-185">Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>


## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="1ed8f-186">SPF 電子郵件驗證實際上做什麼？</span><span class="sxs-lookup"><span data-stu-id="1ed8f-186">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="1ed8f-187">SPF 會識別哪些郵件伺服器可以代表您傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-187">SPF identifies which mail servers are allowed to send mail on your behalf.</span></span> <span data-ttu-id="1ed8f-188">基本上，SPF 以及 DKIM、DMARC 和其他 Office 365 所支援的技術可以協助防止詐騙和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-188">Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing.</span></span> <span data-ttu-id="1ed8f-189">SPF 會新增為 TXT 記錄，DNS 用來識別哪些郵件伺服器可以代表您的網域傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-189">SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain.</span></span> <span data-ttu-id="1ed8f-190">收件者郵件系統參考 SPF TXT 記錄，以判斷您自訂網域的郵件是否來自授權的郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-190">Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="1ed8f-p119">例如，假設您的自訂網域 contoso.com 是使用 Office 365。您新增了 SPF TXT 記錄，而該記錄將 Office 365 訊息伺服器列為您的網域的合法郵件伺服器。當接收郵件伺服器是從 joe@contoso.com 取得訊息時，伺服器就會查閱 contoso.com 的 SPF TXT 記錄，並且找出訊息是否有效。如果接收伺服器發現訊息來自 SPF 記錄中所列的 Office 365 訊息伺服器以外的伺服器，接收郵件伺服器可以選擇將訊息當作垃圾郵件拒絕。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-p119">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="1ed8f-p120">此外，如果您的自訂網域沒有 SPF TXT 記錄，某些接收伺服器可能會拒絕徹底訊息。這是因為接收伺服器無法驗證訊息是來自授權的訊息伺服器。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-p120">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="1ed8f-p121">如果您已經設定 Office 365 的郵件，然後您已經在 DNS 中包含 Microsoft 的訊息伺服器作為 SPF TXT 記錄。不過，在某些情況下，您可能需要在 DNS 中更新您的 SPF TXT 記錄。例如：</span><span class="sxs-lookup"><span data-stu-id="1ed8f-p121">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="1ed8f-p122">以往，如果您是使用 SharePoint Online，您需要新增不同的 SPF TXT 記錄至您的自訂網域。你不再需要這樣做。此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。如果您達到 10 次查閱限制，且收到錯誤，表示「超出查閱限制」和「太多躍點」，請更新您的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-p122">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="1ed8f-204">如果您有 Office 365 與 Exchange 內部部署的混合式環境。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-204">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="1ed8f-205">您想要設定 DKIM 和 DMARC (建議選項)。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-205">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="1ed8f-206">關於 SPF 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="1ed8f-206">More information about SPF</span></span>

<span data-ttu-id="1ed8f-207">如需進階範例、有關支援的 SPF 語法、詐騙、疑難排解，以及 Office 365 如何支援 SPF 的更詳細討論，請參閱 [SPF 如何運作以防止 Office 365 中的詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-207">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="links-to-configure-dkim-and-dmarc"></a><span data-ttu-id="1ed8f-208">用於設定 DKIM 和 DMARC 的連結</span><span class="sxs-lookup"><span data-stu-id="1ed8f-208">Links to configure DKIM and DMARC</span></span>

 <span data-ttu-id="1ed8f-209">SPF 旨在協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-209">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="1ed8f-210">為了防範這些騙術，設定 SPF 之後，應該為 Office 365 設定 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-210">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="1ed8f-211">[DKIM](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide) 電子郵件驗證的目標是證明郵件的內容沒有被篡改。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-211">[DKIM](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="1ed8f-212">[DMARC](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dmarc-to-validate-email?view=o365-worldwide) 電子郵件驗證的目標是確保 SPF 和 DKIM 資訊與寄件者地址相符。</span><span class="sxs-lookup"><span data-stu-id="1ed8f-212">[DMARC](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dmarc-to-validate-email?view=o365-worldwide) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>
