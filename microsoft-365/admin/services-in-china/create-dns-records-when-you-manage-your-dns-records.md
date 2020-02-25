---
title: 管理您的 DNS 記錄時建立 Office 365 的 DNS 記錄
f1.keywords:
- CSH
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
- Adm_NonTOC
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: '了解如何建立由 21Vianet 運作的 Office 365 DNS 記錄時您管理 DNS 記錄。 '
monikerRange: o365-21vianet
ms.openlocfilehash: 1f7b8330b45d6704d2d56b2c68cfcd37de84207a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254143"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="3ebb4-103">管理您的 DNS 記錄時建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="3ebb4-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="3ebb4-104">如需如何建立 Office 365 21vianet，包括郵件路由，所需的 MX 記錄的 DNS 記錄的詳細指示，請參閱[Office 365 任何 DNS 主機服務提供者處建立 DNS 記錄](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="3ebb4-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="3ebb4-105">更多選項]，並留意一些事項：</span><span class="sxs-lookup"><span data-stu-id="3ebb4-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="3ebb4-106">如果您不知道您網域的 DNS 主機提供者或網域註冊機構，請參閱[尋找您的網域註冊機構或 DNS 主機服務提供者](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="3ebb4-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="3ebb4-107">如需 DNS 記錄的說明執行動作，請參閱[DNS 基本概念](../get-help-with-domains/dns-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="3ebb4-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="3ebb4-108">某些 DNS 主機服務提供者不讓您建立所有必要的記錄類型，使[您的主機服務提供者不支援 SRV，CNAME，TXT 或重新導向時，服務限制](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。</span><span class="sxs-lookup"><span data-stu-id="3ebb4-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="3ebb4-109">如果您的提供者不支援 SRV、 TXT、 或 CNAME 記錄，我們建議，您[將網域移轉](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx)到[所有支援的提供者所需的記錄類型](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。</span><span class="sxs-lookup"><span data-stu-id="3ebb4-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) to a [provider that supports all required record types](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="3ebb4-110">若要查看所需的 DNS 記錄，並找出要使用的每筆記錄，包括電子郵件的 MX 記錄的值，請參閱[收集建立 Office 365 DNS 記錄所需的資訊](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)。</span><span class="sxs-lookup"><span data-stu-id="3ebb4-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e).</span></span> <span data-ttu-id="3ebb4-111">如需 DNS 記錄的說明執行動作，請參閱[DNS 基本概念](../get-help-with-domains/dns-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="3ebb4-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

