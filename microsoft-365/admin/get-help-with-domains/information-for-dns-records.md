---
title: 收集建立 Office 365 DNS 記錄所需的資訊
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: '了解如何尋找您要建立 Office 365 的 DNS 記錄的值/資訊。 '
ms.custom: okr_smb
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251653"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="303cf-103">收集建立 Office 365 DNS 記錄所需的資訊</span><span class="sxs-lookup"><span data-stu-id="303cf-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="303cf-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="303cf-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="303cf-105">步驟 1： 尋找 TXT 記錄值，並確認</span><span class="sxs-lookup"><span data-stu-id="303cf-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="303cf-106">在 Microsoft 365 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="303cf-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="303cf-107">如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="303cf-107">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="303cf-108">如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="303cf-108">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="303cf-109">在 [**網域**] 頁面上，選取您的網域，然後選取 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="303cf-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="303cf-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span><span class="sxs-lookup"><span data-stu-id="303cf-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="303cf-111">在 [**驗證網域**] 頁面上選取**改為新增 TXT 記錄**，然後選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="303cf-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="303cf-112">複製所顯示的**TXT 值**。</span><span class="sxs-lookup"><span data-stu-id="303cf-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="303cf-113">它看起來像這樣： **MS = msXXXXXXXX**。</span><span class="sxs-lookup"><span data-stu-id="303cf-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="303cf-114">移至[任何 DNS 主機服務提供者處建立 DNS 記錄](create-dns-records-at-any-dns-hosting-provider.md)，並從若要查看的逐步指示的註冊機構的清單中選取您的 DNS 主機。</span><span class="sxs-lookup"><span data-stu-id="303cf-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="303cf-115">按照在您的 DNS 主機建立 TXT 記錄 (或 MX 記錄) 的步驟進行，然後回到 Office 365 中驗證網域。</span><span class="sxs-lookup"><span data-stu-id="303cf-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="303cf-116">從您的 DNS 主機移除 TXT 記錄 （或 MX 記錄），一旦網域驗證 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="303cf-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="303cf-117">步驟 2： 找出電子郵件及其他的 MX 記錄值</span><span class="sxs-lookup"><span data-stu-id="303cf-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="303cf-118">在 Microsoft 365 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="303cf-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="303cf-119">如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="303cf-119">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="303cf-120">如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="303cf-120">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="303cf-121">On the **Domains** page, select your domain.</span><span class="sxs-lookup"><span data-stu-id="303cf-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="303cf-122">Under **Required DNS settings**, you'll see the DNS records to add.</span><span class="sxs-lookup"><span data-stu-id="303cf-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="303cf-123">在您的 DNS 主機進行變更時，您會需要讓這些資訊保持可用，這樣您就能複製並貼上這些值。</span><span class="sxs-lookup"><span data-stu-id="303cf-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="303cf-124">此頁面所列的 DNS 記錄群組取決於您列在 **[網域用途]** 下的選項。</span><span class="sxs-lookup"><span data-stu-id="303cf-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="303cf-125">移至[任何 DNS 主機服務提供者處建立 DNS 記錄](create-dns-records-at-any-dns-hosting-provider.md)，然後再從若要查看在該 DNS 主機的網站新增記錄的逐步指示的註冊機構的清單中選取您的 DNS 主機。</span><span class="sxs-lookup"><span data-stu-id="303cf-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="303cf-126">請在 DNS 主機上遵循相關步驟建立記錄。</span><span class="sxs-lookup"><span data-stu-id="303cf-126">Follow the steps for creating the records at your DNS host.</span></span>
