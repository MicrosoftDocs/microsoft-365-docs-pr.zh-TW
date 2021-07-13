---
title: 收集建立 DNS 記錄所需的資訊
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 收集必要的值/資訊，以建立 DNS 記錄以將您的網域連線到您的 Microsoft 365 訂閱。
ms.openlocfilehash: c9869444da2ccb7f96ee01576d966767681c5b49
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393880"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="96624-103">收集建立 DNS 記錄所需的資訊</span><span class="sxs-lookup"><span data-stu-id="96624-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="96624-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="96624-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="96624-105">步驟1：尋找 TXT 記錄值，並確認</span><span class="sxs-lookup"><span data-stu-id="96624-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="96624-106">在 Microsoft 365 系統管理中心中，移至 **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="96624-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="96624-107">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="96624-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="96624-108">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="96624-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="96624-109">在 [ **網域** ] 頁面上，選取您的網域，然後選取 [ **開始設定**]。</span><span class="sxs-lookup"><span data-stu-id="96624-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="96624-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span><span class="sxs-lookup"><span data-stu-id="96624-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="96624-111">在 [ **網域驗證** ] 頁面上，選取 **[新增 TXT 記錄至網域的 DNS 記錄**]，然後選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="96624-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="96624-112">複製所顯示的 **TXT 值** 。</span><span class="sxs-lookup"><span data-stu-id="96624-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="96624-113">它看起來像這樣： **MS=msXXXXXXXX**。</span><span class="sxs-lookup"><span data-stu-id="96624-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="96624-114">移至 [[新增 dns 記錄] 以連接您的網域](create-dns-records-at-any-dns-hosting-provider.md)，然後依照步驟在您的 DNS 主機網站加入記錄。</span><span class="sxs-lookup"><span data-stu-id="96624-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="96624-115">遵循在您的 DNS 主機上建立 TXT 記錄 (或 MX 記錄) 的步驟，然後在 Microsoft 365 中重新驗證網域。</span><span class="sxs-lookup"><span data-stu-id="96624-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="96624-116">在 Microsoft 365 中驗證網域之後，從 DNS 主機移除 TXT 記錄 (或 MX 記錄) 。</span><span class="sxs-lookup"><span data-stu-id="96624-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="96624-117">步驟2：尋找電子郵件及其他專案的 MX 記錄值</span><span class="sxs-lookup"><span data-stu-id="96624-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="96624-118">在 Microsoft 365 系統管理中心中，移至 **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="96624-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="96624-119">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="96624-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="96624-120">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="96624-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="96624-121">On the **Domains** page, select your domain.</span><span class="sxs-lookup"><span data-stu-id="96624-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="96624-122">選擇 [**管理 DNS**]，選取 [**其他選項**] [  >  **新增您自己的 DNS** ]，然後選取 [**繼續**]，查看要新增的 dns 記錄。</span><span class="sxs-lookup"><span data-stu-id="96624-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="96624-123">在您的 DNS 主機進行變更時，您會需要讓這些資訊保持可用，這樣您就能複製並貼上這些值。</span><span class="sxs-lookup"><span data-stu-id="96624-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="96624-124">此頁面所列的 DNS 記錄群組取決於您列在 **[網域用途]** 下的選項。</span><span class="sxs-lookup"><span data-stu-id="96624-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="96624-125">移至 [[新增 dns 記錄] 以連接您的網域](create-dns-records-at-any-dns-hosting-provider.md)，然後依照步驟在您的 DNS 主機網站加入記錄。</span><span class="sxs-lookup"><span data-stu-id="96624-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="96624-126">請在 DNS 主機上遵循相關步驟建立記錄。</span><span class="sxs-lookup"><span data-stu-id="96624-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="96624-127">相關內容</span><span class="sxs-lookup"><span data-stu-id="96624-127">Related content</span></span>

<span data-ttu-id="96624-128">[網域常見問題集](../setup/domains-faq.yml) (文章)</span><span class="sxs-lookup"><span data-stu-id="96624-128">[Domains FAQ](../setup/domains-faq.yml) (article)\</span></span>
<span data-ttu-id="96624-129">[尋找並修正新增網域或 DNS 記錄之後所發生的問題](find-and-fix-issues.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="96624-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)\</span></span>
<span data-ttu-id="96624-130">[管理網域](index.yml) (連結頁面)</span><span class="sxs-lookup"><span data-stu-id="96624-130">[Manage domains](index.yml) (link page)</span></span>