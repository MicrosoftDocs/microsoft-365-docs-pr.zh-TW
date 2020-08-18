---
title: 將網域從 Microsoft 轉接至其他主機
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: '在這裡尋找將網域從 Microsoft 轉接至另一個註冊機構的步驟。 '
ms.openlocfilehash: 7e00f5ae2c36a06803a3f7a8acd825dcab90805c
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788975"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="e6ac5-103">將網域從 Microsoft 轉接至其他主機</span><span class="sxs-lookup"><span data-stu-id="e6ac5-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="e6ac5-104">您在從 Microsoft 購買網域之後，您無法將 Microsoft 365 網域轉接至另一個註冊機構60天。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="e6ac5-105">_Whois_   查詢會顯示 Microsoft 購買的網域報名者做為通配網域 LLC。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="e6ac5-106">不過，只應該與 microsoft 365 購買的網域聯繫。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="e6ac5-107">請遵循下列步驟，取得 Microsoft 365 的程式碼，然後移至另一個網域註冊機構網站，設定將您的功能變數名稱轉移至新的註冊機構。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="e6ac5-108">傳輸網域</span><span class="sxs-lookup"><span data-stu-id="e6ac5-108">Transfer a domain</span></span>

1. <span data-ttu-id="e6ac5-109">在系統管理中心中，移至 [  **設定**] [   >  **網域**]。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="e6ac5-110"><在 [ **網域** ] 頁面上，選取您要轉接至另一個網域註冊機構的 Microsoft 365 網域，然後選取 [ **檢查健康情況**]。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-110"><On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="e6ac5-111">在頁面頂端，選取 [ **轉移網域**]。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="e6ac5-112">在 [ **選擇要將您的網域轉接至何處** ] 頁面上，選取 **不同的註冊機構**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="e6ac5-113">在 [**解除鎖定網域轉移**] 頁面上，選取 [ **<_您的網域_ > 解除鎖定傳輸**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="e6ac5-114">請檢查您的網域轉接連絡人資訊，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="e6ac5-115">在繼續進行下一個步驟之前，請複製授權碼，並等候大約30分鐘，讓您的網域傳送狀態變更為 [**註冊**] 索引標籤上的 [**轉移未鎖定**]。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="e6ac5-116">移至您想要管理功能變數名稱的網域註冊機構網站。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="e6ac5-117">遵循傳送網域的指導 (搜尋以取得其網站的協助) 。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-117">Follow directions for transferring a domain (search for help on their website).</span></span>

<span data-ttu-id="e6ac5-118">您可以在 Microsoft 365 的 [ **網域**] 頁面上，找到 [授權碼**註冊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-118">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>

9. <span data-ttu-id="e6ac5-119">完成傳輸後，您將會在新的網域註冊機構中更新您的網域。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-119">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="e6ac5-120">若要完成此程式，請回到系統管理中心的 [ **網域** ] 頁面，然後選取 [  **完成網域傳輸**]。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-120">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span>

> [!NOTE]
> <span data-ttu-id="e6ac5-121">Microsoft 365 購買的網域不符合名稱伺服器的變更或在 Microsoft 365 組織之間傳輸網域的資格。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-121">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="e6ac5-122">若有任何一種是必要的，網域註冊必須轉移到另一個註冊機構。</span><span class="sxs-lookup"><span data-stu-id="e6ac5-122">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
