---
title: 當您管理 DNS 記錄時，建立 Office 365 的 DNS 記錄
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: '瞭解如何在您管理 DNS 記錄時，建立由世紀運作之 Office 365 的 DNS 記錄。 '
monikerRange: o365-21vianet
ms.openlocfilehash: c05dc1c84465ea06572021610744f0cbe5aa9fea
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779902"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="cf1a2-103">當您管理 DNS 記錄時，建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="cf1a2-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="cf1a2-104">如需如何建立由世紀運作之 Office 365 之 DNS 記錄的詳細指示，包括郵件路由所需的 MX 記錄，請參閱[在任何 dns 主機服務提供者處建立 dns 記錄（適用于 Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)）。</span><span class="sxs-lookup"><span data-stu-id="cf1a2-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="cf1a2-105">更多選項及部分須知：</span><span class="sxs-lookup"><span data-stu-id="cf1a2-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="cf1a2-106">如果您不知道您網域的 DNS 主機提供者或網域註冊機構，請參閱[尋找您的網域註冊機構或 DNS 主機服務提供者](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1a2-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="cf1a2-107">如需 DNS 記錄功能的說明，請參閱[DNS 基礎](../get-help-with-domains/dns-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1a2-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="cf1a2-108">有些 DNS 主機提供者不會讓您建立所有必要的記錄類型，這會[在您的主機服務提供者不支援 SRV、CNAME、TXT 或](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)重新導向時，造成服務限制。</span><span class="sxs-lookup"><span data-stu-id="cf1a2-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="cf1a2-109">如果提供者不支援 SRV、TXT 或 CNAME 記錄，我們建議您將[網域轉接](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name)至[支援所有必要記錄類型的提供者](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。</span><span class="sxs-lookup"><span data-stu-id="cf1a2-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="cf1a2-110">若要查看所需的 DNS 記錄，並尋找每筆記錄使用的值，包括電子郵件的 MX 記錄，請參閱[收集建立 Office 365 DNS 記錄所需的資訊](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)。</span><span class="sxs-lookup"><span data-stu-id="cf1a2-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="cf1a2-111">如需 DNS 記錄功能的說明，請參閱[DNS 基礎](../get-help-with-domains/dns-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1a2-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

