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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 收集必要的值/資訊，以建立 DNS 記錄以將您的網域連線到您的 Microsoft 365 訂閱。
ms.openlocfilehash: c8ff30c27e67c8a29b7122ea80a6a33f0594b1b9
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582953"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="7da1e-103">收集建立 DNS 記錄所需的資訊</span><span class="sxs-lookup"><span data-stu-id="7da1e-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="7da1e-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="7da1e-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="7da1e-105">步驟1：尋找 TXT 記錄值，並確認</span><span class="sxs-lookup"><span data-stu-id="7da1e-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7da1e-106">在 Microsoft 365 系統管理中心，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7da1e-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7da1e-107">在系統管理中心中，移至 [ **安裝** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">網域</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7da1e-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7da1e-108">在系統管理中心中，移至 [ **安裝** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">網域</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7da1e-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="7da1e-109">在 [ **網域** ] 頁面上，選取您的網域，然後選取 [ **開始設定**]。</span><span class="sxs-lookup"><span data-stu-id="7da1e-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="7da1e-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span><span class="sxs-lookup"><span data-stu-id="7da1e-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="7da1e-111">在 [ **驗證網域** ] 頁面上，選取 [ **新增 TXT 記錄**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7da1e-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="7da1e-112">複製所顯示的 **TXT 值** 。</span><span class="sxs-lookup"><span data-stu-id="7da1e-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="7da1e-113">它看起來像這樣： **MS=msXXXXXXXX**。</span><span class="sxs-lookup"><span data-stu-id="7da1e-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="7da1e-114">移至 [在任何 DNS 主機服務提供者處建立 dns 記錄](create-dns-records-at-any-dns-hosting-provider.md)，然後從註冊機構清單中選取 dns 主機以查看逐步指示。</span><span class="sxs-lookup"><span data-stu-id="7da1e-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="7da1e-115">遵循在您的 DNS 主機上建立 TXT 記錄 (或 MX 記錄) 的步驟，然後在 Microsoft 365 中重新驗證網域。</span><span class="sxs-lookup"><span data-stu-id="7da1e-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="7da1e-116">在 Microsoft 365 中驗證網域之後，從 DNS 主機移除 TXT 記錄 (或 MX 記錄) 。</span><span class="sxs-lookup"><span data-stu-id="7da1e-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="7da1e-117">步驟2：尋找電子郵件及其他專案的 MX 記錄值</span><span class="sxs-lookup"><span data-stu-id="7da1e-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7da1e-118">在 Microsoft 365 系統管理中心，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7da1e-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="7da1e-119">在系統管理中心中，移至 [ **安裝** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">網域</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7da1e-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7da1e-120">在系統管理中心中，移至 [ **安裝** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">網域</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7da1e-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="7da1e-121">On the **Domains** page, select your domain.</span><span class="sxs-lookup"><span data-stu-id="7da1e-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="7da1e-122">Under **Required DNS settings**, you'll see the DNS records to add.</span><span class="sxs-lookup"><span data-stu-id="7da1e-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="7da1e-123">在您的 DNS 主機進行變更時，您會需要讓這些資訊保持可用，這樣您就能複製並貼上這些值。</span><span class="sxs-lookup"><span data-stu-id="7da1e-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="7da1e-124">此頁面所列的 DNS 記錄群組取決於您列在 **[網域用途]** 下的選項。</span><span class="sxs-lookup"><span data-stu-id="7da1e-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="7da1e-125">移至 [任何 DNS 主機服務提供者的 dns 記錄](create-dns-records-at-any-dns-hosting-provider.md)，然後從註冊機構清單中選取您的 dns 主機，以查看在該 dns 主機的網站上新增記錄的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="7da1e-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="7da1e-126">請在 DNS 主機上遵循相關步驟建立記錄。</span><span class="sxs-lookup"><span data-stu-id="7da1e-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="7da1e-127">相關內容</span><span class="sxs-lookup"><span data-stu-id="7da1e-127">Related content</span></span>

<span data-ttu-id="7da1e-128">[網域常見問題解答](../setup/domains-faq.yml) (篇) </span><span class="sxs-lookup"><span data-stu-id="7da1e-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

<span data-ttu-id="7da1e-129">[尋找並修正新增網域或 DNS 記錄之後所發生的問題](find-and-fix-issues.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="7da1e-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>

<span data-ttu-id="7da1e-130">[管理網域](index.yml) (連結頁面)</span><span class="sxs-lookup"><span data-stu-id="7da1e-130">[Manage domains](index.yml) (link page)</span></span>