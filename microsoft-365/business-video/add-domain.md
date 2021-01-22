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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將另一個網域新增到您的訂閱。
ms.openlocfilehash: a5df440f3b7e28c2bdbc69f9383a8399ef193ed0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927607"
---
# <a name="add-another-domain"></a><span data-ttu-id="cf0e5-103">新增另一個網域</span><span class="sxs-lookup"><span data-stu-id="cf0e5-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="cf0e5-104">您的公司可能需要多個功能變數名稱以用於不同用途。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="cf0e5-105">例如，您可能想要新增公司名稱的不同拼字，因為客戶已經使用該名稱，而且他們的通訊無法連至您。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="cf0e5-106">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="cf0e5-106">Try it!</span></span>

1. <span data-ttu-id="cf0e5-107">在 Microsoft 365 系統管理中心中 **，選擇設定**。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="cf0e5-108">在 **取得您的自訂網域設定下**，選取的 **View。**</span><span class="sxs-lookup"><span data-stu-id="cf0e5-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="cf0e5-109">選擇 **管理**，然後新增 **網域**。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="cf0e5-110">輸入您想要新增的新功能變數名稱，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="cf0e5-111">請登出您的網域註冊機構，在此案例中為 GoDaddy，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="cf0e5-112">如果系統提示，請註冊您的註冊機構，**然後選擇授權。**</span><span class="sxs-lookup"><span data-stu-id="cf0e5-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="cf0e5-113">選擇 **為我新增 DNS 記錄**，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="cf0e5-114">選擇新網域的服務，並清除由不同網域處理之任何服務的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="cf0e5-115">例如，如果您只想將新網域用於電子郵件，請選擇 **Exchange，** 然後清除商務用 **Skype** 與 **Office 365** 行動裝置管理的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="cf0e5-116">選取 **下一\*\*\*\*個、授權\*\*\*\*、下一個**，然後 **完成**。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="cf0e5-117">您的新網域已新增。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-117">Your new domain has been added.</span></span>

<span data-ttu-id="cf0e5-118">若要接收新網域的電子郵件，您必須為每個使用者新增新的電子郵件別名：</span><span class="sxs-lookup"><span data-stu-id="cf0e5-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="cf0e5-119">選取 **使用者**、 **使用** 中使用者，然後選取將指派新別名的使用者。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="cf0e5-120">選擇 **管理電子郵件別名**，然後新增 **別名**。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="cf0e5-121">輸入使用者名稱，然後從下拉式清單中選擇新的網域。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="cf0e5-122">選取 **儲存變更**，然後關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="cf0e5-123">請針對應該從新網域接收電子郵件的每個使用者重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="cf0e5-123">Repeat these steps for each user who should receive email at the new domain.</span></span>