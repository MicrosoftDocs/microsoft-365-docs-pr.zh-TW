---
title: 設定反網路釣魚保護
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何設定反網路釣魚防護。
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701800"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="ce290-103">設定反網路釣魚</span><span class="sxs-lookup"><span data-stu-id="ce290-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="ce290-104">網路釣魚是一種惡意攻擊，其看似來自于熟悉的來源，但它會嘗試收集您的個人資訊。</span><span class="sxs-lookup"><span data-stu-id="ce290-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="ce290-105">根據預設，Microsoft 365 包含一些反網路釣魚保護，但是您可以精煉設定，以提升這種保護。</span><span class="sxs-lookup"><span data-stu-id="ce290-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="ce290-106">讓我們看看。</span><span class="sxs-lookup"><span data-stu-id="ce290-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="ce290-107">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="ce290-107">Try it!</span></span>

1. <span data-ttu-id="ce290-108">在系統管理中心中 [https://admin.microsoft.com](https://admin.microsoft.com) ，選取 [ **安全性**]、[ **威脅管理**]、[ **原則**]，然後按一下 [ **ATP 反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="ce290-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="ce290-109">選取 [ **預設原則** ] 以提煉。</span><span class="sxs-lookup"><span data-stu-id="ce290-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="ce290-110">在 [ **類比** ] 區段中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ce290-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="ce290-111">移至 [ **新增要保護的網域** ]，然後選取 [切換] 以自動包含您擁有的網域。</span><span class="sxs-lookup"><span data-stu-id="ce290-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="ce290-112">移至 [ **動作**]， **如果模仿的使用者傳送電子郵件**，請開啟下拉式清單，然後選擇您想要的動作。</span><span class="sxs-lookup"><span data-stu-id="ce290-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="ce290-113">如果模擬的 **網域傳送電子郵件** ，並選擇您想要的動作，請開啟下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="ce290-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="ce290-114">選取 [ **開啟模擬安全性秘訣**]。</span><span class="sxs-lookup"><span data-stu-id="ce290-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="ce290-115">選擇當系統偵測模擬的使用者、網域或不尋常的字元時，是否應為使用者提供秘訣。</span><span class="sxs-lookup"><span data-stu-id="ce290-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="ce290-116">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="ce290-116">Select **Save**.</span></span>
1. <span data-ttu-id="ce290-117">選取 [ **信箱智慧** ]，然後確認已開啟。</span><span class="sxs-lookup"><span data-stu-id="ce290-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="ce290-118">這可讓您的電子郵件更有效率地瞭解使用模式。</span><span class="sxs-lookup"><span data-stu-id="ce290-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="ce290-119">選擇 [ **新增信任的寄件者和網域**]。</span><span class="sxs-lookup"><span data-stu-id="ce290-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="ce290-120">您可以在這裡新增不應該歸類為模仿的電子郵件地址或網域。</span><span class="sxs-lookup"><span data-stu-id="ce290-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="ce290-121">選擇 [ **檢查您的設定**]，確定所有專案正確無誤，然後選取 [ **儲存**]，然後 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="ce290-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="ce290-122">您的組織現在具有網路釣魚威脅的更佳防護。</span><span class="sxs-lookup"><span data-stu-id="ce290-122">Your organization now has better protection from phishing threats.</span></span>