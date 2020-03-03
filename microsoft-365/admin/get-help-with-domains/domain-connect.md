---
title: 使用網域連線
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
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: 了解如何使用網域連線啟用註冊機構，並將您的網域新增至 Microsoft 365。
ms.openlocfilehash: 59e2f94fe83f87a5426064e49f0441356fbd732e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362178"
---
# <a name="using-domain-connect"></a><span data-ttu-id="49547-103">使用網域連線</span><span class="sxs-lookup"><span data-stu-id="49547-103">Using Domain Connect</span></span>

 <span data-ttu-id="49547-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="49547-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="49547-105">[網域連線](https://www.domainconnect.org/)啟用註冊機構可讓您新增網域至 Microsoft 365 三步驟程序，在幾分鐘。</span><span class="sxs-lookup"><span data-stu-id="49547-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="49547-106">在精靈中，我們只會確認您擁有該網域，然後自動設定您的網域的記錄，以便電子郵件有 Microsoft 365 及其他 Microsoft 365 服務，例如 Teams，搭配您的網域。</span><span class="sxs-lookup"><span data-stu-id="49547-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="49547-107">啟動設定精靈之前，務必停用瀏覽器中的所有快顯封鎖程式。</span><span class="sxs-lookup"><span data-stu-id="49547-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="49547-108">網域連線登錄器與 Microsoft 365 整合</span><span class="sxs-lookup"><span data-stu-id="49547-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="49547-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="49547-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="49547-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="49547-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="49547-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="49547-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="49547-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="49547-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="49547-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="49547-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="49547-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="49547-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="49547-115">SecureServer 或 WildWestDomains （GoDaddy 轉銷商使用 SecureServer DNS 主機服務）</span><span class="sxs-lookup"><span data-stu-id="49547-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="49547-116">MadDog 網域</span><span class="sxs-lookup"><span data-stu-id="49547-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="49547-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="49547-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="49547-118">我的電子郵件與網站會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="49547-118">What happens to my email and website?</span></span>

<span data-ttu-id="49547-119">您完成安裝之後，您的網域的 MX 記錄已經更新為指向 Microsoft 365，並為您的網域的所有電子郵件都會開始送往 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="49547-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="49547-120">請確認您已針對在您的網域取得電子郵件的每位人員，在 Office 365 中新增使用者並設定信箱。</span><span class="sxs-lookup"><span data-stu-id="49547-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="49547-121">如果您擁有商務用途的網站，該網站將會在原處繼續運作。</span><span class="sxs-lookup"><span data-stu-id="49547-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="49547-122">網域連線設定步驟不會影響您的網站。</span><span class="sxs-lookup"><span data-stu-id="49547-122">The Domain Connect setup steps don't affect your website.</span></span>
