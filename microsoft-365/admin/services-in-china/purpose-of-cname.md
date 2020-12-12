---
title: MSOID 的 Office 365 CNAME 記錄的用途為何？
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 深入瞭解 Office 365 中的 ' MSOID ' CNAME 記錄，可引導您使用最佳的驗證程式伺服器，讓您能更快速地進行回應。
monikerRange: o365-21vianet
ms.openlocfilehash: aea04391768993c40978d94b50817244cd77405c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655481"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="84534-103">MSOID 的 Office 365 CNAME 記錄的用途為何？</span><span class="sxs-lookup"><span data-stu-id="84534-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="84534-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="84534-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="84534-105">下列僅適用于由世紀運作的 \* \* Office 365。</span><span class="sxs-lookup"><span data-stu-id="84534-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="84534-p101">您可能會覺得奇怪，為什麼您需要在 Office 365 中新增 "MSOID" CNAME 記錄。 無論您使用何種訂閱，這都是必須針對所有自訂網域而新增的記錄。 為什麼您需要此記錄？ 這是稍有技術性但卻很基本的問題，因為這樣才能將您導向至特定驗證處理程序的最佳伺服器，您因而能更快獲得回應。</span><span class="sxs-lookup"><span data-stu-id="84534-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="84534-p102">技術詳細說明：當您執行可與 Office 365 (例如 商務用 Skype Online、Outlook、Windows PowerShell 或 Microsoft Azure Active Directory 同步作業工具) 搭配使用的用戶端應用程式，您的認證必須經過驗證。Office 365 使用 CNAME 記錄以針對您所在位置指向正確的驗證端點，這可確保快速驗證回應時間。</span><span class="sxs-lookup"><span data-stu-id="84534-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="84534-p103">如果您的網域已遺失此 CNAME 記錄，這些應用程式會使用美國的預設驗證端點，這表示驗證速度可能會變慢。如果未正確設定此 CNAME 記錄，例如，如果您在 **[指向位址]** 中輸入錯誤，這些應用程式將無法進行驗證。</span><span class="sxs-lookup"><span data-stu-id="84534-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="84534-114">**如果 Office 365 管理您網域的 DNS 記錄，** Office 365 為您設定此 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="84534-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="84534-115">**如果您是在 dns 主機管理網域的 dns 記錄，** 您可以 [遵循 DNS 主機的指示](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)自行建立此記錄。</span><span class="sxs-lookup"><span data-stu-id="84534-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>
  
<span data-ttu-id="84534-116">如果您是在規劃 Office 365 部署，並且想要深入瞭解可能需要新增或更新的所有 DNS 記錄，請參閱 [下列內容： Office 365 的外部網域名稱系統記錄](https://go.microsoft.com/fwlink/?LinkId=579013)。</span><span class="sxs-lookup"><span data-stu-id="84534-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).</span></span>
  

