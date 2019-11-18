---
title: 傳輸中資料的 office 365 加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 摘要： 簡要說明 Microsoft 會在傳輸中的資料的加密。
ms.openlocfilehash: 571a0e28386539058a9998f703d7b4537e1a155a
ms.sourcegitcommit: 93cef4906c5495ae293450ceb52d6cc336f52b53
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690298"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="fe05c-103">傳輸中資料的 office 365 加密</span><span class="sxs-lookup"><span data-stu-id="fe05c-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="fe05c-104">除了靜態的客戶資料保護，Microsoft 會使用加密技術來保護傳輸中的 Office 365 客戶資料。</span><span class="sxs-lookup"><span data-stu-id="fe05c-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="fe05c-105">資料是在傳輸中：</span><span class="sxs-lookup"><span data-stu-id="fe05c-105">Data is in transit:</span></span>

- <span data-ttu-id="fe05c-106">當用戶端電腦與 Office 365 伺服器通訊;</span><span class="sxs-lookup"><span data-stu-id="fe05c-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="fe05c-107">當 Office 365 伺服器進行通訊與另一個 Office 365 伺服器;和</span><span class="sxs-lookup"><span data-stu-id="fe05c-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="fe05c-108">當 Office 365 伺服器會與非 Office 365 伺服器 (例如，Exchange Online 提供的電子郵件至外部的電子郵件伺服器） 通訊。</span><span class="sxs-lookup"><span data-stu-id="fe05c-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="fe05c-109">Office 365 伺服器之間的文字資料中心通訊發生 over TLS 或 IPsec，而所有客戶對向伺服器都交涉與用戶端電腦使用 TLS 的安全工作階段 (例如，使用搭配 256 位元加密強度的 TLS 1.2 的 Exchange Online 使用 (FIPS140-2 層級 2 驗證)。</span><span class="sxs-lookup"><span data-stu-id="fe05c-109">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="fe05c-110">（如需 Office 365 所支援的 TLS 加密套件的清單，請參閱[關於 Office 365 中加密的技術參考細節](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221)）。這適用於用戶端，例如 Outlook、 Skype for Business 和 Outlook 網頁 （例如，HTTP、 POP3 等等） 所使用的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="fe05c-110">(See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="fe05c-111">公用 ca 憑證由 Microsoft IT SSL 使用 SSLAdmin，內部的 Microsoft 工具，以保護傳輸的資訊機密性。</span><span class="sxs-lookup"><span data-stu-id="fe05c-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="fe05c-112">Microsoft IT 所發出的所有憑證 2048 位元至少要都有的長度，並且 Webtrust 合規性需要 SSLAdmin 若要確保只有為了由 Microsoft 所擁有的公用 IP 位址而發出的憑證。</span><span class="sxs-lookup"><span data-stu-id="fe05c-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and Webtrust compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="fe05c-113">無法符合此條件的任何 IP 位址會透過例外狀況處理序路由傳送。</span><span class="sxs-lookup"><span data-stu-id="fe05c-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="fe05c-114">公開可用所有實作詳細資料，例如 TLS 正在使用的版本，是否啟用轉寄密碼 (FS)，加密套件等的順序。</span><span class="sxs-lookup"><span data-stu-id="fe05c-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="fe05c-115">若要查看這些詳細資料的一種方式是使用協力廠商網站，例如[Qualys SSL 實驗室](https://www.ssllabs.com)。</span><span class="sxs-lookup"><span data-stu-id="fe05c-115">One way to see these details is to use a third-party website, such as [Qualys SSL Labs](https://www.ssllabs.com).</span></span> <span data-ttu-id="fe05c-116">下面是自動化的測試頁面的連結，從 Qualys 會顯示下列服務的資訊：</span><span class="sxs-lookup"><span data-stu-id="fe05c-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="fe05c-117">Office 365 入口網站</span><span class="sxs-lookup"><span data-stu-id="fe05c-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="fe05c-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fe05c-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="fe05c-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fe05c-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="fe05c-120">Skype for Business (SIP)</span><span class="sxs-lookup"><span data-stu-id="fe05c-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="fe05c-121">Skype for Business (Web)</span><span class="sxs-lookup"><span data-stu-id="fe05c-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="fe05c-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fe05c-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="fe05c-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe05c-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="fe05c-124">Exchange Online Protection 的 Url 會因租用戶名稱;不過，所有客戶可以都測試 Office 365 中，使用**microsoft com.mail.protection.outlook.com**。</span><span class="sxs-lookup"><span data-stu-id="fe05c-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
