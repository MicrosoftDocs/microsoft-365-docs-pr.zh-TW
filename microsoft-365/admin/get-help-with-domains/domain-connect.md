---
title: 使用網域連接
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: 瞭解如何使用啟用網域連線的註冊機構，並將您的網域新增至 Microsoft 365。
ms.openlocfilehash: 70a30201d4b795c7458959b6b2eee14c9b3c7186
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399953"
---
# <a name="using-domain-connect"></a><span data-ttu-id="378a4-103">使用網域連接</span><span class="sxs-lookup"><span data-stu-id="378a4-103">Using Domain Connect</span></span>

 <span data-ttu-id="378a4-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="378a4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="378a4-105">已啟用[網域](https://www.domainconnect.org/)連線註冊機構可讓您將網域新增至 Microsoft 365，並以三個步驟為單位，以分鐘為單位。</span><span class="sxs-lookup"><span data-stu-id="378a4-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="378a4-106">在 [！附注] 中，我們只會確認您擁有網域，然後自動設定您的網域記錄，所以電子郵件會送出至 Microsoft 365 和其他 Microsoft 365 服務，如小組，請與您的網域合作。</span><span class="sxs-lookup"><span data-stu-id="378a4-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="378a4-107">啟動設定精靈之前，務必停用瀏覽器中的所有快顯封鎖程式。</span><span class="sxs-lookup"><span data-stu-id="378a4-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="378a4-108">與 Microsoft 365 整合的網域連接註冊機構</span><span class="sxs-lookup"><span data-stu-id="378a4-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="378a4-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="378a4-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="378a4-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="378a4-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="378a4-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="378a4-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="378a4-112">Wordpress</span><span class="sxs-lookup"><span data-stu-id="378a4-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="378a4-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="378a4-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="378a4-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="378a4-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="378a4-115">SecureServer 或 WildWestDomains （使用 SecureServer DNS 主控的 GoDaddy 轉銷商）</span><span class="sxs-lookup"><span data-stu-id="378a4-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="378a4-116">MadDog 網域</span><span class="sxs-lookup"><span data-stu-id="378a4-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="378a4-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="378a4-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="378a4-118">我的電子郵件和網站會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="378a4-118">What happens to my email and website?</span></span>

<span data-ttu-id="378a4-119">完成設定之後，您的網域的 MX 記錄會更新，以指向 Microsoft 365，而您網域的所有電子郵件都會開始進入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="378a4-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="378a4-120">請確認您已針對在您的網域取得電子郵件的每位人員，在 Office 365 中新增使用者並設定信箱。</span><span class="sxs-lookup"><span data-stu-id="378a4-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="378a4-121">如果您擁有商務用途的網站，該網站將會在原處繼續運作。</span><span class="sxs-lookup"><span data-stu-id="378a4-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="378a4-122">網域連接設定步驟不會影響您的網站。</span><span class="sxs-lookup"><span data-stu-id="378a4-122">The Domain Connect setup steps don't affect your website.</span></span>
