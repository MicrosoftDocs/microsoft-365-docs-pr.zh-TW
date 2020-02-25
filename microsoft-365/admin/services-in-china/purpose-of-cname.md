---
title: MSOID 的 Office 365 CNAME 記錄的用途為何？
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 深入了解 Office 365，可將您導向來驗證程序的最佳伺服器，讓您將 getter 中的 'MSOID' 筆 CNAME 記錄較快的回應。
monikerRange: o365-21vianet
ms.openlocfilehash: fdf728dcaebf65485b1eaed9b41e49f5327e9a41
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252396"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="afd93-103">MSOID 的 Office 365 CNAME 記錄的用途為何？</span><span class="sxs-lookup"><span data-stu-id="afd93-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="afd93-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="afd93-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="afd93-105">下列僅適用於 \* \* 由 21Vianet 運作的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="afd93-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="afd93-p101">您可能會覺得奇怪，為什麼您需要在 Office 365 中新增 "MSOID" CNAME 記錄。 無論您使用何種訂閱，這都是必須針對所有自訂網域而新增的記錄。 為什麼您需要此記錄？ 這是稍有技術性但卻很基本的問題，因為這樣才能將您導向至特定驗證處理程序的最佳伺服器，您因而能更快獲得回應。</span><span class="sxs-lookup"><span data-stu-id="afd93-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="afd93-p102">技術詳細說明：當您執行可與 Office 365 (例如 商務用 Skype Online、Outlook、Windows PowerShell 或 Microsoft Azure Active Directory 同步作業工具) 搭配使用的用戶端應用程式，您的認證必須經過驗證。Office 365 使用 CNAME 記錄以針對您所在位置指向正確的驗證端點，這可確保快速驗證回應時間。</span><span class="sxs-lookup"><span data-stu-id="afd93-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="afd93-p103">如果您的網域已遺失此 CNAME 記錄，這些應用程式會使用美國的預設驗證端點，這表示驗證速度可能會變慢。如果未正確設定此 CNAME 記錄，例如，如果您在 **[指向位址]** 中輸入錯誤，這些應用程式將無法進行驗證。</span><span class="sxs-lookup"><span data-stu-id="afd93-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="afd93-114">**如果 Office 365 管理您的網域 DNS 記錄**Office 365 會為您設定此 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="afd93-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="afd93-115">**如果您要管理您的網域，在您的 DNS 主機的 DNS 記錄**建立此記錄自行遵循[您的 DNS 主機的指示進行](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx)。</span><span class="sxs-lookup"><span data-stu-id="afd93-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx).</span></span>
  
<span data-ttu-id="afd93-116">如果您計劃 Office 365 部署，而且想要深入了解您可能需要新增或更新的所有 DNS 記錄，了解他們在[參照： Office 365 的外部網域名稱系統記錄](https://go.microsoft.com/fwlink/?LinkId=579013)。</span><span class="sxs-lookup"><span data-stu-id="afd93-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).</span></span>
  

