---
title: 將您的網域連線到 Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在 Microsoft 365 上驗證您的網域並建立 DNS 記錄。
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: 506ee887edbc59956aee11059a7085bc4b22624e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914591"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="91774-103">將您的網域連線到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91774-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="91774-104">如果您沒有新增網域，貴組織中的人員將會使用 onmicrosoft.com 網域的電子郵件地址，直到您新增網域為止。</span><span class="sxs-lookup"><span data-stu-id="91774-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="91774-105">新增使用者之前，請務必先新增您的網域，這樣您就不需要再設定一次。</span><span class="sxs-lookup"><span data-stu-id="91774-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="91774-106">若您在下方找不到所需內容，請[查看網域常見問題集](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="91774-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="91774-107">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="91774-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="91774-108">您將會從系統管理中心網域設定向導取得 MX 記錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="91774-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="91774-109">在您的主機提供者的網站上，新增 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="91774-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="91774-110">請確認欄位已設定為下列的值：</span><span class="sxs-lookup"><span data-stu-id="91774-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="91774-111">記錄類型: `MX`</span><span class="sxs-lookup"><span data-stu-id="91774-111">Record Type: `MX`</span></span>
- <span data-ttu-id="91774-112">優先順序: 設定為可用的最高值，通常為 `0`。</span><span class="sxs-lookup"><span data-stu-id="91774-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="91774-113">主機名稱: `@`</span><span class="sxs-lookup"><span data-stu-id="91774-113">Host Name: `@`</span></span>
- <span data-ttu-id="91774-114">指向 [位址]: 從系統管理中心複製值並貼上。</span><span class="sxs-lookup"><span data-stu-id="91774-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="91774-115">TTL： `3600‎` （或您的提供者預設值）</span><span class="sxs-lookup"><span data-stu-id="91774-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="91774-116">儲存記錄，然後移除任何其他的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="91774-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="91774-117">新增 CNAME 記錄以將使用者與他們的郵箱連結</span><span class="sxs-lookup"><span data-stu-id="91774-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="91774-118">您將會從系統管理中心網域設定精靈取得 CNAME 記錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="91774-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="91774-119">在您的寄存供應商的網站上，新增以下 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="91774-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="91774-120">請確認每個欄位皆已設定為下列的值：</span><span class="sxs-lookup"><span data-stu-id="91774-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="91774-121">記錄類型: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="91774-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="91774-122">主機: 從系統管理中心貼上您複製的值。</span><span class="sxs-lookup"><span data-stu-id="91774-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="91774-123">指向 [位址]: 從系統管理中心複製值並貼上。</span><span class="sxs-lookup"><span data-stu-id="91774-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="91774-124">TTL： `3600‎` （或您的提供者預設值）</span><span class="sxs-lookup"><span data-stu-id="91774-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="91774-125">新增 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="91774-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="91774-126">**在您開始之前:** 如果網域已經有 SPF 記錄，請勿為 Microsoft 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="91774-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="91774-127">請改為將所需的 Microsoft 365 值新增到您主機服務提供者網站的目前記錄中，這樣您就有了一份包含兩組值的 *單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="91774-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="91774-128">在您的主機提供者網站上，編輯現有 SPF 記錄或建立 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="91774-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="91774-129">請確認欄位已設定為下列的值：</span><span class="sxs-lookup"><span data-stu-id="91774-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="91774-130">記錄類型: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="91774-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="91774-131">主機: `@`</span><span class="sxs-lookup"><span data-stu-id="91774-131">Host: `@`</span></span>
- <span data-ttu-id="91774-132">TXT 值: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="91774-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="91774-133">TTL： `3600‎` （或您的提供者預設值）</span><span class="sxs-lookup"><span data-stu-id="91774-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="91774-134">儲存記錄。</span><span class="sxs-lookup"><span data-stu-id="91774-134">Save the record.</span></span>

<span data-ttu-id="91774-135">透過其中一個 [SPF 驗證工具](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 以驗證您的 SPF 記錄</span><span class="sxs-lookup"><span data-stu-id="91774-135">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="91774-136">SPF 是設計來協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。</span><span class="sxs-lookup"><span data-stu-id="91774-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="91774-137">為了防範這些技術，設定 SPF 之後，您也應該為 Microsoft 365 設定 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="91774-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="91774-138">若要開始使用，請參閱[在 Microsoft 365 中使用 DKIM 驗證從您的網域傳送的外寄電子郵件](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) 和 [使用 DMARC 在 Microsoft 365 中驗證電子郵件](../../security/office-365-security/use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="91774-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span></span>

<span data-ttu-id="91774-139">最後，返回系統管理員中心網域設定精靈以完成你的設定。</span><span class="sxs-lookup"><span data-stu-id="91774-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>