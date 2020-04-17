---
title: 收集建立 Office 365 DNS 記錄所需的資訊
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: '瞭解如何尋找您為 Office 365 建立 DNS 記錄所需的值/資訊。 '
ms.custom: okr_smb
ms.openlocfilehash: 2cb45b6a5c07bd50e15e7f2a941be344b5f69038
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540876"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="9bbf5-103">收集建立 Office 365 DNS 記錄所需的資訊</span><span class="sxs-lookup"><span data-stu-id="9bbf5-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="9bbf5-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="9bbf5-105">步驟1：尋找 TXT 記錄值，並確認</span><span class="sxs-lookup"><span data-stu-id="9bbf5-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9bbf5-106">在 Microsoft 365 系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9bbf5-107">在系統管理中心中，移至 [**安裝** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9bbf5-108">在系統管理中心中，移至 [**安裝** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="9bbf5-109">在 [**網域**] 頁面上，選取您的網域，然後選取 [**開始設定**]。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="9bbf5-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span><span class="sxs-lookup"><span data-stu-id="9bbf5-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="9bbf5-111">在 [**驗證網域**] 頁面上，選取 [**新增 TXT 記錄**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="9bbf5-112">複製所顯示的**TXT 值**。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="9bbf5-113">它看起來像這樣： **MS=msXXXXXXXX**。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="9bbf5-114">移至[在任何 DNS 主機服務提供者處建立 dns 記錄](create-dns-records-at-any-dns-hosting-provider.md)，然後從註冊機構清單中選取 dns 主機以查看逐步指示。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="9bbf5-115">按照在您的 DNS 主機建立 TXT 記錄 (或 MX 記錄) 的步驟進行，然後回到 Office 365 中驗證網域。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="9bbf5-116">在 Office 365 中驗證網域之後，從 DNS 主機移除 TXT 記錄（或 MX 記錄）。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="9bbf5-117">步驟2：尋找電子郵件及其他專案的 MX 記錄值</span><span class="sxs-lookup"><span data-stu-id="9bbf5-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9bbf5-118">在 Microsoft 365 系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="9bbf5-119">在系統管理中心中，移至 [**安裝** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9bbf5-120">在系統管理中心中，移至 [**安裝** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="9bbf5-121">On the **Domains** page, select your domain.</span><span class="sxs-lookup"><span data-stu-id="9bbf5-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="9bbf5-122">Under **Required DNS settings**, you'll see the DNS records to add.</span><span class="sxs-lookup"><span data-stu-id="9bbf5-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="9bbf5-123">在您的 DNS 主機進行變更時，您會需要讓這些資訊保持可用，這樣您就能複製並貼上這些值。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="9bbf5-124">此頁面所列的 DNS 記錄群組取決於您列在 **[網域用途]** 下的選項。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="9bbf5-125">移至[任何 DNS 主機服務提供者的 dns 記錄](create-dns-records-at-any-dns-hosting-provider.md)，然後從註冊機構清單中選取您的 dns 主機，以查看在該 dns 主機的網站上新增記錄的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="9bbf5-126">請在 DNS 主機上遵循相關步驟建立記錄。</span><span class="sxs-lookup"><span data-stu-id="9bbf5-126">Follow the steps for creating the records at your DNS host.</span></span>
