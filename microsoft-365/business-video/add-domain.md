---
title: 新增網域
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 瞭解如何將另一個網域新增至您的訂閱。
ms.openlocfilehash: fef3dc06f270b79cc7f9e729b39727c9116b923d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423080"
---
# <a name="add-another-domain"></a><span data-ttu-id="cfb8e-103">新增另一個網域</span><span class="sxs-lookup"><span data-stu-id="cfb8e-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="cfb8e-104">您的公司可能需要多個功能變數名稱，以用於不同的目的。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="cfb8e-105">例如，您可能想要為您的公司名稱新增不同的拼寫，因為客戶已經使用它，而且他們的通訊無法與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="cfb8e-106">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="cfb8e-106">Try it!</span></span>

1. <span data-ttu-id="cfb8e-107">在 Microsoft 365 系統管理中心中，選擇 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="cfb8e-108">在 [ **取得您的自訂網域設定**] 底下，選取 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="cfb8e-109">選擇 [ **管理**]，然後按一下 [ **新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="cfb8e-110">輸入您要新增的新功能變數名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="cfb8e-111">登入您的網域註冊機構，在此案例中 GoDaddy]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="cfb8e-112">如果出現提示，請登入您的註冊機構，然後選擇 [ **授權**]。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="cfb8e-113">選擇 [ **新增我的 DNS 記錄**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="cfb8e-114">選擇新網域的服務，並清除將由其他網域處理之任何服務的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="cfb8e-115">例如，如果您只想要將新的網域用於電子郵件，請選擇 [ **Exchange**]，然後清除 [ **商務用 Skype** ] 和 [ **適用于 Office 365 的行動裝置管理**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="cfb8e-116">選取 **[下一步]**、[**授權** **]、[下一步**]，然後 **完成**</span><span class="sxs-lookup"><span data-stu-id="cfb8e-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="cfb8e-117">已新增您的新網域。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-117">Your new domain has been added.</span></span>

<span data-ttu-id="cfb8e-118">若要在您的新網域接收電子郵件，您必須為每個使用者新增電子郵件別名：</span><span class="sxs-lookup"><span data-stu-id="cfb8e-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="cfb8e-119">選取 [ **使用者**]、[作用中的 **使用者**]，然後選取將會被指派新別名的使用者。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="cfb8e-120">選擇 [ **管理電子郵件別名**]，然後 **新增別名**。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="cfb8e-121">輸入使用者名稱，然後從下拉式清單中選擇新的網域。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="cfb8e-122">選取 [ **儲存變更**]，然後關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="cfb8e-123">針對應該在新網域接收電子郵件的每位使用者，重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="cfb8e-123">Repeat these steps for each user who should receive email at the new domain.</span></span>