---
title: 新增網域
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 您的組織可能需要多個網域，客戶才能找到您。 瞭解如何將另一個網域新增至您的訂閱。
ms.openlocfilehash: 13fc3cf73a112945db4372231cce70c1837c1321
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706427"
---
# <a name="add-another-domain"></a><span data-ttu-id="f3df5-104">新增另一個網域</span><span class="sxs-lookup"><span data-stu-id="f3df5-104">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="f3df5-105">您的公司可能需要多個功能變數名稱，以用於不同的目的。</span><span class="sxs-lookup"><span data-stu-id="f3df5-105">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="f3df5-106">例如，您可能想要為您的公司名稱新增不同的拼寫，因為客戶已經使用它，而且他們的通訊無法與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="f3df5-106">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="f3df5-107">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="f3df5-107">Try it!</span></span>

1. <span data-ttu-id="f3df5-108">在 Microsoft 365 系統管理中心，選擇 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="f3df5-108">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="f3df5-109">在 [ **取得您的自訂網域設定**] 底下，選取 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="f3df5-109">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="f3df5-110">選擇 [ **管理**]，然後按一下 [ **新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="f3df5-110">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="f3df5-111">輸入您要新增的新功能變數名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f3df5-111">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="f3df5-112">登入您的網域註冊機構，在此案例中 GoDaddy]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f3df5-112">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="f3df5-113">如果出現提示，請登入您的註冊機構，然後選擇 [ **授權**]。</span><span class="sxs-lookup"><span data-stu-id="f3df5-113">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="f3df5-114">選擇 [ **新增我的 DNS 記錄**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f3df5-114">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="f3df5-115">選擇新網域的服務，並清除將由其他網域處理之任何服務的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f3df5-115">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="f3df5-116">例如，如果您只想要使用新網域的電子郵件，請選擇 [ **Exchange**]，然後清除 **商務用 Skype** 和 **適用於 Office 365 的行動裝置管理** 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f3df5-116">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="f3df5-117">選取 **[下一步]**、[**授權** **]、[下一步**]，然後 **完成**</span><span class="sxs-lookup"><span data-stu-id="f3df5-117">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="f3df5-118">已新增您的新網域。</span><span class="sxs-lookup"><span data-stu-id="f3df5-118">Your new domain has been added.</span></span>

<span data-ttu-id="f3df5-119">若要在您的新網域接收電子郵件，您必須為每個使用者新增電子郵件別名：</span><span class="sxs-lookup"><span data-stu-id="f3df5-119">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="f3df5-120">選取 [ **使用者**]、[作用中的 **使用者**]，然後選取將會被指派新別名的使用者。</span><span class="sxs-lookup"><span data-stu-id="f3df5-120">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="f3df5-121">選擇 [ **管理電子郵件別名**]，然後 **新增別名**。</span><span class="sxs-lookup"><span data-stu-id="f3df5-121">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="f3df5-122">輸入使用者名稱，然後從下拉式清單中選擇新的網域。</span><span class="sxs-lookup"><span data-stu-id="f3df5-122">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="f3df5-123">選取 [ **儲存變更**]，然後關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="f3df5-123">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="f3df5-124">針對應該在新網域接收電子郵件的每位使用者，重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="f3df5-124">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="f3df5-125">相關內容</span><span class="sxs-lookup"><span data-stu-id="f3df5-125">Related content</span></span>

<span data-ttu-id="f3df5-126">[將網域新增至 Microsoft 365](../admin/setup/add-domain.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="f3df5-126">[Add a domain to Microsoft 365](../admin/setup/add-domain.md) (article)</span></span>\
<span data-ttu-id="f3df5-127">[新增 DNS 記錄以將您的網域](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="f3df5-127">[Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="f3df5-128">[運用任何網域註冊機構變更名稱伺服器以設定 Microsoft 365](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="f3df5-128">[Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (article)\</span></span>
<span data-ttu-id="f3df5-129">[網域常見問題集](../admin/setup/domains-faq.yml) (文章)</span><span class="sxs-lookup"><span data-stu-id="f3df5-129">[Domains FAQ](../admin/setup/domains-faq.yml) (article)</span></span>