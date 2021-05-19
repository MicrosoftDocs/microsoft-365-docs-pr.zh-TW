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
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="34051-103">設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="34051-103">Set up SPF to help prevent spoofing</span></span>

- [<span data-ttu-id="34051-104">先決條件</span><span class="sxs-lookup"><span data-stu-id="34051-104">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="34051-105">建立或更新您的 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="34051-105">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
- [<span data-ttu-id="34051-106">如何處理子網域？</span><span class="sxs-lookup"><span data-stu-id="34051-106">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="34051-107">SPF 疑難排解</span><span class="sxs-lookup"><span data-stu-id="34051-107">Troubleshooting SPF</span></span>](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

<span data-ttu-id="34051-108">本文說明如何更新網域名稱服務 (DNS) 記錄，以便可以在 Office 365 中和您的自訂網域一起使用寄件者原則架構 (SPF) 電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="34051-108">This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="34051-109">SPF 協助 *驗證* 自您的自訂網域 (來自該網域所指出) 傳送的外寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="34051-109">SPF helps *validate* outbound email sent from your custom domain (is coming from who it says it is).</span></span> <span data-ttu-id="34051-110">這是設定 SPF、[DKIM](use-dkim-to-validate-outbound-email.md) 和 [DMARC](use-dmarc-to-validate-email.md) 的完整建議電子郵件驗證方法的第一步。</span><span class="sxs-lookup"><span data-stu-id="34051-110">It's a first step in setting up the full recommended email authentication methods of SPF, [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

- [<span data-ttu-id="34051-111">先決條件</span><span class="sxs-lookup"><span data-stu-id="34051-111">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="34051-112">建立或更新您的 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="34051-112">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
  - [<span data-ttu-id="34051-113">如何處理子網域？</span><span class="sxs-lookup"><span data-stu-id="34051-113">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="34051-114">SPF 電子郵件驗證實際上做什麼？</span><span class="sxs-lookup"><span data-stu-id="34051-114">What does SPF email authentication actually do?</span></span>](#what-does-spf-email-authentication-actually-do)
  - [<span data-ttu-id="34051-115">疑難排解 SPF</span><span class="sxs-lookup"><span data-stu-id="34051-115">Troubleshooting SPF</span></span>](#troubleshooting-spf)
- [<span data-ttu-id="34051-116">關於 SPF 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="34051-116">More information about SPF</span></span>](#more-information-about-spf)

## <a name="prerequisites"></a><span data-ttu-id="34051-117">必要條件</span><span class="sxs-lookup"><span data-stu-id="34051-117">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34051-118">如果您是 **小型企業**，或是不熟悉 IP 位址或 DNS 設定，請致電您的網際網路網域註冊機構 (例如，</span><span class="sxs-lookup"><span data-stu-id="34051-118">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="34051-119">GoDaddy、Bluehost、web.com) 並請求有關 *SPF 的 DNS 設定* (以及任何其他電子郵件驗證方法) 的協助。</span><span class="sxs-lookup"><span data-stu-id="34051-119">GoDaddy, Bluehost, web.com) & ask for help with *DNS configuration of SPF* (and any other email authentication method).</span></span> <p> <span data-ttu-id="34051-120">**如果您不使用自訂 URL** (且 Office 365 使用的 URL 結束於 **onmicrosoft.com**)，則 SPF 會在 Office 365 服務中為您設定好。</span><span class="sxs-lookup"><span data-stu-id="34051-120">**If you don't use a custom URL** (and the URL used for Office 365 ends in **onmicrosoft.com**), SPF has already been set up for you in the Office 365 service.</span></span>

<span data-ttu-id="34051-121">讓我們開始吧。</span><span class="sxs-lookup"><span data-stu-id="34051-121">Let's get started.</span></span>

<span data-ttu-id="34051-122">Office 365 的 SPF TXT 記錄將在外部 DNS 中針對任何自訂網域或子網域進行。</span><span class="sxs-lookup"><span data-stu-id="34051-122">The SPF TXT record for Office 365 will be made in external DNS for any custom domains or subdomains.</span></span> <span data-ttu-id="34051-123">您需要一些資訊來製作記錄。</span><span class="sxs-lookup"><span data-stu-id="34051-123">You need some information to make the record.</span></span> <span data-ttu-id="34051-124">收集這項資訊：</span><span class="sxs-lookup"><span data-stu-id="34051-124">Gather this information:</span></span>

- <span data-ttu-id="34051-125">自訂網域的 SPF TXT 記錄 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="34051-125">The SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="34051-126">如需相關指示，請參閱[收集建立 Office 365 DNS 記錄所需的資訊](../../admin/get-help-with-domains/information-for-dns-records.md)。</span><span class="sxs-lookup"><span data-stu-id="34051-126">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="34051-127">前往訊息伺服器並尋找外部 IP 位址 (需要來自所有內部部署訊息伺服器)。</span><span class="sxs-lookup"><span data-stu-id="34051-127">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="34051-128">例如，**131.107.2.200**。</span><span class="sxs-lookup"><span data-stu-id="34051-128">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="34051-p106">要使用的網域名稱，針對您需要包含在 SPF TXT 記錄中的所有協力廠商網域。某些大量郵件提供者已設定要用於他們的客戶的子網域。例如，公司 MailChimp 已設定 **servers.mcsv.net**。</span><span class="sxs-lookup"><span data-stu-id="34051-p106">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="34051-132">確定您想要對 SPF TXT 記錄使用何種強制執行規則。</span><span class="sxs-lookup"><span data-stu-id="34051-132">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="34051-133">建議使用 **-al** l規則。</span><span class="sxs-lookup"><span data-stu-id="34051-133">The **-all** rule is recommended.</span></span> <span data-ttu-id="34051-134">如需其他語法選項的詳細資訊，請參閱 [Office 365 的 SPF TXT 記錄語法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。</span><span class="sxs-lookup"><span data-stu-id="34051-134">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34051-135">如要使用自訂網域，Office 365 要求您將寄件者原則架構 (SPF) TXT 記錄新增至您的 DNS 記錄以協助防止詐騙。</span><span class="sxs-lookup"><span data-stu-id="34051-135">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="34051-136">建立或更新您的 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="34051-136">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="34051-137">請確定您熟悉下表中的 SPF 語法。</span><span class="sxs-lookup"><span data-stu-id="34051-137">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="34051-138">元素</span><span class="sxs-lookup"><span data-stu-id="34051-138">Element</span></span>|<span data-ttu-id="34051-139">如果您正在使用...</span><span class="sxs-lookup"><span data-stu-id="34051-139">If you're using...</span></span>|<span data-ttu-id="34051-140">對客戶通用？</span><span class="sxs-lookup"><span data-stu-id="34051-140">Common for customers?</span></span>|<span data-ttu-id="34051-141">新增此...</span><span class="sxs-lookup"><span data-stu-id="34051-141">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="34051-142">1</span><span class="sxs-lookup"><span data-stu-id="34051-142">1</span></span>|<span data-ttu-id="34051-143">任何電子郵件系統 (必要項)</span><span class="sxs-lookup"><span data-stu-id="34051-143">Any email system (required)</span></span>|<span data-ttu-id="34051-p108">通用。以此值開頭的所有 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="34051-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="34051-146">2</span><span class="sxs-lookup"><span data-stu-id="34051-146">2</span></span>|<span data-ttu-id="34051-147">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="34051-147">Exchange Online</span></span>|<span data-ttu-id="34051-148">通用</span><span class="sxs-lookup"><span data-stu-id="34051-148">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="34051-149">3</span><span class="sxs-lookup"><span data-stu-id="34051-149">3</span></span>|<span data-ttu-id="34051-150">僅限 Exchange Online 專用</span><span class="sxs-lookup"><span data-stu-id="34051-150">Exchange Online dedicated only</span></span>|<span data-ttu-id="34051-151">不通用</span><span class="sxs-lookup"><span data-stu-id="34051-151">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="34051-152">4</span><span class="sxs-lookup"><span data-stu-id="34051-152">4</span></span>|<span data-ttu-id="34051-153">僅限 Office 365 德國、Microsoft Cloud 德國</span><span class="sxs-lookup"><span data-stu-id="34051-153">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="34051-154">不通用</span><span class="sxs-lookup"><span data-stu-id="34051-154">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="34051-155">5</span><span class="sxs-lookup"><span data-stu-id="34051-155">5</span></span>|<span data-ttu-id="34051-156">協力廠商電子郵件系統</span><span class="sxs-lookup"><span data-stu-id="34051-156">Third-party email system</span></span>|<span data-ttu-id="34051-157">不通用</span><span class="sxs-lookup"><span data-stu-id="34051-157">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="34051-158">\<domain_name\> 是協力廠商電子郵件系統的網域。</span><span class="sxs-lookup"><span data-stu-id="34051-158">\<domain_name\> is the domain of the third-party email system.</span></span>|
   |<span data-ttu-id="34051-159">6</span><span class="sxs-lookup"><span data-stu-id="34051-159">6</span></span>|<span data-ttu-id="34051-p109">內部部署電子郵件系統。例如，Exchange Online Protection 加上另一個電子郵件系統</span><span class="sxs-lookup"><span data-stu-id="34051-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="34051-162">不通用</span><span class="sxs-lookup"><span data-stu-id="34051-162">Not common</span></span>|<span data-ttu-id="34051-163">對每個額外郵件系統使用其中一個︰</span><span class="sxs-lookup"><span data-stu-id="34051-163">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="34051-164">\<IP_address\> 和 \<domain_name\> 是其他郵件系統的 IP 位址和網域，可代表您的網域傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="34051-164">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="34051-165">7</span><span class="sxs-lookup"><span data-stu-id="34051-165">7</span></span>|<span data-ttu-id="34051-166">任何電子郵件系統 (必要項)</span><span class="sxs-lookup"><span data-stu-id="34051-166">Any email system (required)</span></span>|<span data-ttu-id="34051-p110">通用。以此值結束的所有 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="34051-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="34051-169">這可以是數個值其中之一。</span><span class="sxs-lookup"><span data-stu-id="34051-169">This can be one of several values.</span></span> <span data-ttu-id="34051-170">我們建議的值是 `-all`。</span><span class="sxs-lookup"><span data-stu-id="34051-170">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="34051-171">如果您還未這樣做，請使用表格中的語法以形成 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="34051-171">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="34051-172">例如，如果您已完全託管於 Office 365，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包括 1、2 和 7 的資料列，並且看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="34051-172">For example, if you are hosted entirely in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="34051-173">**以上範例是最通用的 SPF TXT 記錄。**</span><span class="sxs-lookup"><span data-stu-id="34051-173">**The example above is the most common SPF TXT record**.</span></span> <span data-ttu-id="34051-174">這筆記錄可供絕大部分人使用，無論您的 Microsoft 資料中心是設於美國、歐洲 (包括德國) 或其他地方。</span><span class="sxs-lookup"><span data-stu-id="34051-174">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="34051-175">不過，如果您已購買 Office 365 Germany (為 Microsoft Cloud Germany 的一部分)，您應該使用第 4 行所包括的陳述式，而不是第 2 行。</span><span class="sxs-lookup"><span data-stu-id="34051-175">However, if you bought Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2.</span></span> <span data-ttu-id="34051-176">例如，如果您已經完全託管於 Office 365 Germany，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包括 1、4 和 7 的資料列，並且看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="34051-176">For example, if you are hosted entirely in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="34051-177">如果您已部署 Office 365，並已為您的自訂網域設定 SPF TXT 記錄，且正在移轉至 Office 365 Germany，您將需要更新 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="34051-177">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="34051-178">若要這麼做，請將 `include:spf.protection.outlook.com` 變更為 `include:spf.protection.outlook.de`。</span><span class="sxs-lookup"><span data-stu-id="34051-178">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="34051-179">一旦您已形成 SPF TXT 記錄，您需要在 DNS 中更新記錄。</span><span class="sxs-lookup"><span data-stu-id="34051-179">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="34051-180">**您的網域只能有一個 SPF TXT 記錄。**</span><span class="sxs-lookup"><span data-stu-id="34051-180">**You can only have one SPF TXT record for a domain.**</span></span> <span data-ttu-id="34051-181">如果存在 SPF TXT 記錄，而不是新增新的記錄，您必須更新現有的記錄。</span><span class="sxs-lookup"><span data-stu-id="34051-181">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="34051-182">移至 [建立 Office 365 的 DNS 記錄](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)，然後選取您的 DNS 主機的連結。</span><span class="sxs-lookup"><span data-stu-id="34051-182">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then select the link for your DNS host.</span></span>

4. <span data-ttu-id="34051-183">測試您的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="34051-183">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="34051-184">如何處理子網域？</span><span class="sxs-lookup"><span data-stu-id="34051-184">How to handle subdomains?</span></span>

<span data-ttu-id="34051-185">這很重要，請注意，*你必須為每個子網域建立個別記錄，因為子網域無法繼承頂層網域的 SPF 記錄*。</span><span class="sxs-lookup"><span data-stu-id="34051-185">It's important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top-level domain*.</span></span>

<span data-ttu-id="34051-186">每個網域和子網域都需要萬用字元 SPF 記錄 (`*.`)，以免攻擊者傳送聲稱為來自不存在之子網域的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="34051-186">A wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="34051-187">例如：</span><span class="sxs-lookup"><span data-stu-id="34051-187">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="34051-188">疑難排解 SPF</span><span class="sxs-lookup"><span data-stu-id="34051-188">Troubleshooting SPF</span></span>

<span data-ttu-id="34051-p117">無法使用您的 SPF TXT 記錄嗎？請參閱[疑難排解：Office 365 中 SPF 的最佳作法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="34051-p117">Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="34051-191">SPF 電子郵件驗證實際上做什麼？</span><span class="sxs-lookup"><span data-stu-id="34051-191">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="34051-p118">SPF 會識別允許哪些郵件伺服器可以代表您傳送郵件。基本上，SPF 以及 DKIM、DMARC 和其他 Office 365 所支援的技術可以協助防止詐騙和網路釣魚。SPF 會新增為 TXT 記錄，而 DNS 用此記錄來識別哪些郵件伺服器可以代表您的自訂網域傳送郵件。收件者郵件系統參考 SPF TXT 記錄，以判斷您自訂網域的郵件是否來自授權的郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="34051-p118">SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="34051-p119">例如，假設您的自訂網域 contoso.com 是使用 Office 365。您新增了 SPF TXT 記錄，而該記錄將 Office 365 訊息伺服器列為您的網域的合法郵件伺服器。當接收郵件伺服器是從 joe@contoso.com 取得訊息時，伺服器就會查閱 contoso.com 的 SPF TXT 記錄，並且找出訊息是否有效。如果接收伺服器發現訊息來自 SPF 記錄中所列的 Office 365 訊息伺服器以外的伺服器，接收郵件伺服器可以選擇將訊息當作垃圾郵件拒絕。</span><span class="sxs-lookup"><span data-stu-id="34051-p119">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="34051-p120">此外，如果您的自訂網域沒有 SPF TXT 記錄，某些接收伺服器可能會拒絕徹底訊息。這是因為接收伺服器無法驗證訊息是來自授權的訊息伺服器。</span><span class="sxs-lookup"><span data-stu-id="34051-p120">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="34051-p121">如果您已經設定 Office 365 的郵件，然後您已經在 DNS 中包含 Microsoft 的訊息伺服器作為 SPF TXT 記錄。不過，在某些情況下，您可能需要在 DNS 中更新您的 SPF TXT 記錄。例如：</span><span class="sxs-lookup"><span data-stu-id="34051-p121">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="34051-p122">以往，如果您是使用 SharePoint Online，您需要新增不同的 SPF TXT 記錄至您的自訂網域。你不再需要這樣做。此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。如果您達到 10 次查閱限制，且收到錯誤，表示「超出查閱限制」和「太多躍點」，請更新您的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="34051-p122">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="34051-209">如果您有 Office 365 與 Exchange 內部部署的混合式環境。</span><span class="sxs-lookup"><span data-stu-id="34051-209">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="34051-210">您想要設定 DKIM 和 DMARC (建議選項)。</span><span class="sxs-lookup"><span data-stu-id="34051-210">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="34051-211">關於 SPF 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="34051-211">More information about SPF</span></span>

<span data-ttu-id="34051-212">如需進階範例、有關支援的 SPF 語法、詐騙、疑難排解，以及 Office 365 如何支援 SPF 的更詳細討論，請參閱 [SPF 如何運作以防止 Office 365 中的詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="34051-212">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-dkim-and-dmarc"></a><span data-ttu-id="34051-213">下一個步驟：DKIM 和 DMARC</span><span class="sxs-lookup"><span data-stu-id="34051-213">Next Steps: DKIM and DMARC</span></span>

 <span data-ttu-id="34051-214">SPF 旨在協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。</span><span class="sxs-lookup"><span data-stu-id="34051-214">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="34051-215">為了防範這些騙術，設定 SPF 之後，應該為 Office 365 設定 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="34051-215">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="34051-216">[DKIM](use-dkim-to-validate-outbound-email.md) 電子郵件驗證的目標是證明郵件的內容沒有被篡改。</span><span class="sxs-lookup"><span data-stu-id="34051-216">[DKIM](use-dkim-to-validate-outbound-email.md) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="34051-217">[DMARC](use-dmarc-to-validate-email.md) 電子郵件驗證的目標是確保 SPF 和 DKIM 資訊與寄件者地址相符。</span><span class="sxs-lookup"><span data-stu-id="34051-217">[DMARC](use-dmarc-to-validate-email.md) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>

 <span data-ttu-id="34051-218">如需進階範例和有關支援的 SPF 語法的更詳細討論，請參閱 [SPF 如何在 Office 365 中運作以防止詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="34051-218">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="34051-219">*如果您有關於這個文件的意見反應，請在「意見反應」下選取「此頁面」。*</span><span class="sxs-lookup"><span data-stu-id="34051-219">*Select 'This page' under 'Feedback' if you have feedback on this documentation.*</span></span>
